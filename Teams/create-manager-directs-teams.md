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
ms.openlocfilehash: fa7c82ec584791107e5d269ee40bccba272d20b4
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094408"
---
# <a name="create-people-manager-teams-in-microsoft-teams"></a><span data-ttu-id="c6b29-103">在 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c6b29-103">Create people manager teams in Microsoft Teams</span></span>


<span data-ttu-id="c6b29-104">在推出Microsoft Teams时，我们强烈建议你设置团队和频道的基础框架，而不是使用"空白 ("启动) 团队或频道。</span><span class="sxs-lookup"><span data-stu-id="c6b29-104">When you roll out Microsoft Teams, rather than launching with a "blank slate" (no teams or channels), we strongly recommend that you set up a base framework of teams and channels.</span></span> <span data-ttu-id="c6b29-105">这有助于防止"团队扩展"，即当用户应在现有团队中创建频道时创建大量团队。</span><span class="sxs-lookup"><span data-stu-id="c6b29-105">This helps to prevent "team sprawl," where users create numerous teams when they should be creating channels in existing teams.</span></span> <span data-ttu-id="c6b29-106">为了帮助你开始使用设计良好的团队和频道结构，我们创建了一个 PowerShell 脚本，该脚本为每个第一和第二线人员经理创建一个团队，每个经理的直接下属作为团队成员。</span><span class="sxs-lookup"><span data-stu-id="c6b29-106">To help you get started with a well-designed teams and channels structure, we've created a PowerShell script that creates a team for each of your first and second line people managers, with each manager's direct reports as team members.</span></span> <span data-ttu-id="c6b29-107">这是一个"时间点"脚本 (在从组织内部添加或删除人员时，它不会自动更新团队或) 。</span><span class="sxs-lookup"><span data-stu-id="c6b29-107">This is a "point-in-time" script (it doesn't update your teams or channels automatically when people are added or removed from an organization).</span></span> <span data-ttu-id="c6b29-108">但是，它是一个有价值的工具，可用于从一开始对Teams施加某种顺序。</span><span class="sxs-lookup"><span data-stu-id="c6b29-108">But it's a valuable tool you can use to impose some order on your Teams structure from the start.</span></span> <span data-ttu-id="c6b29-109">此脚本读取 Azure AD，获取经理及其直接下属的列表。</span><span class="sxs-lookup"><span data-stu-id="c6b29-109">This script reads your Azure AD, gets a list of managers and their direct reports.</span></span> <span data-ttu-id="c6b29-110">它使用此列表为每个人员经理创建一个团队。</span><span class="sxs-lookup"><span data-stu-id="c6b29-110">It uses this list to create one team per people manager.</span></span> 

## <a name="how-to-use-the-powershell-script"></a><span data-ttu-id="c6b29-111">如何使用 PowerShell 脚本</span><span class="sxs-lookup"><span data-stu-id="c6b29-111">How to use the PowerShell script</span></span> 

<span data-ttu-id="c6b29-112">首先运行[导出管理器及其 directs](scripts/powershell-script-create-teams-from-managers-export-managers.md)脚本 (该脚本假设已运行[连接-AzureAd](/powershell/module/azuread/connect-azuread?view=azureadps-2.0)和[连接-MicrosoftTeams](/powershell/module/teams/connect-microsoftteams?view=teams-ps) PowerShell 模块) 。</span><span class="sxs-lookup"><span data-stu-id="c6b29-112">Start by running the [Export managers and their directs script](scripts/powershell-script-create-teams-from-managers-export-managers.md) (which assumes you've already run the [Connect-AzureAd](/powershell/module/azuread/connect-azuread?view=azureadps-2.0) and [Connect-MicrosoftTeams](/powershell/module/teams/connect-microsoftteams?view=teams-ps) PowerShell modules).</span></span> <span data-ttu-id="c6b29-113">导出 *管理器及其直接脚本* 创建制表符分隔的文件 (ExportedManagerDirects.txt) ，其中列出了所有经理及其直接下属。</span><span class="sxs-lookup"><span data-stu-id="c6b29-113">The *Export managers and their directs* script creates a tab-delimited file (ExportedManagerDirects.txt) that lists all managers with their direct reports.</span></span> 

<span data-ttu-id="c6b29-114">然后，运行 ["创建新人员管理器团队"脚本](scripts/powershell-script-create-teams-from-managers-new-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="c6b29-114">Then, run the [Create new people manager teams script](scripts/powershell-script-create-teams-from-managers-new-teams.md).</span></span> <span data-ttu-id="c6b29-115">此脚本读取ExportedManagerDirects.txt文件，并为每个经理创建一个团队，该经理的直接下属作为成员。</span><span class="sxs-lookup"><span data-stu-id="c6b29-115">This script reads in the ExportedManagerDirects.txt file and creates a team for each manager, with that manager's direct reports as members.</span></span> <span data-ttu-id="c6b29-116">如果未为管理员或直接管理员启用Teams，脚本将跳过它们，不会创建团队。</span><span class="sxs-lookup"><span data-stu-id="c6b29-116">If any manager or direct isn't enabled for Teams, the script skips them and doesn't create a team.</span></span> <span data-ttu-id="c6b29-117"> (查看报表，然后在为Teams启用脚本后重新运行该脚本。</span><span class="sxs-lookup"><span data-stu-id="c6b29-117">(Review the report, then rerun the script after you've turned on Teams for anybody who needs it.</span></span> <span data-ttu-id="c6b29-118">该脚本不会为已创建团队的任何经理创建第二个) </span><span class="sxs-lookup"><span data-stu-id="c6b29-118">The script won't create a second team for any manager it's already created a team for.)</span></span>

<span data-ttu-id="c6b29-119">对于每个团队，该脚本创建一个"常规"和"只是为了娱乐"频道。</span><span class="sxs-lookup"><span data-stu-id="c6b29-119">For each team, the script creates a General and "Just for fun" channel.</span></span> 

## <a name="best-practices"></a><span data-ttu-id="c6b29-120">最佳做法</span><span class="sxs-lookup"><span data-stu-id="c6b29-120">Best practices</span></span>

- <span data-ttu-id="c6b29-121">请让每个人员经理将组织的问题沟通网站作为选项卡添加到每个团队的"常规"频道。</span><span class="sxs-lookup"><span data-stu-id="c6b29-121">Ask each people manager to add your organization's crisis communications website as a tab to the General channel for each team.</span></span> 

- <span data-ttu-id="c6b29-122">阅读此 2020 年 3 月 8 日博客文章：使用 Microsoft Teams [+ Power Platform 协调Microsoft Teams沟通，查看新的](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715)"政治沟通"应用。</span><span class="sxs-lookup"><span data-stu-id="c6b29-122">Check out the new Crisis Communications app by reading this March 8, 2020 blog post: [Coordinate crisis communications using Microsoft Teams + Power Platform](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715).</span></span>

## <a name="related-topics"></a><span data-ttu-id="c6b29-123">相关主题</span><span class="sxs-lookup"><span data-stu-id="c6b29-123">Related topics</span></span>

[<span data-ttu-id="c6b29-124">组织团队的最佳实践</span><span class="sxs-lookup"><span data-stu-id="c6b29-124">Best practices for organizing teams</span></span>](best-practices-organizing.md)

[<span data-ttu-id="c6b29-125">在 Teams 中创建组织范围内的团队</span><span class="sxs-lookup"><span data-stu-id="c6b29-125">Create an org-wide team in Teams</span></span>](create-an-org-wide-team.md)