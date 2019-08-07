---
title: 在 Skype for Business Server 2015 中禁用 TLS 1.0/1。1
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: '摘要: 在你的环境中准备和实现禁用 TLS 1.0 和1.1。'
ms.openlocfilehash: 3f12642a5abf944ddbcddfdca0745998a8b634ec
ms.sourcegitcommit: a49caec01ff724475d6670b303d851ddd8266c2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2019
ms.locfileid: "34275239"
---
# <a name="disable-tls-1011-in-skype-for-business-server-2015"></a><span data-ttu-id="aeb8a-103">在 Skype for Business Server 2015 中禁用 TLS 1.0/1。1</span><span class="sxs-lookup"><span data-stu-id="aeb8a-103">Disable TLS 1.0/1.1 in Skype for Business Server 2015</span></span>

<span data-ttu-id="aeb8a-104">本文旨在为你提供必要的指南, 以便你准备和实现在你的环境中禁用 TLS 1.0 和1.1。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-104">The purpose of this article is to provide the necessary guidance for you to prepare for and implement disabling TLS 1.0 and 1.1 in your environments.</span></span> <span data-ttu-id="aeb8a-105">此过程需要广泛的规划和准备。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-105">This process requires extensive planning and preparation.</span></span> <span data-ttu-id="aeb8a-106">请仔细查看本文中的所有信息, 确保你的计划能够为你的组织禁用 TLS 1.0 和1.1。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-106">Please carefully review all of the information in this article as you make your plan to disable TLS 1.0 and 1.1 for your organization.</span></span> <span data-ttu-id="aeb8a-107">请注意, 有许多外部依赖项和连接条件可能会受到禁用 TLS 1.0/1.1 的影响, 因此需要进行大量的计划和测试。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-107">Note that there are many external dependencies and connectivity conditions that could be impacted by disabling TLS 1.0/1.1, so extensive planning and testing is warranted.</span></span>

## <a name="in-this-article"></a><span data-ttu-id="aeb8a-108">在本文中</span><span class="sxs-lookup"><span data-stu-id="aeb8a-108">In this article</span></span>

