---
title: Walkie Talkie 使用情况和性能报告
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: admin
ms.topic: article
ms.service: microsoft-365-frontline
ms.reviewer: prastogi
f1.keywords:
- NOCSH
ms.localizationpriority: high
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365-frontline
- highpri
- tier2
description: 了解如何使用 Microsoft Teams 管理中心中的 Walkie Talkie 使用情况和性能报告来概述组织中的 Walkie Talkie 使用情况活动。
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
ms.openlocfilehash: 85f92e715efe2b9608691151a08d006816658095
ms.sourcegitcommit: 776820a6c927fafabdfad9f50654fe7648d77bf3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/20/2023
ms.locfileid: "69846045"
---
# <a name="walkie-talkie-usage-and-performance-report"></a>Walkie Talkie 使用情况和性能报告

Microsoft Teams 管理中心中的 Walkie Talkie 使用情况和性能报告概述了组织中的 [Walkie Talkie](../walkie-talkie.md) 活动。 该报表提供一些信息，例如进行和接收的) 传输 (PTT) 数、通道活动、传输持续时间以及设备和参与者详细信息。

使用此报表深入了解组织中的 Walkie Talkie 使用趋势和性能。 若要访问报表，你必须是全局管理员、Teams 管理员、全局读取者或报表读取者。

## <a name="download-and-view-the-report"></a>下载并查看报表

1. 在 Microsoft Teams 管理中心的左侧导航栏中，选择“ **分析”&报告** > **使用情况报告**。 在“ **查看报表** ”选项卡上的“ **报表**”下，选择“ **Walkie Talkie 使用情况**”。
1. 在 **“日期范围**”下，选择 7 天或 30 天的日期范围。 然后，选择 **“运行报表**”。
1. 选择“ **生成报表**”。
1. 在“ **下载** ”选项卡上 **的“状态**”下，选择“ **下载** ”以下载 CSV 格式的报表。

## <a name="interpret-the-report"></a>解释报告

此报表提供所选日期范围内进行的每次传输的细目。 下面是报表中包含的信息。

|列名称 |说明 |
|---------|---------|
|TenantId|租户 ID。|
|UserId|用户 ID。|
|DeviceId|设备 ID。|
|ChannelId|进行通信的对讲机通道。|
|clientCallStatus | 指示设备是否能够毫无问题地接收传输。|
|ConversationId|每个 PTT 传输的 ID。|
|TeamId|与用户连接到的对讲机通道对应的团队 ID。|
|UnreachableParticipantsCount|被标记为无法访问并隐藏在名册中的参与者的数量，因为他们无法收到最近五次传输中的任何一个。|
|TransmissionDuration|服务收到一个参与者即将开始传输的通知，服务传送最后一个传输包时， (的持续时间（以) 毫秒为单位）。|
|TotalParticipantsCount|连接到沃基对讲机频道的参与者总数。|
|PacketCount|用于发送音频传输的数据包数。|
|NotifiedParticipants|传输开始时向其发送推送通知的参与者。 在设备与服务之间的连接丢失的情况下，会向设备发送通知，以便尽快重新建立连接，因为传输即将来临。|
|AudioDurationMilliseconds|传输持续时间（以毫秒为单位）。|
|ConnectionId|设备建立的对讲机通道的每个连接的 ID。|
|TransmissionStartTime |服务接收第一个音频数据包的日期和时间。
|TransmissionEndTime|服务接收最后一个音频数据包的日期和时间。|
|参与者列表|发送传输时连接到通道的设备 ID 的分号分隔列表。|
|CallTimedOut|传输是否超出持续时间限制。 这是一个布尔值。|
|平台|设备操作系统。|
|参与者类型|参与者是传输的发射器还是接收器。|
|WebSocketState|传输启动时，设备与服务之间的连接状态是否已建立。|
|AppVersion|设备上安装的 Teams 应用版本。|

## <a name="related-articles"></a>相关文章

- [Teams 中的 Walkie Talkie 应用](../walkie-talkie.md)
- [Walkie Talkie 入门](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)