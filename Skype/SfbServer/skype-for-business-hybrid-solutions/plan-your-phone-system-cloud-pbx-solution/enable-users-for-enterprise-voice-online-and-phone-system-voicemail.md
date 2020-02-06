---
title: 为用户启用联机企业语音和 Office 365 电话系统语音邮件
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
description: 了解如何为 Skype for Business 用户启用 Office 365 语音服务中的电话系统。
ms.openlocfilehash: f4fdd2a9a3da58f6804fa65acf96ba2b8fac682e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802202"
---
# <a name="enable-users-for-enterprise-voice-online-and-phone-system-in-office-365-voicemail"></a>为用户启用联机企业语音和 Office 365 电话系统语音邮件
 
了解如何为 Skype for Business 用户启用 Office 365 语音服务中的电话系统。
  
使用本地 PSTN 连接在 Office 365 中部署手机系统的最后一步是在 Office 365 和语音邮件中为手机系统启用用户。 要启用这些功能，你必须是具有 Office 365 全局管理员角色的用户，并且能够运行远程 PowerShell。 对于尚未对 Skype for Business Online 启用企业语音的所有用户帐户，你均需按照本主题中的步骤进行操作。
  
## <a name="enable-phone-system-in-office-365-voice-services"></a>在 Office 365 语音服务中启用电话系统

若要在 Office 365 语音和语音邮件中为电话系统启用用户，需要执行一些初始步骤，例如检查是否在服务器上部署了 Skype for Business Online 连接器以及是否允许用户使用托管的语音邮件。
  
### <a name="to-enable-your-users-for-phone-system-in-office-365-voice-and-voicemail"></a>在 Office 365 语音和语音邮件中为您的用户启用电话系统

1. 开始之前，请检查您的前端服务器上是否已部署 Skype for business Online 连接器（Windows PowerShell 模块）。 如果不是，则可以从[下载中心](https://www.microsoft.com/en-us/download/details.aspx?id=39366)下载它。 在[配置计算机以使用 Skype For Business Online 管理](https://technet.microsoft.com/en-us/library/dn362839%28v=ocs.15%29.aspx)时，可以找到有关使用此模块的详细信息。
    
2. 以管理员身份启动 Windows PowerShell。
    
3. 输入以下内容，然后按 Enter：
    
   ```powershell
   Import-Module skypeonlineconnector
   ```

4. 输入以下内容，然后按 Enter：
    
   ```powershell
   $cred = Get-Credential
   ```

    按 Enter 之后，应该会看到“Windows PowerShell 凭据”对话框。
    
5. 键入租户管理员用户名和密码，然后单击“**确定**”。
    
6. 在 PowerShell 窗口中键入以下内容，然后按 Enter：
    
   ```powershell
   $Session = New-CsOnlineSession -Credential $cred -Verbose
   ```

7. 键入以下 cmdlet 导入会话：
    
   ```powershell
   Import-PSSession $Session -AllowClobber
   ```

    在 Skype for business 服务器上运行 PowerShell 时，在打开 PowerShell 时已加载本地 Skype for business cmdlet。 必须指定-AllowClobber 参数以允许联机 cmdlet 覆盖具有相同名称的本地 cmdlet。
    
8. 使用 Set-CsUser cmdlet，按如下所述为你的用户分配 $EnterpriseVoiceEnabled 和 $HostedVoiceMail 属性：
    
   ```powershell
   Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    例如：
    
   ```powershell
   Set-CsUser -Identity "Bob Kelly" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    > [!NOTE]
    > 也可以通过其 SIP 地址、用户主体名称 (UPN)、域名和用户名以及 Active Directory 中的显示名称（“Bob Kelly”）来指定用户。 
  
## <a name="update-the-line-uri-and-dial-plan-for-users-enabled-for-phone-system-in-office-365"></a>更新在 Office 365 中为手机系统启用的用户的行 URI 和拨号计划

本部分介绍如何更新在 Office 365 中为电话系统启用的用户的行 URI 和拨号计划。 
  
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

你可以使用 Windows PowerShell 和[CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet 分配每用户拨号计划。 你可以从 Skype for Business Server 2015 或 Windows PowerShell 的远程会话中运行此 cmdlet。
  
### <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a>将每用户拨号计划分配给单个用户

- 使用[CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet 将每用户拨号计划 RedmondDialPlan 分配给用户 Ken Myer：
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"
  ```

### <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a>将每用户拨号计划分配给多个用户

- 以下命令向在雷德蒙市工作的所有用户分配每用户拨号计划 RedmondDialPlan。 有关此命令中使用的 LdapFilter 参数的详细信息，请参阅[move-csuser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet 的文档：
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"
  ```

> [!NOTE]
> 您可以对在线用户使用“全局”或“用户”拨号计划。不能使用站点拨号计划，因为这些计划仅适用于在本地托管并且分配到本地站点的用户。 
  
### <a name="to-unassign-a-per-user-dial-plan"></a>取消分配每用户拨号计划

- 使用[CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet 取消分配以前分配给 Ken Myer 的任何每用户拨号计划。 在取消分配每用户拨号计划后，将通过以下方式自动管理 Ken Myer：使用全局拨号计划，或使用分配给其注册机构或 PSTN 网关的服务范围拨号计划。 服务范围拨号计划优先于全局拨号计划。
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null
  ```

## <a name="update-the-voice-routing-policies-using-on-premises-windows-powershell-cmdlets"></a>使用本地 Windows PowerShell cmdlet 更新语音路由策略

本部分介绍如何为在 Office 365 中启用电话系统的用户更新语音路由策略。
  
Office 365 用户中的电话系统必须分配有语音路由策略才能使呼叫成功路由。 这与本地业务语音用户不同，本地业务语音用户需要分配有语音策略，然后才能成功路由呼叫。 语音路由策略应包含用于定义 Office 365 用户中的电话系统的授权呼叫和路线的 PSTN 用法。 您可以将这些 PSTN 用法从现有语音策略复制到新的语音路由策略。 有关更多信息，请参阅 [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)。
  
> [!NOTE]
> Office 365 用户中的所有电话系统都分配有相同的名为 BusinessVoice 的在线语音策略，该策略定义允许的呼叫功能;例如，允许同时拨打。 
  
### <a name="to-assign-a-per-user-voice-routing-policy-to-a-single-user"></a>为单个用户分配每用户语音路由策略

- 使用[CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) cmdlet 将每用户语音路由策略 RedmondVoiceRoutingPolicy 分配给用户 Ken Myer：
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName "RedmondVoiceRoutingPolicy"
  ```

### <a name="to-assign-a-per-user-voice-routing-policy-to-multiple-users"></a>为多个用户分配每用户语音路由策略

- 以下命令为在 Redmond 市工作的所有用户分配每用户语音路由策略 RedmondVoiceRoutingPolicy。 有关此命令中使用的 LdapFilter 参数的详细信息，请参阅[move-csuser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps)。
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsVoiceRoutingPolicy -PolicyName "RedmondVoiceRoutingPolicy"
  ```

    > [!NOTE]
    > 您可以对在线用户使用“全局”或“用户”语音路由策略。不能使用站点语音路由策略，因为这些策略仅适用于在本地托管并且分配到本地站点的用户。 
  
### <a name="to-unassign-a-per-user-voice-routing-policy"></a>取消分配每用户语音路由策略

- 使用 "授权-CsVoiceRoutingPolicy" 取消分配以前分配给 Ken Myer 的任何每用户语音路由策略。 在取消分配每用户语音路由策略之后，将自动使用全局语音路由策略来管理 Ken Myer。
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

    有关详细信息，请参阅 [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps)。
    

