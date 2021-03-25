---
title: Microsoft Teams 企业版部署概述
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: 了解如何部署 Microsoft Teams 的企业功能。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: bd3e60fafecd3cf025187935a9dc28b492c39d1b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121410"
---
# <a name="teams-enterprise-deployment-overview"></a><span data-ttu-id="2b9e8-103">Teams 企业部署概述</span><span class="sxs-lookup"><span data-stu-id="2b9e8-103">Teams enterprise deployment overview</span></span>

<span data-ttu-id="2b9e8-104">如果你是中型企业或大型企业，你需思考如何将该服务部署到用户、将 Microsoft Teams 客户端部署到他们、网络设计如何影响实时通信质量等。</span><span class="sxs-lookup"><span data-stu-id="2b9e8-104">If you're a medium or large business, you need to think about how you're going to roll out the service to your users, how you're going to deploy the Microsoft Teams client to them, how your network design could impact the quality of real-time communication, and so on.</span></span> <span data-ttu-id="2b9e8-105">查看以下各部分，查看指向可帮助你在组织中规划 Teams 的文章的指针。</span><span class="sxs-lookup"><span data-stu-id="2b9e8-105">Check out the following sections for pointers to articles that'll help you plan for Teams in your organization.</span></span>

> [!NOTE]
> <span data-ttu-id="2b9e8-106">如果尚未进行部署，强烈建议通过试点开始团队部署。</span><span class="sxs-lookup"><span data-stu-id="2b9e8-106">If you haven't done so already, we strongly suggest that you begin your Teams deployment with a pilot.</span></span> <span data-ttu-id="2b9e8-107">试点将允许你和一些早期采用者在规划和推出之前熟悉 Teams 及其功能。若要详细了解如何开始进行试点，请参阅 [Microsoft Teams](get-started-with-teams-quick-start.md)。</span><span class="sxs-lookup"><span data-stu-id="2b9e8-107">A pilot will allow you and a few early adopters to get familiar with Teams and its features before your planning and eventual roll out. For more information about how to start your pilot, check out [Get started with Microsoft Teams](get-started-with-teams-quick-start.md).</span></span>

<span data-ttu-id="2b9e8-108">阅读以下部分并准备好开始在组织中部署 Teams 之后，请参阅 [企业部署中的 Microsoft Teams](deploy-enterprise-setup.md)。</span><span class="sxs-lookup"><span data-stu-id="2b9e8-108">After you've read the sections below and are ready to start deploying Teams in your organization, see [Set up Microsoft Teams in your enterprise](deploy-enterprise-setup.md).</span></span>

## <a name="architecture"></a><span data-ttu-id="2b9e8-109">体系结构</span><span class="sxs-lookup"><span data-stu-id="2b9e8-109">Architecture</span></span>

<span data-ttu-id="2b9e8-110">团队紧密集成到 Microsoft 365 中，并使用多种功能支持聊天、文件共享、会议、电话、视频流等。</span><span class="sxs-lookup"><span data-stu-id="2b9e8-110">Teams is tightly integrated into Microsoft 365 and uses many features to power chat, file sharing, meetings, telephony, video streaming, and more.</span></span> <span data-ttu-id="2b9e8-111">推出 Teams 之前，请查看 [Microsoft Teams IT 体系结构和电话解决方案海报](teams-architecture-solutions-posters.md) 以便熟悉 Teams 如何与 Microsoft 365 其余部分协作，为用户创建完整的协作体验。</span><span class="sxs-lookup"><span data-stu-id="2b9e8-111">Before you roll out Teams, check out [Microsoft Teams IT architecture and telephony solutions posters](teams-architecture-solutions-posters.md) to get familiar with how Teams works with the rest of Microsoft 365 to create a complete collaboration experience for your users.</span></span>

## <a name="workloads"></a><span data-ttu-id="2b9e8-112">工作负载</span><span class="sxs-lookup"><span data-stu-id="2b9e8-112">Workloads</span></span>

