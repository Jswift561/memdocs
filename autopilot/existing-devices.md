---
title: Windows Autopilot for existing devices
description: Modern desktop deployment with Windows Autopilot enables you to easily deploy the latest version of Windows to your existing devices.
ms.prod: windows-client
ms.technology: itpro-deploy
ms.localizationpriority: medium
author: frankroj
ms.author: frankroj
ms.reviewer: jubaptis
manager: aaroncz
ms.date: 08/10/2023
ms.collection: 
  - M365-modern-desktop
  - highpri
  - tier1
ms.topic: how-to
---

# Windows Autopilot deployment for existing devices

*Applies to:*

- Windows 11
- Windows 10

Modern desktop deployment with Windows Autopilot helps you easily deploy the latest version of Windows to your existing devices. The apps you need for work can be automatically installed. If you manage Windows user data with OneDrive for Business, your data is synchronized, so users can resume working right away.

**Windows Autopilot for existing devices** lets you reimage and provision a Windows device for Autopilot user-driven mode using a single, native Configuration Manager task sequence. The existing device can be on-premises domain-joined. The end result is a Windows 10 or Windows 11 device joined to either Azure Active Directory (Azure AD) or Active Directory (hybrid Azure AD join).

> [!NOTE]
>
> The JSON file for Windows Autopilot for existing devices only supports user-driven Azure AD and user-driven hybrid Azure AD Autopilot profiles. Self-deploying and pre-provisioning Autopilot profiles aren't supported with JSON files due to these scenarios requiring TPM attestation.
>
> However, during the Windows Autopilot for existing devices deployment, if the following conditions are true:
>
> - Device is already a Windows Autopilot device before the deployment begins
> - Device has an Autopilot profile assigned to it
>
> then the assigned Autopilot profile takes precedence over the JSON file installed by the task sequence. In this scenario, if the assigned Autopilot profile is either a self-deploying or pre-provisioning Autopilot profile, then the self-deploying and pre-provisioning scenarios are supported.

> [!TIP]
>
> Using Autopilot for existing devices could be used as a method to convert existing hybrid Azure AD devices into Azure AD devices. Using the setting **Converting all targeted devices to Autopilot** in the Autopilot profile doesn't automatically convert existing hybrid Azure AD device in the assigned group(s) into an Azure AD device. The setting only registers the devices in the assigned group(s) for the Autopilot service.

## Prerequisites

- A currently supported version of Microsoft Configuration Manager current branch.
- Assigned Microsoft Intune licenses.
- Azure AD Premium.
- A supported version of Windows 10 or Windows 11 imported into Configuration Manager as an [OS image](/mem/configmgr/osd/get-started/manage-operating-system-images).

> [!NOTE]
>
> Typically, the target device isn't registered with the Windows Autopilot service. If the device is already registered, the assigned profile takes precedence. The Autopilot for existing devices profile only applies if that the online profile times out.

## Configure the Enrollment Status Page (optional)

If you want, you can set up an [enrollment status page](enrollment-status.md) (ESP) for Autopilot using Intune.

1. Open the [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431).

1. Go to **Devices > Enroll Devices > Windows enrollment > Enrollment Status Page** and [Set up the Enrollment Status Page](/mem/intune/enrollment/windows-enrollment-status).

    :::image type="content" source="images/esp-config.png" alt-text="Enrollment status page policy page in Intune.":::

