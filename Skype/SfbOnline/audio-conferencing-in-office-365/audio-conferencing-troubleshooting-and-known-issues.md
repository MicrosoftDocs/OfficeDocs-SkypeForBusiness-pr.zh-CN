---
title: 音频会议故障排除和已知问题
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 72979911-5319-4de2-a275-4dd9a0f44fe6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: '使用 Microsoft 作为其电话拨入式会议提供程序、 状态和一些解决方法时，请获取已知问题的列表。 '
ms.openlocfilehash: e5c6144081eb68426d3be53efb0ac9e9acbf41bd
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23887458"
---
# <a name="audio-conferencing-troubleshooting-and-known-issues"></a>音频会议故障排除和已知问题

 **本文是 Skype 业务和 Microsoft 团队使用 Microsoft 作为其音频会议提供商的用户。不适用于于使用第三方音频会议提供商 (ACP) 的客户。**
  
## <a name="troubleshooting-and-known-issues"></a>疑难解答和已知问题

使用 Microsoft 的音频会议提供程序具有当前是正在跟踪，主动调查，会在未来更新功能时可能会解决的问题的音频会议的 Office 365 版本。
  
现在时, 使用此参考解决潜在问题获取音频会议设置和使用您的组织中的业务或 Microsoft 团队应用程序的 Skype 的人员的工作。
  
### <a name="microsoft-teams-app"></a>Microsoft 团队应用程序

|**问题**|**行为/症状**|**已知解决方法**|**发现日期**|
|:-----|:-----|:-----|:-----|
|与"从"数相同的 PSTN 呼叫者显示同一用户在会议名单中。  <br/> |当多个 PSTN 呼叫者加入会议，并将屏蔽为一个数字，其呼叫者 Id 时，它们将显示为单个呼叫者在会议名单中。  <br/> |无解决方法。  <br/> |9/25/2017  <br/> |
|会议信息面板未显示间歇性。  <br/> |会议信息面板可能不显示团队客户端中当用户试图查找的会议桥接电话号码或会议 id。  <br/> |查看会议详细信息或 Outlook 日历，若要查看会议桥接电话号码或会议 id。  <br/> |9/25/2017  <br/> |
|从 Outlook 外接程序的会议邀请中 PSTN 坐标非美国的区域设置显示乱码。  <br/> |当使用 Outlook 外接程序的 Microsoft 团队非美国的区域设置的计算机上的专用会议安排、 PSTN 坐标可能包含垃圾字符。  <br/> |无解决方法。  <br/> |9/25/2017  <br/> |
|拨出需要使用 5 位数字或的详细信息。  <br/> |尝试从会议发起电话拨出的用户需要键入 5 个或多个数字，即使拨号计划的规范化规则是可用于规范化为 E.164 的简短数字拨号。  <br/> |通过键入以下内容，而不是内部分机号的当地号码格式的完整 DID 号码拨出。  <br/> |9/25/2017  <br/> |
|拨出控件未显示间歇性。  <br/> |拨出控件可能无法看到从会议信息面板。  <br/> |无解决方法。  <br/> |9/25/2017  <br/> |
|不支持的 Microsoft 团队会议的静态会议 ID。  <br/> |如果管理员重写为静态会议 ID 从动态的会议 ID 的默认设置，则此设置才会生效的 Microsoft 团队会议。 请参阅[您的组织中使用音频会议动态 Id](using-audio-conferencing-dynamic-ids-in-your-organization.md)。  <br/> |无解决方法。  <br/> |9/25/2017  <br/> |
|PSTN 会议坐标不能用于 Skype 业务内部部署用户  <br/> |如果用户是业务内部部署用户，指定与 Skype 的业务联机、 音频会议和团队许可证 Skype 计划使用团队的所有会议将不包括 PSTN 会议坐标。 <br/> |无解决方法。  <br/> |2/1/2018  <br/> |
   
### <a name="skype-for-business-app"></a>Skype 业务应用程序

|**问题**|**行为/症状**|**已知解决方法**|**发现日期**|
|:-----|:-----|:-----|:-----|
|进入和退出通知时启动会议，但他们正在关闭不久后打开在会议开始。  <br/> |默认情况下，其中两个 Skype 业务应用程序中的参与者加入和时拨入时进入和退出通知的会议中禁用。 您可以在**Skype 会议选项**中的企业应用程序 Skype 通知。 对于所有参与者拨入加入的会议，默认情况下会启用进入和退出通知，因为任何参与者都无法获得参与者名单。 当会议已开始仅调用条目中的参与者和退出通知将打开，但时为业务应用程序使用 Skype 参与者加入，通知将关闭。 关闭时，可以在 Skype 后使用**Skype 会议选项**，业务应用程序启用通知。 <br/> |无解决方法。  <br/> |8/30/2017  <br/> |
|如果用户已由其分配一个 E5 许可证设置第一次、，有可能为音频会议欢迎电子邮件未传送到用户如果没有启用邮箱。  <br/> |如果发生这种情况，始终可以重新发送业务管理中心的 Skype 中使用**音频会议**或使用 PowerShell 的用户的音频会议信息。 请参阅[启用或禁用发送电子邮件时要进行音频会议设置更改](enable-or-disable-sending-emails-when-their-settings-change.md)。  <br/> **注意：** 若要重新发送给用户的音频会议 PIN，PIN 具有要重置。 这也可以通过在业务管理中心的 Skype 中使用**音频会议**或通过使用 PowerShell。          |无解决方法。  <br/> |8/30/2017  <br/> |
|音频会议呼叫可能需要 24 小时的使用率报告中显示。  <br/> |我们期待于在将来的服务更新，以使在这方面的改进。  <br/> |无解决方法。  <br/> |8/30/2017  <br/> |
|当呼叫者拨入的会议桥业务用户 Skype 已锁定会议后时，没有的通知中的业务应用程序指出 Skype 等待用户对会议厅中。  <br/> |当前此设置是特意为之，但我们会考虑此反馈以便在未来的服务更新中支持此功能。  <br/> |无解决方法。  <br/> |8/30/2017  <br/> |
   
## <a name="related-topics"></a>相关主题

[试用或购买 Office 365 中的音频会议](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
