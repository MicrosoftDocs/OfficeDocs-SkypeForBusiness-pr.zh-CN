---
title: "与 Skype for Business 并行启用 Microsoft Teams"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "并行使用 Skype for Business 和 Microsoft Teams 指导"
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 760fa47db7965e0c2a74b01ae25f1d23d37d3180
ms.sourcegitcommit: 2592b268977460d0d483a75d741b1ce9fa8da908
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2017
---
<a name="enable-microsoft-teams-side-by-side-with-skype-for-business"></a><span data-ttu-id="84e73-103">与 Skype for Business 并行启用 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="84e73-103">Enable Microsoft Teams side-by-side with Skype for Business</span></span> 
=============================================================

<span data-ttu-id="84e73-104">对于具有 Skype for Business Online 现有部署的组织，最近推出的 Microsoft Teams 提供了一个评估 Teams 作为唯一通信与协作解决方案的可能性的机会，提出了在两个解决方案之间进行抉择的挑战，以及它们如何在你的环境中共存。</span><span class="sxs-lookup"><span data-stu-id="84e73-104">For organizations with existing deployments of Skype for Business Online, the recent introduction of Microsoft Teams presents an opportunity to evaluate the potential of Teams as a sole, communications and collaboration solution, and a challenge to tip the scale between the two solutions and how they can coexist in your environment.</span></span>

<span data-ttu-id="84e73-105">如果 Teams 现在可以满足你的业务需求，你可以开始采用 Teams 以作为贵组织唯一的通信与协作解决方案。</span><span class="sxs-lookup"><span data-stu-id="84e73-105">If Teams can meet your business requirements today, you can start adopting Teams to become your single communications and collaboration solution for your organization.</span></span>

<span data-ttu-id="84e73-106">默认情况下，在所有符合条件的租户中启用 Teams。</span><span class="sxs-lookup"><span data-stu-id="84e73-106">Teams is enabled by default, on all eligible tenants.</span></span> <span data-ttu-id="84e73-107">因此，你需要确定如何与 Skype for Business 并行管理 Teams，并继续满足用户期望。</span><span class="sxs-lookup"><span data-stu-id="84e73-107">Therefore, you need to decide on how to manage Teams side-by-side with Skype for Business, and continue to meet user expectations.</span></span>

<span data-ttu-id="84e73-108">通常，有两种主要的并行客户旅程。</span><span class="sxs-lookup"><span data-stu-id="84e73-108">In general, there are two major side-by-side customer journeys.</span></span> <span data-ttu-id="84e73-109">它们是：</span><span class="sxs-lookup"><span data-stu-id="84e73-109">They are:</span></span>

-   <span data-ttu-id="84e73-110">**选项 1：** 不受管理的并行客户旅程。</span><span class="sxs-lookup"><span data-stu-id="84e73-110">**Option 1:** Unmanaged side-by-side customer journey.</span></span>

    <span data-ttu-id="84e73-111">IT 不主动控制并行体验，用户可以选择首选应用。</span><span class="sxs-lookup"><span data-stu-id="84e73-111">IT does not actively control the side-by-side experience, and users are empowered to make the choice of preferred app.</span></span>

-   <span data-ttu-id="84e73-112">**选项 2：** 受管理的并行客户旅程。</span><span class="sxs-lookup"><span data-stu-id="84e73-112">**Option 2:** Managed side-by-side customer journey.</span></span>

    <span data-ttu-id="84e73-113">IT 控制并行体验，带领用户完成逐渐采用 Teams 的旅程，先在 Teams 中采用基于聊天的新型协作工作区（可以进行私人聊天），然后体验会议，最后体验通话。</span><span class="sxs-lookup"><span data-stu-id="84e73-113">IT controls the side-by-side experience, taking users through a journey of gradually introducing Teams to first introduce a new chat-based collaboration workspace with private chat, then meeting experiences, and finally the calling experiences in Teams.</span></span>

![](media/guidance_SkypeforBusiness_image1.png)

<a name="side-by-side-benefits-and-considerations"></a><span data-ttu-id="84e73-114">并行优势和考虑事项</span><span class="sxs-lookup"><span data-stu-id="84e73-114">Side-by-side benefits and considerations</span></span>
----------------------------------------

<span data-ttu-id="84e73-115">在根据贵组织的情况确定正确前进方向时，每种旅程都有要评估的优势和考虑事项。</span><span class="sxs-lookup"><span data-stu-id="84e73-115">Each journey has benefits and considerations to evaluate when determining the right path forward based on your organization's profile.</span></span> <span data-ttu-id="84e73-116">下表比较了受管理和不受管理的并行客户旅程。</span><span class="sxs-lookup"><span data-stu-id="84e73-116">The table below provides the comparisons between managed and unmanaged side-by-side customer journeys.</span></span>


