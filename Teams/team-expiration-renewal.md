---
title: Microsoft 团队中的团队过期和续订
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: abgupta
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: 了解有关团队过期和续订以及如何使用 Microsoft 365 组过期策略自动清理 Microsoft 团队中未使用的团队的信息。
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 697e36085169e0666e6a821a66c763be39cf9425
ms.sourcegitcommit: 6a4bd155e73ab21944dd5f4f0c776e4cd0508147
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/24/2020
ms.locfileid: "44868519"
---
# <a name="team-expiration-and-renewal-in-microsoft-teams"></a><span data-ttu-id="2c2c6-103">Microsoft 团队中的团队过期和续订</span><span class="sxs-lookup"><span data-stu-id="2c2c6-103">Team expiration and renewal in Microsoft Teams</span></span>

<span data-ttu-id="2c2c6-104">具有大量团队的组织通常会有团队，这些团队永远不会真正使用。</span><span class="sxs-lookup"><span data-stu-id="2c2c6-104">Organizations with a large number of teams often have teams that are never actually used.</span></span> <span data-ttu-id="2c2c6-105">出现这种情况的原因有多种，其中包括产品实验、短期团队协作或团队所有者离开组织。</span><span class="sxs-lookup"><span data-stu-id="2c2c6-105">This can happen because of several reasons including product experimentation, short-term team collaboration, or team owners leaving the organization.</span></span> <span data-ttu-id="2c2c6-106">随着时间的推移，此类团队可以积累和创造对租户资源的负担。</span><span class="sxs-lookup"><span data-stu-id="2c2c6-106">Over time, such teams can accumulate and create a burden on tenant resources.</span></span>  

<span data-ttu-id="2c2c6-107">若要将未使用的团队的数量与管理员进行路管理，您可以使用[Microsoft 365 组过期策略](https://docs.microsoft.com/microsoft-365/admin/create-groups/office-365-groups-expiration-policy)自动清理未使用的团队。</span><span class="sxs-lookup"><span data-stu-id="2c2c6-107">To curb the number of unused teams, as an admin, you can use [Microsoft 365 group expiration policy](https://docs.microsoft.com/microsoft-365/admin/create-groups/office-365-groups-expiration-policy) to automatically clean up unused teams.</span></span> <span data-ttu-id="2c2c6-108">由于团队由组支持，组过期策略也会自动应用到团队。</span><span class="sxs-lookup"><span data-stu-id="2c2c6-108">Because teams are backed by groups, group expiration policies automatically apply to teams as well.</span></span>

<span data-ttu-id="2c2c6-109">当你将过期策略应用到团队时，团队所有者将在团队的到期日期之前的30天、15天和1天内收到团队续订通知。</span><span class="sxs-lookup"><span data-stu-id="2c2c6-109">When you apply an expiration policy to a team, a team owner receives a notification for team renewal 30 days, 15 days and 1 day before the team's expiration date.</span></span> <span data-ttu-id="2c2c6-110">当团队所有者收到通知时，他们可以单击 "团队设置" 中的 "**立即续订**" 以续订团队。</span><span class="sxs-lookup"><span data-stu-id="2c2c6-110">When the team owner receives the notification, they can click **Renew now** in team settings to renew the team.</span></span>

<span data-ttu-id="2c2c6-111">!["立即续订" 按钮的屏幕截图，用于在团队设置中续订团队](media/team-expiration.png ""立即续订" 按钮的屏幕截图，用于在团队设置中续订团队")</span><span class="sxs-lookup"><span data-stu-id="2c2c6-111">![Screenshot of the Renew Now button to renew a team in team settings](media/team-expiration.png "Screenshot of the Renew Now button to renew a team in team settings")</span></span>

<span data-ttu-id="2c2c6-112">如果团队所有者不续订团队，则会将团队置于 "软删除" 状态，这意味着它可以在未来30天内还原。</span><span class="sxs-lookup"><span data-stu-id="2c2c6-112">If the team owner doesn't renew the team, the team is put in a "soft-deleted" state, which means it can be restored within the next 30 days.</span></span>

## <a name="team-auto-renewal"></a><span data-ttu-id="2c2c6-113">团队自动续订</span><span class="sxs-lookup"><span data-stu-id="2c2c6-113">Team auto-renewal</span></span>

<span data-ttu-id="2c2c6-114">有时团队所有者无法续订团队，可能是因为他们忘记续订或在续订到期时离开。</span><span class="sxs-lookup"><span data-stu-id="2c2c6-114">There can be times when a team owner is unable to renew the team perhaps because they forgot to renew or were away when renewal was due.</span></span> <span data-ttu-id="2c2c6-115">在这些情况下，由于适用于团队的过期策略，活动团队可能会被删除。</span><span class="sxs-lookup"><span data-stu-id="2c2c6-115">In these scenarios, a team in active use can get deleted because of expiration policies that apply to the team.</span></span>  

<span data-ttu-id="2c2c6-116">为了防止意外删除，将自动为组过期策略中的团队启用自动续订。</span><span class="sxs-lookup"><span data-stu-id="2c2c6-116">To prevent accidental deletion, auto-renewal is automatically enabled for a team in the group expiration policy.</span></span> <span data-ttu-id="2c2c6-117">设置组过期策略时，在其到期日期之前至少拥有一个频道访问的任何团队将自动续订，并且不会与团队所有者进行任何手动干预。</span><span class="sxs-lookup"><span data-stu-id="2c2c6-117">When the group expiration policy is set up, any team that has at least one channel visit from any team member before its expiration date is automatically renewed without any manual intervention from the team owner.</span></span>

## <a name="known-issues"></a><span data-ttu-id="2c2c6-118">已知问题</span><span class="sxs-lookup"><span data-stu-id="2c2c6-118">Known issues</span></span>

<span data-ttu-id="2c2c6-119">**团队和基础组的到期日期不匹配**</span><span class="sxs-lookup"><span data-stu-id="2c2c6-119">**Expiration date of team and underlying group don't match**</span></span>

<span data-ttu-id="2c2c6-120">在续订团队之前，先续订支持团队的组。</span><span class="sxs-lookup"><span data-stu-id="2c2c6-120">Before a team is renewed, the group that backs the team is renewed first.</span></span> <span data-ttu-id="2c2c6-121">作为续订的一部分，将在组中为未来日期设置新的到期日期。</span><span class="sxs-lookup"><span data-stu-id="2c2c6-121">As part of renewal, a new expiry date is set on the group for a future date.</span></span> <span data-ttu-id="2c2c6-122">在团队中，此新日期可能不会立即显示。</span><span class="sxs-lookup"><span data-stu-id="2c2c6-122">This new date may not be immediately visible in Teams.</span></span> <span data-ttu-id="2c2c6-123">同步最多可能需要24小时。如果你看到团队及其基础组的到期日期之间的差异，请等待24小时，然后再寻求进一步支持。</span><span class="sxs-lookup"><span data-stu-id="2c2c6-123">It can take up to 24 hours to sync. If you see a discrepancy between the expiry date for a team and its underlying group, wait 24 hours before seeking further support.</span></span>
