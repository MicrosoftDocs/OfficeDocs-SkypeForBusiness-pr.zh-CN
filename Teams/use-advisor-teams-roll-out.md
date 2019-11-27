---
title: 使用 Advisor for Teams（预览版）帮助你推出 Microsoft Teams
author: lolajacobsen
ms.author: lolaj
ms.reviewer: brandber
manager: serdars
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Priority
f1keywords:
- ms.teamsadmincenter.deploymentadvisor.overview
ms.custom: ''
description: 使用 Advisor for Teams（预览版）帮助你计划和完成 Microsoft Teams 部署。
ms.openlocfilehash: f7de348c6f8ca60cc1d062fce79725b4b18d0350
ms.sourcegitcommit: 5a7e273a3636322052e4a48a5a75513cbf5abb84
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "39209188"
---
# <a name="use-advisor-for-teams-to-help-you-roll-out-microsoft-teams"></a><span data-ttu-id="05f44-103">使用 Advisor for Teams 帮助你推出 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="05f44-103">Use Advisor for Teams to help you roll out Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="05f44-104">Advisor for Teams（预览版）为你提供 Microsoft Teams 推出的分步指导。</span><span class="sxs-lookup"><span data-stu-id="05f44-104">Advisor for Teams (preview) walks you through your Microsoft Teams rollout.</span></span> <span data-ttu-id="05f44-105">它将评估 Office 365 租户环境并确定更新或修改所需的最常用配置，帮助你成功推出 Teams。</span><span class="sxs-lookup"><span data-stu-id="05f44-105">It assesses your Office 365 tenant environment and identifies the most common configurations that you may need to update or modify before you can successfully roll out Teams.</span></span> <span data-ttu-id="05f44-106">然后，Advisor for Teams 会创建一个部署团队（在 Teams 中），你要推出的每个工作负载都有对应的频道。部署团队中的每个工作负载都有一个综合 Planner 计划，其中包括每个工作负载的所有推出任务。</span><span class="sxs-lookup"><span data-stu-id="05f44-106">Then, Advisor for Teams creates a Service management team (in Teams), with channels for each workload you want to roll out. Each workload in the Service management team comes with a comprehensive Planner plan that includes all the rollout tasks for each workload.</span></span>  <span data-ttu-id="05f44-107">使用此 Planner 计划将任务分配给负责推出的每个阶段的人员 - 包括项目经理、Teams 和 Office 365 管理员、支持人员以及你的采用和用户就绪性团队。</span><span class="sxs-lookup"><span data-stu-id="05f44-107">Using this Planner plan, you'll assign tasks to the people responsible for each phase of the rollout - including the project manager, Teams and Office 365 admins, support people, and your adoption and user readiness team.</span></span> <span data-ttu-id="05f44-108">每个推出任务包含成功完成任务所需的所有指南和资源。</span><span class="sxs-lookup"><span data-stu-id="05f44-108">Each rollout task contains all the guidance and resources you need to successfully complete the task.</span></span>

