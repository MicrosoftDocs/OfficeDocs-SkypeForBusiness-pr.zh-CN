---
title: 在 Skype for Business Server 2015 中禁用 TLS 1.0/1.1
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 准备并实施在环境中禁用 TLS 1.0 和 1.1。
ms.openlocfilehash: 214605f80c79d7ecb334aeca49d29210e888b511
ms.sourcegitcommit: 4d76837f9481ca2cda437afdf11de5eaf7a57d99
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/11/2021
ms.locfileid: "50726393"
---
# <a name="disable-tls-1011-in-skype-for-business-server-2015"></a><span data-ttu-id="5ce30-103">在 Skype for Business Server 2015 中禁用 TLS 1.0/1.1</span><span class="sxs-lookup"><span data-stu-id="5ce30-103">Disable TLS 1.0/1.1 in Skype for Business Server 2015</span></span>

<span data-ttu-id="5ce30-104">本文帮助你准备和实施在环境中禁用 TLS 1.0 和 1.1。</span><span class="sxs-lookup"><span data-stu-id="5ce30-104">This article helps you prepare for and implement disabling TLS 1.0 and 1.1 in your environments.</span></span> <span data-ttu-id="5ce30-105">此过程需要进行广泛的规划和准备。</span><span class="sxs-lookup"><span data-stu-id="5ce30-105">This process requires extensive planning and preparation.</span></span> <span data-ttu-id="5ce30-106">当您制定为组织禁用 TLS 1.0 和 1.1 的计划时，请仔细查看本文中所有的信息。</span><span class="sxs-lookup"><span data-stu-id="5ce30-106">Carefully review all of the information in this article as you make your plan to disable TLS 1.0 and 1.1 for your organization.</span></span> <span data-ttu-id="5ce30-107">禁用 TLS 1.0/1.1 可能会影响许多外部依赖项和连接条件，因此，需要进行广泛的规划和测试。</span><span class="sxs-lookup"><span data-stu-id="5ce30-107">There are many external dependencies and connectivity conditions that could be impacted by disabling TLS 1.0/1.1, so extensive planning and testing is warranted.</span></span>

- [<span data-ttu-id="5ce30-108">背景和范围</span><span class="sxs-lookup"><span data-stu-id="5ce30-108">Background and scope</span></span>](#background-and-scope)
- [<span data-ttu-id="5ce30-109">先决条件和过程</span><span class="sxs-lookup"><span data-stu-id="5ce30-109">Prerequisites and process</span></span>](#prerequisites-and-process)
- [<span data-ttu-id="5ce30-110">高级部署方案</span><span class="sxs-lookup"><span data-stu-id="5ce30-110">Advanced deployment scenarios</span></span>](#advanced-deployment-scenarios)

## <a name="background-and-scope"></a><span data-ttu-id="5ce30-111">背景和范围</span><span class="sxs-lookup"><span data-stu-id="5ce30-111">Background and scope</span></span>

<span data-ttu-id="5ce30-112">提供对 Skype for Business Server 本地的 TLS 1.0 和 1.1 禁用支持的主要驱动因素是支付卡行业 (PCI) 安全标准委员会和联邦信息处理标准要求。</span><span class="sxs-lookup"><span data-stu-id="5ce30-112">The primary drivers for providing TLS 1.0 and 1.1 disable support for Skype for Business Server On-Premises are Payment Card Industry (PCI) Security Standards Council and Federal Information Processing Standards requirements.</span></span> <span data-ttu-id="5ce30-113">有关 PCI 要求详细信息，请参阅 [此处](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls)。</span><span class="sxs-lookup"><span data-stu-id="5ce30-113">More information for PCI requirements can be found [here](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls).</span></span>  <span data-ttu-id="5ce30-114">Microsoft 无法提供有关你的组织是否需要遵守这些要求或其他要求的指导。</span><span class="sxs-lookup"><span data-stu-id="5ce30-114">Microsoft cannot provide guidance on whether or not your organization is required to adhere to these or other requirements.</span></span> <span data-ttu-id="5ce30-115">必须确定是否需要在你的环境中禁用 TLS 1.0 和/或 1.1。</span><span class="sxs-lookup"><span data-stu-id="5ce30-115">You must determine if it is required for you to disable TLS 1.0 and/or 1.1 in your environments.</span></span>

<span data-ttu-id="5ce30-116">Microsoft 已制作一份有关此处提供的[](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/)TLS 的白皮书，我们还推荐此 Exchange 博客中提供[的背景阅读](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)。</span><span class="sxs-lookup"><span data-stu-id="5ce30-116">Microsoft has produced a white paper on TLS available [here](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/), and we also recommend the background reading available in this [Exchange blog](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/).</span></span>

## <a name="supportability-scope"></a><span data-ttu-id="5ce30-117">可支持性范围</span><span class="sxs-lookup"><span data-stu-id="5ce30-117">Supportability Scope</span></span>

<span data-ttu-id="5ce30-118">*范围* 是指可支持性边界。</span><span class="sxs-lookup"><span data-stu-id="5ce30-118">*Scope* refers to supportability boundaries.</span></span> <span data-ttu-id="5ce30-119">*完全测试和支持* 意味着我们完全支持并已经针对列出的产品版本禁用 TLS 1.0 和 1.1。</span><span class="sxs-lookup"><span data-stu-id="5ce30-119">*Fully tested and supported* means we fully support and have tested disabling of TLS 1.0 and 1.1 for the listed product versions.</span></span> <span data-ttu-id="5ce30-120">*当前正在调查* 意味着这一点;我们正在积极调查将这些产品引入 TLS 禁用支持的范围。</span><span class="sxs-lookup"><span data-stu-id="5ce30-120">*Currently being investigated* means just that; we are actively investigating bringing these products into scope for TLS disable support.</span></span> <span data-ttu-id="5ce30-121">*超出范围* 意味着这些产品版本不支持禁用 TLS 1.0 或 1.1，并且将不起作用，但已指出的例外情况除外。</span><span class="sxs-lookup"><span data-stu-id="5ce30-121">*Out of scope* means these product versions do not support disabling TLS 1.0 or 1.1 and will not work, with noted exceptions.</span></span>

### <a name="fully-tested-and-supported-servers"></a><span data-ttu-id="5ce30-122">经过完全测试且受支持的服务器</span><span class="sxs-lookup"><span data-stu-id="5ce30-122">Fully tested and supported servers</span></span>

- <span data-ttu-id="5ce30-123">Skype for Business Server 2019 CU1 17.0.2046.123 (2019 年 6 月) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="5ce30-123">Skype for Business Server 2019 CU1 17.0.2046.123 (June 2019) or higher</span></span>
- <span data-ttu-id="5ce30-124">skype for Business Server 2015 CU9 6.0.9319.548 (2019) 年 5 月或更高版本（位于 Windows Server 2012 (KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) 或取代更新) 、2012 R2 或 2016）。</span><span class="sxs-lookup"><span data-stu-id="5ce30-124">Skype for Business Server 2015 CU9 6.0.9319.548 (May 2019) or higher on Windows Server 2012 (with KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) or superseding update), 2012 R2 or 2016.</span></span>
- <span data-ttu-id="5ce30-125">Windows Server 2008 R2、2012 (KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) 或取代更新) 或 2012 R2 上的 201) 9 年 5 月或更高版本上的 CU9 6.0.9319.548 (或更高版本的就地升级 Skype for Business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="5ce30-125">In-place Upgraded Skype for Business Server 2015, with CU9 6.0.9319.548 (May 2019) or higher on Windows Server 2008 R2, 2012 (with KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) or superseding update), or 2012 R2.</span></span>
- <span data-ttu-id="5ce30-126">Exchange Connectivity and Outlook Web App with Exchange Server 2010 SP3 RU19 or higher， guidance [here](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)</span><span class="sxs-lookup"><span data-stu-id="5ce30-126">Exchange Connectivity and Outlook Web App with Exchange Server 2010 SP3 RU19 or higher, guidance [here](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)</span></span>
- <span data-ttu-id="5ce30-127">Survivable Branch Appliance (SBA) With Skype for Business Server 2015 CU6 VENDOR2 或更高版本 (与供应商确认他们打包了相应的更新，并且已可用于你的) </span><span class="sxs-lookup"><span data-stu-id="5ce30-127">Survivable Branch Appliance (SBA) with Skype for Business Server 2015 CU6 HF2 or higher (confirm with your vendor that they packaged the appropriate updates and have been made available for your appliance)</span></span>
- <span data-ttu-id="5ce30-128">Survivable Branch Server (SBS) Skype for Business Server 2015 CU6 版第 2 版或更高版本</span><span class="sxs-lookup"><span data-stu-id="5ce30-128">Survivable Branch Server (SBS) with Skype for Business Server 2015 CU6 HF2 or higher</span></span>
- <span data-ttu-id="5ce30-129">仅 Lync Server 2013 边缘角色 ，这是因为边缘角色不依赖于 Windows Fabric 1.0。</span><span class="sxs-lookup"><span data-stu-id="5ce30-129">Lync Server 2013 **Edge Role Only**, this is because Edge role does not have a dependency on Windows Fabric 1.0.</span></span>

### <a name="fully-tested-and-supported-clients"></a><span data-ttu-id="5ce30-130">经过完全测试且受支持的客户端</span><span class="sxs-lookup"><span data-stu-id="5ce30-130">Fully tested and supported clients</span></span>

