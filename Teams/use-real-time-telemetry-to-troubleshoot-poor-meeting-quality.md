---
title: 使用实时遥测来解决会议质量不佳的问题
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, vkorlep
ms.topic: article
ms.assetid: 66945036-ae87-4c08-a0bb-984e50d6b009
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.directrouting.callanalytics
- ms.teamsadmincenter.users.activity.audioqualitycolumn
- Reporting
description: 使用实时遥测来详细了解设备、网络和连接，以排查 Microsoft Teams 计划会议的用户问题。
ms.openlocfilehash: c7bc5ee0415a289782cad1dd7daa5c13bdaf7364
ms.sourcegitcommit: f2253162a23d0683e7424211da1a0a8760c8a91b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2022
ms.locfileid: "66494719"
---
# <a name="use-real-time-telemetry-to-troubleshoot-poor-meeting-quality"></a>使用实时遥测来解决会议质量不佳的问题

本文介绍如何使用Real-Time分析 (RTA) 来排查个别用户的 Microsoft Teams 会议质量不佳问题。 如果具有以下角色之一，则可以访问 Real-Time Analytics：

- Teams 管理员
- Teams 通信支持专家
- Teams 通信支持工程师

有关 Teams 管理员角色的详细信息，请参阅 [使用 Microsoft Teams 管理员角色来管理 Teams](/MicrosoftTeams/using-admin-roles)。

Real-Time分析可让 IT 管理员查看其重要用户的计划会议，并查看音频、视频、内容共享和与网络相关的问题。 作为管理员，可以使用此遥测在会议期间调查这些问题，并实时进行故障排除。

## <a name="what-is-real-time-analytics"></a>什么是Real-Time分析？

目前，各个会议疑难解答在会议结束后通过 [呼叫分析](use-call-analytics-to-troubleshoot-poor-call-quality.md) 可供 Teams 管理员使用。 Real-Time Analytics 允许管理员在计划会议进行期间对其进行故障排除。

Real-Time分析显示有关Office 365帐户中每个用户的 Teams 会议的详细信息，并实时更新。 它包括有关设备、网络、连接、音频、视频和内容共享问题的信息，这将有助于管理员更有效地排查呼叫质量问题。

