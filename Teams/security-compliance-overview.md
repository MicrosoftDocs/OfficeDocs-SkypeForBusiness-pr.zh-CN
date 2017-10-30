---
title: "Microsoft Teams 中的安全性和合规性概述 | Microsoft 支持"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Microsoft Teams 中的安全性和合规性概述，包括审核和报告、合规性内容搜索以及电子数据展示等。"
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 3321dee954b9861054886677b2835c689035888c
ms.sourcegitcommit: 2e557e90b4e30fe99ff9df3897b8e54f38ea2f2e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2017
---
<a name="overview-of-security-and-compliance-in-microsoft-teams"></a><span data-ttu-id="56dc1-103">Microsoft Teams 中的安全性和合规性概述</span><span class="sxs-lookup"><span data-stu-id="56dc1-103">Overview of security and compliance in Microsoft Teams</span></span>
======================================================

<span data-ttu-id="56dc1-104">Microsoft Teams 建立在 Office 365 超大规模企业级云之上，提供我们的客户期望的高级安全性和合规性功能。</span><span class="sxs-lookup"><span data-stu-id="56dc1-104">Microsoft Teams is built on the Office 365 hyper-scale, enterprise-grade cloud, delivering the advanced security and compliance capabilities our customers expect.</span></span>

<span data-ttu-id="56dc1-105">Teams 在上市时符合 Tier C 标准。</span><span class="sxs-lookup"><span data-stu-id="56dc1-105">Teams is Tier C-compliant at launch.</span></span> <span data-ttu-id="56dc1-106">这包括以下标准：ISO 27001、ISO 27018、SSAE16 SOC 1 和 SOC 2、HIPAA 以及欧盟模型条款 (EUMC)。</span><span class="sxs-lookup"><span data-stu-id="56dc1-106">This includes the following standards: ISO 27001, ISO 27018, SSAE16 SOC 1 and SOC 2, HIPAA, and EU Model Clauses (EUMC).</span></span> <span data-ttu-id="56dc1-107">在 Microsoft 合规性框架中，Microsoft 将 Office 365 应用和服务分类为四种类别。</span><span class="sxs-lookup"><span data-stu-id="56dc1-107">Within the Microsoft compliance framework, Microsoft classifies Office 365 applications and services into four categories.</span></span> <span data-ttu-id="56dc1-108">每种类别均按特定的合规性承诺定义，Office 365 服务或相关的 Microsoft 服务必须履行这些承诺才能列在相应类别中。</span><span class="sxs-lookup"><span data-stu-id="56dc1-108">Each category is defined by specific compliance commitments that must be met for an Office 365 service, or a related Microsoft service, to be listed in that category.</span></span>