<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="84e73-117">迁移途径</span><span class="sxs-lookup"><span data-stu-id="84e73-117">Migration Paths</span></span></th>
<th align="left"><span data-ttu-id="84e73-118">不受管理的并行</span><span class="sxs-lookup"><span data-stu-id="84e73-118">Unmanaged Side-by-Side</span></span></th>
<th align="left"><span data-ttu-id="84e73-119">受管理的并行</span><span class="sxs-lookup"><span data-stu-id="84e73-119">Managed Side-by-Side</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="84e73-120"><strong>组织情况</strong></span><span class="sxs-lookup"><span data-stu-id="84e73-120"><strong>Organization profile</strong></span></span></td>
<td align="left"><ul>
<li><span data-ttu-id="84e73-121">通常是没有专门的 IT 资源的小型组织</span><span class="sxs-lookup"><span data-stu-id="84e73-121">Typically, smaller organizations with no dedicated IT resources</span></span></li>
<li><span data-ttu-id="84e73-122">IT 允许用户自行选择适合其工作的工具</span><span class="sxs-lookup"><span data-stu-id="84e73-122">IT allows user discretion in selecting right tools for their work</span></span></li>
<li><span data-ttu-id="84e73-123">Skype for Business 主要用途是 IM/P 和会议</span><span class="sxs-lookup"><span data-stu-id="84e73-123">Primary Skype for Business usage is IM/P and meetings</span></span></li>
</ul></td>
<td align="left"><ul><li><span data-ttu-id="84e73-124">通常是大中型组织</span><span class="sxs-lookup"><span data-stu-id="84e73-124">Typically, mid-size to larger organizations</span></span></li>
<li><span data-ttu-id="84e73-125">IT 希望更加严格地控制新工具的部署</span><span class="sxs-lookup"><span data-stu-id="84e73-125">IT wants to control roll out of new tools more rigorously</span></span></li>
<li><span data-ttu-id="84e73-126">现在深入采用 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="84e73-126">Deeper adoption of Skype for Business today</span></span></li>
<li><span data-ttu-id="84e73-127">网络和基础结构的复杂性增加</span><span class="sxs-lookup"><span data-stu-id="84e73-127">Increased complexity in network and infrastructure</span></span></li>
<li><span data-ttu-id="84e73-128">多个位置</span><span class="sxs-lookup"><span data-stu-id="84e73-128">Multiple locations</span></span></p>
<li><span data-ttu-id="84e73-129">首选具有独特 UC 功能的单一应用</span><span class="sxs-lookup"><span data-stu-id="84e73-129">Preference for single app with unique UC capabilities</span></span></li></ul></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="84e73-130"><strong>优势</strong></span><span class="sxs-lookup"><span data-stu-id="84e73-130"><strong>Benefits</strong></span></span></td>
<td align="left"><ul>
<li><span data-ttu-id="84e73-131">利用 Teams 中提供但 Skype for Business 中未提供的功能</span><span class="sxs-lookup"><span data-stu-id="84e73-131">Leverage capabilities in Teams that are not available in Skype for Business</span></span></li>
<li><span data-ttu-id="84e73-132">在 Office 365 中具有增强的新式工作场所</span><span class="sxs-lookup"><span data-stu-id="84e73-132">Enhanced modern workplace within Office 365</span></span></li>
<li><span data-ttu-id="84e73-133">提高了用户灵活性</span><span class="sxs-lookup"><span data-stu-id="84e73-133">Increased user flexibility</span></span></li>
<li><span data-ttu-id="84e73-134">一次性启用所有功能</span><span class="sxs-lookup"><span data-stu-id="84e73-134">Enable all capabilities at once</span></span></li>
</ul></td>
<td align="left"><ul><li><span data-ttu-id="84e73-135">利用 Teams 中提供但 Skype for Business 中未提供的功能</span><span class="sxs-lookup"><span data-stu-id="84e73-135">Leverage capabilities in Teams that are not available in Skype for Business</span></span></li>
<li><span data-ttu-id="84e73-136">在 Office 365 中具有增强的新式工作场所</span><span class="sxs-lookup"><span data-stu-id="84e73-136">Enhanced modern workplace within Office 365</span></span></li>
<li><span data-ttu-id="84e73-137">最大限度地降低用户工作效率影响</span><span class="sxs-lookup"><span data-stu-id="84e73-137">Minimize user productivity impact</span></span></li>
<li><span data-ttu-id="84e73-138">减少功能重叠</span><span class="sxs-lookup"><span data-stu-id="84e73-138">Reduce capability overlap</span></span></li>
<li><span data-ttu-id="84e73-139">顺利为 UC 应用场景选择工具</span><span class="sxs-lookup"><span data-stu-id="84e73-139">Streamline tool choice for UC scenarios</span></span></li>
<li><span data-ttu-id="84e73-140">使组织中的 IT 和业务部门能够根据需要启用功能</span><span class="sxs-lookup"><span data-stu-id="84e73-140">Empower IT and business to enable capabilities as appropriate in organization</span></span></li>
<li><span data-ttu-id="84e73-141">控制用户的改变步伐</span><span class="sxs-lookup"><span data-stu-id="84e73-141">Control the pace of change for users</span></span></li></ul></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="84e73-142"><strong>考虑事项</strong></span><span class="sxs-lookup"><span data-stu-id="84e73-142"><strong>Considerations</strong></span></span></td>
<td align="left"><ul>
<li><span data-ttu-id="84e73-143">存在多个具有相似、重叠功能的应用</span><span class="sxs-lookup"><span data-stu-id="84e73-143">Multiple apps with similar, overlapping capabilities</span></span></li>
<li><span data-ttu-id="84e73-144">增加了用户混乱的可能性，这可能会导致支持电话增加、IT 工作量增加、工作效率受影响</span><span class="sxs-lookup"><span data-stu-id="84e73-144">Increased potential for user confusion which can lead to increased support calls, shadow IT, impacted productivity</span></span></li>
<li><span data-ttu-id="84e73-145">网络规划和监控必须考虑使用两种服务</span><span class="sxs-lookup"><span data-stu-id="84e73-145">Network planning and monitoring must take usage of two services into consideration</span></span></li>
<li><span data-ttu-id="84e73-146">所需的变更管理工作量增加且迫切：认知、培训和支持</span><span class="sxs-lookup"><span data-stu-id="84e73-146">Increased and immediate change management efforts required: awareness, training, and support</span></span></li>
<li><span data-ttu-id="84e73-147">用户可能会遇到应用之间存在的互操作性限制</span><span class="sxs-lookup"><span data-stu-id="84e73-147">Users may experience interoperability limitations between apps</span></span></li>
</ul></td>
<td align="left"><ul><li><span data-ttu-id="84e73-148">IT 进行从许可到用户体验的细化控制，从而需要额外的规划和实施周期</span><span class="sxs-lookup"><span data-stu-id="84e73-148">IT has granular control, from licensing to user experiences, requiring additional cycles of planning and implementation</span></span></li>
<li><span data-ttu-id="84e73-149">需要用户培训和操作以在 Teams 中禁用选择功能</span><span class="sxs-lookup"><span data-stu-id="84e73-149">User education and action required to disable select capabilities in Teams</span></span></li>
<li><span data-ttu-id="84e73-150">需要变更管理工作以在 Teams 中禁用选择功能</span><span class="sxs-lookup"><span data-stu-id="84e73-150">Change management efforts required to disable select capabilities in Teams</span></span></li>
<li><span data-ttu-id="84e73-151">网络规划和监控必须考虑使用两种服务</span><span class="sxs-lookup"><span data-stu-id="84e73-151">Network planning and monitoring must take usage of two services into consideration</span></span></li>
<li><span data-ttu-id="84e73-152">用户可能会遇到应用之间存在的互操作性限制</span><span class="sxs-lookup"><span data-stu-id="84e73-152">Users may experience interoperability limitations between apps</span></span></li></ul></td>
</tr>
</tbody>
</table>


