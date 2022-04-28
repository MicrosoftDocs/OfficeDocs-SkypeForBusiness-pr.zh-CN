---
title: 管理 Microsoft Teams 会议室
ms.author: czawideh
author: cazawideh
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
ms.openlocfilehash: 47f1c170fd0c41331dfaffa2d81386ac3c2fb722
ms.sourcegitcommit: 0967f725aad0a7b9c430b2e30a37ea333007558a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2022
ms.locfileid: "65106267"
---
# <a name="manage-microsoft-teams-rooms"></a>管理 Microsoft Teams 会议室

如果组织中有Microsoft Teams 会议室，则可以使用灵活的管理选项。  你可以在管理所有Teams解决方案的中央位置（Microsoft Teams管理中心）自行管理设备。 或者，可以使用 [Microsoft Teams 会议室 托管服务](https://portal.rooms.microsoft.com)将管理责任转移给专门的专家。  还可以将管理访问权限委托给所选任一选项的合作伙伴。

使用Microsoft Teams管理中心，可以：

- 执行设备管理，例如重启设备和下载设备日志
- 应用特定Teams设置
- 检查Microsoft Teams 会议室及其外围设备（包括相机、显示器、麦克风等）的运行状况
- 查看当前和过去的会议活动 (，例如有关呼叫质量、网络运行状况和连接的详细信息，以及参与者) 
- 请参阅 () 连接到Microsoft Teams 会议室的相机和投影仪等外围设备

若要管理Teams 会议室设备，请打开 [Microsoft Teams管理中心](https://admin.teams.microsoft.com)，然后转到 **Windows上的Teams设备** > **Teams 会议室**。

:::image type="content" source="../media/teams-rooms-summary2.png" alt-text="Teams管理中心中的Teams 会议室摘要页。":::


> [!IMPORTANT]
> 若要使用Teams管理中心管理设备，需要为你分配全局管理员、Teams管理员或Teams设备管理员角色。

## <a name="make-changes-to-teams-rooms-devices"></a>对Teams 会议室设备进行更改

如果有多个Teams 会议室，则可以同时在多个设备上执行大多数操作。 例如，可以同时在所有Teams 会议室上设置Teams应用设置。

### <a name="device-settings"></a>设备设置

可以在组织中的一个或多个Teams 会议室上更改设置。 若要更改设置，请选择要管理的设备或设备，然后选择 **“编辑设置**”。 将打开一个新窗格，其中包含可以更改的所有设置。 下表列出了可以使用Teams管理中心更改的设置。 某些设置仅在选择单个Teams 会议室时可用。

如果选择多个选项，则支持批量编辑的设置将显示以下两个选项。

- **保留现有值** 如果选择此选项，则不会对所选Teams 会议室上的设置进行任何更改。
- **将现有值替换为** 如果选择此选项，可以使用所提供的值更新所选Teams 会议室上的设置。
    > [!CAUTION]
    > 选择更新的设置上的现有值将替换为你提供的值。 如果要添加到现有值的列表，则需要将现有值与要添加的值一起包含在内。 例如，如果设置具有现有域列表 `contoso.com, fabrikam.com`，并且你想要添加 `northwindtraders.com`，则需要提供的值将是 `contoso.com, fabrikam.com, northwindtraders.com`。
    >
    > 如果选择多个Teams 会议室，所选所有设备上的设置将更改为提供的值。 如果Teams 会议室设置具有不同的值，则它们都将更新为相同的值。

| 设置                                                      | 接受的值                                        | 支持批量编辑 |
|--------------------------------------------------------------|--------------------------------------------------------|--------------------|
| *帐户*                                                    |                                                        |                    |
| **电子邮件**                                                    | 电子邮件地址                                          | 否                 |
| **支持的会议模式**                                   | 仅Microsoft Teams<br>Skype for Business (默认) 和Microsoft Teams<br>Skype for Business和Microsoft Teams (默认) <br>仅Skype for Business|是|
| **新式身份验证**                                    | 开<br>关闭                                              | 是                |
| **Exchange地址**                                         | 电子邮件地址                                          | 否                 |
| **Domain\username (可选)**                               | 帐户域和用户名                           | 否                 |
| **配置域**                                         | 逗号分隔列表                                   | 是                |
| *会议*                                                   |                                                        |                    |
| **自动屏幕共享**                                 | 开<br>关闭                                              | 是                |
| **HDMI 引入音频共享**                                 | 开<br>关闭                                              | 是                |
| **显示会议名称**                                       | 开<br>关闭                                              | 是                |
| **如果其他人都离开了会议，则自动离开**                 | 开<br>关闭                                              | 是                |
| **加入第三方会议**                 | Cisco Webex<br>缩放                                              | 是                |
| **加入会议室信息**                 | 选中<br>未选中                                              | 是                |
| **使用自定义信息加入**                 | 选中<br>未选中                                              | 是                |
| **所需的名称 ()**                 | 房间或空间的名称                                              | 是                |
| **所需的电子邮件 ()**                 | 电子邮件地址                                              | 是                |
| *Device*                                                     |                                                        |                    |
| **双监视模式**                                        | 开<br>关闭                                              | 是                |
| **允许内容重复** | 选中<br>未选中                                 | 是                |
| **蓝牙信标**                                      | 开<br>关闭                                              | 是                |
| **自动接受基于邻近的会议邀请** | 选中<br>未选中                                 | 是                |
| **使用反馈发送日志**                                  | 开<br>关闭                                              | 是                |
| **日志和反馈的电子邮件地址**                      | 电子邮件地址                                          | 是                |
| *坐标会议*                                                     |                                                        |                    |
| **协调会议** | 开<br>关闭                                 | 否                |
| **打开此设备的麦克风** | 开<br>关闭                                 | 否                |
| **允许用户在加入会议时启用** | 选中<br>未选中                                 | 否                |
| **打开此设备的相机** | 开<br>关闭                                 | 否                |
| **允许用户在加入会议时启用** | 选中<br>未选中                                 | 否                |
| **为此设备启用白板** | 开<br>关闭                                 | 否                |
| **受信任的设备帐户 (使用逗号) 分开** | 设备列表                              | 否                |
| *外设*                                                |                                                        |                    |
| **会议麦克风**                                  | 可用麦克风列表                          | 否                 |
| **会议扬声器**                                     | 可用扬声器列表                             | 否                 |
| **默认卷**                                           | 0-100                                                  | 否                 |
| **默认扬声器**                                          | 可用扬声器列表                             | 否                 |
| **默认卷**                                           | 0-100                                                  | 否                 |
| **内容相机**                                           | 可用相机列表                              | 否                 |
| **内容相机增强功能**                              | 开<br>关闭                                              | 否                 |
| **旋转内容相机 180 度**                        | 开<br>关闭                                              | 否                 |
| *主题*                                                    |                                                        |                    |
|                                                              | 默认值<br>无主题<br>自 定义<br>内置主题列表   | 是                |

### <a name="cortana-settings"></a>Cortana设置

可以为组织中的所有设备或每个设备启用 _语音激活_ 或 _推送Cortana，以便_ 使用 PowerShell 进行通信。

请参阅[Windows“Teams](../cortana-in-teams.md) Cortana语音协助”一文中的Microsoft Teams 会议室。

### <a name="front-row-layout-settings"></a>前行布局设置

前行是Windows上Teams 会议室的会议视图布局选项。

| Teams设备 | 应用版本 | 会议室前显示 |
|--------------|-------------|-----------------------|
|Windows上的Microsoft Teams 会议室 | 4.11.12.0 或更高版本 (建议使用最新版本)  | 支持单一和双显示;最小大小：46 英寸;纵横比 16：9，分辨率为 1920x1080 或 21：9，分辨率为 2560x1080：在Windows设置中，所有显示应设置为 100% 缩放 |

请参阅[Microsoft Teams 会议室维护和操作](rooms-operations.md#scale-and-resolution)，以调整显示设置以满足 Front 行的要求。

若要了解如何将 Front 行设置为会议室的默认布局，或如何将其关闭，请参阅[使用 XML 配置文件远程管理Microsoft Teams 会议室控制台设置](xml-config-file.md#set-front-row-as-the-default-layout)。

有关管理 Front 行的详细信息，请参阅 [已知问题](known-issues.md#Limits) 。

## <a name="device-restart-options"></a>设备重启选项

只有在重启Teams 会议室后，对设备设置的更改才会生效。 进行需要重启的更改时，可以选择是立即重启还是计划重启。 下面是可用的重启选项：

- **立即重启** 如果选择此选项，请在选择此选项后立即重启要进行更改的所有设备。
- **计划重启** 如果选择此选项，可以在对组织造成较少干扰的时间重新启动要更改的设备。
  - **选择日期和时间** - 选择重启设备的特定日期和时间。 选择的日期和时间是正在重启的设备的本地日期和时间。 
  - **保留更新以进行夜间重启** 设备每晚重启以执行维护。 在此重启期间，将应用对设备所做的更改。

> [!CAUTION]
> 重启时使用的Teams 会议室在重启过程中将变得不可用。 它们将与正在进行的会议断开连接，并且无法加入新会议。

## <a name="remove-device"></a>删除设备

删除设备时，设备将从组织中删除，并且不再出现在Teams管理中心Windows上的Teams 会议室列表中。

如果删除设备并且仍配置了有效的用户名和密码，则如果设备再次连接到Microsoft 365，它将自动重新添加到Teams 会议室列表中。

若要删除一个或多个设备，请执行以下操作：

1. 转到 **Teams** > 设备 **Teams 会议室Windows**，然后选择要删除的设备。
2. 选择“**删除**”。

## <a name="download-device-logs"></a>下载设备日志

如果 Microsoft 支持部门请求这样做，则可以下载设备诊断日志文件的副本。 日志文件将压缩到可从Teams管理中心下载的 zip 文件中。

若要将日志从Teams 会议室设备下载到计算机，请执行以下操作：

1. 转到 **Teams设备** > **Teams 会议室Windows**，然后选择要从中下载日志的设备的名称。
1. 选择 **“下载设备日志**”。 设备日志可能需要几分钟才能可用。
1. 选择 **“历史记录** ”选项卡，然后选择 **“诊断”文件下的** 日志文件链接。 包含设备诊断日志文件的 zip 文件将下载到浏览器的默认下载文件夹。

## <a name="view-device-information"></a>查看设备信息

在Teams管理中心，可以查看组织中所有设备的总体状态，并单独查看每个设备的详细信息。

### <a name="teams-rooms-system-dashboard"></a>Teams 会议室系统仪表板

Teams 会议室系统仪表板一目了然地显示所有设备的状态和运行状况。

### <a name="device-details-view"></a>设备详细信息视图

若要查看有关设备的详细信息，请从设备列表中选择其名称。 在详细信息视图中，可以看到有关设备的以下信息：

- **运行状况** 显示Teams会议室设备的总体运行状况。 运行状况状态可以是 **“正常** ”或 **“不正常**”。
- **脱机后** 显示Microsoft 365上次能够与设备通信的时间。
- **设备状态** 显示设备的当前状态：**空闲**、**Teams会议**、**Skype会议** 或 **引入**。
- **外设** 显示连接到Teams会议室设备的外围设备及其运行状况。 运行状况状态可以 **是连接** 状态，也可以 **是断开连接状态**。
- **健康** 显示有关连接到Teams会议室设备的外围设备、网络连接、登录所需服务的状态以及软件版本信息的详细信息。
- **细节** 显示制造商信息、网络 IP 地址和Teams会议室设备串行/MAC 地址。
- **活动** 显示过去的会议详细信息，包括会议日期和时间、参与者数、持续时间和音频质量。 有关会议详细信息的详细信息，请参阅本文后面的 [“会议活动详细信息](#meeting-activity-details) ”部分。
- **历史** 显示Teams会议室设备上的管理活动的历史记录，包括配置更新、设备重启和设备日志下载链接。

#### <a name="meeting-activity-details"></a>会议活动详细信息

“Teams会议室”设备详细信息中的 **“活动**”选项卡显示有关设备随时间推移参与的所有会议的高级和详细信息。 在 **“活动”** 选项卡中，可以看到会议召开时间、参加会议的参与者数以及会议期间的音频质量。

:::image type="content" source="../media/teams-rooms-meeting-activity-summary.png" alt-text="Teams会议室设备活动摘要列表。":::

若要查看有关特定会议的详细信息，请选择要详细了解的会议日期和时间。 如果会议只有两个参与者，则会看到参与者详细信息页，否则会看到参与者摘要页。

##### <a name="participant-summary"></a>参与者摘要

参与者摘要页显示参加会议的所有参与者。 可以查看每个参与者何时加入会议、其名称、音频质量以及会话期间使用的功能。 若要查看参与者会话的详细信息，请选择该参与者的会话开始时间。

:::image type="content" source="../media/teams-rooms-meeting-activity-participant-summary.png" alt-text="Teams会议室设备会议详细信息。":::

##### <a name="participant-details"></a>参与者详细信息

参与者详细信息页显示该参与者会话的端到端诊断信息。 如下图所示，为参与者和Teams 会议室设备提供了 **设备**、**系统** 和 **连接** 信息。 还提供了参与者与Teams 会议室设备之间的 **网络** 诊断信息。 选择要详细了解的上下文的图标。 有关其他诊断信息，请选择 **“高级** ”选项卡。

:::image type="content" source="../media/teams-rooms-meeting-activity-participant-details.png" alt-text="Teams会议室设备呼叫详细信息。":::
