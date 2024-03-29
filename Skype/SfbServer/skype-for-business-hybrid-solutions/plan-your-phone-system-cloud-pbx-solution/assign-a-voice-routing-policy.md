---
title: 分配语音路由策略
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: c7f78f23-b74f-402f-bedb-4cc308718f5b
description: 摘要：阅读本主题，了解如何为使用本地 PSTN 连接电话系统用户分配语音策略。
ms.openlocfilehash: 158cd8e7bcd996297077adfb2c812febf4dc491b
ms.sourcegitcommit: b0bb7db41856ee377dbe4ca8c9dff56385bf120d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2021
ms.locfileid: "61563353"
---
# <a name="assign-a-voice-routing-policy"></a>分配语音路由策略
 
> [!Important]
> Skype for Business Online 于 2021 年 7 月 31 日停用，并且本地环境（无论是通过 Skype for Business Server 还是云连接器版本与 Skype for Business Online）之间的 PSTN 连接不再受支持。  了解如何使用直接路由将本地电话网络Teams[到呼叫。](/MicrosoftTeams/direct-routing-landing-page)

**摘要：** 阅读本主题，了解如何为使用本地 PSTN 连接电话系统用户分配语音策略。 
  
一旦用户Skype for Business联机，电话系统本地 PSTN 连接使用语音，则两个语音策略将应用于他们。 一种是您将在本地分配本地语音路由策略。 此策略可以是全局策略或特定于用户的策略，并定义与用户关联的 PSTN 用法记录。 本主题介绍如何分配此策略。
  
另一个语音策略定义哪些呼叫功能可供用户使用;此语音策略由 Microsoft 定义，对于具有本地 PSTN 连接电话系统所有语音策略均相同。 它会自动分配给电话系统用户。
  
|&nbsp;|本地用户|电话系统本地 PSTN 连接用户进行连接|
|:-----|:-----|:-----|
|中定义的调用功能   |语音策略   |预定义的语音策略，在用户获得许可后自动电话系统。   |
|关联的 PSTN 用法记录   |语音策略   |语音路由策略，在用户仍位于本地时分配。   |
   
使用本地部署执行以下步骤，同时用户仍位于本地部署中。
  
## <a name="using-a-global-voice-routing-policy"></a>使用全局语音路由策略

在将全局语音路由策略用于电话系统 PSTN 连接用户之前，您必须将 PSTN 用法记录添加到该策略。
  
### <a name="to-assign-pstn-usage-records-to-the-global-voice-routing-policy"></a>将 PSTN 用法记录分配给全局语音路由策略

1. 使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。
    
2. 启动命令行Skype for Business Server：单击"开始"，单击"所有程序"，单击 **"Skype for Business 2015"，** 然后单击"Skype for Business Server **命令行管理程序"。**
    
3. 将 PSTN 用法记录添加到策略：
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages <PSTNUsagesId> 
   ```

    例如：
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages "Local", "Long Distance" 
   ```

## <a name="creating-a-new-voice-routing-policy"></a>创建新的语音路由策略

### <a name="to-create-a-new-voice-routing-policy"></a>创建新的语音路由策略

1. 使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。
    
2. 启动命令行Skype for Business Server：单击"开始"，单击"所有程序"，单击 **"Skype for Business 2015"，** 然后单击"Skype for Business Server **命令行管理程序"。**
    
3. 创建新的语音路由策略：
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity <String> -Name <String> -PSTNUsages <PSTNUsagesId>
   ```

    例如：
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity HybridVoice -Name Hybrid -PSTNUsages "Local", "Long Distance"
   ```

此示例创建名为 HybridVoice 的新语音路由策略，该策略具有两个与之关联的 PSTN 用法。
  
## <a name="assigning-a-voice-routing-policy"></a>分配语音路由策略

无论您使用全局语音路由策略还是特定于用户的语音路由策略，都请使用以下步骤将策略分配给用户。
  
### <a name="to-assign-the-voice-routing-policy"></a>分配语音路由策略

1. 使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。
    
2. 启动命令行Skype for Business Server：单击"开始"，单击"所有程序"，单击 **"Skype for Business 2015"，** 然后单击"Skype for Business Server **命令行管理程序"。**
    
3. 向用户分配现有语音策略：
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    例如：
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity "Bob Kelly" -PolicyName HybridVoice
   ```

本示例中，将具有 显示名称 Bob Kelly 的用户分配到先前创建的语音策略，其名称为 HybridVoice。
  
有关语音路由策略的更多详细信息，请参阅[Create or modify a voice policy and configure PSTN usage records in Skype for Business 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md)、 [New-CsVoiceRoutingPolicy](/powershell/module/skype/new-csvoiceroutingpolicy)和[Grant-CsVoicePolicy](/powershell/module/skype/grant-csvoicepolicy)。