<a name="unmanaged-side-by-side-customer-journey"></a><span data-ttu-id="84e73-153">不受管理的并行客户旅程</span><span class="sxs-lookup"><span data-stu-id="84e73-153">Unmanaged side-by-side customer journey</span></span>
---------------------------------------


![](media/guidance_SkypeforBusiness_image4.png)

<span data-ttu-id="84e73-154">在不受管理的并行客户旅程中，Teams 作为协作解决方案采用（基于聊天的工作区、频道、应用、与其他 Office 365 工作负荷集成等），涉及桌面计算机（PC 或 Mac）和移动设备上的客户端软件和 Web 客户端。</span><span class="sxs-lookup"><span data-stu-id="84e73-154">In an unmanaged side-by-side customer journey, Teams is introduced as a collaboration solution (chat-based workspace, channels, apps, integration with other Office 365 workloads, etc.) that involves client software and web client on desktop computers (PC or Mac) and mobile devices.</span></span>


<span data-ttu-id="84e73-155">默认情况下，Teams 还提供与 Skype for Business 重叠的功能，其中包括私人聊天和通话以及安排的会议。</span><span class="sxs-lookup"><span data-stu-id="84e73-155">By default, Teams also presents overlapping capabilities with Skype for Business, these include private chat and calling, and scheduled meetings.</span></span> <span data-ttu-id="84e73-156">这意味着 Teams 最终为组织提供完整的通信与协作，而同时 Skype for Business 提供类似的功能。</span><span class="sxs-lookup"><span data-stu-id="84e73-156">This means Teams ends up providing complete communications and collaboration for the organization, while at the same time Skype for Business provides similar capabilities.</span></span>

<span data-ttu-id="84e73-157">Teams 支持与 Skype for Business Online 用户的互操作性，用户将在启动 Teams 时可以选择其首选的聊天和通话应用。</span><span class="sxs-lookup"><span data-stu-id="84e73-157">Teams supports interoperability with Skype for Business Online users, and users will be given an opportunity to choose their preferred chat and calling app when they launch Teams.</span></span> <span data-ttu-id="84e73-158">如果一个用户选择 Teams 作为首选应用，而另一个用户未安装 Teams 或选择了 Skype for Business 作为首选的聊天和通话应用，他们可以通过属于 Teams 的互操作性功能继续相互聊天和通话。</span><span class="sxs-lookup"><span data-stu-id="84e73-158">If one user picks Teams as the preferred app, and another user hasn’t installed Teams or picked Skype for Business as the preferred chat and calling app, they can continue to chat and call each other through the interop capabilities that are part of Teams.</span></span>

<span data-ttu-id="84e73-159">Microsoft 一直在改进互操作性体验。</span><span class="sxs-lookup"><span data-stu-id="84e73-159">Microsoft is continuously improving the interop experiences.</span></span> <span data-ttu-id="84e73-160">在初期，可能会出现互操作性体验未达到用户期望的一些情况。</span><span class="sxs-lookup"><span data-stu-id="84e73-160">In the beginning, there may be some cases whereby the interop experiences are not meeting user expectations.</span></span> <span data-ttu-id="84e73-161">由于用户仍可使用 Skype for Business，他们可以切换到 Skype for Business 来使用 Teams 当前无法提供的功能。</span><span class="sxs-lookup"><span data-stu-id="84e73-161">Since Skype for Business is still available to users, they can switch to Skype for Business for the capabilities that currently cannot be served by Teams.</span></span>

<span data-ttu-id="84e73-162">Teams 中安排的会议是另一项重叠功能，即用户可以安排 Teams 会议，也可以安排 Skype for Business 会议。</span><span class="sxs-lookup"><span data-stu-id="84e73-162">Scheduled meetings in Teams is another overlapping capability that lets users schedule Teams meetings, or Skype for Business meetings.</span></span> <span data-ttu-id="84e73-163">两者均有自己的优势，以后，当 Teams 会议体验满足业务需求或优于 Skype for Business 会议的功能时，我们希望用户顺理成章地切换到 Teams 会议。</span><span class="sxs-lookup"><span data-stu-id="84e73-163">Each has its own advantages, and over time, when Teams meeting experience meets business requirements or surpasses the functionalities of Skype for Business meetings, we expect users to naturally switch to Teams meetings.</span></span>