- [<span data-ttu-id="aeb8a-109">背景和作用域</span><span class="sxs-lookup"><span data-stu-id="aeb8a-109">Background and scope</span></span>](#background)
- [<span data-ttu-id="aeb8a-110">先决条件和过程</span><span class="sxs-lookup"><span data-stu-id="aeb8a-110">Prerequisites and process</span></span>](#prerequisites-and-process)
- [<span data-ttu-id="aeb8a-111">高级部署方案</span><span class="sxs-lookup"><span data-stu-id="aeb8a-111">Advanced deployment scenarios</span></span>](#advanced-deployment-scenarios)

## <a name="background"></a><span data-ttu-id="aeb8a-112">背景</span><span class="sxs-lookup"><span data-stu-id="aeb8a-112">Background</span></span>

<span data-ttu-id="aeb8a-113">提供 TLS 1.0 和1.1 的主要驱动程序对本地 Skype for business 服务器禁用支持是支付卡行业 (PCI) 安全标准委员会和联邦信息处理标准的要求。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-113">The primary drivers for providing TLS 1.0 and 1.1 disable support for Skype for Business Server On-Premises are Payment Card Industry (PCI) Security Standards Council and Federal Information Processing Standards requirements.</span></span> <span data-ttu-id="aeb8a-114">可[在此处](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls)找到有关 PCI 要求的详细信息。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-114">More information for PCI requirements can be found [here](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls).</span></span>  <span data-ttu-id="aeb8a-115">Microsoft 无法提供有关您的组织是否需要遵守这些或其他要求的指导。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-115">Microsoft cannot provide guidance on whether or not your organization is required to adhere to these or other requirements.</span></span> <span data-ttu-id="aeb8a-116">你必须确定是否需要在你的环境中禁用 TLS 1.0 和/或1.1。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-116">You must determine if it is required for you to disable TLS 1.0 and/or 1.1 in your environments.</span></span>

<span data-ttu-id="aeb8a-117">Microsoft 在[此处](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/)提供了有关 TLS 的白皮书, 我们还建议在此[Exchange 博客](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)中提供的后台阅读功能。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-117">Microsoft has produced a white paper on TLS available [here](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/), and we also recommend the background reading available in this [Exchange blog](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/).</span></span>

## <a name="supportability-scope"></a><span data-ttu-id="aeb8a-118">支持范围</span><span class="sxs-lookup"><span data-stu-id="aeb8a-118">Supportability Scope</span></span>

<span data-ttu-id="aeb8a-119">*范围*指的是可支持性边界。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-119">*Scope* refers to supportability boundaries.</span></span> <span data-ttu-id="aeb8a-120">对于本地版 Skype for Business 服务器,*在范围*内意味着我们完全支持并已针对列出的产品版本对 TLS 1.0 和1.1 禁用了该功能。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-120">For Skype for Business Server On-Premises, *in scope* means we fully support and have tested disabling of TLS 1.0 and 1.1 for the listed product versions.</span></span> <span data-ttu-id="aeb8a-121">*目前正在调查*的是, 这一点是指我们正在积极调查如何将这些产品带入 TLS 禁用支持的范围内。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-121">*Currently being investigated* means just that; we are actively investigating bringing these products into scope for TLS disable support.</span></span> <span data-ttu-id="aeb8a-122">*超出范围*意味着这些产品版本不支持禁用 TLS 1.0 或 1.1, 并且将无法正常工作, 但所注明的例外情况除外。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-122">*Out of scope* means these product versions do not support disabling TLS 1.0 or 1.1 and will not work, with noted exceptions.</span></span>

### <a name="fully-tested-and-supported-servers"></a><span data-ttu-id="aeb8a-123">经过充分测试和支持的服务器</span><span class="sxs-lookup"><span data-stu-id="aeb8a-123">Fully tested and supported servers</span></span>

- <span data-ttu-id="aeb8a-124">Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="aeb8a-124">Skype for Business Server 2019</span></span>
- <span data-ttu-id="aeb8a-125">Skype for Business Server 2015 CU6 HF2 6.0.9319.516 ([3 月2018更新](https://support.microsoft.com/en-us/help/4086059/march-2018-cumulative-update-6-0-9319-516-for-skype-for-business)) 及更高版本:</span><span class="sxs-lookup"><span data-stu-id="aeb8a-125">Skype for Business Server 2015 CU6 HF2 6.0.9319.516 ([March 2018 update](https://support.microsoft.com/en-us/help/4086059/march-2018-cumulative-update-6-0-9319-516-for-skype-for-business)) and higher on:</span></span> 
    - <span data-ttu-id="aeb8a-126">Windows Server 2012 (包含 KB 3140245 或取代更新), 2012 R2 或2016</span><span class="sxs-lookup"><span data-stu-id="aeb8a-126">Windows Server 2012 (with KB 3140245 or superseding update), 2012 R2 or 2016</span></span>
- <span data-ttu-id="aeb8a-127">就地升级的 Skype for business Server 2015, CU6 HF2 及更高版本</span><span class="sxs-lookup"><span data-stu-id="aeb8a-127">In-place Upgraded Skype for Business Server 2015, with CU6 HF2 and higher on</span></span> 
    - <span data-ttu-id="aeb8a-128">Windows Server 2008 R2、2012 (包含 KB [3140245](https://support.microsoft.com/en-us/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in)或取代更新) 或 2012 R2</span><span class="sxs-lookup"><span data-stu-id="aeb8a-128">Windows Server 2008 R2, 2012 (with KB [3140245](https://support.microsoft.com/en-us/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) or superseding update), or 2012 R2</span></span>
- <span data-ttu-id="aeb8a-129">Exchange 连接和 Outlook Web App 与 Exchange Server 2010 SP3 RU19 或更高版本, 请参阅[此处](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)的指南</span><span class="sxs-lookup"><span data-stu-id="aeb8a-129">Exchange Connectivity and Outlook Web App with Exchange Server 2010 SP3 RU19 or higher, guidance [here](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)</span></span>
- <span data-ttu-id="aeb8a-130">Survivable 分支装置 (SBA) 使用 Skype for Business Server 2015 CU6 HF2 或更高版本 (请向您的供应商确认他们已将 appropiate 更新打包, 并已为你的设备提供)</span><span class="sxs-lookup"><span data-stu-id="aeb8a-130">Survivable Branch Appliance (SBA) with Skype for Business Server 2015 CU6 HF2 or higher (confirm with your vendor that they packaged the appropiate updates and have been made available for your appliance)</span></span>
- <span data-ttu-id="aeb8a-131">Survivable 分支服务器 (SBS) 与 Skype for Business Server 2015 CU6 HF2 或更高版本</span><span class="sxs-lookup"><span data-stu-id="aeb8a-131">Survivable Branch Server (SBS) with Skype for Business Server 2015 CU6 HF2 or higher</span></span>
- <span data-ttu-id="aeb8a-132">Lync Server 2013 **Edge 角色**, 这是因为 edge 角色不依赖于 Windows Fabric 1.0。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-132">Lync Server 2013 **Edge Role Only**, this is because Edge role does not have a dependency on Windows Fabric 1.0.</span></span>


### <a name="fully-tested-and-supported-clients"></a><span data-ttu-id="aeb8a-133">经过充分测试和支持的客户端</span><span class="sxs-lookup"><span data-stu-id="aeb8a-133">Fully tested and supported clients</span></span>

- <span data-ttu-id="aeb8a-134">Lync 2013 (Skype for Business) 桌面客户端、MSI 和 C2R, 包括基本[15.0.5023.1000 和更高版本](https://support.microsoft.com/en-us/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)</span><span class="sxs-lookup"><span data-stu-id="aeb8a-134">Lync 2013 (Skype for Business) Desktop Client, MSI and C2R, including Basic [15.0.5023.1000 and higher](https://support.microsoft.com/en-us/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)</span></span>
- <span data-ttu-id="aeb8a-135">Skype for Business 2016 桌面客户端、MSI [16.0.4678.1000 及更高版本](https://support.microsoft.com/en-us/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323), 包括基本</span><span class="sxs-lookup"><span data-stu-id="aeb8a-135">Skype for Business 2016 Desktop Client, MSI [16.0.4678.1000 and higher](https://support.microsoft.com/en-us/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323), including Basic</span></span>
- <span data-ttu-id="aeb8a-136">Skype for Business 2016 单击以运行时需要[2018 年4月](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus)更新:</span><span class="sxs-lookup"><span data-stu-id="aeb8a-136">Skype for Business 2016 Click to Run Require the [April 2018](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) Updates:</span></span> 
    - <span data-ttu-id="aeb8a-137">每月和半年度目标、16\.0\.9126\.2152 及更高版本</span><span class="sxs-lookup"><span data-stu-id="aeb8a-137">Monthly and Semi-Annual Targeted, 16\.0\.9126\.2152 and higher</span></span>
    - <span data-ttu-id="aeb8a-138">半年和延期频道, 16\.0\.8431\.2242 及更高版本</span><span class="sxs-lookup"><span data-stu-id="aeb8a-138">Semi-Annual and Deferred Channel, 16\.0\.8431\.2242 and higher</span></span>
- <span data-ttu-id="aeb8a-139">Mac 16.15 及更高版本的 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="aeb8a-139">Skype for Business on Mac 16.15 and higher</span></span>
- <span data-ttu-id="aeb8a-140">适用于 iOS 和 Android 6.19 及更高版本的 Skype for business</span><span class="sxs-lookup"><span data-stu-id="aeb8a-140">Skype for Business for iOS and Android 6.19 and higher</span></span>
- <span data-ttu-id="aeb8a-141">Skype Web App 2015 CU6 HF2 及更高版本 (随服务器一起提供)</span><span class="sxs-lookup"><span data-stu-id="aeb8a-141">Skype Web App 2015 CU6 HF2 and higher (ships with Server)</span></span>

### <a name="currently-being-investigated"></a><span data-ttu-id="aeb8a-142">当前正在调查</span><span class="sxs-lookup"><span data-stu-id="aeb8a-142">Currently being investigated</span></span>

#### <a name="devices"></a><span data-ttu-id="aeb8a-143">设备</span><span class="sxs-lookup"><span data-stu-id="aeb8a-143">Devices</span></span>

- <span data-ttu-id="aeb8a-144">Lync 会议室系统 (a.k.a。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-144">Lync Room System (a.k.a.</span></span> <span data-ttu-id="aeb8a-145">SRSv1)</span><span class="sxs-lookup"><span data-stu-id="aeb8a-145">SRSv1)</span></span>
- <span data-ttu-id="aeb8a-146">Microsoft Teams 会议室</span><span class="sxs-lookup"><span data-stu-id="aeb8a-146">Microsoft Teams Rooms</span></span>
- <span data-ttu-id="aeb8a-147">Surface Hub</span><span class="sxs-lookup"><span data-stu-id="aeb8a-147">Surface Hub</span></span>
- <span data-ttu-id="aeb8a-148">基于2015的 Survivable 分支装置 (SBA) 或 Survivable 分支服务器 (SBS)</span><span class="sxs-lookup"><span data-stu-id="aeb8a-148">2015 based Survivable Branch Appliance (SBA) or Survivable Branch Server (SBS)</span></span>

#### <a name="other"></a><span data-ttu-id="aeb8a-149">其他</span><span class="sxs-lookup"><span data-stu-id="aeb8a-149">Other</span></span>

- <span data-ttu-id="aeb8a-150">通话质量仪表板 (TLS 1.0 后的全新安装, 1.1 已禁用, 请参阅下文) \*</span><span class="sxs-lookup"><span data-stu-id="aeb8a-150">Call Quality Dashboard (new install after TLS 1.0, 1.1 have been disabled, see below)\*</span></span>
 
### <a name="out-of-scope"></a><span data-ttu-id="aeb8a-151">超出范围</span><span class="sxs-lookup"><span data-stu-id="aeb8a-151">Out of scope</span></span>

<span data-ttu-id="aeb8a-152">除非另有说明, 否则以下产品不在 TLS 1.0/1.1 禁用支持的范围内, 在禁用 TLS 1.0 和1.1 的环境中将不起作用。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-152">Except where noted, the following products are not in scope for TLS 1.0/1.1 disable support and will not function in an environment where TLS 1.0 and 1.1 have been disabled.</span></span>  <span data-ttu-id="aeb8a-153">这意味着: 如果仍在使用超出范围的服务器或客户, 则必须在 Skype for Business Server 内部部署中的任意位置禁用 TLS 1.0/1.1, 否则必须更新或删除它们。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-153">What this means: if you still utilize out-of-scope servers or clients, you must update or remove these if you need to disable TLS 1.0/1.1 anywhere in your Skype for Business Server on-premises deployment.</span></span>

- <span data-ttu-id="aeb8a-154">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aeb8a-154">Lync Server 2013</span></span>
- <span data-ttu-id="aeb8a-155">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="aeb8a-155">Lync Server 2010</span></span>
- <span data-ttu-id="aeb8a-156">Windows Server 2008 和更低</span><span class="sxs-lookup"><span data-stu-id="aeb8a-156">Windows Server 2008 and lower</span></span>
- <span data-ttu-id="aeb8a-157">Lync for Mac 2011</span><span class="sxs-lookup"><span data-stu-id="aeb8a-157">Lync for Mac 2011</span></span>
- <span data-ttu-id="aeb8a-158">适用于移动版的 Lync 2013-iOS、iPad、Android 或 Windows Phone</span><span class="sxs-lookup"><span data-stu-id="aeb8a-158">Lync 2013 for Mobile - iOS, iPad, Android or Windows Phone</span></span>
- <span data-ttu-id="aeb8a-159">Lync "MX" Windows 应用商店客户端</span><span class="sxs-lookup"><span data-stu-id="aeb8a-159">Lync "MX" Windows Store client</span></span>
- <span data-ttu-id="aeb8a-160">所有 Lync 2010 客户端</span><span class="sxs-lookup"><span data-stu-id="aeb8a-160">All Lync 2010 clients</span></span>
- <span data-ttu-id="aeb8a-161">Lync Phone Edition-更新的[](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035)指南。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-161">Lync Phone Edition - updated guidance [here](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035).</span></span>
- <span data-ttu-id="aeb8a-162">基于2013的 Survivable 分支装置 (SBA) 或 Survivable 分支服务器 (SBS)</span><span class="sxs-lookup"><span data-stu-id="aeb8a-162">2013 based Survivable Branch Appliance (SBA) or Survivable Branch Server (SBS)</span></span>
- <span data-ttu-id="aeb8a-163">云连接器版 (CCE)</span><span class="sxs-lookup"><span data-stu-id="aeb8a-163">Cloud Connector Edition (CCE)</span></span>
- <span data-ttu-id="aeb8a-164">Windows Phone 版 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="aeb8a-164">Skype for Business for Windows Phone</span></span>

### <a name="exceptions"></a><span data-ttu-id="aeb8a-165">异常</span><span class="sxs-lookup"><span data-stu-id="aeb8a-165">Exceptions</span></span>

#### <a name="lync-server-2013"></a><span data-ttu-id="aeb8a-166">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aeb8a-166">Lync Server 2013</span></span>

<span data-ttu-id="aeb8a-167">Lync Server 2013 依赖于 Windows Fabric 版本1.0。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-167">Lync Server 2013 takes a dependency on Windows Fabric version 1.0.</span></span>  <span data-ttu-id="aeb8a-168">在 Lync Server 2013 的设计阶段, 为其引人注目的和新的分布式体系结构选择了 Windows Fabric 1.0 以提供复制、高可用性和容错。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-168">In the design phase for Lync Server 2013, Windows Fabric 1.0 was chosen for its compelling and new distributed architecture to provide replication, high availability, and fault tolerance.</span></span>  <span data-ttu-id="aeb8a-169">随着时间的推移, Skype for business 服务器和 Windows Fabric 在后续版本中大大提高了这种联合体系结构的显著重新设计。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-169">Over time, both Skype for Business Server and Windows Fabric have greatly improved this joint architecture with significant re-design in subsequent versions.</span></span>  <span data-ttu-id="aeb8a-170">例如, 当前 Skype for Business 2015 服务器使用的是 Windows Fabric 3.0。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-170">Current Skype for Business 2015 Server uses Windows Fabric 3.0, for example.</span></span>

<span data-ttu-id="aeb8a-171">很遗憾, Windows Fabric 1.0 不**支持 TLS 1.2。 但是, 我们将更新 Lync Server 2013 以与 TLS 1.2 配合工作**。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-171">Unfortunately, Windows Fabric 1.0 **does not support TLS 1.2.  However, we will be updating Lync Server 2013 to work with TLS 1.2**.</span></span> <span data-ttu-id="aeb8a-172">这将进入 Lync Server 2013 的下一个累积更新。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-172">This will be coming in the next Cumulative Update for Lync Server 2013.</span></span>  <span data-ttu-id="aeb8a-173">我们提供了 TLS 1.2 支持以启用共存、迁移、联盟和混合方案。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-173">We're providing TLS 1.2 support to enable co-existence, migration, federation, and hybrid scenarios.</span></span>

<span data-ttu-id="aeb8a-174">如果你的组织需要禁用 TLS 1.0 和 1.1, 并且你当前使用的是 Lync Server 2013, 我们建议你开始计划过程, 但你可能需要就地升级或并行迁移 (新的池、移动用户) 到 Skype for Business企业服务器2015或更高版本。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-174">If your organization is required to disable TLS 1.0 and 1.1, and you currently use Lync Server 2013, we recommend you begin your planning process, with the possibility you may have to In-place upgrade or Side-by-Side migrate (new pools, move users) to Skype for Business Server 2015 or higher.</span></span>  <span data-ttu-id="aeb8a-175">或者, 您可能希望加速迁移到 Skype for business Online。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-175">Or you may want to accelerate migration to Skype for Business Online.</span></span>

#### <a name="call-quality-dashboard"></a><span data-ttu-id="aeb8a-176">呼叫质量仪表板</span><span class="sxs-lookup"><span data-stu-id="aeb8a-176">Call Quality Dashboard</span></span>

<span data-ttu-id="aeb8a-177">在全新安装期间, 本地呼叫质量仪表板当前对 TLS 1.0 有依赖性 (首次安装到本地环境)。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-177">On-Premises Call Quality Dashboard currently has a dependency on TLS 1.0 during new install (first time installing into your On-Premises environments).</span></span>  <span data-ttu-id="aeb8a-178">我们目前正在调查此问题, 并计划在不久的将来发布修补程序。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-178">We are currently investigating this issue and plan to release a fix in the near future.</span></span>  <span data-ttu-id="aeb8a-179">如果你计划安装 CQD 并禁用 TLS 1.0, 我们建议你先完成 CQD 安装, 然后再继续 TLS 1.0 禁用。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-179">If you are planning to install CQD and also disable TLS 1.0, we recommend that you complete CQD installation first, and then proceed with TLS 1.0 disabling.</span></span>

#### <a name="third-party-devices"></a><span data-ttu-id="aeb8a-180">第三方设备</span><span class="sxs-lookup"><span data-stu-id="aeb8a-180">Third-party devices</span></span>

<span data-ttu-id="aeb8a-181">在第三方设备 (如3PIP 电话、视频会议、反向代理和负载平衡器) 上, 确保验证 TLS 1.2 可支持性, 仔细测试, 如果需要, 请与供应商联系。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-181">On third-party devices such as 3PIP phones, Video conferencing, Reverse Proxies and Load Balancers, be sure to validate TLS 1.2 supportability, test carefully, and contact the vendor if needed.</span></span>

### <a name="federation-considerations-when-disabling-tls-1011-on-edge-servers"></a><span data-ttu-id="aeb8a-182">在边缘服务器上禁用 TLS 1.0/1.1 时的联合注意事项</span><span class="sxs-lookup"><span data-stu-id="aeb8a-182">Federation considerations when disabling TLS 1.0/1.1 on Edge servers</span></span>

<span data-ttu-id="aeb8a-183">您必须仔细规划并考虑在边缘服务器上禁用 TLS 1.0/1.1 的影响。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-183">You must carefully plan for and consider the impact of disabling TLS 1.0/1.1 on your Edge servers.</span></span>  <span data-ttu-id="aeb8a-184">一旦 TLS 1.0 和1.1 被禁用, 你可能会发现其他组织无法再与你的组织联盟。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-184">Once TLS 1.0 and 1.1 are disabled, you may find that other organizations are no longer be able to federate with your organization.</span></span>

<span data-ttu-id="aeb8a-185">你可以选择将 TLS 1.0/1.1 保留在 Edge 服务器上, 以保持与非修补 (SfB 2015、Lync 2013) 或较早 (2010) 外部系统的向后兼容性。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-185">You may opt to keep TLS 1.0/1.1 enabled on your Edge servers to maintain backward compatibility with non-patched (SfB 2015, Lync 2013) or older (2010) external systems.</span></span>

<span data-ttu-id="aeb8a-186">Microsoft 无法提供有关您的 Edge 网络 (或任何网络) 是否属于 PCI 标准的建议或建议。必须由单个公司确定。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-186">Microsoft cannot provide advice or recommendations on whether or not your Edge network (or any network) falls under PCI standard; that must be determined by the individual company.</span></span>

<span data-ttu-id="aeb8a-187">Skype for Business Online 目前支持 TLS 1.2, 因此不需要与在线的混合/联盟产生任何影响。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-187">Skype for Business Online is capable of TLS 1.2 today, so no impact to Hybrid/Federation with Online is expected.</span></span>

<span data-ttu-id="aeb8a-188">PIC (公共 IM 连接) 到 Skype 消费者服务: 我们不希望禁用 TLS 1.0/1.1 来影响[Skype 连接](../../deploy/deploy-skype-connectivity.md);Microsoft PIC 网关已经支持支持 TLS 1.2。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-188">PIC (Public IM Connectivity) to Skype Consumer service: We do not expect disabling TLS 1.0/1.1 to impact [Skype Connectivity](../../deploy/deploy-skype-connectivity.md); Microsoft PIC Gateways are already TLS 1.2 capable.</span></span>

## <a name="prerequisites-and-process"></a><span data-ttu-id="aeb8a-189">先决条件和过程</span><span class="sxs-lookup"><span data-stu-id="aeb8a-189">Prerequisites and process</span></span>

<span data-ttu-id="aeb8a-190">除了上面提到的情况, 一旦 TLS 1.0 和1.1 禁用了超出范围的服务器, 客户和设备将继续正常运行, 或者完全正常。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-190">Except where noted above, once TLS 1.0 and 1.1 are disabled out-of-scope servers, clients and devices will longer function properly, or at all.</span></span> <span data-ttu-id="aeb8a-191">这可能意味着你需要暂停并等待来自 Microsoft 的更新指南。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-191">This may mean you need to pause and wait for updated guidance from Microsoft.</span></span> <span data-ttu-id="aeb8a-192">一旦您满意满足所有要求并制定一个计划来解决缺口, 请继续操作。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-192">Once you are satisfied that you meet all requirements and have a plan to address gaps, proceed.</span></span>

<span data-ttu-id="aeb8a-193">在较高级别, 虽然 Skype for business Server 2019 已准备好进行安装过程, 但 Skype for business Server 2015 将需要安装 CU6 HF2、应用对 .NET 和 SQL 的必备更新、部署必备的注册表项, 最后一个单独的一轮操作系统配置更新 (例如, 通过注册表文件导入禁用 TLS 1.0 和 1.1)。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-193">At a high level, while Skype for Business Server 2019 is ready for procedure at install, Skype for Business Server 2015 will require that you install CU6 HF2, applying pre-requisite updates to .NET and SQL, deploying prerequisite registry keys, and finally a separate round of OS configuration updates (i.e. disabling TLS 1.0 and 1.1 via registry file import).</span></span> <span data-ttu-id="aeb8a-194">在你环境中的任何服务器上禁用 TLS 1.0 和1.1 之前, 必须先完成安装所有先决条件 (包括 Skype for Business Server 2015 CU6 HF2), 这一点至关重要。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-194">It is critically important that you complete installation of all prerequisites, including Skype for Business Server 2015 CU6 HF2, prior to disabling TLS 1.0 and 1.1 on any server in your environment.</span></span> <span data-ttu-id="aeb8a-195">每个 Skype for Business 服务器 (包括边缘角色和 SQL Backends) 都需要更新。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-195">Every Skype for Business server, including Edge role and SQL Backends, requires the updates.</span></span> <span data-ttu-id="aeb8a-196">还要确保所有受支持的 (范围内) 客户端已更新为所需的最低版本。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-196">Also ensure that all supported (in-scope) clients have been updated to the required minimum versions.</span></span> <span data-ttu-id="aeb8a-197">不要忘记更新管理工作站。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-197">Don’t forget to update management workstations as well.</span></span>

<span data-ttu-id="aeb8a-198">我们希望按照通常的 "内部" 操作顺序来升级 Skype for Business 服务器。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-198">We want to follow the usual order of operations of "inside out" for upgrading Skype for Business servers.</span></span> <span data-ttu-id="aeb8a-199">按照正常方式处理控制器池、持久聊天和配对的池。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-199">Treat Director pools, Persistent chat, and Paired Pools in the same manner you normally would.</span></span> <span data-ttu-id="aeb8a-200">升级的订单和方法在[此处](topology.md)和[此处](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015)介绍。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-200">Order and methods for upgrade are covered [here](topology.md) and [here](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).</span></span>

### <a name="high-level-process"></a><span data-ttu-id="aeb8a-201">高级别流程</span><span class="sxs-lookup"><span data-stu-id="aeb8a-201">High-level process</span></span>

1. <span data-ttu-id="aeb8a-202">在配置生产服务器之前测试实验室中的所有步骤。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-202">Test all steps in your lab prior to configuring production servers.</span></span>
2. <span data-ttu-id="aeb8a-203">在要更新的每台服务器和每台服务器上备份和保留导出注册表的副本。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-203">Back up and preserve a copy of exported registry on each and every individual server to be updated.</span></span> <span data-ttu-id="aeb8a-204">不能在服务器之间共享注册表;它们包含基于计算机的唯一密钥。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-204">You cannot share registries between servers; they contain unique machine-based keys.</span></span>
3. <span data-ttu-id="aeb8a-205">将所有 Skype for business 2015 服务器升级到 CU6 HF2 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-205">Upgrade all Skype for Business 2015 servers to CU6 HF2 or higher.</span></span> <span data-ttu-id="aeb8a-206">(对于 Skype for business Server 2019, 不需要进行 CU)</span><span class="sxs-lookup"><span data-stu-id="aeb8a-206">(For Skype for Business Server 2019, no CU is needed)</span></span>
4. <span data-ttu-id="aeb8a-207">将所有先决条件安装到所有服务器。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-207">Install all prerequisites to all servers.</span></span>
5. <span data-ttu-id="aeb8a-208">部署必备注册表项。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-208">Deploy prerequisite registry keys.</span></span>
6. <span data-ttu-id="aeb8a-209">确保更新所有范围内客户端。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-209">Ensure that all in-scope clients are updated.</span></span>
7. <span data-ttu-id="aeb8a-210">通过注册表导入禁用 TLS 1.0 和1.1。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-210">Disable TLS 1.0 and 1.1 via registry import.</span></span>
8. <span data-ttu-id="aeb8a-211">验证工作负荷是否按预期运行。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-211">Validate that workloads are functioning as expected.</span></span>
    - <span data-ttu-id="aeb8a-212">如果遇到问题、排除和解决问题, 或者</span><span class="sxs-lookup"><span data-stu-id="aeb8a-212">If problems are encountered, troubleshoot and resolve, or</span></span>
    - <span data-ttu-id="aeb8a-213">从步骤2还原注册表以重新启用 TLS 1.0 和1。1</span><span class="sxs-lookup"><span data-stu-id="aeb8a-213">Restore registry from step 2 to re-enable TLS 1.0 and 1.1</span></span>
9. <span data-ttu-id="aeb8a-214">验证是否仅使用 TLS 1.2。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-214">Validate that only TLS 1.2 is being used.</span></span>

### <a name="install-prerequisites-to-all-servers"></a><span data-ttu-id="aeb8a-215">将先决条件安装到所有服务器</span><span class="sxs-lookup"><span data-stu-id="aeb8a-215">Install prerequisites to all servers</span></span>

<span data-ttu-id="aeb8a-216">在开始在 Skype for Business Server 2015 部署中的操作系统级别禁用 TLS 1.0 和1.1 之前, 需要进行广泛的依赖项更新。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-216">Extensive dependency updating is required before you begin to disable TLS 1.0 and 1.1 at the operating system level in your Skype for Business Server 2015 deployments.</span></span> <span data-ttu-id="aeb8a-217">以下是可支持 TLS 1.2 的最低版本。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-217">The following are the minimum versions that can support TLS 1.2.</span></span> <span data-ttu-id="aeb8a-218">在开始禁用 TLS 1.0 和1.1 之前, 在你的环境中的每个 Skype for Business 服务器上部署所有先决条件更新。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-218">Deploy all prerequisite updates across every Skype for Business server in your environment before you begin disabling TLS 1.0 and 1.1.</span></span>

- <span data-ttu-id="aeb8a-219">Skype for Business Server 2015 CU6 HF2 6.0.9319.516 ([3 月2018更新](https://support.microsoft.com/en-us/help/4086059/march-2018-cumulative-update-6-0-9319-516-for-skype-for-business)) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="aeb8a-219">Skype for Business Server 2015 CU6 HF2 6.0.9319.516 ([March 2018 update](https://support.microsoft.com/en-us/help/4086059/march-2018-cumulative-update-6-0-9319-516-for-skype-for-business)) or higher</span></span>
- <span data-ttu-id="aeb8a-220">[.Net Framework 4.7](https://www.microsoft.com/en-us/download/details.aspx?id=55167)或更高版本在注册表中启用了 SchUseStrongCrypto (如下所示)</span><span class="sxs-lookup"><span data-stu-id="aeb8a-220">[.NET Framework 4.7](https://www.microsoft.com/en-us/download/details.aspx?id=55167) or higher with SchUseStrongCrypto enabled in the registry (provided below)</span></span>
- <span data-ttu-id="aeb8a-221">必须在所有 Skype for Business 2015 服务器和 backends 上更新 SQL。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-221">SQL must be updated on all Skype for Business 2015 servers and backends.</span></span> <span data-ttu-id="aeb8a-222">首先更新企业版池 SQL Backends, 然后再更新其各自的 FEs。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-222">Update Enterprise Edition Pool SQL Backends first, then their respective FEs.</span></span> 
    - <span data-ttu-id="aeb8a-223">SQL Server 2014 SP1 + CU5 ([link](https://support.microsoft.com/help/3130926)) 或更高版本/sql SERVER 2012 SP2 + CU16 或更高版本/sql SERVER 2014 RTM + CU12 ([link](https://support.microsoft.com/en-us/help/3130923/cumulative-update-12-for-sql-server-2014)) 或更高版本/sql server 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="aeb8a-223">SQL Server 2014 SP1 + CU5 ([link](https://support.microsoft.com/help/3130926)), or higher / SQL Server 2012 SP2 + CU16 or higher/ SQL Server 2014 RTM + CU12 ([link](https://support.microsoft.com/en-us/help/3130923/cumulative-update-12-for-sql-server-2014)) or higher / SQL Server 2014 SP2</span></span>
    - <span data-ttu-id="aeb8a-224">SQL server 的 SQL Server Native 客户端 2012 ([链接](https://www.microsoft.com/en-us/download/details.aspx?id=50402))</span><span class="sxs-lookup"><span data-stu-id="aeb8a-224">SQL Server Native Client for SQL Server 2012 ([link](https://www.microsoft.com/en-us/download/details.aspx?id=50402))</span></span>
    - <span data-ttu-id="aeb8a-225">Microsoft ODBC Driver 11 for SQL Server ([链接](https://www.microsoft.com/en-us/download/details.aspx?id=36434)) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="aeb8a-225">Microsoft ODBC Driver 11 for SQL Server ([link](https://www.microsoft.com/en-us/download/details.aspx?id=36434)), or higher</span></span>
    - <span data-ttu-id="aeb8a-226">SQL Server 2014 SP2 的共享管理对象 ([链接](https://www.microsoft.com/en-in/download/details.aspx?id=42295))</span><span class="sxs-lookup"><span data-stu-id="aeb8a-226">Shared Management Objects for SQL Server 2014 SP2 ([link](https://www.microsoft.com/en-in/download/details.aspx?id=42295))</span></span>
    - <span data-ttu-id="aeb8a-227">SQL server 2014 SP2 的 SQLSysClrTypes ([链接](https://www.microsoft.com/en-in/download/details.aspx?id=42295))</span><span class="sxs-lookup"><span data-stu-id="aeb8a-227">SQLSysClrTypes for SQL server 2014 SP2 ([link](https://www.microsoft.com/en-in/download/details.aspx?id=42295))</span></span>

### <a name="basic-steps-to-install-pre-requisites-in-recommended-order-of-operations"></a><span data-ttu-id="aeb8a-228">安装先决条件的基本步骤, 以推荐的操作顺序</span><span class="sxs-lookup"><span data-stu-id="aeb8a-228">Basic steps to install pre-requisites, in recommended order of operations</span></span>

1. <span data-ttu-id="aeb8a-229">将 Skype for business Server CU6HF2 (6.0.9319.516) 更新安装到所有服务器。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-229">Install the Skype for Business Server CU6HF2 (6.0.9319.516) update to all servers.</span></span> 
    1. <span data-ttu-id="aeb8a-230">使用更新程序安装对组件的更新。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-230">Install the update to components using the updater.</span></span>
    2. <span data-ttu-id="aeb8a-231">根据已记录的过程更新数据库。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-231">Update databases according to documented procedures.</span></span> <span data-ttu-id="aeb8a-232">说明已记录在[https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015)。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-232">Instructions are documented at [https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).</span></span>
    3. <span data-ttu-id="aeb8a-233">在迁移之前先验证部署中的产品功能, 然后再进行任何其他更改。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-233">Validate product functionality in the deployment prior to moving forward with any other changes.</span></span>
2. <span data-ttu-id="aeb8a-234">下载 .NET 4.7 脱机安装程序。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-234">Download .NET 4.7 Offline Installer.</span></span> 
    1. <span data-ttu-id="aeb8a-235">参阅[https://www.microsoft.com/en-us/download/details.aspx?id=55167](https://www.microsoft.com/en-us/download/details.aspx?id=55167)</span><span class="sxs-lookup"><span data-stu-id="aeb8a-235">Reference: [https://www.microsoft.com/en-us/download/details.aspx?id=55167](https://www.microsoft.com/en-us/download/details.aspx?id=55167)</span></span>
    2. <span data-ttu-id="aeb8a-236">确保在前端服务器上停止 Skype for business Server 2015 服务。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-236">Ensure that Skype for Business Server 2015 services are stopped on the Front End server.</span></span>
    3. <span data-ttu-id="aeb8a-237">参阅[https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015)</span><span class="sxs-lookup"><span data-stu-id="aeb8a-237">Reference: [https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015)</span></span>
    4. <span data-ttu-id="aeb8a-238">Ex (标准版): 停止-CsWindowsServices</span><span class="sxs-lookup"><span data-stu-id="aeb8a-238">Ex (Standard Edition): Stop-CsWindowsServices</span></span>
    5. <span data-ttu-id="aeb8a-239">Ex (企业版): 调用 CsComputerFailover</span><span class="sxs-lookup"><span data-stu-id="aeb8a-239">Ex (Enterprise Edition): Invoke-CsComputerFailover</span></span>
    6. <span data-ttu-id="aeb8a-240">运行安装程序包。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-240">Run the installer package.</span></span>
    7. <span data-ttu-id="aeb8a-241">重新启动服务器。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-241">Reboot the server.</span></span>
3. <span data-ttu-id="aeb8a-242">在所有服务器上更新 SQL Express 2014。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-242">Update SQL Express 2014 on all servers.</span></span> 
    1. <span data-ttu-id="aeb8a-243">参阅[https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span><span class="sxs-lookup"><span data-stu-id="aeb8a-243">Reference: [https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span></span>
    2. <span data-ttu-id="aeb8a-244">下载 SQL 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="aeb8a-244">Download SQL 2014 SP2</span></span> 
        - <span data-ttu-id="aeb8a-245">参阅[https://www.microsoft.com/en-us/download/details.aspx?id=53168](https://www.microsoft.com/en-us/download/details.aspx?id=53168)</span><span class="sxs-lookup"><span data-stu-id="aeb8a-245">Reference: [https://www.microsoft.com/en-us/download/details.aspx?id=53168](https://www.microsoft.com/en-us/download/details.aspx?id=53168)</span></span>
    3. <span data-ttu-id="aeb8a-246">将安装媒体复制到服务器上的文件夹 (例如: C:\01_2014SqlSp2)</span><span class="sxs-lookup"><span data-stu-id="aeb8a-246">Copy the installation media to a folder on the server (Ex: C:\01_2014SqlSp2)</span></span>
    4. <span data-ttu-id="aeb8a-247">确保在前端服务器上停止 Skype for business 服务器2015服务</span><span class="sxs-lookup"><span data-stu-id="aeb8a-247">Ensure Skype for Business Server 2015 services are stopped on the Front End server</span></span> 
        - <span data-ttu-id="aeb8a-248">Ex (标准版): 停止-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="aeb8a-248">Ex (Standard Edition): Stop-CsWindowsService</span></span>
        - <span data-ttu-id="aeb8a-249">Ex (企业版): 调用 CsComputerFailove</span><span class="sxs-lookup"><span data-stu-id="aeb8a-249">Ex (Enterprise Edition): Invoke-CsComputerFailove</span></span>
    5. <span data-ttu-id="aeb8a-250">打开管理员命令提示符, 并升级所有已安装的组件和实例</span><span class="sxs-lookup"><span data-stu-id="aeb8a-250">Open an Admin Command Prompt, and upgrade all installed components and instances</span></span> 
        - <span data-ttu-id="aeb8a-251">示例: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe/qs/IAcceptSQLServerLicenseTerms/Action = Patch/AllInstances</span><span class="sxs-lookup"><span data-stu-id="aeb8a-251">Example: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe /qs /IAcceptSQLServerLicenseTerms /Action=Patch /AllInstances</span></span>
4. <span data-ttu-id="aeb8a-252">更新 SQL Native 客户端。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-252">Update SQL Native Client.</span></span> 
    1. <span data-ttu-id="aeb8a-253">参考: [https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server)。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-253">Reference: [https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server).</span></span>
    2. <span data-ttu-id="aeb8a-254">下载自[https://www.microsoft.com/en-us/download/details.aspx?id=50402](https://www.microsoft.com/en-us/download/details.aspx?id=50402)</span><span class="sxs-lookup"><span data-stu-id="aeb8a-254">Download from [https://www.microsoft.com/en-us/download/details.aspx?id=50402](https://www.microsoft.com/en-us/download/details.aspx?id=50402)</span></span>
    3. <span data-ttu-id="aeb8a-255">确保前端服务器上的 Skype for business Server 2015 服务已停止。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-255">Ensure Skype for Business Server 2015 services are stopped on the Front End server.</span></span> 
        - <span data-ttu-id="aeb8a-256">Ex (标准版): 停止-CsWindowsServices</span><span class="sxs-lookup"><span data-stu-id="aeb8a-256">Ex (Standard Edition): Stop-CsWindowsServices</span></span>
        - <span data-ttu-id="aeb8a-257">Ex (企业版): 调用 CsComputerFailove</span><span class="sxs-lookup"><span data-stu-id="aeb8a-257">Ex (Enterprise Edition): Invoke-CsComputerFailove</span></span>
    4. <span data-ttu-id="aeb8a-258">停止运行已安装的 SQL 实例</span><span class="sxs-lookup"><span data-stu-id="aeb8a-258">Stop the SQL instances installed from running</span></span> 
        - <span data-ttu-id="aeb8a-259">Ex: Get 服务 "MSSQL $ RTCLOCAL" |停止-Servic</span><span class="sxs-lookup"><span data-stu-id="aeb8a-259">Ex: Get-Service 'MSSQL$RTCLOCAL' | Stop-Servic</span></span>
        - <span data-ttu-id="aeb8a-260">Ex: Get 服务 "MSSQL $ LYNCLOCAL" |停止-Servic</span><span class="sxs-lookup"><span data-stu-id="aeb8a-260">Ex: Get-Service 'MSSQL$LYNCLOCAL' | Stop-Servic</span></span>
        - <span data-ttu-id="aeb8a-261">Ex (仅适用于标准版): 获取服务 "MSSQL $ RTC" |停止-Servic</span><span class="sxs-lookup"><span data-stu-id="aeb8a-261">Ex (Standard Edition Only): Get-Service 'MSSQL$RTC' | Stop-Servic</span></span>
    5. <span data-ttu-id="aeb8a-262">安装该更新。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-262">Install the update.</span></span>
5. <span data-ttu-id="aeb8a-263">更新 SQL Server 的 ODBC Driver 11。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-263">Update ODBC Driver 11 for SQL Server.</span></span> 
    1. <span data-ttu-id="aeb8a-264">参考: [https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server)。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-264">Reference: [https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server).</span></span>
    2. <span data-ttu-id="aeb8a-265">下载自[https://www.microsoft.com/en-us/download/confirmation.aspx?id=36434](https://www.microsoft.com/en-us/download/confirmation.aspx?id=36434)</span><span class="sxs-lookup"><span data-stu-id="aeb8a-265">Download from [https://www.microsoft.com/en-us/download/confirmation.aspx?id=36434](https://www.microsoft.com/en-us/download/confirmation.aspx?id=36434)</span></span>
    3. <span data-ttu-id="aeb8a-266">确保在前端服务器上停止 Skype for business Server 2015 服务</span><span class="sxs-lookup"><span data-stu-id="aeb8a-266">Ensure that Skype for Business Server 2015 services are stopped on the Front End server</span></span> 
        - <span data-ttu-id="aeb8a-267">Ex (标准版): 停止-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="aeb8a-267">Ex (Standard Edition): Stop-CsWindowsService</span></span>
        - <span data-ttu-id="aeb8a-268">Ex (企业版): 调用 CsComputerFailove</span><span class="sxs-lookup"><span data-stu-id="aeb8a-268">Ex (Enterprise Edition): Invoke-CsComputerFailove</span></span>
    4. <span data-ttu-id="aeb8a-269">安装该更新。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-269">Install the update.</span></span>
6. <span data-ttu-id="aeb8a-270">部署必备注册表项。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-270">Deploy prerequisite registry keys.</span></span>

### <a name="pre-requisite-registry-keys"></a><span data-ttu-id="aeb8a-271">预必备注册表项</span><span class="sxs-lookup"><span data-stu-id="aeb8a-271">Pre-requisite registry keys</span></span>

<span data-ttu-id="aeb8a-272">将以下测试复制/粘贴到记事本中并重命名 TLSPreReq 或您选择的名称, 然后导入:</span><span class="sxs-lookup"><span data-stu-id="aeb8a-272">Copy/paste the following test into Notepad and rename TLSPreReq.reg or a name of your choice, then import:</span></span>

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

<span data-ttu-id="aeb8a-273">对于适用于企业版池的 SQL 后端, 应将先决条件和 TLS disable 视为任何 SQL 或 OS 更新。请参阅:[https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)</span><span class="sxs-lookup"><span data-stu-id="aeb8a-273">For SQL back ends for Enterprise Edition Pools, prerequisites and TLS disable should be treated as any SQL or OS updates would; refer to: [https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)</span></span>

<span data-ttu-id="aeb8a-274">虽然必备的应用程序和 TLS 禁用步骤都可以合并, 但我们强烈建议在操作系统级别继续禁用 TLS 1.0 和1.1 之前应用所有先决条件。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-274">While both the prerequisite application and TLS disabling steps can be combined, we strongly recommend all prerequisites be applied before proceeding with disabling of TLS 1.0 and 1.1 at the operating system level.</span></span> <span data-ttu-id="aeb8a-275">最佳做法做法是通过部署所有先决条件来准备环境、验证工作负荷是否正常运行和预期, 然后在以后继续执行 TLS 1.0/1.1。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-275">The best practice approach would be to prepare the environment by deploying all prerequisites, validating that workloads all function correctly and as expected, and then proceeding with TLS 1.0/1.1 disable at a later time.</span></span>

### <a name="disable-tls-10-and-11-via-registry-import"></a><span data-ttu-id="aeb8a-276">通过注册表导入禁用 TLS 1.0 和1。1</span><span class="sxs-lookup"><span data-stu-id="aeb8a-276">Disable TLS 1.0 and 1.1 via registry import</span></span>

<span data-ttu-id="aeb8a-277">在继续下一步操作之前,*请确保已完成所有先决条件和更新的 Skype for Business 服务器*。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-277">Before you proceed with the next steps, *make sure you have completed all prerequisites and updated Skype for Business Servers*.</span></span>

<span data-ttu-id="aeb8a-278">将以下文本复制到记事本文件中, 然后将其重命名**TLSDisable**:</span><span class="sxs-lookup"><span data-stu-id="aeb8a-278">Copy the following text into a Notepad file and rename it **TLSDisable.reg**:</span></span>

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

<span data-ttu-id="aeb8a-279">在要禁用 TLS 1.0 和1.1 的每台服务器上导入 .reg 文件。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-279">Import the .reg file on each server you wish to disable TLS 1.0 and 1.1.</span></span> <span data-ttu-id="aeb8a-280">重新启动服务器。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-280">Reboot the server.</span></span> <span data-ttu-id="aeb8a-281">服务重新联机后, 移动到下一台服务器。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-281">Once the services have come back online, move to the next server.</span></span> <span data-ttu-id="aeb8a-282">适用于企业版池的方法与进行任何操作系统更新所需的方法相同。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-282">The approach for Enterprise Edition Pools is the same you would take for any OS update.</span></span>

<span data-ttu-id="aeb8a-283">你可能已注意到, 我们执行的操作不仅仅是在此处禁用 TLS 1.0 和1.1。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-283">You may have noticed we are doing more than just disabling TLS 1.0 and 1.1 here.</span></span> <span data-ttu-id="aeb8a-284">我们支持密码套件重新排序 (如上所示) 和禁用某些较旧的弱密码。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-284">We are supporting Cipher Suite re-order (as shown above) and the disabling of some older weak ciphers.</span></span> <span data-ttu-id="aeb8a-285">这是我们首次在 Skype for Business 服务器上对 SCHANNEL 和加密 API 的这些更改的首次支持, 请务必注意, 这些更改是我们支持且现在已测试的唯一这些更改。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-285">This is the first time we have officially supported these changes to SCHANNEL and Crypto API on Skype for Business Server, and it is important to note that these changes are the only ones we support and have tested at this time.</span></span> <span data-ttu-id="aeb8a-286">我们将来可能会考虑到其他配置, 但目前请不要在你的实现中修改注册表导入文件。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-286">We may consider additional configurations in the future, but for now, please do not modify the registry import file in your implementation.</span></span>

### <a name="validate-that-workloads-are-functioning-as-expected"></a><span data-ttu-id="aeb8a-287">验证工作负荷是否按预期运行</span><span class="sxs-lookup"><span data-stu-id="aeb8a-287">Validate that workloads are functioning as expected</span></span>

<span data-ttu-id="aeb8a-288">一旦 TLS 1.0 和1.1 在你的环境中被禁用, 请确保你的所有主工作负荷正常运行, 例如 IM & 状态、P2P 呼叫、企业语音等。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-288">Once TLS 1.0 and 1.1 have been disabled in your environment, ensure that all your main workloads are functioning as expected, such as IM & Presence, P2P calls, Enterprise Voice, etc.</span></span>

<span data-ttu-id="aeb8a-289">**仅验证正在使用的 TLS 1。2**</span><span class="sxs-lookup"><span data-stu-id="aeb8a-289">**Validate only TLS 1.2 is being used**</span></span>

<span data-ttu-id="aeb8a-290">让你的安全团队执行新的 Skype for business 通信审核, 以确保不再使用 TLS 1.0 和1.1 的较旧协议。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-290">Have your Security Team perform a new audit of Skype for Business traffic to ensure that the older protocols TLS 1.0 and 1.1 are no longer in use.</span></span>

<span data-ttu-id="aeb8a-291">或者, 你可以使用 Internet Explorer 从 Skype for Business Server 2015 中的 Skype for Business Server 测试 TLS 连接, 然后禁用 TLS 1.0 和 TLS 1.1。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-291">Alternatively, you can use Internet Explorer to test TLS connections to web services from Skype for Business Server 2015 after TLS 1.0 and TLS 1.1 have been disabled.</span></span>

1. <span data-ttu-id="aeb8a-292">启动 Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-292">Launch Internet Explorer.</span></span>
2. <span data-ttu-id="aeb8a-293">选择**工具** > "**Internet 选项**"。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-293">Select **Tools** > **Internet Options**.</span></span>
3. <span data-ttu-id="aeb8a-294">选择 "**高级**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-294">Select the **Advanced** tab.</span></span>
4. <span data-ttu-id="aeb8a-295">在 "**设置**" 下, 滚动到底部。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-295">Under **Settings**, scroll to the bottom.</span></span>
5. <span data-ttu-id="aeb8a-296">验证 TLS 1.0、TLS 1.1 和 TLS 1.2 是否已启用。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-296">Verify that TLS 1.0, TLS 1.1, and TLS 1.2 are enabled.</span></span>
6. <span data-ttu-id="aeb8a-297">浏览 SfB 2015 池的内部 Web 服务 URL (应成功连接)。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-297">Browse the Internal Web Service URL of your SfB 2015 pool (should connect successfully).</span></span>
7. <span data-ttu-id="aeb8a-298">返回到 Internet Explorer 并禁用仅**使用 TLS 1.2**的选项。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-298">Go back into Internet Explorer and disable the option to **Use TLS 1.2** only.</span></span>
8. <span data-ttu-id="aeb8a-299">再次浏览 SfB 2015 池的内部 Web 服务 URL (应该无法连接)。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-299">Browse the Internal Web Service URL of your SfB 2015 pool again (should fail to connect).</span></span>

![Internet 选项](../../media/internet-options.jpg)

## <a name="advanced-deployment-scenarios"></a><span data-ttu-id="aeb8a-301">高级部署方案</span><span class="sxs-lookup"><span data-stu-id="aeb8a-301">Advanced deployment scenarios</span></span>

<span data-ttu-id="aeb8a-302">由于需要某些依赖项先决条件来支持 Skype for Business Ser 2015 中的 TLS 1.2, 因此在禁用 TLS 1.0 和1.1 的任何系统上都将无法使用 RTM 介质进行安装。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-302">Because some dependency prerequisites are required to support TLS 1.2 in Skype for Business Ser 2015, installing from RTM media will fail on any system where TLS 1.0 and 1.1 have been disabled.</span></span>

<span data-ttu-id="aeb8a-303">**在你的环境中禁用了 TLS 1.0 和1.1 后部署新的标准版服务器或企业版池。**</span><span class="sxs-lookup"><span data-stu-id="aeb8a-303">**Deploying New Standard Edition Servers or Enterprise Edition Pools once TLS 1.0 and 1.1 have been disabled in your environment.**</span></span>

<span data-ttu-id="aeb8a-304">**选项 1:** 使用[SmartSetup](../../deploy/install/install-skype-for-business-server.md)。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-304">**Option 1:** Use [SmartSetup](../../deploy/install/install-skype-for-business-server.md).</span></span> <span data-ttu-id="aeb8a-305">请注意, 我们正在更新 SmartSetup 以在将来的 CU 中容纳已更新的 SQL 二进制文件, 并将在将来更新本文。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-305">Note that we are updating SmartSetup to accommodate the updated SQL binaries in a future CU, and will update this article in the future.</span></span>

<span data-ttu-id="aeb8a-306">**选项 2:** 预安装本地 SQL 实例 (RTCLOCAL 和 LYNCLOCAL)</span><span class="sxs-lookup"><span data-stu-id="aeb8a-306">**Option 2:** Pre-install local SQL instances (RTCLOCAL and LYNCLOCAL)</span></span>

1. <span data-ttu-id="aeb8a-307">将 SQL Express 2014 SP2 (SQLEXPR_x64) 下载并复制到 FE 上的本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-307">Download and copy SQL Express 2014 SP2 (SQLEXPR_x64.exe) to local folder on FE.</span></span> <span data-ttu-id="aeb8a-308">假设 "文件夹路径" <SQL_FOLDER_PATH> "。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-308">Let’s say folder path <SQL_FOLDER_PATH>.</span></span>
2. <span data-ttu-id="aeb8a-309">启动 PowerShell 或命令提示符并导航到 <SQL_FOLDER_PATH ">。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-309">Launch PowerShell or Command Prompt and navigate to <SQL_FOLDER_PATH>.</span></span>
3. <span data-ttu-id="aeb8a-310">通过运行下面的命令创建 RTCLOCAL SQL 实例。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-310">Create the RTCLOCAL SQL instance by running the command below.</span></span> <span data-ttu-id="aeb8a-311">请等到 SQLEXPR_x64 完成后再继续操作:</span><span class="sxs-lookup"><span data-stu-id="aeb8a-311">Wait until SQLEXPR_x64.exe finishes before proceeding:</span></span>

    <span data-ttu-id="aeb8a-312">SQLEXPR_x64/Q/IACCEPTSQLSERVERLICENSETERMS/UPDATEENABLED = 0/HIDECONSOLE/ACTION = 安装/FEATURES = SQLEngine, Tools/INSTANCENAME = RTCLOCAL/TCPENABLED = 1/SQLSVCACCOUNT = "NT AUTHORITY\NetworkService"/SQLSYSADMINACCOUNTS = "内置 \管理员 "/BROWSERSVCSTARTUPTYPE =" 自动 "/AGTSVCACCOUNT =" NTAUTHORITY\NetworkService "/SQLSVCSTARTUPTYPE = Automati</span><span class="sxs-lookup"><span data-stu-id="aeb8a-312">SQLEXPR_x64.exe  /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=RTCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automati</span></span>
1. <span data-ttu-id="aeb8a-313">通过运行下面的命令创建 LYNCLOCAL SQL 实例。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-313">Create the LYNCLOCAL SQL instance by running the command below.</span></span> <span data-ttu-id="aeb8a-314">等到 SQLEXPR_x64 完成后再继续下一步操作:</span><span class="sxs-lookup"><span data-stu-id="aeb8a-314">Wait until SQLEXPR_x64.exe finishes before proceeding to the next step:</span></span>

    <span data-ttu-id="aeb8a-315">SQLEXPR_x64/Q/IACCEPTSQLSERVERLICENSETERMS/UPDATEENABLED = 0/HIDECONSOLE/ACTION = 安装/FEATURES = SQLEngine, Tools/INSTANCENAME = LYNCLOCAL/TCPENABLED = 1/SQLSVCACCOUNT = "NT AUTHORITY\NetworkService"/SQLSYSADMINACCOUNTS = "内置 \管理员 "/BROWSERSVCSTARTUPTYPE =" 自动 "/AGTSVCACCOUNT =" NTAUTHORITY\NetworkService "/SQLSVCSTARTUPTYPE = 自动</span><span class="sxs-lookup"><span data-stu-id="aeb8a-315">SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=LYNCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automatic</span></span>
1. <span data-ttu-id="aeb8a-316">运行 Skype for Business Server 2015 RTM 设置。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-316">Run Skype for Business Server 2015 RTM setup.</span></span>
2. <span data-ttu-id="aeb8a-317">按照上面的 "先决条件" 部分中的其余步骤操作。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-317">Follow the remaining steps from the prerequisites section above.</span></span>

<span data-ttu-id="aeb8a-318">**选项 3:** 您也可以手动替换本地安装媒体目录中的二进制文件, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="aeb8a-318">**Option 3:** You may also manually replace binaries in a local installation media directory as follows:</span></span>

1. [<span data-ttu-id="aeb8a-319">安装 Skype for business 服务器的先决条件</span><span class="sxs-lookup"><span data-stu-id="aeb8a-319">Install prerequisites for Skype for Business Server</span></span>](../../deploy/install/install-prerequisites.md)  
2. 2. <span data-ttu-id="aeb8a-320">安装 .NET 4.7:</span><span class="sxs-lookup"><span data-stu-id="aeb8a-320">Install .NET 4.7:</span></span> 
      - <span data-ttu-id="aeb8a-321">**注意:** 我们首先在 Skype for business Server 2015 CU5 + (6.0.9319.281) 中引入了对 .NET 4.7 的支持。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-321">**Note:** We first introduced support for .NET 4.7 in Skype for Business Server 2015 CU5+ (6.0.9319.281).</span></span> <span data-ttu-id="aeb8a-322">因此, 在后面的步骤中, 我们将在主安装之前更新核心组件。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-322">Therefore, in later steps below we will be updating Core Components prior to the main install.</span></span>
      - <span data-ttu-id="aeb8a-323">下载: https://www.microsoft.com/en-us/download/details.aspx?id=55167。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-323">Download: https://www.microsoft.com/en-us/download/details.aspx?id=55167.</span></span>
      - <span data-ttu-id="aeb8a-324">参考:[应在 Skype For Business Server 2015 部署之前安装的软件](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)</span><span class="sxs-lookup"><span data-stu-id="aeb8a-324">Reference: [Software that should be installed before a Skype for Business Server 2015 deployment](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)</span></span>
3. <span data-ttu-id="aeb8a-325">复制 ISO 文件/文件夹:</span><span class="sxs-lookup"><span data-stu-id="aeb8a-325">Copy ISO Files/Folders:</span></span> 
    - <span data-ttu-id="aeb8a-326">通过附加 Skype for Business Server 2015 ISO, 打开它所附加的驱动器的根目录 (例如:\)在文件资源管理器中)。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-326">With the Skype for Business Server 2015 ISO attached, open the root directory of the drive it is attached as (Ex: D:\) in File Explorer.</span></span>
    - <span data-ttu-id="aeb8a-327">将所有文件夹和文件复制到本地磁盘上的文件夹 (例如: C:\SkypeForBusiness2015ISO)。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-327">Copy all folders and files to a folder on a local disk (Ex: C:\SkypeForBusiness2015ISO).</span></span>
    - <span data-ttu-id="aeb8a-328">**注意:** 安装组件之前, 需要更新某些文件, 以支持 TLS 1.2。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-328">**Note:** Prior to installing components, some files will need to be updated for support of TLS 1.2.</span></span>
4. <span data-ttu-id="aeb8a-329">替换 MSI/EXE 程序包:</span><span class="sxs-lookup"><span data-stu-id="aeb8a-329">Replace MSI/EXE Packages:</span></span> 
    - <span data-ttu-id="aeb8a-330">替换本地计算机上安装媒体的/Setup/amd64/文件夹中的现有 MSI 和 EXE 程序包。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-330">Replace the existing MSI and EXE packages in the /Setup/amd64/ folder of the installation media on the local machine.</span></span>
    - <span data-ttu-id="aeb8a-331">SQL 2014 SP2 Express:https://www.microsoft.com/en-us/download/details.aspx?id=53167</span><span class="sxs-lookup"><span data-stu-id="aeb8a-331">SQL 2014 SP2 Express: https://www.microsoft.com/en-us/download/details.aspx?id=53167</span></span> 
        - <span data-ttu-id="aeb8a-332">在本地计算机上重命名为 SQLEXPR_x64, 并替换安装媒体的 Setup/amd64/文件夹中的现有文件。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-332">Rename to SQLEXPR_x64 on the local machine, and replace the existing file in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="aeb8a-333">SQL Native 客户端:https://www.microsoft.com/en-us/download/details.aspx?id=50402</span><span class="sxs-lookup"><span data-stu-id="aeb8a-333">SQL Native Client: https://www.microsoft.com/en-us/download/details.aspx?id=50402</span></span> 
        - <span data-ttu-id="aeb8a-334">**注意:** 如有必要, 请将其重命名为 sqlncli, 然后替换安装媒体的 Setup/amd64/文件夹中存在的现有文件。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-334">**Note:** Rename this if necessary to sqlncli.msi, and then replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="aeb8a-335">SQL 管理对象:https://www.microsoft.com/en-us/download/details.aspx?id=53164</span><span class="sxs-lookup"><span data-stu-id="aeb8a-335">SQL Management Objects: https://www.microsoft.com/en-us/download/details.aspx?id=53164</span></span> 
        - <span data-ttu-id="aeb8a-336">**注意:** 功能包将有大量可供下载的项目。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-336">**Note:** The Feature pack will have a lot of items that can be downloaded.</span></span> <span data-ttu-id="aeb8a-337">选择仅下载 SharedManagementObjects。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-337">Select to download SharedManagementObjects.msi only.</span></span>
        - <span data-ttu-id="aeb8a-338">**注意:** 替换安装媒体的 Setup/amd64/文件夹中存在的现有文件。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-338">**Note:** Replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="aeb8a-339">SQL CLR 类型:https://www.microsoft.com/en-us/download/details.aspx?id=53164</span><span class="sxs-lookup"><span data-stu-id="aeb8a-339">SQL CLR Types: https://www.microsoft.com/en-us/download/details.aspx?id=53164</span></span> 
        - <span data-ttu-id="aeb8a-340">**注意:** 功能包将有大量可供下载的项目。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-340">**Note:** The Feature pack will have a lot of items that can be downloaded.</span></span> <span data-ttu-id="aeb8a-341">选择仅下载 CQLSysClrTypes</span><span class="sxs-lookup"><span data-stu-id="aeb8a-341">Select to download CQLSysClrTypes.msi only</span></span>
        - <span data-ttu-id="aeb8a-342">**注意**: 替换安装媒体的 Setup/amd64/文件夹中存在的现有文件。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-342">**Note**: Replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
5. <span data-ttu-id="aeb8a-343">安装核心组件:</span><span class="sxs-lookup"><span data-stu-id="aeb8a-343">Install Core Components:</span></span> 
    - <span data-ttu-id="aeb8a-344">从安装媒体的 Setup/amd64/文件夹运行 Setup.exe。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-344">Run Setup.exe from the Setup/amd64/ folder of the installation media.</span></span> <span data-ttu-id="aeb8a-345">按照说明安装核心组件</span><span class="sxs-lookup"><span data-stu-id="aeb8a-345">Follow the instructions to install Core Components</span></span>
    - <span data-ttu-id="aeb8a-346">关闭核心组件。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-346">Close Core Components.</span></span>
6. <span data-ttu-id="aeb8a-347">更新核心组件:</span><span class="sxs-lookup"><span data-stu-id="aeb8a-347">Update Core Components:</span></span> 
    - <span data-ttu-id="aeb8a-348">下载 Skype for Business 更新安装程序。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-348">Download the Skype for Business Update Installer.</span></span>
    - <span data-ttu-id="aeb8a-349">运行安装程序以更新核心组件并安装性能计数器。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-349">Run the installer to update Core Components and install the performance counters.</span></span>
    - <span data-ttu-id="aeb8a-350">**注意:** 从 CU6HF2 发布开始, "自动更新" 功能目前仅安装最多 CU6。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-350">**Note:** As of the release of CU6HF2, the auto-update feature currently only will install up to CU6.</span></span> <span data-ttu-id="aeb8a-351">因此, 必须单独运行更新程序, 以将核心组件更新到6.0.9319.516。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-351">Therefore, the updater must be run separately to update Core Components to 6.0.9319.516.</span></span>
    - <span data-ttu-id="aeb8a-352">参阅https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015</span><span class="sxs-lookup"><span data-stu-id="aeb8a-352">Reference: https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015</span></span>
7. <span data-ttu-id="aeb8a-353">安装管理工具 (可选):</span><span class="sxs-lookup"><span data-stu-id="aeb8a-353">Install Administrative Tools (Optional):</span></span> 
    - <span data-ttu-id="aeb8a-354">这将使用已更新的文件安装 Microsoft SQL Server 2012 本机客户端、SQL Server 2014 管理对象 (x64) 和 Microsoft System CLR 类型 (x64) 和 SQL Server 2014 (x64)。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-354">This will install the Microsoft SQL Server 2012 Native Client, SQL Server 2014 Management Objects (x64), and Microsoft System CLR Types for SQL Server 2014 (x64) using the updated files.</span></span> <span data-ttu-id="aeb8a-355">此外, Skype for Business Server 2015 拓扑生成器和控制面板将在本地计算机上可用。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-355">Additionally, the Skype for Business Server 2015 Topology Builder and Control Panel will be available on the local machine.</span></span>
8. <span data-ttu-id="aeb8a-356">安装本地配置存储 (步骤 1):</span><span class="sxs-lookup"><span data-stu-id="aeb8a-356">Install Local Configuration Store (Step 1):</span></span> 
     - <span data-ttu-id="aeb8a-357">打开部署向导, 单击 "安装或更新 Skype for business 服务器系统", 然后单击步骤1中的 "**运行**": "安装本地配置存储"。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-357">Open the Deployment Wizard, click Install or Update Skype for Business Server System, and click on **Run** at Step 1: Install Local Configuration Store.</span></span>
     - <span data-ttu-id="aeb8a-358">单击 "**安装本地配置存储**" 对话框中的 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-358">Click **Next** in the **Install Local Configuration Store** dialog box.</span></span>
     <span data-ttu-id="aeb8a-359">!["安装本地配置存储" 对话框](../../media/local-configuration-store.png)</span><span class="sxs-lookup"><span data-stu-id="aeb8a-359">![Install Local Configuration Store dialog box](../../media/local-configuration-store.png)</span></span>
     - <span data-ttu-id="aeb8a-360">查看结果, 确保任务状态为 "已完成"。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-360">Review the results, and ensure that the Task Status is Completed.</span></span> <span data-ttu-id="aeb8a-361">通过单击 "**查看日志**" 查看生成的日志文件。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-361">Review the resulting log file by clicking **View Log**.</span></span>
     <span data-ttu-id="aeb8a-362">![任务状态显示为已完成](../../media/local-configuration-task-completed.png)</span><span class="sxs-lookup"><span data-stu-id="aeb8a-362">![Task status shows as Completed](../../media/local-configuration-task-completed.png)</span></span>
     - <span data-ttu-id="aeb8a-363">单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-363">Click **Finish**.</span></span>
9. <span data-ttu-id="aeb8a-364">设置或删除 Skype for business 服务器组件 (步骤 2):</span><span class="sxs-lookup"><span data-stu-id="aeb8a-364">Set up or remove Skype for Business Server Components (Step 2):</span></span>
    - <span data-ttu-id="aeb8a-365">打开部署向导, 单击 "**安装或更新 skype for Business 服务器系统**", 然后单击步骤2中的 "**运行**": 设置或删除 Skype for business 服务器组件</span><span class="sxs-lookup"><span data-stu-id="aeb8a-365">Open the Deployment Wizard, click **Install or Update Skype for Business Server System**, and click **Run** at Step 2: Set up or Remove Skype for Business Server Components</span></span>
    - <span data-ttu-id="aeb8a-366">在 "设置 Skype for Business 服务器组件" 对话框中, 单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-366">Click **Next** in the Set Up Skype for Business Server Components dialog box.</span></span>
    <span data-ttu-id="aeb8a-367">!["设置 Skype for Business 服务器组件" 窗口](../../media/set-up-skype-for-business-server-components-window.png)</span><span class="sxs-lookup"><span data-stu-id="aeb8a-367">![the Set Up Skype for Business Server Components window](../../media/set-up-skype-for-business-server-components-window.png)</span></span>
    - <span data-ttu-id="aeb8a-368">使用 "查看日志" 查看日志, 并验证安装程序是否未出现问题。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-368">Review the log using View Log, and validate that setup completed without issues.</span></span> 
    - <span data-ttu-id="aeb8a-369">单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-369">Click **Finish**.</span></span>
10. <span data-ttu-id="aeb8a-370">根据需要继续执行其他安装和配置 (此时可以恢复正常的安装过程)。</span><span class="sxs-lookup"><span data-stu-id="aeb8a-370">Proceed with additional installation and configuration as required (you can resume normal installation procedures at this point).</span></span>
