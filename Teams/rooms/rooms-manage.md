---
title: 管理 Microsoft Teams 会议室
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 39d7dc65-22c3-400f-91f1-87ed2fd792b6
ms.collection:
- M365-collaboration
description: 了解如何开发和执行持续维护和操作，以确保Microsoft Teams 会议室系统可供用户使用。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 02faaec97837f61befaa5320f7d73b84e33d25c2
ms.sourcegitcommit: d3c48f0c147cf0c47d5eb4ea1128b5bca13be718
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/01/2022
ms.locfileid: "62298997"
---
# <a name="manage-microsoft-teams-rooms"></a>管理 Microsoft Teams 会议室

如果组织中Microsoft Teams 会议室，则有灵活的管理选项。  可以在管理所有解决方案（包括管理中心）的同一Teams集中Microsoft Teams设备。 或者，可以使用托管服务将管理责任Microsoft Teams 会议室[专家](https://portal.rooms.microsoft.com)。  还可以将管理访问权限委派给所选择的合作伙伴，以选择任一选项。

使用Microsoft Teams管理中心，可以：

- 执行设备管理，例如重新启动设备和下载设备日志
- 应用Teams设置
- 检查设备及其Microsoft Teams 会议室（包括相机、显示器、麦克风等）的运行状况
- 查看当前和过去的会议活动 (，例如有关呼叫质量、网络运行状况和连接的详细信息，以及会议参与者) 
- 查看外围设备 (设备，例如摄像机和投影仪) 连接到Microsoft Teams 会议室

若要管理Teams 会议室，请打开 Microsoft Teams [管理中心并](https://admin.teams.microsoft.com)转到Teams **设备** > Teams 会议室 **Windows**。

:::image type="content" source="../media/teams-rooms-summary2.png" alt-text="Teams 会议室管理中心Teams摘要页面。":::


> [!IMPORTANT]
> 若要使用 Teams 管理中心管理设备，需要分配全局管理员、Teams管理员或Teams管理员角色。

## <a name="make-changes-to-teams-rooms-devices"></a>对设备Teams 会议室更改

如果有多个设备Teams 会议室，可以同时在多个设备上执行大多数操作。 例如，你可以同时Teams所有应用设置Teams 会议室应用设置。

### <a name="device-settings"></a>设备设置

可以更改组织中一个或多个Teams 会议室的设置。 若要更改设置，请选择要管理的设备或设备，然后选择"编辑设置 **"**。 将打开一个新窗格，其中包含可以更改的所有设置。 下表列出了可以使用管理中心更改Teams设置。 某些设置仅在选择单个应用时Teams 会议室。

如果选择多个选项，则支持批量编辑的设置会显示以下两个选项。

- **保留现有值** 如果选择此选项，不会对所选选项上的设置Teams 会议室更改。
- **将现有值替换为** 如果选择此选项，可以使用提供的值Teams 会议室更新所选应用上的设置。
    > [!CAUTION]
    > 你选择更新的设置上的现有值将替换为你提供的值。 如果要添加到现有值列表，则需要包含包含要添加的值的现有值。 例如，如果设置的现有域 `contoso.com, fabrikam.com`列表为 ， `northwindtraders.com`并且你想要添加 ，则需要提供的值将是 `contoso.com, fabrikam.com, northwindtraders.com`。
    >
    > 如果选择多个Teams 会议室，则你选择的所有设备的设置将更改为你提供的值。 如果Teams 会议室设置具有不同的值，则这些值将全部更新为相同的值。

| 设置                                                      | 接受的值                                        | 支持批量编辑 |
|--------------------------------------------------------------|--------------------------------------------------------|--------------------|
| *帐户*                                                    |                                                        |                    |
| **电子邮件**                                                    | 电子邮件地址                                          | 否                 |
| **支持的会议模式**                                   | Microsoft Teams仅<br>Skype for Business (默认) Microsoft Teams<br>Skype for Business和Microsoft Teams (默认) <br>Skype for Business仅|是|
| **新式身份验证**                                    | 开<br>关闭                                              | 是                |
| **Exchange地址**                                         | 电子邮件地址                                          | 否                 |
| **域\用户名 (可选)**                               | 帐户域和用户名                           | 否                 |
| **配置域**                                         | 逗号分隔列表                                   | 是                |
| *会议*                                                   |                                                        |                    |
| **自动屏幕共享**                                 | 开<br>关闭                                              | 是                |
| **HDMI 输入音频共享**                                 | 开<br>关闭                                              | 是                |
| **显示会议名称**                                       | 开<br>关闭                                              | 是                |
| **如果其他人离开会议，自动离开**                 | 开<br>关闭                                              | 是                |
| **加入第三方会议**                 | Cisco Webex<br>缩放                                              | 是                |
| **使用会议室信息加入**                 | 选中<br>未选择                                              | 是                |
| **使用自定义信息加入**                 | 选中<br>未选择                                              | 是                |
| **所需的 (名称)**                 | 会议室或空间的名称                                              | 是                |
| **需要 (电子邮件)**                 | 电子邮件地址                                              | 是                |
| *Device*                                                     |                                                        |                    |
| **双监视器模式**                                        | 开<br>关闭                                              | 是                |
| **允许内容复制** | 选中<br>未选择                                 | 是                |
| **蓝牙信号灯**                                      | 开<br>关闭                                              | 是                |
| **自动接受基于邻近感应的会议邀请** | 选中<br>未选择                                 | 是                |
| **发送有反馈的日志**                                  | 开<br>关闭                                              | 是                |
| **日志和反馈的电子邮件地址**                      | 电子邮件地址                                          | 是                |
| *协调会议*                                                     |                                                        |                    |
| **协调会议** | 开<br>关闭                                 | 否                |
| **打开此设备的麦克风** | 开<br>关闭                                 | 否                |
| **允许用户在加入会议时启用** | 选中<br>未选择                                 | 否                |
| **打开此设备的相机** | 开<br>关闭                                 | 否                |
| **允许用户在加入会议时启用** | 选中<br>未选择                                 | 否                |
| **为此设备打开白板** | 开<br>关闭                                 | 否                |
| **受信任的设备帐户 (逗号分隔)** | 设备列表                              | 否                |
| *外围设备*                                                |                                                        |                    |
| **会议麦克风**                                  | 可用麦克风列表                          | 否                 |
| **会议发言人**                                     | 可用发言人列表                             | 否                 |
| **默认卷**                                           | 0-100                                                  | 否                 |
| **默认扬声器**                                          | 可用发言人列表                             | 否                 |
| **默认卷**                                           | 0-100                                                  | 否                 |
| **内容相机**                                           | 可用相机列表                              | 否                 |
| **内容相机增强功能**                              | 开<br>关闭                                              | 否                 |
| **将内容相机旋转 180 度**                        | 开<br>关闭                                              | 否                 |
| *"进行"。*                                                    |                                                        |                    |
|                                                              | 默认值<br>无主题<br>自定义<br>内置主题列表   | 是                |

### <a name="cortana-settings"></a>Cortana设置

可以使用 PowerShell 为Cortana设备启用语音激活或推送交谈，也可以单独为每台设备启用语音激活。

请参阅[Microsoft Teams 会议室语音Windows](../cortana-in-teams.md)"Cortana语音帮助"一Teams说明。

### <a name="front-row-layout-settings"></a>前行布局设置

前行是会议视图布局选项，Teams 会议室上Windows。

| Teams设备 | 应用版本 | 房间前显示 |
|--------------|-------------|-----------------------|
|Microsoft Teams 会议室上Windows | 4.11.14.0 到 4.11.12.0 | 支持单显示器和双显示器;最小大小：46 英寸;纵横比 16：9（分辨率为 1920*1080）或 21：9（分辨率为 2560x1080）;所有显示器都应在设置中设置为 100% 缩放Windows设置 |

请参阅[Microsoft Teams 会议室](rooms-operations.md#change-scale-and-resolution)操作，调整显示设置以满足前行的要求。

若要了解如何将前行设置为聊天室的默认布局或如何将其关闭，请参阅使用 XML 配置文件Microsoft Teams 会议室远程管理主机[设置](xml-config-file.md#set-front-row-as-the-default-layout)。

有关 [管理 Front](known-issues.md#Limits) 行的信息，请参阅已知问题。

## <a name="device-restart-options"></a>设备重启选项

只有在重启设备设置后，Teams 会议室设置才生效。 进行需要重启的更改时，可以选择是立即重启还是计划重启。 下面是可用的重启选项：

- **立即重启** 如果选择此选项，则要更改的所有设备将在你选择此选项后立即重新启动。
- **计划的重启** 如果选择此选项，可以在对组织造成干扰较少的时间重启要更改的设备。
  - **选择日期和时间** - 选择重新启动设备的特定日期和时间。 选择的日期和时间是正在重启的设备的本地日期和时间。 
  - **让更新保留为夜间重新启动** 设备会在夜间重新启动以执行维护。 在此重启期间，将应用对设备所做的更改。

> [!CAUTION]
> Teams 会议室重启时使用的进程在重启过程中将不可用。 他们将与进行中的会议断开连接，并且无法加入新会议。

## <a name="remove-device"></a>删除设备

删除设备时，设备将从组织中删除，并且不再显示在 Teams 管理中心Teams 会议室上Windows列表中。

如果删除设备，但该设备仍配置了有效的用户名和密码，则如果该设备再次连接到 Teams 会议室，则会自动Microsoft 365列表中。

若要删除一个或多个设备，请执行下列操作：

1. 转到 **Teams设备** > **Teams 会议室Windows** 并选择要删除的设备。
2. 选择“**删除**”。

## <a name="download-device-logs"></a>下载设备日志

如果 Microsoft 支持人员请求下载设备诊断日志文件的副本，可以下载该副本。 日志文件将压缩为可从管理中心下载的 zip Teams文件。

若要将日志从Teams 会议室下载到计算机，请执行下列操作：

1. 转到 **Teams设备** > **Teams 会议室** Windows并选择想要从其中下载日志的设备的名称。
1. 选择 **"下载设备日志"**。 设备日志可能需要几分钟才能可用。
1. 选择" **历史记录"** 选项卡，然后选择日志文件"文件" **下的链接**。 包含设备的诊断日志文件的 zip 文件将下载到浏览器的默认 Downloads 文件夹。

## <a name="view-device-information"></a>查看设备信息

从Teams管理中心，可以查看组织中所有设备的总体状态，并单独查看每个设备的详细信息。

### <a name="teams-rooms-system-dashboard"></a>Teams 会议室系统仪表板

系统Teams 会议室仪表板一目了然地显示所有设备的状态和运行状况。

### <a name="device-details-view"></a>设备详细信息视图

若要查看有关设备的详细信息，请从设备列表中选择其名称。 在详细信息视图中，可以看到有关设备的以下信息：

- **运行状况** 显示会议室设备Teams运行状况。 运行状况可以是"正常 **"或** " **不正常"**。
- **脱机，因为** 显示上次Microsoft 365设备通信的时间。
- **设备状态** 显示设备的当前 **状态：空闲**、Teams **、** Skype **或"正在****"**。
- **外围设备** 显示连接到会议室设备Teams外围设备及其运行状况。 运行状况状态可以是"已 **连接"或** "已 **断开连接"**。
- **运行状况** 显示有关连接到您的 Teams 会议室设备、网络连接、所需服务的登录状态和软件版本信息的详细信息。
- **详细信息** 显示制造商信息、网络 IP 地址和Teams设备串行/MAC 地址。
- **活动** 显示过去的会议详细信息，包括会议日期和时间、参与者数、持续时间和音频质量。 有关会议详细信息的详细信息， [请参阅本文稍后](#meeting-activity-details) 的"会议活动详细信息"部分。
- **历史记录** 显示会议室设备上管理活动的Teams，包括配置更新、设备重启和设备日志下载链接。

#### <a name="meeting-activity-details"></a>会议活动详细信息

"**会议室** Teams详细信息中的"活动"选项卡显示有关设备随着时间的推移参与的所有会议的高级别和详细信息。 在 **"活动** "选项卡中，可以看到会议举行时间、与会者数以及会议期间的音频质量。

:::image type="content" source="../media/teams-rooms-meeting-activity-summary.png" alt-text="Teams会议室设备活动摘要列表。":::

若要查看有关特定会议的详细信息，请选择希望了解详细信息的会议的日期和时间。 如果会议只有两个参与者，你将看到参与者详细信息页面，否则你将看到参与者摘要页面。

##### <a name="participant-summary"></a>参与者摘要

参与者摘要页面显示参加会议的所有参与者。 你可以看到每个参与者何时加入会议、他们的姓名、音频质量，以及会话期间使用了哪些功能。 若要查看参与者的会话详细信息，请选择该参与者的会话开始时间。

:::image type="content" source="../media/teams-rooms-meeting-activity-participant-summary.png" alt-text="Teams会议室设备会议详细信息。":::

##### <a name="participant-details"></a>参与者详细信息

参与者详细信息页显示该参与者会话的端到端诊断信息。 如下图所示，为参与者和设备提供了设备、系统和Teams 会议室信息。  **此外**，还提供了参与者与Teams 会议室之间的网络诊断信息。 选择要了解详细信息的上下文的图标。 有关其他诊断信息，请选择"高级 **"** 选项卡。

:::image type="content" source="../media/teams-rooms-meeting-activity-participant-details.png" alt-text="Teams会议室设备呼叫详细信息。":::
