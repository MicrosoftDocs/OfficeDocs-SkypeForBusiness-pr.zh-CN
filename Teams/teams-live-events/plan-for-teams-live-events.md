---
title: 在 Microsoft Teams 中规划实时事件
author: tonysmith
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: tonysmit
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
description: 了解如何设置中的 Microsoft 团队的实时事件之前应考虑的因素。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4c249c6e63b8342b524b54afc2a6d30be3e92b25
ms.sourcegitcommit: 889295b507c77a93b10b3a5e826f2b0c79c31f75
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/22/2019
ms.locfileid: "30771763"
---
# <a name="plan-for-live-events-in-microsoft-teams"></a>在 Microsoft Teams 中规划实时事件

在规划团队 live 事件，以保留您的组织中的大型会议时，有需要启动所有最多设置之前，需要考虑的几个因素。 

## <a name="who-can-create-and-schedule-live-events"></a>谁可以创建和安排 live 事件？ 
以下必备组件所需的用户安排的团队 live 事件。

下面是必须分配的许可证：  
- Office 365 企业版 E1、 E3 或 E5 许可证或 Office 365 A3 或 A5 许可证。 
- Microsoft 团队和 Microsoft Stream 许可证。

务必要了解 Office 365 许可证需要参与作为经过身份验证的用户的实时事件，但这取决于所使用的生产方法：

- **为快速开始生产** 必须为用户分配的 Microsoft 团队许可证。
- **为外部编码器生产**必须为用户分配 Microsoft 流许可证。

有关许可的详细信息，请参阅[Microsoft 团队加载项授权](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。

用户必须拥有：
- 在启用的团队中的专用会议计划 (*TeamsMeetingPolicy AllowPrivateMeetingScheduling 参数 = True*)。
- 启用团队会议中的视频共享 (*TeamsMeetingPolicy AllowIPVideo 参数 = True*)。
- 启用团队会议中的屏幕共享 (*TeamsMeetingPolicy ScreenSharingMode 参数 = EntireScreen*)。
- Live 事件计划中启用的团队 (*TeamsMeetingBroadcastPolicy AllowBroadcastScheduling 参数 = True*)。
- 在 Microsoft 流中的实时事件创建 （针对[外部编码器生产](#production)） 的权限。

> [!IMPORTANT]
> Office 365 来宾，联盟和匿名用户不能为生产者或团队 live 事件中的演示者邀请。 Office 365 来宾和联盟的用户可以仅观看 live 事件以匿名方式。 
 
## <a name="who-can-watch-live-events"></a>谁可以观看 live 事件？

|**Attendee 可见性**       |**快速入门**  |**外部编码器**  |
|------------------------------|-----------------|----------------------|
|公共 （匿名用户）      |  是            |  否                  |
|来宾用户                   |  没有<sup>1</sup> |  否                  |
|联盟的公司中的所有人 |  没有<sup>1</sup> |  否                  |
|公司中的所有人           |  是             |  是                 |
|特定于组 / 人员      |  是             |  是                 |

<sup>1</sup>仅可以为匿名用户观看 live 事件。

 
## <a name="teams-live-events-and-skype-meeting-broadcast"></a>团队 live 事件和 Skype 会议广播
下表重点介绍的核心功能和实时事件和它们与 Skype 会议广播的不同方式中提供的功能。 

|**功能**   |**Skype 会议直播** |**在 Microsoft 团队中生成的事件** |**外部应用程序或设备中生成事件** |
|---------|---------|---------|---------|
|最大访问群体大小 |10,000 与会者 |10,000 与会者 * |10,000 与会者 * |
|最长持续时间 live 事件 |4 个小时 |4 个小时 |4 个小时 |
|创建 live 事件 |   Skype 会议广播的门户 |通过团队 Yammer 团队 | 通过团队流 Yammer 团队 |
|访问群体合作 – Yammer |& #x 2714; |& #x 2714;（集成的体验） |& #x 2714;（集成的体验） |
|访问群体合作 – 仲裁 Q & A |& #x 2714;  |& #x 2714; |& #x 2714; |
|不对 Windows 上的客户端 |& #x 2714;(For Business 的 Skype) |& #x 2714;（工作组） |& #x 2714;（流，通过流团队嵌入） |
|在 Mac 上不对客户端 |X  | & #x 2714;（工作组） |& #x 2714;（流，通过流团队嵌入） |
|不对用户界面中的与会者计数 |X  |& #x 2714;（工作组） |& #x 2714;（流，通过流团队嵌入） |
|允许多个演示者 |& #x 2714;(For Business 的 Skype) |& #x 2714;（工作组） |不适用  |
|在会议期间邀请演示者 |& #x 2714;(For Business 的 Skype) |X |不适用 |
|Web 和移动设备上的演示者加入 |& #x 2714;(For Business 的 Skype)  |X |不适用 |
|联盟的 & 来宾演示者/与会者 |& #x 2714;(For Business 的 Skype)  | （即将推出） |不适用 |
|演示者 – PSTN 访问 |X |& #x 2714;（工作组） |不适用 |
|显示一个屏幕 |X |& #x 2714;（工作组） |不适用 |
|演示 PowerPoint （PPT 共享） |& #x 2714; |X （通过屏幕共享缓解） |不适用 |
|基于云的会议录制 |& #x 2714; |& #x 2714; |& #x 2714; |
|自动将记录发布到 Microsoft 流 |X |X |& #x 2714; |
|实时标题和转换 |& #x 2714; |& #x 2714;（即将推出） |X |
|在 live 事件录制的标题 |& #x 2714; |& #x 2714;（即将推出） |& #x 2714; |
|Attendee DVR 控件 （暂停、 后退） |& #x 2714; |& #x 2714; |& #x 2714; |
|合作伙伴 eCDN 支持 |& #x 2714;（配置单元，Kollective，提升） |& #x 2714;（配置单元，Kollective，提升） |& #x 2714;（配置单元，Kollective，提升） |
|生产者后广播出席情况报告 |& #x 2714; |& #x 2714; |X |
|访问群体的观点分析 – Live 投票 & 投票 |& #x 2714;（Microsoft 脉冲） |X |X |

> [!IMPORTANT]
> 可能更改设置的限制。

## <a name="regional-availability"></a>区域的可用性
您可以使用团队 live 事件中的多个区域遍及世界各地。 以下信息显示事件工作组成员和与会者的可用性。 

> [!IMPORTANT]
> 根据组织者和 Office 365 组织情况下自动选择的区域的事件。

**在这些区域中可用**
- 美国
- 欧洲/非洲
- 亚太地区
- 转到本地加拿大

**排除和注意事项**
- **转局部变量：** 当前不支持英国、 印度、 澳大利亚、 日本和其他 Microsoft 团队转局部变量。
- **中国：** 事件团队成员和与会者将不能使用团队 live 事件，因为 Azure CDN 不是在中国可访问。 解决方法是使用公司 VPN 连接，获取通过客户的企业网络连接到 CDN 的客户端。

## <a name="next-steps"></a>后续步骤
转到[团队 live 事件的设置](set-up-for-teams-live-events.md)。

### <a name="related-topics"></a>相关主题
- [什么是 Teams 实时事件？](what-are-teams-live-events.md)
- [设置 Teams 实时事件](set-up-for-teams-live-events.md)
- [在工作组中配置 live 事件设置](configure-teams-live-events.md)