<span data-ttu-id="84e73-164">在此不受管理的并行客户旅程中，应准备你的支持团队以处理用户遇到互操作性功能方面的问题时拨打的支持电话。</span><span class="sxs-lookup"><span data-stu-id="84e73-164">In this unmanaged side-by-side customer journey, prepare your helpdesk team to handle support calls from users when facing issues with interop capabilities.</span></span> <span data-ttu-id="84e73-165">或者建议用户何时选择 Teams 会议而非 Skype for Business 会议，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="84e73-165">Or advise users when to choose Teams meetings over Skype for Business meetings, and vice versa.</span></span>

<span data-ttu-id="84e73-166">如果用户更愿意接受不受管理的并行体验方式，并且组织公开允许用户选择适合其要求的最佳通信与协作工具，则此并行客户旅程可能适用于贵组织。</span><span class="sxs-lookup"><span data-stu-id="84e73-166">This side-by-side customer journey may be applicable to your organization, whereby the users are more receptive to the nature of the unmanaged side-by-side experience, and the organization openly allows the users to pick the best communications and collaboration tools that suit their requirements.</span></span>

<a name="managed-side-by-side-customer-journey"></a><span data-ttu-id="84e73-167">受管理的并行客户旅程</span><span class="sxs-lookup"><span data-stu-id="84e73-167">Managed side-by-side customer journey</span></span>
-------------------------------------

![](media/guidance_SkypeforBusiness_image2.png)

<span data-ttu-id="84e73-168">受管理的并行客户旅程适用于希望对 Teams 的采用方式进行更多控制的组织。</span><span class="sxs-lookup"><span data-stu-id="84e73-168">A managed side-by-side customer journey starts with organization wanting more control over how Teams is introduced.</span></span>

-   <span data-ttu-id="84e73-169">此旅程的**第一步**是进行有限的 Teams 试点，范围限于新式协作需求（基于聊天的工作区、频道、应用、与其他 Office 365 工作负荷的集成等）。</span><span class="sxs-lookup"><span data-stu-id="84e73-169">The **first step** of this journey is a limited pilot of Teams scoped to modern collaboration requirements (chat-based workspace, channels, apps, integration with other Office 365 workloads, etc.).</span></span> <span data-ttu-id="84e73-170">此外，还启用 Teams 中的临时频道会议和私人聊天，以便试点用户可以评估 Teams 会议体验和私人聊天体验。</span><span class="sxs-lookup"><span data-stu-id="84e73-170">Ad-hoc channel meetings and private chat in Teams is also enabled to provide a chance for pilot users to evaluate the Teams meetings experience and private chat experiences.</span></span> <span data-ttu-id="84e73-171">在此阶段禁用 Teams 中的安排的会议和专线通话功能。</span><span class="sxs-lookup"><span data-stu-id="84e73-171">Scheduled meetings and private calling capabilities in Teams are disabled at this stage.</span></span> <span data-ttu-id="84e73-172">要开始试点，请访问[在使用 Skype for Business 的同时试用 Teams](pilot-essentials.md)。</span><span class="sxs-lookup"><span data-stu-id="84e73-172">To get started with a pilot, go to [Pilot Teams with Skype for Business](pilot-essentials.md).</span></span>
    
-   <span data-ttu-id="84e73-173">此旅程的**第二步**是扩展 Teams 的部署以用于在整个组织中通过私人聊天进行新式协作。</span><span class="sxs-lookup"><span data-stu-id="84e73-173">The **second step** of this journey is extending the rollout of Teams for modern collaboration with private chat throughout the organization.</span></span> <span data-ttu-id="84e73-174">继续在 Teams 中禁用安排的会议和专线通话，以减少与 Skype for Business 功能的重叠。</span><span class="sxs-lookup"><span data-stu-id="84e73-174">Scheduled meetings, and private calling continue to be disabled in Teams to reduce the overlap  with with Skype for Business capabilities.</span></span>

    <span data-ttu-id="84e73-175">在此阶段，你可能需要考虑应将整个组织的首选聊天应用设置为 Teams 还是 Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="84e73-175">At this stage, you may need to consider whether preferred chat application should be set to Teams or Skype for Business for the entire organization.</span></span>

    - <span data-ttu-id="84e73-176">如果设置为 Teams，请让你的用户准备好处理在与组织内部和之间的其他用户通信时面临的初期互操作性挑战。</span><span class="sxs-lookup"><span data-stu-id="84e73-176">If set to Teams, prepare your users to handle early interoperability challenges when communicating with other parties within and across the organization.</span></span>
    
    - <span data-ttu-id="84e73-177">如果设置为 Skype for Business，Teams 中的私人聊天将仍在 Teams 中进行，最终用户可以立即利用 Teams 中聊天功能的跨平台持久特性，他们将继续使用 Skype for Business 在组织内部和之间进行 Skype for Business 用户之间的私人聊天。</span><span class="sxs-lookup"><span data-stu-id="84e73-177">If set to Skype for Business, private chats within Teams will remain in Teams, and end users can immediately take advantage of the cross-platform persistent nature of chat capabilities within Teams, and they will continue to use Skype for Business for private chats among Skype for Business users, within the organization and across the organization.</span></span>


<table>
<thead>
<tr class="header">
<td align="center"><p><img src="media/guidance_SkypeforBusiness_image3.png" /></p>
<p><span data-ttu-id="84e73-178">注意</span><span class="sxs-lookup"><span data-stu-id="84e73-178">Note:</span></span></p></td>
<td align="left"><br><br><span data-ttu-id="84e73-179">当前，仅在客户端级别提供首选聊天应用设置。</span><span class="sxs-lookup"><span data-stu-id="84e73-179">Currently the preferred chat application setting is available only at the client level.</span></span> <span data-ttu-id="84e73-180">要推动预期的组织范围的配置，需要用户培训和采用推行活动。</span><span class="sxs-lookup"><span data-stu-id="84e73-180">User training and adoption campaign will be required to drive the intended organization-wide configuration.</span></span></td>
</tr>
</thead>
<tbody>
</tbody>
</table>