1. Go to **Azure Active Directory > Mobility (MDM and MAM) > Microsoft Intune** and [enable Windows automatic enrollment](/mem/intune/enrollment/windows-enroll#enable-windows-automatic-enrollment). Configure the MDM user scope for some or all users.

    :::image type="content" source="images/mdm-config.png" alt-text="Configure MDM enrollment in Azure.":::

## Install required modules

> [!TIP]
>
> To run the following commands on a computer running Windows Server 2012/2012 R2, first download and install the [Windows Management Framework](https://www.microsoft.com/download/details.aspx?id=54616).

> [!NOTE]
>
> The PowerShell code snippets in this section were updated in July of 2023 to use the Microsoft Graph PowerShell modules instead of the deprecated AzureAD Graph PowerShell modules. The Microsoft Graph PowerShell modules may require approval of additional permissions in Azure AD when they're first used. It was also updated to force using an updated version of the WindowsAutoPilot module. For more information, see [AzureAD](/powershell/module/azuread/) and [Important: Azure AD Graph Retirement and PowerShell Module Deprecation](https://techcommunity.microsoft.com/t5/microsoft-entra-azure-ad-blog/important-azure-ad-graph-retirement-and-powershell-module/ba-p/3848270).

1. On an internet-connected Windows PC or server, open an elevated Windows PowerShell command window.

2. Enter the following commands to install and import the necessary modules:

    ```powershell
    Install-PackageProvider -Name NuGet -MinimumVersion 2.8.5.201 -Force
    Install-Module WindowsAutopilotIntune -MinimumVersion 5.4.0 -Force
    Install-Module Microsoft.Graph.Groups -Force
    Install-Module Microsoft.Graph.Authentication -Force
    Install-Module Microsoft.Graph.Identity.DirectoryManagement -Force

    Import-Module WindowsAutopilotIntune -MinimumVersion 5.4
    Import-Module Microsoft.Graph.Groups
    Import-Module Microsoft.Graph.Authentication
    Import-Module Microsoft.Graph.Identity.DirectoryManagement
    ```

3. Enter the following commands and provide Intune administrative credentials:

    Make sure the user account you specify has sufficient administrative rights.

    ```powershell
    Connect-MgGraph -Scopes "Device.ReadWrite.All", "DeviceManagementManagedDevices.ReadWrite.All", "DeviceManagementServiceConfig.ReadWrite.All", "Domain.ReadWrite.All", "Group.ReadWrite.All", "GroupMember.ReadWrite.All", "User.Read"
    ```

    Windows requests the user and password for your account with a standard Azure AD form. Type your username and password, and then select **Sign in**.

    :::image type="content" source="images/pwd.png" alt-text="Windows form to sign in to your Azure AD account.":::

    The first time Intune Graph APIs are used on a device, it prompts to enable Microsoft Intune PowerShell read and write permissions. To enable these permissions, select **Consent on behalf or your organization** and then **Accept**.

## Get Autopilot profiles for existing devices

Get all the Autopilot profiles available in your Intune tenant, and display them in JSON format:

```powershell
Get-AutopilotProfile | ConvertTo-AutopilotConfigurationJSON
```

See the following sample output:

```powershell
PS C:\> Get-AutopilotProfile | ConvertTo-AutopilotConfigurationJSON
{
    "CloudAssignedTenantId": "1537de22-988c-4e93-b8a5-83890f34a69b",
    "CloudAssignedForcedEnrollment": 1,
    "Version": 2049,
    "Comment_File": "Profile Autopilot Profile",
    "CloudAssignedAadServerData": "{\"ZeroTouchConfig\":{\"CloudAssignedTenantUpn\":\"\",\"ForcedEnrollment\":1,\"CloudAssignedTenantDomain\":\"M365x373186.onmicrosoft.com\"}}",
    "CloudAssignedTenantDomain": "M365x373186.onmicrosoft.com",
    "CloudAssignedDomainJoinMethod": 0,
    "CloudAssignedOobeConfig": 28,
    "ZtdCorrelationId": "7F9E6025-1E13-45F3-BF82-A3E8C5B59EAC"
}
```

Each profile is encapsulated within braces (`{ }`). The previous example displays a single profile.

### JSON file properties

#### Version

_(Number, optional)_

The version number that identifies the format of the JSON file. <!-- For Windows 10 1809, the version specified must be 2049. -->

#### CloudAssignedTenantId

_(GUID, required)_

The Azure AD tenant ID that should be used. This property is the GUID for the tenant, and can be found in properties of the tenant. The value shouldn't include braces.

#### CloudAssignedTenantDomain

_(String, required)_

The Azure AD tenant name that should be used. For example: `tenant.onmicrosoft.com`.

#### CloudAssignedOobeConfig

_(Number, required)_

This property is a bitmap that shows which Autopilot settings were configured.

- 1: SkipCortanaOptIn
- 2: OobeUserNotLocalAdmin
- 4: SkipExpressSettings
- 8: SkipOemRegistration
- 16: SkipEula

#### CloudAssignedDomainJoinMethod

_(Number, required)_

This property specifies whether the device should join Azure AD or Active Directory (hybrid Azure AD join).

- 0: Azure AD-joined
- 1: Hybrid Azure AD-joined

#### CloudAssignedForcedEnrollment

_(Number, required)_

Specifies that the device should require Azure AD join and MDM enrollment.

- 0: Not required
- 1: required

#### ZtdCorrelationId

_(GUID, required)_

A unique GUID (without braces) that's provided to Intune as part of the registration process. This ID is included in the enrollment message as the `OfflineAutopilotEnrollmentCorrelator`. This attribute is present only if enrollment happens on a device registered with Zero Touch Provisioning via offline registration.

#### CloudAssignedAadServerData

_(Encoded JSON string, required)_

An embedded JSON string used for branding. It requires that you enable Azure AD organization branding.

For example:

`"CloudAssignedAadServerData": "{\"ZeroTouchConfig\":{\"CloudAssignedTenantUpn\":\"\",\"CloudAssignedTenantDomain\":\"tenant.onmicrosoft.com\"}}`

#### CloudAssignedDeviceName

_(String, optional)_

The name that's automatically assigned to the computer. This name follows the naming pattern convention configured in the Intune Autopilot profile. You can also specify an explicit name to use.

## Create the JSON file

Save the Autopilot profile as a JSON file in ASCII or ANSI format. Windows PowerShell defaults to Unicode format. So, if you redirect output of the commands to a file, also specify the file format. The following PowerShell example saves the file in ASCII format. The Autopilot profile(s) appears in a subfolder under the folder specified by the `$targetDirectory` variable. By default, the `$targetDirectory` variable is `C:\AutoPilot`, but it can be changed to another location if desired. The subfolder has the name of the Autopilot profile from Intune. If there are multiple Autopilot profiles, each profile has its own subfolder. In each folder, there's a JSON file named **`AutopilotConfigurationFile.json`**

```powershell
Connect-MgGraph -Scopes "Device.ReadWrite.All", "DeviceManagementManagedDevices.ReadWrite.All", "DeviceManagementServiceConfig.ReadWrite.All", "Domain.ReadWrite.All", "Group.ReadWrite.All", "GroupMember.ReadWrite.All", "User.Read"
$AutopilotProfile = Get-AutopilotProfile
$targetDirectory = "C:\Autopilot"
$AutopilotProfile | ForEach-Object {
    New-Item -ItemType Directory -Path "$targetDirectory\$($_.displayName)"
    $_ | ConvertTo-AutopilotConfigurationJSON | Set-Content -Encoding Ascii "$targetDirectory\$($_.displayName)\AutopilotConfigurationFile.json"
}
```

> [!TIP]
>
> If you use the PowerShell cmdlet **Out-File** to redirect the JSON output to a file, it uses Unicode encoding by default. This cmdlet may also truncate long lines. Use the **Set-Content** cmdlet with the `-Encoding ASCII` parameter to set the proper text encoding.

> [!IMPORTANT]
>
> The file name has to be `AutopilotConfigurationFile.json` and encoded as ASCII or ANSI.

You can also save the profile to a text file and edit in Notepad. In Notepad, when you choose **Save as**, select the save as type: **All Files**, and then choose **ANSI** for the **Encoding**.

:::image type="content" source="images/notepad.png" alt-text="Save as ANSI encoding in Notepad.":::

After you save the file, move it to a location for a Microsoft Configuration Manager package source.

> [!IMPORTANT]
>
> The configuration file can only contain one profile. You can use multiple JSON profile files, but each one must be named `AutopilotConfigurationFile.json`. This requirement is for OOBE to follow the Autopilot experience. To use more than one Autopilot profile, create separate Configuration Manager packages.
>
> If you save the file with Unicode or UTF-8 encoding, or save it with a different file name, the Windows OOBE won't follow the Autopilot experience.

## Create a package containing the JSON file

1. In the Configuration Manager console, go to the **Software Library** workspace, expand **Application Management**, and select the **Packages** node.

1. On the ribbon, select **Create Package**.

1. In the Create Package and Program Wizard, enter the following details for the package:

    - _Name_: **Autopilot for existing devices config**
    - Select **This package contains source files**
    - _Source folder_: Specify the UNC network path that contains the `AutopilotConfigurationFile.json` file

    For more information, see [Packages and programs in Configuration Manager](/mem/configmgr/apps/deploy-use/packages-and-programs).

1. For the program, select the _Program Type_: **Don't create a program**

1. Complete the wizard.

> [!NOTE]
>
> If you change user-driven Autopilot profile settings in Intune at a later date, make sure to update the JSON file. Then redistribute the associated Configuration Manager package.

## Create a target collection

> [!NOTE]
>
> You can also choose to reuse an existing collection.

1. In the Configuration Manager console, go to the **Assets and Compliance** workspace, and select the **Device Collections** node.

1. On the ribbon, select **Create**, and then choose **Create Device Collection**.

1. In the Create Device Collection Wizard, enter the following **General** details:

    - _Name_: **Autopilot for existing devices collection**
    - _Comment_: Add an optional comment to further describe the collection
    - _Limiting collection_: **All Systems**

      > [!NOTE]
      >
      > You can optionally choose to use an alternative collection for the limiting collection. The device to be upgraded must be running the Configuration Manager client in the collection that you select.

1. On the **Membership Rules** page, select **Add Rule**. Specify either a direct or query-based collection rule to add the target Windows devices to the new collection.

    For example, if the hostname of the computer to be wiped and reloaded is `PC-01` and you want to use **Name** as the attribute:

    1. Select **Add Rule**, select **Direct Rule** to open the Create Direct Membership Rule Wizard, and select **Next** on the Welcome page.
    1. On the **Search for Resources** page, enter **PC-01** as the **Value**.

        :::image type="content" source="images/pc-01a.png" alt-text="Enter PC-01 as the name to locate for a collection direct membership rule.":::

    1. Select **Next**, and select **PC-01** in the **Resources**.

        :::image type="content" source="images/pc-01b.png" alt-text="Select PC-01 as the resource to add to the collection.":::

1. Complete the wizard with the default settings.

For more information, see [How to create collections in Configuration Manager](/mem/configmgr/core/clients/manage/collections/create-collections).

## Create a task sequence

1. In the Configuration Manager console, go to the **Software Library** workspace, expand **Operating Systems** and select the **Task Sequences** node.

1. On the **Home** ribbon, select **Create Task Sequence**.

1. On the **Create new task sequence** page, select the option to **Deploy Windows Autopilot for existing devices**.

1. On the **Task sequence information** page, specify the following information:

    - A name for the task sequence. For example, **Autopilot for existing devices**.
    - Optionally add a description to better describe the task sequence.
    - Select a boot image. For more information on supported boot image versions, see [Support for the Windows ADK in Configuration Manager](/mem/configmgr/core/plan-design/configs/support-for-windows-adk).

1. On the **Install Windows** page, select the Windows **Image package**. Then configure the following settings:

    - **Image index**: Select either Enterprise, Education, or Professional, as required by your organization.

    - Enable the option to **Partition and format the target computer before installing the operating system**.

    - **Configure task sequence for use with Bitlocker**: If you enable this option, the task sequence includes the steps necessary to enable BitLocker.

    - **Product key**: If you need to specify a product key for Windows activation, enter it here.

    - Select one of the following options to configure the local administrator account in Windows:
        - **Randomly generate the local administrator password and disable the account on all support platforms (recommended)**
        - **Enable the account and specify the local administrator password**

1. On the **Configure Network** page, select the option to **Join a workgroup**.

    > [!IMPORTANT]
    >
    > The Autopilot for existing devices task sequence runs the **Prepare Windows for capture** step, which uses the Windows System Preparation Tool (Sysprep). This action fails if the device is joined to a domain.
    >
    > Sysprep runs with the `/Generalize` parameter, which on Windows 10 version 1909 deletes the Autopilot profile file. The device then boots into the OOBE phase instead of Autopilot. To fix this issue, see [Windows Autopilot - known issues: Windows Autopilot for existing devices doesn't work for Windows 10, version 1903 or 1909](known-issues.md#windows-autopilot-for-existing-devices-doesnt-work-for-windows-10-version-1903-or-1909).

1. On the **Install Configuration manager** page, add any necessary installation properties for your environment.

    > [!TIP]
    >
    > The task sequence only needs this information if the Configuration Manager client components are needed during the task sequence before Sysprep runs. For example, to install software updates or applications. If you're not doing these actions, the client isn't needed. It's uninstalled before the task sequence runs Sysprep.

1. The **Include updates** page selects by default the option to **Do not install any software updates**.

    > [!TIP]
    >
    > Use offline image servicing to keep the image up to date with the latest Windows cumulative updates. For more information, see [Apply software updates to an image](/mem/configmgr/osd/get-started/manage-operating-system-images#apply-software-updates-to-an-image).

1. On the **Install applications** page, you can select applications to install during the task sequence. However, Microsoft recommends that you mirror the signature image approach with this scenario. After the device provisions with Autopilot, apply all applications and configurations from Microsoft Intune or Configuration Manager co-management. This process provides a consistent experience between users receiving new devices and those using Windows Autopilot for existing devices.  

1. On the **System Preparation** page, select the package that includes the Autopilot configuration file. By default, the task sequence restarts the computer after it runs Windows Sysprep. You can also select the option to **Shutdown computer after this task sequence completes**. This option lets you prepare a device and then deliver it to a user for a consistent Autopilot experience.

1. Complete the wizard.

The Windows Autopilot for existing devices task sequence results in a device joined to Azure AD.

For more information on creating the task sequence, including information on other wizard options, see [Create a task sequence to install an OS](/mem/configmgr/osd/deploy-use/create-a-task-sequence-to-install-an-operating-system).

If you edit the task sequence, it's similar to the default task sequence to apply an existing OS image. This task sequence includes the following extra steps:

- **Apply Windows Autopilot configuration**: This step applies the Autopilot configuration file from the specified package. It's not a new type of step, it's a **Run Command Line** step to copy the file.

- **Prepare Windows for Capture**: This step runs Windows Sysprep, and has the setting to **Shutdown the computer after running this action**. For more information, see [Prepare Windows for Capture](/mem/configmgr/osd/understand/task-sequence-steps#BKMK_PrepareWindowsforCapture).

For more information on editing the task sequence, see [Use the task sequence editor](/mem/configmgr/osd/understand/task-sequence-editor) and [Task sequence steps](/mem/configmgr/osd/understand/task-sequence-steps).

> [!NOTE]
>
> The **Prepare Windows for Capture** step deletes the `AutopilotConfigurationFile.json` file. For more information and a workaround, see [Windows Autopilot - known issues: Windows Autopilot for existing devices doesn't work for Windows 10, version 1903 or 1909](known-issues.md#windows-autopilot-for-existing-devices-doesnt-work-for-windows-10-version-1903-or-1909).

To make sure the user's data is backed up before the Windows 10 upgrade, use OneDrive for Business [known folder move](/onedrive/redirect-known-folders).

## Distribute content to distribution points

Next distribute all content required for the task sequence to distribution points.

1. Select the **Autopilot for existing devices** task sequence, and in the ribbon select **Distribute Content**.

1. On the **Specify the content destination** page, select **Add** to specify either a **Distribution Point** or **Distribution Point Group**.

1. Specify content destinations that let the devices get the content.

1. When you're finished specifying content distribution, complete the wizard.

For more information, see [Manage task sequences to automate tasks](/mem/configmgr/osd/deploy-use/manage-task-sequences-to-automate-tasks).

## Deploy the Autopilot task sequence

1. Select the **Autopilot for existing devices** task sequence, and in the ribbon select **Deploy**.

1. In the Deploy Software Wizard, specify the following details:

    - **General**

      - _Task Sequence_: **Autopilot for existing devices**

      - _Collection_: **Autopilot for existing devices collection**

    - **Deployment Settings**

      - _Action_: **Install**.

      - _Purpose_: **Available**. You can optionally select **Required** instead of **Available**. A required purpose isn't recommended during testing.

      - _Make available to the following_: **Only Configuration Manager Clients**.

        > [!NOTE]
        >
        > Choose the option here that is relevant for the context of your test. If the target client doesn't have the Configuration Manager agent or Windows installed, you must select an option that includes PXE or Boot Media.

    - **Scheduling**

      - Set a time for when this deployment becomes available

    - **User Experience**

      - Select **Show Task Sequence progress**

    - **Distribution Points**

      - _Deployment options_: **Download content locally when needed by the running task sequence**

1. Complete the wizard.

## Complete the deployment process

1. On the target Windows device, go to the **Start** menu, type `Software Center`, and open it.

2. In the Software Library, under **Operating Systems**, select **Autopilot for existing devices**, and then select **Install**. For example:

    :::image type="content" source="images/sc.png" alt-text="Autopilot for existing devices task sequence in Software Center.":::

    :::image type="content" source="images/sc1.png" alt-text="Software Center notice to confirm you want to upgrade the OS on this computer.":::

The task sequence runs and does the following actions:

1. Download content
1. Restart the device
1. Format the drive
1. Install Windows from the specified OS image

    :::image type="content" source="images/up-1.PNG" alt-text="Task sequence installation progress applying image.":::

1. Prepare for Autopilot

    :::image type="content" source="images/up-2.PNG" alt-text="Task sequence installation progress running sysprep.":::

1. After the task sequence completes, the device boots into OOBE for the Autopilot experience:

    :::image type="content" source="images/up-3.PNG" alt-text="Autopilot experience prompting for user account.":::

> [!NOTE]
>
> If you need to join devices to Active Directory for hybrid Azure AD join scenario, create a **Domain Join** device configuration profile. Target the profile to **All Devices**, since there's no Azure AD device object for the computer to do group-based targeting. For more information, see [User-driven mode for hybrid Azure Active Directory join](user-driven.md#user-driven-mode-for-hybrid-azure-ad-join).

## Register the device for Windows Autopilot

Devices provisioned with Autopilot only receive the guided OOBE Autopilot experience on first boot.

After you update Windows on an existing device, make sure to register the device so it has the Autopilot experience when the PC resets. You can enable automatic registration for a device by using the **Convert all targeted devices to Autopilot** setting in the Autopilot profile that is assigned to a group that the device is a member of. For more information, see [Create an Autopilot deployment profile](profiles.md#create-an-autopilot-deployment-profile).

Also see [Adding devices to Windows Autopilot](add-devices.md).

## How to speed up the deployment process

To remove around 20 minutes from the deployment process, see Michael Niehaus's blog with instructions for [Speeding up Windows Autopilot for existing devices](/archive/blogs/mniehaus/speeding-up-windows-autopilot-for-existing-devices).
