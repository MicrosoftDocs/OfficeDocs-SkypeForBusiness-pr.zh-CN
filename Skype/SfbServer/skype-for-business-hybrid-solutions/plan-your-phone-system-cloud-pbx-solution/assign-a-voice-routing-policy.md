---
title: 分配语音路由策略
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: c7f78f23-b74f-402f-bedb-4cc308718f5b
description: 摘要： 阅读本主题可了解如何分配 Office 365 中的电话系统使用内部部署 PSTN 连接的用户的语音策略。
ms.openlocfilehash: 12e74a6ea4a0adf652cc4e9477d20f91b4e13732
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25372407"
---
# <a name="assign-a-voice-routing-policy"></a>分配语音路由策略
 
**摘要：** 阅读本主题可了解如何分配 Office 365 中的电话系统使用内部部署 PSTN 连接的用户的语音策略。 
  
Skype 业务 Online 和 Office 365 中的电话系统使用内部部署 PSTN 连接上用户后，两个语音策略将应用于它们。 一个是在本地将分配给内部部署语音路由策略。 此策略可以是全局或特定于用户并定义与用户关联的 PSTN 用法记录。 本主题介绍了如何分配此策略。
  
其他语音策略定义了哪些呼叫功能可供用户;此语音策略定义由 Microsoft，相同的 Office 365 中的所有电话系统与内部部署 PSTN 连接用户。 它是自动分配给电话系统中的 Office 365 用户。
  
||**本地用户**|**与内部部署 PSTN 连接用户的 Office 365 中的电话系统**|
|:-----|:-----|:-----|
|定义的呼叫功能  <br/> |语音策略  <br/> |预定义用户许可 Office 365 中的电话系统时自动分配语音策略。  <br/> |
|相关联的 PSTN 用法记录  <br/> |语音策略  <br/> |当用户仍驻留在本地时分配的语音路由策略。  <br/> |
   
执行以下步骤时用户仍驻留在本地部署中使用您的本地部署。
  
## <a name="using-a-global-voice-routing-policy"></a>使用全局语音路由策略

内部部署 PSTN 连接用户与电话系统 Office 365 中使用全局语音路由策略之前, 必须向策略中添加 PSTN 用法记录。
  
### <a name="to-assign-pstn-usage-records-to-the-global-voice-routing-policy"></a>向全局语音路由策略分配 PSTN 用法记录

1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。
    
3. 向策略中添加 PSTN 用法记录：
    
   ```
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages <PSTNUsagesId> 
   ```

    例如：
    
   ```
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages "Local", "Long Distance" 
   ```

## <a name="creating-a-new-voice-routing-policy"></a>创建新的语音路由策略

### <a name="to-create-a-new-voice-routing-policy"></a>创建新的语音路由策略

1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。
    
3. 创建新的语音路由策略：
    
   ```
   New-CSVoiceRoutingPolicy -Identity <String> -Name <String> -PSTNUsages <PSTNUsagesId>
   ```

    例如：
    
   ```
   New-CSVoiceRoutingPolicy -Identity HybridVoice -Name Hybrid -PSTNUsages "Local", "Long Distance"
   ```

此示例将创建名为 HybridVoice 的新语音路由策略，它有两个相关联的 PSTN 用法。
  
## <a name="assigning-a-voice-routing-policy"></a>分配语音路由策略

无论您使用的是全局语音路由策略还是用户特定的语音路由策略，请按照以下步骤为用户分配策略。
  
### <a name="to-assign-the-voice-routing-policy"></a>分配语音路由策略

1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。
    
3. 向用户分配现有语音策略：
    
   ```
   Grant-CsVoiceRoutingPolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    例如：
    
   ```
   Grant-CsVoiceRoutingPolicy -Identity "Bob Kelly" -PolicyName HybridVoice
   ```

在此示例中，向显示名称为 Bob Kelly 的用户分配之前创建的名为 HybridVoice 的语音策略。
  
有关语音路由策略的详细信息，请参阅[创建或修改语音策略和配置 PSTN 用法记录中的业务 2015 Skype](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md)， [New-csvoiceroutingpolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)和[Grant-csvoicepolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps)。
  

