---
title: 为用户启用联机企业语音和电话系统语音邮件
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
description: 了解如何为电话系统启用语音Skype for Business服务。
ms.openlocfilehash: fea5da3bb82281c05edd73ce8e69c7164440513080b7aa804b31abc5d4c65ba7
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54289070"
---
# <a name="enable-users-for-enterprise-voice-online-and-phone-system-voicemail"></a>为用户启用联机企业语音和电话系统语音邮件
 
> [!Important]
> Skype for BusinessOnline 将于 2021 年 7 月 31 日停用，此后服务将不再可用。  此外，将不再支持通过 Skype for Business Server 或云连接器版本与 Skype for Business Online 本地环境之间的 PSTN 连接。  了解如何使用直接路由将本地电话网络Teams[到呼叫。](/MicrosoftTeams/direct-routing-landing-page)

了解如何为电话系统启用语音Skype for Business服务。
  
使用本地 PSTN 电话系统部署客户端的最后一步是为用户启用 电话系统 和语音邮件。 若要启用这些功能，您必须是具有全局管理员角色的用户，并且能够运行远程 PowerShell。 对于尚未启用 Skype for Business Online 的所有用户帐户，你需要企业语音步骤。
  
## <a name="enable-phone-system-voice-services"></a>启用电话系统语音服务

若要为用户启用 电话系统 语音和语音邮件，需要执行一些初始步骤，例如检查服务器上是否部署了 Skype for Business Online Connector，并启用托管语音邮件的用户。
  
### <a name="to-enable-your-users-for-phone-system-voice-and-voicemail"></a>为用户启用语音电话系统语音邮件

> [!NOTE]
> Skype for Business联机连接器当前是最新 PowerShell Teams的一部分。
> 如果你使用的是最新的[PowerShell Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/)版本，则无需安装 Skype for Business Online Connector。

1. 在开始之前，请检查Teams服务器上是否安装了 PowerShell 模块。 如果不是，请使用[PowerShell](/microsoftteams/teams-powershell-install)模块安装 中的Teams安装。
    
2. 以Windows PowerShell管理员开始登录。
    
3. 键入以下内容并按 Enter：
    
 ```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```

  
4. 使用 Set-CsUser cmdlet 将 $EnterpriseVoiceEnabled 和 $HostedVoiceMail 属性分配给用户，如下所示：
    
   ```powershell
   Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    例如：
    
   ```powershell
   Set-CsUser -Identity "Bob Kelly" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    > [!NOTE]
    > 您还可以通过用户的 SIP 地址、用户主体名称 (UPN) 、域名和用户名 (domain\username) 以及 Active Directory ("Bob Kelly") 中的 显示名称 来指定用户。 
  
## <a name="update-the-line-uri-and-dial-plan-for-users-enabled-for-phone-system"></a>为已启用呼叫的用户更新线路 URI 和拨号电话系统

本节介绍如何为启用呼叫的用户更新线路 URI 和拨号电话系统。 
  
### <a name="to-update-the-line-uri"></a>更新线路 URI

1. 使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。
    
2. 使用 "开始"菜单 或桌面快捷方式打开Skype for Business Server控制面板。
    
    > [!NOTE]
    > 还可以打开浏览器窗口，然后输入管理员 URL 以打开Skype for Business Server控制面板。 
  
3. 在左侧导航栏中，单击“用户”。
    
4. 在“搜索用户”框中，键入要启用的用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“查找”。
    
5. 在表中，单击Skype for Business更改线路 URI 的用户帐户。
    
6. 单击 **"线路 URI"，** 然后键入唯一的规范化电话号码 (例如 tel：+14255550200) 。 然后单击"**提交"。**
    
## <a name="update-the-dial-plan-using-on-premises-windows-powershell-cmdlets"></a>使用本地部署 cmdlet 更新Windows PowerShell计划

