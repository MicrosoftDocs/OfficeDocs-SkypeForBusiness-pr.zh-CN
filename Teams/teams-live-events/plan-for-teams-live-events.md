---
title: 在 Microsoft Teams 中规划实时事件
author: chuckedmonson
ms.author: chucked
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
description: 了解在 Microsoft 团队中设置实时事件之前需要考虑的因素。
appliesto:
- Microsoft Teams
ms.openlocfilehash: eaa9e00ea3491b66eedbcf8f00e3108b582d7aa9
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41827120"
---
# <a name="plan-for-live-events-in-microsoft-teams"></a>在 Microsoft Teams 中规划实时事件

当你计划团队活动活动以在你的组织中召开大型会议时，在开始将其设置为 "全部" 之前，需要考虑以下几个因素。 

## <a name="who-can-create-and-schedule-live-events"></a>哪些人可以创建和安排实时事件？ 
用户需要具备以下先决条件才能安排团队实时事件。

以下是必须分配的许可证：  
- Office 365 企业版 E1、E3 或 E5 许可证或 Office 365 A3 或 A5 许可证
- Microsoft 团队许可
- Microsoft Stream 许可证

> [!IMPORTANT]
> 创建和安排实时事件的用户必须具有 Exchange Online 邮箱。

请务必了解，需要 Office 365 许可证作为经过身份验证的用户参与实时事件，但此要求取决于所使用的生产方法：

- **对于团队中产生的事件** 必须为用户分配团队许可证。
- **对于使用外部应用或设备生成的事件**必须为用户分配流许可证。

> [!NOTE]
> 团队实况活动现在可供美国政府云社区（GCC）组织使用。

有关许可的详细信息，请参阅[Microsoft 团队加载项许可](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。

用户必须拥有：
- 启用团队中的私人会议计划（*TeamsMeetingPolicy-AllowPrivateMeetingScheduling 参数 = True*）。
- 团队会议中启用了视频共享（*TeamsMeetingPolicy-AllowIPVideo 参数 = True*）。
- 团队会议中启用了屏幕共享（*TeamsMeetingPolicy-ScreenSharingMode 参数 = EntireScreen*）。
- 启用团队中的实时事件调度（*TeamsMeetingBroadcastPolicy-AllowBroadcastScheduling 参数 = True*）。
- 在流中创建实时事件（适用于外部应用或设备生产）的权限。

> [!IMPORTANT]
> 未验证身份的匿名用户不能被邀请为团队实时事件中的生产者或演示者。 
 
## <a name="who-can-watch-live-events"></a>哪些人可以观看实时事件？

|**与会者可见性**       |**团队生产**  |**外部应用或设备生产**  |
|------------------------------|-----------------|----------------------|
|公共（匿名用户）      |  是            |  否                  |
|来宾用户                   |  否<sup>1</sup> |  否                  |
|联合公司中的每个人 |  无<sup>2</sup> |  否                  |
|公司中的每个人           |  必需            |  是                 |
|特定组/人员      |  必需            |  是                 |

如果实时事件是使用**组织范围**选项设置的，则<sup>1</sup>可以观看实时事件。<br>
<sup>2</sup>只能以匿名用户身份观看实时事件。

 
## <a name="teams-live-events-and-skype-meeting-broadcast"></a>团队实况活动和 Skype 会议直播

下表重点介绍实时事件中提供的核心功能和功能以及它们与 Skype 会议直播有何区别。 

|**能**   |**Skype 会议直播** |**团队中产生的事件** |**在外部应用或设备中生成的事件** |
|---------|---------|---------|---------|
|最大受众大小 |10,000 名与会者 |10000与会者<sup>1</sup> |10000与会者<sup>1</sup> |
|实时事件的最长持续时间 |4 小时 |4 小时 |4 小时 |
|每个 Office 365 租户的最大并发实时事件数 |岁  | 岁  | 岁  |
|实时事件创建 |   Skype 会议直播门户 |团队，通过团队进行 Yammer | 团队、Yammer （通过团队、流） |
|受众参与– Yammer |&#x2714; |&#x2714; （集成体验） |&#x2714; （集成体验） |
|受众参与– & |&#x2714;  |&#x2714; |&#x2714; |
|Windows 上的制造者客户端 |&#x2714; （Skype for Business） |&#x2714; （团队） |&#x2714; （流，通过流嵌入进行的团队） |
|Mac 上的制造者客户端 |X  | &#x2714; （团队） |&#x2714; （流，通过流嵌入进行的团队） |
|制造者 UI 中的与会者计数 |X  |&#x2714; （团队） |&#x2714; （流，通过流嵌入进行的团队） |
|允许多个演示者 |&#x2714; （Skype for Business） |&#x2714; （团队） |不适用  |
|会议期间邀请演示者 |&#x2714; （Skype for Business） |X |不适用 |
|演示者加入 Web 和手机 |&#x2714; （Skype for Business）  |X |不适用 |
|联合 & 来宾演示者/与会者 |&#x2714; （Skype for Business）  | （即将推出） |不适用 |
|演示者-PSTN 访问 |X |&#x2714; （团队） |不适用 |
|演示屏幕 |X |&#x2714; （团队） |不适用 |
|演示 PowerPoint （PPT 共享） |&#x2714; |X （通过屏幕共享缓解） |不适用 |
|基于云的会议录制 |&#x2714; |&#x2714; |&#x2714; |
|自动发布录制到流 |X |X |&#x2714; |
|实时字幕和副标题 |&#x2714; |&#x2714; |X |
|实时事件录制中的标题 |&#x2714; |&#x2714; |&#x2714; |
|与会者 DVR 控件（暂停、后退） |&#x2714; |&#x2714; |&#x2714; |
|合作伙伴 eCDN 支持 |&#x2714; （蜂巢、Kollective、斜坡） |&#x2714; （蜂巢、Kollective、斜坡） |&#x2714; （蜂巢、Kollective、斜坡） |
|针对生产者的后置广播出席报告 |&#x2714; |&#x2714; |X |
|受众情绪分析-实时投票 & 投票 |&#x2714; （Microsoft 脉冲） |X |X |

<sup>1</sup>设置的限制可能会更改。

## <a name="regional-availability"></a>区域可用性
您可以在世界上的多个地区使用团队活动事件。 以下信息显示事件团队成员和与会者的可用性。 

> [!IMPORTANT]
> 将自动选择事件的区域，具体取决于组织者和 Office 365 组织。

**在这些地区可用**
- 地区
- 欧洲/非洲
- 亚太地区
- 前往本地加拿大、印度、澳大利亚、日本、英国

**排除和注意事项**
- **转到本地：** 当前不支持团队在上面列出的局部变量之外的局部变量。
- **中国：** 活动团队成员和与会者将无法使用团队实时事件，因为 Azure CDN 在中国不可访问。 解决方法是使用公司 VPN 连接，它通过客户的公司网络获取连接到 CDN 的客户端。

## <a name="next-steps"></a>后续步骤
转到[为团队实时事件设置](set-up-for-teams-live-events.md)。

### <a name="related-topics"></a>相关主题
- [什么是 Teams 实时事件？](what-are-teams-live-events.md)
- [设置 Teams 实时事件](set-up-for-teams-live-events.md)
- [配置团队中的实时事件设置](configure-teams-live-events.md)

