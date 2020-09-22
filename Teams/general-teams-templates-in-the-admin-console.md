---
title: 在管理控制台中使用常规团队模板
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
ms.collection:
- M365-collaboration
localization_priority: Normal
search.appverid: MET150
description: 了解如何使用常规团队模板，通过使用管理控制台提供预定义的设置、信道和预安装应用来创建团队结构。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 44be05a7ae1b449e0b267bb0e4ed107c40877f27
ms.sourcegitcommit: af9f96010460f9323db84912fe143aa0750ac798
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/21/2020
ms.locfileid: "48171116"
---
# <a name="use-general-teams-templates-in-the-admin-console"></a><span data-ttu-id="3546e-103">在管理控制台中使用常规团队模板</span><span class="sxs-lookup"><span data-stu-id="3546e-103">Use general Teams templates in the admin console</span></span>

[!INCLUDE [template](includes/preview-feature.md)]

<span data-ttu-id="3546e-104">团队模板使你可以通过提供设置、频道和预安装应用的预定义模板来快速轻松地创建团队。</span><span class="sxs-lookup"><span data-stu-id="3546e-104">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="3546e-105">团队模板具有围绕财务需求设计的团队结构的预建定义。</span><span class="sxs-lookup"><span data-stu-id="3546e-105">Teams templates have pre-built definitions of team structures designed around financial needs.</span></span> <span data-ttu-id="3546e-106">您还可以扩展团队模板以创建根据您的特定组织需求量身定制的团队。</span><span class="sxs-lookup"><span data-stu-id="3546e-106">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="3546e-107">在本文中，我们将介绍每个团队模板以及我们建议如何使用它们。</span><span class="sxs-lookup"><span data-stu-id="3546e-107">In this article, we will introduce each of the Teams templates and how we recommend using them.</span></span>