- <span data-ttu-id="5ce30-131">Lync 2013 (Skype for Business) 桌面客户端、MSI 和 C2R，包括基本 [15.0.5023.1000 或更高版本](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)</span><span class="sxs-lookup"><span data-stu-id="5ce30-131">Lync 2013 (Skype for Business) Desktop Client, MSI and C2R, including Basic [15.0.5023.1000 or higher](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)</span></span>
- <span data-ttu-id="5ce30-132">Skype for Business 2016 桌面客户端、MSI [16.0.4678.1000 或更高版本](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323)，包括基本</span><span class="sxs-lookup"><span data-stu-id="5ce30-132">Skype for Business 2016 Desktop Client, MSI [16.0.4678.1000 or higher](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323), including Basic</span></span>
- <span data-ttu-id="5ce30-133">Skype for Business 2016 Click to Run Require the [April 2018](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) Updates:</span><span class="sxs-lookup"><span data-stu-id="5ce30-133">Skype for Business 2016 Click to Run Require the [April 2018](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) Updates:</span></span> 
    - <span data-ttu-id="5ce30-134">每月和Semi-Annual定向，16 \. \. 0 9126 \. 2152 或更高版本</span><span class="sxs-lookup"><span data-stu-id="5ce30-134">Monthly and Semi-Annual Targeted, 16\.0\.9126\.2152 or higher</span></span>
    - <span data-ttu-id="5ce30-135">Semi-Annual和延期频道，16 \. \. 0 8431 \. 2242 或更高版本</span><span class="sxs-lookup"><span data-stu-id="5ce30-135">Semi-Annual and Deferred Channel, 16\.0\.8431\.2242 or higher</span></span>
- <span data-ttu-id="5ce30-136">Mac 16.15 或更高版本上的 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="5ce30-136">Skype for Business on Mac 16.15 or higher</span></span>
- <span data-ttu-id="5ce30-137">适用于 iOS 和 Android 6.19 或更高版本的 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="5ce30-137">Skype for Business for iOS and Android 6.19 or higher</span></span>
- <span data-ttu-id="5ce30-138">Microsoft Teams 会议室 (2018 年 12 月或更高版本) Skype 会议室系统 V2 SRS V2 (4.0.64.0) 版</span><span class="sxs-lookup"><span data-stu-id="5ce30-138">Microsoft Teams Rooms (previously known as Skype Room System V2 SRS V2) 4.0.64.0 (December 2018) or higher</span></span>
- <span data-ttu-id="5ce30-139">基于 KB4499162 的 Surface Hub 更新 (2019 年 5 月操作系统版本 15063.1835) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="5ce30-139">Surface Hub update for Team edition based on KB4499162 (May 2019, OS Build 15063.1835) or higher</span></span>
- <span data-ttu-id="5ce30-140">Server (附带 Skype Web App 2015 CU6) </span><span class="sxs-lookup"><span data-stu-id="5ce30-140">Skype Web App 2015 CU6 HF2 or higher (ships with Server)</span></span>

### <a name="currently-being-investigated"></a><span data-ttu-id="5ce30-141">当前正在调查</span><span class="sxs-lookup"><span data-stu-id="5ce30-141">Currently being investigated</span></span>

- <span data-ttu-id="5ce30-142">呼叫质量仪表板 (TLS 1.0、1.1 禁用后的新安装，请参阅下面的) \*</span><span class="sxs-lookup"><span data-stu-id="5ce30-142">Call Quality Dashboard (new install after TLS 1.0, 1.1 have been disabled, see below)\*</span></span>
 
### <a name="out-of-scope"></a><span data-ttu-id="5ce30-143">超出范围</span><span class="sxs-lookup"><span data-stu-id="5ce30-143">Out of scope</span></span>

<span data-ttu-id="5ce30-144">除非特别说明，否则以下产品不在 TLS 1.0/1.1 范围内禁用支持，并且不会在 TLS 1.0 和 1.1 已禁用的环境中运行。</span><span class="sxs-lookup"><span data-stu-id="5ce30-144">Except where noted, the following products are not in scope for TLS 1.0/1.1 disable support and will not function in an environment where TLS 1.0 and 1.1 have been disabled.</span></span> <span data-ttu-id="5ce30-145">这意味着：如果你仍然使用作用域外服务器或客户端，则必须更新或删除这些服务器或客户端，如果你需要在 Skype for Business Server 本地部署中的任何位置禁用 TLS 1.0/1.1。</span><span class="sxs-lookup"><span data-stu-id="5ce30-145">What this means: if you still utilize out-of-scope servers or clients, you must update or remove these if you need to disable TLS 1.0/1.1 anywhere in your Skype for Business Server on-premises deployment.</span></span>

- <span data-ttu-id="5ce30-146">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ce30-146">Lync Server 2013</span></span>
- <span data-ttu-id="5ce30-147">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="5ce30-147">Lync Server 2010</span></span>
- <span data-ttu-id="5ce30-148">Windows Server 2008 或更低版本</span><span class="sxs-lookup"><span data-stu-id="5ce30-148">Windows Server 2008 or lower</span></span>
- <span data-ttu-id="5ce30-149">Lync for Mac 2011</span><span class="sxs-lookup"><span data-stu-id="5ce30-149">Lync for Mac 2011</span></span>
- <span data-ttu-id="5ce30-150">Lync 2013 移动版 - iOS、iPad、Android 或 Windows Phone</span><span class="sxs-lookup"><span data-stu-id="5ce30-150">Lync 2013 for Mobile - iOS, iPad, Android or Windows Phone</span></span>
- <span data-ttu-id="5ce30-151">Lync"MX"Windows 应用商店客户端</span><span class="sxs-lookup"><span data-stu-id="5ce30-151">Lync "MX" Windows Store client</span></span>
- <span data-ttu-id="5ce30-152">Lync 会议室 (。。</span><span class="sxs-lookup"><span data-stu-id="5ce30-152">Lync Room System (a.k.a.</span></span> <span data-ttu-id="5ce30-153">SRSv1) 。</span><span class="sxs-lookup"><span data-stu-id="5ce30-153">SRSv1).</span></span> <span data-ttu-id="5ce30-154">LRS 于 2018 年 10 月 9 日终止支持，不会进行更新以支持 TLS 1.2。</span><span class="sxs-lookup"><span data-stu-id="5ce30-154">LRS reached end of support on October 9, 2018 and will not be updated to support TLS 1.2.</span></span>
- <span data-ttu-id="5ce30-155">所有 Lync 2010 客户端</span><span class="sxs-lookup"><span data-stu-id="5ce30-155">All Lync 2010 clients</span></span>
- <span data-ttu-id="5ce30-156">Lync Phone Edition - 此处更新 [了指南](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035)。</span><span class="sxs-lookup"><span data-stu-id="5ce30-156">Lync Phone Edition - updated guidance [here](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035).</span></span>
- <span data-ttu-id="5ce30-157">基于 2013 的 Survivable Branch Appliance (SBA) 或 Survivable Branch Server (SBS) </span><span class="sxs-lookup"><span data-stu-id="5ce30-157">2013 based Survivable Branch Appliance (SBA) or Survivable Branch Server (SBS)</span></span>
- <span data-ttu-id="5ce30-158">云连接器版本 (CCE) </span><span class="sxs-lookup"><span data-stu-id="5ce30-158">Cloud Connector Edition (CCE)</span></span>
- <span data-ttu-id="5ce30-159">Skype for Business for Windows Phone</span><span class="sxs-lookup"><span data-stu-id="5ce30-159">Skype for Business for Windows Phone</span></span>

### <a name="exceptions"></a><span data-ttu-id="5ce30-160">Exceptions</span><span class="sxs-lookup"><span data-stu-id="5ce30-160">Exceptions</span></span>

#### <a name="lync-server-2013"></a><span data-ttu-id="5ce30-161">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ce30-161">Lync Server 2013</span></span>

<span data-ttu-id="5ce30-162">Lync Server 2013 依赖 Windows Fabric 版本 1.0。</span><span class="sxs-lookup"><span data-stu-id="5ce30-162">Lync Server 2013 takes a dependency on Windows Fabric version 1.0.</span></span>  <span data-ttu-id="5ce30-163">在 Lync Server 2013 的设计阶段，为 Windows Fabric 1.0 选择了具有吸引力的新分布式体系结构，以提供复制、高可用性和容错。</span><span class="sxs-lookup"><span data-stu-id="5ce30-163">In the design phase for Lync Server 2013, Windows Fabric 1.0 was chosen for its compelling and new distributed architecture to provide replication, high availability, and fault tolerance.</span></span>  <span data-ttu-id="5ce30-164">随着时间的推移，Skype for Business Server 和 Windows Fabric 都大大改进了这种联合体系结构，在后续版本中进行重大重新设计。</span><span class="sxs-lookup"><span data-stu-id="5ce30-164">Over time, both Skype for Business Server and Windows Fabric have greatly improved this joint architecture with significant re-design in subsequent versions.</span></span>  <span data-ttu-id="5ce30-165">例如，Current Skype for Business 2015 Server 使用 Windows Fabric 3.0。</span><span class="sxs-lookup"><span data-stu-id="5ce30-165">Current Skype for Business 2015 Server uses Windows Fabric 3.0, for example.</span></span>

<span data-ttu-id="5ce30-166">遗憾的是，Windows Fabric 1.0 **不支持 TLS 1.2。 但是，我们将更新 Lync Server 2013 以使用 TLS 1.2。**</span><span class="sxs-lookup"><span data-stu-id="5ce30-166">Unfortunately, Windows Fabric 1.0 **does not support TLS 1.2.  However, we will be updating Lync Server 2013 to work with TLS 1.2**.</span></span> <span data-ttu-id="5ce30-167">这将在 Lync Server 2013 的下一个累积更新中发布。</span><span class="sxs-lookup"><span data-stu-id="5ce30-167">This will be coming in the next Cumulative Update for Lync Server 2013.</span></span>  <span data-ttu-id="5ce30-168">我们提供 TLS 1.2 支持，以实现共存、迁移、联合和混合方案。</span><span class="sxs-lookup"><span data-stu-id="5ce30-168">We're providing TLS 1.2 support to enable co-existence, migration, federation, and hybrid scenarios.</span></span>

