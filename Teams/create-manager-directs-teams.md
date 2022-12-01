---
title: 在 Microsoft Teams 中创建人员经理团队
ms.reviewer: pbethi
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: 了解如何使用 PowerShell 脚本为每个经理创建一个团队，其直接成员身份为团队成员。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.custom: chat-teams-channels-revamp
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 89a820a1b828621df2a129b7a972408e7280b3da
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198924"
---
# <a name="create-people-manager-teams-in-microsoft-teams"></a>在 Microsoft Teams 中创建人员经理团队


当你推出Microsoft Teams 时，我们强烈建议你设置团队和频道的基本框架，而不是使用“空白板” (没有团队或频道) 启动。 这有助于防止“团队扩张”，用户应在现有团队中创建频道时创建大量团队。 为了帮助你开始使用设计良好的团队和频道结构，我们创建了一个 PowerShell 脚本，为每个一线和第二线人员经理创建一个团队，每个经理的直接下属都是团队成员。 这是一个“时间点”脚本， (在组织) 添加或删除人员时，它不会自动更新你的团队或频道。 但它是一个有价值的工具，可用于从一开始就对 Teams 结构施加某种顺序。 此脚本读取 Azure AD，获取经理及其直接下属的列表。 它使用此列表为每个人员经理创建一个团队。 

## <a name="how-to-use-the-powershell-script"></a>如何使用 PowerShell 脚本 

首先运行 [导出管理器及其直接脚本](scripts/powershell-script-create-teams-from-managers-export-managers.md) (假定你已) 运行 [Connect-AzureAd](/powershell/module/azuread/connect-azuread) 和 [Connect-MicrosoftTeams](/powershell/module/teams/connect-microsoftteams) PowerShell 模块。 *导出经理及其直接* 脚本创建制表符分隔的文件 (ExportedManagerDirects.txt) ，其中列出了所有经理及其直接下属。 

然后，运行 [“创建新的人员经理团队”脚本](scripts/powershell-script-create-teams-from-managers-new-teams.md)。 此脚本在 ExportedManagerDirects.txt 文件中读取，并为每个经理创建一个团队，该经理的直接下属作为成员。 如果未为 Teams 启用任何经理或直接，则脚本会跳过它们，并且不会创建团队。  (查看报表，然后在为任何需要它的人打开 Teams 后重新运行脚本。 该脚本不会为其已为其创建团队的任何经理创建第二个团队。

对于每个团队，该脚本都会创建一个“常规”和“仅为了娱乐”频道。 

## <a name="best-practices"></a>最佳做法

- 要求每个人员经理将组织的危机通信网站作为选项卡添加到每个团队的“常规”频道。 

- 阅读此 2020 年 3 月 8 日博客文章：[使用 Microsoft Teams + Power Platform 协调危机通信](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715)，查看新的 Crisis Communications 应用。

## <a name="related-topics"></a>相关主题

[组织团队的最佳做法](best-practices-organizing.md)

[在 Teams 中创建组织范围内的团队](create-an-org-wide-team.md)