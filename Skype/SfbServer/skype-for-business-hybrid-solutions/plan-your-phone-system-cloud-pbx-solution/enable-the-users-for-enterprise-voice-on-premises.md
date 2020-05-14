---
title: 为用户启用企业语音（本地）
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
ms.assetid: 4598565a-c228-4265-ad03-d2aef95b31a0
description: 若要让用户使用电话系统（云 PBX），必须首先为企业语音启用它们并为其分配一个电话号码。 您可以使用本地部署执行此操作，同时用户仍驻留在本地部署中。
ms.openlocfilehash: f02638f618b32190fafcded66550b5c3dcc52f2d
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221696"
---
# <a name="enable-the-users-for-enterprise-voice-on-premises"></a>为用户启用企业语音（本地）
 
若要让用户使用电话系统（云 PBX），必须首先为企业语音启用它们并为其分配一个电话号码。 您可以使用本地部署执行此操作，同时用户仍驻留在本地部署中。
  
### <a name="to-enable-a-user-for-enterprise-voice-on-premises-and-assign-a-phone-number"></a>为用户启用企业内部语音和分配电话号码

1. 使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。
    
2. 使用 "开始" 菜单或桌面快捷方式打开 Skype for Business Server 控制面板。
    
    您还可以打开浏览器窗口，然后输入管理员 URL 以打开 Skype for Business Server 控制面板。
    
3. 在左侧导航栏中，单击“用户”****。
    
4. 在“搜索用户”**** 框中，键入要启用的用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“查找”****。
    
5. 在表中，单击要为企业语音启用的 Skype for Business Online 用户帐户。
    
6. 在 "**编辑**" 菜单上，单击 "**显示详细信息**"。
    
7. 在 "**电话**" 下，单击 "**企业语音**"。
    
8. 单击 "**线路 URI**"，然后键入唯一的规范化电话号码（例如，电话： + 14255550200）。 然后单击 "**提交**"。
    
## <a name="special-considerations-when-enabling-users-for-enterprise-voice-on-premises"></a>为用户启用企业内部语音时的特殊注意事项

在某些情况下，您可能需要修改为用户启用企业语音的方式，以确保他们可以成功发出和接收呼叫。 如果您的部署中有满足以下条件的用户，请执行所包含的步骤以使用户能够使用企业语音。
  
- 如果用户在本地 AD 中创建，然后与 Skype for business Online 同步，而无需为 Skype for Business 或 Enterprise Voice 启用，并且没有 LineURI 集，请为每个受影响的用户运行以下 cmdlet，并将值替换为 \< \> 您的环境的实际值：
    
  ```powershell
  Enable-CsUser $username -HostingProvider sipfed.online.lync.com -SipAddress sip:<UserName>@<SIP Domain>
  ```

  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- 如果用户已在本地启用 Skype for Business，但未启用企业语音或在移动到 Skype for business Online 之前分配了 LineURI，请为每个用户运行以下 cmdlet：
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- 如果用户已在本地 Skype for Business 中启用，但未启用企业语音（即使已分配了 LineURI），请为每个受影响的用户运行以下 cmdlet：
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true
  ```


