---
title: 为业务 Server 2015 禁用 TLS 1.0/1.1 中 Skype
ms.author: heidip
author: heidip
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 摘要： 准备，并在您的环境中实现禁用 TLS 1.0 和 1.1。
ms.openlocfilehash: 784b6b307275516a18b396864d1a2c4f40c285e8
ms.sourcegitcommit: 2e11749734ff26b18709a1442b2c417f33430144
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/05/2018
ms.locfileid: "25429443"
---
# <a name="disable-tls-1011-in-skype-for-business-server-2015"></a><span data-ttu-id="53dbf-103">为业务 Server 2015 禁用 TLS 1.0/1.1 中 Skype</span><span class="sxs-lookup"><span data-stu-id="53dbf-103">Disable TLS 1.0/1.1 in Skype for Business Server 2015</span></span>

<span data-ttu-id="53dbf-104">本文旨在提供针对您准备和在您的环境中实现禁用 TLS 1.0 和 1.1 的必要指导。</span><span class="sxs-lookup"><span data-stu-id="53dbf-104">The purpose of this article is to provide the necessary guidance for you to prepare for and implement disabling TLS 1.0 and 1.1 in your environments.</span></span> <span data-ttu-id="53dbf-105">此过程要求广泛的规划和准备。</span><span class="sxs-lookup"><span data-stu-id="53dbf-105">This process requires extensive planning and preparation.</span></span> <span data-ttu-id="53dbf-106">请仔细检查所有这篇文章中的信息，使您的计划来禁用 TLS 1.0 和为您的组织的 1.1。</span><span class="sxs-lookup"><span data-stu-id="53dbf-106">Please carefully review all of the information in this article as you make your plan to disable TLS 1.0 and 1.1 for your organization.</span></span> <span data-ttu-id="53dbf-107">请注意，有许多外部依赖项和可能会受到禁用 TLS 1.0/1.1 的连接情况，因此全面的规划和测试确有必要。</span><span class="sxs-lookup"><span data-stu-id="53dbf-107">Note that there are many external dependencies and connectivity conditions that could be impacted by disabling TLS 1.0/1.1, so extensive planning and testing is warranted.</span></span>

## <a name="in-this-article"></a><span data-ttu-id="53dbf-108">本文中</span><span class="sxs-lookup"><span data-stu-id="53dbf-108">In this article</span></span>

