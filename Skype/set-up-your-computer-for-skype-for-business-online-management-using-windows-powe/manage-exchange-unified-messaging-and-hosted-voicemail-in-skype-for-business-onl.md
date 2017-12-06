---
title: "管理 Exchange 统一消息和托管语音邮件在 Skype for Business Online"
ms.author: tonysmit
author: tonysmit
ms.date: 5/18/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.assetid: 707198df-df85-4833-9c15-aa29b71f085c

description: "Use PowerShell to manage Exchange Unified Messaging capabilities such as Auto Attendant and Subscriber Access and hosted voicemail in Skype for Business Online."
---

# 管理 Exchange 统一消息和托管语音邮件在 Skype for Business Online

> [!IMPORTANT]
> 本文是由机器翻译的，请参阅[免责声明](707198df-df85-4833-9c15-aa29b71f085c.md#MT_Footer)。请在 [此处](https://support.office.com/en-us/article/707198df-df85-4833-9c15-aa29b71f085c) 中查找本文的英文版本以便参考。
  
您可以管理Exchange统一消息和中使用一组 cmdlet Skype for Business Online托管语音邮件。
  
## 管理 Exchange 统一消息和托管语音邮件

以下 cmdlet 可用于管理Exchange统一消息 (UM) 和托管的语音邮件策略︰
  
|**Cmdlet**|**说明**|
|:-----|:-----|
|[获取 CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849628) <br/> [新 CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849629) <br/> [删除 CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849630) <br/> [设置 CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849631) <br/> |创建和管理托管的服务Exchange UM 时用于自动助理和订阅者访问服务的联系人对象。  <br/> Skype for Business Online处理Exchange UM 提供多种语音相关的功能，包括自动助理和订阅者访问。自动助理地为呼叫进行自动回答和路由到正确的联系人。订阅者访问使用户能够连接到Exchange UM 并检索电子邮件、 语音邮件、 联系人和日历信息。  <br/> 当作为托管服务提供Exchange UM 时，必须使用Microsoft PowerShell创建用于自动助理和订阅者访问服务的联系人对象。创建和使用 **CsExUmContact** cmdlet 管理这些对象。 <br/> |
|[获取 CSHostedVoicemailPolicy](https://go.microsoft.com/fwlink/p/?linkid=849633) <br/> [授予 CSHostedVoicemailPolicy](https://go.microsoft.com/fwlink/p/?linkid=849602) <br/> |管理组织中使用托管的语音邮件策略。托管的语音邮件策略指定如何未应答的呼叫将被传送到Exchange UM 服务。已为Exchange UM 启用这些策略影响只有用户托管语音邮件。  <br/> 要验证用户是否启用了托管的语音邮件，请运行PowerShell提示从类似于以下命令。  <br/> ```Get-CsOnlineUser -Identity "kenmyer@litwareinc.com" | Select-Object HostedVoiceMail```|
   
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **机器翻译免责声明**：本文是由无人工介入的计算机系统翻译的。Microsoft 提供机器翻译是为了帮助非英语国家/地区用户方便阅读有关 Microsoft 产品、服务和技术的内容。由于机器翻译的原因，本文可能包含词汇、语法或文法方面的错误。 
  

