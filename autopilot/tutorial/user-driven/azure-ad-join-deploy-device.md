---
title: Windows Autopilot user-driven Azure AD join - Step 8 of 8 - Deploy the device
description: How to - Windows Autopilot user-driven Azure AD join - Step 8 of 8 - Deploy the device.
ms.prod: windows-client
ms.localizationpriority: medium
author: frankroj
ms.author: frankroj
ms.reviewer: jubaptis
manager: aaroncz
ms.date: 06/26/2023
ms.topic: tutorial
ms.collection: 
  - tier1
  - highpri
ms.technology: itpro-deploy
appliesto:
  - ✅ <a href="https://learn.microsoft.com/windows/release-health/supported-versions-windows-client" target="_blank">Windows 11</a>
  - ✅ <a href="https://learn.microsoft.com/windows/release-health/supported-versions-windows-client" target="_blank">Windows 10</a>
---

# User-driven Azure AD join: Deploy the device

Autopilot user-driven Azure AD join steps:
- Step 1: [Set up Windows automatic Intune enrollment](azure-ad-join-automatic-enrollment.md)
- Step 2: [Allow users to join devices to Azure AD](azure-ad-join-allow-users-to-join.md)
- Step 3: [Register devices as Autopilot devices](azure-ad-join-register-device.md)
- Step 4: [Create a device group](azure-ad-join-device-group.md)
- Step 5: [Configure and assign Autopilot Enrollment Status Page (ESP)](azure-ad-join-esp.md)
- Step 6: [Create and assign Autopilot profile](azure-ad-join-autopilot-profile.md)
- Step 7: [Assign Autopilot device to a user (optional)](azure-ad-join-assign-device-to-user.md)
> [!div class="checklist"]
> - **Step 8: Deploy the device**

For an overview of the Windows Autopilot user-driven Azure AD join workflow, see [Windows Autopilot user-driven Azure AD join overview](azure-ad-join-workflow.md#workflow)

## Deploy the device

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RW15DG8]

Once all of the configurations for the Windows Autopilot user-driven Azure AD join deployment have been completed on the Intune and Azure AD side, the next step is to start the Autopilot deployment process on the device. If desired, deploy any additional applications and policies that should run during the Autopilot deployment to a device group that the device is a member of.

To start the Autopilot deployment process on the device, select a device that is part of the device group created in the previous [Create a device group](azure-ad-join-device-group.md) step, and then follow these steps:

[!INCLUDE [Network connectivity](../includes/network-connectivity.md)]

4. Once the Autopilot process begins, the Azure AD sign-in page appears. At the Azure AD sign-in page, if a user was assigned to the device, their username may be pre-populated in this screen. Enter the Azure AD credentials for the user and then select **Next** (Windows 10) or **Sign in** (Windows 11) to sign in. If necessary, proceed through the multi-factor authentication (MFA) screens.

5. After authenticating with Azure AD, the Enrollment Status Page (ESP) appears. The Enrollment Status Page (ESP) displays progress during the provisioning process across three phases:

   - **Device preparation** (Device ESP)
   - **Device setup** (Device ESP)
   - **Account setup** (User ESP)

    The first two phases of **Device preparation** and **Device setup** are part of the Device ESP while the final phase of **Account setup** is part of the User ESP.

6. Once **Account setup** and the user ESP process completes, the provisioning process completes, the ESP finishes, and the Desktop appears. At this point, the end-user can start using the device.

## Deployment tips

[!INCLUDE [Tips assignments](../includes/tips-assignments.md)]

[!INCLUDE [Tips AADJ screens](../includes/tips-aadj-screens.md)]

[!INCLUDE [Tips ESP progress](../includes/tips-esp-progress.md)]

## More information
