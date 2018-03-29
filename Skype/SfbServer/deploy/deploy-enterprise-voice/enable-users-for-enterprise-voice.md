---
title: 在 Skype for Business Server 2015 中为用户启用企业语音
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: f252b23b-9641-4160-aa81-bf06dc2eced3
description: 摘要： 了解如何使用户能够拨打和接听电话业务服务器 2015年在 Skype 使用企业语音。
ms.openlocfilehash: d187723b347121400bfbce00d238851f2d0651a9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="enable-users-for-enterprise-voice-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中为用户启用企业语音
 
**摘要：**了解如何使用户能够拨打和接听电话业务服务器 2015年在 Skype 使用企业语音。
  
企业语音或调用通过工作部署之后，可以使用以下过程来使用户能够通过使用企业语音进行调用：
  
> [!NOTE]
> 下面的过程中，只有第一个可以执行通过 Skype 业务服务器的控制面板。 对于剩余的过程中，可用于业务服务器管理外壳只有 Skype。 
  
- 企业语音用于启用用户帐户。
    
- （可选）为用户帐户分配特定于用户的语音策略。
    
- （可选）为用户帐户分配特定于用户的拨号计划。
    
### <a name="to-enable-a-user-account-for-enterprise-voice"></a>以企业语音为启用用户帐户

1. 以 RTCUniversalServerAdmins 组成员或者 **CsVoiceAdministrator**、**CsServerAdministrator** 或 **CsAdministrator** 管理角色成员的身份登录计算机。
    
2. 打开 Skype 业务服务器的控制面板。
    
3. 在左导航栏中，单击“**用户**”。
    
4. 在“**搜索用户**”框中，键入要启用的用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“**查找**”。
    
5. 在表中，单击您想要启用的企业语音的用户帐户。
    
6. 在“编辑”****菜单上，单击“显示详细信息”****。
    
7. **编辑业务服务器用户的 Skype**在页上，单击**电话**，中的**企业语音**。
    
8. 单击“线路 URI”****，然后键入唯一的规范化电话号码（例如，tel:+14255550200）。
    
9. 单击“**提交**”。
    
要启用用户参与企业语音，为确保语音策略和拨号计划，指定用户是否全局 （默认情况下指定） 或特定于用户的。默认情况下，所有用户都分配一个全局语音策略和拨号计划。 如果语音策略或拨号计划的站点级别与承载用户帐户的站点相同，则这些站点策略将自动应用于用户。 要应用的每个用户语音策略或拨号计划与用户，您必须运行**授予 CsVoicePolicy**和**授予 CsDialPlan** cmdlet。 有关详细信息，请参阅本主题中的以下过程。
## <a name="voice-policy-assignment"></a>语音策略分配

全局和站点级语音策略会自动分配到所有的用户帐户启用的企业语音。 还可以创建适用于特定的用户或组的语音策略。 必须将这些每用户策略显式分配给用户或组。 如果您想要使用全局管理员或站点的所有用户都启用了企业语音的语音策略，可以跳过此部分并转到本主题中后面的[拨号计划分配](enable-users-for-enterprise-voice.md#BKMK_DialPlanAssignment)节。
  
### <a name="to-assign-a-user-specific-voice-policy"></a>分配特定于用户的语音策略

1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。
    
3. 要将现有用户语音策略分配给用户，请在命令提示符处运行以下命令：
    
   ```
   Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    例如：
    
   ```
   Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
   ```

    在此示例中，显示名称 Bob 凯利向用户分配名称**VoicePolicyJapan**的语音策略。
    
## <a name="dial-plan-assignment"></a>拨号计划分配
<a name="BKMK_DialPlanAssignment"> </a>

完成用户帐户配置为企业语音的用户或用户的拨入会议服务，用户必须分配一个拨号计划。 如果没有显式分配现有每用户拨号计划，则用户帐户将自动使用全局拨号计划或站点级别拨号计划（如果存在）。 如果您想要使用全局管理员或站点的所有用户都启用了企业语音的拨号计划，则可以跳过本节。
  
### <a name="to-assign-a-user-specific-dial-plan"></a>分配特定于用户的拨号计划

1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。
    
3. 要分配特定于用户的拨号计划，请在命令提示符处运行：
    
   ```
   Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
   ```

    例如：
    
   ```
   Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
   ```

    在此示例中，显示名称 Bob 凯利向用户分配用户拨号计划，名为**DialPlanJapan**。
    

