---
title: 在 Skype for Business Server 2015 中禁用 TLS 1.0/1。1
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
description: 摘要：在你的环境中准备和实现禁用 TLS 1.0 和1.1。
ms.openlocfilehash: 691dcc170830b3efa6129d23401930fcf1c149cb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817143"
---
# <a name="disable-tls-1011-in-skype-for-business-server-2015"></a><span data-ttu-id="d6423-103">在 Skype for Business Server 2015 中禁用 TLS 1.0/1。1</span><span class="sxs-lookup"><span data-stu-id="d6423-103">Disable TLS 1.0/1.1 in Skype for Business Server 2015</span></span>

<span data-ttu-id="d6423-104">本文旨在为你提供必要的指南，以便你准备和实现在你的环境中禁用 TLS 1.0 和1.1。</span><span class="sxs-lookup"><span data-stu-id="d6423-104">The purpose of this article is to provide the necessary guidance for you to prepare for and implement disabling TLS 1.0 and 1.1 in your environments.</span></span> <span data-ttu-id="d6423-105">此过程需要广泛的规划和准备。</span><span class="sxs-lookup"><span data-stu-id="d6423-105">This process requires extensive planning and preparation.</span></span> <span data-ttu-id="d6423-106">请仔细查看本文中的所有信息，确保你的计划能够为你的组织禁用 TLS 1.0 和1.1。</span><span class="sxs-lookup"><span data-stu-id="d6423-106">Please carefully review all of the information in this article as you make your plan to disable TLS 1.0 and 1.1 for your organization.</span></span> <span data-ttu-id="d6423-107">请注意，有许多外部依赖项和连接条件可能会受到禁用 TLS 1.0/1.1 的影响，因此需要进行大量的计划和测试。</span><span class="sxs-lookup"><span data-stu-id="d6423-107">Note that there are many external dependencies and connectivity conditions that could be impacted by disabling TLS 1.0/1.1, so extensive planning and testing is warranted.</span></span>

## <a name="in-this-article"></a><span data-ttu-id="d6423-108">在本文中</span><span class="sxs-lookup"><span data-stu-id="d6423-108">In this article</span></span>

- [<span data-ttu-id="d6423-109">背景和作用域</span><span class="sxs-lookup"><span data-stu-id="d6423-109">Background and scope</span></span>](#background)
- [<span data-ttu-id="d6423-110">先决条件和过程</span><span class="sxs-lookup"><span data-stu-id="d6423-110">Prerequisites and process</span></span>](#prerequisites-and-process)
- [<span data-ttu-id="d6423-111">高级部署方案</span><span class="sxs-lookup"><span data-stu-id="d6423-111">Advanced deployment scenarios</span></span>](#advanced-deployment-scenarios)

## <a name="background"></a><span data-ttu-id="d6423-112">背景</span><span class="sxs-lookup"><span data-stu-id="d6423-112">Background</span></span>

<span data-ttu-id="d6423-113">提供 TLS 1.0 和1.1 的主要驱动程序对本地 Skype for business 服务器禁用支持是支付卡行业（PCI）安全标准委员会和联邦信息处理标准的要求。</span><span class="sxs-lookup"><span data-stu-id="d6423-113">The primary drivers for providing TLS 1.0 and 1.1 disable support for Skype for Business Server On-Premises are Payment Card Industry (PCI) Security Standards Council and Federal Information Processing Standards requirements.</span></span> <span data-ttu-id="d6423-114">可[在此处](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls)找到有关 PCI 要求的详细信息。</span><span class="sxs-lookup"><span data-stu-id="d6423-114">More information for PCI requirements can be found [here](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls).</span></span>  <span data-ttu-id="d6423-115">Microsoft 无法提供有关您的组织是否需要遵守这些或其他要求的指导。</span><span class="sxs-lookup"><span data-stu-id="d6423-115">Microsoft cannot provide guidance on whether or not your organization is required to adhere to these or other requirements.</span></span> <span data-ttu-id="d6423-116">你必须确定是否需要在你的环境中禁用 TLS 1.0 和/或1.1。</span><span class="sxs-lookup"><span data-stu-id="d6423-116">You must determine if it is required for you to disable TLS 1.0 and/or 1.1 in your environments.</span></span>

<span data-ttu-id="d6423-117">Microsoft 在[此处](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/)提供了有关 TLS 的白皮书，我们还建议在此[Exchange 博客](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)中提供的后台阅读功能。</span><span class="sxs-lookup"><span data-stu-id="d6423-117">Microsoft has produced a white paper on TLS available [here](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/), and we also recommend the background reading available in this [Exchange blog](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/).</span></span>

## <a name="supportability-scope"></a><span data-ttu-id="d6423-118">支持范围</span><span class="sxs-lookup"><span data-stu-id="d6423-118">Supportability Scope</span></span>

<span data-ttu-id="d6423-119">*范围*指的是可支持性边界。</span><span class="sxs-lookup"><span data-stu-id="d6423-119">*Scope* refers to supportability boundaries.</span></span> <span data-ttu-id="d6423-120">*经完全测试和支持*意味着我们完全支持并针对列出的产品版本对 TLS 1.0 和1.1 的禁用进行了测试。</span><span class="sxs-lookup"><span data-stu-id="d6423-120">*Fully tested and supported* means we fully support and have tested disabling of TLS 1.0 and 1.1 for the listed product versions.</span></span> <span data-ttu-id="d6423-121">*目前正在调查*的是，这一点是指我们正在积极调查如何将这些产品带入 TLS 禁用支持的范围内。</span><span class="sxs-lookup"><span data-stu-id="d6423-121">*Currently being investigated* means just that; we are actively investigating bringing these products into scope for TLS disable support.</span></span> <span data-ttu-id="d6423-122">*超出范围*意味着这些产品版本不支持禁用 TLS 1.0 或1.1，并且将无法正常工作，但所注明的例外情况除外。</span><span class="sxs-lookup"><span data-stu-id="d6423-122">*Out of scope* means these product versions do not support disabling TLS 1.0 or 1.1 and will not work, with noted exceptions.</span></span>

### <a name="fully-tested-and-supported-servers"></a><span data-ttu-id="d6423-123">经过充分测试和支持的服务器</span><span class="sxs-lookup"><span data-stu-id="d6423-123">Fully tested and supported servers</span></span>

- <span data-ttu-id="d6423-124">Skype for Business Server 2019 CU1 17.0.2046.123 （6月2019日）或更高版本</span><span class="sxs-lookup"><span data-stu-id="d6423-124">Skype for Business Server 2019 CU1 17.0.2046.123 (June 2019) or higher</span></span>
- <span data-ttu-id="d6423-125">Skype for Business Server 2015 CU9 6.0.9319.548 （五月2019）或更高版本在 Windows Server 2012 上（有 KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in)或取代更新），2012 R2 或2016。</span><span class="sxs-lookup"><span data-stu-id="d6423-125">Skype for Business Server 2015 CU9 6.0.9319.548 (May 2019) or higher on Windows Server 2012 (with KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) or superseding update), 2012 R2 or 2016.</span></span>
- <span data-ttu-id="d6423-126">就地升级的 Skype for business Server 2015，CU9 6.0.9319.548 （五月2019）或更高版本的 Windows Server 2008 R2、2012（包含 KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in)或取代更新）或 2012 r2。</span><span class="sxs-lookup"><span data-stu-id="d6423-126">In-place Upgraded Skype for Business Server 2015, with CU9 6.0.9319.548 (May 2019) or higher on Windows Server 2008 R2, 2012 (with KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) or superseding update), or 2012 R2.</span></span>
- <span data-ttu-id="d6423-127">Exchange 连接和 Outlook Web App 与 Exchange Server 2010 SP3 RU19 或更高版本，请参阅[此处](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)的指南</span><span class="sxs-lookup"><span data-stu-id="d6423-127">Exchange Connectivity and Outlook Web App with Exchange Server 2010 SP3 RU19 or higher, guidance [here](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)</span></span>
- <span data-ttu-id="d6423-128">Survivable 分支装置（SBA）使用 Skype for Business Server 2015 CU6 HF2 或更高版本（请向您的供应商确认他们已将 appropiate 更新打包，并已为你的设备提供）</span><span class="sxs-lookup"><span data-stu-id="d6423-128">Survivable Branch Appliance (SBA) with Skype for Business Server 2015 CU6 HF2 or higher (confirm with your vendor that they packaged the appropiate updates and have been made available for your appliance)</span></span>
- <span data-ttu-id="d6423-129">Survivable 分支服务器（SBS）与 Skype for Business Server 2015 CU6 HF2 或更高版本</span><span class="sxs-lookup"><span data-stu-id="d6423-129">Survivable Branch Server (SBS) with Skype for Business Server 2015 CU6 HF2 or higher</span></span>
- <span data-ttu-id="d6423-130">Lync Server 2013 **Edge 角色**，这是因为 edge 角色不依赖于 Windows Fabric 1.0。</span><span class="sxs-lookup"><span data-stu-id="d6423-130">Lync Server 2013 **Edge Role Only**, this is because Edge role does not have a dependency on Windows Fabric 1.0.</span></span>

### <a name="fully-tested-and-supported-clients"></a><span data-ttu-id="d6423-131">经过充分测试和支持的客户端</span><span class="sxs-lookup"><span data-stu-id="d6423-131">Fully tested and supported clients</span></span>

