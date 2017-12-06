---
title: "致电计划的已知的问题"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/14/2017
ms.audience: Admin
ms.topic: troubleshooting
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom: Adm_O365_FullSet
ms.assetid: baa3645a-0518-472e-942e-971c63ba4ca0

description: "Learn known issues with the calling plan for Office 365 (PSTN Calling) and what you can do about them. "
---

# 致电计划的已知的问题

> [!重要信息]
> 本文是由机器翻译的，请参阅[免责声明](baa3645a-0518-472e-942e-971c63ba4ca0.md#MT_Footer)。请在 [此处](https://support.office.com/en-us/article/baa3645a-0518-472e-942e-971c63ba4ca0) 中查找本文的英文版本以便参考。
  
在 Office 365 中的呼叫计划是在Skype for Business Online中找到的新增功能。下面是当前正在的问题跟踪，频繁调查。他们将可能解决更新在 Office 365 和Skype for Business Online未来版本中的功能时。
  
## 致电计划的已知的问题

|**已知问题**|**注释**|
|:-----|:-----|
|从技术预览转换许可证分配给生产许可证调用计划不自动更新许可证。  <br/> |第一次购买新许可证，以便他们已准备好要分配给您的用户。促销 （技术预览版） 许可证中删除用户，并 **立即** 将新 **计划调用国内**和/或 **国际呼叫计划**许可证给用户。  <br/> 如果您是删除，并且添加多个用户的许可证，一点非常重要，从的所有用户使用 Windows PowerShell 中都删除许可证，然后 **立即** 将分配的所有用户也在使用 Windows PowerShell 的许可证。执行此操作将确保有服务不会中断时处理大量的用户许可证分配。示例 PowerShell 脚本，请参阅[分配 Skype for Business 和 Microsoft 团队合作的用户许可证](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。  <br/> > [!注释]> 如果您使用混合用户本地 PSTN 连接，您 *只*  需要分配 **电话系统**许可证。 **不** 应也分配语音呼叫计划。> 但是，如果您已经启用了致电 Office 365 中计划是 Office 365 中的用户，您需要仍分配 **国内调用规划**和/或 **国际呼叫计划**为这些用户许可证。请参阅[分配 Skype for Business 和 Microsoft 团队合作的用户许可证](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。           |
   
## 相关主题

[紧急呼叫条款和条件](emergency-calling-terms-and-conditions.md)
  
[音频会议免费拨出时间段](../accessibility-and-regulatory/audio-conferencing-complimentary-dial-out-period.md)
  
## 
<a name="MT_Footer"> </a>

> [!注释]
> **机器翻译免责声明**：本文是由无人工介入的计算机系统翻译的。Microsoft 提供机器翻译是为了帮助非英语国家/地区用户方便阅读有关 Microsoft 产品、服务和技术的内容。由于机器翻译的原因，本文可能包含词汇、语法或文法方面的错误。 
  

