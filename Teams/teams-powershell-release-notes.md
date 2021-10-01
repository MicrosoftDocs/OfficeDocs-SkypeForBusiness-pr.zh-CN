---
title: Microsoft TeamsPowerShell 发行说明
ms.reviewer: gothambi
author: BrandBer
ms.author: gothambi
manager: naanur
ms.date: 08/31/2021
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: 了解 PowerShell 中的最新Teams。
appliesto:
- Microsoft Teams
ms.openlocfilehash: e3cd18d27434599a94daa55a6c42924ab26b266c
ms.sourcegitcommit: cfc48dc03550c093c4405fb5984648188f523699
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2021
ms.locfileid: "60045528"
---
# <a name="microsoft-teams-powershell-release-notes"></a>Microsoft TeamsPowerShell 发行说明

本页提供适用于公开Teams预览版的最新 PowerShell 更改日志。

## <a name="release-notes"></a>发行说明

> [!NOTE]
> **以下版本** 列中的 -preview 表示 PowerShell Teams更新。

| 日期 | 版本 | 更新 |
|------- | -------------------- | ------------------------------ |
| 2021 年 9 月 | [2.6.0](https://www.powershellgallery.com/packages/MicrosoftTeams/2.6.0) |<li>修复了当 MicrosoftTeams 模块查找成为另一个自定义 PowerShell 模块的嵌套模块时失败的 bug。 现在，MicrosoftTeams cmdlet 可用，即使它是另一模块的嵌套模块。</li><li>Releases [获取 \| 全新 \| 完整 \| 清除]-CsOnlineTelephoneNumberOrder cmdlet。</li><li>发布 Get-CsOnlineTelephoneNumberCountry Get-CsOnlineTelephoneNumberType cmdlet。</li><li>发布这些 cmdlet 的新参数：Get-CsOnlineApplicationInstance、New-CsExternalAccessPolicy、New-CsTeamsAppSetupPolicy、New-CsTeamsCallingPolicy、New-CsTeamsCallParkPolicy、New-CsTeamsMeetingPolicy、New-CsTeamsMessagingPolicy、 Set-CsTeamsAppSetupPolicy、Set-CsTeamsCallParkPolicy、Set-CsTeamsGuestMessagingConfiguration、Set-CsTeamsMeetingPolicy、Set-CsTenantFederationConfiguration、Set-CsExternalAccessPolicy、Set-CsTeamsCallingPolicy。</li><li>修复了在尝试登录错误Connect-MicrosoftTeams重试登录时发生的失败。</li><li>修复Add-TeamChannelUser和Remove-TeamChannelUser通道失败的问题。</li><li>更新，使模块的发行说明在每个新版本的 PowerShell 库中可用。</li>
| 2021 年 9 月 | [2.5.2](https://www.powershellgallery.com/packages/MicrosoftTeams/2.5.2) |<li>注意：从此版本开始，发行说明也将随模块本身一起在 PowerShell 库中发布，以减少发行说明的延迟。</li><li>Releases [Get \| Set \| Grant New \| \| Remove]-CsTeamsEnhancedEncryptionPolicy cmdlets。</li><li>删除 [获取 \| 设置 \| 新 \| 删除]-CsTenantBlockedNumberExceptionPattern cmdlet。</li><li>修复了以下 bug：Microsoft Teams模块查找失败（如果它是另一个自定义 PowerShell 模块的嵌套模块）。 现在，Microsoft Teams cmdlet 可用，即使它是另一模块的嵌套模块。</li><li>Releases [获取 \| 全新 \| 完整 \| 清除]-CsOnlineTelephoneNumberOrder cmdlet。</li><li>发布 Get-CsOnlineTelephoneNumberCountry Get-CsOnlineTelephoneNumberType cmdlet。</li><li>修复了在尝试登录错误后重试Connect-MicrosoftTeams登录时发生的失败。</li><li>修复Add-TeamChannelUser和Remove-TeamChannelUser通道失败的问题。</li>
| 2021 年 8 月 | [2.5.1](https://www.powershellgallery.com/packages/MicrosoftTeams/2.5.1) |<li>现在，Connect-MicrosoftTeams的访问令牌登录使用统一的令牌数组，而不是每个特定于资源的令牌的单独参数。 可在此处找到 [更多详细信息](/powershell/module/teams/connect-microsoftteams)。</li><li>修复了 Cloudshell 中Connect-MicrosoftTeams登录失败的问题。 现在默认使用用户的登录标识，而不是提示重新身份验证。</li><li>TeamsUnassignedNumberTreatment cmdlet 现已可用。</li><li>Get-CsOnlineDialInConferencingBridge Set-CsOnlineDialInConferencingBridge cmdlet 现已从旧实现迁移到较新的 API。</li><li>仅已发布带 -identity Get-CsTenant Get-CsOnlineUser (的) 和更新版本。 与它们的远程处理对应对象相比，它们不再发出已弃用的属性，并且有一些格式更改。</li><li>注意：New-Team相关的更新从 2.5.0 恢复，并且已提供以前的版本以避免任何中断性更改。</li>|
| 2021 年 7 月 | [2.4.1-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/2.4.1-preview) |<li>现在可以授予 cmdlet 更改。</li><li>发布了新的语音相关 cmdlet。</li><li>删除 -Cs* cmdlet 的证书指纹身份验证。</li><li>所有 cmdlet 的日志记录文件的日志记录修复。</li><li>修复了 *TeamChannelUser cmdlet 的问题。</li>|
| 2021 年 6 月 | [2.4.0-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/2.4.0-preview) |<li>仅预览版 Get-CsTenant、Get-CsOnlineUser (且仅具有 -identity 参数的) 、Get-CsOnlineDialInConferencingLanguagesSupported 和 Import-CsOnlineAudioFile。</li><li>现代化版本的 Get-CsOnlineDialInConferencingLanguagesSupported 和 Import-CsOnlineAudioFile 预期与远程处理版本类似/相同。</li><li>使用 -identity 参数Get-CsTenant和Get-CsOnlineUser (时，) 版本不会发出弃用的属性。</li><li>使用 -identity 参数Get-CsTenant Get-CsOnlineUser (时，) 和远程处理计数器部分) 更新版本的格式更改。</li><li>Releases [Get \| Set \| Grant New \| \| Remove]-CsTeamsAudioConferencingPolicy cmdlets。</li><li>发布 Get-CsOnlineAudioFile Remove-CsOnlineAudioFile cmdlet。</li><li>Set-TeamTargetingHierarchy、Remove-TeamTargetingHierarchy Get-TeamTargetingHierarchyStatus现在可供GCC使用。</li><li>修复了 Get-TeamTargetingHierarchyStatus 调用的终结点。</li>|
| 2021 年 5 月 | [2.3.2-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/2.3.2-preview) |<li>支持使用 连接-MicrosoftTeams 进行 AccessToken 登录。 添加了接受令牌数组的 -AccessTokens 参数。 使用 AccessTokens Teams需要 MSGraph 和 Teams 资源令牌。</li><li>删除了 AadAccessToken 和 MsAccessToken 参数。</li>|
| 2021 年 5 月 | [2.3.1](https://www.powershellgallery.com/packages/MicrosoftTeams/2.3.1) |<li>从 更新。NETCore 2.1 到 3.1</li><li>添加了 cmdlet，用于获取用户和组的多地域区域</li><li>修复了集成 Windows 身份验证以将 -AccountId 与 Connect-MicrosoftTeams</li><li>TeamsCallHoldPolicy cmdlet 现已可用</li><li>更新了许多命令的输入参数和输出格式</li><li>修复了远程处理命令时出现的大型延迟问题</li><li>GA 自定义程序包功能</li>|
| 2021 年 4 月 | [2.2.0-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/2.2.0-preview) | <li>修复了集成身份验证Windows -AccountId 与 连接-MicrosoftTeams 的集成身份验证。</li><li>添加了 cmdlet，用于获取可发送给用户的总更改通知事件的详细信息。</li><li>添加了 cmdlet，用于获取用户和组的多地域区域。</li><li>处理传递给 TeamsEnvironment 名称的值区分大小写。 这已修复。</li><li>模块内远程会话管理的主要重构，以便于单元测试。 租户管理员不应有功能更改。</li>|
| 2021 年 4 月 | [2.1.0-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/2.1.0-preview) | <li>修复了某些远程处理 cmdlet (例如 Get-CsTeamsNetworkRoamingPolicy、Get-CsTeamsMeetingPolicy、Get-CsTeamsMessagingPolicy 等) 的输出格式。</li><li>更新了策略管理 cmdlet 的参数列表。</li>|
| 2021 年 3 月 | [2.0.0](https://www.powershellgallery.com/packages/MicrosoftTeams/2.0.0) | <li>使用 MSAL 进行身份验证&授权</li> <li>Connect-MicrosoftTeams是所有 cmdlet 的入口点。</li><li>New-csOnlineSession 不再可用。 它已替换为 连接-MicrosoftTeams。</li><li>不再需要 Enable-csonlinesessionforreconnection。 该功能已在 PowerShell 模块中Teams实现。</li> <li>重构策略包 cmdlet 并添加组包分配</li><li>Get-Team cmdlet 的重要性能增强</li> <li>改进了现有 cmdlet 的日志记录和调试选项 </li> <li>添加了模板管理 cmdlet</li> <li>弃用New-CsOnlineSession</li>|
| 2021 年 2 月 | [1.1.11-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.11-preview) | <li>添加了模板管理 cmdlet</li><li>适用于 Get-Team cmdlet 的 Mezzo 和批处理增强功能</li> <li>改进了现有 cmdlet 的日志记录和调试选项 </li> <li>重构的策略包 cmdlet</li>|
| 2020 年 12 月 | [1.1.10-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.10-preview) | <li>更新了 New-team cmdlet，增加了重试和睡眠持续时间</li>|
| 2020 年 12 月 | [1.1.9-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.9-preview) | <li>Skype for Business Online 集成的更新</li><li>修复了出现重复提示Connect-Microsoft Teams</li>|
| 2020 年 11 月 | [1.1.8-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.8-preview) | <li>添加自定义策略包 cmdlet</li><li>目标层次结构上传命令的修复</li>|
| 2020 年 11 月 | [1.1.7-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.7-preview) | <li>使用 MSAL 进行身份验证&授权</li><li>重构策略包 cmdlet 并添加组包分配</li><li>重构目标层次结构上传命令以使用异步模型</li> <li>如果用户不使用 -credential 参数，则初始身份验证期间会提示用户两次。 用户可以使用 -credential 参数传递凭据，以避免重复的提示。 此行为将在下一版本中修复。</li> |
| 2020 年 9 月 | [1.1.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.6) | <li>Skype for Business联机连接器集成</li> |
| 2020 年 9 月 | [1.1.5-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.5-preview) | <li>Skype for Business联机连接器集成</li> |
| 2020 年 7 月 | [1.1.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.4) | <li>添加了 [组策略分配 cmdlet](./assign-policies.md#assign-a-policy-to-a-group)</li> |
| 2020 年 6 月 | [1.1.3-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.3-preview) | <li>Skype for Business联机连接器集成<li>Get-Team优化<li>增强的可靠性</li> |
| 2020 年 6 月 | [1.0.7](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.7) | <li>添加了 Cmdlet 预加载<li>.Net Framework 优化</li>   |
| 2020 年 4 月 | [1.0.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.6) | <li>验证码和程序集签名<li>添加了Get-CsPolicyPackage<li>添加了Get-CsUserPolicyPackage<li>添加了Get-CsUserPolicyPackageRecommendation<li>添加了Grant-CsUserPolicyPackage<li>添加了New-CsBatchPolicyPackageAssignmentOperation<li>添加了Set-TeamArchivedState<li>添加了Set-TeamPicture<li>已删除Get-TeamHelp</li>  |
| 2020 年 3 月 | [1.0.5](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.5) |<li>添加了New-CsBatchPolicyAssignmentOperation</li> |
| 2020 年 2 月 | [1.0.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.4) | <li>Get-Team优化</li>  |

## <a name="related-topics"></a>相关主题

[Teams PowerShell 概览](teams-powershell-overview.md)

[安装 Teams PowerShell](teams-powershell-install.md)

[使用 Teams PowerShell Teams管理资源](teams-powershell-managing-teams.md)

[Microsoft Teams cmdlet 参考](/powershell/teams/)

[Skype for Business cmdlet 参考](/powershell/skype/intro)
