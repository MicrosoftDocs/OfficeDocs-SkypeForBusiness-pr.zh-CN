---
title: Skype 中的企业语音的用户启用企业服务器
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f252b23b-9641-4160-aa81-bf06dc2eced3
description: 摘要： 了解如何使用户可以拨打和接听电话使用企业语音中 Skype 业务服务器。
ms.openlocfilehash: b02155f424e8b3f29881caf8c4a29db6f76cb807
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212472"
---
# <a name="enable-users-for-enterprise-voice-in-skype-for-business-server"></a>Skype 中的企业语音的用户启用企业服务器
 
**摘要：** 了解如何使用户可以拨打和接听电话使用企业语音中 Skype 业务服务器。
  
在部署企业语音或通过单位电话呼叫后，您可以使用以下过程使用户能够通过使用企业语音发起呼叫：
  
> [!NOTE]
> 下面的过程，可以使用适用于业务 Server Control Panel Skype 执行只有第一个。 其余过程，可用于业务 Server 命令行管理程序仅 Skype。 
  
- 启用企业语音的用户帐户。
    
- （可选）为用户帐户分配特定于用户的语音策略。
    
- （可选）为用户帐户分配特定于用户的拨号计划。
    
### <a name="to-enable-a-user-account-for-enterprise-voice"></a>若要启用企业语音的用户帐户

1. 以 RTCUniversalServerAdmins 组成员或者 **CsVoiceAdministrator**、**CsServerAdministrator** 或 **CsAdministrator** 管理角色成员的身份登录计算机。
    
2. 打开 Skype 业务 Server Control Panel。
    
3. 在左导航栏中，单击“用户”****。
    
4. 在“搜索用户”**** 框中，键入要启用的用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“查找”****。
    
5. 在表中，单击您想要启用企业语音的用户帐户。
    
6. 在“编辑”**** 菜单上，单击“显示详细信息”****。
    
7. 在**的企业服务器用户编辑 Skype**页上，在**电话**下单击**企业语音**。
    
8. 单击“线路 URI”****，然后键入唯一的规范化电话号码（例如，tel:+14255550200）。
    
9. 单击“**提交**”。
    
若要完成为用户启用企业语音，请确保该用户的语音策略和拨号计划，分配全局 （默认分配） 或特定于用户的。默认情况下，所有用户分配全局语音策略和拨号计划。 如果语音策略或拨号计划的站点级别与承载用户帐户的站点相同，则这些站点策略将自动应用于用户。 要对用户应用每用户语音策略或拨号计划，您必须运行 **Grant-CsVoicePolicy** 和 **Grant-CsDialPlan** cmdlet。 有关详细信息，请参阅本主题中的以下过程。
## <a name="voice-policy-assignment"></a>语音策略分配

全局和站点级别语音策略是自动分配给所有启用企业语音的用户帐户。 还可以创建适用于特定的用户或组的语音策略。 必须将这些每用户策略显式分配给用户或组。 如果您想要使用全局或站点的所有用户启用企业语音的语音策略，您可以跳过本节并转到本主题后面的[拨号计划分配](enable-users-for-enterprise-voice.md#BKMK_DialPlanAssignment)节。
  
### <a name="to-assign-a-user-specific-voice-policy"></a>分配特定于用户的语音策略

1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 启动 Skype for Business Server 命令行管理程序：依次单击“开始”****、“所有程序”**** 和“Skype for Business 2015”****，然后单击“Skype for Business Server 命令行管理程序”****。
    
3. 要将现有用户语音策略分配给用户，请在命令提示符处运行以下命令：
    
   ```
   Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    例如：
    
   ```
   Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
   ```

    此示例中，在具有显示名称为 Bob Kelly 的用户分配名称为**VoicePolicyJapan**的语音策略。
    
## <a name="dial-plan-assignment"></a>拨号计划分配
<a name="BKMK_DialPlanAssignment"> </a>

若要完成的企业语音的用户或电话拨入式会议的用户的用户帐户配置，用户必须分配拨号计划。 如果没有显式分配现有每用户拨号计划，则用户帐户将自动使用全局拨号计划或站点级别拨号计划（如果存在）。 如果您想要使用全局或站点的所有用户启用企业语音拨号计划，则可以跳过本节。
  
### <a name="to-assign-a-user-specific-dial-plan"></a>分配特定于用户的拨号计划

1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 启动 Skype for Business Server 命令行管理程序：依次单击“开始”****、“所有程序”**** 和“Skype for Business 2015”****，然后单击“Skype for Business Server 命令行管理程序”****。
    
3. 要分配特定于用户的拨号计划，请在命令提示符处运行：
    
   ```
   Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
   ```

    例如：
    
   ```
   Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
   ```

    此示例中，在具有显示名称为 Bob Kelly 的用户分配名称**DialPlanJapan**的用户拨号计划。
    

