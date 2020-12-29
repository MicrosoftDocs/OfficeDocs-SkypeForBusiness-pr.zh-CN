---
title: 在 Skype for Business Server 2015 中禁用 TLS 1.0/1.1
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 摘要：准备和实施在环境中禁用 TLS 1.0 和 1.1。
ms.openlocfilehash: 06ebc3f5821e8daa1c80633b25140a852f72097d
ms.sourcegitcommit: 4143ce9bd62e67ba09f89cedadfd65803bda5361
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/28/2020
ms.locfileid: "49734290"
---
# <a name="disable-tls-1011-in-skype-for-business-server-2015"></a><span data-ttu-id="a9121-103">在 Skype for Business Server 2015 中禁用 TLS 1.0/1.1</span><span class="sxs-lookup"><span data-stu-id="a9121-103">Disable TLS 1.0/1.1 in Skype for Business Server 2015</span></span>

<span data-ttu-id="a9121-104">本文的目的是为准备和实施环境中禁用 TLS 1.0 和 1.1 提供必要的指导。</span><span class="sxs-lookup"><span data-stu-id="a9121-104">The purpose of this article is to provide the necessary guidance for you to prepare for and implement disabling TLS 1.0 and 1.1 in your environments.</span></span> <span data-ttu-id="a9121-105">此过程需要进行广泛的规划和准备。</span><span class="sxs-lookup"><span data-stu-id="a9121-105">This process requires extensive planning and preparation.</span></span> <span data-ttu-id="a9121-106">在计划为组织禁用 TLS 1.0 和 1.1 时，请仔细检查本文中所有的信息。</span><span class="sxs-lookup"><span data-stu-id="a9121-106">Please carefully review all of the information in this article as you make your plan to disable TLS 1.0 and 1.1 for your organization.</span></span> <span data-ttu-id="a9121-107">请注意，禁用 TLS 1.0/1.1 可能会影响许多外部依赖项和连接条件，因此需要进行广泛的规划和测试。</span><span class="sxs-lookup"><span data-stu-id="a9121-107">Note that there are many external dependencies and connectivity conditions that could be impacted by disabling TLS 1.0/1.1, so extensive planning and testing is warranted.</span></span>

## <a name="in-this-article"></a><span data-ttu-id="a9121-108">本文内容</span><span class="sxs-lookup"><span data-stu-id="a9121-108">In this article</span></span>

- [<span data-ttu-id="a9121-109">背景和范围</span><span class="sxs-lookup"><span data-stu-id="a9121-109">Background and scope</span></span>](#background)
- [<span data-ttu-id="a9121-110">先决条件和过程</span><span class="sxs-lookup"><span data-stu-id="a9121-110">Prerequisites and process</span></span>](#prerequisites-and-process)
- [<span data-ttu-id="a9121-111">高级部署方案</span><span class="sxs-lookup"><span data-stu-id="a9121-111">Advanced deployment scenarios</span></span>](#advanced-deployment-scenarios)

## <a name="background"></a><span data-ttu-id="a9121-112">背景</span><span class="sxs-lookup"><span data-stu-id="a9121-112">Background</span></span>

<span data-ttu-id="a9121-113">提供 TLS 1.0 和 1.1 禁用对 Skype for Business Server 本地支持的主要驱动因素是支付卡行业 (PCI) 安全标准委员会和联邦信息处理标准要求。</span><span class="sxs-lookup"><span data-stu-id="a9121-113">The primary drivers for providing TLS 1.0 and 1.1 disable support for Skype for Business Server On-Premises are Payment Card Industry (PCI) Security Standards Council and Federal Information Processing Standards requirements.</span></span> <span data-ttu-id="a9121-114">有关 PCI 要求详细信息，请参阅 [此处](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls)。</span><span class="sxs-lookup"><span data-stu-id="a9121-114">More information for PCI requirements can be found [here](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls).</span></span>  <span data-ttu-id="a9121-115">Microsoft 无法提供有关组织是否需要遵守这些或其他要求的指导。</span><span class="sxs-lookup"><span data-stu-id="a9121-115">Microsoft cannot provide guidance on whether or not your organization is required to adhere to these or other requirements.</span></span> <span data-ttu-id="a9121-116">您必须确定在环境中禁用 TLS 1.0 和/或 1.1 是否是必需的。</span><span class="sxs-lookup"><span data-stu-id="a9121-116">You must determine if it is required for you to disable TLS 1.0 and/or 1.1 in your environments.</span></span>

<span data-ttu-id="a9121-117">Microsoft 已制作一份有关此处提供的[](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/)TLS 的白皮书，我们还建议在此 Exchange 博客中提供背景[阅读](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)。</span><span class="sxs-lookup"><span data-stu-id="a9121-117">Microsoft has produced a white paper on TLS available [here](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/), and we also recommend the background reading available in this [Exchange blog](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/).</span></span>

## <a name="supportability-scope"></a><span data-ttu-id="a9121-118">可支持性范围</span><span class="sxs-lookup"><span data-stu-id="a9121-118">Supportability Scope</span></span>

<span data-ttu-id="a9121-119">*范围* 是指可支持性边界。</span><span class="sxs-lookup"><span data-stu-id="a9121-119">*Scope* refers to supportability boundaries.</span></span> <span data-ttu-id="a9121-120">*完全测试和支持* 意味着我们完全支持并已针对列出的产品版本禁用 TLS 1.0 和 1.1。</span><span class="sxs-lookup"><span data-stu-id="a9121-120">*Fully tested and supported* means we fully support and have tested disabling of TLS 1.0 and 1.1 for the listed product versions.</span></span> <span data-ttu-id="a9121-121">*当前正在调查* 意味着这一点;我们正在积极调查将这些产品引入 TLS 禁用支持的范围。</span><span class="sxs-lookup"><span data-stu-id="a9121-121">*Currently being investigated* means just that; we are actively investigating bringing these products into scope for TLS disable support.</span></span> <span data-ttu-id="a9121-122">*超出范围* 意味着这些产品版本不支持禁用 TLS 1.0 或 1.1，并且将不起作用，但已指出的例外情况。</span><span class="sxs-lookup"><span data-stu-id="a9121-122">*Out of scope* means these product versions do not support disabling TLS 1.0 or 1.1 and will not work, with noted exceptions.</span></span>

### <a name="fully-tested-and-supported-servers"></a><span data-ttu-id="a9121-123">经过完全测试且受支持的服务器</span><span class="sxs-lookup"><span data-stu-id="a9121-123">Fully tested and supported servers</span></span>

- <span data-ttu-id="a9121-124">Skype for Business Server 2019 CU1 17.0.2046.123 (2019 年 6 月) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="a9121-124">Skype for Business Server 2019 CU1 17.0.2046.123 (June 2019) or higher</span></span>
- <span data-ttu-id="a9121-125">skype for Business Server 2015 CU9 6.0.9319.548 (May 2019) or higher on Windows Server 2012 (with KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) or superseded update) ， 2012 R2 or 2016.</span><span class="sxs-lookup"><span data-stu-id="a9121-125">Skype for Business Server 2015 CU9 6.0.9319.548 (May 2019) or higher on Windows Server 2012 (with KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) or superseding update), 2012 R2 or 2016.</span></span>
- <span data-ttu-id="a9121-126">In-place Upgraded Skype for Business Server 2015， with CU9 6.0.9319.548 (May 2019) or higher on Windows Server 2008 R2， 2012 (with KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) or superseded update) ， or 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="a9121-126">In-place Upgraded Skype for Business Server 2015, with CU9 6.0.9319.548 (May 2019) or higher on Windows Server 2008 R2, 2012 (with KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) or superseding update), or 2012 R2.</span></span>
- <span data-ttu-id="a9121-127">Exchange Connectivity and Outlook Web App with Exchange Server 2010 SP3 RU19 or higher， guidance [here](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)</span><span class="sxs-lookup"><span data-stu-id="a9121-127">Exchange Connectivity and Outlook Web App with Exchange Server 2010 SP3 RU19 or higher, guidance [here](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)</span></span>
- <span data-ttu-id="a9121-128">Survivable Branch Appliance (SBA) with Skype for Business Server 2015 CU6 IBM2 或更高版本 (向供应商确认他们打包了相应的更新，并且已可用于你的) </span><span class="sxs-lookup"><span data-stu-id="a9121-128">Survivable Branch Appliance (SBA) with Skype for Business Server 2015 CU6 HF2 or higher (confirm with your vendor that they packaged the appropriate updates and have been made available for your appliance)</span></span>
- <span data-ttu-id="a9121-129">Survivable Branch Server (SBS) Skype for Business Server 2015 CU6 版</) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="a9121-129">Survivable Branch Server (SBS) with Skype for Business Server 2015 CU6 HF2 or higher</span></span>
- <span data-ttu-id="a9121-130">仅 Lync Server 2013 边缘角色，这是因为边缘角色对 Windows Fabric 1.0 没有依赖关系。</span><span class="sxs-lookup"><span data-stu-id="a9121-130">Lync Server 2013 **Edge Role Only**, this is because Edge role does not have a dependency on Windows Fabric 1.0.</span></span>

### <a name="fully-tested-and-supported-clients"></a><span data-ttu-id="a9121-131">经过完全测试且受支持的客户端</span><span class="sxs-lookup"><span data-stu-id="a9121-131">Fully tested and supported clients</span></span>

