---
title: 为用户启用企业语音在线和电话系统语音邮件
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/25/2017
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
ms.assetid: 28daebcb-c2dc-4338-b2d1-04345ece9c19
description: 了解如何为你的 Skype for Business 用户启用电话系统语音服务。
ms.openlocfilehash: 522da56969f851280812670692a27d94e4df09a8
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221102"
---
# <a name="enable-users-for-enterprise-voice-online-and-phone-system-voicemail"></a>为用户启用企业语音在线和电话系统语音邮件
 
了解如何为你的 Skype for Business 用户启用电话系统语音服务。
  
部署具有本地 PSTN 连接的电话系统的最后一步是为用户启用电话系统和语音邮件。 若要启用这些功能，您必须是具有全局管理员角色的用户，并且能够运行远程 PowerShell。 对于尚未为 Skype for business Online 启用企业语音的所有用户帐户，您需要按照本主题中的步骤操作。
  
## <a name="enable-phone-system-voice-services"></a>启用电话系统语音服务

若要为用户启用电话系统语音和语音邮件，您需要执行一些初始步骤，如检查是否在服务器上部署了 Skype for Business Online 连接器以及是否为您的用户启用托管的语音邮件。
  
### <a name="to-enable-your-users-for-phone-system-voice-and-voicemail"></a>为用户启用电话系统语音和语音邮件