<span data-ttu-id="84e73-181">当组织确定 Teams 会议体验和功能满足其业务需求时，开始受管理的并行客户旅程的**第三步**。</span><span class="sxs-lookup"><span data-stu-id="84e73-181">The **third step** of the managed side-by-side customer journey starts when the organization decides that Teams meeting experience and capabilities meet their business requirements.</span></span> <span data-ttu-id="84e73-182">在 Teams 中启用私人会议和频道会议后，将向用户显示用于安排 Teams 会议和 Skype for Business 会议的选项。</span><span class="sxs-lookup"><span data-stu-id="84e73-182">By enabling private and channel meetings in Teams, users are presented with options to schedule both Teams meetings and Skype for Business meetings.</span></span> <span data-ttu-id="84e73-183">因此，预计以后如果 Teams 中不断增加创新功能，用户将顺理成章地切换到 Teams 会议。</span><span class="sxs-lookup"><span data-stu-id="84e73-183">Therefore, it is expected that over time users will naturally switch to Teams meetings given the continued innovations in Teams.</span></span> <span data-ttu-id="84e73-184">为了成功引导从使用 Skype for Business 转向使用 Teams，应实施有力的变更管理计划，包括培训、支持和沟通（介绍 Teams 为用户提供的增值服务），以及有关如何开始使用 Teams 的清晰指导。</span><span class="sxs-lookup"><span data-stu-id="84e73-184">To be successful in steering usage from Skype for Business to Teams, implement a robust change management program inclusive of training, support and communications that explains the value-add that Teams offers to the user, with clear guidance on how to get started with Teams.</span></span> <span data-ttu-id="84e73-185">利用我们的[用户就绪](http://aka.ms/UserReadiness)资源来帮助设计你的认知推行活动。</span><span class="sxs-lookup"><span data-stu-id="84e73-185">Leverage our [User Readiness](http://aka.ms/UserReadiness) resources to help design your awareness campaign.</span></span>


<span data-ttu-id="84e73-186">受管理的并行客户旅程的**第四步**是先在 Teams 中启用通话。</span><span class="sxs-lookup"><span data-stu-id="84e73-186">The **fourth step** of the managed side-by-side customer journey begins with enabling calling in Teams.</span></span> <span data-ttu-id="84e73-187">为确保实现无缝的并行体验，Teams 互操作性功能将在此步骤中起重要作用。</span><span class="sxs-lookup"><span data-stu-id="84e73-187">Teams interoperability capabilities will feature heavily in this step to ensure a seamless side-by-side experience.</span></span> <span data-ttu-id="84e73-188">理想情况下，为了强制使用 Teams 进行专线通话，Teams 设置为默认通话应用。</span><span class="sxs-lookup"><span data-stu-id="84e73-188">Ideally, to enforce the use of Teams for private calling, Teams is set as the default calling app.</span></span> 

<span data-ttu-id="84e73-189">随着时间的推移，可能整个组织会仅依赖 Teams 满足通信与协作需求并采取**第五步**。</span><span class="sxs-lookup"><span data-stu-id="84e73-189">Over time, potentially the whole organization can rely solely on Teams to meet communications and collaboration requirements and take the **fifth step**.</span></span> <span data-ttu-id="84e73-190">要查看 Teams 中何时会添加新功能，请参阅 [Office 365 路线图](http://aka.ms/TeamsRoadmap)。</span><span class="sxs-lookup"><span data-stu-id="84e73-190">To see when new features are coming in Teams, see the [Office 365 Roadmap](http://aka.ms/TeamsRoadmap).</span></span> 

<a name="managing-side-by-side-experience"></a><span data-ttu-id="84e73-191">管理并行体验</span><span class="sxs-lookup"><span data-stu-id="84e73-191">Managing side-by-side experience</span></span>
--------------------------------

<span data-ttu-id="84e73-192">默认情况下，对于具有符合条件的 Office 365 订阅的组织，会启用 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="84e73-192">By default, for organizations with eligible Office 365 subscriptions, Microsoft Teams is enabled.</span></span> <span data-ttu-id="84e73-193">如果贵组织的情况适合不受管理的并行客户旅程，我们强烈建议你保持原样以便自然地采用 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="84e73-193">If your organization fits the profile for unmanaged side-by-side customer journey, we highly recommend you keep it as-is to foster organic adoption of Microsoft Teams.</span></span>

<span data-ttu-id="84e73-194">可以通过新式 Web 浏览器桌面客户端（不需要 IT 管理权限 - 对于安装，当前仅适用于 PC）和移动客户端访问 Teams。</span><span class="sxs-lookup"><span data-stu-id="84e73-194">Teams is accessible via modern Web browser desktop clients which require no IT administrative privilege (for installation, currently applicable to PC only) and mobile clients.</span></span>

<span data-ttu-id="84e73-195">默认情况下，启用 Teams 中的所有功能（私人聊天和通话、临时和安排的会议以及应用），从而允许用户尝试和使用适合其需求的功能。</span><span class="sxs-lookup"><span data-stu-id="84e73-195">All capabilities in Teams, from private chat and calling, ad-hoc and scheduled meetings, and apps are enabled by default, allowing users to experiment and use the capabilities that suit their needs.</span></span> <span data-ttu-id="84e73-196">Teams 中的首次运行体验会指引用户选择其首选聊天和通话应用（Microsoft Teams 或 Skype for Business）。</span><span class="sxs-lookup"><span data-stu-id="84e73-196">A first-run experience in Teams guides users to pick their preferred chat and calling application (Microsoft Teams or Skype for Business).</span></span>

<span data-ttu-id="84e73-197">如果贵组织需要对新工具（例如 Teams）的发放进行更多的控制，可以在你的受管理的并行客户旅程中考虑以下选项：</span><span class="sxs-lookup"><span data-stu-id="84e73-197">Should your organization require a more controlled release of new tools such as Teams, the following options can be considered for your managed side-by-side customer journey, they are:</span></span>

-   <span data-ttu-id="84e73-198">试用和部署 Teams 用于协作。</span><span class="sxs-lookup"><span data-stu-id="84e73-198">Pilot and rollout of Teams for collaboration.</span></span> <span data-ttu-id="84e73-199">请参阅[在使用 Skype for Business 的同时试用 Teams](pilot-essentials.md)</span><span class="sxs-lookup"><span data-stu-id="84e73-199">See [Pilot Teams with Skype for Business](pilot-essentials.md).</span></span>

-   <span data-ttu-id="84e73-200">部署 Teams 用于会议</span><span class="sxs-lookup"><span data-stu-id="84e73-200">Rollout of Teams for meetings</span></span>

-   <span data-ttu-id="84e73-201">部署 Teams 用于通话</span><span class="sxs-lookup"><span data-stu-id="84e73-201">Rollout of Teams for calling</span></span>

### <a name="teams-pilot-and-rollout-for-collaboration"></a><span data-ttu-id="84e73-202">用于协作的 Teams 试点和部署</span><span class="sxs-lookup"><span data-stu-id="84e73-202">Teams pilot and rollout for collaboration</span></span>

<span data-ttu-id="84e73-203">从其核心来看，Microsoft Teams 是通过增强 Office 365 组围绕持久聊天以及与 Office 365 集成构建而成的。</span><span class="sxs-lookup"><span data-stu-id="84e73-203">At its core, Microsoft Teams was built around persistent chat and integration with Office 365 by enhancing Office 365 Groups.</span></span>

<span data-ttu-id="84e73-204">由于默认情况下对于具有符合条件的 Office 365 订阅的贵组织中的用户会启用 Teams，因此，如果要进行有限的 Teams 试点，就要对试点组外的所有用户禁用 Teams 许可证。</span><span class="sxs-lookup"><span data-stu-id="84e73-204">Since by default users in your organization with an eligible Office 365 subscription license are enabled for Teams, a limited Teams pilot will involve disabling the Teams license for all users who are outside of the pilot group.</span></span>

<span data-ttu-id="84e73-205">为了重点体现 Teams 版本作为协作与私人聊天解决方案，以及减少由于与 Skype for Business 的重叠功能导致的用户混乱，你可以在 Office 365 租户级别更改以下设置。</span><span class="sxs-lookup"><span data-stu-id="84e73-205">To focus the Teams release as a collaboration and private chat solution, and to reduce user confusion due to overlapping capabilities with Skype for Business, you can change the following settings at the Office 365 tenant level.</span></span> <span data-ttu-id="84e73-206">要更改这些 Office 365 设置，请参阅[在你的 Office 365 组织中设置 Microsoft Teams](Office-365-set-up.md)。</span><span class="sxs-lookup"><span data-stu-id="84e73-206">To change these Office 365 settings, see [Set up Microsoft Teams in your Office 365 organization](Office-365-set-up.md).</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="84e73-207">部分</span><span class="sxs-lookup"><span data-stu-id="84e73-207">Section Heading</span></span></th>
<th align="left"><span data-ttu-id="84e73-208">设置</span><span class="sxs-lookup"><span data-stu-id="84e73-208">Setting</span></span></th>
<th align="left"><span data-ttu-id="84e73-209">说明</span><span class="sxs-lookup"><span data-stu-id="84e73-209">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><strong><br><span data-ttu-id="84e73-210">通话和会议</strong></span><span class="sxs-lookup"><span data-stu-id="84e73-210">Calls and meetings</strong></span></span></td>
<td align="left"><p><span data-ttu-id="84e73-211">允许安排私人会议：<strong>关闭</strong></span><span class="sxs-lookup"><span data-stu-id="84e73-211">Allow scheduling for private meetings: <strong>Off</strong></span></span></p><p><span data-ttu-id="84e73-212">允许安排频道会议：<strong>关闭</strong></span><span class="sxs-lookup"><span data-stu-id="84e73-212">Allow scheduling for channel meetings: <strong>Off</strong></span></span></p><p><span data-ttu-id="84e73-213">允许专线通话：<strong>关闭</strong></span><span class="sxs-lookup"><span data-stu-id="84e73-213">Allow private calling: <strong>Off</strong></span></span></p></td>
<td align="left"><p><span data-ttu-id="84e73-214">禁用此设置将防止用户安排私人会议</span><span class="sxs-lookup"><span data-stu-id="84e73-214">Disabling this setting prevents users from scheduling private meetings</span></span></p><p><span data-ttu-id="84e73-215">禁用此设置将防止用户安排频道会议</span><span class="sxs-lookup"><span data-stu-id="84e73-215">Disabling this setting prevents users from scheduling channel meetings</span></span></p><p><span data-ttu-id="84e73-216">禁用此设置将防止用户进行私人通话（音频和视频）</span><span class="sxs-lookup"><span data-stu-id="84e73-216">Disabling this setting prevents users from making private calls (audio and video)</span></span></p></td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr class="header">
<td align="center"><p><img src="media/guidance_SkypeforBusiness_image3.png" /></p>
<p><span data-ttu-id="84e73-217">注意</span><span class="sxs-lookup"><span data-stu-id="84e73-217">Note:</span></span></p></td>
<td align="left"><br><br><span data-ttu-id="84e73-218">你必须对企业用户和来宾用户（如果来宾访问适用于贵组织）都禁用专线通话。</span><span class="sxs-lookup"><span data-stu-id="84e73-218">You must disable Private Calling to both Business and Enterprise users, and Guest users (if Guest Access is applicable to your organization).</span></span></td>
</tr>
</thead>
<tbody>
</tbody>
</table>



<span data-ttu-id="84e73-219">借助此配置，可以通过提倡使用临时频道聚会、在新式协作体验中支持使用语音、视频和屏幕共享，向用户展现 Teams 中的会议工作方式。</span><span class="sxs-lookup"><span data-stu-id="84e73-219">With this configuration, users can be introduced to how meetings work in Teams by advocating the use of ad-hoc channel meetup, enabling the use of voice, video, and screen sharing as part of the modern collaboration experience.</span></span> <span data-ttu-id="84e73-220">最终用户还可以从 Teams 持久、跨平台、私人聊天功能受益。</span><span class="sxs-lookup"><span data-stu-id="84e73-220">End users can also benefit from Teams persistent, cross-platform, private chat capabilities.</span></span>

<span data-ttu-id="84e73-221">针对协作与私人聊天的 Teams 试点成功后，可以向所有用户启用 Teams 许可证以在整个组织中全面部署。</span><span class="sxs-lookup"><span data-stu-id="84e73-221">A successful Teams pilot for collaboration and private chat can be followed up with broad rollout throughout the organization by enabling Teams license for all users.</span></span>

<table>
<thead>
<tr class="header">
<td align="center"><p><img src="media/guidance_SkypeforBusiness_image3.png" /></p>
<p><span data-ttu-id="84e73-222">注意</span><span class="sxs-lookup"><span data-stu-id="84e73-222">Note:</span></span></p></td>
<td align="left"><span data-ttu-id="84e73-223">在试点期间启用了私人聊天的第二阶段，与 Skype for Business 用户聊天的 Teams 用户将无法执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="84e73-223">During the pilot, and in phase two when private chat is enabled, a Teams user chatting with a Skype for Business user will not be able to do the following:</span></span><br><span data-ttu-id="84e73-224">
- 从聊天会话启动视频通话</span><span class="sxs-lookup"><span data-stu-id="84e73-224">
- Start video call from a chat session</span></span><br><span data-ttu-id="84e73-225">
- 传输文件</span><span class="sxs-lookup"><span data-stu-id="84e73-225">
- Transfers files</span></span> <br><span data-ttu-id="84e73-226">
- 从聊天会话启动多方通话</span><span class="sxs-lookup"><span data-stu-id="84e73-226">
- Initiate a multiparty call from the chat session</span></span><br><span data-ttu-id="84e73-227">
- 用户将无法启动桌面共享会话</span><span class="sxs-lookup"><span data-stu-id="84e73-227">
- Users will not be able to start a desktop sharing session</span></span><br>

</td>
</tr>
</thead>
<tbody>
</tbody>
</table>


### <a name="rollout-of-teams-for-meetings"></a><span data-ttu-id="84e73-228">部署 Teams 用于会议</span><span class="sxs-lookup"><span data-stu-id="84e73-228">Rollout of Teams for meetings</span></span>

<span data-ttu-id="84e73-229">随着用户逐渐习惯使用 Microsoft Teams 进行协作，可以考虑将安排的会议作为组织中下一个启用的功能。</span><span class="sxs-lookup"><span data-stu-id="84e73-229">As users are getting accustomed to collaborating using Microsoft Teams, scheduled meetings can be considered as the next capability to enable in the organization.</span></span>

<table>
<thead>
<tr class="header">
<td align="center"><p><img src="media/guidance_SkypeforBusiness_image3.png" /></p>
<p><span data-ttu-id="84e73-230">注意</span><span class="sxs-lookup"><span data-stu-id="84e73-230">Note:</span></span></p></td>
<td align="left"><br><br><span data-ttu-id="84e73-231">安排的会议的组织者必须在 Exchange Online 多租户（或 Exchange Online Dedicated vNext）中有自己的邮箱。</span><span class="sxs-lookup"><span data-stu-id="84e73-231">The organizers of scheduled meetings must have their mailboxes in Exchange Online multi-tenant (or Exchange Online Dedicated vNext).</span></span></td>
</tr>
</thead>
<tbody>
</tbody>
</table>

<span data-ttu-id="84e73-232">可以在租户级别配置以下设置以在 Teams 中启用安排的会议，这些设置仅适用于企业用户。</span><span class="sxs-lookup"><span data-stu-id="84e73-232">The following settings can be configured at the tenant level to enable scheduled meetings in Teams, and the settings are applicable to Business and Enterprise users only.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="84e73-233">部分</span><span class="sxs-lookup"><span data-stu-id="84e73-233">Section Heading</span></span></th>
<th align="left"><span data-ttu-id="84e73-234">设置</span><span class="sxs-lookup"><span data-stu-id="84e73-234">Setting</span></span></th>
<th align="left"><span data-ttu-id="84e73-235">说明</span><span class="sxs-lookup"><span data-stu-id="84e73-235">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><strong><br><span data-ttu-id="84e73-236">通话和会议</strong></span><span class="sxs-lookup"><span data-stu-id="84e73-236">Calls and meetings</strong></span></span></td>
<td align="left"><p><span data-ttu-id="84e73-237">允许安排私人会议：<strong>开启</strong></span><span class="sxs-lookup"><span data-stu-id="84e73-237">Allow scheduling for private meetings: <strong>On</strong></span></span></p><p><span data-ttu-id="84e73-238">允许安排频道会议：<strong>开启</strong></span><span class="sxs-lookup"><span data-stu-id="84e73-238">Allow scheduling for channel meetings: <strong>On</strong></span></span></p></td>
<td align="left"><p><span data-ttu-id="84e73-239">启用此设置将允许用户安排私人会议</span><span class="sxs-lookup"><span data-stu-id="84e73-239">Enabling this setting allows users to schedule private meetings</span></span></p><p><span data-ttu-id="84e73-240">启用此设置将允许用户安排频道会议</span><span class="sxs-lookup"><span data-stu-id="84e73-240">Enabling this setting allows users to schedule channel meetings</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="84e73-241">可以通过 Teams 桌面客户端或浏览器，或者使用适用于 Microsoft Teams 的会议外接程序通过 Microsoft Outlook，来组织安排的会议。</span><span class="sxs-lookup"><span data-stu-id="84e73-241">Scheduled meetings can be organized via the Teams desktop client, a browser, or via Microsoft Outlook using the meeting add-in for Microsoft Teams.</span></span> <span data-ttu-id="84e73-242">一旦在 Teams 中启用了安排的会议，我们建议你开始培训用户创建新的 Teams 会议或将现有 Skype for Business 会议更新为 Teams 会议。</span><span class="sxs-lookup"><span data-stu-id="84e73-242">Once scheduled meetings in Teams is enabled, we recommend you start educating users to create new Teams meetings or update existing Skype for Business meetings to Teams meetings.</span></span>

### <a name="rollout-of-teams-for-calling"></a><span data-ttu-id="84e73-243">部署 Teams 用于通话</span><span class="sxs-lookup"><span data-stu-id="84e73-243">Rollout of Teams for calling</span></span>

<span data-ttu-id="84e73-244">专线通话是将持续开发的 Teams 功能，并将逐步提供取代 Skype for Business 的优势功能。</span><span class="sxs-lookup"><span data-stu-id="84e73-244">Private calling is the Teams capability that will be continuously developed, and over time provide a compelling replacement to Skype for Business.</span></span> <span data-ttu-id="84e73-245">贵组织考虑 Teams 专线通话功能满足关键业务需求时，可以在租户级别配置以下设置以在 Teams 中启用专线通话。</span><span class="sxs-lookup"><span data-stu-id="84e73-245">When your organization considers that Teams private calling capabilities meet key business requirements, the following settings can be configured at the tenant level to enable private calling in Teams.</span></span> 

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="84e73-246">部分</span><span class="sxs-lookup"><span data-stu-id="84e73-246">Section Heading</span></span></th>
<th align="left"><span data-ttu-id="84e73-247">设置</span><span class="sxs-lookup"><span data-stu-id="84e73-247">Setting</span></span></th>
<th align="left"><span data-ttu-id="84e73-248">说明</span><span class="sxs-lookup"><span data-stu-id="84e73-248">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><strong><br><span data-ttu-id="84e73-249">通话和会议</strong></span><span class="sxs-lookup"><span data-stu-id="84e73-249">Calls and meetings</strong></span></span></td>
<td align="left"><p><span data-ttu-id="84e73-250">允许专线通话：<strong>开启</strong></span><span class="sxs-lookup"><span data-stu-id="84e73-250">Allow private calling: <strong>On</strong></span></span></p></td>
<td align="left"><p><span data-ttu-id="84e73-251">启用此设置将允许用户进行私人通话（音频和视频）</span><span class="sxs-lookup"><span data-stu-id="84e73-251">Enabling this setting allows users to place private calls (audio and video)</span></span></p></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<td align="center"><p><img src="media/guidance_SkypeforBusiness_image3.png" /></p>
<p><span data-ttu-id="84e73-252">注意</span><span class="sxs-lookup"><span data-stu-id="84e73-252">Note:</span></span></p></td>
<td align="left"><br><br><span data-ttu-id="84e73-253">允许用户私人聊天：启用此设置将允许用户与其他用户进行私人聊天。</span><span class="sxs-lookup"><span data-stu-id="84e73-253">Allow users to chat privately: Enabling this setting allows users to chat with other users privately.</span></span></td>
</tr>
</thead>
<tbody>
</tbody>
</table>


<span data-ttu-id="84e73-254">在此阶段，必须指示所有用户选择 Teams 作为首选通话应用。</span><span class="sxs-lookup"><span data-stu-id="84e73-254">At this stage, all users must be instructed to choose Teams as the preferred calling app.</span></span>

<span data-ttu-id="84e73-255">通过启用专线通话，Teams 将提供 Skype for Business 当前提供的所有功能，用户可以开始使用 Teams 满足其通信与协作需求。</span><span class="sxs-lookup"><span data-stu-id="84e73-255">With the enablement of private calling, Teams will deliver all capabilities currently provided by Skype for Business, and users can start using Teams to fulfill their communications and collaboration requirements.</span></span>


<table>
<thead>
<tr class="header">
<td align="left"><p><img src="media/pilot_essentials_image2.png" /></p></td>
<td align="left">
<p><span data-ttu-id="84e73-256"><strong>下一步操作：</strong> 一旦 Teams 启动并与 Skype for Business 并行运行，即可[通过用户采用推动价值](continue-journey.md)，同时继续从 Skype for Business 到 Teams 的旅程。</span><span class="sxs-lookup"><span data-stu-id="84e73-256"><strong>Next Action:</strong> Once Teams is up and running side-by-side with Skype for Business, [Drive Value through user adoption of Teams](continue-journey.md), while continuing your journey from Skype for Business to Teams.</span></span></td>
</tr>
</thead>
<tbody>
</tbody>
</table>