- <span data-ttu-id="a9121-132">Lync 2013 (Skype for Business) 桌面客户端、MSI 和 C2R，包括基本 [15.0.5023.1000 或更高版本](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)</span><span class="sxs-lookup"><span data-stu-id="a9121-132">Lync 2013 (Skype for Business) Desktop Client, MSI and C2R, including Basic [15.0.5023.1000 or higher](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)</span></span>
- <span data-ttu-id="a9121-133">Skype for Business 2016 桌面客户端、MSI [16.0.4678.1000 或更高版本](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323)，包括基本</span><span class="sxs-lookup"><span data-stu-id="a9121-133">Skype for Business 2016 Desktop Client, MSI [16.0.4678.1000 or higher](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323), including Basic</span></span>
- <span data-ttu-id="a9121-134">Skype for Business 2016 Click to Run Require the [April 2018](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) Updates:</span><span class="sxs-lookup"><span data-stu-id="a9121-134">Skype for Business 2016 Click to Run Require the [April 2018](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) Updates:</span></span> 
    - <span data-ttu-id="a9121-135">每月和Semi-Annual定向、16 \. 0 \. 9126 \. 2152 或更高版本</span><span class="sxs-lookup"><span data-stu-id="a9121-135">Monthly and Semi-Annual Targeted, 16\.0\.9126\.2152 or higher</span></span>
    - <span data-ttu-id="a9121-136">Semi-Annual和延期频道，16 \. 0 \. 8431 \. 2242 或更高版本</span><span class="sxs-lookup"><span data-stu-id="a9121-136">Semi-Annual and Deferred Channel, 16\.0\.8431\.2242 or higher</span></span>
- <span data-ttu-id="a9121-137">Mac 16.15 或更高版本上的 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="a9121-137">Skype for Business on Mac 16.15 or higher</span></span>
- <span data-ttu-id="a9121-138">适用于 iOS 和 Android 6.19 或更高版本的 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="a9121-138">Skype for Business for iOS and Android 6.19 or higher</span></span>
- <span data-ttu-id="a9121-139">Microsoft Teams 会议室 (2018 年 12 月或更高版本) Skype 会议室系统 V2 SRS V2 (4.0.64.0) </span><span class="sxs-lookup"><span data-stu-id="a9121-139">Microsoft Teams Rooms (previously known as Skype Room System V2 SRS V2) 4.0.64.0 (December 2018) or higher</span></span>
- <span data-ttu-id="a9121-140">基于 KB4499162 的 Surface Hub 更新 (2019 年 5 月操作系统版本 15063.1835) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="a9121-140">Surface Hub update for Team edition based on KB4499162 (May 2019, OS Build 15063.1835) or higher</span></span>
- <span data-ttu-id="a9121-141">Server 2015 附带 Skype Web App 2015 CU6 (或更高版本) </span><span class="sxs-lookup"><span data-stu-id="a9121-141">Skype Web App 2015 CU6 HF2 or higher (ships with Server)</span></span>

### <a name="currently-being-investigated"></a><span data-ttu-id="a9121-142">当前正在调查</span><span class="sxs-lookup"><span data-stu-id="a9121-142">Currently being investigated</span></span>

- <span data-ttu-id="a9121-143">呼叫质量仪表板 (TLS 1.0、1.1 后的新安装，请参阅下面的) \*</span><span class="sxs-lookup"><span data-stu-id="a9121-143">Call Quality Dashboard (new install after TLS 1.0, 1.1 have been disabled, see below)\*</span></span>
 
### <a name="out-of-scope"></a><span data-ttu-id="a9121-144">超出范围</span><span class="sxs-lookup"><span data-stu-id="a9121-144">Out of scope</span></span>

<span data-ttu-id="a9121-145">除非说明，以下产品不在 TLS 1.0/1.1 禁用支持范围内，并且不会在 TLS 1.0 和 1.1 已禁用的环境中运行。</span><span class="sxs-lookup"><span data-stu-id="a9121-145">Except where noted, the following products are not in scope for TLS 1.0/1.1 disable support and will not function in an environment where TLS 1.0 and 1.1 have been disabled.</span></span> <span data-ttu-id="a9121-146">这意味着：如果仍使用作用域外服务器或客户端，则必须更新或删除这些服务器或客户端（如果需要在 Skype for Business Server 本地部署中的任意位置禁用 TLS 1.0/1.1）。</span><span class="sxs-lookup"><span data-stu-id="a9121-146">What this means: if you still utilize out-of-scope servers or clients, you must update or remove these if you need to disable TLS 1.0/1.1 anywhere in your Skype for Business Server on-premises deployment.</span></span>

- <span data-ttu-id="a9121-147">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9121-147">Lync Server 2013</span></span>
- <span data-ttu-id="a9121-148">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="a9121-148">Lync Server 2010</span></span>
- <span data-ttu-id="a9121-149">Windows Server 2008 或更低版本</span><span class="sxs-lookup"><span data-stu-id="a9121-149">Windows Server 2008 or lower</span></span>
- <span data-ttu-id="a9121-150">Lync for Mac 2011</span><span class="sxs-lookup"><span data-stu-id="a9121-150">Lync for Mac 2011</span></span>
- <span data-ttu-id="a9121-151">Lync 2013 移动版 - iOS、iPad、Android 或 Windows Phone</span><span class="sxs-lookup"><span data-stu-id="a9121-151">Lync 2013 for Mobile - iOS, iPad, Android or Windows Phone</span></span>
- <span data-ttu-id="a9121-152">Lync "MX" Windows 应用商店客户端</span><span class="sxs-lookup"><span data-stu-id="a9121-152">Lync "MX" Windows Store client</span></span>
- <span data-ttu-id="a9121-153">Lync 会议室 (。。</span><span class="sxs-lookup"><span data-stu-id="a9121-153">Lync Room System (a.k.a.</span></span> <span data-ttu-id="a9121-154">SRSv1) 。</span><span class="sxs-lookup"><span data-stu-id="a9121-154">SRSv1).</span></span> <span data-ttu-id="a9121-155">LRS 于 2018 年 10 月 9 日终止支持，不会进行更新以支持 TLS 1.2。</span><span class="sxs-lookup"><span data-stu-id="a9121-155">LRS reached end of support on October 9, 2018 and will not be updated to support TLS 1.2.</span></span>
- <span data-ttu-id="a9121-156">所有 Lync 2010 客户端</span><span class="sxs-lookup"><span data-stu-id="a9121-156">All Lync 2010 clients</span></span>
- <span data-ttu-id="a9121-157">Lync Phone Edition - 此处更新 [了指南](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035)。</span><span class="sxs-lookup"><span data-stu-id="a9121-157">Lync Phone Edition - updated guidance [here](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035).</span></span>
- <span data-ttu-id="a9121-158">基于 2013 的 Survivable Branch Appliance (SBA) 或 Survivable Branch Server (SBS) </span><span class="sxs-lookup"><span data-stu-id="a9121-158">2013 based Survivable Branch Appliance (SBA) or Survivable Branch Server (SBS)</span></span>
- <span data-ttu-id="a9121-159">云连接器版本 (CCE) </span><span class="sxs-lookup"><span data-stu-id="a9121-159">Cloud Connector Edition (CCE)</span></span>
- <span data-ttu-id="a9121-160">Skype for Business for Windows Phone</span><span class="sxs-lookup"><span data-stu-id="a9121-160">Skype for Business for Windows Phone</span></span>

### <a name="exceptions"></a><span data-ttu-id="a9121-161">Exceptions</span><span class="sxs-lookup"><span data-stu-id="a9121-161">Exceptions</span></span>

#### <a name="lync-server-2013"></a><span data-ttu-id="a9121-162">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9121-162">Lync Server 2013</span></span>

<span data-ttu-id="a9121-163">Lync Server 2013 依赖 Windows Fabric 1.0 版。</span><span class="sxs-lookup"><span data-stu-id="a9121-163">Lync Server 2013 takes a dependency on Windows Fabric version 1.0.</span></span>  <span data-ttu-id="a9121-164">在 Lync Server 2013 的设计阶段，为 Windows Fabric 1.0 选择了具有吸引力的新分布式体系结构，以提供复制、高可用性和容错。</span><span class="sxs-lookup"><span data-stu-id="a9121-164">In the design phase for Lync Server 2013, Windows Fabric 1.0 was chosen for its compelling and new distributed architecture to provide replication, high availability, and fault tolerance.</span></span>  <span data-ttu-id="a9121-165">随着时间的推移，Skype for Business Server 和 Windows Fabric 已显著改进此联合体系结构，在后续版本中进行重大重新设计。</span><span class="sxs-lookup"><span data-stu-id="a9121-165">Over time, both Skype for Business Server and Windows Fabric have greatly improved this joint architecture with significant re-design in subsequent versions.</span></span>  <span data-ttu-id="a9121-166">例如，当前 Skype for Business 2015 Server 使用 Windows Fabric 3.0。</span><span class="sxs-lookup"><span data-stu-id="a9121-166">Current Skype for Business 2015 Server uses Windows Fabric 3.0, for example.</span></span>

