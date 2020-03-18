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
# <a name="create-people-manager-teams-in-microsoft-teams"></a><span data-ttu-id="30e51-103">在 Microsoft 团队中创建人员经理团队</span><span class="sxs-lookup"><span data-stu-id="30e51-103">Create people manager teams in Microsoft Teams</span></span>


<span data-ttu-id="30e51-104">当你推出 Microsoft 团队，而不是使用 "空白平板" （无团队或频道）启动时，强烈建议你设置团队和频道的基础框架。</span><span class="sxs-lookup"><span data-stu-id="30e51-104">When you roll out Microsoft Teams, rather than launching with a "blank slate" (no teams or channels), we strongly recommend that you set up a base framework of teams and channels.</span></span> <span data-ttu-id="30e51-105">这有助于防止 "团队蔓延"，用户在应在现有团队中创建频道时创建多个团队。</span><span class="sxs-lookup"><span data-stu-id="30e51-105">This helps to prevent "team sprawl," where users create numerous teams when they should be creating channels in existing teams.</span></span> <span data-ttu-id="30e51-106">为了帮助您开始使用精心设计的团队和频道结构，我们创建了一个 PowerShell 脚本，为第一和第二行人员经理创建团队，每个经理的直接下属都是团队成员。</span><span class="sxs-lookup"><span data-stu-id="30e51-106">To help you get started with a well-designed teams and channels structure, we've created a PowerShell script that creates a team for each of your first and second line people managers, with each manager's direct reports as team members.</span></span> <span data-ttu-id="30e51-107">这是一个 "时间点" 脚本（当在组织中添加或删除人员时，它不会自动更新团队或频道）。</span><span class="sxs-lookup"><span data-stu-id="30e51-107">This is a "point-in-time" script (it doesn't update your teams or channels automatically when people are added or removed from an organization).</span></span> <span data-ttu-id="30e51-108">但这是一个有价值的工具，可用于从开始对团队结构施加某些顺序。</span><span class="sxs-lookup"><span data-stu-id="30e51-108">But it's a valuable tool you can use to impose some order on your Teams structure from the start.</span></span> <span data-ttu-id="30e51-109">此脚本读取你的 Azure AD，获取经理及其直接下属的列表。</span><span class="sxs-lookup"><span data-stu-id="30e51-109">This script reads your Azure AD, gets a list of managers and their direct reports.</span></span> <span data-ttu-id="30e51-110">它使用此列表为每个人员经理创建一个团队。</span><span class="sxs-lookup"><span data-stu-id="30e51-110">It uses this list to create one team per people manager.</span></span> 

## <a name="how-to-use-the-powershell-script"></a><span data-ttu-id="30e51-111">如何使用 PowerShell 脚本</span><span class="sxs-lookup"><span data-stu-id="30e51-111">How to use the PowerShell script</span></span> 

<span data-ttu-id="30e51-112">首先运行[导出管理器及其定向脚本](scripts/powershell-script-create-teams-from-managers-export-managers.md)（假设你已运行[connect-AzureAd](https://docs.microsoft.com/powershell/module/azuread/connect-azuread?view=azureadps-2.0)和[MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps) PowerShell 模块）。</span><span class="sxs-lookup"><span data-stu-id="30e51-112">Start by running the [Export managers and their directs script](scripts/powershell-script-create-teams-from-managers-export-managers.md) (which assumes you've already run the [Connect-AzureAd](https://docs.microsoft.com/powershell/module/azuread/connect-azuread?view=azureadps-2.0) and [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps) PowerShell modules).</span></span> <span data-ttu-id="30e51-113">*导出管理器及其指导*脚本创建一个制表符分隔的文件（ExportedManagerDirects），该文件列出所有经理及其直接下属。</span><span class="sxs-lookup"><span data-stu-id="30e51-113">The *Export managers and their directs* script creates a tab-delimited file (ExportedManagerDirects.txt) that lists all managers with their direct reports.</span></span> 

<span data-ttu-id="30e51-114">然后，运行 "[创建新人员经理团队" 脚本](scripts/powershell-script-create-teams-from-managers-new-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="30e51-114">Then, run the [Create new people manager teams script](scripts/powershell-script-create-teams-from-managers-new-teams.md).</span></span> <span data-ttu-id="30e51-115">此脚本将在 ExportedManagerDirects 文件中读取并为每个管理器创建团队，并将该经理的直接下属作为成员。</span><span class="sxs-lookup"><span data-stu-id="30e51-115">This script reads in the ExportedManagerDirects.txt file and creates a team for each manager, with that manager's direct reports as members.</span></span> <span data-ttu-id="30e51-116">如果没有为团队启用任何经理或直接，则脚本将跳过它们，并且不会创建团队。</span><span class="sxs-lookup"><span data-stu-id="30e51-116">If any manager or direct isn't enabled for Teams, the script skips them and doesn't create a team.</span></span> <span data-ttu-id="30e51-117">（查看报表，然后在为需要团队的任何人打开团队后重新运行脚本。</span><span class="sxs-lookup"><span data-stu-id="30e51-117">(Review the report, then rerun the script after you've turned on Teams for anybody who needs it.</span></span> <span data-ttu-id="30e51-118">该脚本将不会为已为其创建团队的任何经理创建第二个团队。</span><span class="sxs-lookup"><span data-stu-id="30e51-118">The script won't create a second team for any manager it's already created a team for.)</span></span>

<span data-ttu-id="30e51-119">对于每个团队，该脚本将创建一个常规和 "仅供趣味" 频道。</span><span class="sxs-lookup"><span data-stu-id="30e51-119">For each team, the script creates a General and "Just for fun" channel.</span></span> 

## <a name="best-practices"></a><span data-ttu-id="30e51-120">最佳做法</span><span class="sxs-lookup"><span data-stu-id="30e51-120">Best practices</span></span>

- <span data-ttu-id="30e51-121">要求每位人员经理将组织的危机通信网站添加为每个团队的常规频道的选项卡。</span><span class="sxs-lookup"><span data-stu-id="30e51-121">Ask each people manager to add your organization's crisis communications website as a tab to the General channel for each team.</span></span> 

- <span data-ttu-id="30e51-122">查看新的危机通信应用，方法是阅读3月8日2020博客文章：[使用 Microsoft 团队 + Power Platform 协调危机通信](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715)。</span><span class="sxs-lookup"><span data-stu-id="30e51-122">Check out the new Crisis Communications app by reading this March 8, 2020 blog post: [Coordinate crisis communications using Microsoft Teams + Power Platform](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715).</span></span>

## <a name="related-topics"></a><span data-ttu-id="30e51-123">相关主题</span><span class="sxs-lookup"><span data-stu-id="30e51-123">Related topics</span></span>

[<span data-ttu-id="30e51-124">组织团队的最佳做法</span><span class="sxs-lookup"><span data-stu-id="30e51-124">Best practices for organizing teams</span></span>](best-practices-organizing.md)

[<span data-ttu-id="30e51-125">在 Teams 中创建组织范围内的团队</span><span class="sxs-lookup"><span data-stu-id="30e51-125">Create an org-wide team in Teams</span></span>](create-an-org-wide-team.md)
