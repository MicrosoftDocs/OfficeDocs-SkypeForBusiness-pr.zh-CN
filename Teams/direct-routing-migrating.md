---
title: 迁移到直接路由
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
appliesto:
- Microsoft Teams
description: 了解从 Skype for Business Online 和团队配置角度迁移到直接路由需要做什么。
ms.openlocfilehash: 49980a0364e729fc41e6fe716de336a8a28f85bb
ms.sourcegitcommit: c554b09527817dc3e06b10509f6668b42ccc5cb9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/17/2019
ms.locfileid: "35759005"
---
# <a name="migrate-to-direct-routing"></a>迁移到直接路由

本文介绍从 Skype for Business Online 和 Microsoft 团队配置角度迁移到直接路由所需的内容。 本文介绍从以下各项进行迁移: 
 
- 带有呼叫计划 (适用于团队和 Skype for business Online) 的 Office 365 电话系统 
- 在 Skype for business 服务器中具有本地 PSTN 连接的 Office 365 电话系统 (适用于 Skype for business Online)  
- 通过使用云连接器版本 (适用于 Skype for business Online) 使用本地 PSTN 连接的 Office 365 电话系统

  
除了这些配置步骤之外, 还需要在会话边界控制器 (SBC) 上配置, 以将呼叫路由到新路由。 超出本文档范围的范围。 有关详细信息, 请参阅 SBC 供应商的文档。  

## <a name="user-provisioning-end-state-for-various-pstn-connectivity-options"></a>各种 PSTN 连接选项的用户预配结束状态 

下表显示了为使用 Office 365 电话系统的选定 PSTN 连接选项设置的用户的结束状态。 仅显示与语音相关的属性。

