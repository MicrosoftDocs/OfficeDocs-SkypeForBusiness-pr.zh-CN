---
title: "故障排除音频会议和已知的问题"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 72979911-5319-4de2-a275-4dd9a0f44fe6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "使用 Microsoft 为其拨入会议提供商、 状态和某些解决方法时得到已知问题的列表。 "
ms.openlocfilehash: 9e566d0ba9f07aeecca222ef586f301b1cd6cf5f
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2018
---
# <a name="audio-conferencing-troubleshooting-and-known-issues"></a>故障排除音频会议和已知的问题

 **这篇文章是 Skype 业务和 Microsoft 小组使用 Microsoft 作为其音频会议提供商的用户。它不适用于正在使用第三方音频会议提供商 (ACP) 的客户。**
  
## <a name="troubleshooting-and-known-issues"></a>故障排除和已知问题

音频会议为音频会议提供商已被跟踪，积极调查并将在以后更新功能时可能解决当前的问题，请使用 Microsoft Office 365 的释放。
  
现在，以此作为参考当解决潜在的问题，与获取设置音频会议和为您的组织中的业务或 Microsoft 小组应用程序使用 Skype 的人工作。
  
### <a name="microsoft-teams-app"></a>Microsoft 小组应用程序

|**问题**|**行为/症状**|**已知解决方法**|**发现日期**|
|:-----|:-----|:-----|:-----|
|与"发"号码相同的 PSTN 呼叫如下所示相同用户会议名单中。  <br/> |当多 PSTN 呼叫加入会议，并且他们呼叫者 Id 被屏蔽为一个数字时，它们将显示为单个调用方会议名单中。  <br/> |无解决方法。  <br/> |于 2017 9/25 年  <br/> |
|会议信息面板不间歇地冒。  <br/> |会议信息面板可能不会显示团队客户端中当用户尝试查找会议桥的电话号码或会议 id。  <br/> |查看会议详细信息或 Outlook 日历以查看会议桥的电话号码或会议 id。  <br/> |于 2017 9/25 年  <br/> |
|从 Outlook 外接程序的会议邀请非美国区域设置的 PSTN 坐标中显示乱码。  <br/> |当使用 Outlook 外接 Microsoft 小组与非美国的区域设置的计算机上的专用会议安排、 PSTN 坐标可能包含垃圾字符。  <br/> |无解决方法。  <br/> |于 2017 9/25 年  <br/> |
|拨出需要使用 5 位数或更多。  <br/> |试图从会议拨出用户需要键入 5 或更多位数，即使提供规范化为 E.164 短数字拨号了拨号计划规范化规则。  <br/> |通过键入全部 DID 号码或本地的数字格式，而不是内部分机号码拨出。  <br/> |于 2017 9/25 年  <br/> |
|拨出控制不间歇地冒。  <br/> |拨出控件可能无法从会议信息面板可见。  <br/> |无解决方法。  <br/> |于 2017 9/25 年  <br/> |
|对于 Microsoft 小组会议不支持静态会议 ID。  <br/> |如果管理员重写默认设置动态会议 ID 静态会议 ID，此设置不会生效为 Microsoft 小组会议。 请参阅[使用音频会议动态 Id，您的组织中](using-audio-conferencing-dynamic-ids-in-your-organization.md)。  <br/> |无解决方法。  <br/> |于 2017 9/25 年  <br/> |
   
### <a name="skype-for-business-app"></a>Skype 的业务应用程序

|**问题**|**行为/症状**|**已知解决方法**|**发现日期**|
|:-----|:-----|:-----|:-----|
|进入和退出通知时开始会议，但它们正在关闭不久后打开会议开始。  <br/> |默认情况下，进入和退出的通知被禁用会议参与者加入从业务应用程序的两个 Skype 的位置，以及当它们拨入。 您可以启用**Skype 会议选项**在 Skype 的业务应用程序中的通知。 对于所有参与者拨入加入的会议，默认情况下会启用进入和退出通知，因为任何参与者都无法获得参与者名单。 当会议已开始调用条目中的参与者和退出通知将打开，但时为业务应用程序中使用 Skype 参与者联接，通知将关闭。 关闭后，可以重新使用 Skype 在业务应用程序为**Skype 会议选项**启用通知。 <br/> |无解决方法。  <br/> |于 2017 8/30 年  <br/> |
|如果用户通过赋 E5 许可证设置第一次，有可能为音频会议欢迎电子邮件未被传递到用户如果没有启用邮箱。  <br/> |如果发生这种情况，您始终可以重新发送用户业务管理中心在 Skype 使用**音频会议**或使用 PowerShell 的音频会议信息。 请参阅[启用或禁用音频会议设置更改时发送的电子邮件](enable-or-disable-sending-emails-when-their-settings-change.md)。  <br/> **注意：**为了重新发送给用户的音频会议针，针已被重置。 这也可以通过在业务管理中心为 Skype 使用**音频会议**或使用 PowerShell。          |无解决方法。  <br/> |于 2017 8/30 年  <br/> |
|音频会议呼叫可能需要 24 小时来显示使用情况报告中。  <br/> |我们期待着未来的服务更新进行该区域上的改进。  <br/> |无解决方法。  <br/> |于 2017 8/30 年  <br/> |
|当呼叫者拨入会议桥后业务用户的 Skype 已锁定会议时，没有通知中对于业务应用程序指出 Skype 用户正在等待对会议厅中。  <br/> |当前此设置是特意为之，但我们会考虑此反馈以便在未来的服务更新中支持此功能。  <br/> |无解决方法。  <br/> |于 2017 8/30 年  <br/> |
   
## <a name="related-topics"></a>相关主题

[设置音频会议 for Skype Business 和 Microsoft 团队](set-up-audio-conferencing.md)
  

