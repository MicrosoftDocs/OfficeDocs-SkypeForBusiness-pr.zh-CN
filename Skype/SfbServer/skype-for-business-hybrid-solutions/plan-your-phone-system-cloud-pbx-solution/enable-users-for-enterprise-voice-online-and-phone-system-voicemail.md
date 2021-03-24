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
description: 了解如何为 Skype for Business 用户启用电话系统语音服务。
ms.openlocfilehash: f1c59505073a7113407f28b7ebbe3a323724782e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098568"
---
# <a name="enable-users-for-enterprise-voice-online-and-phone-system-voicemail"></a>为用户启用联机企业语音和电话系统语音邮件
 
> [!Important]
> Skype for Business Online 将于 2021 年 7 月 31 日停用，此后服务将不再可用。  此外，将不再支持本地环境（无论是通过 Skype for Business Server 还是云连接器版本与 Skype for Business Online）之间的 PSTN 连接。  了解如何使用直接路由将本地电话网络连接到[Teams。](/MicrosoftTeams/direct-routing-landing-page)

了解如何为 Skype for Business 用户启用电话系统语音服务。
  
使用本地 PSTN 连接部署电话系统的最后一步是为用户启用电话系统和语音邮件。 若要启用这些功能，您必须是具有全局管理员角色的用户，并且能够运行远程 PowerShell。 你需要对尚未启用 Skype for Business Online 的所有用户帐户企业语音本主题中的步骤。
  
## <a name="enable-phone-system-voice-services"></a>启用电话系统语音服务

若要为用户启用电话系统语音和语音邮件，你需要执行一些初始步骤，例如检查 Skype for Business Online 连接器是否部署在你的服务器上，并启用你的用户托管语音邮件。
  
### <a name="to-enable-your-users-for-phone-system-voice-and-voicemail"></a>为用户启用电话系统语音和语音邮件

> [!NOTE]
> Skype for Business Online Connector 当前是最新的 Teams PowerShell 模块的一部分。
> 如果你使用的是最新的 [Teams PowerShell 公共版本](https://www.powershellgallery.com/packages/MicrosoftTeams/)，则无需安装 Skype for Business Online 连接器。

1. 开始之前，请检查前端服务器上是否安装了 Teams PowerShell 模块。 如果没有，请按照 Teams PowerShell 模块安装 [中的说明安装](/microsoftteams/teams-powershell-install)。
    
2. 以Windows PowerShell开始登录。
    
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
  
## <a name="update-the-line-uri-and-dial-plan-for-users-enabled-for-phone-system"></a>更新为电话系统启用的用户的线路 URI 和拨号计划

本节介绍如何更新为电话系统启用的用户的线路 URI 和拨号计划。 
  
### <a name="to-update-the-line-uri"></a>更新线路 URI

1. 使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。
    
2. 使用"开始"菜单或桌面快捷方式打开 Skype for Business Server 控制面板。
    
    > [!NOTE]
    > 还可以打开浏览器窗口，然后输入管理员 URL 以打开 Skype for Business Server 控制面板。 
  
3. 在左侧导航栏中，单击“用户”。
    
4. 在“搜索用户”框中，键入要启用的用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“查找”。
    
5. 在表中，单击要更改线路 URI 的 Skype for Business 用户帐户。
    
6. 单击 **"线路 URI"，** 然后键入唯一的规范化电话号码 (例如 tel：+14255550200) 。 然后单击"**提交"。**
    
## <a name="update-the-dial-plan-using-on-premises-windows-powershell-cmdlets"></a>使用本地部署 cmdlet 更新Windows PowerShell计划

可以使用 Windows PowerShell 和 [Grant-CsDialPlan](/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet 分配每用户拨号计划。 可以从 Skype for Business Server 2015 或远程会话运行此 cmdlet Windows PowerShell。
  
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

本节介绍如何更新为电话系统启用的用户的语音路由策略。
  
电话系统用户必须分配有语音路由策略，以便成功路由呼叫。 这不同于需要为其分配语音策略以允许呼叫成功路由本地商务语音用户。 语音路由策略应包含 PSTN 用法，用于定义电话系统用户的授权呼叫和路由。 可以将这些 PSTN 用法从现有语音策略复制到新的语音路由策略。 有关详细信息，请参阅 [New-CsVoiceRoutingPolicy](/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)。
  
> [!NOTE]
> 所有电话系统用户都分配有同一个名为 BusinessVoice 的联机语音策略，该策略定义允许的呼叫功能;例如，允许同时响铃。 
  
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
