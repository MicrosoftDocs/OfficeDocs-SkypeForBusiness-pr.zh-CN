---
title: 在 Microsoft 团队中创建人员经理团队
ms.reviewer: pbethi
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: 了解如何使用 PowerShell 脚本为每个经理创建团队，并将其指引作为团队成员使用。
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: eb6cd6ed74bebd0cbd729b828c152b9f04d1fc1f
ms.sourcegitcommit: cfaae3ecbf853766de788b4825a86e04f68868ca
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/18/2020
ms.locfileid: "42796188"
---
# <a name="create-people-manager-teams-in-microsoft-teams"></a>在 Microsoft 团队中创建人员经理团队


当你推出 Microsoft 团队，而不是使用 "空白平板" （无团队或频道）启动时，强烈建议你设置团队和频道的基础框架。 这有助于防止 "团队蔓延"，用户在应在现有团队中创建频道时创建多个团队。 为了帮助您开始使用精心设计的团队和频道结构，我们创建了一个 PowerShell 脚本，为第一和第二行人员经理创建团队，每个经理的直接下属都是团队成员。 这是一个 "时间点" 脚本（当在组织中添加或删除人员时，它不会自动更新团队或频道）。 但这是一个有价值的工具，可用于从开始对团队结构施加某些顺序。 此脚本读取你的 Azure AD，获取经理及其直接下属的列表。 它使用此列表为每个人员经理创建一个团队。 

## <a name="how-to-use-the-powershell-script"></a>如何使用 PowerShell 脚本 

首先运行[导出管理器及其定向脚本](scripts/powershell-script-create-teams-from-managers-export-managers.md)（假设你已运行[connect-AzureAd](https://docs.microsoft.com/powershell/module/azuread/connect-azuread?view=azureadps-2.0)和[MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps) PowerShell 模块）。 *导出管理器及其指导*脚本创建一个制表符分隔的文件（ExportedManagerDirects），该文件列出所有经理及其直接下属。 

然后，运行 "[创建新人员经理团队" 脚本](scripts/powershell-script-create-teams-from-managers-new-teams.md)。 此脚本将在 ExportedManagerDirects 文件中读取并为每个管理器创建团队，并将该经理的直接下属作为成员。 如果没有为团队启用任何经理或直接，则脚本将跳过它们，并且不会创建团队。 （查看报表，然后在为需要团队的任何人打开团队后重新运行脚本。 该脚本将不会为已为其创建团队的任何经理创建第二个团队。

对于每个团队，该脚本将创建一个常规和 "仅供趣味" 频道。 

## <a name="best-practices"></a>最佳做法

- 要求每位人员经理将组织的危机通信网站添加为每个团队的常规频道的选项卡。 

- 查看新的危机通信应用，方法是阅读3月8日2020博客文章：[使用 Microsoft 团队 + Power Platform 协调危机通信](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715)。

## <a name="related-topics"></a>相关主题

[组织团队的最佳做法](best-practices-organizing.md)

[在 Teams 中创建组织范围内的团队](create-an-org-wide-team.md)