- <span data-ttu-id="d6423-132">Lync 2013 （Skype for Business）桌面客户端、MSI 和 C2R，包括基本[15.0.5023.1000 或更高版本](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)</span><span class="sxs-lookup"><span data-stu-id="d6423-132">Lync 2013 (Skype for Business) Desktop Client, MSI and C2R, including Basic [15.0.5023.1000 or higher](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)</span></span>
- <span data-ttu-id="d6423-133">Skype for Business 2016 桌面客户端、MSI [16.0.4678.1000 或更高版本](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323)，包括基本</span><span class="sxs-lookup"><span data-stu-id="d6423-133">Skype for Business 2016 Desktop Client, MSI [16.0.4678.1000 or higher](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323), including Basic</span></span>
- <span data-ttu-id="d6423-134">Skype for Business 2016 单击以运行时需要[2018 年4月](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus)更新：</span><span class="sxs-lookup"><span data-stu-id="d6423-134">Skype for Business 2016 Click to Run Require the [April 2018](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) Updates:</span></span> 
    - <span data-ttu-id="d6423-135">每月和半年度目标、16\.0\.9126\.2152 或更高版本</span><span class="sxs-lookup"><span data-stu-id="d6423-135">Monthly and Semi-Annual Targeted, 16\.0\.9126\.2152 or higher</span></span>
    - <span data-ttu-id="d6423-136">半年和延期频道，16\.0\.8431\.2242 或更高版本</span><span class="sxs-lookup"><span data-stu-id="d6423-136">Semi-Annual and Deferred Channel, 16\.0\.8431\.2242 or higher</span></span>
- <span data-ttu-id="d6423-137">Mac 16.15 或更高版本上的 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="d6423-137">Skype for Business on Mac 16.15 or higher</span></span>
- <span data-ttu-id="d6423-138">适用于 iOS 和 Android 6.19 或更高版本的 Skype for business</span><span class="sxs-lookup"><span data-stu-id="d6423-138">Skype for Business for iOS and Android 6.19 or higher</span></span>
- <span data-ttu-id="d6423-139">Microsoft 团队聊天室（以前称为 Skype 会议室 System V2 SRS V2）4.0.64.0 （2018年12月）或更高版本</span><span class="sxs-lookup"><span data-stu-id="d6423-139">Microsoft Teams Rooms (previously known as Skype Room System V2 SRS V2) 4.0.64.0 (December 2018) or higher</span></span>
- <span data-ttu-id="d6423-140">基于 KB4499162 （可能是2019、操作系统内部版本15063.1835）或更高版本的 Team edition 的 Surface Hub 更新</span><span class="sxs-lookup"><span data-stu-id="d6423-140">Surface Hub update for Team edition based on KB4499162 (May 2019, OS Build 15063.1835) or higher</span></span>
- <span data-ttu-id="d6423-141">Skype Web App 2015 CU6 HF2 或更高版本（随服务器一起提供）</span><span class="sxs-lookup"><span data-stu-id="d6423-141">Skype Web App 2015 CU6 HF2 or higher (ships with Server)</span></span>

### <a name="currently-being-investigated"></a><span data-ttu-id="d6423-142">当前正在调查</span><span class="sxs-lookup"><span data-stu-id="d6423-142">Currently being investigated</span></span>

- <span data-ttu-id="d6423-143">通话质量仪表板（TLS 1.0 后的全新安装，1.1 已禁用，请参阅下文） \*</span><span class="sxs-lookup"><span data-stu-id="d6423-143">Call Quality Dashboard (new install after TLS 1.0, 1.1 have been disabled, see below)\*</span></span>
 
### <a name="out-of-scope"></a><span data-ttu-id="d6423-144">超出范围</span><span class="sxs-lookup"><span data-stu-id="d6423-144">Out of scope</span></span>

<span data-ttu-id="d6423-145">除非另有说明，否则以下产品不在 TLS 1.0/1.1 禁用支持的范围内，在禁用 TLS 1.0 和1.1 的环境中将不起作用。</span><span class="sxs-lookup"><span data-stu-id="d6423-145">Except where noted, the following products are not in scope for TLS 1.0/1.1 disable support and will not function in an environment where TLS 1.0 and 1.1 have been disabled.</span></span> <span data-ttu-id="d6423-146">这意味着：如果仍在使用超出范围的服务器或客户，则必须在 Skype for Business Server 内部部署中的任意位置禁用 TLS 1.0/1.1，否则必须更新或删除它们。</span><span class="sxs-lookup"><span data-stu-id="d6423-146">What this means: if you still utilize out-of-scope servers or clients, you must update or remove these if you need to disable TLS 1.0/1.1 anywhere in your Skype for Business Server on-premises deployment.</span></span>

- <span data-ttu-id="d6423-147">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d6423-147">Lync Server 2013</span></span>
- <span data-ttu-id="d6423-148">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="d6423-148">Lync Server 2010</span></span>
- <span data-ttu-id="d6423-149">Windows Server 2008 或更低</span><span class="sxs-lookup"><span data-stu-id="d6423-149">Windows Server 2008 or lower</span></span>
- <span data-ttu-id="d6423-150">Lync for Mac 2011</span><span class="sxs-lookup"><span data-stu-id="d6423-150">Lync for Mac 2011</span></span>
- <span data-ttu-id="d6423-151">适用于移动版的 Lync 2013-iOS、iPad、Android 或 Windows Phone</span><span class="sxs-lookup"><span data-stu-id="d6423-151">Lync 2013 for Mobile - iOS, iPad, Android or Windows Phone</span></span>
- <span data-ttu-id="d6423-152">Lync "MX" Windows 应用商店客户端</span><span class="sxs-lookup"><span data-stu-id="d6423-152">Lync "MX" Windows Store client</span></span>
- <span data-ttu-id="d6423-153">Lync 会议室系统（a.k.a。</span><span class="sxs-lookup"><span data-stu-id="d6423-153">Lync Room System (a.k.a.</span></span> <span data-ttu-id="d6423-154">SRSv1).</span><span class="sxs-lookup"><span data-stu-id="d6423-154">SRSv1).</span></span> <span data-ttu-id="d6423-155">LRS 已达到2018年10月9日的支持结束，并且不会更新为支持 TLS 1.2。</span><span class="sxs-lookup"><span data-stu-id="d6423-155">LRS reached end of support on October 9, 2018 and will not be updated to support TLS 1.2.</span></span>
- <span data-ttu-id="d6423-156">所有 Lync 2010 客户端</span><span class="sxs-lookup"><span data-stu-id="d6423-156">All Lync 2010 clients</span></span>
- <span data-ttu-id="d6423-157">Lync Phone Edition-更新的[指南。](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035)</span><span class="sxs-lookup"><span data-stu-id="d6423-157">Lync Phone Edition - updated guidance [here](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035).</span></span>
- <span data-ttu-id="d6423-158">基于2013的 Survivable 分支装置（SBA）或 Survivable 分支服务器（SBS）</span><span class="sxs-lookup"><span data-stu-id="d6423-158">2013 based Survivable Branch Appliance (SBA) or Survivable Branch Server (SBS)</span></span>
- <span data-ttu-id="d6423-159">云连接器版（CCE）</span><span class="sxs-lookup"><span data-stu-id="d6423-159">Cloud Connector Edition (CCE)</span></span>
- <span data-ttu-id="d6423-160">Windows Phone 版 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="d6423-160">Skype for Business for Windows Phone</span></span>

### <a name="exceptions"></a><span data-ttu-id="d6423-161">异常</span><span class="sxs-lookup"><span data-stu-id="d6423-161">Exceptions</span></span>

#### <a name="lync-server-2013"></a><span data-ttu-id="d6423-162">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d6423-162">Lync Server 2013</span></span>

<span data-ttu-id="d6423-163">Lync Server 2013 依赖于 Windows Fabric 版本1.0。</span><span class="sxs-lookup"><span data-stu-id="d6423-163">Lync Server 2013 takes a dependency on Windows Fabric version 1.0.</span></span>  <span data-ttu-id="d6423-164">在 Lync Server 2013 的设计阶段，为其引人注目的和新的分布式体系结构选择了 Windows Fabric 1.0 以提供复制、高可用性和容错。</span><span class="sxs-lookup"><span data-stu-id="d6423-164">In the design phase for Lync Server 2013, Windows Fabric 1.0 was chosen for its compelling and new distributed architecture to provide replication, high availability, and fault tolerance.</span></span>  <span data-ttu-id="d6423-165">随着时间的推移，Skype for business 服务器和 Windows Fabric 在后续版本中大大提高了这种联合体系结构的显著重新设计。</span><span class="sxs-lookup"><span data-stu-id="d6423-165">Over time, both Skype for Business Server and Windows Fabric have greatly improved this joint architecture with significant re-design in subsequent versions.</span></span>  <span data-ttu-id="d6423-166">例如，当前 Skype for Business 2015 服务器使用的是 Windows Fabric 3.0。</span><span class="sxs-lookup"><span data-stu-id="d6423-166">Current Skype for Business 2015 Server uses Windows Fabric 3.0, for example.</span></span>

