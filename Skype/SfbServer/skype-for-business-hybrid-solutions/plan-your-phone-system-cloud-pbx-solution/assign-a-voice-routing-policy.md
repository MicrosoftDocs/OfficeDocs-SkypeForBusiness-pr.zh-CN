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
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: c7f78f23-b74f-402f-bedb-4cc308718f5b
description: 摘要：阅读本主题，了解如何使用本地 PSTN 连接为使用 Office 365 中的电话系统的用户分配语音策略。
ms.openlocfilehash: 0e9a39fba8d1db7b70f0422e71223d49917716ac
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803992"
---
# <a name="assign-a-voice-routing-policy"></a>分配语音路由策略
 
**摘要：** 阅读本主题，了解如何使用本地 PSTN 连接为使用 Office 365 中的电话系统的用户分配语音策略。 
  
一旦用户使用 Skype for Business Online 并在 Office 365 中使用 "电话系统" 与本地 PSTN 连接，将对其应用两个语音策略。 一个是您将在本地分配的本地语音路由策略。 此策略可以是全局策略或特定于用户的，并且定义了哪些 PSTN 使用记录与用户相关联。 本主题介绍了如何分配此策略。
  
其他语音政策定义用户可以使用哪些通话功能;此语音政策由 Microsoft 定义，对于 Office 365 中的所有电话系统，与本地 PSTN 连接用户是相同的。 它会自动分配给 Office 365 用户中的电话系统。
  
||**本地用户**|**使用本地 PSTN 连接用户的 Office 365 中的电话系统**|
|:-----|:-----|:-----|
|定义的呼叫功能  <br/> |语音策略  <br/> |预定义的语音策略，在用户使用 Office 365 中的电话系统授权时自动分配。  <br/> |
|相关联的 PSTN 用法记录  <br/> |语音策略  <br/> |当用户仍驻留在本地时分配的语音路由策略。  <br/> |
   
使用本地部署执行以下步骤，而用户仍托管在本地部署中。
  
## <a name="using-a-global-voice-routing-policy"></a>使用全局语音路由策略

在使用本地 PSTN 连接用户在 Office 365 中为您的电话系统使用全局语音路由策略之前，必须将 PSTN 使用记录添加到该策略。
  
### <a name="to-assign-pstn-usage-records-to-the-global-voice-routing-policy"></a>向全局语音路由策略分配 PSTN 用法记录

1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 启动 Skype for Business Server 命令行管理程序：依次单击“开始”****、“所有程序”**** 和“Skype for Business 2015”****，然后单击“Skype for Business Server 命令行管理程序”****。
    
3. 将 PSTN 使用记录添加到策略：
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages <PSTNUsagesId> 
   ```

    例如：
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages "Local", "Long Distance" 
   ```

## <a name="creating-a-new-voice-routing-policy"></a>创建新的语音路由策略

### <a name="to-create-a-new-voice-routing-policy"></a>创建新的语音路由策略

1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 启动 Skype for Business Server 命令行管理程序：依次单击“开始”****、“所有程序”**** 和“Skype for Business 2015”****，然后单击“Skype for Business Server 命令行管理程序”****。
    
3. 创建新的语音路由策略：
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity <String> -Name <String> -PSTNUsages <PSTNUsagesId>
   ```

    例如：
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity HybridVoice -Name Hybrid -PSTNUsages "Local", "Long Distance"
   ```

此示例将创建名为 HybridVoice 的新语音路由策略，它有两个相关联的 PSTN 用法。
  
## <a name="assigning-a-voice-routing-policy"></a>分配语音路由策略

无论您使用的是全局语音路由策略还是用户特定的语音路由策略，请按照以下步骤为用户分配策略。
  
### <a name="to-assign-the-voice-routing-policy"></a>分配语音路由策略

1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 启动 Skype for Business Server 命令行管理程序：依次单击“开始”****、“所有程序”**** 和“Skype for Business 2015”****，然后单击“Skype for Business Server 命令行管理程序”****。
    
3. 向用户分配现有语音策略：
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    例如：
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity "Bob Kelly" -PolicyName HybridVoice
   ```

在此示例中，向显示名称为 Bob Kelly 的用户分配之前创建的名为 HybridVoice 的语音策略。
  
有关语音路由策略的更多详细信息，请参阅在 Skype for Business 2015、 [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)和[CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps)[中创建或修改语音策略和配置 PSTN 使用记录](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md)。
  