<span data-ttu-id="3546e-108">本文适用于你负责在整个财务组织中规划、部署和管理多个团队的情况。</span><span class="sxs-lookup"><span data-stu-id="3546e-108">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your financial organization.</span></span> <span data-ttu-id="3546e-109">我们假定你的组织中已部署团队服务。</span><span class="sxs-lookup"><span data-stu-id="3546e-109">We assume that you already have deployed Teams service in your organization.</span></span> <span data-ttu-id="3546e-110">如果尚未推出团队，请先阅读 [如何展示 Microsoft 团队](How-to-roll-out-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="3546e-110">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="3546e-111">若要深入了解有关团队模板的详细信息，请参阅 [团队模板入门](get-started-with-teams-templates-in-the-admin-console.md)。</span><span class="sxs-lookup"><span data-stu-id="3546e-111">To learn more about team templates in general, please refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="global-crisis-or-event"></a><span data-ttu-id="3546e-112">全球危机或活动</span><span class="sxs-lookup"><span data-stu-id="3546e-112">Global crisis or event</span></span>

<span data-ttu-id="3546e-113">跨业务单元对危机团队协作，并帮助创建业务连续性计划、共享远程工作提示、跟踪客户通信，以及使用公告和新闻让每个人都保持联系。</span><span class="sxs-lookup"><span data-stu-id="3546e-113">Centralize collaboration for your crisis team across business units and help create business continuity plans, share remote working tips, track customer communications, and keep everyone in the loop with announcements and news.</span></span>

| <span data-ttu-id="3546e-114">基本模板类型</span><span class="sxs-lookup"><span data-stu-id="3546e-114">Base template type</span></span> |<span data-ttu-id="3546e-115">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="3546e-115">baseTemplateId</span></span> | <span data-ttu-id="3546e-116">此基本模板附带的属性</span><span class="sxs-lookup"><span data-stu-id="3546e-116">Properties that come with this base template</span></span> |
| ------------------ |--|----------------------------------------------------- |
| <span data-ttu-id="3546e-117">协作处理全球危机或活动</span><span class="sxs-lookup"><span data-stu-id="3546e-117">Collaborate on global crisis or event</span></span> |`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent` |<span data-ttu-id="3546e-118">信道</span><span class="sxs-lookup"><span data-stu-id="3546e-118">Channels:</span></span> <ul><li><span data-ttu-id="3546e-119">常规</span><span class="sxs-lookup"><span data-stu-id="3546e-119">General</span></span><li><span data-ttu-id="3546e-120">宣告</span><span class="sxs-lookup"><span data-stu-id="3546e-120">Announcements</span></span></li><li><span data-ttu-id="3546e-121">世界新闻</span><span class="sxs-lookup"><span data-stu-id="3546e-121">World news</span></span></li><li><span data-ttu-id="3546e-122">业务连续性</span><span class="sxs-lookup"><span data-stu-id="3546e-122">Business continuity</span></span></li><li><span data-ttu-id="3546e-123">远程工作</span><span class="sxs-lookup"><span data-stu-id="3546e-123">Remote working</span></span></li><li><span data-ttu-id="3546e-124">内部 comms</span><span class="sxs-lookup"><span data-stu-id="3546e-124">Internal comms</span></span></li><li><span data-ttu-id="3546e-125">外部 comms</span><span class="sxs-lookup"><span data-stu-id="3546e-125">External comms</span></span></li><li><span data-ttu-id="3546e-126">客户投诉</span><span class="sxs-lookup"><span data-stu-id="3546e-126">Customer complaints</span></span></li><li><span data-ttu-id="3546e-127">Kudos</span><span class="sxs-lookup"><span data-stu-id="3546e-127">Kudos</span></span></li><li><span data-ttu-id="3546e-128">执行更新</span><span class="sxs-lookup"><span data-stu-id="3546e-128">Executive update</span></span></li></ul><span data-ttu-id="3546e-129">识别</span><span class="sxs-lookup"><span data-stu-id="3546e-129">Apps:</span></span> <ul><li><span data-ttu-id="3546e-130">表扬</span><span class="sxs-lookup"><span data-stu-id="3546e-130">Praise</span></span></li><li><span data-ttu-id="3546e-131">源自</span><span class="sxs-lookup"><span data-stu-id="3546e-131">Wiki</span></span></li><li><span data-ttu-id="3546e-132">网站</span><span class="sxs-lookup"><span data-stu-id="3546e-132">Website</span></span></li></ul>|
||||

## <a name="adopt-office-365"></a><span data-ttu-id="3546e-133">采纳 Office 365</span><span class="sxs-lookup"><span data-stu-id="3546e-133">Adopt Office 365</span></span>

<span data-ttu-id="3546e-134">通过宣传和帮助你的同行使用新技术，帮助构建、扩大和维持你的拥护者社区推出。</span><span class="sxs-lookup"><span data-stu-id="3546e-134">Help build, grow, and sustain your Champions community rollout by evangelizing and helping your peers with the new technology.</span></span>

| <span data-ttu-id="3546e-135">基本模板类型</span><span class="sxs-lookup"><span data-stu-id="3546e-135">Base template type</span></span> |<span data-ttu-id="3546e-136">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="3546e-136">baseTemplateId</span></span> | <span data-ttu-id="3546e-137">此基本模板附带的属性</span><span class="sxs-lookup"><span data-stu-id="3546e-137">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
| <span data-ttu-id="3546e-138">采纳 Office 365</span><span class="sxs-lookup"><span data-stu-id="3546e-138">Adopt Office 365</span></span> | `com.microsoft.teams.template.AdoptOffice365` |  <span data-ttu-id="3546e-139">信道</span><span class="sxs-lookup"><span data-stu-id="3546e-139">Channels:</span></span> <ul><li><span data-ttu-id="3546e-140">常规</span><span class="sxs-lookup"><span data-stu-id="3546e-140">General</span></span></li> <li><span data-ttu-id="3546e-141">宣告</span><span class="sxs-lookup"><span data-stu-id="3546e-141">Announcements</span></span></li> <li><span data-ttu-id="3546e-142">拥护方角落</span><span class="sxs-lookup"><span data-stu-id="3546e-142">Champions corner</span></span></li> <li><span data-ttu-id="3546e-143">工作组表单</span><span class="sxs-lookup"><span data-stu-id="3546e-143">Team forms</span></span></li></ul> <span data-ttu-id="3546e-144">识别</span><span class="sxs-lookup"><span data-stu-id="3546e-144">Apps:</span></span> <ul><li><span data-ttu-id="3546e-145">源自</span><span class="sxs-lookup"><span data-stu-id="3546e-145">Wiki</span></span></li>  <li><span data-ttu-id="3546e-146">日历</span><span class="sxs-lookup"><span data-stu-id="3546e-146">Calendar</span></span></li> |<span data-ttu-id="3546e-147">li></span><span class="sxs-lookup"><span data-stu-id="3546e-147">li></span></span><li><span data-ttu-id="3546e-148">技能发展</span><span class="sxs-lookup"><span data-stu-id="3546e-148">Skills development</span></span></li><li><span data-ttu-id="3546e-149">借贷处理</span><span class="sxs-lookup"><span data-stu-id="3546e-149">Loan processing</span></span></li><li><span data-ttu-id="3546e-150">客户投诉</span><span class="sxs-lookup"><span data-stu-id="3546e-150">Customer complaints</span></span></li><li><span data-ttu-id="3546e-151">Kudos</span><span class="sxs-lookup"><span data-stu-id="3546e-151">Kudos</span></span></li><li><span data-ttu-id="3546e-152">有趣的资料</span><span class="sxs-lookup"><span data-stu-id="3546e-152">Fun stuff</span></span></li><li><span data-ttu-id="3546e-153">合规性</span><span class="sxs-lookup"><span data-stu-id="3546e-153">Compliance</span></span></li></ul>|
||||

## <a name="manage-a-project"></a><span data-ttu-id="3546e-154">管理项目</span><span class="sxs-lookup"><span data-stu-id="3546e-154">Manage a project</span></span>

<span data-ttu-id="3546e-155">通过此模板管理任务、共享文档、开展项目会议和记录风险和决策，以实现常规项目管理。</span><span class="sxs-lookup"><span data-stu-id="3546e-155">Manage tasks, share documents, conduct project meetings and document risks and decisions with this template for general project management.</span></span>

| <span data-ttu-id="3546e-156">基本模板类型</span><span class="sxs-lookup"><span data-stu-id="3546e-156">Base template type</span></span>| <span data-ttu-id="3546e-157">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="3546e-157">baseTemplateId</span></span> | <span data-ttu-id="3546e-158">此基本模板附带的属性</span><span class="sxs-lookup"><span data-stu-id="3546e-158">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
| <span data-ttu-id="3546e-159">管理项目</span><span class="sxs-lookup"><span data-stu-id="3546e-159">Manage a project</span></span>| <span data-ttu-id="3546e-160">ManageAProject 中的 .com</span><span class="sxs-lookup"><span data-stu-id="3546e-160">com.microsoft.teams.template.ManageAProject</span></span>  | <span data-ttu-id="3546e-161">信道</span><span class="sxs-lookup"><span data-stu-id="3546e-161">Channels:</span></span> <ul><li><span data-ttu-id="3546e-162">常规</span><span class="sxs-lookup"><span data-stu-id="3546e-162">General</span></span></li> <li><span data-ttu-id="3546e-163">宣告</span><span class="sxs-lookup"><span data-stu-id="3546e-163">Announcements</span></span></li> <li><span data-ttu-id="3546e-164">.Resources</span><span class="sxs-lookup"><span data-stu-id="3546e-164">Resources</span></span></li> <li><span data-ttu-id="3546e-165">规划</span><span class="sxs-lookup"><span data-stu-id="3546e-165">Planning</span></span></li></ul> <span data-ttu-id="3546e-166">识别</span><span class="sxs-lookup"><span data-stu-id="3546e-166">Apps:</span></span><ul><li><span data-ttu-id="3546e-167">源自</span><span class="sxs-lookup"><span data-stu-id="3546e-167">Wiki</span></span></li><li><span data-ttu-id="3546e-168">OneNote</span><span class="sxs-lookup"><span data-stu-id="3546e-168">OneNote</span></span></li></ul> |
||||

## <a name="manage-an-event"></a><span data-ttu-id="3546e-169">管理事件</span><span class="sxs-lookup"><span data-stu-id="3546e-169">Manage an event</span></span>

<span data-ttu-id="3546e-170">管理任务、文档和协作处理提供引人注目事件所需的所有内容。</span><span class="sxs-lookup"><span data-stu-id="3546e-170">Manage tasks, documents and collaborate on everything you need to deliver a compelling event.</span></span> <span data-ttu-id="3546e-171">邀请来宾用户在您的公司内部和外部进行安全协作。</span><span class="sxs-lookup"><span data-stu-id="3546e-171">Invite guests users to have secure collaboration inside and outside of your company.</span></span>

<span data-ttu-id="3546e-172">你可能无法访问基于你的应用权限策略的某些应用。</span><span class="sxs-lookup"><span data-stu-id="3546e-172">You may not have access to certain apps based on your app permission policy.</span></span>

| <span data-ttu-id="3546e-173">基本模板类型</span><span class="sxs-lookup"><span data-stu-id="3546e-173">Base template type</span></span> | <span data-ttu-id="3546e-174">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="3546e-174">baseTemplateId</span></span>| <span data-ttu-id="3546e-175">此基本模板附带的属性</span><span class="sxs-lookup"><span data-stu-id="3546e-175">Properties that come with this base template</span></span> |
| ------------------ |--|----------------------------------------------------- |
| <span data-ttu-id="3546e-176">管理事件</span><span class="sxs-lookup"><span data-stu-id="3546e-176">Manage an event</span></span>| `com.microsoft.teams.template.ManageAnEvent` | <span data-ttu-id="3546e-177">信道</span><span class="sxs-lookup"><span data-stu-id="3546e-177">Channels:</span></span> <ul><li><span data-ttu-id="3546e-178">常规</span><span class="sxs-lookup"><span data-stu-id="3546e-178">General</span></span></li> <li><span data-ttu-id="3546e-179">宣告</span><span class="sxs-lookup"><span data-stu-id="3546e-179">Announcements</span></span></li> <li><span data-ttu-id="3546e-180">预算</span><span class="sxs-lookup"><span data-stu-id="3546e-180">Budget</span></span></li> <li><span data-ttu-id="3546e-181">内容</span><span class="sxs-lookup"><span data-stu-id="3546e-181">Content</span></span></li><li><span data-ttu-id="3546e-182">后勤工作</span><span class="sxs-lookup"><span data-stu-id="3546e-182">Logistics</span></span></li> <li><span data-ttu-id="3546e-183">规划</span><span class="sxs-lookup"><span data-stu-id="3546e-183">Planning</span></span></li> <li> <span data-ttu-id="3546e-184">市场营销和 PR</span><span class="sxs-lookup"><span data-stu-id="3546e-184">Marketing and PR</span></span></li></ul> <span data-ttu-id="3546e-185">识别</span><span class="sxs-lookup"><span data-stu-id="3546e-185">Apps:</span></span><ul><li><span data-ttu-id="3546e-186">源自</span><span class="sxs-lookup"><span data-stu-id="3546e-186">Wiki</span></span></li><li><span data-ttu-id="3546e-187">网站</span><span class="sxs-lookup"><span data-stu-id="3546e-187">Website</span></span></li> <li><span data-ttu-id="3546e-188">YouTube</span><span class="sxs-lookup"><span data-stu-id="3546e-188">YouTube</span></span></li> <li><span data-ttu-id="3546e-189">Planner</span><span class="sxs-lookup"><span data-stu-id="3546e-189">Planner</span></span></li> <li><span data-ttu-id="3546e-190">OneNote</span><span class="sxs-lookup"><span data-stu-id="3546e-190">OneNote</span></span></li></ul> |
||||

## <a name="onboard-employees"></a><span data-ttu-id="3546e-191">板载员工</span><span class="sxs-lookup"><span data-stu-id="3546e-191">Onboard employees</span></span>

<span data-ttu-id="3546e-192">通过此中心团队改进您的文化，为您的资源、问题和乐趣，简化您的员工加入。</span><span class="sxs-lookup"><span data-stu-id="3546e-192">Improve your culture and streamline your employee onboarding with this central team for resources, questions and a bit of fun.</span></span>

| <span data-ttu-id="3546e-193">基本模板类型</span><span class="sxs-lookup"><span data-stu-id="3546e-193">Base template type</span></span> |<span data-ttu-id="3546e-194">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="3546e-194">baseTemplateId</span></span> | <span data-ttu-id="3546e-195">此基本模板附带的属性</span><span class="sxs-lookup"><span data-stu-id="3546e-195">Properties that come with this base template</span></span> |
| ------------------|- |----------------------------------------------------- |
|<span data-ttu-id="3546e-196">板载员工</span><span class="sxs-lookup"><span data-stu-id="3546e-196">Onboard employees</span></span>|`com.microsoft.teams.template.OnboardEmployees`  | <span data-ttu-id="3546e-197">信道</span><span class="sxs-lookup"><span data-stu-id="3546e-197">Channels:</span></span> <ul><li><span data-ttu-id="3546e-198">常规</span><span class="sxs-lookup"><span data-stu-id="3546e-198">General</span></span></li> <li><span data-ttu-id="3546e-199">宣告</span><span class="sxs-lookup"><span data-stu-id="3546e-199">Announcements</span></span></li> <li><span data-ttu-id="3546e-200">员工聊天</span><span class="sxs-lookup"><span data-stu-id="3546e-200">Employee chat</span></span></li> <li><span data-ttu-id="3546e-201">培训</span><span class="sxs-lookup"><span data-stu-id="3546e-201">Training</span></span></li></ul><span data-ttu-id="3546e-202">识别</span><span class="sxs-lookup"><span data-stu-id="3546e-202">Apps:</span></span><ul><li><span data-ttu-id="3546e-203">源自</span><span class="sxs-lookup"><span data-stu-id="3546e-203">Wiki</span></span></li><li><span data-ttu-id="3546e-204">社区</span><span class="sxs-lookup"><span data-stu-id="3546e-204">Communities</span></span></li></ul>|
||||

## <a name="organize-a-help-desk"></a><span data-ttu-id="3546e-205">组织帮助台</span><span class="sxs-lookup"><span data-stu-id="3546e-205">Organize a help desk</span></span>

<span data-ttu-id="3546e-206">协作处理支持帮助台的文档、政策和流程。</span><span class="sxs-lookup"><span data-stu-id="3546e-206">Collaborate on documentation, policy and processes that support your helpdesk.</span></span> <span data-ttu-id="3546e-207">集成您的现有票证发放系统或使用我们的模板管理请求。</span><span class="sxs-lookup"><span data-stu-id="3546e-207">Integrate your existing ticketing system or use our template to manage requests.</span></span>

| <span data-ttu-id="3546e-208">基本模板类型</span><span class="sxs-lookup"><span data-stu-id="3546e-208">Base template type</span></span> | | <span data-ttu-id="3546e-209">此基本模板附带的属性</span><span class="sxs-lookup"><span data-stu-id="3546e-209">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="3546e-210">组织技术支持</span><span class="sxs-lookup"><span data-stu-id="3546e-210">Organize help desk</span></span>|`com.microsoft.teams.template.OrganizeHelpDesk`| <span data-ttu-id="3546e-211">信道</span><span class="sxs-lookup"><span data-stu-id="3546e-211">Channels:</span></span><ul><li><span data-ttu-id="3546e-212">常规</span><span class="sxs-lookup"><span data-stu-id="3546e-212">General</span></span></li><li><span data-ttu-id="3546e-213">宣告</span><span class="sxs-lookup"><span data-stu-id="3546e-213">Announcements</span></span></li><li><span data-ttu-id="3546e-214">常见问题</span><span class="sxs-lookup"><span data-stu-id="3546e-214">FAQ</span></span></li></ul><span data-ttu-id="3546e-215">识别</span><span class="sxs-lookup"><span data-stu-id="3546e-215">Apps:</span></span><ul><li><span data-ttu-id="3546e-216">源自</span><span class="sxs-lookup"><span data-stu-id="3546e-216">Wiki</span></span></li><li><span data-ttu-id="3546e-217">OneNote</span><span class="sxs-lookup"><span data-stu-id="3546e-217">OneNote</span></span></li></ul> |
||||
