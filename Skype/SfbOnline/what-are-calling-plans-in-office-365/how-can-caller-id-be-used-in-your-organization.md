---
title: 如何在你的组织中使用来电显示
author: CarolynRowe
ms.author: crowe
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
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: 呼叫者 ID 可以通过使用名为 CallingLineIdentity 策略控制的电话系统的用户的入站和出站呼叫。
ms.openlocfilehash: df6c7c053b5dce4ffb1d121a1adbf829efda9943
ms.sourcegitcommit: 60e8365281ec6d780f1b2439bedef0bd71f002d8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2019
ms.locfileid: "30047894"
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
    
- 在您的 Office 365 电话号码库存通话套餐中分类为*服务*和*免费电话*的电话号码。 它通常分配给组织的自动助理或呼叫队列。
    
- 设置为匿名。
    
但你不能为出站来电显示分配以下类型的电话号码：
  
- 任何电话号码分类为*用户*在您调用计划的电话号码库存
    
- Skype for Business Server 内部部署电话号码
    
要设置出站来电显示，请参见[为用户设置来电显示](set-the-caller-id-for-a-user.md)。
  
### <a name="end-user-control-of-outbound-caller-id"></a>出站来电显示的最终用户控制

通过 EnableUserOverride 属性，单个用户或多个用户可以将其"来电显示"设置更改为" **匿名**"。 仅当 CallingLineIdentity 策略配置了 CallingIDSubstitute 参数 LineURI 或 Substitute 时适用。 EnableUserOverride 的默认值是 False。
  
最终用户可以通过使用 for Business 桌面客户端的 Skype 中的**设置**选项卡将其呼叫者 ID 设置为**匿名**，选择**呼叫最终用户**（如果由管理员启用），选择所有呼叫的**隐藏我的电话号码和配置文件信息**.
  
||||
|:-----|:-----|:-----|
|**Windows** <br/> |**版本** <br/> |**支持** <br/> |
|即点即用  <br/> |2016 年 12 月 6 日发布的当前频道 - 版本 1611（内部版本 7571.2072）  <br/> |是  <br/> |
|即点即用  <br/> |2017 年 2 月 22 日发布的延期频道的首次发布 - 版本 1701（内部版本 7766.2060）  <br/> |是  <br/> |
|即点即用  <br/> |延迟通道于 2017 年 6 月 13 日发布 - 版本 1701 (Build 7766.2092)  <br/> |是  <br/> |
|MSI  <br/> |Skype for Business  <br/> |否  <br/> |
|Mac  <br/> |Skype for Business  <br/> |否  <br/> |
   
## <a name="inbound-caller-id"></a>入站来电显示

BlockIncomingCallerID 属性可以用于阻止 PSTN 来电的来电显示。 您可以设置此属性，而只是向最终用户在用户设置页上可用。 当前仅在使用在线 PSTN 连接时可用。
  
要设置出站来电显示，请参见[为用户设置来电显示](set-the-caller-id-for-a-user.md)。
  
## <a name="related-topics"></a>相关主题
[关于转移电话号码的常见问题](/microsoftteams/transferring-phone-numbers-common-questions)

[用于通话套餐的不同类型的电话号码](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[管理你的组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization)

[紧急呼叫条款和条件](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype for Business Online：紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 
