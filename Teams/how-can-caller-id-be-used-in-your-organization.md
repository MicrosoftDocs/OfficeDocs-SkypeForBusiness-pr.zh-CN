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
description: 呼叫方 ID 可以通过使用名为 CallingLineIdentity 的策略控制电话系统用户的入站和出站呼叫。
ms.openlocfilehash: af578cf92f6c19e8ac612dfe8301914c9e55833b
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836304"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a>如何在你的组织中使用来电显示

呼叫方 ID 可以通过使用名为 CallingLineIdentity 的策略控制电话系统用户的入站和出站呼叫。
  
无论 PSTN 连接如何，所有电话系统用户均可使用呼叫方 ID 功能：
  
- 在线 PSTN 连接
    
- 使用 Skype for Business Cloud Connector Edition 的内部部署 PSTN 连接（要求使用 Cloud Connector Edition 1.4.2 及更高版本）
    
- 使用 Skype for Business Server 的内部部署 PSTN 连接（要求使用 Skype for Business Server 2015 CU5 及更高版本）
    
> [!NOTE]
> [!注释] 此策略在 Skype for Business 2015 Server 上不可用。 
  
## <a name="outbound-caller-id"></a>出站来电显示

出站 PSTN 来电显示有三个对应选项：
  
- 分配给用户的电话号码（默认值）。
    
- A telephone number that is classified as a *service* and *toll-free* number in your Calling Plans in Office 365 telephone number inventory. It is usually assigned to an organizational auto attendant or call queue.
    
- 设置为匿名。
    
但你不能为出站来电显示分配以下类型的电话号码：
  
- 在您的通话计划中分类为*用户*的任何电话号码，电话号码库存
    
- Skype for Business Server 内部部署电话号码
    
要设置出站来电显示，请参见[为用户设置来电显示](/microsoftteams/set-the-caller-id-for-a-user)。
  
### <a name="end-user-control-of-outbound-caller-id"></a>出站来电显示的最终用户控制

The EnableUserOverride attribute enables single or multiple users to change their Caller ID setting to **Anonymous**. This only applies when a CallingLineIdentity policy is configured with a CallingIDSubstitute parameter of either LineURI or Substitute. The default value of EnableUserOverride is False.
  
最终用户可以使用 Skype for Business 桌面客户端中的 "**设置**" 选项卡将其来电显示设置为**匿名**，选择 "**调用最终用户**（如果由管理员启用）"，选择 "**隐藏所有呼叫的电话号码和配置文件信息**"。
  
||||
|:-----|:-----|:-----|
|**Windows** <br/> |**版本** <br/> |**支持** <br/> |
|即点即用  <br/> |2016 年 12 月 6 日发布的当前频道 - 版本 1611（内部版本 7571.2072）  <br/> |是  <br/> |
|即点即用  <br/> |2017 年 2 月 22 日发布的延期频道的首次发布 - 版本 1701（内部版本 7766.2060）  <br/> |是  <br/> |
|即点即用  <br/> |延迟通道于 2017 年 6 月 13 日发布 - 版本 1701 (Build 7766.2092)  <br/> |是  <br/> |
|MSI  <br/> |Skype for Business  <br/> |否  <br/> |
|Mac  <br/> |Skype for Business  <br/> |否  <br/> |
   
## <a name="inbound-caller-id"></a>入站来电显示

如果数字与 Azure AD 中的用户关联，则电话系统将显示为外部电话号码调用的 ID。 如果电话号码不在 Azure AD 中，则将显示通讯提供的显示名称（如果可用）。

BlockIncomingCallerID 属性可以用于阻止 PSTN 来电的来电显示。 你可以设置此属性，但你的最终用户无法在 "用户设置" 页面上使用该属性。 当前仅在使用在线 PSTN 连接时可用。
  
要设置出站来电显示，请参见[为用户设置来电显示](/microsoftteams/set-the-caller-id-for-a-user)。
  
## <a name="related-topics"></a>相关主题
[关于转移电话号码的常见问题](/microsoftteams/transferring-phone-numbers-common-questions)

[用于通话套餐的不同类型的电话号码](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[管理你的组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization)

[紧急呼叫条款和条件](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype for Business Online：紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 
