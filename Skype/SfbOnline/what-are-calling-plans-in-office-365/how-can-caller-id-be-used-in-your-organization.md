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
search.appverid: MET150
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
description: 可以通过使用名为 CallingLineIdentity 的策略来控制电话系统用户的入站和出站呼叫的来电显示。
ms.openlocfilehash: 410712a8fd0a6f28b0bc2821daae8143b38ceb63
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23854222"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a>如何在你的组织中使用来电显示

可以通过使用名为 CallingLineIdentity 的策略来控制电话系统用户的入站和出站呼叫的来电显示。
  
来电显示功能对所有电话系统用户都适用，而不考虑 PSTN 连接：
  
- 在线 PSTN 连接
    
- 使用 Skype for Business Cloud Connector Edition 的内部部署 PSTN 连接（要求使用 Cloud Connector Edition 1.4.2 及更高版本）
    
- 使用 Skype for Business Server 的内部部署 PSTN 连接（要求使用 Skype for Business Server 2015 CU5 及更高版本）
    
> [!NOTE]
> [!注释] 此策略在 Skype for Business 2015 Server 上不可用。 
  
## <a name="outbound-caller-id"></a>出站来电显示

出站 PSTN 来电显示有三个对应选项：
  
- 分配给用户的电话号码，这是默认设置。
    
- 在您的 Office 365 电话号码库存通话套餐中分类为*服务*和*免费电话*的电话号码。 它通常分配给组织的自动助理或呼叫队列。
    
- 设置为匿名。
    
但你不能为出站来电显示分配以下类型的电话号码：
  
- 在你的通话套餐电话号码库存中分类为*用户*的任何电话号码
    
- Skype for Business Server 内部部署电话号码
    
要设置出站来电显示，请参见[为用户设置来电显示](set-the-caller-id-for-a-user.md)。
  
### <a name="end-user-control-of-outbound-caller-id"></a>出站来电显示的最终用户控制

EnableUserOverride 属性使单一用户或多个用户可以将其来电显示设置更改为**匿名**。 这仅在用 LineURI 或 Substitute 等 CallingIDSubstitute 参数配置 CallingLineIdentity 策略时才适用。 EnableUserOverride 的默认值是 False。
  
你的最终用户可以使用 Skype for Business 桌面客户端中的**呼叫转移设置**选项卡将其来电显示设置为**匿名**。
  
||||
|:-----|:-----|:-----|
|**Windows** <br/> |**版本** <br/> |**支持** <br/> |
|即点即用  <br/> |2016 年 12 月 6 日发布的当前频道 - 版本 1611（内部版本 7571.2072）  <br/> |是  <br/> |
|即点即用  <br/> |2017 年 2 月 22 日发布的延期频道的首次发布 - 版本 1701（内部版本 7766.2060）  <br/> |是  <br/> |
|即点即用  <br/> |延迟通道于 2017 年 6 月 13 日发布 - 版本 1701 (Build 7766.2092)  <br/> |是  <br/> |
|MSI  <br/> |Skype for Business  <br/> |否  <br/> |
|Mac  <br/> |Skype for Business  <br/> |否  <br/> |
   
## <a name="inbound-caller-id"></a>入站来电显示

BlockIncomingCallerID 属性可以用于阻止传入 PSTN 呼叫的来电显示。 你可以设置此属性，但这不适用于用户设置页面上的你的最终用户。 当前只适用于在线 PSTN 连接。
  
要设置出站来电显示，请参见[为用户设置来电显示](set-the-caller-id-for-a-user.md)。
  
## <a name="related-topics"></a>相关主题
[关于转移电话号码的常见问题](/microsoftteams/transferring-phone-numbers-common-questions)

[用于通话套餐的不同类型的电话号码](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[管理你的组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization)

[紧急呼叫条款和条件](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype for Business Online：紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 