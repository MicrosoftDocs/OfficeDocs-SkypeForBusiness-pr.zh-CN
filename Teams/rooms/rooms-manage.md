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
- Teams_ITAdmin_Rooms
description: 了解如何开发和执行持续维护和操作，以确保Microsoft Teams 会议室系统可供用户使用。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 36145202e12cd9b987b50efd6de3efe636c86ac2
ms.sourcegitcommit: 1934c4803b5b6ae9b9ccd49e695944446d5d5810
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/14/2023
ms.locfileid: "69806367"
---
# <a name="manage-microsoft-teams-rooms-and-surface-hubs"></a>管理Microsoft Teams 会议室和 Surface Hub

如果你在组织中Microsoft Teams 会议室设备或 Surface Hub，则可以使用灵活的管理选项。  可以在管理所有 Teams 解决方案的同一中心位置自行管理设备，即 Microsoft Teams 管理中心。

使用 Microsoft Teams 管理中心，可以：

- 执行设备管理，例如重启设备和下载设备日志
- 应用特定于 Teams 的设置
- 检查Microsoft Teams 会议室及其外围设备的运行状况，包括相机、显示器、麦克风等
- 查看当前和过去的会议活动 (，例如有关通话质量、网络运行状况和连接的详细信息，以及参与者) 
- 查看外围设备 (，例如) 连接到Microsoft Teams 会议室 (的外围设备（例如相机和投影仪）仅在 Windows) 上Teams 会议室

