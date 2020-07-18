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
ms.openlocfilehash: 09014d3e7deba2797b46031efee81f537d2d6538
ms.sourcegitcommit: f1386c5cfe52819e54f4ffb1f1ce06aef5a59522
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/18/2020
ms.locfileid: "45170621"
---
# <a name="microsoft-teams-powershell-release-notes"></a>Microsoft 团队 PowerShell 发行说明

此页面提供适用于常规可用性和公共预览版发布的最新团队 PowerShell 更改日志。

## <a name="release-notes"></a>发行说明

> [!NOTE]
> **-** 在下面的 "版本" 列中预览表示对团队 PowerShell 公共预览版的更新。

| 日期 | 版本 | 端更新 |
|------- | -------------------- | ------------------------------ |
| 2020年7月 | [类库](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.4) | <li>已添加[组策略分配 cmdlet](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-group)</li> |
| 2020年6月 | [1.1.3-预览](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.3-preview) | <li>Skype for Business Online 连接器集成<li>获取团队优化<li>增强的可靠性</li> |
| 2020年6月 | [1.0.7](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.7) | <li>已添加 Cmdlet 预加载<li>.Net Framework 优化</li>   |
| 2020年4月 | [1.0.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.6) | <li>验证码和程序集签名<li>已添加 CsPolicyPackage<li>已添加 CsUserPolicyPackage<li>已添加 CsUserPolicyPackageRecommendation<li>已添加授予 CsUserPolicyPackage<li>新增-CsBatchPolicyPackageAssignmentOperation<li>已添加 TeamArchivedState<li>已添加 TeamPicture<li>已删除 TeamHelp</li>  |
| 2020年3月 | [1.0.5](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.5) |<li>新增-CsBatchPolicyAssignmentOperation</li> |
| 2020年2月 | [1.0.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.4) | <li>获取团队优化</li>  |

### <a name="cmdlet-availability"></a>Cmdlet 可用性

> [!NOTE]
> 下表中的列表仅包含团队 PowerShell 模块本身中的 cmdlet。 不显示 "[kype For Business Online" 连接器模块](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)中的团队 cmdlet。 但是，在将这些 cmdlet 迁移到团队 PowerShell 中时，我们会将它们添加到此表中。

| Cmdlet | 公共预览版中提供 | 上市后提供 |
| -| -- | --|
| [Add-TeamChannelUser](https://docs.microsoft.com/powershell/module/teams/add-teamchanneluser?view=teams-ps) | 是 | **否** |
| [Add-TeamUser](https://docs.microsoft.com/powershell/module/teams/add-teamuser?view=teams-ps) | 是 | 是 |
| [Add-TeamsAppInstallation](https://docs.microsoft.com/powershell/module/teams/add-teamsappinstallation?view=teams-ps) | 是 | **否**|
| [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps) | 是 | 是 |
| [断开连接-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/disconnect-microsoftteams?view=teams-ps) | 是 | 是 |
| [CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation?view=teams-ps) | 是 | 是 |
| [CsGroupPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignmentoperation?view=teams-ps) | 是 | **否** |
| [CsOnlinePowerShellEndpoint](https://docs.microsoft.com/powershell/module/teams/get-csonlinepowershellendpoint?view=teams-ps) | 是 | **否** |
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
| [新-CsOnlineSession](https://docs.microsoft.com/powershell/module/teams/new-csonlinesession?view=teams-ps) | 是 | **否** |
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
