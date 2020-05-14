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
description: 摘要：阅读本主题，了解如何为使用具有本地 PSTN 连接的电话系统的用户分配语音策略。
ms.openlocfilehash: 141d3cca560201df921fb4195db55ac60103a3d6
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221856"
---
# <a name="assign-a-voice-routing-policy"></a>分配语音路由策略
 
**摘要：** 阅读本主题，了解如何为使用具有本地 PSTN 连接的电话系统的用户分配语音策略。 
  
一旦用户在 Skype for Business Online 中使用具有本地 PSTN 连接的电话系统，将对其应用两个语音策略。 一个是您将在本地分配的本地语音路由策略。 此策略可以是全局策略，也可以是特定于用户的策略，并定义哪些 PSTN 用法记录与用户相关联。 本主题说明如何分配此策略。
  
其他语音策略定义了用户可以使用的呼叫功能;此语音策略由 Microsoft 定义，对于具有本地 PSTN 连接用户的所有电话系统都是相同的。 它将自动分配给电话系统用户。
  
||**本地用户**|**具有本地 PSTN 连接用户的电话系统**|
|:-----|:-----|:-----|
|中定义的呼叫功能  <br/> |语音策略  <br/> |预定义的语音策略，在用户许可电话系统时自动分配。  <br/> |
|与相关联的 PSTN 用法记录  <br/> |语音策略  <br/> |语音路由策略，在用户仍在本地托管的情况下进行分配。  <br/> |
   
您可以使用本地部署执行以下步骤，而用户仍驻留在本地部署中。
  
## <a name="using-a-global-voice-routing-policy"></a>使用全局语音路由策略

在使用具有本地 PSTN 连接用户的电话系统的全局语音路由策略之前，必须向策略中添加 PSTN 用法记录。
  
### <a name="to-assign-pstn-usage-records-to-the-global-voice-routing-policy"></a>将 PSTN 用法记录分配给全局语音路由策略

1. 使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。
    
2. 启动 Skype for Business Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **skype for business 2015**"，然后单击 " **skype for business Server Management Shell**"。
    
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
    
2. 启动 Skype for Business Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **skype for business 2015**"，然后单击 " **skype for business Server Management Shell**"。
    
3. 创建新的语音路由策略：
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity <String> -Name <String> -PSTNUsages <PSTNUsagesId>
   ```

    例如：
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity HybridVoice -Name Hybrid -PSTNUsages "Local", "Long Distance"
   ```

本示例创建名为为 hybridvoice 的新的语音路由策略，该策略有两个与之关联的 PSTN 用法。
  
## <a name="assigning-a-voice-routing-policy"></a>分配语音路由策略

无论您使用的是全局语音路由策略还是特定于用户的策略，都可以使用以下步骤将策略分配给用户。
  
### <a name="to-assign-the-voice-routing-policy"></a>分配语音路由策略

1. 使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。
    
2. 启动 Skype for Business Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **skype for business 2015**"，然后单击 " **skype for business Server Management Shell**"。
    
3. 向用户分配现有语音策略：
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    例如：
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity "Bob Kelly" -PolicyName HybridVoice
   ```

在此示例中，显示名称为小明凯利的用户分配给以前创建的名为为 hybridvoice 的语音策略。
  
有关语音路由策略的更多详细信息，请参阅[Create or modify a voice policy and CONFIGURE PSTN usage records In Skype For business 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md)、 [Grant-csvoiceroutingpolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)和[Grant set-csvoicepolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps)。
  

