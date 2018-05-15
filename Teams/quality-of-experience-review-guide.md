---
title: 体验审阅指南的 Microsoft 团队的质量
author: rmw2890
ms.author: MyAdvisor
manager: lehewe
ms.date: 04/12/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: 使用呼叫质量仪表板 (CQD) 分析 Microsoft 团队的实时的媒体性能的指南。
localization_priority: Priority
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9d6e657316af2c4f861e68a0ffebc7e478f1234f
ms.sourcegitcommit: c63e7a8a746d427a1c886e8dca4d631c851e417c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2018
---
# <a name="quality-of-experience-review-guide"></a><span data-ttu-id="34f5a-103">查看用户体验指南的质量</span><span class="sxs-lookup"><span data-stu-id="34f5a-103">Quality of Experience Review Guide</span></span>

<span data-ttu-id="34f5a-104">本指南是有关 Microsoft 团队和业务 online Skype 的驱动器值阶段。</span><span class="sxs-lookup"><span data-stu-id="34f5a-104">This guide is about the Drive Value phase for Microsoft Teams and Skype for Business Online.</span></span> <span data-ttu-id="34f5a-105">您可以本指南[下载的 Word 版本](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/quality-of-experience-review-guide.docx?raw=true)。</span><span class="sxs-lookup"><span data-stu-id="34f5a-105">You can [download a Word version](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/quality-of-experience-review-guide.docx?raw=true) of this guide.</span></span>

## <a name="introduction"></a><span data-ttu-id="34f5a-106">简介</span><span class="sxs-lookup"><span data-stu-id="34f5a-106">Introduction</span></span>

<span data-ttu-id="34f5a-107">若要对在改善用户体验的影响大，组织需要实施的关键区域，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="34f5a-107">To have the greatest impact on improving the user experience, organizations need to operationalize the key areas that are shown in the following figure.</span></span>
<span data-ttu-id="34f5a-108">其他领域包括标识操作任务、 建立质量指标的目标、 有助于确定要用于评估组织成功指标和根据需要将缩小调查的区域。</span><span class="sxs-lookup"><span data-stu-id="34f5a-108">Additional areas include identifying operational tasks, establishing targets for quality metrics, ascertaining the metrics to use to gauge organizational success, and narrowing areas of investigation as needed.</span></span>

![关键区域的用户体验质量包括音频、 可靠性、 用户调查、 设备和客户端。](media/quality-of-experience-review-guide-image1.png)

<span data-ttu-id="34f5a-110">_图 1-覆盖在整个文档中的项操作区域_</span><span class="sxs-lookup"><span data-stu-id="34f5a-110">_Figure 1 - Key operational areas covered throughout this document_</span></span>

<span data-ttu-id="34f5a-111">通过不断地评估和补救本文所述的区域，您可以减少他们可能会产生负面影响的用户体验质量。</span><span class="sxs-lookup"><span data-stu-id="34f5a-111">By continually assessing and remediating the areas described in this document, you can reduce their potential to negatively affect the quality of your users’ experience.</span></span> <span data-ttu-id="34f5a-112">在部署中遇到的最多的用户体验问题可以分为以下类别：</span><span class="sxs-lookup"><span data-stu-id="34f5a-112">Most user-experience problems encountered in a deployment can be grouped into the following categories:</span></span>

-   <span data-ttu-id="34f5a-113">不完整的防火墙或代理配置</span><span class="sxs-lookup"><span data-stu-id="34f5a-113">Incomplete firewall or proxy configuration</span></span>

-   <span data-ttu-id="34f5a-114">质量欠佳 Wi-fi 覆盖范围</span><span class="sxs-lookup"><span data-stu-id="34f5a-114">Poor Wi-Fi coverage</span></span>

-   <span data-ttu-id="34f5a-115">带宽不足</span><span class="sxs-lookup"><span data-stu-id="34f5a-115">Insufficient bandwidth</span></span>

-   <span data-ttu-id="34f5a-116">VPN</span><span class="sxs-lookup"><span data-stu-id="34f5a-116">VPN</span></span>

-   <span data-ttu-id="34f5a-117">不一致或过期的客户端版本</span><span class="sxs-lookup"><span data-stu-id="34f5a-117">Inconsistent or outdated client versions</span></span>

-   <span data-ttu-id="34f5a-118">未优化或内置的音频设备</span><span class="sxs-lookup"><span data-stu-id="34f5a-118">Unoptimized or built-in audio devices</span></span>

-   <span data-ttu-id="34f5a-119">有问题的子网或网络设备</span><span class="sxs-lookup"><span data-stu-id="34f5a-119">Problematic subnets or network devices</span></span>

<span data-ttu-id="34f5a-120">通过适当的规划和设计业务 online 部署团队或 Skype 之前，您可以减少的需要保持高质量体验的工作量。</span><span class="sxs-lookup"><span data-stu-id="34f5a-120">Through proper planning and design before deploying Teams or Skype for Business Online, you can reduce the amount of effort that will be required to maintain high-quality experiences.</span></span>

<span data-ttu-id="34f5a-121">本指南重点介绍使用作为主要工具，呼叫质量仪表板 (CQD) 联机报告和调查每个区域，以最大限度地应用和影响的音频特殊重点。</span><span class="sxs-lookup"><span data-stu-id="34f5a-121">This guide focuses on using the Call Quality Dashboard (CQD) Online as the primary tool to report and investigate each area, with a special emphasis on audio to maximize adoption and impact.</span></span> <span data-ttu-id="34f5a-122">对网络以提高音频体验任何改进还直接将翻译视频和桌面共享的改进。</span><span class="sxs-lookup"><span data-stu-id="34f5a-122">Any improvements made to the network to improve the audio experience will also directly translate to improvements in video and desktop sharing.</span></span>