可以使用 Windows PowerShell 和[Grant-CsDialPlan](/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet 分配每用户拨号计划。 可以从 Skype for Business Server 2015 或 Windows PowerShell 的远程会话中运行此 cmdlet。
  
### <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a>将每用户拨号计划分配给单个用户

- 使用 [Grant-CsDialPlan](/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet 将每用户拨号计划 RedmondDialPlan 分配给用户 Ken Myer：
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"
  ```

### <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a>将每用户拨号计划分配给多个用户

- 以下命令将每用户拨号计划 RedmondDialPlan 分配给在 Redmond 市工作的所有用户。 有关此命令中使用的 LdapFilter 参数详细信息，请参阅 [Get-CsUser](/powershell/module/skype/get-csuser?view=skype-ps) cmdlet 的文档：
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"
  ```

> [!NOTE]
> 您可以为联机用户使用全局或用户拨号计划。 不能使用站点拨号计划，因为此类计划仅适用于在本地托管并分配到本地站点的用户。 
  
### <a name="to-unassign-a-per-user-dial-plan"></a>取消分配每用户拨号计划

- 使用 [Grant-CsDialPlan](/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet 取消分配之前分配给 Ken Myer 的任何每用户拨号计划。 取消分配每用户拨号计划后，将自动使用全局拨号计划或分配给其注册器或 PSTN 网关的服务范围拨号计划管理 Ken Myer。 服务范围拨号计划优先于全局拨号计划：
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null
  ```

## <a name="update-the-voice-routing-policies-using-on-premises-windows-powershell-cmdlets"></a>使用本地部署 cmdlet 更新Windows PowerShell策略

本节介绍如何为启用了语音路由的用户更新电话系统。
  
电话系统用户必须分配有语音路由策略，以便成功路由呼叫。 这不同于需要为其分配语音策略以允许呼叫成功路由本地商务语音用户。 语音路由策略应包含 PSTN 用法，这些用法为用户定义授权呼叫电话系统路由。 可以将这些 PSTN 用法从现有语音策略复制到新的语音路由策略。 有关详细信息，请参阅 [New-CsVoiceRoutingPolicy](/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)。
  
> [!NOTE]
> 所有电话系统用户分配同一个名为 BusinessVoice 的联机语音策略，该策略定义允许的呼叫功能;例如，允许同时响铃。 
  
### <a name="to-assign-a-per-user-voice-routing-policy-to-a-single-user"></a>将每用户语音路由策略分配给单个用户

- 使用 [Grant-CsVoiceRoutingPolicy](/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) cmdlet 将每用户语音路由策略 RedmondVoiceRoutingPolicy 分配给用户 Ken Myer：
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName "RedmondVoiceRoutingPolicy"
  ```

### <a name="to-assign-a-per-user-voice-routing-policy-to-multiple-users"></a>将每用户语音路由策略分配给多个用户

- 下一个命令将每用户语音路由策略 RedmondVoiceRoutingPolicy 分配给在 Redmond 市工作的所有用户。 有关此命令中使用的 LdapFilter 参数详细信息，请参阅 [Get-CsUser](/powershell/module/skype/get-csuser?view=skype-ps)。
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsVoiceRoutingPolicy -PolicyName "RedmondVoiceRoutingPolicy"
  ```

    > [!NOTE]
    > 您可以对联机用户使用全局或用户语音路由策略。 不能使用站点语音路由策略，因为这些策略仅适用于在本地托管并分配到本地站点的用户。 
  
### <a name="to-unassign-a-per-user-voice-routing-policy"></a>取消分配每用户语音路由策略

- 使用Grant-CsVoiceRoutingPolicy取消分配之前分配给 Ken Myer 的任何每用户语音路由策略。 取消分配每用户语音路由策略后，将自动使用全局语音路由策略管理 Ken Myer。
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

    有关详细信息，请参阅 [Grant-CsVoiceRoutingPolicy](/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps)。
