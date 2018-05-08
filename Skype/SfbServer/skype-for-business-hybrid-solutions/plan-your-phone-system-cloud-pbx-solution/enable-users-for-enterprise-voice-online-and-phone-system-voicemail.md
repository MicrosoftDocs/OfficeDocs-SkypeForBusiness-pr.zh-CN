---
title: 为用户启用企业语音 online 和 Office 365 语音邮件中的电话系统
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/25/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 28daebcb-c2dc-4338-b2d1-04345ece9c19
description: 了解如何在 Office 365 语音服务的企业用户您 Skype 中启用电话系统。
ms.openlocfilehash: 1810be3f891e1f66e724133732ed16e94a1d8015
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="enable-users-for-enterprise-voice-online-and-phone-system-in-office-365-voicemail"></a>为用户启用企业语音 online 和 Office 365 语音邮件中的电话系统
 
了解如何在 Office 365 语音服务的企业用户您 Skype 中启用电话系统。
  
部署 Office 365 中的电话系统与内部部署 PSTN 连接的最后一步是您为用户启用 Office 365 和语音邮件中的电话系统。 要启用这些功能，你必须是具有 Office 365 全局管理员角色的用户，并且能够运行远程 PowerShell。 对于尚未对 Skype for Business Online 启用企业语音的所有用户帐户，你均需按照本主题中的步骤进行操作。
  
## <a name="enable-phone-system-in-office-365-voice-services"></a>在 Office 365 语音服务中启用电话系统

要为用户启用 Office 365 语音和语音邮件中的电话系统，您将需要执行一些初始的步骤，如检查以的业务 Online Connector 部署在您的服务器上所看到的 Skype 并启用托管语音邮件的用户。
  
### <a name="to-enable-your-users-for-phone-system-in-office-365-voice-and-voicemail"></a>Office 365 语音和语音邮件中将您的用户启用电话系统

