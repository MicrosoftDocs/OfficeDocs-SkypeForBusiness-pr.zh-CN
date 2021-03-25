---
title: 如何在你的组织中使用来电显示
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: 5a0bd8ba-3334-46ee-becf-1025597737f6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- ms.teamsadmincenter.voice.callerid.overview
description: 可以使用名为 CallingLineIdentity 的策略控制电话系统用户的入站和出站呼叫的来电显示。
ms.openlocfilehash: e723311b2780dd1d43bad4874b72133e09ff4fc3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120673"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a>如何在你的组织中使用来电显示

可以使用名为 CallingLineIdentity 的策略控制电话系统用户的入站和出站呼叫的来电显示。
  
无论 PSTN 连接如何，呼叫方 ID 功能都可供所有电话系统用户使用：

- Microsoft 通话套餐 

- 电话系统直接路由 
  
- 在线 PSTN 连接
    
- 使用 Skype for Business Cloud Connector Edition 的内部部署 PSTN 连接（要求使用 Cloud Connector Edition 1.4.2 及更高版本）
    
- 使用 Skype for Business Server 的内部部署 PSTN 连接（要求使用 Skype for Business Server 2015 CU5 及更高版本）
    
> [!NOTE]
> [!注释] 此策略在 Skype for Business 2015 Server 上不可用。 
  
## <a name="outbound-caller-id"></a>出站来电显示

出站 PSTN 呼叫者 ID 有三个选项可用：
  
- 分配给用户的电话号码，这是默认设置。
    
- 在"呼叫计划"电话号码清单中分类为服务和免费电话号码的电话号码。 它通常分配给组织的自动助理或呼叫队列。
    
- 设置为匿名。
    
但你不能为出站来电显示分配以下类型的电话号码：
  
- 在"呼叫计划"电话号码清单  *中分类*  为用户的任何电话号码
    
- Skype for Business Server 内部部署电话号码
    
要设置出站来电显示，请参见[为用户设置来电显示](./set-the-caller-id-for-a-user.md)。
  
### <a name="end-user-control-of-outbound-caller-id"></a>出站来电显示最终用户控制

EnableUserOverride 属性允许单个或多个用户将呼叫者 ID 设置更改为 **匿名**。 仅当 CallingLineIdentity 策略配置了 CallingIDSubstitute 参数 LineURI 或 Substitute 时适用。 EnableUserOverride 的默认值是 False。
  
最终用户可以使用 Skype for Business桌面客户端中的"设置"选项卡将其来电显示设置为"匿名"，选择"呼叫最终用户 **("（** 如果管理员) 已启用），然后选择"隐藏我的电话号码和个人资料信息"作为所有 **呼叫**。 在 Teams 中，用户可以转到右上角的个人资料图片，选择"设置呼叫"，然后在"来电显示"下，选择"隐藏我的电话号码和个人资料信息"作为所有  >  **呼叫。** 
  
||||
|:-----|:-----|:-----|
|**Windows** <br/> |**版本** <br/> |**支持** <br/> |
|即点即用  <br/> |2016 年 12 月 6 日发布的当前频道 - 版本 1611（内部版本 7571.2072）  <br/> |是  <br/> |
|即点即用  <br/> |2017 年 2 月 22 日发布的延期频道的首次发布 - 版本 1701（内部版本 7766.2060）  <br/> |是  <br/> |
|即点即用  <br/> |延迟通道于 2017 年 6 月 13 日发布 - 版本 1701 (Build 7766.2092)  <br/> |是  <br/> |
|MSI  <br/> |Skype for Business  <br/> |否  <br/> |
|Mac  <br/> |Skype for Business  <br/> |否  <br/> |
   
## <a name="inbound-caller-id"></a>入站来电显示

如果外部电话号码与 Azure AD 中的用户关联，电话系统将显示外部电话号码的已调用 ID。 如果电话号码不在 Azure AD 中，则会显示显示名称提供的电话号码（如果可用）。

BlockIncomingCallerID 属性可以用于阻止 PSTN 来电的来电显示。 可以设置此属性，但它在用户设置页上对最终用户不可用。 当前仅在使用在线 PSTN 连接时可用。
  
要设置出站来电显示，请参见[为用户设置来电显示](./set-the-caller-id-for-a-user.md)。
  
## <a name="related-topics"></a>相关主题
[关于转移电话号码的常见问题](./phone-number-calling-plans/port-order-overview.md)

[用于通话套餐的不同类型的电话号码](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[管理你的组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization)

[紧急呼叫条款和条件](./emergency-calling-terms-and-conditions.md)

[Skype for Business Online：紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