<span data-ttu-id="34f5a-123">若要加快您评估，提供两个 curated 的 CQD 模板： 其中一个管理所有网络和其他筛选出的托管仅 （内部） 网络。</span><span class="sxs-lookup"><span data-stu-id="34f5a-123">To accelerate your assessment, two curated CQD templates are provided: one for managing all networks and the other is filtered for managed (internal) networks only.</span></span> <span data-ttu-id="34f5a-124">虽然所有网络模板报告配置为显示构建和网络信息，但它仍可时您收集和上载构建信息的工作。</span><span class="sxs-lookup"><span data-stu-id="34f5a-124">Although the All Networks template reports are configured to display building and network information, it can still be used while you work toward collecting and uploading building information.</span></span> <span data-ttu-id="34f5a-125">上载构建到 CQD 信息使服务能够增强报告通过添加自定义构建、 网络和位置信息时发送者内部从外部子网。</span><span class="sxs-lookup"><span data-stu-id="34f5a-125">Uploading building information into CQD enables the service to enhance reporting by adding custom building, network, and location information while differentiating internal from external subnets.</span></span> <span data-ttu-id="34f5a-126">有关详细信息，请参阅本文档后面的[构建映射](#building-mapping)。</span><span class="sxs-lookup"><span data-stu-id="34f5a-126">For more information, see [Building mapping](#building-mapping) later in this document.</span></span>

### <a name="what-is-the-cqd"></a><span data-ttu-id="34f5a-127">什么是 CQD？</span><span class="sxs-lookup"><span data-stu-id="34f5a-127">What is the CQD?</span></span>

<span data-ttu-id="34f5a-128">呼叫质量仪表板 (CQD) 用于深入了解 Business services 使用团队和 Skype 进行的呼叫的质量。</span><span class="sxs-lookup"><span data-stu-id="34f5a-128">You use the Call Quality Dashboard (CQD) to gain insight into the quality of calls made by using Teams and Skype for Business services.</span></span> <span data-ttu-id="34f5a-129">CQD 旨在帮助 Skype 的业务和团队 admins 和网络工程师优化网络。</span><span class="sxs-lookup"><span data-stu-id="34f5a-129">CQD is designed to help Skype for Business and Teams admins and network engineers optimize the network.</span></span> <span data-ttu-id="34f5a-130">CQD 查看聚合信息为整个组织总体模式可以成为明显，允许人员进行的呼叫质量的明智的评估。</span><span class="sxs-lookup"><span data-stu-id="34f5a-130">CQD looks at aggregate information for an entire organization where overall patterns can become apparent, allowing staff to make informed assessments of call quality.</span></span> <span data-ttu-id="34f5a-131">CQD 提供呼叫指标，让您洞悉总体呼叫质量、 呼叫可靠性和用户体验的报告。</span><span class="sxs-lookup"><span data-stu-id="34f5a-131">CQD provides reports of call metrics that give you insight into overall call quality, call reliability, and user experience.</span></span>

> [!NOTE]
> <span data-ttu-id="34f5a-132">CQD 不包含任何个人身份信息 (PII)。</span><span class="sxs-lookup"><span data-stu-id="34f5a-132">CQD doesn’t contain any personally identifiable information (PII).</span></span> <span data-ttu-id="34f5a-133">PII 是可用自己或其他信息以确定、 联系人或找到某个人，或以识别个体在上下文中的信息。</span><span class="sxs-lookup"><span data-stu-id="34f5a-133">PII is information that can be used on its own or with other information to identify, contact, or locate a single person, or to identify an individual in context.</span></span> 

### <a name="intended-audience"></a><span data-ttu-id="34f5a-134">目标访问群体</span><span class="sxs-lookup"><span data-stu-id="34f5a-134">Intended audience</span></span>

<span data-ttu-id="34f5a-135">本文档旨在供合作伙伴和客户的利益干系人与角色如协作首席架构师、 顾问、 更改管理/采用专家、 支持/帮助台导致、 网络导致、 桌面潜在顾客和 IT 管理员。</span><span class="sxs-lookup"><span data-stu-id="34f5a-135">This document is intended to be used by partner and customer stakeholders with roles such as Collaboration Lead/Architect, Consultant, Change Management/Adoption Specialist, Support/Help Desk Lead, Network Lead, Desktop Lead, and IT Admin.</span></span>

<span data-ttu-id="34f5a-136">本文档旨在还使用指定的质量 champion(s)。</span><span class="sxs-lookup"><span data-stu-id="34f5a-136">This document is also intended to be used by the designated quality champion(s).</span></span>
<span data-ttu-id="34f5a-137">有关详细信息，请参阅[质量冠军角色](https://docs.microsoft.com/MicrosoftTeams/4-envision-plan-my-service-management#the-quality-champion-role)。</span><span class="sxs-lookup"><span data-stu-id="34f5a-137">For more information, see [the Quality Champion role](https://docs.microsoft.com/MicrosoftTeams/4-envision-plan-my-service-management#the-quality-champion-role).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="34f5a-138">先决条件</span><span class="sxs-lookup"><span data-stu-id="34f5a-138">Prerequisites</span></span>

<span data-ttu-id="34f5a-139">之前使用本指南，请确保您拥有适当租户[角色](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)分配，以便您可以访问 CQD。</span><span class="sxs-lookup"><span data-stu-id="34f5a-139">Before using this guide, make sure you have the proper tenant [roles](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d) assigned so that you can access CQD.</span></span>

-   <span data-ttu-id="34f5a-140">**Office 365 全局管理员角色：** 在您规划，包括 for Business 的 Skype 访问 Office 365 套件的服务中的所有管理功能。</span><span class="sxs-lookup"><span data-stu-id="34f5a-140">**Office 365 Global Administrator role:** Accesses all administrative features in the Office 365 suite of services in your plan, including Skype for Business.</span></span>

-   <span data-ttu-id="34f5a-141">**业务管理员角色的 Skype:** 为您的组织配置 for Business 的 Skype 并能够在 Office 365 管理中心查看所有[活动报告](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263)。</span><span class="sxs-lookup"><span data-stu-id="34f5a-141">**Skype for Business Administrator role:** Configures Skype for Business for your organization and is able to view all the [activity reports](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) in the Office 365 admin center.</span></span> <span data-ttu-id="34f5a-142">即使部署仅团队，则需要此角色。</span><span class="sxs-lookup"><span data-stu-id="34f5a-142">This role is required even if you deploy only Teams.</span></span>

<span data-ttu-id="34f5a-143">此外，您可以向 Office 365 用户帐户以允许访问报告功能仅分配下列角色。</span><span class="sxs-lookup"><span data-stu-id="34f5a-143">Alternatively, you can assign the following role to an Office 365 user account to allow access to reporting features only.</span></span>

-   <span data-ttu-id="34f5a-144">**报告读取器：** 可以在 Office 365 管理中心，任何从[Office 365 应用内容包](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f)，报告和 CQD 报告中查看[活动报告](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263)。</span><span class="sxs-lookup"><span data-stu-id="34f5a-144">**Reports Reader:** Can view all the [activity reports](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) in the Office 365 admin center, any reports from the [Office 365 Adoption content pack](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f), and CQD reports.</span></span>

<span data-ttu-id="34f5a-145">了解 CQD 的关键概念帮助最大化可以改进业务 online 与团队或 Skype 的用户体验的影响。</span><span class="sxs-lookup"><span data-stu-id="34f5a-145">Understanding the key concepts of CQD helps maximize the impact you can make in improving your users’ experience with Teams or Skype for Business Online.</span></span>
<span data-ttu-id="34f5a-146">[附录](#other-resources)中找不到其他资源。</span><span class="sxs-lookup"><span data-stu-id="34f5a-146">Additional resources can be found in the [Appendix](#other-resources).</span></span>

## <a name="what-is-quality"></a><span data-ttu-id="34f5a-147">什么是质量？</span><span class="sxs-lookup"><span data-stu-id="34f5a-147">What is quality?</span></span>

<span data-ttu-id="34f5a-148">在讨论团队和 Skype for Business 中的质量，务必定义要实现常见了解的术语。</span><span class="sxs-lookup"><span data-stu-id="34f5a-148">When discussing quality in Teams and Skype for Business, it’s important to define the term to achieve a common understanding.</span></span> <span data-ttu-id="34f5a-149">此处定义质量，是服务指标和用户体验的组合。</span><span class="sxs-lookup"><span data-stu-id="34f5a-149">Quality, as defined here, is a combination of service metrics and user experience.</span></span>

![服务指标组成的质量欠佳的呼叫比率、 可靠性、 终结点/设备和客户端版本。](media/quality-of-experience-review-guide-image2.png)

<span data-ttu-id="34f5a-152">_图 2-质量是什么？_</span><span class="sxs-lookup"><span data-stu-id="34f5a-152">_Figure 2 - What is quality?_</span></span>

### <a name="define-your-target-metrics"></a><span data-ttu-id="34f5a-153">定义您的目标指标</span><span class="sxs-lookup"><span data-stu-id="34f5a-153">Define your target metrics</span></span>

<span data-ttu-id="34f5a-154">本节讨论我们使用评估如何服务遇到运行状况的核心服务指标。</span><span class="sxs-lookup"><span data-stu-id="34f5a-154">This section discusses the core service metrics that we use to assess how services experience health.</span></span> <span data-ttu-id="34f5a-155">通过不断地评估和驱动努力保留目标下面这些指标，您将帮助确保您的用户体验一致、 可靠地呼叫质量。</span><span class="sxs-lookup"><span data-stu-id="34f5a-155">By continually assessing and driving efforts to keep these metrics below target, you’ll help ensure your users experience consistent, reliable call quality.</span></span> <span data-ttu-id="34f5a-156">为了帮助您入门，提供了以下目标。</span><span class="sxs-lookup"><span data-stu-id="34f5a-156">To get you started, the following targets are provided.</span></span>
<span data-ttu-id="34f5a-157">让我们简要介绍托管和非托管网络之间的差异：</span><span class="sxs-lookup"><span data-stu-id="34f5a-157">Let’s briefly cover the difference between a managed and unmanaged network:</span></span>

-   <span data-ttu-id="34f5a-158">*管理*网络可以影响，并由组织控制。</span><span class="sxs-lookup"><span data-stu-id="34f5a-158">A *managed* network can be influenced and controlled by the organization.</span></span>
    <span data-ttu-id="34f5a-159">这包括内部 LAN、 远程 WAN 和 VPN。</span><span class="sxs-lookup"><span data-stu-id="34f5a-159">This includes the internal LAN, the remote WAN, and VPN.</span></span>

-   <span data-ttu-id="34f5a-160">*非托管*网络无法影响，或由组织控制。</span><span class="sxs-lookup"><span data-stu-id="34f5a-160">An *unmanaged* network can’t be influenced or controlled by the organization.</span></span> <span data-ttu-id="34f5a-161">非托管网络的示例是一个旅馆或机场网络。</span><span class="sxs-lookup"><span data-stu-id="34f5a-161">An example of an unmanaged network is a hotel or airport network.</span></span>

<span data-ttu-id="34f5a-162">_表 1-核心目标运行状况评估指标_</span><span class="sxs-lookup"><span data-stu-id="34f5a-162">_Table 1 - Core target health assessment metrics_</span></span>

|               | <span data-ttu-id="34f5a-163">托管网络质量</span><span class="sxs-lookup"><span data-stu-id="34f5a-163">Quality for managed networks</span></span> | <span data-ttu-id="34f5a-164">对于托管网络可靠性</span><span class="sxs-lookup"><span data-stu-id="34f5a-164">Reliability for managed networks</span></span> |                      |
|---------------|------------------------------|----------------------------------|----------------------|
| <span data-ttu-id="34f5a-165">度量名称</span><span class="sxs-lookup"><span data-stu-id="34f5a-165">Metric name</span></span>   | <span data-ttu-id="34f5a-166">音频质量欠佳的呼叫比率 %</span><span class="sxs-lookup"><span data-stu-id="34f5a-166">Audio Poor Call Ratio %</span></span>      | <span data-ttu-id="34f5a-167">调用安装失败百分比</span><span class="sxs-lookup"><span data-stu-id="34f5a-167">Call Setup Failures %</span></span>            | <span data-ttu-id="34f5a-168">调用投递失败百分比</span><span class="sxs-lookup"><span data-stu-id="34f5a-168">Call Drop Failures %</span></span> |
| <span data-ttu-id="34f5a-169">示例目标</span><span class="sxs-lookup"><span data-stu-id="34f5a-169">Sample target</span></span> | <span data-ttu-id="34f5a-170">\<3%</span><span class="sxs-lookup"><span data-stu-id="34f5a-170">\<3%</span></span>                         | <span data-ttu-id="34f5a-171">\<%1</span><span class="sxs-lookup"><span data-stu-id="34f5a-171">\<1%</span></span>                             | <span data-ttu-id="34f5a-172">\<4%</span><span class="sxs-lookup"><span data-stu-id="34f5a-172">\<4%</span></span>                 |

<span data-ttu-id="34f5a-173">非常重要讨论和定义组织的目标，以满足业务目标。</span><span class="sxs-lookup"><span data-stu-id="34f5a-173">It’s important to discuss and define your organization’s targets to meet your business objectives.</span></span> <span data-ttu-id="34f5a-174">理想情况下，应确定之前部署这些目标。</span><span class="sxs-lookup"><span data-stu-id="34f5a-174">Ideally, you should identify these targets prior to deployment.</span></span>

#### <a name="audio-pcr-"></a><span data-ttu-id="34f5a-175">音频 PCR %</span><span class="sxs-lookup"><span data-stu-id="34f5a-175">Audio PCR %</span></span> 

<span data-ttu-id="34f5a-176">音频质量欠佳呼叫比率 (PCR) 表示呼叫的音频质量不佳的组织的总体的百分比。</span><span class="sxs-lookup"><span data-stu-id="34f5a-176">Audio Poor Call Ratio (PCR) represents the organization’s overall percentage of calls that have poor audio quality.</span></span> <span data-ttu-id="34f5a-177">此指标旨在突出显示您的组织可以对努力向降低此值和改善用户体验，这是原因托管的网络是主要焦点时查看 PCR 最强大的影响精力处理的区域。</span><span class="sxs-lookup"><span data-stu-id="34f5a-177">This metric is meant to highlight areas where your organization can concentrate effort to have the strongest impact toward reducing this value and improving the user experience, which is why managed networks are the primary focus when looking at PCR.</span></span> <span data-ttu-id="34f5a-178">外部用户是很重要，但调查不同组织和用户的基于。</span><span class="sxs-lookup"><span data-stu-id="34f5a-178">External users are important too, but investigations differs on an organizational and user basis.</span></span>
<span data-ttu-id="34f5a-179">请考虑为外部用户提供最佳实践，并查看独立于整个组织的外部呼叫。</span><span class="sxs-lookup"><span data-stu-id="34f5a-179">Consider providing best practices for external users, and look at external calls independently from the overall organization.</span></span>

#### <a name="call-setup-failures-"></a><span data-ttu-id="34f5a-180">调用安装失败百分比</span><span class="sxs-lookup"><span data-stu-id="34f5a-180">Call Setup Failures %</span></span> 

<span data-ttu-id="34f5a-181">这表示无法建立任何媒体会话。</span><span class="sxs-lookup"><span data-stu-id="34f5a-181">This represents any media session that couldn’t be established.</span></span> <span data-ttu-id="34f5a-182">给定此处测量的用户体验的影响的严重性，旨在降低此值为零尽可能接近。</span><span class="sxs-lookup"><span data-stu-id="34f5a-182">Given the severity of the impact on the user experience measured here, the goal is to reduce this value to as close to zero as possible.</span></span> <span data-ttu-id="34f5a-183">此度量值高是在新部署中使用完整的防火墙规则更常见比成熟的部署，但仍，务必观看定期。</span><span class="sxs-lookup"><span data-stu-id="34f5a-183">A high value for this metric is more common in new deployments with incomplete firewall rules than a mature deployment, but it’s still important to watch on a regular basis.</span></span> <span data-ttu-id="34f5a-184">随着您操作严格逐渐成熟，那么您可以展开包含视频和桌面共享的工作负荷此指标。</span><span class="sxs-lookup"><span data-stu-id="34f5a-184">As your operational rigor matures, you can expand this metric to include video and desktop-sharing workloads.</span></span>

#### <a name="call-drop-failures-"></a><span data-ttu-id="34f5a-185">调用投递失败百分比</span><span class="sxs-lookup"><span data-stu-id="34f5a-185">Call Drop Failures %</span></span> 

<span data-ttu-id="34f5a-186">这适用于会话意外终止音频工作负荷。</span><span class="sxs-lookup"><span data-stu-id="34f5a-186">This applies to an audio workload where the session terminated unexpectedly.</span></span> <span data-ttu-id="34f5a-187">随着您操作严格逐渐成熟，那么您可以展开包含视频和桌面共享的工作负荷此指标。</span><span class="sxs-lookup"><span data-stu-id="34f5a-187">As your operational rigor matures, you can expand this metric to include video and desktop-sharing workloads.</span></span>

### <a name="service-metrics"></a><span data-ttu-id="34f5a-188">服务指标</span><span class="sxs-lookup"><span data-stu-id="34f5a-188">Service metrics</span></span>

<span data-ttu-id="34f5a-189">服务公制目标包含基于客户端的特定指标。</span><span class="sxs-lookup"><span data-stu-id="34f5a-189">Service metric targets consist of specific client-based metrics.</span></span>

#### <a name="pcr"></a><span data-ttu-id="34f5a-190">PCR</span><span class="sxs-lookup"><span data-stu-id="34f5a-190">PCR</span></span>

<span data-ttu-id="34f5a-191">用于确定是否将呼叫归类为质量欠佳的基础是使用质量欠佳的呼叫比率 (PCR)。</span><span class="sxs-lookup"><span data-stu-id="34f5a-191">The basis for determining whether a call is classified as poor is by using the poor call ratio (PCR).</span></span> <span data-ttu-id="34f5a-192">PCR 组成下表中所述的五个网络指标。</span><span class="sxs-lookup"><span data-stu-id="34f5a-192">PCR is made up of the five network metrics described in the following table.</span></span> <span data-ttu-id="34f5a-193">对于分类为质量欠佳的调用，只有一个指标需要超过定义的阈值。</span><span class="sxs-lookup"><span data-stu-id="34f5a-193">For a call to be classified as poor, only one metric needs to exceed the defined threshold.</span></span> <span data-ttu-id="34f5a-194">有关呼叫分类过程的详细信息，请参阅[本博客张贴内容](https://blogs.technet.microsoft.com/jenstr/2013/09/20/what-is-the-basis-for-classifying-a-call-as-poor-in-lync-2013-qoe/)。</span><span class="sxs-lookup"><span data-stu-id="34f5a-194">For more information about the call classification process, see [this blog post](https://blogs.technet.microsoft.com/jenstr/2013/09/20/what-is-the-basis-for-classifying-a-call-as-poor-in-lync-2013-qoe/).</span></span>

<span data-ttu-id="34f5a-195">_表 2-质量欠佳的呼叫服务指标_</span><span class="sxs-lookup"><span data-stu-id="34f5a-195">_Table 2 - Poor Call Service Metrics_</span></span>

| <span data-ttu-id="34f5a-196">指标</span><span class="sxs-lookup"><span data-stu-id="34f5a-196">Metric</span></span>                                           | <span data-ttu-id="34f5a-197">说明</span><span class="sxs-lookup"><span data-stu-id="34f5a-197">Description</span></span>                                                                                                                                                                                                                                                                                                                                                                  | <span data-ttu-id="34f5a-198">用户体验</span><span class="sxs-lookup"><span data-stu-id="34f5a-198">User experience</span></span>                                                                                                                                                          |
|--------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="34f5a-199">抖动\>30 ms</span><span class="sxs-lookup"><span data-stu-id="34f5a-199">Jitter \>30 ms</span></span>                                   | <span data-ttu-id="34f5a-200">这是连续的数据包之间的延迟的平均更改。</span><span class="sxs-lookup"><span data-stu-id="34f5a-200">This is the average change in delay between successive packets.</span></span> <span data-ttu-id="34f5a-201">工作组和 for Business 的 Skype 可以适应通过缓冲抖动某些级别。</span><span class="sxs-lookup"><span data-stu-id="34f5a-201">Teams and Skype for Business can adapt to some levels of jitter through buffering.</span></span> <span data-ttu-id="34f5a-202">则只有当抖动超过缓冲参与者通知的抖动效果。</span><span class="sxs-lookup"><span data-stu-id="34f5a-202">It’s only when the jitter exceeds the buffering that a participant notices the effects of jitter.</span></span>                                                                                                                         | <span data-ttu-id="34f5a-203">到达不同的速度数据包会导致演讲者语音声自动。</span><span class="sxs-lookup"><span data-stu-id="34f5a-203">The packets arriving at different speeds cause a speaker’s voice to sound robotic.</span></span>                                                                                       |
| <span data-ttu-id="34f5a-204">数据包丢失率\>10%或 0.1</span><span class="sxs-lookup"><span data-stu-id="34f5a-204">Packet loss rate \>10% or 0.1</span></span>                    | <span data-ttu-id="34f5a-205">这通常被指的数据包丢失的百分比。</span><span class="sxs-lookup"><span data-stu-id="34f5a-205">This is often defined as a percentage of packets that are lost.</span></span> <span data-ttu-id="34f5a-206">数据包丢失直接影响音频质量 — 从小，个人丢失数据包背对背脉冲损失几乎没有任何影响的原因音频，完全去掉。</span><span class="sxs-lookup"><span data-stu-id="34f5a-206">Packet loss directly affects audio quality—from small, individual lost packets that have almost no impact to back-to-back burst losses that cause audio to cut out completely.</span></span>                                                                                                                               | <span data-ttu-id="34f5a-207">在其预期目标被丢弃和未到达数据包会导致出现间隙媒体、 错过的音节和词中生成和断断续续视频和共享。</span><span class="sxs-lookup"><span data-stu-id="34f5a-207">The packets being dropped and not arriving at their intended destination cause gaps in the media, resulting in missed syllables and words, and choppy video and sharing.</span></span> |
| <span data-ttu-id="34f5a-208">往返时间\>500 ms</span><span class="sxs-lookup"><span data-stu-id="34f5a-208">Round-trip time \>500 ms</span></span>                         | <span data-ttu-id="34f5a-209">这是时间获取 IP 数据包从点 A，B 点和回点 a。此网络传播延迟限制到物理距离的两个点和轻量的速度，并包括执行的各种设备中的网络路径的额外开销。</span><span class="sxs-lookup"><span data-stu-id="34f5a-209">This is the time it takes to get an IP packet from point A to point B and back to point A. This network propagation delay is tied to the physical distance between the two points and the speed of light and includes additional overhead taken by the various devices in the network path.</span></span>                                                                                  | <span data-ttu-id="34f5a-210">时间过长到达其目标数据包会导致 walkie-talkie 效果。</span><span class="sxs-lookup"><span data-stu-id="34f5a-210">The packets taking too long to arrive at their destination cause a walkie-talkie effect.</span></span>                                                                                 |
| <span data-ttu-id="34f5a-211">NMOS 性能降低平均\>1.0</span><span class="sxs-lookup"><span data-stu-id="34f5a-211">NMOS degradation average \> 1.0</span></span>                  | <span data-ttu-id="34f5a-212">一个或多个这些网络指标，尽管单独或者没有不佳、 一起导致网络[意味着平均意见得分](https://technet.microsoft.com/library/bb894481(v=office.12).aspx)(NMOS) 要删除多个点。</span><span class="sxs-lookup"><span data-stu-id="34f5a-212">One or more of these network metrics, although individually weren’t poor, together caused the Network [Mean Opinion Score](https://technet.microsoft.com/library/bb894481(v=office.12).aspx) (NMOS) to drop by more than one point.</span></span> <span data-ttu-id="34f5a-213">这并不一定意味着网络连接不佳，但质量已减少了呼叫期间发生足够问题。</span><span class="sxs-lookup"><span data-stu-id="34f5a-213">This doesn’t necessarily mean the network connection is poor, but enough issues occurred during the call that quality was reduced.</span></span> | <span data-ttu-id="34f5a-214">这是抖动数据包丢失的组合和 — 在较小者一定程度上 — 增加的往返时间。</span><span class="sxs-lookup"><span data-stu-id="34f5a-214">This is a combination of jitter, packet loss, and—to a lesser degree—increased round-trip time.</span></span> <span data-ttu-id="34f5a-215">用户可能遇到以下症状的组合。</span><span class="sxs-lookup"><span data-stu-id="34f5a-215">The user might be experiencing a combination of these symptoms.</span></span>          |
| <span data-ttu-id="34f5a-216">隐藏样本数的平均比率\>7%或 0.07</span><span class="sxs-lookup"><span data-stu-id="34f5a-216">Average ratio of concealed samples \> 7% or 0.07</span></span> | <span data-ttu-id="34f5a-217">一个或多个这些网络指标，尽管单独或者没有不佳，导致媒体的自我康复到客户端。</span><span class="sxs-lookup"><span data-stu-id="34f5a-217">One or more of these network metrics, although individually weren’t poor, caused the client to self-heal the media.</span></span> <span data-ttu-id="34f5a-218">隐藏的音频示例是一种用于平滑通常将由丢弃的网络数据包突然转换技术。</span><span class="sxs-lookup"><span data-stu-id="34f5a-218">A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.</span></span>                                                                                                                | <span data-ttu-id="34f5a-219">高值指示丢失隐蔽的重要级别已应用，且导致音频失真或丢失。</span><span class="sxs-lookup"><span data-stu-id="34f5a-219">High values indicate that significant levels of loss concealment were applied, and resulted in distorted or lost audio.</span></span>                                                  |

#### <a name="client-and-device-readiness"></a><span data-ttu-id="34f5a-220">客户端和设备的准备情况</span><span class="sxs-lookup"><span data-stu-id="34f5a-220">Client and device readiness</span></span>

<span data-ttu-id="34f5a-221">您需要的实体的客户端和设备策略，以确保您的用户具有一致和良好的用户体验。</span><span class="sxs-lookup"><span data-stu-id="34f5a-221">You need a solid client and device strategy to ensure that your users have a consistent and positive user experience.</span></span> <span data-ttu-id="34f5a-222">几项主要原则驱动器每个准备策略。</span><span class="sxs-lookup"><span data-stu-id="34f5a-222">A few key principles drive each readiness strategy.</span></span>

##### <a name="client-readiness"></a><span data-ttu-id="34f5a-223">客户端准备</span><span class="sxs-lookup"><span data-stu-id="34f5a-223">Client readiness</span></span>

<span data-ttu-id="34f5a-224">强的客户端准备策略可确保您的用户，同时可享受最佳体验可能运行客户端的最新版本。</span><span class="sxs-lookup"><span data-stu-id="34f5a-224">A strong client readiness strategy ensures that your users are running the most recent version of the client while enjoying the best experience possible.</span></span>
<span data-ttu-id="34f5a-225">Microsoft 定期修补程序业务客户端; Skype确保您保存它最新环境中对您的总体成功至关重要。</span><span class="sxs-lookup"><span data-stu-id="34f5a-225">Microsoft routinely patches the Skype for Business client; ensuring that you keep it up to date in your environment is vital to your overall success.</span></span>

<span data-ttu-id="34f5a-226">我们建议您不让您落后按超过六个月的客户端版本。</span><span class="sxs-lookup"><span data-stu-id="34f5a-226">We recommend that you not let your client versions fall behind by more than six months.</span></span> <span data-ttu-id="34f5a-227">如果您使用的 Office 即单击，您正在已被保持最新的服务。</span><span class="sxs-lookup"><span data-stu-id="34f5a-227">If you’re using Office Click-to-Run, you’re already being kept up to date by the service.</span></span> <span data-ttu-id="34f5a-228">更高版本中本指南中，所述使用包含的[客户端报告](#determine-client-versions)，以帮助您完成此过程。</span><span class="sxs-lookup"><span data-stu-id="34f5a-228">Use the included [Client Report](#determine-client-versions), as described later in this guide, to assist you with this process.</span></span> <span data-ttu-id="34f5a-229">您还可以利用速率我呼叫示例报表，若要进一步增强您的客户端准备策略。</span><span class="sxs-lookup"><span data-stu-id="34f5a-229">You can also leverage the Rate My Call sample reports to further enhance your client readiness strategy.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="34f5a-230">目前，分发并自动更新通过 Azure 内容交付网络团队客户端和将保持最新的服务。</span><span class="sxs-lookup"><span data-stu-id="34f5a-230">Currently, Teams clients are distributed and updated automatically through the Azure Content Delivery Network and will be kept up to date by the service.</span></span> <span data-ttu-id="34f5a-231">客户端准备和调查活动不适用于团队。</span><span class="sxs-lookup"><span data-stu-id="34f5a-231">Client readiness and investigative activities aren’t applicable to Teams.</span></span>


##### <a name="device-readiness"></a><span data-ttu-id="34f5a-232">设备就绪</span><span class="sxs-lookup"><span data-stu-id="34f5a-232">Device readiness</span></span>

<span data-ttu-id="34f5a-233">任何一种单个策略会不影响您的设备准备策略以上的用户体验。</span><span class="sxs-lookup"><span data-stu-id="34f5a-233">No one single strategy can affect the user experience more than your device readiness strategy.</span></span> <span data-ttu-id="34f5a-234">大多数组织而言非常高兴不必要的设备中删除用户 （例如，桌面电话或其他专用的音频设备），这通常是切换到团队或 Skype for Business 的核心业务理由。</span><span class="sxs-lookup"><span data-stu-id="34f5a-234">Most organizations are happy to remove unnecessary devices from users (for example, desk phones or other dedicated audio devices), and this is often a core business justification for switching to Teams or Skype for Business.</span></span> <span data-ttu-id="34f5a-235">但是，这些相同的组织有时不愿意再提供替换设备，即使这些设备成本较低。</span><span class="sxs-lookup"><span data-stu-id="34f5a-235">However, those same organizations sometimes hesitate to provide replacement devices, even if those devices are less expensive.</span></span> <span data-ttu-id="34f5a-236">现代便携式计算机和 Pc，上述配有内置麦克风和扬声器，不进行了优化业务类语音 ip 电话 (VoIP)。</span><span class="sxs-lookup"><span data-stu-id="34f5a-236">Modern-day laptops and PCs, though equipped with built-in microphone and speaker, aren’t optimized for business-class voice over IP (VoIP).</span></span> <span data-ttu-id="34f5a-237">这通常将创建不好的体验所有参与者，尤其是扬声器处于噪音环境。</span><span class="sxs-lookup"><span data-stu-id="34f5a-237">This often creates a poor experience for all participants, especially if the speaker is in a noisy environment.</span></span> <span data-ttu-id="34f5a-238">Microsoft 的设备认证计划可确保用户参与通过使用任何设备的团队或 for Business 的 Skype 认证的电话呼叫，它生成优于非认证的设备的体验。</span><span class="sxs-lookup"><span data-stu-id="34f5a-238">Microsoft’s device certification program ensures that when a user participates in a phone call by using any device certified for Teams or Skype for Business, it produces an experience that’s superior to a non-certified device.</span></span>

<span data-ttu-id="34f5a-239">我们始终建议团队和业务用户的 Skype 使用认证的耳麦或扬声器时使用桌面客户端参与语音呼叫。</span><span class="sxs-lookup"><span data-stu-id="34f5a-239">We always recommend that Teams and Skype for Business users use a certified headset or speaker when participating in a voice call by using a desktop client.</span></span>
<span data-ttu-id="34f5a-240">有关 Microsoft 认证设备的详细信息，请查看此[电话和限定的设备有关的文章](https://technet.microsoft.com/office/dn788944.aspx)。</span><span class="sxs-lookup"><span data-stu-id="34f5a-240">For more information about Microsoft certified devices, review this [article about phones and qualified devices](https://technet.microsoft.com/office/dn788944.aspx).</span></span> <span data-ttu-id="34f5a-241">[设备报告](#devices-investigations)，后面本指南中，用于帮助管理您的设备。</span><span class="sxs-lookup"><span data-stu-id="34f5a-241">Use the [Device Report](#devices-investigations), later in this guide, for assistance with managing your devices.</span></span> <span data-ttu-id="34f5a-242">您可以使用速率我呼叫示例报告若要进一步增强您的设备准备策略。</span><span class="sxs-lookup"><span data-stu-id="34f5a-242">You can also use the Rate My Call sample reports to further enhance your device readiness strategy.</span></span>

### <a name="user-experience"></a><span data-ttu-id="34f5a-243">用户体验</span><span class="sxs-lookup"><span data-stu-id="34f5a-243">User experience</span></span>

<span data-ttu-id="34f5a-244">分析的用户体验比科学的多个图片，因为此处收集指标不始终意味着没有网络或服务的问题，但相反，及其指示用户可以体验问题。</span><span class="sxs-lookup"><span data-stu-id="34f5a-244">Analyzing the user experience is more art than science, because the metrics gathered here don’t always mean that there’s a problem with the network or service but rather, they indicate that the user perceives a problem.</span></span> <span data-ttu-id="34f5a-245">Microsoft 提供的内置调查机制 — 已知作为速率我呼叫 (RMC) — 为了衡量整体用户体验。</span><span class="sxs-lookup"><span data-stu-id="34f5a-245">Microsoft offers a built-in survey mechanism—known as Rate My Call (RMC)—to help gauge overall user experience.</span></span> <span data-ttu-id="34f5a-246">RMC 将帮助您回答从用户的角度来看以下问题：</span><span class="sxs-lookup"><span data-stu-id="34f5a-246">RMC will help you answer the following questions from your users’ perspective:</span></span>

-   <span data-ttu-id="34f5a-247">是否知道如何使用解决方案？</span><span class="sxs-lookup"><span data-stu-id="34f5a-247">Do I know how to use the solution?</span></span>

-   <span data-ttu-id="34f5a-248">是解决方案易于使用且直观，并不支持我的日常通信需求？</span><span class="sxs-lookup"><span data-stu-id="34f5a-248">Is the solution easy to use and intuitive, and does it support my day-to-day communication needs?</span></span>

-   <span data-ttu-id="34f5a-249">解决方案帮助我完成工作？</span><span class="sxs-lookup"><span data-stu-id="34f5a-249">Does the solution help me get my job done?</span></span>

-   <span data-ttu-id="34f5a-250">我的解决方案的整体认知是什么？</span><span class="sxs-lookup"><span data-stu-id="34f5a-250">What’s my overall perception of the solution?</span></span>

-   <span data-ttu-id="34f5a-251">可以使用解决方案的任意位置的时间，无论我的位置？</span><span class="sxs-lookup"><span data-stu-id="34f5a-251">Can I use the solution at any point in time, regardless of where I am?</span></span>

-   <span data-ttu-id="34f5a-252">可设置和维护呼叫？</span><span class="sxs-lookup"><span data-stu-id="34f5a-252">Can I set up and maintain a call?</span></span>

#### <a name="rmc"></a><span data-ttu-id="34f5a-253">RMC</span><span class="sxs-lookup"><span data-stu-id="34f5a-253">RMC</span></span>

<span data-ttu-id="34f5a-254">RMC 内置团队和 Skype for Business 和自动配置为一个在每个 10 呼叫或的所有呼叫的 10%之后显示。</span><span class="sxs-lookup"><span data-stu-id="34f5a-254">RMC is built into Teams and Skype for Business and is automatically configured to be displayed after one in every 10 calls, or 10 percent of all calls.</span></span> <span data-ttu-id="34f5a-255">此简短调查询问用户评价呼叫，并提供了为什么呼叫质量可能已不佳的很少的上下文。</span><span class="sxs-lookup"><span data-stu-id="34f5a-255">This brief survey asks the user to rate the call and provide a little context for why the call quality might have been poor.</span></span> <span data-ttu-id="34f5a-256">一个或两个评级被视为不佳、 三个到四个很好，并且五非常出色。</span><span class="sxs-lookup"><span data-stu-id="34f5a-256">A one or two rating is considered poor, three to four is good, and five is excellent.</span></span> <span data-ttu-id="34f5a-257">虽然有点滞后而指示器，这是错过服务指标可以的发现问题非常有用的指标。</span><span class="sxs-lookup"><span data-stu-id="34f5a-257">Although it’s somewhat of a lagging indicator, this is a useful metric for uncovering issues that service metrics can miss.</span></span>

> [!NOTE]
> <span data-ttu-id="34f5a-258">指示用户可以通过很好授予对 RMC 调查响应之前，响应除了反馈通常回来为极其负值。</span><span class="sxs-lookup"><span data-stu-id="34f5a-258">Until users are instructed to respond to RMC surveys by giving good feedback in addition to bad, responses typically come back as overwhelmingly negative.</span></span> <span data-ttu-id="34f5a-259">大多数用户才响应时呼叫质量较差。</span><span class="sxs-lookup"><span data-stu-id="34f5a-259">Most users only respond when call quality is poor.</span></span> <span data-ttu-id="34f5a-260">因此，RMC 报告可能出现偏态不佳的一侧即使服务指标正常工作。</span><span class="sxs-lookup"><span data-stu-id="34f5a-260">Because of this, your RMC reports might be skewed to the poor side even while service metrics are good.</span></span> 


<span data-ttu-id="34f5a-261">您可以使用 CQD RMC 用户响应报告和 CQD 模板中包括示例报告。</span><span class="sxs-lookup"><span data-stu-id="34f5a-261">You can use CQD to report on RMC user responses, and sample reports are included in the CQD template.</span></span> <span data-ttu-id="34f5a-262">但是，他们不讨论在本指南的详细信息。</span><span class="sxs-lookup"><span data-stu-id="34f5a-262">However, they aren’t discussed in detail in this guide.</span></span> <span data-ttu-id="34f5a-263">有关 RMC Skype 业务 online 中的详细信息和指导用户授予有用 RMC 响应的指南，请参阅此[博客文章](https://blogs.technet.microsoft.com/jenstr/2015/05/05/rate-my-call-in-skype-for-business-2015/)。</span><span class="sxs-lookup"><span data-stu-id="34f5a-263">For more information about RMC in Skype for Business Online and guidance for educating users to give useful RMC responses, see this [blog post](https://blogs.technet.microsoft.com/jenstr/2015/05/05/rate-my-call-in-skype-for-business-2015/).</span></span>

### <a name="categories-of-quality"></a><span data-ttu-id="34f5a-264">类别的质量</span><span class="sxs-lookup"><span data-stu-id="34f5a-264">Categories of quality</span></span>

<span data-ttu-id="34f5a-265">留给高质量和可靠部署成功与否取决于您构建操作严格程度。</span><span class="sxs-lookup"><span data-stu-id="34f5a-265">The success of operationalizing a high-quality and reliable deployment depends on your building operational rigor.</span></span> <span data-ttu-id="34f5a-266">具体而言，特别注意图; 中所示的三个类别下面是本指南的焦点：</span><span class="sxs-lookup"><span data-stu-id="34f5a-266">Specifically, pay special attention to the three categories illustrated in the following figure; these are the focus of this guide:</span></span>

-   <span data-ttu-id="34f5a-267">**网络：** 音频质量重点 PCR 指标、 TCP 使用率、 有线和无线子网，并确定使用 HTTP 代理和 VPN。</span><span class="sxs-lookup"><span data-stu-id="34f5a-267">**Network:** Audio quality focused on the PCR metric, TCP usage, wired and wireless subnets, and identifying the use of HTTP proxies and VPN.</span></span>

-   <span data-ttu-id="34f5a-268">**终结点：** 音频设备和客户端版本 (Skype for Business 仅)。</span><span class="sxs-lookup"><span data-stu-id="34f5a-268">**Endpoints:** Audio devices and client version (Skype for Business only).</span></span>

-   <span data-ttu-id="34f5a-269">**服务管理：** 此类别包括两个部分：</span><span class="sxs-lookup"><span data-stu-id="34f5a-269">**Service Management:** This category comprises two sections:</span></span>

    -   <span data-ttu-id="34f5a-270">首先是 Microsoft 的责任管理和维护的团队和 Skype 的业务联机服务。</span><span class="sxs-lookup"><span data-stu-id="34f5a-270">First is Microsoft’s responsibility to manage and maintain the Teams and Skype for Business Online services.</span></span>

    -   <span data-ttu-id="34f5a-271">第二个必须管理您的组织，以确保可靠地访问该服务，如更新构建信息和维护防火墙新的 Office 365 IP 地址，如基础结构添加到服务的任务。</span><span class="sxs-lookup"><span data-stu-id="34f5a-271">Second are tasks your organization must manage to ensure reliable access to the service, such as updating building information and maintaining firewalls for new Office 365 IP addresses as infrastructure is added to the service.</span></span>

![Qualilty 组织中的类别： 服务管理、 终结点，以及网络。](media/quality-of-experience-review-guide-image3.png)

<span data-ttu-id="34f5a-273">_图 3-关键类别个团队和 Skype 业务 Online 部署_</span><span class="sxs-lookup"><span data-stu-id="34f5a-273">_Figure 3 - Critical categories for Teams and Skype for Business Online deployment_</span></span>

<span data-ttu-id="34f5a-274">下图概述每个类别必须执行的任务。</span><span class="sxs-lookup"><span data-stu-id="34f5a-274">The graphic below outlines the tasks you must execute for each category.</span></span> <span data-ttu-id="34f5a-275">我们建议您运行这些任务周一次，最少。</span><span class="sxs-lookup"><span data-stu-id="34f5a-275">We recommend that you run these tasks once a week, at a minimum.</span></span>

<span data-ttu-id="34f5a-276">第一次执行这些任务需要比后续迭代的更多工作，因为这些类别的许多需要您验证您部署的配置。</span><span class="sxs-lookup"><span data-stu-id="34f5a-276">The first time you perform these tasks will take more effort than subsequent iterations, because many of these categories require that you validate your deployment configurations.</span></span> <span data-ttu-id="34f5a-277">获得了所需的会议已定义的目标的状态后，执行这些任务将帮助您维护该状态。</span><span class="sxs-lookup"><span data-stu-id="34f5a-277">After you’ve achieved the state you want by meeting the targets you’ve defined, performing these tasks will help you maintain that state.</span></span>

#### <a name="service-management-tasks"></a><span data-ttu-id="34f5a-278">服务管理任务</span><span class="sxs-lookup"><span data-stu-id="34f5a-278">Service management tasks</span></span>

<span data-ttu-id="34f5a-279">在云优先世界中，您必须执行某些服务管理任务，才能保持高品质用户体验。</span><span class="sxs-lookup"><span data-stu-id="34f5a-279">In a cloud-first world, you must perform certain service management tasks to maintain high-quality user experiences.</span></span> <span data-ttu-id="34f5a-280">确保没有足够带宽到达服务没有饱和 internet 链接，验证该服务质量 (QoS) 位于置于所有托管的网络区域，范围为这些任务和 — 最后 — 掌握[上的 Office 365 IP 范围防火墙](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)。</span><span class="sxs-lookup"><span data-stu-id="34f5a-280">These tasks range from ensuring there is sufficient bandwidth to reach the service without saturating internet links, validating that quality of service (QoS) is in place on all managed network areas, and—lastly—staying on top of [Office 365 IP ranges on firewalls](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2).</span></span>

#### <a name="network-tasks"></a><span data-ttu-id="34f5a-281">网络任务</span><span class="sxs-lookup"><span data-stu-id="34f5a-281">Network tasks</span></span>

<span data-ttu-id="34f5a-282">有两种类别的网络任务： 可靠性和质量。</span><span class="sxs-lookup"><span data-stu-id="34f5a-282">There are two categories of network tasks: reliability and quality.</span></span> <span data-ttu-id="34f5a-283">可靠性着重于测量成功发起呼叫并保持联系的用户的能力。</span><span class="sxs-lookup"><span data-stu-id="34f5a-283">Reliability focuses on measuring the user’s ability to make calls successfully and stay connected.</span></span> <span data-ttu-id="34f5a-284">质量着重于发送到工作组和 Skype 业务联机期间的用户的客户端和呼叫结束后的聚合遥测数据。</span><span class="sxs-lookup"><span data-stu-id="34f5a-284">Quality focuses on the aggregated telemetry sent to Teams and Skype for Business Online by the user’s client during and after the call has ended.</span></span>

<span data-ttu-id="34f5a-285">给定关键可靠性对用户体验的影响，开始评估和深入质量之前调查这些指标。</span><span class="sxs-lookup"><span data-stu-id="34f5a-285">Given the critical impact that reliability has on the user experience, begin assessing and investigating those metrics before diving into quality.</span></span>

#### <a name="endpoints-tasks"></a><span data-ttu-id="34f5a-286">终结点任务</span><span class="sxs-lookup"><span data-stu-id="34f5a-286">Endpoints tasks</span></span>

<span data-ttu-id="34f5a-287">此类别中的主要任务验证上从最后一个的六个月，以确保用户获取对业务桌面客户端 Skype 连续优化的好处的桌面生成 for Business 的 Skype 运行哪些客户端版本。</span><span class="sxs-lookup"><span data-stu-id="34f5a-287">The main task in this category is validating which client versions are running Skype for Business on desktop builds from the last six months to ensure users are getting the benefit of the continual optimizations made to the Skype for Business desktop client.</span></span> <span data-ttu-id="34f5a-288">此外，这可简化总体客户端管理任务，并提供一致的用户体验。</span><span class="sxs-lookup"><span data-stu-id="34f5a-288">Additionally, this simplifies overall client management tasks and provides a consistent user experience.</span></span>

<span data-ttu-id="34f5a-289">其他重要区域是监控哪些设备普遍部署中，推动认证设备来提供最佳用户体验。</span><span class="sxs-lookup"><span data-stu-id="34f5a-289">The other important area is monitoring which devices are prevalent in your deployment and driving the use of certified devices to provide the best user experience.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="34f5a-290">目前，分发并自动更新通过 Azure 内容交付网络团队客户端和将保持最新的服务。</span><span class="sxs-lookup"><span data-stu-id="34f5a-290">Currently, Teams clients are distributed and updated automatically through the Azure Content Delivery Network and will be kept up to date by the service.</span></span> <span data-ttu-id="34f5a-291">客户端准备和调查活动不适用于团队。</span><span class="sxs-lookup"><span data-stu-id="34f5a-291">Client readiness and investigative activities aren’t applicable to Teams.</span></span>


## <a name="using-the-reports"></a><span data-ttu-id="34f5a-292">使用报告</span><span class="sxs-lookup"><span data-stu-id="34f5a-292">Using the reports</span></span>

<span data-ttu-id="34f5a-293">本节介绍使用 CQD 的基础知识。</span><span class="sxs-lookup"><span data-stu-id="34f5a-293">This section describes the fundamentals of working with CQD.</span></span> <span data-ttu-id="34f5a-294">指南授予的下列主题：</span><span class="sxs-lookup"><span data-stu-id="34f5a-294">Guidance is given for the following topics:</span></span>

-   <span data-ttu-id="34f5a-295">查找您的租户 ID</span><span class="sxs-lookup"><span data-stu-id="34f5a-295">Finding your tenant ID</span></span>

-   <span data-ttu-id="34f5a-296">为业务报告与 Skype 的团队</span><span class="sxs-lookup"><span data-stu-id="34f5a-296">Reporting on Teams versus Skype for Business</span></span>

-   <span data-ttu-id="34f5a-297">首先与第二个分类</span><span class="sxs-lookup"><span data-stu-id="34f5a-297">First versus second classifications</span></span>

-   <span data-ttu-id="34f5a-298">维度、 度量和筛选器</span><span class="sxs-lookup"><span data-stu-id="34f5a-298">Dimensions, measures, and filters</span></span>

-   <span data-ttu-id="34f5a-299">与呼叫流</span><span class="sxs-lookup"><span data-stu-id="34f5a-299">Streams versus calls</span></span>

-   <span data-ttu-id="34f5a-300">良好的、 不佳的和未分类的呼叫</span><span class="sxs-lookup"><span data-stu-id="34f5a-300">Good, poor, and unclassified calls</span></span>

-   <span data-ttu-id="34f5a-301">入门 CQD</span><span class="sxs-lookup"><span data-stu-id="34f5a-301">Getting started with CQD</span></span>

-   <span data-ttu-id="34f5a-302">编辑 CQD 中的报告</span><span class="sxs-lookup"><span data-stu-id="34f5a-302">Editing reports in CQD</span></span>

-   <span data-ttu-id="34f5a-303">筛选 CQD 中的报告</span><span class="sxs-lookup"><span data-stu-id="34f5a-303">Filtering reports in CQD</span></span>

<span data-ttu-id="34f5a-304">有关更深入的培训和资源，请参阅[附录](#other-resources)。</span><span class="sxs-lookup"><span data-stu-id="34f5a-304">For more in-depth training and resources, see the [Appendix](#other-resources).</span></span>

### <a name="tenant-id"></a><span data-ttu-id="34f5a-305">租户 ID</span><span class="sxs-lookup"><span data-stu-id="34f5a-305">Tenant ID</span></span>

<span data-ttu-id="34f5a-306">某些 CQD 报告需要您的租户 id 包含筛选器</span><span class="sxs-lookup"><span data-stu-id="34f5a-306">Some CQD reports require that you include a filter for your tenant ID.</span></span> <span data-ttu-id="34f5a-307">由于 CQD 聚合数据的方式，联盟参与者遥测是包含。</span><span class="sxs-lookup"><span data-stu-id="34f5a-307">Due to the way CQD aggregates data, federated participant telemetry is included.</span></span>
<span data-ttu-id="34f5a-308">尽管时分析质量欠佳的呼叫指标，这是非常重要，客户端和设备报告需要的特定租户排除联盟参与者的遥测数据的筛选。</span><span class="sxs-lookup"><span data-stu-id="34f5a-308">Although this can prove valuable when analyzing poor call metrics, client and device reports require the filtering of data to a specific tenant to exclude federated participant telemetry.</span></span> <span data-ttu-id="34f5a-309">如果您不知道您的租户 ID，您可以使用下列方法之一找到它。</span><span class="sxs-lookup"><span data-stu-id="34f5a-309">If you don’t know your tenant ID, you can use one of the following methods to find it.</span></span>

<span data-ttu-id="34f5a-310">权限要求</span><span class="sxs-lookup"><span data-stu-id="34f5a-310">Permission requirements</span></span>

-   <span data-ttu-id="34f5a-311">全局管理员角色</span><span class="sxs-lookup"><span data-stu-id="34f5a-311">Global Administrator Role</span></span>

-   <span data-ttu-id="34f5a-312">Skype 业务管理员角色</span><span class="sxs-lookup"><span data-stu-id="34f5a-312">Skype for Business Administrator Role</span></span>

#### <a name="azure-ad-portal"></a><span data-ttu-id="34f5a-313">Azure AD 门户</span><span class="sxs-lookup"><span data-stu-id="34f5a-313">Azure AD Portal</span></span>

1.  <span data-ttu-id="34f5a-314">登录到 Microsoft Azure 门户：<https://portal.azure.com></span><span class="sxs-lookup"><span data-stu-id="34f5a-314">Sign in to the Microsoft Azure portal: <https://portal.azure.com></span></span>

2.  <span data-ttu-id="34f5a-315">选择**Azure Active Directory**。</span><span class="sxs-lookup"><span data-stu-id="34f5a-315">Select **Azure Active Directory**.</span></span>

3.  <span data-ttu-id="34f5a-316">在**管理**下选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="34f5a-316">Under **Manage**, select **Properties**.</span></span> <span data-ttu-id="34f5a-317">在**目录 ID**框中显示的租户 ID。</span><span class="sxs-lookup"><span data-stu-id="34f5a-317">The tenant ID is shown in the **Directory ID** box.</span></span>

#### <a name="azure-powershell"></a><span data-ttu-id="34f5a-318">Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="34f5a-318">Azure PowerShell</span></span>

1.  <span data-ttu-id="34f5a-319">[安装 Microsoft Azure PowerShell 服务管理模块](https://docs.microsoft.com/powershell/azure/servicemanagement/install-azure-ps?view=azuresmps-4.0.0)。</span><span class="sxs-lookup"><span data-stu-id="34f5a-319">[Install the Microsoft Azure PowerShell Service Management module](https://docs.microsoft.com/powershell/azure/servicemanagement/install-azure-ps?view=azuresmps-4.0.0).</span></span>

2.  <span data-ttu-id="34f5a-320">打开 Azure PowerShell 命令窗口并运行以下脚本中，输入您的 Office 365 凭据出现提示时：</span><span class="sxs-lookup"><span data-stu-id="34f5a-320">Open an Azure PowerShell command window and run the following script, entering your Office 365 credentials when prompted:</span></span>  
    <span data-ttu-id="34f5a-321">**登录 AzureRmAccount**</span><span class="sxs-lookup"><span data-stu-id="34f5a-321">**Login-AzureRmAccount**</span></span>

3.  <span data-ttu-id="34f5a-322">在输出中列出的租户 ID。</span><span class="sxs-lookup"><span data-stu-id="34f5a-322">The tenant ID is listed in the output.</span></span>

#### <a name="skype-for-business-online-admin-center"></a><span data-ttu-id="34f5a-323">Skype 的业务 Online 管理中心</span><span class="sxs-lookup"><span data-stu-id="34f5a-323">Skype for Business Online Admin Center</span></span>

1.  <span data-ttu-id="34f5a-324">转到(G)<https://portal.office.com></span><span class="sxs-lookup"><span data-stu-id="34f5a-324">Go to <https://portal.office.com></span></span>

2.  <span data-ttu-id="34f5a-325">使用您的租户管理员组织帐户登录。</span><span class="sxs-lookup"><span data-stu-id="34f5a-325">Sign in with your tenant administrator organizational account.</span></span>

3.  <span data-ttu-id="34f5a-326">选择在**管理中心**下的**Skype for Business** 。</span><span class="sxs-lookup"><span data-stu-id="34f5a-326">Select **Skype for Business** under **Admin Centers**.</span></span>

4.  <span data-ttu-id="34f5a-327">在欢迎页上的租户 ID 被列为**组织 ID** 。</span><span class="sxs-lookup"><span data-stu-id="34f5a-327">The tenant ID is listed as **Organization ID** on the Welcome page.</span></span>

#### <a name="skype-for-business-online-using-powershell"></a><span data-ttu-id="34f5a-328">Skype 业务 online 使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="34f5a-328">Skype for Business Online using PowerShell</span></span>

1.  <span data-ttu-id="34f5a-329">[连接到业务联机通过 PowerShell 自定义的 Skype](https://technet.microsoft.com/library/dn362839(v=ocs.15).aspx)。</span><span class="sxs-lookup"><span data-stu-id="34f5a-329">[Connect to Skype for Business Online via PowerShell](https://technet.microsoft.com/library/dn362839(v=ocs.15).aspx).</span></span>

2.  <span data-ttu-id="34f5a-330">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="34f5a-330">Run the following command:</span></span>  
    <span data-ttu-id="34f5a-331">**(Get cstenant).tenantid**</span><span class="sxs-lookup"><span data-stu-id="34f5a-331">**(Get-cstenant).tenantid**</span></span>

3.  <span data-ttu-id="34f5a-332">租户 ID 显示为 GUID。</span><span class="sxs-lookup"><span data-stu-id="34f5a-332">The tenant ID is displayed as a GUID.</span></span>

### <a name="teams-vs-skype-for-business"></a><span data-ttu-id="34f5a-333">团队与 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="34f5a-333">Teams vs. Skype for Business</span></span>

<span data-ttu-id="34f5a-334">CQD 可以报告团队和 Skype 的业务遥测。</span><span class="sxs-lookup"><span data-stu-id="34f5a-334">CQD can report on both Teams and Skype for Business telemetry.</span></span> <span data-ttu-id="34f5a-335">但是，可能会出现时要进行开发报表可以这样看待团队遥测分开 for Business 的 Skype 的次数。</span><span class="sxs-lookup"><span data-stu-id="34f5a-335">However, there might be times when you want to develop a report to look at Teams telemetry separate from Skype for Business.</span></span>

#### <a name="summary-reports"></a><span data-ttu-id="34f5a-336">摘要报告</span><span class="sxs-lookup"><span data-stu-id="34f5a-336">Summary reports</span></span>

<span data-ttu-id="34f5a-337">若要修改摘要报告页上，可以这样看待仅团队或 for Business 的 Skype，顶部的屏幕上，选择**产品筛选器**下拉列表菜单，然后选择所需的产品。</span><span class="sxs-lookup"><span data-stu-id="34f5a-337">To modify the summary reports page to look at only Teams or Skype for Business, select the **Product Filter** drop-down menu from the top of the screen, and then select the product you want.</span></span>

![这就反映了一个下拉列表菜单显示筛选的工作负荷的选项的呼叫质量仪表板的屏幕截图。](media/quality-of-experience-review-guide-image4.png)

<span data-ttu-id="34f5a-339">_图 4-选择产品筛选器_</span><span class="sxs-lookup"><span data-stu-id="34f5a-339">_Figure 4 - Select a Product Filter_</span></span>

#### <a name="detailed-reports"></a><span data-ttu-id="34f5a-340">详细的报告</span><span class="sxs-lookup"><span data-stu-id="34f5a-340">Detailed reports</span></span>

<span data-ttu-id="34f5a-341">若要筛选的详细的报告，向报告添加筛选器**是团队**，并将其设置为 True 或 False。</span><span class="sxs-lookup"><span data-stu-id="34f5a-341">To filter a detailed report, add the filter **Is Teams** to the report and set it to True or False.</span></span> <span data-ttu-id="34f5a-342">有关详细信息，请参阅本节后面的[编辑报告](#editing-reports)。</span><span class="sxs-lookup"><span data-stu-id="34f5a-342">For more information, see [Editing reports](#editing-reports) later in this section.</span></span>

![显示文件服务器可以添加到的详细报告呼叫质量仪表板的屏幕截图。](media/quality-of-experience-review-guide-image5.png)

<span data-ttu-id="34f5a-344">_图 5-Microsoft 团队筛选器添加到报表_</span><span class="sxs-lookup"><span data-stu-id="34f5a-344">_Figure 5 - Adding a Microsoft Teams filter to a report_</span></span>

### <a name="dimensions-measures-and-filters"></a><span data-ttu-id="34f5a-345">维度、 度量和筛选器</span><span class="sxs-lookup"><span data-stu-id="34f5a-345">Dimensions, measures, and filters</span></span>

<span data-ttu-id="34f5a-346">良好的 CQD 查询包含所有这三个以下参数：</span><span class="sxs-lookup"><span data-stu-id="34f5a-346">A well-formed CQD query contains all three of the following parameters:</span></span>

-   <span data-ttu-id="34f5a-347">**维度：** 我希望如何对数据透视。</span><span class="sxs-lookup"><span data-stu-id="34f5a-347">**Dimension:** How I want to pivot on the data.</span></span>

-   <span data-ttu-id="34f5a-348">**度量值：** 我希望报告。</span><span class="sxs-lookup"><span data-stu-id="34f5a-348">**Measure:** What I want to report on.</span></span>

-   <span data-ttu-id="34f5a-349">**Filter:** 如何要减小查询返回的数据集。</span><span class="sxs-lookup"><span data-stu-id="34f5a-349">**Filter:** How do I want to reduce the data set the query returns.</span></span>

<span data-ttu-id="34f5a-350">另一种方法可以这样看待这是维度是分组函数、 度量是我感兴趣的数据和筛选器是我希望来缩小那些与我的查询相关的结果。</span><span class="sxs-lookup"><span data-stu-id="34f5a-350">Another way to look at this is a dimension is the grouping function, a measure is the data I’m interested in, and a filter is how I want to narrow down the results to those that are relevant to my query.</span></span>

<span data-ttu-id="34f5a-351">格式正确的查询的示例是"我的状态显示不佳流 [度量] 的子网 [维度] 用于构建 6 [筛选器]。"</span><span class="sxs-lookup"><span data-stu-id="34f5a-351">An example of a well-formed query is "Show me Poor Streams [Measure] by Subnet [Dimension] for Building 6 [Filter]."</span></span>

<span data-ttu-id="34f5a-352">有关详细信息，请参阅[维度和度量 CQD 中可用](https://aka.ms/cqd-dm)。</span><span class="sxs-lookup"><span data-stu-id="34f5a-352">For more information, see [Dimensions and measures available in CQD](https://aka.ms/cqd-dm).</span></span>

<span data-ttu-id="34f5a-353">维度、 度量和 CQD 模板中使用的报告的筛选器，请参阅[附录](#CQD-training)。</span><span class="sxs-lookup"><span data-stu-id="34f5a-353">For dimensions, measures, and filters for the reports used in the CQD templates, see the [Appendix](#CQD-training).</span></span>

### <a name="first-vs-second"></a><span data-ttu-id="34f5a-354">首先与秒</span><span class="sxs-lookup"><span data-stu-id="34f5a-354">First vs. second</span></span> 

<span data-ttu-id="34f5a-355">维度和度量 CQD 中的许多分类为第一个或第二个。</span><span class="sxs-lookup"><span data-stu-id="34f5a-355">Many of the dimensions and measures in CQD are classified as first or second.</span></span>
<span data-ttu-id="34f5a-356">CQD 不使用呼叫者/被叫方字段 — 这些已重命名_首先_和_第二个_由于存在且之间的呼叫者和被叫方的步骤。</span><span class="sxs-lookup"><span data-stu-id="34f5a-356">CQD doesn’t use caller/callee fields—these have been renamed _first_ and _second_ because there are intervening steps between the caller and callee.</span></span> <span data-ttu-id="34f5a-357">以下逻辑用于确定将流或通话中涉及的哪些终结点标为第一。</span><span class="sxs-lookup"><span data-stu-id="34f5a-357">The following logic determines which endpoint involved in the stream or call is labeled as first:</span></span>

-   <span data-ttu-id="34f5a-358">首先将始终保持 （会议服务器、 中介服务器，等） 中的服务器终结点如果服务器所涉及的流或呼叫中。</span><span class="sxs-lookup"><span data-stu-id="34f5a-358">First will always be a server endpoint (Conference Server, Mediation Server, and so on) if a server is involved in the stream or call.</span></span>

-   <span data-ttu-id="34f5a-359">第二将始终为客户端终结点除非是两个服务器终结点之间的流。</span><span class="sxs-lookup"><span data-stu-id="34f5a-359">Second will always be a client endpoint unless the stream is between two server endpoints.</span></span>

-   <span data-ttu-id="34f5a-360">如果两个端点都相同的类型，其中的选择是第一个基于用户代理类别的内部排序。</span><span class="sxs-lookup"><span data-stu-id="34f5a-360">If both endpoints are the same type, the choice of which is first is based on internal ordering of the user agent category.</span></span> <span data-ttu-id="34f5a-361">这样可以确保排序的一致性。</span><span class="sxs-lookup"><span data-stu-id="34f5a-361">This ensures the ordering is consistent.</span></span>

<span data-ttu-id="34f5a-362">有关在这两个相同时，确定第一个或第二个终结点的详细信息，请参阅[维度和度量 CQD 中可用](https://aka.ms/cqd-dm)。</span><span class="sxs-lookup"><span data-stu-id="34f5a-362">For more information about determining the first or second endpoint when they’re both the same, see [Dimensions and measures available in CQD](https://aka.ms/cqd-dm).</span></span>

### <a name="stream-vs-call"></a><span data-ttu-id="34f5a-363">与呼叫流</span><span class="sxs-lookup"><span data-stu-id="34f5a-363">Stream vs. call</span></span>

<span data-ttu-id="34f5a-364">您需要了解呼叫和流正确选择的维度或度量需要查看在 CQD 之间的差异。</span><span class="sxs-lookup"><span data-stu-id="34f5a-364">You need to understand the difference between a call and a stream to properly choose which dimensions or measures you’ll be looking at in CQD.</span></span>

<span data-ttu-id="34f5a-365">**流：** 只有两个终结点之间存在流。</span><span class="sxs-lookup"><span data-stu-id="34f5a-365">**Stream:** A stream exists between only two endpoints.</span></span> <span data-ttu-id="34f5a-366">没有为每个方向，只有一个流和两个流所需的通信。</span><span class="sxs-lookup"><span data-stu-id="34f5a-366">There is only one stream for each direction, and two streams are required for communication.</span></span> <span data-ttu-id="34f5a-367">流可用于分析建筑或网络。</span><span class="sxs-lookup"><span data-stu-id="34f5a-367">Streams are useful for analyzing buildings or networks.</span></span> <span data-ttu-id="34f5a-368">在某些情况下，呼叫和流名称 （例如，呼叫安装流或呼叫丢弃流） 中使用。</span><span class="sxs-lookup"><span data-stu-id="34f5a-368">In some cases, both call and stream are used in the name (for example, Call Setup Stream or Call Dropped Stream).</span></span>
<span data-ttu-id="34f5a-369">这些仍将归类为单个流。</span><span class="sxs-lookup"><span data-stu-id="34f5a-369">These are still classified as single streams.</span></span>

<span data-ttu-id="34f5a-370">**呼叫：** 呼叫是从所有参与者的所有流的分组。</span><span class="sxs-lookup"><span data-stu-id="34f5a-370">**Call:** A call is a grouping of all streams from all participants.</span></span> <span data-ttu-id="34f5a-371">呼叫组成 — 至少 — 两个流。</span><span class="sxs-lookup"><span data-stu-id="34f5a-371">A call consists of—at minimum—two streams.</span></span> <span data-ttu-id="34f5a-372">单个呼叫将具有两个参与者每一个流至少具有。</span><span class="sxs-lookup"><span data-stu-id="34f5a-372">A single call will have two participants each with a minimum of one stream.</span></span> <span data-ttu-id="34f5a-373">呼叫可用于分析段时间内的趋势。</span><span class="sxs-lookup"><span data-stu-id="34f5a-373">Calls are useful for analyzing trends over time.</span></span>

<span data-ttu-id="34f5a-374">是否维度或度量值引用呼叫或流的其他指导信息，请参阅[维度和度量 CQD 中可用](https://aka.ms/cqd-dm)</span><span class="sxs-lookup"><span data-stu-id="34f5a-374">For additional guidance on whether the dimension or measure is referring to a call or a stream, see [Dimensions and measures available in CQD](https://aka.ms/cqd-dm)</span></span>

### <a name="good-poor-and-unclassified-calls"></a><span data-ttu-id="34f5a-375">良好的、 不佳的和未分类的呼叫</span><span class="sxs-lookup"><span data-stu-id="34f5a-375">Good, poor, and unclassified calls</span></span>

<span data-ttu-id="34f5a-376">呼叫被分类为良好、 不佳，或者未分类。</span><span class="sxs-lookup"><span data-stu-id="34f5a-376">A call is categorized either as good, poor, or unclassified.</span></span> <span data-ttu-id="34f5a-377">我们来看片刻讨论更多详细信息中的每个。</span><span class="sxs-lookup"><span data-stu-id="34f5a-377">Let’s take a moment to talk about each one in more detail.</span></span>

<span data-ttu-id="34f5a-378">**好或质量欠佳：** 好或质量欠佳的呼叫包含的包含一组完整的服务指标，为其生成完整的 QoE 报告呼叫。</span><span class="sxs-lookup"><span data-stu-id="34f5a-378">**Good or poor:** A good or poor call consists of a call that contains a complete set of service metrics, for which a full QoE report was generated.</span></span>
<span data-ttu-id="34f5a-379">确定呼叫是否良好或质量欠佳是所述的[之前在本指南](#pcr)。</span><span class="sxs-lookup"><span data-stu-id="34f5a-379">Determining whether a call is good or poor is described [earlier in this guide](#pcr).</span></span>

<span data-ttu-id="34f5a-380">**未分类：** 未分类的呼叫不包含一组完整的服务指标。</span><span class="sxs-lookup"><span data-stu-id="34f5a-380">**Unclassified:** An unclassified call doesn’t contain a full set of service metrics.</span></span> <span data-ttu-id="34f5a-381">这通常是短呼叫 — 通常不超过 60 秒 — 其中无法计算平均值和未生成 QoE 报告。</span><span class="sxs-lookup"><span data-stu-id="34f5a-381">These are often short calls—usually less than 60 seconds—where averages couldn’t be computed and a QoE report wasn’t generated.</span></span>

### <a name="access-cqd-online"></a><span data-ttu-id="34f5a-382">联机访问 CQD</span><span class="sxs-lookup"><span data-stu-id="34f5a-382">Access CQD Online</span></span>

<span data-ttu-id="34f5a-383">您可以访问 CQD 两种方式之一。</span><span class="sxs-lookup"><span data-stu-id="34f5a-383">You can access CQD one of two ways.</span></span>

-   <span data-ttu-id="34f5a-384">转到<https://cqd.lync.com>。</span><span class="sxs-lookup"><span data-stu-id="34f5a-384">Go to <https://cqd.lync.com>.</span></span>

-   <span data-ttu-id="34f5a-385">转到**业务管理中心的 Skype** \> **工具**，然后选择 CQD，如下所示的链接。</span><span class="sxs-lookup"><span data-stu-id="34f5a-385">Go to **Skype for Business admin center** \> **tools**, and select the link to CQD, as shown below.</span></span>

![显示"工具"，然后选择在左侧的导航窗格中，并链接到"Skype 的业务联机呼叫质量仪表板"选择屏幕截图。](media/quality-of-experience-review-guide-image6.png)

<span data-ttu-id="34f5a-387">_图 6 – 访问通过业务管理中心的 Skype CQD_</span><span class="sxs-lookup"><span data-stu-id="34f5a-387">_Figure 6 – Accessing CQD through the Skype for Business admin center_</span></span>

### <a name="getting-started"></a><span data-ttu-id="34f5a-388">入门</span><span class="sxs-lookup"><span data-stu-id="34f5a-388">Getting started</span></span>

<span data-ttu-id="34f5a-389">当您首次浏览到 CQD 时，您将看到摘要报告页。</span><span class="sxs-lookup"><span data-stu-id="34f5a-389">When you first browse to CQD, you’ll see the Summary Reports page.</span></span> <span data-ttu-id="34f5a-390">自定义的详细的报告了大部分本指南中所述的报告。</span><span class="sxs-lookup"><span data-stu-id="34f5a-390">Most of the reports described in this guide are custom detailed reports.</span></span> <span data-ttu-id="34f5a-391">若要开始使用详细的报告，选择页上，顶部的**摘要报告**，然后选择**详细的报告**。</span><span class="sxs-lookup"><span data-stu-id="34f5a-391">To get started using the detailed reports, select **Summary Reports** at the top of the page, and then choose **Detailed Reports**.</span></span>

![呼叫质量仪表板 depcting 的屏幕截图的不同类型的可用报告。](media/quality-of-experience-review-guide-image7.png)

<span data-ttu-id="34f5a-393">_图 7-导航到详细的报告_</span><span class="sxs-lookup"><span data-stu-id="34f5a-393">_Figure 7 - Navigating to Detailed Reports_</span></span>

<span data-ttu-id="34f5a-394">CQD 详细的报告页类似于图所示。</span><span class="sxs-lookup"><span data-stu-id="34f5a-394">The Detailed Reports page in CQD looks like the figure shown below.</span></span>

![CQD 和组成报表的不同元素中的详细的报告页的屏幕截图。](media/quality-of-experience-review-guide-image8.png)

<span data-ttu-id="34f5a-396">_图 8-详细的报告页面_</span><span class="sxs-lookup"><span data-stu-id="34f5a-396">_Figure 8 - Detailed Reports page_</span></span>

1.  <span data-ttu-id="34f5a-397">摘要窗格显示上下文报告集中的右侧。</span><span class="sxs-lookup"><span data-stu-id="34f5a-397">The summary pane shows context for the report set that appears to the right.</span></span>

2.  <span data-ttu-id="34f5a-398">您可以在设置报表级属性 （包括 y 轴高度） 摘要窗格中选择**编辑**。</span><span class="sxs-lookup"><span data-stu-id="34f5a-398">You can select **Edit** in the summary pane to set report–level properties (including y-axis height).</span></span>

3.  <span data-ttu-id="34f5a-399">痕迹导航可帮助用户确定报告集层次结构中的当前位置。</span><span class="sxs-lookup"><span data-stu-id="34f5a-399">The breadcrumb helps users identify their current location in the report set hierarchy.</span></span>

4.  <span data-ttu-id="34f5a-400">具有子报表的报告所示的蓝色的链接。</span><span class="sxs-lookup"><span data-stu-id="34f5a-400">Reports that have child reports are shown with a blue link.</span></span> <span data-ttu-id="34f5a-401">通过选择链接，您可以子报表向下钻取。</span><span class="sxs-lookup"><span data-stu-id="34f5a-401">By selecting the link, you can drill down to the child reports.</span></span>

<span data-ttu-id="34f5a-402">指向条形图和趋势线显示详细的值。</span><span class="sxs-lookup"><span data-stu-id="34f5a-402">Point to the bar charts and trend lines to display detailed values.</span></span> <span data-ttu-id="34f5a-403">具有焦点的报告将显示操作菜单：**编辑**、**克隆**、**删除**、**下载**和**导出报告树**。</span><span class="sxs-lookup"><span data-stu-id="34f5a-403">The report that has focus will show the action menu: **Edit**, **Clone**, **Delete**, **Download**, and **Export Report Tree**.</span></span>

### <a name="editing-reports"></a><span data-ttu-id="34f5a-404">编辑报告</span><span class="sxs-lookup"><span data-stu-id="34f5a-404">Editing reports</span></span>

<span data-ttu-id="34f5a-405">当在报表的操作菜单上选择**编辑**时，您将打开查询编辑器。</span><span class="sxs-lookup"><span data-stu-id="34f5a-405">When you select **Edit** on the action menu of a report, you’ll open Query Editor.</span></span> <span data-ttu-id="34f5a-406">每个报告被后盾查询。</span><span class="sxs-lookup"><span data-stu-id="34f5a-406">Each report is backed by a query.</span></span> <span data-ttu-id="34f5a-407">报告是其查询返回的数据的可视化形式。</span><span class="sxs-lookup"><span data-stu-id="34f5a-407">A report is a visualization of the data returned by its query.</span></span> <span data-ttu-id="34f5a-408">查询编辑器以供编辑报表的显示选项除了这些查询为用户界面，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="34f5a-408">The Query Editor is a UI for editing these queries in addition to the display options for the report, as illustrated in the following figure.</span></span>

![CQD 和组成报表，如果正在编辑报表的不同元素中的详细的报告页的屏幕截图。](media/quality-of-experience-review-guide-image9.png)

<span data-ttu-id="34f5a-410">_图 9-报告编辑器_</span><span class="sxs-lookup"><span data-stu-id="34f5a-410">_Figure 9 - Report Editor_</span></span>

1.  <span data-ttu-id="34f5a-411">从左窗格中选择了维度、 度量和筛选器。</span><span class="sxs-lookup"><span data-stu-id="34f5a-411">You choose dimensions, measures, and filters from the left pane.</span></span> <span data-ttu-id="34f5a-412">指向现有值显示关闭按钮 (**X**) 您可以选择删除值。</span><span class="sxs-lookup"><span data-stu-id="34f5a-412">Pointing to an existing value displays a close button (**X**) you can select to remove the value.</span></span>

    1.  <span data-ttu-id="34f5a-413">通过选择维度或度量值，您可以通过编辑**标题**字段更改标题。</span><span class="sxs-lookup"><span data-stu-id="34f5a-413">By selecting the dimension or measure, you can change the title by editing the **Title** field.</span></span> <span data-ttu-id="34f5a-414">您可以通过在顶部窗格中选择的蓝色向上或向下箭头来更改的顺序。</span><span class="sxs-lookup"><span data-stu-id="34f5a-414">You can also change the order by selecting the blue Up or Down arrows in the top pane.</span></span>

    2.  <span data-ttu-id="34f5a-415">选择 (**+**) 标题旁边将打开添加新的维度、 度量值或筛选器对话框。</span><span class="sxs-lookup"><span data-stu-id="34f5a-415">Selecting (**+**) next to a heading opens the dialog box for adding a new dimension, measure, or filter.</span></span>

    3.  <span data-ttu-id="34f5a-416">输入前几个字母的维度、 度量值或筛选器中的**查找**字段筛选的更易于搜索列表。</span><span class="sxs-lookup"><span data-stu-id="34f5a-416">Enter the first few letters of the dimension, measure, or filter in the **Find a** field to filter the list for easier searching.</span></span>

2.  <span data-ttu-id="34f5a-417">顶部窗格中显示图表自定义选项。</span><span class="sxs-lookup"><span data-stu-id="34f5a-417">The top pane shows options for chart customization.</span></span>

3.  <span data-ttu-id="34f5a-418">查询编辑器中显示的报表的预览。</span><span class="sxs-lookup"><span data-stu-id="34f5a-418">The Query Editor shows a preview of the report.</span></span>

4.  <span data-ttu-id="34f5a-419">使用在屏幕底部的**编辑**框中创建或编辑报表的详细的说明。</span><span class="sxs-lookup"><span data-stu-id="34f5a-419">Use the **Edit** box at the bottom of the screen to create or edit a detailed description of the report.</span></span>

### <a name="filtering-reports"></a><span data-ttu-id="34f5a-420">筛选报告</span><span class="sxs-lookup"><span data-stu-id="34f5a-420">Filtering reports</span></span>

<span data-ttu-id="34f5a-421">提供的模板包括几内置查询和报告筛选器。</span><span class="sxs-lookup"><span data-stu-id="34f5a-421">The templates provided includes several built-in queries and report filters.</span></span> <span data-ttu-id="34f5a-422">以下各节介绍整个模板中使用的最常见的筛选器。</span><span class="sxs-lookup"><span data-stu-id="34f5a-422">The following sections describe the most common filters used throughout the templates.</span></span>

#### <a name="cqd-filter"></a><span data-ttu-id="34f5a-423">CQD 筛选器</span><span class="sxs-lookup"><span data-stu-id="34f5a-423">CQD filter</span></span>

<span data-ttu-id="34f5a-424">您可以使用 CQD 筛选器或 URL 筛选器，暂时筛选每个报告查询。</span><span class="sxs-lookup"><span data-stu-id="34f5a-424">You can use the CQD filter, or URL filter, to temporarily filter every report query.</span></span> <span data-ttu-id="34f5a-425">您可以使用的最常见 CQD 筛选器是筛选报告中排除联盟参与者遥测。</span><span class="sxs-lookup"><span data-stu-id="34f5a-425">The most common CQD filter you’ll use is to filter reports to exclude federated participant telemetry.</span></span> <span data-ttu-id="34f5a-426">我们建议您书签此筛选器，使其成为默认视图。</span><span class="sxs-lookup"><span data-stu-id="34f5a-426">We recommend that you bookmark this filter so it becomes the default view.</span></span> <span data-ttu-id="34f5a-427">正在补救托管的建筑或网络其中联合的数据可能会影响您的报表时，从 CQD 报告中排除联合的数据很有用。</span><span class="sxs-lookup"><span data-stu-id="34f5a-427">Excluding federated data from CQD reports is useful when you’re remediating managed buildings or networks where federated data might influence your report.</span></span>

<span data-ttu-id="34f5a-428">若要实现 CQD 筛选器，在浏览器地址栏中，该 URL 的末尾附加以下：</span><span class="sxs-lookup"><span data-stu-id="34f5a-428">To implement a CQD filter, in the browser address bar, append the following to the end of the URL:</span></span>

<span data-ttu-id="34f5a-429">/filter/ [AllStreams]。[第二个租户 Id]\|[您租户 ID 此处]</span><span class="sxs-lookup"><span data-stu-id="34f5a-429">/filter/[AllStreams].[Second Tenant Id]\|[YOUR TENANT ID HERE]</span></span>

<span data-ttu-id="34f5a-430">**示例：**</span><span class="sxs-lookup"><span data-stu-id="34f5a-430">**Example:**</span></span>  
<span data-ttu-id="34f5a-431">https://cqd.lync.com/cqd/\#/1234567/2018-02/filter/[AllStreams]。[第二个租户 Id]\|[TENANTID] & 租户 = TENANTID</span><span class="sxs-lookup"><span data-stu-id="34f5a-431">https://cqd.lync.com/cqd/\#/1234567/2018-02/filter/[AllStreams].[Second Tenant Id]\|[TENANTID]&tenant=TENANTID</span></span>

> [!NOTE]
> <span data-ttu-id="34f5a-432">上面的 URL 示例是直观表示形式。</span><span class="sxs-lookup"><span data-stu-id="34f5a-432">The URL example above is for visual representation only.</span></span> <span data-ttu-id="34f5a-433">请使用的默认 CQD 链接<https://cqd.lync.com>。</span><span class="sxs-lookup"><span data-stu-id="34f5a-433">Please use the default CQD link of <https://cqd.lync.com>.</span></span>

#### <a name="query-filters"></a><span data-ttu-id="34f5a-434">查询筛选器</span><span class="sxs-lookup"><span data-stu-id="34f5a-434">Query filters</span></span>

<span data-ttu-id="34f5a-435">通过使用报表编辑器实现查询筛选器。</span><span class="sxs-lookup"><span data-stu-id="34f5a-435">Query filters are implemented by using the Report Editor.</span></span> <span data-ttu-id="34f5a-436">这些筛选器用于减少由 CQD，因此最小化报表的整体大小返回的记录数。</span><span class="sxs-lookup"><span data-stu-id="34f5a-436">These filters are used to reduce the number of records returned by CQD, thus minimizing the report’s overall size.</span></span> <span data-ttu-id="34f5a-437">这是对于筛选出非托管网络特别有用。</span><span class="sxs-lookup"><span data-stu-id="34f5a-437">This is especially useful for filtering out unmanaged networks.</span></span>
<span data-ttu-id="34f5a-438">下面的筛选器使用正则表达式 (RegEx)。</span><span class="sxs-lookup"><span data-stu-id="34f5a-438">The filters below use regular expressions (RegEx).</span></span>

<span data-ttu-id="34f5a-439">_表 3-查询筛选器_</span><span class="sxs-lookup"><span data-stu-id="34f5a-439">_Table 3 - Query filters_</span></span>

| <span data-ttu-id="34f5a-440">筛选器</span><span class="sxs-lookup"><span data-stu-id="34f5a-440">Filter</span></span>               | <span data-ttu-id="34f5a-441">说明</span><span class="sxs-lookup"><span data-stu-id="34f5a-441">Description</span></span>          | <span data-ttu-id="34f5a-442">CQD 查询筛选器示例</span><span class="sxs-lookup"><span data-stu-id="34f5a-442">CQD query filter example</span></span>                                  |
|----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------|
| <span data-ttu-id="34f5a-443">空值</span><span class="sxs-lookup"><span data-stu-id="34f5a-443">Blank values</span></span>         | <span data-ttu-id="34f5a-444">某些筛选器无需对空值进行筛选选项。</span><span class="sxs-lookup"><span data-stu-id="34f5a-444">Some filters don’t have the option to filter for blank values.</span></span> <span data-ttu-id="34f5a-445">若要手动筛选空值，请使用空表达式，并设置为等于或不等于，筛选器，具体取决于您的需求。</span><span class="sxs-lookup"><span data-stu-id="34f5a-445">To filter blank values manually, use the blank expression and set the filter to Equals or Not Equals, depending on your needs.</span></span>                                                                                                                             | <span data-ttu-id="34f5a-446">第二个建筑物名称\< \> \^ \\s\*\$</span><span class="sxs-lookup"><span data-stu-id="34f5a-446">Second Building Name \<\> \^\\s\*\$</span></span>                       |
| <span data-ttu-id="34f5a-447">受欢迎的主子网</span><span class="sxs-lookup"><span data-stu-id="34f5a-447">Popular home subnets</span></span> | <span data-ttu-id="34f5a-448">没有有效的生成文件到单独的托管从非托管网络，报告中获取包含家庭网络。</span><span class="sxs-lookup"><span data-stu-id="34f5a-448">Without a valid building file to separate managed from unmanaged networks, home networks will get included in the reports.</span></span> <span data-ttu-id="34f5a-449">这些主页的子网是它的控件的范围之外，可以快速排除从报表。</span><span class="sxs-lookup"><span data-stu-id="34f5a-449">These home subnets are outside the scope of IT’s control and can be quickly excluded from a report.</span></span> <span data-ttu-id="34f5a-450">常用家庭子网中本指南中，定义为 10.0.0.0、 192.168.1.0 和 192.168.0.0。</span><span class="sxs-lookup"><span data-stu-id="34f5a-450">Popular home subnets, as defined in this guide, are 10.0.0.0, 192.168.1.0 and 192.168.0.0.</span></span> | <span data-ttu-id="34f5a-451">第二个子网\< \> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="34f5a-451">Second Subnet \<\> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0</span></span> |
| <span data-ttu-id="34f5a-452">内部和外部</span><span class="sxs-lookup"><span data-stu-id="34f5a-452">Inside vs. outside</span></span>   | <span data-ttu-id="34f5a-453">用于筛选 （内部） 托管或非托管 （外部） 的报告。</span><span class="sxs-lookup"><span data-stu-id="34f5a-453">Used to filter a report for managed (inside) or unmanaged (outside).</span></span> <span data-ttu-id="34f5a-454">托管的 CQD 模板已与这些筛选器预配置。</span><span class="sxs-lookup"><span data-stu-id="34f5a-454">The managed CQD template is already preconfigured with these filters.</span></span>                                                                                                                                                                                | <span data-ttu-id="34f5a-455">第二内 Corp = 内</span><span class="sxs-lookup"><span data-stu-id="34f5a-455">Second Inside Corp = Inside</span></span>                               |

#### <a name="report-filters"></a><span data-ttu-id="34f5a-456">报告筛选器</span><span class="sxs-lookup"><span data-stu-id="34f5a-456">Report filters</span></span>

<span data-ttu-id="34f5a-457">通过对呈现报表可以在报表编辑器中或直接向报表添加筛选器实现报告筛选器。</span><span class="sxs-lookup"><span data-stu-id="34f5a-457">Report filters are implemented by adding a filter to the rendered report either in the Report Editor or directly to the report.</span></span> <span data-ttu-id="34f5a-458">在模板整个中使用的以下报告筛选器。</span><span class="sxs-lookup"><span data-stu-id="34f5a-458">The following reports filters are used throughout the template.</span></span>

<span data-ttu-id="34f5a-459">_表 4-报告筛选器_</span><span class="sxs-lookup"><span data-stu-id="34f5a-459">_Table 4 - Report Filter_</span></span>

| <span data-ttu-id="34f5a-460">筛选器</span><span class="sxs-lookup"><span data-stu-id="34f5a-460">Filter</span></span>     | <span data-ttu-id="34f5a-461">说明</span><span class="sxs-lookup"><span data-stu-id="34f5a-461">Description</span></span>                            | <span data-ttu-id="34f5a-462">CQD 报告筛选器示例</span><span class="sxs-lookup"><span data-stu-id="34f5a-462">CQD report filter example</span></span>         |
|------------|----------------------------------------|-----------------------------------|
| <span data-ttu-id="34f5a-463">Month</span><span class="sxs-lookup"><span data-stu-id="34f5a-463">Month</span></span>      | <span data-ttu-id="34f5a-464">从一年开始第一张、 然后月份。</span><span class="sxs-lookup"><span data-stu-id="34f5a-464">Start with the year first, then month.</span></span> | <span data-ttu-id="34f5a-465">2017 10</span><span class="sxs-lookup"><span data-stu-id="34f5a-465">2017-10</span></span>                           |
| <span data-ttu-id="34f5a-466">字母</span><span class="sxs-lookup"><span data-stu-id="34f5a-466">Alphabetic</span></span> | <span data-ttu-id="34f5a-467">筛选的任何字母字符。</span><span class="sxs-lookup"><span data-stu-id="34f5a-467">Filters for any alphabetic characters.</span></span> | <span data-ttu-id="34f5a-468">[-z]</span><span class="sxs-lookup"><span data-stu-id="34f5a-468">[a-z]</span></span>                             |
| <span data-ttu-id="34f5a-469">数字</span><span class="sxs-lookup"><span data-stu-id="34f5a-469">Numeric</span></span>    | <span data-ttu-id="34f5a-470">筛选的任何数字字符。</span><span class="sxs-lookup"><span data-stu-id="34f5a-470">Filters for any numeric characters.</span></span>    | <span data-ttu-id="34f5a-471">[0-9]</span><span class="sxs-lookup"><span data-stu-id="34f5a-471">[0-9]</span></span>                             |
| <span data-ttu-id="34f5a-472">百分比</span><span class="sxs-lookup"><span data-stu-id="34f5a-472">Percentage</span></span> | <span data-ttu-id="34f5a-473">百分比筛选。</span><span class="sxs-lookup"><span data-stu-id="34f5a-473">Filters for a percentage.</span></span>              | <span data-ttu-id="34f5a-474">([3-9]\\。)\|([3-9])\|([1-9][0-9])</span><span class="sxs-lookup"><span data-stu-id="34f5a-474">([3-9]\\.)\|([3-9])\|([1-9][0-9])</span></span> |

## <a name="import-the-cqd-templates"></a><span data-ttu-id="34f5a-475">导入 CQD 模板</span><span class="sxs-lookup"><span data-stu-id="34f5a-475">Import the CQD templates</span></span>

<span data-ttu-id="34f5a-476">本指南包含[两个 curated 的 CQD 模板](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/quality-of-experience-review-lite-templates-v-2-1.zip?raw=true)。</span><span class="sxs-lookup"><span data-stu-id="34f5a-476">This guide includes [two curated CQD templates](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/quality-of-experience-review-lite-templates-v-2-1.zip?raw=true).</span></span> <span data-ttu-id="34f5a-477">这些模板加快 CQD 的使用情况，并为您提供快速利用 CQD 的功能，使用户团队或 Skype 对业务体验的影响的机会。</span><span class="sxs-lookup"><span data-stu-id="34f5a-477">These templates accelerate your usage of CQD and provide you an opportunity to quickly leverage CQD’s capabilities to make an impact on your users’ Teams or Skype for Business experience.</span></span> <span data-ttu-id="34f5a-478">所有网络模板，上述优化用于生成数据文件，可以使用您的工作收集和上载到 CQD，构建信息下一步部分中所述。</span><span class="sxs-lookup"><span data-stu-id="34f5a-478">The All Networks template, though optimized to work with a building data file, can be used while you work toward collecting and uploading building information into CQD, as described in the next section.</span></span>

<span data-ttu-id="34f5a-479">**若要导入模板 (。CQDX) 到 CQD 联机**</span><span class="sxs-lookup"><span data-stu-id="34f5a-479">**To import the templates (.CQDX) into CQD Online**</span></span>

1.  <span data-ttu-id="34f5a-480">转到<https://cqd.lync.com>。</span><span class="sxs-lookup"><span data-stu-id="34f5a-480">Go to <https://cqd.lync.com>.</span></span>

2.  <span data-ttu-id="34f5a-481">使用 Office 365 管理凭据进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="34f5a-481">Authenticate by using your Office 365 Administrative credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="34f5a-482">您必须具有 Office 365 全局管理员，业务管理员或报告读者角色访问 CQD Skype。</span><span class="sxs-lookup"><span data-stu-id="34f5a-482">You must have the Office 365 Global Administrator, Skype for Business Administrator, or Report Readers role to access CQD.</span></span> 


3.  <span data-ttu-id="34f5a-483">选择顶部的页上，**摘要报表**菜单，然后选择**详细的报告**。</span><span class="sxs-lookup"><span data-stu-id="34f5a-483">Select the **Summary Reports** menu at the top of the page, and then choose **Detailed Reports**.</span></span>

4.  <span data-ttu-id="34f5a-484">在摘要窗格中，选择**导入**。</span><span class="sxs-lookup"><span data-stu-id="34f5a-484">On the summary pane, select **Import**.</span></span> <span data-ttu-id="34f5a-485">转到保存位置 CQDX，选择 CQDX 模板，然后选择**打开**。</span><span class="sxs-lookup"><span data-stu-id="34f5a-485">Go to the CQDX saved location, select the CQDX template, and then select **Open**.</span></span>

5.  <span data-ttu-id="34f5a-486">将模板上载后，变为弹出式窗口将显示消息"报表导入成功。"</span><span class="sxs-lookup"><span data-stu-id="34f5a-486">After the template is uploaded, a pop-up window will display the message “Report import was successful.”</span></span> <span data-ttu-id="34f5a-487">选择**确定。**</span><span class="sxs-lookup"><span data-stu-id="34f5a-487">Select **OK.**</span></span>

![通知用户模板已成功导入的弹出窗口的屏幕截图。](media/quality-of-experience-review-guide-imagestep5.png)

6.  <span data-ttu-id="34f5a-489">第二个 CQD 模板重复步骤 4 和 5。</span><span class="sxs-lookup"><span data-stu-id="34f5a-489">Repeat steps 4 and 5 for the second CQD template.</span></span>

> [!NOTE]
> <span data-ttu-id="34f5a-490">每个用户导入 CQD 模板。</span><span class="sxs-lookup"><span data-stu-id="34f5a-490">The CQD templates are imported per user.</span></span> <span data-ttu-id="34f5a-491">如果其他用户需要使用报告，它们必须登录，并将模板导入其 CQD 实例。</span><span class="sxs-lookup"><span data-stu-id="34f5a-491">If additional users need to use the report, they must sign in and import the templates into their CQD instance.</span></span> 


## <a name="building-mapping"></a><span data-ttu-id="34f5a-492">构建映射</span><span class="sxs-lookup"><span data-stu-id="34f5a-492">Building mapping</span></span>

<span data-ttu-id="34f5a-493">在工作组或业务 Online 部署的 Skype，所有客户端的外部。</span><span class="sxs-lookup"><span data-stu-id="34f5a-493">In a Teams or Skype for Business Online deployment, all clients are external.</span></span>
<span data-ttu-id="34f5a-494">具有，默认情况下，所有客户端都外部 CQD Online 中为报告，无论是否在公司内部网络连接，客户端隐含。</span><span class="sxs-lookup"><span data-stu-id="34f5a-494">That has the implication that by default, all clients are reported as outside in CQD Online, regardless of whether the client was connected on an internal corporate network.</span></span>

<span data-ttu-id="34f5a-495">当您处理呼叫质量，您需要知道客户端的位置和它已连接到网络可以管理或网络是否无法管理 — 您可以管理假设正在您只会提高网络。</span><span class="sxs-lookup"><span data-stu-id="34f5a-495">When you work with call quality, you need to know the location of a client and whether it was connected to a network you can manage or a network you can’t manage—the assumption being that you can only improve networks you can manage.</span></span>
<span data-ttu-id="34f5a-496">上载到 CQD Online 网络和构建信息，则启用 CQD 以确定客户端是否已连接到托管公司 / 内部网络或非托管外部/网络。</span><span class="sxs-lookup"><span data-stu-id="34f5a-496">By uploading network and building information to CQD Online, you enable CQD to determine whether a client was connected to an internal corporate/managed network or to an external/unmanaged network.</span></span>

### <a name="building-data-file-structure"></a><span data-ttu-id="34f5a-497">构建数据文件结构</span><span class="sxs-lookup"><span data-stu-id="34f5a-497">Building data file structure</span></span>

<span data-ttu-id="34f5a-498">您上载的数据文件的格式必须满足以下要求才能通过在上载之前验证检查。</span><span class="sxs-lookup"><span data-stu-id="34f5a-498">The format of the data file you upload must meet the following requirements to pass the validation check before uploading.</span></span>

-   <span data-ttu-id="34f5a-499">文件必须 TSV 文件，这意味着，对于每一行，每个列分隔制表符或每个列并用逗号分隔的 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="34f5a-499">The file must be either a TSV file, which means that for each row, each column is separated by a Tab character, or a CSV file in which each column is separated by a comma.</span></span>

-   <span data-ttu-id="34f5a-500">文件不能超过 50 MB。</span><span class="sxs-lookup"><span data-stu-id="34f5a-500">The file can’t be larger than 50 MB.</span></span>

-   <span data-ttu-id="34f5a-501">数据的内容文件*不能包括表格标题*。</span><span class="sxs-lookup"><span data-stu-id="34f5a-501">The content of the data file *must not include table headers*.</span></span> <span data-ttu-id="34f5a-502">换句话说，数据文件的第一行必须实际数据，不列标题，例如"网络"。</span><span class="sxs-lookup"><span data-stu-id="34f5a-502">In other words, the first line of the data file must be real data, not column headings such as “Network.”</span></span>

-   <span data-ttu-id="34f5a-503">每个列的数据类型仅可以是字符串、 号码或 Bool。</span><span class="sxs-lookup"><span data-stu-id="34f5a-503">For each column, the data type can only be String, Number, or Bool.</span></span> <span data-ttu-id="34f5a-504">如果数据类型是数字，值必须是数值;如果是 Bool，值必须是 0 或 1。</span><span class="sxs-lookup"><span data-stu-id="34f5a-504">If the data type is Number, the value must be a numeric value; if it’s Bool, the value must be either 0 or 1.</span></span>

-   <span data-ttu-id="34f5a-505">每个列的数据类型为 String，如果数据可以为空 （但仍必须用适当的分隔符，即制表符或逗号分隔）。</span><span class="sxs-lookup"><span data-stu-id="34f5a-505">For each column, if the data type is String, the data can be empty (but still must be separated by an appropriate delimiter, that is a Tab character or comma).</span></span> <span data-ttu-id="34f5a-506">这只是分配该字段空字符串值。</span><span class="sxs-lookup"><span data-stu-id="34f5a-506">This just assigns that field an empty string value.</span></span>

-   <span data-ttu-id="34f5a-507">必须为每个行的 14 列。</span><span class="sxs-lookup"><span data-stu-id="34f5a-507">There must be 14 columns for each row.</span></span> <span data-ttu-id="34f5a-508">每个列必须具有下表中所述的数据类型和列都必须包含在表中列出的顺序。</span><span class="sxs-lookup"><span data-stu-id="34f5a-508">Each column must have the data type described in the following table, and the columns must be in the order listed in the table.</span></span>

<span data-ttu-id="34f5a-509">_表 5-构建文件结构_</span><span class="sxs-lookup"><span data-stu-id="34f5a-509">_Table 5 - Building file structure_</span></span>

| <span data-ttu-id="34f5a-510">列名称</span><span class="sxs-lookup"><span data-stu-id="34f5a-510">Column name</span></span>        | <span data-ttu-id="34f5a-511">数据类型</span><span class="sxs-lookup"><span data-stu-id="34f5a-511">Data type</span></span> | <span data-ttu-id="34f5a-512">示例</span><span class="sxs-lookup"><span data-stu-id="34f5a-512">Example</span></span>                   | <span data-ttu-id="34f5a-513">指南</span><span class="sxs-lookup"><span data-stu-id="34f5a-513">Guidance</span></span>    |
|--------------------|-----------|---------------------------|-------------|
| <span data-ttu-id="34f5a-514">网络</span><span class="sxs-lookup"><span data-stu-id="34f5a-514">Network</span></span>            | <span data-ttu-id="34f5a-515">字符串</span><span class="sxs-lookup"><span data-stu-id="34f5a-515">String</span></span>    | <span data-ttu-id="34f5a-516">192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="34f5a-516">192.168.1.0</span></span>               | <span data-ttu-id="34f5a-517">必需</span><span class="sxs-lookup"><span data-stu-id="34f5a-517">Required</span></span>    |
| <span data-ttu-id="34f5a-518">NetworkName</span><span class="sxs-lookup"><span data-stu-id="34f5a-518">NetworkName</span></span>        | <span data-ttu-id="34f5a-519">字符串</span><span class="sxs-lookup"><span data-stu-id="34f5a-519">String</span></span>    | <span data-ttu-id="34f5a-520">美国/西雅图/西雅图-SEA-1</span><span class="sxs-lookup"><span data-stu-id="34f5a-520">USA/Seattle/SEATTLE-SEA-1</span></span> | <span data-ttu-id="34f5a-521">必填\*</span><span class="sxs-lookup"><span data-stu-id="34f5a-521">Required\*</span></span>  |
| <span data-ttu-id="34f5a-522">NetworkRange</span><span class="sxs-lookup"><span data-stu-id="34f5a-522">NetworkRange</span></span>       | <span data-ttu-id="34f5a-523">数字</span><span class="sxs-lookup"><span data-stu-id="34f5a-523">Number</span></span>    | <span data-ttu-id="34f5a-524">26</span><span class="sxs-lookup"><span data-stu-id="34f5a-524">26</span></span>                        | <span data-ttu-id="34f5a-525">必需</span><span class="sxs-lookup"><span data-stu-id="34f5a-525">Required</span></span>    |
| <span data-ttu-id="34f5a-526">BuildingName</span><span class="sxs-lookup"><span data-stu-id="34f5a-526">BuildingName</span></span>       | <span data-ttu-id="34f5a-527">字符串</span><span class="sxs-lookup"><span data-stu-id="34f5a-527">String</span></span>    | <span data-ttu-id="34f5a-528">西雅图-SEA-1</span><span class="sxs-lookup"><span data-stu-id="34f5a-528">SEATTLE-SEA-1</span></span>             | <span data-ttu-id="34f5a-529">必填\*</span><span class="sxs-lookup"><span data-stu-id="34f5a-529">Required\*</span></span>  |
| <span data-ttu-id="34f5a-530">OwnershipType</span><span class="sxs-lookup"><span data-stu-id="34f5a-530">OwnershipType</span></span>      | <span data-ttu-id="34f5a-531">字符串</span><span class="sxs-lookup"><span data-stu-id="34f5a-531">String</span></span>    | <span data-ttu-id="34f5a-532">Contoso</span><span class="sxs-lookup"><span data-stu-id="34f5a-532">Contoso</span></span>                   | <span data-ttu-id="34f5a-533">可选</span><span class="sxs-lookup"><span data-stu-id="34f5a-533">Optional</span></span>    |
| <span data-ttu-id="34f5a-534">BuildingType</span><span class="sxs-lookup"><span data-stu-id="34f5a-534">BuildingType</span></span>       | <span data-ttu-id="34f5a-535">字符串</span><span class="sxs-lookup"><span data-stu-id="34f5a-535">String</span></span>    | <span data-ttu-id="34f5a-536">IT 终止</span><span class="sxs-lookup"><span data-stu-id="34f5a-536">IT Termination</span></span>            | <span data-ttu-id="34f5a-537">可选</span><span class="sxs-lookup"><span data-stu-id="34f5a-537">Optional</span></span>    |
| <span data-ttu-id="34f5a-538">BuildingOfficeType</span><span class="sxs-lookup"><span data-stu-id="34f5a-538">BuildingOfficeType</span></span> | <span data-ttu-id="34f5a-539">字符串</span><span class="sxs-lookup"><span data-stu-id="34f5a-539">String</span></span>    | <span data-ttu-id="34f5a-540">Engineering</span><span class="sxs-lookup"><span data-stu-id="34f5a-540">Engineering</span></span>               | <span data-ttu-id="34f5a-541">可选</span><span class="sxs-lookup"><span data-stu-id="34f5a-541">Optional</span></span>    |
| <span data-ttu-id="34f5a-542">城市</span><span class="sxs-lookup"><span data-stu-id="34f5a-542">City</span></span>               | <span data-ttu-id="34f5a-543">字符串</span><span class="sxs-lookup"><span data-stu-id="34f5a-543">String</span></span>    | <span data-ttu-id="34f5a-544">西雅图</span><span class="sxs-lookup"><span data-stu-id="34f5a-544">Seattle</span></span>                   | <span data-ttu-id="34f5a-545">推荐</span><span class="sxs-lookup"><span data-stu-id="34f5a-545">Recommended</span></span> |
| <span data-ttu-id="34f5a-546">邮政编码</span><span class="sxs-lookup"><span data-stu-id="34f5a-546">ZipCode</span></span>            | <span data-ttu-id="34f5a-547">字符串</span><span class="sxs-lookup"><span data-stu-id="34f5a-547">String</span></span>    | <span data-ttu-id="34f5a-548">98001</span><span class="sxs-lookup"><span data-stu-id="34f5a-548">98001</span></span>                     | <span data-ttu-id="34f5a-549">推荐</span><span class="sxs-lookup"><span data-stu-id="34f5a-549">Recommended</span></span> |
| <span data-ttu-id="34f5a-550">国家/地区</span><span class="sxs-lookup"><span data-stu-id="34f5a-550">Country</span></span>            | <span data-ttu-id="34f5a-551">字符串</span><span class="sxs-lookup"><span data-stu-id="34f5a-551">String</span></span>    | <span data-ttu-id="34f5a-552">我们</span><span class="sxs-lookup"><span data-stu-id="34f5a-552">US</span></span>                        | <span data-ttu-id="34f5a-553">推荐</span><span class="sxs-lookup"><span data-stu-id="34f5a-553">Recommended</span></span> |
| <span data-ttu-id="34f5a-554">省/市/自治区</span><span class="sxs-lookup"><span data-stu-id="34f5a-554">State</span></span>              | <span data-ttu-id="34f5a-555">字符串</span><span class="sxs-lookup"><span data-stu-id="34f5a-555">String</span></span>    | <span data-ttu-id="34f5a-556">WA</span><span class="sxs-lookup"><span data-stu-id="34f5a-556">WA</span></span>                        | <span data-ttu-id="34f5a-557">推荐</span><span class="sxs-lookup"><span data-stu-id="34f5a-557">Recommended</span></span> |
| <span data-ttu-id="34f5a-558">区域</span><span class="sxs-lookup"><span data-stu-id="34f5a-558">Region</span></span>             | <span data-ttu-id="34f5a-559">字符串</span><span class="sxs-lookup"><span data-stu-id="34f5a-559">String</span></span>    | <span data-ttu-id="34f5a-560">MSU</span><span class="sxs-lookup"><span data-stu-id="34f5a-560">MSUS</span></span>                      | <span data-ttu-id="34f5a-561">推荐</span><span class="sxs-lookup"><span data-stu-id="34f5a-561">Recommended</span></span> |
| <span data-ttu-id="34f5a-562">InsideCorp</span><span class="sxs-lookup"><span data-stu-id="34f5a-562">InsideCorp</span></span>         | <span data-ttu-id="34f5a-563">Bool</span><span class="sxs-lookup"><span data-stu-id="34f5a-563">Bool</span></span>      | <span data-ttu-id="34f5a-564">1</span><span class="sxs-lookup"><span data-stu-id="34f5a-564">1</span></span>                         | <span data-ttu-id="34f5a-565">必需</span><span class="sxs-lookup"><span data-stu-id="34f5a-565">Required</span></span>    |
| <span data-ttu-id="34f5a-566">ExpressRoute</span><span class="sxs-lookup"><span data-stu-id="34f5a-566">ExpressRoute</span></span>       | <span data-ttu-id="34f5a-567">Bool</span><span class="sxs-lookup"><span data-stu-id="34f5a-567">Bool</span></span>      | <span data-ttu-id="34f5a-568">0</span><span class="sxs-lookup"><span data-stu-id="34f5a-568">0</span></span>                         | <span data-ttu-id="34f5a-569">必需</span><span class="sxs-lookup"><span data-stu-id="34f5a-569">Required</span></span>    |

<span data-ttu-id="34f5a-570">\*时不需要 CQD，模板配置为显示构建和网络名称。</span><span class="sxs-lookup"><span data-stu-id="34f5a-570">\*While not required by CQD, the templates are configured to display Building and Network name.</span></span>

#### <a name="supernetting"></a><span data-ttu-id="34f5a-571">Supernetting</span><span class="sxs-lookup"><span data-stu-id="34f5a-571">Supernetting</span></span>

<span data-ttu-id="34f5a-572">您可以使用 supernetting，通常称作无类别域际路由 (选择 CIDR，) 来代替定义每个子网。</span><span class="sxs-lookup"><span data-stu-id="34f5a-572">You can use supernetting, commonly called Classless Inter-Domain Routing (CIDR,) in place of defining each subnet.</span></span> <span data-ttu-id="34f5a-573">*Supernet*是共享单个路由前缀的几个子网的组合。</span><span class="sxs-lookup"><span data-stu-id="34f5a-573">A *supernet* is a combination of several subnets that share a single routing prefix.</span></span> <span data-ttu-id="34f5a-574">而不是添加的每个子网的项，您可以使用 supernetted/CIDR 地址。</span><span class="sxs-lookup"><span data-stu-id="34f5a-574">Instead of adding an entry for each subnet, you can use the supernetted/CIDR address.</span></span> <span data-ttu-id="34f5a-575">支持 supernetting，但我们不建议使用它。</span><span class="sxs-lookup"><span data-stu-id="34f5a-575">Supernetting is supported, but we don’t recommend using it.</span></span>

<span data-ttu-id="34f5a-576">例如，Contoso 市场营销构建组成下的子网：</span><span class="sxs-lookup"><span data-stu-id="34f5a-576">For example, Contoso’s marketing building is made up of the subnets below:</span></span>

-   <span data-ttu-id="34f5a-577">10.1.0.0/24 – 第 1 层</span><span class="sxs-lookup"><span data-stu-id="34f5a-577">10.1.0.0/24 – first floor</span></span>

-   <span data-ttu-id="34f5a-578">10.1.1.0/24 – 第二层</span><span class="sxs-lookup"><span data-stu-id="34f5a-578">10.1.1.0/24 – second floor</span></span>

-   <span data-ttu-id="34f5a-579">10.1.2.0/24 – 第三层</span><span class="sxs-lookup"><span data-stu-id="34f5a-579">10.1.2.0/24 – third floor</span></span>

-   <span data-ttu-id="34f5a-580">10.1.3.0/24 – 第四 floor</span><span class="sxs-lookup"><span data-stu-id="34f5a-580">10.1.3.0/24 – fourth floor</span></span>

<span data-ttu-id="34f5a-581">而不是添加的每个子网的项，您可以使用 supernetted/CIDR 地址 — 在此示例中，10.1.0.0/22。</span><span class="sxs-lookup"><span data-stu-id="34f5a-581">Instead of adding an entry for each subnet, you can use the supernetted/CIDR address—in this example, 10.1.0.0/22.</span></span>

-   <span data-ttu-id="34f5a-582">网络 = 10.1.0.0</span><span class="sxs-lookup"><span data-stu-id="34f5a-582">Network = 10.1.0.0</span></span>

-   <span data-ttu-id="34f5a-583">网络范围 = 22</span><span class="sxs-lookup"><span data-stu-id="34f5a-583">Network Range = 22</span></span>

<span data-ttu-id="34f5a-584">下面是实现 supernetting 之前应考虑的几个事项：</span><span class="sxs-lookup"><span data-stu-id="34f5a-584">Here are a few things to consider before you implement supernetting:</span></span>

-   <span data-ttu-id="34f5a-585">Supernetting 提前，需要较少的时间，但它代价减少您的数据的丰富功能。</span><span class="sxs-lookup"><span data-stu-id="34f5a-585">Supernetting takes less time up front, but it comes at the cost of reducing the richness of your data.</span></span> <span data-ttu-id="34f5a-586">假设没有质量问题涉及子网 200.1.2.0。</span><span class="sxs-lookup"><span data-stu-id="34f5a-586">Let’s say there’s a quality problem involving subnet 200.1.2.0.</span></span> <span data-ttu-id="34f5a-587">如果您实现 supernetting，您不知道中构建子网的位置或 （例如，实验室） 是哪种类型的网络。</span><span class="sxs-lookup"><span data-stu-id="34f5a-587">If you implemented supernetting, you won’t know where in the building the subnet is located or what type of network it is (for example, a lab).</span></span> <span data-ttu-id="34f5a-588">如果您具有定义生成的所有子网，并上载 floor 位置信息，您可以看到的差异。</span><span class="sxs-lookup"><span data-stu-id="34f5a-588">If you’d defined all the subnets for a building and uploaded floor location information, you’d be able to see that distinction.</span></span>

-   <span data-ttu-id="34f5a-589">请务必确保 supernetted/CIDR 地址正确，且不捕获不需要的子网。</span><span class="sxs-lookup"><span data-stu-id="34f5a-589">It’s important to ensure that the supernetted/CIDR address is correct and isn’t catching unwanted subnets.</span></span>

-   <span data-ttu-id="34f5a-590">Supernetting 可在构建映射到 28 位的 8 位掩码。</span><span class="sxs-lookup"><span data-stu-id="34f5a-590">Supernetting can be used in a building mapping with 8-bit to 28-bit mask.</span></span>

-   <span data-ttu-id="34f5a-591">是非常常见在数据中查找 192.168.0.0。</span><span class="sxs-lookup"><span data-stu-id="34f5a-591">It’s quite common to find 192.168.0.0 in data.</span></span> <span data-ttu-id="34f5a-592">对于许多组织，这表明该用户是在家。</span><span class="sxs-lookup"><span data-stu-id="34f5a-592">For many organizations, this indicates that the user is at home.</span></span> <span data-ttu-id="34f5a-593">对于其他人，这是分支办公地点的 IP 地址方案。</span><span class="sxs-lookup"><span data-stu-id="34f5a-593">For others, this is the IP address scheme for a satellite office.</span></span> <span data-ttu-id="34f5a-594">如果您的组织具有使用此配置的办公室，不要包含该生成文件中，很难区分使用常见的子网家庭和内部网络。</span><span class="sxs-lookup"><span data-stu-id="34f5a-594">If your organization does have offices that use this configuration, don’t include it in your building file as it’s difficult to distinguish between home and internal networks by using common subnets.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="34f5a-595">网络范围可以用于表示 supernet。</span><span class="sxs-lookup"><span data-stu-id="34f5a-595">The network range can be used to represent a supernet.</span></span> <span data-ttu-id="34f5a-596">所有新生成数据文件上载将检查的任何重叠的区域。</span><span class="sxs-lookup"><span data-stu-id="34f5a-596">All new building data file uploads will be checked for any overlapping ranges.</span></span> <span data-ttu-id="34f5a-597">如果先前已上载的生成文件，您应下载当前文件和上载再次来确定任何重叠并修复问题。</span><span class="sxs-lookup"><span data-stu-id="34f5a-597">If you have previously uploaded a building file, you should download the current file and upload it again to identify any overlaps and fix the issue.</span></span> <span data-ttu-id="34f5a-598">重叠之前上载文件的任何情况可能会导致建筑物报告中的子网的错误映射。</span><span class="sxs-lookup"><span data-stu-id="34f5a-598">Any overlap in previously uploaded files might result in the wrong mappings of subnets to buildings in the reports.</span></span> 


#### <a name="vpn"></a><span data-ttu-id="34f5a-599">VPN</span><span class="sxs-lookup"><span data-stu-id="34f5a-599">VPN</span></span>

<span data-ttu-id="34f5a-600">体验质量 (QoE) 数据的客户端发送到 Office 365 — 即 CQD 数据源自 — 包含一个 VPN 标志。</span><span class="sxs-lookup"><span data-stu-id="34f5a-600">The quality of experience (QoE) data that clients send to Office 365—which is where CQD data is sourced from—includes a VPN flag.</span></span> <span data-ttu-id="34f5a-601">但是，此标志依赖于 VPN 供应商的 VPN 网络适配器注册为远程访问适配器到 Windows 报告。</span><span class="sxs-lookup"><span data-stu-id="34f5a-601">However, this flag relies on VPN vendors’ reporting to Windows that the VPN network adapter registered is a Remote Access adapter.</span></span> <span data-ttu-id="34f5a-602">并非所有 VPN 供应商正确都注册远程访问适配器。</span><span class="sxs-lookup"><span data-stu-id="34f5a-602">Not all VPN vendors properly register Remote Access adapters.</span></span> <span data-ttu-id="34f5a-603">因此，您可能无法使用内置的 VPN 查询筛选器。</span><span class="sxs-lookup"><span data-stu-id="34f5a-603">Because of this, you might not be able to use the built-in VPN query filters.</span></span> <span data-ttu-id="34f5a-604">有两种方法适应 VPN 中构建的子网信息文件。</span><span class="sxs-lookup"><span data-stu-id="34f5a-604">There are two approaches to accommodating VPN subnets in the building information file.</span></span>

-   <span data-ttu-id="34f5a-605">在此字段中使用的文本"VPN"，为 VPN 子网定义**网络名称**。</span><span class="sxs-lookup"><span data-stu-id="34f5a-605">Define a **Network Name** by using the text “VPN” in this field for VPN subnets.</span></span>

![呼叫质量仪表板中定义如何创建 VPN 子网报表的屏幕截图](media/quality-of-experience-review-guide-image10.png)

<span data-ttu-id="34f5a-607">_图 10-VPN 使用网络名称_</span><span class="sxs-lookup"><span data-stu-id="34f5a-607">_Figure 10 - VPN using network name_</span></span>

-   <span data-ttu-id="34f5a-608">在此字段中使用的文本"VPN"，为 VPN 子网定义**建筑物名称**。</span><span class="sxs-lookup"><span data-stu-id="34f5a-608">Define a **Building Name** by using the text “VPN” in this field for VPN subnets.</span></span>

![呼叫质量仪表板中定义如何创建构建定义构成 VPN 子报表的屏幕截图。](media/quality-of-experience-review-guide-image11.png)

<span data-ttu-id="34f5a-610">_图 11-使用建筑物名称的 VPN_</span><span class="sxs-lookup"><span data-stu-id="34f5a-610">_Figure 11 - VPN using building name_</span></span>

> [!IMPORTANT]
> <span data-ttu-id="34f5a-611">某些 VPN 实现不准确报告子网信息。</span><span class="sxs-lookup"><span data-stu-id="34f5a-611">Certain VPN implementations don’t accurately report subnet information.</span></span> <span data-ttu-id="34f5a-612">如果在您的报告，我们建议时将 VPN 子网添加到该生成文件，而不是一个条目的子网，将发生这种情况作为单独的 32 位网络的 VPN 子网中添加单独对每个地址条目。</span><span class="sxs-lookup"><span data-stu-id="34f5a-612">If this occurs in your reporting, we recommend that when you add a VPN subnet to the building file, instead of one entry for the subnet, add separate entries for each address in the VPN subnet as a separate 32-bit network.</span></span> <span data-ttu-id="34f5a-613">每行可以有相同的构建元数据。</span><span class="sxs-lookup"><span data-stu-id="34f5a-613">Each row can have the same building metadata.</span></span> <span data-ttu-id="34f5a-614">例如，而不是一个 172.16.18.0/24 行中，您必须 253 行，通过从 172.16.18.1/32 通过 172.16.18.254/32，包括每个地址的一行。</span><span class="sxs-lookup"><span data-stu-id="34f5a-614">For example, instead of one row for 172.16.18.0/24, you have 253 rows, with one row for each address from 172.16.18.1/32 through 172.16.18.254/32, inclusive.</span></span>


> [!NOTE]
> <span data-ttu-id="34f5a-615">已知 VPN 连接错误识别的网络连接，如有线基础的 internet 连接时无线。</span><span class="sxs-lookup"><span data-stu-id="34f5a-615">VPN connections have been known to misidentify the network connection as wired when the underlying internet connection is wireless.</span></span> <span data-ttu-id="34f5a-616">当通过 VPN 连接看质量，您不能假定已准确地发现的连接类型。</span><span class="sxs-lookup"><span data-stu-id="34f5a-616">When looking at quality over VPN connections, you can’t assume that the connection type has been accurately identified.</span></span>

### <a name="uploading-building-information"></a><span data-ttu-id="34f5a-617">上载构建信息</span><span class="sxs-lookup"><span data-stu-id="34f5a-617">Uploading building information</span></span>

<span data-ttu-id="34f5a-618">CQD 摘要报告仪表板包含一个**租户数据上载**的页，通过选择右上角 （查找齿轮图标） 上的**租户数据上载**链接标记访问。</span><span class="sxs-lookup"><span data-stu-id="34f5a-618">The CQD Summary Reports dashboard includes a **Tenant Data Upload** page, accessed by selecting the **Tenant Data Upload** link tag on the upper-right corner (look for the gear icon).</span></span> <span data-ttu-id="34f5a-619">此页用于为 admins 上载他们自己的信息，如映射的 IP 地址和地理信息，映射的每个无线访问点和其 MAC 地址，等等。</span><span class="sxs-lookup"><span data-stu-id="34f5a-619">This page is used for admins to upload their own information, such as mapping of IP address and geographical information, mapping each wireless access point and its MAC address, and so on.</span></span>

1.  <span data-ttu-id="34f5a-620">转到 CQD 联机通过浏览到<https://cqd.lync.com>。</span><span class="sxs-lookup"><span data-stu-id="34f5a-620">Go to CQD Online by browsing to <https://cqd.lync.com>.</span></span>

2.  <span data-ttu-id="34f5a-621">在右上角，选择齿轮图标，然后从**摘要报告**页中选择**租户数据上载**。</span><span class="sxs-lookup"><span data-stu-id="34f5a-621">Select the gear icon in the upper-right corner, and choose **Tenant Data Upload** from the **Summary Reports** page.</span></span>

![呼叫质量仪表板中上载数据时出现的对话框的屏幕截图。](media/quality-of-experience-review-guide-image12.png)

<span data-ttu-id="34f5a-623">_图 12-租户数据上载菜单_</span><span class="sxs-lookup"><span data-stu-id="34f5a-623">_Figure 12 - Tenant Data Upload menu_</span></span>

1.  <span data-ttu-id="34f5a-624">此外，如果这是首次访问 CQD，您将需要上载生成数据。</span><span class="sxs-lookup"><span data-stu-id="34f5a-624">Alternatively, if this is your first time visiting CQD, you’ll be asked to upload building data.</span></span> <span data-ttu-id="34f5a-625">您可以**立即上载**迅速导航至**租户数据上载**页上选择。</span><span class="sxs-lookup"><span data-stu-id="34f5a-625">You can select **Upload Now** to quickly navigate to the **Tenant Data Upload** page.</span></span>

![呼叫质量仪表板中通知用户上载生成数据的横幅的屏幕截图。](media/quality-of-experience-review-guide-image13.png)

<span data-ttu-id="34f5a-627">_图 13-构建数据上载横幅_</span><span class="sxs-lookup"><span data-stu-id="34f5a-627">_Figure 13 - Building data upload banner_</span></span>

1.  <span data-ttu-id="34f5a-628">在**租户数据上载**页上，选择**浏览**选择数据文件。</span><span class="sxs-lookup"><span data-stu-id="34f5a-628">On the **Tenant Data Upload** page, select **Browse** to choose a data file.</span></span>

2.  <span data-ttu-id="34f5a-629">在选择数据文件之后, 指定**开始日期**和 （可选） 指定结束日期。</span><span class="sxs-lookup"><span data-stu-id="34f5a-629">After selecting a data file, specify **Start date** and, optionally, specify an end date.</span></span>

3.  <span data-ttu-id="34f5a-630">选择后**开始日期**，选择**上载**以将文件上载到 CQD。</span><span class="sxs-lookup"><span data-stu-id="34f5a-630">After selecting **Start date**, select **Upload** to upload the file to the CQD.</span></span> <br><br><span data-ttu-id="34f5a-631">上载文件之前，对其进行验证。</span><span class="sxs-lookup"><span data-stu-id="34f5a-631">Before the file is uploaded, it’s validated.</span></span> <span data-ttu-id="34f5a-632">如果验证失败，请求您更正文件显示一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="34f5a-632">If validation fails, an error message is displayed requesting that you correct the file.</span></span> <span data-ttu-id="34f5a-633">下图显示在数据文件中的列数不正确时出现错误。</span><span class="sxs-lookup"><span data-stu-id="34f5a-633">The following figure shows an error occurring when the number of columns in the data file is incorrect.</span></span>

![呼叫质量仪表板中的导入构建数据时介绍一条错误消息对话框的屏幕截图。](media/quality-of-experience-review-guide-image14.png)

<span data-ttu-id="34f5a-635">_图 14-构建数据上载错误_</span><span class="sxs-lookup"><span data-stu-id="34f5a-635">_Figure 14 - Building data upload error_</span></span>

4.  <span data-ttu-id="34f5a-636">如果验证过程中不发生任何错误，将会成功上载文件。</span><span class="sxs-lookup"><span data-stu-id="34f5a-636">If no errors occur during validation, the file upload will succeed.</span></span> <span data-ttu-id="34f5a-637">您随后可以看到**我上载**表，其中显示所有上载文件的完整列表，该页面底部当前租户中上载的数据文件。</span><span class="sxs-lookup"><span data-stu-id="34f5a-637">You can then see the uploaded data file in the **My uploads** table, which shows the full list of all uploaded files for the current tenant at the bottom of that page.</span></span>

> [!NOTE]
> <span data-ttu-id="34f5a-638">可能需要四个小时完成处理的生成文件。</span><span class="sxs-lookup"><span data-stu-id="34f5a-638">It can take up to four hours to finish processing the building file.</span></span> <br><br> <span data-ttu-id="34f5a-639">如果您已上载的生成文件，而需要添加子网可能已丢失或排除，通过添加新的子网中修改的原始文件，删除当前文件，并重新上载新编辑过的文件。</span><span class="sxs-lookup"><span data-stu-id="34f5a-639">If you’ve already uploaded a building file and need to add subnets that might have been missed or excluded, modify the original file by adding the new subnets, remove the current file, and re-upload the newly edited file.</span></span> <span data-ttu-id="34f5a-640">可以有一个活动生成 CQD 中的数据文件。</span><span class="sxs-lookup"><span data-stu-id="34f5a-640">There can be only one active building data file in CQD.</span></span> 

### <a name="missing-subnets"></a><span data-ttu-id="34f5a-641">缺少的子网</span><span class="sxs-lookup"><span data-stu-id="34f5a-641">Missing subnets</span></span>

<span data-ttu-id="34f5a-642">上载托管网络的构建信息后每个托管的网络应有构建关联。</span><span class="sxs-lookup"><span data-stu-id="34f5a-642">After uploading building information for managed networks, every managed network should have a building association.</span></span> <span data-ttu-id="34f5a-643">但是，这并不总是大小写;通常情况下，会丢失一些子网。</span><span class="sxs-lookup"><span data-stu-id="34f5a-643">However, this isn’t always the case; typically, a few subnets are missed.</span></span> <span data-ttu-id="34f5a-644">本节介绍如何验证这些缺少的网络。</span><span class="sxs-lookup"><span data-stu-id="34f5a-644">This section covers how to validate those missing networks.</span></span>

<span data-ttu-id="34f5a-645">浏览到 CQD Online 中的**详细的报告**页面，并导航到 CQD 模板中包括**缺少子网报告**。</span><span class="sxs-lookup"><span data-stu-id="34f5a-645">Browse to the **Detailed Reports** page in CQD Online and navigate to the **Missing Subnet Report** included in the CQD templates.</span></span> <span data-ttu-id="34f5a-646">此提供与未定义中构建的 10 或更多音频流的所有子网数据文件。</span><span class="sxs-lookup"><span data-stu-id="34f5a-646">This presents all the subnets with 10 or more audio streams that are not defined in the building data file.</span></span> <span data-ttu-id="34f5a-647">确保在此列表中没有托管的网络。</span><span class="sxs-lookup"><span data-stu-id="34f5a-647">Ensure that there are no managed networks in this list.</span></span> <span data-ttu-id="34f5a-648">如果子网丢失，更新原始构建数据文件并将其重新上载到 CQD。</span><span class="sxs-lookup"><span data-stu-id="34f5a-648">If subnets are missing, update the original building data file and re-upload it to CQD.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="34f5a-649">您需要将您的租户 ID 作为**第二个租户 ID**的查询筛选器添加到此报告可以筛选报表，以只查看您的组织的租户数据。</span><span class="sxs-lookup"><span data-stu-id="34f5a-649">You’ll need to add your tenant ID as a query filter for **Second Tenant ID** to this report to filter the report to view only your organization’s tenant data.</span></span> <span data-ttu-id="34f5a-650">否则，报告将显示联合的子网。</span><span class="sxs-lookup"><span data-stu-id="34f5a-650">Otherwise, the report will show federated subnets.</span></span>

> [!NOTE] 
> <span data-ttu-id="34f5a-651">一定要调整到本月的月年报告筛选器。</span><span class="sxs-lookup"><span data-stu-id="34f5a-651">Be sure to adjust the Month Year report filter to the current month.</span></span> <span data-ttu-id="34f5a-652">选择**编辑**，然后调整**月年**报告筛选器，以保存新默认的月份。</span><span class="sxs-lookup"><span data-stu-id="34f5a-652">Select **Edit**, and adjust the **Month Year** report filter to save the new default month.</span></span>                                                  |

![报告显示未包括在 CQD 构建数据文件的显示使用情况的子网。](media/quality-of-experience-review-guide-image15.png)

<span data-ttu-id="34f5a-654">_图 15-丢失生成报表_</span><span class="sxs-lookup"><span data-stu-id="34f5a-654">_Figure 15 - Missing Building Report_</span></span>

## <a name="reliability-investigations"></a><span data-ttu-id="34f5a-655">可靠性调查</span><span class="sxs-lookup"><span data-stu-id="34f5a-655">Reliability investigations</span></span>

<span data-ttu-id="34f5a-656">提高质量的第一步是在组织内评估音频可靠性的状态。</span><span class="sxs-lookup"><span data-stu-id="34f5a-656">The first step to improving quality is to assess the state of audio reliability across the organization.</span></span> <span data-ttu-id="34f5a-657">音频可靠性至关重要良好的用户体验，因为我们开始测量可靠性的两个组件：</span><span class="sxs-lookup"><span data-stu-id="34f5a-657">Because audio reliability is vital to a positive user experience, we start with the two components that measure reliability:</span></span>

1.  <span data-ttu-id="34f5a-658">**呼叫安装失败：** 无法建立会话。</span><span class="sxs-lookup"><span data-stu-id="34f5a-658">**Call Setup Failures:** Session couldn’t be established.</span></span>

2.  <span data-ttu-id="34f5a-659">**呼叫投递失败：** 建立和意外终止会话</span><span class="sxs-lookup"><span data-stu-id="34f5a-659">**Call Drop Failures:** Session was established and unexpectedly terminated</span></span>

<span data-ttu-id="34f5a-660">整个此部分中，我们将介绍方法来进行调查这两个区域。</span><span class="sxs-lookup"><span data-stu-id="34f5a-660">Throughout this section, we’ll cover methods to investigate both areas.</span></span>

> [!NOTE]
> <span data-ttu-id="34f5a-661">在本指南中介绍的模板中包含的不是所有报告。</span><span class="sxs-lookup"><span data-stu-id="34f5a-661">Not all reports included in the templates are covered in this guide.</span></span> <span data-ttu-id="34f5a-662">请参阅单个报表说明的详细信息。</span><span class="sxs-lookup"><span data-stu-id="34f5a-662">Please refer to the individual report description for more information.</span></span>


### <a name="call-setup"></a><span data-ttu-id="34f5a-663">呼叫设置</span><span class="sxs-lookup"><span data-stu-id="34f5a-663">Call setup</span></span>

<span data-ttu-id="34f5a-664">优先此区域中的补救呼叫安装失败，因为这些失败的用户体验产生重大负面影响。</span><span class="sxs-lookup"><span data-stu-id="34f5a-664">Prioritize remediating call setup failures in this area first, because these failures have a significant negative impact on the user experience.</span></span>

<span data-ttu-id="34f5a-665">首先调查评估组织的总体呼叫安装失败的百分比，然后设置其优先级的调查基于最高的百分比构建或网络区域。</span><span class="sxs-lookup"><span data-stu-id="34f5a-665">Begin your investigation by assessing the percentage of overall call setup failures for the organization, and then prioritize areas of investigation based on the highest percentage by building or network.</span></span>

#### <a name="call-setup-failures-overall"></a><span data-ttu-id="34f5a-666">调用总体安装失败</span><span class="sxs-lookup"><span data-stu-id="34f5a-666">Call setup failures overall</span></span>

<span data-ttu-id="34f5a-667">此图表报表显示设置的成功调用的总数，并调用随着时间的推移的安装程序失败。</span><span class="sxs-lookup"><span data-stu-id="34f5a-667">This chart report displays the total amount of successful call set up and call setup failures over time.</span></span> <span data-ttu-id="34f5a-668">指向要显示其单个值的列中的任何一个，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="34f5a-668">Point to any one of the columns to display its individual values, as shown in the figure below.</span></span>

![显示的音频呼叫流安装失败百分比的图表的屏幕截图](media/quality-of-experience-review-guide-image16.png)

<span data-ttu-id="34f5a-670">_图 16-音频可靠性-呼叫流安装失败_</span><span class="sxs-lookup"><span data-stu-id="34f5a-670">_Figure 16 - Audio Reliability - Call Stream Setup Failures_</span></span>

##### <a name="analysis"></a><span data-ttu-id="34f5a-671">分析</span><span class="sxs-lookup"><span data-stu-id="34f5a-671">Analysis</span></span>

<span data-ttu-id="34f5a-672">此报表显示随着时间的推移贵组织的音频呼叫安装程序使用情况和失败。</span><span class="sxs-lookup"><span data-stu-id="34f5a-672">This report displays your organization’s audio call setup usage and failures over time.</span></span> <span data-ttu-id="34f5a-673">通过使用此报告，您可以回答以下问题和确定您的操作的下一过程：</span><span class="sxs-lookup"><span data-stu-id="34f5a-673">By using this report, you can answer the following questions and determine your next course of action:</span></span>

1.  <span data-ttu-id="34f5a-674">什么是当前月份的总呼叫安装失败百分比？</span><span class="sxs-lookup"><span data-stu-id="34f5a-674">What is the total call setup failure percentage for the current month?</span></span>

2.  <span data-ttu-id="34f5a-675">是总呼叫安装失败百分比低于或高于定义的目标指标？</span><span class="sxs-lookup"><span data-stu-id="34f5a-675">Is the total call setup failure percentage below or above the defined target metric?</span></span>

3.  <span data-ttu-id="34f5a-676">严重或优于上个月是故障趋势？</span><span class="sxs-lookup"><span data-stu-id="34f5a-676">Is the failure trend worse or better than the previous month?</span></span>

4.  <span data-ttu-id="34f5a-677">故障趋势增加，steady，或减少？</span><span class="sxs-lookup"><span data-stu-id="34f5a-677">Is the failure trend increasing, steady, or decreasing?</span></span>

<span data-ttu-id="34f5a-678">此报告中提供的信息将告知您的总体呼叫设置您的组织内出现故障的频率的案例。</span><span class="sxs-lookup"><span data-stu-id="34f5a-678">The information presented in this report will tell the story of how often your overall call setups are failing across your organization.</span></span>

<span data-ttu-id="34f5a-679">以前的解答，不管花时间来进行调查进一步使用包含子报表以查找任何单个建筑或可能需要修复的网络。</span><span class="sxs-lookup"><span data-stu-id="34f5a-679">Irrespective of the previous answers, take the time to investigate further by using the included sub-reports to look for any individual buildings or networks that might need remediation.</span></span> <span data-ttu-id="34f5a-680">尽管总体失败率可能是下面目标指标，通常为一个或多个建筑或网络故障率之上指标，需要进行修复。</span><span class="sxs-lookup"><span data-stu-id="34f5a-680">Although the overall failure rate might be below the target metric, often the failure rates for one or more buildings or networks are above the metric and need remediation.</span></span>

#### <a name="call-setup-failures-by-building-and-subnet"></a><span data-ttu-id="34f5a-681">通过生成和子网呼叫安装失败</span><span class="sxs-lookup"><span data-stu-id="34f5a-681">Call setup failures by building and subnet</span></span> 

<span data-ttu-id="34f5a-682">此表报告用于发现并隔离任何建筑或需要修复的网络。</span><span class="sxs-lookup"><span data-stu-id="34f5a-682">This table report is used to discover and isolate any buildings or networks that need remediation.</span></span>

> [!NOTE]
> <span data-ttu-id="34f5a-683">一定要调整到本月的月年报告筛选器。</span><span class="sxs-lookup"><span data-stu-id="34f5a-683">Be sure to adjust the Month Year report filter to the current month.</span></span> <span data-ttu-id="34f5a-684">选择**编辑**，然后调整**月年**报告筛选器，以保存新默认的月份。</span><span class="sxs-lookup"><span data-stu-id="34f5a-684">Select **Edit**, and adjust the **Month Year** report filter to save the new default month.</span></span>


![报告列表呼叫安装失败原因，按构建、 网络和每月的子网。](media/quality-of-experience-review-guide-image17.png)

<span data-ttu-id="34f5a-686">_图 17-通过生成的音频设置失败或子网_</span><span class="sxs-lookup"><span data-stu-id="34f5a-686">_Figure 17 - Audio Setup Failures by Building or Subnet_</span></span>

##### <a name="remediation"></a><span data-ttu-id="34f5a-687">修正</span><span class="sxs-lookup"><span data-stu-id="34f5a-687">Remediation</span></span> 

<span data-ttu-id="34f5a-688">关注您建筑或首先，具有的最大失败量，因为这将最大限度地对用户体验的影响，并帮助快速减少组织的呼叫安装失败的子网的修复措施。</span><span class="sxs-lookup"><span data-stu-id="34f5a-688">Focus your remediation efforts on buildings or subnets that have the largest volume of failures first, because this will maximize impact to the user experience and help to quickly reduce the organizational call setup failures.</span></span>
<span data-ttu-id="34f5a-689">下表列出两个呼叫安装失败原因由 CQD 报告。</span><span class="sxs-lookup"><span data-stu-id="34f5a-689">The following table lists the two reasons for call setup failures as reported by CQD.</span></span>

<span data-ttu-id="34f5a-690">_表 6 – 呼叫安装失败的原因_</span><span class="sxs-lookup"><span data-stu-id="34f5a-690">_Table 6 – Reasons for Call Setup Failures_</span></span>

| <span data-ttu-id="34f5a-691">调用安装失败原因</span><span class="sxs-lookup"><span data-stu-id="34f5a-691">Call Setup Failures reason</span></span>                       | <span data-ttu-id="34f5a-692">典型的原因</span><span class="sxs-lookup"><span data-stu-id="34f5a-692">Typical cause</span></span>                                                                                                                                                                                                                                                                                   |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="34f5a-693">缺少 FW 深入数据包检查例外规则</span><span class="sxs-lookup"><span data-stu-id="34f5a-693">Missing FW Deep Packet Inspection Exemption Rule</span></span> | <span data-ttu-id="34f5a-694">指示沿路径的网络设备的建立由于深入包检查规则阻止的媒体路径。</span><span class="sxs-lookup"><span data-stu-id="34f5a-694">Indicates that network equipment along the path prevented the media path from being established due to deep packet inspection rules.</span></span> <span data-ttu-id="34f5a-695">这可能是因为未正确配置的防火墙规则。</span><span class="sxs-lookup"><span data-stu-id="34f5a-695">This is likely due to firewall rules not being correctly configured.</span></span> <span data-ttu-id="34f5a-696">在这种情况下 TCP 握手成功，但 SSL 握手没有。</span><span class="sxs-lookup"><span data-stu-id="34f5a-696">In this case the TCP handshake succeeded but the SSL handshake did not.</span></span>               |
| <span data-ttu-id="34f5a-697">缺少 FW IP 阻止例外规则</span><span class="sxs-lookup"><span data-stu-id="34f5a-697">Missing FW IP Block Exception Rule</span></span>               | <span data-ttu-id="34f5a-698">指示沿路径的网络设备的建立到 Office 365 网络阻止的媒体路径。</span><span class="sxs-lookup"><span data-stu-id="34f5a-698">Indicates that network equipment along the path prevented the media path from being established to the Office 365 network.</span></span> <span data-ttu-id="34f5a-699">这可能是由于不允许访问 IP 地址和端口用于个团队和 Skype 业务通信正确配置代理服务器或防火墙规则。</span><span class="sxs-lookup"><span data-stu-id="34f5a-699">This might be due to proxy or firewall rules not being correctly configured to allow access to IP addresses and ports used for Teams and Skype for Business traffic.</span></span> |

<span data-ttu-id="34f5a-700">现在您修正开始时，您可以将精力上特定构建或子网。</span><span class="sxs-lookup"><span data-stu-id="34f5a-700">Now as you begin your remediation, you can focus your efforts on a particular building or subnet.</span></span> <span data-ttu-id="34f5a-701">如前面的表所示，这些问题是由于防火墙或代理的配置。</span><span class="sxs-lookup"><span data-stu-id="34f5a-701">As the preceding table shows, these issues are due to firewall or proxy configurations.</span></span> <span data-ttu-id="34f5a-702">查看修正操作下表中的选项。</span><span class="sxs-lookup"><span data-stu-id="34f5a-702">Review the options in the following table for remediation actions.</span></span>

<span data-ttu-id="34f5a-703">_表 7-呼叫的后续步骤安装失败修正_</span><span class="sxs-lookup"><span data-stu-id="34f5a-703">_Table 7 - Next Steps for Call Setup Failure Remediation_</span></span>

| <span data-ttu-id="34f5a-704">修正</span><span class="sxs-lookup"><span data-stu-id="34f5a-704">Remediation</span></span>           | <span data-ttu-id="34f5a-705">指南</span><span class="sxs-lookup"><span data-stu-id="34f5a-705">Guidance</span></span>     |
|-----------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="34f5a-706">配置防火墙</span><span class="sxs-lookup"><span data-stu-id="34f5a-706">Configure firewall(s)</span></span> | <span data-ttu-id="34f5a-707">与网络团队合作，并确认您针对[Office 365 IP 地址列表](https://aka.ms/o365ips)的防火墙配置。</span><span class="sxs-lookup"><span data-stu-id="34f5a-707">Work with your network team and verify your firewall(s) configuration against [the Office 365 IP address list](https://aka.ms/o365ips).</span></span> <span data-ttu-id="34f5a-708">确认的防火墙规则包含[媒体子网](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams)和端口。</span><span class="sxs-lookup"><span data-stu-id="34f5a-708">Verify that the [media subnets](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams) and ports are included in the firewall rules.</span></span> <span data-ttu-id="34f5a-709">验证在防火墙中打开所需的 TCP 和 UDP 端口。</span><span class="sxs-lookup"><span data-stu-id="34f5a-709">Verify that the necessary TCP and UDP ports are opened in the firewall.</span></span> <span data-ttu-id="34f5a-710">媒体 over TCP 喜欢 UDP。</span><span class="sxs-lookup"><span data-stu-id="34f5a-710">Media prefers UDP over TCP.</span></span> <span data-ttu-id="34f5a-711">TCP 被视为故障回复协议。</span><span class="sxs-lookup"><span data-stu-id="34f5a-711">TCP is considered a failback protocol.</span></span><br><ul><li><span data-ttu-id="34f5a-712">**TCP:** 端口 443</span><span class="sxs-lookup"><span data-stu-id="34f5a-712">**TCP:** port 443</span></span></li><li><span data-ttu-id="34f5a-713">**UDP:** 端口 3478 – 3481</span><span class="sxs-lookup"><span data-stu-id="34f5a-713">**UDP:** ports 3478–3481</span></span></li><ul> |
| <span data-ttu-id="34f5a-714">验证</span><span class="sxs-lookup"><span data-stu-id="34f5a-714">Verify</span></span>                | <span data-ttu-id="34f5a-715">利用[Microsoft 网络评估工具](https://www.microsoft.com/download/details.aspx?id=53885)使用连接检查函数验证在受影响的构建或子网的连接。</span><span class="sxs-lookup"><span data-stu-id="34f5a-715">Leverage the [Microsoft Network Assessment Tool](https://www.microsoft.com/download/details.aspx?id=53885) to verify connectivity from the affected building or subnet by using the connectivity check function.</span></span>    |


### <a name="call-drop"></a><span data-ttu-id="34f5a-716">呼叫拖放</span><span class="sxs-lookup"><span data-stu-id="34f5a-716">Call drop</span></span>

<span data-ttu-id="34f5a-717">与不同呼叫安装失败，没有任何原因代码，以指示为什么呼叫而丢弃故障发生，这将使隔离特定根源变得比较困难。</span><span class="sxs-lookup"><span data-stu-id="34f5a-717">Unlike call setup failures, there is no reason code to indicate why call dropped failures occurred, which makes it difficult to isolate a specific root cause.</span></span> <span data-ttu-id="34f5a-718">若要更好地会审丢弃的呼叫，使用推测的方法。</span><span class="sxs-lookup"><span data-stu-id="34f5a-718">To better triage dropped calls, use an inferred approach.</span></span> <span data-ttu-id="34f5a-719">通过补救感兴趣的音频的任何区域、 修补客户端，并个团队和 Skype 的业务驱动的认证的设备的使用情况，您希望拒绝而丢弃的调用失败。</span><span class="sxs-lookup"><span data-stu-id="34f5a-719">By remediating any areas of interest for audio, patching clients, and driving usage of certified devices for Teams and Skype for Business, you’d expect call dropped failures to decline.</span></span>

#### <a name="call-drop-failures-overall"></a><span data-ttu-id="34f5a-720">调用总体投递失败</span><span class="sxs-lookup"><span data-stu-id="34f5a-720">Call drop failures overall</span></span>

<span data-ttu-id="34f5a-721">此图表报告显示音频流，而丢弃的总音频流的总量以及总流而丢弃的百分比。</span><span class="sxs-lookup"><span data-stu-id="34f5a-721">This chart report displays the total amount of audio streams, total audio streams dropped, and total stream dropped percentage.</span></span> <span data-ttu-id="34f5a-722">指向要显示其值的列中的任何一个，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="34f5a-722">Point to any one of the columns to display its values, as shown in the following figure.</span></span>

![图表显示音频呼叫流丢弃所占屏幕截图](media/quality-of-experience-review-guide-image18.png)

<span data-ttu-id="34f5a-724">_图 18 的总呼叫而丢弃失败百分比_</span><span class="sxs-lookup"><span data-stu-id="34f5a-724">_Figure 18 - Total call dropped failure percentage_</span></span>

##### <a name="analysis"></a><span data-ttu-id="34f5a-725">分析</span><span class="sxs-lookup"><span data-stu-id="34f5a-725">Analysis</span></span>

<span data-ttu-id="34f5a-726">此图表报表显示随时间相关呼叫断开贵组织的用法和失败。</span><span class="sxs-lookup"><span data-stu-id="34f5a-726">This chart report displays your organization’s usage and failures over time related to call drops.</span></span> <span data-ttu-id="34f5a-727">通过使用此报告，您可以回答以下问题：</span><span class="sxs-lookup"><span data-stu-id="34f5a-727">By using this report, you can answer the following questions:</span></span>

1.  <span data-ttu-id="34f5a-728">什么是当前的总呼叫而丢弃百分比？</span><span class="sxs-lookup"><span data-stu-id="34f5a-728">What is the current total call dropped percentage?</span></span>

2.  <span data-ttu-id="34f5a-729">总百分比低于定义的目标指标？</span><span class="sxs-lookup"><span data-stu-id="34f5a-729">Is the total drop percentage below the defined target metric?</span></span>

3.  <span data-ttu-id="34f5a-730">严重或优于上个月是故障趋势？</span><span class="sxs-lookup"><span data-stu-id="34f5a-730">Is the failure trend worse or better than the previous month?</span></span>

4.  <span data-ttu-id="34f5a-731">故障趋势增加，steady，或减少？</span><span class="sxs-lookup"><span data-stu-id="34f5a-731">Is the failure trend increasing, steady, or decreasing?</span></span>

<span data-ttu-id="34f5a-732">此报告中提供的信息会告诉您总体呼叫断开频率出现在整个组织的案例。</span><span class="sxs-lookup"><span data-stu-id="34f5a-732">The information presented in this report can tell the story of how often your overall call drops are occurring across your organization.</span></span>

<span data-ttu-id="34f5a-733">不管上面的问题的答案花时间来进行调查使用子报表以查找任何建筑或可能需要修复的网络。</span><span class="sxs-lookup"><span data-stu-id="34f5a-733">Irrespective of the answers to the questions above, take the time to investigate using the sub-reports to look for any buildings or networks that might need remediation.</span></span> <span data-ttu-id="34f5a-734">尽管总体投递率可能是下面目标指标，通常为一个或多个建筑或网络的投递速率超过指标和需要修复。</span><span class="sxs-lookup"><span data-stu-id="34f5a-734">Although the overall drop rate might be below the target metric, often the drop rate for one or more buildings or networks is above the metric and needs remediation.</span></span>

#### <a name="call-drop-failures-by-building-or-subnet"></a><span data-ttu-id="34f5a-735">通过在生成或子网呼叫投递失败</span><span class="sxs-lookup"><span data-stu-id="34f5a-735">Call drop failures by building or subnet</span></span>

<span data-ttu-id="34f5a-736">指示此表报告中的失败的呼叫已被意外删除，并导致负用户体验。</span><span class="sxs-lookup"><span data-stu-id="34f5a-736">Failures in this table report indicate that the call was dropped unexpectedly and resulted in a negative user experience.</span></span> <span data-ttu-id="34f5a-737">有两个表报告中的模板，一个用于调查会议和另一个用于两方包含。</span><span class="sxs-lookup"><span data-stu-id="34f5a-737">There are two table reports included in the template, one for investigating conferencing and the other for two-party.</span></span>

> [!NOTE]
> <span data-ttu-id="34f5a-738">请务必调整到当前月份月年筛选器。</span><span class="sxs-lookup"><span data-stu-id="34f5a-738">Be sure to adjust the Month Year filter to the current month.</span></span> <span data-ttu-id="34f5a-739">选择**编辑**，然后调整**月年**保存新默认的月份。</span><span class="sxs-lookup"><span data-stu-id="34f5a-739">Select **Edit**, and adjust **Month Year** to save the new default month.</span></span>


![报告按构建、 网络和每月的子网组织列表编号和丢弃呼叫的百分比。](media/quality-of-experience-review-guide-image19.png)

<span data-ttu-id="34f5a-741">_构建或子网的图 19 – 音频呼叫而丢弃失败_</span><span class="sxs-lookup"><span data-stu-id="34f5a-741">_Figure 19 – Audio call dropped failures by building or subnet_</span></span>

##### <a name="remediation"></a><span data-ttu-id="34f5a-742">修正</span><span class="sxs-lookup"><span data-stu-id="34f5a-742">Remediation</span></span>

<span data-ttu-id="34f5a-743">使用前面的表报表，您可以现在隔离"热点"托管呼叫断开发生上方的定义的目标指标的网络中。</span><span class="sxs-lookup"><span data-stu-id="34f5a-743">Using the preceding table report, you can now isolate “hot spots” in the managed network where call drops occur above the defined target metric.</span></span> <span data-ttu-id="34f5a-744">关注您建筑或首先，具有最高总流计数，以便最大的影响的网络上的修复措施。</span><span class="sxs-lookup"><span data-stu-id="34f5a-744">Focus your remediation efforts on buildings or networks that have the highest total stream count first, to make the biggest impact.</span></span>

<span data-ttu-id="34f5a-745">呼叫下降的常见原因：</span><span class="sxs-lookup"><span data-stu-id="34f5a-745">Common causes of call drops:</span></span>

-   <span data-ttu-id="34f5a-746">下设置网络或 internet 出口</span><span class="sxs-lookup"><span data-stu-id="34f5a-746">Under-provisioned network or internet egress</span></span>

-   <span data-ttu-id="34f5a-747">配置受约束的网络上没有 QoS</span><span class="sxs-lookup"><span data-stu-id="34f5a-747">No QoS configured on constrained networks</span></span>

-   <span data-ttu-id="34f5a-748">旧客户端版本</span><span class="sxs-lookup"><span data-stu-id="34f5a-748">Older client versions</span></span>

-   <span data-ttu-id="34f5a-749">用户行为</span><span class="sxs-lookup"><span data-stu-id="34f5a-749">User behavior</span></span>

<span data-ttu-id="34f5a-750">发现热点后，您可以利用[呼叫分析](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309)进一步查看该生成的具体问题中的用户。</span><span class="sxs-lookup"><span data-stu-id="34f5a-750">After you discover hot spots, you can leverage [Call Analytics](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309) to further review users in that building for specific issues.</span></span> <span data-ttu-id="34f5a-751">呼叫分析包含 PII 数据，可用于进一步隔离呼叫断开的可能原因。</span><span class="sxs-lookup"><span data-stu-id="34f5a-751">Call Analytics contains PII data and can be useful for further isolating potential reasons for the call drops.</span></span>

<span data-ttu-id="34f5a-752">无论您下一步，最好通知帮助台已与特定建筑或子网发现的问题。</span><span class="sxs-lookup"><span data-stu-id="34f5a-752">Regardless of your next step, it’s a good practice to notify the helpdesk that an issue has been discovered with specific buildings or subnets.</span></span> <span data-ttu-id="34f5a-753">这种方式，可以快速地响应传入呼叫并更有效地会审用户。</span><span class="sxs-lookup"><span data-stu-id="34f5a-753">This way, they can quickly respond to incoming calls and triage users more efficiently.</span></span> <span data-ttu-id="34f5a-754">然后可以向工程团队进行进一步调查后报告已标记的用户。</span><span class="sxs-lookup"><span data-stu-id="34f5a-754">Flagged users can then be reported back to the engineering team for further investigation.</span></span>

<span data-ttu-id="34f5a-755">下表列出了一些常见方法管理和修正呼叫下降。</span><span class="sxs-lookup"><span data-stu-id="34f5a-755">The following table lists some common methods to manage and remediate call drops.</span></span>

<span data-ttu-id="34f5a-756">_表 9-呼叫的后续步骤放置修正_</span><span class="sxs-lookup"><span data-stu-id="34f5a-756">_Table 9 - Next steps for call drop remediation_</span></span>

| <span data-ttu-id="34f5a-757">修正</span><span class="sxs-lookup"><span data-stu-id="34f5a-757">Remediation</span></span>                              | <span data-ttu-id="34f5a-758">指南</span><span class="sxs-lookup"><span data-stu-id="34f5a-758">Guidance</span></span>     |
|------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="34f5a-759">网络/internet</span><span class="sxs-lookup"><span data-stu-id="34f5a-759">Network/internet</span></span>                         | <span data-ttu-id="34f5a-760">既然您知道哪些构建的影响，使用您的网络团队监视在该生成，以确定是否存在问题过度使用带宽。</span><span class="sxs-lookup"><span data-stu-id="34f5a-760">Now that you know which building is affected, work with your network team to monitor bandwidth at that building to determine whether there are issues with overutilization.</span></span> <span data-ttu-id="34f5a-761">如果发现问题时网络拥塞相关，请考虑该构建增加带宽。</span><span class="sxs-lookup"><span data-stu-id="34f5a-761">If the issue is discovered to be related to network congestion, consider increasing bandwidth to that building.</span></span> <br><br><span data-ttu-id="34f5a-762">**QoS:** 如果增加带宽意思或成本上不可行，请考虑实现 QoS。</span><span class="sxs-lookup"><span data-stu-id="34f5a-762">**QoS:** If increasing bandwidth is impossible or cost-prohibitive, consider implementing QoS.</span></span> <span data-ttu-id="34f5a-763">这将确保托管网络上的媒体数据包的优先级别是上方非媒体流量。</span><span class="sxs-lookup"><span data-stu-id="34f5a-763">This will guarantee media packets on the managed network are prioritized above non-media traffic.</span></span> <span data-ttu-id="34f5a-764">此外，如果不清除证据的带宽有原因，请考虑这些解决方案：</span><span class="sxs-lookup"><span data-stu-id="34f5a-764">Alternatively, if there is no clear evidence that bandwidth is the culprit, consider these solutions:</span></span><br><ul><li>[<span data-ttu-id="34f5a-765">Microsoft 团队 QoS 指南</span><span class="sxs-lookup"><span data-stu-id="34f5a-765">Microsoft Teams QoS Guidance</span></span>](https://docs.microsoft.com/MicrosoftTeams/qos-in-teams)</li><li>[<span data-ttu-id="34f5a-766">Skype 的业务 QoS 指南</span><span class="sxs-lookup"><span data-stu-id="34f5a-766">Skype for Business QoS Guidance</span></span>](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_8)</li></ul><br><span data-ttu-id="34f5a-767">**执行网络准备情况评估：** 网络评估提供了有关预期的带宽使用情况的详细信息、 如何应对带宽和网络发生更改，以及建议个团队和 Skype for Business 的网络的做法。</span><span class="sxs-lookup"><span data-stu-id="34f5a-767">**Perform a network readiness assessment:** A network assessment provides details about expected bandwidth usage, how to cope with bandwidth and network changes, and recommended networking practices for Teams and Skype for Business.</span></span> <span data-ttu-id="34f5a-768">使用上表作为您的源，必须建筑或子网的最佳候选人评估的列表。</span><span class="sxs-lookup"><span data-stu-id="34f5a-768">Using the preceding table as your source, you have a list of buildings or subnets that are excellent candidates for an assessment.</span></span> <br><ul><li>[<span data-ttu-id="34f5a-769">Microsoft 团队网络准备情况评估</span><span class="sxs-lookup"><span data-stu-id="34f5a-769">Microsoft Teams Network Readiness Assessment</span></span>](https://docs.microsoft.com/MicrosoftTeams/3-envision-evaluate-my-environment#test-the-network)</li><li>[<span data-ttu-id="34f5a-770">Skype 的业务网络准备情况评估</span><span class="sxs-lookup"><span data-stu-id="34f5a-770">Skype for Business Network Readiness Assessment</span></span>](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers/?pageState=NetworkReadiness)</li></ul><br><span data-ttu-id="34f5a-771">**Microsoft 网络评估工具：** 简单的网络性能测试中使用此工具可确定网络团队将执行程度或 Skype 业务联机呼叫。</span><span class="sxs-lookup"><span data-stu-id="34f5a-771">**Microsoft Network Assessment Tool:** Use this tool for a simple test of network performance to determine how well the network would perform for a Teams or Skype for Business Online call.</span></span> <span data-ttu-id="34f5a-772">此工具可帮助您评估子网的性能和验证针对 Microsoft 性能[要求](https://aka.ms/performancerequirements)的网络的准备。</span><span class="sxs-lookup"><span data-stu-id="34f5a-772">The tool helps you assess the performance of a subnet and validate the readiness of the network against Microsoft performance [requirements](https://aka.ms/performancerequirements).</span></span><ul><li>[<span data-ttu-id="34f5a-773">下载网络评估工具</span><span class="sxs-lookup"><span data-stu-id="34f5a-773">Download the Network Assessment Tool</span></span>](https://www.microsoft.com/download/details.aspx?id=53885)</li></ul>         |
| <span data-ttu-id="34f5a-774">客户端 (for Business 的 Skype 仅联机)</span><span class="sxs-lookup"><span data-stu-id="34f5a-774">Clients (Skype for Business Online Only)</span></span> | <span data-ttu-id="34f5a-775">知道某些旧客户端，记录与媒体可靠性的问题。</span><span class="sxs-lookup"><span data-stu-id="34f5a-775">Some older clients have known, documented issues with media reliability.</span></span> <span data-ttu-id="34f5a-776">查看多个受影响用户的呼叫分析报告或在 CQD 筛选到特定建筑或子网与而丢弃的总呼叫失败 %度量值中创建自定义客户端版本表报表。</span><span class="sxs-lookup"><span data-stu-id="34f5a-776">Review the Call Analytics reports from multiple affected users or create a custom Client Version table report in CQD filtered to specific buildings or subnets with Total Call Dropped Failure % measure.</span></span> <span data-ttu-id="34f5a-777">此信息将帮助您了解呼叫中的特定构建的垂直距离和客户端的特定版本之间是否存在的关系。</span><span class="sxs-lookup"><span data-stu-id="34f5a-777">This information will help you understand whether a relationship exists between call drops in that specific building and a specific version of the client.</span></span>                                                                                                                                                              |
| <span data-ttu-id="34f5a-778">设备</span><span class="sxs-lookup"><span data-stu-id="34f5a-778">Devices</span></span>                                  | <span data-ttu-id="34f5a-779">设备故障的大部分是由于使用不认证的团队或 Skype for Business 的设备。</span><span class="sxs-lookup"><span data-stu-id="34f5a-779">The majority of device failures are due to using devices that aren’t certified for Teams or Skype for Business.</span></span> <span data-ttu-id="34f5a-780">故障通常采用集成的扬声器或正在被使用的话筒或插入到设备上的 3.5 毫米音频插孔 earbud/麦克风组合的形式。</span><span class="sxs-lookup"><span data-stu-id="34f5a-780">Failures usually take the form of the integrated speakers or mics that are being used, or earbud/mic combinations that are plugged into the 3.5 mm audio jack on a device.</span></span> <span data-ttu-id="34f5a-781">Microsoft 的当前建议是遇到任何用户呼叫断开 — 或质量欠佳的呼叫通常 — 且应使用集成的设备或驱动程序设置的[认证的耳麦或免提电话](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs)。</span><span class="sxs-lookup"><span data-stu-id="34f5a-781">Microsoft’s current recommendation is that any users who are experiencing call drops—or poor calls in general—and are using integrated devices or drivers should be provisioned a [certified headset or speakerphone](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs).</span></span> |
| <span data-ttu-id="34f5a-782">用户行为</span><span class="sxs-lookup"><span data-stu-id="34f5a-782">User Behavior</span></span>                            | <span data-ttu-id="34f5a-783">如果您确定，既未网络、 设备或客户端问题，请考虑[我顾问](https://aka.ms/myadvisor)适当的开发培训用户如何以最佳加入并退出会议的用户应用策略的指南。</span><span class="sxs-lookup"><span data-stu-id="34f5a-783">If you determine that neither network, devices, or clients are the issue, consider engaging [My Advisor](https://aka.ms/myadvisor) for guidance in developing a user adoption strategy to educate users how to best join and exit meetings.</span></span> <span data-ttu-id="34f5a-784">效率团队和 Skype 用户将会议中的所有参与者的用于生成更好的用户体验。</span><span class="sxs-lookup"><span data-stu-id="34f5a-784">A smarter Teams and Skype user will produce a better user experience for all participants in the meeting.</span></span> <span data-ttu-id="34f5a-785">将其便携式计算机置入休眠模式 （通过关闭盖） 放而不退出会议的用户将被分类为意外的调用投递。</span><span class="sxs-lookup"><span data-stu-id="34f5a-785">A user who puts their laptop to sleep (by closing the lid) without exiting the meeting will be classified as an unexpected call drop.</span></span>     |

## <a name="quality-investigations"></a><span data-ttu-id="34f5a-786">质量调查</span><span class="sxs-lookup"><span data-stu-id="34f5a-786">Quality investigations</span></span>

<span data-ttu-id="34f5a-787">若要评估整个部署的音频质量的状态下一步是调查音频质量欠佳呼叫比率 (PCR)、 TCP 和代理使用率。</span><span class="sxs-lookup"><span data-stu-id="34f5a-787">The next step to assess the state of audio quality across the deployment is to investigate Audio Poor Call Ratio (PCR), TCP, and proxy usage.</span></span> <span data-ttu-id="34f5a-788">务必要记住 CQD 数据不提供具体的根本原因，但您改用提供可能的问题的区域以开始使用修正活动的相应团队协作会话。</span><span class="sxs-lookup"><span data-stu-id="34f5a-788">It’s important to remember that CQD data doesn’t provide you a specific root cause, but instead provides you with likely problem areas to begin a collaborative conversation with the appropriate teams for remediation activities.</span></span>

> [!NOTE]
> <span data-ttu-id="34f5a-789">在本指南中介绍的模板中包含的不是所有报告。</span><span class="sxs-lookup"><span data-stu-id="34f5a-789">Not all reports included in the templates are covered in this guide.</span></span> <span data-ttu-id="34f5a-790">请参阅单个报表说明的详细信息。</span><span class="sxs-lookup"><span data-stu-id="34f5a-790">Please refer to the individual report description for more information.</span></span> 


### <a name="investigate-call-quality"></a><span data-ttu-id="34f5a-791">调查呼叫质量</span><span class="sxs-lookup"><span data-stu-id="34f5a-791">Investigate call quality</span></span>

<span data-ttu-id="34f5a-792">整体 PCR 百分比主要用于指示组织是否会议定义音频指标目标。</span><span class="sxs-lookup"><span data-stu-id="34f5a-792">The overall PCR percentage is primarily used to indicate whether the organization is meeting defined audio metric targets.</span></span> <span data-ttu-id="34f5a-793">请务必注意，即使内目标的整体百分比，则某些子网或建筑可能不满足定义的目标，因此需要进一步调查。</span><span class="sxs-lookup"><span data-stu-id="34f5a-793">It’s important to note that even if the overall percentage is within target, some subnets or buildings might not meet the defined targets and therefore need further investigation.</span></span> <span data-ttu-id="34f5a-794">例如，如果组织的音频 PCR 百分比值 3%中年 12 月，这符合示例目标、 特定建筑物可能仍存在不佳的体验，具体取决于该 3%的通讯组。</span><span class="sxs-lookup"><span data-stu-id="34f5a-794">For example, if the organizational audio PCR percentage is 3 percent in December, which meets the sample target, specific buildings might still be having poor experiences, depending on the distribution of that 3 percent.</span></span>

#### <a name="overall-organizational-poor-call-percentage"></a><span data-ttu-id="34f5a-795">总体组织质量欠佳的呼叫百分比</span><span class="sxs-lookup"><span data-stu-id="34f5a-795">Overall organizational poor call percentage</span></span>

<span data-ttu-id="34f5a-796">若要评估组织质量欠佳的呼叫的整体百分比，请使用总体质量图表报表。</span><span class="sxs-lookup"><span data-stu-id="34f5a-796">To assess the overall percentage of poor calls for the organization use the Quality Overall chart report.</span></span>

![图表显示劣质呼叫所占屏幕截图](media/quality-of-experience-review-guide-image20.png)

<span data-ttu-id="34f5a-798">_图 20 – 音频质量-总体_</span><span class="sxs-lookup"><span data-stu-id="34f5a-798">_Figure 20 – Audio Quality - Overall_</span></span>

##### <a name="investigation"></a><span data-ttu-id="34f5a-799">调查</span><span class="sxs-lookup"><span data-stu-id="34f5a-799">Investigation</span></span>

<span data-ttu-id="34f5a-800">此图表报表显示随着时间的推移贵组织的用法和 PCR。</span><span class="sxs-lookup"><span data-stu-id="34f5a-800">This chart report displays your organization’s usage and PCR over time.</span></span> <span data-ttu-id="34f5a-801">通过使用此报告，您可以回答以下问题：</span><span class="sxs-lookup"><span data-stu-id="34f5a-801">By using this report, you can answer the following questions:</span></span>

1.  <span data-ttu-id="34f5a-802">什么是当前月份的总 PCR？</span><span class="sxs-lookup"><span data-stu-id="34f5a-802">What is the total PCR for the current month?</span></span>

2.  <span data-ttu-id="34f5a-803">PCR 低于定义的目标指标？</span><span class="sxs-lookup"><span data-stu-id="34f5a-803">Is the PCR below the defined target metric?</span></span>

3.  <span data-ttu-id="34f5a-804">严重或优于上个月是故障趋势？</span><span class="sxs-lookup"><span data-stu-id="34f5a-804">Is the failure trend worse or better than the previous month?</span></span>

4.  <span data-ttu-id="34f5a-805">故障趋势增加，steady，或减少？</span><span class="sxs-lookup"><span data-stu-id="34f5a-805">Is the failure trend increasing, steady, or decreasing?</span></span>

<span data-ttu-id="34f5a-806">不管上面的问题的答案花时间使用子报表以查找任何建筑或可能需要进一步调查的网络调查。</span><span class="sxs-lookup"><span data-stu-id="34f5a-806">Irrespective of the answers to the questions above, take the time to investigate by using the sub-reports to look for any buildings or networks that might need further investigation.</span></span> <span data-ttu-id="34f5a-807">尽管总体 PCR 可能是下面目标指标，通常为一个或多个建筑或网络 PCR 超过指标，并且需要进一步调查。</span><span class="sxs-lookup"><span data-stu-id="34f5a-807">Although the overall PCR might be below the target metric, often the PCR for one or more buildings or networks is above the metric and needs further investigation.</span></span>

#### <a name="audio-quality-overall"></a><span data-ttu-id="34f5a-808">总体音质</span><span class="sxs-lookup"><span data-stu-id="34f5a-808">Audio quality overall</span></span>

<span data-ttu-id="34f5a-809">有两个音频质量的模板，一个用于调查会议和另一个用于双方呼叫中包含的报告树。</span><span class="sxs-lookup"><span data-stu-id="34f5a-809">There are two report trees included in the templates for audio quality, one for investigating conferencing and the other for two-party calls.</span></span> <span data-ttu-id="34f5a-810">为了质量修正，调查过程是相同，因此我们将重点介绍会议。</span><span class="sxs-lookup"><span data-stu-id="34f5a-810">For the purposes of quality remediation, the investigative process is the same, so we’ll focus here on conferencing.</span></span> <span data-ttu-id="34f5a-811">在会议品质改进还产生积极会影响双方呼叫质量。</span><span class="sxs-lookup"><span data-stu-id="34f5a-811">Improvements in conference quality will also positively affect two-party call quality.</span></span> <span data-ttu-id="34f5a-812">报告，还提供通过有线会议和两方的音频质量的视图和 Wi-fi。</span><span class="sxs-lookup"><span data-stu-id="34f5a-812">Reports are also included to view audio quality for conferencing and two-party by wired and Wi-Fi.</span></span>

> [!NOTE]
> <span data-ttu-id="34f5a-813">调查双方质量欠佳的呼叫是类似于调查电话会议。</span><span class="sxs-lookup"><span data-stu-id="34f5a-813">Investigating two-party poor calls is similar to investigating conference calls.</span></span> <span data-ttu-id="34f5a-814">任务是确定建筑或具有最低质量以验证是否与另一个构建或子网质量欠佳的呼叫的模式的子网。</span><span class="sxs-lookup"><span data-stu-id="34f5a-814">The task is to identify buildings or subnets that have the lowest quality to validate whether there’s a pattern of poor calls with another building or subnet.</span></span> 

![音频质量-会议呼叫质量仪表板中的报表的屏幕截图。](media/quality-of-experience-review-guide-image21.png)

<span data-ttu-id="34f5a-816">_图 21 – 音频质量-会议_</span><span class="sxs-lookup"><span data-stu-id="34f5a-816">_Figure 21 – Audio Quality - Conferencing_</span></span>

##### <a name="investigation"></a><span data-ttu-id="34f5a-817">调查</span><span class="sxs-lookup"><span data-stu-id="34f5a-817">Investigation</span></span>

<span data-ttu-id="34f5a-818">此图表报表显示您的组织的会议或两方使用率和 PCR 段时间。</span><span class="sxs-lookup"><span data-stu-id="34f5a-818">This chart report displays your organization’s conferencing or two-party usage and PCR over time.</span></span> <span data-ttu-id="34f5a-819">通过使用此报告，您可以回答以下问题：</span><span class="sxs-lookup"><span data-stu-id="34f5a-819">By using this report, you can answer the following questions:</span></span>

1.  <span data-ttu-id="34f5a-820">什么是当前月份的总 PCR？</span><span class="sxs-lookup"><span data-stu-id="34f5a-820">What is the total PCR for the current month?</span></span>

2.  <span data-ttu-id="34f5a-821">PCR 低于定义的目标指标？</span><span class="sxs-lookup"><span data-stu-id="34f5a-821">Is the PCR below the defined target metric?</span></span>

3.  <span data-ttu-id="34f5a-822">严重或优于上个月是 PCR？</span><span class="sxs-lookup"><span data-stu-id="34f5a-822">Is PCR worse or better than the previous month?</span></span>

4.  <span data-ttu-id="34f5a-823">PCR 趋势增加，steady，或减少？</span><span class="sxs-lookup"><span data-stu-id="34f5a-823">Is the PCR trend increasing, steady, or decreasing?</span></span>

<span data-ttu-id="34f5a-824">不管上面的问题的答案花时间使用子报表以查找任何建筑或可能需要调查的网络调查。</span><span class="sxs-lookup"><span data-stu-id="34f5a-824">Irrespective of the answers to the questions above, take the time to investigate by using the sub-reports to look for any buildings or networks that might need investigation.</span></span> <span data-ttu-id="34f5a-825">尽管总体 PCR 可能是下面目标指标，通常为一个或多个建筑或网络 PCR 超过指标，并且需要修复。</span><span class="sxs-lookup"><span data-stu-id="34f5a-825">Although the overall PCR might be below the target metric, often the PCR for one or more buildings or networks is above the metric and needs remediation.</span></span>

#### <a name="poor-audio-stream-by-building-and-subnet"></a><span data-ttu-id="34f5a-826">构建和子网的差音频流</span><span class="sxs-lookup"><span data-stu-id="34f5a-826">Poor audio stream by building and subnet</span></span>

<span data-ttu-id="34f5a-827">此表报告可帮助您什么贡献的呼叫被分类为质量欠佳的其他深入，并有助于隔离热点托管网络中。</span><span class="sxs-lookup"><span data-stu-id="34f5a-827">This table report gives you additional insight into what contributed to the calls’ being classified as poor and helps to isolate hot spots in the managed network.</span></span>

<span data-ttu-id="34f5a-828">连接细节区分有线和 Wi-fi 并包括抖动、 数据包丢失和往返时间 (RTT) 测量。</span><span class="sxs-lookup"><span data-stu-id="34f5a-828">The connection detail distinguishes between wired and Wi-Fi and includes jitter, packet loss, and round-trip time (RTT) measurements.</span></span> <span data-ttu-id="34f5a-829">类似报告还存在下的两方报表，并用于隔离托管网络上的双方呼叫。</span><span class="sxs-lookup"><span data-stu-id="34f5a-829">A similar report also exists under the two-party reports, and is used to isolate two-party calls on your managed network.</span></span>

> [!NOTE]
> <span data-ttu-id="34f5a-830">请务必调整到当前月份月年筛选器。</span><span class="sxs-lookup"><span data-stu-id="34f5a-830">Be sure to adjust the Month Year filter to the current month.</span></span> <span data-ttu-id="34f5a-831">选择**编辑**，然后调整**月年**保存新默认的月份。</span><span class="sxs-lookup"><span data-stu-id="34f5a-831">Select **Edit**, and adjust **Month Year** to save the new default month.</span></span> 

> [!TIP]
> <span data-ttu-id="34f5a-832">常见家庭网络难以会审由于其广泛使用。</span><span class="sxs-lookup"><span data-stu-id="34f5a-832">Common home networks are difficult to triage due to their widespread use.</span></span> <span data-ttu-id="34f5a-833">单独的报告使用防火墙 IP 已添加到要帮助与使用公共网络的补救办公室的所有网络模板。</span><span class="sxs-lookup"><span data-stu-id="34f5a-833">A separate report that uses the firewall IP has been added to the All Networks template to assist with remediating offices that use common networks.</span></span>

![列出连接类型、 传输类型和 PCR 大于 3%以及各种理由按构建、 网络和每月的子网的质量不佳的报表。](media/quality-of-experience-review-guide-image22.png)

<span data-ttu-id="34f5a-835">_图 22 来构建差音频流摘要-和子网会议_</span><span class="sxs-lookup"><span data-stu-id="34f5a-835">_Figure 22 - Poor Audio Stream Summary by Building and Subnet - Conferencing_</span></span>

##### <a name="remediation"></a><span data-ttu-id="34f5a-836">修正</span><span class="sxs-lookup"><span data-stu-id="34f5a-836">Remediation</span></span>

<span data-ttu-id="34f5a-837">修正精力上建筑或快速网络中安装的音频流的最大卷，因为这将最大限度地影响，并帮助改善用户体验。</span><span class="sxs-lookup"><span data-stu-id="34f5a-837">Focus your remediation efforts on buildings or networks that have the largest volume of audio streams, because this will maximize impact and help to improve the user experience quickly.</span></span> <span data-ttu-id="34f5a-838">使用抖动、 数据包丢失和 RTT 度量值来了解什么分配给质量欠佳的呼叫质量。</span><span class="sxs-lookup"><span data-stu-id="34f5a-838">Use the jitter, packet loss, and RTT measurements to understand what’s contributing to the poor call quality.</span></span> <span data-ttu-id="34f5a-839">很可能有多个问题：</span><span class="sxs-lookup"><span data-stu-id="34f5a-839">It’s possible for there to be more than one problem:</span></span>

-   <span data-ttu-id="34f5a-840">**抖动：** 以不同的速度，这将导致扬声器发出声音自动正在传入媒体数据包。</span><span class="sxs-lookup"><span data-stu-id="34f5a-840">**Jitter:** Media packets are arriving at different speeds, which causes a speaker to sound robotic.</span></span>

-   <span data-ttu-id="34f5a-841">**数据包丢失：** 媒体数据包将被丢弃，这将创建缺少的单词或音节的影响。</span><span class="sxs-lookup"><span data-stu-id="34f5a-841">**Packet loss:** Media packets are being dropped, which creates the effect of missing words or syllables.</span></span>

-   <span data-ttu-id="34f5a-842">**RTT:** 媒体数据包正在获取其目标，创建一个 walkie-talkie 效果很长时间。</span><span class="sxs-lookup"><span data-stu-id="34f5a-842">**RTT:** Media packets are taking a long time to get to their destination, which creates a walkie-talkie effect.</span></span>

<span data-ttu-id="34f5a-843">虽然真实性没有单个源的内容会导致质量欠佳的呼叫帐户，多个常用方法可以帮助您处理网络异常。</span><span class="sxs-lookup"><span data-stu-id="34f5a-843">Although no single source of truth accounts for what can cause a poor call, several common methods can help you deal with network anomalies.</span></span>

<span data-ttu-id="34f5a-844">为了帮助您研究质量问题，您可以利用[呼叫分析](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309)。</span><span class="sxs-lookup"><span data-stu-id="34f5a-844">To assist your investigation into quality issues, you can leverage [Call Analytics](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309).</span></span>
<span data-ttu-id="34f5a-845">使用呼叫分析，您可以查看特定会议或用户的详细的呼叫报告。</span><span class="sxs-lookup"><span data-stu-id="34f5a-845">With Call Analytics, you can look at a specific conference or users’ detailed call report.</span></span> <span data-ttu-id="34f5a-846">此报告将包含 PII 数据，并尝试辨别失败的原因时很有用。</span><span class="sxs-lookup"><span data-stu-id="34f5a-846">This report will contain PII data and is useful when attempting to discern a reason for failures.</span></span> <span data-ttu-id="34f5a-847">一旦您知道哪些构建受到影响，跟踪用户，构建应变得非常简单。</span><span class="sxs-lookup"><span data-stu-id="34f5a-847">Once you know which building that is affected, tracking down users in that building should be straightforward.</span></span>

<span data-ttu-id="34f5a-848">不要忘记让支持人员了解这些网络遇到质量问题，以便他们可以快速会审并响应传入呼叫。</span><span class="sxs-lookup"><span data-stu-id="34f5a-848">Don’t forget to let the helpdesk know that these networks are experiencing quality issues, so they can quickly triage and respond to incoming calls.</span></span>

<span data-ttu-id="34f5a-849">_表 9-常见贡献高 PCR_</span><span class="sxs-lookup"><span data-stu-id="34f5a-849">_Table 9 - Common contributors to high PCR_</span></span>

| <span data-ttu-id="34f5a-850">修正</span><span class="sxs-lookup"><span data-stu-id="34f5a-850">Remediation</span></span>                              | <span data-ttu-id="34f5a-851">指南</span><span class="sxs-lookup"><span data-stu-id="34f5a-851">Guidance</span></span>       |
|------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="34f5a-852">网络</span><span class="sxs-lookup"><span data-stu-id="34f5a-852">Networks</span></span>                                 | <span data-ttu-id="34f5a-853">使用过度或下设置网络可以与媒体质量出现问题。</span><span class="sxs-lookup"><span data-stu-id="34f5a-853">An overused or under-provisioned network can cause issues with media quality.</span></span> <span data-ttu-id="34f5a-854">使用网络团队核实，确定是否从用户网络连接到 internet 出口点具有足够的带宽来支持媒体。</span><span class="sxs-lookup"><span data-stu-id="34f5a-854">Work with the network team to determine whether the network connections from the user to the internet egress point has enough bandwidth to support media.</span></span> <span data-ttu-id="34f5a-855">**执行网络准备情况评估：** 网络评估提供了有关预期的带宽使用情况的详细信息、 如何应对带宽和网络发生更改，以及建议个团队和 Skype for Business 的网络的做法。</span><span class="sxs-lookup"><span data-stu-id="34f5a-855">**Perform a network readiness assessment:** A network assessment provides details about expected bandwidth usage, how to cope with bandwidth and network changes, and recommended networking practices for Teams and Skype for Business.</span></span> <span data-ttu-id="34f5a-856">使用上表作为您的源，必须建筑或子网的最佳候选人评估的列表。</span><span class="sxs-lookup"><span data-stu-id="34f5a-856">Using the preceding table as your source, you have a list of buildings or subnets that are excellent candidates for an assessment.</span></span><br><ul><li>[<span data-ttu-id="34f5a-857">Microsoft 团队网络准备情况评估</span><span class="sxs-lookup"><span data-stu-id="34f5a-857">Microsoft Teams Network Readiness Assessment</span></span>](https://docs.microsoft.com/MicrosoftTeams/3-envision-evaluate-my-environment#test-the-network)</li><li>[<span data-ttu-id="34f5a-858">Skype 的业务网络准备情况评估</span><span class="sxs-lookup"><span data-stu-id="34f5a-858">Skype for Business Network Readiness Assessment</span></span>](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers/?pageState=NetworkReadiness)</li></ul><br><span data-ttu-id="34f5a-859">**Microsoft 网络评估工具：** 简单的网络性能测试中使用此工具可确定网络团队将执行程度或 Skype 业务联机呼叫。</span><span class="sxs-lookup"><span data-stu-id="34f5a-859">**Microsoft Network Assessment Tool:** Use this tool for a simple test of network performance to determine how well the network would perform for a Teams or Skype for Business Online call.</span></span> <span data-ttu-id="34f5a-860">此工具可帮助您评估子网的性能和验证针对 Microsoft 性能[要求](https://aka.ms/performancerequirements)的网络的准备。</span><span class="sxs-lookup"><span data-stu-id="34f5a-860">This tool helps you assess the performance of a subnet and validate the readiness of the network against the Microsoft performance [requirements](https://aka.ms/performancerequirements).</span></span><br><ul><li>[<span data-ttu-id="34f5a-861">下载网络评估工具</span><span class="sxs-lookup"><span data-stu-id="34f5a-861">Download the Network Assessment Tool</span></span>](https://www.microsoft.com/download/details.aspx?id=53885) </li></ul>        |
| <span data-ttu-id="34f5a-862">服务质量 (QoS)</span><span class="sxs-lookup"><span data-stu-id="34f5a-862">Quality of Service (QoS)</span></span>                 | <span data-ttu-id="34f5a-863">QoS 是经验证的方法，可帮助确定优先级和时间上以确保它们到达其保持不变的目标网络数据包。</span><span class="sxs-lookup"><span data-stu-id="34f5a-863">QoS is a proven method to help prioritize packets on a network to ensure they arrive at their destination intact and on time.</span></span> <span data-ttu-id="34f5a-864">请考虑实现跨组织最大限度地的带宽限制或约束其中的用户体验质量的 QoS。</span><span class="sxs-lookup"><span data-stu-id="34f5a-864">Consider implementing QoS across your organization to maximize the quality of the user experience where bandwidth is limited or constrained.</span></span> <span data-ttu-id="34f5a-865">QoS 将帮助您解决通常与数据包丢失的高级别关联的问题和 — 在较小者一定程度上 — 不稳定和往返行程的时间。</span><span class="sxs-lookup"><span data-stu-id="34f5a-865">QoS will help solve issues typically associated with high levels of packet loss, and—to a lesser degree—jitter and round-trip times.</span></span> <br><ul><li>[<span data-ttu-id="34f5a-866">Microsoft 团队 QoS 指南</span><span class="sxs-lookup"><span data-stu-id="34f5a-866">Microsoft Teams QoS Guidance</span></span>](https://docs.microsoft.com/MicrosoftTeams/qos-in-teams)</li><li>[<span data-ttu-id="34f5a-867">Skype 的业务 QoS 指南</span><span class="sxs-lookup"><span data-stu-id="34f5a-867">Skype for Business QoS Guidance</span></span>](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_8)</li></ul>    |
| <span data-ttu-id="34f5a-868">Wi-fi</span><span class="sxs-lookup"><span data-stu-id="34f5a-868">Wi-Fi</span></span>                                    | <span data-ttu-id="34f5a-869">Wi-fi 可以对呼叫质量产生重大影响。</span><span class="sxs-lookup"><span data-stu-id="34f5a-869">Wi-Fi can have a significant impact on call quality.</span></span> <span data-ttu-id="34f5a-870">Wi-fi 设计不通常考虑 VoIP 服务的网络要求，而且通常质量不佳的源。</span><span class="sxs-lookup"><span data-stu-id="34f5a-870">Wi-Fi design doesn’t typically take into consideration the network requirements for VoIP services and are often a source of poor quality.</span></span> <span data-ttu-id="34f5a-871">**QoS:** 现代无线网络必须支持多个设备。</span><span class="sxs-lookup"><span data-stu-id="34f5a-871">**QoS:** Modern wireless networks must support many devices.</span></span> <span data-ttu-id="34f5a-872">这些设备争夺带宽，并可能导致 VoIP 服务的质量问题的速度和延迟至关重要。</span><span class="sxs-lookup"><span data-stu-id="34f5a-872">These devices compete for bandwidth and can lead to quality issues for VoIP services where speed and latency are vital.</span></span> <span data-ttu-id="34f5a-873">咨询您的无线供应商的详细信息，并考虑实现无线网络若要设置 Skype 业务和团队媒体上的 QoS。</span><span class="sxs-lookup"><span data-stu-id="34f5a-873">Consult your wireless vendor for specifics, and consider implementing QoS on your wireless network to prioritize Skype for Business and Teams media.</span></span> <span data-ttu-id="34f5a-874">**AP 密度：** 访问点 (Ap) 可能太远或不在的理想位置。</span><span class="sxs-lookup"><span data-stu-id="34f5a-874">**AP density:** Access points (APs) might be too far apart or not in an ideal location.</span></span> <span data-ttu-id="34f5a-875">若要最小化潜在干扰放置额外 Ap 会议室和中不会受到背景墙或其他对象的位置。</span><span class="sxs-lookup"><span data-stu-id="34f5a-875">To minimize potential interference, place extra APs in conference rooms and in locations that aren’t obstructed by walls or other objects.</span></span> <span data-ttu-id="34f5a-876">**2.4 GHz 与 5 GHz:** 5 GHz 提供较少的背景干扰和更高的速度，并通过 Wi-fi 部署 VoIP 时应确定优先级。</span><span class="sxs-lookup"><span data-stu-id="34f5a-876">**2.4 GHz vs. 5 GHz:** 5 GHz provides less background interference and higher speeds, and should be prioritized when deploying VoIP over Wi-Fi.</span></span> <span data-ttu-id="34f5a-877">但是，5 GHz 不与 2.4 GHz 为强，并且不入侵轻松地的背景墙。</span><span class="sxs-lookup"><span data-stu-id="34f5a-877">However, 5 GHz isn’t as strong as 2.4 GHz and doesn’t penetrate walls as easily.</span></span> <span data-ttu-id="34f5a-878">查看您构建的布局来确定可以最佳的连接依赖的频率。</span><span class="sxs-lookup"><span data-stu-id="34f5a-878">Review your building layout to determine which frequency you can rely on for the best connection.</span></span> <span data-ttu-id="34f5a-879">**信号强度：** 通常情况下以 dBm （分贝电源比），这测量无线信号强度。</span><span class="sxs-lookup"><span data-stu-id="34f5a-879">**Signal strength:** Traditionally measured in dBm (power ratio in decibels), this measures the strength of the wireless signal.</span></span> <span data-ttu-id="34f5a-880">设备连接到应用程序后，它不是要让轻松地转。</span><span class="sxs-lookup"><span data-stu-id="34f5a-880">After a device is connected to an AP, it doesn’t want to let go easily.</span></span> <span data-ttu-id="34f5a-881">随着离开 AP 移动设备，则信号到点，则会引发不佳的连接，即使其他、 仔细 AP 位于属于。</span><span class="sxs-lookup"><span data-stu-id="34f5a-881">As the device moves away from the AP, the signal strength falls off to a point that induces a poor connection even though another, closer AP is available.</span></span> <span data-ttu-id="34f5a-882">如果可能，请使用 AP 供应商，以确保 Ap 配置要删除的设备时信号低于可接受的程度。</span><span class="sxs-lookup"><span data-stu-id="34f5a-882">If possible, work with your AP vendor to ensure that the APs are configured to drop a device when signal strength falls below an acceptable level.</span></span> <span data-ttu-id="34f5a-883">这将确保设备未挂起弱 ap。</span><span class="sxs-lookup"><span data-stu-id="34f5a-883">This will ensure that the device doesn’t hang on to a weak AP.</span></span> <span data-ttu-id="34f5a-884">无法轻松添加更多 Ap 时，这是很好的解决方案。</span><span class="sxs-lookup"><span data-stu-id="34f5a-884">This is a good solution when you can’t easily add more APs.</span></span> <span data-ttu-id="34f5a-885">**无线驱动程序：** 当所有其他失败时，确保最新的无线驱动程序。</span><span class="sxs-lookup"><span data-stu-id="34f5a-885">**Wireless driver:** When all else fails, ensure that wireless drivers are up to date.</span></span> <span data-ttu-id="34f5a-886">这有助于减轻任何用户体验不佳与过期的驱动程序。</span><span class="sxs-lookup"><span data-stu-id="34f5a-886">This will help mitigate any poor user experience related to an outdated driver.</span></span> |
| <span data-ttu-id="34f5a-887">网络设备</span><span class="sxs-lookup"><span data-stu-id="34f5a-887">Network device</span></span>                           | <span data-ttu-id="34f5a-888">较大的组织可能有数百个分散在网络设备。</span><span class="sxs-lookup"><span data-stu-id="34f5a-888">Larger organizations might have hundreds of devices spread out across the network.</span></span> <span data-ttu-id="34f5a-889">使用您的网络团队以确保从用户到 internet 的网络设备是维护和最新。</span><span class="sxs-lookup"><span data-stu-id="34f5a-889">Work with your network team to ensure the network devices from the user to the internet are maintained and up to date.</span></span>     |
| <span data-ttu-id="34f5a-890">VPN</span><span class="sxs-lookup"><span data-stu-id="34f5a-890">VPN</span></span>                                      | <span data-ttu-id="34f5a-891">它已完备 VPN 设备不通常情况下旨在处理实时的媒体工作负荷。</span><span class="sxs-lookup"><span data-stu-id="34f5a-891">It has been well-documented that VPN appliances aren’t traditionally designed to handle real-time media workloads.</span></span> <span data-ttu-id="34f5a-892">某些 VPN 配置禁止 UDP （这是首选的协议音频） 使用，并且仅依赖 TCP。</span><span class="sxs-lookup"><span data-stu-id="34f5a-892">Some VPN configurations prohibit the use of UDP (which is the preferred protocol for audio) and rely on TCP only.</span></span> <span data-ttu-id="34f5a-893">请考虑实现[VPN 拆分隧道解决方案](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_9)以帮助减少 VPN 作为质量不佳的一个来源。</span><span class="sxs-lookup"><span data-stu-id="34f5a-893">Consider implementing a [VPN split-tunnel solution](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_9) to help reduce VPN as a source of poor quality.</span></span>        |
| <span data-ttu-id="34f5a-894">客户端 (for Business 的 Skype 仅联机)</span><span class="sxs-lookup"><span data-stu-id="34f5a-894">Clients (Skype for Business Online Only)</span></span> | <span data-ttu-id="34f5a-895">具有已知旧版客户端与媒体造成问题。</span><span class="sxs-lookup"><span data-stu-id="34f5a-895">Older clients have been known to cause issues with media.</span></span> <span data-ttu-id="34f5a-896">确保客户端的版本的六个月内修补。</span><span class="sxs-lookup"><span data-stu-id="34f5a-896">Ensure that clients are being patched within six months of release.</span></span> <span data-ttu-id="34f5a-897">有关开发的客户端准备策略的指南利用[MyAdvisor](https://aka.ms/myadvisor)和部署[即点即单击](https://technet.microsoft.com/library/jj219427.aspx)。</span><span class="sxs-lookup"><span data-stu-id="34f5a-897">Leverage [MyAdvisor](https://aka.ms/myadvisor) for guidance on developing a client readiness strategy and deploy [Click-to-Run](https://technet.microsoft.com/library/jj219427.aspx).</span></span>      |
| <span data-ttu-id="34f5a-898">设备</span><span class="sxs-lookup"><span data-stu-id="34f5a-898">Devices</span></span>                                  | <span data-ttu-id="34f5a-899">使用[优化设备](https://partnersolutions.skypeforbusiness.com/solutionscatalog)可以帮助明显改善用户体验。</span><span class="sxs-lookup"><span data-stu-id="34f5a-899">The use of [optimized devices](https://partnersolutions.skypeforbusiness.com/solutionscatalog) can help to significantly improve the user experience.</span></span> <span data-ttu-id="34f5a-900">与所有要素相同，优化的设备旨在最大限度地与团队和 Skype for Business 的用户体验和生成出色的质量。</span><span class="sxs-lookup"><span data-stu-id="34f5a-900">With all things being equal, optimized devices are designed to maximize the user experience with Teams and Skype for Business and produce superior quality.</span></span> <span data-ttu-id="34f5a-901">利用[MyAdvisor](https://aka.ms/myadvisor)有关开发的设备准备策略的指南。</span><span class="sxs-lookup"><span data-stu-id="34f5a-901">Leverage [MyAdvisor](https://aka.ms/myadvisor) for guidance on developing a device readiness strategy.</span></span>   |


### <a name="investigate-tcp-audio-sessions"></a><span data-ttu-id="34f5a-902">调查 TCP 音频会话</span><span class="sxs-lookup"><span data-stu-id="34f5a-902">Investigate TCP audio sessions</span></span>

<span data-ttu-id="34f5a-903">故障回复传输和主要用于实时的媒体传输，将不被视为 TCP。</span><span class="sxs-lookup"><span data-stu-id="34f5a-903">TCP is considered a failback transport and not the primary transport you want for real-time media.</span></span> <span data-ttu-id="34f5a-904">它是一个故障回复传输的原因是 TCP 的性质状态。</span><span class="sxs-lookup"><span data-stu-id="34f5a-904">The reason it’s a failback transport is due to the stateful nature of TCP.</span></span> <span data-ttu-id="34f5a-905">例如，如果延迟网络上进行调用和延迟媒体数据包，然后从以前的几秒钟的数据包 — 不再有用的 — 争夺带宽，转到接收方，这会使错误情况变差。</span><span class="sxs-lookup"><span data-stu-id="34f5a-905">For example, if a call is made on a latent network and media packets are delayed, then packets from a few seconds ago—which are no longer useful—compete for bandwidth to get to the receiver, which can make a bad situation worse.</span></span> <span data-ttu-id="34f5a-906">这样的音频修复程序缝合和拉伸音频，导致听见通常在抖动的窗体中的项目。</span><span class="sxs-lookup"><span data-stu-id="34f5a-906">This makes the audio healer stitch and stretch audio, resulting in audible artifacts often in the form of jitter.</span></span>

<span data-ttu-id="34f5a-907">本节中的报表不进行了区分良好质量欠佳的呼叫。</span><span class="sxs-lookup"><span data-stu-id="34f5a-907">The reports in this section don’t make a distinction between good and poor calls.</span></span> <span data-ttu-id="34f5a-908">UDP 是首选，报告将查找 TCP 用于音频。</span><span class="sxs-lookup"><span data-stu-id="34f5a-908">Given that UDP is preferred, the reports look for the use of TCP for audio.</span></span> <span data-ttu-id="34f5a-909">主要原因是完整的防火墙规则。</span><span class="sxs-lookup"><span data-stu-id="34f5a-909">This is primarily caused by incomplete firewall rules.</span></span> <span data-ttu-id="34f5a-910">有关详细信息防火墙规则个团队和 Skype 业务 online，请参阅[Office 365 Url 和 IP 地址范围](https://aka.ms/o365ips)。</span><span class="sxs-lookup"><span data-stu-id="34f5a-910">For more information about firewall rules for Teams and Skype for Business Online, see [Office 365 URLs and IP address ranges](https://aka.ms/o365ips).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="34f5a-911">无有效[构建文件](#building-mapping)上载建议能够快速区分内外部的音频流时看 TCP 使用率。</span><span class="sxs-lookup"><span data-stu-id="34f5a-911">Having a valid [building file](#building-mapping) uploaded is recommended to be able to quickly distinguish inside from outside audio streams when looking at TCP usage.</span></span> 


#### <a name="audio-streams-with-tcp-usage-overall"></a><span data-ttu-id="34f5a-912">音频流总体 TCP 使用率</span><span class="sxs-lookup"><span data-stu-id="34f5a-912">Audio streams with TCP usage overall</span></span>

<span data-ttu-id="34f5a-913">此报告指示最近七个月，音频的总体 TCP 使用情况，如下所示。</span><span class="sxs-lookup"><span data-stu-id="34f5a-913">This report indicates the overall TCP usage for audio over the last seven months, as shown below.</span></span>

<span data-ttu-id="34f5a-914">本节中的所有进一步报告将重点缩小特定建筑和 TCP 最常使用的位置的子网。</span><span class="sxs-lookup"><span data-stu-id="34f5a-914">All further reports in this section will focus on narrowing down specific buildings and subnets where TCP is most commonly used.</span></span> <span data-ttu-id="34f5a-915">按会议和双方呼叫进行进一步子报表分解 TCP 使用率。</span><span class="sxs-lookup"><span data-stu-id="34f5a-915">Further sub-reports break down TCP usage by both conferencing and two-party calls.</span></span>

![图表显示的每月的 TCP 音频流的数目的屏幕截图](media/quality-of-experience-review-guide-image23.png)

<span data-ttu-id="34f5a-917">_图 23 – TCP 使用率的音频流_</span><span class="sxs-lookup"><span data-stu-id="34f5a-917">_Figure 23 – Audio Streams with TCP Usage_</span></span>

##### <a name="investigation"></a><span data-ttu-id="34f5a-918">调查</span><span class="sxs-lookup"><span data-stu-id="34f5a-918">Investigation</span></span>

<span data-ttu-id="34f5a-919">此图表报表显示您的组织的总体 TCP 用法。</span><span class="sxs-lookup"><span data-stu-id="34f5a-919">This chart report displays your organization’s overall TCP usage.</span></span> <span data-ttu-id="34f5a-920">通过使用此报告，您可以回答以下问题：</span><span class="sxs-lookup"><span data-stu-id="34f5a-920">By using this report, you can answer the following questions:</span></span>

1.  <span data-ttu-id="34f5a-921">什么是当前月份的总量的 TCP 呼叫？</span><span class="sxs-lookup"><span data-stu-id="34f5a-921">What is the total volume of TCP calls for the current month?</span></span>

2.  <span data-ttu-id="34f5a-922">很差或优于上个月？</span><span class="sxs-lookup"><span data-stu-id="34f5a-922">Is it worse or better than the previous month?</span></span>

3.  <span data-ttu-id="34f5a-923">TCP 使用率趋势增加，steady，或减少？</span><span class="sxs-lookup"><span data-stu-id="34f5a-923">Is the TCP usage trend increasing, steady, or decreasing?</span></span>

<span data-ttu-id="34f5a-924">如果您注意到，TCP 使用率趋势不断增加，或高于正常的每月使用花时间使用子报表以查找任何建筑或网络可能需要修正调查。</span><span class="sxs-lookup"><span data-stu-id="34f5a-924">If you notice that the TCP usage trend is increasing, or above normal monthly usage, take the time to investigate by using the sub-reports to look for any buildings or networks that might need remediation.</span></span> <span data-ttu-id="34f5a-925">理想情况下，您希望托管网络上尽可能少 TCP 基于音频会话。</span><span class="sxs-lookup"><span data-stu-id="34f5a-925">Ideally, you want as few TCP-based audio sessions as possible on the managed network.</span></span>

#### <a name="tcp-vs-udp"></a><span data-ttu-id="34f5a-926">TCP 和 UDP</span><span class="sxs-lookup"><span data-stu-id="34f5a-926">TCP vs. UDP</span></span>

<span data-ttu-id="34f5a-927">此表报表标识量 TCP 和 UDP 使用率报告的会议的音频、 视频和基于视频的屏幕共享 (VBSS) 的最新月份。</span><span class="sxs-lookup"><span data-stu-id="34f5a-927">This table report identifies the volume of TCP versus UDP usage reporting on the latest month for conferences for audio, video, and video-based screen sharing (VBSS).</span></span>

![显示与 UDP 会议流 TCP 量与 PCR 显示比较报表](media/quality-of-experience-review-guide-image24.png)

<span data-ttu-id="34f5a-929">_图 24 – TCP 和 UDP-会议_</span><span class="sxs-lookup"><span data-stu-id="34f5a-929">_Figure 24 – TCP vs. UDP - Conferencing_</span></span>

##### <a name="analysis"></a><span data-ttu-id="34f5a-930">分析</span><span class="sxs-lookup"><span data-stu-id="34f5a-930">Analysis</span></span>

<span data-ttu-id="34f5a-931">虽然您想要尽可能的低的 TCP 使用率，您可能会看到 TCP 用法，否则为正常部署中的位。</span><span class="sxs-lookup"><span data-stu-id="34f5a-931">Although you want TCP usage to be as low as possible, you might see a bit of TCP usage in an otherwise healthy deployment.</span></span> <span data-ttu-id="34f5a-932">若要为 TCP 使用情况比较 UDP，除 TCP 通过 UDP 确定百分比的音频流的音频流。</span><span class="sxs-lookup"><span data-stu-id="34f5a-932">To compare UDP to TCP usage, divide TCP audio streams by UDP audio streams to determine a percentage.</span></span> <span data-ttu-id="34f5a-933">一个值，超过 1%需要进一步调查。</span><span class="sxs-lookup"><span data-stu-id="34f5a-933">A value over 1 percent needs to be further investigated.</span></span>

<span data-ttu-id="34f5a-934">在上述示例中，我们执行 1,806 TCP 流除以 10,481 UDP 流到达 17.2%的值。</span><span class="sxs-lookup"><span data-stu-id="34f5a-934">In the example above, we take 1,806 TCP streams divided by 10,481 UDP streams to arrive at a value of 17.2 percent.</span></span> <span data-ttu-id="34f5a-935">此值远远高于 1%，并告诉我们，我们需要继续我们调查，以确定正在发生的 TCP 使用情况。</span><span class="sxs-lookup"><span data-stu-id="34f5a-935">This value is well above 1 percent and tells us that we need to continue our investigation to determine where the TCP usage is occurring.</span></span>

<span data-ttu-id="34f5a-936">在报告中还包含是音频质量欠佳的百分比。</span><span class="sxs-lookup"><span data-stu-id="34f5a-936">Also included in the report is Audio Poor Percentage.</span></span> <span data-ttu-id="34f5a-937">这样，您可以呼叫质量 UDP 和 TCP，以帮助可视化 TCP 如何影响 overcall 呼叫质量之间的比较结果视图。</span><span class="sxs-lookup"><span data-stu-id="34f5a-937">This gives you a view into the comparison of call quality between UDP and TCP to help visualize how TCP is affecting overcall call quality.</span></span>

<span data-ttu-id="34f5a-938">因此，现在您已确定是否存在的 TCP 基于您的组织中的音频的使用率过高，该怎么办您下一步？</span><span class="sxs-lookup"><span data-stu-id="34f5a-938">So now that you’ve determined that there is a high usage of TCP-based audio in your organization, what do you do next?</span></span> <span data-ttu-id="34f5a-939">转到**由构建和子网的 TCP 流**报表，以将分解 TCP 将使用构建和子网。</span><span class="sxs-lookup"><span data-stu-id="34f5a-939">Go to the **TCP Streams by Building and Subnet** reports to break down the TCP usage by building and subnets.</span></span>

#### <a name="tcp-streams-by-building-and-subnet"></a><span data-ttu-id="34f5a-940">构建和子网的 TCP 流</span><span class="sxs-lookup"><span data-stu-id="34f5a-940">TCP streams by building and subnet</span></span>

<span data-ttu-id="34f5a-941">在提供的 CQD 模板中，转到 TCP 流由构建和子网表报告使用的托管或所有网络模板。</span><span class="sxs-lookup"><span data-stu-id="34f5a-941">In the provided CQD templates, go to the TCP Streams by Building and Subnet table reports by using either the managed or All Networks template.</span></span> <span data-ttu-id="34f5a-942">有三种报告包含在模板中，一个用于调查会议，具有和没有 Microsoft 中继信息和一个用于调查双方呼叫。</span><span class="sxs-lookup"><span data-stu-id="34f5a-942">There are three reports included in the template, one for investigating conferencing, with and without Microsoft relay information, and one for investigating two-party calls.</span></span> <span data-ttu-id="34f5a-943">调查 TCP 使用，以便过程是相同的因此我们将专注上仅会议讨论。</span><span class="sxs-lookup"><span data-stu-id="34f5a-943">For the purpose of investigating TCP usage, the process is the same, so we’ll focus the discussion here on conferencing only.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="34f5a-944">无有效[构建文件](#building-mapping)上载建议能够快速区分内外部的音频流时看 TCP 使用率。</span><span class="sxs-lookup"><span data-stu-id="34f5a-944">Having a valid [building file](#building-mapping) uploaded is recommended to be able to quickly distinguish inside from outside audio streams when looking at TCP usage.</span></span> 

> [!NOTE]
> <span data-ttu-id="34f5a-945">请务必调整到当前月份月年筛选器。</span><span class="sxs-lookup"><span data-stu-id="34f5a-945">Be sure to adjust the Month Year filter to the current month.</span></span> <span data-ttu-id="34f5a-946">选择**编辑**，然后调整**月年**保存新默认的月份。</span><span class="sxs-lookup"><span data-stu-id="34f5a-946">Select **Edit**, and adjust **Month Year** to save the new default month.</span></span>                                  |

![报表，列出 TCP 流，按构建、 网络和每月的子网。](media/quality-of-experience-review-guide-image25.png)

<span data-ttu-id="34f5a-948">_图 25 – TCP 流来构建-和子网会议_</span><span class="sxs-lookup"><span data-stu-id="34f5a-948">_Figure 25 – TCP Streams by Building and Subnet - Conferencing_</span></span>

##### <a name="remediation"></a><span data-ttu-id="34f5a-949">修正</span><span class="sxs-lookup"><span data-stu-id="34f5a-949">Remediation</span></span>

<span data-ttu-id="34f5a-950">此报表标识特定建筑和分配给 TCP 使用率量的子网。</span><span class="sxs-lookup"><span data-stu-id="34f5a-950">This report identifies specific buildings and subnets that are contributing to the volume of TCP usage.</span></span> <span data-ttu-id="34f5a-951">此外包含其他报表来标识呼叫中用来帮助隔离缺少防火墙规则 Microsoft 中继 IP。</span><span class="sxs-lookup"><span data-stu-id="34f5a-951">An additional report is also included to identify the Microsoft relay IP that was used in the call to help isolate missing firewall rules.</span></span> <span data-ttu-id="34f5a-952">关注您在具有最大容量的音频流以最大限度地影响的这些建筑的修复措施。</span><span class="sxs-lookup"><span data-stu-id="34f5a-952">Focus your remediation efforts on those buildings that have the highest volume of audio streams to maximize impact.</span></span>

<span data-ttu-id="34f5a-953">TCP 使用率的最常见原因缺少在防火墙或代理的例外规则。</span><span class="sxs-lookup"><span data-stu-id="34f5a-953">The most common cause of TCP usage is missing exception rules in firewalls or proxies.</span></span> <span data-ttu-id="34f5a-954">我们将谈论代理的下一步部分，那么现在精力放在防火墙。</span><span class="sxs-lookup"><span data-stu-id="34f5a-954">We’ll be talking about proxies in the next section, so for now focus your efforts on the firewalls.</span></span> <span data-ttu-id="34f5a-955">通过使用构建或提供的子网，您可以确定哪些防火墙需要更新。</span><span class="sxs-lookup"><span data-stu-id="34f5a-955">By using the building or subnet provided, you can determine which firewall needs to be updated.</span></span>

<span data-ttu-id="34f5a-956">_表 10-修正 \* 由构建和子网的 TCP 流指南_</span><span class="sxs-lookup"><span data-stu-id="34f5a-956">_Table 10 - Remediation\* guidance for TCP streams by building and subnet_</span></span>

| <span data-ttu-id="34f5a-957">修正</span><span class="sxs-lookup"><span data-stu-id="34f5a-957">Remediation</span></span>        | <span data-ttu-id="34f5a-958">指南</span><span class="sxs-lookup"><span data-stu-id="34f5a-958">Guidance</span></span>     |
|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="34f5a-959">配置防火墙</span><span class="sxs-lookup"><span data-stu-id="34f5a-959">Configure firewall</span></span> | <span data-ttu-id="34f5a-960">验证[Office 365 IP 端口和地址](https://aka.ms/o365ips)将排除在您的防火墙。</span><span class="sxs-lookup"><span data-stu-id="34f5a-960">Verify [Office 365 IP ports and addresses](https://aka.ms/o365ips) are excluded from your firewall.</span></span> <span data-ttu-id="34f5a-961">尽管有多个 IP 地址和端口所需的媒体相关 TCP 问题，打开以下关注您初始的工作： 验证以下[媒体子网](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams)位于防火墙规则。</span><span class="sxs-lookup"><span data-stu-id="34f5a-961">Though there are many IP addresses and ports that need to be opened, for media-related TCP issues, focus your initial efforts on the following: Verify the following [media subnets](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams) are in your firewall rules.</span></span> <span data-ttu-id="34f5a-962">显示的特定媒体子网信息的表中，请参阅第 4 行中。</span><span class="sxs-lookup"><span data-stu-id="34f5a-962">Refer to Row 4 in the table shown for specific media subnet information.</span></span> <span data-ttu-id="34f5a-963">[UDP 端口 3478 – 3481](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Updated-IP-ranges-and-ports-for-Skype-for-Business-Online/ba-p/47470)： 这些端口的首选的媒体端口和必须打开，否则将客户端故障回复到 TCP 端口 443。</span><span class="sxs-lookup"><span data-stu-id="34f5a-963">[UDP ports 3478–3481](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Updated-IP-ranges-and-ports-for-Skype-for-Business-Online/ba-p/47470): These ports are the preferred media ports and must be opened, otherwise the client will fail back to TCP port 443.</span></span> |
| <span data-ttu-id="34f5a-964">验证</span><span class="sxs-lookup"><span data-stu-id="34f5a-964">Verify</span></span>             | <span data-ttu-id="34f5a-965">使用[Microsoft 网络评估工具](https://www.microsoft.com/download/details.aspx?id=53885)检查到特定的 Office 365 IP 地址和端口在受影响的构建或子网的连接问题。</span><span class="sxs-lookup"><span data-stu-id="34f5a-965">Use the [Microsoft Network Assessment Tool](https://www.microsoft.com/download/details.aspx?id=53885) to check for connectivity issues to specific Office 365 IP addresses and ports from the affected building or subnet.</span></span>    |

### <a name="investigate-http-proxy-usage"></a><span data-ttu-id="34f5a-966">调查 HTTP 代理使用情况</span><span class="sxs-lookup"><span data-stu-id="34f5a-966">Investigate HTTP proxy usage</span></span>

<span data-ttu-id="34f5a-967">HTTP 代理未建立媒体会话，用于军方的原因的首选的路径。</span><span class="sxs-lookup"><span data-stu-id="34f5a-967">HTTP proxies aren’t the preferred path for establishing media sessions, for a multitude of reasons.</span></span> <span data-ttu-id="34f5a-968">许多包含可以阻止连接到服务正在完成并引入缩至最短的深度数据包检查功能。</span><span class="sxs-lookup"><span data-stu-id="34f5a-968">Many contain deep packet inspection features that can prevent connections to the service from being completed and introduce disruptions.</span></span> <span data-ttu-id="34f5a-969">此外，代理可能而不是允许 UDP，最佳音频质量，建议强制 TCP。</span><span class="sxs-lookup"><span data-stu-id="34f5a-969">Additionally, proxies might force TCP as opposed to allowing UDP, which is recommended for optimal audio quality.</span></span>

<span data-ttu-id="34f5a-970">它始终是 Microsoft 的建议配置客户端直接连接到工作组和 Skype 业务服务。</span><span class="sxs-lookup"><span data-stu-id="34f5a-970">It is always Microsoft’s recommendation to configure the client to directly connect to Teams and Skype for Business services.</span></span> <span data-ttu-id="34f5a-971">这一点尤其重要的基于媒体流量。</span><span class="sxs-lookup"><span data-stu-id="34f5a-971">This is especially important for media-based traffic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="34f5a-972">无有效[构建文件](#building-mapping)上载便于正确区分内外部的音频流在分析代理使用情况。</span><span class="sxs-lookup"><span data-stu-id="34f5a-972">Having a valid [building file](#building-mapping) uploaded makes it easy to properly distinguish inside from outside audio streams when analyzing proxy usage.</span></span> 


#### <a name="audio-streams-with-http-proxy-usage-overall"></a><span data-ttu-id="34f5a-973">HTTP 代理使用率总体音频流</span><span class="sxs-lookup"><span data-stu-id="34f5a-973">Audio streams with HTTP proxy usage overall</span></span>

<span data-ttu-id="34f5a-974">此报告概述随时间在每月范围内的代理服务器使用情况。</span><span class="sxs-lookup"><span data-stu-id="34f5a-974">This report outlines the proxy usage over time on a monthly scale.</span></span> <span data-ttu-id="34f5a-975">本节中的模板中的 HTTP 代理流报告很相似 TCP 报告。</span><span class="sxs-lookup"><span data-stu-id="34f5a-975">The HTTP proxy stream report in this section of the template is much like the TCP reports.</span></span> <span data-ttu-id="34f5a-976">它看起来不在呼叫是否很差或良好，但呼叫是否已通过 HTTP 进行连接。</span><span class="sxs-lookup"><span data-stu-id="34f5a-976">It doesn’t look at whether calls are poor or good, but whether the call is connected over HTTP.</span></span>

![与呼叫质量仪表板中的 HTTP 代理使用情况报告的音频流的屏幕截图。](media/quality-of-experience-review-guide-image26.png)

<span data-ttu-id="34f5a-978">_图 26 – HTTP 代理使用的音频流_</span><span class="sxs-lookup"><span data-stu-id="34f5a-978">_Figure 26 – Audio Streams with HTTP Proxy Usage_</span></span>

##### <a name="analysis"></a><span data-ttu-id="34f5a-979">分析</span><span class="sxs-lookup"><span data-stu-id="34f5a-979">Analysis</span></span>

<span data-ttu-id="34f5a-980">如果您看到较大的 HTTP 使用率，请参阅网络团队以确保正确排除措施，以便客户端直接路由到团队或 Skype 而业务联机媒体子网。</span><span class="sxs-lookup"><span data-stu-id="34f5a-980">If you see a high volume of HTTP usage, consult your networking team to ensure the proper exclusions are in place so that clients are directly routing to Teams or Skype for Business Online media subnets.</span></span> <span data-ttu-id="34f5a-981">理想情况下，应该有此处显示没有 HTTP 用法。</span><span class="sxs-lookup"><span data-stu-id="34f5a-981">Ideally, there should be no HTTP usage displayed here.</span></span>

<span data-ttu-id="34f5a-982">如果已在组织中只有一个 internet 代理，确认正确的[Office 365 Url 和 IP 地址范围排除](https://aka.ms/o365ips)。</span><span class="sxs-lookup"><span data-stu-id="34f5a-982">If you have only one internet proxy in your organization, verify the proper [Office 365 URLs and IP address range exclusions](https://aka.ms/o365ips).</span></span> <span data-ttu-id="34f5a-983">如果多个 internet 代理配置组织中利用 HTTP 子报告以隔离的构建或子网的影响。</span><span class="sxs-lookup"><span data-stu-id="34f5a-983">If more than one internet proxy is configured in your organization, leverage the HTTP sub-report to isolate which building or subnet is affected.</span></span>

<span data-ttu-id="34f5a-984">Skype for Business 的组织的无法绕过代理服务器，确保业务客户端 Skype 配置登录正确时它位于后面代理[一文中所述应使用代理服务器而不是直接尝试登录连接](https://support.microsoft.com/help/3207112/skype-for-business-should-use-proxy-server-to-sign-in-instead-of-tryin)。</span><span class="sxs-lookup"><span data-stu-id="34f5a-984">For organizations that can’t bypass the proxy, ensure that the Skype for Business client is configured to sign in properly when it’s located behind a proxy as outlined in the article [Skype for Business should use proxy server to sign in instead of trying direct connection](https://support.microsoft.com/help/3207112/skype-for-business-should-use-proxy-server-to-sign-in-instead-of-tryin).</span></span>

#### <a name="http-proxy-streams-by-building-and-subnet"></a><span data-ttu-id="34f5a-985">构建和子网的 HTTP 代理流</span><span class="sxs-lookup"><span data-stu-id="34f5a-985">HTTP proxy streams by building and subnet</span></span>

<span data-ttu-id="34f5a-986">此报表标识特定建筑和分配给 HTTP 使用率的子网。</span><span class="sxs-lookup"><span data-stu-id="34f5a-986">This report identifies specific buildings and subnets that are contributing to HTTP usage.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="34f5a-987">无有效[构建文件](#building-mapping)上载便于正确区分内外部的音频流在分析代理使用情况。</span><span class="sxs-lookup"><span data-stu-id="34f5a-987">Having a valid [building file](#building-mapping) uploaded makes it easy to properly distinguish inside from outside audio streams when analyzing proxy usage.</span></span>

> [!NOTE]
> <span data-ttu-id="34f5a-988">请务必调整到当前月份月年筛选器。</span><span class="sxs-lookup"><span data-stu-id="34f5a-988">Be sure to adjust the Month Year filter to the current month.</span></span> <span data-ttu-id="34f5a-989">选择**编辑**，然后调整**月年**保存新默认的月份。</span><span class="sxs-lookup"><span data-stu-id="34f5a-989">Select **Edit**, and adjust **Month Year** to save the new default month.</span></span>                        |

![由构建和子网报告呼叫质量仪表板中的 HTTP 代理使用的屏幕截图。](media/quality-of-experience-review-guide-image27.png)

<span data-ttu-id="34f5a-991">_图 27 – 来构建 HTTP 代理使用率和子网_</span><span class="sxs-lookup"><span data-stu-id="34f5a-991">_Figure 27 – HTTP Proxy Usage by Building and Subnet_</span></span>

##### <a name="remediation"></a><span data-ttu-id="34f5a-992">修正</span><span class="sxs-lookup"><span data-stu-id="34f5a-992">Remediation</span></span>

<span data-ttu-id="34f5a-993">关注您在任何建筑或子网已使用 HTTP 代理上的修复措施。</span><span class="sxs-lookup"><span data-stu-id="34f5a-993">Focus your remediation efforts on any buildings or subnets that have HTTP proxy usage.</span></span> <span data-ttu-id="34f5a-994">HTTP 使用率的最常见原因缺少中代理的例外规则。</span><span class="sxs-lookup"><span data-stu-id="34f5a-994">The most common cause of HTTP usage is missing exception rules in proxies.</span></span> <span data-ttu-id="34f5a-995">通过使用构建或提供的子网，您可以确定哪些代理需要更新。</span><span class="sxs-lookup"><span data-stu-id="34f5a-995">By using the building or subnet provided, you can determine which proxy needs to be updated.</span></span>

<span data-ttu-id="34f5a-996">验证所需的[Office 365 Fqdn](https://aka.ms/o365ips)不包括在您的代理。</span><span class="sxs-lookup"><span data-stu-id="34f5a-996">Verify that the required [Office 365 FQDNs](https://aka.ms/o365ips) are excluded from your proxy.</span></span>

## <a name="endpoint-investigations"></a><span data-ttu-id="34f5a-997">终结点调查</span><span class="sxs-lookup"><span data-stu-id="34f5a-997">Endpoint investigations</span></span>

<span data-ttu-id="34f5a-998">本节重点介绍报告的业务特定客户端版本的 Skype 和使用认证的设备上的任务。</span><span class="sxs-lookup"><span data-stu-id="34f5a-998">This section is focused on the tasks for reporting on Skype for Business–specific client versions and the use of certified devices.</span></span>

> [!NOTE]
> <span data-ttu-id="34f5a-999">在本指南中介绍的模板中包含的不是所有报告。</span><span class="sxs-lookup"><span data-stu-id="34f5a-999">Not all reports included in the templates are covered in this guide.</span></span> <span data-ttu-id="34f5a-1000">请参阅单个报表说明的详细信息。</span><span class="sxs-lookup"><span data-stu-id="34f5a-1000">Please refer to the individual report description for more information.</span></span> 


### <a name="determine-client-versions"></a><span data-ttu-id="34f5a-1001">确定客户端版本</span><span class="sxs-lookup"><span data-stu-id="34f5a-1001">Determine client versions</span></span>

<span data-ttu-id="34f5a-1002">在此处报告着重于 for Business 中使用的客户端版本与环境中的其相对批量标识 Skype。</span><span class="sxs-lookup"><span data-stu-id="34f5a-1002">The report in this space focuses on identifying Skype for Business client versions in use and their relative volume in the environment.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="34f5a-1003">目前，分发并自动更新 Azure 内容交付网络 (CDN) 通过团队客户端和将保持最新的服务。</span><span class="sxs-lookup"><span data-stu-id="34f5a-1003">Currently, Teams clients are distributed and updated automatically through the Azure Content Delivery Network (CDN) and will be kept up to date by the service.</span></span> <span data-ttu-id="34f5a-1004">客户端准备和调查活动不适用于团队。</span><span class="sxs-lookup"><span data-stu-id="34f5a-1004">Client readiness and investigative activities aren’t applicable to Teams.</span></span>

<span data-ttu-id="34f5a-1005">通过以下链接可找到以及业务 2015年 2016 Skype 的版本号：</span><span class="sxs-lookup"><span data-stu-id="34f5a-1005">Version numbers for Skype for Business 2015 and 2016 can be found via the links below:</span></span>

-   [<span data-ttu-id="34f5a-1006">Office 365 客户端更新通道版本</span><span class="sxs-lookup"><span data-stu-id="34f5a-1006">Office 365 client update channel releases</span></span>](https://technet.microsoft.com/office/mt465751?f=255&MSPPError=-2147217396)

-   [<span data-ttu-id="34f5a-1007">单击要运行的 office 365 版本号和内部版本号</span><span class="sxs-lookup"><span data-stu-id="34f5a-1007">Office 365 version and build numbers for Click to run</span></span>](https://support.office.com/article/Version-and-build-numbers-of-update-channel-releases-ae942449-1fca-4484-898b-a933ea23def7)

-   [<span data-ttu-id="34f5a-1008">Skype 业务下载和更新</span><span class="sxs-lookup"><span data-stu-id="34f5a-1008">Skype for Business downloads and updates</span></span>](https://technet.microsoft.com/office/dn788954.aspx)

> [!NOTE] 
> <span data-ttu-id="34f5a-1009">请务必调整到当前月份月年筛选器。</span><span class="sxs-lookup"><span data-stu-id="34f5a-1009">Be sure to adjust the Month Year filter to the current month.</span></span> <span data-ttu-id="34f5a-1010">选择**编辑**，然后调整**月年**保存新默认的月份。</span><span class="sxs-lookup"><span data-stu-id="34f5a-1010">Select **Edit**, and adjust **Month Year** to save the new default month.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="34f5a-1011">客户端报告要求您排除联盟参与者的数据。</span><span class="sxs-lookup"><span data-stu-id="34f5a-1011">Client reports require you to exclude federated participant data.</span></span> <span data-ttu-id="34f5a-1012">若要排除联盟参与者数据，您必须添加**第二个租户 ID**设置为贵组织的[租户 ID](#tenant-id)查询筛选器。</span><span class="sxs-lookup"><span data-stu-id="34f5a-1012">To exclude federated participant data, you must add a query filter for **Second Tenant ID** set to your organization’s [tenant ID](#tenant-id).</span></span> |

![呼叫质量仪表板中的客户端和设备报告的屏幕截图。](media/quality-of-experience-review-guide-image28.png)

<span data-ttu-id="34f5a-1014">_图 28-客户端版本报告_</span><span class="sxs-lookup"><span data-stu-id="34f5a-1014">_Figure 28 - Client version report_</span></span>

#### <a name="remediation"></a><span data-ttu-id="34f5a-1015">修正</span><span class="sxs-lookup"><span data-stu-id="34f5a-1015">Remediation</span></span>

<span data-ttu-id="34f5a-1016">驱动高品质用户体验的关键部分确保托管客户端运行的 Skype for Business 的最新版本。</span><span class="sxs-lookup"><span data-stu-id="34f5a-1016">A critical part of driving high-quality user experiences is ensuring that managed clients are running up-to-date versions of Skype for Business.</span></span> <span data-ttu-id="34f5a-1017">这可以提供有许多益处，其中包括：</span><span class="sxs-lookup"><span data-stu-id="34f5a-1017">This provides several benefits, among them:</span></span>

-   <span data-ttu-id="34f5a-1018">很方便地管理与多个版本的几个版本。</span><span class="sxs-lookup"><span data-stu-id="34f5a-1018">It’s easier to manage a few versions versus many versions.</span></span>

-   <span data-ttu-id="34f5a-1019">它提供了体验的一致性级别。</span><span class="sxs-lookup"><span data-stu-id="34f5a-1019">It provides a level of consistency of experience.</span></span>

-   <span data-ttu-id="34f5a-1020">它可更轻松地解决问题呼叫质量和可用性。</span><span class="sxs-lookup"><span data-stu-id="34f5a-1020">It makes it easier to troubleshoot problems with call quality and usability.</span></span>

-   <span data-ttu-id="34f5a-1021">Microsoft 不断会使跨产品的常规改进和优化。</span><span class="sxs-lookup"><span data-stu-id="34f5a-1021">Microsoft continually makes general improvements and optimizations across the product.</span></span> <span data-ttu-id="34f5a-1022">确保用户接收这些更新减少了运行到已解决的问题的风险。</span><span class="sxs-lookup"><span data-stu-id="34f5a-1022">Ensuring that users receive these updates reduces their risk of running into a problem that has already been solved.</span></span>

<span data-ttu-id="34f5a-1023">限制对客户端版本不超过六个月的部署将改进的整体用户体验，并提高可管理性与具有相同的环境中的大量不同版本的客户端比较。</span><span class="sxs-lookup"><span data-stu-id="34f5a-1023">Limiting your deployment to client versions that are less than six months old will improve the overall user experience and improve manageability compared to having large numbers of different versions of the client in the same environment.</span></span>

<span data-ttu-id="34f5a-1024">如果您正在使用仅 Office 单击即点即，您将自动是六个月的时段内。</span><span class="sxs-lookup"><span data-stu-id="34f5a-1024">If you’re using only Office Click-to-Run, you’ll automatically be within the six-month window.</span></span> <span data-ttu-id="34f5a-1025">不不需要任何进一步的操作。</span><span class="sxs-lookup"><span data-stu-id="34f5a-1025">No further action is required.</span></span>

<span data-ttu-id="34f5a-1026">如果，如大多数组织而言，必须单击即点即用和 installer 程序包 (MSI) 的组合，则可以使用报表以验证定期更新 MSI 客户端。</span><span class="sxs-lookup"><span data-stu-id="34f5a-1026">If, like most organizations, you have a mix of Click-to-Run and installer packages (MSI), you can use the report to verify that the MSI clients are being updated regularly.</span></span> <span data-ttu-id="34f5a-1027">您的措施重点介绍这些客户端，其中卷是高于平均值。</span><span class="sxs-lookup"><span data-stu-id="34f5a-1027">Focus your efforts on those clients where the volume is above average.</span></span> <span data-ttu-id="34f5a-1028">如果您注意到客户端落后，使用团队负责管理 Office 更新，并确保您批准并定期部署客户端修补程序。</span><span class="sxs-lookup"><span data-stu-id="34f5a-1028">If you notice clients are falling behind, work with the team responsible for managing Office updates and ensure that they’re approving and deploying client patches regularly.</span></span>

### <a name="devices-investigations"></a><span data-ttu-id="34f5a-1029">设备调查</span><span class="sxs-lookup"><span data-stu-id="34f5a-1029">Devices investigations</span></span>

<span data-ttu-id="34f5a-1030">若要使使用的以下设备报告，最好了解概念的平均意见得分 (MOS)。</span><span class="sxs-lookup"><span data-stu-id="34f5a-1030">To make use of the following device report, it’s best to understand the concept of the mean opinion score (MOS).</span></span> <span data-ttu-id="34f5a-1031">MOS 是以衡量检测音频质量的金色标准度量值。</span><span class="sxs-lookup"><span data-stu-id="34f5a-1031">MOS is the gold-standard measurement to gauge the perceived audio quality.</span></span> <span data-ttu-id="34f5a-1032">它表示为从 0 到 5 的整数分级。</span><span class="sxs-lookup"><span data-stu-id="34f5a-1032">It’s represented as an integer rating from 0 to 5.</span></span>

<span data-ttu-id="34f5a-1033">语音质量的所有度量值的基础是人员可以语音质量的体验。</span><span class="sxs-lookup"><span data-stu-id="34f5a-1033">The basis of all measures of voice quality is how a person perceives the quality of speech.</span></span> <span data-ttu-id="34f5a-1034">它受 human 认知，因为它是本质上是主观。</span><span class="sxs-lookup"><span data-stu-id="34f5a-1034">Because it’s affected by human perception, it’s inherently subjective.</span></span> <span data-ttu-id="34f5a-1035">有几个不同的方法，用于主观测试。</span><span class="sxs-lookup"><span data-stu-id="34f5a-1035">There are several different methodologies for subjective testing.</span></span>
<span data-ttu-id="34f5a-1036">大多数语音质量度量值基于绝对分类评估 (ACR) 范围。</span><span class="sxs-lookup"><span data-stu-id="34f5a-1036">Most voice quality measures are based on an absolute categorization rating (ACR) scale.</span></span>

<span data-ttu-id="34f5a-1037">在 ACR 主观测试中，统计大量人员评级其用户体验质量的范围为 1 （错误） 为 5 （极好）。</span><span class="sxs-lookup"><span data-stu-id="34f5a-1037">In an ACR subjective test, a statistically significant number of people rate their quality of experience on a scale of 1 (bad) to 5 (excellent).</span></span> <span data-ttu-id="34f5a-1038">MOS 得分的平均值。</span><span class="sxs-lookup"><span data-stu-id="34f5a-1038">The average of the scores is the MOS.</span></span> <span data-ttu-id="34f5a-1039">生成 MOS 取决于已公开到组中，为正在分级的体验的类型的体验的范围。</span><span class="sxs-lookup"><span data-stu-id="34f5a-1039">The resulting MOS depends on the range of experiences that were exposed to the group and to the type of experience being rated.</span></span>

<span data-ttu-id="34f5a-1040">是不切实际进行实时通信系统的语音质量主观测试，因为团队和 Skype for Business 使用高级的算法客观地预测主观测试的结果生成 MOS 值。</span><span class="sxs-lookup"><span data-stu-id="34f5a-1040">Because it’s impractical to conduct subjective tests of voice quality for a live communication system, Teams and Skype for Business generate MOS values by using advanced algorithms to objectively predict the results of a subjective test.</span></span>

<span data-ttu-id="34f5a-1041">提供一组的 MOS 和关联的指标提供到传递给用户体验质量视图。</span><span class="sxs-lookup"><span data-stu-id="34f5a-1041">The available set of MOS and associated metrics provide a view into the quality of the experience being delivered to the users.</span></span>

<span data-ttu-id="34f5a-1042">通过为用户提供认证个团队和 Skype for Business 的设备，可以减少遇到设备本身 （这是更可能，例如，带内置便携式计算机扬声器和麦克风） 由于负体验的可能性。</span><span class="sxs-lookup"><span data-stu-id="34f5a-1042">By supplying users with devices certified for Teams and Skype for Business, you reduce the likelihood of encountering negative experiences due to the device itself (which is more likely, for example, with built-in laptop speakers and microphones).</span></span> <span data-ttu-id="34f5a-1043">有关详细信息，请参阅[电话和设备 for Business 的 Skype](https://technet.microsoft.com/office/dn947482)。</span><span class="sxs-lookup"><span data-stu-id="34f5a-1043">For more information, see [Phones and devices for Skype for Business](https://technet.microsoft.com/office/dn947482).</span></span>

#### <a name="organizational-usage-of-capture-devices-microphones-by-volume"></a><span data-ttu-id="34f5a-1044">捕获设备 （麦克风） 的卷的组织使用情况</span><span class="sxs-lookup"><span data-stu-id="34f5a-1044">Organizational usage of capture devices (microphones) by volume</span></span>

<span data-ttu-id="34f5a-1045">此报告用于评估麦克风使用率卷和 MOS 得分，并可在客户端和设备 *。* 下的相应模板中找到</span><span class="sxs-lookup"><span data-stu-id="34f5a-1045">This report is used to assess microphone usage by volume and MOS score, and can be found in the accompanying templates under Clients & Devices *.*</span></span>

> [!IMPORTANT]
> <span data-ttu-id="34f5a-1046">设备报告要求您排除联盟参与者的数据。</span><span class="sxs-lookup"><span data-stu-id="34f5a-1046">Device reports require you to exclude federated participant data.</span></span> <span data-ttu-id="34f5a-1047">若要排除联盟参与者数据，您必须添加**第二个租户 ID**设置为贵组织的[租户 ID](#tenant-id)查询筛选器。</span><span class="sxs-lookup"><span data-stu-id="34f5a-1047">To exclude federated participant data, you must add a query filter for **Second Tenant ID** set to your organization’s [tenant ID](#tenant-id).</span></span> 

> [!NOTE] 
> <span data-ttu-id="34f5a-1048">请务必调整到当前月份月年筛选器。</span><span class="sxs-lookup"><span data-stu-id="34f5a-1048">Be sure to adjust the Month Year filter to the current month.</span></span> <span data-ttu-id="34f5a-1049">选择**编辑**，然后调整**月年**保存新默认的月份。</span><span class="sxs-lookup"><span data-stu-id="34f5a-1049">Select **Edit**, and adjust **Month Year** to save the new default month.</span></span><br><br> <span data-ttu-id="34f5a-1050">您还可能注意何时查看此报告，您会看到相同的设备报告多次。</span><span class="sxs-lookup"><span data-stu-id="34f5a-1050">You might notice when viewing this report that you see the same device reported multiple times.</span></span> <span data-ttu-id="34f5a-1051">这是由于设备报告向 CQD 报告的方式。</span><span class="sxs-lookup"><span data-stu-id="34f5a-1051">This is due to the way the device is reported being reported to CQD.</span></span> <span data-ttu-id="34f5a-1052">硬件和操作系统区域设置中的差异报告不同设备数据。</span><span class="sxs-lookup"><span data-stu-id="34f5a-1052">Differences in hardware and OS locale report device data differently.</span></span>

![呼叫质量仪表板中的设备 （麦克风） 报告的屏幕截图。](media/quality-of-experience-review-guide-image29.png)

<span data-ttu-id="34f5a-1054">_图 29-– 设备 （麦克风） 报告_</span><span class="sxs-lookup"><span data-stu-id="34f5a-1054">_Figure 29 - – Device (Microphone) Report_</span></span>

##### <a name="remediation"></a><span data-ttu-id="34f5a-1055">修正</span><span class="sxs-lookup"><span data-stu-id="34f5a-1055">Remediation</span></span>

<span data-ttu-id="34f5a-1056">第一个任务是确定要实现 MOS 目标。</span><span class="sxs-lookup"><span data-stu-id="34f5a-1056">The first task is to determine the MOS target you would like to attain.</span></span> <span data-ttu-id="34f5a-1057">MOS 分数介于 1 到 5，与正在最佳 5。</span><span class="sxs-lookup"><span data-stu-id="34f5a-1057">MOS scores range from 1 to 5, with 5 being the best.</span></span> <span data-ttu-id="34f5a-1058">选择根据您的环境和查询结果的合理目标。</span><span class="sxs-lookup"><span data-stu-id="34f5a-1058">Choose a reasonable target based on your environment and query results.</span></span> <span data-ttu-id="34f5a-1059">在以下示例中，则目标为 3.6 或具有 100 流的所有设备的更好的 MOS 得分。</span><span class="sxs-lookup"><span data-stu-id="34f5a-1059">In the following example, the target is an MOS score of 3.6 or better for all devices that have over 100 streams.</span></span> <span data-ttu-id="34f5a-1060">将实现设备质量目标时：</span><span class="sxs-lookup"><span data-stu-id="34f5a-1060">You’ll achieve your device quality target when:</span></span>

-   <span data-ttu-id="34f5a-1061">设备查询结果返回 MOS\>的 NumStreams 3.6 \> 100</span><span class="sxs-lookup"><span data-stu-id="34f5a-1061">The device query results return MOS \> 3.6 for NumStreams \> 100</span></span>

<span data-ttu-id="34f5a-1062">通常情况下，您将需要佳设备替换认证的设备。</span><span class="sxs-lookup"><span data-stu-id="34f5a-1062">Typically, you’ll need to replace poorly performing devices with certified devices.</span></span> <span data-ttu-id="34f5a-1063">查看设备报告时的一些注意事项包括：</span><span class="sxs-lookup"><span data-stu-id="34f5a-1063">Some considerations when reviewing the device report include:</span></span>

-   <span data-ttu-id="34f5a-1064">是认证的设备或已知良好环境中？</span><span class="sxs-lookup"><span data-stu-id="34f5a-1064">Are the devices certified or known to be good in your environment?</span></span> <span data-ttu-id="34f5a-1065">如果您的比较基准比低 MOS 得分为查询中返回认证或良好的设备，可能有未知其他因素 （如较差的网络或性能下降 pc） 分配给低分数。</span><span class="sxs-lookup"><span data-stu-id="34f5a-1065">If a certified or good device is returned in the query with a lower MOS score than your baseline, there may be unknown additional factors (such as a poor network or underpowered pc) that is contributing to the low score.</span></span>
    <span data-ttu-id="34f5a-1066">需要进一步调查。</span><span class="sxs-lookup"><span data-stu-id="34f5a-1066">Additional investigation will be required.</span></span>

-   <span data-ttu-id="34f5a-1067">您可以标识通过[调用分析](#call-analytics-training)的设备的用户。</span><span class="sxs-lookup"><span data-stu-id="34f5a-1067">You can identify users of a device through [Call Analytics](#call-analytics-training).</span></span> <span data-ttu-id="34f5a-1068">检查以确保它们具有最新的设备驱动程序，并且其设备不通过 USB 集线器连接。</span><span class="sxs-lookup"><span data-stu-id="34f5a-1068">Check to make sure they have the latest device drivers and that their device isn’t connected through a USB hub.</span></span>

-   <span data-ttu-id="34f5a-1069">检查是否存在损坏的设备和特定的系统的品牌和型号之间的关联。</span><span class="sxs-lookup"><span data-stu-id="34f5a-1069">Check to see whether there’s a correlation between bad devices and a particular system’s make and model.</span></span> <span data-ttu-id="34f5a-1070">如果跟随，则设备可能会不兼容或者需要驱动程序升级。</span><span class="sxs-lookup"><span data-stu-id="34f5a-1070">If so, the device might be incompatible or need driver upgrades.</span></span>

<span data-ttu-id="34f5a-1071">第二个任务是确定非认证设备的总体使用情况。</span><span class="sxs-lookup"><span data-stu-id="34f5a-1071">The second task is to determine the overall usage of non-certified devices.</span></span> <span data-ttu-id="34f5a-1072">建议至少 80%的所有音频流的使用已认证的设备。</span><span class="sxs-lookup"><span data-stu-id="34f5a-1072">We recommend that at least 80 percent of all audio streams use a certified device.</span></span>
<span data-ttu-id="34f5a-1073">这是最佳通过将设备报告导出到 Excel 和手动计算认证或已批准的设备的使用情况。</span><span class="sxs-lookup"><span data-stu-id="34f5a-1073">This is best accomplished by exporting the Devices report to Excel and manually calculating the usage of certified or approved devices.</span></span> <span data-ttu-id="34f5a-1074">组织通常保留所有批准的设备的列表，以便进行筛选和排序数据应变得非常简单。</span><span class="sxs-lookup"><span data-stu-id="34f5a-1074">Organizations typically keep a list of all approved devices, so filtering and sorting the data should be straightforward.</span></span>

## <a name="appendix-a-lync-networking-guide"></a><span data-ttu-id="34f5a-1075">附录 a。 Lync 网络指南</span><span class="sxs-lookup"><span data-stu-id="34f5a-1075">Appendix A. Lync Networking Guide</span></span>

<span data-ttu-id="34f5a-1076">有关更多背景的团队和 Skype 业务网络概念和基本原理对质量的重要性， [Lync Server 2013 网络指南](https://blogs.technet.microsoft.com/nexthop/2013/06/03/lync-server-2013-networking-guide-network-planning-monitoring-and-troubleshooting-with-microsoft-lync-server/)是仍然适用。</span><span class="sxs-lookup"><span data-stu-id="34f5a-1076">For more background on the Teams and Skype for Business networking concepts and rationale behind their importance to quality, the [Lync Server 2013 Networking Guide](https://blogs.technet.microsoft.com/nexthop/2013/06/03/lync-server-2013-networking-guide-network-planning-monitoring-and-troubleshooting-with-microsoft-lync-server/) is still applicable.</span></span>

## <a name="appendix-b-network-performance-requirements"></a><span data-ttu-id="34f5a-1077">附录 b。 网络性能要求</span><span class="sxs-lookup"><span data-stu-id="34f5a-1077">Appendix B. Network performance requirements</span></span>

<span data-ttu-id="34f5a-1078">Ip 电话 （音频、 视频和应用程序共享） 实时媒体质量会显著影响的端到端网络连接质量。</span><span class="sxs-lookup"><span data-stu-id="34f5a-1078">The quality of real-time media (audio, video, and application sharing) over IP is greatly affected by the quality of end-to-end network connectivity.</span></span> <span data-ttu-id="34f5a-1079">对于最佳工作组或业务媒体质量的 Skype，您的网络必须满足以下网络性能指标。</span><span class="sxs-lookup"><span data-stu-id="34f5a-1079">For optimal Teams or Skype for Business media quality, your network must meet the following network performance metrics.</span></span>

<span data-ttu-id="34f5a-1080">_表 11-网络性能要求_</span><span class="sxs-lookup"><span data-stu-id="34f5a-1080">_Table 11 - Network performance requirements_</span></span>

| <span data-ttu-id="34f5a-1081">指标</span><span class="sxs-lookup"><span data-stu-id="34f5a-1081">Metric</span></span>                           | <span data-ttu-id="34f5a-1082">客户端到 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="34f5a-1082">Client to Microsoft Edge</span></span>           | <span data-ttu-id="34f5a-1083">客户边缘到 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="34f5a-1083">Customer Edge to Microsoft Edge</span></span>    |
|----------------------------------|------------------------------------|------------------------------------|
| <span data-ttu-id="34f5a-1084">延迟 （一种方法）</span><span class="sxs-lookup"><span data-stu-id="34f5a-1084">Latency (one way)</span></span>                | <span data-ttu-id="34f5a-1085">\<50 ms</span><span class="sxs-lookup"><span data-stu-id="34f5a-1085">\<50 ms</span></span>                            | <span data-ttu-id="34f5a-1086">\<30 ms</span><span class="sxs-lookup"><span data-stu-id="34f5a-1086">\<30 ms</span></span>                            |
| <span data-ttu-id="34f5a-1087">延迟 （RTT 或往返时间）</span><span class="sxs-lookup"><span data-stu-id="34f5a-1087">Latency (RTT or Round-trip Time)</span></span> | <span data-ttu-id="34f5a-1088">\<100 毫秒</span><span class="sxs-lookup"><span data-stu-id="34f5a-1088">\<100 ms</span></span>                           | <span data-ttu-id="34f5a-1089">\<60 毫秒</span><span class="sxs-lookup"><span data-stu-id="34f5a-1089">\<60 ms</span></span>                            |
| <span data-ttu-id="34f5a-1090">突发数据包丢失</span><span class="sxs-lookup"><span data-stu-id="34f5a-1090">Burst packet loss</span></span>                | <span data-ttu-id="34f5a-1091">\<任何 200 毫秒间隔期间的 10%</span><span class="sxs-lookup"><span data-stu-id="34f5a-1091">\<10% during any 200-ms interval</span></span>   | <span data-ttu-id="34f5a-1092">\<任何 200 毫秒间隔期间 1%</span><span class="sxs-lookup"><span data-stu-id="34f5a-1092">\<1% during any 200-ms interval</span></span>    |
| <span data-ttu-id="34f5a-1093">数据包丢失</span><span class="sxs-lookup"><span data-stu-id="34f5a-1093">Packet loss</span></span>                      | <span data-ttu-id="34f5a-1094">\<任何 15 秒间隔期间 1%</span><span class="sxs-lookup"><span data-stu-id="34f5a-1094">\<1% during any 15-sec interval</span></span>    | <span data-ttu-id="34f5a-1095">\<0.1 任何 15 秒间隔期间 %</span><span class="sxs-lookup"><span data-stu-id="34f5a-1095">\<0.1% during any 15-sec interval</span></span>  |
| <span data-ttu-id="34f5a-1096">数据包间到达抖动</span><span class="sxs-lookup"><span data-stu-id="34f5a-1096">Packet inter-arrival Jitter</span></span>      | <span data-ttu-id="34f5a-1097">\<任何 15 秒间隔期间 30 ms</span><span class="sxs-lookup"><span data-stu-id="34f5a-1097">\<30 ms during any 15-sec interval</span></span> | <span data-ttu-id="34f5a-1098">\<在任何 15 秒时间间隔 15 ms</span><span class="sxs-lookup"><span data-stu-id="34f5a-1098">\<15 ms during any 15-sec interval</span></span> |
| <span data-ttu-id="34f5a-1099">数据包重新排序</span><span class="sxs-lookup"><span data-stu-id="34f5a-1099">Packet reorder</span></span>                   | <span data-ttu-id="34f5a-1100">\<0.05%无序的数据包</span><span class="sxs-lookup"><span data-stu-id="34f5a-1100">\<0.05% out-of-order packets</span></span>       | <span data-ttu-id="34f5a-1101">\<0.01%无序的数据包</span><span class="sxs-lookup"><span data-stu-id="34f5a-1101">\< 0.01% out-of-order packets</span></span>      |

<span data-ttu-id="34f5a-1102">详细信息，请参阅[媒体质量和网络性能](https://aka.ms/performancerequirements)有关的以下文章个团队和 Skype 业务 online。</span><span class="sxs-lookup"><span data-stu-id="34f5a-1102">For more information, see the following article about [media quality and network performance](https://aka.ms/performancerequirements) for Teams and Skype for Business Online.</span></span>

<a name="other-resources"></a>

## <a name="appendix-c-other-resources"></a><span data-ttu-id="34f5a-1103">附录 c。其他资源</span><span class="sxs-lookup"><span data-stu-id="34f5a-1103">Appendix C. Other resources</span></span>

### <a name="building-data-file"></a><span data-ttu-id="34f5a-1104">正在创建数据文件</span><span class="sxs-lookup"><span data-stu-id="34f5a-1104">Building data file</span></span>

-   [<span data-ttu-id="34f5a-1105">打开和使用 CQD 中 Skype 业务联机</span><span class="sxs-lookup"><span data-stu-id="34f5a-1105">Turning on and using CQD in Skype for Business Online</span></span>](https://support.office.com/article/Turning-on-and-using-Call-Quality-Dashboard-in-Skype-for-Business-Online-553fa13c-92d2-4d5c-a3d5-41a073cb047c)

<a name="CQD-training"></a>

### <a name="cqd-training"></a><span data-ttu-id="34f5a-1106">CQD 培训</span><span class="sxs-lookup"><span data-stu-id="34f5a-1106">CQD training</span></span>

-   <https://aka.ms/sof-cqd>

-   <span data-ttu-id="34f5a-1107">[CQD 入门](https://www.skypeoperationsframework.com/Academy?SOFTrainings=Configuring%20Call%20Quality%20Dashboard%20to%20monitor%20your%20Skype%20for%20Business%20Online%20Environment)指南和研讨会 （英文）。</span><span class="sxs-lookup"><span data-stu-id="34f5a-1107">[Getting started with CQD](https://www.skypeoperationsframework.com/Academy?SOFTrainings=Configuring%20Call%20Quality%20Dashboard%20to%20monitor%20your%20Skype%20for%20Business%20Online%20Environment) guide and workshop.</span></span>

-   [<span data-ttu-id="34f5a-1108">CQD 维度和度量联机指南</span><span class="sxs-lookup"><span data-stu-id="34f5a-1108">CQD Dimensions and Measures online guide</span></span>](https://support.office.com/article/Dimensions-and-measures-available-in-Call-Quality-Dashboard-in-Skype-for-Business-Online-e97aeeee-9e43-416f-b433-9cdd63d8874b)

### <a name="call-analytics-training"></a><span data-ttu-id="34f5a-1109">呼叫分析培训</span><span class="sxs-lookup"><span data-stu-id="34f5a-1109">Call Analytics training</span></span>

-   [<span data-ttu-id="34f5a-1110">介绍呼叫分析</span><span class="sxs-lookup"><span data-stu-id="34f5a-1110">Introducing Call Analytics</span></span>](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309)

-   [<span data-ttu-id="34f5a-1111">设置 Skype for Business 通话分析</span><span class="sxs-lookup"><span data-stu-id="34f5a-1111">Set up Skype for Business Call Analytics</span></span>](https://support.office.com/article/Set-up-Skype-for-Business-Call-Analytics-FBF7247A-84AE-46CC-9204-2C45B1C734CD)

-   [<span data-ttu-id="34f5a-1112">通话分析与通话质量仪表板之间有何区别？</span><span class="sxs-lookup"><span data-stu-id="34f5a-1112">What's the difference between Call Analytics and Call Quality Dashboard?</span></span>](https://support.office.com/article/What-s-the-difference-between-Call-Analytics-and-Call-Quality-Dashboard-4CD5FE35-8463-4996-A252-086CD3CA2D9A)

-   [<span data-ttu-id="34f5a-1113">使用通话分析解决 Skype for Business 通话质量不佳的问题</span><span class="sxs-lookup"><span data-stu-id="34f5a-1113">Use Call Analytics to troubleshoot poor Skype for Business call quality</span></span>](https://support.office.com/article/Use-Call-Analytics-to-troubleshoot-poor-Skype-for-Business-call-quality-66945036-ae87-4c08-a0bb-984e50d6b009)

### <a name="call-analytics-support"></a><span data-ttu-id="34f5a-1114">呼叫分析支持</span><span class="sxs-lookup"><span data-stu-id="34f5a-1114">Call Analytics support</span></span>

-   <span data-ttu-id="34f5a-1115">社区： [Skype 业务预览程序](https://techcommunity.microsoft.com/t5/Skype-for-Business-Preview/bd-p/SkypeforBusinessPreviewProgram)</span><span class="sxs-lookup"><span data-stu-id="34f5a-1115">Community: [Skype for Business Preview Program](https://techcommunity.microsoft.com/t5/Skype-for-Business-Preview/bd-p/SkypeforBusinessPreviewProgram)</span></span>

-   <span data-ttu-id="34f5a-1116">要获得支持，登录到我们预览门户[www.skypepreview.com](http://www.skypepreview.com)、 选择**报告问题**，并**创建新的 Bug**选项用于报告问题。</span><span class="sxs-lookup"><span data-stu-id="34f5a-1116">To get support, sign in to our preview portal [www.skypepreview.com](http://www.skypepreview.com), select **Report an issue**, and use the **Create New Bug** option to report an issue.</span></span> <span data-ttu-id="34f5a-1117">请注意，支持工程师可以提供支持从周一到周五，之间的小时数 6 到 9 PM EST。</span><span class="sxs-lookup"><span data-stu-id="34f5a-1117">Please note that support engineers are available to provide support from Monday through Friday, between the hours of 6 AM to 9 PM EST.</span></span> <span data-ttu-id="34f5a-1118">将要请求之外这些小时会审下一天。</span><span class="sxs-lookup"><span data-stu-id="34f5a-1118">Requests outside of those hours will be triaged the following day.</span></span>

### <a name="devices"></a><span data-ttu-id="34f5a-1119">设备</span><span class="sxs-lookup"><span data-stu-id="34f5a-1119">Devices</span></span>

-   [<span data-ttu-id="34f5a-1120">为业务解决方案的 Skype 目录个人外设和 Pc</span><span class="sxs-lookup"><span data-stu-id="34f5a-1120">Skype for Business Solutions Catalog Personal Peripherals & PCs</span></span>](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs)

### <a name="tenant-reporting"></a><span data-ttu-id="34f5a-1121">报告的租户</span><span class="sxs-lookup"><span data-stu-id="34f5a-1121">Tenant reporting</span></span>

-   [<span data-ttu-id="34f5a-1122">Office 365 应用内容包</span><span class="sxs-lookup"><span data-stu-id="34f5a-1122">Office 365 Adoption Content Pack</span></span>](https://blogs.office.com/2017/05/22/announcing-the-public-preview-of-the-office-365-adoption-content-pack-in-powerbi/)

-   [<span data-ttu-id="34f5a-1123">Skype for Business Online 报告</span><span class="sxs-lookup"><span data-stu-id="34f5a-1123">Skype for Business Online reporting</span></span>](https://support.office.com/article/Skype-for-Business-Online-reporting-4935cddf-fafa-442d-91a3-246af01f8373)

-   [<span data-ttu-id="34f5a-1124">报告的 Microsoft 团队</span><span class="sxs-lookup"><span data-stu-id="34f5a-1124">Microsoft Teams reporting</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/New-usage-reports-for-Microsoft-Teams/ba-p/132614)