- [<span data-ttu-id="53dbf-109">背景和范围</span><span class="sxs-lookup"><span data-stu-id="53dbf-109">Background and scope</span></span>](#background)
- [<span data-ttu-id="53dbf-110">先决条件和过程</span><span class="sxs-lookup"><span data-stu-id="53dbf-110">Prerequisites and process</span></span>](#prerequisites-and-process)
- [<span data-ttu-id="53dbf-111">高级的部署方案</span><span class="sxs-lookup"><span data-stu-id="53dbf-111">Advanced deployment scenarios</span></span>](#advanced-deployment-scenarios)

## <a name="background"></a><span data-ttu-id="53dbf-112">背景</span><span class="sxs-lookup"><span data-stu-id="53dbf-112">Background</span></span>

<span data-ttu-id="53dbf-113">提供了 TLS 1.0 和 1.1 禁用支持的 Skype 的业务 Server 内部部署的主要驱动程序支付卡行业 (PCI) 安全标准委员会和美国联邦信息处理标准要求。</span><span class="sxs-lookup"><span data-stu-id="53dbf-113">The primary drivers for providing TLS 1.0 and 1.1 disable support for Skype for Business Server On-Premises are Payment Card Industry (PCI) Security Standards Council and Federal Information Processing Standards requirements.</span></span> <span data-ttu-id="53dbf-114">可以找到 PCI 要求的详细信息[此处](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls)。</span><span class="sxs-lookup"><span data-stu-id="53dbf-114">More information for PCI requirements can be found [here](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls).</span></span>  <span data-ttu-id="53dbf-115">Microsoft 不能提供有关您的组织需要遵守这些或其他要求的指南。</span><span class="sxs-lookup"><span data-stu-id="53dbf-115">Microsoft cannot provide guidance on whether or not your organization is required to adhere to these or other requirements.</span></span> <span data-ttu-id="53dbf-116">您必须确定它是否需要为您要禁用 TLS 1.0 和/或 1.1 您环境中。</span><span class="sxs-lookup"><span data-stu-id="53dbf-116">You must determine if it is required for you to disable TLS 1.0 and/or 1.1 in your environments.</span></span>

<span data-ttu-id="53dbf-117">Microsoft 提供了在 TLS 可用[下面](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/)的白皮书，我们还建议读取此[Exchange 博客](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)中提供的背景。</span><span class="sxs-lookup"><span data-stu-id="53dbf-117">Microsoft has produced a white paper on TLS available [here](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/), and we also recommend the background reading available in this [Exchange blog](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/).</span></span>

## <a name="supportability-scope"></a><span data-ttu-id="53dbf-118">可支持性范围</span><span class="sxs-lookup"><span data-stu-id="53dbf-118">Supportability Scope</span></span>

<span data-ttu-id="53dbf-119">*范围*是指可支持性边界。</span><span class="sxs-lookup"><span data-stu-id="53dbf-119">*Scope* refers to supportability boundaries.</span></span> <span data-ttu-id="53dbf-120">Skype 的业务 Server 内部部署，为*范围内*是指我们完全支持，并禁用 TLS 1.0 和列出的产品版本 1.1 的测试。</span><span class="sxs-lookup"><span data-stu-id="53dbf-120">For Skype for Business Server On-Premises, *in scope* means we fully support and have tested disabling of TLS 1.0 and 1.1 for the listed product versions.</span></span> <span data-ttu-id="53dbf-121">*当前正在调查*意味着我们正在主动研究如何为 TLS 禁用支持进入范围将这些产品。</span><span class="sxs-lookup"><span data-stu-id="53dbf-121">*Currently being investigated* means just that; we are actively investigating bringing these products into scope for TLS disable support.</span></span> <span data-ttu-id="53dbf-122">*超出范围*意味着这些产品版本不支持禁用 TLS 1.0 或 1.1 并且将不起作用，与指定例外。</span><span class="sxs-lookup"><span data-stu-id="53dbf-122">*Out of scope* means these product versions do not support disabling TLS 1.0 or 1.1 and will not work, with noted exceptions.</span></span>

### <a name="fully-tested-and-supported-servers"></a><span data-ttu-id="53dbf-123">充分测试和支持的服务器</span><span class="sxs-lookup"><span data-stu-id="53dbf-123">Fully tested and supported servers</span></span>

- <span data-ttu-id="53dbf-124">Skype 业务服务器 2019</span><span class="sxs-lookup"><span data-stu-id="53dbf-124">Skype for Business Server 2019</span></span>
- <span data-ttu-id="53dbf-125">Skype 的业务服务器 2015 CU6 HF2 6.0.9319.516 （[2018 年 3 月更新](https://support.microsoft.com/en-us/help/4086059/march-2018-cumulative-update-6-0-9319-516-for-skype-for-business)） 和更高版本上：</span><span class="sxs-lookup"><span data-stu-id="53dbf-125">Skype for Business Server 2015 CU6 HF2 6.0.9319.516 ([March 2018 update](https://support.microsoft.com/en-us/help/4086059/march-2018-cumulative-update-6-0-9319-516-for-skype-for-business)) and higher on:</span></span> 
    - <span data-ttu-id="53dbf-126">（与 KB 3140245 或取代更新） 的 Windows Server 2012、 2012 R2 或 2016</span><span class="sxs-lookup"><span data-stu-id="53dbf-126">Windows Server 2012 (with KB 3140245 or superseding update), 2012 R2 or 2016</span></span>
- <span data-ttu-id="53dbf-127">就地升级业务服务器 2015，与 CU6 HF2 和更高版本上的 Skype</span><span class="sxs-lookup"><span data-stu-id="53dbf-127">In-place Upgraded Skype for Business Server 2015, with CU6 HF2 and higher on</span></span> 
    - <span data-ttu-id="53dbf-128">Windows Server 2008 R2，2012 （与 KB [3140245](https://support.microsoft.com/en-us/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in)或取代更新） 或 2012 R2</span><span class="sxs-lookup"><span data-stu-id="53dbf-128">Windows Server 2008 R2, 2012 (with KB [3140245](https://support.microsoft.com/en-us/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) or superseding update), or 2012 R2</span></span>
- <span data-ttu-id="53dbf-129">Exchange 连接和 Outlook Web App 与 Exchange Server 2010 SP3 RU19 或更高版本，指南[此处](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)</span><span class="sxs-lookup"><span data-stu-id="53dbf-129">Exchange Connectivity and Outlook Web App with Exchange Server 2010 SP3 RU19 or higher, guidance [here](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)</span></span>
 
### <a name="fully-tested-and-supported-clients"></a><span data-ttu-id="53dbf-130">充分测试和支持的客户端</span><span class="sxs-lookup"><span data-stu-id="53dbf-130">Fully tested and supported clients</span></span>

- <span data-ttu-id="53dbf-131">Lync 2013 (for Business 的 Skype) 桌面客户端、 MSI 和 C2R，包括基本[15.0.5023.1000 及更高](https://support.microsoft.com/en-us/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)</span><span class="sxs-lookup"><span data-stu-id="53dbf-131">Lync 2013 (Skype for Business) Desktop Client, MSI and C2R, including Basic [15.0.5023.1000 and higher](https://support.microsoft.com/en-us/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)</span></span>
- <span data-ttu-id="53dbf-132">Skype 业务 2016年桌面客户端，MSI [16.0.4678.1000 及更高](https://support.microsoft.com/en-us/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323)，包括基本</span><span class="sxs-lookup"><span data-stu-id="53dbf-132">Skype for Business 2016 Desktop Client, MSI [16.0.4678.1000 and higher](https://support.microsoft.com/en-us/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323), including Basic</span></span>
- <span data-ttu-id="53dbf-133">业务 2016年单击要运行的 Skype 需要[年 4 月 2018年](https://docs.microsoft.com/en-us/officeupdates/release-notes-office365-proplus)更新：</span><span class="sxs-lookup"><span data-stu-id="53dbf-133">Skype for Business 2016 Click to Run Require the [April 2018](https://docs.microsoft.com/en-us/officeupdates/release-notes-office365-proplus) Updates:</span></span> 
    - <span data-ttu-id="53dbf-134">每月和半年目标，16\.0\.9126\.2152年及更高</span><span class="sxs-lookup"><span data-stu-id="53dbf-134">Monthly and Semi-Annual Targeted, 16\.0\.9126\.2152 and higher</span></span>
    - <span data-ttu-id="53dbf-135">半年和推迟通道，16\.0\.8431\.2242年及更高</span><span class="sxs-lookup"><span data-stu-id="53dbf-135">Semi-Annual and Deferred Channel, 16\.0\.8431\.2242 and higher</span></span>
- <span data-ttu-id="53dbf-136">Skype for Business 上 Mac 16.15 和更高版本</span><span class="sxs-lookup"><span data-stu-id="53dbf-136">Skype for Business on Mac 16.15 and higher</span></span>
- <span data-ttu-id="53dbf-137">Skype 的 iOS 和 Android 6.19 业务及更高</span><span class="sxs-lookup"><span data-stu-id="53dbf-137">Skype for Business for iOS and Android 6.19 and higher</span></span>
- <span data-ttu-id="53dbf-138">Skype Web 应用程序 2015 CU6 HF2 和更高版本 （附带服务器）</span><span class="sxs-lookup"><span data-stu-id="53dbf-138">Skype Web App 2015 CU6 HF2 and higher (ships with Server)</span></span>

### <a name="currently-being-investigated"></a><span data-ttu-id="53dbf-139">当前正在调查</span><span class="sxs-lookup"><span data-stu-id="53dbf-139">Currently being investigated</span></span>

#### <a name="devices"></a><span data-ttu-id="53dbf-140">设备</span><span class="sxs-lookup"><span data-stu-id="53dbf-140">Devices</span></span>

- <span data-ttu-id="53dbf-141">Lync 会议室系统 （也</span><span class="sxs-lookup"><span data-stu-id="53dbf-141">Lync Room System (a.k.a.</span></span> <span data-ttu-id="53dbf-142">SRSv1)</span><span class="sxs-lookup"><span data-stu-id="53dbf-142">SRSv1)</span></span>
- <span data-ttu-id="53dbf-143">Skype 会议室系统 v2 （也</span><span class="sxs-lookup"><span data-stu-id="53dbf-143">Skype Room Systems v2 (a.k.a.</span></span> <span data-ttu-id="53dbf-144">SRSv2)</span><span class="sxs-lookup"><span data-stu-id="53dbf-144">SRSv2)</span></span>
- <span data-ttu-id="53dbf-145">Surface Hub</span><span class="sxs-lookup"><span data-stu-id="53dbf-145">Surface Hub</span></span>
- <span data-ttu-id="53dbf-146">2015 基于 Survivable Branch Appliance (SBA) 或 Survivable Branch Server (SBS)</span><span class="sxs-lookup"><span data-stu-id="53dbf-146">2015 based Survivable Branch Appliance (SBA) or Survivable Branch Server (SBS)</span></span>

#### <a name="other"></a><span data-ttu-id="53dbf-147">其他</span><span class="sxs-lookup"><span data-stu-id="53dbf-147">Other</span></span>

- <span data-ttu-id="53dbf-148">呼叫质量仪表板 （已禁用 TLS 1.0，1.1 之后的新安装，请参阅下面） \*</span><span class="sxs-lookup"><span data-stu-id="53dbf-148">Call Quality Dashboard (new install after TLS 1.0, 1.1 have been disabled, see below)\*</span></span>
 
### <a name="out-of-scope"></a><span data-ttu-id="53dbf-149">超出范围</span><span class="sxs-lookup"><span data-stu-id="53dbf-149">Out of scope</span></span>

<span data-ttu-id="53dbf-150">除非另有说明，以下产品不在 TLS 1.0/1.1 禁用支持的范围内，将无法正常 TLS 1.0 和 1.1 其中已禁用的环境中。</span><span class="sxs-lookup"><span data-stu-id="53dbf-150">Except where noted, the following products are not in scope for TLS 1.0/1.1 disable support and will not function in an environment where TLS 1.0 and 1.1 have been disabled.</span></span>  <span data-ttu-id="53dbf-151">这意味着： 如果您仍可以利用超出范围服务器或客户端，您必须更新或删除这些，如果您需要禁用 TLS 1.0/1.1 无处不在您 Skype 的业务服务器本地部署。</span><span class="sxs-lookup"><span data-stu-id="53dbf-151">What this means: if you still utilize out-of-scope servers or clients, you must update or remove these if you need to disable TLS 1.0/1.1 anywhere in your Skype for Business Server on-premises deployment.</span></span>

- <span data-ttu-id="53dbf-152">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="53dbf-152">Lync Server 2013</span></span>
- <span data-ttu-id="53dbf-153">Windows Server 2008 及更低</span><span class="sxs-lookup"><span data-stu-id="53dbf-153">Windows Server 2008 and lower</span></span>
- <span data-ttu-id="53dbf-154">Lync for Mac 2011</span><span class="sxs-lookup"><span data-stu-id="53dbf-154">Lync for Mac 2011</span></span>
- <span data-ttu-id="53dbf-155">Lync 2013 mobile-iOS、 iPad、 Android 或 Windows Phone</span><span class="sxs-lookup"><span data-stu-id="53dbf-155">Lync 2013 for Mobile - iOS, iPad, Android or Windows Phone</span></span>
- <span data-ttu-id="53dbf-156">Lync"MX"Windows 应用商店客户端</span><span class="sxs-lookup"><span data-stu-id="53dbf-156">Lync "MX" Windows Store client</span></span>
- <span data-ttu-id="53dbf-157">所有 Lync 2010 客户端</span><span class="sxs-lookup"><span data-stu-id="53dbf-157">All Lync 2010 clients</span></span>
- <span data-ttu-id="53dbf-158">Lync Phone Edition-更新的指南[下面](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035)。</span><span class="sxs-lookup"><span data-stu-id="53dbf-158">Lync Phone Edition - updated guidance [here](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035).</span></span>
- <span data-ttu-id="53dbf-159">2013 基于 Survivable Branch Appliance (SBA) 或 Survivable Branch Server (SBS)</span><span class="sxs-lookup"><span data-stu-id="53dbf-159">2013 based Survivable Branch Appliance (SBA) or Survivable Branch Server (SBS)</span></span>

### <a name="exceptions"></a><span data-ttu-id="53dbf-160">异常</span><span class="sxs-lookup"><span data-stu-id="53dbf-160">Exceptions</span></span>

#### <a name="lync-server-2013"></a><span data-ttu-id="53dbf-161">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="53dbf-161">Lync Server 2013</span></span>

<span data-ttu-id="53dbf-162">Lync Server 2013 承担 Windows Fabric 1.0 版的依赖关系。</span><span class="sxs-lookup"><span data-stu-id="53dbf-162">Lync Server 2013 takes a dependency on Windows Fabric version 1.0.</span></span>  <span data-ttu-id="53dbf-163">在 Lync Server 2013 的设计阶段，Windows Fabric 1.0 已选择其令人信服和新分布式体系结构来提供复制、 高可用性和容错能力。</span><span class="sxs-lookup"><span data-stu-id="53dbf-163">In the design phase for Lync Server 2013, Windows Fabric 1.0 was chosen for its compelling and new distributed architecture to provide replication, high availability, and fault tolerance.</span></span>  <span data-ttu-id="53dbf-164">随时间推移，这两个 Skype Business Server 和 Windows Fabric 大大提高了重大重新设计后续版本中使用此联合体系结构。</span><span class="sxs-lookup"><span data-stu-id="53dbf-164">Over time, both Skype for Business Server and Windows Fabric have greatly improved this joint architecture with significant re-design in subsequent versions.</span></span>  <span data-ttu-id="53dbf-165">当前 Skype 业务 2015年服务器使用 Windows Fabric 3.0，例如。</span><span class="sxs-lookup"><span data-stu-id="53dbf-165">Current Skype for Business 2015 Server uses Windows Fabric 3.0, for example.</span></span>

<span data-ttu-id="53dbf-166">遗憾的是，Windows Fabric 1.0**不支持 TLS 1.2。 但是，我们将在更新 Lync Server 2013 以使用 TLS 1.2**。</span><span class="sxs-lookup"><span data-stu-id="53dbf-166">Unfortunately, Windows Fabric 1.0 **does not support TLS 1.2.  However, we will be updating Lync Server 2013 to work with TLS 1.2**.</span></span> <span data-ttu-id="53dbf-167">这将在下一步 Lync Server 2013 的累积更新中即将。</span><span class="sxs-lookup"><span data-stu-id="53dbf-167">This will be coming in the next Cumulative Update for Lync Server 2013.</span></span>  <span data-ttu-id="53dbf-168">我们提供 TLS 1.2 支持启用共存、 迁移、 联合和混合方案。</span><span class="sxs-lookup"><span data-stu-id="53dbf-168">We're providing TLS 1.2 support to enable co-existence, migration, federation, and hybrid scenarios.</span></span>

<span data-ttu-id="53dbf-169">如果您的组织需要禁用 TLS 1.0 和 1.1 中，并且您目前使用 Lync Server 2013，我们建议您开始规划过程、 的可能性您可能遇到的就地升级或-并行迁移到 Skype 的 （新池，移动用户）业务服务器 2015年或更高版本。</span><span class="sxs-lookup"><span data-stu-id="53dbf-169">If your organization is required to disable TLS 1.0 and 1.1, and you currently use Lync Server 2013, we recommend you begin your planning process, with the possibility you may have to In-place upgrade or Side-by-Side migrate (new pools, move users) to Skype for Business Server 2015 or higher.</span></span>  <span data-ttu-id="53dbf-170">或者，您可能想要迁移到 Skype 加速业务 online。</span><span class="sxs-lookup"><span data-stu-id="53dbf-170">Or you may want to accelerate migration to Skype for Business Online.</span></span>

#### <a name="call-quality-dashboard"></a><span data-ttu-id="53dbf-171">通话质量仪表板</span><span class="sxs-lookup"><span data-stu-id="53dbf-171">Call Quality Dashboard</span></span>

<span data-ttu-id="53dbf-172">在本地呼叫质量仪表板当前依赖 TLS 1.0 在新的安装 （到您的本地环境中安装第一次）。</span><span class="sxs-lookup"><span data-stu-id="53dbf-172">On-Premises Call Quality Dashboard currently has a dependency on TLS 1.0 during new install (first time installing into your On-Premises environments).</span></span>  <span data-ttu-id="53dbf-173">我们当前正在调查此问题，并计划在将来版本修复。</span><span class="sxs-lookup"><span data-stu-id="53dbf-173">We are currently investigating this issue and plan to release a fix in the near future.</span></span>  <span data-ttu-id="53dbf-174">如果您计划安装 CQD 和还禁用 TLS 1.0，我们建议您首先，完成 CQD 安装，然后继续进行 TLS 1.0 禁用。</span><span class="sxs-lookup"><span data-stu-id="53dbf-174">If you are planning to install CQD and also disable TLS 1.0, we recommend that you complete CQD installation first, and then proceed with TLS 1.0 disabling.</span></span>

#### <a name="third-party-devices"></a><span data-ttu-id="53dbf-175">第三方设备</span><span class="sxs-lookup"><span data-stu-id="53dbf-175">Third-party devices</span></span>

<span data-ttu-id="53dbf-176">在第三方设备，如 3PIP 电话，视频会议，反向代理和负载平衡器，请务必验证 TLS 1.2 可支持性和测试仔细，如果需要请联系供应商。</span><span class="sxs-lookup"><span data-stu-id="53dbf-176">On third-party devices such as 3PIP phones, Video conferencing, Reverse Proxies and Load Balancers, be sure to validate TLS 1.2 supportability, test carefully, and contact the vendor if needed.</span></span>

### <a name="federation-considerations-when-disabling-tls-1011-on-edge-servers"></a><span data-ttu-id="53dbf-177">联合身份验证边缘服务器上禁用 TLS 1.0/1.1 时的注意事项</span><span class="sxs-lookup"><span data-stu-id="53dbf-177">Federation considerations when disabling TLS 1.0/1.1 on Edge servers</span></span>

<span data-ttu-id="53dbf-178">仔细规划还必须考虑的边缘服务器上禁用 TLS 1.0/1.1 影响。</span><span class="sxs-lookup"><span data-stu-id="53dbf-178">You must carefully plan for and consider the impact of disabling TLS 1.0/1.1 on your Edge servers.</span></span>  <span data-ttu-id="53dbf-179">一旦禁用 TLS 1.0 和 1.1，您可能会发现，其他组织将不再能够与您的组织建立联盟。</span><span class="sxs-lookup"><span data-stu-id="53dbf-179">Once TLS 1.0 and 1.1 are disabled, you may find that other organizations are no longer be able to federate with your organization.</span></span>

<span data-ttu-id="53dbf-180">您可以选择保留 TLS 1.0/1.1 边缘服务器上的启用以保持向后兼容的非修补 (SfB 2015，Lync 2013) 或旧 (2010) 的外部系统。</span><span class="sxs-lookup"><span data-stu-id="53dbf-180">You may opt to keep TLS 1.0/1.1 enabled on your Edge servers to maintain backward compatibility with non-patched (SfB 2015, Lync 2013) or older (2010) external systems.</span></span>

<span data-ttu-id="53dbf-181">Microsoft 不能在您在边缘网络 （或任何网络） 属于下一级 PCI 标准; 提供意见或建议必须由单个公司确定的。</span><span class="sxs-lookup"><span data-stu-id="53dbf-181">Microsoft cannot provide advice or recommendations on whether or not your Edge network (or any network) falls under PCI standard; that must be determined by the individual company.</span></span>

<span data-ttu-id="53dbf-182">业务 online Skype 是能够如今，TLS 1.2，因此预期对与 Online 混合/联盟没有任何影响。</span><span class="sxs-lookup"><span data-stu-id="53dbf-182">Skype for Business Online is capable of TLS 1.2 today, so no impact to Hybrid/Federation with Online is expected.</span></span>

<span data-ttu-id="53dbf-183">Skype 使用者服务 PIC （公共 IM 连接）： 我们不希望禁用 TLS 1.0/1.1 影响[Skype 连接](../../deploy/deploy-skype-connectivity.md);Microsoft PIC 网关已 TLS 1.2 能够。</span><span class="sxs-lookup"><span data-stu-id="53dbf-183">PIC (Public IM Connectivity) to Skype Consumer service: We do not expect disabling TLS 1.0/1.1 to impact [Skype Connectivity](../../deploy/deploy-skype-connectivity.md); Microsoft PIC Gateways are already TLS 1.2 capable.</span></span>

## <a name="prerequisites-and-process"></a><span data-ttu-id="53dbf-184">先决条件和过程</span><span class="sxs-lookup"><span data-stu-id="53dbf-184">Prerequisites and process</span></span>

<span data-ttu-id="53dbf-185">除了上文所述，其中一次，TLS 1.0 和 1.1 均已禁用的范围外服务器，客户端和设备将继续正常工作，或者根本。</span><span class="sxs-lookup"><span data-stu-id="53dbf-185">Except where noted above, once TLS 1.0 and 1.1 are disabled out-of-scope servers, clients and devices will longer function properly, or at all.</span></span> <span data-ttu-id="53dbf-186">这可能意味着需要暂停并等待来自 Microsoft 更新的指南。</span><span class="sxs-lookup"><span data-stu-id="53dbf-186">This may mean you need to pause and wait for updated guidance from Microsoft.</span></span> <span data-ttu-id="53dbf-187">一旦您满足您满足所有要求，并具有对地址间隙的计划，继续。</span><span class="sxs-lookup"><span data-stu-id="53dbf-187">Once you are satisfied that you meet all requirements and have a plan to address gaps, proceed.</span></span>

<span data-ttu-id="53dbf-188">在高级别，供在安装过程的业务服务器 2019 Skype 时的业务服务器 2015 Skype 将要求您安装 CU6 HF2，应用到.NET 和 SQL、 部署系统必备的注册表项，和最后一个单独的系统必备的更新round OS 配置的更新 （即禁用 TLS 1.0 和通过注册表文件导入 1.1）。</span><span class="sxs-lookup"><span data-stu-id="53dbf-188">At a high level, while Skype for Business Server 2019 is ready for procedure at install, Skype for Business Server 2015 will require that you install CU6 HF2, applying pre-requisite updates to .NET and SQL, deploying prerequisite registry keys, and finally a separate round of OS configuration updates (i.e. disabling TLS 1.0 and 1.1 via registry file import).</span></span> <span data-ttu-id="53dbf-189">完成安装所有必备组件，包括之前禁用 TLS 1.0 和您的环境中的任何服务器上的 1.1 Skype 业务服务器 2015 CU6 HF2 至关重要。</span><span class="sxs-lookup"><span data-stu-id="53dbf-189">It is critically important that you complete installation of all prerequisites, including Skype for Business Server 2015 CU6 HF2, prior to disabling TLS 1.0 and 1.1 on any server in your environment.</span></span> <span data-ttu-id="53dbf-190">对于业务服务器，包括边缘角色和 SQL Backends，每个 Skype 需要更新。</span><span class="sxs-lookup"><span data-stu-id="53dbf-190">Every Skype for Business server, including Edge role and SQL Backends, requires the updates.</span></span> <span data-ttu-id="53dbf-191">此外还应确保所有受支持 （范围） 客户端的已更新为所需的最低版本。</span><span class="sxs-lookup"><span data-stu-id="53dbf-191">Also ensure that all supported (in-scope) clients have been updated to the required minimum versions.</span></span> <span data-ttu-id="53dbf-192">不要忘记更新以及管理工作站。</span><span class="sxs-lookup"><span data-stu-id="53dbf-192">Don’t forget to update management workstations as well.</span></span>

<span data-ttu-id="53dbf-193">我们希望需遵循的业务服务器升级 Skype 操作的"内向外"的常规顺序。</span><span class="sxs-lookup"><span data-stu-id="53dbf-193">We want to follow the usual order of operations of "inside out" for upgrading Skype for Business servers.</span></span> <span data-ttu-id="53dbf-194">将控制器池、 持久聊天和配对池视为平常一样方式相同。</span><span class="sxs-lookup"><span data-stu-id="53dbf-194">Treat Director pools, Persistent chat, and Paired Pools in the same manner you normally would.</span></span> <span data-ttu-id="53dbf-195">介绍的订单和用于升级方法[此处](topology.md)和[此处](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015)。</span><span class="sxs-lookup"><span data-stu-id="53dbf-195">Order and methods for upgrade are covered [here](topology.md) and [here](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).</span></span>

### <a name="high-level-process"></a><span data-ttu-id="53dbf-196">高级过程</span><span class="sxs-lookup"><span data-stu-id="53dbf-196">High-level process</span></span>

1. <span data-ttu-id="53dbf-197">测试实验室之前配置生产服务器中的所有步骤。</span><span class="sxs-lookup"><span data-stu-id="53dbf-197">Test all steps in your lab prior to configuring production servers.</span></span>
2. <span data-ttu-id="53dbf-198">备份和保留一份每个要更新的单个服务器上的导出注册表。</span><span class="sxs-lookup"><span data-stu-id="53dbf-198">Back up and preserve a copy of exported registry on each and every individual server to be updated.</span></span> <span data-ttu-id="53dbf-199">您不能共享服务器; 之间的注册表它们包含基于计算机的唯一键。</span><span class="sxs-lookup"><span data-stu-id="53dbf-199">You cannot share registries between servers; they contain unique machine-based keys.</span></span>
3. <span data-ttu-id="53dbf-200">升级所有 Skype 业务 2015年服务器，为 CU6 HF2 或更高。</span><span class="sxs-lookup"><span data-stu-id="53dbf-200">Upgrade all Skype for Business 2015 servers to CU6 HF2 or higher.</span></span> <span data-ttu-id="53dbf-201">（的业务服务器 2019年的 Skype，则需要无 CU）</span><span class="sxs-lookup"><span data-stu-id="53dbf-201">(For Skype for Business Server 2019, no CU is needed)</span></span>
4. <span data-ttu-id="53dbf-202">安装所有必备组件的所有服务器。</span><span class="sxs-lookup"><span data-stu-id="53dbf-202">Install all prerequisites to all servers.</span></span>
5. <span data-ttu-id="53dbf-203">部署先决条件的注册表项。</span><span class="sxs-lookup"><span data-stu-id="53dbf-203">Deploy prerequisite registry keys.</span></span>
6. <span data-ttu-id="53dbf-204">确保更新范围内的所有客户端。</span><span class="sxs-lookup"><span data-stu-id="53dbf-204">Ensure that all in-scope clients are updated.</span></span>
7. <span data-ttu-id="53dbf-205">禁用 TLS 1.0 和通过注册表导入 1.1。</span><span class="sxs-lookup"><span data-stu-id="53dbf-205">Disable TLS 1.0 and 1.1 via registry import.</span></span>
8. <span data-ttu-id="53dbf-206">验证预期的工作负荷的正常运行。</span><span class="sxs-lookup"><span data-stu-id="53dbf-206">Validate that workloads are functioning as expected.</span></span>
    - <span data-ttu-id="53dbf-207">如果遇到问题，诊断和解决，或</span><span class="sxs-lookup"><span data-stu-id="53dbf-207">If problems are encountered, troubleshoot and resolve, or</span></span>
    - <span data-ttu-id="53dbf-208">从步骤 2 以重新启用 TLS 1.0 和 1.1 还原注册表</span><span class="sxs-lookup"><span data-stu-id="53dbf-208">Restore registry from step 2 to re-enable TLS 1.0 and 1.1</span></span>
9. <span data-ttu-id="53dbf-209">验证正在使用仅 TLS 1.2。</span><span class="sxs-lookup"><span data-stu-id="53dbf-209">Validate that only TLS 1.2 is being used.</span></span>

### <a name="install-prerequisites-to-all-servers"></a><span data-ttu-id="53dbf-210">安装所有服务器的必备组件</span><span class="sxs-lookup"><span data-stu-id="53dbf-210">Install prerequisites to all servers</span></span>

<span data-ttu-id="53dbf-211">禁用 TLS 1.0 和在操作系统级别中的业务服务器 2015年部署您 Skype 1.1 开始之前，需要进行大量依赖项更新。</span><span class="sxs-lookup"><span data-stu-id="53dbf-211">Extensive dependency updating is required before you begin to disable TLS 1.0 and 1.1 at the operating system level in your Skype for Business Server 2015 deployments.</span></span> <span data-ttu-id="53dbf-212">以下是可支持 TLS 1.2 的最低版本。</span><span class="sxs-lookup"><span data-stu-id="53dbf-212">The following are the minimum versions that can support TLS 1.2.</span></span> <span data-ttu-id="53dbf-213">禁用 TLS 1.0 和 1.1 开始之前，请在您的环境中的业务服务器的每个 Skype 中部署所有必备组件更新。</span><span class="sxs-lookup"><span data-stu-id="53dbf-213">Deploy all prerequisite updates across every Skype for Business server in your environment before you begin disabling TLS 1.0 and 1.1.</span></span>

- <span data-ttu-id="53dbf-214">Skype 的业务服务器 2015 CU6 HF2 6.0.9319.516 （[2018 年 3 月更新](https://support.microsoft.com/en-us/help/4086059/march-2018-cumulative-update-6-0-9319-516-for-skype-for-business)） 或更高版本</span><span class="sxs-lookup"><span data-stu-id="53dbf-214">Skype for Business Server 2015 CU6 HF2 6.0.9319.516 ([March 2018 update](https://support.microsoft.com/en-us/help/4086059/march-2018-cumulative-update-6-0-9319-516-for-skype-for-business)) or higher</span></span>
- <span data-ttu-id="53dbf-215">[.NET framework 4.7](https://www.microsoft.com/en-us/download/details.aspx?id=55167)或更高版本 （下面提供） 的注册表中启用的 SchUseStrongCrypto 与</span><span class="sxs-lookup"><span data-stu-id="53dbf-215">[.NET Framework 4.7](https://www.microsoft.com/en-us/download/details.aspx?id=55167) or higher with SchUseStrongCrypto enabled in the registry (provided below)</span></span>
- <span data-ttu-id="53dbf-216">必须在所有 Skype 业务 2015年服务器和 backends 更新 SQL。</span><span class="sxs-lookup"><span data-stu-id="53dbf-216">SQL must be updated on all Skype for Business 2015 servers and backends.</span></span> <span data-ttu-id="53dbf-217">企业版池 SQL Backends 首先更新，然后其各自的 FEs。</span><span class="sxs-lookup"><span data-stu-id="53dbf-217">Update Enterprise Edition Pool SQL Backends first, then their respective FEs.</span></span> 
    - <span data-ttu-id="53dbf-218">SQL Server 2014 SP1 + CU5 （[链接](https://support.microsoft.com/help/3130926)），或更高版本 / SQL Server 2012 SP2 + CU16 或更高版本 / SQL Server 2014 RTM + CU12 （[链接](https://support.microsoft.com/en-us/help/3130923/cumulative-update-12-for-sql-server-2014)） 或更高版本 / SQL Server 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="53dbf-218">SQL Server 2014 SP1 + CU5 ([link](https://support.microsoft.com/help/3130926)), or higher / SQL Server 2012 SP2 + CU16 or higher/ SQL Server 2014 RTM + CU12 ([link](https://support.microsoft.com/en-us/help/3130923/cumulative-update-12-for-sql-server-2014)) or higher / SQL Server 2014 SP2</span></span>
    - <span data-ttu-id="53dbf-219">SQL Server 2012 （[链接](https://www.microsoft.com/en-us/download/details.aspx?id=50402)） 版的 SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="53dbf-219">SQL Server Native Client for SQL Server 2012 ([link](https://www.microsoft.com/en-us/download/details.aspx?id=50402))</span></span>
    - <span data-ttu-id="53dbf-220">Microsoft ODBC 驱动程序 11 SQL server （[链接](https://www.microsoft.com/en-us/download/details.aspx?id=36434)），或更高版本</span><span class="sxs-lookup"><span data-stu-id="53dbf-220">Microsoft ODBC Driver 11 for SQL Server ([link](https://www.microsoft.com/en-us/download/details.aspx?id=36434)), or higher</span></span>
    - <span data-ttu-id="53dbf-221">共享的 SQL Server 2014 SP2 （[链接](https://www.microsoft.com/en-in/download/details.aspx?id=42295)） 的管理对象</span><span class="sxs-lookup"><span data-stu-id="53dbf-221">Shared Management Objects for SQL Server 2014 SP2 ([link](https://www.microsoft.com/en-in/download/details.aspx?id=42295))</span></span>
    - <span data-ttu-id="53dbf-222">SQL server 2014 SP2 SQLSysClrTypes （[链接](https://www.microsoft.com/en-in/download/details.aspx?id=42295)）</span><span class="sxs-lookup"><span data-stu-id="53dbf-222">SQLSysClrTypes for SQL server 2014 SP2 ([link](https://www.microsoft.com/en-in/download/details.aspx?id=42295))</span></span>

### <a name="basic-steps-to-install-pre-requisites-in-recommended-order-of-operations"></a><span data-ttu-id="53dbf-223">安装必备组件，建议的操作顺序中的基本步骤</span><span class="sxs-lookup"><span data-stu-id="53dbf-223">Basic steps to install pre-requisites, in recommended order of operations</span></span>

1. <span data-ttu-id="53dbf-224">安装 Business Server CU6HF2 Skype (6.0.9319.516) 更新的所有服务器。</span><span class="sxs-lookup"><span data-stu-id="53dbf-224">Install the Skype for Business Server CU6HF2 (6.0.9319.516) update to all servers.</span></span> 
    1. <span data-ttu-id="53dbf-225">使用 updater 组件安装更新。</span><span class="sxs-lookup"><span data-stu-id="53dbf-225">Install the update to components using the updater.</span></span>
    2. <span data-ttu-id="53dbf-226">更新数据库根据记录的过程。</span><span class="sxs-lookup"><span data-stu-id="53dbf-226">Update databases according to documented procedures.</span></span> <span data-ttu-id="53dbf-227">说明均编档在[https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015)。</span><span class="sxs-lookup"><span data-stu-id="53dbf-227">Instructions are documented at [https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).</span></span>
    3. <span data-ttu-id="53dbf-228">验证之前与任何其他更改向前移动部署中的产品功能。</span><span class="sxs-lookup"><span data-stu-id="53dbf-228">Validate product functionality in the deployment prior to moving forward with any other changes.</span></span>
2. <span data-ttu-id="53dbf-229">下载.NET 4.7 脱机的安装程序。</span><span class="sxs-lookup"><span data-stu-id="53dbf-229">Download .NET 4.7 Offline Installer.</span></span> 
    1. <span data-ttu-id="53dbf-230">参考：[https://www.microsoft.com/en-us/download/details.aspx?id=55167](https://www.microsoft.com/en-us/download/details.aspx?id=55167)</span><span class="sxs-lookup"><span data-stu-id="53dbf-230">Reference: [https://www.microsoft.com/en-us/download/details.aspx?id=55167](https://www.microsoft.com/en-us/download/details.aspx?id=55167)</span></span>
    2. <span data-ttu-id="53dbf-231">确保 Skype 业务服务器 2015年服务已停止在前端服务器上。</span><span class="sxs-lookup"><span data-stu-id="53dbf-231">Ensure that Skype for Business Server 2015 services are stopped on the Front End server.</span></span>
    3. <span data-ttu-id="53dbf-232">参考：[https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015)</span><span class="sxs-lookup"><span data-stu-id="53dbf-232">Reference: [https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015)</span></span>
    4. <span data-ttu-id="53dbf-233">(Standard Edition): ex 停止 CsWindowsServices</span><span class="sxs-lookup"><span data-stu-id="53dbf-233">Ex (Standard Edition): Stop-CsWindowsServices</span></span>
    5. <span data-ttu-id="53dbf-234">Ex （企业版）： 调用-CsComputerFailover</span><span class="sxs-lookup"><span data-stu-id="53dbf-234">Ex (Enterprise Edition): Invoke-CsComputerFailover</span></span>
    6. <span data-ttu-id="53dbf-235">运行安装程序包。</span><span class="sxs-lookup"><span data-stu-id="53dbf-235">Run the installer package.</span></span>
    7. <span data-ttu-id="53dbf-236">重新启动服务器。</span><span class="sxs-lookup"><span data-stu-id="53dbf-236">Reboot the server.</span></span>
3. <span data-ttu-id="53dbf-237">在所有服务器上更新 SQL Express 2014。</span><span class="sxs-lookup"><span data-stu-id="53dbf-237">Update SQL Express 2014 on all servers.</span></span> 
    1. <span data-ttu-id="53dbf-238">参考：[https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span><span class="sxs-lookup"><span data-stu-id="53dbf-238">Reference: [https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span></span>
    2. <span data-ttu-id="53dbf-239">下载 SQL 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="53dbf-239">Download SQL 2014 SP2</span></span> 
        - <span data-ttu-id="53dbf-240">参考：[https://www.microsoft.com/en-us/download/details.aspx?id=53168](https://www.microsoft.com/en-us/download/details.aspx?id=53168)</span><span class="sxs-lookup"><span data-stu-id="53dbf-240">Reference: [https://www.microsoft.com/en-us/download/details.aspx?id=53168](https://www.microsoft.com/en-us/download/details.aspx?id=53168)</span></span>
    3. <span data-ttu-id="53dbf-241">将安装媒体复制到服务器上的文件夹 (例如： C:\01_2014SqlSp2)</span><span class="sxs-lookup"><span data-stu-id="53dbf-241">Copy the installation media to a folder on the server (Ex: C:\01_2014SqlSp2)</span></span>
    4. <span data-ttu-id="53dbf-242">确保 Skype 的业务服务器 2015 在前端服务器停止服务</span><span class="sxs-lookup"><span data-stu-id="53dbf-242">Ensure Skype for Business Server 2015 services are stopped on the Front End server</span></span> 
        - <span data-ttu-id="53dbf-243">Ex (Standard Edition): Stop-cswindowsservice</span><span class="sxs-lookup"><span data-stu-id="53dbf-243">Ex (Standard Edition): Stop-CsWindowsService</span></span>
        - <span data-ttu-id="53dbf-244">Ex （企业版）： 调用-CsComputerFailove</span><span class="sxs-lookup"><span data-stu-id="53dbf-244">Ex (Enterprise Edition): Invoke-CsComputerFailove</span></span>
    5. <span data-ttu-id="53dbf-245">打开管理命令提示符处，并升级所有安装的组件和实例</span><span class="sxs-lookup"><span data-stu-id="53dbf-245">Open an Admin Command Prompt, and upgrade all installed components and instances</span></span> 
        - <span data-ttu-id="53dbf-246">示例： C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe /qs /IAcceptSQLServerLicenseTerms /Action = 修补程序 /AllInstances</span><span class="sxs-lookup"><span data-stu-id="53dbf-246">Example: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe /qs /IAcceptSQLServerLicenseTerms /Action=Patch /AllInstances</span></span>
4. <span data-ttu-id="53dbf-247">更新 SQL Native Client。</span><span class="sxs-lookup"><span data-stu-id="53dbf-247">Update SQL Native Client.</span></span> 
    1. <span data-ttu-id="53dbf-248">参考： [https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server)。</span><span class="sxs-lookup"><span data-stu-id="53dbf-248">Reference: [https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server).</span></span>
    2. <span data-ttu-id="53dbf-249">从下载[https://www.microsoft.com/en-us/download/details.aspx?id=50402](https://www.microsoft.com/en-us/download/details.aspx?id=50402)</span><span class="sxs-lookup"><span data-stu-id="53dbf-249">Download from [https://www.microsoft.com/en-us/download/details.aspx?id=50402](https://www.microsoft.com/en-us/download/details.aspx?id=50402)</span></span>
    3. <span data-ttu-id="53dbf-250">确保 Skype 的业务服务器 2015 在前端服务器停止服务。</span><span class="sxs-lookup"><span data-stu-id="53dbf-250">Ensure Skype for Business Server 2015 services are stopped on the Front End server.</span></span> 
        - <span data-ttu-id="53dbf-251">(Standard Edition): ex 停止 CsWindowsServices</span><span class="sxs-lookup"><span data-stu-id="53dbf-251">Ex (Standard Edition): Stop-CsWindowsServices</span></span>
        - <span data-ttu-id="53dbf-252">Ex （企业版）： 调用-CsComputerFailove</span><span class="sxs-lookup"><span data-stu-id="53dbf-252">Ex (Enterprise Edition): Invoke-CsComputerFailove</span></span>
    4. <span data-ttu-id="53dbf-253">停止运行安装的 SQL 实例</span><span class="sxs-lookup"><span data-stu-id="53dbf-253">Stop the SQL instances installed from running</span></span> 
        - <span data-ttu-id="53dbf-254">示例： 获取服务 MSSQL RTCLOCAL' |停止服务</span><span class="sxs-lookup"><span data-stu-id="53dbf-254">Ex: Get-Service 'MSSQL$RTCLOCAL' | Stop-Servic</span></span>
        - <span data-ttu-id="53dbf-255">示例： 获取服务 MSSQL$ LYNCLOCAL' |停止服务</span><span class="sxs-lookup"><span data-stu-id="53dbf-255">Ex: Get-Service 'MSSQL$LYNCLOCAL' | Stop-Servic</span></span>
        - <span data-ttu-id="53dbf-256">（仅标准版）： ex Get-服务 MSSQL RTC |停止服务</span><span class="sxs-lookup"><span data-stu-id="53dbf-256">Ex (Standard Edition Only): Get-Service 'MSSQL$RTC' | Stop-Servic</span></span>
    5. <span data-ttu-id="53dbf-257">安装该更新。</span><span class="sxs-lookup"><span data-stu-id="53dbf-257">Install the update.</span></span>
5. <span data-ttu-id="53dbf-258">SQL Server 的更新 ODBC 驱动程序 11。</span><span class="sxs-lookup"><span data-stu-id="53dbf-258">Update ODBC Driver 11 for SQL Server.</span></span> 
    1. <span data-ttu-id="53dbf-259">参考： [https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server)。</span><span class="sxs-lookup"><span data-stu-id="53dbf-259">Reference: [https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server).</span></span>
    2. <span data-ttu-id="53dbf-260">从下载[https://www.microsoft.com/en-us/download/confirmation.aspx?id=36434](https://www.microsoft.com/en-us/download/confirmation.aspx?id=36434)</span><span class="sxs-lookup"><span data-stu-id="53dbf-260">Download from [https://www.microsoft.com/en-us/download/confirmation.aspx?id=36434](https://www.microsoft.com/en-us/download/confirmation.aspx?id=36434)</span></span>
    3. <span data-ttu-id="53dbf-261">确保 Skype 业务服务器 2015年服务已停止在前端服务器上</span><span class="sxs-lookup"><span data-stu-id="53dbf-261">Ensure that Skype for Business Server 2015 services are stopped on the Front End server</span></span> 
        - <span data-ttu-id="53dbf-262">Ex (Standard Edition): Stop-cswindowsservice</span><span class="sxs-lookup"><span data-stu-id="53dbf-262">Ex (Standard Edition): Stop-CsWindowsService</span></span>
        - <span data-ttu-id="53dbf-263">Ex （企业版）： 调用-CsComputerFailove</span><span class="sxs-lookup"><span data-stu-id="53dbf-263">Ex (Enterprise Edition): Invoke-CsComputerFailove</span></span>
    4. <span data-ttu-id="53dbf-264">安装该更新。</span><span class="sxs-lookup"><span data-stu-id="53dbf-264">Install the update.</span></span>
6. <span data-ttu-id="53dbf-265">部署先决条件的注册表项。</span><span class="sxs-lookup"><span data-stu-id="53dbf-265">Deploy prerequisite registry keys.</span></span>

### <a name="pre-requisite-registry-keys"></a><span data-ttu-id="53dbf-266">系统必备的注册表项</span><span class="sxs-lookup"><span data-stu-id="53dbf-266">Pre-requisite registry keys</span></span>

<span data-ttu-id="53dbf-267">复制/粘贴以下测试到记事本并重命名 TLSPreReq.reg 或您选择的名称，然后导入：</span><span class="sxs-lookup"><span data-stu-id="53dbf-267">Copy/paste the following test into Notepad and rename TLSPreReq.reg or a name of your choice, then import:</span></span>

```
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

<span data-ttu-id="53dbf-268">SQL 的企业版池、 先决条件和 TLS 结束禁用的后应被视为任何 SQL 或操作系统更新将;请参阅：[https://docs.microsoft.com/en-us/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/en-us/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)</span><span class="sxs-lookup"><span data-stu-id="53dbf-268">For SQL back ends for Enterprise Edition Pools, prerequisites and TLS disable should be treated as any SQL or OS updates would; refer to: [https://docs.microsoft.com/en-us/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/en-us/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)</span></span>

<span data-ttu-id="53dbf-269">时可以组合的必备组件的应用程序和禁用步骤 TLS，我们强烈建议在继续禁用的 TLS 1.0 和在操作系统级别 1.1 之前应用的所有必备组件。</span><span class="sxs-lookup"><span data-stu-id="53dbf-269">While both the prerequisite application and TLS disabling steps can be combined, we strongly recommend all prerequisites be applied before proceeding with disabling of TLS 1.0 and 1.1 at the operating system level.</span></span> <span data-ttu-id="53dbf-270">最佳做法的方法是通过部署所有必备组件，验证所有工作负荷函数正确和预期工作，并在以后再禁用继续使用 TLS 1.0/1.1 中准备环境。</span><span class="sxs-lookup"><span data-stu-id="53dbf-270">The best practice approach would be to prepare the environment by deploying all prerequisites, validating that workloads all function correctly and as expected, and then proceeding with TLS 1.0/1.1 disable at a later time.</span></span>

### <a name="disable-tls-10-and-11-via-registry-import"></a><span data-ttu-id="53dbf-271">禁用 TLS 1.0 和通过注册表导入 1.1</span><span class="sxs-lookup"><span data-stu-id="53dbf-271">Disable TLS 1.0 and 1.1 via registry import</span></span>

<span data-ttu-id="53dbf-272">在继续操作之前与接下来的步骤，*请确保您已完成所有必备组件并更新 Skype 业务服务器*。</span><span class="sxs-lookup"><span data-stu-id="53dbf-272">Before you proceed with the next steps, *make sure you have completed all prerequisites and updated Skype for Business Servers*.</span></span>

<span data-ttu-id="53dbf-273">将以下文本复制到记事本文件，并将其重命名**TLSDisable.reg**:</span><span class="sxs-lookup"><span data-stu-id="53dbf-273">Copy the following text into a Notepad file and rename it **TLSDisable.reg**:</span></span>

```
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

<span data-ttu-id="53dbf-274">导入您想要禁用 TLS 1.0 每台服务器和 1.1 该.reg 文件。</span><span class="sxs-lookup"><span data-stu-id="53dbf-274">Import the .reg file on each server you wish to disable TLS 1.0 and 1.1.</span></span> <span data-ttu-id="53dbf-275">重新启动服务器。</span><span class="sxs-lookup"><span data-stu-id="53dbf-275">Reboot the server.</span></span> <span data-ttu-id="53dbf-276">一旦服务具有联机后，将移动到下一台服务器。</span><span class="sxs-lookup"><span data-stu-id="53dbf-276">Once the services have come back online, move to the next server.</span></span> <span data-ttu-id="53dbf-277">企业版池的方法是将花费的任何操作系统更新相同。</span><span class="sxs-lookup"><span data-stu-id="53dbf-277">The approach for Enterprise Edition Pools is the same you would take for any OS update.</span></span>

<span data-ttu-id="53dbf-278">您可能已经注意到我们的多台只禁用 TLS 1.0 和 1.1 此处操作。</span><span class="sxs-lookup"><span data-stu-id="53dbf-278">You may have noticed we are doing more than just disabling TLS 1.0 and 1.1 here.</span></span> <span data-ttu-id="53dbf-279">我们要支持密码套件重新排序 （如上所示） 和某些旧的弱密码的禁用。</span><span class="sxs-lookup"><span data-stu-id="53dbf-279">We are supporting Cipher Suite re-order (as shown above) and the disabling of some older weak ciphers.</span></span> <span data-ttu-id="53dbf-280">这是首次我们具有正式支持对 SCHANNEL 和加密 API 的这些更改 Skype 业务服务器，务必注意这些更改是我们支持，并测试这一次是唯一的。</span><span class="sxs-lookup"><span data-stu-id="53dbf-280">This is the first time we have officially supported these changes to SCHANNEL and Crypto API on Skype for Business Server, and it is important to note that these changes are the only ones we support and have tested at this time.</span></span> <span data-ttu-id="53dbf-281">我们将来，可能会考虑的其他配置，但现在，请不要修改注册表导入文件中您的实现。</span><span class="sxs-lookup"><span data-stu-id="53dbf-281">We may consider additional configurations in the future, but for now, please do not modify the registry import file in your implementation.</span></span>

### <a name="validate-that-workloads-are-functioning-as-expected"></a><span data-ttu-id="53dbf-282">验证预期的工作负荷的正常运行</span><span class="sxs-lookup"><span data-stu-id="53dbf-282">Validate that workloads are functioning as expected</span></span>

<span data-ttu-id="53dbf-283">一次 TLS 1.0 和 1.1 已禁用您的环境中，确保您的主要工作负载都按预期方式，如 IM 和状态、 P2P 运行所有呼叫，企业语音，等等。</span><span class="sxs-lookup"><span data-stu-id="53dbf-283">Once TLS 1.0 and 1.1 have been disabled in your environment, ensure that all your main workloads are functioning as expected, such as IM & Presence, P2P calls, Enterprise Voice, etc.</span></span>

<span data-ttu-id="53dbf-284">**验证正在使用仅 TLS 1.2**</span><span class="sxs-lookup"><span data-stu-id="53dbf-284">**Validate only TLS 1.2 is being used**</span></span>

<span data-ttu-id="53dbf-285">具有安全团队执行 Skype 的业务通信，以确保较旧的协议 TLS 1.0 和 1.1 不再使用的新审核。</span><span class="sxs-lookup"><span data-stu-id="53dbf-285">Have your Security Team perform a new audit of Skype for Business traffic to ensure that the older protocols TLS 1.0 and 1.1 are no longer in use.</span></span>

<span data-ttu-id="53dbf-286">此外，您可以使用 Internet Explorer 测试 TLS 连接到 web 服务从 Skype 业务服务器 2015年后已禁用 TLS 1.0 和 TLS 1.1。</span><span class="sxs-lookup"><span data-stu-id="53dbf-286">Alternatively, you can use Internet Explorer to test TLS connections to web services from Skype for Business Server 2015 after TLS 1.0 and TLS 1.1 have been disabled.</span></span>

1. <span data-ttu-id="53dbf-287">启动 Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="53dbf-287">Launch Internet Explorer.</span></span>
2. <span data-ttu-id="53dbf-288">选择**工具** > **Internet 选项**。</span><span class="sxs-lookup"><span data-stu-id="53dbf-288">Select **Tools** > **Internet Options**.</span></span>
3. <span data-ttu-id="53dbf-289">选择**高级**选项卡。</span><span class="sxs-lookup"><span data-stu-id="53dbf-289">Select the **Advanced** tab.</span></span>
4. <span data-ttu-id="53dbf-290">在**设置**中，滚动到底部。</span><span class="sxs-lookup"><span data-stu-id="53dbf-290">Under **Settings**, scroll to the bottom.</span></span>
5. <span data-ttu-id="53dbf-291">验证已启用 TLS 1.0、 TLS 1.1 和 TLS 1.2。</span><span class="sxs-lookup"><span data-stu-id="53dbf-291">Verify that TLS 1.0, TLS 1.1, and TLS 1.2 are enabled.</span></span>
6. <span data-ttu-id="53dbf-292">浏览 SfB 2015 池 （应成功连接） 的内部 Web 服务 URL。</span><span class="sxs-lookup"><span data-stu-id="53dbf-292">Browse the Internal Web Service URL of your SfB 2015 pool (should connect successfully).</span></span>
7. <span data-ttu-id="53dbf-293">返回到 Internet Explorer，并禁用仅**使用 TLS 1.2**的选项。</span><span class="sxs-lookup"><span data-stu-id="53dbf-293">Go back into Internet Explorer and disable the option to **Use TLS 1.2** only.</span></span>
8. <span data-ttu-id="53dbf-294">浏览 SfB 2015 池再次 （应无法连接） 的内部 Web 服务 URL。</span><span class="sxs-lookup"><span data-stu-id="53dbf-294">Browse the Internal Web Service URL of your SfB 2015 pool again (should fail to connect).</span></span>

![Internet 选项](../../media/internet-options.jpg)

## <a name="advanced-deployment-scenarios"></a><span data-ttu-id="53dbf-296">高级的部署方案</span><span class="sxs-lookup"><span data-stu-id="53dbf-296">Advanced deployment scenarios</span></span>

<span data-ttu-id="53dbf-297">因为不需要 TLS 1.2 Skype 中支持的业务服务器 2015年一些依赖项先决条件，从 RTM 媒体安装 TLS 1.0 和 1.1 其中已禁用任何系统上将失败。</span><span class="sxs-lookup"><span data-stu-id="53dbf-297">Because some dependency prerequisites are required to support TLS 1.2 in Skype for Business Ser 2015, installing from RTM media will fail on any system where TLS 1.0 and 1.1 have been disabled.</span></span>

<span data-ttu-id="53dbf-298">**一旦 TLS 1.0 和 1.1 已禁用您的环境中部署新的 Standard Edition Server 或企业版池。**</span><span class="sxs-lookup"><span data-stu-id="53dbf-298">**Deploying New Standard Edition Servers or Enterprise Edition Pools once TLS 1.0 and 1.1 have been disabled in your environment.**</span></span>

<span data-ttu-id="53dbf-299">**选项 1:** 使用[SmartSetup](../../deploy/install/install-skype-for-business-server.md)。</span><span class="sxs-lookup"><span data-stu-id="53dbf-299">**Option 1:** Use [SmartSetup](../../deploy/install/install-skype-for-business-server.md).</span></span> <span data-ttu-id="53dbf-300">请注意我们要更新 SmartSetup 以适应未来 CU 中, 更新的 SQL 二进制文件，将在将来更新这篇文章。</span><span class="sxs-lookup"><span data-stu-id="53dbf-300">Note that we are updating SmartSetup to accommodate the updated SQL binaries in a future CU, and will update this article in the future.</span></span>

<span data-ttu-id="53dbf-301">**选项 2:** 预安装本地 SQL 实例 （RTCLOCAL 和 LYNCLOCAL）</span><span class="sxs-lookup"><span data-stu-id="53dbf-301">**Option 2:** Pre-install local SQL instances (RTCLOCAL and LYNCLOCAL)</span></span>

1. <span data-ttu-id="53dbf-302">下载并将 SQL Express 2014 SP2 (SQLEXPR_x64.exe) 复制到 FE 上的本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="53dbf-302">Download and copy SQL Express 2014 SP2 (SQLEXPR_x64.exe) to local folder on FE.</span></span> <span data-ttu-id="53dbf-303">假设文件夹路径 < SQL_FOLDER_PATH >。</span><span class="sxs-lookup"><span data-stu-id="53dbf-303">Let’s say folder path <SQL_FOLDER_PATH>.</span></span>
2. <span data-ttu-id="53dbf-304">启动 PowerShell 或命令提示符并导航到 < SQL_FOLDER_PATH >。</span><span class="sxs-lookup"><span data-stu-id="53dbf-304">Launch PowerShell or Command Prompt and navigate to <SQL_FOLDER_PATH>.</span></span>
3. <span data-ttu-id="53dbf-305">通过运行以下命令创建 RTCLOCAL SQL 实例。</span><span class="sxs-lookup"><span data-stu-id="53dbf-305">Create the RTCLOCAL SQL instance by running the command below.</span></span> <span data-ttu-id="53dbf-306">等待 SQLEXPR_x64.exe 完成之前：</span><span class="sxs-lookup"><span data-stu-id="53dbf-306">Wait until SQLEXPR_x64.exe finishes before proceeding:</span></span>

    <span data-ttu-id="53dbf-307">SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED = 0 /HIDECONSOLE /ACTION = 安装/功能 = SQLEngine、 工具 /INSTANCENAME = RTCLOCAL /TCPENABLED = 1 /SQLSVCACCOUNT ="NT 机构 \ 网络服务"/SQLSYSADMINACCOUNTS ="Builtin\管理员"/BROWSERSVCSTARTUPTYPE ="自动"/AGTSVCACCOUNT ="NTAUTHORITY\NetworkService"/SQLSVCSTARTUPTYPE = 地</span><span class="sxs-lookup"><span data-stu-id="53dbf-307">SQLEXPR_x64.exe  /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=RTCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automati</span></span>
1. <span data-ttu-id="53dbf-308">通过运行以下命令创建 LYNCLOCAL SQL 实例。</span><span class="sxs-lookup"><span data-stu-id="53dbf-308">Create the LYNCLOCAL SQL instance by running the command below.</span></span> <span data-ttu-id="53dbf-309">请等待 SQLEXPR_x64.exe，再继续下一步完成：</span><span class="sxs-lookup"><span data-stu-id="53dbf-309">Wait until SQLEXPR_x64.exe finishes before proceeding to the next step:</span></span>

    <span data-ttu-id="53dbf-310">SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED = 0 /HIDECONSOLE /ACTION = 安装/功能 = SQLEngine、 工具 /INSTANCENAME = LYNCLOCAL /TCPENABLED = 1 /SQLSVCACCOUNT ="NT 机构 \ 网络服务"/SQLSYSADMINACCOUNTS ="Builtin\管理员"/BROWSERSVCSTARTUPTYPE ="自动"/AGTSVCACCOUNT ="NTAUTHORITY\NetworkService"/SQLSVCSTARTUPTYPE = 自动</span><span class="sxs-lookup"><span data-stu-id="53dbf-310">SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=LYNCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automatic</span></span>
1. <span data-ttu-id="53dbf-311">业务 Server 2015 RTM 安装程序运行 Skype。</span><span class="sxs-lookup"><span data-stu-id="53dbf-311">Run Skype for Business Server 2015 RTM setup.</span></span>
2. <span data-ttu-id="53dbf-312">从上面的必备组件部分执行的其余步骤。</span><span class="sxs-lookup"><span data-stu-id="53dbf-312">Follow the remaining steps from the prerequisites section above.</span></span>

<span data-ttu-id="53dbf-313">**选项 3:** 手动可以替换本地安装媒体目录中的二进制文件，如下所示：</span><span class="sxs-lookup"><span data-stu-id="53dbf-313">**Option 3:** You may also manually replace binaries in a local installation media directory as follows:</span></span>

1. [<span data-ttu-id="53dbf-314">安装 Business Server Skype 的先决条件</span><span class="sxs-lookup"><span data-stu-id="53dbf-314">Install prerequisites for Skype for Business Server</span></span>](../../deploy/install/install-prerequisites.md)  
2. 2. <span data-ttu-id="53dbf-315">安装.NET 4.7:</span><span class="sxs-lookup"><span data-stu-id="53dbf-315">Install .NET 4.7:</span></span> 
      - <span data-ttu-id="53dbf-316">**注意：** 首次引入.NET 4.7 Skype 中的支持的业务服务器 2015 CU5 + (6.0.9319.281)。</span><span class="sxs-lookup"><span data-stu-id="53dbf-316">**Note:** We first introduced support for .NET 4.7 in Skype for Business Server 2015 CU5+ (6.0.9319.281).</span></span> <span data-ttu-id="53dbf-317">因此，下面的后续步骤中我们将更新核心组件之前主安装。</span><span class="sxs-lookup"><span data-stu-id="53dbf-317">Therefore, in later steps below we will be updating Core Components prior to the main install.</span></span>
      - <span data-ttu-id="53dbf-318">下载： https://www.microsoft.com/en-us/download/details.aspx?id=55167。</span><span class="sxs-lookup"><span data-stu-id="53dbf-318">Download: https://www.microsoft.com/en-us/download/details.aspx?id=55167.</span></span>
      - <span data-ttu-id="53dbf-319">参考：[软件的应安装之前业务服务器 2015年部署 Skype](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)</span><span class="sxs-lookup"><span data-stu-id="53dbf-319">Reference: [Software that should be installed before a Skype for Business Server 2015 deployment](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)</span></span>
3. <span data-ttu-id="53dbf-320">将复制的 ISO 文件/文件夹：</span><span class="sxs-lookup"><span data-stu-id="53dbf-320">Copy ISO Files/Folders:</span></span> 
    - <span data-ttu-id="53dbf-321">与业务服务器 2015 ISO 附加的 Skype，打开作为附加的驱动器的根目录 (例如： d:\)在文件资源管理器。</span><span class="sxs-lookup"><span data-stu-id="53dbf-321">With the Skype for Business Server 2015 ISO attached, open the root directory of the drive it is attached as (Ex: D:\) in File Explorer.</span></span>
    - <span data-ttu-id="53dbf-322">将所有文件夹和文件都复制到本地磁盘上的文件夹 (例如： C:\SkypeForBusiness2015ISO)。</span><span class="sxs-lookup"><span data-stu-id="53dbf-322">Copy all folders and files to a folder on a local disk (Ex: C:\SkypeForBusiness2015ISO).</span></span>
    - <span data-ttu-id="53dbf-323">**注意：** 在安装之前组件，某些文件将需要更新的 TLS 1.2 支持。</span><span class="sxs-lookup"><span data-stu-id="53dbf-323">**Note:** Prior to installing components, some files will need to be updated for support of TLS 1.2.</span></span>
4. <span data-ttu-id="53dbf-324">替换 MSI/EXE 包：</span><span class="sxs-lookup"><span data-stu-id="53dbf-324">Replace MSI/EXE Packages:</span></span> 
    - <span data-ttu-id="53dbf-325">将本地计算机上安装媒体的 /Setup/amd64/文件夹中现有的 MSI 和 EXE 包。</span><span class="sxs-lookup"><span data-stu-id="53dbf-325">Replace the existing MSI and EXE packages in the /Setup/amd64/ folder of the installation media on the local machine.</span></span>
    - <span data-ttu-id="53dbf-326">SQL 2014 SP2 Express:https://www.microsoft.com/en-us/download/details.aspx?id=53167</span><span class="sxs-lookup"><span data-stu-id="53dbf-326">SQL 2014 SP2 Express: https://www.microsoft.com/en-us/download/details.aspx?id=53167</span></span> 
        - <span data-ttu-id="53dbf-327">重命名为 SQLEXPR_x64 在本地计算机上并替换现有文件中安装程序/amd64/安装媒体的文件夹。</span><span class="sxs-lookup"><span data-stu-id="53dbf-327">Rename to SQLEXPR_x64 on the local machine, and replace the existing file in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="53dbf-328">SQL Native Client:https://www.microsoft.com/en-us/download/details.aspx?id=50402</span><span class="sxs-lookup"><span data-stu-id="53dbf-328">SQL Native Client: https://www.microsoft.com/en-us/download/details.aspx?id=50402</span></span> 
        - <span data-ttu-id="53dbf-329">**注意：** 重命名此必要 sqlncli.msi 安装，和然后替换现有的文件的安装程序/amd64 中存在/安装媒体的文件夹。</span><span class="sxs-lookup"><span data-stu-id="53dbf-329">**Note:** Rename this if necessary to sqlncli.msi, and then replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="53dbf-330">SQL 管理对象：https://www.microsoft.com/en-us/download/details.aspx?id=53164</span><span class="sxs-lookup"><span data-stu-id="53dbf-330">SQL Management Objects: https://www.microsoft.com/en-us/download/details.aspx?id=53164</span></span> 
        - <span data-ttu-id="53dbf-331">**注意：** 功能包将有大量的可以下载的项目。</span><span class="sxs-lookup"><span data-stu-id="53dbf-331">**Note:** The Feature pack will have a lot of items that can be downloaded.</span></span> <span data-ttu-id="53dbf-332">仅下载 SharedManagementObjects.msi 选择。</span><span class="sxs-lookup"><span data-stu-id="53dbf-332">Select to download SharedManagementObjects.msi only.</span></span>
        - <span data-ttu-id="53dbf-333">**注意：** 替换现有文件的安装程序/amd64 中存在/安装媒体的文件夹。</span><span class="sxs-lookup"><span data-stu-id="53dbf-333">**Note:** Replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="53dbf-334">SQL CLR 类型：https://www.microsoft.com/en-us/download/details.aspx?id=53164</span><span class="sxs-lookup"><span data-stu-id="53dbf-334">SQL CLR Types: https://www.microsoft.com/en-us/download/details.aspx?id=53164</span></span> 
        - <span data-ttu-id="53dbf-335">**注意：** 功能包将有大量的可以下载的项目。</span><span class="sxs-lookup"><span data-stu-id="53dbf-335">**Note:** The Feature pack will have a lot of items that can be downloaded.</span></span> <span data-ttu-id="53dbf-336">选择此选项可仅下载 CQLSysClrTypes.msi</span><span class="sxs-lookup"><span data-stu-id="53dbf-336">Select to download CQLSysClrTypes.msi only</span></span>
        - <span data-ttu-id="53dbf-337">**注意**： 替换现有文件的安装程序/amd64 中存在/安装媒体的文件夹。</span><span class="sxs-lookup"><span data-stu-id="53dbf-337">**Note**: Replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
5. <span data-ttu-id="53dbf-338">安装核心组件：</span><span class="sxs-lookup"><span data-stu-id="53dbf-338">Install Core Components:</span></span> 
    - <span data-ttu-id="53dbf-339">从安装程序/amd64 运行 Setup.exe/安装媒体的文件夹。</span><span class="sxs-lookup"><span data-stu-id="53dbf-339">Run Setup.exe from the Setup/amd64/ folder of the installation media.</span></span> <span data-ttu-id="53dbf-340">按照说明安装核心组件</span><span class="sxs-lookup"><span data-stu-id="53dbf-340">Follow the instructions to install Core Components</span></span>
    - <span data-ttu-id="53dbf-341">关闭核心组件。</span><span class="sxs-lookup"><span data-stu-id="53dbf-341">Close Core Components.</span></span>
6. <span data-ttu-id="53dbf-342">更新核心组件：</span><span class="sxs-lookup"><span data-stu-id="53dbf-342">Update Core Components:</span></span> 
    - <span data-ttu-id="53dbf-343">下载 Skype 适用于业务更新安装程序。</span><span class="sxs-lookup"><span data-stu-id="53dbf-343">Download the Skype for Business Update Installer.</span></span>
    - <span data-ttu-id="53dbf-344">运行安装程序更新核心组件和安装的性能计数器。</span><span class="sxs-lookup"><span data-stu-id="53dbf-344">Run the installer to update Core Components and install the performance counters.</span></span>
    - <span data-ttu-id="53dbf-345">**注意：** 从 CU6HF2 的版本，自动更新功能当前仅将安装到 CU6 为止。</span><span class="sxs-lookup"><span data-stu-id="53dbf-345">**Note:** As of the release of CU6HF2, the auto-update feature currently only will install up to CU6.</span></span> <span data-ttu-id="53dbf-346">因此，必须单独运行 updater 更新为 6.0.9319.516 的核心组件。</span><span class="sxs-lookup"><span data-stu-id="53dbf-346">Therefore, the updater must be run separately to update Core Components to 6.0.9319.516.</span></span>
    - <span data-ttu-id="53dbf-347">参考：https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015</span><span class="sxs-lookup"><span data-stu-id="53dbf-347">Reference: https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015</span></span>
7. <span data-ttu-id="53dbf-348">安装管理工具 （可选）：</span><span class="sxs-lookup"><span data-stu-id="53dbf-348">Install Administrative Tools (Optional):</span></span> 
    - <span data-ttu-id="53dbf-349">这将安装 Microsoft SQL Server 2012 Native Client、 SQL Server 2014 管理对象 (x64) 和 Microsoft System CLR Types for SQL Server 2014 (x64) 使用更新的文件。</span><span class="sxs-lookup"><span data-stu-id="53dbf-349">This will install the Microsoft SQL Server 2012 Native Client, SQL Server 2014 Management Objects (x64), and Microsoft System CLR Types for SQL Server 2014 (x64) using the updated files.</span></span> <span data-ttu-id="53dbf-350">此外，业务 Server 2015 拓扑生成器和控制面板 Skype 将本地计算机上可用。</span><span class="sxs-lookup"><span data-stu-id="53dbf-350">Additionally, the Skype for Business Server 2015 Topology Builder and Control Panel will be available on the local machine.</span></span>
8. <span data-ttu-id="53dbf-351">安装本地配置存储 （第 1 步）：</span><span class="sxs-lookup"><span data-stu-id="53dbf-351">Install Local Configuration Store (Step 1):</span></span> 
     - <span data-ttu-id="53dbf-352">打开部署向导、 业务服务器系统中，单击安装或更新 Skype 并单击**运行**步骤 1： 安装本地配置存储。</span><span class="sxs-lookup"><span data-stu-id="53dbf-352">Open the Deployment Wizard, click Install or Update Skype for Business Server System, and click on **Run** at Step 1: Install Local Configuration Store.</span></span>
     - <span data-ttu-id="53dbf-353">单击**下一步\*\*\*\*安装本地配置存储**对话框中。</span><span class="sxs-lookup"><span data-stu-id="53dbf-353">Click **Next** in the **Install Local Configuration Store** dialog box.</span></span>
     <span data-ttu-id="53dbf-354">![安装本地配置存储对话框](../../media/local-configuration-store.png)</span><span class="sxs-lookup"><span data-stu-id="53dbf-354">![Install Local Configuration Store dialog box](../../media/local-configuration-store.png)</span></span>
     - <span data-ttu-id="53dbf-355">查看结果，并确保完成任务状态。</span><span class="sxs-lookup"><span data-stu-id="53dbf-355">Review the results, and ensure that the Task Status is Completed.</span></span> <span data-ttu-id="53dbf-356">通过单击**查看日志**查看生成的日志文件。</span><span class="sxs-lookup"><span data-stu-id="53dbf-356">Review the resulting log file by clicking **View Log**.</span></span>
     <span data-ttu-id="53dbf-357">![任务状态显示为已完成](../../media/local-configuration-task-completed.png)</span><span class="sxs-lookup"><span data-stu-id="53dbf-357">![Task status shows as Completed](../../media/local-configuration-task-completed.png)</span></span>
     - <span data-ttu-id="53dbf-358">单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="53dbf-358">Click **Finish**.</span></span>
9. <span data-ttu-id="53dbf-359">设置或删除 Skype 业务服务器组件 (第 2 步):</span><span class="sxs-lookup"><span data-stu-id="53dbf-359">Set up or remove Skype for Business Server Components (Step 2):</span></span>
    - <span data-ttu-id="53dbf-360">打开部署向导中，单击**安装或更新 Skype 业务 Server 系统**，然后单击**运行**步骤 2： 安装或删除 Skype 业务服务器组件</span><span class="sxs-lookup"><span data-stu-id="53dbf-360">Open the Deployment Wizard, click **Install or Update Skype for Business Server System**, and click **Run** at Step 2: Set up or Remove Skype for Business Server Components</span></span>
    - <span data-ttu-id="53dbf-361">单击**下一步**中业务服务器组件对话框中设置用户 Skype。</span><span class="sxs-lookup"><span data-stu-id="53dbf-361">Click **Next** in the Set Up Skype for Business Server Components dialog box.</span></span>
    <span data-ttu-id="53dbf-362">![业务服务器组件窗口设置用户 Skype](../../media/set-up-skype-for-business-server-components-window.png)</span><span class="sxs-lookup"><span data-stu-id="53dbf-362">![the Set Up Skype for Business Server Components window](../../media/set-up-skype-for-business-server-components-window.png)</span></span>
    - <span data-ttu-id="53dbf-363">查看使用查看日志的日志，并验证该安装已完成毫无问题。</span><span class="sxs-lookup"><span data-stu-id="53dbf-363">Review the log using View Log, and validate that setup completed without issues.</span></span> 
    - <span data-ttu-id="53dbf-364">单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="53dbf-364">Click **Finish**.</span></span>
10. <span data-ttu-id="53dbf-365">继续进行额外的安装和配置所需 （此时，您可以继续正常安装过程）。</span><span class="sxs-lookup"><span data-stu-id="53dbf-365">Proceed with additional installation and configuration as required (you can resume normal installation procedures at this point).</span></span>
