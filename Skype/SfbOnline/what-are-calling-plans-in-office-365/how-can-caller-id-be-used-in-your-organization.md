---
title: 如何在你的组织中使用来电显示
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: 5a0bd8ba-3334-46ee-becf-1025597737f6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Calling Plans
description: 呼叫者 ID 可以通过使用名为 CallingLineIdentity 策略控制的电话系统的用户的入站和出站呼叫。
ms.openlocfilehash: a1a809805b96152e4b205c8f38b3c8409014eb55
ms.sourcegitcommit: 2c084358844f02fbf7953f2ea49ed6d710cbf06f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2018
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a>如何在你的组织中使用来电显示

呼叫者 ID 可以通过使用名为 CallingLineIdentity 策略控制的电话系统的用户的入站和出站呼叫。
  
呼叫者 ID 功能，无论 PSTN 连接的所有电话系统用户：
  
- 在线 PSTN 连接
    
- 使用 Skype for Business Cloud Connector Edition 的内部部署 PSTN 连接（要求使用 Cloud Connector Edition 1.4.2 及更高版本）
    
- 使用 Skype for Business Server 的内部部署 PSTN 连接（要求使用 Skype for Business Server 2015 CU5 及更高版本）
    
> [!NOTE]
> [!注释] 此策略在 Skype for Business 2015 Server 上不可用。 
  
## <a name="outbound-caller-id"></a>出站来电显示

出站 PSTN 来电显示有三个对应选项：
  
- 分配给用户，这是默认电话号码。
    
- 作为*服务*分类的电话号码和*免费电话*号码在您调用计划在 Office 365 电话号码库存。 它通常分配给组织的自动助理或呼叫的队列。
    
- 设置为匿名。
    
但你不能为出站来电显示分配以下类型的电话号码：
  
- 任何电话号码分类为*用户*在您调用计划的电话号码库存
    
- Skype for Business Server 内部部署电话号码
    
要设置出站来电显示，请参见[为用户设置来电显示](set-the-caller-id-for-a-user.md)。
  
### <a name="end-user-control-of-outbound-caller-id"></a>出站来电显示的最终用户控制

EnableUserOverride 属性，单个或多个用户，可以将其呼叫者 ID 设置更改为**匿名**。 这仅适用于 CallingLineIdentity 策略配置 LineURI 或替代 CallingIDSubstitute 参数。 EnableUserOverride 的默认值为 False。
  
最终用户可以使用 for Business 桌面客户端的 Skype 中的**呼叫转接设置**选项卡将其呼叫者 ID 设置为**匿名**。
  
||||
|:-----|:-----|:-----|
|**Windows** <br/> |**版本** <br/> |**支持** <br/> |
|即点即用  <br/> |2016 年 12 月 6 日发布的当前频道 - 版本 1611（内部版本 7571.2072）  <br/> |是  <br/> |
|即点即用  <br/> |2017 年 2 月 22 日发布的延期频道的首次发布 - 版本 1701（内部版本 7766.2060）  <br/> |是  <br/> |
|即点即用  <br/> |延迟通道发布 2017 年 6 月 13，-版本 1701 (生成 7766.2092)  <br/> |是  <br/> |
|MSI  <br/> |Skype for Business  <br/> |否  <br/> |
|Mac  <br/> |Skype for Business  <br/> |否  <br/> |
   
## <a name="inbound-caller-id"></a>入站来电显示

BlockIncomingCallerID 属性允许阻止上传入 PSTN 呼叫的呼叫者 ID。 您可以设置此属性，而只是向最终用户在用户设置页上可用。 当前仅在使用在线 PSTN 连接时可用。
  
要设置出站来电显示，请参见[为用户设置来电显示](set-the-caller-id-for-a-user.md)。
  
## <a name="related-topics"></a>相关主题
[关于转移电话号码的常见问题](transferring-phone-numbers-common-questions.md)

[用于通话套餐的不同类型的电话号码](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[管理你的组织的电话号码](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[紧急呼叫条款和条件](../legal-and-regulatory/emergency-calling-terms-and-conditions.md)

[Skype for Business Online：紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 