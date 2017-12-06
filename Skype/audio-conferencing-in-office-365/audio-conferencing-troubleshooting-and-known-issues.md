---
title: "音频会议疑难解答和已知的问题"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/9/2017
ms.audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
ms.assetid: 72979911-5319-4de2-a275-4dd9a0f44fe6

description: "Get a list of known isses when using Microsoft as their dial-in conference provider, status, and some work arounds. "
---

# 音频会议疑难解答和已知的问题

> [!重要信息]
> 本文是由机器翻译的，请参阅[免责声明](72979911-5319-4de2-a275-4dd9a0f44fe6.md#MT_Footer)。请在 [此处](https://support.office.com/en-us/article/72979911-5319-4de2-a275-4dd9a0f44fe6) 中查找本文的英文版本以便参考。
  
 **本文是 for Skype Business 和 Microsoft 团队用户使用 Microsoft 作为其音频会议提供商。它不适用于客户在使用第三方音频会议提供商 (ACP)。**
  
## 疑难解答和已知问题

使用 Microsoft 与音频会议提供商具有当前正在跟踪，频繁调查并将该功能在将来更新时可能解决的问题的音频会议的 Office 365 版本。
  
现在，以此作为引用进行故障排除获取音频会议设置，然后使用您的组织中的业务或 Microsoft 小组应用 Skype 的人员的工作的潜在问题时。
  
### Microsoft 小组应用程序

|**问题**|**行为中的症状**|**已知解决方法**|**发现日期**|
|:-----|:-----|:-----|:-----|
|使用"发件人"号码相同的 PSTN 呼叫者如下所示相同用户在会议名单中。  <br/> |当多个 PSTN 呼叫者加入会议，并将屏蔽为一个数字，其呼叫者 Id 时，它们将显示为单个呼叫者在会议花名册中。  <br/> |暂无解决方法。  <br/> |2017-9/25  <br/> |
|会议信息面板不会间歇性地出来。  <br/> |会议信息面板可能不会显示在团队客户端中当用户尝试查找会议网桥电话号码或会议 id。  <br/> |查看会议详细信息或 Outlook 日历以查看会议网桥电话号码或会议 id。  <br/> |2017-9/25  <br/> |
|从 Outlook 加载项的会议邀请中的非美国区域设置的 PSTN 坐标显示垃圾字符。  <br/> |计划使用 Outlook 加载项 for Microsoft 小组与非美国区域设置的计算机上的专用会议，PSTN 坐标可能包含垃圾字符。  <br/> |暂无解决方法。  <br/> |2017-9/25  <br/> |
|拨出需要使用 5 位或更多位。  <br/> |用户尝试从会议拨出需要键入 5 个或多个数字，即使拨号计划规范化规则是可规范化 E.164 拨简短的数字。  <br/> |通过键入完整的 DID 数字或本地的数字格式，而不是内部分机号码拨出。  <br/> |2017-9/25  <br/> |
|拨出控件不会间歇性地出来。  <br/> |拨出控件可能不会从会议信息面板。  <br/> |暂无解决方法。  <br/> |2017-9/25  <br/> |
|不支持的 Microsoft 小组会议的静态会议 ID。  <br/> |如果管理员重写到静态会议 ID 动态会议 ID 的默认设置，此设置才会 Microsoft 小组会议的效果。请参阅[在您的组织中使用音频会议动态 Id](using-audio-conferencing-dynamic-ids-in-your-organization.md)。  <br/> |暂无解决方法。  <br/> |2017-9/25  <br/> |
   
### Skype for Business 应用程序

|**问题**|**行为中的症状**|**已知解决方法**|**发现日期**|
|:-----|:-----|:-----|:-----|
|进入和退出通知时启动会议，但它们关闭不久之后打开会议开始。  <br/> |默认情况下，从两个 Skype for Business 应用程序加入的参与者的位置和拨入时时进入和退出通知的会议中禁用。您可以启用 Skype for Business 应用程序中的 **Skype 会议选项**中的公告。会议拨入所有参与者的位置，并加入会议，为参与者名单不可用到任何参与者进入和退出通知默认中启用。当会议已开始调用条目中的参与者和退出通知将打开，但时使用 Skype for Business 应用参与者联接，通知将关闭。关闭时，可以重新使用 Skype 会议中的 **选项 Skype** for Business 应用程序启用通知。 <br/> |暂无解决方法。  <br/> |2017-8/30  <br/> |
|如果用户通过分配 E5 许可证设置第一次，有可能音频会议欢迎电子邮件无法发送给用户如果邮箱未启用。  <br/> |如果发生这种情况，您始终可以重新发送在 Skype for Business 管理中心中使用 **音频会议**或使用 PowerShell 的用户的音频会议信息。请参阅[启用或禁用发送电子邮件时更改音频会议设置](enable-or-disable-sending-emails-when-audio-conferencing-settings-change.md)。  <br/> > [!注释]> 为了重新发送给用户的音频会议的 PIN，请必须重置 PIN。这也可以通过在 Skype for Business 管理中心中使用 **音频会议**或使用 PowerShell。           |暂无解决方法。  <br/> |2017-8/30  <br/> |
|音频会议呼叫可能需要多达 24 小时，以显示在使用率报告中。  <br/> |我们正在转发到进行改进，在此区域在将来的服务更新中。  <br/> |暂无解决方法。  <br/> |2017-8/30  <br/> |
|当呼叫者拨入会议网桥会议已锁定Skype for Business用户之后时，没有通知中Skype for Business应用表明用户正在等待大厅中。  <br/> |当前此设置是特意为之，但我们会考虑此反馈以便在未来的服务更新中支持此功能。  <br/> |暂无解决方法。  <br/> |2017-8/30  <br/> |
   
## 相关主题

[设置音频会议 for Skype Business 和 Microsoft 团队](set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams.md)
  
## 
<a name="MT_Footer"> </a>

> [!注释]
> **机器翻译免责声明**：本文是由无人工介入的计算机系统翻译的。Microsoft 提供机器翻译是为了帮助非英语国家/地区用户方便阅读有关 Microsoft 产品、服务和技术的内容。由于机器翻译的原因，本文可能包含词汇、语法或文法方面的错误。 
  

