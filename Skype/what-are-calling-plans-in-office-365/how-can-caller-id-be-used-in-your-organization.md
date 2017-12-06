---
title: "如何在你的组织中使用来电显示"
ms.author: tonysmit
author: tonysmit
ms.date: 11/13/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.custom: Strat_SB_PSTN
ms.assetid: 5a0bd8ba-3334-46ee-becf-1025597737f6
description: "通过使用称为 CallingLineIdentity 策略，可以为电话系统的用户的入站和出站呼叫控制的呼叫者 ID。"
---

# 如何在你的组织中使用来电显示

> [!重要信息]
> 本文是由机器翻译的，请参阅[免责声明](5a0bd8ba-3334-46ee-becf-1025597737f6.md#MT_Footer)。请在 [此处](https://support.office.com/en-us/article/5a0bd8ba-3334-46ee-becf-1025597737f6) 中查找本文的英文版本以便参考。
  
通过使用称为 CallingLineIdentity 策略，可以为电话系统的用户的入站和出站呼叫控制的呼叫者 ID。
  
呼叫方 ID 功能可用于所有电话系统的用户，无论 PSTN 连接：
  
- 在线 PSTN 连接
    
- 使用 Skype for Business Cloud Connector Edition 的内部部署 PSTN 连接（要求使用 Cloud Connector Edition 1.4.2 及更高版本）
    
- 使用 Skype for Business Server 的内部部署 PSTN 连接（要求使用 Skype for Business Server 2015 CU5 及更高版本）
    
> [!注释]
> 此策略在 Skype for Business 2015 Server 上不可用。 
  
## 出站来电显示

出站 PSTN 来电显示有三个对应选项：
  
- 分配给用户，这是默认电话号码。
    
- 划分为一项 *服务*  的电话号码和 *免费电话*  号码，您调用计划在 Office 365 电话中的数字库存。通常，它被分配给组织的自动助理或呼叫队列。
    
- 设置为匿名。
    
但你不能为出站来电显示分配以下类型的电话号码：
  
- 划分为调用计划通过电话 *用户*  的任何电话号码的数字库存
    
- Skype for Business Server 内部部署电话号码
    
要设置出站来电显示，请参见[为用户设置来电显示](set-the-caller-id-for-a-user.md)。
  
### 出站来电显示的最终用户控制

EnableUserOverride 属性允许将其呼叫者 ID 设置更改为 **匿名**单个或多个用户。这仅适用于 CallingLineIdentity 策略配置 CallingIDSubstitute 参数为 LineURI 或替代。EnableUserOverride 的默认值为 False。
  
最终用户可以通过使用 Skype for Business 桌面客户端的 **呼叫转接设置**选项卡，为 **匿名**设置其呼叫者 ID。
  
||||
|:-----|:-----|:-----|
|**Windows** <br/> |**版本** <br/> |**支持** <br/> |
|即点即用  <br/> |2016 年 12 月 6 日发布的当前频道 - 版本 1611（内部版本 7571.2072）  <br/> |是  <br/> |
|即点即用  <br/> |2017 年 2 月 22 日发布的延期频道的首次发布 - 版本 1701（内部版本 7766.2060）  <br/> |是  <br/> |
|即点即用  <br/> |推迟发布 2017-6 月 13，版本 1701 (构建 7766.2092) 的通道  <br/> |是  <br/> |
|MSI  <br/> |Skype for Business  <br/> |否  <br/> |
|Mac  <br/> |Skype for Business  <br/> |否  <br/> |
   
你的最终用户还可以在用户设置页面上设置其来电显示设置，网址为：[https://mysettings.lync.com/pstncalling](https://mysettings.lync.com/pstncalling)。
  
## 入站来电显示

BlockIncomingCallerID 属性允许阻止传入 PSTN 呼叫的呼叫者 ID。您可以设置此属性，但它不适用于您在用户设置页面上的最终用户。并且当前仅联机 PSTN 连接中可用。
  
要设置出站来电显示，请参见[为用户设置来电显示](set-the-caller-id-for-a-user.md)。
  
## 
<a name="MT_Footer"> </a>

> [!注释]
> **机器翻译免责声明**：本文是由无人工介入的计算机系统翻译的。Microsoft 提供机器翻译是为了帮助非英语国家/地区用户方便阅读有关 Microsoft 产品、服务和技术的内容。由于机器翻译的原因，本文可能包含词汇、语法或文法方面的错误。 
  
## 另请参阅
<a name="MT_Footer"> </a>

#### 其他资源

[紧急呼叫条款和条件](emergency-calling-terms-and-conditions.md)
  
[音频会议免费拨出时间段](../accessibility-and-regulatory/audio-conferencing-complimentary-dial-out-period.md)
  
[Skype for Business 和 Microsoft 团队许可加载项](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)