<span data-ttu-id="d6423-167">很遗憾，Windows Fabric 1.0 不**支持 TLS 1.2。 但是，我们将更新 Lync Server 2013 以与 TLS 1.2 配合工作**。</span><span class="sxs-lookup"><span data-stu-id="d6423-167">Unfortunately, Windows Fabric 1.0 **does not support TLS 1.2.  However, we will be updating Lync Server 2013 to work with TLS 1.2**.</span></span> <span data-ttu-id="d6423-168">这将进入 Lync Server 2013 的下一个累积更新。</span><span class="sxs-lookup"><span data-stu-id="d6423-168">This will be coming in the next Cumulative Update for Lync Server 2013.</span></span>  <span data-ttu-id="d6423-169">我们提供了 TLS 1.2 支持以启用共存、迁移、联盟和混合方案。</span><span class="sxs-lookup"><span data-stu-id="d6423-169">We're providing TLS 1.2 support to enable co-existence, migration, federation, and hybrid scenarios.</span></span>

<span data-ttu-id="d6423-170">如果你的组织需要禁用 TLS 1.0 和1.1，并且你当前使用的是 Lync Server 2013，我们建议你开始计划过程，但你可能需要就地升级或并行迁移（新的池、移动用户）到 Skype for Business企业服务器2015或更高版本。</span><span class="sxs-lookup"><span data-stu-id="d6423-170">If your organization is required to disable TLS 1.0 and 1.1, and you currently use Lync Server 2013, we recommend you begin your planning process, with the possibility you may have to In-place upgrade or Side-by-Side migrate (new pools, move users) to Skype for Business Server 2015 or higher.</span></span>  <span data-ttu-id="d6423-171">或者，您可能希望加速迁移到 Skype for business Online。</span><span class="sxs-lookup"><span data-stu-id="d6423-171">Or you may want to accelerate migration to Skype for Business Online.</span></span>

#### <a name="call-quality-dashboard"></a><span data-ttu-id="d6423-172">呼叫质量仪表板</span><span class="sxs-lookup"><span data-stu-id="d6423-172">Call Quality Dashboard</span></span>

<span data-ttu-id="d6423-173">在全新安装期间，本地呼叫质量仪表板当前对 TLS 1.0 有依赖性（首次安装到本地环境）。</span><span class="sxs-lookup"><span data-stu-id="d6423-173">On-Premises Call Quality Dashboard currently has a dependency on TLS 1.0 during new install (first time installing into your On-Premises environments).</span></span>  <span data-ttu-id="d6423-174">我们目前正在调查此问题，并计划在不久的将来发布修补程序。</span><span class="sxs-lookup"><span data-stu-id="d6423-174">We are currently investigating this issue and plan to release a fix in the near future.</span></span>  <span data-ttu-id="d6423-175">如果你计划安装 CQD 并禁用 TLS 1.0，我们建议你先完成 CQD 安装，然后再继续 TLS 1.0 禁用。</span><span class="sxs-lookup"><span data-stu-id="d6423-175">If you are planning to install CQD and also disable TLS 1.0, we recommend that you complete CQD installation first, and then proceed with TLS 1.0 disabling.</span></span>

#### <a name="third-party-devices"></a><span data-ttu-id="d6423-176">第三方设备</span><span class="sxs-lookup"><span data-stu-id="d6423-176">Third-party devices</span></span>

<span data-ttu-id="d6423-177">在第三方设备（如3PIP 电话、视频会议、反向代理和负载平衡器）上，确保验证 TLS 1.2 可支持性，仔细测试，如果需要，请与供应商联系。</span><span class="sxs-lookup"><span data-stu-id="d6423-177">On third-party devices such as 3PIP phones, Video conferencing, Reverse Proxies and Load Balancers, be sure to validate TLS 1.2 supportability, test carefully, and contact the vendor if needed.</span></span>

### <a name="federation-considerations-when-disabling-tls-1011-on-edge-servers"></a><span data-ttu-id="d6423-178">在边缘服务器上禁用 TLS 1.0/1.1 时的联合注意事项</span><span class="sxs-lookup"><span data-stu-id="d6423-178">Federation considerations when disabling TLS 1.0/1.1 on Edge servers</span></span>

<span data-ttu-id="d6423-179">您必须仔细规划并考虑在边缘服务器上禁用 TLS 1.0/1.1 的影响。</span><span class="sxs-lookup"><span data-stu-id="d6423-179">You must carefully plan for and consider the impact of disabling TLS 1.0/1.1 on your Edge servers.</span></span>  <span data-ttu-id="d6423-180">一旦 TLS 1.0 和1.1 被禁用，你可能会发现其他组织无法再与你的组织联盟。</span><span class="sxs-lookup"><span data-stu-id="d6423-180">Once TLS 1.0 and 1.1 are disabled, you may find that other organizations are no longer be able to federate with your organization.</span></span>

<span data-ttu-id="d6423-181">你可以选择将 TLS 1.0/1.1 保留在 Edge 服务器上，以保持与非修补（SfB 2015、Lync 2013）或较早（2010）外部系统的向后兼容性。</span><span class="sxs-lookup"><span data-stu-id="d6423-181">You may opt to keep TLS 1.0/1.1 enabled on your Edge servers to maintain backward compatibility with non-patched (SfB 2015, Lync 2013) or older (2010) external systems.</span></span>

<span data-ttu-id="d6423-182">Microsoft 无法提供有关您的 Edge 网络（或任何网络）是否属于 PCI 标准的建议或建议。必须由单个公司确定。</span><span class="sxs-lookup"><span data-stu-id="d6423-182">Microsoft cannot provide advice or recommendations on whether or not your Edge network (or any network) falls under PCI standard; that must be determined by the individual company.</span></span>

<span data-ttu-id="d6423-183">Skype for Business Online 目前支持 TLS 1.2，因此不需要与在线的混合/联盟产生任何影响。</span><span class="sxs-lookup"><span data-stu-id="d6423-183">Skype for Business Online is capable of TLS 1.2 today, so no impact to Hybrid/Federation with Online is expected.</span></span>

<span data-ttu-id="d6423-184">PIC （公共 IM 连接）到 Skype 消费者服务：我们不希望禁用 TLS 1.0/1.1 来影响[Skype 连接](../../deploy/deploy-skype-connectivity.md);Microsoft PIC 网关已经支持支持 TLS 1.2。</span><span class="sxs-lookup"><span data-stu-id="d6423-184">PIC (Public IM Connectivity) to Skype Consumer service: We do not expect disabling TLS 1.0/1.1 to impact [Skype Connectivity](../../deploy/deploy-skype-connectivity.md); Microsoft PIC Gateways are already TLS 1.2 capable.</span></span>

## <a name="prerequisites-and-process"></a><span data-ttu-id="d6423-185">先决条件和过程</span><span class="sxs-lookup"><span data-stu-id="d6423-185">Prerequisites and process</span></span>

<span data-ttu-id="d6423-186">除了上面提到的情况，一旦 TLS 1.0 和1.1 禁用了超出范围的服务器，客户和设备将继续正常运行，或者完全正常。</span><span class="sxs-lookup"><span data-stu-id="d6423-186">Except where noted above, once TLS 1.0 and 1.1 are disabled out-of-scope servers, clients and devices will longer function properly, or at all.</span></span> <span data-ttu-id="d6423-187">这可能意味着你需要暂停并等待来自 Microsoft 的更新指南。</span><span class="sxs-lookup"><span data-stu-id="d6423-187">This may mean you need to pause and wait for updated guidance from Microsoft.</span></span> <span data-ttu-id="d6423-188">一旦您满意满足所有要求并制定一个计划来解决缺口，请继续操作。</span><span class="sxs-lookup"><span data-stu-id="d6423-188">Once you are satisfied that you meet all requirements and have a plan to address gaps, proceed.</span></span>

<span data-ttu-id="d6423-189">在较高级别，虽然 Skype for business Server 2019 已准备好进行安装过程，但 Skype for business Server 2015 将要求你安装 CU9、将必备更新应用到 .NET 和 SQL、部署必备注册表项以及最后一个单独的一轮操作系统配置更新（例如，通过注册表文件导入禁用 TLS 1.0 和1.1）。</span><span class="sxs-lookup"><span data-stu-id="d6423-189">At a high level, while Skype for Business Server 2019 is ready for procedure at install, Skype for Business Server 2015 will require that you install CU9, applying pre-requisite updates to .NET and SQL, deploying prerequisite registry keys, and finally a separate round of OS configuration updates (i.e. disabling TLS 1.0 and 1.1 via registry file import).</span></span> <span data-ttu-id="d6423-190">在你环境中的任何服务器上禁用 TLS 1.0 和1.1 之前，必须先完成安装所有先决条件（包括 Skype for Business Server 2015 CU6 HF2），这一点至关重要。</span><span class="sxs-lookup"><span data-stu-id="d6423-190">It is critically important that you complete installation of all prerequisites, including Skype for Business Server 2015 CU6 HF2, prior to disabling TLS 1.0 and 1.1 on any server in your environment.</span></span> <span data-ttu-id="d6423-191">每个 Skype for Business 服务器（包括边缘角色和 SQL Backends）都需要更新。</span><span class="sxs-lookup"><span data-stu-id="d6423-191">Every Skype for Business server, including Edge role and SQL Backends, requires the updates.</span></span> <span data-ttu-id="d6423-192">还要确保所有受支持的（范围内）客户端已更新为所需的最低版本。</span><span class="sxs-lookup"><span data-stu-id="d6423-192">Also ensure that all supported (in-scope) clients have been updated to the required minimum versions.</span></span> <span data-ttu-id="d6423-193">不要忘记更新管理工作站。</span><span class="sxs-lookup"><span data-stu-id="d6423-193">Don’t forget to update management workstations as well.</span></span>

