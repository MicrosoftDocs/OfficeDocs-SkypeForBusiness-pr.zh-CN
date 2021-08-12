---
title: 在 Microsoft Teams
ms.reviewer: pbethi
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: 了解如何使用 PowerShell 脚本为每个经理创建一个团队，其直接下属是团队成员。
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ce7fb0a34f202481df0062367ec7a905b84848d21e7a2e5e4bce73bea4073eac
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54282805"
---
# <a name="create-people-manager-teams-in-microsoft-teams"></a>在 Microsoft Teams


在推出Microsoft Teams时，我们强烈建议你设置团队和频道的基础框架，而不是使用"空白 ("启动) 团队或频道。 这有助于防止"团队扩展"，即当用户应在现有团队中创建频道时创建大量团队。 为了帮助你开始使用设计良好的团队和频道结构，我们创建了一个 PowerShell 脚本，该脚本为每个第一和第二线人员经理创建一个团队，每个经理的直接下属作为团队成员。 这是一个"时间点"脚本 (在从组织内部添加或删除人员时，它不会自动更新团队或) 。 但是，它是一个有价值的工具，可用于从一开始对Teams施加某种顺序。 此脚本读取 Azure AD，获取经理及其直接下属的列表。 它使用此列表为每个人员经理创建一个团队。 

## <a name="how-to-use-the-powershell-script"></a>如何使用 PowerShell 脚本 

首先运行[导出管理器及其 directs](scripts/powershell-script-create-teams-from-managers-export-managers.md)脚本 (该脚本假设已运行[连接-AzureAd](/powershell/module/azuread/connect-azuread?view=azureadps-2.0)和[连接-MicrosoftTeams](/powershell/module/teams/connect-microsoftteams?view=teams-ps) PowerShell 模块) 。 导出 *管理器及其直接脚本* 创建制表符分隔的文件 (ExportedManagerDirects.txt) ，其中列出了所有经理及其直接下属。 

然后，运行 ["创建新人员管理器团队"脚本](scripts/powershell-script-create-teams-from-managers-new-teams.md)。 此脚本读取ExportedManagerDirects.txt文件，并为每个经理创建一个团队，该经理的直接下属作为成员。 如果未为管理员或直接管理员启用Teams，脚本将跳过它们，不会创建团队。  (查看报表，然后在为Teams启用脚本后重新运行该脚本。 该脚本不会为已创建团队的任何经理创建第二个) 

对于每个团队，该脚本创建一个"常规"和"只是为了娱乐"频道。 

## <a name="best-practices"></a>最佳做法

- 请让每个人员经理将组织的问题沟通网站作为选项卡添加到每个团队的"常规"频道。 

- 阅读此 2020 年 3 月 8 日博客文章：使用 Microsoft Teams [+ Power Platform 协调Microsoft Teams沟通，查看新的](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715)"政治沟通"应用。

## <a name="related-topics"></a>相关主题

[组织团队的最佳实践](best-practices-organizing.md)

[在 Teams 中创建组织范围内的团队](create-an-org-wide-team.md)