<span data-ttu-id="a9121-167">遗憾的是，Windows Fabric 1.0 **不支持 TLS 1.2。 但是，我们将更新 Lync Server 2013 以使用 TLS 1.2。**</span><span class="sxs-lookup"><span data-stu-id="a9121-167">Unfortunately, Windows Fabric 1.0 **does not support TLS 1.2.  However, we will be updating Lync Server 2013 to work with TLS 1.2**.</span></span> <span data-ttu-id="a9121-168">这将在 Lync Server 2013 的下一次累积更新中提供。</span><span class="sxs-lookup"><span data-stu-id="a9121-168">This will be coming in the next Cumulative Update for Lync Server 2013.</span></span>  <span data-ttu-id="a9121-169">我们提供 TLS 1.2 支持，以实现共存、迁移、联合和混合方案。</span><span class="sxs-lookup"><span data-stu-id="a9121-169">We're providing TLS 1.2 support to enable co-existence, migration, federation, and hybrid scenarios.</span></span>

<span data-ttu-id="a9121-170">如果你的组织需要禁用 TLS 1.0 和 1.1，并且你当前使用 Lync Server 2013，我们建议你开始规划过程，你可能必须就地升级或并行迁移 (新池，将用户) 移动到 Skype for Business Server 2015 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="a9121-170">If your organization is required to disable TLS 1.0 and 1.1, and you currently use Lync Server 2013, we recommend you begin your planning process, with the possibility you may have to In-place upgrade or Side-by-Side migrate (new pools, move users) to Skype for Business Server 2015 or higher.</span></span>  <span data-ttu-id="a9121-171">或者，你可能想要加速迁移到 Skype for Business Online。</span><span class="sxs-lookup"><span data-stu-id="a9121-171">Or you may want to accelerate migration to Skype for Business Online.</span></span>

#### <a name="call-quality-dashboard"></a><span data-ttu-id="a9121-172">通话质量仪表板</span><span class="sxs-lookup"><span data-stu-id="a9121-172">Call Quality Dashboard</span></span>

<span data-ttu-id="a9121-173">本地呼叫质量仪表板当前依赖于新安装期间 TLS 1.0 (首次安装到本地环境时) 。</span><span class="sxs-lookup"><span data-stu-id="a9121-173">On-Premises Call Quality Dashboard currently has a dependency on TLS 1.0 during new install (first time installing into your On-Premises environments).</span></span>  <span data-ttu-id="a9121-174">我们目前正在调查此问题，并计划在近期发布修补程序。</span><span class="sxs-lookup"><span data-stu-id="a9121-174">We are currently investigating this issue and plan to release a fix in the near future.</span></span>  <span data-ttu-id="a9121-175">如果计划安装 CQD 并同时禁用 TLS 1.0，我们建议您首先完成 CQD 安装，然后继续禁用 TLS 1.0。</span><span class="sxs-lookup"><span data-stu-id="a9121-175">If you are planning to install CQD and also disable TLS 1.0, we recommend that you complete CQD installation first, and then proceed with TLS 1.0 disabling.</span></span>

#### <a name="skype-for-business-sdn-manager"></a><span data-ttu-id="a9121-176">Skype for Business SDN 管理器</span><span class="sxs-lookup"><span data-stu-id="a9121-176">Skype for Business SDN Manager</span></span>

<span data-ttu-id="a9121-177">使用 Skype for Business SDN 管理器SQL新安装期间，数据库依赖于 TLS 1.0。</span><span class="sxs-lookup"><span data-stu-id="a9121-177">Skype for Business SDN Manager using SQL a database has a dependency on TLS 1.0 during new install.</span></span> <span data-ttu-id="a9121-178">如果计划使用 SQL 数据库安装 Skype for Business SDN 管理器并禁用 TLS 1.0，我们建议您首先完成 Skype for Business SDN 管理器，然后继续禁用 TLS 1.0。</span><span class="sxs-lookup"><span data-stu-id="a9121-178">If you are planning to install Skype for Business SDN Manager using SQL a database and also disable TLS 1.0, we recommend that you complete Skype for Business SDN Manager first, and then proceed with TLS 1.0 disabling.</span></span> <span data-ttu-id="a9121-179">如果 TLS 1.0 在安装之前已被禁用，应在将用于托管 Skype for Business SDN 管理器 SQL 数据库的 SQL Server 后端服务器中临时启用 TLS 1.0。</span><span class="sxs-lookup"><span data-stu-id="a9121-179">In case TLS 1.0 was disabled prior to installation, you should temporarily enabled TLS 1.0 back in SQL Server backend server that will be used to host Skype for Business SDN Manager SQL database.</span></span>

#### <a name="third-party-devices"></a><span data-ttu-id="a9121-180">第三方设备</span><span class="sxs-lookup"><span data-stu-id="a9121-180">Third-party devices</span></span>

<span data-ttu-id="a9121-181">在 3PIP 电话、视频会议、反向代理和负载平衡器等第三方设备上，请务必验证 TLS 1.2 可支持性，仔细测试，并根据需要与供应商联系。</span><span class="sxs-lookup"><span data-stu-id="a9121-181">On third-party devices such as 3PIP phones, Video conferencing, Reverse Proxies and Load Balancers, be sure to validate TLS 1.2 supportability, test carefully, and contact the vendor if needed.</span></span>

### <a name="federation-considerations-when-disabling-tls-1011-on-edge-servers"></a><span data-ttu-id="a9121-182">在边缘服务器上禁用 TLS 1.0/1.1 时联合身份验证注意事项</span><span class="sxs-lookup"><span data-stu-id="a9121-182">Federation considerations when disabling TLS 1.0/1.1 on Edge servers</span></span>

<span data-ttu-id="a9121-183">必须仔细规划并考虑禁用 TLS 1.0/1.1 对边缘服务器的影响。</span><span class="sxs-lookup"><span data-stu-id="a9121-183">You must carefully plan for and consider the impact of disabling TLS 1.0/1.1 on your Edge servers.</span></span>  <span data-ttu-id="a9121-184">禁用 TLS 1.0 和 1.1 后，您可能会发现其他组织无法再与您的组织联盟。</span><span class="sxs-lookup"><span data-stu-id="a9121-184">Once TLS 1.0 and 1.1 are disabled, you may find that other organizations are no longer be able to federate with your organization.</span></span>

<span data-ttu-id="a9121-185">您可以选择在边缘服务器上保持启用 TLS 1.0/1.1，以保持与非修补的 (SfB 2015、Lync 2013) 或 (2010) 外部系统的向后兼容性。</span><span class="sxs-lookup"><span data-stu-id="a9121-185">You may opt to keep TLS 1.0/1.1 enabled on your Edge servers to maintain backward compatibility with non-patched (SfB 2015, Lync 2013) or older (2010) external systems.</span></span>

<span data-ttu-id="a9121-186">Microsoft 无法提供有关边缘网络网络或 (网络网络是否) PCI 标准的建议或建议;必须由单个公司确定。</span><span class="sxs-lookup"><span data-stu-id="a9121-186">Microsoft cannot provide advice or recommendations on whether or not your Edge network (or any network) falls under PCI standard; that must be determined by the individual company.</span></span>

<span data-ttu-id="a9121-187">Skype for Business Online 现在支持 TLS 1.2，因此对与 Online 的混合/联盟没有影响。</span><span class="sxs-lookup"><span data-stu-id="a9121-187">Skype for Business Online is capable of TLS 1.2 today, so no impact to Hybrid/Federation with Online is expected.</span></span>

<span data-ttu-id="a9121-188">PIC (公共 IM) Skype 消费者服务：我们预计禁用 TLS 1.0/1.1 不会影响 Skype [连接](../../deploy/deploy-skype-connectivity.md);Microsoft PIC 网关已经支持 TLS 1.2。</span><span class="sxs-lookup"><span data-stu-id="a9121-188">PIC (Public IM Connectivity) to Skype Consumer service: We do not expect disabling TLS 1.0/1.1 to impact [Skype Connectivity](../../deploy/deploy-skype-connectivity.md); Microsoft PIC Gateways are already TLS 1.2 capable.</span></span>

## <a name="prerequisites-and-process"></a><span data-ttu-id="a9121-189">先决条件和过程</span><span class="sxs-lookup"><span data-stu-id="a9121-189">Prerequisites and process</span></span>

<span data-ttu-id="a9121-190">除非如上所述，一旦禁用了 TLS 1.0 和 1.1 的作用域外服务器，客户端和设备将更长地正常运行，或一切正常。</span><span class="sxs-lookup"><span data-stu-id="a9121-190">Except where noted above, once TLS 1.0 and 1.1 are disabled out-of-scope servers, clients and devices will longer function properly, or at all.</span></span> <span data-ttu-id="a9121-191">这可能意味着你需要暂停并等待来自 Microsoft 的更新指导。</span><span class="sxs-lookup"><span data-stu-id="a9121-191">This may mean you need to pause and wait for updated guidance from Microsoft.</span></span> <span data-ttu-id="a9121-192">一旦满足所有要求并计划解决差距，请继续。</span><span class="sxs-lookup"><span data-stu-id="a9121-192">Once you are satisfied that you meet all requirements and have a plan to address gaps, proceed.</span></span>