<span data-ttu-id="d6423-194">我们希望按照通常的 "内部" 操作顺序来升级 Skype for Business 服务器。</span><span class="sxs-lookup"><span data-stu-id="d6423-194">We want to follow the usual order of operations of "inside out" for upgrading Skype for Business servers.</span></span> <span data-ttu-id="d6423-195">按照正常方式处理控制器池、持久聊天和配对的池。</span><span class="sxs-lookup"><span data-stu-id="d6423-195">Treat Director pools, Persistent chat, and Paired Pools in the same manner you normally would.</span></span> <span data-ttu-id="d6423-196">升级的订单和方法在[此处](topology.md)和[此处](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)介绍。</span><span class="sxs-lookup"><span data-stu-id="d6423-196">Order and methods for upgrade are covered [here](topology.md) and [here](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span>

### <a name="high-level-process"></a><span data-ttu-id="d6423-197">高级别流程</span><span class="sxs-lookup"><span data-stu-id="d6423-197">High-level process</span></span>

1. <span data-ttu-id="d6423-198">在配置生产服务器之前测试实验室中的所有步骤。</span><span class="sxs-lookup"><span data-stu-id="d6423-198">Test all steps in your lab prior to configuring production servers.</span></span>
2. <span data-ttu-id="d6423-199">在要更新的每台服务器和每台服务器上备份和保留导出注册表的副本。</span><span class="sxs-lookup"><span data-stu-id="d6423-199">Back up and preserve a copy of exported registry on each and every individual server to be updated.</span></span> <span data-ttu-id="d6423-200">不能在服务器之间共享注册表;它们包含基于计算机的唯一密钥。</span><span class="sxs-lookup"><span data-stu-id="d6423-200">You cannot share registries between servers; they contain unique machine-based keys.</span></span>
3. <span data-ttu-id="d6423-201">将所有 Skype for business 2015 服务器升级到 CU9 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="d6423-201">Upgrade all Skype for Business 2015 servers to CU9 or higher.</span></span> <span data-ttu-id="d6423-202">对于 Skype for business Server 2019，请升级到 CU1 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="d6423-202">For Skype for Business Server 2019, upgrade to CU1 or higher.</span></span>
4. <span data-ttu-id="d6423-203">将所有先决条件安装到所有服务器。</span><span class="sxs-lookup"><span data-stu-id="d6423-203">Install all prerequisites to all servers.</span></span>
5. <span data-ttu-id="d6423-204">部署必备注册表项。</span><span class="sxs-lookup"><span data-stu-id="d6423-204">Deploy prerequisite registry keys.</span></span>
6. <span data-ttu-id="d6423-205">确保更新所有范围内客户端。</span><span class="sxs-lookup"><span data-stu-id="d6423-205">Ensure that all in-scope clients are updated.</span></span>
7. <span data-ttu-id="d6423-206">通过注册表导入禁用 TLS 1.0 和1.1。</span><span class="sxs-lookup"><span data-stu-id="d6423-206">Disable TLS 1.0 and 1.1 via registry import.</span></span>
8. <span data-ttu-id="d6423-207">验证工作负荷是否按预期运行。</span><span class="sxs-lookup"><span data-stu-id="d6423-207">Validate that workloads are functioning as expected.</span></span>
    - <span data-ttu-id="d6423-208">如果遇到问题、排除和解决问题，或者</span><span class="sxs-lookup"><span data-stu-id="d6423-208">If problems are encountered, troubleshoot and resolve, or</span></span>
    - <span data-ttu-id="d6423-209">从步骤2还原注册表以重新启用 TLS 1.0 和1。1</span><span class="sxs-lookup"><span data-stu-id="d6423-209">Restore registry from step 2 to re-enable TLS 1.0 and 1.1</span></span>
9. <span data-ttu-id="d6423-210">验证是否仅使用 TLS 1.2。</span><span class="sxs-lookup"><span data-stu-id="d6423-210">Validate that only TLS 1.2 is being used.</span></span>

### <a name="install-prerequisites-to-all-servers"></a><span data-ttu-id="d6423-211">将先决条件安装到所有服务器</span><span class="sxs-lookup"><span data-stu-id="d6423-211">Install prerequisites to all servers</span></span>

<span data-ttu-id="d6423-212">在开始在 Skype for Business Server 2015 部署中的操作系统级别禁用 TLS 1.0 和1.1 之前，需要进行广泛的依赖项更新。</span><span class="sxs-lookup"><span data-stu-id="d6423-212">Extensive dependency updating is required before you begin to disable TLS 1.0 and 1.1 at the operating system level in your Skype for Business Server 2015 deployments.</span></span> <span data-ttu-id="d6423-213">以下是可支持 TLS 1.2 的最低版本。</span><span class="sxs-lookup"><span data-stu-id="d6423-213">The following are the minimum versions that can support TLS 1.2.</span></span> <span data-ttu-id="d6423-214">在开始禁用 TLS 1.0 和1.1 之前，在你的环境中的每个 Skype for Business 服务器上部署所有先决条件更新。</span><span class="sxs-lookup"><span data-stu-id="d6423-214">Deploy all prerequisite updates across every Skype for Business server in your environment before you begin disabling TLS 1.0 and 1.1.</span></span>

- <span data-ttu-id="d6423-215">Skype for Business Server 2015 CU9 6.0.9319.548 （五月2019）或更高版本</span><span class="sxs-lookup"><span data-stu-id="d6423-215">Skype for Business Server 2015 CU9 6.0.9319.548 (May 2019) or higher</span></span>
- <span data-ttu-id="d6423-216">[.Net Framework 4.7](https://www.microsoft.com/download/details.aspx?id=55167)或更高版本在注册表中启用了 SchUseStrongCrypto （如下所示）</span><span class="sxs-lookup"><span data-stu-id="d6423-216">[.NET Framework 4.7](https://www.microsoft.com/download/details.aspx?id=55167) or higher with SchUseStrongCrypto enabled in the registry (provided below)</span></span>
- <span data-ttu-id="d6423-217">必须在所有 Skype for Business 2015 服务器和 backends 上更新 SQL。</span><span class="sxs-lookup"><span data-stu-id="d6423-217">SQL must be updated on all Skype for Business 2015 servers and backends.</span></span> <span data-ttu-id="d6423-218">首先更新企业版池 SQL Backends，然后再更新其各自的 FEs。</span><span class="sxs-lookup"><span data-stu-id="d6423-218">Update Enterprise Edition Pool SQL Backends first, then their respective FEs.</span></span> 
    - <span data-ttu-id="d6423-219">[SQL Server 2014 SP1 + CU5](https://support.microsoft.com/help/3130926)或更高版本/sql SERVER 2012 SP2 + CU16 或更高版本/ [SQL server 2014 RTM + CU12](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014)或更高版本/sql server 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="d6423-219">[SQL Server 2014 SP1 + CU5](https://support.microsoft.com/help/3130926), or higher / SQL Server 2012 SP2 + CU16 or higher / [SQL Server 2014 RTM + CU12](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014), or higher / SQL Server 2014 SP2</span></span>
     - [<span data-ttu-id="d6423-220">SQL server 的 SQL Server Native Client 2012</span><span class="sxs-lookup"><span data-stu-id="d6423-220">SQL Server Native Client for SQL Server 2012</span></span>](https://www.microsoft.com/download/details.aspx?id=50402)
     - <span data-ttu-id="d6423-221">[MICROSOFT ODBC Driver 11 FOR SQL Server](https://www.microsoft.com/download/details.aspx?id=36434)或更高版本</span><span class="sxs-lookup"><span data-stu-id="d6423-221">[Microsoft ODBC Driver 11 for SQL Server](https://www.microsoft.com/download/details.aspx?id=36434), or higher</span></span>
     - [<span data-ttu-id="d6423-222">SQL Server 2014 SP2 的共享管理对象</span><span class="sxs-lookup"><span data-stu-id="d6423-222">Shared Management Objects for SQL Server 2014 SP2</span></span>](https://www.microsoft.com/download/details.aspx?id=53164)
     - [<span data-ttu-id="d6423-223">SQL server 2014 SP2 的 SQLSysClrTypes</span><span class="sxs-lookup"><span data-stu-id="d6423-223">SQLSysClrTypes for SQL server 2014 SP2</span></span>](https://www.microsoft.com/download/details.aspx?id=42295)

### <a name="basic-steps-to-install-pre-requisites-in-recommended-order-of-operations"></a><span data-ttu-id="d6423-224">安装先决条件的基本步骤，以推荐的操作顺序</span><span class="sxs-lookup"><span data-stu-id="d6423-224">Basic steps to install pre-requisites, in recommended order of operations</span></span>

1. <span data-ttu-id="d6423-225">将 Skype for business Server CU9 更新安装到所有服务器。</span><span class="sxs-lookup"><span data-stu-id="d6423-225">Install the Skype for Business Server CU9 update to all servers.</span></span> 
    1. <span data-ttu-id="d6423-226">使用更新程序安装对组件的更新。</span><span class="sxs-lookup"><span data-stu-id="d6423-226">Install the update to components using the updater.</span></span>
    2. <span data-ttu-id="d6423-227">根据已记录的过程更新数据库。</span><span class="sxs-lookup"><span data-stu-id="d6423-227">Update databases according to documented procedures.</span></span> <span data-ttu-id="d6423-228">对于 Skype for business 服务器2015，请参阅 KB [3061064](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)。</span><span class="sxs-lookup"><span data-stu-id="d6423-228">For Skype for Business Server 2015, see KB [3061064](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span>
    3. <span data-ttu-id="d6423-229">在迁移之前先验证部署中的产品功能，然后再进行任何其他更改。</span><span class="sxs-lookup"><span data-stu-id="d6423-229">Validate product functionality in the deployment prior to moving forward with any other changes.</span></span>
2. <span data-ttu-id="d6423-230">下载 .NET 4.7 脱机安装程序。</span><span class="sxs-lookup"><span data-stu-id="d6423-230">Download .NET 4.7 Offline Installer.</span></span> 
    1. <span data-ttu-id="d6423-231">参阅[https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)</span><span class="sxs-lookup"><span data-stu-id="d6423-231">Reference: [https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)</span></span>
    2. <span data-ttu-id="d6423-232">确保在前端服务器上停止 Skype for business Server 2015 服务。</span><span class="sxs-lookup"><span data-stu-id="d6423-232">Ensure that Skype for Business Server 2015 services are stopped on the Front End server.</span></span>
    3. <span data-ttu-id="d6423-233">参阅[https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)</span><span class="sxs-lookup"><span data-stu-id="d6423-233">Reference: [https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)</span></span>
    4. <span data-ttu-id="d6423-234">Ex （标准版）：```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="d6423-234">Ex (Standard Edition): ```Stop-CsWindowsService```</span></span>
    5. <span data-ttu-id="d6423-235">Ex （企业版）：```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="d6423-235">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    6. <span data-ttu-id="d6423-236">运行安装程序包。</span><span class="sxs-lookup"><span data-stu-id="d6423-236">Run the installer package.</span></span>
    7. <span data-ttu-id="d6423-237">重新启动服务器。</span><span class="sxs-lookup"><span data-stu-id="d6423-237">Reboot the server.</span></span>
3. <span data-ttu-id="d6423-238">在所有服务器上更新 SQL Express 2014。</span><span class="sxs-lookup"><span data-stu-id="d6423-238">Update SQL Express 2014 on all servers.</span></span> 
    1. <span data-ttu-id="d6423-239">参阅[https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span><span class="sxs-lookup"><span data-stu-id="d6423-239">Reference: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span></span>
    2. <span data-ttu-id="d6423-240">下载 SQL 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="d6423-240">Download SQL 2014 SP2</span></span> 
        - <span data-ttu-id="d6423-241">参阅[https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)</span><span class="sxs-lookup"><span data-stu-id="d6423-241">Reference: [https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)</span></span>
    3. <span data-ttu-id="d6423-242">将安装媒体复制到服务器上的文件夹（例如： C：\ 01_2014SqlSp2）</span><span class="sxs-lookup"><span data-stu-id="d6423-242">Copy the installation media to a folder on the server (Ex: C:\01_2014SqlSp2)</span></span>
    4. <span data-ttu-id="d6423-243">确保在前端服务器上停止 Skype for business 服务器2015服务</span><span class="sxs-lookup"><span data-stu-id="d6423-243">Ensure Skype for Business Server 2015 services are stopped on the Front End server</span></span> 
        - <span data-ttu-id="d6423-244">Ex （标准版）：```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="d6423-244">Ex (Standard Edition): ```Stop-CsWindowsService```</span></span>
        - <span data-ttu-id="d6423-245">Ex （企业版）：```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="d6423-245">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    5. <span data-ttu-id="d6423-246">打开管理员命令提示符，并升级所有已安装的组件和实例</span><span class="sxs-lookup"><span data-stu-id="d6423-246">Open an Admin Command Prompt, and upgrade all installed components and instances</span></span> 
        - <span data-ttu-id="d6423-247">示例： C：\ 01_2014SqlSp2 \SQLServer2014SP2-KB3171021-x64-ENU.exe/qs/IAcceptSQLServerLicenseTerms/Action = Patch/AllInstances</span><span class="sxs-lookup"><span data-stu-id="d6423-247">Example: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe /qs /IAcceptSQLServerLicenseTerms /Action=Patch /AllInstances</span></span>
4. <span data-ttu-id="d6423-248">更新 SQL Native 客户端。</span><span class="sxs-lookup"><span data-stu-id="d6423-248">Update SQL Native Client.</span></span> 
    1. <span data-ttu-id="d6423-249">参考： [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)。</span><span class="sxs-lookup"><span data-stu-id="d6423-249">Reference: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server).</span></span>
    2. <span data-ttu-id="d6423-250">下载自[https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)</span><span class="sxs-lookup"><span data-stu-id="d6423-250">Download from [https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)</span></span>
    3. <span data-ttu-id="d6423-251">确保前端服务器上的 Skype for business Server 2015 服务已停止。</span><span class="sxs-lookup"><span data-stu-id="d6423-251">Ensure Skype for Business Server 2015 services are stopped on the Front End server.</span></span> 
        - <span data-ttu-id="d6423-252">Ex （标准版）：```Stop-CsWindowsServices```</span><span class="sxs-lookup"><span data-stu-id="d6423-252">Ex (Standard Edition): ```Stop-CsWindowsServices```</span></span>
        - <span data-ttu-id="d6423-253">Ex （企业版）：```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="d6423-253">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    4. <span data-ttu-id="d6423-254">停止运行已安装的 SQL 实例</span><span class="sxs-lookup"><span data-stu-id="d6423-254">Stop the SQL instances installed from running</span></span> 
        - <span data-ttu-id="d6423-255">例如```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="d6423-255">Ex: ```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```</span></span>
        - <span data-ttu-id="d6423-256">例如```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="d6423-256">Ex: ```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```</span></span>
        - <span data-ttu-id="d6423-257">Ex （仅适用于标准版）：```Get-Service 'MSSQL$RTC' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="d6423-257">Ex (Standard Edition Only): ```Get-Service 'MSSQL$RTC' | Stop-Service```</span></span>
    5. <span data-ttu-id="d6423-258">安装该更新。</span><span class="sxs-lookup"><span data-stu-id="d6423-258">Install the update.</span></span>
5. <span data-ttu-id="d6423-259">更新 ODBC Driver 11 for SQL Server 以包括对 TLS 1.2 （KB [3135244](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)）的支持。</span><span class="sxs-lookup"><span data-stu-id="d6423-259">Update ODBC Driver 11 for SQL Server to include support for TLS 1.2 (KB [3135244](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)).</span></span>
    1. <span data-ttu-id="d6423-260">下载[SQL Server 的 ODBC 驱动程序 11-Windows](https://www.microsoft.com/download/confirmation.aspx?id=36434)。</span><span class="sxs-lookup"><span data-stu-id="d6423-260">Download [ODBC Driver 11 for SQL Server - Windows](https://www.microsoft.com/download/confirmation.aspx?id=36434).</span></span>
    2. <span data-ttu-id="d6423-261">确保在前端服务器上停止 Skype for business Server 2015 服务。</span><span class="sxs-lookup"><span data-stu-id="d6423-261">Ensure that Skype for Business Server 2015 services are stopped on the Front End server.</span></span>
        - <span data-ttu-id="d6423-262">示例（标准版）：```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="d6423-262">Example (Standard Edition): ```Stop-CsWindowsService```</span></span>
        - <span data-ttu-id="d6423-263">示例（企业版）：```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="d6423-263">Example (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    3. <span data-ttu-id="d6423-264">安装该更新。</span><span class="sxs-lookup"><span data-stu-id="d6423-264">Install the update.</span></span>
6. <span data-ttu-id="d6423-265">部署必备注册表项。</span><span class="sxs-lookup"><span data-stu-id="d6423-265">Deploy prerequisite registry keys.</span></span>

### <a name="pre-requisite-registry-keys"></a><span data-ttu-id="d6423-266">预必备注册表项</span><span class="sxs-lookup"><span data-stu-id="d6423-266">Pre-requisite registry keys</span></span>

<span data-ttu-id="d6423-267">将以下测试复制/粘贴到记事本中并重命名 TLSPreReq 或您选择的名称，然后导入：</span><span class="sxs-lookup"><span data-stu-id="d6423-267">Copy/paste the following test into Notepad and rename TLSPreReq.reg or a name of your choice, then import:</span></span>

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

<span data-ttu-id="d6423-268">对于适用于企业版池的 SQL 后端，应将先决条件和 TLS disable 视为任何 SQL 或 OS 更新。请参阅：[https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)</span><span class="sxs-lookup"><span data-stu-id="d6423-268">For SQL back ends for Enterprise Edition Pools, prerequisites and TLS disable should be treated as any SQL or OS updates would; refer to: [https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)</span></span>

<span data-ttu-id="d6423-269">虽然必备的应用程序和 TLS 禁用步骤都可以合并，但我们强烈建议在操作系统级别继续禁用 TLS 1.0 和1.1 之前应用所有先决条件。</span><span class="sxs-lookup"><span data-stu-id="d6423-269">While both the prerequisite application and TLS disabling steps can be combined, we strongly recommend all prerequisites be applied before proceeding with disabling of TLS 1.0 and 1.1 at the operating system level.</span></span> <span data-ttu-id="d6423-270">最佳做法做法是通过部署所有先决条件来准备环境、验证工作负荷是否正常运行和预期，然后在以后继续执行 TLS 1.0/1.1。</span><span class="sxs-lookup"><span data-stu-id="d6423-270">The best practice approach would be to prepare the environment by deploying all prerequisites, validating that workloads all function correctly and as expected, and then proceeding with TLS 1.0/1.1 disable at a later time.</span></span>

### <a name="disable-tls-10-and-11-via-registry-import"></a><span data-ttu-id="d6423-271">通过注册表导入禁用 TLS 1.0 和1。1</span><span class="sxs-lookup"><span data-stu-id="d6423-271">Disable TLS 1.0 and 1.1 via registry import</span></span>

<span data-ttu-id="d6423-272">在继续下一步操作之前，*请确保已完成所有先决条件和更新的 Skype for Business 服务器*。</span><span class="sxs-lookup"><span data-stu-id="d6423-272">Before you proceed with the next steps, *make sure you have completed all prerequisites and updated Skype for Business Servers*.</span></span>

<span data-ttu-id="d6423-273">将以下文本复制到记事本文件中，然后将其重命名**TLSDisable**：</span><span class="sxs-lookup"><span data-stu-id="d6423-273">Copy the following text into a Notepad file and rename it **TLSDisable.reg**:</span></span>

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

<span data-ttu-id="d6423-274">在要禁用 TLS 1.0 和1.1 的每台服务器上导入 .reg 文件。</span><span class="sxs-lookup"><span data-stu-id="d6423-274">Import the .reg file on each server you wish to disable TLS 1.0 and 1.1.</span></span> <span data-ttu-id="d6423-275">重新启动服务器。</span><span class="sxs-lookup"><span data-stu-id="d6423-275">Reboot the server.</span></span> <span data-ttu-id="d6423-276">服务重新联机后，移动到下一台服务器。</span><span class="sxs-lookup"><span data-stu-id="d6423-276">Once the services have come back online, move to the next server.</span></span> <span data-ttu-id="d6423-277">适用于企业版池的方法与进行任何操作系统更新所需的方法相同。</span><span class="sxs-lookup"><span data-stu-id="d6423-277">The approach for Enterprise Edition Pools is the same you would take for any OS update.</span></span>

<span data-ttu-id="d6423-278">你可能已注意到，我们执行的操作不仅仅是在此处禁用 TLS 1.0 和1.1。</span><span class="sxs-lookup"><span data-stu-id="d6423-278">You may have noticed we are doing more than just disabling TLS 1.0 and 1.1 here.</span></span> <span data-ttu-id="d6423-279">我们支持密码套件重新排序（如上所示）和禁用某些较旧的弱密码。</span><span class="sxs-lookup"><span data-stu-id="d6423-279">We are supporting Cipher Suite re-order (as shown above) and the disabling of some older weak ciphers.</span></span> <span data-ttu-id="d6423-280">这是我们首次在 Skype for Business 服务器上对 SCHANNEL 和加密 API 的这些更改的首次支持，请务必注意，这些更改是我们支持且现在已测试的唯一这些更改。</span><span class="sxs-lookup"><span data-stu-id="d6423-280">This is the first time we have officially supported these changes to SCHANNEL and Crypto API on Skype for Business Server, and it is important to note that these changes are the only ones we support and have tested at this time.</span></span> <span data-ttu-id="d6423-281">我们将来可能会考虑到其他配置，但目前请不要在你的实现中修改注册表导入文件。</span><span class="sxs-lookup"><span data-stu-id="d6423-281">We may consider additional configurations in the future, but for now, please do not modify the registry import file in your implementation.</span></span>

### <a name="validate-that-workloads-are-functioning-as-expected"></a><span data-ttu-id="d6423-282">验证工作负荷是否按预期运行</span><span class="sxs-lookup"><span data-stu-id="d6423-282">Validate that workloads are functioning as expected</span></span>

<span data-ttu-id="d6423-283">一旦 TLS 1.0 和1.1 在你的环境中被禁用，请确保你的所有主工作负荷正常运行，例如 IM & 状态、P2P 呼叫、企业语音等。</span><span class="sxs-lookup"><span data-stu-id="d6423-283">Once TLS 1.0 and 1.1 have been disabled in your environment, ensure that all your main workloads are functioning as expected, such as IM & Presence, P2P calls, Enterprise Voice, etc.</span></span>

<span data-ttu-id="d6423-284">**仅验证正在使用的 TLS 1。2**</span><span class="sxs-lookup"><span data-stu-id="d6423-284">**Validate only TLS 1.2 is being used**</span></span>

<span data-ttu-id="d6423-285">让你的安全团队执行新的 Skype for business 通信审核，以确保不再使用 TLS 1.0 和1.1 的较旧协议。</span><span class="sxs-lookup"><span data-stu-id="d6423-285">Have your Security Team perform a new audit of Skype for Business traffic to ensure that the older protocols TLS 1.0 and 1.1 are no longer in use.</span></span>

<span data-ttu-id="d6423-286">或者，你可以使用 Internet Explorer 从 Skype for Business Server 2015 中的 Skype for Business Server 测试 TLS 连接，然后禁用 TLS 1.0 和 TLS 1.1。</span><span class="sxs-lookup"><span data-stu-id="d6423-286">Alternatively, you can use Internet Explorer to test TLS connections to web services from Skype for Business Server 2015 after TLS 1.0 and TLS 1.1 have been disabled.</span></span>

1. <span data-ttu-id="d6423-287">启动 Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="d6423-287">Launch Internet Explorer.</span></span>
2. <span data-ttu-id="d6423-288">选择**工具** > "**Internet 选项**"。</span><span class="sxs-lookup"><span data-stu-id="d6423-288">Select **Tools** > **Internet Options**.</span></span>
3. <span data-ttu-id="d6423-289">选择 "**高级**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="d6423-289">Select the **Advanced** tab.</span></span>
4. <span data-ttu-id="d6423-290">在 "**设置**" 下，滚动到底部。</span><span class="sxs-lookup"><span data-stu-id="d6423-290">Under **Settings**, scroll to the bottom.</span></span>
5. <span data-ttu-id="d6423-291">验证 TLS 1.0、TLS 1.1 和 TLS 1.2 是否已启用。</span><span class="sxs-lookup"><span data-stu-id="d6423-291">Verify that TLS 1.0, TLS 1.1, and TLS 1.2 are enabled.</span></span>
6. <span data-ttu-id="d6423-292">浏览 SfB 2015 池的内部 Web 服务 URL （应成功连接）。</span><span class="sxs-lookup"><span data-stu-id="d6423-292">Browse the Internal Web Service URL of your SfB 2015 pool (should connect successfully).</span></span>
7. <span data-ttu-id="d6423-293">返回到 Internet Explorer 并禁用仅**使用 TLS 1.2**的选项。</span><span class="sxs-lookup"><span data-stu-id="d6423-293">Go back into Internet Explorer and disable the option to **Use TLS 1.2** only.</span></span>
8. <span data-ttu-id="d6423-294">再次浏览 SfB 2015 池的内部 Web 服务 URL （应该无法连接）。</span><span class="sxs-lookup"><span data-stu-id="d6423-294">Browse the Internal Web Service URL of your SfB 2015 pool again (should fail to connect).</span></span>

![Internet 选项](../../media/internet-options.jpg)

## <a name="advanced-deployment-scenarios"></a><span data-ttu-id="d6423-296">高级部署方案</span><span class="sxs-lookup"><span data-stu-id="d6423-296">Advanced deployment scenarios</span></span>

<span data-ttu-id="d6423-297">由于需要某些依赖项先决条件来支持 Skype for Business Ser 2015 中的 TLS 1.2，因此在禁用 TLS 1.0 和1.1 的任何系统上都将无法使用 RTM 介质进行安装。</span><span class="sxs-lookup"><span data-stu-id="d6423-297">Because some dependency prerequisites are required to support TLS 1.2 in Skype for Business Ser 2015, installing from RTM media will fail on any system where TLS 1.0 and 1.1 have been disabled.</span></span>

<span data-ttu-id="d6423-298">**在你的环境中禁用了 TLS 1.0 和1.1 后部署新的标准版服务器或企业版池。**</span><span class="sxs-lookup"><span data-stu-id="d6423-298">**Deploying New Standard Edition Servers or Enterprise Edition Pools once TLS 1.0 and 1.1 have been disabled in your environment.**</span></span>

<span data-ttu-id="d6423-299">**选项1：** 使用[SmartSetup](../../deploy/install/install-skype-for-business-server.md)。</span><span class="sxs-lookup"><span data-stu-id="d6423-299">**Option 1:** Use [SmartSetup](../../deploy/install/install-skype-for-business-server.md).</span></span> <span data-ttu-id="d6423-300">请注意，我们正在更新 SmartSetup 以在将来的 CU 中容纳已更新的 SQL 二进制文件，并将在将来更新本文。</span><span class="sxs-lookup"><span data-stu-id="d6423-300">Note that we are updating SmartSetup to accommodate the updated SQL binaries in a future CU, and will update this article in the future.</span></span>

<span data-ttu-id="d6423-301">**选项2：** 预安装本地 SQL 实例（RTCLOCAL 和 LYNCLOCAL）</span><span class="sxs-lookup"><span data-stu-id="d6423-301">**Option 2:** Pre-install local SQL instances (RTCLOCAL and LYNCLOCAL)</span></span>

1. <span data-ttu-id="d6423-302">下载 SQL Express 2014 SP2 （SQLEXPR_x64）并将其复制到 FE 上的本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="d6423-302">Download and copy SQL Express 2014 SP2 (SQLEXPR_x64.exe) to local folder on FE.</span></span> <span data-ttu-id="d6423-303">假设 "文件夹路径" <SQL_FOLDER_PATH>。</span><span class="sxs-lookup"><span data-stu-id="d6423-303">Let’s say folder path <SQL_FOLDER_PATH>.</span></span>
2. <span data-ttu-id="d6423-304">启动 PowerShell 或命令提示符并导航到 <SQL_FOLDER_PATH>。</span><span class="sxs-lookup"><span data-stu-id="d6423-304">Launch PowerShell or Command Prompt and navigate to <SQL_FOLDER_PATH>.</span></span>
3. <span data-ttu-id="d6423-305">通过运行下面的命令创建 RTCLOCAL SQL 实例。</span><span class="sxs-lookup"><span data-stu-id="d6423-305">Create the RTCLOCAL SQL instance by running the command below.</span></span> <span data-ttu-id="d6423-306">请等到 SQLEXPR_x64 完成，然后再继续操作：</span><span class="sxs-lookup"><span data-stu-id="d6423-306">Wait until SQLEXPR_x64.exe finishes before proceeding:</span></span>

    <span data-ttu-id="d6423-307">SQLEXPR_x64 .exe/Q/IACCEPTSQLSERVERLICENSETERMS/UPDATEENABLED = 0/HIDECONSOLE/ACTION = 安装/FEATURES = SQLEngine，Tools/INSTANCENAME = RTCLOCAL/TCPENABLED = 1/SQLSVCACCOUNT = "NT AUTHORITY\NetworkService"/SQLSYSADMINACCOUNTS = "Builtin\Administrators"/BROWSERSVCSTARTUPTYPE = "/AGTSVCACCOUNT" NTAUTHORITY\NetworkService = "/SQLSVCSTARTUPTYPE" Automati =</span><span class="sxs-lookup"><span data-stu-id="d6423-307">SQLEXPR_x64.exe  /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=RTCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automati</span></span>
1. <span data-ttu-id="d6423-308">通过运行下面的命令创建 LYNCLOCAL SQL 实例。</span><span class="sxs-lookup"><span data-stu-id="d6423-308">Create the LYNCLOCAL SQL instance by running the command below.</span></span> <span data-ttu-id="d6423-309">等到 SQLEXPR_x64 完成后再继续下一步操作：</span><span class="sxs-lookup"><span data-stu-id="d6423-309">Wait until SQLEXPR_x64.exe finishes before proceeding to the next step:</span></span>

    <span data-ttu-id="d6423-310">SQLEXPR_x64 .exe/Q/IACCEPTSQLSERVERLICENSETERMS/UPDATEENABLED = 0/HIDECONSOLE/ACTION = 安装/FEATURES = SQLEngine，Tools/INSTANCENAME = LYNCLOCAL/TCPENABLED = 1/SQLSVCACCOUNT = "NT AUTHORITY\NetworkService"/SQLSYSADMINACCOUNTS = "Builtin\Administrators"/BROWSERSVCSTARTUPTYPE = "/AGTSVCACCOUNT =" NTAUTHORITY\NetworkService "/SQLSVCSTARTUPTYPE =" "=" "= 自动</span><span class="sxs-lookup"><span data-stu-id="d6423-310">SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=LYNCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automatic</span></span>
1. <span data-ttu-id="d6423-311">运行 Skype for Business Server 2015 RTM 设置。</span><span class="sxs-lookup"><span data-stu-id="d6423-311">Run Skype for Business Server 2015 RTM setup.</span></span>
2. <span data-ttu-id="d6423-312">按照上面的 "先决条件" 部分中的其余步骤操作。</span><span class="sxs-lookup"><span data-stu-id="d6423-312">Follow the remaining steps from the prerequisites section above.</span></span>

<span data-ttu-id="d6423-313">**选项3：** 您也可以手动替换本地安装媒体目录中的二进制文件，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d6423-313">**Option 3:** You may also manually replace binaries in a local installation media directory as follows:</span></span>

1. [<span data-ttu-id="d6423-314">安装 Skype for business 服务器的先决条件</span><span class="sxs-lookup"><span data-stu-id="d6423-314">Install prerequisites for Skype for Business Server</span></span>](../../deploy/install/install-prerequisites.md)  
2. <span data-ttu-id="d6423-315">安装 .NET 4.7：</span><span class="sxs-lookup"><span data-stu-id="d6423-315">Install .NET 4.7:</span></span> 
      - <span data-ttu-id="d6423-316">**注意：** 我们首先在 Skype for business Server 2015 CU5 （6.0.9319.281）中引入了对 .NET 4.7 的支持。</span><span class="sxs-lookup"><span data-stu-id="d6423-316">**Note:** We first introduced support for .NET 4.7 in Skype for Business Server 2015 CU5 (6.0.9319.281).</span></span> <span data-ttu-id="d6423-317">因此，在后面的步骤中，我们将在主安装之前更新核心组件。</span><span class="sxs-lookup"><span data-stu-id="d6423-317">Therefore, in later steps below we will be updating Core Components prior to the main install.</span></span>
      - <span data-ttu-id="d6423-318">下载： https://www.microsoft.com/download/details.aspx?id=55167。</span><span class="sxs-lookup"><span data-stu-id="d6423-318">Download: https://www.microsoft.com/download/details.aspx?id=55167.</span></span> 
      - <span data-ttu-id="d6423-319">参考：[应在 Skype For Business Server 2015 部署之前安装的软件](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)</span><span class="sxs-lookup"><span data-stu-id="d6423-319">Reference: [Software that should be installed before a Skype for Business Server 2015 deployment](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)</span></span>
3. <span data-ttu-id="d6423-320">复制 ISO 文件/文件夹：</span><span class="sxs-lookup"><span data-stu-id="d6423-320">Copy ISO Files/Folders:</span></span> 
    - <span data-ttu-id="d6423-321">通过附加 Skype for Business Server 2015 ISO，打开它所附加的驱动器的根目录（例如：\)在文件资源管理器中）。</span><span class="sxs-lookup"><span data-stu-id="d6423-321">With the Skype for Business Server 2015 ISO attached, open the root directory of the drive it is attached as (Ex: D:\) in File Explorer.</span></span>
    - <span data-ttu-id="d6423-322">将所有文件夹和文件复制到本地磁盘上的文件夹（例如： C:\SkypeForBusiness2015ISO）。</span><span class="sxs-lookup"><span data-stu-id="d6423-322">Copy all folders and files to a folder on a local disk (Ex: C:\SkypeForBusiness2015ISO).</span></span>
    - <span data-ttu-id="d6423-323">**注意：** 安装组件之前，需要更新某些文件，以支持 TLS 1.2。</span><span class="sxs-lookup"><span data-stu-id="d6423-323">**Note:** Prior to installing components, some files will need to be updated for support of TLS 1.2.</span></span>
4. <span data-ttu-id="d6423-324">替换 MSI/EXE 程序包：</span><span class="sxs-lookup"><span data-stu-id="d6423-324">Replace MSI/EXE Packages:</span></span> 
    - <span data-ttu-id="d6423-325">替换本地计算机上安装媒体的/Setup/amd64/文件夹中的现有 MSI 和 EXE 程序包。</span><span class="sxs-lookup"><span data-stu-id="d6423-325">Replace the existing MSI and EXE packages in the /Setup/amd64/ folder of the installation media on the local machine.</span></span>
    - <span data-ttu-id="d6423-326">SQL 2014 SP2 Express：https://www.microsoft.com/en-us/download/details.aspx?id=53167</span><span class="sxs-lookup"><span data-stu-id="d6423-326">SQL 2014 SP2 Express: https://www.microsoft.com/en-us/download/details.aspx?id=53167</span></span> 
        - <span data-ttu-id="d6423-327">在本地计算机上重命名为 SQLEXPR_x64，并替换安装媒体的 Setup/amd64/文件夹中的现有文件。</span><span class="sxs-lookup"><span data-stu-id="d6423-327">Rename to SQLEXPR_x64 on the local machine, and replace the existing file in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="d6423-328">SQL Native 客户端：https://www.microsoft.com/en-us/download/details.aspx?id=50402</span><span class="sxs-lookup"><span data-stu-id="d6423-328">SQL Native Client: https://www.microsoft.com/en-us/download/details.aspx?id=50402</span></span> 
        - <span data-ttu-id="d6423-329">**注意：** 如有必要，请将其重命名为 sqlncli，然后替换安装媒体的 Setup/amd64/文件夹中存在的现有文件。</span><span class="sxs-lookup"><span data-stu-id="d6423-329">**Note:** Rename this if necessary to sqlncli.msi, and then replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="d6423-330">SQL 管理对象：https://www.microsoft.com/en-us/download/details.aspx?id=53164</span><span class="sxs-lookup"><span data-stu-id="d6423-330">SQL Management Objects: https://www.microsoft.com/en-us/download/details.aspx?id=53164</span></span> 
        - <span data-ttu-id="d6423-331">**注意：** 功能包将有大量可供下载的项目。</span><span class="sxs-lookup"><span data-stu-id="d6423-331">**Note:** The Feature pack will have a lot of items that can be downloaded.</span></span> <span data-ttu-id="d6423-332">选择仅下载 SharedManagementObjects。</span><span class="sxs-lookup"><span data-stu-id="d6423-332">Select to download SharedManagementObjects.msi only.</span></span>
        - <span data-ttu-id="d6423-333">**注意：** 替换安装媒体的 Setup/amd64/文件夹中存在的现有文件。</span><span class="sxs-lookup"><span data-stu-id="d6423-333">**Note:** Replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="d6423-334">SQL CLR 类型：https://www.microsoft.com/en-us/download/details.aspx?id=53164</span><span class="sxs-lookup"><span data-stu-id="d6423-334">SQL CLR Types: https://www.microsoft.com/en-us/download/details.aspx?id=53164</span></span> 
        - <span data-ttu-id="d6423-335">**注意：** 功能包将有大量可供下载的项目。</span><span class="sxs-lookup"><span data-stu-id="d6423-335">**Note:** The Feature pack will have a lot of items that can be downloaded.</span></span> <span data-ttu-id="d6423-336">选择仅下载 CQLSysClrTypes</span><span class="sxs-lookup"><span data-stu-id="d6423-336">Select to download CQLSysClrTypes.msi only</span></span>
        - <span data-ttu-id="d6423-337">**注意**：替换安装媒体的 Setup/amd64/文件夹中存在的现有文件。</span><span class="sxs-lookup"><span data-stu-id="d6423-337">**Note**: Replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
5. <span data-ttu-id="d6423-338">安装核心组件：</span><span class="sxs-lookup"><span data-stu-id="d6423-338">Install Core Components:</span></span> 
    - <span data-ttu-id="d6423-339">从安装媒体的 Setup/amd64/文件夹运行 Setup.exe。</span><span class="sxs-lookup"><span data-stu-id="d6423-339">Run Setup.exe from the Setup/amd64/ folder of the installation media.</span></span> <span data-ttu-id="d6423-340">按照说明安装核心组件</span><span class="sxs-lookup"><span data-stu-id="d6423-340">Follow the instructions to install Core Components</span></span>
    - <span data-ttu-id="d6423-341">关闭核心组件。</span><span class="sxs-lookup"><span data-stu-id="d6423-341">Close Core Components.</span></span>
6. <span data-ttu-id="d6423-342">更新核心组件：</span><span class="sxs-lookup"><span data-stu-id="d6423-342">Update Core Components:</span></span> 
    - <span data-ttu-id="d6423-343">下载 Skype for Business 更新安装程序。</span><span class="sxs-lookup"><span data-stu-id="d6423-343">Download the Skype for Business Update Installer.</span></span>
    - <span data-ttu-id="d6423-344">运行安装程序以更新核心组件并安装性能计数器。</span><span class="sxs-lookup"><span data-stu-id="d6423-344">Run the installer to update Core Components and install the performance counters.</span></span>
    - <span data-ttu-id="d6423-345">**注意：** 从 CU6HF2 发布开始，"自动更新" 功能目前仅安装最多 CU6。</span><span class="sxs-lookup"><span data-stu-id="d6423-345">**Note:** As of the release of CU6HF2, the auto-update feature currently only will install up to CU6.</span></span> <span data-ttu-id="d6423-346">因此，必须单独运行更新程序，以将核心组件更新到6.0.9319.516。</span><span class="sxs-lookup"><span data-stu-id="d6423-346">Therefore, the updater must be run separately to update Core Components to 6.0.9319.516.</span></span>
    - <span data-ttu-id="d6423-347">参阅https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015</span><span class="sxs-lookup"><span data-stu-id="d6423-347">Reference: https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015</span></span>
7. <span data-ttu-id="d6423-348">安装管理工具（可选）：</span><span class="sxs-lookup"><span data-stu-id="d6423-348">Install Administrative Tools (Optional):</span></span> 
    - <span data-ttu-id="d6423-349">这将使用已更新的文件安装 Microsoft SQL Server 2012 本机客户端、SQL Server 2014 管理对象（x64）和 Microsoft System CLR 类型（x64）和 SQL Server 2014 （x64）。</span><span class="sxs-lookup"><span data-stu-id="d6423-349">This will install the Microsoft SQL Server 2012 Native Client, SQL Server 2014 Management Objects (x64), and Microsoft System CLR Types for SQL Server 2014 (x64) using the updated files.</span></span> <span data-ttu-id="d6423-350">此外，Skype for Business Server 2015 拓扑生成器和控制面板将在本地计算机上可用。</span><span class="sxs-lookup"><span data-stu-id="d6423-350">Additionally, the Skype for Business Server 2015 Topology Builder and Control Panel will be available on the local machine.</span></span>
8. <span data-ttu-id="d6423-351">安装本地配置存储（步骤1）：</span><span class="sxs-lookup"><span data-stu-id="d6423-351">Install Local Configuration Store (Step 1):</span></span> 
     - <span data-ttu-id="d6423-352">打开部署向导，单击 "安装或更新 Skype for business 服务器系统"，然后单击步骤1中的 "**运行**"： "安装本地配置存储"。</span><span class="sxs-lookup"><span data-stu-id="d6423-352">Open the Deployment Wizard, click Install or Update Skype for Business Server System, and click on **Run** at Step 1: Install Local Configuration Store.</span></span>
     - <span data-ttu-id="d6423-353">单击 "**安装本地配置存储**" 对话框中的 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="d6423-353">Click **Next** in the **Install Local Configuration Store** dialog box.</span></span>
     <span data-ttu-id="d6423-354">!["安装本地配置存储" 对话框](../../media/local-configuration-store.png)</span><span class="sxs-lookup"><span data-stu-id="d6423-354">![Install Local Configuration Store dialog box](../../media/local-configuration-store.png)</span></span>
     - <span data-ttu-id="d6423-355">查看结果，确保任务状态为 "已完成"。</span><span class="sxs-lookup"><span data-stu-id="d6423-355">Review the results, and ensure that the Task Status is Completed.</span></span> <span data-ttu-id="d6423-356">通过单击 "**查看日志**" 查看生成的日志文件。</span><span class="sxs-lookup"><span data-stu-id="d6423-356">Review the resulting log file by clicking **View Log**.</span></span>
     <span data-ttu-id="d6423-357">![任务状态显示为已完成](../../media/local-configuration-task-completed.png)</span><span class="sxs-lookup"><span data-stu-id="d6423-357">![Task status shows as Completed](../../media/local-configuration-task-completed.png)</span></span>
     - <span data-ttu-id="d6423-358">单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="d6423-358">Click **Finish**.</span></span>
9. <span data-ttu-id="d6423-359">设置或删除 Skype for business 服务器组件（步骤2）：</span><span class="sxs-lookup"><span data-stu-id="d6423-359">Set up or remove Skype for Business Server Components (Step 2):</span></span>
    - <span data-ttu-id="d6423-360">打开部署向导，单击 "**安装或更新 skype for Business 服务器系统**"，然后单击步骤2中的 "**运行**"：设置或删除 Skype for business 服务器组件</span><span class="sxs-lookup"><span data-stu-id="d6423-360">Open the Deployment Wizard, click **Install or Update Skype for Business Server System**, and click **Run** at Step 2: Set up or Remove Skype for Business Server Components</span></span>
    - <span data-ttu-id="d6423-361">在 "设置 Skype for Business 服务器组件" 对话框中，单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="d6423-361">Click **Next** in the Set Up Skype for Business Server Components dialog box.</span></span>
    <span data-ttu-id="d6423-362">!["设置 Skype for Business 服务器组件" 窗口](../../media/set-up-skype-for-business-server-components-window.png)</span><span class="sxs-lookup"><span data-stu-id="d6423-362">![the Set Up Skype for Business Server Components window](../../media/set-up-skype-for-business-server-components-window.png)</span></span>
    - <span data-ttu-id="d6423-363">使用 "查看日志" 查看日志，并验证安装程序是否未出现问题。</span><span class="sxs-lookup"><span data-stu-id="d6423-363">Review the log using View Log, and validate that setup completed without issues.</span></span> 
    - <span data-ttu-id="d6423-364">单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="d6423-364">Click **Finish**.</span></span>
10. <span data-ttu-id="d6423-365">根据需要继续执行其他安装和配置（此时可以恢复正常的安装过程）。</span><span class="sxs-lookup"><span data-stu-id="d6423-365">Proceed with additional installation and configuration as required (you can resume normal installation procedures at this point).</span></span>
