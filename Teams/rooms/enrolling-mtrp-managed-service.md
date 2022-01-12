---
title: 在 Teams 会议室 托管服务中Microsoft Teams 会议室高级版设备
author: v-smandalika
ms.author: v-smandalika
manager: serdars
ms.reviewer: ''
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 了解如何在托管服务Microsoft Teams 会议室注册Microsoft Teams 会议室高级版帐户。
f1keywords: ''
ms.openlocfilehash: 79dee52cc9c814338c6c5dc4c91245155ef2fd41
ms.sourcegitcommit: a969502c0a5237caf041d7726f4f1edefdd75b44
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2022
ms.locfileid: "61766965"
---
# <a name="enroll-a-device-in-the-microsoft-teams-rooms-premium-managed-service"></a>在托管服务中Microsoft Teams 会议室高级版设备

若要在Microsoft Teams 会议室服务中注册Teams 会议室 高级版设备，需要向托管服务管理员再分配一个用户，然后使用该用户完成注册步骤。

## <a name="assign-users-to-the-managed-service-administrator-role"></a>将用户分配到托管服务管理员角色

完成以下步骤，将用户分配到托管服务管理员角色：

1. 使用与[Teams 会议室 高级版](https://portal.rooms.microsoft.com/)登录管理员权限相同的管理员权限登录到 Microsoft 365 管理中心。
2. 导航到  >  **设置设置**  >  **角色"，** 然后选择"**托管服务管理员"。**
3. 在 **"托管服务管理员"** 下，选择"**分配"** 选项卡，然后选择"**添加"。**
4. 按照向导命名分配并选择应添加到该分配的用户。 该作业将应用于所有会议室和会议室组。
5. 在作业向导的末尾，选择"添加 **分配"。**

分配有托管服务管理员角色的用户负责对托管服务门户进行日常管理和Teams 会议室 高级版监视。

将用户分配到托管服务管理员角色后，请继续"注册设备"部分，[](#enroll-a-teams-rooms-device)将Teams 会议室添加到托管服务门户。

## <a name="enroll-a-teams-rooms-device"></a>注册Teams 会议室设备

 若要在托管服务中Teams 会议室 高级版设备，请参阅[监视设备软件安装](monitor-software-installation-guide.md)。

<!--2. Select on the **?** icon at the top right-hand corner of the portal to launch the help menu. The help menu includes an [Installation guide](https://portal.rooms.microsoft.com/docs/MMR%20Monitoring%20Software%20Installation%20Guide%20Feb%202021.pdf) containing detailed enrollment instructions:

    1. Review the **Pre-requisites** section in the Installation guide. Confirm that the URLs listed in the **URLs Required for Communication** list are added to your firewall's traffic allow list.
    2. Follow the instructions in the **Enabling TPM Settings** section to enable the Trusted Platform Module (TPM) functionality on your device.
    3. Follow the instructions in the **Adding Proxy Settings** section to configure your device to use your proxy gateway, if you have one.
    4. Follow the instructions in the **Process** section to install the monitoring agent software and configure the self enrollment key on your device.

3. After the monitoring agent and unique XML key are configured on your device, navigate to **Rooms** > room name > **Status**, and then select **Enroll**.

    > [!NOTE]
    > The Teams Rooms device will remain in the **Onboarding** state until a Managed Service Administrator enrolls the device using the portal.

    See [Monitoring device software installation](monitoring-software-installation-guide.md).

<!--## Link to Installation guide

The **Help** menu provides a link to the [Installation guide](https://portal.rooms.microsoft.com/docs/MMR%20Monitoring%20Software%20Installation%20Guide%20Feb%202021.pdf) which in turn provides the following information:

- Instructions on URLs that need to be allow-listed to serve to enable room telemetry to be sent to the managed service.
- Instructions for applying the Microsoft Teams Rooms Premium monitoring agent and unique XML key as part of enrolling a device in the managed service.
- Troubleshooting instructions.-->
