---
title: 为用户启用本地的企业语音
ms.reviewer: ''
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
ms.assetid: 4598565a-c228-4265-ad03-d2aef95b31a0
description: 用于在 Office 365 (云 PBX) 电话系统的用户，首先必须启用企业语音并将其分配电话号码。 执行此操作时用户仍驻留在本地部署中使用您的本地部署。
ms.openlocfilehash: 1b8329ec4deb90aed6bb9ae93c4a202beebb673c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32234075"
---
# <a name="enable-the-users-for-enterprise-voice-on-premises"></a>为用户启用本地的企业语音
 
用于在 Office 365 (云 PBX) 电话系统的用户，首先必须启用企业语音并将其分配电话号码。 执行此操作时用户仍驻留在本地部署中使用您的本地部署。
  
### <a name="to-enable-a-user-for-enterprise-voice-on-premises-and-assign-a-phone-number"></a>若要为用户启用企业语音本地和分配电话号码

1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 使用“开始”菜单或桌面快捷方式打开 Skype for Business Server 控制面板。
    
    也可以打开浏览器窗口，然后输入管理员 URL 以打开 Skype for Business Server 控制面板。
    
3. 在左导航栏中，单击“**用户**”。
    
4. 在“搜索用户”**** 框中，键入要启用的用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“查找”****。
    
5. 在表中，单击业务联机您想要启用企业语音的用户帐户 Skype。
    
6. 在“**编辑**”菜单上，单击“**显示详细信息**”。
    
7. 在“**电话**”下，单击“**企业语音**”。
    
8. 单击“**线路 URI**”，输入唯一的规范化电话号码（例如，tel:+14255550200）。然后单击“**提交**”。
    
## <a name="special-considerations-when-enabling-users-for-enterprise-voice-on-premises"></a>为用户启用本地的企业语音时的特殊注意事项

在某些情况下，可能需要修改为用户启用企业语音的方式来确保他们可以成功地发出和接听呼叫。 如果必须满足以下条件的用户部署中，执行包含用户启用企业语音的步骤。
  
- 如果您的内部部署中创建用户 AD 和 Skype 与同步业务 online 不被启用 Skype 业务或企业语音的情况下，并且没有 LineURI 设置，运行以下 cmdlet 为每个受影响的用户，替换中的值 <c0 > <b1></b1>替换为您环境的实际值：
    
  ```
  Enable-CsUser $username -HostingProvider sipfed.online.lync.com -SipAddress sip:<UserName>@<SIP Domain>
  ```

  ```
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- 如果用户已启用 Skype for Business 在本地，但未启用企业语音或业务 online 被移动到 Skype 之前分配 LineURI，运行以下 cmdlet 为每个用户：
    
  ```
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- 如果用户是在本地的业务的 Skype 中已启用，但未启用企业语音，即使已分配 LineURI，运行以下 cmdlet 为每个受影响的用户：
    
  ```
  Set-CsUser $username -EnterpriseVoiceEnabled $true
  ```


