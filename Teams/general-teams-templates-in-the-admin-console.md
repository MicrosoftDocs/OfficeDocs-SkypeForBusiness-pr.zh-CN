---
title: 在管理中心中使用常规团队模板
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
description: 了解如何使用常规团队模板，通过使用管理中心提供预定义的设置、信道和预安装应用来创建团队结构。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: a158850a70a0410c9be7cb434d6f0868d68218f5
ms.sourcegitcommit: 0a9c5c01b37a93eecc369ca0ed49ae18f6a5065b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2020
ms.locfileid: "48655499"
---
# <a name="use-general-teams-templates-in-the-admin-center"></a><span data-ttu-id="0c622-103">在管理中心中使用常规团队模板</span><span class="sxs-lookup"><span data-stu-id="0c622-103">Use general Teams templates in the admin center</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="0c622-104">团队模板使你可以通过提供设置、频道和预安装应用的预定义模板来快速轻松地创建团队。</span><span class="sxs-lookup"><span data-stu-id="0c622-104">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="0c622-105">团队模板具有围绕财务需求设计的团队结构的预建定义。</span><span class="sxs-lookup"><span data-stu-id="0c622-105">Teams templates have pre-built definitions of team structures designed around financial needs.</span></span> <span data-ttu-id="0c622-106">您还可以扩展团队模板以创建根据您的特定组织需求量身定制的团队。</span><span class="sxs-lookup"><span data-stu-id="0c622-106">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="0c622-107">在本文中，我们将介绍每个团队模板并建议如何使用它们。</span><span class="sxs-lookup"><span data-stu-id="0c622-107">In this article, we introduce each of the Teams templates and recommend how to use them.</span></span>

<span data-ttu-id="0c622-108">本文适用于你负责在整个财务组织中规划、部署和管理多个团队的情况。</span><span class="sxs-lookup"><span data-stu-id="0c622-108">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your financial organization.</span></span> <span data-ttu-id="0c622-109">你已在你的组织中部署团队服务。</span><span class="sxs-lookup"><span data-stu-id="0c622-109">You've already deployed Teams service in your organization.</span></span> <span data-ttu-id="0c622-110">如果尚未推出团队，请先阅读 [如何展示 Microsoft 团队](How-to-roll-out-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="0c622-110">If you haven't rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="0c622-111">若要深入了解有关团队模板的详细信息，请参阅 [团队模板入门](get-started-with-teams-templates-in-the-admin-console.md)。</span><span class="sxs-lookup"><span data-stu-id="0c622-111">To learn more about team templates in general, refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="global-crisis-or-event"></a><span data-ttu-id="0c622-112">全球危机或活动</span><span class="sxs-lookup"><span data-stu-id="0c622-112">Global crisis or event</span></span>

<span data-ttu-id="0c622-113">跨业务单元对危机团队协作，并帮助创建业务连续性计划、共享远程工作提示、跟踪客户通信，以及使用公告和新闻让每个人都保持联系。</span><span class="sxs-lookup"><span data-stu-id="0c622-113">Centralize collaboration for your crisis team across business units and help create business continuity plans, share remote working tips, track customer communications, and keep everyone in the loop with announcements and news.</span></span>