若要管理Teams 会议室设备，请打开 [Microsoft Teams 管理中心](https://admin.teams.microsoft.com)，转到 Windows 或 **Surface Hub** 上的 **Teams 设备** > **Teams 会议室**。

:::image type="content" source="../media/teams-rooms-summary2.png" alt-text="teams 管理中心中的Teams 会议室摘要页。":::


> [!IMPORTANT]
> 若要使用 Teams 管理中心管理设备，需要分配全局管理员、Teams 管理员或 Teams 设备管理员角色。

## <a name="make-changes-to-teams-rooms-devices-or-surface-hubs"></a>对Teams 会议室设备或 Surface Hub 进行更改

如果你有多个Teams 会议室或 Surface Hub 设备，则可以同时在多台设备上执行大多数操作。 例如，可以同时在所有Teams 会议室上设置 Teams 应用设置。

### <a name="device-settings"></a>设备设置

可以更改组织中的一个或多个Teams 会议室或 Surface Hub 的设置。 若要更改设置，请选择要管理的一个或多个设备，然后选择 **“编辑设置**”。 将打开一个新窗格，其中包含可更改的所有设置。 下表列出了可以使用 Teams 管理中心更改的设置。 某些设置仅在选择单个Teams 会议室时才可用。

如果选择多个选项，则支持批量编辑的设置将显示以下两个选项。

- **保留现有值** 如果选择此选项，将不会对所选Teams 会议室的设置进行更改。
- **将现有值替换为** 如果选择此选项，则可以使用所提供的值更新所选Teams 会议室上的设置。
    > [!CAUTION]
    > 你选择更新的设置上的现有值将替换为你提供的值。 如果要添加到现有值列表，则需要将现有值与要添加的值一起包含在内。 例如，如果设置具有 的现有域列表 `contoso.com, fabrikam.com`，并且你想要添加 `northwindtraders.com`，则需要提供的值将是 `contoso.com, fabrikam.com, northwindtraders.com`。
    >
    > 如果选择多个Teams 会议室，则所选的所有设备上的设置将更改为你提供的值。 如果Teams 会议室设置具有不同的值，则它们都将更新为相同的值。

| 设置                                                      | 接受的值                                        | 支持批量编辑 | 支持的设备类型 |
|--------------------------------------------------------------|--------------------------------------------------------|--------------------|------------------------|
| *帐户*                                                    |                                                        |                    | Windows 上的Teams 会议室 |
| **电子邮件**                                                    | Email地址                                          | 否                 | Windows 上的Teams 会议室 |
| **支持的会议模式**                                   | 仅限 Microsoft Teams<br>Skype for Business (默认) 和 Microsoft Teams<br>Skype for Business和 Microsoft Teams (默认) <br>仅限Skype for Business|是| Windows 上的Teams 会议室 |
| **新式身份验证**                                    | 开<br>关闭                                              | 是                | Windows 上的Teams 会议室 |
| **Exchange 地址**                                         | Email地址                                          | 否                 | Windows 上的Teams 会议室 |
| **Domain\username (可选)**                               | 帐户域和用户名                           | 否                 | Windows 上的Teams 会议室 |
| **配置域**                                         | 逗号分隔列表                                   | 是                | Windows 上的Teams 会议室 |
| *会议*                                                   |                                                        |                    | Windows、Surface Hub 上的Teams 会议室 |
| **自动屏幕共享**                                 | 开<br>关闭                                              | 是                | Windows 上的Teams 会议室 |
| **HDMI 引入音频共享**                                 | 开<br>关闭                                              | 是                | Windows 上的Teams 会议室 |
| **显示会议名称**                                       | 开<br>关闭                                              | 是                | Windows 上的Teams 会议室 |
| **如果其他人都离开会议，则自动离开**                 | 开<br>关闭                                              | 是                | Windows 上的Teams 会议室 |
| **加入第三方会议**                 | Cisco Webex<br>缩放                                              | 是                | Windows、Surface Hub 上的Teams 会议室 |
| **使用会议室信息加入**                 | 选中<br>未选中                                              | 是                | Windows、Surface Hub 上的Teams 会议室 |
| **使用自定义信息加入**                 | 选中<br>未选中                                              | 是                | Windows 上的Teams 会议室 |
| **需要名称 ()**                 | 会议室或空间的名称                                              | 是                | Windows 上的Teams 会议室 |
| **需要Email ()**                 | Email地址                                              | 是                | Windows 上的Teams 会议室 |
| *Device*                                                     |                                                        |                    | Windows 上的Teams 会议室 |
| **双监视器模式**                                        | 开<br>关闭                                              | 是                | Windows 上的Teams 会议室 |
| **允许内容重复** | 选中<br>未选中                                 | 是                | Windows 上的Teams 会议室 |
| **蓝牙信标**                                      | 开<br>关闭                                              | 是                | Windows、Surface Hub 上的Teams 会议室 |
| **自动接受基于邻近感应的会议邀请** | 选中<br>未选中                                 | 是                | Windows、Surface Hub 上的Teams 会议室 |
| **发送包含反馈的日志**                                  | 开<br>关闭                                              | 是                | Windows 上的Teams 会议室 |
| **日志和反馈Email地址**                      | Email地址                                          | 是                | Windows 上的Teams 会议室 |
| *协调会议*                                                     |                                                        |                    | Windows 上的Teams 会议室 |
| **协调会议** | 开<br>关闭                                 | 否                | Windows、Surface Hub 上的Teams 会议室 |
| **打开此设备的麦克风** | 开<br>关闭                                 | 否                | Windows、Surface Hub 上的Teams 会议室 |
| **允许用户在加入会议时启用** | 选中<br>未选中                                 | 否                | Windows、Surface Hub 上的Teams 会议室 |
| **打开此设备的相机** | 开<br>关闭                                 | 否                | Windows、Surface Hub 上的Teams 会议室 |
| **允许用户在加入会议时启用** | 选中<br>未选中                                 | 否                | Windows、Surface Hub 上的Teams 会议室 |
| **为此设备启用白板** | 开<br>关闭                                 | 否                | Windows、Surface Hub 上的Teams 会议室 |
| **受信任的设备帐户 (逗号分隔)** | 设备列表                              | 否                | Windows、Surface Hub 上的Teams 会议室 |
| *外设*                                                |                                                        |                    | Windows 上的Teams 会议室 |
| **会议麦克风**                                  | 可用麦克风列表                          | 否                 | Windows 上的Teams 会议室 |
| **会议扬声器**                                     | 可用演讲者列表                             | 否                 | Windows 上的Teams 会议室 |
| **默认卷**                                           | 0-100                                                  | 否                 | Windows 上的Teams 会议室 |
| **默认扬声器**                                          | 可用演讲者列表                             | 否                 | Windows 上的Teams 会议室 |
| **默认卷**                                           | 0-100                                                  | 否                 | Windows 上的Teams 会议室 |
| **内容相机**                                           | 可用相机列表                              | 否                 | Windows 上的Teams 会议室 |
| **内容相机增强功能**                              | 开<br>关闭                                              | 否                 | Windows 上的Teams 会议室 |
| **将内容相机旋转 180 度**                        | 开<br>关闭                                              | 否                 | Windows 上的Teams 会议室 |
| *主题*                                                    |                                                        |                    | Windows 上的Teams 会议室 |
|                                                              | 默认值<br>无主题<br>自 定义<br>内置主题列表   | 是                | Windows 上的Teams 会议室 |

有关配置 Surface Hub 的更多选项，请参阅 [管理 Surface Hub 上的 Microsoft Teams](surface-hub-manage-config.md) 配置。

### <a name="cortana-settings"></a>Cortana 设置

可以使用 PowerShell 为组织中的所有设备或单独为每个设备启用 Cortana 进行 _语音激活_ 或 _推送通话_ 。

请参阅“Teams 中的 Cortana 语音协助”一文中的 [Windows 上的Microsoft Teams 会议室](../cortana-in-teams.md)。

### <a name="front-row-layout-settings"></a>前行布局设置

前行是 Windows 上Teams 会议室的会议视图布局选项。

| Teams 设备 | 应用版本 | 房间前显示 |
|--------------|-------------|-----------------------|
|Windows 上的Microsoft Teams 会议室 | 4.11.12.0 或更高版本 (建议使用最新版本)  | 支持单显示器和双显示器;最小大小：46 英寸;纵横比 16：9（分辨率为 1920x1080）或 21：9（分辨率为 2560x1080）;应在 Windows 设置中将所有显示器设置为 100% 缩放 |

请参阅[Microsoft Teams 会议室维护和操作](rooms-operations.md#scale-and-resolution)，以调整显示设置以满足 Front row 的要求。

若要了解如何将前行设置为会议室的默认布局或如何将其关闭，请参阅[使用 XML 配置文件远程管理Microsoft Teams 会议室控制台设置](xml-config-file.md#set-front-row-as-the-default-layout)。

有关管理前行的详细信息，请参阅 [已知问题](known-issues.md#Limits) 。

## <a name="device-restart-options"></a>设备重启选项

仅当设备重启后，对设备设置的更改才会生效。 进行需要重启的更改时，可以选择是立即重启还是计划重启。 下面是可用的重启选项：

- **立即重启** 如果选择此选项，则一旦选择此选项，将立即重启要对其进行更改的所有设备。
- **计划重启** 如果选择此选项，则可以在对组织造成干扰较小的时间重启要更改的设备。
  - **选择日期和时间** - 选择重启设备的特定日期和时间。 所选的日期和时间是重启设备的本地日期和时间。 
  - **保留夜间重新启动的更新** 设备在夜间重启以执行维护。 对设备所做的更改将在此重启期间应用。

> [!CAUTION]
> 重启时正在使用的Teams 会议室和 Surface Hub 将在重启过程中不可用。 设备重启时，它们将与正在进行的会议断开连接，并且无法加入新会议。

## <a name="remove-device"></a>删除设备

删除设备时，设备将从组织中删除，并且不再显示在 Teams 管理中心的 Windows 或 Surface Hub 上的Teams 会议室列表中。

如果你删除了某个设备，并且它仍然配置了有效的用户名和密码，如果设备再次连接到 Microsoft 365，它将自动重新添加到你的Teams 会议室或 Surface Hub 列表中。

若要删除一个或多个设备，请执行以下操作：

1. 转到 Windows 或 **Surface Hub** 上的 **Teams 设备** > **Teams 会议室**，然后选择要删除的设备。
2. 选择“**删除**”。

## <a name="download-device-logs"></a>下载设备日志

如果 Microsoft 支持部门要求下载设备的诊断日志文件的副本，则可以下载该副本。 日志文件被压缩为可从 Teams 管理中心下载的 zip 文件。

若要将日志从Teams 会议室设备下载到计算机，请执行以下操作：

1. 转到 Windows 或 **Surface Hub** 上的 **Teams 设备** > **Teams 会议室**，然后选择要从中下载日志的设备的名称。
1. 选择 **“下载设备日志**”。 设备日志可能需要几分钟才能可用。
1. 选择“ **历史记录** ”选项卡，然后选择“ **诊断文件**”下的“日志文件”链接。 包含设备的诊断日志文件的 zip 文件将下载到浏览器的默认“下载”文件夹。

## <a name="view-device-information"></a>查看设备信息

在 Teams 管理中心，可以查看组织中所有设备的整体状态，并单独查看每个设备的详细信息。

### <a name="teams-rooms-system-dashboard"></a>Teams 会议室系统仪表板

Teams 会议室系统仪表板一目了然地显示所有设备的状态和运行状况。

### <a name="device-details-view"></a>设备详细信息视图

若要查看有关设备的详细信息，请从设备列表中选择其名称。 在详细信息视图中，可以看到有关设备的以下信息：

- **运行状况状态** 显示Teams 会议室或 Surface Hub 设备的整体运行状况。 运行状况状态可以是 **“正常”、“****非紧急**”、“**严重”** 或 **“脱机**”。
- **脱机自** 显示 Microsoft 365 上次能够与设备通信的时间。
- **使用情况状态** 显示设备的当前状态：**“空闲”、“****忙碌”** 或 **“不可用**”。 仅适用于 Windows 上的Teams 会议室。
- **外设** 显示连接到Teams 会议室设备的外围设备及其运行状况。 运行状况状态可以是 **“已连接”** 或 **“已断开连接**”。 仅适用于 Windows 上的Teams 会议室。
- **健康** 显示连接到Teams 会议室设备的外围设备、网络连接、所需服务的登录状态以及软件版本信息的详细信息。
- **细节** 显示制造商信息、网络 IP 地址和Teams 会议室设备串行/MAC 地址。
- **活动** 显示过去的会议详细信息，包括会议的日期和时间、参与者人数、持续时间和音频质量。 有关会议详细信息的详细信息，请参阅本文后面的 [会议活动详细信息](#meeting-activity-details) 部分。
- **历史** 显示Teams 会议室或 Surface Hub 设备上的管理活动的历史记录，包括配置更新、设备重启和设备日志下载链接。

#### <a name="meeting-activity-details"></a>会议活动详细信息

设备详细信息中的“ **活动** ”选项卡显示有关设备随时间推移参加的所有会议的概要和详细信息。 在“ **活动** ”选项卡中，可以查看会议召开时间、与会者人数以及会议期间的音频质量。

:::image type="content" source="../media/teams-rooms-meeting-activity-summary.png" alt-text="Teams 会议室设备活动摘要列表。":::

若要查看有关特定会议的详细信息，请选择所需的会议日期和时间。 如果会议只有两个参与者，你将看到参与者详细信息页，否则你将看到参与者摘要页。

##### <a name="participant-summary"></a>参与者摘要

参与者摘要页显示参加会议的所有参与者。 可以查看每个参与者何时加入会议、姓名、音频质量，以及会话期间使用的功能。 若要查看参与者会话的详细信息，请选择该参与者的会话开始时间。

:::image type="content" source="../media/teams-rooms-meeting-activity-participant-summary.png" alt-text="Teams 会议室设备会议详细信息。":::

##### <a name="participant-details"></a>参与者详细信息

参与者详细信息页显示该参与者会话的端到端诊断信息。 如下图所示，为参与者和Teams 会议室设备提供了 **设备**、**系统和****连接** 信息。 还提供了参与者与Teams 会议室设备之间的 **网络** 诊断信息。 选择想要了解详细信息的上下文的图标。 有关其他诊断信息，请选择“ **高级** ”选项卡。

:::image type="content" source="../media/teams-rooms-meeting-activity-participant-details.png" alt-text="Teams 会议室设备呼叫详细信息。":::
