---
title: 在 Microsoft Teams 中规划实时事件
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 08/19/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: sonua
f1.keywords:
- NOCSH
localization_priority: Priority
ms.collection:
- M365-collaboration
search.appverid: MET150
description: 在本文中，你将了解在 Microsoft Teams 中设置实时事件之前要考虑的因素。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 51c81bb5c9ec945d7a7c47021a6a0af705c98883
ms.sourcegitcommit: 09ff11f8e4f6a93cedc34a5d732a133163df79a0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/05/2020
ms.locfileid: "44042849"
---
# <a name="plan-for-live-events-in-microsoft-teams"></a>在 Microsoft Teams 中规划实时事件

计划 Teams 实时事件时，若要在组织中召开大型会议，则在开始设置所有操作之前，需要考虑几个因素。

## <a name="who-can-attend-create-and-schedule-live-events"></a>谁可以参加、创建和计划实时事件

任何人都可以在没有许可证的情况下参加实时事件。 请阅读[管理员快速入门 - 会议和实时事件](../quick-start-meetings-live-events.md)。

若要安排 Teams 实时事件，用户必须满足以下前提条件。

下面是必须分配的许可证：  

- Office 365 企业版 E1、E3 或 E5 许可证，或 Office 365 A3 或 A5 许可证
- Microsoft Teams 许可证
- Microsoft Stream 许可证

> [!IMPORTANT]
> 创建和安排实时事件的用户必须拥有 Exchange Online 邮箱。

注意，Office 365 许可证是经过身份验证的用户参见实时事件的必要条件，但是此要求取决于所使用的制作方式：

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
> 未经身份验证的匿名用户不能被邀请为 Teams 实时 事件中的“制作者”或“演示者”。

## <a name="who-can-watch-live-events"></a>谁可以观看实时事件

|**参加者可见性**       |**Teams 制作**  |**外部应用或设备制作**  |
|------------------------------|-----------------|----------------------|
|公共（匿名用户）      |  是            |  否                  |
|来宾用户                   |  是            |  否                  |
|外部访问（联盟）公司中的任何人 |  是<sup>1</sup>|  否                  |
|公司中的所有人           |  是            |  是                 |
|指定组/人员      |  是            |  是                 |

<sup>1</sup>只能通过“人员和组”邀请外部访问（联盟）与会者。 <br>

## <a name="teams-live-events-and-skype-meeting-broadcast"></a>Teams 实时事件和Skype 会议直播

下表突出显示了实时事件中提供的核心功能以及区别 Skype 会议直播的方式。

|**功能**   |**Skype 会议直播** |**在 Teams 中制作的事件** |**使用外部应用或设备制作的事件** |
|---------|---------|---------|---------|
|最大受众规模 |10,000 名与会者 |10,000 名与会者<sup>1</sup> |10,000 名与会者<sup>1</sup> |
|实时事件最大持续时间 |4 小时 |4 小时 |4 小时 |
|现场活动中演示者和制作者最大数量 |10 <sup>2</sup> |10 <sup>2</sup> |10 <sup>2</sup> |
|每个 Office 365 组织的最大并发实时事件数量 |15  | 15  | 15  |
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
|合作伙伴 eCDN 支持 |&#x2714; (Hive, Kollective, Ramp) |&#x2714; (Hive, Kollective, Ramp) |&#x2714; (Hive, Kollective, Ramp) |
|制作者直播后受众报告 |&#x2714; |&#x2714; |&#x274C; |
|受众情绪分析 – 实时投票和民意调查 |&#x2714; (Microsoft Pulse) |&#x274C; |&#x274C; |

<sup>1</sup> 设定的限制可能会更改。 查看 [Teams 限制和规范](../limits-specifications-teams.md)。<br/>
<sup>2</sup> 可在实时事件中拥有多达 250 位演示者和制作者，但列表中仅显示最后 10 位发言的人员。

## <a name="regional-availability"></a>区域可用性

可在全球中的多个区域实用 Teams 实时事件。 以下信息显示事件团队成员和参与者的空闲时间。

> [!IMPORTANT]
> 将根据组织者和 Microsoft 365 租户的位置自动选择事件的区域。

**可用于以下区域数据中心**

- 美洲
- 亚太地区
- 欧洲/非洲

**以下国家/地区的数据位置**

- 澳大利亚
- 加拿大
- 印度
- 日本
- 英国

**例外和注意事项**

- **数据位置：** 暂不支持除以上所列国家/地区之外的其他任何 Teams 数据位置。
- **中国：** 事件团队成员和参与者将无法使用 Teams 事件，因为 Azure CDN 在中国不可访问。 解决方法是使用公司 VPN 连接，后者通过客户的公司网络获取连接到 CDN 的客户端。

## <a name="next-steps"></a>后续步骤

转到[设置 Teams 实时事件](set-up-for-teams-live-events.md)。

### <a name="related-topics"></a>相关主题

- [什么是 Teams 实时事件？](what-are-teams-live-events.md)
- [设置 Teams 实时事件](set-up-for-teams-live-events.md)
- [配置 Teams 实时事件设置](configure-teams-live-events.md)