<span data-ttu-id="05f44-109">Advisor for Teams 是 [Teams管理中心](https://admin.teams.microsoft.com)的一部分。</span><span class="sxs-lookup"><span data-stu-id="05f44-109">Advisor for Teams is part of the [Teams admin center](https://admin.teams.microsoft.com).</span></span> <span data-ttu-id="05f44-110">若要首次使用 Advisor for Teams，请在仪表板上的“**部署 Teams 工作负载**”小组件中单击“**启动**”按钮。</span><span class="sxs-lookup"><span data-stu-id="05f44-110">To use Advisor for Teams the first time, click the **Start** button in the **Deploying Teams workload** widget on the Dashboard.</span></span> <span data-ttu-id="05f44-111">或者转到“**计划**” > “**Advisor**”。</span><span class="sxs-lookup"><span data-stu-id="05f44-111">Or go to **Planning** > **Advisor**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="05f44-112">Advisor for Teams 不适用于 Microsoft 365 政府版 - GCC High 或 DoD 部署。</span><span class="sxs-lookup"><span data-stu-id="05f44-112">Advisor for Teams isn't available for Microsoft 365 Government - GCC High or DoD deployments.</span></span>

## <a name="using-advisor-for-teams-preview"></a><span data-ttu-id="05f44-113">使用 Advisor for Teams（预览版）</span><span class="sxs-lookup"><span data-stu-id="05f44-113">Using Advisor for Teams (preview)</span></span>

<span data-ttu-id="05f44-114">要使用 Advisor for Teams，不需要是 Teams 管理员 - 组织中的任何人都可使用它。</span><span class="sxs-lookup"><span data-stu-id="05f44-114">You don't have to be a Teams admin to use Advisor for Teams - anybody in your organization can use it.</span></span> <span data-ttu-id="05f44-115">我们设置了特殊权限，使非管理员用户可以使用 Advisor for Teams，即使它位于团队管理中心，也是如此。</span><span class="sxs-lookup"><span data-stu-id="05f44-115">We've set up special permissions so non-admin users can get to Advisor for Teams, even though it's in the Teams admin center.</span></span> <span data-ttu-id="05f44-116">必须是 Teams 管理员、Teams 服务管理员或全局管理员才能打开租户就绪性评估。</span><span class="sxs-lookup"><span data-stu-id="05f44-116">You DO have to be a Teams admin, Teams Service Administrator, or Global Administrator to open the tenant readiness assessments.</span></span>

<span data-ttu-id="05f44-117">第一次使用 Advisor for Teams 时，它将在 Teams 中为你创建一个部署团队。</span><span class="sxs-lookup"><span data-stu-id="05f44-117">The first time you use Advisor for Teams, it'll create a Service management team for you in Teams.</span></span> <span data-ttu-id="05f44-118">它为你要推出的每个工作负载添加频道。</span><span class="sxs-lookup"><span data-stu-id="05f44-118">It adds channels for each workload you want to roll out.</span></span> 


## <a name="available-advisor-for-teams-plans"></a><span data-ttu-id="05f44-119">可用的 Advisor for Teams 计划</span><span class="sxs-lookup"><span data-stu-id="05f44-119">Available Advisor for Teams plans</span></span>

<span data-ttu-id="05f44-120">在 Advisor for Teams 处于预览阶段时，我们提供以下两种计划：</span><span class="sxs-lookup"><span data-stu-id="05f44-120">While Advisor for Teams is in preview, we're providing these two plans:</span></span>

1. <span data-ttu-id="05f44-121">聊天、团队、频道和应用</span><span class="sxs-lookup"><span data-stu-id="05f44-121">Chat, teams, channels, and apps</span></span>
    - <span data-ttu-id="05f44-122">租户评估</span><span class="sxs-lookup"><span data-stu-id="05f44-122">Tenant assessment</span></span>
    - <span data-ttu-id="05f44-123">Planner 计划，包括采用任务</span><span class="sxs-lookup"><span data-stu-id="05f44-123">Planner plan, including adoption tasks</span></span>
    - <span data-ttu-id="05f44-124">Forms 用户调查</span><span class="sxs-lookup"><span data-stu-id="05f44-124">Forms user survey</span></span>
1. <span data-ttu-id="05f44-125">会话和会议</span><span class="sxs-lookup"><span data-stu-id="05f44-125">Meetings and conferencing</span></span>
    - <span data-ttu-id="05f44-126">租户评估</span><span class="sxs-lookup"><span data-stu-id="05f44-126">Tenant assessment</span></span>
    - <span data-ttu-id="05f44-127">Planner 计划，包括采用任务</span><span class="sxs-lookup"><span data-stu-id="05f44-127">Planner plan, including adoption tasks</span></span>
    - <span data-ttu-id="05f44-128">Forms 用户调查</span><span class="sxs-lookup"><span data-stu-id="05f44-128">Forms user survey</span></span>

<span data-ttu-id="05f44-129">建议从“聊天”、“团队”、“频道”和“应用计划”开始。</span><span class="sxs-lookup"><span data-stu-id="05f44-129">We recommend that you start with the Chat, teams, channels, and apps plan.</span></span> <span data-ttu-id="05f44-130">工作负载部署完成后，请返回到 Advisor，然后单击“**添加频道**”以开始下一个工作负载。</span><span class="sxs-lookup"><span data-stu-id="05f44-130">When you're done deploying that workload, go back to Advisor and click **Add channel** to start the next workload.</span></span> 

## <a name="tenant-assessment"></a><span data-ttu-id="05f44-131">租户评估</span><span class="sxs-lookup"><span data-stu-id="05f44-131">Tenant assessment</span></span>
<span data-ttu-id="05f44-132">每个计划都包括租户就绪性评估，可用于在推出 Teams 前识别并补救环境中的任何缺陷。</span><span class="sxs-lookup"><span data-stu-id="05f44-132">Each plan includes a tenant readiness assessment that you can use to identify and remediate any deficiencies in your environment before you roll out Teams.</span></span> <span data-ttu-id="05f44-133">下面是每个评估的检查内容：</span><span class="sxs-lookup"><span data-stu-id="05f44-133">Here's what each assessment checks:</span></span>

### <a name="chat-teams-channels-and-apps"></a><span data-ttu-id="05f44-134">聊天、团队、频道和应用</span><span class="sxs-lookup"><span data-stu-id="05f44-134">Chat, teams, channels, and apps</span></span>


|<span data-ttu-id="05f44-135">评估</span><span class="sxs-lookup"><span data-stu-id="05f44-135">Assessment</span></span>  |<span data-ttu-id="05f44-136">结果</span><span class="sxs-lookup"><span data-stu-id="05f44-136">What it tells you</span></span>  |
|---------|---------|
|<span data-ttu-id="05f44-137">Teams 许可证</span><span class="sxs-lookup"><span data-stu-id="05f44-137">Teams licenses</span></span>     |<span data-ttu-id="05f44-138">你是否有具有可用 Teams 许可证的活动订阅</span><span class="sxs-lookup"><span data-stu-id="05f44-138">Whether you have an active subscription with available Teams licenses</span></span> |
|<span data-ttu-id="05f44-139">Exchange 许可证</span><span class="sxs-lookup"><span data-stu-id="05f44-139">Exchange licenses</span></span>     |<span data-ttu-id="05f44-140">你是否有具有可用 Exchange Online 许可证的活动订阅</span><span class="sxs-lookup"><span data-stu-id="05f44-140">Whether you have an active subscription with available Exchange Online licenses.</span></span> <span data-ttu-id="05f44-141">虽然 Exchange 不是基本 Teams 功能所必需的，但与 Exchange 的集成提供了一种最佳 Teams 体验。</span><span class="sxs-lookup"><span data-stu-id="05f44-141">While Exchange isn't required for basic Teams functionality, integration with Exchange provides an optimal Teams experience.</span></span>         |
|<span data-ttu-id="05f44-142">SharePoint Online 许可证</span><span class="sxs-lookup"><span data-stu-id="05f44-142">SharePoint Online licenses</span></span>     | <span data-ttu-id="05f44-143">你是否有具有可用 SharePoint Online 许可证的活动订阅。</span><span class="sxs-lookup"><span data-stu-id="05f44-143">Whether you have an active subscription with available SharePoint Online licenses.</span></span> <span data-ttu-id="05f44-144">对于文件存储、频道协作和聊天，每个用户需要一个 SharePoint Online 许可证。</span><span class="sxs-lookup"><span data-stu-id="05f44-144">You need one SharePoint Online license per user for file storage, channel collaboration, and chat.</span></span> 
|<span data-ttu-id="05f44-145">已启用来宾访问</span><span class="sxs-lookup"><span data-stu-id="05f44-145">Guest access enabled</span></span>     |<span data-ttu-id="05f44-146">Teams 中的来宾访问是否已启用。</span><span class="sxs-lookup"><span data-stu-id="05f44-146">If guest access is turned on in Teams.</span></span> <span data-ttu-id="05f44-147">不会审核来宾访问的 Azure Active Directory 设置。</span><span class="sxs-lookup"><span data-stu-id="05f44-147">Azure Active Directory settings for guest access are not reviewed.</span></span>   |
|<span data-ttu-id="05f44-148">已配置虚域</span><span class="sxs-lookup"><span data-stu-id="05f44-148">Vanity domain configured</span></span>     |<span data-ttu-id="05f44-149">是否为你的租户配置了非 @onmicrosoft.com 域</span><span class="sxs-lookup"><span data-stu-id="05f44-149">Whether there's a non-@onmicrosoft.com domain configured for your tenant</span></span>  |
|<span data-ttu-id="05f44-150">已配置 Office 365 组命名标准</span><span class="sxs-lookup"><span data-stu-id="05f44-150">Office 365 Group naming standard configured</span></span>     | <span data-ttu-id="05f44-151">是否已为 Office 365 组配置命名标准</span><span class="sxs-lookup"><span data-stu-id="05f44-151">Whether naming standards have been configured for Office 365 Groups</span></span>        |
|<span data-ttu-id="05f44-152">已配置 Office 365 组到期</span><span class="sxs-lookup"><span data-stu-id="05f44-152">Office 365 Group expiration configured</span></span>     |  <span data-ttu-id="05f44-153">是否已为 Office 365 组定义组到期策略。</span><span class="sxs-lookup"><span data-stu-id="05f44-153">Whether a Group expiration policy has been defined for Office 365 Groups.</span></span> <span data-ttu-id="05f44-154">如果没有，则该值设置为“从不”。</span><span class="sxs-lookup"><span data-stu-id="05f44-154">If not, the value is set to never.</span></span>        |
|<span data-ttu-id="05f44-155">已配置外部访问</span><span class="sxs-lookup"><span data-stu-id="05f44-155">External access configured</span></span>     |<span data-ttu-id="05f44-156">如果已启用外部访问，则可与 Teams 中的外部组织进行通信。</span><span class="sxs-lookup"><span data-stu-id="05f44-156">If external access is turned on so you can communicate with external organizations in Teams.</span></span>          |

### <a name="meetings-and-conferencing"></a><span data-ttu-id="05f44-157">会话和会议</span><span class="sxs-lookup"><span data-stu-id="05f44-157">Meetings and conferencing</span></span>


|<span data-ttu-id="05f44-158">评估</span><span class="sxs-lookup"><span data-stu-id="05f44-158">Assessment</span></span>  |<span data-ttu-id="05f44-159">结果</span><span class="sxs-lookup"><span data-stu-id="05f44-159">What it tells you</span></span>  |
|---------|---------|
|<span data-ttu-id="05f44-160">Teams 许可证</span><span class="sxs-lookup"><span data-stu-id="05f44-160">Teams licenses</span></span>     |<span data-ttu-id="05f44-161">你是否有具有可用 Teams 许可证的活动订阅</span><span class="sxs-lookup"><span data-stu-id="05f44-161">Whether you have an active subscription with available Teams licenses</span></span> |
|<span data-ttu-id="05f44-162">Exchange 许可证</span><span class="sxs-lookup"><span data-stu-id="05f44-162">Exchange licenses</span></span>     |<span data-ttu-id="05f44-163">你是否有具有可用 Exchange Online 许可证的活动订阅</span><span class="sxs-lookup"><span data-stu-id="05f44-163">Whether you have an active subscription with available Exchange Online licenses.</span></span> <span data-ttu-id="05f44-164">虽然 Exchange 不是基本 Teams 功能所必需的，但与 Exchange 的集成提供了一种最佳 Teams 体验。</span><span class="sxs-lookup"><span data-stu-id="05f44-164">While Exchange isn't required for basic Teams functionality, integration with Exchange provides an optimal Teams experience.</span></span> |
|<span data-ttu-id="05f44-165">音频会议许可证</span><span class="sxs-lookup"><span data-stu-id="05f44-165">Audio conferencing licenses</span></span>    |<span data-ttu-id="05f44-166">你是否有具有音频会议许可证的活动订阅</span><span class="sxs-lookup"><span data-stu-id="05f44-166">Whether you have an active subscription with Audio conferencing licenses</span></span> |
|<span data-ttu-id="05f44-167">流式传输许可证</span><span class="sxs-lookup"><span data-stu-id="05f44-167">Stream licenses</span></span>     |<span data-ttu-id="05f44-168">你是否有具有流式传输许可证的活动订阅（如果需要会议录制可以使用此许可证）。</span><span class="sxs-lookup"><span data-stu-id="05f44-168">Whether you have an active subscription with Stream licenses, which can used should Meeting Recording be desired.</span></span> |
|<span data-ttu-id="05f44-169">来宾访问权限</span><span class="sxs-lookup"><span data-stu-id="05f44-169">Guest access</span></span>     |<span data-ttu-id="05f44-170">Teams 中的来宾访问是否已启用。</span><span class="sxs-lookup"><span data-stu-id="05f44-170">If guest access is turned on in Teams.</span></span> <span data-ttu-id="05f44-171">不会审核来宾访问的 Azure Active Directory 设置。</span><span class="sxs-lookup"><span data-stu-id="05f44-171">Azure Active Directory settings for guest access are not reviewed.</span></span>|
|<span data-ttu-id="05f44-172">虚域</span><span class="sxs-lookup"><span data-stu-id="05f44-172">Vanity domain</span></span>     |<span data-ttu-id="05f44-173">是否为你的租户配置了非 @onmicrosoft.com 域。</span><span class="sxs-lookup"><span data-stu-id="05f44-173">Whether there's a non-@onmicrosoft.com domain configured for your tenant.</span></span>  |
|<span data-ttu-id="05f44-174">外部访问</span><span class="sxs-lookup"><span data-stu-id="05f44-174">External access</span></span>     |<span data-ttu-id="05f44-175">如果已启用外部访问，则可与 Teams 中的外部组织进行通信。</span><span class="sxs-lookup"><span data-stu-id="05f44-175">If external access is turned on so you can communicate with external organizations in Teams.</span></span> |


### <a name="advisor-bot"></a><span data-ttu-id="05f44-176">Advisor 机器人</span><span class="sxs-lookup"><span data-stu-id="05f44-176">Advisor bot</span></span>
<span data-ttu-id="05f44-177">Advisor 创建部署团队后，Advisor 机器人就会发送以下消息。</span><span class="sxs-lookup"><span data-stu-id="05f44-177">Once Advisor creates your Service management team, the Advisor bot delivers the following message.</span></span>

><span data-ttu-id="05f44-178">**欢迎使用 Microsoft Teams 中的部署团队！**</span><span class="sxs-lookup"><span data-stu-id="05f44-178">**Welcome to your Service management team for Microsoft Teams!**</span></span>
>  
><span data-ttu-id="05f44-179">此团队的目的是为你提供组织的 Teams 推出的分步指导，方法是为你提供所需的所有资源，并为项目团队提供协作空间。</span><span class="sxs-lookup"><span data-stu-id="05f44-179">The purpose of this team is to walk you through your organization's Teams rollout by giving you all the resources you need and providing a collaboration space for the project team.</span></span> <span data-ttu-id="05f44-180">使用 Advisor for Teams 创建的每个频道包括分步 Planner 计划和其他资源，例如可在整个推出过程中使用的 Forms 用户调查。</span><span class="sxs-lookup"><span data-stu-id="05f44-180">Each channel created using Advisor for Teams includes a step-by-step Planner plan and other resources such as a Forms users survey that can be used throughout your rollout.</span></span> <span data-ttu-id="05f44-181">可随时返回并查看租户就绪性评估或使用 Teams 管理中心添加其他工作负载计划。</span><span class="sxs-lookup"><span data-stu-id="05f44-181">At any point, you can you go back and review the tenant readiness assessment or add additional workload plans using the Teams admin center.</span></span> 
> 
><span data-ttu-id="05f44-182">**行动号召**</span><span class="sxs-lookup"><span data-stu-id="05f44-182">**Call to action**</span></span> 
>- <span data-ttu-id="05f44-183">如果你不熟悉 Teams 或 Planner，请查看我们的 [Teams 演练](https://teamsdemo.office.com/)并观看 [Planner 快速入门视频](https://support.office.com/article/microsoft-planner-video-training-4d71390f-08d8-4db0-84ea-92fb078687c7)。</span><span class="sxs-lookup"><span data-stu-id="05f44-183">If you're new to Teams or Planner, check out our [Teams walkthrough](https://teamsdemo.office.com/) and watch the [Planner quick-start videos](https://support.office.com/article/microsoft-planner-video-training-4d71390f-08d8-4db0-84ea-92fb078687c7).</span></span> 
>- <span data-ttu-id="05f44-184">转到 Teams 中的部署团队。</span><span class="sxs-lookup"><span data-stu-id="05f44-184">Head over to your Service management team in Teams.</span></span> <span data-ttu-id="05f44-185">选择工作负载频道（例如，“聊天”、“团队”、“频道”和“应用”），选择“**Planner**”选项卡以开始使用。</span><span class="sxs-lookup"><span data-stu-id="05f44-185">Select your workload channel (for example, Chat, teams, channels, and apps), and select the **Planner** tab to get started.</span></span>
> 
><span data-ttu-id="05f44-186">若要了解有关 Advisor for Teams 的详细信息，请参阅[使用 Advisor for Teams 推出 Microsoft Teams](use-advisor-teams-roll-out.md)。</span><span class="sxs-lookup"><span data-stu-id="05f44-186">To learn more about Advisor for Teams, read [Use Advisor for Teams to roll out Microsoft Teams](use-advisor-teams-roll-out.md).</span></span>
>
> [!IMPORTANT]
> <span data-ttu-id="05f44-187">Advisor for Teams 机器人仅用于向部署团队发送欢迎消息。</span><span class="sxs-lookup"><span data-stu-id="05f44-187">The Advisor for Teams Bot is only used to send a welcome message to your service management team.</span></span> <span data-ttu-id="05f44-188">不会收集额外的数据。</span><span class="sxs-lookup"><span data-stu-id="05f44-188">No additional data is collected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="05f44-189">默认情况下启用 Advisor for Teams。</span><span class="sxs-lookup"><span data-stu-id="05f44-189">The Advisor for Teams bot is enabled by default.</span></span> <span data-ttu-id="05f44-190">如果你使用或计划使用 Advisor for Teams，请不要禁用此项。</span><span class="sxs-lookup"><span data-stu-id="05f44-190">Do not disable it if you use or plan on using Advisor for Teams.</span></span>


## <a name="frequently-asked-questions"></a><span data-ttu-id="05f44-191">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="05f44-191">Frequently asked questions</span></span>
### <a name="what-are-the-licensing-requirements-for-advisor-for-teams"></a><span data-ttu-id="05f44-192">Advisor for Teams 的许可要求是什么？</span><span class="sxs-lookup"><span data-stu-id="05f44-192">What are the licensing requirements for Advisor for Teams?</span></span>
<span data-ttu-id="05f44-193">除获得 Teams 许可之外，没有其他许可要求。</span><span class="sxs-lookup"><span data-stu-id="05f44-193">There are no additional licensing requirements other than being licensed for Teams.</span></span>

### <a name="can-i-delete-the-deployment-team"></a><span data-ttu-id="05f44-194">我是否可以删除部署团队？</span><span class="sxs-lookup"><span data-stu-id="05f44-194">Can I delete the Service management team?</span></span>
<span data-ttu-id="05f44-195">在 Advisor for Teams 创建部署团队后，可以像管理任何其他团队那样管理该团队，包括可以删除该团队。</span><span class="sxs-lookup"><span data-stu-id="05f44-195">After Advisor for Teams has created your Service management team, manage the team like any other team - including the ability to delete it.</span></span> <span data-ttu-id="05f44-196">请注意，如果不使用 Teams 管理中心删除该团队，系统将报告该团队存在。</span><span class="sxs-lookup"><span data-stu-id="05f44-196">Be aware that, if you don't delete the team by using the Teams admin center, it will be reported that the team exists.</span></span>

### <a name="can-i-add-or-remove-channels-in-the-deployment-team"></a><span data-ttu-id="05f44-197">我是否可以在部署团队中添加或删除频道？</span><span class="sxs-lookup"><span data-stu-id="05f44-197">Can I add or remove channels in the Service management team?</span></span>
<span data-ttu-id="05f44-198">可以，创建部署团队后，你将按照管理任何其他团队的方式管理频道。</span><span class="sxs-lookup"><span data-stu-id="05f44-198">Yes, once the Service management team has been created, you'll manage the channels the same way as any other team.</span></span>

### <a name="can-i-add-or-remove-project-team-members-in-the-deployment-team"></a><span data-ttu-id="05f44-199">我是否可以在部署团队中添加或删除项目团队成员？</span><span class="sxs-lookup"><span data-stu-id="05f44-199">Can I add or remove project team members in the Service management team?</span></span>
<span data-ttu-id="05f44-200">可以，创建部署团队后，你将按照管理任何其他团队的方式进行管理。</span><span class="sxs-lookup"><span data-stu-id="05f44-200">Yes, once the Service management team has been created, you'll manage it the same way as any other team.</span></span>

### <a name="can-i-modify-the-planner-plans"></a><span data-ttu-id="05f44-201">能否修改 Planner 计划？</span><span class="sxs-lookup"><span data-stu-id="05f44-201">Can I modify the Planner plans?</span></span>
<span data-ttu-id="05f44-202">可以，Advisor for Teams 创建部署团队后，你应更新 Planner 计划，使其可以为你的 Teams 推出提供最佳支持。</span><span class="sxs-lookup"><span data-stu-id="05f44-202">Yes, after Advisor for Teams has created your Service management team, you should update the Planner plan so it best supports your Teams rollout.</span></span> <span data-ttu-id="05f44-203">可以像任何其他 Planner 计划那样修改任何项 - 存储桶、任务和任务详细信息。</span><span class="sxs-lookup"><span data-stu-id="05f44-203">You can modify anything - buckets, tasks, task details - just like any other Planner plan.</span></span>


### <a name="can-i-modify-the-forms-survey"></a><span data-ttu-id="05f44-204">能否修改 Forms 调查？</span><span class="sxs-lookup"><span data-stu-id="05f44-204">Can I modify the Forms survey?</span></span>
<span data-ttu-id="05f44-205">可以，Advisor for Teams 创建部署团队后，可以按需修改 Forms 调查。</span><span class="sxs-lookup"><span data-stu-id="05f44-205">Yes, after Advisor for Teams has created your Service management team, you can modify the Forms survey as needed.</span></span>

### <a name="what-information-is-advisor-for-teams-collecting-about-my-organization"></a><span data-ttu-id="05f44-206">Advisor for Teams 会收集关于我的组织的什么信息？</span><span class="sxs-lookup"><span data-stu-id="05f44-206">What information is Advisor for Teams collecting about my organization?</span></span>
<span data-ttu-id="05f44-207">Advisor for Teams 请求你同意收集非 EUII（最终用户标识信息）。</span><span class="sxs-lookup"><span data-stu-id="05f44-207">Advisor for Teams requests your agreement to collecting non-EUII (end user identifying information).</span></span> <span data-ttu-id="05f44-208">收集的信息采用遥测的形式，用于向 Microsoft 提供有关 Advisor for Teams 在促进成功结果方面的作用以及需要改进之处的反馈。</span><span class="sxs-lookup"><span data-stu-id="05f44-208">The information that is collected is in the form of telemetry that provides feedback to Microsoft on how well Advisor for Teams is driving successful outcomes and where it may need to be improved.</span></span> <span data-ttu-id="05f44-209">此类数据用于帮助 Microsoft 识别与你的组织积极互动，从而为你的部署提供协助的机会。</span><span class="sxs-lookup"><span data-stu-id="05f44-209">This same data is used to identify opportunities for Microsoft to proactively engage with your organization in an effort to assist with your deployment.</span></span>

### <a name="can-i-use-advisor-for-teams-with-fasttrack"></a><span data-ttu-id="05f44-210">能否将 Advisor for Teams 与 FastTrack 配合使用？</span><span class="sxs-lookup"><span data-stu-id="05f44-210">Can I use Advisor for Teams with FastTrack?</span></span>
<span data-ttu-id="05f44-211">可以，针对希望部署 Teams 的所有客户，FastTrack 会利用 Advisor for Teams。</span><span class="sxs-lookup"><span data-stu-id="05f44-211">Yes, FastTrack leverages Advisor for Teams for all customers looking to deploy Teams.</span></span> <span data-ttu-id="05f44-212">他们可以使用 Advisor for Teams（如果需要）协助部署团队进行初始设置，并在 Teams 推出期间根据需要就特定主题提供支持。</span><span class="sxs-lookup"><span data-stu-id="05f44-212">They can assist with the initial setup of your Service management team using Advisor for Teams (if required) and also provide as-needed support on specific topics during your Teams rollout.</span></span>

### <a name="can-i-use-advisor-for-teams-with-a-partner"></a><span data-ttu-id="05f44-213">能否在与合作伙伴协作的过程中使用 Advisor for Teams？</span><span class="sxs-lookup"><span data-stu-id="05f44-213">Can I use Advisor for Teams with a partner?</span></span>
<span data-ttu-id="05f44-214">可以，在使用 Advisor for Teams 时，你也可以使用部署合作伙伴进行 Teams 部署。</span><span class="sxs-lookup"><span data-stu-id="05f44-214">Yes, you can use Advisor for Teams while also using a deployment partner for your Teams deployment.</span></span> <span data-ttu-id="05f44-215">如果你的合作伙伴是 CSP 并代表你管理租户，则他们可以使用 Advisor for Teams 来创建部署团队，并协助你执行整个项目。</span><span class="sxs-lookup"><span data-stu-id="05f44-215">If your partner is a CSP and manages your tenant on your behalf, they can use Advisor for Teams to create your Service management team and assist you with executing the overall project.</span></span> <span data-ttu-id="05f44-216">此外，你还可以通过将各合作伙伴添加到你的部署团队来与他们一起工作，从而让他们作为整个项目团队的成员参与进来。</span><span class="sxs-lookup"><span data-stu-id="05f44-216">Additionally, you can work with any partner by adding those individuals as guests in your Service management team, to allow them to participate as a member of the overall project team.</span></span>

### <a name="how-do-i-use-planner"></a><span data-ttu-id="05f44-217">如何使用 Planner？</span><span class="sxs-lookup"><span data-stu-id="05f44-217">How do I use Planner?</span></span>
<span data-ttu-id="05f44-218">查看 [Microsoft Planner 帮助](https://support.office.com/article/Microsoft-Planner-help-4a9a13c6-3adf-4a60-a6fc-15c0b15e16fc)和 [Planner 快速入门视频](https://support.office.com/article/microsoft-planner-video-training-4d71390f-08d8-4db0-84ea-92fb078687c7)。</span><span class="sxs-lookup"><span data-stu-id="05f44-218">Check out [Microsoft Planner help](https://support.office.com/article/Microsoft-Planner-help-4a9a13c6-3adf-4a60-a6fc-15c0b15e16fc) and the [Planner quick-start videos](https://support.office.com/article/microsoft-planner-video-training-4d71390f-08d8-4db0-84ea-92fb078687c7).</span></span> 

### <a name="how-do-i-use-forms"></a><span data-ttu-id="05f44-219">如何使用 Forms？</span><span class="sxs-lookup"><span data-stu-id="05f44-219">How do I use Forms?</span></span>
<span data-ttu-id="05f44-220">转到 [Forms 帮助中心](https://support.office.com/forms)。</span><span class="sxs-lookup"><span data-stu-id="05f44-220">Go to the [Forms help center](https://support.office.com/forms).</span></span>

## <a name="related-topics"></a><span data-ttu-id="05f44-221">相关主题</span><span class="sxs-lookup"><span data-stu-id="05f44-221">Related topics</span></span>

[<span data-ttu-id="05f44-222">如何部署 Teams</span><span class="sxs-lookup"><span data-stu-id="05f44-222">How to roll out Teams</span></span>](How-to-roll-out-teams.md)
