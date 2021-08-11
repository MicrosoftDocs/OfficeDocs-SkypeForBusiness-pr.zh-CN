---
title: 为用户启用企业语音Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f252b23b-9641-4160-aa81-bf06dc2eced3
description: 摘要：了解如何在 Skype for Business Server 中通过使用 企业语音 来允许用户拨打和接听Skype for Business Server。
ms.openlocfilehash: 0bc680872d2b339c9db9d4b8f4e9acbe0106e3869b918e1b48e16d3676a45cd3
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54312060"
---
# <a name="enable-users-for-enterprise-voice-in-skype-for-business-server"></a>为用户启用企业语音Skype for Business Server
 
**摘要：** 了解如何使用户能够通过使用 企业语音 中的 Skype for Business Server 拨打和接听Skype for Business Server。
  
在部署企业语音或通过工电话呼叫后，可以使用以下过程使用户可以通过使用 企业语音：
  
> [!NOTE]
> 在下列过程中，只有第一个过程可以使用"控制面板Skype for Business Server执行。 对于其余过程，只能使用命令行管理Skype for Business Server命令行管理程序。 
  
- 为用户帐户启用企业语音。
    
- （可选）为用户帐户分配特定于用户的语音策略。
    
- （可选）为用户帐户分配特定于用户的拨号计划。
    
### <a name="to-enable-a-user-account-for-enterprise-voice"></a>为用户帐户启用企业语音

1. 以 RTCUniversalServerAdmins 组成员或 **CsVoiceAdministrator**、**CsServerAdministrator** 或 **CsAdministrator** 管理角色成员的身份登录计算机。
    
2. 打开Skype for Business Server控制面板"。
    
3. 在左侧导航栏中，单击“用户”。
    
4. 在“搜索用户”框中，键入要启用的用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“查找”。
    
5. 在表中，单击要为此帐户启用的企业语音。
    
6. 在“编辑”菜单上，单击“显示详细信息”。
    
7. 在"**编辑Skype for Business Server用户"** 页上的"电话 **"** 下，单击 **"企业语音"。**
    
8. 单击“线路 URI”，然后键入唯一的规范化电话号码（例如，tel:+14255550200）。
    
9. 单击“提交”。
    
要完成为用户启用 企业语音，请确保为该用户分配了语音策略和拨号计划，无论默认情况下 (全局) 还是特定于用户。默认情况下，会为所有用户分配全局语音策略和拨号计划。 如果语音策略或拨号计划的站点级别与承载用户帐户的站点相同，则这些站点策略将自动应用于用户。 要对用户应用每用户语音策略或拨号计划，您必须运行 **Grant-CsVoicePolicy** 和 **Grant-CsDialPlan** cmdlet。 有关详细信息，请参阅本主题中的以下过程。
## <a name="voice-policy-assignment"></a>语音策略分配

全局和站点级别的语音策略将自动分配给所有启用此企业语音。 还可以创建适用于特定的用户或组的语音策略。 必须将这些每用户策略显式分配给用户或组。 如果要对已启用 企业语音 的所有用户使用全局或站点语音策略，可以跳过此部分并继续本主题稍后介绍的"拨号[计划](enable-users-for-enterprise-voice.md#BKMK_DialPlanAssignment)分配"部分。
  
### <a name="to-assign-a-user-specific-voice-policy"></a>分配特定于用户的语音策略

1. 使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。
    
2. 启动命令行Skype for Business Server：单击"开始"，单击"所有程序"，单击 **"Skype for Business 2015"，** 然后单击"Skype for Business Server **命令行管理程序"。**
    
3. 要将现有用户语音策略分配给用户，请在命令提示符处运行：
    
   ```powershell
   Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    例如：
    
   ```powershell
   Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
   ```

    本示例中，为具有 显示名称 Bob Kelly 的用户分配了名称 **为 VoicePolicyJapan 的语音策略**。
    
## <a name="dial-plan-assignment"></a>拨号计划分配
<a name="BKMK_DialPlanAssignment"> </a>

要完成企业语音用户或电话拨入式会议用户的用户帐户配置，必须为用户分配拨号计划。 如果没有显式分配现有每用户拨号计划，则用户帐户将自动使用全局拨号计划或站点级别拨号计划（如果存在）。 如果要对已启用呼叫的所有用户使用全局或站点拨号企业语音，可以跳过此部分。
  
### <a name="to-assign-a-user-specific-dial-plan"></a>分配特定于用户的拨号计划

1. 使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。
    
2. 启动命令行Skype for Business Server：单击"开始"，单击"所有程序"，单击 **"Skype for Business 2015"，** 然后单击"Skype for Business Server **命令行管理程序"。**
    
3. 要分配特定于用户的拨号计划，请在命令提示符处运行：
    
   ```powershell
   Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
   ```

    例如：
    
   ```powershell
   Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
   ```

    本示例中，为具有 显示名称 Bob Kelly 的用户分配了名称为 **DialPlanJapan 的用户拨号计划**。
    