| <span data-ttu-id="0c622-114">基本模板类型</span><span class="sxs-lookup"><span data-stu-id="0c622-114">Base template type</span></span> |<span data-ttu-id="0c622-115">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="0c622-115">baseTemplateId</span></span>| <span data-ttu-id="0c622-116">此基本模板附带的属性</span><span class="sxs-lookup"><span data-stu-id="0c622-116">Properties that come with this base template</span></span> |
| ------------------ |--|----------------------------------------------------------|
| <span data-ttu-id="0c622-117">协作处理全球危机或活动</span><span class="sxs-lookup"><span data-stu-id="0c622-117">Collaborate on global crisis or event</span></span> |`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent` |<span data-ttu-id="0c622-118">信道</span><span class="sxs-lookup"><span data-stu-id="0c622-118">Channels:</span></span> <ul><li><span data-ttu-id="0c622-119">常规</span><span class="sxs-lookup"><span data-stu-id="0c622-119">General</span></span><li><span data-ttu-id="0c622-120">宣告</span><span class="sxs-lookup"><span data-stu-id="0c622-120">Announcements</span></span></li><li><span data-ttu-id="0c622-121">世界新闻</span><span class="sxs-lookup"><span data-stu-id="0c622-121">World news</span></span></li><li><span data-ttu-id="0c622-122">业务连续性</span><span class="sxs-lookup"><span data-stu-id="0c622-122">Business continuity</span></span></li><li><span data-ttu-id="0c622-123">远程工作</span><span class="sxs-lookup"><span data-stu-id="0c622-123">Remote working</span></span></li><li><span data-ttu-id="0c622-124">内部 comms</span><span class="sxs-lookup"><span data-stu-id="0c622-124">Internal comms</span></span></li><li><span data-ttu-id="0c622-125">外部 comms</span><span class="sxs-lookup"><span data-stu-id="0c622-125">External comms</span></span></li><li><span data-ttu-id="0c622-126">客户投诉</span><span class="sxs-lookup"><span data-stu-id="0c622-126">Customer complaints</span></span></li><li><span data-ttu-id="0c622-127">Kudos</span><span class="sxs-lookup"><span data-stu-id="0c622-127">Kudos</span></span></li><li><span data-ttu-id="0c622-128">执行更新</span><span class="sxs-lookup"><span data-stu-id="0c622-128">Executive update</span></span></li></ul><span data-ttu-id="0c622-129">识别</span><span class="sxs-lookup"><span data-stu-id="0c622-129">Apps:</span></span> <ul><li><span data-ttu-id="0c622-130">表扬</span><span class="sxs-lookup"><span data-stu-id="0c622-130">Praise</span></span></li><li><span data-ttu-id="0c622-131">源自</span><span class="sxs-lookup"><span data-stu-id="0c622-131">Wiki</span></span></li><li><span data-ttu-id="0c622-132">网站</span><span class="sxs-lookup"><span data-stu-id="0c622-132">Website</span></span></li></ul>|
||||

## <a name="adopt-office-365"></a><span data-ttu-id="0c622-133">采纳 Office 365</span><span class="sxs-lookup"><span data-stu-id="0c622-133">Adopt Office 365</span></span>

<span data-ttu-id="0c622-134">通过宣传和帮助你的同行使用新技术，帮助构建、扩大和维持你的拥护者社区推出。</span><span class="sxs-lookup"><span data-stu-id="0c622-134">Help build, grow, and sustain your Champions community rollout by evangelizing and helping your peers with the new technology.</span></span>

| <span data-ttu-id="0c622-135">基本模板类型</span><span class="sxs-lookup"><span data-stu-id="0c622-135">Base template type</span></span> |<span data-ttu-id="0c622-136">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="0c622-136">baseTemplateId</span></span>| <span data-ttu-id="0c622-137">此基本模板附带的属性</span><span class="sxs-lookup"><span data-stu-id="0c622-137">Properties that come with this base template</span></span> |
| ------------------|--|-----------------------------------------------------------|
| <span data-ttu-id="0c622-138">采纳 Office 365</span><span class="sxs-lookup"><span data-stu-id="0c622-138">Adopt Office 365</span></span> | `com.microsoft.teams.template.AdoptOffice365` |  <span data-ttu-id="0c622-139">信道</span><span class="sxs-lookup"><span data-stu-id="0c622-139">Channels:</span></span> <ul><li><span data-ttu-id="0c622-140">常规</span><span class="sxs-lookup"><span data-stu-id="0c622-140">General</span></span></li> <li><span data-ttu-id="0c622-141">宣告</span><span class="sxs-lookup"><span data-stu-id="0c622-141">Announcements</span></span></li> <li><span data-ttu-id="0c622-142">拥护方角落</span><span class="sxs-lookup"><span data-stu-id="0c622-142">Champions corner</span></span></li> <li><span data-ttu-id="0c622-143">工作组表单</span><span class="sxs-lookup"><span data-stu-id="0c622-143">Team forms</span></span></li></ul> <span data-ttu-id="0c622-144">识别</span><span class="sxs-lookup"><span data-stu-id="0c622-144">Apps:</span></span> <ul><li><span data-ttu-id="0c622-145">源自</span><span class="sxs-lookup"><span data-stu-id="0c622-145">Wiki</span></span></li>  <li><span data-ttu-id="0c622-146">日历</span><span class="sxs-lookup"><span data-stu-id="0c622-146">Calendar</span></span></li><li><span data-ttu-id="0c622-147">技能发展</span><span class="sxs-lookup"><span data-stu-id="0c622-147">Skills development</span></span></li><li><span data-ttu-id="0c622-148">借贷处理</span><span class="sxs-lookup"><span data-stu-id="0c622-148">Loan processing</span></span></li><li><span data-ttu-id="0c622-149">客户投诉</span><span class="sxs-lookup"><span data-stu-id="0c622-149">Customer complaints</span></span></li><li><span data-ttu-id="0c622-150">Kudos</span><span class="sxs-lookup"><span data-stu-id="0c622-150">Kudos</span></span></li><li><span data-ttu-id="0c622-151">有趣的资料</span><span class="sxs-lookup"><span data-stu-id="0c622-151">Fun stuff</span></span></li><li><span data-ttu-id="0c622-152">合规性</span><span class="sxs-lookup"><span data-stu-id="0c622-152">Compliance</span></span></li></ul>|
||||

