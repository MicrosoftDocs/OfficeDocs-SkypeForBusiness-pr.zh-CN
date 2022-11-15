---
title: 在 Microsoft Teams 中规划实时事件
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: sonua
f1.keywords:
- NOCSH
ms.localizationpriority: high
ms.collection:
- M365-collaboration
- m365initiative-meetings
- m365initiative-meetings-enabler
- enabler-strategic
- highpri
search.appverid: MET150
description: 在本文中，你将了解在 Microsoft Teams 中设置实时事件之前要考虑的因素。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a1bbc6452847182533271f4aa7c7652ff8b00ba3
ms.sourcegitcommit: 73b13cd8a79ba1724b9fb79c8356a7cacafb7dd3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2022
ms.locfileid: "68966311"
---
# <a name="plan-for-live-events-in-microsoft-teams"></a>在 Microsoft Teams 中规划实时事件

计划 Teams 实时事件时，若要在组织中召开大型会议，则在开始设置之前，需要考虑几个因素。

> [!Note]
> For details about Teams live events on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3). See [prepare your organization](../prepare-network.md) to learn about bandwidth requirements for Teams live events.

## <a name="who-can-attend-create-and-schedule-live-events"></a>谁可以参加、创建和计划实时事件

Anyone can attend a live event without a license. Read [Admin quick start - Meetings and live events](../quick-start-meetings-live-events.md).

若要安排 Teams 实时事件，用户必须满足以下前提条件。

以下是组织、制作或呈现 Teams 现场活动所必须分配的许可证：  

