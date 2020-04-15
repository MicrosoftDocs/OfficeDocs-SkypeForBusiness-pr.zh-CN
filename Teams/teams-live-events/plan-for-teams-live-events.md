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
localization_priority: Normal
ms.collection:
- M365-collaboration
search.appverid: MET150
description: 了解在 Microsoft Teams 中设置实时事件之前要考虑的因素。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2f70a7a2be51045f616ebb4cedc5baf46dbe101d
ms.sourcegitcommit: 56ceda54ca48d2984298d4d1f26017c0147d4431
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2020
ms.locfileid: "43505619"
---
# <a name="plan-for-live-events-in-microsoft-teams"></a>在 Microsoft Teams 中规划实时事件

计划 Teams 实时事件时，若要在组织中召开大型会议，则在开始设置所有操作之前，需要考虑几个因素。 

## <a name="who-can-create-and-schedule-live-events"></a>谁可以创建和安排实时事件？ 
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
- 已配置为能够安排团队会议的共存模式（*仅限岛、会议优先或团队*会议）。

> [!IMPORTANT]
> 未经身份验证的匿名用户不能被邀请为 Teams 实时 事件中的“制作者”或“演示者”。 
 
## <a name="who-can-watch-live-events"></a>谁可以观看实时事件？

|**参加者可见性**       |**Teams 制作**  |**外部应用或设备制作**  |
|------------------------------|-----------------|----------------------|
|公共（匿名用户）      |  是            |  否                  |
|来宾用户                   |  是            |  否                  |
|联盟公司中的所有人 |  是<sup>1</sup>|  否                  |
|公司中的所有人           |  是            |  是                 |
|指定组/人员      |  是            |  是                 |

只有<sup>1</sup>个联盟的与会者才能通过 & 组的人员进行邀请 <br>
 
## <a name="teams-live-events-and-skype-meeting-broadcast"></a>Teams 实时事件和Skype 会议直播

下表突出显示了实时事件中提供的核心功能以及区别 Skype 会议直播的方式。 

|**功能**   |**Skype 会议直播** |**在 Teams 中制作的事件** |**使用外部应用或设备制作的事件** |
|---------|---------|---------|---------|
|最大受众规模 |10,000 名与会者 |10,000 名与会者<sup>1</sup> |10,000 名与会者<sup>1</sup> |
|实时事件最大持续时间 |4 小时 |4 小时 |4 小时 |
|实时事件中演示者和发生器的最大数量 |10 <sup>2</sup> |10 <sup>2</sup> |10 <sup>2</sup> |
|每 Office 365 租户最大并发实时事件数量 |岁  | 岁  | 岁  |
|创建实时事件 |   Skype 会议直播门户 |团队、Yammer （通过 Teams） | Teams、Yammer （通过团队），Stream |
|受众参与 – Yammer |&#x2714; |&#x2714;（集成体验） |&#x2714;（集成体验） |
|受众参与 – 已审核问答 |&#x2714;  |&#x2714; |&#x2714; |
|Windows 制作者客户端 |&#x2714; (Skype for Business) |&#x2714; (Teams) |&#x2714; （Stream、Teams （通过嵌入 Stream）） |
|Mac 制作者客户端 |&#x274C;  | &#x2714; (Teams) |&#x2714; （Stream、Teams （通过嵌入 Stream）） |
|制作者用户界面参与者计数 |&#x274C;  |&#x2714; (Teams) |&#x2714; （Stream、Teams （通过嵌入 Stream）） |
|允许多个演示者 |&#x2714; (Skype for Business) |&#x2714; (Teams) |不适用  |
|会议期间邀请演示者 |&#x2714; (Skype for Business) |&#x274C; |不适用 |
|演示者通过 Web 和移动设备加入 |&#x2714; (Skype for Business)  |&#x274C; |不适用 |
|联合和来宾演示者/参与者 |&#x2714; (Skype for Business)  |  &#x2714; (Teams) |不适用 |
|演示者 – PSTN 接入 |&#x274C; |&#x2714; (Teams) |不适用 |
|演示屏幕 |&#x274C; |&#x2714; (Teams) |不适用 |
|演示 PowerPoint （PPT 共享） |&#x2714; |&#x274C; （通过屏幕共享缓解） |不适用 |
|云基会议录制 |&#x2714; |&#x2714; |&#x2714; |
|自动将录制发布到 Stream |&#x274C; |&#x274C; |&#x2714; |
|实时辅助字幕与字幕 |&#x2714; |&#x2714; |&#x274C; |
|实时事件录制字幕 |&#x2714; |&#x2714; |&#x2714; |
|与会者 DVR 控件（暂停、后退） |&#x2714; |&#x2714; |&#x2714; |
|合作伙伴 eCDN 支持 |&#x2714; (Hive, Kollective, Ramp) |&#x2714; (Hive, Kollective, Ramp) |&#x2714; (Hive, Kollective, Ramp) |
|制作者直播后受众报告 |&#x2714; |&#x2714; |&#x274C; |
|受众情绪分析 – 实时投票和民意调查 |&#x2714; (Microsoft Pulse) |&#x274C; |&#x274C; |

<sup>1</sup> 设定的限制可能会更改。 [适用于团队的检查限制和规范](../limits-specifications-teams.md)。<br/>
<sup>2</sup>在实时事件中，你最多可以有250个演示者和发生器，但仅在列表中显示最后10个分支。


## <a name="regional-availability"></a>区域可用性
可在全球中的多个区域实用 Teams 实时事件。 以下信息显示事件团队成员和参与者的空闲时间。 

> [!IMPORTANT]
> 事件的地区根据组织者和 Office 365 组织者自动选择。

**可在下列区域可用**
- 美洲
- 欧洲/非洲
- 亚太地区
- 转到本地 加拿大、印度、澳大利亚、日本、英国

**排除和注意事项**
- **转到本地：** 除上述列出国家/地区，不支持 Teams 转到本地。
- **中国：** 事件团队成员和参与者将无法使用 Teams 事件，因为 Azure CDN 在中国不可访问。 解决方法是使用公司 VPN 连接，后者通过客户的公司网络获取连接到 CDN 的客户端。

## <a name="next-steps"></a>后续步骤
转到[设置 Teams 实时事件](set-up-for-teams-live-events.md)。

### <a name="related-topics"></a>相关主题
- [什么是 Teams 实时事件？](what-are-teams-live-events.md)
- [设置 Teams 实时事件](set-up-for-teams-live-events.md)
- [配置 Teams 实时事件设置](configure-teams-live-events.md)