作为 Teams 管理员，可以完全访问每个用户的所有实时遥测数据。 此外，还可以分配 Azure Active Directory 角色来支持员工。 若要了解有关这些角色的详细信息，请参阅 [授予支持人员和支持人员的权限](set-up-call-analytics.md#give-permission-to-support-and-helpdesk-staff)。

## <a name="where-to-find-per-user-real-time-troubleshooting-telemetry"></a>在何处查找每个用户的实时遥测疑难解答

若要查看用户的所有会议信息和数据，请转到 [Teams 管理中心](https://admin.teams.microsoft.com)。 在 **“用户** > **管理用户”** 下，选择一个用户，并在用户的个人资料页上打开 **“会议&呼叫** ”选项卡。 在 **“最近的会议**”下，你将看到用户在过去 24 小时内参加的会议列表， *其中提供了实时遥测* 数据，包括任何正在进行的会议。 如果会议未进行或没有实时遥测数据，它将显示在 **以往的会议** 中。

:::image type="content" alt-text="最近会议表的屏幕截图。" source="media/recent-meetings.png" lightbox="media/recent-meetings.png":::

若要获取有关正在进行的会议参与者的其他信息，包括其设备、网络和音频统计信息，请在 **“最近会议** ”中查找会议，然后选择“ **参与者** ”列下的链接。

:::image type="content" alt-text="参与者详细信息表的屏幕截图。" source="media/participant-details-edit.png" lightbox="media/participant-details-edit.png":::

若要查看正在进行的会议的给定用户的遥测数据，包括有关设备、网络、音频、视频和内容共享详细信息的信息，请选择 **会议 ID**。

:::image type="content" alt-text="呼叫分析用户会话数据的屏幕截图。" source="media/real-time-telemetry-edit.png" lightbox="media/real-time-telemetry-edit.png":::

## <a name="details-and-measures-available-in-real-time-analytics"></a>Real-Time分析中提供的详细信息和度量值

### <a name="device-information"></a>设备信息
| 名称 | 描述 | 空白值的可能原因|
|:---|:---|:---|
| 音频捕获设备 | 音频捕获设备的名称 (例如：正在使用的麦克风)  | 系统可能没有与设备关联的名称 (例如：远程桌面或虚拟机“远程音频”设备)   |
| 音频呈现设备 | 音频呈现设备的名称 (例如：扬声器或耳机) 正在使用 | 系统可能没有与设备关联的名称 (例如：远程桌面或虚拟机“远程音频”设备)   |
| 视频捕获设备 | 正在使用的视频捕获设备的名称 | 用户未从受监视的终结点发送视频 |

### <a name="connectivity-information"></a>连接信息
| 指标 | 单位/可能的值 | 说明 | 空白值的可能原因|
|:---|:---|:---|:---|
| 网络类型 | &bull; 以太网 <br/> &bull; Wi-Fi | 正在使用的网络连接类型 | |
| Wi-Fi强度 | &bull; 优秀： -50dBm 或更高版本 <br/> &bull; 好： -51 dBm 到 -64 dBm<br/> &bull; 差： -65 dBm 或更低 | 用户当前Wi-Fi连接的强度 | 用户未连接到Wi-Fi |
| Wi-Fi通道 | 整型 | Wi-Fi网络访问点正在广播的频道 | 用户未连接到Wi-Fi |
| 物理类型 | String <br/> &bull; 示例：802.11ac | 正在使用的无线基础结构类型 | 用户未连接到Wi-Fi |
| Wi-Fi带 | 2.4 GHz 或 5 GHz | Wi-Fi用户连接到的带 | 用户未连接到Wi-Fi |
| 位置 | String | 用户所在的国家/地区 | 用户的位置信息被阻止或不可用 |
| 本地 IP 地址 | 字符串 (IP：端口)  | 用户终结点和媒体端口的本地 IP 地址 | |
| 服务器反身 IP 地址 | 字符串 (IP：端口)  | 用户终结点和媒体端口的公共 IP 地址 | |
| 连接类型 | UDP 或 TCP | 正在使用的传输层协议;UDP 是实时媒体的首选 | |

### <a name="user-signals"></a>用户信号
用户信号标识用户何时积极参与呼叫、不说话但未取消调用或静音。 目前，用户信号仅适用于音频。

| 形式 | 可能的值 | 说明 |
|:---|:---|:---|
| 音频 | &bull; 未计算，参与者发言 <br/> &bull; 未计算，不说话 <br/> &bull; 温和 | 指示用户对呼叫的音频部分的行为  |


### <a name="audio"></a>音频
|衡量指标名称 |单位 |良好的阈值 |说明 |
|:---|:---|:---|:---|
|抖动 |毫秒 |小于 30 毫秒 |Jitter 是衡量数据流的数据包延迟变化的度量值。 当这太高时，音频可能会变得断断续续。 | 
|丢包 |百分比 |小于 5% |当数据包无法到达其目标时，会发生数据包丢失。 丢失的数据包百分比基于发送的数据包总数。 |
|往返时间 |毫秒 |小于 500 毫秒 |往返时间是单个数据包从客户端到远程终结点并返回到客户端所需的时间。 往返时间过多可能导致流播放延迟。 例如，当会议中的两个人由于延迟而无意间互相交谈时。 仅显示出站音频。 |
|比特率 |Kbps)  (千比特/秒 |大于 24 Kbps |以千位每秒表示的音频流的吞吐量。 |
| 编解码器 | String <br/> &bull; 示例：SATIN | 仅限信息 | 显示正在发送和接收的音频编解码器。 可以接收与发送的编解码器不同的编解码器。 |


### <a name="video"></a>视频
|衡量指标名称 |单位 |良好的阈值 |说明 |
|:---|:---|:---|:---|
|往返时间 |毫秒 |小于 500 毫秒 |往返时间是单个数据包从客户端到远程终结点并返回到客户端所需的时间。 往返时间过多可能导致流播放延迟。 例如，当会议中的两个人由于延迟而无意间互相交谈时。 |
|比特率 |每秒兆位 (Mbps)  | 仅限信息 |以每秒兆位表示的视频流的吞吐量。 |
|视频)  (帧速率 |帧/秒 |360p 或更高版本：25-30 FPS <br/> 270p 或更低：7-15 FPS |对于出站视频流，帧速率 (FPS) 是客户端发送的视频每秒帧数。 此处低于预期值可能表明系统资源约束、网络带宽不足或视频捕获设备行为不正常。 不同的分辨率有不同的可接受的 FPS 范围。 |
|编解码器 |String | 仅限信息 |显示出站视频流的视频编解码器和呈现模式。  (示例：H264 SW HW 指示使用软件和硬件呈现的 H264 视频流。) |
|解决方案 |像素 | 仅限信息 |要发送的视频的解析。 出站视频解析是动态的，基于会议中终结点的最高要求。 如果客户端未在大于 640 x 360 的帧中显示该用户的视频，则支持 1920 x 1080 视频的客户端只会发送 640 x 360 视频 |


### <a name="application-sharing-vbss"></a>应用程序共享 (VBSS) 
|衡量指标名称 |单位 |良好的阈值 |说明 |
|:---|:---|:---|:---|
|丢包 |百分比 |小于 5% |当数据包无法到达其目标时，会发生数据包丢失。 丢失的数据包百分比基于发送的数据包总数。 |
|往返时间 |毫秒 |小于 500 毫秒 |往返时间是单个数据包从客户端到远程终结点并返回到客户端所需的时间。 往返时间过多可能导致流播放延迟。 例如，当会议中的两个人由于延迟而无意间互相交谈时。 |
|比特率 |每秒兆位 (Mbps)  | 仅限信息 |以每秒兆位表示的 VBSS 流的吞吐量。 |
|帧速率 |每秒帧 (FPS)  | 仅限信息 |对于 VBSS，帧速率是内容感知，以确保根据需要发送尽可能多的帧，以确保良好的体验，同时避免发送帧（如果不需要）。 例如，在屏幕上共享文本文档只需每秒 1 帧才能生成良好的体验，而使用更多活动共享视频或内容将每秒的帧数增加到最多 30 个 FPS，以产生更流畅的体验。 |
|编解码器 |String | 仅限信息 |显示 VBSS 流的编解码器和呈现模式。  (示例：H264 SW HW 指示使用软件和硬件呈现的 H264 VBSS 流。) |
|解决方案 |像素 | 仅限信息 |发送和接收的 VBSS 流的解析。 |


## <a name="client-platforms-supported-for-real-time-telemetry"></a>实时遥测支持的客户端平台

- Windows
- macOS
- Linux
- Android
- iOS

> [!NOTE]
> 包括 VDI) 在内的 Teams Web 客户端 (不支持实时传送遥测数据。

## <a name="teams-devices-with-support-for-real-time-telemetry"></a>支持实时遥测的 Teams 设备

- MTR - Surface Hub
- MTR - Teams 显示
- MTR - 协作栏
- IP Phone 设备

> [!NOTE]
> Real-Time分析不支持使用云视频互操作 (CVI) 解决方案加入会议的设备。


## <a name="limitations"></a>限制

- 实时遥测仅适用于计划的会议和立即开会。 对于 PSTN、1：1 呼叫和组呼叫，实时遥测不可用。
- 实时遥测仅适用于计划直播活动的演示者。 它目前不适用于实时事件与会者。
- 在会议结束后的 24 小时内，实时遥测数据可用于 **最近会议** 下的会议。 24 小时后，无法访问数据，会议将移至 **过去会议**。 如果会议超过 3 小时，则实时遥测仅可用于 *过去 3 小时*。
- 使用早期版本的 Teams 时，遥测不可实时提供。 如果没有遥测数据可用，请尝试更新客户端。
- 如果外部参与者或匿名用户加入会议，则其显示名称将显示为 **不可** 保留跨租户隐私。

## <a name="related-topics"></a>相关主题

[设置每用户呼叫分析](set-up-call-analytics.md)

[使用 Microsoft Teams 管理员角色管理 Teams](/MicrosoftTeams/using-admin-roles)。
