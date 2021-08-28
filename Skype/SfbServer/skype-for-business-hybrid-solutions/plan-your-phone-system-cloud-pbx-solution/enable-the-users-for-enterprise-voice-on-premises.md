---
title: 为用户启用企业语音内部部署
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
ms.localizationpriority: medium
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 4598565a-c228-4265-ad03-d2aef95b31a0
description: 对于使用云 PBX 电话系统 (用户) ，必须先为其启用企业语音并为其分配电话号码。 在用户仍位于本地部署中时，可以使用本地部署完成此操作。
ms.openlocfilehash: 28943670a0919d80c96c97b7574cdc82ac68cfde
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58613691"
---
# <a name="enable-the-users-for-enterprise-voice-on-premises"></a>为用户启用企业语音内部部署
 
对于使用云 PBX 电话系统 (用户) ，必须先为其启用企业语音并为其分配电话号码。 在用户仍位于本地部署中时，可以使用本地部署完成此操作。

> [!Important]
> Skype for BusinessOnline 将于 2021 年 7 月 31 日停用，此后服务将不再可用。  此外，将不再支持通过 Skype for Business Server 或云连接器版本与 Skype for Business Online 之间的 PSTN 连接。  了解如何使用直接路由将本地电话网络Teams[到呼叫。](/MicrosoftTeams/direct-routing-landing-page)
  
### <a name="to-enable-a-user-for-enterprise-voice-on-premises-and-assign-a-phone-number"></a>为用户启用本地企业语音并分配电话号码

1. 使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。
    
2. 使用"开始"菜单或桌面快捷方式打开"Skype for Business Server控制面板"。
    
    还可以打开浏览器窗口，然后输入管理员 URL 以打开Skype for Business Server控制面板。
    
3. 在左侧导航栏中，单击“用户”。
    
4. 在“搜索用户”框中，键入要启用的用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“查找”。
    
5. 在表中，单击Skype for Business要启用的联机用户帐户企业语音。
    
6. 在"编辑 **"菜单** 上，单击"**显示详细信息"。**
    
7. 在 **"电话"下**，单击 **"企业语音"。**
    
8. 单击 **"线路 URI"，** 然后键入唯一的规范化电话号码 (例如 tel：+14255550200) 。 然后单击"**提交"。**
    
## <a name="special-considerations-when-enabling-users-for-enterprise-voice-on-premises"></a>为用户启用本地部署企业语音注意事项

在某些情况下，您可能需要修改为用户启用呼叫企业语音以确保他们可以成功拨打和接听呼叫。 如果您的部署中具有满足以下条件的用户，请执行包含的步骤以启用用户企业语音。
  
- 如果在内部部署 AD 中创建用户，然后在未启用 Skype for Business 或 企业语音 的情况下与 Skype for Business Online 同步，并且没有设置 LineURI，请针对每个受影响的用户运行以下 cmdlet，将 中的值替换为您的环境的实际 \< \> 值：
    
  ```powershell
  Enable-CsUser $username -HostingProvider sipfed.online.lync.com -SipAddress sip:<UserName>@<SIP Domain>
  ```

  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- 如果用户已启用本地 Skype for Business，但在移至 Skype for Business Online 之前未为 企业语音 启用或分配了 LineURI，请为每个用户运行以下 cmdlet：
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- 如果用户已在本地 Skype for Business中启用，但没有为 企业语音 启用，即使已分配 LineURI，请为每个受影响的用户运行以下 cmdlet：
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true
  ```