<span data-ttu-id="a9121-193">在高级别上，虽然 Skype for Business Server 2019 已做好安装过程准备，但 Skype for Business Server 2015 将要求您安装 CU9、将必备更新应用到 .NET 和 SQL、部署必备注册表项，最后是单独一轮操作系统配置更新 (即通过注册表文件导入) 禁用 TLS 1.0 和 1.1。</span><span class="sxs-lookup"><span data-stu-id="a9121-193">At a high level, while Skype for Business Server 2019 is ready for procedure at install, Skype for Business Server 2015 will require that you install CU9, applying pre-requisite updates to .NET and SQL, deploying prerequisite registry keys, and finally a separate round of OS configuration updates (i.e. disabling TLS 1.0 and 1.1 via registry file import).</span></span> <span data-ttu-id="a9121-194">在环境中的任何服务器上禁用 TLS 1.0 和 1.1 之前，必须完成所有必备组件（包括 Skype for Business Server 2015 CU6 IBM2）的安装，这一点至关重要。</span><span class="sxs-lookup"><span data-stu-id="a9121-194">It is critically important that you complete installation of all prerequisites, including Skype for Business Server 2015 CU6 HF2, prior to disabling TLS 1.0 and 1.1 on any server in your environment.</span></span> <span data-ttu-id="a9121-195">每个 Skype for Business 服务器（包括边缘角色SQL后端）都需要更新。</span><span class="sxs-lookup"><span data-stu-id="a9121-195">Every Skype for Business server, including Edge role and SQL Backends, requires the updates.</span></span> <span data-ttu-id="a9121-196">此外，请确保所有 (范围内) 客户端已更新为所需的最低版本。</span><span class="sxs-lookup"><span data-stu-id="a9121-196">Also ensure that all supported (in-scope) clients have been updated to the required minimum versions.</span></span> <span data-ttu-id="a9121-197">不要忘记更新管理工作站。</span><span class="sxs-lookup"><span data-stu-id="a9121-197">Don’t forget to update management workstations as well.</span></span>