<span data-ttu-id="2b9e8-113">团队有三个工作负载，可独立部署： **聊天、团队和**; **会议和会议**;和 **电话系统和 PSTN（公用电话交换网络）连接**。</span><span class="sxs-lookup"><span data-stu-id="2b9e8-113">Teams has three workloads that can be deployed independently of each other: **chat, teams, and channels**; **meetings and conferencing**; and **Phone System and PSTN (public switched telephone network) connectivity**.</span></span> <span data-ttu-id="2b9e8-114">每个工作负载在我们的文档中都有其自己的部分，以便更容易找到有关该工作负载的信息。</span><span class="sxs-lookup"><span data-stu-id="2b9e8-114">Each workload has its own section in our documentation to make it easier to find information about that workload.</span></span> <span data-ttu-id="2b9e8-115">这包括部署规划信息。</span><span class="sxs-lookup"><span data-stu-id="2b9e8-115">This includes deployment planning information.</span></span>

<span data-ttu-id="2b9e8-116">若要查看要部署的工作负荷的部署规划信息，请参阅下列文章：</span><span class="sxs-lookup"><span data-stu-id="2b9e8-116">To see deployment planning information for the workload you want to deploy, see the following articles:</span></span>

- [<span data-ttu-id="2b9e8-117">聊天、团队和渠道</span><span class="sxs-lookup"><span data-stu-id="2b9e8-117">Chat, teams, and channels</span></span>](deploy-chat-teams-channels-microsoft-teams-landing-page.md)
- [<span data-ttu-id="2b9e8-118">会话和会议</span><span class="sxs-lookup"><span data-stu-id="2b9e8-118">Meetings and conferencing</span></span>](deploy-meetings-microsoft-teams-landing-page.md)
- [<span data-ttu-id="2b9e8-119">电话系统和 PSTN 连接</span><span class="sxs-lookup"><span data-stu-id="2b9e8-119">Phone System and PSTN connectivity</span></span>](cloud-voice-landing-page.md)

## <a name="network-planner"></a><span data-ttu-id="2b9e8-120">Network Planner</span><span class="sxs-lookup"><span data-stu-id="2b9e8-120">Network planner</span></span>

<span data-ttu-id="2b9e8-121">如果用户众多或同时具有复杂的网络，则 Teams 的网络规划非常重要。</span><span class="sxs-lookup"><span data-stu-id="2b9e8-121">Network planning for Teams is extremely important when you have large numbers of users, complex networks, or both.</span></span> <span data-ttu-id="2b9e8-122">Teams 支持语音呼叫和视频会议，这两者均依赖于实时通信，为用户提供最佳体验。</span><span class="sxs-lookup"><span data-stu-id="2b9e8-122">Teams supports voice calling and video conferencing, both of which rely on real-time communications to provide the best experience possible for users.</span></span> <span data-ttu-id="2b9e8-123">网络必须：</span><span class="sxs-lookup"><span data-stu-id="2b9e8-123">Networks must:</span></span>

- <span data-ttu-id="2b9e8-124">有足够的带宽容量，容纳并发语音呼叫数、视频会议、会议、屏幕共享等。</span><span class="sxs-lookup"><span data-stu-id="2b9e8-124">Have sufficient bandwidth capacity to accommodate the number of concurrent voice calls, video conferences, meetings, screen sharing, and so on.</span></span>
- <span data-ttu-id="2b9e8-125">具有支持实时通信协议的网络硬件。</span><span class="sxs-lookup"><span data-stu-id="2b9e8-125">Have network hardware that supports real-time communication protocols.</span></span>
- <span data-ttu-id="2b9e8-126">允许网络上各设备之间的所需网络端口、Microsoft 365 服务和外部用户。</span><span class="sxs-lookup"><span data-stu-id="2b9e8-126">Allow the required network ports between devices on your networks, Microsoft 365 services, and external users.</span></span>

<span data-ttu-id="2b9e8-127">请参阅以下文章，帮助了解 Teams 网络要求：</span><span class="sxs-lookup"><span data-stu-id="2b9e8-127">See the following articles to help you understand Teams network requirements:</span></span>