1. 在开始之前，检查 Business Online Connector （Windows PowerShell 模块） 的 Skype 部署在前端服务器上。 如果不存在，则可以从[下载中心](https://www.microsoft.com/en-us/download/details.aspx?id=39366)下载。 您可以找到有关使用[配置您的计算机的业务联机管理 Skype](https://technet.microsoft.com/en-us/library/dn362839%28v=ocs.15%29.aspx)在此模块的详细信息。
    
2. 以管理员身份启动 Windows PowerShell。
    
3. 输入以下内容，然后按 Enter：
    
  ```
  Import-Module skypeonlineconnector
  ```

4. 输入以下内容，然后按 Enter：
    
  ```
  $cred = Get-Credential
  ```

    按 Enter 之后，应该会看到“Windows PowerShell 凭据”对话框。
    
5. 键入租户管理员用户名和密码，然后单击“**确定**”。
    
6. 在 PowerShell 窗口中键入以下内容，然后按 Enter：
    
  ```
  $Session = New-CsOnlineSession -Credential $cred -Verbose
  ```

7. 键入以下 cmdlet 导入会话：
    
  ```
  Import-PSSession $Session -AllowClobber
  ```

    上运行时 PowerShell Skype 业务服务器，打开 PowerShell 时已加载本地 Skype 业务 cmdlet。 必须指定-AllowClobber 参数允许 online cmdlet 以覆盖具有相同名称的内部部署 cmdlet。
    
8. 使用 Set-CsUser cmdlet，按如下所述为你的用户分配 $EnterpriseVoiceEnabled 和 $HostedVoiceMail 属性：
    
  ```
  Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
  ```

    例如：
    
  ```
  Set-CsUser -Identity "Bob Kelly" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
  ```

    > [!NOTE]
    > 也可以通过其 SIP 地址、用户主体名称 (UPN)、域名和用户名以及 Active Directory 中的显示名称（“Bob Kelly”）来指定用户。 
  
## <a name="update-the-line-uri-and-dial-plan-for-users-enabled-for-phone-system-in-office-365"></a>更新线路 URI 并启用了 Office 365 中的电话系统的用户的拨号计划

本节介绍如何更新线路 URI 并启用了 Office 365 中的电话系统的用户的拨号计划。 
  
### <a name="to-update-the-line-uri"></a>更新线路 URI

1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 使用“开始”菜单或桌面快捷方式打开 Skype for Business Server 控制面板。
    
    > [!NOTE]
    > 也可以打开浏览器窗口，然后输入管理员 URL 以打开 Skype for Business Server 控制面板。 
  
3. 在左导航栏中，单击“**用户**”。
    
4. 在“**搜索用户**”框中，键入要启用的用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“**查找**”。
    
5. 在表中，单击要更改线路 URI 的 Skype for Business 用户帐户。
    
6. 单击“**线路 URI**”，输入唯一的规范化电话号码（例如，tel:+14255550200）。然后单击“**提交**”。
    
## <a name="update-the-dial-plan-using-on-premises-windows-powershell-cmdlets"></a>使用本地 Windows PowerShell cmdlet 更新拨号计划

您可以分配每用户拨号计划使用 Windows PowerShell 和[Grant-csdialplan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet。 可以从 Skype 业务服务器 2015年或从 Windows PowerShell 远程会话来运行此 cmdlet。
  
### <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a>将每用户拨号计划分配给单个用户

- 使用[Grant-csdialplan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet 向用户 Ken Myer 分配每用户拨号计划 RedmondDialPlan:
    
  ```
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"
  ```

### <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a>将每用户拨号计划分配给多个用户

- 以下命令向在雷德蒙市工作的所有用户分配每用户拨号计划 RedmondDialPlan。 LdapFilter 参数在此命令中使用的详细信息，请参阅文档中的有关[Get-csuser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet:
    
  ```
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"

  ```

> [!NOTE]
> 您可以对在线用户使用“全局”或“用户”拨号计划。不能使用站点拨号计划，因为这些计划仅适用于在本地托管并且分配到本地站点的用户。 
  
### <a name="to-unassign-a-per-user-dial-plan"></a>取消分配每用户拨号计划

- 使用[Grant-csdialplan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet 可以取消分配以前分配给 Ken Myer 任何每用户拨号计划。 在取消分配每用户拨号计划后，将通过以下方式自动管理 Ken Myer：使用全局拨号计划，或使用分配给其注册机构或 PSTN 网关的服务范围拨号计划。 服务范围拨号计划优先于全局拨号计划。
    
  ```
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null
  ```

## <a name="update-the-voice-routing-policies-using-on-premises-windows-powershell-cmdlets"></a>使用本地 Windows PowerShell cmdlet 更新语音路由策略

本节介绍如何更新启用了 Office 365 中的电话系统的用户的语音路由策略。
  
在 Office 365 用户的电话系统必须具有语音路由策略分配给它们的呼叫路由成功。 这与本地业务语音用户不同，本地业务语音用户需要分配有语音策略，然后才能成功路由呼叫。 语音路由策略应包含在 Office 365 用户的电话系统定义授权的呼叫和路由的 PSTN 用法。 您可以将这些 PSTN 用法从现有语音策略复制到新的语音路由策略。 有关详细信息，请参阅[New-csvoiceroutingpolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)。
  
> [!NOTE]
> 在 Office 365 用户的所有电话系统都分配名为它定义的呼叫功能，允许; BusinessVoice 相同 online 语音策略例如，允许同时响铃。 
  
### <a name="to-assign-a-per-user-voice-routing-policy-to-a-single-user"></a>为单个用户分配每用户语音路由策略

- 使用[Grant-csvoiceroutingpolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) cmdlet 向用户 Ken Myer 分配每用户语音路由策略 RedmondVoiceRoutingPolicy:
    
  ```
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName "RedmondVoiceRoutingPolicy"
  ```

### <a name="to-assign-a-per-user-voice-routing-policy-to-multiple-users"></a>为多个用户分配每用户语音路由策略

- 以下命令为在 Redmond 市工作的所有用户分配每用户语音路由策略 RedmondVoiceRoutingPolicy。 LdapFilter 参数在此命令中使用的详细信息，请参阅[Get-csuser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps)。
    
  ```
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsVoiceRoutingPolicy -PolicyName "RedmondVoiceRoutingPolicy"
  ```

    > [!NOTE]
    > 您可以对在线用户使用“全局”或“用户”语音路由策略。不能使用站点语音路由策略，因为这些策略仅适用于在本地托管并且分配到本地站点的用户。 
  
### <a name="to-unassign-a-per-user-voice-routing-policy"></a>取消分配每用户语音路由策略

- 使用 Grant-csvoiceroutingpolicy 取消分配以前分配给 Ken myer 的用户的任何每用户语音路由策略。 在取消分配每用户语音路由策略之后，将自动使用全局语音路由策略来管理 Ken Myer。
    
  ```
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

    有关详细信息，请参阅[Grant-csvoiceroutingpolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps)。
    

