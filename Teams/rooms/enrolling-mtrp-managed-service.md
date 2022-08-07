---
title: 在Microsoft Teams 会议室高级版托管服务中注册Teams 会议室设备
author: donnah007
ms.author: v-donnahill
manager: serdars
ms.reviewer: ''
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_MTRP
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 了解如何在托管服务Microsoft Teams 会议室高级版注册Microsoft Teams 会议室帐户。
f1keywords: ''
ms.openlocfilehash: f721406381e1eb99584563473196893bc21cf39b
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2022
ms.locfileid: "67270997"
---
# <a name="enroll-a-device-in-the-microsoft-teams-rooms-premium-managed-service"></a>在Microsoft Teams 会议室高级版托管服务中注册设备

若要在Teams 会议室高级托管服务中注册Microsoft Teams 会议室设备，需要将一个或多个用户分配给托管服务管理员，然后使用该用户完成注册步骤。

## <a name="assign-users-to-the-managed-service-administrator-role"></a>将用户分配到托管服务管理员角色

完成以下步骤，将用户分配到托管服务管理员角色：

1. 使用与用于登录Microsoft 365 管理中心的管理员权限相同的管理员权限登录到Teams 会议室[高级门户](https://portal.rooms.microsoft.com/)。
2. 导航到 **“设置** > **设置** > **角色** ”，然后选择 **“托管服务管理员**”。
3. 在 **“托管服务管理员**”下，选择 **“分配”** 选项卡，然后选择 **“添加**”。
4. 按照向导命名分配，然后选择应添加到分配的用户。 分配将应用于所有会议室和会议室组。
5. 在分配向导结束时，选择 **“添加分配**”。

分配有托管服务管理员角色的用户负责日常管理和监视Teams 会议室高级托管服务门户。

将用户分配到托管服务管理员角色后，请继续[注册Teams 会议室设备](enroll-a-device.md)，将Teams 会议室设备添加到托管服务门户。

<!-- ## Enroll a Teams Rooms device

 To enroll a device in the Teams Rooms Premium managed service, see [Monitoring device software installation](monitor-software-installation-guide.md).

2. Select on the **?** icon at the top right-hand corner of the portal to launch the help menu. The help menu includes an [Installation guide](https://portal.rooms.microsoft.com/docs/MMR%20Monitoring%20Software%20Installation%20Guide%20Feb%202021.pdf) containing detailed enrollment instructions:

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