## <a name="manage-a-project"></a><span data-ttu-id="0c622-153">管理项目</span><span class="sxs-lookup"><span data-stu-id="0c622-153">Manage a project</span></span>

<span data-ttu-id="0c622-154">通过此模板管理任务、共享文档、开展项目会议和记录风险和决策，以实现常规项目管理。</span><span class="sxs-lookup"><span data-stu-id="0c622-154">Manage tasks, share documents, conduct project meetings and document risks and decisions with this template for general project management.</span></span>

| <span data-ttu-id="0c622-155">基本模板类型</span><span class="sxs-lookup"><span data-stu-id="0c622-155">Base template type</span></span>| <span data-ttu-id="0c622-156">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="0c622-156">baseTemplateId</span></span>| <span data-ttu-id="0c622-157">此基本模板附带的属性</span><span class="sxs-lookup"><span data-stu-id="0c622-157">Properties that come with this base template</span></span> |
| ------------------|--|-----------------------------------------------------------|
| <span data-ttu-id="0c622-158">管理项目</span><span class="sxs-lookup"><span data-stu-id="0c622-158">Manage a project</span></span>| <span data-ttu-id="0c622-159">ManageAProject 中的 .com</span><span class="sxs-lookup"><span data-stu-id="0c622-159">com.microsoft.teams.template.ManageAProject</span></span>  | <span data-ttu-id="0c622-160">信道</span><span class="sxs-lookup"><span data-stu-id="0c622-160">Channels:</span></span> <ul><li><span data-ttu-id="0c622-161">常规</span><span class="sxs-lookup"><span data-stu-id="0c622-161">General</span></span></li> <li><span data-ttu-id="0c622-162">宣告</span><span class="sxs-lookup"><span data-stu-id="0c622-162">Announcements</span></span></li> <li><span data-ttu-id="0c622-163">.Resources</span><span class="sxs-lookup"><span data-stu-id="0c622-163">Resources</span></span></li> <li><span data-ttu-id="0c622-164">规划</span><span class="sxs-lookup"><span data-stu-id="0c622-164">Planning</span></span></li></ul> <span data-ttu-id="0c622-165">识别</span><span class="sxs-lookup"><span data-stu-id="0c622-165">Apps:</span></span><ul><li><span data-ttu-id="0c622-166">源自</span><span class="sxs-lookup"><span data-stu-id="0c622-166">Wiki</span></span></li><li><span data-ttu-id="0c622-167">OneNote</span><span class="sxs-lookup"><span data-stu-id="0c622-167">OneNote</span></span></li></ul> |
||||

## <a name="manage-an-event"></a><span data-ttu-id="0c622-168">管理事件</span><span class="sxs-lookup"><span data-stu-id="0c622-168">Manage an event</span></span>

