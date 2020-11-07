---
title: Microsoft 团队 PowerShell 发行说明
ms.reviewer: brandber
author: BrandBer
ms.author: brandber
manager: kojiko
ms.date: 06/30/2020
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: 了解团队 PowerShell 中的最新更改。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 41aa6cdf05901756bb2bcd13dbb8b9ad2cedabf6
ms.sourcegitcommit: a6c7a0cdbedf6cf32213d7636da52db71b4bac3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/06/2020
ms.locfileid: "48937741"
---
# <a name="microsoft-teams-powershell-release-notes"></a>Microsoft 团队 PowerShell 发行说明

此页面提供适用于常规可用性和公共预览版发布的最新团队 PowerShell 更改日志。

## <a name="release-notes"></a>发行说明

> [!NOTE]
> **-** 在下面的 "版本" 列中预览表示对团队 PowerShell 公共预览版的更新。

| 日期 | 版本 | 端更新 |
|------- | -------------------- | ------------------------------ |
| 2020年11月 | [1.1.7-预览](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.7-preview) | <li>使用 MSAL 进行身份验证 & 授权</li><li>重构策略包 cmdlet 并添加组包分配</li><li>重构的目标层次结构上载命令以使用异步模型</li> <li>当用户不使用-credential 参数时，将在初始身份验证期间收到两次。 用户可以使用-credential 参数传递凭据，以避免重复提示。 此行为将在下一个版本中修复。</li> |
| 2020年9月 | [1.1.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.6) | <li>Skype for Business Online 连接器集成</li> |
| 2020年9月 | [1.1.5-预览](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.5-preview) | <li>Skype for Business Online 连接器集成</li> |
| 2020年7月 | [类库](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.4) | <li>已添加 [组策略分配 cmdlet](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-group)</li> |
| 2020年6月 | [1.1.3-预览](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.3-preview) | <li>Skype for Business Online 连接器集成<li>Get-Team 优化<li>增强的可靠性</li> |
| 2020年6月 | [1.0.7](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.7) | <li>已添加 Cmdlet 预加载<li>.Net Framework 优化</li>   |
| 2020年4月 | [1.0.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.6) | <li>验证码和程序集签名<li>已添加 Get-CsPolicyPackage<li>已添加 Get-CsUserPolicyPackage<li>已添加 Get-CsUserPolicyPackageRecommendation<li>已添加 Grant-CsUserPolicyPackage<li>已添加 New-CsBatchPolicyPackageAssignmentOperation<li>已添加 Set-TeamArchivedState<li>已添加 Set-TeamPicture<li>已删除 Get-TeamHelp</li>  |
| 2020年3月 | [1.0.5](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.5) |<li>已添加 New-CsBatchPolicyAssignmentOperation</li> |
| 2020年2月 | [1.0.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.4) | <li>Get-Team 优化</li>  |

### <a name="cmdlet-availability"></a>Cmdlet 可用性

> [!NOTE]
> 下表中的列表仅包含团队 PowerShell 模块本身中的 cmdlet。 不显示 "[kype For Business Online" 连接器模块](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps) 中的团队 cmdlet。 但是，在将这些 cmdlet 迁移到团队 PowerShell 中时，我们会将它们添加到此表中。