<span data-ttu-id="5ce30-169">如果你的组织需要禁用 TLS 1.0 和 1.1，并且你当前使用 Lync Server 2013，我们建议你开始规划过程，你可能必须就地升级或并行迁移 (新池，将用户) 移动到 Skype for Business Server 2015 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="5ce30-169">If your organization is required to disable TLS 1.0 and 1.1, and you currently use Lync Server 2013, we recommend you begin your planning process, with the possibility you may have to In-place upgrade or Side-by-Side migrate (new pools, move users) to Skype for Business Server 2015 or higher.</span></span>  <span data-ttu-id="5ce30-170">或者，你可能希望加速迁移到 Skype for Business Online。</span><span class="sxs-lookup"><span data-stu-id="5ce30-170">Or you may want to accelerate migration to Skype for Business Online.</span></span>

#### <a name="call-quality-dashboard"></a><span data-ttu-id="5ce30-171">通话质量仪表板</span><span class="sxs-lookup"><span data-stu-id="5ce30-171">Call Quality Dashboard</span></span>

<span data-ttu-id="5ce30-172">内部部署呼叫质量仪表板当前依赖于新安装期间 TLS 1.0 (首次安装到本地环境) 。</span><span class="sxs-lookup"><span data-stu-id="5ce30-172">On-Premises Call Quality Dashboard currently has a dependency on TLS 1.0 during new install (first time installing into your On-Premises environments).</span></span>  <span data-ttu-id="5ce30-173">我们目前正在调查此问题，并计划在近期发布修补程序。</span><span class="sxs-lookup"><span data-stu-id="5ce30-173">We are currently investigating this issue and plan to release a fix in the near future.</span></span>  <span data-ttu-id="5ce30-174">如果计划安装 CQD 并同时禁用 TLS 1.0，我们建议您首先完成 CQD 安装，然后继续禁用 TLS 1.0。</span><span class="sxs-lookup"><span data-stu-id="5ce30-174">If you are planning to install CQD and also disable TLS 1.0, we recommend that you complete CQD installation first, and then proceed with TLS 1.0 disabling.</span></span>

#### <a name="skype-for-business-sdn-manager"></a><span data-ttu-id="5ce30-175">Skype for Business SDN 管理器</span><span class="sxs-lookup"><span data-stu-id="5ce30-175">Skype for Business SDN Manager</span></span>

<span data-ttu-id="5ce30-176">使用 Skype for Business SDN 管理器SQL安装期间，数据库依赖于 TLS 1.0。</span><span class="sxs-lookup"><span data-stu-id="5ce30-176">Skype for Business SDN Manager using SQL a database has a dependency on TLS 1.0 during new install.</span></span> <span data-ttu-id="5ce30-177">如果你计划使用 SQL 数据库安装 Skype for Business SDN 管理器并禁用 TLS 1.0，我们建议你首先完成 Skype for Business SDN 管理器，然后继续禁用 TLS 1.0。</span><span class="sxs-lookup"><span data-stu-id="5ce30-177">If you are planning to install Skype for Business SDN Manager using SQL a database and also disable TLS 1.0, we recommend that you complete Skype for Business SDN Manager first, and then proceed with TLS 1.0 disabling.</span></span> <span data-ttu-id="5ce30-178">如果 TLS 1.0 在安装之前被禁用，应在将用于托管 Skype for Business SDN 管理器 SQL 数据库的 SQL Server 后端服务器中临时启用 TLS 1.0。</span><span class="sxs-lookup"><span data-stu-id="5ce30-178">In case TLS 1.0 was disabled prior to installation, you should temporarily enabled TLS 1.0 back in SQL Server backend server that will be used to host Skype for Business SDN Manager SQL database.</span></span>

#### <a name="third-party-devices"></a><span data-ttu-id="5ce30-179">第三方设备</span><span class="sxs-lookup"><span data-stu-id="5ce30-179">Third-party devices</span></span>

<span data-ttu-id="5ce30-180">在 3PIP 电话、视频会议、反向代理和负载平衡器等第三方设备上，请务必验证 TLS 1.2 可支持性、仔细测试并根据需要与供应商联系。</span><span class="sxs-lookup"><span data-stu-id="5ce30-180">On third-party devices such as 3PIP phones, Video conferencing, Reverse Proxies and Load Balancers, be sure to validate TLS 1.2 supportability, test carefully, and contact the vendor if needed.</span></span>

### <a name="federation-considerations-when-disabling-tls-1011-on-edge-servers"></a><span data-ttu-id="5ce30-181">在边缘服务器上禁用 TLS 1.0/1.1 时联盟注意事项</span><span class="sxs-lookup"><span data-stu-id="5ce30-181">Federation considerations when disabling TLS 1.0/1.1 on Edge servers</span></span>

<span data-ttu-id="5ce30-182">必须仔细规划并考虑禁用 TLS 1.0/1.1 对边缘服务器的影响。</span><span class="sxs-lookup"><span data-stu-id="5ce30-182">You must carefully plan for and consider the impact of disabling TLS 1.0/1.1 on your Edge servers.</span></span>  <span data-ttu-id="5ce30-183">禁用 TLS 1.0 和 1.1 后，您可能会发现其他组织无法再与您的组织联盟。</span><span class="sxs-lookup"><span data-stu-id="5ce30-183">Once TLS 1.0 and 1.1 are disabled, you may find that other organizations are no longer be able to federate with your organization.</span></span>

<span data-ttu-id="5ce30-184">您可以选择在边缘服务器上保持启用 TLS 1.0/1.1，以保持与非修补的 (SfB 2015、Lync 2013) 或 (2010) 外部系统的向后兼容性。</span><span class="sxs-lookup"><span data-stu-id="5ce30-184">You may opt to keep TLS 1.0/1.1 enabled on your Edge servers to maintain backward compatibility with non-patched (SfB 2015, Lync 2013) or older (2010) external systems.</span></span>

<span data-ttu-id="5ce30-185">Microsoft 无法提供有关边缘网络网络或任何 (网络是否) PCI 标准的建议或建议;必须由单个公司确定。</span><span class="sxs-lookup"><span data-stu-id="5ce30-185">Microsoft cannot provide advice or recommendations on whether or not your Edge network (or any network) falls under PCI standard; that must be determined by the individual company.</span></span>

<span data-ttu-id="5ce30-186">Skype for Business Online 现在支持 TLS 1.2，因此对与 Online 的混合/联盟没有影响。</span><span class="sxs-lookup"><span data-stu-id="5ce30-186">Skype for Business Online is capable of TLS 1.2 today, so no impact to Hybrid/Federation with Online is expected.</span></span>

<span data-ttu-id="5ce30-187">PIC (Skype) 服务的公共 IM 连接：我们预计禁用 TLS 1.0/1.1 不会影响 Skype [连接](../../deploy/deploy-skype-connectivity.md);Microsoft PIC 网关已经支持 TLS 1.2。</span><span class="sxs-lookup"><span data-stu-id="5ce30-187">PIC (Public IM Connectivity) to Skype Consumer service: We do not expect disabling TLS 1.0/1.1 to impact [Skype Connectivity](../../deploy/deploy-skype-connectivity.md); Microsoft PIC Gateways are already TLS 1.2 capable.</span></span>

## <a name="prerequisites-and-process"></a><span data-ttu-id="5ce30-188">先决条件和过程</span><span class="sxs-lookup"><span data-stu-id="5ce30-188">Prerequisites and process</span></span>

<span data-ttu-id="5ce30-189">除非如上所述，一旦禁用了 TLS 1.0 和 1.1 的作用域外服务器，客户端和设备将可以正常运行，或者甚至会一切正常。</span><span class="sxs-lookup"><span data-stu-id="5ce30-189">Except where noted above, once TLS 1.0 and 1.1 are disabled out-of-scope servers, clients and devices will longer function properly, or at all.</span></span> <span data-ttu-id="5ce30-190">这可能意味着你需要暂停并等待 Microsoft 的更新指导。</span><span class="sxs-lookup"><span data-stu-id="5ce30-190">This may mean you need to pause and wait for updated guidance from Microsoft.</span></span> <span data-ttu-id="5ce30-191">一旦满足所有要求并计划解决差距，请继续。</span><span class="sxs-lookup"><span data-stu-id="5ce30-191">Once you are satisfied that you meet all requirements and have a plan to address gaps, proceed.</span></span>