- [<span data-ttu-id="2b9e8-128">为 Microsoft Teams 准备组织的网络</span><span class="sxs-lookup"><span data-stu-id="2b9e8-128">Prepare your organization's network for Microsoft Teams</span></span>](prepare-network.md)
- [<span data-ttu-id="2b9e8-129">Teams 或 Skype for Business Online 的代理服务器</span><span class="sxs-lookup"><span data-stu-id="2b9e8-129">Proxy servers for Teams or Skype for Business Online</span></span>](proxy-servers-for-skype-for-business-online.md)

<span data-ttu-id="2b9e8-130">为帮助你进行规划，Teams 包括网络规划器。</span><span class="sxs-lookup"><span data-stu-id="2b9e8-130">To help you with your planning, Teams includes the Network planner.</span></span> <span data-ttu-id="2b9e8-131">网络规划器将询问有关你拥有的用户数和类型、组织拥有的网站数、网络链接带宽容量等的问题。</span><span class="sxs-lookup"><span data-stu-id="2b9e8-131">The Network planner asks you questions about the number and types of users you have, how many sites your organization has, the bandwidth capacity of your network links, and more.</span></span> <span data-ttu-id="2b9e8-132">使用此信息，网络规划器将创建一个报表，显示每项活动的带宽要求和建议。</span><span class="sxs-lookup"><span data-stu-id="2b9e8-132">Using this information, the Network planner creates a report that shows the bandwidth requirements for each activity, along with the recommendations.</span></span>

 > [!div class="nextstepaction"]
> [<span data-ttu-id="2b9e8-133">转到网络规划器</span><span class="sxs-lookup"><span data-stu-id="2b9e8-133">Go to Network planner</span></span>](https://admin.teams.microsoft.com/networkplanner/organization)

<span data-ttu-id="2b9e8-134">（只有 Microsoft 365 [管理员才能](/microsoft-365/admin/add-users/about-admin-roles#commonly-used-microsoft-365-admin-center-roles) 网络规划器。）</span><span class="sxs-lookup"><span data-stu-id="2b9e8-134">(You must be a [Microsoft 365 global admin](/microsoft-365/admin/add-users/about-admin-roles#commonly-used-microsoft-365-admin-center-roles) to open the Network planner.)</span></span>

<span data-ttu-id="2b9e8-135">有关网络规划器工作方式的详细信息，请参阅 [使用 Microsoft Teams 网络规划器](network-planner.md)。</span><span class="sxs-lookup"><span data-stu-id="2b9e8-135">For details about how the Network planner works, see [Use the Network planner for Microsoft Teams](network-planner.md).</span></span>

<span data-ttu-id="2b9e8-136">若要了解网络规划器可如何规划网络的示例，请参阅["使用网络规划“ 的示例方案](tutorial-network-planner-example.yml)。</span><span class="sxs-lookup"><span data-stu-id="2b9e8-136">To see an example of how Network planner can plan your network, see [Using Network Planner - example scenario](tutorial-network-planner-example.yml).</span></span>

## <a name="teams-advisor"></a><span data-ttu-id="2b9e8-137">Teams 顾问</span><span class="sxs-lookup"><span data-stu-id="2b9e8-137">Teams advisor</span></span>

<span data-ttu-id="2b9e8-138">Teams 顾问是团队内解决方案，将团队、频道、文件共享和 Planner 结合起来，为组织创建部署项目。</span><span class="sxs-lookup"><span data-stu-id="2b9e8-138">The Teams advisor is a solution within Teams that brings together teams, channels, file sharing, and Planner, to create a deployment project for your organization.</span></span> <span data-ttu-id="2b9e8-139">Teams 顾问创建特定于您选择的工作负荷（例如聊天、团队和频道）的项目计划，其中包括在部署期间应执行的建议任务。</span><span class="sxs-lookup"><span data-stu-id="2b9e8-139">Teams advisor creates project plan, specific to the workload you select (such as chat, teams, and channels), that includes the recommended tasks you should perform during your deployment.</span></span> <span data-ttu-id="2b9e8-140">每个任务包含说明、建议和相关文章的链接，引导你完成该过程。</span><span class="sxs-lookup"><span data-stu-id="2b9e8-140">Each task contains instructions, suggestions, and links to relevant articles, to guide you through the process.</span></span> <span data-ttu-id="2b9e8-141">可以轻松将任务分配给一个或多个人员，并为每个任务指定开始日期和结束日期。</span><span class="sxs-lookup"><span data-stu-id="2b9e8-141">You can easily assign tasks to one or more individuals, and specify start and end dates for each task.</span></span>

> [!TIP]
> <span data-ttu-id="2b9e8-142">请参阅如何使用 Teams 顾问来帮助你规划团队部署，方法可以是完成 [Microsoft Learn 上的 Teams 顾问](/learn/modules/m365-teams-rollout-using-advisor/) 模块。</span><span class="sxs-lookup"><span data-stu-id="2b9e8-142">See how you can use Teams advisor to help you plan your Teams deployment by completing the [Roll out using the Teams advisor](/learn/modules/m365-teams-rollout-using-advisor/) module on Microsoft Learn.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="2b9e8-143">转到 Teams 顾问</span><span class="sxs-lookup"><span data-stu-id="2b9e8-143">Go to Teams advisor</span></span>](https://admin.teams.microsoft.com/teams-deployment)

<span data-ttu-id="2b9e8-144">（必须是 Microsoft 365 [管理员才能](/microsoft-365/admin/add-users/about-admin-roles#commonly-used-microsoft-365-admin-center-roles) Teams 顾问。）</span><span class="sxs-lookup"><span data-stu-id="2b9e8-144">(You must be a [Microsoft 365 global admin](/microsoft-365/admin/add-users/about-admin-roles#commonly-used-microsoft-365-admin-center-roles) to open the Teams advisor.)</span></span>

<span data-ttu-id="2b9e8-145">有关 Teams 顾问工作方式的详细信息，请参阅 [使用 Teams 顾问来帮助你推出 Microsoft Teams](use-advisor-teams-roll-out.md)。</span><span class="sxs-lookup"><span data-stu-id="2b9e8-145">For details about how the Teams advisor works, see [Use Advisor for Teams to help you roll out Microsoft Teams](use-advisor-teams-roll-out.md).</span></span>

## <a name="lifecycle-and-governance-planning"></a><span data-ttu-id="2b9e8-146">生命周期和管理规划</span><span class="sxs-lookup"><span data-stu-id="2b9e8-146">Lifecycle and governance planning</span></span>

<span data-ttu-id="2b9e8-147">规划团队部署时，需要考虑组织中团队的生命周期、频道、文件等。</span><span class="sxs-lookup"><span data-stu-id="2b9e8-147">As you plan your Teams deployment, you need to consider the lifecycle of teams, channels, files, and so on, in your organization.</span></span> <span data-ttu-id="2b9e8-148">还你应该考虑将存储在其中的信息类型。</span><span class="sxs-lookup"><span data-stu-id="2b9e8-148">You should also think about what types of information will be stored in them.</span></span> <span data-ttu-id="2b9e8-149">可能会为特定项目创建团队、为部门创建团队，或者将团队用作整个组织的集中资源。</span><span class="sxs-lookup"><span data-stu-id="2b9e8-149">Teams may be created for a specific project, for a department, or they might be used as a central resource for the entire organization.</span></span> <span data-ttu-id="2b9e8-150">每个用法具有不同的要求，这进一步提出类似问题：</span><span class="sxs-lookup"><span data-stu-id="2b9e8-150">Each of these uses have different requirements, which drive questions like the following:</span></span>

- <span data-ttu-id="2b9e8-151">团队持续活动会持续多久？</span><span class="sxs-lookup"><span data-stu-id="2b9e8-151">How long will the teams remain active?</span></span>
- <span data-ttu-id="2b9e8-152">谁应拥有和管理团队及其频道？</span><span class="sxs-lookup"><span data-stu-id="2b9e8-152">Who should own and manage the teams and their channels?</span></span>
- <span data-ttu-id="2b9e8-153">某些合规性要求应该适用于某些团队，而不适用于其他团队？</span><span class="sxs-lookup"><span data-stu-id="2b9e8-153">Should certain compliance requirements apply to some teams, but not others?</span></span>
- <span data-ttu-id="2b9e8-154">是否有可帮助用户识别合适团队的命名策略？</span><span class="sxs-lookup"><span data-stu-id="2b9e8-154">Should there be a naming policy to help users identify the right team?</span></span>

<span data-ttu-id="2b9e8-155">创建策略和准则作为初始部署的一部分，有助于确保你的用户能够找到所需的信息。</span><span class="sxs-lookup"><span data-stu-id="2b9e8-155">Creating policies and guidelines as part of your initial deployment will help ensure that your users can find the information they need.</span></span> <span data-ttu-id="2b9e8-156">但最重要的是，适当的策略可帮助防止组织信息泄露，帮助你符合法规要求，并根据需要保留信息以用于存档。</span><span class="sxs-lookup"><span data-stu-id="2b9e8-156">Just as importantly, however, appropriate policies will help protect your organization from information leakage, help you conform to regulatory requirements, and help you retain information as needed for archival purposes.</span></span>

<span data-ttu-id="2b9e8-157">若要深入了解 Teams 中的生命周期管理和管理，请参阅以下内容：</span><span class="sxs-lookup"><span data-stu-id="2b9e8-157">To learn more about lifecycle management and governance in Teams, see the following:</span></span>

- [<span data-ttu-id="2b9e8-158">在 Teams 中规划生命周期管理</span><span class="sxs-lookup"><span data-stu-id="2b9e8-158">Plan for lifecycle management in Teams</span></span>](plan-teams-lifecycle.md)
- [<span data-ttu-id="2b9e8-159">在 Teams 中规划管理</span><span class="sxs-lookup"><span data-stu-id="2b9e8-159">Plan for governance in Teams</span></span>](plan-teams-governance.md)

## <a name="adoption"></a><span data-ttu-id="2b9e8-160">采用</span><span class="sxs-lookup"><span data-stu-id="2b9e8-160">Adoption</span></span>

<span data-ttu-id="2b9e8-161">为确保你的组织和用户获取最多使用 Teams，需要采用计划。</span><span class="sxs-lookup"><span data-stu-id="2b9e8-161">To ensure that your organization and your users get the most out of Teams, you need an adoption program.</span></span> <span data-ttu-id="2b9e8-162">有效的采用计划可以提前采用者，他们可：</span><span class="sxs-lookup"><span data-stu-id="2b9e8-162">An effective adoption program can mobilize early adopters who can:</span></span>

- <span data-ttu-id="2b9e8-163">向同事以及业务或组领导阐明 Teams 的好处。</span><span class="sxs-lookup"><span data-stu-id="2b9e8-163">Articulate the benefits of Teams to their colleagues and to business or group leaders.</span></span>
- <span data-ttu-id="2b9e8-164">看到 Teams 如何改善协作并更轻松地相互联系时，为其他人激发热情。</span><span class="sxs-lookup"><span data-stu-id="2b9e8-164">Spark excitement in others who see how Teams improves collaboration and makes it easier to connect with each other.</span></span>
- <span data-ttu-id="2b9e8-165">帮助评估现有业务流程，并针对团队如何集成到其中提出建议。</span><span class="sxs-lookup"><span data-stu-id="2b9e8-165">Help evaluate existing business processes and make recommendations for how Teams can be integrated into them.</span></span>
- <span data-ttu-id="2b9e8-166">向部署团队报告成功和难题，帮助改进采用过程。</span><span class="sxs-lookup"><span data-stu-id="2b9e8-166">Report back to the deployment team both successes and difficulties to help improve the adoption process.</span></span>

<span data-ttu-id="2b9e8-167">有关设置采用计划的详细信息，请参阅 [采用 Microsoft Teams](adopt-microsoft-teams-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="2b9e8-167">For details about setting up an adoption program, see [Adopt Microsoft Teams](adopt-microsoft-teams-landing-page.md).</span></span>