| Cmdlet | 公共预览版中提供 | 上市后提供 |
| -| -- | --|
| [Add-TeamChannelUser](https://docs.microsoft.com/powershell/module/teams/add-teamchanneluser?view=teams-ps) | 是 | **否** |
| [Add-TeamUser](https://docs.microsoft.com/powershell/module/teams/add-teamuser?view=teams-ps) | 是 | 是 |
| [Add-TeamsAppInstallation](https://docs.microsoft.com/powershell/module/teams/add-teamsappinstallation?view=teams-ps) | 是 | **否**|
| [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps) | 是 | 是 |
| [断开连接-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/disconnect-microsoftteams?view=teams-ps) | 是 | 是 |
| [CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation?view=teams-ps) | 是 | 是 |
| [CsGroupPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignmentoperation?view=teams-ps) | 是 | **否** |
| [CsOnlinePowerShellEndpoint](https://docs.microsoft.com/powershell/module/teams/get-csonlinepowershellendpoint?view=teams-ps) | 是 | 是 |
| [CsPolicyPackage](https://docs.microsoft.com/powershell/module/teams/get-cspolicypackage?view=teams-ps) | 是 | 是 |
| [CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment?view=teams-ps) | 是 | 是 |
| [CsUserPolicyPackage](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicypackage?view=teams-ps) | 是 | 是 |
| [CsUserPolicyPackageRecommendation](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicypackagerecommendation?view=teams-ps) | 是 | 是 |
| [获取团队](https://docs.microsoft.com/powershell/module/teams/get-team?view=teams-ps) | 是 | 是 |
| [TeamChannel](https://docs.microsoft.com/powershell/module/teams/get-teamchannel?view=teams-ps) | 是 | 是|
| [TeamChannelUser](https://docs.microsoft.com/powershell/module/teams/get-teamchanneluser?view=teams-ps) | 是 | **否** |
| [TeamUser](https://docs.microsoft.com/powershell/module/teams/get-teamuser?view=teams-ps) | 是 | 是 |
| [TeamsApp](https://docs.microsoft.com/powershell/module/teams/get-teamsapp?view=teams-ps) | 是 | 是 |
| [TeamsAppInstallation](https://docs.microsoft.com/powershell/module/teams/get-teamsappinstallation?view=teams-ps) | 是 | **否** |
| [授权-CsUserPolicyPackage](https://docs.microsoft.com/powershell/module/teams/grant-csuserpolicypackage?view=teams-ps) | 是 | 是 |
| [新-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) | 是 | 是 |
| [新-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment?view=teams-ps) | 是 | 是 |
| [新-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation?view=teams-ps) | 是 | 是 |
| [新-CsOnlineSession](https://docs.microsoft.com/powershell/module/teams/new-csonlinesession?view=teams-ps) | 是 | 是 |
| [新团队](https://docs.microsoft.com/powershell/module/teams/new-team?view=teams-ps) | 是 | 是 |
| [新-TeamChannel](https://docs.microsoft.com/powershell/module/teams/new-channel?view=teams-ps) | 是 | 是 |
| [新-TeamsApp](https://docs.microsoft.com/powershell/module/teams/new-teamsapp?view=teams-ps) | 是 | 是 |
| [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment?view=teams-ps) | 是 | 是 |
| [删除-团队](https://docs.microsoft.com/powershell/module/teams/remove-team?view=teams-ps) | 是 | 是 |
| [Remove-TeamChannel](https://docs.microsoft.com/powershell/module/teams/remove-teamchannel?view=teams-ps) | 是 | 是 |
| [Remove-TeamChannelUser](https://docs.microsoft.com/powershell/module/teams/remove-teamchanneluser?view=teams-ps) | 是 | **否** |
| [Remove-TeamsApp](https://docs.microsoft.com/powershell/module/teams/remove-teamsapp?view=teams-ps) | 是 | 是 |
| [Remove-TeamsAppInstallation](https://docs.microsoft.com/powershell/module/teams/remove-teamsappinstallation?view=teams-ps) | 是 | **否** |
| [Remove-TeamTargetingHierarchy](https://docs.microsoft.com/powershell/module/teams/remove-teamtargetinghierarchy?view=teams-ps) | 是 | **否**|
| [Remove-TeamUser](https://docs.microsoft.com/powershell/module/teams/remove-teamuser?view=teams-ps) | 是 | 是 |
| [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment?view=teams-ps) | 是 | **否** |
| [集-团队](https://docs.microsoft.com/powershell/module/teams/set-team?view=teams-ps) | 是 | 是 |
| [Set-TeamArchivedState](https://docs.microsoft.com/powershell/module/teams/set-teamarchivedstate?view=teams-ps) | 是 | 是 |
| [Set-TeamChannel](https://docs.microsoft.com/powershell/module/teams/set-teamchannel?view=teams-ps) | 是 | 是 |
| [Set-TeamPicture](https://docs.microsoft.com/powershell/module/teams/set-teampicture?view=teams-ps) | 是 | 是 |
| [Set-TeamsApp](https://docs.microsoft.com/powershell/module/teams/set-teamapp?view=teams-ps) | 是 | 是 |
| [Set-TeamTargetingHierarchy](https://docs.microsoft.com/powershell/module/teams/set-teamtargetinghierarchy?view=teams-ps) | 是 | **否** |
| [Update-TeamsAppInstallation](https://docs.microsoft.com/powershell/module/teams/update-teamappinstallation?view=teams-ps) | 是 | **否** |

## <a name="related-topics"></a>相关主题

[Teams PowerShell 概览](teams-powershell-overview.md)

[安装团队 PowerShell](teams-powershell-install.md)

[通过团队 PowerShell 管理团队](teams-powershell-managing-teams.md)

[Microsoft 团队 cmdlet 参考](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Skype for Business cmdlet 参考](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