<span data-ttu-id="5ce30-192">在高级别上，虽然 Skype for Business Server 2019 已准备好安装过程，但 Skype for Business Server 2015 将要求您安装 CU9，将先决条件更新应用到 .NET 和 SQL，部署必备注册表项，最后部署一轮单独的操作系统配置更新 (即通过注册表文件导入) 禁用 TLS 1.0 和 1.1。</span><span class="sxs-lookup"><span data-stu-id="5ce30-192">At a high level, while Skype for Business Server 2019 is ready for procedure at install, Skype for Business Server 2015 will require that you install CU9, applying pre-requisite updates to .NET and SQL, deploying prerequisite registry keys, and finally a separate round of OS configuration updates (i.e. disabling TLS 1.0 and 1.1 via registry file import).</span></span> <span data-ttu-id="5ce30-193">在环境中的任何服务器上禁用 TLS 1.0 和 1.1 之前，完成安装所有必备组件（包括 Skype for Business Server 2015 CU6 版）。这一点非常重要。</span><span class="sxs-lookup"><span data-stu-id="5ce30-193">It is critically important that you complete installation of all prerequisites, including Skype for Business Server 2015 CU6 HF2, prior to disabling TLS 1.0 and 1.1 on any server in your environment.</span></span> <span data-ttu-id="5ce30-194">每个 Skype for Business 服务器（包括边缘角色和SQL后端）都需要更新。</span><span class="sxs-lookup"><span data-stu-id="5ce30-194">Every Skype for Business server, including Edge role and SQL Backends, requires the updates.</span></span> <span data-ttu-id="5ce30-195">此外，请确保所有 (范围内) 客户端已更新为所需的最低版本。</span><span class="sxs-lookup"><span data-stu-id="5ce30-195">Also ensure that all supported (in-scope) clients have been updated to the required minimum versions.</span></span> <span data-ttu-id="5ce30-196">不要忘记更新管理工作站。</span><span class="sxs-lookup"><span data-stu-id="5ce30-196">Don’t forget to update management workstations as well.</span></span>

