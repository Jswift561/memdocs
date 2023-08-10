---
# required metadata
title: What's new in Microsoft Intune
titleSuffix:
description: Find out what's new in Microsoft Intune
keywords:
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 08/01/2023
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc

# optional metadata

#ROBOTS:
#audience:

ms.reviewer: lebacon
ms.suite: ems
search.appverid: MET150
#ms.tgt_pltfrm:
ms.custom: intune-azure; get-started
ms.collection:
- tier2
- M365-identity-device-management
- highseo
---

# What's new in Microsoft Intune

Learn what's new each week in Microsoft Intune.

You can also read:

- [**Important notices**](#notices)
- [Past releases](whats-new-archive.md) in the What's new archive
- Information about [how Intune service updates are released](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Microsoft-Intune-Service-Updates/ba-p/358728)

> [!NOTE]
> Each [monthly update](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Microsoft-Intune-Service-Updates/ba-p/358728) may take up to three days to rollout and will be in the following order:
>
> - Day 1: Asia Pacific (APAC)
> - Day 2: Europe, Middle East, Africa (EMEA)
> - Day 3: North America
> - Day 4+: Intune for Government
>
> Some features may roll out over several weeks and might not be available to all customers in the first week.
>
> For a list of upcoming Intune feature releases, see [In development for Microsoft Intune](../fundamentals/in-development.md). For new information about Autopilot, see [Windows Autopilot What's new](/autopilot/windows-autopilot-whats-new).

You can use RSS to be notified when this page is updated. For more information, see [How to use the docs](../../use-docs.md#notifications).
<!-- **RSS feed**: Get notified when this page is updated by copying and pasting the following URL into your feed reader: `https://learn.microsoft.com/api/search/rss?search=%22What%27s+new+in+microsoft+intune%3F+-+Azure%22&locale=en-us` -->

<!-- Common categories: -->

<!-- ### App management -->
<!-- ### Device configuration -->
<!-- ### Device enrollment -->
<!-- ### Device management -->
<!-- ### Device security -->
<!-- ### Intune apps -->
<!-- ### Monitor and troubleshoot -->
<!-- ### Role-based access control -->
<!-- ### Scripts -->
<!-- ### Tenant administration -->

## Week of August 7, 2023

### Role-based access control<!--11298214 -->

#### Introducing a new role-based access control (RBAC) permission under the resource Android for work

Introducing a new RBAC **Permission** for creating a custom role in Intune, under the resource **Android for work**. The permission **Update Enrollment Profile** allows the admin to manage or change both AOSP and Android Enterprise Device Owner enrollment profiles that are used to enroll devices.

For more information, go to [Create custom role](../fundamentals/create-custom-role.md)

## Week of July 31, 2023

### Device security

### New BitLocker profile for Intune’s endpoint security Disk encryption policy<!-- 24631986   -->  
We have released a new experience creating new *BitLocker* profiles for endpoint security Disk Encryption policy. The experience for editing your previously created BitLocker policy remains the same, and you can continue to use them. This update applies only for the new [BitLocker](../protect/endpoint-security-disk-encryption-policy.md) policies you create for the *Windows 10 and later* platform.

This update is part of the continuing [rollout of new profiles for endpoint security policies](../fundamentals/whats-new-archive.md#new-profile-templates-and-settings-structure-for-endpoint-security-policies), which began in April 2022.

### App management

#### Uninstall Win32 and Microsoft store apps using the Windows Company Portal<!-- 4664389 -->  
End-users can uninstall Win32 apps and Microsoft store apps using the Windows Company Portal if the apps were assigned as available and were installed on-demand by the end-users. For Win32 apps, you have the option to enable or disable this feature (off by default). For Microsoft store apps, it is always on and available for your end-users. If an app can be uninstalled by the end-user, the end-user will be able to select **Uninstall** for the app in the Windows Company Portal. For related information, see [Add apps to Microsoft Intune](../apps/apps-add.md).

## Week of July 24, 2023 (Service release 2307)

### App management

#### Intune supports new Google Play Android Management API<!-- 10982449 -->  
Changes have been made to how Managed Google Play public apps are managed in Intune. These changes are to support [Google’s Android Management APIs](https://developers.google.com/android/management) (opens Google's web site).

To learn more about changes to the admin and user experience, go to [Support Tip: Intune moving to support new Google Play Android Management API](https://techcommunity.microsoft.com/t5/intune-customer-success/support-tip-intune-moving-to-support-new-google-play-android/ba-p/3849875).

Applies to:

- Android Enterprise

#### App report for Android Enterprise corporate-owned devices<!-- 2055436  -->  
You can now view a report containing all apps found on a device for Android Enterprise corporate-owned scenarios, including system apps. This report is available in [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431) by selecting **Apps** > **Monitor** > **Discovered apps**. You will see **Application Name** and **Version** for all apps detected as installed on the device. It may take up to 24 hours for app information to populate the report. For related information, see [Intune discovered apps](../apps/app-discovered-apps.md).

#### Add unmanaged PKG-type applications to managed macOS devices [Public Preview]<!-- 17296091   -->  
You can now upload and deploy unmanaged PKG-type applications to managed macOS devices using the Intune MDM agent for macOS devices. This feature enables you to deploy custom PKG installers, such as unsigned apps and component packages. You can add a PKG app in the Intune admin center by selecting **Apps** > **macOS** > **Add** > **macOS app (PKG)** for app type.

For more information, see [Add an unmanaged macOS PKG app to Microsoft Intune](../apps/macos-unmanaged-pkg.md). To deploy managed PKG-type app, you can continue to [add macOS line-of-business (LOB) apps to Microsoft Intune](../apps/lob-apps-macos.md). For more information about the Intune MDM agent for macOS devices, see [Microsoft Intune management agent for macOS](../apps/lob-apps-macos-agent.md).

Applies to:

- macOS

#### New settings available for the iOS/iPadOS web clip app type<!-- 21084128   -->  
In Intune, you can pin web apps to your iOS/iPadOS devices (**Apps** > **iOS/iPadOS** > **Add** > **iOS/iPadOS web clip**). When you add web clips, there are new settings available:

- **Full screen**: If configured to **Yes**, launches the web clip as a full-screen web app without a browser. Additionally, there’s no URL or search bar, and no bookmarks.
- **Ignore manifest scope**: If configured to **Yes**, a full screen web clip can navigate to an external web site without showing Safari UI. Otherwise, Safari UI appears when navigating away from the web clip’s URL. This setting has no effect when **Full screen** is set to **No**. Available in iOS 14 and later.
- **Precomposed**: If configured to **Yes**, prevents Apple's application launcher (SpringBoard) from adding "shine" to the icon.
- **Target application bundle identifier**: Enter the application bundle identifier that specifies the application that opens the URL. Available in iOS 14 and later.

For more information, go to [Add web apps to Microsoft Intune](../apps/web-app.md).

Applies to:

- iOS/iPadOS

#### Change to default settings when adding Windows PowerShell scripts<!-- 20986905  -->  
In Intune, you can use policies to deploy Windows PowerShell scripts to your Windows devices (**Devices** > **Scripts** > **Add** > **Windows 10 and later**). When you add a Windows PowerShell script, there are settings you configure. To increase secure-by-default behavior of Intune, the default behavior of the following settings has changed:

- The **Run this script using the logged on credentials** setting defaults to **Yes**. Previously, the default was **No**.
- The **Enforce script signature check** setting defaults to **Yes**. Previously, the default was **No**.

This behavior applies to new scripts you add, not existing scripts.

For more information about using Windows PowerShell scripts in Intune, go to [Use PowerShell scripts on Windows 10/11 devices in Intune](../apps/intune-management-extension.md).

Applies to:

- Windows 10 and later (excluding Windows 10 Home)


### Device configuration

#### Added Support for Scope tags<!-- 16485280  -->  
You can now add scope tags when creating deployments using Zebra LifeGuard Over-the-Air integration (in public preview).

#### New settings available in the macOS settings catalog <!-- 24167142  -->  
The [Settings Catalog](../configuration/settings-catalog.md) lists all the settings you can configure in a device policy, and all in one place.

A new setting is available in the Settings Catalog. In the [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431), you can see these settings at **Devices** > **Configuration profiles** > **Create profile** > **macOS** > **Settings catalog** for profile type.

**Microsoft AutoUpdate (MAU)**:

- Current Channel (Monthly)

**Microsoft Defender > User interface preferences**:

- Control sign-in to consumer version

**Microsoft Office > Microsoft Outlook**:

- Disable 'Do not send response'

**User Experience > Dock**:

- MCX Dock Special Folders

Applies to:

- macOS

For more information about configuring Settings Catalog profiles in Intune, go to [Create a policy using settings catalog](../configuration/settings-catalog.md).

#### Compliance Retrieval service support for MAC address endpoints<!--  24332824  -->  
You can now use MAC address endpoints with the Intune Compliance Retrieval service (CR service), which is a replacement to the Intune [Network Access Control service](../protect/network-access-control-integrate.md).

The initial release of the CR service included support for using only the Intune device ID with the intent to eliminate the need to manage internal identifiers like serial numbers and MAC addresses. With this update, organizations that prefer to use MAC addresses over certificate authentication may continue to do so while implementing the CR service.

While this update adds MAC address support to the CR service, our recommendation is to use certificate-based authentication with the Intune device ID included in the certificate.

For information about the CR service as a replacement for the Intune Network Access Control (NAC) service, see the Intune blog at [https://techcommunity.microsoft.com/t5/intune-customer-success/new-microsoft-intune-service-for-network-access-control/ba-p/2544696](https://techcommunity.microsoft.com/t5/intune-customer-success/new-microsoft-intune-service-for-network-access-control/ba-p/2544696).

#### Settings insight within Intune Security Baselines is generally available<!-- 24507891   -->  
Announcing the general availability of Settings insight in Microsoft Intune.

The [Settings insight](../fundamentals/settings-insight.md) feature adds insight to settings giving you confidence in configurations that have been successfully adopted by similar organizations. Settings insight is currently available for Security Baselines.

Navigate to **Endpoint security** > **Security baselines**. While creating and editing a workflow these insights are available for all settings with light bulbs.

<!-- ### Device enrollment -->
<!-- ### Device management -->

### Device security

#### Tamper protection support for Windows on Azure Virtual Desktop<!--15135590     -->  
Intune now supports use of endpoint security [Antivirus policy](../protect/endpoint-security-antivirus-policy.md#prerequisites-for-tamper-protection) to manage *Tamper protection* for Windows on Azure Virtual Desktop multi-session devices. Support for Tamper protection requires devices to onboard to Microsoft Defender for Endpoint before the policy that enables Tamper protection is applied.

#### EpmTools PowerShell module for Endpoint Privilege Management<!-- 22800379  -->  
The EpmTools PowerShell module is now available for use with Intune Endpoint Privilege Management (EPM). EpmTools includes the cmdlets like **Get-FileAttributes** that you can use to retrieve file details to help build accurate elevation rules, and additional cmdlets you can use to troubleshoot or diagnose EPM policy deployments.

For more information, see [EpmTools PowerShell module](../protect/epm-overview.md#epmtools-powershell-module).

#### Endpoint Privilege Management support to manage elevation rules for child processes<!-- 15931887 -->  
With Intune Endpoint Privilege Management (EPM) you can manage which files and processes are allowed to *Run as Administrator* on your Windows devices.  Now, EPM [elevation rules](../protect/epm-policies.md#create-a-windows-elevation-rules-policy) support a new setting, **Child process behavior**.

With *Child process behavior*, your rules can manage the elevation context for any child processes created by the managed process. Options include:

- Allowing all child processes created by the managed process to always run as elevated.
- Allow a child process to run as elevated only when it matches the rule that manages its parent process.
- Deny all child processes from running in an elevated context, in which case they run as standard users.

Endpoint Privilege Management is available as an Intune add-on. For more information, see [Use Intune Suite add-on capabilities](../fundamentals/intune-add-ons.md).

### Intune apps

#### Newly available protected app for Intune<!-- 24323519  -->  
The following protected app is now available for Microsoft Intune:

- Dooray! for Intune

For more information about protected apps, see [Microsoft Intune protected apps](../apps/apps-supported-intune-apps.md).

### Monitor and troubleshoot

#### Updated reports for Setting compliance and Policy compliance are in public preview<!-- 15425624, 15425656  -->   
We've released two new reports as a public preview for Intune device compliance. You can find these new preview reports in the Intune admin center at **Reports** > **Device compliance** > *Reports* tab:

- [Setting compliance (preview)](../fundamentals/reports.md)
- [Policy compliance (preview)](../fundamentals/reports.md)

Both reports are new instances of existing reports, and deliver improvements over the older versions, including:  

- Details for Linux settings and devices
- Support for sorting, searching, filtering, exports, and paging views
- Drill-down reports for deeper details, which are filtered based on the column you select. 
- Devices are represented a single time, which is in contrast to the original reports which could count a device more than once if multiple users used that device

Eventually, the [older report versions](../protect/compliance-policy-monitor.md#view-compliance-reports) that are still available in the admin center at *Devices > Monitor* will be retired.

<!-- ### Role-based access control -->
<!-- ### Scripts -->
<!-- ### Tenant administration -->

## Week of July 10, 2023

### App management

#### Updates to app configuration policy reporting<!-- 18098046  -->  
As part of our continuing efforts to improve the Intune reporting infrastructure, there have been several user interface (UI) changes for app configuration policy reporting. The UI has been updated with the following changes:

- There is no longer a **User status** tile or a **Not applicable device** tile on the **Overview** section of the **App configuration policies** workload.
- There is no longer a **User install status** report on the **Monitor** section of the **App configuration policies** workload.
- The **Device install status** report under the **Monitor** section of the **App configuration policies** workload no longer shows the **Pending state** in the **Status** column.

You can find configure policy reporting in [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431) by selecting **Apps** > **App configuration policies**.

## Week of July 3, 2023

### Device management

#### Intune support for Zebra devices on Android 13<!-- 17192763 -->

Zebra will be releasing support for Android 13 on their devices. You can read more at [Migrating to Android 13](https://techdocs.zebra.com/lifeguard/a13/) (opens Zebra's web site).

- **Temporary issues on Android 13**

  The Intune team thoroughly tested Android 13 on Zebra devices. Everything continues working as normal, except for the following two temporary issues for device administrator (DA) devices.

  For Zebra devices running Android 13 and enrolled with DA management:

  1. App installations don't happen silently. Instead, users get a notification from the Company Portal app (if they allow notifications) that asks for permission to allow the app installation. If a user doesn't accept the app installation when prompted, then the app doesn't install. Users will have a persistent notification in the notification drawer until they allow the installation.

  2. New MX profiles don't apply to Android 13 devices. Newly enrolled Android 13 devices don't receive configuration from MX profiles. MX profiles that previously applied to enrolled devices continue to apply.

  In an update coming later in July, these issues will be resolved and the behavior will return to how it was before.

- **Update devices to Android 13**

  You will soon be able to use Intune's Zebra LifeGuard Over-the-Air integration to update Android Enterprise dedicated and fully managed devices to Android 13. For more information, go to [Zebra LifeGuard Over-the-Air Integration with Microsoft Intune](../protect/zebra-lifeguard-ota-integration.md).

  Before you migrate to Android 13, review [Migrating to Android 13](https://techdocs.zebra.com/lifeguard/a13/) (opens Zebra's web site).

- **OEMConfig for Zebra devices on Android 13**

  OEMConfig for Zebra devices on Android 13 requires using Zebra's new [Zebra OEMConfig Powered by MX OEMConfig app](https://play.google.com/store/apps/details?id=com.zebra.oemconfig.release) (opens the Google Play store). This new app can also be used on Zebra devices running Android 11, but not earlier versions.

  For more information on this app, go to the [New Zebra OEMConfig app for Android 11 and later](https://techcommunity.microsoft.com/t5/intune-customer-success/new-zebra-oemconfig-app-for-android-11-and-later/ba-p/3846730) blog post.

  The [Legacy Zebra OEMConfig app](https://play.google.com/store/apps/details?id=com.zebra.oemconfig.common) (opens the Google Play store) can only be used on Zebra devices running Android 11 and earlier.

For more general information about Intune Android 13 support, go to the [Day Zero support for Android 13 with Microsoft Intune](https://techcommunity.microsoft.com/t5/intune-customer-success/day-zero-support-for-android-13-with-microsoft-intune/ba-p/3601760) blog post.

### Device security

#### Defender for Endpoint security settings management enhancements and support for Linux and macOS in public preview<!-- 14743017, 15319901, 18713045, 18713050, 17757959 17757967, 17758270  -->  
With [Defender for Endpoint security settings management](../protect/mde-security-integration.md) (security settings configuration), you can use Intune’s endpoint security policies to manage Defender security settings on devices that onboard to Defender for Endpoint but aren’t enrolled with Intune.

Now, you can opt-in to a public preview from within the Microsoft 365 Defender portal to gain access to several enhancements for this scenario:

- Intune’s endpoint security policies become visible in and can be managed from within the Microsoft 365 Defender portal. This enables security admins to remain in the Defender portal to manage Defender and the Intune endpoint security policies for Defender security settings configurations.

- Security settings configuration supports deploying Intune endpoint security Antivirus policies to devices that run Linux and macOS.

- For Windows devices, the Windows Security Experience profile is now supported with Security settings configuration.

- A new onboarding workflow removes the Hybrid Azure AD Join prerequisite. Hybrid Azure AD Join requirements prevented many Windows devices from successfully onboarding to Defender for Endpoint security settings configuration. With this change, those devices can now complete enrollment and start processing policies for security settings configuration.

- Intune creates a synthetic registration in Azure AD for devices that can’t fully register with Azure AD. Synthetic registrations are device objects created in Azure AD that enable devices to receive and report back on Intune policies for security settings configuration. In addition, should a device with a synthetic registration become fully registered, the synthetic registration is removed form Azure AD in deference to the full registration.

If you don’t opt-in to the Defender for Endpoint Public Preview, the previous behaviors remain in place. In this case, while you can view the Antivirus profiles for Linux, you can’t deploy it as its supported only for devices managed by Defender. Similarly, the macOS profile which is currently available for devices enrolled with Intune can’t be deployed to devices managed by Defender.

Applies to:

- Linux
- macOS
- Windows

## Week of June 26, 2023

### Device configuration

#### Android (AOSP) supports assignment filters<!-- 7591220 -->

Android (AOSP) supports assignment filters. When you create a filter for Android (AOSP), you can use the following properties:

- DeviceName
- Manufacturer
- Model
- DeviceCategory
- oSVersion
- IsRooted
- DeviceOwnership
- EnrollmentProfileName

For more information on filters, go to [Use filters when assigning your apps, policies, and profiles in Microsoft Intune](filters.md).

Applies to:

- Android

#### On-demand remediation for a Windows device<!-- 14783338 -->

A new device action that is in public preview allows you to run a remediation on-demand on a single Windows device. The **Run remediation** device action allows you to resolve issues without having to wait for a remediation to run on its assigned schedule. You will also be able to view the status of remediations under **Remediations** in the **Monitor** section of a device.

The **Run remediation** device action is rolling-out and may take a few weeks to reach all customers.

For more information, go to:

- [Remediations](../fundamentals/remediations.md)

### Device management

#### Windows Driver update management in Intune is generally available<!-- 5584639  -->  
Announcing the general availability of **Windows Driver update management** in Microsoft Intune. With driver update policies, you can view a list of driver updates that are recommended and applicable to your Windows 10 and Windows 11 device that are assigned to the policy. Applicable driver updates are those that can update a device's driver version. Driver update policies update automatically to add new updates as they are published by the driver manufacturer and remove older drivers that no longer apply to any device with the policy.

Update policies can be configured for one of two approval methods:

- With *Automatic approval*, each new *recommended* driver that's published by the driver manufacturer and added to the policy is automatically approved for deployment to applicable devices. Policies set for automatic approvals can be configured with a deferral period before the automatically approved updates are installed on devices. This deferral gives you time to review the driver and to pause its deployment if necessary.

- With *manual approval*, all new driver updates are automatically added to the policy, but an admin must explicitly approve each update before Windows Update deploys it to a device. When you manually approve an update, you choose the date when Windows Update will begin to deploy it to your devices.

To help you manage driver updates, you review a policy and decline an update you don't want to install, indefinitely pause any approved update,  and reapprove a paused update to restart its deployment.

This release also includes [driver update reports](../protect/windows-update-reports.md#reports-for-windows-driver-updates-policy) that provide a success summary, per-device update status for each approved driver, and error and troubleshooting information. You can also select an individual driver update and view details about it across all the policies that include that driver version.

To learn about using Windows Driver update policies, see [Manage policy for Windows Driver updates with Microsoft Intune](../protect/windows-driver-updates-overview.md).

Applies to:

- Windows 10
- Windows 11

## Week of June 19, 2023 (Service release 2306)

### App management

#### MAM for Microsoft Edge for Business [Preview]<!-- 12394345 -->  
You can now enable protected MAM access to org data via Microsoft Edge on personal Windows devices. This capability uses the following functionality:

- Intune Application Configuration Policies (ACP) to customize the org user experience in Microsoft Edge
- Intune Application Protection Policies (APP) to secure org data and ensure the client device is healthy when using Microsoft Edge
- Windows Defender client threat defense integrated with Intune APP to detect local health threats on personal Windows devices
- Application Protection Conditional Access to ensure the device is protected and healthy before granting protected service access via Azure AD

For more information, see [Preview: App protection policy settings for Windows](../apps/app-protection-policy-settings-windows.md).

To participate in the public preview, [complete the opt-in form](https://aka.ms/MAMforWindowsPublic).

### Device configuration

#### New settings available in the Apple settings catalog<!-- 19951554  -->  
The [Settings Catalog](../configuration/settings-catalog.md) lists all the settings you can configure in a device policy, and all in one place.

A new setting is available in the Settings Catalog. In the [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431), you can see these settings at **Devices** > **Configuration profiles** > **Create profile** > **iOS/iPadOS** or **macOS** for platform > **Settings catalog** for profile type.

**Authentication > Extensible Single Sign On (SSO)**:

- Authentication Method
- Denied Bundle Identifiers
- Registration Token

**Full Disk Encryption > FileVault**:

- Output path
- Username
- Password
- UseKeyChain

Applies to:

- macOS

**Networking > Network Usage Rules**:

- SIM Rules

Applies to:

- iOS/iPadOS

For more information about configuring Settings Catalog profiles in Intune, go to [Create a policy using settings catalog](../configuration/settings-catalog.md).

#### Device Firmware Configuration Interface (DFCI) supports Asus devices <!-- 10249874 -->  
For Windows 10/11 devices, you can create a DFCI profile to manage UEFI (BIOS) settings. In [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431), select **Devices** > **Configuration profiles** > **Create profile** > **Windows 10 and later** for platform > **Templates** > **Device Firmware Configuration Interface** for profile type.

Some Asus devices running Windows 10/11 are enabled for DFCI. Contact your device vendor or device manufacturer for eligible devices.

For more information about DFCI profiles, go to:

- [Configure Device Firmware Configuration Interface (DFCI) profiles on Windows devices in Microsoft Intune](../configuration/device-firmware-configuration-interface-windows.md)
- [Device Firmware Configuration Interface (DFCI) management with Windows Autopilot](/autopilot/dfci-management)

Applies to:

- Windows 10
- Windows 11

#### Saaswedo Datalert telecom expense management is removed in Intune <!-- 23616707  -->  
In Intune, you could manage telecom expenses using Saaswedo's Datalert telecom expense management. This feature is removed from Intune. This removal includes:

- The **Telecom Expense Management** connector

- **Telecom expenses** RBAC category
  - **Read** permission
  - **Update** permission

For more information from Saaswedo, go to [The datalert service is unavailable](https://www.saaswedo.com/datalert-service-unavailable) (opens Saaswedo's web site).

Applies to:

- Android
- iOS/iPadOS

#### Settings insight within Intune Security Baselines<!-- 11127203  -->  
The [Settings insight](../fundamentals/settings-insight.md) feature adds insights to security baselines giving you confidence in configurations that are successfully adopted by similar organizations.

Navigate to **Endpoint security** > **Security baselines**. When you create and edit the workflow, these insights are available for you in the form of a light bulb.

### Device management

#### New endpoint security Application Control policy in preview<!-- 15711976 -->  
As a public preview, you can use a new endpoint security policy category, Application Control. Endpoint security Application Control policy includes:

- Policy to set the Intune Management Extension as a tenant-wide managed installer. When enabled as a managed installer, apps you deploy through Intune (after enablement of Managed Installer) to Windows devices are tagged as installed by Intune. This tag becomes useful when you use Application Control policies to manage which apps you want to allow or block from running on your managed devices.

- Application Control policies that are an implementation of Defender Application Control (WDAC). With Endpoint security Application Control policies, it's easy to configure policy that allows trusted apps to run on your managed devices. Trusted apps are installed by a managed installer or from the App store. In addition to built-in trust settings, these policies also support custom XML for application control so you can allow other apps from other sources to run to meet your organizations requirements.

To get started with using this new policy type, see [Manage approved apps for Windows devices with Application Control policy and Managed Installers for Microsoft Intune](../protect/endpoint-security-app-control-policy.md)

Applies to:

- Windows 10
- Windows 11

#### Endpoint analytics is available to tenants in Government cloud<!-- 8527244  -->  
With this release, Endpoint analytics is available to tenants in Government cloud.

Learn more about [Endpoint analytics](/mem/analytics/).

#### Introducing in-session connection mode switch in Remote Help<!-- 10602971  -->  
In Remote Help, you can now take advantage of the in-session connection mode switch feature. This feature can help effortlessly transition between full control and view-only modes, granting flexibility and convenience.

For more information on Remote Help, go to [Remote Help](../fundamentals/remote-help.md).

Applies to:

- Windows 10/11

### Device security

#### Update to Endpoint Privilege Management reports<!-- 17727222 -->  
Intune's Endpoint Privilege Management (EPM) reports now support exporting the full reporting payload to a CSV file. With this change, you can now export all events from an elevation report in Intune.

#### Endpoint Privilege Managements run with elevated access option now available on the top-level menu for Windows 11<!-- 17749664  -->
The Endpoint Privilege Management option to *Run with elevated access* is now available as a top-level right-click option on Windows 11 devices. Previous to this change, standard users were required to select *Show more options* to view the *Run with elevated access* prompt on Windows 11 devices.

[Endpoint Privilege Management](../protect/epm-overview.md) is available as an Intune add-on. For more information, see [Use Intune Suite add-on capabilities](../fundamentals/intune-add-ons.md).

Applies to:

- Windows 11

### Intune apps

#### Newly available protected apps for Intune<!-- 23027634, 21159364, 21234187, 21237641, 20771088  -->  
The following protected apps are now available for Microsoft Intune:

- Idenprotect Go by Apply Mobile Ltd (Android)
- LiquidText by LiquidText, Inc. (iOS)
- MyQ Roger: OCR scanner PDF by MyQ spol. s r.o.
- CiiMS GO by Online Intelligence (Pty) Ltd
- Vbrick Mobile by Vbrick Systems

For more information about protected apps, see [Microsoft Intune protected apps](../apps/apps-supported-intune-apps.md).

### Monitor and troubleshoot

#### Microsoft Intune troubleshooting pane is now generally available<!-- 18099474 -->  
The Intune troubleshooting pane is now generally available.  It provides details about user's devices, policies, applications, and status. The troubleshooting pane includes the following information:

- A summary of policy, compliance, and application deployment status.
- Support for exporting, filtering, and sorting all reports.
- Support to filter by excluding policies and applications.
- Support to filter to a user's single device.
- Details about available device diagnostics and disabled devices.
- Details about offline devices that haven't checked-in to the service for three or more days.

You can find the troubleshooting pane in [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) by selecting **Troubleshooting + support** > **Troubleshoot**.

#### Updated troubleshoot + support pane in Intune<!-- 16240430  -->  
The **Troubleshooting + support** pane in the Intune admin center has been updated by consolidating the **Roles and Scopes** report into a single report. This report now includes all relevant role and scope data from both Intune and Azure Active Directory, providing a more streamlined and efficient experience. For related information, see [Use the troubleshooting dashboard to help users at your company](../fundamentals/help-desk-operators.md).

#### Download mobile app diagnostics<!-- 22139638  -->  
Now generally available, access user-submitted mobile app diagnostics in the Intune admin center, including app logs sent through Company Portal apps, which include Windows, iOS, Android, Android ASOP, and macOS. In addition, you can retrieve app protection logs via Microsoft Edge. For more information, see [Company Portal app logs](../apps/company-portal-app.md#app-logs) and [Use Edge for iOS and Android to access managed app logs](../apps/manage-microsoft-edge.md#use-edge-for-ios-and-android-to-access-managed-app-logs).

## Week of June 12, 2023

### Device management

#### New Devices from HTC and Pico supported on Microsoft Intune for Android Open Source Devices<!-- 24271568 -->  
Microsoft Intune for Android open source project devices (AOSP) now supports the following devices:

- HTC Vive XR Elite
- Pico Neo 3 Pro
- Pico 4

For more information, go to:

- [Operating systems and browsers supported by Microsoft Intune](../fundamentals/supported-devices-browsers.md)

- [Android Open Source Project Supported Devices](../fundamentals/android-os-project-supported-devices.md)

Applies to:

- Android (AOSP)

### App management

#### Microsoft Store for Business or Microsoft Store for Education<!-- 24250535 -->
Apps added from the Microsoft Store for Business or Microsoft Store for Education won't deploy to devices and users. Apps show as "not applicable" in reporting. Apps already deployed are unaffected. Use the [new Microsoft Store app](../apps/store-apps-microsoft.md) to deploy Microsoft Store apps to devices or users. For related information, see [Plan for Change: Ending support for Microsoft Store for Business and Education apps](../fundamentals/whats-new.md#plan-for-change-ending-support-for-microsoft-store-for-business-and-education-apps) for upcoming dates when Microsoft Store for Business apps will no longer deploy and Microsoft Store for Business apps will be removed.

For more information, see the following resources:
- [Update to Intune integration with the Microsoft Store on Windows](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/update-to-intune-integration-with-the-microsoft-store-on-windows/ba-p/3585077)
- [Embracing the Future of Microsoft Store with Intune: A Step-by-Step Guide](https://www.youtube.com/watch?v=c534X9yMvDo)
- [Embracing the Future of Microsoft Store with Intune for Education: A Step-by-Step Guide](https://www.youtube.com/watch?v=Heoi0RuClQM)

## Week of June 5, 2023

### Device configuration

### Android Enterprise 11+ devices can use Zebra's latest OEMConfig app version<!-- 8675347 -->  

On Android Enterprise devices, you can use OEMConfig to add, create, and customize OEM-specific settings in Microsoft Intune (**Devices** > **Configuration profiles** > **Create profile** > **Android Enterprise** for platform > **OEMConfig**).

There's a new **Zebra OEMConfig Powered by MX** OEMConfig app that aligns more closely to Google's standards. This app supports Android Enterprise 11.0 and newer devices.

The older **Legacy Zebra OEMConfig** app continues to support devices with Android 11 and earlier.

In your Managed Google Play, there are two versions of Zebra OEMConfig app. Be sure to select the correct app that applies to your Android device versions.

For more information on OEMConfig and Intune, go to [Use and manage Android Enterprise devices with OEMConfig in Microsoft Intune](../configuration/android-oem-configuration-overview.md).

Applies to:

- Android Enterprise 11.0 and newer

## Week of May 29, 2023  

### Device management

### Intune UI displays Windows Server devices as distinct from Windows clients for the Security Management for Microsoft Defender for Endpoint scenario<!-- 16882836 -->  
To support the [Security Management for Microsoft Defender for Endpoint](../protect/mde-security-integration.md) (MDE security configuration) scenario, Intune now differentiates Windows devices in Azure Active Directory as either *Windows Server* for devices that run Windows Server, or as *Windows* for devices that run Windows 10 or Windows 11.

With this change, you can improve policy targeting for MDE security configuration. For example, you can use dynamic groups that consist of only Windows Server devices, or only Windows client devices (Windows 10/11).

For more information about this change, see the Intune Customer Success blog [Windows Server devices now recognized as a new OS in Microsoft Intune, Azure AD, and Defender for Endpoint
](https://techcommunity.microsoft.com/t5/intune-customer-success/support-tip-windows-server-devices-will-now-be-identified-as-a/ba-p/3767773).

### Tenant administration  

#### Organizational messages for Windows 11 now generally available<!-- 15272978 -->  
Use organizational messages to deliver branded, personalized call-to-actions to employees. Select from more than 25 messages that support employees through device onboarding and lifecycle management, in 15 different languages. Messages can be assigned to Azure AD user groups. They're shown just above the taskbar, in the notifications area, or in the Get started app on devices running Windows 11. Messages continue to appear or reappear based on the frequency you configure in Intune, and until the user has visited the customized URL.

Other features and functionality added in this release include:

- Confirm licensing requirements prior to first message.
- Choose from eight new themes for taskbar messages.  
- Give messages a custom name.
- Add scope groups and scope tags.
- Edit the details of a scheduled message.

Scope tags were previously unavailable for organizational messages. With the addition of scope tag support, Intune adds the default scope tag to every message created before June 2023. Admins that want access to those messages must be associated with a role that has the same tag. For more information about available features and how to set up organizational messages, see
[Overview of organizational messages](../remote-actions/organizational-messages-overview.md).   

## Week of May 22, 2023 (Service release 2305)

### App management

#### Update to macOS shell scripts maximum running time limit<!-- 23187517 -->
Based on customer feedback, we're updating the Intune agent for macOS (version 2305.019) to extend the maximum script run time to 60 minutes. Previously, the Intune agent for macOS only allowed shell scripts to run for up to 15 minutes before reporting the script as a failure. The Intune agent for macOS 2206.014 and higher supports the 60-minute timeout.

#### Assignment filters support app protection policies and app configuration policies<!-- 7476247 -->  
Assignment filters support MAM app protection policies and app configuration policies. When you create a new filter, you can fine tune MAM policy targeting using the following properties:

- Device Management Type
- Device Manufacturer
- Device Model
- OS Version
- Application Version
- MAM Client Version

> [!IMPORTANT]
> All new and edited app protection policies that use **Device Type** targeting are replaced with assignment filters.

For more information on filters, go to [Use filters when assigning your apps, policies, and profiles in Microsoft Intune](filters.md).

#### Update to MAM reporting in Intune<!-- 10100428  -->  
MAM reporting has been simplified and overhauled, and now uses Intune's newest reporting infrastructure. Benefits of this include improved data accuracy and instantaneous updating. You can find these streamlined MAM reports in the [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431) by selecting **Apps** > **Monitor**. All MAM data available to you is contained within the new **App protection status** report and **App configuration status** report.

#### Global quiet time app policy settings<!-- 15424417   -->  
The global quiet time settings allow you to create policies to schedule quiet time for your end users. These settings automatically mute Microsoft Outlook email and Teams notifications on iOS/iPadOS and Android platforms. These policies can be used to limit end user notifications received after work hours. For more information, see [Quiet time notification policies](../apps/app-office-policies.md#quiet-time-notification-policies).

### Device configuration

#### Introducing enhanced chat in Remote Help<!-- 10602997 -->

Introducing enhanced chat with Remote Help. With the new and enhanced chat you can maintain a continuous thread of all messages. This chat provides support for special characters and other languages including Chinese and Arabic.

For more information on Remote Help, go to [Remote Help](../fundamentals/remote-help.md).

Applies to:
Windows 10/11 

#### Remote Help administrators can reference audit log sessions<!-- 9052185  -->  
For Remote Help, in addition to existing session reports, administrators can now reference audit logs sessions created in Intune. This feature enables administrators to reference past events for troubleshooting and analyzing log activities.

For more information on Remote Help, go to [Remote Help](../fundamentals/remote-help.md).

Applies to:

- Windows 10
- Windows 11

#### Turn on/off Personal data encryption on Windows 11 devices using the settings catalog<!-- 10346018  -->  
The settings catalog includes hundreds of settings that you can configure and deploy to your devices.

In the settings catalog, you can turn on/off **Personal data encryption** (PDE). PDE is a security feature introduced in Windows 11 version 22H2 that provides more encryption features for Windows.

PDE is different than BitLocker. PDE encrypts individual files and content, instead of whole volumes and disks. You can use PDE with other encryption methods, such as BitLocker.

For more information on the settings catalog, go to:

- [Use the settings catalog to configure settings on Windows, iOS/iPadOS and macOS devices](../configuration/settings-catalog.md)
- [Common Tasks you can complete using the Settings Catalog in Intune](../configuration/settings-catalog-common-features.md)

This feature applies to:

- Windows 11

#### Visual Studio ADMX settings are in the Settings Catalog and Administrative Templates <!-- 10875730 -->  
Visual Studio settings are included in the Settings Catalog and Administrative Templates (ADMX). Previously, to configure Visual Studio settings on Windows devices, you imported them with ADMX import.

For more information on these policy types, go to:

- [Use the settings catalog to configure settings](../configuration/settings-catalog.md)
- [Use Windows 10/11 templates to configure group policy settings in Microsoft Intune](../configuration/administrative-templates-windows.md)
- [Visual Studio Administrative Templates (ADMX)](/visualstudio/install/administrative-templates)

Applies to:

- Windows 10
- Windows 11

#### Group policy analytics supports scope tags<!-- 12714882  -->  
In Group Policy analytics, you import your on-premises GPO. The tool analyzes your GPOs and shows the settings that can (and can't) be used in Intune.

When you import your GPO XML file in Intune, you can select an existing scope tag. If you don't select a scope tag, then the **Default** scope tag is automatically selected. Previously, when you imported a GPO, the scope tags assigned to you were automatically applied to the GPO.

Only admins within that scope tag can see the imported policies. Admins not in that scope tag can't see the imported policies.

Also, admins within their scope tag can migrate the imported policies that they have permissions to see. To migrate an imported GPO into a Settings Catalog policy, a scope tag must be associated with the imported GPO. If a scope tag isn't associated, then it can't migrate to a Settings Catalog policy. If no scope tag is selected, then a default scope tag is automatically applied.

For more information on scope tags and Group Policy analytics, go to:

- [Analyze your on-premises GPOs using Group Policy analytics in Microsoft Intune](../configuration/group-policy-analytics.md)
- [Create a Settings Catalog policy using your imported GPOs](../configuration/group-policy-analytics-migrate.md)
- [Use role-based access control (RBAC) and scope tags for distributed IT](scope-tags.md)

#### Introducing Intune integration with the Zebra Lifeguard Over-the-Air service (public preview)<!-- 14340034  -->  
Now available in public preview, Microsoft Intune supports integration with Zebra Lifeguard Over-the-Air service, which allows you to deliver OS updates and security patches over-the-air to eligible Zebra devices that are enrolled with Intune. You can select the firmware version you want to deploy, set a schedule, and stagger update downloads and installs. You can also set minimum battery, charging status, and network conditions requirements for when the update can happen.

Available for Android Enterprise Dedicated and Fully Managed Zebra devices that are running Android 8 or later, and requires an account with Zebra.

#### New Google domain allowlist settings for Android Enterprise personally owned devices with a work profile<!-- 14711684 -->  
On Android Enterprise personally owned devices with a work profile, you can configure settings that restrict device features and settings.

Currently, there's an **Add and remove accounts** setting that can allow Google accounts be added to the work profile. For this setting, when you select **Allow all accounts types**, you can also configure:

- **Google domain allow-list**:  Restricts users to add only certain Google account domains in the work profile. You can import a list of allowed domains or add them in the admin center using the `contoso.com` format. When left blank, by default, the OS might allow adding all Google domains in the work profile.

For more information on the settings you can configure, go to [Android Enterprise device settings list to allow or restrict features on personally owned devices using Intune](../configuration/device-restrictions-android-enterprise-personal.md).

Applies to:

- Android Enterprise personally owned devices with a work profile

#### Renaming Proactive remediation to Remediations and moving to a new location<!-- 16526263  -->  
Proactive remediations are now Remediations and are available from **Devices** > **Remediations**. You can still find Remediations in both the new location and the existing **Reports** > **Endpoint Analytics** location until the next Intune service update.

Remediations are currently not available in the new [Devices experience preview](../fundamentals/microsoft-intune-admin-center-devices.md).

Applies to:

- Windows 10
- Windows 11

#### Remediations are now available in Intune for US Government GCC High and DoD<!-- 16526300 -->  
Remediations (previously known as proactive remediations) are now available in [Microsoft Intune for US Government GCC High and DoD](../fundamentals/intune-govt-service-description.md)

Applies to:

- Windows 10
- Windows 11

#### Create inbound and outbound network traffic rules for VPN profiles on Windows devices<!-- 17943658 -->  

> [!NOTE]
> This setting is coming in a future release, possibly the 2308 Intune release.

You can create a device configuration profile that deploys a VPN connection to devices (**Devices** > **Configuration profiles** > **Create profile** > **Windows 10 and later** for platform > **Templates** > **VPN** for profile type).

In this VPN connection, you can use the **Apps and Traffic rules** settings to create network traffic rules.

There's a new **Direction** setting you can configure. Use this setting to allow Inbound and Outbound traffic from the VPN connection:

- **Outbound** (default): Allows only traffic to external networks/destinations to flow using the VPN. Inbound traffic is blocked from entering the VPN.
- **Inbound**: Allows only traffic coming from external networks/ sources to flow using the VPN. Outbound traffic is blocked from entering the VPN.

For more information on the VPN settings you can configure, including the network traffic rule settings, go to [Windows device settings to add VPN connections using Intune](../configuration/vpn-settings-windows-10.md).

Applies to:

- Windows 10 and later

#### New settings available in the macOS settings catalog <!-- 18430228  -->  
The [Settings Catalog](../configuration/settings-catalog.md) lists all the settings you can configure in a device policy, and all in one place.

A new setting is available in the Settings Catalog. In the [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431), you can see these settings at **Devices** > **Configuration profiles** > **Create profile** > **macOS** for platform > **Settings catalog** for profile type.

**Microsoft Defender > Antivirus engine**:

- Scanning inside archive files
- Enable file hash computation

Applies to:

- macOS

For more information about configuring Settings Catalog profiles in Intune, go to [Create a policy using settings catalog](../configuration/settings-catalog.md).

#### Wipe device action and new obliteration behavior setting available for macOS<!-- 16647226 -->  
You can now use the **Wipe** device action instead of Erase for macOS devices. Additionally, you can configure the **Obliteration Behavior** setting as part of the **Wipe** action.

This new key allows you to control the wipe fallback behavior on Macs that have Apple Silicon or the T2 Security Chip. To find this setting, navigate to **Devices** > **macOS** > [Select a device] > **Overview** > **Wipe** in the **Device action** area.

For more information on the Obliteration Behavior setting, go to Apple's Platform Deployment site [Erase Apple devices - Apple Support](https://support.apple.com/guide/deployment/erase-devices-dep0a819891e/web).

Applies to:

- macOS  

### Device enrollment  

#### Account driven Apple User Enrollment available for iOS/iPadOS 15+ devices (public preview)<!-- 14161683  -->  
Intune supports account driven user enrollment, a new and improved variation of Apple User Enrollment for iOS/iPadOS 15+ devices. Now available for public preview, the new option utilizes just-in-time registration, which eliminates the need for the Company Portal app during enrollment. Device users can initiate enrollment directly in the Settings app, resulting in a shorter and more efficient onboarding experience. You can continue to target iOS/iPadOS devices using the existing profile-based user enrollment method that uses Company Portal. Devices running iOS/iPadOS, version 14.8.1 and earlier remain unaffected by this update and can continue to use the existing method. For more information, see [Set up account driven Apple User Enrollment](../enrollment/apple-account-driven-user-enrollment.md).  

### Device security

#### New security baseline for Microsoft 365 Office Apps<!-- 9587103  -->  
We've released a new security baseline to help you manage security configurations for **M365 Office Apps**. This new baseline uses an updated template and experience that uses the unified settings platform seen in the Intune settings catalog. You can view the list of settings in the new baseline at [Microsoft 365 Apps for Enterprise baseline settings (Office)](../protect/security-baseline-v2-office-settings.md).

The new Intune security baseline format aligns the presentation of settings that are available to the settings found in the Intune settings catalog. This alignment helps resolve past issues for setting names and implementations for settings that could create conflicts. The new format also improves the reporting experience for baselines in the Intune admin center.

The Microsoft 365 Office Apps baseline can help you rapidly deploy configurations to your Office Apps that meet the security recommendations of the Office and security teams at Microsoft. As with all baselines, the default baseline represents the recommended configurations. You can modify the default baseline to meet the requirements of your organization.

To learn more, see [Security baselines overview](../protect/security-baselines.md).

Applies to:

- Windows 10
- Windows 11

#### Security baseline update for Microsoft Edge version 112<!-- 3408610  -->  
We've released a new version of the Intune security baseline for Microsoft Edge, version 112. In addition to releasing this new version for Microsoft Edge, the new baseline uses an updated template experience that uses the unified settings platform seen in the Intune settings catalog. You can view the list of settings in the new baseline at [Microsoft Edge baseline settings (version 112 and higher)](../protect/security-baseline-v2-edge-settings.md).

The new Intune security baseline format aligns the presentation of settings that are available to the settings found in the Intune settings catalog. This alignment helps resolve past issues for setting names and implementations for settings that could create conflicts. The new format also improves the reporting experience for baselines in the Intune admin center.

Now that the new baseline version is available, all new profiles you create for Microsoft Edge use the new baseline format and version. While the new version becomes the default baseline version, you can continue to use the profiles you've previously created for older versions of Microsoft Edge. But, you can't create new profiles for those older versions of Microsoft Edge.

To learn more, see [Security baselines overview](../protect/security-baselines.md).

Applies to:

- Windows 10
- Windows 11

### Intune apps

#### Newly available protected apps for Intune<!-- 17782795, 17782816, 17851777, 17644967, 17948005, 17971727 -->  
The following protected apps are now available for Microsoft Intune:

- Achievers by Achievers Inc.
- Board.Vision for iPad by Trusted Services PTE. LTD.
- Global Relay by Global Relay Communications Inc.
- Incorta (BestBuy) by Incorta, Inc. (iOS)
- Island Enterprise Browser by Island (iOS)
- Klaxoon for Intune by Klaxoon (iOS)

For more information about protected apps, see [Microsoft Intune protected apps](../apps/apps-supported-intune-apps.md).

## Week of May 8, 2023

### Device configuration

#### Device Firmware Configuration Interface (DFCI) supports Dynabook devices<!-- 10249859 -->
For Windows 10/11 devices, you can create a DFCI profile to manage UEFI (BIOS) settings. In [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431), select **Devices** > **Configuration profiles** > **Create profile** > **Windows 10 and later** for platform > **Templates** > **Device Firmware Configuration Interface** for profile type.

Some Dynabook devices running Windows 10/11 are enabled for DFCI. Contact your device vendor or device manufacturer for eligible devices.

For more information about DFCI profiles, go to:
- [Configure Device Firmware Configuration Interface (DFCI) profiles on Windows devices in Microsoft Intune](../configuration/device-firmware-configuration-interface-windows.md)
- [Device Firmware Configuration Interface (DFCI) management with Windows Autopilot](/autopilot/dfci-management)

Applies to:
- Windows 10
- Windows 11

#### eSIM bulk activation for Windows PCs via download server is now available on the Settings Catalog<!-- 19809114 -->
You can now perform at-scale configuration of Windows eSIM PCs using the Settings Catalog. A download server (SM-DP+) is configured using a configuration profile. 

Once the devices receive the configuration, they automatically download the eSIM profile. For more information, go to [eSIM configuration of a download server](../configuration/esim-device-configuration-download-server.md)

Applies to:

- Windows 11
- eSIM capable devices

## Week of May 1, 2023

### App management

#### macOS shell scripts maximum running time limit<!-- 19396575 -->
We have fixed an issue that caused Intune tenants with long-running shell scripts to not report back on the script run status. The macOS Intune agent stops any macOS shell scripts that run longer than 15 minutes. These scripts report as failed. The new behavior is enforced from macOS Intune agent version 2305.019.

#### DMG app installation for macOS<!-- 13911806 -->  
The DMG app installation feature for macOS is now generally available. Intune supports **required** and **uninstall** assignment types for DMG apps. The Intune agent for macOS is used to deploy DMG apps. For related information, see [Deploy DMG-type applications to managed macOS devices](../fundamentals/whats-new-archive.md#deploy-dmg-type-applications-to-managed-macos-devices).

#### Deprecation of Microsoft Store for Business and Education<!-- 19677954 -->
The Microsoft Store for Business connector is no longer accessible in the [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431). Apps added from the Microsoft Store for Business or Microsoft Store for Education won't sync with Intune. Apps that have previously synced continue to be available and deploy to devices and users.

It's now also possible to delete Microsoft Store for Business apps from the **Apps** pane in the Microsoft Intune admin center so that you can clean up your environment as you move to the new Microsoft Store app type.

For related information, see [Plan for Change: Ending support for Microsoft Store for Business and Education apps](../fundamentals/whats-new.md#plan-for-change-ending-support-for-microsoft-store-for-business-and-education-apps) for upcoming dates when Microsoft Store for Business apps won't deploy and Microsoft Store for Business apps are removed.

### Device configuration

#### Remote Help now supports conditional access capability<!--16108299 -->  
Administrators can now utilize conditional access capability when setting up policies and conditions for Remote Help. For example, multi-factor authentication, installing security updates, and locking access to Remote Help for a specific region or IP addresses.

For more information, go to:

- [Conditional access](../protect/conditional-access.md)
- [Remote Help](../fundamentals/remote-help.md#setup-conditional-access-for-remote-help)

### Device security

#### Updated settings for Microsoft Defender in endpoint security Antivirus policy<!-- 19991301  -->  
We've updated the available settings in the *Microsoft Defender Antivirus* profile for endpoint security Antivirus policy.  You can find this profile in the Intune admin center at **Endpoint security** > **Antivirus** > *Platform:* **Windows 10, Windows 11, and Windows Server**  > *Profile:* **Microsoft Defender Antivirus**.  
- **The following settings have been added**:

  - Metered Connection Updates
  - Disable Tls Parsing
  - Disable Http Parsing
  - Disable Dns Parsing
  - Disable Dns Over Tcp Parsing
  - Disable Ssh Parsing
  - Platform Updates Channel
  - Engine Updates Channel
  - Security Intelligence Updates Channel
  - Allow Network Protection Down Level
  - Allow Datagram Processing On Win Server
  - Enable Dns Sinkhole

  For more information about these settings, see the [Defender CSP]( /windows/client-management/mdm/Defender-csp?WT.mc_id=Portal-fx).
The new settings are also available through the Intune [Settings Catalog](../configuration/settings-catalog.md).

- **The following setting has been deprecated**:

  - Allow Intrusion Prevention System

  This setting now appears with the *Deprecated* tag. If this deprecated setting was previously applied on a device, the setting value is updated to *NotApplicable* and has no effect on the device. If this setting is configured on a device, there's no effect on the device.

Applies to:

- Windows 10
- Windows 11

## Week of April 17, 2023 (Service release 2304)

### App management

#### Changes to iCloud app backup and restore behavior on iOS/iPadOS and macOS devices<!-- 16261392  -->  
As an app setting, you can select to **Prevent iCloud app backup** for iOS/iPadOS and macOS devices. You can *not* backup managed App Store apps and line-of-business (LOB) apps on iOS/iPadOS, as well as managed App Store apps on macOS devices (macOS LOB apps don't support this feature), for both user and device licensed VPP/non-VPP apps. This update includes both new and existing App Store/LOB apps sent with and without VPP that are being added to Intune and targeted to users and devices.

Preventing the backup of the specified managed apps ensures that these apps can be properly deployed via Intune when the device is enrolled and restored from backup. If the admin configures this new setting for new or existing apps in their tenant, then managed apps can and will be reinstalled for devices. But, Intune doesn't allow them to be backed up.

This new setting appears in [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431) by modifying the properties of an app. For an existing app, you can select **Apps** > **iOS/iPadOS** or **macOS** > *select the app* > **Properties** > Assignment **Edit**. If no group assignment has been set, select **Add group** to add a group. Modify either the setting under **VPN**, **Uninstall on device removal**, or **Install as removable**. Then, select **Prevent iCloud app backup**. The **Prevent iCloud app backup** setting is used to prevent backup of app data for the application. Set to **No** to allow the app to be backed up by iCloud.

For more information, see [Changes to applications' backup and restore behavior on iOS/iPadOS and macOS devices](https://techcommunity.microsoft.com/t5/intune-customer-success/changes-to-applications-backup-and-restore-behavior-on-ios/ba-p/3692064) and [Assign apps to groups with Microsoft Intune](../apps/apps-deploy.md).

#### Prevent automatic updates for Apple VPP apps<!-- 16876430   -->  
You can control the automatic update behavior for Apple VPP at the per-app assignment level using the **Prevent automatic updates** setting. This setting is available in [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431) by selecting **Apps** > **iOS/iPadOS** or **macOS** > *Select a volume purchase program app* > **Properties** > **Assignments** > *Select an Azure AD group* > **App settings**.

Applies to:

- iOS/iPadOS
- macOS

### Device configuration

#### Updates to the macOS Settings Catalog <!-- 17673709  -->  
The [Settings Catalog](../configuration/settings-catalog.md) lists all the settings you can configure in a device policy, and all in one place.

A new setting is available in the Settings Catalog. In the [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431), you can see these settings at **Devices** > **Configuration profiles** > **Create profile** > **macOS** for platform > **Settings catalog** for profile type.

The new setting is located under:

**Microsoft AutoUpdate (MAU) > [targeted app]**:

- Update channel override

The following settings have been deprecated:

**Microsoft AutoUpdate (MAU) > [targeted app]**:

- Channel Name (Deprecated)

**Privacy > Privacy Preferences Policy Control > Services > Listen Event or Screen Capture**:

- Allowed

Applies to:

- macOS

For more information about configuring Settings Catalog profiles in Intune, go to [Create a policy using settings catalog](../configuration/settings-catalog.md).

#### The Microsoft Enterprise SSO plug-in for Apple devices is now generally available<!-- 17826329  -->  
In Microsoft Intune, there's a Microsoft Enterprise SSO plug-in. This plug-in provides single sign-on (SSO) to iOS/iPadOS and macOS apps and websites that use Microsoft Azure AD for authentication.

This plug-in is now generally available (GA).

For more information about configuring the Microsoft Enterprise SSO plug-in for Apple devices in Intune, go to [Microsoft Enterprise SSO plug-in in Microsoft Intune](../configuration/use-enterprise-sso-plug-in-ios-ipados-macos.md).

Applies to:

- iOS/iPadOS
- macOS

#### Disable Activation Lock device action for supervised macOS devices<!-- 16813146  -->  

You can now use the **Disable Activation Lock** device action in Intune to bypass Activation Lock on Mac devices without requiring the current username or password. This new action is available in **Devices** > **macOS** > select one of your listed devices > **Disable Activation Lock**.

More information on managing Activation Lock is available at [Bypass iOS/iPadOS Activation Lock with Intune](../remote-actions/device-activation-lock-disable.md) or on Apple's website at [Activation Lock for iPhone, iPad, and iPod touch - Apple Support](https://support.apple.com/en-us/HT201365).

Applies to:

- macOS 10.15 or later

#### ServiceNow Integration is now Generally Available (GA)<!-- 18163832  -->  
Now generally available, you can view a list of ServiceNow incidents associated with the user you've selected in the Intune Troubleshooting workspace. This new feature is available under **Troubleshooting + Support** > select a user > **ServiceNow Incidents**. The incidents shown have a direct link back to the source incident and show key information from the incident. All incidents listed link the "Caller" identified in the incident with the user selected for Troubleshooting.

For more information, go to [Use the troubleshooting portal to help users at your company](service-now-integration.md).

#### More permissions to support administrators in controlling delivery of organization messages<!-- 16982298  -->  

With more permissions administrators can control delivery of content created and deployed from Organizational messages and the delivery of content from Microsoft to users.

The **Update organizational message control** RBAC permission for organizational messages determines who can change the Organizational Messages toggle to allow or block Microsoft direct messages. This permission is also added to the **Organizational Messages Manager** built-in role.

Existing custom roles for managing Organizational Messages must be modified to add this permission for users to modify this setting.

- For more information, about role-based access control (RBAC), see [RBAC with Microsoft Intune](../fundamentals/role-based-access-control.md).
- For more information, about prerequisites for organization messages, see [Organizational messages prerequisites](../remote-actions/organizational-messages-prerequisites.md#role-based-access-control-requirements).

### Device management

#### Endpoint security firewall rules support for ICMP type<!-- 5653356  -->  
You can now use the **IcmpTypesAndCodes** setting to configure inbound and outbound rules for [Internet Control Message Protocol](/windows/security/threat-protection/windows-firewall/create-an-inbound-icmp-rule) (ICMP) as part of a firewall rule. This setting is available in the [*Microsoft Defender Firewall rules*](../protect/endpoint-security-firewall-policy.md#devices-managed-by-intune) profile for the *Windows 10, Windows 11, and Windows Server* platform.

Applies to:

- Windows 11 and later

#### Manage Windows LAPS with Intune policies (public preview)<!-- 11890571  -->  
Now available in a public preview, manage Windows Local Administrator Password Solution (Windows LAPS) with Microsoft Intune [Account protection policies](../protect/endpoint-security-account-protection-policy.md). To get started, see [Intune support for Windows LAPS](../protect/windows-laps-overview.md).

[Windows LAPS](/windows-server/identity/laps/laps-overview) is a Windows feature that allows you to manage and backs up the password of a local administrator account on your Azure Active Directory-joined or Windows Server Active Directory-joined devices.

To manage LAPS, Intune configures the Windows [LAPS configuration service provider](/windows/client-management/mdm/LAPS-csp) (CSP) that is built in to Windows devices. It takes precedence over other sources of Windows LAPS configurations, like GPOs or the Microsoft Legacy LAPS tool. Some of the capabilities you can use when Intune manages Windows LAPS include:

- Define password requirements like complexity and length that apply to the local administrator accounts on a device.
- Configure devices to rotate their local admin account passwords on a schedule. And, back up the account and password in your Azure Active Directory or on-premises Active Directory.
- Use an Intune device action from the admin center to manually rotate the password for an account on your own schedule.
- View account details from within the Intune admin center, like the account name and password. This information can help you recover devices that are otherwise inaccessible.
- Use Intune reports to monitor your LAPS policies, and when devices last rotated passwords manually or by schedule.  

Applies to:

- Windows 10
- Windows 11

#### New settings available for macOS software update policies<!-- 16646756  -->  
macOS software update policies now include the following settings to help manage when updates install on a device. These settings are available when the *All other updates* update type is configured to *Install later*:

- **Max User Deferrals**:  When the *All other updates* update type is configured to *Install later*, this setting allows you to specify the maximum number of times a user can postpone a minor OS update before it's installed. The system prompts the user once a day. Available for devices running macOS 12 and later.

- **Priority**: When the *All other updates* update type is configured to *Install later*, this setting allows you to specify values of *Low* or *High* for the scheduling priority for downloading and preparing minor OS updates. Available for devices running macOS 12.3 and later.

For more information, see [Use Microsoft Intune policies to manage macOS software updates](../protect/software-updates-macos.md).

Applies to:

- macOS

#### Introducing the new partner portals page<!-- 17829024  -->  
You can now manage hardware specific information on your HP or Surface devices from our partner portals page.

The HP link takes you to HP Connect where you can update, configure, and secure the BIOS on your HP devices.
The Microsoft Surface link takes you to the Surface Management Portal where you can get insights into device compliance, support activity, and warranty coverage.

To access the Partner portals page, you must enable the Devices pane preview and then navigate to **Devices** > **Partner Portals**.

#### Windows Update compatibility reports for Apps and Drivers are now generally available<!-- 17917026  -->  
The following Microsoft Intune reports for [Windows Update compatibility](../protect/windows-update-compatibility-reports.md) are out of preview and now generally available:

- **Windows feature update device readiness report** - This report provides per-device information about compatibility risks that are associated with an upgrade or update to a chosen version of Windows.

- **Windows feature update compatibility risks report** - This report provides a summary view of the top compatibility risks across your organization for a chosen version of Windows. You can use this report to understand which compatibility risks impact the greatest number of devices in your organization.

These reports can help you plan an upgrade from Windows 10 to 11, or for installing the latest Windows feature update.

### Device security

#### Microsoft Intune Endpoint Privilege Management is generally available<!--1564177  -->  
Microsoft Endpoint Privilege Management (EPM) is now generally available and no longer in preview.

With [Endpoint Privilege Management](../protect/epm-overview.md), admins can set policies that allow standard users to perform tasks normally reserved for an administrator. To do so, you configure policies for *automatic* and *user-confirmed* workflows that elevate the run-time permissions for apps or processes you select. You then assign these policies to users or devices that have end users running without Administrator privileges. After the device receives a policy, EPM brokers the elevation on behalf of the user, allowing them to elevate approved applications without needing full administrator privileges. EPM also includes built-in insights and reporting.

Now that EPM is out of preview, it requires another license to use. You can choose between a stand-alone license that adds only EPM, or license EPM as part of the Microsoft Intune Suite. For more information, see [Use Intune Suite add-on capabilities](../fundamentals/intune-add-ons.md).

While Endpoint Privilege Management is now generally available, the [reports for EPM](../protect/epm-reports.md) will transition to a feature in *preview*, and will receive some more enhancements before being removed from preview.

#### Support for WDAC Application ID tagging with Intune Firewall Rules policy<!-- 17224780  -->  
Intune's *Microsoft Defender Firewall Rules* profiles, which are available as part of [endpoint security Firewall policy](../protect/endpoint-security-firewall-policy.md), now include the Policy App ID setting. This setting is described in the [*MdmStore/FirewallRules/{FirewallRuleName}/PolicyAppId*](/windows/client-management/mdm/Firewall-csp?WT.mc_id=Portal-fx#mdmstorefirewallrulesfirewallrulenamepolicyappid) CSP and supports specifying a Windows Defender Application Control (WDAC) Application ID tag.

With this capability, you can scope your firewall rules to an application or a group of applications and rely on your WDAC policies to define those applications. By using tags to link to and rely on WDAC policies, your Firewall Rules policy won't need to rely on the firewall rules option of an absolute file path, or use of a variable file path that can reduce security of the rule.

Use of this capability requires you to have WDAC policies in place that include *AppId* tags that you can then specify in your Intune Microsoft Defender Firewall Rules.

For more information, see the following articles in the Windows Defender Application Control documentation:

- [About application control for Windows](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control)
- [WDAC Application ID (AppId) Tagging guide](/windows/security/threat-protection/windows-defender-application-control/appidtagging/windows-defender-application-control-appid-tagging-guide)

Applies to:

- Windows 10/11

#### New App and browser isolation profile for Intune's endpoint security Attack Surface Reduction policy<!-- 17392386  -->  
We have released a new experience creating new *App and Browser Isolation* profiles for endpoint security Attack Surface Reduction policy. The experience for editing your previously created App and Browser isolation policies remains the same, and you can continue to use them. This update applies only for the new [App and Browser Isolation](../protect/endpoint-security-asr-policy.md#attack-surface-reduction-profiles) policies you create for the *Windows 10 and later* platform.

This update is part of the continuing [rollout of new profiles for endpoint security policies](../fundamentals/whats-new-archive.md#new-profile-templates-and-settings-structure-for-endpoint-security-policies), which began in April 2022.

Additionally, the new profile includes the following changes for the settings it includes:

- **Block external content from non-enterprise approved sites** - This setting is removed from the updated profile as it was supported only by Microsoft Edge Legacy. Microsoft Edge Legacy support ended in March 2021. [Microsoft 365 apps say farewell to Internet Explorer 11 and Windows 10 sunsets Microsoft Edge Legacy - Microsoft Community Hub](https://techcommunity.microsoft.com/t5/microsoft-365-blog/microsoft-365-apps-say-farewell-to-internet-explorer-11-and/ba-p/1591666).

- **Clipboard file type** – This setting is added to the updated profile and determines the type of content that can be copied from the host to Application Guard environment and vice versa. You can view the CSP for this new setting at [Settings/ClipboardFileType](/windows/client-management/mdm/windowsdefenderapplicationguard-csp#settingsclipboardfiletype) in the WindowsDefenderApplicationGuard CSP documentation.

### Intune apps

#### Newly available protected apps for Intune<!-- 17318943, 17319737, 17457189, 17624650  -->
The following protected apps are now available for Microsoft Intune:
- ixArma by INAX-APPS (iOS)
- myBLDNG by Bldng.ai (iOS)
- RICOH Spaces V2 by Ricoh Digital Services
- Firstup - Intune by Firstup, Inc. (iOS)

For more information about protected apps, see [Microsoft Intune protected apps](../apps/apps-supported-intune-apps.md).

### Role-based access control

#### New Assign (RBAC) permissions for organizational messages<!-- 16872833  -->  
The **Assign** RBAC permissions for organizational messages determines who can assign target Azure AD groups to an organizational message. To access RBAC permissions, sign in to the [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431) and go to **Tenant administration** > **Roles**.

This permission is also added to the **Organizational Messages Manager** built-in role.  Existing custom roles for managing Organizational Messages must be modified to add this permission for users to modify this setting.

- For more information, about role-based access control (RBAC), see [RBAC with Microsoft Intune](../fundamentals/role-based-access-control.md).
- For more information, about prerequisites for organization messages, see [Organizational messages prerequisites](../remote-actions/organizational-messages-prerequisites.md#role-based-access-control-requirements).

### Tenant administration

#### Delete organizational messages<!-- 15273028  -->  
You can now delete organizational messages from Microsoft Intune.  After you delete a message, it's removed from Intune, and no longer appears in the admin center. You can delete a message anytime, regardless of its status. Intune automatically cancels active messages after you delete them. For more information, see [Delete organizational messages](../remote-actions/organizational-messages-cancel.md#delete-message).  

#### Review audit logs for organizational messages<!-- 16576073 -->  
Use audit logs to track and monitor organizational message events in Microsoft Intune. To access the logs, sign in to the [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431) and go to **Tenant administration** > **Audit logs**. For more information, see [Audit logs for Intune activities](../fundamentals/monitor-audit-logs.md#audit-logs-for-intune-workloads).  

## Week of April 10, 2023

### Device configuration

#### User configuration support for Windows 10 multi-session VMs is now GA<!-- 17060455 -->

You can now:

- Configure user scope policies using **Settings catalog** and assign to groups of users.
- Configure user certificates and assign to users.
- Configure PowerShell scripts to install in the user context and assign to users.

Applies to:

- **Windows 10**
- Virtual machines created in [Azure Public and Azure Government clouds](../fundamentals/intune-govt-service-description.md)

## Week of April 3, 2023

### Device configuration

#### Add Google accounts to Android Enterprise personally owned devices with a work profile<!-- 9113561 -->

On Android Enterprise personally owned devices with a work profile, you can configure settings that restrict device features and settings. Currently, there's an **Add and remove accounts** setting. This setting prevents accounts from being added in the work profile, including preventing Google accounts.

This setting changed. You can now add Google accounts. The **Add and remove accounts** setting options are:

- **Block all accounts types**: Prevents users from manually adding or removing accounts in the work profile. For example, when you deploy the Gmail app into the work profile, you can prevent users from adding or removing accounts in this work profile.
- **Allow all accounts types**: Allows all accounts, including Google accounts. These Google accounts are blocked from installing apps from the **Managed Google Play Store**.

  This setting requires:

  - Google Play app version 80970100 or higher

- **Allow all accounts types, except Google accounts** (default): Intune doesn't change or update this setting. By default, the OS might allow adding accounts in the work profile.

For more information on the settings you can configure, go to [Android Enterprise device settings list to allow or restrict features on personally owned devices using Intune](../configuration/device-restrictions-android-enterprise-personal.md).

Applies to:

- Android Enterprise personally owned devices with a work profile

## Week of March 27, 2023

### App management

#### Update macOS DMG apps<!-- 13155074 -->
You can now update apps of type **macOS apps (DMG)** deployed using Intune. To edit a DMG app that's already created in Intune, upload the app update with the same bundle identifier as the original DMG app. For related information, see [Add a macOS DMG app to Microsoft Intune](../apps/lob-apps-macos-dmg.md).

#### Install required apps during pre-provisioning<!-- 12716381 -->
A new toggle is available in the Enrollment Status Page (ESP) profile that allows you to select whether you want to attempt to install required applications during the pre-provisioning (white glove) technician phase. We understand that installing as many applications as possible during pre-provisioning is desired to reduce the end user setup time. If there's an app install failure, ESP continues except for the apps specified in the ESP profile. To enable this function, you need to edit your Enrollment Status Page profile by selecting **Yes** on the new setting entitled **Only fail selected apps in technician phase**. This setting only appears if you have blocking apps selected. For information about ESP, go to [Set up the Enrollment Status Page](../enrollment/windows-enrollment-status.md).

## Week of March 20, 2023 (Service release 2303) 

### App management

### More minimum OS versions for Win32 apps<!-- 16842404  -->  
Intune supports more minimum operating system versions for Windows 10 and 11 when installing Win32 apps. In [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431), select **Apps** > **Windows** > **Add** > **Windows app (Win32)**. In the **Requirements** tab next to **Minimum operating system**, select one of the available operating systems. Other OS options include:

- Windows 10 21H2
- Windows 10 22H2
- Windows 11 21H2
- Windows 11 22H2

#### Managed apps permission is no longer required to manage VPP apps<!-- 17205644  -->  
You can view and manage VPP apps with only the **Mobile apps** permission assigned. Previously, the **Managed apps** permission was required to view and manage VPP apps. This change doesn't apply to Intune for Education tenants who still need to assign the **Managed apps** permission. More information about permissions in Intune is available at [Custom role permissions](../fundamentals/create-custom-role.md#custom-role-permissions).

### Device configuration

#### New settings and setting options available in the macOS Settings Catalog <!-- 16813395  -->  
The [Settings Catalog](../configuration/settings-catalog.md) lists all the settings you can configure in a device policy, and all in one place.

New settings are available in the Settings Catalog. In the [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431), you can see these settings at **Devices** > **Configuration profiles** > **Create profile** > **macOS** for platform > **Settings catalog** for profile type.

New settings include:

**Microsoft Defender > Tamper protection**:

- Enforcement level

**Microsoft Office > Microsoft OneDrive**:

- Automatic upload bandwidth percentage
- Automatically and silently enable the Folder Backup feature (aka Known Folder Move)
- Block apps from downloading online-only files
- Block external sync
- Disable automatic sign in
- Disable download toasts
- Disable personal accounts
- Disable tutorial
- Display a notification to users once their folders have been redirected
- Enable Files On-Demand
- Enable simultaneous edits for Office apps
- Force users to use the Folder Backup feature (aka Known Folder Move)
- Hide dock icon
- Ignore named files
- Include ~/Desktop in Folder Backup (aka Known Folder Move)
- Include ~/Documents in Folder Backup (aka Known Folder Move)
- Open at login
- Prevent users from using the Folder Backup feature (aka Known Folder Move)
- Prompt users to enable the Folder Backup feature (aka Known Folder Move)
- Set maximum download throughput
- Set maximum upload throughput
- SharePoint Prioritization
- SharePoint Server Front Door URL
- SharePoint Server Tenant Name

Applies to:

- macOS

For more information about configuring Settings Catalog profiles in Intune, go to [Create a policy using settings catalog](../configuration/settings-catalog.md).

#### Add custom Bash scripts to configure Linux devices<!-- 12508999  -->  
In Intune, you can add existing Bash scripts to configure Linux devices (**Devices** > **Linux** > **Configuration Scripts**).

When you create this script policy, you can set the context that the script runs in (user or root), how frequently the script runs, and how many times execution should retry.

For more information on this feature, go to [Use custom Bash scripts to configure Linux devices in Microsoft Intune](../configuration/custom-settings-linux.md).

Applies to:

- Linux Ubuntu Desktops

### Device enrollment

#### Support for the await final configuration setting for iOS/iPadOS Automated device enrollment (public preview)<!-- 13156553  -->  
Now in public preview, Intune supports a new setting called **Await final configuration** in eligible new and existing iOS/iPadOS automated device enrollment profiles. This setting enables an out-of-the-box locked experience in Setup Assistant. It prevents device users from accessing restricted content or changing settings on the device until most Intune device configuration policies are installed. You can configure the setting in an existing automated device enrollment profile, or in a new profile (**Devices** > **iOS/iPadOS** > **iOS/iPadOS enrollment** > **Enrollment program tokens** > **Create profile**). For more information, see [Create an Apple enrollment profile](../enrollment/device-enrollment-program-enroll-ios.md#create-an-apple-enrollment-profile).  

#### New setting gives Intune admins control over device-to-category mapping<!-- 15029839 -->  
Control visibility of the device category prompt in Intune Company Portal. You can now hide the prompt from end users and leave the device-to-category mapping up to Intune admins. The new setting is available in the admin center under **Tenant Administration** > **Customization** > **Device Categories**. For more information, see [Device categories](../apps/company-portal-app.md#device-categories).

#### Support for multiple enrollment profiles and tokens for fully managed devices <!-- 14205233  -->  
Create and manage multiple enrollment profiles and tokens for Android Enterprise fully managed devices. With this new functionality, you can now use the *EnrollmentProfileName* dynamic device property to automatically assign enrollment profiles to fully managed devices. The enrollment token that came with your tenant remains in a default profile. For more information, see [Set up Intune enrollment of Android Enterprise fully managed devices](../enrollment/android-fully-managed-enroll.md).

#### New Azure AD frontline worker experience for iPad (public preview)<!-- 6367427  -->  
*This capability begins to roll out to tenants in mid-April.*

Intune now supports a frontline worker experience for iPhones and iPads using Apple automated device enrollment. You can now enroll devices that are enabled in Azure AD shared mode via zero-touch. For more information about how to configure automated device enrollment for shared device mode, see [Set up enrollment for devices in Azure AD shared device mode](../enrollment/automated-device-enrollment-shared-device-mode.md).  

Applies to:

- iOS/iPadOS

### Device management

#### Endpoint security firewall policy support for log configurations<!-- 16730565   -->  
You can now configure settings in [endpoint security Firewall policy](../protect/endpoint-security-firewall-policy.md#devices-managed-by-intune) that configure firewall logging options. These settings can be found in the *Microsoft Defender Firewall* profile template for the *Windows 10 and later* platform, and are available for the *Domain*, *Private*, and *Public* profiles in that template.

Following are the new settings, all found in the [Firewall configuration service provider (CSP)](/windows/client-management/mdm/Firewall-csp?WT.mc_id=Portal-fx):

- Enable Log Success Connections
- Log File Path
- Enable Log Dropped Packets
- Enable Log Ignored Rules

Applies to:

- Windows 10
- Windows 11

#### Endpoint security firewall rules support for Mobile Broadband (MBB)<!-- 16730577  -->  
The **Interface Types** setting in [endpoint security Firewall policy](../protect/endpoint-security-firewall-policy.md#devices-managed-by-intune) now include the option for **Mobile Broadband**. Interface Types is available in the **Microsoft Defender Firewall Rules** profile for all platforms that support Windows. For information about the use of this setting and option, see [Firewall configuration service provider (CSP)](/windows/client-management/mdm/Firewall-csp?WT.mc_id=Portal-fx).

Applies to:  

- Windows 10
- Windows 11

#### Endpoint security firewall policy support for network list manager settings<!-- 9803477  -->  
We've added a pair of network list manager settings to [endpoint security Firewall policy](../protect/endpoint-security-firewall-policy.md#devices-managed-by-intune). To help determine when an Azure AD device is or isn't on your on-premises domain subnets, you can use the network list manager settings. This information can help firewall rules apply correctly.

The following settings are found in a new category named *Network List Manager*, that's available in the *Microsoft Defender Firewall* profile template for the *Windows 10, Windows 11, and Windows Server* platform:

- Allowed Tls Authentication Endpoints
- Configured Tls Authentication Network Name

For information about Network Categorization settings, see [NetworkListManager CSP](/windows/client-management/mdm/policy-csp-networklistmanager).

Applies to:  

- Windows 10
- Windows 11

#### Improvements to Devices area in admin center (public preview) <!-- 12775837 -->  
The Devices area in the admin center now has a more consistent UI, with more capable controls and an improved navigation structure so you can find the information you need faster. To opt in to the public preview and try out the new experience, go to **Devices** and flip the toggle at the top of the page. Improvements include:

* A new scenario-focused navigation structure.
* New location for platform pivots to create a more consistent navigation model.
* A reduction in journey, helping you get to your destination faster.
* Monitoring and reports are within the management workflows, giving you easy access to key metrics and reports without having to leave the workflow.
* A consistent way across list views to search, sort, and filter data.

For more information about the updated UI, see [Try new Devices experience in Microsoft Intune](microsoft-intune-admin-center-devices.md).

### Device security

#### Microsoft Intune Endpoint Privilege Management (public preview)<!-- 15654169   -->  
As a public preview, you can now use Microsoft Intune Endpoint Privilege Management. With Endpoint Privilege Management, admins can set policies that allow standard users to perform tasks normally reserved for an administrator. Endpoint Privilege Management can be configured in the [Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431) at **Endpoint security** > **Endpoint Privilege Management**.

With the public preview, you can configure policies for *automatic* and *user-confirmed* workflows that elevate the run-time permissions for apps or processes you select. You then assign these policies to users or devices that have end users running without Administrator privileges. Once policy is received, Endpoint Privilege Management will broker the elevation on behalf of the user, allowing them to elevate approved applications without needing full administrator privileges. The preview also includes built-in insights and reporting for Endpoint Privilege Management.

To learn how to activate the public preview and use Endpoint Privilege Management policies, start with [Use Endpoint Privilege Management with Microsoft Intune](../protect/epm-overview.md). Endpoint Privilege Management is part of the [Intune Suite](../fundamentals/intune-add-ons.md) offering, and free to try while it remains in public preview.

### Intune apps

#### Newly available protected apps for Intune<!-- 16927438, 17030201, 17074872 17103353 -->  
The following protected apps are now available for Microsoft Intune:

- EVALARM by GroupKom GmbH (iOS)
- ixArma by INAX-APPS (Android)
- Seismic | Intune by Seismic Software, Inc.
- Microsoft Viva Engage by Microsoft (formally Microsoft Yammer)

For more information about protected apps, see [Microsoft Intune protected apps](../apps/apps-supported-intune-apps.md).

### Monitor and troubleshoot

#### Diagnostic data collection for Endpoint Privilege Management<!-- 17392824   -->  
To support the release of Endpoint Privilege Management, we've updated [Collect diagnostics from a Windows device](../remote-actions/collect-diagnostics.md) to include the following data, which is collected from devices enabled for Endpoint Privilege Management:

- Registry keys:  
  - HKLM\SOFTWARE\Microsoft\EPMAgent

- Commands:  
  - %windir%\system32\pnputil.exe /enum-drivers
 
- Log files:  
  - %ProgramFiles%\Microsoft EPM Agent\Logs\\\*.*
  - %windir%\system32\config\systemprofile\AppData\Local\mdm\\\*.log

#### View status for pending and failed organizational messages<!-- 17017707  -->  
We've added two more states to organizational message reporting details to make it easier to track pending and failed messages in the admin center.

- **Pending**: The message hasn't been scheduled yet and is currently in progress.
- **Failed**: The message failed to schedule due to a service error.

For information about reporting details, see [View reporting details for organizational messages](../remote-actions/organizational-messages-reporting.md).  


#### More reporting information related to tenant attach devices<!-- 9220597  -->  
You can now view information for tenant attach devices in the existing antivirus reports under the Endpoint Security workload. A new column differentiates between devices managed by Intune and devices managed by Configuration Manager. This reporting information is available in [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431) by selecting **Endpoint security** > **Antivirus**.

## Week of March 13, 2023

### Device management

#### Meta Quest 2 and Quest Pro are now in Open Beta (US only) on Microsoft Intune for Android Open Source Devices

Microsoft Intune for Android open source project devices (AOSP) has welcomed Meta Quest 2 and Quest Pro into Open Beta for the US market.

For more information, go to [Operating systems and browsers supported by Microsoft Intune](../fundamentals/supported-devices-browsers.md)

Applies to:

- Android (AOSP)  

### App management

#### Trusted Root Certificates Management for Intune App SDK for Android<!-- 15135752 -->
If your Android application requires SSL/TLS certificates issued by an on-premises or private certificate authority to provide secure access to internal websites and applications, the Intune App SDK for Android now has support for certificate trust management. For more information and examples, see [Trusted Root Certificates Management](../developer/app-sdk-android-phase7.md#trusted-root-certificates-management).

#### System context support for UWP apps<!-- 16544103 -->
In addition to user context, you can deploy Universal Windows Platform (UWP) apps from the **Microsoft Store app (new)** in system context. If a provisioned *.appx* app is deployed in system context, the app auto-installs for each user that logs in. If an individual end user uninstalls the user context app, the app still shows as installed because it's still provisioned. In addition, the app must not already be installed for any users on the device. Our general recommendation is to not mix install contexts when deploying apps. Win32 apps from the **Microsoft Store app (new)** already support system context.

## Week of March 6, 2023  

### App management

#### Deploy Win32 apps to device groups<!-- 7359954 -->
You can now deploy Win32 apps with **Available** intent to device groups. For more information, see [Win32 app management in Microsoft Intune](../apps/apps-win32-app-management.md). 

### Device management  

#### New URL for Microsoft Intune admin center<!-- 17441426 -->  
The Microsoft Intune admin center has a new URL: [https://intune.microsoft.com](https://intune.microsoft.com). The previously used URL, [https://endpoint.microsoft.com](https://endpoint.microsoft.com), continues to work but will redirect to the new URL in late 2023. We recommend taking the following actions to avoid issues with Intune access and automated scripts: 

* Update login or automation to point to `https://intune.microsoft.com`. 
* Update your firewalls, as needed, to allow access to the new URL. 
* Add the new URL to your favorites and bookmarks. 
* Notify your helpdesk and update IT administrator documentation.  

### Tenant administration

#### Add CMPivot queries to Favorites folder<!-- 16702226 -->
You can add your frequently used queries to a **Favorites** folder in CMPivot. CMPivot allows you to quickly assess the state of a device managed by Configuration Manager via Tenant Attach and take action. The functionality is similar to one already present in the Configuration Manager console. This addition helps you keep all your most used queries in one place. You can also add tags to your queries to help search and find queries. The queries saved in the Configuration Manager console aren't automatically added to your **Favorites** folder. You need to create new queries and add them to this folder. For more information about CMPivot, see [Tenant attach: CMPivot usage overview](../../configmgr/tenant-attach/cmpivot-start.md).

### Device enrollment

#### New Microsoft Store apps now supported with the Enrollment Status Page<!-- 16280325 -->
The Enrollment Status Page (ESP) now supports the new Microsoft store applications during Windows Autopilot. This update enables better support for the new Microsoft Store experience and should be rolling out to all tenants starting with Intune 2303. For related information, see [Set up the Enrollment Status Page](../enrollment/windows-enrollment-status.md).

## Week of February 27, 2023

### Device configuration

#### Support for Locate device on Android Enterprise corporate owned fully managed and Android Enterprise corporate owned work profile devices<!--12391424 -->

You can now use "Locate device" on Android Enterprise corporate owned fully managed and Android Enterprise corporate owned work profile devices. With this feature, admins are able to locate lost or stolen corporate devices on-demand.

In [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431), you need to turn the feature on using **Device Restrictions** in **Device Configuration** for Android Enterprise.

Select **Allow** on the **Locate device** toggle for fully managed and corporate owned work profile devices and select applicable groups. **Locate device** is available when you select **Devices**, and then select **All devices**. From the list of devices you manage, select a supported device, and choose the **Locate device** remote action.

For information on locating lost or stolen devices with Intune, go to:

- [Locate lost or stolen devices with Intune](../remote-actions/device-locate.md)

Applies to:

- Android Enterprise corporate owned fully managed
- Android Enterprise corporate owned dedicated devices
- Android Enterprise corporate owned work profile

#### Intune add-ons <!-- 13817801 -->

Microsoft Intune Suite provides mission-critical advanced endpoint management and security capabilities into Microsoft Intune. 

You can find add-ons to Intune in the [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431) under **Tenant administration** > **Intune add-ons**.

For detailed information, see [Use Intune Suite add-on capabilities](../fundamentals/intune-add-ons.md).

#### View ServiceNow Incidents in the Intune Troubleshooting workspace (Preview)<!-- 12508062 -->

In public preview, you can view a list of ServiceNow incidents associated with the user you've selected in the Intune Troubleshooting workspace. This new feature is available under **Troubleshooting + Support** > select a user > **ServiceNow Incidents**. The list of incidents shown have a direct link back to the source incident and show key information from the incident. All incidents listed link the "Caller" identified in the incident with the user selected for Troubleshooting.

For more information, go to [Use the troubleshooting portal to help users at your company](service-now-integration.md).

### Device security

#### Microsoft Tunnel for MAM is now generally available<!-- 16883728  -->

Now out of preview and generally available, you can add [Microsoft Tunnel for Mobile Application Management](../protect/microsoft-tunnel-overview.md) to your tenant. Tunnel for MAM supports connections from unenrolled [Android](../protect/microsoft-tunnel-mam-android.md) and [iOS](../protect/microsoft-tunnel-mam-ios.md) devices. This solution provides your tenant with a lightweight VPN solution that allows mobile devices access to corporate resources while adhering to your security policies.

In addition, MAM Tunnel for iOS now supports Microsoft Edge.

Previously, Tunnel for MAM for Android and iOS was in public preview and free for use. With this release as generally available, this solution now requires an add-on license for its use.

For licensing details, see [Intune add-ons](../fundamentals/intune-add-ons.md).

Applies to:  
- Android
- iOS  

### Tenant administration  

#### Organizational messages now support custom destination URLs <!-- 16576068  -->

You can now add any custom destination URL to organizational messages in the taskbar, notifications area, and Get Started app. This feature applies to Windows 11. Messages created with Azure AD-registered domains that are in a scheduled or active state are still supported. For more information, see [Create organizational messages](../remote-actions/organizational-messages-create.md?tabs=taskbar#step-1-create-a-message). 

## Week of February 20, 2023 (Service release 2302)

### App management

#### Latest iOS/iPadOS version available as minimum OS requirement for LOB and store apps<!-- 16433620  -->  
You can specify iOS/iPadOS 16.0 as the minimum operating system for line-of-business and store app deployments. This setting option is available in [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431) by selecting **Apps** > **iOS/iPadOS** > *iOS store app or Line-of-business app*. For more information about managing apps, see [Add apps to Microsoft Intune](../apps/apps-add.md).

#### Newly available protected app for Intune<!-- 16655639  -->  
The following protected app is now available for Microsoft Intune:

- Egnyte for Intune by Egnyte

For more information about protected apps, see [Microsoft Intune protected apps](../apps/apps-supported-intune-apps.md).

### Device configuration

#### Endpoint Manager admin center is renamed to Intune admin center<!-- 15560662   -->  
The Microsoft Endpoint Manager admin center is now called the **Microsoft Intune admin center**.

#### A new Associated Assignments tab for your filters<!-- 7538503  -->  
When you assign an app or policy, you can filter the assignment using different device properties, such as device manufacturer, model, and ownership. You can create and associate a filter with the assignment.

After you create a filter, there's a new **Associated Assignments tab**. This tab shows all the policy assignments, the groups that receive the filter assignments, and if the filter is using **Exclude** or **Include**:

1. Sign in to the Microsoft Intune admin center.
2. Go to **Devices** > **Filters** > Select an existing filter > **Associated Assignments tab**.
 
For more information on filters, go to:

- [Use filters when assigning your apps, policies, and profiles in Intune](filters.md)
- [Device properties, operators, and rule editing when creating filters in Intune](filters-device-properties.md)

#### Size and generation included in iOS/iPadOS model information<!-- 16406692  -->  
You can view the size and generation for enrolled iOS/iPadOS devices as part of the **Model** attribute in **Hardware device details**.

Go to **Devices > All devices** > select one of your listed devices and select **Hardware** to open its details. For example, iPad Pro 11 inch (3rd generation) displays for the device model instead of iPad Pro 3. For more information, go to: [See device details in Intune](../remote-actions/device-inventory.md#hardware-device-details)

Applies to:  
- **iOS/iPadOS**

#### Disable Activation Lock device action for supervised iOS/iPadOS devices<!-- 15571509 -->  
You can use the **Disable Activation Lock** device action in Intune to bypass Activation Lock on iOS/iPadOS devices without requiring the current username or password.

This new action is available under  **Devices > iOS/iPadOS >** *select one of your listed devices* **> Disable Activation Lock**.

More information on managing Activation Lock is available at [Bypass iOS/iPadOS Activation Lock with Intune](../remote-actions/device-activation-lock-disable.md) or on Apple's website at [Activation Lock for iPhone, iPad, and iPod touch - Apple Support.](https://support.apple.com/en-us/HT201365)

Applies to:  
- **iOS/iPadOS**

#### Allow Temporary Enterprise Feature Control is available in the Settings Catalog<!-- 15752120  -->  
In on-premises group policy, there's an **Enable features introduced via servicing that are off by default** setting.

In Intune, this setting is known as **Allow Temporary Enterprise Feature Control** and is available in the Settings Catalog. This servicing adds features that off by default. When set to **Allowed**, these features are enabled and turned on.

For more information on this feature, go to:

- [AllowTemporaryEnterpriseFeatureControl](/windows/client-management/mdm/policy-csp-Update#allowtemporaryenterprisefeaturecontrol) policy CSP
- [Blog: Commercial control for continuous innovation](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/commercial-control-for-continuous-innovation/ba-p/3737575)

The Windows features that enabled by this policy setting will be released later in 2023. Intune is releasing this policy setting now for your awareness and preparation, which is before any need to use the setting with future Windows 11 releases.

For more information on the settings catalog, go to [Use the settings catalog to configure settings on Windows, iOS/iPadOS and macOS devices](../configuration/settings-catalog.md).

Applies to:

- Windows 11

### Device management

#### Device Control support for Printer Protection (Preview)<!-- 12355154  -->  
In public preview, Device Control profiles for Attack Surface Reduction policy now support [reusable settings groups for Printer Protection](../protect/reusable-settings-groups.md#add-reusable-groups-to-a-device-control-profile).

Microsoft Defender for Endpoint Device Control [Printer Protection](/microsoft-365/security/defender-endpoint/printer-protection-overview) enables you to audit, allow, or prevent printer with or without exclusions within Intune. It allows you to block users from printing via a non-corporate network printer or non-approved USB printer. This feature adds another layer of security and data protection for work from home and remote work scenarios.

Applies to:  
- Windows 10
- Windows 11

#### Support to delete stale devices that are managed through Security Management for Microsoft Defender for Endpoint<!--14729617  -->   
You can now **Delete** a device that's managed through the [Security Management for Microsoft Defender for Endpoint](../protect/mde-security-integration.md) solution from within the Microsoft Intune admin center. The delete option appears along with other device management options when you view the device's Overview details. To locate a device managed by this solution, in the admin center go to **Devices** > **All devices**, and then select a device that displays either *MDEJoined* or *MDEManaged* in the *Managed by* column.

#### New settings and setting options available in the Apple Settings Catalog<!-- 16813380  -->  
The [Settings Catalog](../configuration/settings-catalog.md) lists all the settings you can configure in a device policy, and all in one place.

New settings are available in the Settings Catalog. In the [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431), you can see these settings at **Devices** > **Configuration profiles** > **Create profile** > **iOS/iPadOS** or **macOS** for platform > **Settings catalog** for profile type.

New settings include:

**Login > Service Management - Managed Login Items**:

- Team Identifier

**Microsoft Office > Microsoft Office**:

- Office Activation Email Address

Applies to:  
- macOS

**Networking > Domains**:

- Cross Site Tracking Prevention Relaxed Domains

Applies to:  
- iOS/iPadOS

For more information about configuring Settings Catalog profiles in Intune, see [Create a policy using settings catalog](../configuration/settings-catalog.md).

### Device security
 
#### Use Endpoint security Antivirus policy to manage Microsoft Defender update behavior (Preview)<!-- 11890335 -->  
As part of a public preview for Endpoint security [Antivirus policy](../protect/endpoint-security-antivirus-policy.md), you can use the new profile **Defender Update controls** for the *Windows 10 and later* platform to manage update settings for Microsoft Defender. The new profile includes settings for the rollout release channel by which devices and users receive Defender Updates that are related to daily security intelligence updates, monthly platform updates, and monthly engine updates.

This profile includes the following settings, which are all directly taken from [Defender CSP - Windows Client Management](/windows/client-management/mdm/policy-csp-Defender).

- Engine Updates Channel
- Platform Updates Channel
- Security Intelligence Updates Channel

These settings are also available from the [settings catalog](../configuration/settings-catalog.md) for the *Windows 10 and later* profile.

Applies to:  
- Windows 10
- Windows 11

## Week of February 6, 2023

### Tenant administration

#### Apply recommendations and insights to enrich the Configuration Manager site health and device management experience<!--16957774 -->

You can now use the Microsoft Intune admin center to view recommendations and insights for your Configuration Manager sites. These recommendations can help you improve the site health and infrastructure and enrich the device management experience.

Recommendations include:  

- How to simplify your infrastructure
- Enhance device management
- Provide device insights
- Improve the health of the site

To view recommendations, open the [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431) and go to **Tenant administration** > **Connectors and tokens** > **Microsoft Endpoint Configuration Manager**,  and select a *site* to view recommendations for that site.  Once selected, the *Recommendations* tab displays each insight along with a *Learn more* link. This link opens details on how to apply that recommendation.

For more information, see [Enable Microsoft Intune tenant attach - Configuration Manager](../../configmgr/tenant-attach/device-sync-actions.md).

## Week of January 30, 2023

### Device management

#### HTC Vive Focus 3 supported on Microsoft Intune for Android Open Source Devices<!--15670082--> 

Microsoft Intune for Android open source project devices (AOSP) now supports HTC Vive Focus 3. 

For more information, go to [Operating systems and browsers supported by Microsoft Intune](../fundamentals/supported-devices-browsers.md)

Applies to:

- Android (AOSP)

#### Introducing support for laser pointers in Remote Help<!-- 16108312 -->

In Remote Help, you can now use a laser pointer when you're providing assistance on Windows.

For more information on Remote Help, go to [Remote Help](/mem/intune/fundamentals/remote-help).

Applies to:

- Windows 10/11

## What's new archive
<!-- Past announcements that are older than six months will be moved to the archive -->

For previous months, see the [What's new archive](whats-new-archive.md).

## Notices

[!INCLUDE [Intune notices](../includes/intune-notices.md)]
