---
title: Microsoft Teams PowerShell 发行说明
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
description: 了解 Teams PowerShell 中的最新更改。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9687dcdca15507caad0c52ef13feb2c12fb61e9a
ms.sourcegitcommit: 616403037ddb2d44f06cd9b2eaa9da699b119ef8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/15/2021
ms.locfileid: "51768332"
---
# <a name="microsoft-teams-powershell-release-notes"></a>Microsoft Teams PowerShell 发行说明

本页提供公开发布和公共预览版的最新 Teams PowerShell 更改日志。

## <a name="release-notes"></a>发行说明

> [!NOTE]
> **-preview** 在下面的版本列中表示 Teams PowerShell 公共预览版的更新。

| 日期 | 版本 | 更新 |
|------- | -------------------- | ------------------------------ |
| 2021 年 4 月 | [2.1.0-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/2.1.0-preview) | <li>修复了现有 cmdlet (例如 Get-CsTeamsNetworkRoamingPolicy、Get-CsTeamsMeetingPolicy、Get-CsTeamsMessagingPolicy 等) 的格式。</li><li>更新了策略管理 cmdlet 的参数列表。</li>|
| 2021 年 3 月 | [2.0.0](https://www.powershellgallery.com/packages/MicrosoftTeams/2.0.0) | <li>使用 MSAL 进行身份验证&授权</li> <li>Connect-MicrosoftTeams是所有 cmdlet 的入口点。</li><li>New-csOnlineSession 不再可用。 它已被 Connect-MicrosoftTeams 取代。</li><li>不再需要 Enable-csonlinesessionforreconnection。 此功能已在 Teams PowerShell 模块中本机实现。</li> <li>重构策略包 cmdlet 并添加组包分配</li><li>Get-Team cmdlet 的重要性能增强</li> <li>改进了现有 cmdlet 的日志记录和调试选项 </li> <li>添加了模板管理 cmdlet</li> <li>弃用New-CsOnlineSession</li>|
| 2021 年 2 月 | [1.1.11-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.11-preview) | <li>添加了模板管理 cmdlet</li><li>适用于 Get-Team cmdlet 的 Mezzo 和批处理增强功能</li> <li>改进了现有 cmdlet 的日志记录和调试选项 </li> <li>重构的策略包 cmdlet</li>|
| 2020 年 12 月 | [1.1.10-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.10-preview) | <li>更新了 New-team cmdlet，增加了重试和睡眠持续时间</li>|
| 2020 年 12 月 | [1.1.9-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.9-preview) | <li>Skype for Business Online 集成更新</li><li>修复了 Teams 中重复Connect-Microsoft的问题</li>|
| 2020 年 11 月 | [1.1.8-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.8-preview) | <li>添加自定义策略包 cmdlet</li><li>目标层次结构上传命令的修复</li>|
| 2020 年 11 月 | [1.1.7-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.7-preview) | <li>使用 MSAL 进行身份验证&授权</li><li>重构策略包 cmdlet 并添加组包分配</li><li>重构目标层次结构上传命令以使用异步模型</li> <li>如果用户不使用 -credential 参数，则初始身份验证期间会提示用户两次。 用户可以使用 -credential 参数传递凭据，以避免重复的提示。 此行为将在下一版本中修复。</li> |
| 2020 年 9 月 | [1.1.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.6) | <li>Skype for Business Online 连接器集成</li> |
| 2020 年 9 月 | [1.1.5-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.5-preview) | <li>Skype for Business Online 连接器集成</li> |
| 2020 年 7 月 | [1.1.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.4) | <li>添加了 [组策略分配 cmdlet](./assign-policies.md#assign-a-policy-to-a-group)</li> |
| 2020 年 6 月 | [1.1.3-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.3-preview) | <li>Skype for Business Online 连接器集成<li>Get-Team优化<li>增强的可靠性</li> |
| 2020 年 6 月 | [1.0.7](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.7) | <li>添加了 Cmdlet 预加载<li>.Net Framework 优化</li>   |
| 2020 年 4 月 | [1.0.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.6) | <li>验证码和程序集签名<li>添加了Get-CsPolicyPackage<li>添加了Get-CsUserPolicyPackage<li>添加了Get-CsUserPolicyPackageRecommendation<li>添加了Grant-CsUserPolicyPackage<li>添加了New-CsBatchPolicyPackageAssignmentOperation<li>添加了Set-TeamArchivedState<li>添加了Set-TeamPicture<li>已删除Get-TeamHelp</li>  |
| 2020 年 3 月 | [1.0.5](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.5) |<li>添加了New-CsBatchPolicyAssignmentOperation</li> |
| 2020 年 2 月 | [1.0.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.4) | <li>Get-Team优化</li>  |

## <a name="related-topics"></a>相关主题

[Teams PowerShell 概览](teams-powershell-overview.md)

[安装 Teams PowerShell](teams-powershell-install.md)

[使用 Teams PowerShell 管理 Teams](teams-powershell-managing-teams.md)

[Microsoft Teams cmdlet 参考](/powershell/teams/?view=teams-ps)

[Skype for Business cmdlet 参考](/powershell/skype/intro?view=skype-ps)
