---
title: 迁移到直接路由
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 了解什么需要迁移到直接路由从 Skype 业务联机和团队配置角度。
ms.openlocfilehash: 4a1cb3d96d6f5d024b8da6a42288b09b3a8cde3d
ms.sourcegitcommit: 2f3d105203edbc21bbbb9c17390b1d3011ef4546
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "20084435"
---
# <a name="migrating-to-direct-routing"></a>迁移到直接路由

本文介绍了所需从业务 Online 和 Microsoft 团队配置角度 Skype 直接路由到迁移。 本文介绍如何从以下迁移： 
 
- Office 365 与呼叫的电话系统计划 （对于团队和 Skype for Business 联机） 
- Office 365 中的业务服务器 （代表 for Business 联机 Skype) 的 Skype 的内部部署 PSTN 连接的电话系统  
- 通过使用云连接器 Edition （业务 online Skype) 的内部部署 PSTN 连接的 office 365 电话系统

  
除了这些配置步骤，配置是也被必需的会话边界控制器 (SBC) 在将呼叫路由至新的路由。 这是本文档的范围之外。 有关详细信息，请参阅 SBC 供应商文档。  

## <a name="user-provisioning-end-state-for-various-pstn-connectivity-options"></a>设置各种 PSTN 连接选项的最终状态的用户 

下表显示为与 Office 365 电话系统所选 PSTN 连接选项设置为用户的最终状态。 显示仅语音相关的属性。

|用户对象属性 |具有通话套餐的电话系统|电话系统与本地 Skype 通过 PSTN 连接的业务服务器|在本地与云连接器通过 PSTN 连接电话系统|PSTN 连接，通过直接路由内部部署与电话系统|
|---|---|---|---|---|
|客户端|适用于商务或团队的 Skype |Skype for Business |Skype for Business |Teams|
|许可证|在线 Skype 业务</br>计划 2</br></br>MCOProfessional 或 MCOSTANDARD）</br></br></br>电话系统 (MCOEV)</br></br></br>通话套餐</br>Teams|Skype 业务 Online 计划 2 （MCOProfessional 或 MCOSTANDARD）</br></br></br>电话系统 (MCOEV)|Skype 业务 Online 计划 2 （MCOProfessional 或 MCOSTANDARD）</br></br></br>电话系统 (MCOEV)|Skype 业务 Online 计划 2 （MCOProfessional 或 MCOSTANDARD</br></br></br>电话系统 (MCOEV)</br></br>Teams|
OnPremLineURI |不适用|电话号码必须同步从内部部署 AD。 |内部部署 Active Directory 中或在 Azure Active Directory 中，可以管理的电话号码。|内部部署 Active Directory 中或在 Azure Active Directory 中，可以管理的电话号码。 但是，如果组织具有 for Business 的内部部署 Skype，必须从本地 Active Directory 同步数。|
|LineURI|PSTN 呼叫电话号码|自动设置从 OnPremLineURI 参数|自动设置从 OnPremLineURI 参数|自动设置从 OnPremLineURI 参数|
|EnterpriseVoiceEnabled|True|True|True|True|
|HostedVoiceMail |True|True|True|True|
|VoicePolicy|BusinessVoice|HybridVoice|HybridVoice|HybridVoice|
|托管 |BusinessVoice|BusinessVoice|BusinessVoice|BusinessVoice|
|VoiceRoutingPolicy|值|值|值|不适用|
|OnlineVoiceRoutingPolicy|$Null|$Null|$Null|值|
|TeamsUpgradePolicy<sup>1</sup>|TeamsOnly、 SfBOnly 或群岛|$Null|$Null|群岛或 TeamsOnly|
|TeamsInterPolicy<sup>2</sup></br>CallingDefaultClient –，请阅读下面的注释。|团队或 SfB |SfB|SfB|Teams|
|TeamsCallingPolicy</br>AllowPrivateCalling|True|不适用|不适用|True|
|TeamsCallingPolicy</br>AllowGroupCalling|True|不适用|不适用|True|
||||||

<sup>1</sup>选择 TeamsUpgradePolicy 的右模式取决于该方案。 请阅读有关[迁移和互操作性指南组织使用一起 for Business 的 Skype 团队](migration-interop-guidance-for-teams-with-skype.md)中的不同模式中的语音体验。

