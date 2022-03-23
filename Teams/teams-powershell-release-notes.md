---
title: Microsoft Teams PowerShell 发行说明
ms.reviewer: gothambi
author: sumitb18
ms.author: subadjat
manager: pbafna03
ms.date: 12/10/2021
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: 了解 PowerShell 中的最新Teams。
appliesto:
- Microsoft Teams
ms.openlocfilehash: dea6b9d93d3950d4a831fdf669a98e28028f3c41
ms.sourcegitcommit: fcac607fb4ad342a0936527f848e04c85f153ba5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/22/2022
ms.locfileid: "63711706"
---
# <a name="microsoft-teams-powershell-release-notes"></a>Microsoft Teams PowerShell 发行说明

本页提供适用于公开Teams预览版的最新 PowerShell 更改日志。

## <a name="release-notes"></a>发行说明

> [!NOTE]
> **以下版本** 列中的 -preview 表示 PowerShell Teams更新。

| 日期 | 版本 | 更新 |
|------- | -------------------- | ------------------------------ |
| 2022 年 3 月 | [4.0.1-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/4.0.1-preview) |<li>修复了 ErrorAction 常见参数的问题。</li>
| 2022 年 3 月 | [4.0.0](https://www.powershellgallery.com/packages/MicrosoftTeams/4.0.0) |<li>此 GA 版本完成了所有与组织相关的 cmdlet Teams现代化。 现代版本将逐渐推出，因此某些组织将继续看到较旧的远程处理版本。</li><li>GA 中的发布 [NewSetRemove\|\|]-CsUserCallingDelegate 和 [GetSet\|]-CsUserCallingSettings cmdlet。</li><li>[中断性变更]New-CsVoiceNormalizationRule 除外;其他 cmdlet 不再支持 InMemory 开关。</li><li>弃用以下 cmdlet：ConvertTo-JsonForPSWS、 Set-CsUserServicesPolicy、[GetSet\|]-CsNetworkConfiguration、[SetRemove\|]-CsTenantNetworkConfiguration、New-CsNetworkMediaBypassConfiguration、[GetGrantNewRemoveSet\|\|\|\|]-CsTeamsVerticalPackagePolicy，[GetRemoveSet\|\|]-CsVoiceNormalizationRule。</li>
| 2022 年 2 月 | [3.2.0-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/3.2.0-preview) |<li>此版本完成了所有与组织相关的 cmdlet Teams现代化。 现代版本将逐渐推出，因此某些组织将继续看到较旧的远程处理版本。</li><li>[中断性变更]New-CsVoiceNormalizationRule 除外;其他 cmdlet 不再支持 InMemory 开关。</li><li>Connect-MicrosoftTeams性能改进。</li><li>使用前缀Import-Module的修复。</li><li>修复了在 [GetSetRemove\|\|]-CsOnlineLisPort 中处理具有斜杠字符"/"的端口的问题。</li><li>Test-CsTeamsUnassignedNumberTreatment cmdlet。</li><li>弃用以下 cmdlet：ConvertTo-JsonForPSWS、 Set-CsUserServicesPolicy、[GetSet\|]-CsNetworkConfiguration、[SetRemove]-CsTenantNetworkConfiguration、New-CsNetworkMediaBypassConfiguration、[GetGrantNewRemoveSet\|\|\|\|]-CsTeamsVerticalPackagePolicy、[GetRemoveSet\|\|\|]-CsVoiceNormalizationRule。</li>
| 2022 年 2 月 | [3.1.1](https://www.powershellgallery.com/packages/MicrosoftTeams/3.1.1) |<li>Import-Module 的性能改进。</li><li>PSListModifier 反序列化问题已修复。</li>
| 2022 年 1 月 | [3.1.0](https://www.powershellgallery.com/packages/MicrosoftTeams/3.1.0) |<li>将 Cmdlet 从 Get-CsTeamsShiftsConnectionUser Get-CsTeamsShiftsConnectionWfmUser。</li><li>为 Get-CsOnlineUser 发布新参数 ResultSize、SkipUserPolicies。 </li><li>为 Get-CsOnlineDialInConferencingUser 发布新参数 ResultSize。</li><li>为 Get-CsOnlineVoiceUser 发布新参数 First、NumberAssigned、NumberNotAssigned、PSTNConnectivity、EnterpriseVoiceStatus、CivicAddressId、LocationId。</li>
| 2021 年 12 月 | [3.0.1-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/3.0.1-preview) |<li>发布最新版本的 Grant-CsTeamsFilesPolicy 和 Remove-CsTeamsFilesPolicy。 它们应类似于其远程处理对应项。 将逐步推出新式版本。因此，某些租户将看到较旧的远程 (，直到推出完成) 。</li><li> Releases [NewSetRemove\|\|]-CsUserCallingDelegate cmdlets。 这些 cmdlet 最终会在 GA 模块中发布。 在预览版模块中发布试用版。</li><li>Releases [GetRemove\|]-CsTeamsShiftsConnectionErrorReport cmdlets。 这些 cmdlet 最终会在 GA 模块中发布。 在预览版模块中发布试用版。</li><li>Get-CsTeamsShiftsConnectionOperation cmdlet。 此 cmdlet 最终会在 GA 模块中发布。 在预览版模块中发布试用版。</li><li>New-CsTeamsShiftsConnectionBatchTeamMap cmdlet。 此 cmdlet 最终会在 GA 模块中发布。 在预览版模块中发布试用版。</li><li>Remove-CsTeamsShiftsScheduleRecord cmdlet。 此 cmdlet 最终会在 GA 模块中发布。 在预览版模块中发布试用版。</li>
| 2021 年 11 月 | [3.0.0](https://www.powershellgallery.com/packages/MicrosoftTeams/3.0.0) |<li>[中断性更改] Get-CsOnlineUser 和 Get-CsOnlineVoiceUser：以下更改适用于 TeamsOnly 租户：<ul><li>这些 cmdlet 现已从早期实现迁移到较新的 API。</li><li> (-Identity 参数) ：TeamsOnly 租户不再Teams的属性已弃用。 某些属性也已重命名/替换 —请参阅 [Get-CsOnlineUser](/powershell/module/skype/get-csonlineuser?view=skype-ps) 和 [Get-CsOnlineVoiceUser](/powershell/module/skype/get-csonlinevoiceuser?view=skype-ps)。</li><li>Get-CsOnlineUser (-Filter 参数) ：基于 AssignedPlans 和 EnterpriseVoice 的筛选格式已修改。 基于 TeamsOnly 用户的使用情况 (可筛选属性) 暂时受到限制 — 请参阅 [Get-CsOnlineVoiceUser](/powershell/module/skype/get-csonlinevoiceuser?view=skype-ps)。</li><li>这些 cmdlet 将逐步推出，在 CY21 结束推出之前，某些租户不会遇到这些更改。</ul></li><li>[中断性变更]Get-CsTenant：对于 TeamsOnly 租户，不再与 Teams 相关的属性已弃用 — 请参阅 [Get-CsTenant](/powershell/module/skype/get-cstenant?view=skype-ps)。</li><li> 发布所有 75+ Grant-CsPolicy\<Name\> cmdlet (所有参数集) 。 它们应类似于其远程处理对应项。 将逐步推出新式版本，因此某些租户将看到较早的远程处理版本 (推出完成) 。</li><li> 发布所有 75+ Remove-CsPolicy\<Name\> cmdlet 的现代化版本。 它们应类似于其远程处理对应项。 将逐步推出新式版本，因此某些租户将看到较早的远程处理版本 (推出完成) 。</li><li> Releases [SetRemove\|]-CsPhoneNumberAssignment cmdlets。 这些 cmdlet 将逐渐推出，因此，某些租户将收到一条错误消息，其中引用了在推出完成 (可以使用的现有 cmdlet) 。</li><li> 为 [SetNew\|]-CsTeamsEmergencyCallingPolicy cmdlet 发布新参数 EnhancedEmergencyServiceDisclaimer。<li> Releases [GetAddRemove\|\|]-TeamChannelUser cmdlets。</li><li> Export-CsOnlineAudioFile cmdlet。</li><li> 修复了 [GetImportRemove\|\|]-CsOnlineAudioFile cmdlet 的错误处理。</li><li>错误处理Get-Team修复。 如果提取团队数据失败，则输出错误消息。</li><li>修复了Connect-MicrosoftTeams - AccessToken 增加了到期时间的差异。</li>
| 2021 年 11 月 | [2.6.2-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/2.6.2-preview) |<li>发布所有 75+ Grant-CsPolicy\<Name\> cmdlet (所有参数集) 。 它们应与它们的远程处理对应方类似。 将逐渐推出新式版本，未进行测试的租户将看到较旧的远程处理版本。</li><li>发布所有 75+ Remove-CsPolicy\<Name\> cmdlet 的现代化版本。 它们应与它们的远程处理对应方类似。 将逐渐推出新式版本，未进行测试的租户将看到较旧的远程处理版本。</li><li>Set-CsUserCallingSettings cmdlet。 此 cmdlet 最终会在 GA 模块中发布。 在预览版模块中发布试用版。</li><li>Export-CsOnlineAudioFile cmdlet。</li><li>修复了 [GetImportRemove\|\|]-CsOnlineAudioFile cmdlet 的错误处理。</li>
| 2021 年 10 月 | [2.6.1-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/2.6.1-preview) |<li>Releases [SetRemove\|]-CsPhoneNumberAssignment cmdlets。 这些 cmdlet 将逐渐推出。因此，某些租户将收到一条错误消息，指出他们可以使用现有的 cmdlet， (推出完成) 。</li><li>发布 Get-CsOnlineTelephoneNumberCountry Get-CsOnlineTelephoneNumberType cmdlet。</li><li>为 [SetNew\|]-CsTeamsEmergencyCallingPolicy cmdlet 发布新参数 EnhancedEmergencyServiceDisclaimer。</li><li>Get-CsUserCallingSettings cmdlet。 此 cmdlet 最终会在 GA 模块中发布。 在预览版模块中发布试用版。</li>
| 2021 年 9 月 | [2.6.0](https://www.powershellgallery.com/packages/MicrosoftTeams/2.6.0) |<li>修复了当 MicrosoftTeams 模块查找成为另一个自定义 PowerShell 模块的嵌套模块时失败的 bug。 现在，MicrosoftTeams cmdlet 可用，即使它是另一模块的嵌套模块。</li><li>Releases [GetNewCompleteClear\|\|\|]-CsOnlineTelephoneNumberOrder cmdlets。</li><li>发布 Get-CsOnlineTelephoneNumberCountry Get-CsOnlineTelephoneNumberType cmdlet。</li><li>发布这些 cmdlet 的新参数：Get-CsOnlineApplicationInstance、New-CsExternalAccessPolicy、New-CsTeamsAppSetupPolicy、New-CsTeamsCallingPolicy、New-CsTeamsCallParkPolicy、New-CsTeamsMeetingPolicy、New-CsTeamsMessagingPolicy、 Set-CsTeamsAppSetupPolicy、Set-CsTeamsCallParkPolicy、Set-CsTeamsGuestMessagingConfiguration、Set-CsTeamsMeetingPolicy、Set-CsTenantFederationConfiguration、Set-CsExternalAccessPolicy、Set-CsTeamsCallingPolicy。</li><li>修复了在尝试登录错误后重试登录Connect-MicrosoftTeams登录时发生的失败。</li><li>更新，使模块的发行说明在每个新版本的 PowerShell 库中可用。</li>
| 2021 年 9 月 | [2.5.2-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/2.5.2-preview) |<li>注意：从此版本开始，发行说明也将随模块本身一起在 PowerShell 库中发布，以减少发行说明的延迟。</li><li>Releases [GetSetGrantNewRemove\|\|\|\|]-CsTeamsEnhancedEncryptionPolicy cmdlet。</li><li>删除 [GetSetNewRemove\|\|\|]-CsTenantBlockedNumberExceptionPattern cmdlet。</li><li>修复了当模块Microsoft Teams另一个自定义 PowerShell 模块的嵌套模块时，该模块查找失败的 bug。 现在，Microsoft Teams cmdlet 可用，即使它是另一模块的嵌套模块。</li><li>Releases [GetNewCompleteClear\|\|\|]-CsOnlineTelephoneNumberOrder cmdlets。</li><li>发布 Get-CsOnlineTelephoneNumberCountry Get-CsOnlineTelephoneNumberType cmdlet。</li><li>修复了在尝试登录错误后重试Connect-MicrosoftTeams登录时发生的失败。</li><li>修复Add-TeamChannelUserRemove-TeamChannelUser通道失败的问题。</li>
| 2021 年 8 月 | [2.5.1](https://www.powershellgallery.com/packages/MicrosoftTeams/2.5.1) |<li>现在，Connect-MicrosoftTeams的访问令牌登录使用统一的令牌数组，而不是每个特定于资源的令牌的单独参数。 可在此处找到更多详细信息：[连接-MicrosoftTeams](/powershell/module/teams/connect-microsoftteams)。</li><li>修复了 Cloudshell 中Connect-MicrosoftTeams登录失败的问题。 现在默认使用用户的登录标识，而不是提示重新身份验证。</li><li>TeamsUnassignedNumberTreatment cmdlet 现已可用。</li><li>Get-CsOnlineDialInConferencingBridge Set-CsOnlineDialInConferencingBridge cmdlet 现已从旧实现迁移到较新的 API。</li><li>仅已发布具有 -identity Get-CsTenant Get-CsOnlineUser (的) 和更新版本。 与它们的远程处理对应对象相比，它们不再发出已弃用的属性，并且有一些格式更改。</li><li>注意：New-Team相关的更新已从 2.5.0 还原，并且已提供以前的版本以避免任何中断性更改。</li>|
| 2021 年 7 月 | [2.4.1-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/2.4.1-preview) |<li>现在可以授予 cmdlet 更改。</li><li>发布了新的语音相关 cmdlet。</li><li>删除 -Cs* cmdlet 的证书指纹身份验证。</li><li>所有 cmdlet 的日志记录文件的日志记录修复。</li><li>修复了 *TeamChannelUser cmdlet 的问题。</li>|
| 2021 年 6 月 | [2.4.0-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/2.4.0-preview) |<li>仅预览版 Get-CsTenant、Get-CsOnlineUser (且仅包含 -identity 参数的) 、Get-CsOnlineDialInConferencingLanguagesSupported 和 Import-CsOnlineAudioFile。</li><li>与远程处理Get-CsOnlineDialInConferencingLanguagesSupportedImport-CsOnlineAudioFile版本应类似/相同。</li><li>使用 -identity 参数Get-CsTenant Get-CsOnlineUser (时，) 和属性的已现代化版本不会发出弃用的属性。</li><li>使用 -identity Get-CsTenant Get-CsOnlineUser (运行时，) 和远程处理计数器部分) 一些格式更改。</li><li>Releases [GetSetGrantNewRemove\|\|\|\|]-CsTeamsAudioConferencingPolicy cmdlet。</li><li>发布 Get-CsOnlineAudioFile Remove-CsOnlineAudioFile cmdlet。</li><li>Set-TeamTargetingHierarchy、Remove-TeamTargetingHierarchy Get-TeamTargetingHierarchyStatus现在可用于GCC客户。</li><li>修复了 Get-TeamTargetingHierarchyStatus 调用的终结点。</li>|
| 2021 年 5 月 | [2.3.2-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/2.3.2-preview) |<li>支持使用 连接-MicrosoftTeams 进行 AccessToken 登录。 添加了接受令牌数组的 -AccessTokens 参数。 使用 AccessTokens Teams需要 MSGraph 和 Teams 资源令牌。</li><li>删除了 AadAccessToken 和 MsAccessToken 参数。</li>|
| 2021 年 5 月 | [2.3.1](https://www.powershellgallery.com/packages/MicrosoftTeams/2.3.1) |<li>从 更新。NETCore 2.1 到 3.1</li><li>添加了 cmdlet，用于获取用户和组的多地域区域</li><li>修复了集成 Windows 身份验证以将 -AccountId 与 Connect-MicrosoftTeams</li><li>TeamsCallHoldPolicy cmdlet 现已可用</li><li>更新了许多命令的输入参数和输出格式</li><li>修复了远程处理命令时出现的大型延迟问题</li><li>GA 自定义程序包功能</li>|
| 2021 年 4 月 | [2.2.0-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/2.2.0-preview) | <li>修复了集成身份验证Windows -AccountId 与 连接-MicrosoftTeams 的集成身份验证。</li><li>添加了 cmdlet，用于获取可发送给用户的总更改通知事件的详细信息。</li><li>添加了 cmdlet，用于获取用户和组的多地域区域。</li><li>处理传递给 TeamsEnvironment 名称的值区分大小写。 这已修复。</li><li>模块内远程会话管理的主要重构，以便于单元测试。 租户管理员不应有功能更改。</li>|
| 2021 年 4 月 | [2.1.0-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/2.1.0-preview) | <li>修复了某些远程处理 cmdlet (例如 Get-CsTeamsNetworkRoamingPolicy、Get-CsTeamsMeetingPolicy、Get-CsTeamsMessagingPolicy 等) 的输出格式。</li><li>更新了策略管理 cmdlet 的参数列表。</li>|
| 2021 年 3 月 | [2.0.0](https://www.powershellgallery.com/packages/MicrosoftTeams/2.0.0) | <li>使用 MSAL 进行身份验证&授权</li> <li>Connect-MicrosoftTeams是所有 cmdlet 的入口点。</li><li>New-csOnlineSession 不再可用。 已替换为 连接-MicrosoftTeams。</li><li>不再需要 Enable-csonlinesessionforreconnection。 此功能已在 PowerShell 模块中Teams实现。</li> <li>重构策略包 cmdlet 并添加组包分配</li><li>Get-Team cmdlet 的重要性能增强</li> <li>改进了现有 cmdlet 的日志记录和调试选项 </li> <li>添加了模板管理 cmdlet</li> <li>弃用New-CsOnlineSession</li>|
| 2021 年 2 月 | [1.1.11-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.11-preview) | <li>添加了模板管理 cmdlet</li><li>Get-Team cmdlet 的 Mezzo 和批处理增强功能</li> <li>改进了现有 cmdlet 的日志记录和调试选项 </li> <li>重构的策略包 cmdlet</li>|
| 2020 年 12 月 | [1.1.10-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.10-preview) | <li>更新了 New-team cmdlet，增加了重试和睡眠持续时间</li>|
| 2020 年 12 月 | [1.1.9-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.9-preview) | <li>Skype for Business Online 集成的更新</li><li>修复了重复提示Connect-Microsoft Teams</li>|
| 2020 年 11 月 | [1.1.8-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.8-preview) | <li>添加自定义策略包 cmdlet</li><li>目标层次结构上传命令的修复</li>|
| 2020 年 11 月 | [1.1.7-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.7-preview) | <li>使用 MSAL 进行身份验证&授权</li><li>重构策略包 cmdlet 并添加组包分配</li><li>重构目标层次结构上传命令以使用异步模型</li> <li>如果用户不使用 -credential 参数，则初始身份验证期间会提示用户两次。 用户可以使用 -credential 参数传递凭据，以避免重复的提示。 此行为将在下一版本中修复。</li> |
| 2020 年 9 月 | [1.1.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.6) | <li>Skype for Business Online 连接器集成</li> |
| 2020 年 9 月 | [1.1.5-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.5-preview) | <li>Skype for Business Online 连接器集成</li> |
| 2020 年 7 月 | [1.1.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.4) | <li>添加了 [组策略分配 cmdlet](./assign-policies-users-and-groups.md#assign-a-policy-to-a-group)</li> |
| 2020 年 6 月 | [1.1.3-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.3-preview) | <li>Skype for Business Online 连接器集成<li>Get-Team优化<li>增强的可靠性</li> |
| 2020 年 6 月 | [1.0.7](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.7) | <li>添加了 Cmdlet 预加载<li>.NET Framework优化</li>   |
| 2020 年 4 月 | [1.0.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.6) | <li>验证码和程序集签名<li>添加了Get-CsPolicyPackage<li>添加了Get-CsUserPolicyPackage<li>添加了Get-CsUserPolicyPackageRecommendation<li>添加了Grant-CsUserPolicyPackage<li>添加了New-CsBatchPolicyPackageAssignmentOperation<li>添加了Set-TeamArchivedState<li>添加了Set-TeamPicture<li>已删除Get-TeamHelp</li>  |
| 2020 年 3 月 | [1.0.5](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.5) |<li>添加了New-CsBatchPolicyAssignmentOperation</li> |
| 2020 年 2 月 | [1.0.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.4) | <li>Get-Team优化</li>  |

## <a name="related-topics"></a>相关主题

[Teams PowerShell 概览](teams-powershell-overview.md)

[安装 Teams PowerShell](teams-powershell-install.md)

[使用 Teams PowerShell 管理Teams](teams-powershell-managing-teams.md)

[Microsoft Teams cmdlet 参考](/powershell/teams/)

[Skype for Business cmdlet 参考](/powershell/skype/intro)
