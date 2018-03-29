---
title: 允许用户使用内部部署的企业语音
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
ms.custom: Strat_SB_Hybrid
ms.assetid: 4598565a-c228-4265-ad03-d2aef95b31a0
description: 对于用户在 Office 365 (云 PBX) 中使用电话系统，必须首先启用它们的企业语音并将它们分配电话号码。 您这样做时用户仍驻留在内部部署中使用内部部署。
ms.openlocfilehash: c661d6da46cc42843346541b29841a728ab0fc16
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="enable-the-users-for-enterprise-voice-on-premises"></a>允许用户使用内部部署的企业语音
 
对于用户在 Office 365 (云 PBX) 中使用电话系统，必须首先启用它们的企业语音并将它们分配电话号码。 您这样做时用户仍驻留在内部部署中使用内部部署。
  
### <a name="to-enable-a-user-for-enterprise-voice-on-premises-and-assign-a-phone-number"></a>若要为用户启用内部部署的企业语音和分配电话号码

1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 使用“开始”菜单或桌面快捷方式打开 Skype for Business Server 控制面板。
    
    也可以打开浏览器窗口，然后输入管理员 URL 以打开 Skype for Business Server 控制面板。
    
3. 在左导航栏中，单击“**用户**”。
    
4. 在“**搜索用户**”框中，键入要启用的用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“**查找**”。
    
5. 在表中，单击您想要启用的企业语音的在线业务用户帐户 Skype。
    
6. 在“**编辑**”菜单上，单击“**显示详细信息**”。
    
7. 在“**电话**”下，单击“**企业语音**”。
    
8. 单击“**线路 URI**”，输入唯一的规范化电话号码（例如，tel:+14255550200）。然后单击“**提交**”。
    
## <a name="special-considerations-when-enabling-users-for-enterprise-voice-on-premises"></a>为用户启用内部部署的企业语音时的特殊注意事项

在某些情况下，可能需要修改为用户启用企业语音的方式来确保他们可以成功地发出和接听呼叫。 如果您有您的部署中满足以下条件的用户，请执行步骤包含允许用户为企业语音。
  
- 如果您在部署中创建的用户广告与 Skype 业务在线同步，而无需为业务或企业语音对 Skype 正在启用并没有设置，则运行以下 cmdlet 的每个受影响的用户，替换中的值 LineURI <c0 > <b1></b1>为您的环境的实际值：
    
  ```
  Enable-CsUser $username -HostingProvider sipfed.online.lync.com -SipAddress sip:<UserName>@<SIP Domain>
  ```

  ```
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- 如果用户已为企业内部部署，Skype 为启用，但未启用企业语音或移到 Skype 的在线业务前分配 LineURI，运行以下 cmdlet 的每个用户：
    
  ```
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- 如果用户已经在 Skype 为企业内部部署中启用但未启用为企业语音，即使已分配 LineURI，运行以下 cmdlet 为每个受影响的用户：
    
  ```
  Set-CsUser $username -EnterpriseVoiceEnabled $true
  ```


