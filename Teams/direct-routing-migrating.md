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
- M365-voice
appliesto:
- Microsoft Teams
description: 从 Skype for Business Online 和 Teams 配置角度了解迁移到直接路由所需的内容。
ms.openlocfilehash: 9fb644c938c61fd9dd1c78362ad90bfe855e97ec
ms.sourcegitcommit: 4a4ed872eff22663720296ae29c0e644286857f2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2019
ms.locfileid: "37572175"
---
# <a name="migrate-to-direct-routing"></a>迁移到直接路由

本文从 Skype for Business Online 和 Microsoft Teams 配置角度描述迁移到直接路由所需的内容。 本文介绍了如何从以下各项进行迁移： 
 
- Office 365 电话系统，含通话套餐（适用于 Teams 和 Skype for Business Online） 
- 使用 Skype for Business Server 中本地 PSTN 连接的 Office 365 电话系统（适用于 Skype for Business Online）
  
- 通过使用云连接器版本使用本地 PSTN 连接的 Office 365 电话系统（适用于 Skype for Business Online）


  
除了这些配置步骤外，还需要在会话边界控制器 (SBC) 上进行配置，才能将通话转接到新的路由。 那超出了本文档的范畴。 有关详细信息，请参阅 SBC 供应商文档。  

## <a name="user-provisioning-end-state-for-various-pstn-connectivity-options"></a>用于各种 PSTN 连接选项的用户预配结束状态 

下表显示了为 Office 365 电话系统选定 PSTN 连接选项配置的用户预配结束状态。 仅显示与语音相关的属性。

|用户对象属性 |具有通话套餐的电话系统|通过 Skype for Business Server 使用本地 PSTN 连接的电话系统
|通过云连接器使用本地 PSTN 连接的电话系统|通过直接路由使用本地 PSTN 连接的电话系统|
|---|---|---|---|---|
|客户端|Skype For Business 或 Teams |Skype for Business |Skype for Business |Teams|
|许可证|Skype Business Online</br>套餐 2</br></br>MCOProfessional 或 MCOSTANDARD）</br></br></br>电话系统 (MCOEV)</br></br></br>通话套餐</br>Teams|Skype Business Online 套餐 2（MCOProfessional 或 MCOSTANDARD）</br></br></br>电话系统 (MCOEV)|Skype Business Online 套餐 2（MCOProfessional 或 MCOSTANDARD）</br></br></br>电话系统 (MCOEV)|Skype Business Online 套餐 2（MCOProfessional 或 MCOSTANDARD</br></br></br>电话系统 (MCOEV)</br></br>Teams|
OnPremLineURI |不适用|电话号码必须与本地 AD 同步。 |可在本地 Active Directory 或 Azure Active Directory 中管理电话号码。|可在本地 Active Directory 或 Azure Active Directory 中管理电话号码。 但是，如果组织有本地 Skype for Business，则该号码必须与本地 Active Directory 同步。|
|LineURI|PSTN 通话电话号码|从 OnPremLineURI 参数自动设置|从 OnPremLineURI 参数自动设置|从 OnPremLineURI 参数自动设置|
|EnterpriseVoiceEnabled|True|True|True|True|
|HostedVoiceMail |True|True|True|True|
|VoicePolicy|BusinessVoice|HybridVoice|HybridVoice|HybridVoice|
|HostedVoiceMailPolicy |BusinessVoice|BusinessVoice|BusinessVoice|BusinessVoice|
|VoiceRoutingPolicy|具有值|具有值|具有值|不适用|
|OnlineVoiceRoutingPolicy|$Null|$Null|$Null|具有值|
|TeamsUpgradePolicy<sup>1</sup>|TeamsOnly, SfBOnly|$Null|$Null|TeamsOnly|
|TeamsCallingPolicy</br>AllowPrivateCalling|True|不适用|不适用|True|
|TeamsCallingPolicy</br>AllowGroupCalling|True|不适用|不适用|True|
||||||

<sup>1</sup>选择合适的 TeamsUpgradePolicy 模式取决于场景。 请阅读了解[面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导](migration-interop-guidance-for-teams-with-skype.md)中各种模式的语音体验。

作为此工作的一部分，Microsoft 最近更新了“Microsoft Teams 管理中心”（也称为“新式门户”），以反映基于共存模式的新管理模型。 在新式门户中，配置 TeamsUpgradePolicy 也会立即将 TeamsInteropPolicy 自动设置为一致的值，因此不会再在用户界面中公开 TeamsInteropPolicy。 但是，使用 PowerShell 的管理员仍然必须同时设置 TeamsUpgradePolicy 和 TeamsInteropPolicy，以确保正确转接。 完成到 TeamsUpgradePolicy 的转换后，将不再需要设置 TeamsInteropPolicy。

有关详细信息，请参阅[面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导](migration-interop-guidance-for-teams-with-skype.md)。

## <a name="migrating-from-calling-plans"></a>从通话套餐迁移

有关从通话套餐迁移的详细信息，请参阅：

- [设置通话套餐](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)
- [Set-CsOnlineVoice 用户](https://docs.microsoft.com/powershell/module/skype/Set-CsOnlineVoiceUser?view=skype-ps)
- [Get-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/get-csonlinelislocation?view=skype-ps)  
 
 
建议删除以前配置的许可证计划信息，如下所示：
 
```
$companyname = “contoso” 
$lic1 = $companyname + “:MCOPSTN1” 
$lic2 = $companyname + “:MCOPSTN2” 
Set-MsolUserLicense -UserPrincipalName <UPN> -RemoveLicenses $lic1 
Set-MsolUserLicense -UserPrincipalName <UPN> -RemoveLicenses $lic2 
```
## <a name="migrating-from-office-365-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>在 Skype for Business Server 中使用本地 PSTN 连接从 Office 365 电话系统迁移


有关在 Skype for Business Server 中使用本地 PSTN 连接从电话系统迁移的详细信息，请参阅以下内容：


- [规划](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)
- [部署](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-phone-system) 

建议删除以前配置的语音转接信息，如下所示：

```
Grant-CsVoiceRoutingPolicy -PolicyName $NULL -Identity <UPN> 
```
## <a name="migrating-from-office-365-phone-system-with-on-premises-pstn-connectivity-via-cloud-connector-edition"></a>通过云连接器版本使用本地 PSTN 连接从 Office 365 电话系统迁移
 

有关通过云连接器版本使用本地 PSTN 连接从电话系统迁移的详细信息，请参阅以下内容：


- [规划](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition)  
- [部署](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-phone-system)
- [用户配置](https://docs.microsoft.com/powershell/module/skype/set-csuserpstnsettings?view=skype-ps) 

建议删除以前配置的语音转接信息，如下所示：
 
```
Grant-CsVoiceRoutingPolicy -PolicyName $NULL -Identity <UPN> 
Set-CsUserPstnSettings -Identity <UPN> -AllowInternationalCalls $false -HybridPSTNSite $null 
```


## <a name="related-links"></a>相关链接

[面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导](migration-interop-guidance-for-teams-with-skype.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy)

[Get-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsTeamsUpgradePolicy)

[New-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsTeamsUpgradePolicy)

[Remove-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsTeamsUpgradePolicy)

[Set-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsUpgradePolicy)

[Get-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTeamsUpgradeConfiguration)

[Set-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsUpgradeConfiguration)