1. 在开始之前，请检查是否在前端服务器上部署了 Skype for Business Online 连接器（Windows PowerShell 模块）。 如果不是，则可以从[下载中心](https://www.microsoft.com/download/details.aspx?id=39366)下载它。 您可以在[为计算机配置 Skype for Business Online 管理](https://technet.microsoft.com/library/dn362839%28v=ocs.15%29.aspx)中找到有关使用此模块的详细信息。
    
2. 以管理员身份启动 Windows PowerShell。
    
3. 键入以下命令，然后按 Enter：
    
   ```powershell
   Import-Module skypeonlineconnector
   ```

4. 键入以下命令，然后按 Enter：
    
   ```powershell
   $cred = Get-Credential
   ```

    按 Enter 后，您应该会看到 "Windows PowerShell 凭据" 对话框。
    
5. 键入租户管理员用户名和密码，然后单击 **"确定"**。
    
6. 在 PowerShell 窗口中，键入以下命令，然后按 Enter：
    
   ```powershell
   $Session = New-CsOnlineSession -Credential $cred -Verbose
   ```

7. 通过键入以下 cmdlet 导入会话：
    
   ```powershell
   Import-PSSession $Session -AllowClobber
   ```

    在 Skype for business 服务器上运行 PowerShell 时，在打开 PowerShell 时，本地 Skype for Business cmdlet 已加载。 您必须指定-AllowClobber 参数，以允许联机 cmdlet 覆盖具有相同名称的本地 cmdlet。
    
8. 使用 Get-csuser cmdlet 将 $EnterpriseVoiceEnabled 和 $HostedVoiceMail 属性分配给用户，如下所示：
    
   ```powershell
   Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    例如：
    
   ```powershell
   Set-CsUser -Identity "Bob Kelly" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    > [!NOTE]
    > 您还可以通过其 SIP 地址、用户主体名称（UPN）、域名和用户名（域 \ 用户名）以及 Active Directory 中的显示名称（"Bob 凯利"）来指定用户。 
  
## <a name="update-the-line-uri-and-dial-plan-for-users-enabled-for-phone-system"></a>为已为电话系统启用的用户更新线路 URI 和拨号计划

本节介绍如何为启用了电话系统的用户更新线路 URI 和拨号计划。 
  
### <a name="to-update-the-line-uri"></a>更新线路 URI

1. 使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。
    
2. 使用 "开始" 菜单或桌面快捷方式打开 Skype for Business Server 控制面板。
    
    > [!NOTE]
    > 您还可以打开浏览器窗口，然后输入管理员 URL 以打开 Skype for Business Server 控制面板。 
  
3. 在左侧导航栏中，单击“用户”****。
    
4. 在“搜索用户”**** 框中，键入要启用的用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“查找”****。
    
5. 在表中，单击要更改行 URI 的 Skype for Business 用户帐户。
    
6. 单击 "**线路 URI**"，然后键入唯一的规范化电话号码（例如，电话： + 14255550200）。 然后单击 "**提交**"。
    
## <a name="update-the-dial-plan-using-on-premises-windows-powershell-cmdlets"></a>使用本地 Windows PowerShell cmdlet 更新拨号计划

您可以使用 Windows PowerShell 和[grant-csdialplan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet 分配每用户拨号计划。 您可以从 Skype for Business Server 2015 或从 Windows PowerShell 的远程会话中运行此 cmdlet。
  
### <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a>为单个用户分配每用户拨号计划

- 使用[grant-csdialplan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet 可将每用户拨号计划 RedmondDialPlan 分配给用户 Ken Myer：
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"
  ```

### <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a>将每用户拨号计划分配给多个用户

- 以下命令将每用户拨号计划 RedmondDialPlan 分配给在 Redmond 市工作的所有用户。 有关此命令中使用的 LdapFilter 参数的详细信息，请参阅[get-csuser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet 的文档：
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"
  ```

> [!NOTE]
> 您可以为联机用户使用全局或用户拨号计划。 无法使用网站拨号计划，因为这些计划仅适用于在本地托管并且分配到本地网站的用户。 
  
### <a name="to-unassign-a-per-user-dial-plan"></a>取消分配每用户拨号计划

- 使用[grant-csdialplan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet 可以取消分配之前分配给 Ken Myer 的任何每用户拨号计划。 未分配每用户拨号计划后，将使用分配给他/她的注册机构或 PSTN 网关的全局拨号计划或服务范围拨号计划自动管理 Ken Myer。 服务范围拨号计划优先于全局拨号计划：
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null
  ```

## <a name="update-the-voice-routing-policies-using-on-premises-windows-powershell-cmdlets"></a>使用本地 Windows PowerShell cmdlet 更新语音路由策略

本节介绍如何更新为电话系统启用的用户的语音路由策略。
  
电话系统用户必须为其分配一个语音路由策略，以便呼叫能够成功路由。 这与需要向其分配语音策略以允许呼叫成功路由的本地业务语音用户不同。 语音路由策略应包含 PSTN 用法，用于定义电话系统用户的授权呼叫和路由。 您可以将这些 PSTN 用法从现有语音策略复制到新的语音路由策略。 有关详细信息，请参阅[grant-csvoiceroutingpolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)。
  
> [!NOTE]
> 所有电话系统用户都被分配了名为 BusinessVoice 的相同联机语音策略，该策略定义了允许的呼叫功能;例如，允许同时响铃。 
  
### <a name="to-assign-a-per-user-voice-routing-policy-to-a-single-user"></a>向单个用户分配每用户语音路由策略

- 使用[grant-csvoiceroutingpolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) cmdlet 可将每用户语音路由策略 RedmondVoiceRoutingPolicy 分配给用户 Ken Myer：
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName "RedmondVoiceRoutingPolicy"
  ```

### <a name="to-assign-a-per-user-voice-routing-policy-to-multiple-users"></a>为多个用户分配每用户语音路由策略

- 下一个命令向在 Redmond 市工作的所有用户分配每用户语音路由策略 RedmondVoiceRoutingPolicy。 有关此命令中使用的 LdapFilter 参数的详细信息，请参阅[get-csuser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps)。
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsVoiceRoutingPolicy -PolicyName "RedmondVoiceRoutingPolicy"
  ```

    > [!NOTE]
    > 您可以对联机用户使用全局或用户语音路由策略。 无法使用站点语音路由策略，因为这些策略仅适用于在本地托管并且分配到本地站点的用户。 
  
### <a name="to-unassign-a-per-user-voice-routing-policy"></a>取消分配每用户语音路由策略

- 使用 Grant-csvoiceroutingpolicy 可取消分配之前分配给 Ken Myer 的任何每用户语音路由策略。 在未分配每用户语音路由策略之后，将自动使用全局语音路由策略管理 Ken Myer。
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

    有关详细信息，请参阅[grant-csvoiceroutingpolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps)。
    

