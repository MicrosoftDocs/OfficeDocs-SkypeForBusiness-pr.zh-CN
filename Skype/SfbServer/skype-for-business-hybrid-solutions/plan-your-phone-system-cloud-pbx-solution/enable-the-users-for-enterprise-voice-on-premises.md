---
title: 为企业内部部署的用户启用企业语音
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
description: 若要让用户在 Office 365 （云 PBX）中使用电话系统，必须首先启用企业语音，并为其分配电话号码。 你可以使用本地部署执行此操作，同时用户仍托管在本地部署中。
ms.openlocfilehash: 4409de1965fbcca641dde69d70c734d1bcd3a8b6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802292"
---
# <a name="enable-the-users-for-enterprise-voice-on-premises"></a>为企业内部部署的用户启用企业语音
 
若要让用户在 Office 365 （云 PBX）中使用电话系统，必须首先启用企业语音，并为其分配电话号码。 你可以使用本地部署执行此操作，同时用户仍托管在本地部署中。
  
### <a name="to-enable-a-user-for-enterprise-voice-on-premises-and-assign-a-phone-number"></a>允许用户在内部部署企业语音并分配电话号码

1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 使用“开始”菜单或桌面快捷方式打开 Skype for Business Server 控制面板。
    
    也可以打开浏览器窗口，然后输入管理员 URL 以打开 Skype for Business Server 控制面板。
    
3. 在左导航栏中，单击“**用户**”。
    
4. 在“搜索用户”**** 框中，键入要启用的用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“查找”****。
    
5. 在表中，单击要为企业语音启用的 Skype for Business Online 用户帐户。
    
6. 在“**编辑**”菜单上，单击“**显示详细信息**”。
    
7. 在“**电话**”下，单击“**企业语音**”。
    
8. 单击“**线路 URI**”，输入唯一的规范化电话号码（例如，tel:+14255550200）。然后单击“**提交**”。
    
## <a name="special-considerations-when-enabling-users-for-enterprise-voice-on-premises"></a>为企业内部部署的用户启用的特殊注意事项

在某些情况下，可能需要修改为用户启用企业语音的方式来确保他们可以成功地发出和接听呼叫。 如果你的部署中有满足以下条件的用户，请执行所包含的步骤以启用企业语音用户。
  
- 如果用户在本地广告中创建，然后与 skype for business Online 同步，而不启用 skype for business 或企业语音，并且没有 LineURI 集，请为每个受影响的用户运行以下 cmdlet， \< \>并用你的环境的实际值替换其中的值：
    
  ```powershell
  Enable-CsUser $username -HostingProvider sipfed.online.lync.com -SipAddress sip:<UserName>@<SIP Domain>
  ```

  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- 如果用户已针对本地 Skype for business 启用，但未启用企业语音或在移动到 Skype for business Online 之前分配了 LineURI，请为每个用户运行以下 cmdlet：
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- 如果用户已在本地 Skype for Business 中启用，但未启用企业语音，即使已分配了 LineURI，也为每个受影响的用户运行以下 cmdlet：
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true
  ```