<sup>2</sup>以前发布，TeamsInteropPolicy 将已撤销 （第 3 季度的末尾的目标），并已被其功能合并到 TeamsUpgradePolicy。 使用"共存模式"，如由 TeamsUpgradePolicy，这是现在可将托管互操作和迁移。 选择的用户的模式将管理这两个路由的传入呼叫和聊天室和用户可在哪些客户端启动聊天和呼叫或安排会议。 虽然 TeamsInteropPolicy 将停用，它仍需要 phaseout 期间，在与 TeamsUpgradePolicy 并行中进行设置。  

作为本次努力取得的一部分，Microsoft 最近更新"Microsoft 团队和 Skype 的业务管理中心"（也称为现代门户） 以反映新的管理模型基于共存模式。 在现代门户中，配置现在在自动 TeamsUpgradePolicy 将还设置 TeamsInteropPolicy 为一致的值，因此 TeamsInteropPolicy 不再显示在用户界面中。 但是，管理员使用 PowerShell 仍必须设置 TeamsUpgradePolicy 兼 TeamsInteropPolicy 在一起以确保正确路由。 转换到 TeamsUpgradePolicy 完毕后，它将不再需要还设置 TeamsInteropPolicy。

有关详细信息，请参阅[迁移和互操作性的组织使用团队一起 for Business 的 Skype 的指南](migration-interop-guidance-for-teams-with-skype.md)。

## <a name="migrating-from-calling-plans"></a>从调用计划迁移

有关从调用计划迁移的详细信息，请参阅：

- [设置通话套餐](https://docs.microsoft.com/en-us/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)
- [设置 CsOnlineVoice 用户](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsOnlineVoiceUser?view=skype-ps)
- [Get CsOnlineLisLocation](https://docs.microsoft.com/en-us/powershell/module/skype/get-csonlinelislocation?view=skype-ps)  
 
 
建议您删除 previouslycconfigured 许可计划信息，如下所示：
 
```
$companyname = “contoso” 
$lic1 = $companyname + “:MCOPSTN1” 
$lic2 = $companyname + “:MCOPSTN2” 
Set-MsolUserLicense -UserPrincipalName <UPN> -RemoveLicenses $lic1 
Set-MsolUserLicense -UserPrincipalName <UPN> -RemoveLicenses $lic2 
```
## <a name="migrating-from-office-365-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>从迁移 Office 365 电话系统与内部部署 PSTN 连接中 Skype 业务服务器

从迁移电话系统与内部部署 PSTN 连接中 Skype 业务服务器的详细信息，请参阅以下资源：

- [规划](https://technet.microsoft.com/en-us/library/mt455212.aspx)
- [部署](https://technet.microsoft.com/en-us/library/mt634319.aspx) 

建议您删除以前配置的语音路由的信息，如下所示：

```
Grant-CsVoiceRoutingPolicy -PolicyName $NULL -Identity <UPN> 
```
## <a name="migrating-from-office-365-phone-system-with-on-premises-pstn-connectivity-via-cloud-connector-edition"></a>从 Office 365 电话系统迁移与云连接器 Edition 通过内部部署 PSTN 连接 

有关从电话系统与内部部署 PSTN 连接，通过云连接器迁移的详细信息，请参阅以下文章：

- [规划](https://technet.microsoft.com/en-us/library/mt605227.aspx)  
- [部署](https://technet.microsoft.com/en-us/library/mt634319.aspx)
- [用户配置](https://docs.microsoft.com/en-us/powershell/module/skype/set-csuserpstnsettings?view=skype-ps) 

建议您删除以前配置的语音路由的信息，如下所示：
 
```
Grant-CsVoiceRoutingPolicy -PolicyName $NULL -Identity <UPN> 
Set-CsUserPstnSettings -Identity <UPN> -AllowInternationCalls $false -HybridPSTNSite $null 
```


## <a name="related-links"></a>相关的链接

[使用团队一起 Skype for Business 的组织的迁移和互操作性指南](migration-interop-guidance-for-teams-with-skype.md)

[授予 CsTeamsUpgradePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-csteamsupgradepolicy)

[Get CsTeamsUpgradePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTeamsUpgradePolicy)

[新 CsTeamsUpgradePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsTeamsUpgradePolicy)

[删除 CsTeamsUpgradePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTeamsUpgradePolicy)

[设置 CsTeamsUpgradePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsTeamsUpgradePolicy)

[Get CsTeamsUpgradeConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTeamsUpgradeConfiguration)

[设置 CsTeamsUpgradeConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsTeamsUpgradeConfiguration)

