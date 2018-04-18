---
title: Microsoft 小组的经验审查指南的质量
author: rmw2890
ms.author: MyAdvisor
manager: lehewe
ms.date: 04/12/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: 通过使用呼叫质量仪表板 (CQD) 分析 Microsoft 小组的实时媒体性能的指南。
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 42af71e9062b68da6e9d3bc77a6c067eee35ec92
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="quality-of-experience-review-guide"></a><span data-ttu-id="de2e2-103">质量的经验审查指南</span><span class="sxs-lookup"><span data-stu-id="de2e2-103">Quality of Experience Review Guide</span></span>

<span data-ttu-id="de2e2-104">本指南是关于 Microsoft 小组和 Skype 的在线业务的推动价值阶段。</span><span class="sxs-lookup"><span data-stu-id="de2e2-104">This guide is about the Drive Value phase for Microsoft Teams and Skype for Business Online.</span></span> <span data-ttu-id="de2e2-105">您可以在本指南的[下载 Word 版本](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/quality-of-experience-review-guide.docx?raw=true)。</span><span class="sxs-lookup"><span data-stu-id="de2e2-105">You can [download a Word version](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/quality-of-experience-review-guide.docx?raw=true) of this guide.</span></span>

## <a name="introduction"></a><span data-ttu-id="de2e2-106">简介</span><span class="sxs-lookup"><span data-stu-id="de2e2-106">Introduction</span></span>

<span data-ttu-id="de2e2-107">若要提高用户体验的影响最大，企业需要实施如下图所示的关键领域。</span><span class="sxs-lookup"><span data-stu-id="de2e2-107">To have the greatest impact on improving the user experience, organizations need to operationalize the key areas that are shown in the following figure.</span></span>
<span data-ttu-id="de2e2-108">其他领域包括标识操作任务、 建立质量标准的目标、 有助于确定的指标，用于衡量企业成功，和收缩方面的调查，根据需要。</span><span class="sxs-lookup"><span data-stu-id="de2e2-108">Additional areas include identifying operational tasks, establishing targets for quality metrics, ascertaining the metrics to use to gauge organizational success, and narrowing areas of investigation as needed.</span></span>

![用户体验的质量有关的关键领域包括音频、 可靠性、 用户调查、 设备和客户端。](media/quality-of-experience-review-guide-image1.png)

<span data-ttu-id="de2e2-110">_图 1-键操作领域涵盖本文档_</span><span class="sxs-lookup"><span data-stu-id="de2e2-110">_Figure 1 - Key operational areas covered throughout this document_</span></span>

<span data-ttu-id="de2e2-111">通过不断地评估和纠正本文所述的区域，可以减少他们可能会对您的用户体验的质量产生负面影响。</span><span class="sxs-lookup"><span data-stu-id="de2e2-111">By continually assessing and remediating the areas described in this document, you can reduce their potential to negatively affect the quality of your users’ experience.</span></span> <span data-ttu-id="de2e2-112">在部署中遇到的大多数用户体验问题可以分为以下几类：</span><span class="sxs-lookup"><span data-stu-id="de2e2-112">Most user-experience problems encountered in a deployment can be grouped into the following categories:</span></span>

-   <span data-ttu-id="de2e2-113">不完整的防火墙或代理服务器配置</span><span class="sxs-lookup"><span data-stu-id="de2e2-113">Incomplete firewall or proxy configuration</span></span>

-   <span data-ttu-id="de2e2-114">较差的 Wi-fi 覆盖范围</span><span class="sxs-lookup"><span data-stu-id="de2e2-114">Poor Wi-Fi coverage</span></span>

-   <span data-ttu-id="de2e2-115">没有足够的带宽</span><span class="sxs-lookup"><span data-stu-id="de2e2-115">Insufficient bandwidth</span></span>

-   <span data-ttu-id="de2e2-116">VPN</span><span class="sxs-lookup"><span data-stu-id="de2e2-116">VPN</span></span>

-   <span data-ttu-id="de2e2-117">不一致的或过期的客户端版本</span><span class="sxs-lookup"><span data-stu-id="de2e2-117">Inconsistent or outdated client versions</span></span>

-   <span data-ttu-id="de2e2-118">未优化或内置的音频设备</span><span class="sxs-lookup"><span data-stu-id="de2e2-118">Unoptimized or built-in audio devices</span></span>

-   <span data-ttu-id="de2e2-119">有问题的子网或网络设备</span><span class="sxs-lookup"><span data-stu-id="de2e2-119">Problematic subnets or network devices</span></span>

<span data-ttu-id="de2e2-120">通过适当的规划和部署团队或 Skype 业务联机之前的设计，可以减少需要维护体验高质量的工作。</span><span class="sxs-lookup"><span data-stu-id="de2e2-120">Through proper planning and design before deploying Teams or Skype for Business Online, you can reduce the amount of effort that will be required to maintain high-quality experiences.</span></span>

<span data-ttu-id="de2e2-121">本指南重点介绍作为主要工具使用呼叫质量仪表板 (CQD) 在线报告，并研究每个区域中的，音频，以最大限度地采用和影响特别强调。</span><span class="sxs-lookup"><span data-stu-id="de2e2-121">This guide focuses on using the Call Quality Dashboard (CQD) Online as the primary tool to report and investigate each area, with a special emphasis on audio to maximize adoption and impact.</span></span> <span data-ttu-id="de2e2-122">视频和桌面共享的改进将还直接转化为提高音频体验到网络所做的任何改进。</span><span class="sxs-lookup"><span data-stu-id="de2e2-122">Any improvements made to the network to improve the audio experience will also directly translate to improvements in video and desktop sharing.</span></span>

<span data-ttu-id="de2e2-123">为了加快您的评估，提供两个 curated 的 CQD 模板： 一个管理所有网络和其他的筛选管理仅使用 （在内部） 网络。</span><span class="sxs-lookup"><span data-stu-id="de2e2-123">To accelerate your assessment, two curated CQD templates are provided: one for managing all networks and the other is filtered for managed (internal) networks only.</span></span> <span data-ttu-id="de2e2-124">尽管所有网络模板报告被配置为显示建筑物和网络信息，但它仍可用于同时朝着正在收集并上载生成信息。</span><span class="sxs-lookup"><span data-stu-id="de2e2-124">Although the All Networks template reports are configured to display building and network information, it can still be used while you work toward collecting and uploading building information.</span></span> <span data-ttu-id="de2e2-125">上载构建成 CQD 的信息使服务能够增强通过添加自定义构建、 网络和位置信息，同时区分从外部子网内部报告。</span><span class="sxs-lookup"><span data-stu-id="de2e2-125">Uploading building information into CQD enables the service to enhance reporting by adding custom building, network, and location information while differentiating internal from external subnets.</span></span> <span data-ttu-id="de2e2-126">有关详细信息，请参见本文档后面的[建筑映射](#building-mapping)。</span><span class="sxs-lookup"><span data-stu-id="de2e2-126">For more information, see [Building mapping](#building-mapping) later in this document.</span></span>

### <a name="what-is-the-cqd"></a><span data-ttu-id="de2e2-127">CQD 是什么？</span><span class="sxs-lookup"><span data-stu-id="de2e2-127">What is the CQD?</span></span>

<span data-ttu-id="de2e2-128">使用调用质量仪表板 (CQD) 为深入的业务服务通过团队和 Skype 电话的质量。</span><span class="sxs-lookup"><span data-stu-id="de2e2-128">You use the Call Quality Dashboard (CQD) to gain insight into the quality of calls made by using Teams and Skype for Business services.</span></span> <span data-ttu-id="de2e2-129">CQD 旨在帮助 Skype 业务和团队管理员和网络工程师优化网络。</span><span class="sxs-lookup"><span data-stu-id="de2e2-129">CQD is designed to help Skype for Business and Teams admins and network engineers optimize the network.</span></span> <span data-ttu-id="de2e2-130">CQD 探讨聚合信息，为整个组织整体模式可能会明显，允许人员进行明智的呼叫质量评估。</span><span class="sxs-lookup"><span data-stu-id="de2e2-130">CQD looks at aggregate information for an entire organization where overall patterns can become apparent, allowing staff to make informed assessments of call quality.</span></span> <span data-ttu-id="de2e2-131">CQD 提供让您深入了解总体的通话质量、 电话可靠性和用户体验的调用指标的报告。</span><span class="sxs-lookup"><span data-stu-id="de2e2-131">CQD provides reports of call metrics that give you insight into overall call quality, call reliability, and user experience.</span></span>

> [!NOTE]
> <span data-ttu-id="de2e2-132">CQD 不包含任何个人身份信息 (PII)。</span><span class="sxs-lookup"><span data-stu-id="de2e2-132">CQD doesn’t contain any personally identifiable information (PII).</span></span> <span data-ttu-id="de2e2-133">PII 是可用于单独或与其他信息来标识、 联系或找到一个人，或以识别上下文中的个体的信息。</span><span class="sxs-lookup"><span data-stu-id="de2e2-133">PII is information that can be used on its own or with other information to identify, contact, or locate a single person, or to identify an individual in context.</span></span> 

### <a name="intended-audience"></a><span data-ttu-id="de2e2-134">目标的读者</span><span class="sxs-lookup"><span data-stu-id="de2e2-134">Intended audience</span></span>

<span data-ttu-id="de2e2-135">本文档旨在将由合作伙伴和客户风险承担者的角色，如协作领导架构师、 顾问、 更改管理/采用专家、 领导支持/帮助台、 网络导致、 桌面潜在顾客和 IT 管理员。</span><span class="sxs-lookup"><span data-stu-id="de2e2-135">This document is intended to be used by partner and customer stakeholders with roles such as Collaboration Lead/Architect, Consultant, Change Management/Adoption Specialist, Support/Help Desk Lead, Network Lead, Desktop Lead, and IT Admin.</span></span>

<span data-ttu-id="de2e2-136">本文档旨在还将由指定的质量 champion(s)。</span><span class="sxs-lookup"><span data-stu-id="de2e2-136">This document is also intended to be used by the designated quality champion(s).</span></span>
<span data-ttu-id="de2e2-137">有关详细信息，请参阅[质量冠军角色](https://docs.microsoft.com/MicrosoftTeams/4-envision-plan-my-service-management#the-quality-champion-role)。</span><span class="sxs-lookup"><span data-stu-id="de2e2-137">For more information, see [the Quality Champion role](https://docs.microsoft.com/MicrosoftTeams/4-envision-plan-my-service-management#the-quality-champion-role).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="de2e2-138">先决条件</span><span class="sxs-lookup"><span data-stu-id="de2e2-138">Prerequisites</span></span>

<span data-ttu-id="de2e2-139">使用本指南之前, 请确保您有适当的组织[角色](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)分配，以便您可以访问 CQD。</span><span class="sxs-lookup"><span data-stu-id="de2e2-139">Before using this guide, make sure you have the proper tenant [roles](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d) assigned so that you can access CQD.</span></span>

-   <span data-ttu-id="de2e2-140">**Office 365 全局管理员角色：**在计划中，包括业务的 Skype 访问 Office 365 套服务中的所有管理功能。</span><span class="sxs-lookup"><span data-stu-id="de2e2-140">**Office 365 Global Administrator role:** Accesses all administrative features in the Office 365 suite of services in your plan, including Skype for Business.</span></span>

-   <span data-ttu-id="de2e2-141">**业务管理员角色的 Skype:**为您的组织配置为业务 Skype 和能够在 Office 365 管理中心查看所有[活动的报告](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263)。</span><span class="sxs-lookup"><span data-stu-id="de2e2-141">**Skype for Business Administrator role:** Configures Skype for Business for your organization and is able to view all the [activity reports](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) in the Office 365 admin center.</span></span> <span data-ttu-id="de2e2-142">此角色是必需的即使部署只团队。</span><span class="sxs-lookup"><span data-stu-id="de2e2-142">This role is required even if you deploy only Teams.</span></span>

<span data-ttu-id="de2e2-143">或者，可以将以下角色分配给 Office 365 提供用户帐户以允许访问报告的功能。</span><span class="sxs-lookup"><span data-stu-id="de2e2-143">Alternatively, you can assign the following role to an Office 365 user account to allow access to reporting features only.</span></span>

-   <span data-ttu-id="de2e2-144">**报告读取器：**Office 365 管理中心、 任何来自[Office 365 采用内容包](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f)，报告和 CQD 报表中，可以查看所有[活动的报告](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263)。</span><span class="sxs-lookup"><span data-stu-id="de2e2-144">**Reports Reader:** Can view all the [activity reports](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) in the Office 365 admin center, any reports from the [Office 365 Adoption content pack](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f), and CQD reports.</span></span>

<span data-ttu-id="de2e2-145">了解关键概念的 CQD 帮助最大化可以改善用户的体验与团队或 Skype 的在线业务的影响。</span><span class="sxs-lookup"><span data-stu-id="de2e2-145">Understanding the key concepts of CQD helps maximize the impact you can make in improving your users’ experience with Teams or Skype for Business Online.</span></span>
<span data-ttu-id="de2e2-146">在[附录](#other-resources)中找不到更多的资源。</span><span class="sxs-lookup"><span data-stu-id="de2e2-146">Additional resources can be found in the [Appendix](#other-resources).</span></span>

## <a name="what-is-quality"></a><span data-ttu-id="de2e2-147">品质是什么？</span><span class="sxs-lookup"><span data-stu-id="de2e2-147">What is quality?</span></span>

<span data-ttu-id="de2e2-148">在讨论质量团队和业务的 Skype，务必要定义术语能够达成共识。</span><span class="sxs-lookup"><span data-stu-id="de2e2-148">When discussing quality in Teams and Skype for Business, it’s important to define the term to achieve a common understanding.</span></span> <span data-ttu-id="de2e2-149">在这里，定义质量，是组合服务标准和用户体验。</span><span class="sxs-lookup"><span data-stu-id="de2e2-149">Quality, as defined here, is a combination of service metrics and user experience.</span></span>

![服务度量组成差调用比、 可靠性、 终结点中的设备和客户端版本。](media/quality-of-experience-review-guide-image2.png)

<span data-ttu-id="de2e2-152">_图 2-品质是什么？_</span><span class="sxs-lookup"><span data-stu-id="de2e2-152">_Figure 2 - What is quality?_</span></span>

### <a name="define-your-target-metrics"></a><span data-ttu-id="de2e2-153">定义目标度量</span><span class="sxs-lookup"><span data-stu-id="de2e2-153">Define your target metrics</span></span>

<span data-ttu-id="de2e2-154">本节讨论评估服务经验，健康状况如何，我们使用的核心服务指标。</span><span class="sxs-lookup"><span data-stu-id="de2e2-154">This section discusses the core service metrics that we use to assess how services experience health.</span></span> <span data-ttu-id="de2e2-155">通过不断地评估和推动工作，以使这些指标低于目标，将帮助确保您的用户体验一致、 可靠的呼叫质量。</span><span class="sxs-lookup"><span data-stu-id="de2e2-155">By continually assessing and driving efforts to keep these metrics below target, you’ll help ensure your users experience consistent, reliable call quality.</span></span> <span data-ttu-id="de2e2-156">为了帮助您入门，请提供以下的目标。</span><span class="sxs-lookup"><span data-stu-id="de2e2-156">To get you started, the following targets are provided.</span></span>
<span data-ttu-id="de2e2-157">让我们简要介绍托管和非托管网络之间的区别：</span><span class="sxs-lookup"><span data-stu-id="de2e2-157">Let’s briefly cover the difference between a managed and unmanaged network:</span></span>

-   <span data-ttu-id="de2e2-158">可以影响和控制的组织*管理*网络。</span><span class="sxs-lookup"><span data-stu-id="de2e2-158">A *managed* network can be influenced and controlled by the organization.</span></span>
    <span data-ttu-id="de2e2-159">这包括内部局域网、 远程广域网和 VPN。</span><span class="sxs-lookup"><span data-stu-id="de2e2-159">This includes the internal LAN, the remote WAN, and VPN.</span></span>

-   <span data-ttu-id="de2e2-160">*非托管*网络无法影响或控制的组织。</span><span class="sxs-lookup"><span data-stu-id="de2e2-160">An *unmanaged* network can’t be influenced or controlled by the organization.</span></span> <span data-ttu-id="de2e2-161">非托管网络的一个例子是旅馆或机场网络。</span><span class="sxs-lookup"><span data-stu-id="de2e2-161">An example of an unmanaged network is a hotel or airport network.</span></span>

<span data-ttu-id="de2e2-162">_表 1-核心目标运行状况评估指标_</span><span class="sxs-lookup"><span data-stu-id="de2e2-162">_Table 1 - Core target health assessment metrics_</span></span>

|               | <span data-ttu-id="de2e2-163">托管网络质量</span><span class="sxs-lookup"><span data-stu-id="de2e2-163">Quality for managed networks</span></span> | <span data-ttu-id="de2e2-164">对于托管网络的可靠性</span><span class="sxs-lookup"><span data-stu-id="de2e2-164">Reliability for managed networks</span></span> |                      |
|---------------|------------------------------|----------------------------------|----------------------|
| <span data-ttu-id="de2e2-165">指标名称</span><span class="sxs-lookup"><span data-stu-id="de2e2-165">Metric name</span></span>   | <span data-ttu-id="de2e2-166">音频质量较差的呼叫率 %</span><span class="sxs-lookup"><span data-stu-id="de2e2-166">Audio Poor Call Ratio %</span></span>      | <span data-ttu-id="de2e2-167">调用安装程序失败百分比</span><span class="sxs-lookup"><span data-stu-id="de2e2-167">Call Setup Failures %</span></span>            | <span data-ttu-id="de2e2-168">调用放失败百分比</span><span class="sxs-lookup"><span data-stu-id="de2e2-168">Call Drop Failures %</span></span> |
| <span data-ttu-id="de2e2-169">示例的目标</span><span class="sxs-lookup"><span data-stu-id="de2e2-169">Sample target</span></span> | <span data-ttu-id="de2e2-170">\<3%</span><span class="sxs-lookup"><span data-stu-id="de2e2-170">\<3%</span></span>                         | <span data-ttu-id="de2e2-171">\<1%</span><span class="sxs-lookup"><span data-stu-id="de2e2-171">\<1%</span></span>                             | <span data-ttu-id="de2e2-172">\<4%</span><span class="sxs-lookup"><span data-stu-id="de2e2-172">\<4%</span></span>                 |

<span data-ttu-id="de2e2-173">值得讨论和定义贵组织的目标，以满足您的业务目标。</span><span class="sxs-lookup"><span data-stu-id="de2e2-173">It’s important to discuss and define your organization’s targets to meet your business objectives.</span></span> <span data-ttu-id="de2e2-174">理想情况下，应确定在部署之前这些目标。</span><span class="sxs-lookup"><span data-stu-id="de2e2-174">Ideally, you should identify these targets prior to deployment.</span></span>

#### <a name="audio-pcr-"></a><span data-ttu-id="de2e2-175">音频的 PCR %</span><span class="sxs-lookup"><span data-stu-id="de2e2-175">Audio PCR %</span></span> 

<span data-ttu-id="de2e2-176">音频差调用比率 (PCR) 表示调用具有音频质量差的单位的总体百分比。</span><span class="sxs-lookup"><span data-stu-id="de2e2-176">Audio Poor Call Ratio (PCR) represents the organization’s overall percentage of calls that have poor audio quality.</span></span> <span data-ttu-id="de2e2-177">此统计数据是为了突出显示的区域，您的组织可以专注努力产生强大影响朝着减小此值，并改善用户体验，这就是托管的网络时观察 PCR 是主要原因。</span><span class="sxs-lookup"><span data-stu-id="de2e2-177">This metric is meant to highlight areas where your organization can concentrate effort to have the strongest impact toward reducing this value and improving the user experience, which is why managed networks are the primary focus when looking at PCR.</span></span> <span data-ttu-id="de2e2-178">外部用户是很重要，但调查不同组织和用户的基础上。</span><span class="sxs-lookup"><span data-stu-id="de2e2-178">External users are important too, but investigations differs on an organizational and user basis.</span></span>
<span data-ttu-id="de2e2-179">考虑提供最佳做法对于外部用户，并查看独立于整个组织的外部调用。</span><span class="sxs-lookup"><span data-stu-id="de2e2-179">Consider providing best practices for external users, and look at external calls independently from the overall organization.</span></span>

#### <a name="call-setup-failures-"></a><span data-ttu-id="de2e2-180">调用安装程序失败百分比</span><span class="sxs-lookup"><span data-stu-id="de2e2-180">Call Setup Failures %</span></span> 

<span data-ttu-id="de2e2-181">这表示无法建立任何媒体会话。</span><span class="sxs-lookup"><span data-stu-id="de2e2-181">This represents any media session that couldn’t be established.</span></span> <span data-ttu-id="de2e2-182">此处测量用户体验上，给出影响的严重性，目的是降低此值改为接近零。</span><span class="sxs-lookup"><span data-stu-id="de2e2-182">Given the severity of the impact on the user experience measured here, the goal is to reduce this value to as close to zero as possible.</span></span> <span data-ttu-id="de2e2-183">此度量值高是更比成熟的部署，在新部署中不完整的防火墙规则与常见但仍然很重要，要定期进行监视。</span><span class="sxs-lookup"><span data-stu-id="de2e2-183">A high value for this metric is more common in new deployments with incomplete firewall rules than a mature deployment, but it’s still important to watch on a regular basis.</span></span> <span data-ttu-id="de2e2-184">随着您操作的严格程度的逐渐成熟，您可以展开该度量包括视频和桌面共享工作负载。</span><span class="sxs-lookup"><span data-stu-id="de2e2-184">As your operational rigor matures, you can expand this metric to include video and desktop-sharing workloads.</span></span>

#### <a name="call-drop-failures-"></a><span data-ttu-id="de2e2-185">调用放失败百分比</span><span class="sxs-lookup"><span data-stu-id="de2e2-185">Call Drop Failures %</span></span> 

<span data-ttu-id="de2e2-186">这适用于会话意外终止音频工作负荷。</span><span class="sxs-lookup"><span data-stu-id="de2e2-186">This applies to an audio workload where the session terminated unexpectedly.</span></span> <span data-ttu-id="de2e2-187">随着您操作的严格程度的逐渐成熟，您可以展开该度量包括视频和桌面共享工作负载。</span><span class="sxs-lookup"><span data-stu-id="de2e2-187">As your operational rigor matures, you can expand this metric to include video and desktop-sharing workloads.</span></span>

### <a name="service-metrics"></a><span data-ttu-id="de2e2-188">服务度量</span><span class="sxs-lookup"><span data-stu-id="de2e2-188">Service metrics</span></span>

<span data-ttu-id="de2e2-189">服务度量目标包含的基于客户端的特定指标。</span><span class="sxs-lookup"><span data-stu-id="de2e2-189">Service metric targets consist of specific client-based metrics.</span></span>

#### <a name="pcr"></a><span data-ttu-id="de2e2-190">PCR</span><span class="sxs-lookup"><span data-stu-id="de2e2-190">PCR</span></span>

<span data-ttu-id="de2e2-191">确定是否将调用归类为较差的基础是使用较差的呼叫率 (PCR)。</span><span class="sxs-lookup"><span data-stu-id="de2e2-191">The basis for determining whether a call is classified as poor is by using the poor call ratio (PCR).</span></span> <span data-ttu-id="de2e2-192">PCR 是下表中所述五个网络跃点值组成。</span><span class="sxs-lookup"><span data-stu-id="de2e2-192">PCR is made up of the five network metrics described in the following table.</span></span> <span data-ttu-id="de2e2-193">执行调用以将归类为较差，只有一个指标需要超过定义的阈值。</span><span class="sxs-lookup"><span data-stu-id="de2e2-193">For a call to be classified as poor, only one metric needs to exceed the defined threshold.</span></span> <span data-ttu-id="de2e2-194">有关调用分类过程的详细信息，请参见[以下博客文章](https://blogs.technet.microsoft.com/jenstr/2013/09/20/what-is-the-basis-for-classifying-a-call-as-poor-in-lync-2013-qoe/)。</span><span class="sxs-lookup"><span data-stu-id="de2e2-194">For more information about the call classification process, see [this blog post](https://blogs.technet.microsoft.com/jenstr/2013/09/20/what-is-the-basis-for-classifying-a-call-as-poor-in-lync-2013-qoe/).</span></span>

<span data-ttu-id="de2e2-195">_表 2-差调用服务标准_</span><span class="sxs-lookup"><span data-stu-id="de2e2-195">_Table 2 - Poor Call Service Metrics_</span></span>

| <span data-ttu-id="de2e2-196">指标</span><span class="sxs-lookup"><span data-stu-id="de2e2-196">Metric</span></span>                                           | <span data-ttu-id="de2e2-197">说明</span><span class="sxs-lookup"><span data-stu-id="de2e2-197">Description</span></span>                                                                                                                                                                                                                                                                                                                                                                  | <span data-ttu-id="de2e2-198">用户体验</span><span class="sxs-lookup"><span data-stu-id="de2e2-198">User experience</span></span>                                                                                                                                                          |
|--------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="de2e2-199">抖动\>30 毫秒</span><span class="sxs-lookup"><span data-stu-id="de2e2-199">Jitter \>30 ms</span></span>                                   | <span data-ttu-id="de2e2-200">这是连续数据包之间的延迟的平均变化。</span><span class="sxs-lookup"><span data-stu-id="de2e2-200">This is the average change in delay between successive packets.</span></span> <span data-ttu-id="de2e2-201">团队和业务的 Skype 可以适应抖动缓冲通过某些级别。</span><span class="sxs-lookup"><span data-stu-id="de2e2-201">Teams and Skype for Business can adapt to some levels of jitter through buffering.</span></span> <span data-ttu-id="de2e2-202">它是抖动的只有当抖动超过缓冲参与者注意到的影响。</span><span class="sxs-lookup"><span data-stu-id="de2e2-202">It’s only when the jitter exceeds the buffering that a participant notices the effects of jitter.</span></span>                                                                                                                         | <span data-ttu-id="de2e2-203">以不同速度到达的数据包会导致用户的声音要听机器人。</span><span class="sxs-lookup"><span data-stu-id="de2e2-203">The packets arriving at different speeds cause a speaker’s voice to sound robotic.</span></span>                                                                                       |
| <span data-ttu-id="de2e2-204">数据包丢失率\>10%或 0.1</span><span class="sxs-lookup"><span data-stu-id="de2e2-204">Packet loss rate \>10% or 0.1</span></span>                    | <span data-ttu-id="de2e2-205">这通常被指将丢失的数据包的百分比。</span><span class="sxs-lookup"><span data-stu-id="de2e2-205">This is often defined as a percentage of packets that are lost.</span></span> <span data-ttu-id="de2e2-206">数据包丢失率直接影响语音质量 — — 小，从单个丢失几乎没有影响到背对背突发包丢失的数据包导致音频来完全切除。</span><span class="sxs-lookup"><span data-stu-id="de2e2-206">Packet loss directly affects audio quality—from small, individual lost packets that have almost no impact to back-to-back burst losses that cause audio to cut out completely.</span></span>                                                                                                                               | <span data-ttu-id="de2e2-207">在其预定目标被丢弃，且未到达的数据包会导致视频和共享媒体，导致错过的音节和词汇，和时断时续中间隙。</span><span class="sxs-lookup"><span data-stu-id="de2e2-207">The packets being dropped and not arriving at their intended destination cause gaps in the media, resulting in missed syllables and words, and choppy video and sharing.</span></span> |
| <span data-ttu-id="de2e2-208">往返时间\>500 毫秒</span><span class="sxs-lookup"><span data-stu-id="de2e2-208">Round-trip time \>500 ms</span></span>                         | <span data-ttu-id="de2e2-209">在这种的情况所花费 IP 数据包从点 A 到点 B 和回点 a。此网络传播延迟绑定到两个点和光的速度之间的物理距离，包括采取的网络路径中的各种设备的额外系统开销。</span><span class="sxs-lookup"><span data-stu-id="de2e2-209">This is the time it takes to get an IP packet from point A to point B and back to point A. This network propagation delay is tied to the physical distance between the two points and the speed of light and includes additional overhead taken by the various devices in the network path.</span></span>                                                                                  | <span data-ttu-id="de2e2-210">时间太长，要到达目的地的数据包会导致 walkie-talkie 效果。</span><span class="sxs-lookup"><span data-stu-id="de2e2-210">The packets taking too long to arrive at their destination cause a walkie-talkie effect.</span></span>                                                                                 |
| <span data-ttu-id="de2e2-211">NMOS 下降平均\>1.0</span><span class="sxs-lookup"><span data-stu-id="de2e2-211">NMOS degradation average \> 1.0</span></span>                  | <span data-ttu-id="de2e2-212">一个或多个这些网络指标，虽然分别不是很差，网络[意味着意见分数](https://technet.microsoft.com/library/bb894481(v=office.12).aspx)(NMOS) 放置在一起由多个点。</span><span class="sxs-lookup"><span data-stu-id="de2e2-212">One or more of these network metrics, although individually weren’t poor, together caused the Network [Mean Opinion Score](https://technet.microsoft.com/library/bb894481(v=office.12).aspx) (NMOS) to drop by more than one point.</span></span> <span data-ttu-id="de2e2-213">这并不一定意味着网络连接较差，但质量降低呼叫过程中出现不足的问题。</span><span class="sxs-lookup"><span data-stu-id="de2e2-213">This doesn’t necessarily mean the network connection is poor, but enough issues occurred during the call that quality was reduced.</span></span> | <span data-ttu-id="de2e2-214">这是组合的抖动，数据包丢失和 — 程度要轻一些 — — 增加了往返的时间。</span><span class="sxs-lookup"><span data-stu-id="de2e2-214">This is a combination of jitter, packet loss, and—to a lesser degree—increased round-trip time.</span></span> <span data-ttu-id="de2e2-215">用户可能会遇到这些症状的组合。</span><span class="sxs-lookup"><span data-stu-id="de2e2-215">The user might be experiencing a combination of these symptoms.</span></span>          |
| <span data-ttu-id="de2e2-216">隐蔽的样本的平均比率\>7%或 0.07</span><span class="sxs-lookup"><span data-stu-id="de2e2-216">Average ratio of concealed samples \> 7% or 0.07</span></span> | <span data-ttu-id="de2e2-217">一个或多个这些网络指标，虽然分别不是很差，导致媒体的自我康复到客户端。</span><span class="sxs-lookup"><span data-stu-id="de2e2-217">One or more of these network metrics, although individually weren’t poor, caused the client to self-heal the media.</span></span> <span data-ttu-id="de2e2-218">隐蔽的音频采样是一种技术，平滑通常会由丢弃的网络数据包的突然转变。</span><span class="sxs-lookup"><span data-stu-id="de2e2-218">A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.</span></span>                                                                                                                | <span data-ttu-id="de2e2-219">高值指示重大损失隐蔽程度被应用，并导致扭曲或丢失的音频。</span><span class="sxs-lookup"><span data-stu-id="de2e2-219">High values indicate that significant levels of loss concealment were applied, and resulted in distorted or lost audio.</span></span>                                                  |

#### <a name="client-and-device-readiness"></a><span data-ttu-id="de2e2-220">客户端和设备的准备工作</span><span class="sxs-lookup"><span data-stu-id="de2e2-220">Client and device readiness</span></span>

<span data-ttu-id="de2e2-221">您需要一个稳定的客户端和设备战略，以确保您的用户具有一致和良好的用户体验。</span><span class="sxs-lookup"><span data-stu-id="de2e2-221">You need a solid client and device strategy to ensure that your users have a consistent and positive user experience.</span></span> <span data-ttu-id="de2e2-222">几个关键原则推动每个准备工作策略。</span><span class="sxs-lookup"><span data-stu-id="de2e2-222">A few key principles drive each readiness strategy.</span></span>

##### <a name="client-readiness"></a><span data-ttu-id="de2e2-223">客户端准备工作</span><span class="sxs-lookup"><span data-stu-id="de2e2-223">Client readiness</span></span>

<span data-ttu-id="de2e2-224">强大的客户端准备工作策略可确保您的用户正在享受最佳的体验同时运行最新版本的客户端。</span><span class="sxs-lookup"><span data-stu-id="de2e2-224">A strong client readiness strategy ensures that your users are running the most recent version of the client while enjoying the best experience possible.</span></span>
<span data-ttu-id="de2e2-225">Microsoft 的例行修补 Skype 业务客户端;确保将其最新的环境中对您整体的成功至关重要。</span><span class="sxs-lookup"><span data-stu-id="de2e2-225">Microsoft routinely patches the Skype for Business client; ensuring that you keep it up to date in your environment is vital to your overall success.</span></span>

<span data-ttu-id="de2e2-226">我们建议您不让落后超过六个月由您的客户端版本。</span><span class="sxs-lookup"><span data-stu-id="de2e2-226">We recommend that you not let your client versions fall behind by more than six months.</span></span> <span data-ttu-id="de2e2-227">如果您正在使用 Office 单击运行，您就已经正在保持最新服务。</span><span class="sxs-lookup"><span data-stu-id="de2e2-227">If you’re using Office Click-to-Run, you’re already being kept up to date by the service.</span></span> <span data-ttu-id="de2e2-228">使用包含的[客户机报告](#determine-client-versions)，在本指南的后面部分所述来帮助您完成此过程。</span><span class="sxs-lookup"><span data-stu-id="de2e2-228">Use the included [Client Report](#determine-client-versions), as described later in this guide, to assist you with this process.</span></span> <span data-ttu-id="de2e2-229">您还可以利用速率我调用示例报告，以进一步提高您的客户端准备工作战略。</span><span class="sxs-lookup"><span data-stu-id="de2e2-229">You can also leverage the Rate My Call sample reports to further enhance your client readiness strategy.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="de2e2-230">目前，分布式团队客户端和 Azure 内容传递网络通过自动更新并将保留最新的服务。</span><span class="sxs-lookup"><span data-stu-id="de2e2-230">Currently, Teams clients are distributed and updated automatically through the Azure Content Delivery Network and will be kept up to date by the service.</span></span> <span data-ttu-id="de2e2-231">客户端准备工作和调查活动并不适用于小组。</span><span class="sxs-lookup"><span data-stu-id="de2e2-231">Client readiness and investigative activities aren’t applicable to Teams.</span></span>


##### <a name="device-readiness"></a><span data-ttu-id="de2e2-232">设备就绪</span><span class="sxs-lookup"><span data-stu-id="de2e2-232">Device readiness</span></span>

<span data-ttu-id="de2e2-233">没有一种单一策略会影响用户体验比您设备的准备工作战略。</span><span class="sxs-lookup"><span data-stu-id="de2e2-233">No one single strategy can affect the user experience more than your device readiness strategy.</span></span> <span data-ttu-id="de2e2-234">大多数组织很高兴地从用户 （例如，桌面电话或其他专用音频设备） 中删除不必要的设备，这通常是用于切换到团队或 Skype 为业务核心业务合理性论证。</span><span class="sxs-lookup"><span data-stu-id="de2e2-234">Most organizations are happy to remove unnecessary devices from users (for example, desk phones or other dedicated audio devices), and this is often a core business justification for switching to Teams or Skype for Business.</span></span> <span data-ttu-id="de2e2-235">然而，这些相同的组织有时不愿意再提供替换的设备，即使这些设备成本较低。</span><span class="sxs-lookup"><span data-stu-id="de2e2-235">However, those same organizations sometimes hesitate to provide replacement devices, even if those devices are less expensive.</span></span> <span data-ttu-id="de2e2-236">现代笔记本电脑和 Pc，但配有内置的麦克风和扬声器，不适合企业级语音 ip (VoIP)。</span><span class="sxs-lookup"><span data-stu-id="de2e2-236">Modern-day laptops and PCs, though equipped with built-in microphone and speaker, aren’t optimized for business-class voice over IP (VoIP).</span></span> <span data-ttu-id="de2e2-237">通常如果这会产生不好的体验所有参与者，特别是演讲者是很嘈杂的环境中。</span><span class="sxs-lookup"><span data-stu-id="de2e2-237">This often creates a poor experience for all participants, especially if the speaker is in a noisy environment.</span></span> <span data-ttu-id="de2e2-238">Microsoft 的设备认证计划确保用户使用任何设备认证团队或 Skype 业务参与电话呼叫，它产生了优于未经认证的设备体验。</span><span class="sxs-lookup"><span data-stu-id="de2e2-238">Microsoft’s device certification program ensures that when a user participates in a phone call by using any device certified for Teams or Skype for Business, it produces an experience that’s superior to a non-certified device.</span></span>

<span data-ttu-id="de2e2-239">我们始终建议团队和业务用户的 Skype 使用认证的耳机或扬声器在参与语音呼叫使用桌面客户端。</span><span class="sxs-lookup"><span data-stu-id="de2e2-239">We always recommend that Teams and Skype for Business users use a certified headset or speaker when participating in a voice call by using a desktop client.</span></span>
<span data-ttu-id="de2e2-240">有关 Microsoft 认证的设备的详细信息，请查看此[文章有关电话和经鉴定的设备](https://technet.microsoft.com/office/dn788944.aspx)。</span><span class="sxs-lookup"><span data-stu-id="de2e2-240">For more information about Microsoft certified devices, review this [article about phones and qualified devices](https://technet.microsoft.com/office/dn788944.aspx).</span></span> <span data-ttu-id="de2e2-241">[设备报告](#devices-investigations)，以后在本指南中，用于管理您的设备的帮助。</span><span class="sxs-lookup"><span data-stu-id="de2e2-241">Use the [Device Report](#devices-investigations), later in this guide, for assistance with managing your devices.</span></span> <span data-ttu-id="de2e2-242">速度我调用示例报表也可用于进一步提高您的设备准备工作战略。</span><span class="sxs-lookup"><span data-stu-id="de2e2-242">You can also use the Rate My Call sample reports to further enhance your device readiness strategy.</span></span>

### <a name="user-experience"></a><span data-ttu-id="de2e2-243">用户体验</span><span class="sxs-lookup"><span data-stu-id="de2e2-243">User experience</span></span>

<span data-ttu-id="de2e2-244">分析了用户体验比科学更多艺术，因为这里收集的指标不总是意味着没有网络或服务问题，但相反，它们表明用户可以体验问题。</span><span class="sxs-lookup"><span data-stu-id="de2e2-244">Analyzing the user experience is more art than science, because the metrics gathered here don’t always mean that there’s a problem with the network or service but rather, they indicate that the user perceives a problem.</span></span> <span data-ttu-id="de2e2-245">Microsoft 提供了一种内置的调查机制--已知为率我调用 (RMC) — — 以帮助衡量整体用户体验。</span><span class="sxs-lookup"><span data-stu-id="de2e2-245">Microsoft offers a built-in survey mechanism—known as Rate My Call (RMC)—to help gauge overall user experience.</span></span> <span data-ttu-id="de2e2-246">RMC 将帮助您回答下面的问题，从用户的角度来看：</span><span class="sxs-lookup"><span data-stu-id="de2e2-246">RMC will help you answer the following questions from your users’ perspective:</span></span>

-   <span data-ttu-id="de2e2-247">我知道如何使用解决方案吗？</span><span class="sxs-lookup"><span data-stu-id="de2e2-247">Do I know how to use the solution?</span></span>

-   <span data-ttu-id="de2e2-248">易于使用且直观，是解决方案，它支持我日常通信的需要？</span><span class="sxs-lookup"><span data-stu-id="de2e2-248">Is the solution easy to use and intuitive, and does it support my day-to-day communication needs?</span></span>

-   <span data-ttu-id="de2e2-249">该解决方案帮助我完成工作了吗？</span><span class="sxs-lookup"><span data-stu-id="de2e2-249">Does the solution help me get my job done?</span></span>

-   <span data-ttu-id="de2e2-250">我总体感觉是解决方案的什么？</span><span class="sxs-lookup"><span data-stu-id="de2e2-250">What’s my overall perception of the solution?</span></span>

-   <span data-ttu-id="de2e2-251">可以使用解决方案在某一点的时间，而不考虑我的位置？</span><span class="sxs-lookup"><span data-stu-id="de2e2-251">Can I use the solution at any point in time, regardless of where I am?</span></span>

-   <span data-ttu-id="de2e2-252">可以设置并维护一个调用？</span><span class="sxs-lookup"><span data-stu-id="de2e2-252">Can I set up and maintain a call?</span></span>

#### <a name="rmc"></a><span data-ttu-id="de2e2-253">RMC</span><span class="sxs-lookup"><span data-stu-id="de2e2-253">RMC</span></span>

<span data-ttu-id="de2e2-254">RMC 建团队和业务的 Skype，并被自动配置为显示后每隔 10 个电话或 10%的所有调用中的一个。</span><span class="sxs-lookup"><span data-stu-id="de2e2-254">RMC is built into Teams and Skype for Business and is automatically configured to be displayed after one in every 10 calls, or 10 percent of all calls.</span></span> <span data-ttu-id="de2e2-255">这份简短的调查询问用户评价调用并提供很少的上下文为何呼叫质量可能做得很差。</span><span class="sxs-lookup"><span data-stu-id="de2e2-255">This brief survey asks the user to rate the call and provide a little context for why the call quality might have been poor.</span></span> <span data-ttu-id="de2e2-256">一个或两个评级被认为较差、 三到四属正常，而五个是优秀。</span><span class="sxs-lookup"><span data-stu-id="de2e2-256">A one or two rating is considered poor, three to four is good, and five is excellent.</span></span> <span data-ttu-id="de2e2-257">尽管有些绝热指示符，这是服务度量可以错过的发现问题的一个有用指标。</span><span class="sxs-lookup"><span data-stu-id="de2e2-257">Although it’s somewhat of a lagging indicator, this is a useful metric for uncovering issues that service metrics can miss.</span></span>

> [!NOTE]
> <span data-ttu-id="de2e2-258">直到用户将被要求通过通常授予除响应不正确，您的意见对 RMC 调查响应回来作为排山倒海般负面。</span><span class="sxs-lookup"><span data-stu-id="de2e2-258">Until users are instructed to respond to RMC surveys by giving good feedback in addition to bad, responses typically come back as overwhelmingly negative.</span></span> <span data-ttu-id="de2e2-259">大多数用户只响应时通话质量较差。</span><span class="sxs-lookup"><span data-stu-id="de2e2-259">Most users only respond when call quality is poor.</span></span> <span data-ttu-id="de2e2-260">因此，可能出现 RMC 报告偏态差侧服务指标都很好时，即使。</span><span class="sxs-lookup"><span data-stu-id="de2e2-260">Because of this, your RMC reports might be skewed to the poor side even while service metrics are good.</span></span> 


<span data-ttu-id="de2e2-261">您可以使用 CQD RMC 用户响应，报告和 CQD 模板中包括的示例报告。</span><span class="sxs-lookup"><span data-stu-id="de2e2-261">You can use CQD to report on RMC user responses, and sample reports are included in the CQD template.</span></span> <span data-ttu-id="de2e2-262">不过，它们不在本指南中详细讨论。</span><span class="sxs-lookup"><span data-stu-id="de2e2-262">However, they aren’t discussed in detail in this guide.</span></span> <span data-ttu-id="de2e2-263">教育用户提供有用的 RMC 响应的指南和关于 Skype 的在线业务中的 RMC 的详细信息，请参阅此[博客文章](https://blogs.technet.microsoft.com/jenstr/2015/05/05/rate-my-call-in-skype-for-business-2015/)。</span><span class="sxs-lookup"><span data-stu-id="de2e2-263">For more information about RMC in Skype for Business Online and guidance for educating users to give useful RMC responses, see this [blog post](https://blogs.technet.microsoft.com/jenstr/2015/05/05/rate-my-call-in-skype-for-business-2015/).</span></span>

### <a name="categories-of-quality"></a><span data-ttu-id="de2e2-264">类别的质量</span><span class="sxs-lookup"><span data-stu-id="de2e2-264">Categories of quality</span></span>

<span data-ttu-id="de2e2-265">留给高质量且可靠的部署成功与否取决于您正在生成操作的严格程度。</span><span class="sxs-lookup"><span data-stu-id="de2e2-265">The success of operationalizing a high-quality and reliable deployment depends on your building operational rigor.</span></span> <span data-ttu-id="de2e2-266">具体而言，应特别注意以下图; 所示的三个类别这些是本指南的重点：</span><span class="sxs-lookup"><span data-stu-id="de2e2-266">Specifically, pay special attention to the three categories illustrated in the following figure; these are the focus of this guide:</span></span>

-   <span data-ttu-id="de2e2-267">**网络：**侧重于 TCP 使用 PCR 指标、 有线和无线子网和标识使用的 HTTP 代理服务器和 VPN 的音频质量。</span><span class="sxs-lookup"><span data-stu-id="de2e2-267">**Network:** Audio quality focused on the PCR metric, TCP usage, wired and wireless subnets, and identifying the use of HTTP proxies and VPN.</span></span>

-   <span data-ttu-id="de2e2-268">**的终结点：**音频设备和客户端版本 (Skype 业务只)。</span><span class="sxs-lookup"><span data-stu-id="de2e2-268">**Endpoints:** Audio devices and client version (Skype for Business only).</span></span>

-   <span data-ttu-id="de2e2-269">**服务管理：**此类别包含两个部分：</span><span class="sxs-lookup"><span data-stu-id="de2e2-269">**Service Management:** This category comprises two sections:</span></span>

    -   <span data-ttu-id="de2e2-270">第一次由微软负责管理和维护的业务联机服务的团队和 Skype。</span><span class="sxs-lookup"><span data-stu-id="de2e2-270">First is Microsoft’s responsibility to manage and maintain the Teams and Skype for Business Online services.</span></span>

    -   <span data-ttu-id="de2e2-271">第二是您的组织必须设法确保可靠地访问该服务，如更新生成信息和基础结构添加到该服务维护防火墙的新 Office 365 IP 地址的任务。</span><span class="sxs-lookup"><span data-stu-id="de2e2-271">Second are tasks your organization must manage to ensure reliable access to the service, such as updating building information and maintaining firewalls for new Office 365 IP addresses as infrastructure is added to the service.</span></span>

![在组织中 qualilty 的类别： 管理、 端点和网络提供服务。](media/quality-of-experience-review-guide-image3.png)

<span data-ttu-id="de2e2-273">_图 3-团队和 Skype 的在线业务部署的关键类别_</span><span class="sxs-lookup"><span data-stu-id="de2e2-273">_Figure 3 - Critical categories for Teams and Skype for Business Online deployment_</span></span>

<span data-ttu-id="de2e2-274">下图概述了每个类别必须执行的任务。</span><span class="sxs-lookup"><span data-stu-id="de2e2-274">The graphic below outlines the tasks you must execute for each category.</span></span> <span data-ttu-id="de2e2-275">我们建议您运行这些任务每周一次，最少。</span><span class="sxs-lookup"><span data-stu-id="de2e2-275">We recommend that you run these tasks once a week, at a minimum.</span></span>

<span data-ttu-id="de2e2-276">第一次执行这些任务会比后续的迭代中，更多的工作，因为许多这些类别要求您验证您的部署配置。</span><span class="sxs-lookup"><span data-stu-id="de2e2-276">The first time you perform these tasks will take more effort than subsequent iterations, because many of these categories require that you validate your deployment configurations.</span></span> <span data-ttu-id="de2e2-277">获得了所需的会议的目标已定义的状态后，执行这些任务将帮助您保持该状态。</span><span class="sxs-lookup"><span data-stu-id="de2e2-277">After you’ve achieved the state you want by meeting the targets you’ve defined, performing these tasks will help you maintain that state.</span></span>

#### <a name="service-management-tasks"></a><span data-ttu-id="de2e2-278">服务管理任务</span><span class="sxs-lookup"><span data-stu-id="de2e2-278">Service management tasks</span></span>

<span data-ttu-id="de2e2-279">在云第一个世界中，必须执行某些服务管理任务，以维护高质量的用户体验。</span><span class="sxs-lookup"><span data-stu-id="de2e2-279">In a cloud-first world, you must perform certain service management tasks to maintain high-quality user experiences.</span></span> <span data-ttu-id="de2e2-280">这些任务范围从确保足够的带宽不饱和互联网链接，验证该服务质量 (QoS) 是在地方上所有受管理的网络区域，到达服务以及 — — 最后 — — 掌握[Office 365 IP 范围上防火墙](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)。</span><span class="sxs-lookup"><span data-stu-id="de2e2-280">These tasks range from ensuring there is sufficient bandwidth to reach the service without saturating internet links, validating that quality of service (QoS) is in place on all managed network areas, and—lastly—staying on top of [Office 365 IP ranges on firewalls](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2).</span></span>

#### <a name="network-tasks"></a><span data-ttu-id="de2e2-281">网络任务</span><span class="sxs-lookup"><span data-stu-id="de2e2-281">Network tasks</span></span>

<span data-ttu-id="de2e2-282">有两种类别的网络任务： 可靠性和质量。</span><span class="sxs-lookup"><span data-stu-id="de2e2-282">There are two categories of network tasks: reliability and quality.</span></span> <span data-ttu-id="de2e2-283">可靠性的重点测量用户的能力，成功地进行调用并保持联系。</span><span class="sxs-lookup"><span data-stu-id="de2e2-283">Reliability focuses on measuring the user’s ability to make calls successfully and stay connected.</span></span> <span data-ttu-id="de2e2-284">质量重点发给团队和 Skype 的在线业务过程的用户的客户端和调用结束后的聚合遥测数据。</span><span class="sxs-lookup"><span data-stu-id="de2e2-284">Quality focuses on the aggregated telemetry sent to Teams and Skype for Business Online by the user’s client during and after the call has ended.</span></span>

<span data-ttu-id="de2e2-285">给出可靠性具有对用户体验的关键影响，开始评估和深入质量之前研究这些指标。</span><span class="sxs-lookup"><span data-stu-id="de2e2-285">Given the critical impact that reliability has on the user experience, begin assessing and investigating those metrics before diving into quality.</span></span>

#### <a name="endpoints-tasks"></a><span data-ttu-id="de2e2-286">终结点任务</span><span class="sxs-lookup"><span data-stu-id="de2e2-286">Endpoints tasks</span></span>

<span data-ttu-id="de2e2-287">此类别中的主要任务验证哪些客户端版本上从过去的六个月，以确保用户得到的好处对 Skype 业务桌面客户端所做的持续优化桌面生成运行业务的 Skype。</span><span class="sxs-lookup"><span data-stu-id="de2e2-287">The main task in this category is validating which client versions are running Skype for Business on desktop builds from the last six months to ensure users are getting the benefit of the continual optimizations made to the Skype for Business desktop client.</span></span> <span data-ttu-id="de2e2-288">此外，这简化了整体的客户端管理任务，并提供一致的用户体验。</span><span class="sxs-lookup"><span data-stu-id="de2e2-288">Additionally, this simplifies overall client management tasks and provides a consistent user experience.</span></span>

<span data-ttu-id="de2e2-289">其他重要的领域是监视的设备在您的部署中普遍和推动经过认证的设备，以提供最佳用户体验。</span><span class="sxs-lookup"><span data-stu-id="de2e2-289">The other important area is monitoring which devices are prevalent in your deployment and driving the use of certified devices to provide the best user experience.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="de2e2-290">目前，分布式团队客户端和 Azure 内容传递网络通过自动更新并将保留最新的服务。</span><span class="sxs-lookup"><span data-stu-id="de2e2-290">Currently, Teams clients are distributed and updated automatically through the Azure Content Delivery Network and will be kept up to date by the service.</span></span> <span data-ttu-id="de2e2-291">客户端准备工作和调查活动并不适用于小组。</span><span class="sxs-lookup"><span data-stu-id="de2e2-291">Client readiness and investigative activities aren’t applicable to Teams.</span></span>


## <a name="using-the-reports"></a><span data-ttu-id="de2e2-292">使用报表</span><span class="sxs-lookup"><span data-stu-id="de2e2-292">Using the reports</span></span>

<span data-ttu-id="de2e2-293">本部分介绍使用 CQD 的基础知识。</span><span class="sxs-lookup"><span data-stu-id="de2e2-293">This section describes the fundamentals of working with CQD.</span></span> <span data-ttu-id="de2e2-294">指南给出了有关的以下主题：</span><span class="sxs-lookup"><span data-stu-id="de2e2-294">Guidance is given for the following topics:</span></span>

-   <span data-ttu-id="de2e2-295">查找客户端 ID</span><span class="sxs-lookup"><span data-stu-id="de2e2-295">Finding your tenant ID</span></span>

-   <span data-ttu-id="de2e2-296">团队与 Skype 业务报告</span><span class="sxs-lookup"><span data-stu-id="de2e2-296">Reporting on Teams versus Skype for Business</span></span>

-   <span data-ttu-id="de2e2-297">第一次与第二个分类</span><span class="sxs-lookup"><span data-stu-id="de2e2-297">First versus second classifications</span></span>

-   <span data-ttu-id="de2e2-298">维度、 度量值和筛选器</span><span class="sxs-lookup"><span data-stu-id="de2e2-298">Dimensions, measures, and filters</span></span>

-   <span data-ttu-id="de2e2-299">而不是调用流</span><span class="sxs-lookup"><span data-stu-id="de2e2-299">Streams versus calls</span></span>

-   <span data-ttu-id="de2e2-300">良好、 较差，以及未分类电话</span><span class="sxs-lookup"><span data-stu-id="de2e2-300">Good, poor, and unclassified calls</span></span>

-   <span data-ttu-id="de2e2-301">CQD 入门</span><span class="sxs-lookup"><span data-stu-id="de2e2-301">Getting started with CQD</span></span>

-   <span data-ttu-id="de2e2-302">编辑在 CQD 的报告</span><span class="sxs-lookup"><span data-stu-id="de2e2-302">Editing reports in CQD</span></span>

-   <span data-ttu-id="de2e2-303">筛选报表中 CQD</span><span class="sxs-lookup"><span data-stu-id="de2e2-303">Filtering reports in CQD</span></span>

<span data-ttu-id="de2e2-304">更深入的培训和资源，请参阅[附录](#other-resources)。</span><span class="sxs-lookup"><span data-stu-id="de2e2-304">For more in-depth training and resources, see the [Appendix](#other-resources).</span></span>

### <a name="tenant-id"></a><span data-ttu-id="de2e2-305">租户 ID</span><span class="sxs-lookup"><span data-stu-id="de2e2-305">Tenant ID</span></span>

<span data-ttu-id="de2e2-306">一些 CQD 报告要求租户 id，包含筛选器</span><span class="sxs-lookup"><span data-stu-id="de2e2-306">Some CQD reports require that you include a filter for your tenant ID.</span></span> <span data-ttu-id="de2e2-307">由于 CQD 聚合数据的方式，将包括联盟参与者遥测。</span><span class="sxs-lookup"><span data-stu-id="de2e2-307">Due to the way CQD aggregates data, federated participant telemetry is included.</span></span>
<span data-ttu-id="de2e2-308">尽管分析指标较差的调用时，这可以证明有价值，客户端和设备报告要求特定租户要排除联盟参与者遥测到的数据的筛选。</span><span class="sxs-lookup"><span data-stu-id="de2e2-308">Although this can prove valuable when analyzing poor call metrics, client and device reports require the filtering of data to a specific tenant to exclude federated participant telemetry.</span></span> <span data-ttu-id="de2e2-309">如果您不知道您的租户 ID，可以使用以下方法之一来查找它。</span><span class="sxs-lookup"><span data-stu-id="de2e2-309">If you don’t know your tenant ID, you can use one of the following methods to find it.</span></span>

<span data-ttu-id="de2e2-310">权限要求</span><span class="sxs-lookup"><span data-stu-id="de2e2-310">Permission requirements</span></span>

-   <span data-ttu-id="de2e2-311">全局管理员角色</span><span class="sxs-lookup"><span data-stu-id="de2e2-311">Global Administrator Role</span></span>

-   <span data-ttu-id="de2e2-312">Skype 业务管理员角色</span><span class="sxs-lookup"><span data-stu-id="de2e2-312">Skype for Business Administrator Role</span></span>

#### <a name="azure-ad-portal"></a><span data-ttu-id="de2e2-313">Azure 广告门户</span><span class="sxs-lookup"><span data-stu-id="de2e2-313">Azure AD Portal</span></span>

1.  <span data-ttu-id="de2e2-314">登录到 Microsoft Azure 门户：<https://portal.azure.com></span><span class="sxs-lookup"><span data-stu-id="de2e2-314">Sign in to the Microsoft Azure portal: <https://portal.azure.com></span></span>

2.  <span data-ttu-id="de2e2-315">选择**Azure 的活动目录**。</span><span class="sxs-lookup"><span data-stu-id="de2e2-315">Select **Azure Active Directory**.</span></span>

3.  <span data-ttu-id="de2e2-316">在**管理**下选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="de2e2-316">Under **Manage**, select **Properties**.</span></span> <span data-ttu-id="de2e2-317">租户 ID 将显示在**目录 ID**框中。</span><span class="sxs-lookup"><span data-stu-id="de2e2-317">The tenant ID is shown in the **Directory ID** box.</span></span>

#### <a name="azure-powershell"></a><span data-ttu-id="de2e2-318">Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="de2e2-318">Azure PowerShell</span></span>

1.  <span data-ttu-id="de2e2-319">[安装 Microsoft Azure PowerShell 服务管理模块](https://docs.microsoft.com/powershell/azure/servicemanagement/install-azure-ps?view=azuresmps-4.0.0)。</span><span class="sxs-lookup"><span data-stu-id="de2e2-319">[Install the Microsoft Azure PowerShell Service Management module](https://docs.microsoft.com/powershell/azure/servicemanagement/install-azure-ps?view=azuresmps-4.0.0).</span></span>

2.  <span data-ttu-id="de2e2-320">打开 Azure PowerShell 命令窗口并运行以下脚本中，输入您的 Office 365 提供凭据时提示您：</span><span class="sxs-lookup"><span data-stu-id="de2e2-320">Open an Azure PowerShell command window and run the following script, entering your Office 365 credentials when prompted:</span></span>  
    <span data-ttu-id="de2e2-321">**登录 AzureRmAccount**</span><span class="sxs-lookup"><span data-stu-id="de2e2-321">**Login-AzureRmAccount**</span></span>

3.  <span data-ttu-id="de2e2-322">在输出中列出的租户 ID。</span><span class="sxs-lookup"><span data-stu-id="de2e2-322">The tenant ID is listed in the output.</span></span>

#### <a name="skype-for-business-online-admin-center"></a><span data-ttu-id="de2e2-323">Skype 的业务联机管理中心</span><span class="sxs-lookup"><span data-stu-id="de2e2-323">Skype for Business Online Admin Center</span></span>

1.  <span data-ttu-id="de2e2-324">转到(G)<https://portal.office.com></span><span class="sxs-lookup"><span data-stu-id="de2e2-324">Go to <https://portal.office.com></span></span>

2.  <span data-ttu-id="de2e2-325">使用您组织的管理员组织帐户登录。</span><span class="sxs-lookup"><span data-stu-id="de2e2-325">Sign in with your tenant administrator organizational account.</span></span>

3.  <span data-ttu-id="de2e2-326">选择**管理员中心**下**Skype 业务**。</span><span class="sxs-lookup"><span data-stu-id="de2e2-326">Select **Skype for Business** under **Admin Centers**.</span></span>

4.  <span data-ttu-id="de2e2-327">租户 ID 中，被列为欢迎页上的**组织 ID** 。</span><span class="sxs-lookup"><span data-stu-id="de2e2-327">The tenant ID is listed as **Organization ID** on the Welcome page.</span></span>

#### <a name="skype-for-business-online-using-powershell"></a><span data-ttu-id="de2e2-328">Skype 业务在线使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="de2e2-328">Skype for Business Online using PowerShell</span></span>

1.  <span data-ttu-id="de2e2-329">[连接到 Skype 的在线业务通过 PowerShell](https://technet.microsoft.com/library/dn362839(v=ocs.15).aspx)。</span><span class="sxs-lookup"><span data-stu-id="de2e2-329">[Connect to Skype for Business Online via PowerShell](https://technet.microsoft.com/library/dn362839(v=ocs.15).aspx).</span></span>

2.  <span data-ttu-id="de2e2-330">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="de2e2-330">Run the following command:</span></span>  
    <span data-ttu-id="de2e2-331">**(Get cstenant).tenantid**</span><span class="sxs-lookup"><span data-stu-id="de2e2-331">**(Get-cstenant).tenantid**</span></span>

3.  <span data-ttu-id="de2e2-332">租户 ID 显示为 GUID。</span><span class="sxs-lookup"><span data-stu-id="de2e2-332">The tenant ID is displayed as a GUID.</span></span>

### <a name="teams-vs-skype-for-business"></a><span data-ttu-id="de2e2-333">团队与 Skype 业务</span><span class="sxs-lookup"><span data-stu-id="de2e2-333">Teams vs. Skype for Business</span></span>

<span data-ttu-id="de2e2-334">CQD 可以报告团队和 Skype 的业务遥测。</span><span class="sxs-lookup"><span data-stu-id="de2e2-334">CQD can report on both Teams and Skype for Business telemetry.</span></span> <span data-ttu-id="de2e2-335">但是，有时可能想要制定报表来查看团队遥测与 Skype 业务分开。</span><span class="sxs-lookup"><span data-stu-id="de2e2-335">However, there might be times when you want to develop a report to look at Teams telemetry separate from Skype for Business.</span></span>

#### <a name="summary-reports"></a><span data-ttu-id="de2e2-336">摘要报告</span><span class="sxs-lookup"><span data-stu-id="de2e2-336">Summary reports</span></span>

<span data-ttu-id="de2e2-337">若要修改摘要报告页后，可以看一只团队或 Skype 业务，从顶部的屏幕上，选择**产品筛选器**下拉列表菜单，然后选择所需的产品。</span><span class="sxs-lookup"><span data-stu-id="de2e2-337">To modify the summary reports page to look at only Teams or Skype for Business, select the **Product Filter** drop-down menu from the top of the screen, and then select the product you want.</span></span>

![呼叫质量面板以反映一个下拉列表菜单中显示的选项要作为筛选依据的工作负荷的屏幕快照。](media/quality-of-experience-review-guide-image4.png)

<span data-ttu-id="de2e2-339">_图 4-选择产品筛选器_</span><span class="sxs-lookup"><span data-stu-id="de2e2-339">_Figure 4 - Select a Product Filter_</span></span>

#### <a name="detailed-reports"></a><span data-ttu-id="de2e2-340">详细的报告</span><span class="sxs-lookup"><span data-stu-id="de2e2-340">Detailed reports</span></span>

<span data-ttu-id="de2e2-341">若要进行筛选的详细的报告，向报表中添加筛选器**是团队**，并将其设置为 True 或 False。</span><span class="sxs-lookup"><span data-stu-id="de2e2-341">To filter a detailed report, add the filter **Is Teams** to the report and set it to True or False.</span></span> <span data-ttu-id="de2e2-342">有关详细信息，请参阅本部分中稍后介绍的[编辑报告](#editing-reports)。</span><span class="sxs-lookup"><span data-stu-id="de2e2-342">For more information, see [Editing reports](#editing-reports) later in this section.</span></span>

![呼叫质量面板来描述文件管理器，可以将添加到详细报告的屏幕快照。](media/quality-of-experience-review-guide-image5.png)

<span data-ttu-id="de2e2-344">_图 5-向报表中添加 Microsoft 小组筛选器_</span><span class="sxs-lookup"><span data-stu-id="de2e2-344">_Figure 5 - Adding a Microsoft Teams filter to a report_</span></span>

### <a name="dimensions-measures-and-filters"></a><span data-ttu-id="de2e2-345">维度、 度量值和筛选器</span><span class="sxs-lookup"><span data-stu-id="de2e2-345">Dimensions, measures, and filters</span></span>

<span data-ttu-id="de2e2-346">一个格式良好的 CQD 查询包含所有三个以下参数：</span><span class="sxs-lookup"><span data-stu-id="de2e2-346">A well-formed CQD query contains all three of the following parameters:</span></span>

-   <span data-ttu-id="de2e2-347">**尺寸：**我如何想要的数据的数据透视表。</span><span class="sxs-lookup"><span data-stu-id="de2e2-347">**Dimension:** How I want to pivot on the data.</span></span>

-   <span data-ttu-id="de2e2-348">**度量：**我要报告。</span><span class="sxs-lookup"><span data-stu-id="de2e2-348">**Measure:** What I want to report on.</span></span>

-   <span data-ttu-id="de2e2-349">**筛选器：**如何想要减小查询返回的数据集。</span><span class="sxs-lookup"><span data-stu-id="de2e2-349">**Filter:** How do I want to reduce the data set the query returns.</span></span>

<span data-ttu-id="de2e2-350">另一种方式来看这是维度是分组函数、 一项措施就是我很感兴趣，数据和筛选器是如何想要缩小与查询相关的结果。</span><span class="sxs-lookup"><span data-stu-id="de2e2-350">Another way to look at this is a dimension is the grouping function, a measure is the data I’m interested in, and a filter is how I want to narrow down the results to those that are relevant to my query.</span></span>

<span data-ttu-id="de2e2-351">一个格式良好的查询的一个示例是"向我显示差流 [措施] [维度] 的子网由建筑物 6 [过滤器]。"</span><span class="sxs-lookup"><span data-stu-id="de2e2-351">An example of a well-formed query is "Show me Poor Streams [Measure] by Subnet [Dimension] for Building 6 [Filter]."</span></span>

<span data-ttu-id="de2e2-352">有关详细信息，请参阅[维度和度量值中 CQD 可用](https://aka.ms/cqd-dm)。</span><span class="sxs-lookup"><span data-stu-id="de2e2-352">For more information, see [Dimensions and measures available in CQD](https://aka.ms/cqd-dm).</span></span>

<span data-ttu-id="de2e2-353">维度、 度量值和 CQD 模板中使用的报表筛选器，请参阅[附录](#CQD-training)。</span><span class="sxs-lookup"><span data-stu-id="de2e2-353">For dimensions, measures, and filters for the reports used in the CQD templates, see the [Appendix](#CQD-training).</span></span>

### <a name="first-vs-second"></a><span data-ttu-id="de2e2-354">第一次与第二个</span><span class="sxs-lookup"><span data-stu-id="de2e2-354">First vs. second</span></span> 

<span data-ttu-id="de2e2-355">许多维度和度量值中 CQD 被划分为第一或第二。</span><span class="sxs-lookup"><span data-stu-id="de2e2-355">Many of the dimensions and measures in CQD are classified as first or second.</span></span>
<span data-ttu-id="de2e2-356">CQD 不使用调用方/被调用方字段 — — 因为有调用方和被调用方之间的中间步骤，这些已被重命名为_第一次_和_第二_。</span><span class="sxs-lookup"><span data-stu-id="de2e2-356">CQD doesn’t use caller/callee fields—these have been renamed _first_ and _second_ because there are intervening steps between the caller and callee.</span></span> <span data-ttu-id="de2e2-357">以下逻辑用于确定将流或通话中涉及的哪些终结点标为第一。</span><span class="sxs-lookup"><span data-stu-id="de2e2-357">The following logic determines which endpoint involved in the stream or call is labeled as first:</span></span>

-   <span data-ttu-id="de2e2-358">第一次将始终 （会议服务器、 中介服务器等） 的服务器终结点服务器涉及到流或调用。</span><span class="sxs-lookup"><span data-stu-id="de2e2-358">First will always be a server endpoint (Conference Server, Mediation Server, and so on) if a server is involved in the stream or call.</span></span>

-   <span data-ttu-id="de2e2-359">其次将始终为客户端终结点除非流在两个服务器终结点之间。</span><span class="sxs-lookup"><span data-stu-id="de2e2-359">Second will always be a client endpoint unless the stream is between two server endpoints.</span></span>

-   <span data-ttu-id="de2e2-360">如果两个终结点具有相同的类型，这些选择是第一个基于内部订购的用户代理类别。</span><span class="sxs-lookup"><span data-stu-id="de2e2-360">If both endpoints are the same type, the choice of which is first is based on internal ordering of the user agent category.</span></span> <span data-ttu-id="de2e2-361">这样可以确保排序的一致性。</span><span class="sxs-lookup"><span data-stu-id="de2e2-361">This ensures the ordering is consistent.</span></span>

<span data-ttu-id="de2e2-362">在这两个相同时确定的第一个或第二个终结点的详细信息，请参阅[维度和度量值中 CQD 可用](https://aka.ms/cqd-dm)。</span><span class="sxs-lookup"><span data-stu-id="de2e2-362">For more information about determining the first or second endpoint when they’re both the same, see [Dimensions and measures available in CQD](https://aka.ms/cqd-dm).</span></span>

### <a name="stream-vs-call"></a><span data-ttu-id="de2e2-363">与呼叫流</span><span class="sxs-lookup"><span data-stu-id="de2e2-363">Stream vs. call</span></span>

<span data-ttu-id="de2e2-364">您需要了解正确选择的维度或度量值，您将会看到中的 CQD 的调用和流之间的区别。</span><span class="sxs-lookup"><span data-stu-id="de2e2-364">You need to understand the difference between a call and a stream to properly choose which dimensions or measures you’ll be looking at in CQD.</span></span>

<span data-ttu-id="de2e2-365">**流：**只有两个终结点之间存在一个流。</span><span class="sxs-lookup"><span data-stu-id="de2e2-365">**Stream:** A stream exists between only two endpoints.</span></span> <span data-ttu-id="de2e2-366">没有为每个方向，只有一个流和两个流所需的通信。</span><span class="sxs-lookup"><span data-stu-id="de2e2-366">There is only one stream for each direction, and two streams are required for communication.</span></span> <span data-ttu-id="de2e2-367">流可以用于分析建筑物或网络。</span><span class="sxs-lookup"><span data-stu-id="de2e2-367">Streams are useful for analyzing buildings or networks.</span></span> <span data-ttu-id="de2e2-368">在某些情况下，调用和流的名称 （例如，调用安装程序流或调用下沉流） 中使用。</span><span class="sxs-lookup"><span data-stu-id="de2e2-368">In some cases, both call and stream are used in the name (for example, Call Setup Stream or Call Dropped Stream).</span></span>
<span data-ttu-id="de2e2-369">这些还都属于单个流。</span><span class="sxs-lookup"><span data-stu-id="de2e2-369">These are still classified as single streams.</span></span>

<span data-ttu-id="de2e2-370">**调用：**调用是从所有参与者的所有流的分组。</span><span class="sxs-lookup"><span data-stu-id="de2e2-370">**Call:** A call is a grouping of all streams from all participants.</span></span> <span data-ttu-id="de2e2-371">调用组成 — — 至少 — — 两个流。</span><span class="sxs-lookup"><span data-stu-id="de2e2-371">A call consists of—at minimum—two streams.</span></span> <span data-ttu-id="de2e2-372">一次调用中将有两个参与者每个最小的一个流。</span><span class="sxs-lookup"><span data-stu-id="de2e2-372">A single call will have two participants each with a minimum of one stream.</span></span> <span data-ttu-id="de2e2-373">调用可以用于分析趋势，随着时间的推移。</span><span class="sxs-lookup"><span data-stu-id="de2e2-373">Calls are useful for analyzing trends over time.</span></span>

<span data-ttu-id="de2e2-374">到调用或流引用维度或度量值的其他指南，请参阅[维度和度量值中 CQD 可用](https://aka.ms/cqd-dm)</span><span class="sxs-lookup"><span data-stu-id="de2e2-374">For additional guidance on whether the dimension or measure is referring to a call or a stream, see [Dimensions and measures available in CQD](https://aka.ms/cqd-dm)</span></span>

### <a name="good-poor-and-unclassified-calls"></a><span data-ttu-id="de2e2-375">良好、 较差，以及未分类电话</span><span class="sxs-lookup"><span data-stu-id="de2e2-375">Good, poor, and unclassified calls</span></span>

<span data-ttu-id="de2e2-376">调用被归类为良好、 较差，或者未分类。</span><span class="sxs-lookup"><span data-stu-id="de2e2-376">A call is categorized either as good, poor, or unclassified.</span></span> <span data-ttu-id="de2e2-377">让我们花点时间来谈谈更多详细信息中的每个。</span><span class="sxs-lookup"><span data-stu-id="de2e2-377">Let’s take a moment to talk about each one in more detail.</span></span>

<span data-ttu-id="de2e2-378">**很好或很差：**好或差的调用包含，包含一套完整的服务标准，为生成完整的 QoE 报告了一个调用。</span><span class="sxs-lookup"><span data-stu-id="de2e2-378">**Good or poor:** A good or poor call consists of a call that contains a complete set of service metrics, for which a full QoE report was generated.</span></span>
<span data-ttu-id="de2e2-379">确定调用是否好或差是介绍[本指南中前面](#pcr)。</span><span class="sxs-lookup"><span data-stu-id="de2e2-379">Determining whether a call is good or poor is described [earlier in this guide](#pcr).</span></span>

<span data-ttu-id="de2e2-380">**未分类：**未分类的电话中没有一套完整的服务标准。</span><span class="sxs-lookup"><span data-stu-id="de2e2-380">**Unclassified:** An unclassified call doesn’t contain a full set of service metrics.</span></span> <span data-ttu-id="de2e2-381">这些通常是简短的电话 — — 通常小于 60 秒 — — 其中无法计算平均值，QoE 报告没有生成。</span><span class="sxs-lookup"><span data-stu-id="de2e2-381">These are often short calls—usually less than 60 seconds—where averages couldn’t be computed and a QoE report wasn’t generated.</span></span>

### <a name="access-cqd-online"></a><span data-ttu-id="de2e2-382">在线访问 CQD</span><span class="sxs-lookup"><span data-stu-id="de2e2-382">Access CQD Online</span></span>

<span data-ttu-id="de2e2-383">您可以访问 CQD 两种方式之一。</span><span class="sxs-lookup"><span data-stu-id="de2e2-383">You can access CQD one of two ways.</span></span>

-   <span data-ttu-id="de2e2-384">转到<https://cqd.lync.com>。</span><span class="sxs-lookup"><span data-stu-id="de2e2-384">Go to <https://cqd.lync.com>.</span></span>

-   <span data-ttu-id="de2e2-385">转到**业务管理中心的 Skype** \> **工具**，然后选择 CQD，如下所示的链接。</span><span class="sxs-lookup"><span data-stu-id="de2e2-385">Go to **Skype for Business admin center** \> **tools**, and select the link to CQD, as shown below.</span></span>

![显示"工具"，然后在左侧的导航窗格中，并链接到 Skype 的业务在线呼叫质量仪表板选择中选定的屏幕截图。](media/quality-of-experience-review-guide-image6.png)

<span data-ttu-id="de2e2-387">_图 6 – 访问通过 Skype 业务管理中心的 CQD_</span><span class="sxs-lookup"><span data-stu-id="de2e2-387">_Figure 6 – Accessing CQD through the Skype for Business admin center_</span></span>

### <a name="getting-started"></a><span data-ttu-id="de2e2-388">入门</span><span class="sxs-lookup"><span data-stu-id="de2e2-388">Getting started</span></span>

<span data-ttu-id="de2e2-389">当您第一次浏览到 CQD 时，您将看到摘要报告页。</span><span class="sxs-lookup"><span data-stu-id="de2e2-389">When you first browse to CQD, you’ll see the Summary Reports page.</span></span> <span data-ttu-id="de2e2-390">本指南中所述的报告大多数是自定义的详细的报告。</span><span class="sxs-lookup"><span data-stu-id="de2e2-390">Most of the reports described in this guide are custom detailed reports.</span></span> <span data-ttu-id="de2e2-391">若要开始使用详细的报告，选择顶部的页的**摘要报告**，然后选择**详细报告**。</span><span class="sxs-lookup"><span data-stu-id="de2e2-391">To get started using the detailed reports, select **Summary Reports** at the top of the page, and then choose **Detailed Reports**.</span></span>

![呼叫质量面板 depcting 屏幕抓图的不同类型的可用报告。](media/quality-of-experience-review-guide-image7.png)

<span data-ttu-id="de2e2-393">_图 7-导航到详细报表_</span><span class="sxs-lookup"><span data-stu-id="de2e2-393">_Figure 7 - Navigating to Detailed Reports_</span></span>

<span data-ttu-id="de2e2-394">在 CQD 的详细报告页看起来像图如下所示。</span><span class="sxs-lookup"><span data-stu-id="de2e2-394">The Detailed Reports page in CQD looks like the figure shown below.</span></span>

![CQD 和不同的元素组成一个报告中的详细的报告页面的屏幕快照。](media/quality-of-experience-review-guide-image8.png)

<span data-ttu-id="de2e2-396">_图 8-详细的报告页_</span><span class="sxs-lookup"><span data-stu-id="de2e2-396">_Figure 8 - Detailed Reports page_</span></span>

1.  <span data-ttu-id="de2e2-397">摘要窗格中显示为报告集，将出现在右侧的上下文。</span><span class="sxs-lookup"><span data-stu-id="de2e2-397">The summary pane shows context for the report set that appears to the right.</span></span>

2.  <span data-ttu-id="de2e2-398">您可以选择**编辑**设置报表 – 级别的属性 （包括 y 轴高度） 的摘要窗格中。</span><span class="sxs-lookup"><span data-stu-id="de2e2-398">You can select **Edit** in the summary pane to set report–level properties (including y-axis height).</span></span>

3.  <span data-ttu-id="de2e2-399">痕迹导航可帮助用户识别报告集层次结构中的当前位置。</span><span class="sxs-lookup"><span data-stu-id="de2e2-399">The breadcrumb helps users identify their current location in the report set hierarchy.</span></span>

4.  <span data-ttu-id="de2e2-400">蓝色链接显示了包含子报表的报表。</span><span class="sxs-lookup"><span data-stu-id="de2e2-400">Reports that have child reports are shown with a blue link.</span></span> <span data-ttu-id="de2e2-401">通过选择该链接，您可以深化到子报表。</span><span class="sxs-lookup"><span data-stu-id="de2e2-401">By selecting the link, you can drill down to the child reports.</span></span>

<span data-ttu-id="de2e2-402">指向的条形图和显示详细的值的趋势线。</span><span class="sxs-lookup"><span data-stu-id="de2e2-402">Point to the bar charts and trend lines to display detailed values.</span></span> <span data-ttu-id="de2e2-403">具有焦点的报表将显示操作菜单：**编辑**、**克隆**、**删除**、**下载**并**导出报表树**。</span><span class="sxs-lookup"><span data-stu-id="de2e2-403">The report that has focus will show the action menu: **Edit**, **Clone**, **Delete**, **Download**, and **Export Report Tree**.</span></span>

### <a name="editing-reports"></a><span data-ttu-id="de2e2-404">编辑报告</span><span class="sxs-lookup"><span data-stu-id="de2e2-404">Editing reports</span></span>

<span data-ttu-id="de2e2-405">如果在报表的操作菜单中选择**编辑**，您将打开查询编辑器。</span><span class="sxs-lookup"><span data-stu-id="de2e2-405">When you select **Edit** on the action menu of a report, you’ll open Query Editor.</span></span> <span data-ttu-id="de2e2-406">每个报表的查询被后盾。</span><span class="sxs-lookup"><span data-stu-id="de2e2-406">Each report is backed by a query.</span></span> <span data-ttu-id="de2e2-407">报告是其查询返回的数据的可视化形式。</span><span class="sxs-lookup"><span data-stu-id="de2e2-407">A report is a visualization of the data returned by its query.</span></span> <span data-ttu-id="de2e2-408">查询编辑器中编辑这些查询，除了报告中，显示的选项为用户界面，如下图中所示。</span><span class="sxs-lookup"><span data-stu-id="de2e2-408">The Query Editor is a UI for editing these queries in addition to the display options for the report, as illustrated in the following figure.</span></span>

![CQD 和构成报告在编辑报表时的不同元素中的详细的报表页面的屏幕快照。](media/quality-of-experience-review-guide-image9.png)

<span data-ttu-id="de2e2-410">_图 9-报告编辑器_</span><span class="sxs-lookup"><span data-stu-id="de2e2-410">_Figure 9 - Report Editor_</span></span>

1.  <span data-ttu-id="de2e2-411">从左窗格中选择的维度、 度量值和筛选器。</span><span class="sxs-lookup"><span data-stu-id="de2e2-411">You choose dimensions, measures, and filters from the left pane.</span></span> <span data-ttu-id="de2e2-412">指向某个现有值显示关闭按钮 (**X**)，您可以选择要删除的值。</span><span class="sxs-lookup"><span data-stu-id="de2e2-412">Pointing to an existing value displays a close button (**X**) you can select to remove the value.</span></span>

    1.  <span data-ttu-id="de2e2-413">通过选择维度或度量值，可以通过编辑**标题**字段中更改标题。</span><span class="sxs-lookup"><span data-stu-id="de2e2-413">By selecting the dimension or measure, you can change the title by editing the **Title** field.</span></span> <span data-ttu-id="de2e2-414">您可以通过在顶部窗格中选择蓝色的向上或向下箭头来更改顺序。</span><span class="sxs-lookup"><span data-stu-id="de2e2-414">You can also change the order by selecting the blue Up or Down arrows in the top pane.</span></span>

    2.  <span data-ttu-id="de2e2-415">选择 (**+**) 标题旁边打开的对话框中添加新的维度、 度量值或筛选器。</span><span class="sxs-lookup"><span data-stu-id="de2e2-415">Selecting (**+**) next to a heading opens the dialog box for adding a new dimension, measure, or filter.</span></span>

    3.  <span data-ttu-id="de2e2-416">输入的维度、 度量值或筛选器中的前几个字母**查找**字段来筛选列表更易于搜索。</span><span class="sxs-lookup"><span data-stu-id="de2e2-416">Enter the first few letters of the dimension, measure, or filter in the **Find a** field to filter the list for easier searching.</span></span>

2.  <span data-ttu-id="de2e2-417">顶部窗格中显示为图表自定义的选项。</span><span class="sxs-lookup"><span data-stu-id="de2e2-417">The top pane shows options for chart customization.</span></span>

3.  <span data-ttu-id="de2e2-418">查询编辑器显示报表的预览。</span><span class="sxs-lookup"><span data-stu-id="de2e2-418">The Query Editor shows a preview of the report.</span></span>

4.  <span data-ttu-id="de2e2-419">使用屏幕底部的**编辑**框中创建或编辑报表的详细的说明。</span><span class="sxs-lookup"><span data-stu-id="de2e2-419">Use the **Edit** box at the bottom of the screen to create or edit a detailed description of the report.</span></span>

### <a name="filtering-reports"></a><span data-ttu-id="de2e2-420">筛选报告</span><span class="sxs-lookup"><span data-stu-id="de2e2-420">Filtering reports</span></span>

<span data-ttu-id="de2e2-421">提供的模板包括多个内置查询和报表筛选器。</span><span class="sxs-lookup"><span data-stu-id="de2e2-421">The templates provided includes several built-in queries and report filters.</span></span> <span data-ttu-id="de2e2-422">以下各节描述了在整个模板最常用的筛选器。</span><span class="sxs-lookup"><span data-stu-id="de2e2-422">The following sections describe the most common filters used throughout the templates.</span></span>

#### <a name="cqd-filter"></a><span data-ttu-id="de2e2-423">CQD 筛选器</span><span class="sxs-lookup"><span data-stu-id="de2e2-423">CQD filter</span></span>

<span data-ttu-id="de2e2-424">可以使用 CQD 筛选器或 URL 筛选器来临时筛选每个报表查询。</span><span class="sxs-lookup"><span data-stu-id="de2e2-424">You can use the CQD filter, or URL filter, to temporarily filter every report query.</span></span> <span data-ttu-id="de2e2-425">您将使用最常见 CQD 筛选器来筛选报告以排除联盟参与者遥测。</span><span class="sxs-lookup"><span data-stu-id="de2e2-425">The most common CQD filter you’ll use is to filter reports to exclude federated participant telemetry.</span></span> <span data-ttu-id="de2e2-426">我们建议您书签此筛选器，使其成为默认视图。</span><span class="sxs-lookup"><span data-stu-id="de2e2-426">We recommend that you bookmark this filter so it becomes the default view.</span></span> <span data-ttu-id="de2e2-427">当托管的建筑物或网络联合的数据可能会影响您的报表要补救，从 CQD 报告排除联合的数据非常有用。</span><span class="sxs-lookup"><span data-stu-id="de2e2-427">Excluding federated data from CQD reports is useful when you’re remediating managed buildings or networks where federated data might influence your report.</span></span>

<span data-ttu-id="de2e2-428">若要实现 CQD 筛选器，在浏览器地址栏中，URL 的末尾追加以下：</span><span class="sxs-lookup"><span data-stu-id="de2e2-428">To implement a CQD filter, in the browser address bar, append the following to the end of the URL:</span></span>

<span data-ttu-id="de2e2-429">/filter/ [AllStreams]。[第二个租户 Id]\|[您租户 ID 这里]</span><span class="sxs-lookup"><span data-stu-id="de2e2-429">/filter/[AllStreams].[Second Tenant Id]\|[YOUR TENANT ID HERE]</span></span>

<span data-ttu-id="de2e2-430">**示例：**</span><span class="sxs-lookup"><span data-stu-id="de2e2-430">**Example:**</span></span>  
<span data-ttu-id="de2e2-431">https://cqd.lync.com/cqd/\#/ 1234567/2018年-02/筛选器 / [AllStreams]。[第二个租户 Id]\|[TENANTID] & 租户 = TENANTID</span><span class="sxs-lookup"><span data-stu-id="de2e2-431">https://cqd.lync.com/cqd/\#/1234567/2018-02/filter/[AllStreams].[Second Tenant Id]\|[TENANTID]&tenant=TENANTID</span></span>

> [!NOTE]
> <span data-ttu-id="de2e2-432">上面的 URL 示例中用于可视化表示形式。</span><span class="sxs-lookup"><span data-stu-id="de2e2-432">The URL example above is for visual representation only.</span></span> <span data-ttu-id="de2e2-433">请使用默认 CQD 链接的<https://cqd.lync.com>。</span><span class="sxs-lookup"><span data-stu-id="de2e2-433">Please use the default CQD link of <https://cqd.lync.com>.</span></span>

#### <a name="query-filters"></a><span data-ttu-id="de2e2-434">查询筛选器</span><span class="sxs-lookup"><span data-stu-id="de2e2-434">Query filters</span></span>

<span data-ttu-id="de2e2-435">使用报告编辑器实现查询筛选器。</span><span class="sxs-lookup"><span data-stu-id="de2e2-435">Query filters are implemented by using the Report Editor.</span></span> <span data-ttu-id="de2e2-436">这些筛选器用于减少 CQD，从而尽量减少报告的总体大小所返回的记录数。</span><span class="sxs-lookup"><span data-stu-id="de2e2-436">These filters are used to reduce the number of records returned by CQD, thus minimizing the report’s overall size.</span></span> <span data-ttu-id="de2e2-437">这是非常有用的过滤掉非托管网络。</span><span class="sxs-lookup"><span data-stu-id="de2e2-437">This is especially useful for filtering out unmanaged networks.</span></span>
<span data-ttu-id="de2e2-438">下面的筛选器使用正则表达式 (RegEx)。</span><span class="sxs-lookup"><span data-stu-id="de2e2-438">The filters below use regular expressions (RegEx).</span></span>

<span data-ttu-id="de2e2-439">_表 3-查询筛选器_</span><span class="sxs-lookup"><span data-stu-id="de2e2-439">_Table 3 - Query filters_</span></span>

| <span data-ttu-id="de2e2-440">筛选器</span><span class="sxs-lookup"><span data-stu-id="de2e2-440">Filter</span></span>               | <span data-ttu-id="de2e2-441">说明</span><span class="sxs-lookup"><span data-stu-id="de2e2-441">Description</span></span>          | <span data-ttu-id="de2e2-442">CQD 查询筛选器示例</span><span class="sxs-lookup"><span data-stu-id="de2e2-442">CQD query filter example</span></span>                                  |
|----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------|
| <span data-ttu-id="de2e2-443">空值</span><span class="sxs-lookup"><span data-stu-id="de2e2-443">Blank values</span></span>         | <span data-ttu-id="de2e2-444">某些筛选器不能对空值进行筛选。</span><span class="sxs-lookup"><span data-stu-id="de2e2-444">Some filters don’t have the option to filter for blank values.</span></span> <span data-ttu-id="de2e2-445">若要手动筛选空值，请使用空的表达式，设置筛选器到等于或不等于，具体取决于您的需要。</span><span class="sxs-lookup"><span data-stu-id="de2e2-445">To filter blank values manually, use the blank expression and set the filter to Equals or Not Equals, depending on your needs.</span></span>                                                                                                                             | <span data-ttu-id="de2e2-446">第二个建筑物名称\< \> \^ \\s\*\$</span><span class="sxs-lookup"><span data-stu-id="de2e2-446">Second Building Name \<\> \^\\s\*\$</span></span>                       |
| <span data-ttu-id="de2e2-447">受欢迎的家庭子网</span><span class="sxs-lookup"><span data-stu-id="de2e2-447">Popular home subnets</span></span> | <span data-ttu-id="de2e2-448">没有有效的构建文件分离托管与非托管网络，在报告中，得到包括家庭网络。</span><span class="sxs-lookup"><span data-stu-id="de2e2-448">Without a valid building file to separate managed from unmanaged networks, home networks will get included in the reports.</span></span> <span data-ttu-id="de2e2-449">这些家庭的子网超出了它的控制范围，可以从报告迅速排除。</span><span class="sxs-lookup"><span data-stu-id="de2e2-449">These home subnets are outside the scope of IT’s control and can be quickly excluded from a report.</span></span> <span data-ttu-id="de2e2-450">受欢迎的家庭子网，在本指南中，定义是 10.0.0.0、 192.168.1.0 和 192.168.0.0。</span><span class="sxs-lookup"><span data-stu-id="de2e2-450">Popular home subnets, as defined in this guide, are 10.0.0.0, 192.168.1.0 and 192.168.0.0.</span></span> | <span data-ttu-id="de2e2-451">子网的第二个\< \> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="de2e2-451">Second Subnet \<\> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0</span></span> |
| <span data-ttu-id="de2e2-452">内部与外部</span><span class="sxs-lookup"><span data-stu-id="de2e2-452">Inside vs. outside</span></span>   | <span data-ttu-id="de2e2-453">用于筛选 （内部） 托管或非托管 （外部） 的报告。</span><span class="sxs-lookup"><span data-stu-id="de2e2-453">Used to filter a report for managed (inside) or unmanaged (outside).</span></span> <span data-ttu-id="de2e2-454">托管的 CQD 模板已预配置了这些筛选器。</span><span class="sxs-lookup"><span data-stu-id="de2e2-454">The managed CQD template is already preconfigured with these filters.</span></span>                                                                                                                                                                                | <span data-ttu-id="de2e2-455">第二个在公司内部为内部</span><span class="sxs-lookup"><span data-stu-id="de2e2-455">Second Inside Corp = Inside</span></span>                               |

#### <a name="report-filters"></a><span data-ttu-id="de2e2-456">报表筛选器</span><span class="sxs-lookup"><span data-stu-id="de2e2-456">Report filters</span></span>

<span data-ttu-id="de2e2-457">报表筛选器实现的呈现报告或者在报告编辑器中或直接向报表中添加筛选器。</span><span class="sxs-lookup"><span data-stu-id="de2e2-457">Report filters are implemented by adding a filter to the rendered report either in the Report Editor or directly to the report.</span></span> <span data-ttu-id="de2e2-458">在整个模板使用下列报表筛选器。</span><span class="sxs-lookup"><span data-stu-id="de2e2-458">The following reports filters are used throughout the template.</span></span>

<span data-ttu-id="de2e2-459">_表 4-报告筛选器_</span><span class="sxs-lookup"><span data-stu-id="de2e2-459">_Table 4 - Report Filter_</span></span>

| <span data-ttu-id="de2e2-460">筛选器</span><span class="sxs-lookup"><span data-stu-id="de2e2-460">Filter</span></span>     | <span data-ttu-id="de2e2-461">说明</span><span class="sxs-lookup"><span data-stu-id="de2e2-461">Description</span></span>                            | <span data-ttu-id="de2e2-462">CQD 的报表筛选器示例</span><span class="sxs-lookup"><span data-stu-id="de2e2-462">CQD report filter example</span></span>         |
|------------|----------------------------------------|-----------------------------------|
| <span data-ttu-id="de2e2-463">Month</span><span class="sxs-lookup"><span data-stu-id="de2e2-463">Month</span></span>      | <span data-ttu-id="de2e2-464">从该年开始，然后月。</span><span class="sxs-lookup"><span data-stu-id="de2e2-464">Start with the year first, then month.</span></span> | <span data-ttu-id="de2e2-465">2017-10</span><span class="sxs-lookup"><span data-stu-id="de2e2-465">2017-10</span></span>                           |
| <span data-ttu-id="de2e2-466">按字母顺序</span><span class="sxs-lookup"><span data-stu-id="de2e2-466">Alphabetic</span></span> | <span data-ttu-id="de2e2-467">筛选器的任何字母字符。</span><span class="sxs-lookup"><span data-stu-id="de2e2-467">Filters for any alphabetic characters.</span></span> | <span data-ttu-id="de2e2-468">[一-z]</span><span class="sxs-lookup"><span data-stu-id="de2e2-468">[a-z]</span></span>                             |
| <span data-ttu-id="de2e2-469">数字</span><span class="sxs-lookup"><span data-stu-id="de2e2-469">Numeric</span></span>    | <span data-ttu-id="de2e2-470">筛选器的任何数字字符。</span><span class="sxs-lookup"><span data-stu-id="de2e2-470">Filters for any numeric characters.</span></span>    | <span data-ttu-id="de2e2-471">[0-9]</span><span class="sxs-lookup"><span data-stu-id="de2e2-471">[0-9]</span></span>                             |
| <span data-ttu-id="de2e2-472">百分比</span><span class="sxs-lookup"><span data-stu-id="de2e2-472">Percentage</span></span> | <span data-ttu-id="de2e2-473">一定的百分比筛选器。</span><span class="sxs-lookup"><span data-stu-id="de2e2-473">Filters for a percentage.</span></span>              | <span data-ttu-id="de2e2-474">([3-9]\\。)\|([3-9])\|([1-9][0-9])</span><span class="sxs-lookup"><span data-stu-id="de2e2-474">([3-9]\\.)\|([3-9])\|([1-9][0-9])</span></span> |

## <a name="import-the-cqd-templates"></a><span data-ttu-id="de2e2-475">导入的 CQD 模板</span><span class="sxs-lookup"><span data-stu-id="de2e2-475">Import the CQD templates</span></span>

<span data-ttu-id="de2e2-476">本指南包含[两个 curated 的 CQD 模板](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/quality-of-experience-review-lite-templates-v-1-2.zip?raw=true)。</span><span class="sxs-lookup"><span data-stu-id="de2e2-476">This guide includes [two curated CQD templates](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/quality-of-experience-review-lite-templates-v-1-2.zip?raw=true).</span></span> <span data-ttu-id="de2e2-477">这些模板加快 CQD 的使用情况，并为您提供能够快速利用 CQD 的功能，使用户的团队或 Skype 业务经验的影响。</span><span class="sxs-lookup"><span data-stu-id="de2e2-477">These templates accelerate your usage of CQD and provide you an opportunity to quickly leverage CQD’s capabilities to make an impact on your users’ Teams or Skype for Business experience.</span></span> <span data-ttu-id="de2e2-478">所有网络模板，通过优化使用建筑物下一节中所述工作朝着正在收集并上载到 CQD，构建信息时，可以使用数据文件。</span><span class="sxs-lookup"><span data-stu-id="de2e2-478">The All Networks template, though optimized to work with a building data file, can be used while you work toward collecting and uploading building information into CQD, as described in the next section.</span></span>

<span data-ttu-id="de2e2-479">**若要导入的模板 (。CQDX) 到 CQD 联机**</span><span class="sxs-lookup"><span data-stu-id="de2e2-479">**To import the templates (.CQDX) into CQD Online**</span></span>

1.  <span data-ttu-id="de2e2-480">转到<https://cqd.lync.com>。</span><span class="sxs-lookup"><span data-stu-id="de2e2-480">Go to <https://cqd.lync.com>.</span></span>

2.  <span data-ttu-id="de2e2-481">通过使用 Office 365 管理凭据进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="de2e2-481">Authenticate by using your Office 365 Administrative credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="de2e2-482">您必须具有 Office 365 全局管理员，Skype 业务管理员或报表读者角色访问 CQD。</span><span class="sxs-lookup"><span data-stu-id="de2e2-482">You must have the Office 365 Global Administrator, Skype for Business Administrator, or Report Readers role to access CQD.</span></span> 


3.  <span data-ttu-id="de2e2-483">选择顶部的页的**摘要报告**菜单，然后选择**详细报告**。</span><span class="sxs-lookup"><span data-stu-id="de2e2-483">Select the **Summary Reports** menu at the top of the page, and then choose **Detailed Reports**.</span></span>

4.  <span data-ttu-id="de2e2-484">在摘要窗格中，选择**导入**。</span><span class="sxs-lookup"><span data-stu-id="de2e2-484">On the summary pane, select **Import**.</span></span> <span data-ttu-id="de2e2-485">转到 CQDX 保存的位置，选择 CQDX 模板，然后选择**打开**。</span><span class="sxs-lookup"><span data-stu-id="de2e2-485">Go to the CQDX saved location, select the CQDX template, and then select **Open**.</span></span>

5.  <span data-ttu-id="de2e2-486">将模板上载之后，弹出窗口将显示消息"报告已成功导入。"</span><span class="sxs-lookup"><span data-stu-id="de2e2-486">After the template is uploaded, a pop-up window will display the message “Report import was successful.”</span></span> <span data-ttu-id="de2e2-487">选择**确定。**</span><span class="sxs-lookup"><span data-stu-id="de2e2-487">Select **OK.**</span></span>

![一个弹出窗口，通知用户该模板已成功导入的屏幕快照。](media/quality-of-experience-review-guide-imagestep5.png)

6.  <span data-ttu-id="de2e2-489">第二个的 CQD 模板重复步骤 4 和 5。</span><span class="sxs-lookup"><span data-stu-id="de2e2-489">Repeat steps 4 and 5 for the second CQD template.</span></span>

> [!NOTE]
> <span data-ttu-id="de2e2-490">每个用户导入的 CQD 模板。</span><span class="sxs-lookup"><span data-stu-id="de2e2-490">The CQD templates are imported per user.</span></span> <span data-ttu-id="de2e2-491">如果其他用户需要使用报表，他们必须登录并将这些模板导入到其 CQD 实例。</span><span class="sxs-lookup"><span data-stu-id="de2e2-491">If additional users need to use the report, they must sign in and import the templates into their CQD instance.</span></span> 


## <a name="building-mapping"></a><span data-ttu-id="de2e2-492">生成映射</span><span class="sxs-lookup"><span data-stu-id="de2e2-492">Building mapping</span></span>

<span data-ttu-id="de2e2-493">在团队中或 Skype 的在线业务的部署，所有客户端都外部。</span><span class="sxs-lookup"><span data-stu-id="de2e2-493">In a Teams or Skype for Business Online deployment, all clients are external.</span></span>
<span data-ttu-id="de2e2-494">这意味着，默认情况下，所有客户端都外 CQD 在线中为报告，无论是否在公司内部网络连接客户端具有的。</span><span class="sxs-lookup"><span data-stu-id="de2e2-494">That has the implication that by default, all clients are reported as outside in CQD Online, regardless of whether the client was connected on an internal corporate network.</span></span>

<span data-ttu-id="de2e2-495">当您处理呼叫质量，您需要知道客户端的位置和是否连接到网络，您可以管理或网络无法管理 — — 假设只会提高网络的可管理。</span><span class="sxs-lookup"><span data-stu-id="de2e2-495">When you work with call quality, you need to know the location of a client and whether it was connected to a network you can manage or a network you can’t manage—the assumption being that you can only improve networks you can manage.</span></span>
<span data-ttu-id="de2e2-496">通过将网络和构建信息上载到 CQD 联机，可以使 CQD 来确定客户端是否已连接到/托管公司的内部网络或外部/非托管网络。</span><span class="sxs-lookup"><span data-stu-id="de2e2-496">By uploading network and building information to CQD Online, you enable CQD to determine whether a client was connected to an internal corporate/managed network or to an external/unmanaged network.</span></span>

### <a name="building-data-file-structure"></a><span data-ttu-id="de2e2-497">建立数据文件结构</span><span class="sxs-lookup"><span data-stu-id="de2e2-497">Building data file structure</span></span>

<span data-ttu-id="de2e2-498">您上载的数据文件的格式必须满足以下要求才能通过上载之前，验证检查。</span><span class="sxs-lookup"><span data-stu-id="de2e2-498">The format of the data file you upload must meet the following requirements to pass the validation check before uploading.</span></span>

-   <span data-ttu-id="de2e2-499">该文件必须 TSV 文件，这意味着，对于每一行，每一列分隔的制表符字符或 CSV 文件中的每一列由逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="de2e2-499">The file must be either a TSV file, which means that for each row, each column is separated by a Tab character, or a CSV file in which each column is separated by a comma.</span></span>

-   <span data-ttu-id="de2e2-500">文件不能大于 50 MB。</span><span class="sxs-lookup"><span data-stu-id="de2e2-500">The file can’t be larger than 50 MB.</span></span>

-   <span data-ttu-id="de2e2-501">数据的内容文件*不能包含表格标题*。</span><span class="sxs-lookup"><span data-stu-id="de2e2-501">The content of the data file *must not include table headers*.</span></span> <span data-ttu-id="de2e2-502">换句话说，数据文件的第一行必须是真实的数据，未列标题，如"网络。</span><span class="sxs-lookup"><span data-stu-id="de2e2-502">In other words, the first line of the data file must be real data, not column headings such as “Network.”</span></span>

-   <span data-ttu-id="de2e2-503">对于每个列，数据类型只能是字符串、 数字或布尔值。</span><span class="sxs-lookup"><span data-stu-id="de2e2-503">For each column, the data type can only be String, Number, or Bool.</span></span> <span data-ttu-id="de2e2-504">如果数据类型是数字，值必须为数字的值;它是布尔值，如果值必须是 0 或 1。</span><span class="sxs-lookup"><span data-stu-id="de2e2-504">If the data type is Number, the value must be a numeric value; if it’s Bool, the value must be either 0 or 1.</span></span>

-   <span data-ttu-id="de2e2-505">对于每一列，如果数据类型是字符串，数据可以为空 （但仍必须用适当的分隔符，制表符或逗号分隔）。</span><span class="sxs-lookup"><span data-stu-id="de2e2-505">For each column, if the data type is String, the data can be empty (but still must be separated by an appropriate delimiter, that is a Tab character or comma).</span></span> <span data-ttu-id="de2e2-506">这只是该为字段指定空字符串值。</span><span class="sxs-lookup"><span data-stu-id="de2e2-506">This just assigns that field an empty string value.</span></span>

-   <span data-ttu-id="de2e2-507">必须为每个行的 14 列。</span><span class="sxs-lookup"><span data-stu-id="de2e2-507">There must be 14 columns for each row.</span></span> <span data-ttu-id="de2e2-508">每个列必须具有下表中，所述数据类型和列必须包含在表中列出的顺序。</span><span class="sxs-lookup"><span data-stu-id="de2e2-508">Each column must have the data type described in the following table, and the columns must be in the order listed in the table.</span></span>

<span data-ttu-id="de2e2-509">_表 5 的生成文件结构_</span><span class="sxs-lookup"><span data-stu-id="de2e2-509">_Table 5 - Building file structure_</span></span>

| <span data-ttu-id="de2e2-510">列名称</span><span class="sxs-lookup"><span data-stu-id="de2e2-510">Column name</span></span>        | <span data-ttu-id="de2e2-511">数据类型</span><span class="sxs-lookup"><span data-stu-id="de2e2-511">Data type</span></span> | <span data-ttu-id="de2e2-512">示例</span><span class="sxs-lookup"><span data-stu-id="de2e2-512">Example</span></span>                   | <span data-ttu-id="de2e2-513">指南</span><span class="sxs-lookup"><span data-stu-id="de2e2-513">Guidance</span></span>    |
|--------------------|-----------|---------------------------|-------------|
| <span data-ttu-id="de2e2-514">网络</span><span class="sxs-lookup"><span data-stu-id="de2e2-514">Network</span></span>            | <span data-ttu-id="de2e2-515">字符串</span><span class="sxs-lookup"><span data-stu-id="de2e2-515">String</span></span>    | <span data-ttu-id="de2e2-516">192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="de2e2-516">192.168.1.0</span></span>               | <span data-ttu-id="de2e2-517">必需</span><span class="sxs-lookup"><span data-stu-id="de2e2-517">Required</span></span>    |
| <span data-ttu-id="de2e2-518">NetworkName</span><span class="sxs-lookup"><span data-stu-id="de2e2-518">NetworkName</span></span>        | <span data-ttu-id="de2e2-519">字符串</span><span class="sxs-lookup"><span data-stu-id="de2e2-519">String</span></span>    | <span data-ttu-id="de2e2-520">美国/西雅图/西雅图-海-1</span><span class="sxs-lookup"><span data-stu-id="de2e2-520">USA/Seattle/SEATTLE-SEA-1</span></span> | <span data-ttu-id="de2e2-521">必填\*</span><span class="sxs-lookup"><span data-stu-id="de2e2-521">Required\*</span></span>  |
| <span data-ttu-id="de2e2-522">NetworkRange</span><span class="sxs-lookup"><span data-stu-id="de2e2-522">NetworkRange</span></span>       | <span data-ttu-id="de2e2-523">数字</span><span class="sxs-lookup"><span data-stu-id="de2e2-523">Number</span></span>    | <span data-ttu-id="de2e2-524">26</span><span class="sxs-lookup"><span data-stu-id="de2e2-524">26</span></span>                        | <span data-ttu-id="de2e2-525">必需</span><span class="sxs-lookup"><span data-stu-id="de2e2-525">Required</span></span>    |
| <span data-ttu-id="de2e2-526">BuildingName</span><span class="sxs-lookup"><span data-stu-id="de2e2-526">BuildingName</span></span>       | <span data-ttu-id="de2e2-527">字符串</span><span class="sxs-lookup"><span data-stu-id="de2e2-527">String</span></span>    | <span data-ttu-id="de2e2-528">西雅图-海-1</span><span class="sxs-lookup"><span data-stu-id="de2e2-528">SEATTLE-SEA-1</span></span>             | <span data-ttu-id="de2e2-529">必填\*</span><span class="sxs-lookup"><span data-stu-id="de2e2-529">Required\*</span></span>  |
| <span data-ttu-id="de2e2-530">OwnershipType</span><span class="sxs-lookup"><span data-stu-id="de2e2-530">OwnershipType</span></span>      | <span data-ttu-id="de2e2-531">字符串</span><span class="sxs-lookup"><span data-stu-id="de2e2-531">String</span></span>    | <span data-ttu-id="de2e2-532">Contoso</span><span class="sxs-lookup"><span data-stu-id="de2e2-532">Contoso</span></span>                   | <span data-ttu-id="de2e2-533">可选</span><span class="sxs-lookup"><span data-stu-id="de2e2-533">Optional</span></span>    |
| <span data-ttu-id="de2e2-534">BuildingType</span><span class="sxs-lookup"><span data-stu-id="de2e2-534">BuildingType</span></span>       | <span data-ttu-id="de2e2-535">字符串</span><span class="sxs-lookup"><span data-stu-id="de2e2-535">String</span></span>    | <span data-ttu-id="de2e2-536">IT 终止</span><span class="sxs-lookup"><span data-stu-id="de2e2-536">IT Termination</span></span>            | <span data-ttu-id="de2e2-537">可选</span><span class="sxs-lookup"><span data-stu-id="de2e2-537">Optional</span></span>    |
| <span data-ttu-id="de2e2-538">BuildingOfficeType</span><span class="sxs-lookup"><span data-stu-id="de2e2-538">BuildingOfficeType</span></span> | <span data-ttu-id="de2e2-539">字符串</span><span class="sxs-lookup"><span data-stu-id="de2e2-539">String</span></span>    | <span data-ttu-id="de2e2-540">工程</span><span class="sxs-lookup"><span data-stu-id="de2e2-540">Engineering</span></span>               | <span data-ttu-id="de2e2-541">可选</span><span class="sxs-lookup"><span data-stu-id="de2e2-541">Optional</span></span>    |
| <span data-ttu-id="de2e2-542">城市</span><span class="sxs-lookup"><span data-stu-id="de2e2-542">City</span></span>               | <span data-ttu-id="de2e2-543">字符串</span><span class="sxs-lookup"><span data-stu-id="de2e2-543">String</span></span>    | <span data-ttu-id="de2e2-544">西雅图</span><span class="sxs-lookup"><span data-stu-id="de2e2-544">Seattle</span></span>                   | <span data-ttu-id="de2e2-545">推荐</span><span class="sxs-lookup"><span data-stu-id="de2e2-545">Recommended</span></span> |
| <span data-ttu-id="de2e2-546">邮政编码</span><span class="sxs-lookup"><span data-stu-id="de2e2-546">ZipCode</span></span>            | <span data-ttu-id="de2e2-547">字符串</span><span class="sxs-lookup"><span data-stu-id="de2e2-547">String</span></span>    | <span data-ttu-id="de2e2-548">98001</span><span class="sxs-lookup"><span data-stu-id="de2e2-548">98001</span></span>                     | <span data-ttu-id="de2e2-549">推荐</span><span class="sxs-lookup"><span data-stu-id="de2e2-549">Recommended</span></span> |
| <span data-ttu-id="de2e2-550">国家/地区</span><span class="sxs-lookup"><span data-stu-id="de2e2-550">Country</span></span>            | <span data-ttu-id="de2e2-551">字符串</span><span class="sxs-lookup"><span data-stu-id="de2e2-551">String</span></span>    | <span data-ttu-id="de2e2-552">我们</span><span class="sxs-lookup"><span data-stu-id="de2e2-552">US</span></span>                        | <span data-ttu-id="de2e2-553">推荐</span><span class="sxs-lookup"><span data-stu-id="de2e2-553">Recommended</span></span> |
| <span data-ttu-id="de2e2-554">省/市/自治区</span><span class="sxs-lookup"><span data-stu-id="de2e2-554">State</span></span>              | <span data-ttu-id="de2e2-555">字符串</span><span class="sxs-lookup"><span data-stu-id="de2e2-555">String</span></span>    | <span data-ttu-id="de2e2-556">WA</span><span class="sxs-lookup"><span data-stu-id="de2e2-556">WA</span></span>                        | <span data-ttu-id="de2e2-557">推荐</span><span class="sxs-lookup"><span data-stu-id="de2e2-557">Recommended</span></span> |
| <span data-ttu-id="de2e2-558">区域</span><span class="sxs-lookup"><span data-stu-id="de2e2-558">Region</span></span>             | <span data-ttu-id="de2e2-559">字符串</span><span class="sxs-lookup"><span data-stu-id="de2e2-559">String</span></span>    | <span data-ttu-id="de2e2-560">MSU</span><span class="sxs-lookup"><span data-stu-id="de2e2-560">MSUS</span></span>                      | <span data-ttu-id="de2e2-561">推荐</span><span class="sxs-lookup"><span data-stu-id="de2e2-561">Recommended</span></span> |
| <span data-ttu-id="de2e2-562">InsideCorp</span><span class="sxs-lookup"><span data-stu-id="de2e2-562">InsideCorp</span></span>         | <span data-ttu-id="de2e2-563">Bool</span><span class="sxs-lookup"><span data-stu-id="de2e2-563">Bool</span></span>      | <span data-ttu-id="de2e2-564">1</span><span class="sxs-lookup"><span data-stu-id="de2e2-564">1</span></span>                         | <span data-ttu-id="de2e2-565">必需</span><span class="sxs-lookup"><span data-stu-id="de2e2-565">Required</span></span>    |
| <span data-ttu-id="de2e2-566">ExpressRoute</span><span class="sxs-lookup"><span data-stu-id="de2e2-566">ExpressRoute</span></span>       | <span data-ttu-id="de2e2-567">Bool</span><span class="sxs-lookup"><span data-stu-id="de2e2-567">Bool</span></span>      | <span data-ttu-id="de2e2-568">0</span><span class="sxs-lookup"><span data-stu-id="de2e2-568">0</span></span>                         | <span data-ttu-id="de2e2-569">必需</span><span class="sxs-lookup"><span data-stu-id="de2e2-569">Required</span></span>    |

<span data-ttu-id="de2e2-570">\*尽管并不要求由 CQD，所配置的模板显示建筑物和网络名称。</span><span class="sxs-lookup"><span data-stu-id="de2e2-570">\*While not required by CQD, the templates are configured to display Building and Network name.</span></span>

#### <a name="supernetting"></a><span data-ttu-id="de2e2-571">Supernetting</span><span class="sxs-lookup"><span data-stu-id="de2e2-571">Supernetting</span></span>

<span data-ttu-id="de2e2-572">您可以使用 supernetting，通常称为无类别域间路由 (CIDR，) 定义各个子网的位置。</span><span class="sxs-lookup"><span data-stu-id="de2e2-572">You can use supernetting, commonly called Classless Inter-Domain Routing (CIDR,) in place of defining each subnet.</span></span> <span data-ttu-id="de2e2-573">*Supernet*是组合的几种共享单个路由前缀的子网。</span><span class="sxs-lookup"><span data-stu-id="de2e2-573">A *supernet* is a combination of several subnets that share a single routing prefix.</span></span> <span data-ttu-id="de2e2-574">而不是添加一个条目为每个子网，您可以使用 supernetted/CIDR 地址。</span><span class="sxs-lookup"><span data-stu-id="de2e2-574">Instead of adding an entry for each subnet, you can use the supernetted/CIDR address.</span></span> <span data-ttu-id="de2e2-575">Supernetting 支持，但我们不建议使用它。</span><span class="sxs-lookup"><span data-stu-id="de2e2-575">Supernetting is supported, but we don’t recommend using it.</span></span>

<span data-ttu-id="de2e2-576">例如，Contoso 的营销建筑组成下面的子网：</span><span class="sxs-lookup"><span data-stu-id="de2e2-576">For example, Contoso’s marketing building is made up of the subnets below:</span></span>

-   <span data-ttu-id="de2e2-577">10.1.0.0/24--第一层</span><span class="sxs-lookup"><span data-stu-id="de2e2-577">10.1.0.0/24 – first floor</span></span>

-   <span data-ttu-id="de2e2-578">10.1.1.0/24 – 二楼</span><span class="sxs-lookup"><span data-stu-id="de2e2-578">10.1.1.0/24 – second floor</span></span>

-   <span data-ttu-id="de2e2-579">10.1.2.0/24--第三个平面布置</span><span class="sxs-lookup"><span data-stu-id="de2e2-579">10.1.2.0/24 – third floor</span></span>

-   <span data-ttu-id="de2e2-580">10.1.3.0/24--第四的地面</span><span class="sxs-lookup"><span data-stu-id="de2e2-580">10.1.3.0/24 – fourth floor</span></span>

<span data-ttu-id="de2e2-581">您可以添加一个条目为每个子网，而不是使用 supernetted/CIDR 地址 — — 在本示例中，10.1.0.0/22。</span><span class="sxs-lookup"><span data-stu-id="de2e2-581">Instead of adding an entry for each subnet, you can use the supernetted/CIDR address—in this example, 10.1.0.0/22.</span></span>

-   <span data-ttu-id="de2e2-582">网络 = 10.1.0.0</span><span class="sxs-lookup"><span data-stu-id="de2e2-582">Network = 10.1.0.0</span></span>

-   <span data-ttu-id="de2e2-583">网络范围 = 22</span><span class="sxs-lookup"><span data-stu-id="de2e2-583">Network Range = 22</span></span>

<span data-ttu-id="de2e2-584">以下是几点要实现 supernetting 之前，请考虑：</span><span class="sxs-lookup"><span data-stu-id="de2e2-584">Here are a few things to consider before you implement supernetting:</span></span>

-   <span data-ttu-id="de2e2-585">Supernetting 采用较少的时间提前，但代价是降低数据的丰富程度方面。</span><span class="sxs-lookup"><span data-stu-id="de2e2-585">Supernetting takes less time up front, but it comes at the cost of reducing the richness of your data.</span></span> <span data-ttu-id="de2e2-586">让我们假设没有质量问题涉及网 200.1.2.0。</span><span class="sxs-lookup"><span data-stu-id="de2e2-586">Let’s say there’s a quality problem involving subnet 200.1.2.0.</span></span> <span data-ttu-id="de2e2-587">如果实现 supernetting，不知道在建筑物中子网的位置或哪种类型的网络 （例如，实验室）。</span><span class="sxs-lookup"><span data-stu-id="de2e2-587">If you implemented supernetting, you won’t know where in the building the subnet is located or what type of network it is (for example, a lab).</span></span> <span data-ttu-id="de2e2-588">如同建筑物的所有子网定义并上载楼层位置信息，您可以查看该区别。</span><span class="sxs-lookup"><span data-stu-id="de2e2-588">If you’d defined all the subnets for a building and uploaded floor location information, you’d be able to see that distinction.</span></span>

-   <span data-ttu-id="de2e2-589">请务必确保 supernetted/CIDR 地址是正确的并不捕捉不需要子网。</span><span class="sxs-lookup"><span data-stu-id="de2e2-589">It’s important to ensure that the supernetted/CIDR address is correct and isn’t catching unwanted subnets.</span></span>

-   <span data-ttu-id="de2e2-590">Supernetting 可以使用 8 位为 28 位掩码生成映射中。</span><span class="sxs-lookup"><span data-stu-id="de2e2-590">Supernetting can be used in a building mapping with 8-bit to 28-bit mask.</span></span>

-   <span data-ttu-id="de2e2-591">它是非常常见，在数据中查找 192.168.0.0。</span><span class="sxs-lookup"><span data-stu-id="de2e2-591">It’s quite common to find 192.168.0.0 in data.</span></span> <span data-ttu-id="de2e2-592">对于许多公司来说，这表示该用户是在家里。</span><span class="sxs-lookup"><span data-stu-id="de2e2-592">For many organizations, this indicates that the user is at home.</span></span> <span data-ttu-id="de2e2-593">对于其他人，这是 IP 地址方案为附属机构。</span><span class="sxs-lookup"><span data-stu-id="de2e2-593">For others, this is the IP address scheme for a satellite office.</span></span> <span data-ttu-id="de2e2-594">如果您的组织具有使用此配置的办公室，不包括其在构建文件中很难区分家庭和内部网络，通过使用通用的子网。</span><span class="sxs-lookup"><span data-stu-id="de2e2-594">If your organization does have offices that use this configuration, don’t include it in your building file as it’s difficult to distinguish between home and internal networks by using common subnets.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="de2e2-595">用于表示 supernet 网络范围。</span><span class="sxs-lookup"><span data-stu-id="de2e2-595">The network range can be used to represent a supernet.</span></span> <span data-ttu-id="de2e2-596">所有新生成的数据文件上载将检查有任何重叠范围。</span><span class="sxs-lookup"><span data-stu-id="de2e2-596">All new building data file uploads will be checked for any overlapping ranges.</span></span> <span data-ttu-id="de2e2-597">如果您以前上载的构建文件，应下载当前文件并上载再次来识别任何重叠并修复该问题。</span><span class="sxs-lookup"><span data-stu-id="de2e2-597">If you have previously uploaded a building file, you should download the current file and upload it again to identify any overlaps and fix the issue.</span></span> <span data-ttu-id="de2e2-598">任何重叠以前上载的文件的情况可能会导致错误的子网与报告中的建筑映射。</span><span class="sxs-lookup"><span data-stu-id="de2e2-598">Any overlap in previously uploaded files might result in the wrong mappings of subnets to buildings in the reports.</span></span> 


#### <a name="vpn"></a><span data-ttu-id="de2e2-599">VPN</span><span class="sxs-lookup"><span data-stu-id="de2e2-599">VPN</span></span>

<span data-ttu-id="de2e2-600">客户端发送到 Office 365 的体验 (QoE) 数据的质量 — — 即 CQD 数据来自 — — 包括 VPN 标志。</span><span class="sxs-lookup"><span data-stu-id="de2e2-600">The quality of experience (QoE) data that clients send to Office 365—which is where CQD data is sourced from—includes a VPN flag.</span></span> <span data-ttu-id="de2e2-601">但是，此标志依赖 VPN 供应商报告到 Windows 注册 VPN 网络适配器远程访问适配器。</span><span class="sxs-lookup"><span data-stu-id="de2e2-601">However, this flag relies on VPN vendors’ reporting to Windows that the VPN network adapter registered is a Remote Access adapter.</span></span> <span data-ttu-id="de2e2-602">不是所有 VPN 供应商正确都注册远程访问适配器。</span><span class="sxs-lookup"><span data-stu-id="de2e2-602">Not all VPN vendors properly register Remote Access adapters.</span></span> <span data-ttu-id="de2e2-603">因此，您可能无法使用内置的 VPN 查询筛选器。</span><span class="sxs-lookup"><span data-stu-id="de2e2-603">Because of this, you might not be able to use the built-in VPN query filters.</span></span> <span data-ttu-id="de2e2-604">有两种方法以适应 VPN 中生成的子网信息文件。</span><span class="sxs-lookup"><span data-stu-id="de2e2-604">There are two approaches to accommodating VPN subnets in the building information file.</span></span>

-   <span data-ttu-id="de2e2-605">通过在此字段中的文本"VPN"用于 VPN 网定义**网络名称**。</span><span class="sxs-lookup"><span data-stu-id="de2e2-605">Define a **Network Name** by using the text “VPN” in this field for VPN subnets.</span></span>

![报表定义如何创建 VPN 网呼叫质量面板中的屏幕快照](media/quality-of-experience-review-guide-image10.png)

<span data-ttu-id="de2e2-607">_图 10-VPN 使用网络名称_</span><span class="sxs-lookup"><span data-stu-id="de2e2-607">_Figure 10 - VPN using network name_</span></span>

-   <span data-ttu-id="de2e2-608">通过在此字段中的文本"VPN"用于 VPN 网定义**生成名称**。</span><span class="sxs-lookup"><span data-stu-id="de2e2-608">Define a **Building Name** by using the text “VPN” in this field for VPN subnets.</span></span>

![报表中定义如何创建生成定义包含 VPN 网呼叫质量面板的屏幕快照。](media/quality-of-experience-review-guide-image11.png)

<span data-ttu-id="de2e2-610">_图 11-VPN 使用建筑物名称_</span><span class="sxs-lookup"><span data-stu-id="de2e2-610">_Figure 11 - VPN using building name_</span></span>

> [!IMPORTANT]
> <span data-ttu-id="de2e2-611">某些 VPN 实现不准确报告子网信息。</span><span class="sxs-lookup"><span data-stu-id="de2e2-611">Certain VPN implementations don’t accurately report subnet information.</span></span> <span data-ttu-id="de2e2-612">如果这发生在您的报告，我们建议当将 VPN 网添加到构建文件中，而不是子网的一项作为单独的 32 位网络 VPN 网中添加每个地址输入项进行分隔。</span><span class="sxs-lookup"><span data-stu-id="de2e2-612">If this occurs in your reporting, we recommend that when you add a VPN subnet to the building file, instead of one entry for the subnet, add separate entries for each address in the VPN subnet as a separate 32-bit network.</span></span> <span data-ttu-id="de2e2-613">每行可有相同的生成元数据。</span><span class="sxs-lookup"><span data-stu-id="de2e2-613">Each row can have the same building metadata.</span></span> <span data-ttu-id="de2e2-614">例如，而不是 172.16.18.0/24 一行，有 253 行，一行从 172.16.18.1/32 到 172.16.18.254/32，包括每个地址。</span><span class="sxs-lookup"><span data-stu-id="de2e2-614">For example, instead of one row for 172.16.18.0/24, you have 253 rows, with one row for each address from 172.16.18.1/32 through 172.16.18.254/32, inclusive.</span></span>


> [!NOTE]
> <span data-ttu-id="de2e2-615">VPN 连接据悉错误识别的网络连接为基础的互联网连接时有线无线。</span><span class="sxs-lookup"><span data-stu-id="de2e2-615">VPN connections have been known to misidentify the network connection as wired when the underlying internet connection is wireless.</span></span> <span data-ttu-id="de2e2-616">在 VPN 连接上考察质量，不能假定，准确地标识的连接类型。</span><span class="sxs-lookup"><span data-stu-id="de2e2-616">When looking at quality over VPN connections, you can’t assume that the connection type has been accurately identified.</span></span>

### <a name="uploading-building-information"></a><span data-ttu-id="de2e2-617">上载的信息构建</span><span class="sxs-lookup"><span data-stu-id="de2e2-617">Uploading building information</span></span>

<span data-ttu-id="de2e2-618">CQD 摘要报告控制板包括**租户数据上载**页面，通过选择**租户数据上载**链接标签右上角 （查找齿轮形状的图标）。</span><span class="sxs-lookup"><span data-stu-id="de2e2-618">The CQD Summary Reports dashboard includes a **Tenant Data Upload** page, accessed by selecting the **Tenant Data Upload** link tag on the upper-right corner (look for the gear icon).</span></span> <span data-ttu-id="de2e2-619">此页用于管理员上载他们自己的信息，如 IP 地址和地理位置的信息，映射每个无线接入点和它的 MAC 地址的映射等等。</span><span class="sxs-lookup"><span data-stu-id="de2e2-619">This page is used for admins to upload their own information, such as mapping of IP address and geographical information, mapping each wireless access point and its MAC address, and so on.</span></span>

1.  <span data-ttu-id="de2e2-620">转到通过浏览联机的 CQD <https://cqd.lync.com>。</span><span class="sxs-lookup"><span data-stu-id="de2e2-620">Go to CQD Online by browsing to <https://cqd.lync.com>.</span></span>

2.  <span data-ttu-id="de2e2-621">在右上角，选择齿轮图标并从**摘要报告**页面中选择**租户的数据上载**。</span><span class="sxs-lookup"><span data-stu-id="de2e2-621">Select the gear icon in the upper-right corner, and choose **Tenant Data Upload** from the **Summary Reports** page.</span></span>

![呼叫质量仪表板中的上载数据时，会出现一个对话框的屏幕快照。](media/quality-of-experience-review-guide-image12.png)

<span data-ttu-id="de2e2-623">_图 12-租户数据上载菜单_</span><span class="sxs-lookup"><span data-stu-id="de2e2-623">_Figure 12 - Tenant Data Upload menu_</span></span>

1.  <span data-ttu-id="de2e2-624">或者，如果这是您第一次访问 CQD，您需要将生成的数据上载。</span><span class="sxs-lookup"><span data-stu-id="de2e2-624">Alternatively, if this is your first time visiting CQD, you’ll be asked to upload building data.</span></span> <span data-ttu-id="de2e2-625">您可以选择**立即上载**要快速导航到**租户数据上载**页面。</span><span class="sxs-lookup"><span data-stu-id="de2e2-625">You can select **Upload Now** to quickly navigate to the **Tenant Data Upload** page.</span></span>

![通知用户上载构建数据呼叫质量面板中的标志性的屏幕快照。](media/quality-of-experience-review-guide-image13.png)

<span data-ttu-id="de2e2-627">_图 13-构建数据上载横幅_</span><span class="sxs-lookup"><span data-stu-id="de2e2-627">_Figure 13 - Building data upload banner_</span></span>

1.  <span data-ttu-id="de2e2-628">在**租户数据上载**页上，选择**浏览**以选择一个数据文件。</span><span class="sxs-lookup"><span data-stu-id="de2e2-628">On the **Tenant Data Upload** page, select **Browse** to choose a data file.</span></span>

2.  <span data-ttu-id="de2e2-629">选择数据文件后, 指定**开始日期**和 （可选） 指定的结束日期。</span><span class="sxs-lookup"><span data-stu-id="de2e2-629">After selecting a data file, specify **Start date** and, optionally, specify an end date.</span></span>

3.  <span data-ttu-id="de2e2-630">选择**开始日期**之后, 选择**上载**到 CQD 上载文件。</span><span class="sxs-lookup"><span data-stu-id="de2e2-630">After selecting **Start date**, select **Upload** to upload the file to the CQD.</span></span> <br><br><span data-ttu-id="de2e2-631">该文件将上载之前，对其进行验证。</span><span class="sxs-lookup"><span data-stu-id="de2e2-631">Before the file is uploaded, it’s validated.</span></span> <span data-ttu-id="de2e2-632">如果验证失败，则会显示错误消息，请求您更正该文件。</span><span class="sxs-lookup"><span data-stu-id="de2e2-632">If validation fails, an error message is displayed requesting that you correct the file.</span></span> <span data-ttu-id="de2e2-633">下图显示了在数据文件中的列的数目不正确时出现错误。</span><span class="sxs-lookup"><span data-stu-id="de2e2-633">The following figure shows an error occurring when the number of columns in the data file is incorrect.</span></span>

![呼叫质量仪表板中导入生成数据时描述的错误消息对话框的屏幕快照。](media/quality-of-experience-review-guide-image14.png)

<span data-ttu-id="de2e2-635">_图 14-构建数据上载错误_</span><span class="sxs-lookup"><span data-stu-id="de2e2-635">_Figure 14 - Building data upload error_</span></span>

4.  <span data-ttu-id="de2e2-636">如果在验证过程中不出现任何错误，将会成功上载文件。</span><span class="sxs-lookup"><span data-stu-id="de2e2-636">If no errors occur during validation, the file upload will succeed.</span></span> <span data-ttu-id="de2e2-637">然后，您可以看到在**我上载**表中，显示在该页面底部当前的租户的所有上载的文件的完整列表上载的数据文件。</span><span class="sxs-lookup"><span data-stu-id="de2e2-637">You can then see the uploaded data file in the **My uploads** table, which shows the full list of all uploaded files for the current tenant at the bottom of that page.</span></span>

> [!NOTE]
> <span data-ttu-id="de2e2-638">它可以长达四个小时完成处理生成文件。</span><span class="sxs-lookup"><span data-stu-id="de2e2-638">It can take up to four hours to finish processing the building file.</span></span> <br><br> <span data-ttu-id="de2e2-639">如果您已上载的构建文件而需要添加子网可能已丢失或排除，通过添加新的子网中修改的原始文件、 删除当前文件，并重新上载新编辑过的文件。</span><span class="sxs-lookup"><span data-stu-id="de2e2-639">If you’ve already uploaded a building file and need to add subnets that might have been missed or excluded, modify the original file by adding the new subnets, remove the current file, and re-upload the newly edited file.</span></span> <span data-ttu-id="de2e2-640">可只有一个活动的生成中 CQD 的数据文件。</span><span class="sxs-lookup"><span data-stu-id="de2e2-640">There can be only one active building data file in CQD.</span></span> 

### <a name="missing-subnets"></a><span data-ttu-id="de2e2-641">丢失子网</span><span class="sxs-lookup"><span data-stu-id="de2e2-641">Missing subnets</span></span>

<span data-ttu-id="de2e2-642">上载管理网络的构建信息之后, 每个托管的网络应具有构建关联。</span><span class="sxs-lookup"><span data-stu-id="de2e2-642">After uploading building information for managed networks, every managed network should have a building association.</span></span> <span data-ttu-id="de2e2-643">然而，这并不总是这种情况;通常情况下，会丢失一些子网。</span><span class="sxs-lookup"><span data-stu-id="de2e2-643">However, this isn’t always the case; typically, a few subnets are missed.</span></span> <span data-ttu-id="de2e2-644">本部分介绍如何验证这些丢失的网络。</span><span class="sxs-lookup"><span data-stu-id="de2e2-644">This section covers how to validate those missing networks.</span></span>

<span data-ttu-id="de2e2-645">中 CQD 联机的**详细报告**网页浏览，并定位到 CQD 模板中包括**缺少子报表**。</span><span class="sxs-lookup"><span data-stu-id="de2e2-645">Browse to the **Detailed Reports** page in CQD Online and navigate to the **Missing Subnet Report** included in the CQD templates.</span></span> <span data-ttu-id="de2e2-646">这会带来建筑中未定义的 10 个或更多的音频流的所有子网数据文件。</span><span class="sxs-lookup"><span data-stu-id="de2e2-646">This presents all the subnets with 10 or more audio streams that are not defined in the building data file.</span></span> <span data-ttu-id="de2e2-647">请确保此列表中没有管理的网络。</span><span class="sxs-lookup"><span data-stu-id="de2e2-647">Ensure that there are no managed networks in this list.</span></span> <span data-ttu-id="de2e2-648">如果丢失子网，请更新数据文件并重新将其上载到 CQD 的原始建筑。</span><span class="sxs-lookup"><span data-stu-id="de2e2-648">If subnets are missing, update the original building data file and re-upload it to CQD.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="de2e2-649">您将需要将租户 ID 作为**第二个租户 ID**的查询筛选器添加到此报表以筛选报表，以便只查看您的组织的租户数据。</span><span class="sxs-lookup"><span data-stu-id="de2e2-649">You’ll need to add your tenant ID as a query filter for **Second Tenant ID** to this report to filter the report to view only your organization’s tenant data.</span></span> <span data-ttu-id="de2e2-650">否则，该报告将显示联合子网。</span><span class="sxs-lookup"><span data-stu-id="de2e2-650">Otherwise, the report will show federated subnets.</span></span>

> [!NOTE] 
> <span data-ttu-id="de2e2-651">一定要调整到当前月份月年报表筛选器。</span><span class="sxs-lookup"><span data-stu-id="de2e2-651">Be sure to adjust the Month Year report filter to the current month.</span></span> <span data-ttu-id="de2e2-652">选择**编辑**，然后调整**月份年度**报告筛选器以保存新默认的月份。</span><span class="sxs-lookup"><span data-stu-id="de2e2-652">Select **Edit**, and adjust the **Month Year** report filter to save the new default month.</span></span>                                                  |

![报告显示 CQD 构建数据文件中不包含的显示使用实例的子网。](media/quality-of-experience-review-guide-image15.png)

<span data-ttu-id="de2e2-654">_图 15-缺少生成报告_</span><span class="sxs-lookup"><span data-stu-id="de2e2-654">_Figure 15 - Missing Building Report_</span></span>

## <a name="reliability-investigations"></a><span data-ttu-id="de2e2-655">可靠性调查</span><span class="sxs-lookup"><span data-stu-id="de2e2-655">Reliability investigations</span></span>

<span data-ttu-id="de2e2-656">提高质量的第一步是评估整个组织内的音频可靠性的状态。</span><span class="sxs-lookup"><span data-stu-id="de2e2-656">The first step to improving quality is to assess the state of audio reliability across the organization.</span></span> <span data-ttu-id="de2e2-657">音频的可靠性非常重要的一种良好的用户体验，因为我们从开始测量可靠性的两个组件：</span><span class="sxs-lookup"><span data-stu-id="de2e2-657">Because audio reliability is vital to a positive user experience, we start with the two components that measure reliability:</span></span>

1.  <span data-ttu-id="de2e2-658">**调用安装程序失败：**无法建立会话。</span><span class="sxs-lookup"><span data-stu-id="de2e2-658">**Call Setup Failures:** Session couldn’t be established.</span></span>

2.  <span data-ttu-id="de2e2-659">**调用放失败：**会话建立和意外终止</span><span class="sxs-lookup"><span data-stu-id="de2e2-659">**Call Drop Failures:** Session was established and unexpectedly terminated</span></span>

<span data-ttu-id="de2e2-660">在本节中，我们将介绍方法来研究这两个方面。</span><span class="sxs-lookup"><span data-stu-id="de2e2-660">Throughout this section, we’ll cover methods to investigate both areas.</span></span>

> [!NOTE]
> <span data-ttu-id="de2e2-661">本指南中介绍了模板中包含的并不是所有报告。</span><span class="sxs-lookup"><span data-stu-id="de2e2-661">Not all reports included in the templates are covered in this guide.</span></span> <span data-ttu-id="de2e2-662">请向单个报表说明的详细信息，参阅。</span><span class="sxs-lookup"><span data-stu-id="de2e2-662">Please refer to the individual report description for more information.</span></span>


### <a name="call-setup"></a><span data-ttu-id="de2e2-663">呼叫设置</span><span class="sxs-lookup"><span data-stu-id="de2e2-663">Call setup</span></span>

<span data-ttu-id="de2e2-664">优先在这一领域的补救调用安装程序失败，因为这些故障对用户体验产生重大的负面影响。</span><span class="sxs-lookup"><span data-stu-id="de2e2-664">Prioritize remediating call setup failures in this area first, because these failures have a significant negative impact on the user experience.</span></span>

<span data-ttu-id="de2e2-665">开始调查评估组织，整个调用安装程序失败的百分比，然后设置优先级的建筑物或网络基础的最高百分比的调查区域。</span><span class="sxs-lookup"><span data-stu-id="de2e2-665">Begin your investigation by assessing the percentage of overall call setup failures for the organization, and then prioritize areas of investigation based on the highest percentage by building or network.</span></span>

#### <a name="call-setup-failures-overall"></a><span data-ttu-id="de2e2-666">调用整体安装错误</span><span class="sxs-lookup"><span data-stu-id="de2e2-666">Call setup failures overall</span></span>

<span data-ttu-id="de2e2-667">此图表报表显示成功调用设置的总金额，并随着时间的推移调用安装程序失败。</span><span class="sxs-lookup"><span data-stu-id="de2e2-667">This chart report displays the total amount of successful call set up and call setup failures over time.</span></span> <span data-ttu-id="de2e2-668">指向任何一个要显示的列的单个值，如下图中所示。</span><span class="sxs-lookup"><span data-stu-id="de2e2-668">Point to any one of the columns to display its individual values, as shown in the figure below.</span></span>

![该图显示音频呼叫流安装失败的百分比的屏幕抓图](media/quality-of-experience-review-guide-image16.png)

<span data-ttu-id="de2e2-670">_图 16-音频可靠性-呼叫流设置失败_</span><span class="sxs-lookup"><span data-stu-id="de2e2-670">_Figure 16 - Audio Reliability - Call Stream Setup Failures_</span></span>

##### <a name="analysis"></a><span data-ttu-id="de2e2-671">分析</span><span class="sxs-lookup"><span data-stu-id="de2e2-671">Analysis</span></span>

<span data-ttu-id="de2e2-672">此报表显示随着时间的推移您所在组织的音频呼叫设置使用情况和故障。</span><span class="sxs-lookup"><span data-stu-id="de2e2-672">This report displays your organization’s audio call setup usage and failures over time.</span></span> <span data-ttu-id="de2e2-673">使用此报表，可以回答以下问题并确定您下一步行动纲领：</span><span class="sxs-lookup"><span data-stu-id="de2e2-673">By using this report, you can answer the following questions and determine your next course of action:</span></span>

1.  <span data-ttu-id="de2e2-674">什么是当月总调用安装程序失败百分比？</span><span class="sxs-lookup"><span data-stu-id="de2e2-674">What is the total call setup failure percentage for the current month?</span></span>

2.  <span data-ttu-id="de2e2-675">是总调用安装程序失败百分比的下方或上方的定义的目标度量？</span><span class="sxs-lookup"><span data-stu-id="de2e2-675">Is the total call setup failure percentage below or above the defined target metric?</span></span>

3.  <span data-ttu-id="de2e2-676">更糟或更好，比前一个月是故障趋势？</span><span class="sxs-lookup"><span data-stu-id="de2e2-676">Is the failure trend worse or better than the previous month?</span></span>

4.  <span data-ttu-id="de2e2-677">故障趋势增加，steady，或减少吗？</span><span class="sxs-lookup"><span data-stu-id="de2e2-677">Is the failure trend increasing, steady, or decreasing?</span></span>

<span data-ttu-id="de2e2-678">本报告中提供的信息将告诉您整体的呼叫设置整个组织的失败频率的情景。</span><span class="sxs-lookup"><span data-stu-id="de2e2-678">The information presented in this report will tell the story of how often your overall call setups are failing across your organization.</span></span>

<span data-ttu-id="de2e2-679">不管前面的回答中，花时间来研究进一步通过使用包含子报表来查找任何个别建筑物或可能需要更新的网络。</span><span class="sxs-lookup"><span data-stu-id="de2e2-679">Irrespective of the previous answers, take the time to investigate further by using the included sub-reports to look for any individual buildings or networks that might need remediation.</span></span> <span data-ttu-id="de2e2-680">虽然总体失败率可能低于目标指标，往往对于一个或多个建筑物或网络故障率高于规格，并且需要修正。</span><span class="sxs-lookup"><span data-stu-id="de2e2-680">Although the overall failure rate might be below the target metric, often the failure rates for one or more buildings or networks are above the metric and need remediation.</span></span>

#### <a name="call-setup-failures-by-building-and-subnet"></a><span data-ttu-id="de2e2-681">通过构建和子网来调用安装程序失败</span><span class="sxs-lookup"><span data-stu-id="de2e2-681">Call setup failures by building and subnet</span></span> 

<span data-ttu-id="de2e2-682">此表报表用于发现和隔离任何建筑物或需要补救的网络。</span><span class="sxs-lookup"><span data-stu-id="de2e2-682">This table report is used to discover and isolate any buildings or networks that need remediation.</span></span>

> [!NOTE]
> <span data-ttu-id="de2e2-683">一定要调整到当前月份月年报表筛选器。</span><span class="sxs-lookup"><span data-stu-id="de2e2-683">Be sure to adjust the Month Year report filter to the current month.</span></span> <span data-ttu-id="de2e2-684">选择**编辑**，然后调整**月份年度**报告筛选器以保存新默认的月份。</span><span class="sxs-lookup"><span data-stu-id="de2e2-684">Select **Edit**, and adjust the **Month Year** report filter to save the new default month.</span></span>


![报告列表调用安装程序失败原因，组织的构建、 网络和子网，每个月。](media/quality-of-experience-review-guide-image17.png)

<span data-ttu-id="de2e2-686">_图 17-通过生成的音频设置故障或子网_</span><span class="sxs-lookup"><span data-stu-id="de2e2-686">_Figure 17 - Audio Setup Failures by Building or Subnet_</span></span>

##### <a name="remediation"></a><span data-ttu-id="de2e2-687">补救措施</span><span class="sxs-lookup"><span data-stu-id="de2e2-687">Remediation</span></span> 

<span data-ttu-id="de2e2-688">精力修正在建筑物或子网的第一次，有失败的最大卷，因为这将最大限度地对用户体验的影响，并有助于迅速降低组织调用安装程序失败。</span><span class="sxs-lookup"><span data-stu-id="de2e2-688">Focus your remediation efforts on buildings or subnets that have the largest volume of failures first, because this will maximize impact to the user experience and help to quickly reduce the organizational call setup failures.</span></span>
<span data-ttu-id="de2e2-689">下表列出报告的 CQD 调用安装程序失败的两个原因。</span><span class="sxs-lookup"><span data-stu-id="de2e2-689">The following table lists the two reasons for call setup failures as reported by CQD.</span></span>

<span data-ttu-id="de2e2-690">_表 6-调用安装程序失败原因_</span><span class="sxs-lookup"><span data-stu-id="de2e2-690">_Table 6 – Reasons for Call Setup Failures_</span></span>

| <span data-ttu-id="de2e2-691">调用安装程序失败原因</span><span class="sxs-lookup"><span data-stu-id="de2e2-691">Call Setup Failures reason</span></span>                       | <span data-ttu-id="de2e2-692">通常的原因</span><span class="sxs-lookup"><span data-stu-id="de2e2-692">Typical cause</span></span>                                                                                                                                                                                                                                                                                   |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="de2e2-693">缺少的 FW 深度数据包检查例外规则</span><span class="sxs-lookup"><span data-stu-id="de2e2-693">Missing FW Deep Packet Inspection Exemption Rule</span></span> | <span data-ttu-id="de2e2-694">指示的路径上的网络设备阻止介质路径由于深度数据包检查规则的建立。</span><span class="sxs-lookup"><span data-stu-id="de2e2-694">Indicates that network equipment along the path prevented the media path from being established due to deep packet inspection rules.</span></span> <span data-ttu-id="de2e2-695">这可能是由于未正确配置的防火墙规则。</span><span class="sxs-lookup"><span data-stu-id="de2e2-695">This is likely due to firewall rules not being correctly configured.</span></span> <span data-ttu-id="de2e2-696">在这种情况下 TCP 握手成功，但在 SSL 握手是不行的。</span><span class="sxs-lookup"><span data-stu-id="de2e2-696">In this case the TCP handshake succeeded but the SSL handshake did not.</span></span>               |
| <span data-ttu-id="de2e2-697">缺少转发 IP 块例外规则</span><span class="sxs-lookup"><span data-stu-id="de2e2-697">Missing FW IP Block Exception Rule</span></span>               | <span data-ttu-id="de2e2-698">指示该路径上的网络设备阻止介质路径到 Office 365 网络正在建立。</span><span class="sxs-lookup"><span data-stu-id="de2e2-698">Indicates that network equipment along the path prevented the media path from being established to the Office 365 network.</span></span> <span data-ttu-id="de2e2-699">这可能是因为不允许访问的 IP 地址和端口用于团队和 Skype 业务流量正确配置的代理服务器或防火墙规则。</span><span class="sxs-lookup"><span data-stu-id="de2e2-699">This might be due to proxy or firewall rules not being correctly configured to allow access to IP addresses and ports used for Teams and Skype for Business traffic.</span></span> |

<span data-ttu-id="de2e2-700">现在当您开始您的补救措施，您可以将精力上特定建筑物或子网。</span><span class="sxs-lookup"><span data-stu-id="de2e2-700">Now as you begin your remediation, you can focus your efforts on a particular building or subnet.</span></span> <span data-ttu-id="de2e2-701">如前表所示，这些问题是由于防火墙或代理服务器配置。</span><span class="sxs-lookup"><span data-stu-id="de2e2-701">As the preceding table shows, these issues are due to firewall or proxy configurations.</span></span> <span data-ttu-id="de2e2-702">查看下表的更新操作中的选项。</span><span class="sxs-lookup"><span data-stu-id="de2e2-702">Review the options in the following table for remediation actions.</span></span>

<span data-ttu-id="de2e2-703">_表 7-调用的下一步安装失败补救措施_</span><span class="sxs-lookup"><span data-stu-id="de2e2-703">_Table 7 - Next Steps for Call Setup Failure Remediation_</span></span>

| <span data-ttu-id="de2e2-704">补救措施</span><span class="sxs-lookup"><span data-stu-id="de2e2-704">Remediation</span></span>           | <span data-ttu-id="de2e2-705">指南</span><span class="sxs-lookup"><span data-stu-id="de2e2-705">Guidance</span></span>     |
|-----------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="de2e2-706">配置防火墙</span><span class="sxs-lookup"><span data-stu-id="de2e2-706">Configure firewall(s)</span></span> | <span data-ttu-id="de2e2-707">与您的网络小组的工作并验证您的防火墙配置针对[Office 365 IP 地址列表](https://aka.ms/o365ips)。</span><span class="sxs-lookup"><span data-stu-id="de2e2-707">Work with your network team and verify your firewall(s) configuration against [the Office 365 IP address list](https://aka.ms/o365ips).</span></span> <span data-ttu-id="de2e2-708">请在防火墙规则包括[媒体网](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams)和端口。</span><span class="sxs-lookup"><span data-stu-id="de2e2-708">Verify that the [media subnets](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams) and ports are included in the firewall rules.</span></span> <span data-ttu-id="de2e2-709">验证必要的 TCP 和 UDP 端口打开防火墙中。</span><span class="sxs-lookup"><span data-stu-id="de2e2-709">Verify that the necessary TCP and UDP ports are opened in the firewall.</span></span> <span data-ttu-id="de2e2-710">媒体倾向于在 TCP 上的 UDP。</span><span class="sxs-lookup"><span data-stu-id="de2e2-710">Media prefers UDP over TCP.</span></span> <span data-ttu-id="de2e2-711">TCP 被认为是一种故障回复的协议。</span><span class="sxs-lookup"><span data-stu-id="de2e2-711">TCP is considered a failback protocol.</span></span><br><ul><li><span data-ttu-id="de2e2-712">**TCP:**端口 443</span><span class="sxs-lookup"><span data-stu-id="de2e2-712">**TCP:** port 443</span></span></li><li><span data-ttu-id="de2e2-713">**UDP:**端口 3478-3481</span><span class="sxs-lookup"><span data-stu-id="de2e2-713">**UDP:** ports 3478–3481</span></span></li><ul> |
| <span data-ttu-id="de2e2-714">验证</span><span class="sxs-lookup"><span data-stu-id="de2e2-714">Verify</span></span>                | <span data-ttu-id="de2e2-715">利用[Microsoft 网络评估工具](https://www.microsoft.com/download/details.aspx?id=53885)来使用连接检查函数验证来自受影响的建筑物或子网的连接。</span><span class="sxs-lookup"><span data-stu-id="de2e2-715">Leverage the [Microsoft Network Assessment Tool](https://www.microsoft.com/download/details.aspx?id=53885) to verify connectivity from the affected building or subnet by using the connectivity check function.</span></span>    |


### <a name="call-drop"></a><span data-ttu-id="de2e2-716">调用拖放</span><span class="sxs-lookup"><span data-stu-id="de2e2-716">Call drop</span></span>

<span data-ttu-id="de2e2-717">与不同调用安装程序失败，没有任何原因代码指示呼叫为什么断线故障发生了，这使它难以找出具体的根本原因。</span><span class="sxs-lookup"><span data-stu-id="de2e2-717">Unlike call setup failures, there is no reason code to indicate why call dropped failures occurred, which makes it difficult to isolate a specific root cause.</span></span> <span data-ttu-id="de2e2-718">若要更好地会审通话中断，使用推理的方法。</span><span class="sxs-lookup"><span data-stu-id="de2e2-718">To better triage dropped calls, use an inferred approach.</span></span> <span data-ttu-id="de2e2-719">通过补救音频感兴趣的任何区域、 修补客户端，并推动团队和业务的 Skype 使用的认证设备，希望除去的呼叫失败拒绝。</span><span class="sxs-lookup"><span data-stu-id="de2e2-719">By remediating any areas of interest for audio, patching clients, and driving usage of certified devices for Teams and Skype for Business, you’d expect call dropped failures to decline.</span></span>

#### <a name="call-drop-failures-overall"></a><span data-ttu-id="de2e2-720">调用整体放失败</span><span class="sxs-lookup"><span data-stu-id="de2e2-720">Call drop failures overall</span></span>

<span data-ttu-id="de2e2-721">此图表报表显示音频流，除去，总的音频流的总金额，总流删除百分比。</span><span class="sxs-lookup"><span data-stu-id="de2e2-721">This chart report displays the total amount of audio streams, total audio streams dropped, and total stream dropped percentage.</span></span> <span data-ttu-id="de2e2-722">指向要显示其值的列的任何一个，如下图中所示。</span><span class="sxs-lookup"><span data-stu-id="de2e2-722">Point to any one of the columns to display its values, as shown in the following figure.</span></span>

![显示音频呼叫流丢弃的百分比图表的屏幕截图](media/quality-of-experience-review-guide-image18.png)

<span data-ttu-id="de2e2-724">_图 18-总调用删除失败百分比_</span><span class="sxs-lookup"><span data-stu-id="de2e2-724">_Figure 18 - Total call dropped failure percentage_</span></span>

##### <a name="analysis"></a><span data-ttu-id="de2e2-725">分析</span><span class="sxs-lookup"><span data-stu-id="de2e2-725">Analysis</span></span>

<span data-ttu-id="de2e2-726">此图表报表显示您所在组织的使用情况和故障一段时间相关调用坠落。</span><span class="sxs-lookup"><span data-stu-id="de2e2-726">This chart report displays your organization’s usage and failures over time related to call drops.</span></span> <span data-ttu-id="de2e2-727">使用此报表，可以回答以下问题：</span><span class="sxs-lookup"><span data-stu-id="de2e2-727">By using this report, you can answer the following questions:</span></span>

1.  <span data-ttu-id="de2e2-728">什么是当前总调用删除百分比？</span><span class="sxs-lookup"><span data-stu-id="de2e2-728">What is the current total call dropped percentage?</span></span>

2.  <span data-ttu-id="de2e2-729">下面定义的目标指标是总百分比？</span><span class="sxs-lookup"><span data-stu-id="de2e2-729">Is the total drop percentage below the defined target metric?</span></span>

3.  <span data-ttu-id="de2e2-730">更糟或更好，比前一个月是故障趋势？</span><span class="sxs-lookup"><span data-stu-id="de2e2-730">Is the failure trend worse or better than the previous month?</span></span>

4.  <span data-ttu-id="de2e2-731">故障趋势增加，steady，或减少吗？</span><span class="sxs-lookup"><span data-stu-id="de2e2-731">Is the failure trend increasing, steady, or decreasing?</span></span>

<span data-ttu-id="de2e2-732">本报告中提供的信息会告诉您整体的呼叫断开整个组织的发生频率的情景。</span><span class="sxs-lookup"><span data-stu-id="de2e2-732">The information presented in this report can tell the story of how often your overall call drops are occurring across your organization.</span></span>

<span data-ttu-id="de2e2-733">不管上面问题的答案需要时间调查使用子报表，若要查找任何建筑物或可能需要更新的网络。</span><span class="sxs-lookup"><span data-stu-id="de2e2-733">Irrespective of the answers to the questions above, take the time to investigate using the sub-reports to look for any buildings or networks that might need remediation.</span></span> <span data-ttu-id="de2e2-734">虽然整体放率可能低于目标指标，经常放一个或多个建筑物或网络指标高于率需要修正。</span><span class="sxs-lookup"><span data-stu-id="de2e2-734">Although the overall drop rate might be below the target metric, often the drop rate for one or more buildings or networks is above the metric and needs remediation.</span></span>

#### <a name="call-drop-failures-by-building-or-subnet"></a><span data-ttu-id="de2e2-735">通过构建或子网来调用放失败</span><span class="sxs-lookup"><span data-stu-id="de2e2-735">Call drop failures by building or subnet</span></span>

<span data-ttu-id="de2e2-736">此表报表中的失败表明通话被意外删除，并导致负的用户体验。</span><span class="sxs-lookup"><span data-stu-id="de2e2-736">Failures in this table report indicate that the call was dropped unexpectedly and resulted in a negative user experience.</span></span> <span data-ttu-id="de2e2-737">有两个模板，一个用于调查会议，另一个用于两方中包括的表报告。</span><span class="sxs-lookup"><span data-stu-id="de2e2-737">There are two table reports included in the template, one for investigating conferencing and the other for two-party.</span></span>

> [!NOTE]
> <span data-ttu-id="de2e2-738">一定要调整到当前月份的月年筛选器。</span><span class="sxs-lookup"><span data-stu-id="de2e2-738">Be sure to adjust the Month Year filter to the current month.</span></span> <span data-ttu-id="de2e2-739">选择**编辑**，然后调整**月年**保存新默认的月份。</span><span class="sxs-lookup"><span data-stu-id="de2e2-739">Select **Edit**, and adjust **Month Year** to save the new default month.</span></span>


![报告列出数量和百分比的通话中断，组织的构建、 网络和子网，每个月。](media/quality-of-experience-review-guide-image19.png)

<span data-ttu-id="de2e2-741">_图 19-音频呼叫断开故障建筑物或子网_</span><span class="sxs-lookup"><span data-stu-id="de2e2-741">_Figure 19 – Audio call dropped failures by building or subnet_</span></span>

##### <a name="remediation"></a><span data-ttu-id="de2e2-742">补救措施</span><span class="sxs-lookup"><span data-stu-id="de2e2-742">Remediation</span></span>

<span data-ttu-id="de2e2-743">使用前面的表格报告，可以在托管网络调用坠落发生上面定义的目标指标现在隔离"热点"。</span><span class="sxs-lookup"><span data-stu-id="de2e2-743">Using the preceding table report, you can now isolate “hot spots” in the managed network where call drops occur above the defined target metric.</span></span> <span data-ttu-id="de2e2-744">精力修正在建筑物或网络的最高总流计数必须首先，做出最大的影响。</span><span class="sxs-lookup"><span data-stu-id="de2e2-744">Focus your remediation efforts on buildings or networks that have the highest total stream count first, to make the biggest impact.</span></span>

<span data-ttu-id="de2e2-745">调用下降的常见原因：</span><span class="sxs-lookup"><span data-stu-id="de2e2-745">Common causes of call drops:</span></span>

-   <span data-ttu-id="de2e2-746">在下设置网络或互联网出口</span><span class="sxs-lookup"><span data-stu-id="de2e2-746">Under-provisioned network or internet egress</span></span>

-   <span data-ttu-id="de2e2-747">没有 QoS 约束的网络配置</span><span class="sxs-lookup"><span data-stu-id="de2e2-747">No QoS configured on constrained networks</span></span>

-   <span data-ttu-id="de2e2-748">旧客户端版本</span><span class="sxs-lookup"><span data-stu-id="de2e2-748">Older client versions</span></span>

-   <span data-ttu-id="de2e2-749">用户行为</span><span class="sxs-lookup"><span data-stu-id="de2e2-749">User behavior</span></span>

<span data-ttu-id="de2e2-750">您发现热点后，您可以利用[调用分析](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309)进一步检查的特定问题的这栋建筑物中的用户。</span><span class="sxs-lookup"><span data-stu-id="de2e2-750">After you discover hot spots, you can leverage [Call Analytics](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309) to further review users in that building for specific issues.</span></span> <span data-ttu-id="de2e2-751">调用分析包含 PII 数据，可用于进一步隔离调用下降的潜在原因。</span><span class="sxs-lookup"><span data-stu-id="de2e2-751">Call Analytics contains PII data and can be useful for further isolating potential reasons for the call drops.</span></span>

<span data-ttu-id="de2e2-752">无论下一步，它是最好通知帮助台问题已经被发现与特定的建筑物或子网。</span><span class="sxs-lookup"><span data-stu-id="de2e2-752">Regardless of your next step, it’s a good practice to notify the helpdesk that an issue has been discovered with specific buildings or subnets.</span></span> <span data-ttu-id="de2e2-753">这种方式，他们可以快速响应传入呼叫和会审的用户更高效。</span><span class="sxs-lookup"><span data-stu-id="de2e2-753">This way, they can quickly respond to incoming calls and triage users more efficiently.</span></span> <span data-ttu-id="de2e2-754">标记的用户可以然后报告给工程团队进行进一步调查。</span><span class="sxs-lookup"><span data-stu-id="de2e2-754">Flagged users can then be reported back to the engineering team for further investigation.</span></span>

<span data-ttu-id="de2e2-755">下表列出了一些常用的方法来管理和补救调用坠落。</span><span class="sxs-lookup"><span data-stu-id="de2e2-755">The following table lists some common methods to manage and remediate call drops.</span></span>

<span data-ttu-id="de2e2-756">_表 9-调用的下一步行动除去补救措施_</span><span class="sxs-lookup"><span data-stu-id="de2e2-756">_Table 9 - Next steps for call drop remediation_</span></span>

| <span data-ttu-id="de2e2-757">补救措施</span><span class="sxs-lookup"><span data-stu-id="de2e2-757">Remediation</span></span>                              | <span data-ttu-id="de2e2-758">指南</span><span class="sxs-lookup"><span data-stu-id="de2e2-758">Guidance</span></span>     |
|------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="de2e2-759">网络/互联网</span><span class="sxs-lookup"><span data-stu-id="de2e2-759">Network/internet</span></span>                         | <span data-ttu-id="de2e2-760">既然您知道哪些建筑受到影响，工作与您的网络小组监视带宽在这栋建筑物，以确定是否有过度使用的问题。</span><span class="sxs-lookup"><span data-stu-id="de2e2-760">Now that you know which building is affected, work with your network team to monitor bandwidth at that building to determine whether there are issues with overutilization.</span></span> <span data-ttu-id="de2e2-761">如果发现问题要与相关联的网络拥塞问题，考虑到这栋建筑物的不断增加带宽。</span><span class="sxs-lookup"><span data-stu-id="de2e2-761">If the issue is discovered to be related to network congestion, consider increasing bandwidth to that building.</span></span> <br><br><span data-ttu-id="de2e2-762">**QoS:**如果增加的带宽是无法实现或成本上不可行，可以考虑 QoS 的实施。</span><span class="sxs-lookup"><span data-stu-id="de2e2-762">**QoS:** If increasing bandwidth is impossible or cost-prohibitive, consider implementing QoS.</span></span> <span data-ttu-id="de2e2-763">这将保证托管网络上的媒体包的优先级别高于非媒体通信。</span><span class="sxs-lookup"><span data-stu-id="de2e2-763">This will guarantee media packets on the managed network are prioritized above non-media traffic.</span></span> <span data-ttu-id="de2e2-764">或者，如果没有明确的证据，该带宽是问题所在，请考虑这些解决方案：</span><span class="sxs-lookup"><span data-stu-id="de2e2-764">Alternatively, if there is no clear evidence that bandwidth is the culprit, consider these solutions:</span></span><br><ul><li>[<span data-ttu-id="de2e2-765">Microsoft 小组 QoS 指南</span><span class="sxs-lookup"><span data-stu-id="de2e2-765">Microsoft Teams QoS Guidance</span></span>](https://docs.microsoft.com/MicrosoftTeams/qos-in-teams)</li><li>[<span data-ttu-id="de2e2-766">Skype 业务 QoS 指南</span><span class="sxs-lookup"><span data-stu-id="de2e2-766">Skype for Business QoS Guidance</span></span>](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_8)</li></ul><br><span data-ttu-id="de2e2-767">**执行网络就绪性评估：**网络评估提供了有关预期的带宽使用情况的详细信息，如何对付带宽和网络发生变化，并建议为团队和业务的 Skype 的网络实践。</span><span class="sxs-lookup"><span data-stu-id="de2e2-767">**Perform a network readiness assessment:** A network assessment provides details about expected bandwidth usage, how to cope with bandwidth and network changes, and recommended networking practices for Teams and Skype for Business.</span></span> <span data-ttu-id="de2e2-768">使用前面的表作为源，有建筑物或评估优秀候选的子网的列表。</span><span class="sxs-lookup"><span data-stu-id="de2e2-768">Using the preceding table as your source, you have a list of buildings or subnets that are excellent candidates for an assessment.</span></span> <br><ul><li>[<span data-ttu-id="de2e2-769">Microsoft 小组网络就绪性评估</span><span class="sxs-lookup"><span data-stu-id="de2e2-769">Microsoft Teams Network Readiness Assessment</span></span>](https://docs.microsoft.com/MicrosoftTeams/3-envision-evaluate-my-environment#test-the-network)</li><li>[<span data-ttu-id="de2e2-770">Skype 的业务网络就绪性评估</span><span class="sxs-lookup"><span data-stu-id="de2e2-770">Skype for Business Network Readiness Assessment</span></span>](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers/?pageState=NetworkReadiness)</li></ul><br><span data-ttu-id="de2e2-771">**Microsoft 网络评估工具：**使用此工具对网络性能的一个简单的测试来确定如何更好地将网络执行小组或 Skype 的在线业务的呼叫。</span><span class="sxs-lookup"><span data-stu-id="de2e2-771">**Microsoft Network Assessment Tool:** Use this tool for a simple test of network performance to determine how well the network would perform for a Teams or Skype for Business Online call.</span></span> <span data-ttu-id="de2e2-772">该工具可帮助您评估的子网的性能和验证网络免遭 Microsoft 性能[要求](https://aka.ms/performancerequirements)的准备情况。</span><span class="sxs-lookup"><span data-stu-id="de2e2-772">The tool helps you assess the performance of a subnet and validate the readiness of the network against Microsoft performance [requirements](https://aka.ms/performancerequirements).</span></span><ul><li>[<span data-ttu-id="de2e2-773">下载网络评估工具</span><span class="sxs-lookup"><span data-stu-id="de2e2-773">Download the Network Assessment Tool</span></span>](https://www.microsoft.com/download/details.aspx?id=53885)</li></ul>         |
| <span data-ttu-id="de2e2-774">客户端 (Skype 业务仅在线)</span><span class="sxs-lookup"><span data-stu-id="de2e2-774">Clients (Skype for Business Online Only)</span></span> | <span data-ttu-id="de2e2-775">某些较旧的客户端具有已知，记录问题和介质的可靠性。</span><span class="sxs-lookup"><span data-stu-id="de2e2-775">Some older clients have known, documented issues with media reliability.</span></span> <span data-ttu-id="de2e2-776">查看来自多个受影响的用户的调用分析报告或 CQD 筛选特定的建筑物或子网与总调用删除失败 %测量到在中创建自定义的客户端版本表报告。</span><span class="sxs-lookup"><span data-stu-id="de2e2-776">Review the Call Analytics reports from multiple affected users or create a custom Client Version table report in CQD filtered to specific buildings or subnets with Total Call Dropped Failure % measure.</span></span> <span data-ttu-id="de2e2-777">此信息将帮助您了解特定版本的客户端调用特定建筑谷之间是否存在关系。</span><span class="sxs-lookup"><span data-stu-id="de2e2-777">This information will help you understand whether a relationship exists between call drops in that specific building and a specific version of the client.</span></span>                                                                                                                                                              |
| <span data-ttu-id="de2e2-778">设备</span><span class="sxs-lookup"><span data-stu-id="de2e2-778">Devices</span></span>                                  | <span data-ttu-id="de2e2-779">大部分设备故障是由于使用不认证团队或 Skype 的业务的设备。</span><span class="sxs-lookup"><span data-stu-id="de2e2-779">The majority of device failures are due to using devices that aren’t certified for Teams or Skype for Business.</span></span> <span data-ttu-id="de2e2-780">故障通常采用集成的扬声器或麦克风正在使用或已插入的设备上的 3.5 毫米音频插孔的 earbud/麦克风输入组合的形式。</span><span class="sxs-lookup"><span data-stu-id="de2e2-780">Failures usually take the form of the integrated speakers or mics that are being used, or earbud/mic combinations that are plugged into the 3.5 mm audio jack on a device.</span></span> <span data-ttu-id="de2e2-781">微软当前建议时所遇到的任何用户调用坠落 — — 或差通常调用 — — 并且使用集成的设备或驱动程序应该提供[认证的耳机或话筒](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs)。</span><span class="sxs-lookup"><span data-stu-id="de2e2-781">Microsoft’s current recommendation is that any users who are experiencing call drops—or poor calls in general—and are using integrated devices or drivers should be provisioned a [certified headset or speakerphone](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs).</span></span> |
| <span data-ttu-id="de2e2-782">用户行为</span><span class="sxs-lookup"><span data-stu-id="de2e2-782">User Behavior</span></span>                            | <span data-ttu-id="de2e2-783">如果您确定既没有网络，设备或客户端是一个问题，则考虑使用[我的顾问](https://aka.ms/myadvisor)作为准则，制定用户采用策略让用户了解如何最佳联接并退出会议。</span><span class="sxs-lookup"><span data-stu-id="de2e2-783">If you determine that neither network, devices, or clients are the issue, consider engaging [My Advisor](https://aka.ms/myadvisor) for guidance in developing a user adoption strategy to educate users how to best join and exit meetings.</span></span> <span data-ttu-id="de2e2-784">更明智的团队和 Skype 用户将所有参与者在会议中产生更好的用户体验。</span><span class="sxs-lookup"><span data-stu-id="de2e2-784">A smarter Teams and Skype user will produce a better user experience for all participants in the meeting.</span></span> <span data-ttu-id="de2e2-785">使他们的膝上型计算机 （通过在关闭盖子） 睡眠状态而不退出会议的用户将被归为意外的调用放。</span><span class="sxs-lookup"><span data-stu-id="de2e2-785">A user who puts their laptop to sleep (by closing the lid) without exiting the meeting will be classified as an unexpected call drop.</span></span>     |

## <a name="quality-investigations"></a><span data-ttu-id="de2e2-786">质量调查</span><span class="sxs-lookup"><span data-stu-id="de2e2-786">Quality investigations</span></span>

<span data-ttu-id="de2e2-787">下一步要评估整个部署状态的音频质量是研究音频差调用比率 (PCR)，TCP 和使用代理。</span><span class="sxs-lookup"><span data-stu-id="de2e2-787">The next step to assess the state of audio quality across the deployment is to investigate Audio Poor Call Ratio (PCR), TCP, and proxy usage.</span></span> <span data-ttu-id="de2e2-788">请务必记住 CQD 数据没有提供具体的根本原因，但实际上为您提供了可能的问题区域开始补救活动的适当团队的协作会话。</span><span class="sxs-lookup"><span data-stu-id="de2e2-788">It’s important to remember that CQD data doesn’t provide you a specific root cause, but instead provides you with likely problem areas to begin a collaborative conversation with the appropriate teams for remediation activities.</span></span>

> [!NOTE]
> <span data-ttu-id="de2e2-789">本指南中介绍了模板中包含的并不是所有报告。</span><span class="sxs-lookup"><span data-stu-id="de2e2-789">Not all reports included in the templates are covered in this guide.</span></span> <span data-ttu-id="de2e2-790">请向单个报表说明的详细信息，参阅。</span><span class="sxs-lookup"><span data-stu-id="de2e2-790">Please refer to the individual report description for more information.</span></span> 


### <a name="investigate-call-quality"></a><span data-ttu-id="de2e2-791">呼叫质量调查</span><span class="sxs-lookup"><span data-stu-id="de2e2-791">Investigate call quality</span></span>

<span data-ttu-id="de2e2-792">整体的 PCR 百分比主要用来表示组织是否能够满足定义的音频度量目标。</span><span class="sxs-lookup"><span data-stu-id="de2e2-792">The overall PCR percentage is primarily used to indicate whether the organization is meeting defined audio metric targets.</span></span> <span data-ttu-id="de2e2-793">请务必注意，即使内目标的整体百分比，则某些子网或建筑物可能不满足定义的目标，因此需要进一步调查。</span><span class="sxs-lookup"><span data-stu-id="de2e2-793">It’s important to note that even if the overall percentage is within target, some subnets or buildings might not meet the defined targets and therefore need further investigation.</span></span> <span data-ttu-id="de2e2-794">例如，如果组织音频 PCR 百分比中的 3%十二月，满足样本目标、 特定建筑物可能仍存在感觉非常糟糕，这取决于该 3%的分布。</span><span class="sxs-lookup"><span data-stu-id="de2e2-794">For example, if the organizational audio PCR percentage is 3 percent in December, which meets the sample target, specific buildings might still be having poor experiences, depending on the distribution of that 3 percent.</span></span>

#### <a name="overall-organizational-poor-call-percentage"></a><span data-ttu-id="de2e2-795">整体组织较差的呼叫百分比</span><span class="sxs-lookup"><span data-stu-id="de2e2-795">Overall organizational poor call percentage</span></span>

<span data-ttu-id="de2e2-796">若要评估差求助组织的整体百分比使用总体质量图表报表。</span><span class="sxs-lookup"><span data-stu-id="de2e2-796">To assess the overall percentage of poor calls for the organization use the Quality Overall chart report.</span></span>

![屏幕抓图的图的质量较差的呼叫的百分比](media/quality-of-experience-review-guide-image20.png)

<span data-ttu-id="de2e2-798">_图 20 – 音频质量-整体_</span><span class="sxs-lookup"><span data-stu-id="de2e2-798">_Figure 20 – Audio Quality - Overall_</span></span>

##### <a name="investigation"></a><span data-ttu-id="de2e2-799">调查</span><span class="sxs-lookup"><span data-stu-id="de2e2-799">Investigation</span></span>

<span data-ttu-id="de2e2-800">此图表报表显示您的组织使用和 PCR 一段时间。</span><span class="sxs-lookup"><span data-stu-id="de2e2-800">This chart report displays your organization’s usage and PCR over time.</span></span> <span data-ttu-id="de2e2-801">使用此报表，可以回答以下问题：</span><span class="sxs-lookup"><span data-stu-id="de2e2-801">By using this report, you can answer the following questions:</span></span>

1.  <span data-ttu-id="de2e2-802">什么是当月总 PCR？</span><span class="sxs-lookup"><span data-stu-id="de2e2-802">What is the total PCR for the current month?</span></span>

2.  <span data-ttu-id="de2e2-803">下面定义的目标指标是 PCR？</span><span class="sxs-lookup"><span data-stu-id="de2e2-803">Is the PCR below the defined target metric?</span></span>

3.  <span data-ttu-id="de2e2-804">更糟或更好，比前一个月是故障趋势？</span><span class="sxs-lookup"><span data-stu-id="de2e2-804">Is the failure trend worse or better than the previous month?</span></span>

4.  <span data-ttu-id="de2e2-805">故障趋势增加，steady，或减少吗？</span><span class="sxs-lookup"><span data-stu-id="de2e2-805">Is the failure trend increasing, steady, or decreasing?</span></span>

<span data-ttu-id="de2e2-806">不管上面问题的答案需要通过使用子报表来查找任何建筑物或网络可能需要进一步调查，调查时间。</span><span class="sxs-lookup"><span data-stu-id="de2e2-806">Irrespective of the answers to the questions above, take the time to investigate by using the sub-reports to look for any buildings or networks that might need further investigation.</span></span> <span data-ttu-id="de2e2-807">尽管总体 PCR 可能是下面的目标度量，通常为一个或多个建筑物或网络 PCR 高于指标和需要进一步调查。</span><span class="sxs-lookup"><span data-stu-id="de2e2-807">Although the overall PCR might be below the target metric, often the PCR for one or more buildings or networks is above the metric and needs further investigation.</span></span>

#### <a name="audio-quality-overall"></a><span data-ttu-id="de2e2-808">音频质量总体</span><span class="sxs-lookup"><span data-stu-id="de2e2-808">Audio quality overall</span></span>

<span data-ttu-id="de2e2-809">有两个音频质量的模板，一个用于调查会议，另一个用于两方的调用中包含的报表树。</span><span class="sxs-lookup"><span data-stu-id="de2e2-809">There are two report trees included in the templates for audio quality, one for investigating conferencing and the other for two-party calls.</span></span> <span data-ttu-id="de2e2-810">为了质量修正，研究过程是相同的所以我们将重点介绍会议。</span><span class="sxs-lookup"><span data-stu-id="de2e2-810">For the purposes of quality remediation, the investigative process is the same, so we’ll focus here on conferencing.</span></span> <span data-ttu-id="de2e2-811">会议质量的改进将会两方呼叫质量也产生积极影响。</span><span class="sxs-lookup"><span data-stu-id="de2e2-811">Improvements in conference quality will also positively affect two-party call quality.</span></span> <span data-ttu-id="de2e2-812">报告还将包括查看音频质量会议和两方由有线和 Wi-Fi。</span><span class="sxs-lookup"><span data-stu-id="de2e2-812">Reports are also included to view audio quality for conferencing and two-party by wired and Wi-Fi.</span></span>

> [!NOTE]
> <span data-ttu-id="de2e2-813">研究两方差调用是类似于研究会议呼叫。</span><span class="sxs-lookup"><span data-stu-id="de2e2-813">Investigating two-party poor calls is similar to investigating conference calls.</span></span> <span data-ttu-id="de2e2-814">任务是确定建筑物或子网具有最低的质量，以验证是否有差处理的调用另一个构造或子网的模式。</span><span class="sxs-lookup"><span data-stu-id="de2e2-814">The task is to identify buildings or subnets that have the lowest quality to validate whether there’s a pattern of poor calls with another building or subnet.</span></span> 

![音频质量-会议报告呼叫质量面板中的屏幕快照。](media/quality-of-experience-review-guide-image21.png)

<span data-ttu-id="de2e2-816">_图 21-音频质量-会议_</span><span class="sxs-lookup"><span data-stu-id="de2e2-816">_Figure 21 – Audio Quality - Conferencing_</span></span>

##### <a name="investigation"></a><span data-ttu-id="de2e2-817">调查</span><span class="sxs-lookup"><span data-stu-id="de2e2-817">Investigation</span></span>

<span data-ttu-id="de2e2-818">此图表报表显示您组织的会议或两方使用和 PCR 一段时间。</span><span class="sxs-lookup"><span data-stu-id="de2e2-818">This chart report displays your organization’s conferencing or two-party usage and PCR over time.</span></span> <span data-ttu-id="de2e2-819">使用此报表，可以回答以下问题：</span><span class="sxs-lookup"><span data-stu-id="de2e2-819">By using this report, you can answer the following questions:</span></span>

1.  <span data-ttu-id="de2e2-820">什么是当月总 PCR？</span><span class="sxs-lookup"><span data-stu-id="de2e2-820">What is the total PCR for the current month?</span></span>

2.  <span data-ttu-id="de2e2-821">下面定义的目标指标是 PCR？</span><span class="sxs-lookup"><span data-stu-id="de2e2-821">Is the PCR below the defined target metric?</span></span>

3.  <span data-ttu-id="de2e2-822">更糟或更好，比前一个月是 PCR？</span><span class="sxs-lookup"><span data-stu-id="de2e2-822">Is PCR worse or better than the previous month?</span></span>

4.  <span data-ttu-id="de2e2-823">PCR 趋势增加，steady，或减少吗？</span><span class="sxs-lookup"><span data-stu-id="de2e2-823">Is the PCR trend increasing, steady, or decreasing?</span></span>

<span data-ttu-id="de2e2-824">不管上面问题的答案需要通过使用子报表来查找任何建筑物或网络可能需要进行调查，调查时间。</span><span class="sxs-lookup"><span data-stu-id="de2e2-824">Irrespective of the answers to the questions above, take the time to investigate by using the sub-reports to look for any buildings or networks that might need investigation.</span></span> <span data-ttu-id="de2e2-825">尽管总体 PCR 可能是下面的目标度量，通常为一个或多个建筑物或网络 PCR 指标高于和需要修正。</span><span class="sxs-lookup"><span data-stu-id="de2e2-825">Although the overall PCR might be below the target metric, often the PCR for one or more buildings or networks is above the metric and needs remediation.</span></span>

#### <a name="poor-audio-stream-by-building-and-subnet"></a><span data-ttu-id="de2e2-826">通过构建和子网差音频流</span><span class="sxs-lookup"><span data-stu-id="de2e2-826">Poor audio stream by building and subnet</span></span>

<span data-ttu-id="de2e2-827">此表报表可帮助您更多深入的调用被归类为差什么贡献，并有助于隔离托管网络中的热点。</span><span class="sxs-lookup"><span data-stu-id="de2e2-827">This table report gives you additional insight into what contributed to the calls’ being classified as poor and helps to isolate hot spots in the managed network.</span></span>

<span data-ttu-id="de2e2-828">连接详细区分有线和 Wi-Fi 和包括抖动、 数据包丢失和往返时间 (RTT) 测量。</span><span class="sxs-lookup"><span data-stu-id="de2e2-828">The connection detail distinguishes between wired and Wi-Fi and includes jitter, packet loss, and round-trip time (RTT) measurements.</span></span> <span data-ttu-id="de2e2-829">类似的报告还存在于下两方的报告，并用于隔离两方调用托管网络上。</span><span class="sxs-lookup"><span data-stu-id="de2e2-829">A similar report also exists under the two-party reports, and is used to isolate two-party calls on your managed network.</span></span>

> [!NOTE]
> <span data-ttu-id="de2e2-830">一定要调整到当前月份的月年筛选器。</span><span class="sxs-lookup"><span data-stu-id="de2e2-830">Be sure to adjust the Month Year filter to the current month.</span></span> <span data-ttu-id="de2e2-831">选择**编辑**，然后调整**月年**保存新默认的月份。</span><span class="sxs-lookup"><span data-stu-id="de2e2-831">Select **Edit**, and adjust **Month Year** to save the new default month.</span></span> 

> [!TIP]
> <span data-ttu-id="de2e2-832">常见的家庭网络难以会审由于其广泛的使用。</span><span class="sxs-lookup"><span data-stu-id="de2e2-832">Common home networks are difficult to triage due to their widespread use.</span></span> <span data-ttu-id="de2e2-833">单独使用的报表的防火墙 IP 添加到所有网络模板有助于修正使用公共网络的办公室。</span><span class="sxs-lookup"><span data-stu-id="de2e2-833">A separate report that uses the firewall IP has been added to the All Networks template to assist with remediating offices that use common networks.</span></span>

![列出连接类型、 传输类型和 PCR 大于 3%及其组织的构建、 网络和子网每月的质量较差的各种原因的报告。](media/quality-of-experience-review-guide-image22.png)

<span data-ttu-id="de2e2-835">_图 22-通过构建较差的音频流摘要-和子网会议_</span><span class="sxs-lookup"><span data-stu-id="de2e2-835">_Figure 22 - Poor Audio Stream Summary by Building and Subnet - Conferencing_</span></span>

##### <a name="remediation"></a><span data-ttu-id="de2e2-836">补救措施</span><span class="sxs-lookup"><span data-stu-id="de2e2-836">Remediation</span></span>

<span data-ttu-id="de2e2-837">精力在建筑物上的补救或具有音频流，最大卷，因为这会使影响最大化并有助于提高用户的网络体验快速。</span><span class="sxs-lookup"><span data-stu-id="de2e2-837">Focus your remediation efforts on buildings or networks that have the largest volume of audio streams, because this will maximize impact and help to improve the user experience quickly.</span></span> <span data-ttu-id="de2e2-838">使用抖动、 数据包丢失和 RTT 测量来了解什么导致较差的呼叫质量。</span><span class="sxs-lookup"><span data-stu-id="de2e2-838">Use the jitter, packet loss, and RTT measurements to understand what’s contributing to the poor call quality.</span></span> <span data-ttu-id="de2e2-839">很可能有多个问题：</span><span class="sxs-lookup"><span data-stu-id="de2e2-839">It’s possible for there to be more than one problem:</span></span>

-   <span data-ttu-id="de2e2-840">**抖动：**媒体的数据包以不同的速度，从而导致演讲要听机器人到达。</span><span class="sxs-lookup"><span data-stu-id="de2e2-840">**Jitter:** Media packets are arriving at different speeds, which causes a speaker to sound robotic.</span></span>

-   <span data-ttu-id="de2e2-841">**数据包丢失：**媒体数据包将被丢弃，这将创建缺少的单词或音节的效果。</span><span class="sxs-lookup"><span data-stu-id="de2e2-841">**Packet loss:** Media packets are being dropped, which creates the effect of missing words or syllables.</span></span>

-   <span data-ttu-id="de2e2-842">**RTT:**媒体的数据包会需要很长时间才能到达目的地，这将创建一个 walkie-talkie 效果。</span><span class="sxs-lookup"><span data-stu-id="de2e2-842">**RTT:** Media packets are taking a long time to get to their destination, which creates a walkie-talkie effect.</span></span>

<span data-ttu-id="de2e2-843">虽然事实没有单个源解释什么可能会导致较差的呼叫，常见的几种方法可以帮助您处理网络异常。</span><span class="sxs-lookup"><span data-stu-id="de2e2-843">Although no single source of truth accounts for what can cause a poor call, several common methods can help you deal with network anomalies.</span></span>

<span data-ttu-id="de2e2-844">为了帮助您调查质量问题，您可以利用[调用分析](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309)。</span><span class="sxs-lookup"><span data-stu-id="de2e2-844">To assist your investigation into quality issues, you can leverage [Call Analytics](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309).</span></span>
<span data-ttu-id="de2e2-845">与调用的分析，您可以查看特定会议或用户的详细的通话报告。</span><span class="sxs-lookup"><span data-stu-id="de2e2-845">With Call Analytics, you can look at a specific conference or users’ detailed call report.</span></span> <span data-ttu-id="de2e2-846">此报告将包含 PII 数据，并试图弄清失败的原因时很有用。</span><span class="sxs-lookup"><span data-stu-id="de2e2-846">This report will contain PII data and is useful when attempting to discern a reason for failures.</span></span> <span data-ttu-id="de2e2-847">一旦您知道哪个大楼受到影响，跟踪用户，建筑物变得很简单。</span><span class="sxs-lookup"><span data-stu-id="de2e2-847">Once you know which building that is affected, tracking down users in that building should be straightforward.</span></span>

<span data-ttu-id="de2e2-848">别忘了让支持人员知道这些网络所遇到质量问题，所以他们可以快速会审和响应传入的呼叫。</span><span class="sxs-lookup"><span data-stu-id="de2e2-848">Don’t forget to let the helpdesk know that these networks are experiencing quality issues, so they can quickly triage and respond to incoming calls.</span></span>

<span data-ttu-id="de2e2-849">_表 9-高 PCR 的共同贡献_</span><span class="sxs-lookup"><span data-stu-id="de2e2-849">_Table 9 - Common contributors to high PCR_</span></span>

| <span data-ttu-id="de2e2-850">补救措施</span><span class="sxs-lookup"><span data-stu-id="de2e2-850">Remediation</span></span>                              | <span data-ttu-id="de2e2-851">指南</span><span class="sxs-lookup"><span data-stu-id="de2e2-851">Guidance</span></span>       |
|------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="de2e2-852">网络</span><span class="sxs-lookup"><span data-stu-id="de2e2-852">Networks</span></span>                                 | <span data-ttu-id="de2e2-853">使用过度或在下设置网络可以导致媒体质量问题。</span><span class="sxs-lookup"><span data-stu-id="de2e2-853">An overused or under-provisioned network can cause issues with media quality.</span></span> <span data-ttu-id="de2e2-854">与网络小组，以确定是否从用户到互联网出口网络连接点的工作有足够的带宽来支持媒体。</span><span class="sxs-lookup"><span data-stu-id="de2e2-854">Work with the network team to determine whether the network connections from the user to the internet egress point has enough bandwidth to support media.</span></span> <span data-ttu-id="de2e2-855">**执行网络就绪性评估：**网络评估提供了有关预期的带宽使用情况的详细信息，如何对付带宽和网络发生变化，并建议为团队和业务的 Skype 的网络实践。</span><span class="sxs-lookup"><span data-stu-id="de2e2-855">**Perform a network readiness assessment:** A network assessment provides details about expected bandwidth usage, how to cope with bandwidth and network changes, and recommended networking practices for Teams and Skype for Business.</span></span> <span data-ttu-id="de2e2-856">使用前面的表作为源，有建筑物或评估优秀候选的子网的列表。</span><span class="sxs-lookup"><span data-stu-id="de2e2-856">Using the preceding table as your source, you have a list of buildings or subnets that are excellent candidates for an assessment.</span></span><br><ul><li>[<span data-ttu-id="de2e2-857">Microsoft 小组网络就绪性评估</span><span class="sxs-lookup"><span data-stu-id="de2e2-857">Microsoft Teams Network Readiness Assessment</span></span>](https://docs.microsoft.com/MicrosoftTeams/3-envision-evaluate-my-environment#test-the-network)</li><li>[<span data-ttu-id="de2e2-858">Skype 的业务网络就绪性评估</span><span class="sxs-lookup"><span data-stu-id="de2e2-858">Skype for Business Network Readiness Assessment</span></span>](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers/?pageState=NetworkReadiness)</li></ul><br><span data-ttu-id="de2e2-859">**Microsoft 网络评估工具：**使用此工具对网络性能的一个简单的测试来确定如何更好地将网络执行小组或 Skype 的在线业务的呼叫。</span><span class="sxs-lookup"><span data-stu-id="de2e2-859">**Microsoft Network Assessment Tool:** Use this tool for a simple test of network performance to determine how well the network would perform for a Teams or Skype for Business Online call.</span></span> <span data-ttu-id="de2e2-860">此工具可帮助您评估的子网的性能和验证网络免遭 Microsoft 性能[要求](https://aka.ms/performancerequirements)的准备情况。</span><span class="sxs-lookup"><span data-stu-id="de2e2-860">This tool helps you assess the performance of a subnet and validate the readiness of the network against the Microsoft performance [requirements](https://aka.ms/performancerequirements).</span></span><br><ul><li>[<span data-ttu-id="de2e2-861">下载网络评估工具</span><span class="sxs-lookup"><span data-stu-id="de2e2-861">Download the Network Assessment Tool</span></span>](https://www.microsoft.com/download/details.aspx?id=53885) </li></ul>        |
| <span data-ttu-id="de2e2-862">服务质量 (QoS)</span><span class="sxs-lookup"><span data-stu-id="de2e2-862">Quality of Service (QoS)</span></span>                 | <span data-ttu-id="de2e2-863">QoS 是行之有效的方法，可帮助确定优先级数据包在网络，以确保它们到达目的地不变，在时间上。</span><span class="sxs-lookup"><span data-stu-id="de2e2-863">QoS is a proven method to help prioritize packets on a network to ensure they arrive at their destination intact and on time.</span></span> <span data-ttu-id="de2e2-864">考虑在您的组织可以获得最高质量的用户体验，其中带宽限制或约束 QoS 的实施。</span><span class="sxs-lookup"><span data-stu-id="de2e2-864">Consider implementing QoS across your organization to maximize the quality of the user experience where bandwidth is limited or constrained.</span></span> <span data-ttu-id="de2e2-865">QoS 将有助于解决问题通常与高的数据包丢失率、 和 — 程度要轻一些 — — 抖动和往返的时间。</span><span class="sxs-lookup"><span data-stu-id="de2e2-865">QoS will help solve issues typically associated with high levels of packet loss, and—to a lesser degree—jitter and round-trip times.</span></span> <br><ul><li>[<span data-ttu-id="de2e2-866">Microsoft 小组 QoS 指南</span><span class="sxs-lookup"><span data-stu-id="de2e2-866">Microsoft Teams QoS Guidance</span></span>](https://docs.microsoft.com/MicrosoftTeams/qos-in-teams)</li><li>[<span data-ttu-id="de2e2-867">Skype 业务 QoS 指南</span><span class="sxs-lookup"><span data-stu-id="de2e2-867">Skype for Business QoS Guidance</span></span>](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_8)</li></ul>    |
| <span data-ttu-id="de2e2-868">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="de2e2-868">Wi-Fi</span></span>                                    | <span data-ttu-id="de2e2-869">Wi-Fi 可以在通话质量上有很大的影响。</span><span class="sxs-lookup"><span data-stu-id="de2e2-869">Wi-Fi can have a significant impact on call quality.</span></span> <span data-ttu-id="de2e2-870">Wi-Fi 设计通常会考虑到 VoIP 服务的网络要求，而且通常质量较差的根源。</span><span class="sxs-lookup"><span data-stu-id="de2e2-870">Wi-Fi design doesn’t typically take into consideration the network requirements for VoIP services and are often a source of poor quality.</span></span> <span data-ttu-id="de2e2-871">**QoS:**现代无线网络必须支持很多设备。</span><span class="sxs-lookup"><span data-stu-id="de2e2-871">**QoS:** Modern wireless networks must support many devices.</span></span> <span data-ttu-id="de2e2-872">这些设备争夺带宽，并可能导致的 VoIP 服务的质量问题速度和延迟时间至关重要。</span><span class="sxs-lookup"><span data-stu-id="de2e2-872">These devices compete for bandwidth and can lead to quality issues for VoIP services where speed and latency are vital.</span></span> <span data-ttu-id="de2e2-873">有关细节，请参阅无线供应商联系，并考虑在您的无线网络业务和团队媒体优先 Skype 上 QoS 的实施。</span><span class="sxs-lookup"><span data-stu-id="de2e2-873">Consult your wireless vendor for specifics, and consider implementing QoS on your wireless network to prioritize Skype for Business and Teams media.</span></span> <span data-ttu-id="de2e2-874">**AP 密度：**访问点 (Ap) 可能太远或不在理想的位置。</span><span class="sxs-lookup"><span data-stu-id="de2e2-874">**AP density:** Access points (APs) might be too far apart or not in an ideal location.</span></span> <span data-ttu-id="de2e2-875">为了尽量减少潜在的干扰，将额外的 Ap 放在会议室和不受阻墙壁或其他对象的位置。</span><span class="sxs-lookup"><span data-stu-id="de2e2-875">To minimize potential interference, place extra APs in conference rooms and in locations that aren’t obstructed by walls or other objects.</span></span> <span data-ttu-id="de2e2-876">**2.4 g h z 和 5ghz:** 5 GHz 提供较少的背景干扰和更高的速度，并通过 Wi-fi 部署 VoIP 时应优先。</span><span class="sxs-lookup"><span data-stu-id="de2e2-876">**2.4 GHz vs. 5 GHz:** 5 GHz provides less background interference and higher speeds, and should be prioritized when deploying VoIP over Wi-Fi.</span></span> <span data-ttu-id="de2e2-877">但是，5 GHz 不为 2.4 g h z，并且不会穿透墙壁，轻松地。</span><span class="sxs-lookup"><span data-stu-id="de2e2-877">However, 5 GHz isn’t as strong as 2.4 GHz and doesn’t penetrate walls as easily.</span></span> <span data-ttu-id="de2e2-878">查看您的建筑布局，以确定您可以依靠的最佳连接的频率。</span><span class="sxs-lookup"><span data-stu-id="de2e2-878">Review your building layout to determine which frequency you can rely on for the best connection.</span></span> <span data-ttu-id="de2e2-879">**信号强度：**这传统上以 dBm （以分贝计电源比率），衡量无线信号强度。</span><span class="sxs-lookup"><span data-stu-id="de2e2-879">**Signal strength:** Traditionally measured in dBm (power ratio in decibels), this measures the strength of the wireless signal.</span></span> <span data-ttu-id="de2e2-880">设备连接到接入点后，它不想要轻松地松开。</span><span class="sxs-lookup"><span data-stu-id="de2e2-880">After a device is connected to an AP, it doesn’t want to let go easily.</span></span> <span data-ttu-id="de2e2-881">随着设备离开 AP 时，信号强度将到即使另一个，更接近的接入点可导致接触不良引起的点脱落。</span><span class="sxs-lookup"><span data-stu-id="de2e2-881">As the device moves away from the AP, the signal strength falls off to a point that induces a poor connection even though another, closer AP is available.</span></span> <span data-ttu-id="de2e2-882">如果可能，请使用您的接入点供应商，以确保 Ap 被配置为删除设备时信号强度低于可接受的水平。</span><span class="sxs-lookup"><span data-stu-id="de2e2-882">If possible, work with your AP vendor to ensure that the APs are configured to drop a device when signal strength falls below an acceptable level.</span></span> <span data-ttu-id="de2e2-883">这将确保设备未挂起弱的接入点。</span><span class="sxs-lookup"><span data-stu-id="de2e2-883">This will ensure that the device doesn’t hang on to a weak AP.</span></span> <span data-ttu-id="de2e2-884">当您无法方便地添加多个接入点，这是一个不错的解决方案。</span><span class="sxs-lookup"><span data-stu-id="de2e2-884">This is a good solution when you can’t easily add more APs.</span></span> <span data-ttu-id="de2e2-885">**无线驱动程序：**当其他所有方法均失败时，请确保无线驱动程序是最新版本。</span><span class="sxs-lookup"><span data-stu-id="de2e2-885">**Wireless driver:** When all else fails, ensure that wireless drivers are up to date.</span></span> <span data-ttu-id="de2e2-886">这将有助于减轻任何不良的用户体验与过时的驱动程序。</span><span class="sxs-lookup"><span data-stu-id="de2e2-886">This will help mitigate any poor user experience related to an outdated driver.</span></span> |
| <span data-ttu-id="de2e2-887">网络设备</span><span class="sxs-lookup"><span data-stu-id="de2e2-887">Network device</span></span>                           | <span data-ttu-id="de2e2-888">大型组织可能有数以百计的跨网络的设备。</span><span class="sxs-lookup"><span data-stu-id="de2e2-888">Larger organizations might have hundreds of devices spread out across the network.</span></span> <span data-ttu-id="de2e2-889">与您的网络小组，以确保用户从互联网的网络设备的工作是维护和最新的。</span><span class="sxs-lookup"><span data-stu-id="de2e2-889">Work with your network team to ensure the network devices from the user to the internet are maintained and up to date.</span></span>     |
| <span data-ttu-id="de2e2-890">VPN</span><span class="sxs-lookup"><span data-stu-id="de2e2-890">VPN</span></span>                                      | <span data-ttu-id="de2e2-891">它已完备 VPN 的装置不传统上用于处理实时媒体工作负载。</span><span class="sxs-lookup"><span data-stu-id="de2e2-891">It has been well-documented that VPN appliances aren’t traditionally designed to handle real-time media workloads.</span></span> <span data-ttu-id="de2e2-892">某些 VPN 配置禁止使用 UDP （这是首选的音频协议），并且只能依赖 TCP。</span><span class="sxs-lookup"><span data-stu-id="de2e2-892">Some VPN configurations prohibit the use of UDP (which is the preferred protocol for audio) and rely on TCP only.</span></span> <span data-ttu-id="de2e2-893">请考虑实施[拆分隧道的 VPN 解决方案](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_9)可以帮助减少 VPN 作为源的质量太差。</span><span class="sxs-lookup"><span data-stu-id="de2e2-893">Consider implementing a [VPN split-tunnel solution](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_9) to help reduce VPN as a source of poor quality.</span></span>        |
| <span data-ttu-id="de2e2-894">客户端 (Skype 业务仅在线)</span><span class="sxs-lookup"><span data-stu-id="de2e2-894">Clients (Skype for Business Online Only)</span></span> | <span data-ttu-id="de2e2-895">旧客户端已知也会导致问题的介质。</span><span class="sxs-lookup"><span data-stu-id="de2e2-895">Older clients have been known to cause issues with media.</span></span> <span data-ttu-id="de2e2-896">确保客户端正在修补发行六个月内。</span><span class="sxs-lookup"><span data-stu-id="de2e2-896">Ensure that clients are being patched within six months of release.</span></span> <span data-ttu-id="de2e2-897">利用[MyAdvisor](https://aka.ms/myadvisor)为开发一种客户端准备战略的指导和部署[点用](https://technet.microsoft.com/library/jj219427.aspx)。</span><span class="sxs-lookup"><span data-stu-id="de2e2-897">Leverage [MyAdvisor](https://aka.ms/myadvisor) for guidance on developing a client readiness strategy and deploy [Click-to-Run](https://technet.microsoft.com/library/jj219427.aspx).</span></span>      |
| <span data-ttu-id="de2e2-898">设备</span><span class="sxs-lookup"><span data-stu-id="de2e2-898">Devices</span></span>                                  | <span data-ttu-id="de2e2-899">[优化设备](https://partnersolutions.skypeforbusiness.com/solutionscatalog)的使用可以大大改进用户体验。</span><span class="sxs-lookup"><span data-stu-id="de2e2-899">The use of [optimized devices](https://partnersolutions.skypeforbusiness.com/solutionscatalog) can help to significantly improve the user experience.</span></span> <span data-ttu-id="de2e2-900">与所有的光源都相等，优化的设备的设计，最大限度地与团队和业务的 Skype 的用户体验并产生卓越品质。</span><span class="sxs-lookup"><span data-stu-id="de2e2-900">With all things being equal, optimized devices are designed to maximize the user experience with Teams and Skype for Business and produce superior quality.</span></span> <span data-ttu-id="de2e2-901">利用[MyAdvisor](https://aka.ms/myadvisor)有关设备准备工作战略制订的指南。</span><span class="sxs-lookup"><span data-stu-id="de2e2-901">Leverage [MyAdvisor](https://aka.ms/myadvisor) for guidance on developing a device readiness strategy.</span></span>   |


### <a name="investigate-tcp-audio-sessions"></a><span data-ttu-id="de2e2-902">研究 TCP 音频会话</span><span class="sxs-lookup"><span data-stu-id="de2e2-902">Investigate TCP audio sessions</span></span>

<span data-ttu-id="de2e2-903">TCP 是切传输并不主要传输所需的实时媒体。</span><span class="sxs-lookup"><span data-stu-id="de2e2-903">TCP is considered a failback transport and not the primary transport you want for real-time media.</span></span> <span data-ttu-id="de2e2-904">它是一个故障回复传输的原因是的 TCP 状态的性质。</span><span class="sxs-lookup"><span data-stu-id="de2e2-904">The reason it’s a failback transport is due to the stateful nature of TCP.</span></span> <span data-ttu-id="de2e2-905">例如，如果调用了潜在的网络上和媒体数据包被延迟，然后从以前几秒钟的数据包 — — 它不再有用 — — 争夺带宽以获得向接收器，可以使糟糕的情形更糟。</span><span class="sxs-lookup"><span data-stu-id="de2e2-905">For example, if a call is made on a latent network and media packets are delayed, then packets from a few seconds ago—which are no longer useful—compete for bandwidth to get to the receiver, which can make a bad situation worse.</span></span> <span data-ttu-id="de2e2-906">这使音频 healer 拼接和拉伸的音频，导致听见工件，通常在窗体中的抖动。</span><span class="sxs-lookup"><span data-stu-id="de2e2-906">This makes the audio healer stitch and stretch audio, resulting in audible artifacts often in the form of jitter.</span></span>

<span data-ttu-id="de2e2-907">本节中的报告不进行良好和较差的调用之间的区分。</span><span class="sxs-lookup"><span data-stu-id="de2e2-907">The reports in this section don’t make a distinction between good and poor calls.</span></span> <span data-ttu-id="de2e2-908">因为 UDP 是首选，报告查找 TCP 用于音频。</span><span class="sxs-lookup"><span data-stu-id="de2e2-908">Given that UDP is preferred, the reports look for the use of TCP for audio.</span></span> <span data-ttu-id="de2e2-909">这主要是由于不完整的防火墙规则所致。</span><span class="sxs-lookup"><span data-stu-id="de2e2-909">This is primarily caused by incomplete firewall rules.</span></span> <span data-ttu-id="de2e2-910">有关详细信息防火墙规则工作组和 Skype 的在线业务，请参阅[Office 365 的 Url 和 IP 地址范围](https://aka.ms/o365ips)。</span><span class="sxs-lookup"><span data-stu-id="de2e2-910">For more information about firewall rules for Teams and Skype for Business Online, see [Office 365 URLs and IP address ranges](https://aka.ms/o365ips).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="de2e2-911">有效[建立文件](#building-mapping)上载，建议能够迅速区分内部从外部音频流时查看 TCP 使用情况。</span><span class="sxs-lookup"><span data-stu-id="de2e2-911">Having a valid [building file](#building-mapping) uploaded is recommended to be able to quickly distinguish inside from outside audio streams when looking at TCP usage.</span></span> 


#### <a name="audio-streams-with-tcp-usage-overall"></a><span data-ttu-id="de2e2-912">整体使用 TCP 的音频流</span><span class="sxs-lookup"><span data-stu-id="de2e2-912">Audio streams with TCP usage overall</span></span>

<span data-ttu-id="de2e2-913">此报表指明最近 7 个月，整体的 TCP 使用音频，如下所示。</span><span class="sxs-lookup"><span data-stu-id="de2e2-913">This report indicates the overall TCP usage for audio over the last seven months, as shown below.</span></span>

<span data-ttu-id="de2e2-914">本部分中的所有进一步报告将重点放在缩小特定建筑物和 TCP 普遍使用的子网。</span><span class="sxs-lookup"><span data-stu-id="de2e2-914">All further reports in this section will focus on narrowing down specific buildings and subnets where TCP is most commonly used.</span></span> <span data-ttu-id="de2e2-915">进一步的子报表分解通过会议，两方调用 TCP 使用情况。</span><span class="sxs-lookup"><span data-stu-id="de2e2-915">Further sub-reports break down TCP usage by both conferencing and two-party calls.</span></span>

![一个图，显示的 TCP 每月的音频流的数目的屏幕抓图](media/quality-of-experience-review-guide-image23.png)

<span data-ttu-id="de2e2-917">_图 23-TCP 使用音频流_</span><span class="sxs-lookup"><span data-stu-id="de2e2-917">_Figure 23 – Audio Streams with TCP Usage_</span></span>

##### <a name="investigation"></a><span data-ttu-id="de2e2-918">调查</span><span class="sxs-lookup"><span data-stu-id="de2e2-918">Investigation</span></span>

<span data-ttu-id="de2e2-919">此图表报表显示您的组织的总体 TCP 使用。</span><span class="sxs-lookup"><span data-stu-id="de2e2-919">This chart report displays your organization’s overall TCP usage.</span></span> <span data-ttu-id="de2e2-920">使用此报表，可以回答以下问题：</span><span class="sxs-lookup"><span data-stu-id="de2e2-920">By using this report, you can answer the following questions:</span></span>

1.  <span data-ttu-id="de2e2-921">本月是总体积的 TCP 调用什么？</span><span class="sxs-lookup"><span data-stu-id="de2e2-921">What is the total volume of TCP calls for the current month?</span></span>

2.  <span data-ttu-id="de2e2-922">它是严重还是比上个月更好？</span><span class="sxs-lookup"><span data-stu-id="de2e2-922">Is it worse or better than the previous month?</span></span>

3.  <span data-ttu-id="de2e2-923">TCP 使用情况趋势增加，steady，或减少吗？</span><span class="sxs-lookup"><span data-stu-id="de2e2-923">Is the TCP usage trend increasing, steady, or decreasing?</span></span>

<span data-ttu-id="de2e2-924">如果您注意到，越来越多的 TCP 使用趋势，或高于正常每月使用费，花时间来通过使用子报表来查找任何建筑物或可能需要更新的网络调查。</span><span class="sxs-lookup"><span data-stu-id="de2e2-924">If you notice that the TCP usage trend is increasing, or above normal monthly usage, take the time to investigate by using the sub-reports to look for any buildings or networks that might need remediation.</span></span> <span data-ttu-id="de2e2-925">理想情况下，您希望此托管网络上尽可能少基于 TCP 的音频会话。</span><span class="sxs-lookup"><span data-stu-id="de2e2-925">Ideally, you want as few TCP-based audio sessions as possible on the managed network.</span></span>

#### <a name="tcp-vs-udp"></a><span data-ttu-id="de2e2-926">TCP 和 UDP</span><span class="sxs-lookup"><span data-stu-id="de2e2-926">TCP vs. UDP</span></span>

<span data-ttu-id="de2e2-927">此表报表标识量 TCP 和 UDP 使用率报告最新每月会议的音频、 视频和基于视频的共享 (VBSS) 的屏幕上。</span><span class="sxs-lookup"><span data-stu-id="de2e2-927">This table report identifies the volume of TCP versus UDP usage reporting on the latest month for conferences for audio, video, and video-based screen sharing (VBSS).</span></span>

![报告显示与 PCR 进行比较显示量 TCP 和 UDP 会议流，](media/quality-of-experience-review-guide-image24.png)

<span data-ttu-id="de2e2-929">_图 24-TCP 和 UDP 的会议_</span><span class="sxs-lookup"><span data-stu-id="de2e2-929">_Figure 24 – TCP vs. UDP - Conferencing_</span></span>

##### <a name="analysis"></a><span data-ttu-id="de2e2-930">分析</span><span class="sxs-lookup"><span data-stu-id="de2e2-930">Analysis</span></span>

<span data-ttu-id="de2e2-931">虽然您希望 TCP 使用要尽可能低的水平，您可能会看到 TCP 使用，否则为正常的部署中的一个位。</span><span class="sxs-lookup"><span data-stu-id="de2e2-931">Although you want TCP usage to be as low as possible, you might see a bit of TCP usage in an otherwise healthy deployment.</span></span> <span data-ttu-id="de2e2-932">要与 TCP 使用 UDP，除 TCP 通过 UDP 音频流，以确定百分比的音频流。</span><span class="sxs-lookup"><span data-stu-id="de2e2-932">To compare UDP to TCP usage, divide TCP audio streams by UDP audio streams to determine a percentage.</span></span> <span data-ttu-id="de2e2-933">超过 1%的值需要进行进一步调查。</span><span class="sxs-lookup"><span data-stu-id="de2e2-933">A value over 1 percent needs to be further investigated.</span></span>

<span data-ttu-id="de2e2-934">在上面的示例中，我们采用 1,806 除以 10,481 UDP 流来达到 17.2%的值的 TCP 流。</span><span class="sxs-lookup"><span data-stu-id="de2e2-934">In the example above, we take 1,806 TCP streams divided by 10,481 UDP streams to arrive at a value of 17.2 percent.</span></span> <span data-ttu-id="de2e2-935">此值远远高于 1%，并且告诉我们，我们需要继续我们的调查，以确定正在发生的 TCP 使用情况。</span><span class="sxs-lookup"><span data-stu-id="de2e2-935">This value is well above 1 percent and tells us that we need to continue our investigation to determine where the TCP usage is occurring.</span></span>

<span data-ttu-id="de2e2-936">报告中还包括为音频差百分比。</span><span class="sxs-lookup"><span data-stu-id="de2e2-936">Also included in the report is Audio Poor Percentage.</span></span> <span data-ttu-id="de2e2-937">这让您可以查看到的 UDP 和 TCP 有助于直观显示 TCP 如何影响 overcall 呼叫质量之间的呼叫质量的比较。</span><span class="sxs-lookup"><span data-stu-id="de2e2-937">This gives you a view into the comparison of call quality between UDP and TCP to help visualize how TCP is affecting overcall call quality.</span></span>

<span data-ttu-id="de2e2-938">那么现在，您已经确定没有在您的组织基于 TCP 的音频高使用率，怎么办下一步？</span><span class="sxs-lookup"><span data-stu-id="de2e2-938">So now that you’ve determined that there is a high usage of TCP-based audio in your organization, what do you do next?</span></span> <span data-ttu-id="de2e2-939">请转到**通过构建和子网的 TCP 流**报告细分通过构建和子网的 TCP 使用情况。</span><span class="sxs-lookup"><span data-stu-id="de2e2-939">Go to the **TCP Streams by Building and Subnet** reports to break down the TCP usage by building and subnets.</span></span>

#### <a name="tcp-streams-by-building-and-subnet"></a><span data-ttu-id="de2e2-940">通过构建和子网的 TCP 流</span><span class="sxs-lookup"><span data-stu-id="de2e2-940">TCP streams by building and subnet</span></span>

<span data-ttu-id="de2e2-941">在提供的 CQD 模板，转到 TCP 流通过构建和子网表报表使用托管或所有网络模板。</span><span class="sxs-lookup"><span data-stu-id="de2e2-941">In the provided CQD templates, go to the TCP Streams by Building and Subnet table reports by using either the managed or All Networks template.</span></span> <span data-ttu-id="de2e2-942">有三种报告包含在该模板，一个用于调查会议，有和没有 Microsoft 中继信息，以及一个用于调查两方的调用。</span><span class="sxs-lookup"><span data-stu-id="de2e2-942">There are three reports included in the template, one for investigating conferencing, with and without Microsoft relay information, and one for investigating two-party calls.</span></span> <span data-ttu-id="de2e2-943">目的调查 TCP 使用，过程是相同的所以我们将重点放在会议只讨论。</span><span class="sxs-lookup"><span data-stu-id="de2e2-943">For the purpose of investigating TCP usage, the process is the same, so we’ll focus the discussion here on conferencing only.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="de2e2-944">有效[建立文件](#building-mapping)上载，建议能够迅速区分内部从外部音频流时查看 TCP 使用情况。</span><span class="sxs-lookup"><span data-stu-id="de2e2-944">Having a valid [building file](#building-mapping) uploaded is recommended to be able to quickly distinguish inside from outside audio streams when looking at TCP usage.</span></span> 

> [!NOTE]
> <span data-ttu-id="de2e2-945">一定要调整到当前月份的月年筛选器。</span><span class="sxs-lookup"><span data-stu-id="de2e2-945">Be sure to adjust the Month Year filter to the current month.</span></span> <span data-ttu-id="de2e2-946">选择**编辑**，然后调整**月年**保存新默认的月份。</span><span class="sxs-lookup"><span data-stu-id="de2e2-946">Select **Edit**, and adjust **Month Year** to save the new default month.</span></span>                                  |

![列出了 TCP 流，通过构建、 网络和子网，每月组织的报告。](media/quality-of-experience-review-guide-image25.png)

<span data-ttu-id="de2e2-948">_图 25--通过构建 TCP 流的和子网会议_</span><span class="sxs-lookup"><span data-stu-id="de2e2-948">_Figure 25 – TCP Streams by Building and Subnet - Conferencing_</span></span>

##### <a name="remediation"></a><span data-ttu-id="de2e2-949">补救措施</span><span class="sxs-lookup"><span data-stu-id="de2e2-949">Remediation</span></span>

<span data-ttu-id="de2e2-950">此报表标识特定的建筑物，导致 TCP 使用该卷的子网。</span><span class="sxs-lookup"><span data-stu-id="de2e2-950">This report identifies specific buildings and subnets that are contributing to the volume of TCP usage.</span></span> <span data-ttu-id="de2e2-951">其他报告也包括确定在调用中用于帮助找出缺失的防火墙规则的 Microsoft 中继 IP。</span><span class="sxs-lookup"><span data-stu-id="de2e2-951">An additional report is also included to identify the Microsoft relay IP that was used in the call to help isolate missing firewall rules.</span></span> <span data-ttu-id="de2e2-952">精力补救措施有了最大量的音频流，以最大限度地影响这些建筑物上。</span><span class="sxs-lookup"><span data-stu-id="de2e2-952">Focus your remediation efforts on those buildings that have the highest volume of audio streams to maximize impact.</span></span>

<span data-ttu-id="de2e2-953">TCP 使用的最常见原因缺少在防火墙或代理服务器的例外规则。</span><span class="sxs-lookup"><span data-stu-id="de2e2-953">The most common cause of TCP usage is missing exception rules in firewalls or proxies.</span></span> <span data-ttu-id="de2e2-954">我们将谈论代理在下一节中，因此现在精力放在防火墙。</span><span class="sxs-lookup"><span data-stu-id="de2e2-954">We’ll be talking about proxies in the next section, so for now focus your efforts on the firewalls.</span></span> <span data-ttu-id="de2e2-955">通过使用建筑物或子网提供，您可以确定哪些防火墙需要更新。</span><span class="sxs-lookup"><span data-stu-id="de2e2-955">By using the building or subnet provided, you can determine which firewall needs to be updated.</span></span>

<span data-ttu-id="de2e2-956">_表 10-修正 \* 通过构建和子网的 TCP 流指南_</span><span class="sxs-lookup"><span data-stu-id="de2e2-956">_Table 10 - Remediation\* guidance for TCP streams by building and subnet_</span></span>

| <span data-ttu-id="de2e2-957">补救措施</span><span class="sxs-lookup"><span data-stu-id="de2e2-957">Remediation</span></span>        | <span data-ttu-id="de2e2-958">指南</span><span class="sxs-lookup"><span data-stu-id="de2e2-958">Guidance</span></span>     |
|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="de2e2-959">配置防火墙</span><span class="sxs-lookup"><span data-stu-id="de2e2-959">Configure firewall</span></span> | <span data-ttu-id="de2e2-960">请验证[Office 365 IP 端口和地址](https://aka.ms/o365ips)将不会在您的防火墙。</span><span class="sxs-lookup"><span data-stu-id="de2e2-960">Verify [Office 365 IP ports and addresses](https://aka.ms/o365ips) are excluded from your firewall.</span></span> <span data-ttu-id="de2e2-961">尽管有许多 IP 地址和端口，需要打开，与媒体相关的 TCP 问题，为集中精力下初始更正： 验证下列[媒体子网](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams)位于防火墙规则。</span><span class="sxs-lookup"><span data-stu-id="de2e2-961">Though there are many IP addresses and ports that need to be opened, for media-related TCP issues, focus your initial efforts on the following: Verify the following [media subnets](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams) are in your firewall rules.</span></span> <span data-ttu-id="de2e2-962">指特定媒体网信息显示的表中第 4 行。</span><span class="sxs-lookup"><span data-stu-id="de2e2-962">Refer to Row 4 in the table shown for specific media subnet information.</span></span> <span data-ttu-id="de2e2-963">[UDP 端口 3478-3481](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Updated-IP-ranges-and-ports-for-Skype-for-Business-Online/ba-p/47470)： 首选的媒体端口并必须打开这些端口，否则客户端将无法返回到 TCP 端口 443。</span><span class="sxs-lookup"><span data-stu-id="de2e2-963">[UDP ports 3478–3481](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Updated-IP-ranges-and-ports-for-Skype-for-Business-Online/ba-p/47470): These ports are the preferred media ports and must be opened, otherwise the client will fail back to TCP port 443.</span></span> |
| <span data-ttu-id="de2e2-964">验证</span><span class="sxs-lookup"><span data-stu-id="de2e2-964">Verify</span></span>             | <span data-ttu-id="de2e2-965">使用[Microsoft 网络评估工具](https://www.microsoft.com/download/details.aspx?id=53885)来检查特定 Office 365 IP 地址和端口与在受影响的建筑物或子网的连接问题。</span><span class="sxs-lookup"><span data-stu-id="de2e2-965">Use the [Microsoft Network Assessment Tool](https://www.microsoft.com/download/details.aspx?id=53885) to check for connectivity issues to specific Office 365 IP addresses and ports from the affected building or subnet.</span></span>    |

### <a name="investigate-http-proxy-usage"></a><span data-ttu-id="de2e2-966">调查使用 HTTP 代理</span><span class="sxs-lookup"><span data-stu-id="de2e2-966">Investigate HTTP proxy usage</span></span>

<span data-ttu-id="de2e2-967">HTTP 代理服务器没有建立媒体会话，原因众多的首选的路径。</span><span class="sxs-lookup"><span data-stu-id="de2e2-967">HTTP proxies aren’t the preferred path for establishing media sessions, for a multitude of reasons.</span></span> <span data-ttu-id="de2e2-968">许多包含深度数据包检查功能，可以防止连接到服务的完成，并引入过程中断。</span><span class="sxs-lookup"><span data-stu-id="de2e2-968">Many contain deep packet inspection features that can prevent connections to the service from being completed and introduce disruptions.</span></span> <span data-ttu-id="de2e2-969">另外，代理服务器可能会强制 TCP 不应任由 UDP，最佳音频质量的建议。</span><span class="sxs-lookup"><span data-stu-id="de2e2-969">Additionally, proxies might force TCP as opposed to allowing UDP, which is recommended for optimal audio quality.</span></span>

<span data-ttu-id="de2e2-970">它始终是 Microsoft 的建议来配置客户端直接连接到团队和 Skype 业务服务。</span><span class="sxs-lookup"><span data-stu-id="de2e2-970">It is always Microsoft’s recommendation to configure the client to directly connect to Teams and Skype for Business services.</span></span> <span data-ttu-id="de2e2-971">这是基于媒体的通信尤为重要。</span><span class="sxs-lookup"><span data-stu-id="de2e2-971">This is especially important for media-based traffic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="de2e2-972">无有效[构建文件](#building-mapping)上载便于正确区分内部从外部音频流分析使用代理时。</span><span class="sxs-lookup"><span data-stu-id="de2e2-972">Having a valid [building file](#building-mapping) uploaded makes it easy to properly distinguish inside from outside audio streams when analyzing proxy usage.</span></span> 


#### <a name="audio-streams-with-http-proxy-usage-overall"></a><span data-ttu-id="de2e2-973">音频流与整体使用 HTTP 代理</span><span class="sxs-lookup"><span data-stu-id="de2e2-973">Audio streams with HTTP proxy usage overall</span></span>

<span data-ttu-id="de2e2-974">此报告简洁描述随着时间每月温的代理使用。</span><span class="sxs-lookup"><span data-stu-id="de2e2-974">This report outlines the proxy usage over time on a monthly scale.</span></span> <span data-ttu-id="de2e2-975">HTTP 代理流报表模板的此部分中非常相似的 TCP 报告。</span><span class="sxs-lookup"><span data-stu-id="de2e2-975">The HTTP proxy stream report in this section of the template is much like the TCP reports.</span></span> <span data-ttu-id="de2e2-976">它看起来不调用都是不好或很好，但是否通过 HTTP 连接调用。</span><span class="sxs-lookup"><span data-stu-id="de2e2-976">It doesn’t look at whether calls are poor or good, but whether the call is connected over HTTP.</span></span>

![音频流与 HTTP 代理服务器使用情况报告呼叫质量面板中的屏幕快照。](media/quality-of-experience-review-guide-image26.png)

<span data-ttu-id="de2e2-978">_图 26 – 使用 HTTP 代理服务器的音频流_</span><span class="sxs-lookup"><span data-stu-id="de2e2-978">_Figure 26 – Audio Streams with HTTP Proxy Usage_</span></span>

##### <a name="analysis"></a><span data-ttu-id="de2e2-979">分析</span><span class="sxs-lookup"><span data-stu-id="de2e2-979">Analysis</span></span>

<span data-ttu-id="de2e2-980">如果您看到有大量的 HTTP 使用，请咨询网络团队以确保正确的排除条款均已到位，以便客户端被直接路由到团队或 Skype 业务联机媒体子网。</span><span class="sxs-lookup"><span data-stu-id="de2e2-980">If you see a high volume of HTTP usage, consult your networking team to ensure the proper exclusions are in place so that clients are directly routing to Teams or Skype for Business Online media subnets.</span></span> <span data-ttu-id="de2e2-981">理想情况下，应在此处显示没有 HTTP 用法。</span><span class="sxs-lookup"><span data-stu-id="de2e2-981">Ideally, there should be no HTTP usage displayed here.</span></span>

<span data-ttu-id="de2e2-982">如果您的组织中只能有一个 internet 代理，验证正确[Office 365 Url 和 IP 地址范围内排除](https://aka.ms/o365ips)。</span><span class="sxs-lookup"><span data-stu-id="de2e2-982">If you have only one internet proxy in your organization, verify the proper [Office 365 URLs and IP address range exclusions](https://aka.ms/o365ips).</span></span> <span data-ttu-id="de2e2-983">如果多个 internet 代理配置在您的组织中，利用 HTTP 子报告找出哪些建筑物或子网会受到影响。</span><span class="sxs-lookup"><span data-stu-id="de2e2-983">If more than one internet proxy is configured in your organization, leverage the HTTP sub-report to isolate which building or subnet is affected.</span></span>

<span data-ttu-id="de2e2-984">Skype 业务的企业，不能绕过代理服务器，确保 Skype 业务客户机被配置为登录正确当它位于代理服务器的后面文章[中所述应使用代理服务器登录而不是试图直接连接](https://support.microsoft.com/help/3207112/skype-for-business-should-use-proxy-server-to-sign-in-instead-of-tryin)。</span><span class="sxs-lookup"><span data-stu-id="de2e2-984">For organizations that can’t bypass the proxy, ensure that the Skype for Business client is configured to sign in properly when it’s located behind a proxy as outlined in the article [Skype for Business should use proxy server to sign in instead of trying direct connection](https://support.microsoft.com/help/3207112/skype-for-business-should-use-proxy-server-to-sign-in-instead-of-tryin).</span></span>

#### <a name="http-proxy-streams-by-building-and-subnet"></a><span data-ttu-id="de2e2-985">通过构建和子网的 HTTP 代理服务器流</span><span class="sxs-lookup"><span data-stu-id="de2e2-985">HTTP proxy streams by building and subnet</span></span>

<span data-ttu-id="de2e2-986">此报表标识特定的建筑物，并导致 HTTP 使用的子网。</span><span class="sxs-lookup"><span data-stu-id="de2e2-986">This report identifies specific buildings and subnets that are contributing to HTTP usage.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="de2e2-987">无有效[构建文件](#building-mapping)上载便于正确区分内部从外部音频流分析使用代理时。</span><span class="sxs-lookup"><span data-stu-id="de2e2-987">Having a valid [building file](#building-mapping) uploaded makes it easy to properly distinguish inside from outside audio streams when analyzing proxy usage.</span></span>

> [!NOTE]
> <span data-ttu-id="de2e2-988">一定要调整到当前月份的月年筛选器。</span><span class="sxs-lookup"><span data-stu-id="de2e2-988">Be sure to adjust the Month Year filter to the current month.</span></span> <span data-ttu-id="de2e2-989">选择**编辑**，然后调整**月年**保存新默认的月份。</span><span class="sxs-lookup"><span data-stu-id="de2e2-989">Select **Edit**, and adjust **Month Year** to save the new default month.</span></span>                        |

![通过构建和子网呼叫质量仪表板中的报表使用 HTTP 代理的屏幕快照。](media/quality-of-experience-review-guide-image27.png)

<span data-ttu-id="de2e2-991">_图 27--通过构建的 HTTP 代理服务器使用率和子网_</span><span class="sxs-lookup"><span data-stu-id="de2e2-991">_Figure 27 – HTTP Proxy Usage by Building and Subnet_</span></span>

##### <a name="remediation"></a><span data-ttu-id="de2e2-992">补救措施</span><span class="sxs-lookup"><span data-stu-id="de2e2-992">Remediation</span></span>

<span data-ttu-id="de2e2-993">精力修正在任何建筑物或已经使用 HTTP 代理的子网。</span><span class="sxs-lookup"><span data-stu-id="de2e2-993">Focus your remediation efforts on any buildings or subnets that have HTTP proxy usage.</span></span> <span data-ttu-id="de2e2-994">HTTP 使用的最常见原因缺少在代理服务器的例外规则。</span><span class="sxs-lookup"><span data-stu-id="de2e2-994">The most common cause of HTTP usage is missing exception rules in proxies.</span></span> <span data-ttu-id="de2e2-995">通过使用建筑物或子网提供，您可以确定哪些代理需要更新。</span><span class="sxs-lookup"><span data-stu-id="de2e2-995">By using the building or subnet provided, you can determine which proxy needs to be updated.</span></span>

<span data-ttu-id="de2e2-996">确认所需的[Office 365 Fqdn](https://aka.ms/o365ips)排除从您的代理服务器。</span><span class="sxs-lookup"><span data-stu-id="de2e2-996">Verify that the required [Office 365 FQDNs](https://aka.ms/o365ips) are excluded from your proxy.</span></span>

## <a name="endpoint-investigations"></a><span data-ttu-id="de2e2-997">终结点调查</span><span class="sxs-lookup"><span data-stu-id="de2e2-997">Endpoint investigations</span></span>

<span data-ttu-id="de2e2-998">本部分的重点报告业务特定的客户端版本的 Skype 和使用经过认证的设备的任务。</span><span class="sxs-lookup"><span data-stu-id="de2e2-998">This section is focused on the tasks for reporting on Skype for Business–specific client versions and the use of certified devices.</span></span>

> [!NOTE]
> <span data-ttu-id="de2e2-999">本指南中介绍了模板中包含的并不是所有报告。</span><span class="sxs-lookup"><span data-stu-id="de2e2-999">Not all reports included in the templates are covered in this guide.</span></span> <span data-ttu-id="de2e2-1000">请向单个报表说明的详细信息，参阅。</span><span class="sxs-lookup"><span data-stu-id="de2e2-1000">Please refer to the individual report description for more information.</span></span> 


### <a name="determine-client-versions"></a><span data-ttu-id="de2e2-1001">确定客户端版本</span><span class="sxs-lookup"><span data-stu-id="de2e2-1001">Determine client versions</span></span>

<span data-ttu-id="de2e2-1002">在这一领域报告的重点是确定 Skype 业务中使用的客户端版本和它们在环境中的相对音量。</span><span class="sxs-lookup"><span data-stu-id="de2e2-1002">The report in this space focuses on identifying Skype for Business client versions in use and their relative volume in the environment.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="de2e2-1003">目前，分布式团队客户端和自动更新到 Azure 内容传递网络 (CDN) 而且将保留最新的服务。</span><span class="sxs-lookup"><span data-stu-id="de2e2-1003">Currently, Teams clients are distributed and updated automatically through the Azure Content Delivery Network (CDN) and will be kept up to date by the service.</span></span> <span data-ttu-id="de2e2-1004">客户端准备工作和调查活动并不适用于小组。</span><span class="sxs-lookup"><span data-stu-id="de2e2-1004">Client readiness and investigative activities aren’t applicable to Teams.</span></span>

<span data-ttu-id="de2e2-1005">可以通过以下链接找到 Skype 业务 2015年和 2016年的版本号：</span><span class="sxs-lookup"><span data-stu-id="de2e2-1005">Version numbers for Skype for Business 2015 and 2016 can be found via the links below:</span></span>

-   [<span data-ttu-id="de2e2-1006">Office 365 客户机更新通道版本</span><span class="sxs-lookup"><span data-stu-id="de2e2-1006">Office 365 client update channel releases</span></span>](https://technet.microsoft.com/office/mt465751?f=255&MSPPError=-2147217396)

-   [<span data-ttu-id="de2e2-1007">单击要运行 office 365 版本号和内部版本号</span><span class="sxs-lookup"><span data-stu-id="de2e2-1007">Office 365 version and build numbers for Click to run</span></span>](https://support.office.com/article/Version-and-build-numbers-of-update-channel-releases-ae942449-1fca-4484-898b-a933ea23def7)

-   [<span data-ttu-id="de2e2-1008">为业务 Skype 下载和更新</span><span class="sxs-lookup"><span data-stu-id="de2e2-1008">Skype for Business downloads and updates</span></span>](https://technet.microsoft.com/office/dn788954.aspx)

> [!NOTE] 
> <span data-ttu-id="de2e2-1009">一定要调整到当前月份的月年筛选器。</span><span class="sxs-lookup"><span data-stu-id="de2e2-1009">Be sure to adjust the Month Year filter to the current month.</span></span> <span data-ttu-id="de2e2-1010">选择**编辑**，然后调整**月年**保存新默认的月份。</span><span class="sxs-lookup"><span data-stu-id="de2e2-1010">Select **Edit**, and adjust **Month Year** to save the new default month.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="de2e2-1011">客户端报告需要排除联盟参与者的数据。</span><span class="sxs-lookup"><span data-stu-id="de2e2-1011">Client reports require you to exclude federated participant data.</span></span> <span data-ttu-id="de2e2-1012">若要排除联盟参与者的数据，必须对于**第二个租户 ID**设置为您的组织的[租户 ID](#tenant-id)添加查询筛选器。</span><span class="sxs-lookup"><span data-stu-id="de2e2-1012">To exclude federated participant data, you must add a query filter for **Second Tenant ID** set to your organization’s [tenant ID](#tenant-id).</span></span> |

![客户端和设备报告呼叫质量面板中的屏幕快照。](media/quality-of-experience-review-guide-image28.png)

<span data-ttu-id="de2e2-1014">_图 28-客户端版本报告_</span><span class="sxs-lookup"><span data-stu-id="de2e2-1014">_Figure 28 - Client version report_</span></span>

#### <a name="remediation"></a><span data-ttu-id="de2e2-1015">补救措施</span><span class="sxs-lookup"><span data-stu-id="de2e2-1015">Remediation</span></span>

<span data-ttu-id="de2e2-1016">推动高质量用户体验的一个重要部分确保托管客户端运行最新版本的 Skype 的业务。</span><span class="sxs-lookup"><span data-stu-id="de2e2-1016">A critical part of driving high-quality user experiences is ensuring that managed clients are running up-to-date versions of Skype for Business.</span></span> <span data-ttu-id="de2e2-1017">这提供了以下几个好处，其中包括：</span><span class="sxs-lookup"><span data-stu-id="de2e2-1017">This provides several benefits, among them:</span></span>

-   <span data-ttu-id="de2e2-1018">它是易于管理，而不是许多版本的几个版本。</span><span class="sxs-lookup"><span data-stu-id="de2e2-1018">It’s easier to manage a few versions versus many versions.</span></span>

-   <span data-ttu-id="de2e2-1019">它提供了一定级别的体验的一致性。</span><span class="sxs-lookup"><span data-stu-id="de2e2-1019">It provides a level of consistency of experience.</span></span>

-   <span data-ttu-id="de2e2-1020">它更容易进行故障诊断呼叫质量和易用性问题。</span><span class="sxs-lookup"><span data-stu-id="de2e2-1020">It makes it easier to troubleshoot problems with call quality and usability.</span></span>

-   <span data-ttu-id="de2e2-1021">Microsoft 不跨产品不断做常规的改进和优化。</span><span class="sxs-lookup"><span data-stu-id="de2e2-1021">Microsoft continually makes general improvements and optimizations across the product.</span></span> <span data-ttu-id="de2e2-1022">确保用户收到这些更新可以降低其风险运行到尚未解决的问题。</span><span class="sxs-lookup"><span data-stu-id="de2e2-1022">Ensuring that users receive these updates reduces their risk of running into a problem that has already been solved.</span></span>

<span data-ttu-id="de2e2-1023">限制客户端版本都小于六个月部署将改善整体用户体验并提高可管理性与在相同的环境中有大量的不同版本的客户端。</span><span class="sxs-lookup"><span data-stu-id="de2e2-1023">Limiting your deployment to client versions that are less than six months old will improve the overall user experience and improve manageability compared to having large numbers of different versions of the client in the same environment.</span></span>

<span data-ttu-id="de2e2-1024">如果使用的只有办公室单击即点即用，自动将是六个月内。</span><span class="sxs-lookup"><span data-stu-id="de2e2-1024">If you’re using only Office Click-to-Run, you’ll automatically be within the six-month window.</span></span> <span data-ttu-id="de2e2-1025">不不需要任何进一步的操作。</span><span class="sxs-lookup"><span data-stu-id="de2e2-1025">No further action is required.</span></span>

<span data-ttu-id="de2e2-1026">如果，像大多数组织中，您必须单击以运行和安装程序的程序包 (MSI) 的混合，您可以使用报表以验证 MSI 客户端会定期更新。</span><span class="sxs-lookup"><span data-stu-id="de2e2-1026">If, like most organizations, you have a mix of Click-to-Run and installer packages (MSI), you can use the report to verify that the MSI clients are being updated regularly.</span></span> <span data-ttu-id="de2e2-1027">注意力集中在这些客户端，此卷将高于平均值。</span><span class="sxs-lookup"><span data-stu-id="de2e2-1027">Focus your efforts on those clients where the volume is above average.</span></span> <span data-ttu-id="de2e2-1028">如果您发现客户端被落在后面，与负责管理 Office 更新团队合作和确保他们所批准并定期部署客户端修补程序。</span><span class="sxs-lookup"><span data-stu-id="de2e2-1028">If you notice clients are falling behind, work with the team responsible for managing Office updates and ensure that they’re approving and deploying client patches regularly.</span></span>

### <a name="devices-investigations"></a><span data-ttu-id="de2e2-1029">设备调查</span><span class="sxs-lookup"><span data-stu-id="de2e2-1029">Devices investigations</span></span>

<span data-ttu-id="de2e2-1030">若要使使用的下列设备报告，它的最大努力理解这一概念的平均意见成绩 (MOS)。</span><span class="sxs-lookup"><span data-stu-id="de2e2-1030">To make use of the following device report, it’s best to understand the concept of the mean opinion score (MOS).</span></span> <span data-ttu-id="de2e2-1031">MOS 是黄金标准量化指标，以衡量感觉的音频质量。</span><span class="sxs-lookup"><span data-stu-id="de2e2-1031">MOS is the gold-standard measurement to gauge the perceived audio quality.</span></span> <span data-ttu-id="de2e2-1032">它表示为从 0 到 5 的整数分级。</span><span class="sxs-lookup"><span data-stu-id="de2e2-1032">It’s represented as an integer rating from 0 to 5.</span></span>

<span data-ttu-id="de2e2-1033">所有的语音质量的措施的基础是语音的一个人如何感觉质量。</span><span class="sxs-lookup"><span data-stu-id="de2e2-1033">The basis of all measures of voice quality is how a person perceives the quality of speech.</span></span> <span data-ttu-id="de2e2-1034">因为它人类感知的影响，它是本质上具有主观性。</span><span class="sxs-lookup"><span data-stu-id="de2e2-1034">Because it’s affected by human perception, it’s inherently subjective.</span></span> <span data-ttu-id="de2e2-1035">有几种不同的方法进行主观测试。</span><span class="sxs-lookup"><span data-stu-id="de2e2-1035">There are several different methodologies for subjective testing.</span></span>
<span data-ttu-id="de2e2-1036">大多数的语音质量度量基于绝对分类 (ACR) 评级。</span><span class="sxs-lookup"><span data-stu-id="de2e2-1036">Most voice quality measures are based on an absolute categorization rating (ACR) scale.</span></span>

<span data-ttu-id="de2e2-1037">在 ACR 主观测试中，人数统计方面的重大评级及其质量的经验范围为 1 （坏） 到 5 （极好）。</span><span class="sxs-lookup"><span data-stu-id="de2e2-1037">In an ACR subjective test, a statistically significant number of people rate their quality of experience on a scale of 1 (bad) to 5 (excellent).</span></span> <span data-ttu-id="de2e2-1038">分数的平均值是 MOS。</span><span class="sxs-lookup"><span data-stu-id="de2e2-1038">The average of the scores is the MOS.</span></span> <span data-ttu-id="de2e2-1039">结果 MOS 取决于经验至组和类型的体验被评定为公开的范围。</span><span class="sxs-lookup"><span data-stu-id="de2e2-1039">The resulting MOS depends on the range of experiences that were exposed to the group and to the type of experience being rated.</span></span>

<span data-ttu-id="de2e2-1040">因为它是不实际执行实时通信系统的语音质量的主观测试，团队和业务的 Skype 使用高级的算法来客观地预测主观测试的结果生成 MOS 的值。</span><span class="sxs-lookup"><span data-stu-id="de2e2-1040">Because it’s impractical to conduct subjective tests of voice quality for a live communication system, Teams and Skype for Business generate MOS values by using advanced algorithms to objectively predict the results of a subjective test.</span></span>

<span data-ttu-id="de2e2-1041">可用组 MOS 以及相关衡量标准提供视图到传递给用户体验的质量。</span><span class="sxs-lookup"><span data-stu-id="de2e2-1041">The available set of MOS and associated metrics provide a view into the quality of the experience being delivered to the users.</span></span>

<span data-ttu-id="de2e2-1042">通过提供与设备认证团队和业务的 Skype 的用户，您可以减少遇到由于设备本身 （这是更有可能，例如，对于便携式计算机的内置扬声器和麦克风） 的负面经验的可能性。</span><span class="sxs-lookup"><span data-stu-id="de2e2-1042">By supplying users with devices certified for Teams and Skype for Business, you reduce the likelihood of encountering negative experiences due to the device itself (which is more likely, for example, with built-in laptop speakers and microphones).</span></span> <span data-ttu-id="de2e2-1043">有关详细信息，请参阅[电话和 Skype 的业务的设备](https://technet.microsoft.com/office/dn947482)。</span><span class="sxs-lookup"><span data-stu-id="de2e2-1043">For more information, see [Phones and devices for Skype for Business](https://technet.microsoft.com/office/dn947482).</span></span>

#### <a name="organizational-usage-of-capture-devices-microphones-by-volume"></a><span data-ttu-id="de2e2-1044">组织使用的卷的捕获设备 （麦克风）</span><span class="sxs-lookup"><span data-stu-id="de2e2-1044">Organizational usage of capture devices (microphones) by volume</span></span>

<span data-ttu-id="de2e2-1045">此报告用于评估麦克风使用卷和 MOS 得分，并在客户端和设备*.*下的相应模板中找</span><span class="sxs-lookup"><span data-stu-id="de2e2-1045">This report is used to assess microphone usage by volume and MOS score, and can be found in the accompanying templates under Clients & Devices*.*</span></span>

> [!IMPORTANT]
> <span data-ttu-id="de2e2-1046">设备报告需要排除联盟参与者的数据。</span><span class="sxs-lookup"><span data-stu-id="de2e2-1046">Device reports require you to exclude federated participant data.</span></span> <span data-ttu-id="de2e2-1047">若要排除联盟参与者的数据，必须对于**第二个租户 ID**设置为您的组织的[租户 ID](#tenant-id)添加查询筛选器。</span><span class="sxs-lookup"><span data-stu-id="de2e2-1047">To exclude federated participant data, you must add a query filter for **Second Tenant ID** set to your organization’s [tenant ID](#tenant-id).</span></span> 

> [!NOTE] 
> <span data-ttu-id="de2e2-1048">一定要调整到当前月份的月年筛选器。</span><span class="sxs-lookup"><span data-stu-id="de2e2-1048">Be sure to adjust the Month Year filter to the current month.</span></span> <span data-ttu-id="de2e2-1049">选择**编辑**，然后调整**月年**保存新默认的月份。</span><span class="sxs-lookup"><span data-stu-id="de2e2-1049">Select **Edit**, and adjust **Month Year** to save the new default month.</span></span><br><br> <span data-ttu-id="de2e2-1050">您可能会注意到在查看此报表，您将看到相同的设备报告多次。</span><span class="sxs-lookup"><span data-stu-id="de2e2-1050">You might notice when viewing this report that you see the same device reported multiple times.</span></span> <span data-ttu-id="de2e2-1051">这是因为被汇报给 CQD 报告设备的方法。</span><span class="sxs-lookup"><span data-stu-id="de2e2-1051">This is due to the way the device is reported being reported to CQD.</span></span> <span data-ttu-id="de2e2-1052">硬件和操作系统的区域设置的差异报告设备数据各不相同。</span><span class="sxs-lookup"><span data-stu-id="de2e2-1052">Differences in hardware and OS locale report device data differently.</span></span>

![呼叫质量面板中的设备 （麦克风） 报告的屏幕快照。](media/quality-of-experience-review-guide-image29.png)

<span data-ttu-id="de2e2-1054">_图 29--设备 （麦克风） 报表_</span><span class="sxs-lookup"><span data-stu-id="de2e2-1054">_Figure 29 - – Device (Microphone) Report_</span></span>

##### <a name="remediation"></a><span data-ttu-id="de2e2-1055">补救措施</span><span class="sxs-lookup"><span data-stu-id="de2e2-1055">Remediation</span></span>

<span data-ttu-id="de2e2-1056">第一项任务是确定想要达到的 MOS 目标。</span><span class="sxs-lookup"><span data-stu-id="de2e2-1056">The first task is to determine the MOS target you would like to attain.</span></span> <span data-ttu-id="de2e2-1057">MOS 分数范围从 1 到 5，5 表示最好。</span><span class="sxs-lookup"><span data-stu-id="de2e2-1057">MOS scores range from 1 to 5, with 5 being the best.</span></span> <span data-ttu-id="de2e2-1058">选择基于查询结果和环境的合理目标。</span><span class="sxs-lookup"><span data-stu-id="de2e2-1058">Choose a reasonable target based on your environment and query results.</span></span> <span data-ttu-id="de2e2-1059">在以下示例中，目标是 MOS 得分 3.6 或更好的有 100 多个流的所有设备。</span><span class="sxs-lookup"><span data-stu-id="de2e2-1059">In the following example, the target is an MOS score of 3.6 or better for all devices that have over 100 streams.</span></span> <span data-ttu-id="de2e2-1060">您将能获得设备质量目标时：</span><span class="sxs-lookup"><span data-stu-id="de2e2-1060">You’ll achieve your device quality target when:</span></span>

-   <span data-ttu-id="de2e2-1061">设备查询结果返回 MOS \> NumStreams 的 3.6 \> 100</span><span class="sxs-lookup"><span data-stu-id="de2e2-1061">The device query results return MOS \> 3.6 for NumStreams \> 100</span></span>

<span data-ttu-id="de2e2-1062">通常情况下，您将需要使用经过认证的设备替换差设备。</span><span class="sxs-lookup"><span data-stu-id="de2e2-1062">Typically, you’ll need to replace poorly performing devices with certified devices.</span></span> <span data-ttu-id="de2e2-1063">查看设备报告时的一些注意事项包括：</span><span class="sxs-lookup"><span data-stu-id="de2e2-1063">Some considerations when reviewing the device report include:</span></span>

-   <span data-ttu-id="de2e2-1064">被认证的设备或已知无法在您的环境中正常工作？</span><span class="sxs-lookup"><span data-stu-id="de2e2-1064">Are the devices certified or known to be good in your environment?</span></span> <span data-ttu-id="de2e2-1065">如果认证或好的设备比基线低 MOS 得分为查询中返回，可能有未知其他因素 （如网络性能差或性能下降的 pc） 分配给较低的分数。</span><span class="sxs-lookup"><span data-stu-id="de2e2-1065">If a certified or good device is returned in the query with a lower MOS score than your baseline, there may be unknown additional factors (such as a poor network or underpowered pc) that is contributing to the low score.</span></span>
    <span data-ttu-id="de2e2-1066">需要进一步研究。</span><span class="sxs-lookup"><span data-stu-id="de2e2-1066">Additional investigation will be required.</span></span>

-   <span data-ttu-id="de2e2-1067">您可以确定通过[调用分析](#call-analytics-training)设备的用户。</span><span class="sxs-lookup"><span data-stu-id="de2e2-1067">You can identify users of a device through [Call Analytics](#call-analytics-training).</span></span> <span data-ttu-id="de2e2-1068">检查以确保他们有最新的设备驱动程序和设备没有连接到 USB 集线器。</span><span class="sxs-lookup"><span data-stu-id="de2e2-1068">Check to make sure they have the latest device drivers and that their device isn’t connected through a USB hub.</span></span>

-   <span data-ttu-id="de2e2-1069">检查以查看是否有不正确的设备和特定系统的构造和型号之间的相关性。</span><span class="sxs-lookup"><span data-stu-id="de2e2-1069">Check to see whether there’s a correlation between bad devices and a particular system’s make and model.</span></span> <span data-ttu-id="de2e2-1070">如果是这样，设备可能不兼容，或需要驱动程序升级。</span><span class="sxs-lookup"><span data-stu-id="de2e2-1070">If so, the device might be incompatible or need driver upgrades.</span></span>

<span data-ttu-id="de2e2-1071">第二项任务是确定未经认证的设备的总体使用情况。</span><span class="sxs-lookup"><span data-stu-id="de2e2-1071">The second task is to determine the overall usage of non-certified devices.</span></span> <span data-ttu-id="de2e2-1072">我们建议至少 80%的所有音频流使用经过认证的设备。</span><span class="sxs-lookup"><span data-stu-id="de2e2-1072">We recommend that at least 80 percent of all audio streams use a certified device.</span></span>
<span data-ttu-id="de2e2-1073">这最好通过将设备报告导出到 Excel 并手动计算认证或经批准的设备的使用情况。</span><span class="sxs-lookup"><span data-stu-id="de2e2-1073">This is best accomplished by exporting the Devices report to Excel and manually calculating the usage of certified or approved devices.</span></span> <span data-ttu-id="de2e2-1074">公司通常存放所有批准的设备的列表，以便进行筛选和排序数据变得很简单。</span><span class="sxs-lookup"><span data-stu-id="de2e2-1074">Organizations typically keep a list of all approved devices, so filtering and sorting the data should be straightforward.</span></span>

## <a name="appendix-a-lync-networking-guide"></a><span data-ttu-id="de2e2-1075">附录 A.Lync 网络指南</span><span class="sxs-lookup"><span data-stu-id="de2e2-1075">Appendix A. Lync Networking Guide</span></span>

<span data-ttu-id="de2e2-1076">有关更多背景的团队和 Skype 业务网络的概念和基本原理对质量的重要性， [Lync Server 2013 网络指南](https://blogs.technet.microsoft.com/nexthop/2013/06/03/lync-server-2013-networking-guide-network-planning-monitoring-and-troubleshooting-with-microsoft-lync-server/)仍然适用。</span><span class="sxs-lookup"><span data-stu-id="de2e2-1076">For more background on the Teams and Skype for Business networking concepts and rationale behind their importance to quality, the [Lync Server 2013 Networking Guide](https://blogs.technet.microsoft.com/nexthop/2013/06/03/lync-server-2013-networking-guide-network-planning-monitoring-and-troubleshooting-with-microsoft-lync-server/) is still applicable.</span></span>

## <a name="appendix-b-network-performance-requirements"></a><span data-ttu-id="de2e2-1077">附录 b。 网络性能要求</span><span class="sxs-lookup"><span data-stu-id="de2e2-1077">Appendix B. Network performance requirements</span></span>

<span data-ttu-id="de2e2-1078">基于 IP 的实时媒体 （音频、 视频和应用程序共享） 的质量极大地受端到端网络连接的质量。</span><span class="sxs-lookup"><span data-stu-id="de2e2-1078">The quality of real-time media (audio, video, and application sharing) over IP is greatly affected by the quality of end-to-end network connectivity.</span></span> <span data-ttu-id="de2e2-1079">最佳团队或 Skype 业务媒体质量，您的网络必须满足下面的网络性能指标。</span><span class="sxs-lookup"><span data-stu-id="de2e2-1079">For optimal Teams or Skype for Business media quality, your network must meet the following network performance metrics.</span></span>

<span data-ttu-id="de2e2-1080">_表 11-网络性能要求_</span><span class="sxs-lookup"><span data-stu-id="de2e2-1080">_Table 11 - Network performance requirements_</span></span>

| <span data-ttu-id="de2e2-1081">指标</span><span class="sxs-lookup"><span data-stu-id="de2e2-1081">Metric</span></span>                           | <span data-ttu-id="de2e2-1082">客户端到 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="de2e2-1082">Client to Microsoft Edge</span></span>           | <span data-ttu-id="de2e2-1083">客户边缘到 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="de2e2-1083">Customer Edge to Microsoft Edge</span></span>    |
|----------------------------------|------------------------------------|------------------------------------|
| <span data-ttu-id="de2e2-1084">滞后时间 （单向）</span><span class="sxs-lookup"><span data-stu-id="de2e2-1084">Latency (one way)</span></span>                | <span data-ttu-id="de2e2-1085">\<50 毫秒</span><span class="sxs-lookup"><span data-stu-id="de2e2-1085">\<50 ms</span></span>                            | <span data-ttu-id="de2e2-1086">\<30 毫秒</span><span class="sxs-lookup"><span data-stu-id="de2e2-1086">\<30 ms</span></span>                            |
| <span data-ttu-id="de2e2-1087">滞后时间 （RTT 或往返时间）</span><span class="sxs-lookup"><span data-stu-id="de2e2-1087">Latency (RTT or Round-trip Time)</span></span> | <span data-ttu-id="de2e2-1088">\<100 毫秒</span><span class="sxs-lookup"><span data-stu-id="de2e2-1088">\<100 ms</span></span>                           | <span data-ttu-id="de2e2-1089">\<60 毫秒</span><span class="sxs-lookup"><span data-stu-id="de2e2-1089">\<60 ms</span></span>                            |
| <span data-ttu-id="de2e2-1090">突发数据包丢失</span><span class="sxs-lookup"><span data-stu-id="de2e2-1090">Burst packet loss</span></span>                | <span data-ttu-id="de2e2-1091">\<任何 200 毫秒间隔期间的 10%</span><span class="sxs-lookup"><span data-stu-id="de2e2-1091">\<10% during any 200-ms interval</span></span>   | <span data-ttu-id="de2e2-1092">\<1%，在任何 200 毫秒时间间隔</span><span class="sxs-lookup"><span data-stu-id="de2e2-1092">\<1% during any 200-ms interval</span></span>    |
| <span data-ttu-id="de2e2-1093">数据包丢失</span><span class="sxs-lookup"><span data-stu-id="de2e2-1093">Packet loss</span></span>                      | <span data-ttu-id="de2e2-1094">\<1%，在所有 15 秒时间间隔</span><span class="sxs-lookup"><span data-stu-id="de2e2-1094">\<1% during any 15-sec interval</span></span>    | <span data-ttu-id="de2e2-1095">\<0.1 在任何 15 秒间隔 %</span><span class="sxs-lookup"><span data-stu-id="de2e2-1095">\<0.1% during any 15-sec interval</span></span>  |
| <span data-ttu-id="de2e2-1096">数据包间到达抖动</span><span class="sxs-lookup"><span data-stu-id="de2e2-1096">Packet inter-arrival Jitter</span></span>      | <span data-ttu-id="de2e2-1097">\<任何 15 秒间隔期间 30 毫秒</span><span class="sxs-lookup"><span data-stu-id="de2e2-1097">\<30 ms during any 15-sec interval</span></span> | <span data-ttu-id="de2e2-1098">\<任何 15 秒间隔期间 15 毫秒</span><span class="sxs-lookup"><span data-stu-id="de2e2-1098">\<15 ms during any 15-sec interval</span></span> |
| <span data-ttu-id="de2e2-1099">数据包重新排序</span><span class="sxs-lookup"><span data-stu-id="de2e2-1099">Packet reorder</span></span>                   | <span data-ttu-id="de2e2-1100">\<0.05%无序的数据包</span><span class="sxs-lookup"><span data-stu-id="de2e2-1100">\<0.05% out-of-order packets</span></span>       | <span data-ttu-id="de2e2-1101">\<0.01%无序的数据包</span><span class="sxs-lookup"><span data-stu-id="de2e2-1101">\< 0.01% out-of-order packets</span></span>      |

<span data-ttu-id="de2e2-1102">详细信息，请参阅下文有关[媒体质量和网络性能](https://aka.ms/performancerequirements)团队和 Skype 的在线业务。</span><span class="sxs-lookup"><span data-stu-id="de2e2-1102">For more information, see the following article about [media quality and network performance](https://aka.ms/performancerequirements) for Teams and Skype for Business Online.</span></span>

<a name="other-resources"></a>

## <a name="appendix-c-other-resources"></a><span data-ttu-id="de2e2-1103">附录 c。其他资源</span><span class="sxs-lookup"><span data-stu-id="de2e2-1103">Appendix C. Other resources</span></span>

### <a name="building-data-file"></a><span data-ttu-id="de2e2-1104">正在创建数据文件</span><span class="sxs-lookup"><span data-stu-id="de2e2-1104">Building data file</span></span>

-   [<span data-ttu-id="de2e2-1105">打开和使用的 Skype 的在线业务的 CQD</span><span class="sxs-lookup"><span data-stu-id="de2e2-1105">Turning on and using CQD in Skype for Business Online</span></span>](https://support.office.com/article/Turning-on-and-using-Call-Quality-Dashboard-in-Skype-for-Business-Online-553fa13c-92d2-4d5c-a3d5-41a073cb047c)

<a name="CQD-training"></a>

### <a name="cqd-training"></a><span data-ttu-id="de2e2-1106">CQD 培训</span><span class="sxs-lookup"><span data-stu-id="de2e2-1106">CQD training</span></span>

-   <https://aka.ms/sof-cqd>

-   <span data-ttu-id="de2e2-1107">[CQD 入门](https://www.skypeoperationsframework.com/Academy?SOFTrainings=Configuring%20Call%20Quality%20Dashboard%20to%20monitor%20your%20Skype%20for%20Business%20Online%20Environment)指南和研讨会。</span><span class="sxs-lookup"><span data-stu-id="de2e2-1107">[Getting started with CQD](https://www.skypeoperationsframework.com/Academy?SOFTrainings=Configuring%20Call%20Quality%20Dashboard%20to%20monitor%20your%20Skype%20for%20Business%20Online%20Environment) guide and workshop.</span></span>

-   [<span data-ttu-id="de2e2-1108">CQD 维度和度量值的联机指南</span><span class="sxs-lookup"><span data-stu-id="de2e2-1108">CQD Dimensions and Measures online guide</span></span>](https://support.office.com/article/Dimensions-and-measures-available-in-Call-Quality-Dashboard-in-Skype-for-Business-Online-e97aeeee-9e43-416f-b433-9cdd63d8874b)

### <a name="call-analytics-training"></a><span data-ttu-id="de2e2-1109">调用分析培训</span><span class="sxs-lookup"><span data-stu-id="de2e2-1109">Call Analytics training</span></span>

-   [<span data-ttu-id="de2e2-1110">引入调用分析</span><span class="sxs-lookup"><span data-stu-id="de2e2-1110">Introducing Call Analytics</span></span>](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309)

-   [<span data-ttu-id="de2e2-1111">设置 Skype for Business 通话分析</span><span class="sxs-lookup"><span data-stu-id="de2e2-1111">Set up Skype for Business Call Analytics</span></span>](https://support.office.com/article/Set-up-Skype-for-Business-Call-Analytics-FBF7247A-84AE-46CC-9204-2C45B1C734CD)

-   [<span data-ttu-id="de2e2-1112">通话分析与通话质量仪表板之间有何区别？</span><span class="sxs-lookup"><span data-stu-id="de2e2-1112">What's the difference between Call Analytics and Call Quality Dashboard?</span></span>](https://support.office.com/article/What-s-the-difference-between-Call-Analytics-and-Call-Quality-Dashboard-4CD5FE35-8463-4996-A252-086CD3CA2D9A)

-   [<span data-ttu-id="de2e2-1113">使用通话分析解决 Skype for Business 通话质量不佳的问题</span><span class="sxs-lookup"><span data-stu-id="de2e2-1113">Use Call Analytics to troubleshoot poor Skype for Business call quality</span></span>](https://support.office.com/article/Use-Call-Analytics-to-troubleshoot-poor-Skype-for-Business-call-quality-66945036-ae87-4c08-a0bb-984e50d6b009)

### <a name="call-analytics-support"></a><span data-ttu-id="de2e2-1114">调用分析支持</span><span class="sxs-lookup"><span data-stu-id="de2e2-1114">Call Analytics support</span></span>

-   <span data-ttu-id="de2e2-1115">社区： [Skype 业务预览程序](https://techcommunity.microsoft.com/t5/Skype-for-Business-Preview/bd-p/SkypeforBusinessPreviewProgram)</span><span class="sxs-lookup"><span data-stu-id="de2e2-1115">Community: [Skype for Business Preview Program](https://techcommunity.microsoft.com/t5/Skype-for-Business-Preview/bd-p/SkypeforBusinessPreviewProgram)</span></span>

-   <span data-ttu-id="de2e2-1116">要获得支持，登录到我们预览门户[www.skypepreview.com](http://www.skypepreview.com)、 选择**报表问题**，和使用**创建的新 Bug**选项来报告问题。</span><span class="sxs-lookup"><span data-stu-id="de2e2-1116">To get support, sign in to our preview portal [www.skypepreview.com](http://www.skypepreview.com), select **Report an issue**, and use the **Create New Bug** option to report an issue.</span></span> <span data-ttu-id="de2e2-1117">请注意，支持工程师可以从周一到周五，上午 6 点到晚上 9 点预计小时之间提供支持</span><span class="sxs-lookup"><span data-stu-id="de2e2-1117">Please note that support engineers are available to provide support from Monday through Friday, between the hours of 6 AM to 9 PM EST.</span></span> <span data-ttu-id="de2e2-1118">在这些时间之外的请求将优先处理下一天。</span><span class="sxs-lookup"><span data-stu-id="de2e2-1118">Requests outside of those hours will be triaged the following day.</span></span>

### <a name="devices"></a><span data-ttu-id="de2e2-1119">设备</span><span class="sxs-lookup"><span data-stu-id="de2e2-1119">Devices</span></span>

-   [<span data-ttu-id="de2e2-1120">Skype 的业务解决方案目录个人的外围设备和 Pc</span><span class="sxs-lookup"><span data-stu-id="de2e2-1120">Skype for Business Solutions Catalog Personal Peripherals & PCs</span></span>](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs)

### <a name="tenant-reporting"></a><span data-ttu-id="de2e2-1121">租户报告</span><span class="sxs-lookup"><span data-stu-id="de2e2-1121">Tenant reporting</span></span>

-   [<span data-ttu-id="de2e2-1122">Office 365 采用内容包</span><span class="sxs-lookup"><span data-stu-id="de2e2-1122">Office 365 Adoption Content Pack</span></span>](https://blogs.office.com/2017/05/22/announcing-the-public-preview-of-the-office-365-adoption-content-pack-in-powerbi/)

-   [<span data-ttu-id="de2e2-1123">Skype for Business Online 报告</span><span class="sxs-lookup"><span data-stu-id="de2e2-1123">Skype for Business Online reporting</span></span>](https://support.office.com/article/Skype-for-Business-Online-reporting-4935cddf-fafa-442d-91a3-246af01f8373)

-   [<span data-ttu-id="de2e2-1124">Microsoft 的小组报告</span><span class="sxs-lookup"><span data-stu-id="de2e2-1124">Microsoft Teams reporting</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/New-usage-reports-for-Microsoft-Teams/ba-p/132614)