<span data-ttu-id="0c622-169">管理任务、文档，并协作处理提供引人注目事件所需的所有内容。</span><span class="sxs-lookup"><span data-stu-id="0c622-169">Manage tasks, documents, and collaborate on everything you need to deliver a compelling event.</span></span> <span data-ttu-id="0c622-170">邀请来宾用户在您的公司内部和外部进行安全协作。</span><span class="sxs-lookup"><span data-stu-id="0c622-170">Invite guests users to have secure collaboration inside and outside of your company.</span></span>

<span data-ttu-id="0c622-171">你可能无法访问基于你的应用权限策略的某些应用。</span><span class="sxs-lookup"><span data-stu-id="0c622-171">You might not have access to certain apps based on your app permission policy.</span></span>

| <span data-ttu-id="0c622-172">基本模板类型</span><span class="sxs-lookup"><span data-stu-id="0c622-172">Base template type</span></span> | <span data-ttu-id="0c622-173">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="0c622-173">baseTemplateId</span></span>| <span data-ttu-id="0c622-174">此基本模板附带的属性</span><span class="sxs-lookup"><span data-stu-id="0c622-174">Properties that come with this base template</span></span> |
| ------------------ |--|-----------------------------------------------------------|
| <span data-ttu-id="0c622-175">管理事件</span><span class="sxs-lookup"><span data-stu-id="0c622-175">Manage an event</span></span>| `com.microsoft.teams.template.ManageAnEvent` | <span data-ttu-id="0c622-176">信道</span><span class="sxs-lookup"><span data-stu-id="0c622-176">Channels:</span></span> <ul><li><span data-ttu-id="0c622-177">常规</span><span class="sxs-lookup"><span data-stu-id="0c622-177">General</span></span></li> <li><span data-ttu-id="0c622-178">宣告</span><span class="sxs-lookup"><span data-stu-id="0c622-178">Announcements</span></span></li> <li><span data-ttu-id="0c622-179">预算</span><span class="sxs-lookup"><span data-stu-id="0c622-179">Budget</span></span></li> <li><span data-ttu-id="0c622-180">内容</span><span class="sxs-lookup"><span data-stu-id="0c622-180">Content</span></span></li><li><span data-ttu-id="0c622-181">后勤工作</span><span class="sxs-lookup"><span data-stu-id="0c622-181">Logistics</span></span></li> <li><span data-ttu-id="0c622-182">规划</span><span class="sxs-lookup"><span data-stu-id="0c622-182">Planning</span></span></li> <li> <span data-ttu-id="0c622-183">市场营销和 PR</span><span class="sxs-lookup"><span data-stu-id="0c622-183">Marketing and PR</span></span></li></ul> <span data-ttu-id="0c622-184">识别</span><span class="sxs-lookup"><span data-stu-id="0c622-184">Apps:</span></span><ul><li><span data-ttu-id="0c622-185">源自</span><span class="sxs-lookup"><span data-stu-id="0c622-185">Wiki</span></span></li><li><span data-ttu-id="0c622-186">网站</span><span class="sxs-lookup"><span data-stu-id="0c622-186">Website</span></span></li> <li><span data-ttu-id="0c622-187">YouTube</span><span class="sxs-lookup"><span data-stu-id="0c622-187">YouTube</span></span></li> <li><span data-ttu-id="0c622-188">Planner</span><span class="sxs-lookup"><span data-stu-id="0c622-188">Planner</span></span></li> <li><span data-ttu-id="0c622-189">OneNote</span><span class="sxs-lookup"><span data-stu-id="0c622-189">OneNote</span></span></li></ul> |
||||

## <a name="onboard-employees"></a><span data-ttu-id="0c622-190">板载员工</span><span class="sxs-lookup"><span data-stu-id="0c622-190">Onboard employees</span></span>

<span data-ttu-id="0c622-191">利用此中心团队改进您的文化，为您的资源、问题和乐趣，简化您的工作。</span><span class="sxs-lookup"><span data-stu-id="0c622-191">Improve your culture and streamline your employee onboarding with this central team for resources, questions, and a bit of fun.</span></span>