<span data-ttu-id="a9121-198">我们希望遵循"从内到外"的常规操作顺序来升级 Skype for Business 服务器。</span><span class="sxs-lookup"><span data-stu-id="a9121-198">We want to follow the usual order of operations of "inside out" for upgrading Skype for Business servers.</span></span> <span data-ttu-id="a9121-199">以通常相同的方式处理控制器池、持久聊天和配对池。</span><span class="sxs-lookup"><span data-stu-id="a9121-199">Treat Director pools, Persistent chat, and Paired Pools in the same manner you normally would.</span></span> <span data-ttu-id="a9121-200">此处和此处介绍了升级[的顺序](topology.md)[和方法](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)。</span><span class="sxs-lookup"><span data-stu-id="a9121-200">Order and methods for upgrade are covered [here](topology.md) and [here](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span>

### <a name="high-level-process"></a><span data-ttu-id="a9121-201">高级流程</span><span class="sxs-lookup"><span data-stu-id="a9121-201">High-level process</span></span>

1. <span data-ttu-id="a9121-202">在配置生产服务器之前，测试实验室中的所有步骤。</span><span class="sxs-lookup"><span data-stu-id="a9121-202">Test all steps in your lab prior to configuring production servers.</span></span>
2. <span data-ttu-id="a9121-203">在每台要更新的每台服务器上备份并保留导出的注册表副本。</span><span class="sxs-lookup"><span data-stu-id="a9121-203">Back up and preserve a copy of exported registry on each and every individual server to be updated.</span></span> <span data-ttu-id="a9121-204">不能在服务器之间共享注册表;它们包含基于计算机的唯一密钥。</span><span class="sxs-lookup"><span data-stu-id="a9121-204">You cannot share registries between servers; they contain unique machine-based keys.</span></span>
3. <span data-ttu-id="a9121-205">将所有 Skype for Business 2015 服务器升级到 CU9 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="a9121-205">Upgrade all Skype for Business 2015 servers to CU9 or higher.</span></span> <span data-ttu-id="a9121-206">对于 Skype for Business Server 2019，请升级到 CU1 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="a9121-206">For Skype for Business Server 2019, upgrade to CU1 or higher.</span></span>
4. <span data-ttu-id="a9121-207">将所有必备组件安装到所有服务器。</span><span class="sxs-lookup"><span data-stu-id="a9121-207">Install all prerequisites to all servers.</span></span>
5. <span data-ttu-id="a9121-208">部署必备注册表项。</span><span class="sxs-lookup"><span data-stu-id="a9121-208">Deploy prerequisite registry keys.</span></span>
6. <span data-ttu-id="a9121-209">确保所有作用域内客户端已更新。</span><span class="sxs-lookup"><span data-stu-id="a9121-209">Ensure that all in-scope clients are updated.</span></span>
7. <span data-ttu-id="a9121-210">通过注册表导入禁用 TLS 1.0 和 1.1。</span><span class="sxs-lookup"><span data-stu-id="a9121-210">Disable TLS 1.0 and 1.1 via registry import.</span></span>
8. <span data-ttu-id="a9121-211">验证工作负荷是否正常工作。</span><span class="sxs-lookup"><span data-stu-id="a9121-211">Validate that workloads are functioning as expected.</span></span>
    - <span data-ttu-id="a9121-212">如果遇到问题，请进行故障排除和解决，或者</span><span class="sxs-lookup"><span data-stu-id="a9121-212">If problems are encountered, troubleshoot and resolve, or</span></span>
    - <span data-ttu-id="a9121-213">从步骤 2 还原注册表以重新启用 TLS 1.0 和 1.1</span><span class="sxs-lookup"><span data-stu-id="a9121-213">Restore registry from step 2 to re-enable TLS 1.0 and 1.1</span></span>
9. <span data-ttu-id="a9121-214">验证是否仅使用了 TLS 1.2。</span><span class="sxs-lookup"><span data-stu-id="a9121-214">Validate that only TLS 1.2 is being used.</span></span>

### <a name="install-prerequisites-to-all-servers"></a><span data-ttu-id="a9121-215">将必备组件安装到所有服务器</span><span class="sxs-lookup"><span data-stu-id="a9121-215">Install prerequisites to all servers</span></span>

<span data-ttu-id="a9121-216">在开始在 Skype for Business Server 2015 部署的操作系统级别禁用 TLS 1.0 和 1.1 之前，需要进行广泛的依赖更新。</span><span class="sxs-lookup"><span data-stu-id="a9121-216">Extensive dependency updating is required before you begin to disable TLS 1.0 and 1.1 at the operating system level in your Skype for Business Server 2015 deployments.</span></span> <span data-ttu-id="a9121-217">以下是支持 TLS 1.2 的最低版本。</span><span class="sxs-lookup"><span data-stu-id="a9121-217">The following are the minimum versions that can support TLS 1.2.</span></span> <span data-ttu-id="a9121-218">在开始禁用 TLS 1.0 和 1.1 之前，在环境中每个 Skype for Business 服务器上部署所有必备组件更新。</span><span class="sxs-lookup"><span data-stu-id="a9121-218">Deploy all prerequisite updates across every Skype for Business server in your environment before you begin disabling TLS 1.0 and 1.1.</span></span>

- <span data-ttu-id="a9121-219">Skype for Business Server 2015 CU9 6.0.9319.548 (2019 年 5 月) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="a9121-219">Skype for Business Server 2015 CU9 6.0.9319.548 (May 2019) or higher</span></span>
- <span data-ttu-id="a9121-220">[.NET Framework 4.7](https://www.microsoft.com/download/details.aspx?id=55167) 或更高版本，在注册表中启用 SchUseStrongCrypto， (提供如下) </span><span class="sxs-lookup"><span data-stu-id="a9121-220">[.NET Framework 4.7](https://www.microsoft.com/download/details.aspx?id=55167) or higher with SchUseStrongCrypto enabled in the registry (provided below)</span></span>
- <span data-ttu-id="a9121-221">SQL必须在所有 Skype for Business 2015 服务器和后端上进行更新。</span><span class="sxs-lookup"><span data-stu-id="a9121-221">SQL must be updated on all Skype for Business 2015 servers and backends.</span></span> <span data-ttu-id="a9121-222">首先更新 Enterprise Edition Pool SQL后端，然后更新其各自的 FEs。</span><span class="sxs-lookup"><span data-stu-id="a9121-222">Update Enterprise Edition Pool SQL Backends first, then their respective FEs.</span></span> 
    - <span data-ttu-id="a9121-223">[SQL Server 2014 SP1 + CU5](https://support.microsoft.com/help/3130926)或更高版本/ SQL Server 2012 SP2 + CU16 或更高版本/ [SQL Server 2014 RTM + CU12](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014)或更高版本/ SQL Server 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="a9121-223">[SQL Server 2014 SP1 + CU5](https://support.microsoft.com/help/3130926), or higher / SQL Server 2012 SP2 + CU16 or higher / [SQL Server 2014 RTM + CU12](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014), or higher / SQL Server 2014 SP2</span></span>
     - [<span data-ttu-id="a9121-224">SQL Server 2012 SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="a9121-224">SQL Server Native Client for SQL Server 2012</span></span>](https://www.microsoft.com/download/details.aspx?id=50402)
     - <span data-ttu-id="a9121-225">[Microsoft ODBC Driver 11 for SQL Server](https://www.microsoft.com/download/details.aspx?id=36434)或更高版本</span><span class="sxs-lookup"><span data-stu-id="a9121-225">[Microsoft ODBC Driver 11 for SQL Server](https://www.microsoft.com/download/details.aspx?id=36434), or higher</span></span>
     - [<span data-ttu-id="a9121-226">SQL Server 2014 SP2 的共享管理对象</span><span class="sxs-lookup"><span data-stu-id="a9121-226">Shared Management Objects for SQL Server 2014 SP2</span></span>](https://www.microsoft.com/download/details.aspx?id=53164)
     - [<span data-ttu-id="a9121-227">SQLSysClrTypes for SQL server 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="a9121-227">SQLSysClrTypes for SQL server 2014 SP2</span></span>](https://www.microsoft.com/download/details.aspx?id=42295)

### <a name="basic-steps-to-install-pre-requisites-in-recommended-order-of-operations"></a><span data-ttu-id="a9121-228">按建议的操作顺序安装先决条件的基本步骤</span><span class="sxs-lookup"><span data-stu-id="a9121-228">Basic steps to install pre-requisites, in recommended order of operations</span></span>

1. <span data-ttu-id="a9121-229">将 Skype for Business Server CU9 更新安装到所有服务器。</span><span class="sxs-lookup"><span data-stu-id="a9121-229">Install the Skype for Business Server CU9 update to all servers.</span></span> 
    1. <span data-ttu-id="a9121-230">使用更新程序将更新安装到组件。</span><span class="sxs-lookup"><span data-stu-id="a9121-230">Install the update to components using the updater.</span></span>
    2. <span data-ttu-id="a9121-231">根据记录的过程更新数据库。</span><span class="sxs-lookup"><span data-stu-id="a9121-231">Update databases according to documented procedures.</span></span> <span data-ttu-id="a9121-232">对于 Skype for Business Server 2015，请参阅 KB [3061064。](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)</span><span class="sxs-lookup"><span data-stu-id="a9121-232">For Skype for Business Server 2015, see KB [3061064](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span>
    3. <span data-ttu-id="a9121-233">在推进任何其他更改之前，验证部署中的产品功能。</span><span class="sxs-lookup"><span data-stu-id="a9121-233">Validate product functionality in the deployment prior to moving forward with any other changes.</span></span>
2. <span data-ttu-id="a9121-234">下载 .NET 4.7 脱机安装程序。</span><span class="sxs-lookup"><span data-stu-id="a9121-234">Download .NET 4.7 Offline Installer.</span></span> 
    1. <span data-ttu-id="a9121-235">参考： [https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)</span><span class="sxs-lookup"><span data-stu-id="a9121-235">Reference: [https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)</span></span>
    2. <span data-ttu-id="a9121-236">确保前端服务器上已停止 Skype for Business Server 2015 服务。</span><span class="sxs-lookup"><span data-stu-id="a9121-236">Ensure that Skype for Business Server 2015 services are stopped on the Front End server.</span></span>
    3. <span data-ttu-id="a9121-237">参考： [https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)</span><span class="sxs-lookup"><span data-stu-id="a9121-237">Reference: [https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)</span></span>
    4. <span data-ttu-id="a9121-238">例如 (Standard Edition) ： ```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="a9121-238">Ex (Standard Edition): ```Stop-CsWindowsService```</span></span>
    5. <span data-ttu-id="a9121-239">例如 (Enterprise Edition) ： ```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="a9121-239">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    6. <span data-ttu-id="a9121-240">运行安装程序程序包。</span><span class="sxs-lookup"><span data-stu-id="a9121-240">Run the installer package.</span></span>
    7. <span data-ttu-id="a9121-241">请重新启动服务器。</span><span class="sxs-lookup"><span data-stu-id="a9121-241">Reboot the server.</span></span>
3. <span data-ttu-id="a9121-242">在所有SQL更新 Express 2014。</span><span class="sxs-lookup"><span data-stu-id="a9121-242">Update SQL Express 2014 on all servers.</span></span> 
    1. <span data-ttu-id="a9121-243">参考： [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span><span class="sxs-lookup"><span data-stu-id="a9121-243">Reference: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span></span>
    2. <span data-ttu-id="a9121-244">下载 SQL 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="a9121-244">Download SQL 2014 SP2</span></span> 
        - <span data-ttu-id="a9121-245">参考： [https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)</span><span class="sxs-lookup"><span data-stu-id="a9121-245">Reference: [https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)</span></span>
    3. <span data-ttu-id="a9121-246">将安装媒体复制到服务器上文件夹 (例如：C：\01_2014SqlSp2) </span><span class="sxs-lookup"><span data-stu-id="a9121-246">Copy the installation media to a folder on the server (Ex: C:\01_2014SqlSp2)</span></span>
    4. <span data-ttu-id="a9121-247">确保前端服务器上已停止 Skype for Business Server 2015 服务</span><span class="sxs-lookup"><span data-stu-id="a9121-247">Ensure Skype for Business Server 2015 services are stopped on the Front End server</span></span> 
        - <span data-ttu-id="a9121-248">例如 (Standard Edition) ： ```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="a9121-248">Ex (Standard Edition): ```Stop-CsWindowsService```</span></span>
        - <span data-ttu-id="a9121-249">例如 (Enterprise Edition) ： ```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="a9121-249">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    5. <span data-ttu-id="a9121-250">打开管理命令提示符，并升级所有已安装的组件和实例</span><span class="sxs-lookup"><span data-stu-id="a9121-250">Open an Admin Command Prompt, and upgrade all installed components and instances</span></span> 
        - <span data-ttu-id="a9121-251">示例：C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe /qs /IAcceptSQLServerLicenseTerms /Action=Patch /AllInstances</span><span class="sxs-lookup"><span data-stu-id="a9121-251">Example: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe /qs /IAcceptSQLServerLicenseTerms /Action=Patch /AllInstances</span></span>
4. <span data-ttu-id="a9121-252">更新SQL客户端。</span><span class="sxs-lookup"><span data-stu-id="a9121-252">Update SQL Native Client.</span></span> 
    1. <span data-ttu-id="a9121-253">参考 [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server) ：.</span><span class="sxs-lookup"><span data-stu-id="a9121-253">Reference: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server).</span></span>
    2. <span data-ttu-id="a9121-254">下载自 [https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)</span><span class="sxs-lookup"><span data-stu-id="a9121-254">Download from [https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)</span></span>
    3. <span data-ttu-id="a9121-255">确保前端服务器上已停止 Skype for Business Server 2015 服务。</span><span class="sxs-lookup"><span data-stu-id="a9121-255">Ensure Skype for Business Server 2015 services are stopped on the Front End server.</span></span> 
        - <span data-ttu-id="a9121-256">例如 (Standard Edition) ： ```Stop-CsWindowsServices```</span><span class="sxs-lookup"><span data-stu-id="a9121-256">Ex (Standard Edition): ```Stop-CsWindowsServices```</span></span>
        - <span data-ttu-id="a9121-257">例如 (Enterprise Edition) ： ```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="a9121-257">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    4. <span data-ttu-id="a9121-258">停止SQL实例运行</span><span class="sxs-lookup"><span data-stu-id="a9121-258">Stop the SQL instances installed from running</span></span> 
        - <span data-ttu-id="a9121-259">例如： ```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="a9121-259">Ex: ```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```</span></span>
        - <span data-ttu-id="a9121-260">例如： ```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="a9121-260">Ex: ```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```</span></span>
        - <span data-ttu-id="a9121-261">例如 (Standard Edition) ： ```Get-Service 'MSSQL$RTC' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="a9121-261">Ex (Standard Edition Only): ```Get-Service 'MSSQL$RTC' | Stop-Service```</span></span>
    5. <span data-ttu-id="a9121-262">安装该更新。</span><span class="sxs-lookup"><span data-stu-id="a9121-262">Install the update.</span></span>
5. <span data-ttu-id="a9121-263">更新 ODBC Driver 11 for SQL Server以包含对 TLS 1.2 (KB [3135244](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)) 。</span><span class="sxs-lookup"><span data-stu-id="a9121-263">Update ODBC Driver 11 for SQL Server to include support for TLS 1.2 (KB [3135244](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)).</span></span>
    1. <span data-ttu-id="a9121-264">下载 [ODBC Driver 11 for SQL Server - Windows](https://www.microsoft.com/download/confirmation.aspx?id=36434)。</span><span class="sxs-lookup"><span data-stu-id="a9121-264">Download [ODBC Driver 11 for SQL Server - Windows](https://www.microsoft.com/download/confirmation.aspx?id=36434).</span></span>
    2. <span data-ttu-id="a9121-265">确保前端服务器上已停止 Skype for Business Server 2015 服务。</span><span class="sxs-lookup"><span data-stu-id="a9121-265">Ensure that Skype for Business Server 2015 services are stopped on the Front End server.</span></span>
        - <span data-ttu-id="a9121-266">Standard Edition (示例) ： ```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="a9121-266">Example (Standard Edition): ```Stop-CsWindowsService```</span></span>
        - <span data-ttu-id="a9121-267">Enterprise Edition (示例) ： ```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="a9121-267">Example (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    3. <span data-ttu-id="a9121-268">安装该更新。</span><span class="sxs-lookup"><span data-stu-id="a9121-268">Install the update.</span></span>
6. <span data-ttu-id="a9121-269">部署必备注册表项。</span><span class="sxs-lookup"><span data-stu-id="a9121-269">Deploy prerequisite registry keys.</span></span>

### <a name="pre-requisite-registry-keys"></a><span data-ttu-id="a9121-270">先决条件注册表项</span><span class="sxs-lookup"><span data-stu-id="a9121-270">Pre-requisite registry keys</span></span>

<span data-ttu-id="a9121-271">将以下测试复制/粘贴到记事本中，重命名 TLSPreReq.reg 或您所选择的名称，然后导入：</span><span class="sxs-lookup"><span data-stu-id="a9121-271">Copy/paste the following test into Notepad and rename TLSPreReq.reg or a name of your choice, then import:</span></span>

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

<span data-ttu-id="a9121-272">对于SQL池的后端，必备组件和 TLS 禁用应视为任何SQL操作系统更新;请参阅： [https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)</span><span class="sxs-lookup"><span data-stu-id="a9121-272">For SQL back ends for Enterprise Edition Pools, prerequisites and TLS disable should be treated as any SQL or OS updates would; refer to: [https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)</span></span>

<span data-ttu-id="a9121-273">尽管必备应用程序和 TLS 禁用步骤都可以组合使用，但我们强烈建议先应用所有必备组件，然后再在操作系统级别继续禁用 TLS 1.0 和 1.1。</span><span class="sxs-lookup"><span data-stu-id="a9121-273">While both the prerequisite application and TLS disabling steps can be combined, we strongly recommend all prerequisites be applied before proceeding with disabling of TLS 1.0 and 1.1 at the operating system level.</span></span> <span data-ttu-id="a9121-274">最佳做法是准备环境，方法是部署所有必备组件，验证工作负荷是否按预期正常运行，然后稍后继续禁用 TLS 1.0/1.1。</span><span class="sxs-lookup"><span data-stu-id="a9121-274">The best practice approach would be to prepare the environment by deploying all prerequisites, validating that workloads all function correctly and as expected, and then proceeding with TLS 1.0/1.1 disable at a later time.</span></span>

### <a name="disable-tls-10-and-11-via-registry-import"></a><span data-ttu-id="a9121-275">通过注册表导入禁用 TLS 1.0 和 1.1</span><span class="sxs-lookup"><span data-stu-id="a9121-275">Disable TLS 1.0 and 1.1 via registry import</span></span>

<span data-ttu-id="a9121-276">在继续执行下一步之前，请确保已完成所有先决条件和更新 *的 Skype for Business 服务器*。</span><span class="sxs-lookup"><span data-stu-id="a9121-276">Before you proceed with the next steps, *make sure you have completed all prerequisites and updated Skype for Business Servers*.</span></span>

<span data-ttu-id="a9121-277">将以下文本复制到记事本文件中，并将其重命名 **为 TLSDisable.reg：**</span><span class="sxs-lookup"><span data-stu-id="a9121-277">Copy the following text into a Notepad file and rename it **TLSDisable.reg**:</span></span>

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

<span data-ttu-id="a9121-278">在要禁用 TLS 1.0 和 1.1 的每个服务器上导入 .reg 文件。</span><span class="sxs-lookup"><span data-stu-id="a9121-278">Import the .reg file on each server you wish to disable TLS 1.0 and 1.1.</span></span> <span data-ttu-id="a9121-279">请重新启动服务器。</span><span class="sxs-lookup"><span data-stu-id="a9121-279">Reboot the server.</span></span> <span data-ttu-id="a9121-280">服务重新联机后，移动到下一台服务器。</span><span class="sxs-lookup"><span data-stu-id="a9121-280">Once the services have come back online, move to the next server.</span></span> <span data-ttu-id="a9121-281">Enterprise Edition Pools 的方法与任何操作系统更新的方法相同。</span><span class="sxs-lookup"><span data-stu-id="a9121-281">The approach for Enterprise Edition Pools is the same you would take for any OS update.</span></span>

<span data-ttu-id="a9121-282">你可能已经注意到，我们所做的不仅仅是禁用 TLS 1.0 和 1.1。</span><span class="sxs-lookup"><span data-stu-id="a9121-282">You may have noticed we are doing more than just disabling TLS 1.0 and 1.1 here.</span></span> <span data-ttu-id="a9121-283">我们支持加密套件重新排序 (如上所示) 禁用一些旧的弱密码。</span><span class="sxs-lookup"><span data-stu-id="a9121-283">We are supporting Cipher Suite re-order (as shown above) and the disabling of some older weak ciphers.</span></span> <span data-ttu-id="a9121-284">这是我们第一次正式支持对 Skype for Business Server 上的 SCHANNEL 和加密 API 的这些更改，必须注意，这些更改是唯一支持并且目前已经过测试的更改。</span><span class="sxs-lookup"><span data-stu-id="a9121-284">This is the first time we have officially supported these changes to SCHANNEL and Crypto API on Skype for Business Server, and it is important to note that these changes are the only ones we support and have tested at this time.</span></span> <span data-ttu-id="a9121-285">我们将来可能会考虑其他配置，但现在请不要在你的实现中修改注册表导入文件。</span><span class="sxs-lookup"><span data-stu-id="a9121-285">We may consider additional configurations in the future, but for now, please do not modify the registry import file in your implementation.</span></span>

### <a name="validate-that-workloads-are-functioning-as-expected"></a><span data-ttu-id="a9121-286">验证工作负荷是否正常工作</span><span class="sxs-lookup"><span data-stu-id="a9121-286">Validate that workloads are functioning as expected</span></span>

<span data-ttu-id="a9121-287">在环境中禁用 TLS 1.0 和 1.1 后，请确保所有主工作负荷均正常运行，例如 IM & 状态、P2P 呼叫、企业语音等。</span><span class="sxs-lookup"><span data-stu-id="a9121-287">Once TLS 1.0 and 1.1 have been disabled in your environment, ensure that all your main workloads are functioning as expected, such as IM & Presence, P2P calls, Enterprise Voice, etc.</span></span>

<span data-ttu-id="a9121-288">**仅验证是否使用了 TLS 1.2**</span><span class="sxs-lookup"><span data-stu-id="a9121-288">**Validate only TLS 1.2 is being used**</span></span>

<span data-ttu-id="a9121-289">让安全团队对 Skype for Business 流量执行新的审核，以确保不再使用较旧的协议 TLS 1.0 和 1.1。</span><span class="sxs-lookup"><span data-stu-id="a9121-289">Have your Security Team perform a new audit of Skype for Business traffic to ensure that the older protocols TLS 1.0 and 1.1 are no longer in use.</span></span>

<span data-ttu-id="a9121-290">或者，在 TLS 1.0 和 TLS 1.1 被禁用后，可以使用 Internet Explorer 测试从 Skype for Business Server 2015 到 Web 服务的 TLS 连接。</span><span class="sxs-lookup"><span data-stu-id="a9121-290">Alternatively, you can use Internet Explorer to test TLS connections to web services from Skype for Business Server 2015 after TLS 1.0 and TLS 1.1 have been disabled.</span></span>

1. <span data-ttu-id="a9121-291">启动Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="a9121-291">Launch Internet Explorer.</span></span>
2. <span data-ttu-id="a9121-292">选择 **工具**  >  **Internet 选项**。</span><span class="sxs-lookup"><span data-stu-id="a9121-292">Select **Tools** > **Internet Options**.</span></span>
3. <span data-ttu-id="a9121-293">选择 **"高级"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="a9121-293">Select the **Advanced** tab.</span></span>
4. <span data-ttu-id="a9121-294">在 **"设置**"下，滚动到底部。</span><span class="sxs-lookup"><span data-stu-id="a9121-294">Under **Settings**, scroll to the bottom.</span></span>
5. <span data-ttu-id="a9121-295">验证是否已启用 TLS 1.0、TLS 1.1 和 TLS 1.2。</span><span class="sxs-lookup"><span data-stu-id="a9121-295">Verify that TLS 1.0, TLS 1.1, and TLS 1.2 are enabled.</span></span>
6. <span data-ttu-id="a9121-296">浏览 SfB 2015 池的内部 Web 服务 URL， (连接成功) 。</span><span class="sxs-lookup"><span data-stu-id="a9121-296">Browse the Internal Web Service URL of your SfB 2015 pool (should connect successfully).</span></span>
7. <span data-ttu-id="a9121-297">返回到Internet Explorer并禁用"仅 **使用 TLS 1.2"** 选项。</span><span class="sxs-lookup"><span data-stu-id="a9121-297">Go back into Internet Explorer and disable the option to **Use TLS 1.2** only.</span></span>
8. <span data-ttu-id="a9121-298">再次浏览 SfB 2015 池的内部 Web 服务 URL， (连接失败) 。</span><span class="sxs-lookup"><span data-stu-id="a9121-298">Browse the Internal Web Service URL of your SfB 2015 pool again (should fail to connect).</span></span>

![Internet 选项](../../media/internet-options.jpg)

## <a name="advanced-deployment-scenarios"></a><span data-ttu-id="a9121-300">高级部署方案</span><span class="sxs-lookup"><span data-stu-id="a9121-300">Advanced deployment scenarios</span></span>

<span data-ttu-id="a9121-301">由于在 Skype for Business Server 2015 中支持 TLS 1.2 需要一些依赖先决条件，因此从 RTM 媒体安装将在已禁用 TLS 1.0 和 1.1 的任何系统上失败。</span><span class="sxs-lookup"><span data-stu-id="a9121-301">Because some dependency prerequisites are required to support TLS 1.2 in Skype for Business Server 2015, installing from RTM media will fail on any system where TLS 1.0 and 1.1 have been disabled.</span></span>

<span data-ttu-id="a9121-302">**在环境中禁用 TLS 1.0 和 1.1 后部署新的 Standard Edition Servers 或 Enterprise Edition 池。**</span><span class="sxs-lookup"><span data-stu-id="a9121-302">**Deploying New Standard Edition Servers or Enterprise Edition Pools once TLS 1.0 and 1.1 have been disabled in your environment.**</span></span>

<span data-ttu-id="a9121-303">**选项 1：** 使用 [SmartSetup](../../deploy/install/install-skype-for-business-server.md)。</span><span class="sxs-lookup"><span data-stu-id="a9121-303">**Option 1:** Use [SmartSetup](../../deploy/install/install-skype-for-business-server.md).</span></span> <span data-ttu-id="a9121-304">请注意，我们将更新 SmartSetup 以适应SQL CU 中更新的二进制文件，并在将来更新本文。</span><span class="sxs-lookup"><span data-stu-id="a9121-304">Note that we are updating SmartSetup to accommodate the updated SQL binaries in a future CU, and will update this article in the future.</span></span>

<span data-ttu-id="a9121-305">**选项 2：** 在 RTCLOCAL SQL LYNCLOCAL (预安装本地) </span><span class="sxs-lookup"><span data-stu-id="a9121-305">**Option 2:** Pre-install local SQL instances (RTCLOCAL and LYNCLOCAL)</span></span>

1. <span data-ttu-id="a9121-306">下载 Express 2014 SP2 SQL， (SQLEXPR_x64.exe) 复制到 FE 上的本地文件夹中。</span><span class="sxs-lookup"><span data-stu-id="a9121-306">Download and copy SQL Express 2014 SP2 (SQLEXPR_x64.exe) to local folder on FE.</span></span> <span data-ttu-id="a9121-307">假设文件夹路径为 <SQL_FOLDER_PATH>。</span><span class="sxs-lookup"><span data-stu-id="a9121-307">Let’s say folder path <SQL_FOLDER_PATH>.</span></span>
2. <span data-ttu-id="a9121-308">启动 PowerShell 或命令提示符并导航到 <SQL_FOLDER_PATH>。</span><span class="sxs-lookup"><span data-stu-id="a9121-308">Launch PowerShell or Command Prompt and navigate to <SQL_FOLDER_PATH>.</span></span>
3. <span data-ttu-id="a9121-309">通过运行以下SQL创建 RTCLOCAL 实例。</span><span class="sxs-lookup"><span data-stu-id="a9121-309">Create the RTCLOCAL SQL instance by running the command below.</span></span> <span data-ttu-id="a9121-310">请等待SQLEXPR_x64.exe完成，然后再继续：</span><span class="sxs-lookup"><span data-stu-id="a9121-310">Wait until SQLEXPR_x64.exe finishes before proceeding:</span></span>

    <span data-ttu-id="a9121-311">SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine，Tools /INSTANCENAME=RTCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT=1 "NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automati</span><span class="sxs-lookup"><span data-stu-id="a9121-311">SQLEXPR_x64.exe  /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=RTCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automati</span></span>
1. <span data-ttu-id="a9121-312">通过运行以下SQL创建 LYNCLOCAL 实例。</span><span class="sxs-lookup"><span data-stu-id="a9121-312">Create the LYNCLOCAL SQL instance by running the command below.</span></span> <span data-ttu-id="a9121-313">请等待SQLEXPR_x64.exe完成，然后再继续下一步：</span><span class="sxs-lookup"><span data-stu-id="a9121-313">Wait until SQLEXPR_x64.exe finishes before proceeding to the next step:</span></span>

    <span data-ttu-id="a9121-314">SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine，Tools /INSTANCENAME=LYNCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT=1 "NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automatic</span><span class="sxs-lookup"><span data-stu-id="a9121-314">SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=LYNCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automatic</span></span>
1. <span data-ttu-id="a9121-315">运行 Skype for Business Server 2015 RTM 安装程序。</span><span class="sxs-lookup"><span data-stu-id="a9121-315">Run Skype for Business Server 2015 RTM setup.</span></span>
2. <span data-ttu-id="a9121-316">按照上述先决条件部分的剩余步骤操作。</span><span class="sxs-lookup"><span data-stu-id="a9121-316">Follow the remaining steps from the prerequisites section above.</span></span>

<span data-ttu-id="a9121-317">**选项 3：** 还可以手动替换本地安装媒体目录中的二进制文件，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a9121-317">**Option 3:** You may also manually replace binaries in a local installation media directory as follows:</span></span>

1. [<span data-ttu-id="a9121-318">安装 Skype for Business Server 的先决条件</span><span class="sxs-lookup"><span data-stu-id="a9121-318">Install prerequisites for Skype for Business Server</span></span>](../../deploy/install/install-prerequisites.md)  
2. <span data-ttu-id="a9121-319">安装 .NET 4.7：</span><span class="sxs-lookup"><span data-stu-id="a9121-319">Install .NET 4.7:</span></span> 
      - <span data-ttu-id="a9121-320">**注意：** 我们首先在 Skype for Business Server 2015 CU5 (6.0.9319.281 中引入了对 .NET 4.7 的支持) 。</span><span class="sxs-lookup"><span data-stu-id="a9121-320">**Note:** We first introduced support for .NET 4.7 in Skype for Business Server 2015 CU5 (6.0.9319.281).</span></span> <span data-ttu-id="a9121-321">因此，在下面的步骤中，我们将在主要安装之前更新核心组件。</span><span class="sxs-lookup"><span data-stu-id="a9121-321">Therefore, in later steps below we will be updating Core Components prior to the main install.</span></span>
      - <span data-ttu-id="a9121-322">下载： https://www.microsoft.com/download/details.aspx?id=55167 。</span><span class="sxs-lookup"><span data-stu-id="a9121-322">Download: https://www.microsoft.com/download/details.aspx?id=55167.</span></span> 
      - <span data-ttu-id="a9121-323">参考[：应在 Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)部署之前安装的软件</span><span class="sxs-lookup"><span data-stu-id="a9121-323">Reference: [Software that should be installed before a Skype for Business Server 2015 deployment](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)</span></span>
3. <span data-ttu-id="a9121-324">复制 ISO 文件/文件夹：</span><span class="sxs-lookup"><span data-stu-id="a9121-324">Copy ISO Files/Folders:</span></span> 
    - <span data-ttu-id="a9121-325">附加 Skype for Business Server 2015 ISO 后，在文件资源管理器中打开它作为 (Ex： D： 连接的驱动器 \) 的根目录。</span><span class="sxs-lookup"><span data-stu-id="a9121-325">With the Skype for Business Server 2015 ISO attached, open the root directory of the drive it is attached as (Ex: D:\) in File Explorer.</span></span>
    - <span data-ttu-id="a9121-326">将所有文件夹和文件复制到本地磁盘上的文件夹 (例如：C：\SkypeForBusiness2015ISO) 。</span><span class="sxs-lookup"><span data-stu-id="a9121-326">Copy all folders and files to a folder on a local disk (Ex: C:\SkypeForBusiness2015ISO).</span></span>
    - <span data-ttu-id="a9121-327">**注意：** 在安装组件之前，需要更新某些文件以支持 TLS 1.2。</span><span class="sxs-lookup"><span data-stu-id="a9121-327">**Note:** Prior to installing components, some files will need to be updated for support of TLS 1.2.</span></span>
4. <span data-ttu-id="a9121-328">替换 MSI/EXE 包：</span><span class="sxs-lookup"><span data-stu-id="a9121-328">Replace MSI/EXE Packages:</span></span> 
    - <span data-ttu-id="a9121-329">替换本地计算机上安装媒体的 /Setup/amd64/ 文件夹中的现有 MSI 和 EXE 包。</span><span class="sxs-lookup"><span data-stu-id="a9121-329">Replace the existing MSI and EXE packages in the /Setup/amd64/ folder of the installation media on the local machine.</span></span>
    - <span data-ttu-id="a9121-330">SQL 2014 SP2 Express： https://www.microsoft.com/download/details.aspx?id=53167</span><span class="sxs-lookup"><span data-stu-id="a9121-330">SQL 2014 SP2 Express: https://www.microsoft.com/download/details.aspx?id=53167</span></span> 
        - <span data-ttu-id="a9121-331">重命名为SQLEXPR_x64计算机上的名称，并替换安装媒体的 Setup/amd64/ 文件夹中的现有文件。</span><span class="sxs-lookup"><span data-stu-id="a9121-331">Rename to SQLEXPR_x64 on the local machine, and replace the existing file in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="a9121-332">SQL本机客户端： https://www.microsoft.com/download/details.aspx?id=50402</span><span class="sxs-lookup"><span data-stu-id="a9121-332">SQL Native Client: https://www.microsoft.com/download/details.aspx?id=50402</span></span> 
        - <span data-ttu-id="a9121-333">**注意：** 如有必要，请重命名sqlncli.msi，然后替换安装媒体的 Setup/amd64/ 文件夹中的现有文件。</span><span class="sxs-lookup"><span data-stu-id="a9121-333">**Note:** Rename this if necessary to sqlncli.msi, and then replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="a9121-334">SQL管理对象： https://www.microsoft.com/download/details.aspx?id=53164</span><span class="sxs-lookup"><span data-stu-id="a9121-334">SQL Management Objects: https://www.microsoft.com/download/details.aspx?id=53164</span></span> 
        - <span data-ttu-id="a9121-335">**注意：** 功能包将有很多可下载的项目。</span><span class="sxs-lookup"><span data-stu-id="a9121-335">**Note:** The Feature pack will have a lot of items that can be downloaded.</span></span> <span data-ttu-id="a9121-336">选择以仅SharedManagementObjects.msi下载。</span><span class="sxs-lookup"><span data-stu-id="a9121-336">Select to download SharedManagementObjects.msi only.</span></span>
        - <span data-ttu-id="a9121-337">**注意：** 替换安装媒体的 Setup/amd64/ 文件夹中的现有文件。</span><span class="sxs-lookup"><span data-stu-id="a9121-337">**Note:** Replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="a9121-338">SQL CLR 类型： https://www.microsoft.com/download/details.aspx?id=53164</span><span class="sxs-lookup"><span data-stu-id="a9121-338">SQL CLR Types: https://www.microsoft.com/download/details.aspx?id=53164</span></span> 
        - <span data-ttu-id="a9121-339">**注意：** 功能包将有很多可下载的项目。</span><span class="sxs-lookup"><span data-stu-id="a9121-339">**Note:** The Feature pack will have a lot of items that can be downloaded.</span></span> <span data-ttu-id="a9121-340">选择仅CQLSysClrTypes.msi下载</span><span class="sxs-lookup"><span data-stu-id="a9121-340">Select to download CQLSysClrTypes.msi only</span></span>
        - <span data-ttu-id="a9121-341">**注意**：替换安装媒体的 Setup/amd64/ 文件夹中的现有文件。</span><span class="sxs-lookup"><span data-stu-id="a9121-341">**Note**: Replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
5. <span data-ttu-id="a9121-342">安装核心组件：</span><span class="sxs-lookup"><span data-stu-id="a9121-342">Install Core Components:</span></span> 
    - <span data-ttu-id="a9121-343">从Setup.exe的 Setup/amd64/ 文件夹中运行安装程序。</span><span class="sxs-lookup"><span data-stu-id="a9121-343">Run Setup.exe from the Setup/amd64/ folder of the installation media.</span></span> <span data-ttu-id="a9121-344">按照说明安装核心组件</span><span class="sxs-lookup"><span data-stu-id="a9121-344">Follow the instructions to install Core Components</span></span>
    - <span data-ttu-id="a9121-345">关闭核心组件。</span><span class="sxs-lookup"><span data-stu-id="a9121-345">Close Core Components.</span></span>
6. <span data-ttu-id="a9121-346">更新核心组件：</span><span class="sxs-lookup"><span data-stu-id="a9121-346">Update Core Components:</span></span> 
    - <span data-ttu-id="a9121-347">下载 Skype for Business 更新安装程序。</span><span class="sxs-lookup"><span data-stu-id="a9121-347">Download the Skype for Business Update Installer.</span></span>
    - <span data-ttu-id="a9121-348">运行安装程序以更新核心组件并安装性能计数器。</span><span class="sxs-lookup"><span data-stu-id="a9121-348">Run the installer to update Core Components and install the performance counters.</span></span>
    - <span data-ttu-id="a9121-349">**注意：** 自 CU6HF2 发布起，自动更新功能当前最多只能安装 CU6。</span><span class="sxs-lookup"><span data-stu-id="a9121-349">**Note:** As of the release of CU6HF2, the auto-update feature currently only will install up to CU6.</span></span> <span data-ttu-id="a9121-350">因此，更新程序必须单独运行，以将核心组件更新为 6.0.9319.516。</span><span class="sxs-lookup"><span data-stu-id="a9121-350">Therefore, the updater must be run separately to update Core Components to 6.0.9319.516.</span></span>
    - <span data-ttu-id="a9121-351">参考： https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015</span><span class="sxs-lookup"><span data-stu-id="a9121-351">Reference: https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015</span></span>
7. <span data-ttu-id="a9121-352">安装管理工具 (可选) ：</span><span class="sxs-lookup"><span data-stu-id="a9121-352">Install Administrative Tools (Optional):</span></span> 
    - <span data-ttu-id="a9121-353">这将使用更新的文件安装 Microsoft SQL Server 2012 Native Client、SQL Server 2014 Management Objects (x64) 和 Microsoft System CLR Types for SQL Server 2014 (x64) 。</span><span class="sxs-lookup"><span data-stu-id="a9121-353">This will install the Microsoft SQL Server 2012 Native Client, SQL Server 2014 Management Objects (x64), and Microsoft System CLR Types for SQL Server 2014 (x64) using the updated files.</span></span> <span data-ttu-id="a9121-354">此外，本地计算机上还将提供 Skype for Business Server 2015 拓扑生成器和控制面板。</span><span class="sxs-lookup"><span data-stu-id="a9121-354">Additionally, the Skype for Business Server 2015 Topology Builder and Control Panel will be available on the local machine.</span></span>
8. <span data-ttu-id="a9121-355">安装本地配置存储 (步骤 1) ：</span><span class="sxs-lookup"><span data-stu-id="a9121-355">Install Local Configuration Store (Step 1):</span></span> 
     - <span data-ttu-id="a9121-356">打开部署向导，单击"安装或更新 Skype for Business Server系统"，然后单击"步骤 1：安装本地配置存储"中的"运行"。</span><span class="sxs-lookup"><span data-stu-id="a9121-356">Open the Deployment Wizard, click Install or Update Skype for Business Server System, and click on **Run** at Step 1: Install Local Configuration Store.</span></span>
     - <span data-ttu-id="a9121-357">在 **"** 安装本地配置 **存储"对话框中单击"下一** 步"。</span><span class="sxs-lookup"><span data-stu-id="a9121-357">Click **Next** in the **Install Local Configuration Store** dialog box.</span></span>
     <span data-ttu-id="a9121-358">!["安装本地配置存储"对话框](../../media/local-configuration-store.png)</span><span class="sxs-lookup"><span data-stu-id="a9121-358">![Install Local Configuration Store dialog box](../../media/local-configuration-store.png)</span></span>
     - <span data-ttu-id="a9121-359">查看结果，并确保任务状态已完成。</span><span class="sxs-lookup"><span data-stu-id="a9121-359">Review the results, and ensure that the Task Status is Completed.</span></span> <span data-ttu-id="a9121-360">通过单击"日志文件日志 **"查看生成的结果**。</span><span class="sxs-lookup"><span data-stu-id="a9121-360">Review the resulting log file by clicking **View Log**.</span></span>
     <span data-ttu-id="a9121-361">![任务状态将显示为"已完成"](../../media/local-configuration-task-completed.png)</span><span class="sxs-lookup"><span data-stu-id="a9121-361">![Task status shows as Completed](../../media/local-configuration-task-completed.png)</span></span>
     - <span data-ttu-id="a9121-362">单击“完成”。</span><span class="sxs-lookup"><span data-stu-id="a9121-362">Click **Finish**.</span></span>
9. <span data-ttu-id="a9121-363">在步骤 2 中设置 (或删除 Skype for Business Server) ：</span><span class="sxs-lookup"><span data-stu-id="a9121-363">Set up or remove Skype for Business Server Components (Step 2):</span></span>
    - <span data-ttu-id="a9121-364">打开部署向导，单击 **"安装或** 更新 Skype for Business Server系统"，然后单击"步骤 2：设置或删除 Skype for Business Server 组件"中的"运行"</span><span class="sxs-lookup"><span data-stu-id="a9121-364">Open the Deployment Wizard, click **Install or Update Skype for Business Server System**, and click **Run** at Step 2: Set up or Remove Skype for Business Server Components</span></span>
    - <span data-ttu-id="a9121-365">在 **"** 设置 Skype for Business Server 组件"对话框中单击"下一步"。</span><span class="sxs-lookup"><span data-stu-id="a9121-365">Click **Next** in the Set Up Skype for Business Server Components dialog box.</span></span>
    <span data-ttu-id="a9121-366">!["设置 Skype for Business Server 组件"窗口](../../media/set-up-skype-for-business-server-components-window.png)</span><span class="sxs-lookup"><span data-stu-id="a9121-366">![the Set Up Skype for Business Server Components window](../../media/set-up-skype-for-business-server-components-window.png)</span></span>
    - <span data-ttu-id="a9121-367">使用视图日志查看日志，并验证安装程序是否已完成且没有问题。</span><span class="sxs-lookup"><span data-stu-id="a9121-367">Review the log using View Log, and validate that setup completed without issues.</span></span> 
    - <span data-ttu-id="a9121-368">单击“完成”。</span><span class="sxs-lookup"><span data-stu-id="a9121-368">Click **Finish**.</span></span>
10. <span data-ttu-id="a9121-369">如果需要，请继续其他安装和配置 (此时可以恢复正常安装) 。</span><span class="sxs-lookup"><span data-stu-id="a9121-369">Proceed with additional installation and configuration as required (you can resume normal installation procedures at this point).</span></span>
