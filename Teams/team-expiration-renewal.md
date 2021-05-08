---
title: 团队过期和续订Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: abgupta
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: 了解团队过期和续订，以及如何使用Microsoft 365过期策略自动清理组中未使用的Microsoft Teams。
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 606d957b703725d631beec38237f4d9b4272433e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116950"
---
# <a name="team-expiration-and-renewal-in-microsoft-teams"></a><span data-ttu-id="aa780-103">团队过期和续订Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="aa780-103">Team expiration and renewal in Microsoft Teams</span></span>

<span data-ttu-id="aa780-104">具有大量团队的组织通常拥有从未实际使用的团队。</span><span class="sxs-lookup"><span data-stu-id="aa780-104">Organizations with a large number of teams often have teams that are never actually used.</span></span> <span data-ttu-id="aa780-105">发生这种情况的原因有多种，包括产品试验、短期团队协作或团队所有者离开组织。</span><span class="sxs-lookup"><span data-stu-id="aa780-105">This can happen because of several reasons including product experimentation, short-term team collaboration, or team owners leaving the organization.</span></span> <span data-ttu-id="aa780-106">随着时间的推移，此类团队可能会累积，给租户资源带来负担。</span><span class="sxs-lookup"><span data-stu-id="aa780-106">Over time, such teams can accumulate and create a burden on tenant resources.</span></span>  

<span data-ttu-id="aa780-107">若要减少未使用的团队数，作为管理员，可以使用Microsoft 365[过期](/microsoft-365/admin/create-groups/office-365-groups-expiration-policy)策略自动清理未使用的团队。</span><span class="sxs-lookup"><span data-stu-id="aa780-107">To curb the number of unused teams, as an admin, you can use [Microsoft 365 group expiration policy](/microsoft-365/admin/create-groups/office-365-groups-expiration-policy) to automatically clean up unused teams.</span></span> <span data-ttu-id="aa780-108">由于团队受组支持，因此组过期策略也会自动应用于团队。</span><span class="sxs-lookup"><span data-stu-id="aa780-108">Because teams are backed by groups, group expiration policies automatically apply to teams as well.</span></span>

<span data-ttu-id="aa780-109">向团队应用过期策略时，团队所有者将在团队到期日期之前 30 天、15 天和 1 天收到团队续订通知。</span><span class="sxs-lookup"><span data-stu-id="aa780-109">When you apply an expiration policy to a team, a team owner receives a notification for team renewal 30 days, 15 days and 1 day before the team's expiration date.</span></span> <span data-ttu-id="aa780-110">当团队所有者收到通知时，他们可以在团队设置中单击"立即续订"以续订团队。</span><span class="sxs-lookup"><span data-stu-id="aa780-110">When the team owner receives the notification, they can click **Renew now** in team settings to renew the team.</span></span>

<span data-ttu-id="aa780-111">![在团队设置中续订团队的"立即续订"按钮的屏幕截图](media/team-expiration.png "在团队设置中续订团队的&quot;立即续订&quot;按钮的屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="aa780-111">![Screenshot of the Renew Now button to renew a team in team settings](media/team-expiration.png "Screenshot of the Renew Now button to renew a team in team settings")</span></span>

<span data-ttu-id="aa780-112">如果团队所有者未续订团队，且在过期策略结束之前团队中没有任何进一步的活动，则团队将置于"软删除"状态，这意味着它可以在接下来 30 天内还原。</span><span class="sxs-lookup"><span data-stu-id="aa780-112">If the team owner doesn't renew the team and there is no further activity on the team until the end of the expiration policy, the team is put in a "soft-deleted" state, which means it can be restored within the next 30 days.</span></span>

## <a name="team-auto-renewal"></a><span data-ttu-id="aa780-113">团队自动续订</span><span class="sxs-lookup"><span data-stu-id="aa780-113">Team auto-renewal</span></span>

<span data-ttu-id="aa780-114">有时，团队所有者可能因为忘记续订或续订到期时离开而无法续订团队。</span><span class="sxs-lookup"><span data-stu-id="aa780-114">There can be times when a team owner is unable to renew the team perhaps because they forgot to renew or were away when renewal was due.</span></span> <span data-ttu-id="aa780-115">在这些情况下，由于适用于该团队的过期策略，活动使用中的团队可能会被删除。</span><span class="sxs-lookup"><span data-stu-id="aa780-115">In these scenarios, a team in active use can get deleted because of expiration policies that apply to the team.</span></span>  

<span data-ttu-id="aa780-116">为了防止意外删除，将自动为组过期策略中的团队启用自动续订。</span><span class="sxs-lookup"><span data-stu-id="aa780-116">To prevent accidental deletion, auto-renewal is automatically enabled for a team in the group expiration policy.</span></span> <span data-ttu-id="aa780-117">设置组过期策略后，在到期日期之前至少具有任何团队成员的一个频道访问的任何团队都会自动续订，无需团队所有者的任何手动干预。</span><span class="sxs-lookup"><span data-stu-id="aa780-117">When the group expiration policy is set up, any team that has at least one channel visit from any team member before its expiration date is automatically renewed without any manual intervention from the team owner.</span></span>

## <a name="known-issues"></a><span data-ttu-id="aa780-118">已知问题</span><span class="sxs-lookup"><span data-stu-id="aa780-118">Known issues</span></span>

<span data-ttu-id="aa780-119">**团队和基础组的到期日期不匹配**</span><span class="sxs-lookup"><span data-stu-id="aa780-119">**Expiration date of team and underlying group don't match**</span></span>

<span data-ttu-id="aa780-120">在续订团队之前，先续订支持该团队的组。</span><span class="sxs-lookup"><span data-stu-id="aa780-120">Before a team is renewed, the group that backs the team is renewed first.</span></span> <span data-ttu-id="aa780-121">作为续订的一部分，将针对组设置新的过期日期作为未来日期。</span><span class="sxs-lookup"><span data-stu-id="aa780-121">As part of renewal, a new expiry date is set on the group for a future date.</span></span> <span data-ttu-id="aa780-122">此新日期可能不会立即显示在Teams。</span><span class="sxs-lookup"><span data-stu-id="aa780-122">This new date may not be immediately visible in Teams.</span></span> <span data-ttu-id="aa780-123">同步最多可能需要 24 小时。如果发现团队及其基础组的到期日期存在差异，请等待 24 小时，然后寻求进一步的支持。</span><span class="sxs-lookup"><span data-stu-id="aa780-123">It can take up to 24 hours to sync. If you see a discrepancy between the expiry date for a team and its underlying group, wait 24 hours before seeking further support.</span></span>