| <span data-ttu-id="0c622-192">基本模板类型</span><span class="sxs-lookup"><span data-stu-id="0c622-192">Base template type</span></span> |<span data-ttu-id="0c622-193">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="0c622-193">baseTemplateId</span></span>| <span data-ttu-id="0c622-194">此基本模板附带的属性</span><span class="sxs-lookup"><span data-stu-id="0c622-194">Properties that come with this base template</span></span> |
| ------------------|--|-----------------------------------------------------------|
|<span data-ttu-id="0c622-195">板载员工</span><span class="sxs-lookup"><span data-stu-id="0c622-195">Onboard employees</span></span>|`com.microsoft.teams.template.OnboardEmployees`  | <span data-ttu-id="0c622-196">信道</span><span class="sxs-lookup"><span data-stu-id="0c622-196">Channels:</span></span> <ul><li><span data-ttu-id="0c622-197">常规</span><span class="sxs-lookup"><span data-stu-id="0c622-197">General</span></span></li> <li><span data-ttu-id="0c622-198">宣告</span><span class="sxs-lookup"><span data-stu-id="0c622-198">Announcements</span></span></li> <li><span data-ttu-id="0c622-199">员工聊天</span><span class="sxs-lookup"><span data-stu-id="0c622-199">Employee chat</span></span></li> <li><span data-ttu-id="0c622-200">培训</span><span class="sxs-lookup"><span data-stu-id="0c622-200">Training</span></span></li></ul><span data-ttu-id="0c622-201">识别</span><span class="sxs-lookup"><span data-stu-id="0c622-201">Apps:</span></span><ul><li><span data-ttu-id="0c622-202">源自</span><span class="sxs-lookup"><span data-stu-id="0c622-202">Wiki</span></span></li><li><span data-ttu-id="0c622-203">社区</span><span class="sxs-lookup"><span data-stu-id="0c622-203">Communities</span></span></li></ul>|
||||

## <a name="organize-a-help-desk"></a><span data-ttu-id="0c622-204">组织帮助台</span><span class="sxs-lookup"><span data-stu-id="0c622-204">Organize a help desk</span></span>

<span data-ttu-id="0c622-205">协作处理支持帮助台的文档、政策和流程。</span><span class="sxs-lookup"><span data-stu-id="0c622-205">Collaborate on documentation, policy, and processes that support your helpdesk.</span></span> <span data-ttu-id="0c622-206">集成您的现有票证发放系统或使用我们的模板管理请求。</span><span class="sxs-lookup"><span data-stu-id="0c622-206">Integrate your existing ticketing system or use our template to manage requests.</span></span>

| <span data-ttu-id="0c622-207">基本模板类型</span><span class="sxs-lookup"><span data-stu-id="0c622-207">Base template type</span></span> |<span data-ttu-id="0c622-208">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="0c622-208">baseTemplateId</span></span>| <span data-ttu-id="0c622-209">此基本模板附带的属性</span><span class="sxs-lookup"><span data-stu-id="0c622-209">Properties that come with this base template</span></span> |
| ------------------|--|------------------------------------------------------------|
|<span data-ttu-id="0c622-210">组织技术支持</span><span class="sxs-lookup"><span data-stu-id="0c622-210">Organize help desk</span></span>|`com.microsoft.teams.template.OrganizeHelpDesk`| <span data-ttu-id="0c622-211">信道</span><span class="sxs-lookup"><span data-stu-id="0c622-211">Channels:</span></span><ul><li><span data-ttu-id="0c622-212">常规</span><span class="sxs-lookup"><span data-stu-id="0c622-212">General</span></span></li><li><span data-ttu-id="0c622-213">宣告</span><span class="sxs-lookup"><span data-stu-id="0c622-213">Announcements</span></span></li><li><span data-ttu-id="0c622-214">常见问题</span><span class="sxs-lookup"><span data-stu-id="0c622-214">FAQ</span></span></li></ul><span data-ttu-id="0c622-215">识别</span><span class="sxs-lookup"><span data-stu-id="0c622-215">Apps:</span></span><ul><li><span data-ttu-id="0c622-216">源自</span><span class="sxs-lookup"><span data-stu-id="0c622-216">Wiki</span></span></li><li><span data-ttu-id="0c622-217">OneNote</span><span class="sxs-lookup"><span data-stu-id="0c622-217">OneNote</span></span></li></ul> |
||||
