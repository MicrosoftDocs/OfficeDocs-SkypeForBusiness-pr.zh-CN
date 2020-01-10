---
title: 在 Skype for business 服务器中启用企业语音用户
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f252b23b-9641-4160-aa81-bf06dc2eced3
description: 摘要：了解如何在 Skype for business 服务器中使用企业语音帮助用户拨打和接听电话。
ms.openlocfilehash: 441b7a5705268dedea1feb87e01a48d0ef68b32c
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002522"
---
# <a name="enable-users-for-enterprise-voice-in-skype-for-business-server"></a>在 Skype for business 服务器中启用企业语音用户
 
**摘要：** 了解如何通过在 Skype for Business 服务器中使用企业语音，帮助用户拨打和接听电话。
  
通过工作部署企业语音或呼叫后，您可以使用以下过程使用户能够使用企业语音进行呼叫：
  
> [!NOTE]
> 在以下过程中，仅可以使用 Skype for Business Server 控制面板执行第一个过程。 对于剩余的过程，您只能使用 Skype for Business Server 命令行管理程序。 
  
- 启用企业语音的用户帐户。
    
- （可选）为用户帐户分配特定于用户的语音策略。
    
- （可选）为用户帐户分配特定于用户的拨号计划。
    
### <a name="to-enable-a-user-account-for-enterprise-voice"></a>启用企业语音的用户帐户

1. 以 RTCUniversalServerAdmins 组成员或者 **CsVoiceAdministrator**、**CsServerAdministrator** 或 **CsAdministrator** 管理角色成员的身份登录计算机。
    
2. 打开 "Skype for Business 服务器" 控制面板。
    
3. 在左导航栏中，单击“用户”****。
    
4. 在“搜索用户”**** 框中，键入要启用的用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“查找”****。
    
5. 在表中，单击要为企业语音启用的用户帐户。
    
6. 在“编辑”**** 菜单上，单击“显示详细信息”****。
    
7. 在 "**编辑 Skype For Business 服务器" 用户**页面上的 "**电话服务**" 下，单击 "**企业语音**"。
    
8. 单击“线路 URI”****，然后键入唯一的规范化电话号码（例如，tel:+14255550200）。
    
9. 单击“**提交**”。
    
若要为用户启用企业语音，请确保向用户分配一个语音策略和一个拨号计划，无论是全局的（默认情况下分配的）还是特定于用户。默认情况下，将为所有用户分配全局语音策略和拨号计划。 如果语音策略或拨号计划的站点级别与承载用户帐户的站点相同，则这些站点策略将自动应用于用户。 要对用户应用每用户语音策略或拨号计划，您必须运行 **Grant-CsVoicePolicy** 和 **Grant-CsDialPlan** cmdlet。 有关详细信息，请参阅本主题中的以下过程。
## <a name="voice-policy-assignment"></a>语音策略分配

全局策略和网站级语音策略将自动分配给所有已启用企业语音的用户帐户。 还可以创建适用于特定的用户或组的语音策略。 必须将这些每用户策略显式分配给用户或组。 如果要对已启用企业语音的所有用户使用全局或网站语音策略，可以跳过此部分，然后继续本主题后面部分的 "[拨入计划作业](enable-users-for-enterprise-voice.md#BKMK_DialPlanAssignment)" 部分。
  
### <a name="to-assign-a-user-specific-voice-policy"></a>分配特定于用户的语音策略

1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 启动 Skype for Business Server 命令行管理程序：依次单击“开始”****、“所有程序”**** 和“Skype for Business 2015”****，然后单击“Skype for Business Server 命令行管理程序”****。
    
3. 要将现有用户语音策略分配给用户，请在命令提示符处运行以下命令：
    
   ```powershell
   Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    例如：
    
   ```powershell
   Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
   ```

    在此示例中，具有显示名称 Bob 凯利的用户被分配了名称为 " **VoicePolicyJapan**" 的语音策略。
    
## <a name="dial-plan-assignment"></a>拨号计划分配
<a name="BKMK_DialPlanAssignment"> </a>

若要为企业语音的用户和电话拨入式会议的用户完成用户帐户配置，必须为用户分配一个拨号计划。 如果没有显式分配现有每用户拨号计划，则用户帐户将自动使用全局拨号计划或站点级别拨号计划（如果存在）。 如果要对启用了企业语音的所有用户使用全局或网站拨号计划，可以跳过此部分。
  
### <a name="to-assign-a-user-specific-dial-plan"></a>分配特定于用户的拨号计划

1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 启动 Skype for Business Server 命令行管理程序：依次单击“开始”****、“所有程序”**** 和“Skype for Business 2015”****，然后单击“Skype for Business Server 命令行管理程序”****。
    
3. 要分配特定于用户的拨号计划，请在命令提示符处运行：
    
   ```powershell
   Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
   ```

    例如：
    
   ```powershell
   Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
   ```

    在此示例中，使用显示名称 Bob 凯利的用户被分配了名称为 " **DialPlanJapan**" 的用户拨号计划。
    