- **组织：** Microsoft 或 Office 365 企业版 E1、E3 或 E5 许可证，**[或]** Microsoft 或 Office 365 教育版 A3 或 A5 许可证。 
- **To produce or present:** A Microsoft or Office 365 Enterprise E1, E3 or E5 license, **[or]** a Microsoft or Office 365 Education A1, A3 or A5 license. The exception to this requirement is guest users can present without a license if the other criteria for [guest users](plan-for-teams-live-events.md#guest-to-present) is met.
- Microsoft Teams 许可证 - 此许可证包含在第一个和第二个项目符合所列的许可证中。
- 如果你计划将内容共享到外部应用或设备，则需要 Microsoft Stream 许可证；请参阅 [Microsoft Stream 许可证](/stream/license-overview)。 如果使用较新的 Teams 编码器服务来生成事件，则不需要流许可证。 

  Users won't need a Microsoft Stream license assigned if you want users to only record and download the recordings. This will mean that the recordings aren't stored in Microsoft Stream but are instead stored in Azure Media Services (AMS) with a 180-day limit before it's deleted. It's not something at this point that an admin can control or manage to include the ability to delete it.

>[!Note]
> The change from using Microsoft Stream to [OneDrive for Business and SharePoint for meeting recordings](../tmr-meeting-recording-change.md) will be a phased approach. At launch you'll be able to opt-in to this experience, in November you'll have to opt-out if you want to continue using Stream, and some time in early 2021 we'll require all customers to OneDrive for Business and SharePoint for meeting recordings.

> [!NOTE]
> 目前，没有任何 Microsoft 365 小型企业版计划可用于创建和保留 Teams 实时事件。

注意，Microsoft 365 或 Office 365 许可证是经过身份验证的用户参见实时事件的必要条件，但是此要求取决于所使用的制作方式：

- **对于在 Teams 中或使用 Teams Powered Encoder 生成的事件**  必须为用户分配 Teams 许可证。
- **使用外部应用程序或设备制作的事件** 必须向该用户分配 Stream 许可证。

> [!NOTE]
> “Teams 实时活动”现在可为美国政府云社区（GCC）组织提供。

有关许可的详细信息，请参阅 [Microsoft Teams 附加许可](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。

用户必须：

- Teams 中已启用私人会议安排（*TeamsMeetingPolicy -AllowPrivateMeetingScheduling 参数 = True*）。
- Teams 会议中已启用视频共享（*TeamsMeetingPolicy -AllowIPVideo 参数 = True*）。
- Teams 会议中启用屏幕共享（*TeamsMeetingPolicy -ScreenSharingMode parameter = EntireScreen*）。
- Teams 中启用实时会议安排（*TeamsMeetingBroadcastPolicy -AllowBroadcastScheduling 参数 = True*）。
- 使用 Stream 创建实时事件的权限（适用于外部应用或设备制作）。
- 配置了共存模式，以能够安排 Teams 会议（*并行、会议优先或仅 Teams*）。

> [!IMPORTANT]
> 未经身份验证的匿名用户不能被邀请为 Teams 实时事件中的“制作者”或“演示者”。

### <a name="guest-to-present"></a>[出席来宾](#guest-to-present)

若要让来宾出席直播活动，请执行下列 Tasks:

1. [将该用户作为来宾添加到团队](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f)。
2. 让该用户接受来宾邀请并加入团队。
3. [安排直播活动并将来宾添加到活动组](https://support.microsoft.com/article/schedule-a-teams-live-event-7a9ce97c-e1cd-470f-acaf-e6dfc179a0e2)。

As a best practice, we recommend that you create a channel for producers and presenters of the live event so they can chat and share information before the event. Guests who don't have Microsoft 365 credentials won't see the Calendar in Teams. To make it easy for them to join the event, producers can post the event link to the channel. Presenters can then open Teams, go to the channel, and then select the link to join the event.

## <a name="who-can-watch-live-events"></a>谁可以观看实时事件

| 与会者可见性 | Teams 制作 | 外部应用或设备制作 | Teams Powered Encoder
|------------------------------|-----------------|----------------------|----------------|
|公共（匿名用户）      |  是            |  否                  | 是
|来宾用户                   |  是<sup>1</sup>            |  否                  |  支持            |
|外部访问（联盟）公司中的任何人 |  是<sup>1</sup>|  否                  | 是            |
|公司中的所有人           |  是            |  是                 | 是                |
|指定组/人员      |  是            |  是                 | 是                |

<sup>1</sup> 只能通过“人员和组”邀请 <br>

## <a name="teams-live-events"></a>Teams 实时事件

下表重点介绍直播活动中提供的核心功能和功能

> [!IMPORTANT]
> **Microsoft 365 实时事件限制的增加**
>
> **为了继续满足客户需求，我们将现场活动的临时限制增加延长至 2022 年 12 月 31 日，包括**：
>
>- 可为多达20,000名与会者提供活动支持
>- 一个租户可同时举办50场活动
>- 每次广播的活动持续时间为16小时
>
> Additionally, live events with up to 100,000 attendees can be planned through the Microsoft 365 live events assistance program. The team will assess each request and work with you to determine options that may be available. [Learn more](https://aka.ms/Stream/Blog/LiveEventOptions). 

| 功能 | Skype 会议直播 | 在 Teams 中制作的事件 | 使用外部应用或设备制作的事件 |
|---------|---------|---------|---------|
|最大受众规模 |10,000 名与会者 |10,000 名与会者<sup>1</sup> |10,000 名与会者<sup>1</sup> |
|实时事件最大持续时间 |4 小时 |4 小时 |4 小时 |
|现场活动中演示者和制作者最大数量 |10 <sup>2</sup> |10 <sup>2</sup> |10 <sup>2</sup> |
|每个 Microsoft 365 或 Office 365 组织的最大并发实时事件数量 |15  | 15  | 15  |
|创建实时事件 |   Skype 会议直播门户 |团队、Yammer （通过 Teams） | Teams、Yammer （通过团队），Stream |
|受众参与 – Yammer |&#x2714; |&#x2714;（集成体验） |&#x2714;（集成体验） |
|受众参与 – 已审核问答 |&#x2714;  |&#x2714; |&#x2714; |
|Windows 制作者客户端 |&#x2714; (Skype for Business) |&#x2714; (Teams) |&#x2714; （Stream、Teams （通过嵌入 Stream）） |
|Mac 制作者客户端 |&#x274C;  | &#x2714; (Teams) |&#x2714; （Stream、Teams （通过嵌入 Stream）） |
|制作者用户界面参与者计数 |&#x274C;  |&#x2714; (Teams) |&#x2714; （Stream、Teams （通过嵌入 Stream）） |
|允许多个演示者 |&#x2714; (Skype for Business) |&#x2714; (Teams) |不适用  |
|会议期间邀请演示者 |&#x2714; (Skype for Business) |&#x274C; |不适用 |
|演示者通过 Web 和移动设备加入 |&#x2714; (Skype for Business)  |&#x274C; |不适用 |
|外部访问（联盟）和来宾演示者/与会者 |&#x2714; (Skype for Business)  |  &#x2714; (Teams) |不适用 |
|演示者 – PSTN 接入 |&#x274C; |&#x2714; (Teams) |不适用 |
|演示屏幕 |&#x274C; |&#x2714; (Teams) |不适用 |
|在 Windows 上共享系统音频（仅在屏幕共享时可用）|&#x274C; |&#x2714; (Teams) |&#x2714; |
|演示 PowerPoint （PPT 共享） |&#x2714; |&#x274C;（通过屏幕共享缓解） |不适用 |
|云基会议录制 |&#x2714; |&#x2714; |&#x2714; |
|自动将录制发布到 Stream |&#x274C; |&#x274C; |&#x2714; |
|实时辅助字幕与字幕 |&#x2714; |&#x2714; |&#x274C; |
|实时事件录制字幕 |&#x2714; |&#x2714; |&#x2714; |
|与会者 DVR 控件（暂停、后退） |&#x2714; |&#x2714; |&#x2714; |
|Microsoft eCDN |&#x274C; |&#x2714; |&#x2714; |
|合作伙伴 eCDN 支持 |&#x2714; (Kollective, Hive, Riverbed) |&#x2714; (Kollective, Hive, Ramp, Riverbed) |&#x2714; (Hive, Kollective, Ramp, Riverbed) |
|制作者直播后受众报告 |&#x2714; |&#x2714; |&#x274C; |
|受众情绪分析 – 实时投票和民意调查 |&#x2714; (Microsoft Pulse) |&#x274C; |&#x274C; |

<sup>1</sup> The limits that are set might be changed. Check [Limits and specifications for Teams](../limits-specifications-teams.md).<br/>
<sup>2</sup> 可在实时事件中拥有多达 100 位演示者和制作者，但列表中仅显示最后 10 位发言的人员。

## <a name="regional-availability"></a>区域可用性

You can use Teams live events in multiple regions across the world. The following information shows availability for event team members and attendees.

> [!IMPORTANT]
> 将根据组织者和 Microsoft 365 租户的位置自动选择事件的区域。

**可用于以下区域数据中心**

- 北美洲
- 中美洲
- 南美洲
- 亚太地区
- 欧洲/非洲

**以下国家/地区（支持）的数据位置**

- 澳大利亚
- 巴西
- 加拿大
- 法国
- 德国
- 印度
- 日本
- 挪威
- 新加坡
- 南非
- 韩国
- 瑞士
- 阿拉伯联合酋长国
- 英国

**排除和注意事项**

- **数据位置:** 暂不支持上述数据地点以外的团队数据地点。

## <a name="next-steps"></a>后续步骤

转到[设置 Teams 实时事件](set-up-for-teams-live-events.md)。

### <a name="related-topics"></a>相关主题

- [什么是 Teams 实时活动?](what-are-teams-live-events.md)
- [设置 Teams 实时事件](set-up-for-teams-live-events.md)
- [配置 Teams 实时事件设置](configure-teams-live-events.md)