<span data-ttu-id="5ce30-197">我们希望按照"内部"的常规操作顺序升级 Skype for Business 服务器。</span><span class="sxs-lookup"><span data-stu-id="5ce30-197">We want to follow the usual order of operations of "inside out" for upgrading Skype for Business servers.</span></span> <span data-ttu-id="5ce30-198">以通常相同的方式处理控制器池、持久聊天和配对池。</span><span class="sxs-lookup"><span data-stu-id="5ce30-198">Treat Director pools, Persistent chat, and Paired Pools in the same manner you normally would.</span></span> <span data-ttu-id="5ce30-199">此处和此处介绍了升级[的顺序](topology.md)[和方法](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)。</span><span class="sxs-lookup"><span data-stu-id="5ce30-199">Order and methods for upgrade are covered [here](topology.md) and [here](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span>

### <a name="high-level-process"></a><span data-ttu-id="5ce30-200">高级流程</span><span class="sxs-lookup"><span data-stu-id="5ce30-200">High-level process</span></span>

1. <span data-ttu-id="5ce30-201">在配置生产服务器之前，测试实验室中的所有步骤。</span><span class="sxs-lookup"><span data-stu-id="5ce30-201">Test all steps in your lab prior to configuring production servers.</span></span>
2. <span data-ttu-id="5ce30-202">在每个要更新的每台服务器上备份和保留导出的注册表副本。</span><span class="sxs-lookup"><span data-stu-id="5ce30-202">Back up and preserve a copy of exported registry on each and every individual server to be updated.</span></span> <span data-ttu-id="5ce30-203">不能在服务器之间共享注册表;它们包含基于计算机的唯一密钥。</span><span class="sxs-lookup"><span data-stu-id="5ce30-203">You cannot share registries between servers; they contain unique machine-based keys.</span></span>
3. <span data-ttu-id="5ce30-204">将所有 Skype for Business 2015 服务器升级到 CU9 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="5ce30-204">Upgrade all Skype for Business 2015 servers to CU9 or higher.</span></span> <span data-ttu-id="5ce30-205">对于 Skype for Business Server 2019，请升级到 CU1 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="5ce30-205">For Skype for Business Server 2019, upgrade to CU1 or higher.</span></span>
4. <span data-ttu-id="5ce30-206">将所有必备组件安装到所有服务器。</span><span class="sxs-lookup"><span data-stu-id="5ce30-206">Install all prerequisites to all servers.</span></span>
5. <span data-ttu-id="5ce30-207">部署必备注册表项。</span><span class="sxs-lookup"><span data-stu-id="5ce30-207">Deploy prerequisite registry keys.</span></span>
6. <span data-ttu-id="5ce30-208">确保所有范围内客户端已更新。</span><span class="sxs-lookup"><span data-stu-id="5ce30-208">Ensure that all in-scope clients are updated.</span></span>
7. <span data-ttu-id="5ce30-209">通过注册表导入禁用 TLS 1.0 和 1.1。</span><span class="sxs-lookup"><span data-stu-id="5ce30-209">Disable TLS 1.0 and 1.1 via registry import.</span></span>
8. <span data-ttu-id="5ce30-210">验证工作负荷是否正常工作。</span><span class="sxs-lookup"><span data-stu-id="5ce30-210">Validate that workloads are functioning as expected.</span></span>
    - <span data-ttu-id="5ce30-211">如果遇到问题，请进行故障排除和解决，或者</span><span class="sxs-lookup"><span data-stu-id="5ce30-211">If problems are encountered, troubleshoot and resolve, or</span></span>
    - <span data-ttu-id="5ce30-212">从步骤 2 还原注册表以重新启用 TLS 1.0 和 1.1</span><span class="sxs-lookup"><span data-stu-id="5ce30-212">Restore registry from step 2 to re-enable TLS 1.0 and 1.1</span></span>
9. <span data-ttu-id="5ce30-213">验证是否仅使用了 TLS 1.2。</span><span class="sxs-lookup"><span data-stu-id="5ce30-213">Validate that only TLS 1.2 is being used.</span></span>

### <a name="install-prerequisites-to-all-servers"></a><span data-ttu-id="5ce30-214">将必备组件安装到所有服务器</span><span class="sxs-lookup"><span data-stu-id="5ce30-214">Install prerequisites to all servers</span></span>

<span data-ttu-id="5ce30-215">在开始在 Skype for Business Server 2015 部署的操作系统级别禁用 TLS 1.0 和 1.1 之前，需要进行大量依赖更新。</span><span class="sxs-lookup"><span data-stu-id="5ce30-215">Extensive dependency updating is required before you begin to disable TLS 1.0 and 1.1 at the operating system level in your Skype for Business Server 2015 deployments.</span></span> <span data-ttu-id="5ce30-216">以下是可以支持 TLS 1.2 的最低版本。</span><span class="sxs-lookup"><span data-stu-id="5ce30-216">The following are the minimum versions that can support TLS 1.2.</span></span> <span data-ttu-id="5ce30-217">在开始禁用 TLS 1.0 和 1.1 之前，请部署环境中每个 Skype for Business 服务器的所有必备组件更新。</span><span class="sxs-lookup"><span data-stu-id="5ce30-217">Deploy all prerequisite updates across every Skype for Business server in your environment before you begin disabling TLS 1.0 and 1.1.</span></span>

- <span data-ttu-id="5ce30-218">Skype for Business Server 2015 CU9 6.0.9319.548 (2019 年 5 月) 更高版本</span><span class="sxs-lookup"><span data-stu-id="5ce30-218">Skype for Business Server 2015 CU9 6.0.9319.548 (May 2019) or higher</span></span>
- <span data-ttu-id="5ce30-219">.NET Framework注册表中启用了 SchUseStrongCrypto， ([4.7](https://www.microsoft.com/download/details.aspx?id=55167)或更高版本) </span><span class="sxs-lookup"><span data-stu-id="5ce30-219">[.NET Framework 4.7](https://www.microsoft.com/download/details.aspx?id=55167) or higher with SchUseStrongCrypto enabled in the registry (provided below)</span></span>
- <span data-ttu-id="5ce30-220">SQL Skype for Business 2015 服务器和后端上必须更新。</span><span class="sxs-lookup"><span data-stu-id="5ce30-220">SQL must be updated on all Skype for Business 2015 servers and backends.</span></span> <span data-ttu-id="5ce30-221">首先更新 Enterprise Edition SQL后端，然后更新其各自的 FES。</span><span class="sxs-lookup"><span data-stu-id="5ce30-221">Update Enterprise Edition Pool SQL Backends first, then their respective FEs.</span></span> 
    - <span data-ttu-id="5ce30-222">[SQL Server 2014 SP1 + CU5](https://support.microsoft.com/help/3130926)或更高版本/ SQL Server 2012 SP2 + CU16 或更高版本 / [SQL Server 2014 RTM + CU12](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014)或更高版本 / SQL Server 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="5ce30-222">[SQL Server 2014 SP1 + CU5](https://support.microsoft.com/help/3130926), or higher / SQL Server 2012 SP2 + CU16 or higher / [SQL Server 2014 RTM + CU12](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014), or higher / SQL Server 2014 SP2</span></span>
     - [<span data-ttu-id="5ce30-223">SQL Server 2012 SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="5ce30-223">SQL Server Native Client for SQL Server 2012</span></span>](https://www.microsoft.com/download/details.aspx?id=50402)
     - <span data-ttu-id="5ce30-224">[Microsoft ODBC Driver 11 for SQL Server](https://www.microsoft.com/download/details.aspx?id=36434)或更高版本</span><span class="sxs-lookup"><span data-stu-id="5ce30-224">[Microsoft ODBC Driver 11 for SQL Server](https://www.microsoft.com/download/details.aspx?id=36434), or higher</span></span>
     - [<span data-ttu-id="5ce30-225">SQL Server 2014 SP2 的共享管理对象</span><span class="sxs-lookup"><span data-stu-id="5ce30-225">Shared Management Objects for SQL Server 2014 SP2</span></span>](https://www.microsoft.com/download/details.aspx?id=53164)
     - [<span data-ttu-id="5ce30-226">SQLSysClrTypes for SQL server 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="5ce30-226">SQLSysClrTypes for SQL server 2014 SP2</span></span>](https://www.microsoft.com/download/details.aspx?id=42295)

### <a name="basic-steps-to-install-pre-requisites-in-recommended-order-of-operations"></a><span data-ttu-id="5ce30-227">按建议的操作顺序安装先决条件的基本步骤</span><span class="sxs-lookup"><span data-stu-id="5ce30-227">Basic steps to install pre-requisites, in recommended order of operations</span></span>

1. <span data-ttu-id="5ce30-228">将 Skype for Business Server CU9 更新安装到所有服务器。</span><span class="sxs-lookup"><span data-stu-id="5ce30-228">Install the Skype for Business Server CU9 update to all servers.</span></span> 
    1. <span data-ttu-id="5ce30-229">使用更新程序将更新安装到组件。</span><span class="sxs-lookup"><span data-stu-id="5ce30-229">Install the update to components using the updater.</span></span>
    2. <span data-ttu-id="5ce30-230">根据记录的过程更新数据库。</span><span class="sxs-lookup"><span data-stu-id="5ce30-230">Update databases according to documented procedures.</span></span> <span data-ttu-id="5ce30-231">对于 Skype for Business Server 2015，请参阅 KB [3061064。](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)</span><span class="sxs-lookup"><span data-stu-id="5ce30-231">For Skype for Business Server 2015, see KB [3061064](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span>
    3. <span data-ttu-id="5ce30-232">在推进任何其他更改之前，验证部署中的产品功能。</span><span class="sxs-lookup"><span data-stu-id="5ce30-232">Validate product functionality in the deployment prior to moving forward with any other changes.</span></span>
2. <span data-ttu-id="5ce30-233">下载 .NET 4.7 脱机安装程序。</span><span class="sxs-lookup"><span data-stu-id="5ce30-233">Download .NET 4.7 Offline Installer.</span></span> 
    1. <span data-ttu-id="5ce30-234">参考： [https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)</span><span class="sxs-lookup"><span data-stu-id="5ce30-234">Reference: [https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)</span></span>
    2. <span data-ttu-id="5ce30-235">确保前端服务器上已停止 Skype for Business Server 2015 服务。</span><span class="sxs-lookup"><span data-stu-id="5ce30-235">Ensure that Skype for Business Server 2015 services are stopped on the Front End server.</span></span>
    3. <span data-ttu-id="5ce30-236">参考： [https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)</span><span class="sxs-lookup"><span data-stu-id="5ce30-236">Reference: [https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)</span></span>
    4. <span data-ttu-id="5ce30-237">例如 (Standard Edition) ： ```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="5ce30-237">Ex (Standard Edition): ```Stop-CsWindowsService```</span></span>
    5. <span data-ttu-id="5ce30-238">Ex (Enterprise Edition) ： ```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="5ce30-238">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    6. <span data-ttu-id="5ce30-239">运行安装程序程序包。</span><span class="sxs-lookup"><span data-stu-id="5ce30-239">Run the installer package.</span></span>
    7. <span data-ttu-id="5ce30-240">请重新启动服务器。</span><span class="sxs-lookup"><span data-stu-id="5ce30-240">Reboot the server.</span></span>
3. <span data-ttu-id="5ce30-241">在所有SQL更新 SQL Express 2014。</span><span class="sxs-lookup"><span data-stu-id="5ce30-241">Update SQL Express 2014 on all servers.</span></span> 
    1. <span data-ttu-id="5ce30-242">参考： [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span><span class="sxs-lookup"><span data-stu-id="5ce30-242">Reference: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span></span>
    2. <span data-ttu-id="5ce30-243">下载 SQL 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="5ce30-243">Download SQL 2014 SP2</span></span> 
        - <span data-ttu-id="5ce30-244">参考： [https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)</span><span class="sxs-lookup"><span data-stu-id="5ce30-244">Reference: [https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)</span></span>
    3. <span data-ttu-id="5ce30-245">将安装媒体复制到服务器上文件夹 (例如：C：\01_2014SqlSp2) </span><span class="sxs-lookup"><span data-stu-id="5ce30-245">Copy the installation media to a folder on the server (Ex: C:\01_2014SqlSp2)</span></span>
    4. <span data-ttu-id="5ce30-246">确保前端服务器上已停止 Skype for Business Server 2015 服务</span><span class="sxs-lookup"><span data-stu-id="5ce30-246">Ensure Skype for Business Server 2015 services are stopped on the Front End server</span></span> 
        - <span data-ttu-id="5ce30-247">例如 (Standard Edition) ： ```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="5ce30-247">Ex (Standard Edition): ```Stop-CsWindowsService```</span></span>
        - <span data-ttu-id="5ce30-248">Ex (Enterprise Edition) ： ```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="5ce30-248">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    5. <span data-ttu-id="5ce30-249">打开管理员命令提示符，并升级所有已安装的组件和实例</span><span class="sxs-lookup"><span data-stu-id="5ce30-249">Open an Admin Command Prompt, and upgrade all installed components and instances</span></span> 
        - <span data-ttu-id="5ce30-250">示例：C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe /qs /IAcceptSQLServerLicenseTerms /Action=Patch /AllInstances</span><span class="sxs-lookup"><span data-stu-id="5ce30-250">Example: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe /qs /IAcceptSQLServerLicenseTerms /Action=Patch /AllInstances</span></span>
4. <span data-ttu-id="5ce30-251">更新 SQL Native Client。</span><span class="sxs-lookup"><span data-stu-id="5ce30-251">Update SQL Native Client.</span></span> 
    1. <span data-ttu-id="5ce30-252">参考 [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server) ：。</span><span class="sxs-lookup"><span data-stu-id="5ce30-252">Reference: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server).</span></span>
    2. <span data-ttu-id="5ce30-253">下载自 [https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)</span><span class="sxs-lookup"><span data-stu-id="5ce30-253">Download from [https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)</span></span>
    3. <span data-ttu-id="5ce30-254">确保前端服务器上已停止 Skype for Business Server 2015 服务。</span><span class="sxs-lookup"><span data-stu-id="5ce30-254">Ensure Skype for Business Server 2015 services are stopped on the Front End server.</span></span> 
        - <span data-ttu-id="5ce30-255">例如 (Standard Edition) ： ```Stop-CsWindowsServices```</span><span class="sxs-lookup"><span data-stu-id="5ce30-255">Ex (Standard Edition): ```Stop-CsWindowsServices```</span></span>
        - <span data-ttu-id="5ce30-256">Ex (Enterprise Edition) ： ```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="5ce30-256">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    4. <span data-ttu-id="5ce30-257">停止SQL安装的实例运行</span><span class="sxs-lookup"><span data-stu-id="5ce30-257">Stop the SQL instances installed from running</span></span> 
        - <span data-ttu-id="5ce30-258">例如： ```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="5ce30-258">Ex: ```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```</span></span>
        - <span data-ttu-id="5ce30-259">例如： ```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="5ce30-259">Ex: ```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```</span></span>
        - <span data-ttu-id="5ce30-260">仅 (Standard Edition) ： ```Get-Service 'MSSQL$RTC' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="5ce30-260">Ex (Standard Edition Only): ```Get-Service 'MSSQL$RTC' | Stop-Service```</span></span>
    5. <span data-ttu-id="5ce30-261">安装该更新。</span><span class="sxs-lookup"><span data-stu-id="5ce30-261">Install the update.</span></span>
5. <span data-ttu-id="5ce30-262">更新 ODBC Driver 11 for SQL Server以包含对 TLS 1.2 (KB [3135244](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)) 。</span><span class="sxs-lookup"><span data-stu-id="5ce30-262">Update ODBC Driver 11 for SQL Server to include support for TLS 1.2 (KB [3135244](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)).</span></span>
    1. <span data-ttu-id="5ce30-263">下载 [ODBC Driver 11 for SQL Server - Windows](https://www.microsoft.com/download/confirmation.aspx?id=36434)。</span><span class="sxs-lookup"><span data-stu-id="5ce30-263">Download [ODBC Driver 11 for SQL Server - Windows](https://www.microsoft.com/download/confirmation.aspx?id=36434).</span></span>
    2. <span data-ttu-id="5ce30-264">确保前端服务器上已停止 Skype for Business Server 2015 服务。</span><span class="sxs-lookup"><span data-stu-id="5ce30-264">Ensure that Skype for Business Server 2015 services are stopped on the Front End server.</span></span>
        - <span data-ttu-id="5ce30-265">Standard Edition (示例) ： ```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="5ce30-265">Example (Standard Edition): ```Stop-CsWindowsService```</span></span>
        - <span data-ttu-id="5ce30-266">Enterprise Edition (示例) ： ```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="5ce30-266">Example (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    3. <span data-ttu-id="5ce30-267">安装该更新。</span><span class="sxs-lookup"><span data-stu-id="5ce30-267">Install the update.</span></span>
6. <span data-ttu-id="5ce30-268">部署必备注册表项。</span><span class="sxs-lookup"><span data-stu-id="5ce30-268">Deploy prerequisite registry keys.</span></span>

### <a name="pre-requisite-registry-keys"></a><span data-ttu-id="5ce30-269">先决条件注册表项</span><span class="sxs-lookup"><span data-stu-id="5ce30-269">Pre-requisite registry keys</span></span>

<span data-ttu-id="5ce30-270">将以下测试复制/粘贴到记事本中，重命名 TLSPreReq.reg 或你选择的名称，然后导入：</span><span class="sxs-lookup"><span data-stu-id="5ce30-270">Copy/paste the following test into Notepad and rename TLSPreReq.reg or a name of your choice, then import:</span></span>

```console
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\v2.0.50727]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\v4.0.30319]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v2.0.50727]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v4.0.30319]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp]

"DefaultSecureProtocols"=dword:00000AA0

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp]

"DefaultSecureProtocols"=dword:00000AA0

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2\Client]

"DisabledByDefault"=dword:00000000

"Enabled"=dword:00000001

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2\Server]

"DisabledByDefault"=dword:00000000

"Enabled"=dword:00000001
```

<span data-ttu-id="5ce30-271">对于SQL池的后端，先决条件和 TLS 禁用应视为任何SQL或操作系统更新;引用： [https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)</span><span class="sxs-lookup"><span data-stu-id="5ce30-271">For SQL back ends for Enterprise Edition Pools, prerequisites and TLS disable should be treated as any SQL or OS updates would; refer to: [https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)</span></span>

<span data-ttu-id="5ce30-272">尽管必备组件应用程序和 TLS 禁用步骤可以组合使用，但我们强烈建议先应用所有先决条件，然后再在操作系统级别禁用 TLS 1.0 和 1.1。</span><span class="sxs-lookup"><span data-stu-id="5ce30-272">While both the prerequisite application and TLS disabling steps can be combined, we strongly recommend all prerequisites be applied before proceeding with disabling of TLS 1.0 and 1.1 at the operating system level.</span></span> <span data-ttu-id="5ce30-273">最佳实践方法是：部署所有必备组件，验证工作负荷是否按预期正常运行，然后稍后继续禁用 TLS 1.0/1.1。</span><span class="sxs-lookup"><span data-stu-id="5ce30-273">The best practice approach would be to prepare the environment by deploying all prerequisites, validating that workloads all function correctly and as expected, and then proceeding with TLS 1.0/1.1 disable at a later time.</span></span>

### <a name="disable-tls-10-and-11-via-registry-import"></a><span data-ttu-id="5ce30-274">通过注册表导入禁用 TLS 1.0 和 1.1</span><span class="sxs-lookup"><span data-stu-id="5ce30-274">Disable TLS 1.0 and 1.1 via registry import</span></span>

<span data-ttu-id="5ce30-275">继续执行下一步之前，请确保已完成所有先决条件和更新 *的 Skype for Business 服务器*。</span><span class="sxs-lookup"><span data-stu-id="5ce30-275">Before you proceed with the next steps, *make sure you have completed all prerequisites and updated Skype for Business Servers*.</span></span>

<span data-ttu-id="5ce30-276">将以下文本复制到记事本文件中，并将其重命名为 **TLSDisable.reg**：</span><span class="sxs-lookup"><span data-stu-id="5ce30-276">Copy the following text into a Notepad file and rename it **TLSDisable.reg**:</span></span>

```console
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Cryptography\Configuration\SSL\00010002]

"Functions"="TLS_ECDHE_ECDSA_WITH_AES_256_GCM_SHA384_P384,TLS_ECDHE_ECDSA_WITH_AES_128_GCM_SHA256_P256,TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384_P384,TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256_P256,TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA384_P384,TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA256_P256,TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384_P384,TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256_P256,TLS_RSA_WITH_AES_256_GCM_SHA384,TLS_RSA_WITH_AES_128_GCM_SHA256,TLS_RSA_WITH_AES_256_CBC_SHA256,TLS_RSA_WITH_AES_128_CBC_SHA256"

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL]

"AllowInsecureRenegoClients"=dword:00000000

"AllowInsecureRenegoServers"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\AES 128/128]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\AES 256/256]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\DES 56/56]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\NULL]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 128/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 40/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 56/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 56/56]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 128/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 40/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 56/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 64/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\Triple DES 168]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\MD5]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA256]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA384]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA512]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms\Diffie-Hellman]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms\ECDH]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms\PKCS]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\Multi-Protocol Unified Hello]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\Multi-Protocol Unified Hello\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\Multi-Protocol Unified Hello\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\PCT 1.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\PCT 1.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\PCT 1.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 2.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 2.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 2.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 3.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 3.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 3.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.1]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.1\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.1\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000
```

<span data-ttu-id="5ce30-277">在要禁用 TLS 1.0 和 1.1 的每个服务器上导入 .reg 文件。</span><span class="sxs-lookup"><span data-stu-id="5ce30-277">Import the .reg file on each server you wish to disable TLS 1.0 and 1.1.</span></span> <span data-ttu-id="5ce30-278">请重新启动服务器。</span><span class="sxs-lookup"><span data-stu-id="5ce30-278">Reboot the server.</span></span> <span data-ttu-id="5ce30-279">服务重新联机后，移动到下一台服务器。</span><span class="sxs-lookup"><span data-stu-id="5ce30-279">Once the services have come back online, move to the next server.</span></span> <span data-ttu-id="5ce30-280">Enterprise Edition Pools 的方法与用于任何操作系统更新的方法相同。</span><span class="sxs-lookup"><span data-stu-id="5ce30-280">The approach for Enterprise Edition Pools is the same you would take for any OS update.</span></span>

<span data-ttu-id="5ce30-281">你可能已经注意到，我们所做的不仅仅是在此处禁用 TLS 1.0 和 1.1。</span><span class="sxs-lookup"><span data-stu-id="5ce30-281">You may have noticed we are doing more than just disabling TLS 1.0 and 1.1 here.</span></span> <span data-ttu-id="5ce30-282">我们支持加密套件重新排序 (如上所示) 禁用一些旧的弱密码。</span><span class="sxs-lookup"><span data-stu-id="5ce30-282">We are supporting Cipher Suite re-order (as shown above) and the disabling of some older weak ciphers.</span></span> <span data-ttu-id="5ce30-283">这是我们第一次正式支持对 Skype for Business Server 上的 SCHANNEL 和加密 API 的这些更改，需要注意的是，这些更改是唯一支持并且目前已经过测试的更改。</span><span class="sxs-lookup"><span data-stu-id="5ce30-283">This is the first time we have officially supported these changes to SCHANNEL and Crypto API on Skype for Business Server, and it is important to note that these changes are the only ones we support and have tested at this time.</span></span> <span data-ttu-id="5ce30-284">我们将来可能会考虑其他配置，但现在请不要在你的实现中修改注册表导入文件。</span><span class="sxs-lookup"><span data-stu-id="5ce30-284">We may consider additional configurations in the future, but for now, please do not modify the registry import file in your implementation.</span></span>

### <a name="validate-that-workloads-are-functioning-as-expected"></a><span data-ttu-id="5ce30-285">验证工作负荷是否正常工作</span><span class="sxs-lookup"><span data-stu-id="5ce30-285">Validate that workloads are functioning as expected</span></span>

<span data-ttu-id="5ce30-286">在环境中禁用 TLS 1.0 和 1.1 后，请确保所有主工作负荷均正常运行，如 IM & Presence、P2P 呼叫、企业语音 等。</span><span class="sxs-lookup"><span data-stu-id="5ce30-286">Once TLS 1.0 and 1.1 have been disabled in your environment, ensure that all your main workloads are functioning as expected, such as IM & Presence, P2P calls, Enterprise Voice, etc.</span></span>

<span data-ttu-id="5ce30-287">**仅验证是否使用了 TLS 1.2**</span><span class="sxs-lookup"><span data-stu-id="5ce30-287">**Validate only TLS 1.2 is being used**</span></span>

<span data-ttu-id="5ce30-288">让安全团队对 Skype for Business 流量执行新的审核，以确保不再使用较旧的协议 TLS 1.0 和 1.1。</span><span class="sxs-lookup"><span data-stu-id="5ce30-288">Have your Security Team perform a new audit of Skype for Business traffic to ensure that the older protocols TLS 1.0 and 1.1 are no longer in use.</span></span>

<span data-ttu-id="5ce30-289">或者，在 TLS 1.0 和 TLS 1.1 禁用后，Internet Explorer测试从 Skype for Business Server 2015 到 Web 服务的 TLS 连接。</span><span class="sxs-lookup"><span data-stu-id="5ce30-289">Alternatively, you can use Internet Explorer to test TLS connections to web services from Skype for Business Server 2015 after TLS 1.0 and TLS 1.1 have been disabled.</span></span>

1. <span data-ttu-id="5ce30-290">启动Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="5ce30-290">Launch Internet Explorer.</span></span>
2. <span data-ttu-id="5ce30-291">选择 **"工具**  >  **""Internet 选项"。**</span><span class="sxs-lookup"><span data-stu-id="5ce30-291">Select **Tools** > **Internet Options**.</span></span>
3. <span data-ttu-id="5ce30-292">选择" **高级"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="5ce30-292">Select the **Advanced** tab.</span></span>
4. <span data-ttu-id="5ce30-293">在 **"设置"** 下，滚动到底部。</span><span class="sxs-lookup"><span data-stu-id="5ce30-293">Under **Settings**, scroll to the bottom.</span></span>
5. <span data-ttu-id="5ce30-294">验证是否已启用 TLS 1.0、TLS 1.1 和 TLS 1.2。</span><span class="sxs-lookup"><span data-stu-id="5ce30-294">Verify that TLS 1.0, TLS 1.1, and TLS 1.2 are enabled.</span></span>
6. <span data-ttu-id="5ce30-295">浏览 SfB 2015 池的内部 Web 服务 URL， (连接成功) 。</span><span class="sxs-lookup"><span data-stu-id="5ce30-295">Browse the Internal Web Service URL of your SfB 2015 pool (should connect successfully).</span></span>
7. <span data-ttu-id="5ce30-296">返回到"Internet Explorer并禁用"仅 **使用 TLS 1.2"** 选项。</span><span class="sxs-lookup"><span data-stu-id="5ce30-296">Go back into Internet Explorer and disable the option to **Use TLS 1.2** only.</span></span>
8. <span data-ttu-id="5ce30-297">再次浏览 SfB 2015 池的内部 Web 服务 URL， (无法连接到) 。</span><span class="sxs-lookup"><span data-stu-id="5ce30-297">Browse the Internal Web Service URL of your SfB 2015 pool again (should fail to connect).</span></span>

![Internet 选项](../../media/internet-options.jpg)

## <a name="advanced-deployment-scenarios"></a><span data-ttu-id="5ce30-299">高级部署方案</span><span class="sxs-lookup"><span data-stu-id="5ce30-299">Advanced deployment scenarios</span></span>

<span data-ttu-id="5ce30-300">由于在 Skype for Business Server 2015 中支持 TLS 1.2 需要某些依赖项先决条件，因此在已禁用 TLS 1.0 和 1.1 的任何系统上，从 RTM 媒体进行安装将失败。</span><span class="sxs-lookup"><span data-stu-id="5ce30-300">Because some dependency prerequisites are required to support TLS 1.2 in Skype for Business Server 2015, installing from RTM media will fail on any system where TLS 1.0 and 1.1 have been disabled.</span></span>

<span data-ttu-id="5ce30-301">**在环境中禁用 TLS 1.0 和 1.1 后部署新的 Standard Edition 服务器或 Enterprise Edition 池。**</span><span class="sxs-lookup"><span data-stu-id="5ce30-301">**Deploying New Standard Edition Servers or Enterprise Edition Pools once TLS 1.0 and 1.1 have been disabled in your environment.**</span></span>

<span data-ttu-id="5ce30-302">**选项 1：** 使用 [SmartSetup](../../deploy/install/install-skype-for-business-server.md)。</span><span class="sxs-lookup"><span data-stu-id="5ce30-302">**Option 1:** Use [SmartSetup](../../deploy/install/install-skype-for-business-server.md).</span></span> <span data-ttu-id="5ce30-303">请注意，我们将更新 SmartSetup 以适应SQL CU 中更新的二进制文件，并在将来更新本文。</span><span class="sxs-lookup"><span data-stu-id="5ce30-303">Note that we are updating SmartSetup to accommodate the updated SQL binaries in a future CU, and will update this article in the future.</span></span>

<span data-ttu-id="5ce30-304">**选项 2：** 在 RTCLOCAL SQL LYNCLOCAL (预安装本地) </span><span class="sxs-lookup"><span data-stu-id="5ce30-304">**Option 2:** Pre-install local SQL instances (RTCLOCAL and LYNCLOCAL)</span></span>

1. <span data-ttu-id="5ce30-305">下载并复制 SQL Express 2014 SP2 (SQLEXPR_x64.exe) FE 上的本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="5ce30-305">Download and copy SQL Express 2014 SP2 (SQLEXPR_x64.exe) to local folder on FE.</span></span> <span data-ttu-id="5ce30-306">假设文件夹路径为 <SQL_FOLDER_PATH>。</span><span class="sxs-lookup"><span data-stu-id="5ce30-306">Let’s say folder path <SQL_FOLDER_PATH>.</span></span>
2. <span data-ttu-id="5ce30-307">启动 PowerShell 或命令提示符并导航到 <SQL_FOLDER_PATH>。</span><span class="sxs-lookup"><span data-stu-id="5ce30-307">Launch PowerShell or Command Prompt and navigate to <SQL_FOLDER_PATH>.</span></span>
3. <span data-ttu-id="5ce30-308">通过运行以下SQL创建 RTCLOCAL 实例。</span><span class="sxs-lookup"><span data-stu-id="5ce30-308">Create the RTCLOCAL SQL instance by running the command below.</span></span> <span data-ttu-id="5ce30-309">请等待SQLEXPR_x64.exe完成，然后再继续：</span><span class="sxs-lookup"><span data-stu-id="5ce30-309">Wait until SQLEXPR_x64.exe finishes before proceeding:</span></span>

    <span data-ttu-id="5ce30-310">SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine，Tools /INSTANCENAME=RTCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT=1 "NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automati</span><span class="sxs-lookup"><span data-stu-id="5ce30-310">SQLEXPR_x64.exe  /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=RTCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automati</span></span>
1. <span data-ttu-id="5ce30-311">通过运行SQL创建 LYNCLOCAL 实例。</span><span class="sxs-lookup"><span data-stu-id="5ce30-311">Create the LYNCLOCAL SQL instance by running the command below.</span></span> <span data-ttu-id="5ce30-312">请等待SQLEXPR_x64.exe完成，然后再继续下一步：</span><span class="sxs-lookup"><span data-stu-id="5ce30-312">Wait until SQLEXPR_x64.exe finishes before proceeding to the next step:</span></span>

    <span data-ttu-id="5ce30-313">SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine，Tools /INSTANCENAME=LYNCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT=1 "NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automatic</span><span class="sxs-lookup"><span data-stu-id="5ce30-313">SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=LYNCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automatic</span></span>
1. <span data-ttu-id="5ce30-314">运行 Skype for Business Server 2015 RTM 安装程序。</span><span class="sxs-lookup"><span data-stu-id="5ce30-314">Run Skype for Business Server 2015 RTM setup.</span></span>
2. <span data-ttu-id="5ce30-315">按照上述先决条件部分中的其余步骤操作。</span><span class="sxs-lookup"><span data-stu-id="5ce30-315">Follow the remaining steps from the prerequisites section above.</span></span>

<span data-ttu-id="5ce30-316">**选项 3：** 还可以手动替换本地安装媒体目录中的二进制文件，如下所示：</span><span class="sxs-lookup"><span data-stu-id="5ce30-316">**Option 3:** You may also manually replace binaries in a local installation media directory as follows:</span></span>

1. [<span data-ttu-id="5ce30-317">安装 Skype for Business Server 的先决条件</span><span class="sxs-lookup"><span data-stu-id="5ce30-317">Install prerequisites for Skype for Business Server</span></span>](../../deploy/install/install-prerequisites.md)  
2. <span data-ttu-id="5ce30-318">安装 .NET 4.7：</span><span class="sxs-lookup"><span data-stu-id="5ce30-318">Install .NET 4.7:</span></span> 
      - <span data-ttu-id="5ce30-319">**注意：** 我们首先在 Skype for Business Server 2015 CU5 (6.0.9319.281 中引入了对 .NET 4.7 的支持) 。</span><span class="sxs-lookup"><span data-stu-id="5ce30-319">**Note:** We first introduced support for .NET 4.7 in Skype for Business Server 2015 CU5 (6.0.9319.281).</span></span> <span data-ttu-id="5ce30-320">因此，在下面的步骤中，我们将在主要安装之前更新核心组件。</span><span class="sxs-lookup"><span data-stu-id="5ce30-320">Therefore, in later steps below we will be updating Core Components prior to the main install.</span></span>
      - <span data-ttu-id="5ce30-321">下载 https://www.microsoft.com/download/details.aspx?id=55167 ：。</span><span class="sxs-lookup"><span data-stu-id="5ce30-321">Download: https://www.microsoft.com/download/details.aspx?id=55167.</span></span> 
      - <span data-ttu-id="5ce30-322">参考 [：应在 Skype for Business Server 2015 部署之前安装的软件](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)</span><span class="sxs-lookup"><span data-stu-id="5ce30-322">Reference: [Software that should be installed before a Skype for Business Server 2015 deployment](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)</span></span>
3. <span data-ttu-id="5ce30-323">复制 ISO 文件/文件夹：</span><span class="sxs-lookup"><span data-stu-id="5ce30-323">Copy ISO Files/Folders:</span></span> 
    - <span data-ttu-id="5ce30-324">附加 Skype for Business Server 2015 ISO 后，在文件资源管理器中打开作为 ex： D： (附件的驱动器 \) 的根目录。</span><span class="sxs-lookup"><span data-stu-id="5ce30-324">With the Skype for Business Server 2015 ISO attached, open the root directory of the drive it is attached as (Ex: D:\) in File Explorer.</span></span>
    - <span data-ttu-id="5ce30-325">将所有文件夹和文件复制到本地磁盘上的文件夹 (例如：C：\SkypeForBusiness2015ISO) 。</span><span class="sxs-lookup"><span data-stu-id="5ce30-325">Copy all folders and files to a folder on a local disk (Ex: C:\SkypeForBusiness2015ISO).</span></span>
    - <span data-ttu-id="5ce30-326">**注意：** 在安装组件之前，需要更新某些文件以支持 TLS 1.2。</span><span class="sxs-lookup"><span data-stu-id="5ce30-326">**Note:** Prior to installing components, some files will need to be updated for support of TLS 1.2.</span></span>
4. <span data-ttu-id="5ce30-327">替换 MSI/EXE 包：</span><span class="sxs-lookup"><span data-stu-id="5ce30-327">Replace MSI/EXE Packages:</span></span> 
    - <span data-ttu-id="5ce30-328">替换本地计算机上安装媒体的 /Setup/amd64/ 文件夹中的现有 MSI 和 EXE 包。</span><span class="sxs-lookup"><span data-stu-id="5ce30-328">Replace the existing MSI and EXE packages in the /Setup/amd64/ folder of the installation media on the local machine.</span></span>
    - <span data-ttu-id="5ce30-329">SQL 2014 SP2 Express： https://www.microsoft.com/download/details.aspx?id=53167</span><span class="sxs-lookup"><span data-stu-id="5ce30-329">SQL 2014 SP2 Express: https://www.microsoft.com/download/details.aspx?id=53167</span></span> 
        - <span data-ttu-id="5ce30-330">重命名为SQLEXPR_x64本地计算机上，并替换安装媒体的 Setup/amd64/ 文件夹中的现有文件。</span><span class="sxs-lookup"><span data-stu-id="5ce30-330">Rename to SQLEXPR_x64 on the local machine, and replace the existing file in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="5ce30-331">SQL本机客户端： https://www.microsoft.com/download/details.aspx?id=50402</span><span class="sxs-lookup"><span data-stu-id="5ce30-331">SQL Native Client: https://www.microsoft.com/download/details.aspx?id=50402</span></span> 
        - <span data-ttu-id="5ce30-332">**注意：** 如有必要，重命名sqlncli.msi，然后替换安装媒体的 Setup/amd64/ 文件夹中的现有文件。</span><span class="sxs-lookup"><span data-stu-id="5ce30-332">**Note:** Rename this if necessary to sqlncli.msi, and then replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="5ce30-333">SQL管理对象： https://www.microsoft.com/download/details.aspx?id=53164</span><span class="sxs-lookup"><span data-stu-id="5ce30-333">SQL Management Objects: https://www.microsoft.com/download/details.aspx?id=53164</span></span> 
        - <span data-ttu-id="5ce30-334">**注意：** 功能包中将包含许多可下载的项目。</span><span class="sxs-lookup"><span data-stu-id="5ce30-334">**Note:** The Feature pack will have a lot of items that can be downloaded.</span></span> <span data-ttu-id="5ce30-335">选择以仅SharedManagementObjects.msi下载。</span><span class="sxs-lookup"><span data-stu-id="5ce30-335">Select to download SharedManagementObjects.msi only.</span></span>
        - <span data-ttu-id="5ce30-336">**注意：** 替换安装媒体的 Setup/amd64/ 文件夹中的现有文件。</span><span class="sxs-lookup"><span data-stu-id="5ce30-336">**Note:** Replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="5ce30-337">SQL CLR 类型： https://www.microsoft.com/download/details.aspx?id=53164</span><span class="sxs-lookup"><span data-stu-id="5ce30-337">SQL CLR Types: https://www.microsoft.com/download/details.aspx?id=53164</span></span> 
        - <span data-ttu-id="5ce30-338">**注意：** 功能包中将包含许多可下载的项目。</span><span class="sxs-lookup"><span data-stu-id="5ce30-338">**Note:** The Feature pack will have a lot of items that can be downloaded.</span></span> <span data-ttu-id="5ce30-339">选择以仅CQLSysClrTypes.msi下载</span><span class="sxs-lookup"><span data-stu-id="5ce30-339">Select to download CQLSysClrTypes.msi only</span></span>
        - <span data-ttu-id="5ce30-340">**注意**：替换安装媒体的 Setup/amd64/ 文件夹中的现有文件。</span><span class="sxs-lookup"><span data-stu-id="5ce30-340">**Note**: Replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
5. <span data-ttu-id="5ce30-341">安装核心组件：</span><span class="sxs-lookup"><span data-stu-id="5ce30-341">Install Core Components:</span></span> 
    - <span data-ttu-id="5ce30-342">从Setup.exe的 Setup/amd64/ 文件夹中运行安装程序。</span><span class="sxs-lookup"><span data-stu-id="5ce30-342">Run Setup.exe from the Setup/amd64/ folder of the installation media.</span></span> <span data-ttu-id="5ce30-343">按照说明安装核心组件</span><span class="sxs-lookup"><span data-stu-id="5ce30-343">Follow the instructions to install Core Components</span></span>
    - <span data-ttu-id="5ce30-344">关闭核心组件。</span><span class="sxs-lookup"><span data-stu-id="5ce30-344">Close Core Components.</span></span>
6. <span data-ttu-id="5ce30-345">更新核心组件：</span><span class="sxs-lookup"><span data-stu-id="5ce30-345">Update Core Components:</span></span> 
    - <span data-ttu-id="5ce30-346">下载 Skype for Business 更新安装程序。</span><span class="sxs-lookup"><span data-stu-id="5ce30-346">Download the Skype for Business Update Installer.</span></span>
    - <span data-ttu-id="5ce30-347">运行安装程序以更新核心组件并安装性能计数器。</span><span class="sxs-lookup"><span data-stu-id="5ce30-347">Run the installer to update Core Components and install the performance counters.</span></span>
    - <span data-ttu-id="5ce30-348">**注意：** 自 CU6HF2 发布起，自动更新功能当前仅安装 CU6。</span><span class="sxs-lookup"><span data-stu-id="5ce30-348">**Note:** As of the release of CU6HF2, the auto-update feature currently only will install up to CU6.</span></span> <span data-ttu-id="5ce30-349">因此，更新程序必须单独运行，以将核心组件更新为 6.0.9319.516。</span><span class="sxs-lookup"><span data-stu-id="5ce30-349">Therefore, the updater must be run separately to update Core Components to 6.0.9319.516.</span></span>
    - <span data-ttu-id="5ce30-350">参考： https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015</span><span class="sxs-lookup"><span data-stu-id="5ce30-350">Reference: https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015</span></span>
7. <span data-ttu-id="5ce30-351">安装管理工具 (可选) ：</span><span class="sxs-lookup"><span data-stu-id="5ce30-351">Install Administrative Tools (Optional):</span></span> 
    - <span data-ttu-id="5ce30-352">这将使用更新的文件安装 Microsoft SQL Server 2012 Native Client、SQL Server 2014 Management Objects (x64) 和适用于 SQL Server 2014 (x64) 的 Microsoft System CLR 类型。</span><span class="sxs-lookup"><span data-stu-id="5ce30-352">This will install the Microsoft SQL Server 2012 Native Client, SQL Server 2014 Management Objects (x64), and Microsoft System CLR Types for SQL Server 2014 (x64) using the updated files.</span></span> <span data-ttu-id="5ce30-353">此外，本地计算机上还将提供 Skype for Business Server 2015 拓扑生成器和控制面板。</span><span class="sxs-lookup"><span data-stu-id="5ce30-353">Additionally, the Skype for Business Server 2015 Topology Builder and Control Panel will be available on the local machine.</span></span>
8. <span data-ttu-id="5ce30-354">安装本地配置存储 (步骤 1) ：</span><span class="sxs-lookup"><span data-stu-id="5ce30-354">Install Local Configuration Store (Step 1):</span></span> 
     - <span data-ttu-id="5ce30-355">打开部署向导，单击安装或更新 Skype for Business Server 系统，然后单击步骤 1：安装本地配置存储中的运行。</span><span class="sxs-lookup"><span data-stu-id="5ce30-355">Open the Deployment Wizard, click Install or Update Skype for Business Server System, and click on **Run** at Step 1: Install Local Configuration Store.</span></span>
     - <span data-ttu-id="5ce30-356">在 **"安装** 本地配置 **存储"对话框中单击"下一** 步"。</span><span class="sxs-lookup"><span data-stu-id="5ce30-356">Click **Next** in the **Install Local Configuration Store** dialog box.</span></span>
     <span data-ttu-id="5ce30-357">!["安装本地配置存储"对话框](../../media/local-configuration-store.png)</span><span class="sxs-lookup"><span data-stu-id="5ce30-357">![Install Local Configuration Store dialog box](../../media/local-configuration-store.png)</span></span>
     - <span data-ttu-id="5ce30-358">查看结果，并确保"任务状态"已完成。</span><span class="sxs-lookup"><span data-stu-id="5ce30-358">Review the results, and ensure that the Task Status is Completed.</span></span> <span data-ttu-id="5ce30-359">通过单击"查看日志文件查看生成的 **记录**。</span><span class="sxs-lookup"><span data-stu-id="5ce30-359">Review the resulting log file by clicking **View Log**.</span></span>
     <span data-ttu-id="5ce30-360">![任务状态将显示为"已完成"](../../media/local-configuration-task-completed.png)</span><span class="sxs-lookup"><span data-stu-id="5ce30-360">![Task status shows as Completed](../../media/local-configuration-task-completed.png)</span></span>
     - <span data-ttu-id="5ce30-361">单击“完成”。</span><span class="sxs-lookup"><span data-stu-id="5ce30-361">Click **Finish**.</span></span>
9. <span data-ttu-id="5ce30-362">在步骤 2 中 (或删除 Skype for Business Server) ：</span><span class="sxs-lookup"><span data-stu-id="5ce30-362">Set up or remove Skype for Business Server Components (Step 2):</span></span>
    - <span data-ttu-id="5ce30-363">打开部署向导，单击 **安装或** 更新 Skype for Business Server系统，然后单击步骤 2：设置或删除 Skype for Business Server 组件中的运行</span><span class="sxs-lookup"><span data-stu-id="5ce30-363">Open the Deployment Wizard, click **Install or Update Skype for Business Server System**, and click **Run** at Step 2: Set up or Remove Skype for Business Server Components</span></span>
    - <span data-ttu-id="5ce30-364">在 **"设置** Skype for Business Server 组件"对话框中单击"下一步"。</span><span class="sxs-lookup"><span data-stu-id="5ce30-364">Click **Next** in the Set Up Skype for Business Server Components dialog box.</span></span>
    <span data-ttu-id="5ce30-365">!["设置 Skype for Business Server 组件"窗口](../../media/set-up-skype-for-business-server-components-window.png)</span><span class="sxs-lookup"><span data-stu-id="5ce30-365">![the Set Up Skype for Business Server Components window](../../media/set-up-skype-for-business-server-components-window.png)</span></span>
    - <span data-ttu-id="5ce30-366">使用"查看日志"查看日志，并验证安装是否已完成且没有问题。</span><span class="sxs-lookup"><span data-stu-id="5ce30-366">Review the log using View Log, and validate that setup completed without issues.</span></span> 
    - <span data-ttu-id="5ce30-367">单击“完成”。</span><span class="sxs-lookup"><span data-stu-id="5ce30-367">Click **Finish**.</span></span>
10. <span data-ttu-id="5ce30-368">如果需要，请继续进行其他安装和配置 (此时您可以恢复正常的安装) 。</span><span class="sxs-lookup"><span data-stu-id="5ce30-368">Proceed with additional installation and configuration as required (you can resume normal installation procedures at this point).</span></span>
