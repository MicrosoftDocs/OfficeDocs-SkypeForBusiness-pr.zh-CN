---
title: 在 Microsoft Teams 中创建人员管理器团队
ms.reviewer: pbethi
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: 了解如何使用 PowerShell 脚本为每个经理创建一个团队，并使用其直接作为团队成员。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: bd880e58b2c6818b8738afd5fb4e5efaf78642d4
ms.sourcegitcommit: ff783fad2fb5d412e864e3af2ceaa8fedcd9da07
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/30/2022
ms.locfileid: "66562581"
---
# <a name="create-people-manager-teams-in-microsoft-teams"></a>在 Microsoft Teams 中创建人员管理器团队


推出 Microsoft Teams 时，我们强烈建议你设置团队和频道的基本框架，而不是 (任何团队或频道) “空板”启动。 这有助于防止“团队扩张”，用户在现有团队中创建频道时会创建多个团队。 为了帮助你开始使用设计良好的团队和频道结构，我们创建了一个 PowerShell 脚本，为每个一线和二线人员经理创建一个团队，每个经理的直接报告都是团队成员。 这是一个“时间点”脚本， (当从组织) 添加或删除人员时，它不会自动更新团队或频道。 但是，这是一个有价值的工具，你可以使用它从一开始就对 Teams 结构施加一些顺序。 此脚本读取 Azure AD，获取管理器及其直接报表的列表。 它使用此列表为每个人员经理创建一个团队。 

## <a name="how-to-use-the-powershell-script"></a>如何使用 PowerShell 脚本 

首先运行 [导出管理器及其定向脚本](scripts/powershell-script-create-teams-from-managers-export-managers.md) (假定你已运行 [Connect-AzureAd](/powershell/module/azuread/connect-azuread?view=azureadps-2.0) 和 [Connect-MicrosoftTeams](/powershell/module/teams/connect-microsoftteams?view=teams-ps) PowerShell 模块) 。 *导出管理器及其定向* 脚本创建一个选项卡分隔文件 (ExportedManagerDirects.txt) ，其中列出了具有其直接报表的所有管理器。 

然后，运行 [“新建人员管理器团队”脚本](scripts/powershell-script-create-teams-from-managers-new-teams.md)。 此脚本在ExportedManagerDirects.txt文件中读取，并为每个经理创建一个团队，该经理的直接报表作为成员。 如果未为 Teams 启用任何管理器或直接管理器，脚本将跳过它们，并且不会创建团队。  (查看报表，然后在为任何需要它的人启用 Teams 后重新运行脚本。 该脚本不会为已为其创建团队的任何经理创建第二个团队) 

对于每个团队，该脚本将创建一个“常规”和“只是为了好玩”频道。 

## <a name="best-practices"></a>最佳做法

- 要求每个人员经理将组织的危机通信网站作为选项卡添加到每个团队的“常规”频道。 

- 阅读本 2020 年 3 月 8 日的博客文章： [使用 Microsoft Teams + Power Platform 协调危机通信](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715)，查看新的危机通信应用。

## <a name="related-topics"></a>相关主题

[组织团队的最佳做法](best-practices-organizing.md)

[在 Teams 中创建组织范围内的团队](create-an-org-wide-team.md)