|用户对象属性 |带有呼叫计划的电话系统|通过 Skype for Business Server 进行本地 PSTN 连接的电话系统|通过云连接器进行本地 PSTN 连接的电话系统|通过直接路由使用本地 PSTN 连接的电话系统|
|---|---|---|---|---|
|客户端|Skype for Business 或团队 |Skype for Business |Skype for Business |Teams|
|协议|在线 Skype 企业版</br>计划2</br></br>MCOProfessional 或 MCOSTANDARD)</br></br></br>电话系统 (MCOEV)</br></br></br>通话套餐</br>团队|Skype 商业在线计划 2 (MCOProfessional 或 MCOSTANDARD)</br></br></br>电话系统 (MCOEV)|Skype 商业在线计划 2 (MCOProfessional 或 MCOSTANDARD)</br></br></br>电话系统 (MCOEV)|Skype 商业在线计划 2 (MCOProfessional 或 MCOSTANDARD</br></br></br>电话系统 (MCOEV)</br></br>团队|
OnPremLineURI |不适用|电话号码必须从本地广告同步。 |可以在本地 Active Directory 或 Azure Active Directory 中管理电话号码。|可以在本地 Active Directory 或 Azure Active Directory 中管理电话号码。 但是, 如果组织具有本地 Skype for Business, 则该号码必须从本地 Active Directory 同步。|
|LineURI|PSTN 呼叫电话号码|从 OnPremLineURI 参数自动设置|从 OnPremLineURI 参数自动设置|从 OnPremLineURI 参数自动设置|
|EnterpriseVoiceEnabled|True|True|True|True|
|HostedVoiceMail |True|True|True|True|
|VoicePolicy|BusinessVoice|HybridVoice|HybridVoice|HybridVoice|
|HostedVoiceMailPolicy |BusinessVoice|BusinessVoice|BusinessVoice|BusinessVoice|
|VoiceRoutingPolicy|具有值|具有值|具有值|不适用|
|OnlineVoiceRoutingPolicy|$Null|$Null|$Null|具有值|
|TeamsUpgradePolicy<sup>1</sup>|TeamsOnly、SfBOnly 或孤岛|$Null|$Null|岛或 TeamsOnly|
|TeamsInterPolicy<sup>2</sup></br>CallingDefaultClient –请阅读下面的说明。|团队或 SfB |SfB|SfB|团队|
|TeamsCallingPolicy</br>AllowPrivateCalling|True|不适用|不适用|True|
|TeamsCallingPolicy</br>AllowGroupCalling|True|不适用|不适用|True|
||||||

<sup>1</sup>选择 TeamsUpgradePolicy 的正确模式取决于方案。 请阅读有关将[团队与 Skype For business 结合使用的组织的迁移和互操作性指南](migration-interop-guidance-for-teams-with-skype.md)中的语音体验。

<sup>2</sup>在以前宣布的情况下, TeamsInteropPolicy 将停用 (针对 Q3 年底), 其功能将合并到 TeamsUpgradePolicy 中。 互操作和迁移将使用由 TeamsUpgradePolicy 确定的 "共存模式" 进行管理, 现已推出。 用户模式的选择将控制传入呼叫和聊天以及用户可以发起聊天和呼叫或安排会议的客户端的两个路由。 TeamsInteropPolicy 将停用, 在 phaseout 期间, 仍需要与 TeamsUpgradePolicy 并行设置。  

作为此工作的一部分, Microsoft 最近更新了 "Microsoft 团队管理中心" (也称为新式门户), 以基于共存模式反映新的管理模型。 在新式门户中, 配置 TeamsUpgradePolicy 现在还会自动将 TeamsInteropPolicy 设置为一致的值, 因此 TeamsInteropPolicy 在用户界面中不再公开。 但是, 使用 PowerShell 的管理员仍然必须同时设置 TeamsUpgradePolicy 和 TeamsInteropPolicy, 以确保正确路由。 转换到 TeamsUpgradePolicy 后, 将不再需要设置 TeamsInteropPolicy。

有关详细信息, 请参阅[与 Skype For business 一起使用团队的组织的迁移和互操作指南](migration-interop-guidance-for-teams-with-skype.md)。

## <a name="migrating-from-calling-plans"></a>从通话计划迁移

有关从通话计划迁移的详细信息, 请参阅:

- [设置通话套餐](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)
- [Set-CsOnlineVoice 用户](https://docs.microsoft.com/powershell/module/skype/Set-CsOnlineVoiceUser?view=skype-ps)
- [CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/get-csonlinelislocation?view=skype-ps)  
 
 
建议你删除以前配置的授权计划信息, 如下所示:
 
```
$companyname = “contoso” 
$lic1 = $companyname + “:MCOPSTN1” 
$lic2 = $companyname + “:MCOPSTN2” 
Set-MsolUserLicense -UserPrincipalName <UPN> -RemoveLicenses $lic1 
Set-MsolUserLicense -UserPrincipalName <UPN> -RemoveLicenses $lic2 
```
## <a name="migrating-from-office-365-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>在 Skype for business Server 中通过本地 PSTN 连接从 Office 365 Phone 系统迁移

有关在 Skype for Business Server 中通过本地 PSTN 连接从电话系统迁移的详细信息, 请参阅以下内容:

- [规划](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)
- [部署](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-phone-system) 

建议您删除以前配置的语音路由信息, 如下所示:

```
Grant-CsVoiceRoutingPolicy -PolicyName $NULL -Identity <UPN> 
```
## <a name="migrating-from-office-365-phone-system-with-on-premises-pstn-connectivity-via-cloud-connector-edition"></a>通过云连接器版本通过本地 PSTN 连接从 Office 365 Phone 系统迁移 

有关通过云连接器使用本地 PSTN 连接从手机系统迁移的详细信息, 请参阅以下内容:

- [规划](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition)  
- [部署](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-phone-system)
- [用户配置](https://docs.microsoft.com/powershell/module/skype/set-csuserpstnsettings?view=skype-ps) 

建议您删除以前配置的语音路由信息, 如下所示:
 
```
Grant-CsVoiceRoutingPolicy -PolicyName $NULL -Identity <UPN> 
Set-CsUserPstnSettings -Identity <UPN> -AllowInternationalCalls $false -HybridPSTNSite $null 
```


## <a name="related-links"></a>相关链接

[面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导](migration-interop-guidance-for-teams-with-skype.md)

[授权-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy)

[CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsTeamsUpgradePolicy)

[新-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsTeamsUpgradePolicy)

[Remove-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsTeamsUpgradePolicy)

[Set-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsUpgradePolicy)

[CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTeamsUpgradeConfiguration)

[Set-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsUpgradeConfiguration)

