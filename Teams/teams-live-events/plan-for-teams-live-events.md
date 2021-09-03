---
title: 在 Microsoft Teams 中规划实时事件
author: cichur
ms.author: v-cichur
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
search.appverid: MET150
description: 在本文中，你将了解在 Microsoft Teams 中设置实时事件之前要考虑的因素。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8996c796d6ab5a2e98c636a115707e6bb2249c6e
ms.sourcegitcommit: 65964d5079120c900abdba24c08d4cc18d2fde7a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/03/2021
ms.locfileid: "58883750"
---
# <a name="plan-for-live-events-in-microsoft-teams"></a>在 Microsoft Teams 中规划实时事件

计划 Teams 实时事件时，若要在组织中召开大型会议，则在开始设置之前，需要考虑几个因素。

> [!Note]
> 有关不同平台上的 Teams 实时事件的详细信息，请参阅 [Teams 功能（按平台）](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)。请参阅[让你的组织做好准备](../prepare-network.md)，了解 Teams 直播活动的带宽要求。

## <a name="who-can-attend-create-and-schedule-live-events"></a>谁可以参加、创建和计划实时事件

任何人都可以在没有许可证的情况下参加实时事件。请阅读[管理员快速入门 - 会议和实时事件](../quick-start-meetings-live-events.md)。

若要安排 Teams 实时事件，用户必须满足以下前提条件。

以下是组织、制作或呈现 Teams 现场活动所必须分配的许可证：  

- **组织：** Microsoft 或 Office 365 企业版 E1、E3 或 E5 许可证，**[或]** Microsoft 或 Office 365 教育版 A3 或 A5 许可证。 
- **制作或呈现：** Microsoft 或 Office 365 企业版 E1、E3 或 E5 许可证，**[或]** Microsoft 或 Office 365 教育版 A1、A3 或 A5 许可证。此要求的例外情况是：如果满足 [来宾用户](plan-for-teams-live-events.md#guest-to-present) 的其他条件，来宾用户无需许可证即可出席。
- Microsoft Teams 许可证 - 此许可证包含在第一个和第二个项目符合所列的许可证中。
- 如果你计划将内容共享到外部应用或设备，则需要 Microsoft Stream 许可证；请参阅 [Microsoft Stream 许可证](/stream/license-overview)。

  如果你希望用户仅进行录制和下载录制的内容，那么这些用户无需拥有 Microsoft Stream 许可证。这意味着录制的内容不会存储在 Microsoft Stream 中，而是存储在 Azure 媒体服务 (AMS) 中，且存储 180 天后被删除。目前，管理员无法控制或管理此设置来包含删除这些内容的功能。

>[!Note]
> 将会议录制从 Microsoft Stream 改为 [OneDrive for Business 和 SharePoint](../tmr-meeting-recording-change.md) 将是一种分阶段的方法。在发布时，你将能够选择加入此体验，如果想继续使用 Stream，则在 11 月你必须选择退出，在 2021 年初的某个时候，我们将要求所有客户使用 OneDrive for Business 和 SharePoint 进行会议录制。

> [!NOTE]
> 目前，没有任何 Microsoft 365 小型企业版计划可用于创建和保留 Teams 实时事件。

注意，Microsoft 365 或 Office 365 许可证是经过身份验证的用户参见实时事件的必要条件，但是此要求取决于所使用的制作方式：

- **使用 Teams 制作的事件**  必须为用户分配 Teams 许可证。
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

作为最佳做法，我们建议你为直播活动的制作者和演示者创建一个频道，以便他们可以在活动前聊天和共享信息。没有 Microsoft 365 凭据的来宾将无法在 Teams 中看到日历。为便于用户加入活动，制作者可将活动链接发布到相应频道。演示者随后可以打开 Teams，转到该频道，然后单击链接以加入该活动。

## <a name="who-can-watch-live-events"></a>谁可以观看实时事件

| 与会者可见性 | Teams 制作 | 外部应用或设备制作 |
|------------------------------|-----------------|----------------------|
|公共（匿名用户）      |  是            |  否                  |
|来宾用户                   |  是<sup>1</sup>            |  否                  |
|外部访问（联盟）公司中的任何人 |  是<sup>1</sup>|  否                  |
|公司中的所有人           |  是            |  是                 |
|指定组/人员      |  是            |  是                 |

<sup>1</sup> 只能通过“人员和组”邀请 <br>

## <a name="teams-live-events-and-skype-meeting-broadcast"></a>Teams 实时事件和Skype 会议直播

下表突出显示了实时事件中提供的核心功能以及区别 Skype 会议直播的方式。

> [!IMPORTANT]
> **Microsoft 365 实时事件限制的增加**
>
> **为了继续支持客户的需求，在 2022 年 1 月 31 日前，我们将延长直播活动的临时限制增加，包括**：
>
>- 可为多达20,000名与会者提供活动支持
>- 一个租户可同时举办50场活动
>- 每次广播的活动持续时间为16小时
>
> 此外，可通过 Microsoft 365 辅助计划规划最多 100,000 名与会者的实时活动。团队将评估每个请求，并共同确定可能可用的选项。[了解详情](https://aka.ms/Stream/Blog/LiveEventOptions)。 

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
|合作伙伴 eCDN 支持 |&#x2714; (Kollective, Hive, Riverbed) |&#x2714; (Kollective, Hive, Ramp, Riverbed) |&#x2714; (Hive, Kollective, Ramp, Riverbed) |
|制作者直播后受众报告 |&#x2714; |&#x2714; |&#x274C; |
|受众情绪分析 – 实时投票和民意调查 |&#x2714; (Microsoft Pulse) |&#x274C; |&#x274C; |

<sup>1</sup> 设定的限制可能会更改。查看 [Teams 限制和规范](../limits-specifications-teams.md)。<br/>
<sup>2</sup> 可在实时事件中拥有多达 100 位演示者和制作者，但列表中仅显示最后 10 位发言的人员。

## <a name="regional-availability"></a>区域可用性

可在全球中的多个区域实用 Teams 实时事件。以下信息显示事件团队成员和参与者的空闲时间。

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
- 加拿大
- 法国
- 德国
- 印度
- 日本
- 南非
- 韩国
- 瑞士
- 阿拉伯联合酋长国
- 英国

**不支持这些国家/地区和云**

- 巴西
- 挪威
- 政府社区云 (GCC)-H
- 国防部 (DOD)

**排除和注意事项**

- **数据位置:** 暂不支持上述数据地点以外的团队数据地点。
- **中国：**  事件团队成员和参与者将无法使用 Teams 事件，因为 Azure CDN 在中国不可访问。解决方法是使用公司 VPN 连接，后者通过客户的公司网络获取连接到 CDN 的客户端。

## <a name="next-steps"></a>后续步骤

转到[设置 Teams 实时事件](set-up-for-teams-live-events.md)。

### <a name="related-topics"></a>相关主题

- [什么是 Teams 实时活动?](what-are-teams-live-events.md)
- [设置 Teams 实时事件](set-up-for-teams-live-events.md)
- [配置 Teams 实时事件设置](configure-teams-live-events.md)