<span data-ttu-id="56dc1-109">默认情况下启用合规性类别 C 和 D 中的服务，它们有行业领先的合规性承诺。</span><span class="sxs-lookup"><span data-stu-id="56dc1-109">Services in compliance categories C and D that have industry-leading compliance commitments are enabled by default.</span></span> <span data-ttu-id="56dc1-110">类别 A 和 B 中的服务提供了针对整个组织开启或关闭这些服务的控制功能。</span><span class="sxs-lookup"><span data-stu-id="56dc1-110">Services in categories A and B come with controls to turn on or turn off these services for an entire organization.</span></span> <span data-ttu-id="56dc1-111">有关详细信息，请参阅[行业标准和规章的合规性框架](https://go.microsoft.com/fwlink/?linkid=855777)。</span><span class="sxs-lookup"><span data-stu-id="56dc1-111">Details can be found in the [Compliance Framework for Industry Standards and Regulations](https://go.microsoft.com/fwlink/?linkid=855777).</span></span> <span data-ttu-id="56dc1-112">Microsoft Teams 还支持云安全联盟合规性。</span><span class="sxs-lookup"><span data-stu-id="56dc1-112">Microsoft Teams also supports Cloud Security Alliance compliance.</span></span>

<span data-ttu-id="56dc1-113">Teams 还强制执行团队范围和组织范围的双重身份验证、通过 Active Directory 进行单一登录以及对正在传输的数据和静态数据加密。</span><span class="sxs-lookup"><span data-stu-id="56dc1-113">Teams also enforces team-wide and organization-wide two-factor authentication, single sign-on through Active Directory, and encryption of data in transit and at rest.</span></span> <span data-ttu-id="56dc1-114">文件存储在 SharePoint 中，并会进行 SharePoint 加密。</span><span class="sxs-lookup"><span data-stu-id="56dc1-114">Files are stored in SharePoint and are backed by SharePoint encryption.</span></span> <span data-ttu-id="56dc1-115">笔记存储在 OneNote 中，并会进行 OneNote 加密。</span><span class="sxs-lookup"><span data-stu-id="56dc1-115">Notes are stored in OneNote and are backed by OneNote encryption.</span></span>

<span data-ttu-id="56dc1-116">我们还增加了以下支持：审核日志搜索、针对频道、聊天和文件的电子数据展示和法定保留，以及通过 Microsoft Intune 进行移动应用管理。</span><span class="sxs-lookup"><span data-stu-id="56dc1-116">We also added support for audit log search, eDiscovery and legal hold for channels, chats and files as well as mobile application management with Microsoft Intune.</span></span>

<span data-ttu-id="56dc1-117">这些工具位于 Office 365 安全性和合规性门户中，提供以下功能：</span><span class="sxs-lookup"><span data-stu-id="56dc1-117">These tools reside in the Office 365 Security and Compliance Portal and provide the following features:</span></span>

-   <span data-ttu-id="56dc1-118">审核和报告</span><span class="sxs-lookup"><span data-stu-id="56dc1-118">Auditing and Reporting</span></span>

    -   <span data-ttu-id="56dc1-119">审核日志搜索置于 Office 365 安全性和合规性中心中，进而可以通过提供审核日志数据对审核事件设置警报和/或进行报告，能够导出工作负荷特定或一般事件集以用于管理和调查，审核时间线无限制。</span><span class="sxs-lookup"><span data-stu-id="56dc1-119">Audit log search plugs right into the Office 365 Security and Compliance Center and exposes abilities to set alerts and/or report on Audit event by making available, export of workload specific or generic event sets for admin use and investigation, across an unlimited auditing timeline.</span></span> <span data-ttu-id="56dc1-120">所有审核日志数据可用于在 Office 365 安全性和合规性中心中设置警报，以及用于筛选和报告以供进一步分析。</span><span class="sxs-lookup"><span data-stu-id="56dc1-120">All Audit Log data is available for setting up of alerts within the Office 365 Security and Compliance Center, as well as for filtering and export for further analysis.</span></span>

-   <span data-ttu-id="56dc1-121">合规性内容搜索</span><span class="sxs-lookup"><span data-stu-id="56dc1-121">Compliance Content Search</span></span>

    -   <span data-ttu-id="56dc1-122">可以使用内容搜索通过丰富的筛选功能搜索 Microsoft Teams，并可以将搜索结果导出到特定容器以用于合规性和诉讼活动。</span><span class="sxs-lookup"><span data-stu-id="56dc1-122">Content Search can be used to search Microsoft Teams through rich filtering capabilities and exported to a specific container for compliance and litigation support.</span></span> <span data-ttu-id="56dc1-123">在有无电子数据展示案例的情况下，均可执行此操作。</span><span class="sxs-lookup"><span data-stu-id="56dc1-123">This can be done with or without an eDiscovery case.</span></span>

-   <span data-ttu-id="56dc1-124">电子数据展示</span><span class="sxs-lookup"><span data-stu-id="56dc1-124">eDiscovery</span></span>

    -   <span data-ttu-id="56dc1-125">电子数据展示是为了回应法律诉讼或调查中提供文件的要求而找出、收集和生成电子方式存储的信息 (ESI) 的电子操作过程。</span><span class="sxs-lookup"><span data-stu-id="56dc1-125">Electronic discovery is the electronic aspect of identifying, collecting and producing electronically stored information (ESI) in response to a request for production in a law suit or investigation.</span></span>

    -   <span data-ttu-id="56dc1-126">功能包括对 Teams 数据进行案例管理、保留、搜索、分析和导出。</span><span class="sxs-lookup"><span data-stu-id="56dc1-126">Capabilities include case management, preservation, search, analysis and export of Teams data.</span></span> <span data-ttu-id="56dc1-127">这些数据包括聊天、消息传递和文件数据。</span><span class="sxs-lookup"><span data-stu-id="56dc1-127">This includes chat, messaging and file data.</span></span>

    -   <span data-ttu-id="56dc1-128">客户可以利用就地电子数据展示或[高级电子数据展示](https://support.office.com/en-us/article/Office-365-Advanced-eDiscovery-fd53438a-a760-45f6-9df4-861b50161ae4)。</span><span class="sxs-lookup"><span data-stu-id="56dc1-128">Customers can leverage in-place eDiscovery or [Advanced eDiscovery](https://support.office.com/en-us/article/Office-365-Advanced-eDiscovery-fd53438a-a760-45f6-9df4-861b50161ae4)</span></span>

    -   <span data-ttu-id="56dc1-129">下表概括列出了这两者之间的差异：</span><span class="sxs-lookup"><span data-stu-id="56dc1-129">The following table shows the differences between these two methods:</span></span>


| |<span data-ttu-id="56dc1-130">就地电子数据展示</span><span class="sxs-lookup"><span data-stu-id="56dc1-130">In-place eDiscovery</span></span>  |<span data-ttu-id="56dc1-131">高级电子数据展示</span><span class="sxs-lookup"><span data-stu-id="56dc1-131">Advanced eDiscovery</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="56dc1-132">案例管理</span><span class="sxs-lookup"><span data-stu-id="56dc1-132">Case Management</span></span>     |<span data-ttu-id="56dc1-133">X</span><span class="sxs-lookup"><span data-stu-id="56dc1-133">X</span></span>        |<span data-ttu-id="56dc1-134">X</span><span class="sxs-lookup"><span data-stu-id="56dc1-134">X</span></span>         |
|<span data-ttu-id="56dc1-135">访问控制</span><span class="sxs-lookup"><span data-stu-id="56dc1-135">Role-Based Access Control</span></span>  |<span data-ttu-id="56dc1-136">X</span><span class="sxs-lookup"><span data-stu-id="56dc1-136">X</span></span>         |<span data-ttu-id="56dc1-137">X</span><span class="sxs-lookup"><span data-stu-id="56dc1-137">X</span></span>         |
|<span data-ttu-id="56dc1-138">内容搜索</span><span class="sxs-lookup"><span data-stu-id="56dc1-138">Content Searches</span></span>     |<span data-ttu-id="56dc1-139">X</span><span class="sxs-lookup"><span data-stu-id="56dc1-139">X</span></span>         | <span data-ttu-id="56dc1-140">X</span><span class="sxs-lookup"><span data-stu-id="56dc1-140">X</span></span>        |
|<span data-ttu-id="56dc1-141">保留</span><span class="sxs-lookup"><span data-stu-id="56dc1-141">Hold(s)</span></span>   |<span data-ttu-id="56dc1-142">X</span><span class="sxs-lookup"><span data-stu-id="56dc1-142">X</span></span>         | <span data-ttu-id="56dc1-143">X</span><span class="sxs-lookup"><span data-stu-id="56dc1-143">X</span></span>        |
|<span data-ttu-id="56dc1-144">导出</span><span class="sxs-lookup"><span data-stu-id="56dc1-144">Export</span></span>     |<span data-ttu-id="56dc1-145">X</span><span class="sxs-lookup"><span data-stu-id="56dc1-145">X</span></span>         |<span data-ttu-id="56dc1-146">X</span><span class="sxs-lookup"><span data-stu-id="56dc1-146">X</span></span>         |
|<span data-ttu-id="56dc1-147">重复项检测</span><span class="sxs-lookup"><span data-stu-id="56dc1-147">Duplication Detection</span></span>     |-         |<span data-ttu-id="56dc1-148">X</span><span class="sxs-lookup"><span data-stu-id="56dc1-148">X</span></span>         |
|<span data-ttu-id="56dc1-149">使用机器学习的相关性搜索</span><span class="sxs-lookup"><span data-stu-id="56dc1-149">Relevance Searches with Machine Learning</span></span>    |-         |<span data-ttu-id="56dc1-150">X</span><span class="sxs-lookup"><span data-stu-id="56dc1-150">X</span></span>         |
|<span data-ttu-id="56dc1-151">非结构化数据分析</span><span class="sxs-lookup"><span data-stu-id="56dc1-151">Unstructured Data Analysis</span></span>      |-         |<span data-ttu-id="56dc1-152">X</span><span class="sxs-lookup"><span data-stu-id="56dc1-152">X</span></span>         |


-   <span data-ttu-id="56dc1-153">法定保留</span><span class="sxs-lookup"><span data-stu-id="56dc1-153">Legal Hold</span></span>

    -   <span data-ttu-id="56dc1-154">当 Microsoft Teams 中的任何团队置于就地保留或诉讼保留时，将组邮箱置于保留状态。</span><span class="sxs-lookup"><span data-stu-id="56dc1-154">When any Team within Microsoft Teams is put on In-Place Hold or Litigation Hold, the hold is placed on the groups mailbox.</span></span>

    -   <span data-ttu-id="56dc1-155">通常在电子数据展示案例的上下文中应用法定保留。</span><span class="sxs-lookup"><span data-stu-id="56dc1-155">Legal Holds are generally applied within the context of an eDiscovery case.</span></span>

<span data-ttu-id="56dc1-156">下图显示了 Teams 数据到 Exchange 和 SharePoint 的工作流。</span><span class="sxs-lookup"><span data-stu-id="56dc1-156">The figure below indicates the workflow of Teams data to both Exchange and SharePoint.</span></span>

![](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1.png)


> [!IMPORTANT]
> <span data-ttu-id="56dc1-157">发现 Teams 内容的过程最长可能延迟 24 小时。</span><span class="sxs-lookup"><span data-stu-id="56dc1-157">There can be up to a 24-hr delay to discover Teams content.</span></span>

<span data-ttu-id="56dc1-158">此外，Microsoft 正在考虑为 Teams 提供以下安全功能。</span><span class="sxs-lookup"><span data-stu-id="56dc1-158">Additionally, Microsoft is considering providing the following security features for Teams.</span></span> <span data-ttu-id="56dc1-159">一旦可用，将提供有关客户如何利用这些功能的指导：</span><span class="sxs-lookup"><span data-stu-id="56dc1-159">Once available, guidance will be provided on how customers can leverage the features:</span></span>

-   <span data-ttu-id="56dc1-160">租户特定的保留策略</span><span class="sxs-lookup"><span data-stu-id="56dc1-160">Tenant-specific retention Policy</span></span>

-   <span data-ttu-id="56dc1-161">数据丢失防护 (DLP)</span><span class="sxs-lookup"><span data-stu-id="56dc1-161">Data loss prevention (DLP)</span></span>

-   <span data-ttu-id="56dc1-162">客户密码箱</span><span class="sxs-lookup"><span data-stu-id="56dc1-162">Customer Lockbox</span></span>

-   <span data-ttu-id="56dc1-163">权限管理</span><span class="sxs-lookup"><span data-stu-id="56dc1-163">Right Management</span></span>


| | | |
|---------|---------|---------|
|![](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |<span data-ttu-id="56dc1-164">决策点</span><span class="sxs-lookup"><span data-stu-id="56dc1-164">Policy Decision Point</span></span>         |<span data-ttu-id="56dc1-165">贵组织需要哪些安全性和合规性功能？</span><span class="sxs-lookup"><span data-stu-id="56dc1-165">What security and compliance features does your organization require?</span></span> <span data-ttu-id="56dc1-166">贵组织是否有所需的许可证来满足安全性和合规性业务需求？</span><span class="sxs-lookup"><span data-stu-id="56dc1-166">Does your organization have the required licenses to meet Security and Compliance business requirements?</span></span>         |
|![](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)     |<span data-ttu-id="56dc1-167">后续步骤</span><span class="sxs-lookup"><span data-stu-id="56dc1-167">Next Steps</span></span>         |<span data-ttu-id="56dc1-168">在下面的表格中记录所需的安全性和合规性功能。</span><span class="sxs-lookup"><span data-stu-id="56dc1-168">Document the required security and compliance features in the table below.</span></span>         |

<a name="licensing"></a><span data-ttu-id="56dc1-169">许可</span><span class="sxs-lookup"><span data-stu-id="56dc1-169">Licensing</span></span>
---------------

<span data-ttu-id="56dc1-170">涉及到信息保护功能时，Office 365 订阅和关联的单独许可证将确定功能集。</span><span class="sxs-lookup"><span data-stu-id="56dc1-170">When it comes to the information protection capabilities, Office 365 subscriptions and the associated standalone licenses will determine the available feature set.</span></span>

|<span data-ttu-id="56dc1-171">信息保护功能</span><span class="sxs-lookup"><span data-stu-id="56dc1-171">Information Protection Capability</span></span>   |<span data-ttu-id="56dc1-172">Office 365 商业协作版</span><span class="sxs-lookup"><span data-stu-id="56dc1-172">Office 365 Business Essentials</span></span>   |<span data-ttu-id="56dc1-173">Office 365 商业高级版</span><span class="sxs-lookup"><span data-stu-id="56dc1-173">Office 365 Business Premium</span></span>   |<span data-ttu-id="56dc1-174">Office 365 企业版 E1</span><span class="sxs-lookup"><span data-stu-id="56dc1-174">Office 365 Enterprise E1</span></span>   |<span data-ttu-id="56dc1-175">Office 365 企业版 E3/E4</span><span class="sxs-lookup"><span data-stu-id="56dc1-175">Office 365 Enterprise E3/E4</span></span>   |<span data-ttu-id="56dc1-176">Office 365 企业版 E5</span><span class="sxs-lookup"><span data-stu-id="56dc1-176">Office 365 Enterprise E5</span></span>   |
|---|---|---|---|---|---|
|<span data-ttu-id="56dc1-177">存档</span><span class="sxs-lookup"><span data-stu-id="56dc1-177">Archive</span></span>|-  |-   |-   |<span data-ttu-id="56dc1-178">是</span><span class="sxs-lookup"><span data-stu-id="56dc1-178">Yes</span></span>   |<span data-ttu-id="56dc1-179">是</span><span class="sxs-lookup"><span data-stu-id="56dc1-179">Yes</span></span>   |
|<span data-ttu-id="56dc1-180">就地电子数据展示</span><span class="sxs-lookup"><span data-stu-id="56dc1-180">In-Place eDiscovery</span></span>|-   |-   |-   |<span data-ttu-id="56dc1-181">是</span><span class="sxs-lookup"><span data-stu-id="56dc1-181">Yes</span></span>   |<span data-ttu-id="56dc1-182">是</span><span class="sxs-lookup"><span data-stu-id="56dc1-182">Yes</span></span>   |
|<span data-ttu-id="56dc1-183">高级电子数据展示</span><span class="sxs-lookup"><span data-stu-id="56dc1-183">Advanced eDiscovery</span></span>|-   |-   |-   |-   |<span data-ttu-id="56dc1-184">是</span><span class="sxs-lookup"><span data-stu-id="56dc1-184">Yes</span></span>   |
|<span data-ttu-id="56dc1-185">法定保留</span><span class="sxs-lookup"><span data-stu-id="56dc1-185">Legal Hold</span></span>|-   |-   |-   |<span data-ttu-id="56dc1-186">是</span><span class="sxs-lookup"><span data-stu-id="56dc1-186">Yes</span></span>   |<span data-ttu-id="56dc1-187">是</span><span class="sxs-lookup"><span data-stu-id="56dc1-187">Yes</span></span>   |
|<span data-ttu-id="56dc1-188">合规性内容搜索</span><span class="sxs-lookup"><span data-stu-id="56dc1-188">Compliance Content Search</span></span>|- |- |- |<span data-ttu-id="56dc1-189">是</span><span class="sxs-lookup"><span data-stu-id="56dc1-189">Yes</span></span> |<span data-ttu-id="56dc1-190">是</span><span class="sxs-lookup"><span data-stu-id="56dc1-190">Yes</span></span> |
|<span data-ttu-id="56dc1-191">审核和报告</span><span class="sxs-lookup"><span data-stu-id="56dc1-191">Auditing and Reporting</span></span>|<span data-ttu-id="56dc1-192">是</span><span class="sxs-lookup"><span data-stu-id="56dc1-192">Yes</span></span> |<span data-ttu-id="56dc1-193">是</span><span class="sxs-lookup"><span data-stu-id="56dc1-193">Yes</span></span> |<span data-ttu-id="56dc1-194">是</span><span class="sxs-lookup"><span data-stu-id="56dc1-194">Yes</span></span> |<span data-ttu-id="56dc1-195">是</span><span class="sxs-lookup"><span data-stu-id="56dc1-195">Yes</span></span> |<span data-ttu-id="56dc1-196">是</span><span class="sxs-lookup"><span data-stu-id="56dc1-196">Yes</span></span> |
|<span data-ttu-id="56dc1-197">条件访问</span><span class="sxs-lookup"><span data-stu-id="56dc1-197">Conditional Access*</span></span> |<span data-ttu-id="56dc1-198">是</span><span class="sxs-lookup"><span data-stu-id="56dc1-198">Yes</span></span> |<span data-ttu-id="56dc1-199">是</span><span class="sxs-lookup"><span data-stu-id="56dc1-199">Yes</span></span> |<span data-ttu-id="56dc1-200">是</span><span class="sxs-lookup"><span data-stu-id="56dc1-200">Yes</span></span> |<span data-ttu-id="56dc1-201">是</span><span class="sxs-lookup"><span data-stu-id="56dc1-201">Yes</span></span> |<span data-ttu-id="56dc1-202">是</span><span class="sxs-lookup"><span data-stu-id="56dc1-202">Yes</span></span> |
<span data-ttu-id="56dc1-203">\*条件访问需要额外的许可证</span><span class="sxs-lookup"><span data-stu-id="56dc1-203">\*Conditional Access requires additional licenses</span></span>


| |  |  |
|---------|---------|---------|
|![](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |<span data-ttu-id="56dc1-204">决策点</span><span class="sxs-lookup"><span data-stu-id="56dc1-204">Policy Decision Point</span></span>         |<span data-ttu-id="56dc1-205">贵组织是否有所需的许可证来满足合规性和安全性业务需求？</span><span class="sxs-lookup"><span data-stu-id="56dc1-205">Does your organization have the required licenses to meet Compliance and Security business requirements?</span></span>         |
|![](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)    |<span data-ttu-id="56dc1-206">后续步骤</span><span class="sxs-lookup"><span data-stu-id="56dc1-206">Next Steps</span></span>         |<span data-ttu-id="56dc1-207">检查贵组织的当前许可，并确认其是否满足合规性和安全性的所有业务需求。</span><span class="sxs-lookup"><span data-stu-id="56dc1-207">Review your organizations current licensing and confirm it meets all business requirements for compliance and security.</span></span>         |

<span data-ttu-id="56dc1-208">在启用其中任何功能之前，请确保你有权访问 Office 365 管理中心中的安全性和合规性中心。</span><span class="sxs-lookup"><span data-stu-id="56dc1-208">Before enabling any of these features, ensure you have access to the Security & Compliance Center in the Office 365 Admin center.</span></span> <span data-ttu-id="56dc1-209">默认情况下，租户管理员有访问权限。</span><span class="sxs-lookup"><span data-stu-id="56dc1-209">By default, tenant admins have access.</span></span>

<span data-ttu-id="56dc1-210">不要求在安全性和合规性中心中启用内容搜索和电子数据展示。</span><span class="sxs-lookup"><span data-stu-id="56dc1-210">Content Search and eDiscovery do not require enablement within the Security & Compliance Center.</span></span>

<a name="location-of-data-in-microsoft-teams"></a><span data-ttu-id="56dc1-211">Microsoft Teams 中的数据的位置</span><span class="sxs-lookup"><span data-stu-id="56dc1-211">Location of data in Microsoft Teams</span></span>
-----------------------------------

<span data-ttu-id="56dc1-212">Teams 中的数据基于租户相关性位于相应区域中。</span><span class="sxs-lookup"><span data-stu-id="56dc1-212">Data in Teams resides in the region based on tenant affinity.</span></span> <span data-ttu-id="56dc1-213">当前，Teams 支持美洲、欧洲、中东和非洲以及亚太地区这些区域。</span><span class="sxs-lookup"><span data-stu-id="56dc1-213">Currently, Teams supports the Americas, EMEA, and APAC regions.</span></span> <span data-ttu-id="56dc1-214">将来，Teams 将提供 GoLocal 支持，那时数据保留在国家/地区（不只是区域）中。</span><span class="sxs-lookup"><span data-stu-id="56dc1-214">In the future, Teams will provide GoLocal support, where data remains in country (not just in region).</span></span> <span data-ttu-id="56dc1-215">敬请关注 [*Office 365 路线图*](https://go.microsoft.com/fwlink/?linkid=855778)了解更新。</span><span class="sxs-lookup"><span data-stu-id="56dc1-215">Stay tuned to the [*Office 365 Roadmap*](https://go.microsoft.com/fwlink/?linkid=855778) for updates.</span></span>

<a name="privacy-in-microsoft-teams"></a><span data-ttu-id="56dc1-216">Microsoft Teams 中的隐私</span><span class="sxs-lookup"><span data-stu-id="56dc1-216">Privacy in Microsoft Teams</span></span>
--------------------------

<span data-ttu-id="56dc1-217">作为 Office 365 的客户，你拥有并控制你的数据。</span><span class="sxs-lookup"><span data-stu-id="56dc1-217">As a customer of Office 365, you own and control your data.</span></span> <span data-ttu-id="56dc1-218">除了为你提供你已订阅的服务外，Microsoft 不会将你的数据用于任何其他用途。</span><span class="sxs-lookup"><span data-stu-id="56dc1-218">Microsoft does not use your data for anything other than providing you with the service that you have subscribed to.</span></span> <span data-ttu-id="56dc1-219">作为服务提供商，我们不会扫描你的电子邮件、文档或团队来做广告或用于与服务无关的用途。</span><span class="sxs-lookup"><span data-stu-id="56dc1-219">As a service provider, we do not scan your email, documents, or teams for advertising or for purposes that are not service-related.</span></span> <span data-ttu-id="56dc1-220">Microsoft 无权访问上载的内容。</span><span class="sxs-lookup"><span data-stu-id="56dc1-220">Microsoft doesn’t have access to uploaded content.</span></span> <span data-ttu-id="56dc1-221">对于 OneDrive for Business 和 SharePoint Online，客户数据位于租户中。</span><span class="sxs-lookup"><span data-stu-id="56dc1-221">Like OneDrive for Business and SharePoint Online, customer data stays within the tenant.</span></span>

<span data-ttu-id="56dc1-222">请在 [*Office 365 信任中心*](https://go.microsoft.com/fwlink/?linkid=855779)详细查看我们的信任和安全相关的信息。</span><span class="sxs-lookup"><span data-stu-id="56dc1-222">Check out more about our trust and security related information at the [*Office 365 Trust Center*](https://go.microsoft.com/fwlink/?linkid=855779).</span></span> <span data-ttu-id="56dc1-223">Teams 与 Office 365 信任中心遵循相同的指导和原则。</span><span class="sxs-lookup"><span data-stu-id="56dc1-223">Teams follows the same guidance and principles as the Office 365 Trust Center.</span></span>
