---
title: 在 VDI 环境中规划 Skype for Business
author: lanachin
ms.author: v-lanac
ms.reviewer: krishra
manager: serdars
ms.date: 1/9/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ea68414b-bb7e-483a-b731-b6b5a44372b1
description: 本主题讨论在连接到远程虚拟桌面时使用 Skype for Business 的规划注意事项。
ms.openlocfilehash: c2972e2b453b6cf5592ddc8b3b48dfceee9a4e35
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42027993"
---
# <a name="plan-for-skype-for-business-in-vdi-environments"></a><span data-ttu-id="b6895-103">在 VDI 环境中规划 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="b6895-103">Plan for Skype for Business in VDI environments</span></span>
 
<span data-ttu-id="b6895-104">本主题讨论在连接到远程虚拟桌面时使用 Skype for Business 的规划注意事项。</span><span class="sxs-lookup"><span data-stu-id="b6895-104">This topic discusses planning considerations for using Skype for Business while connecting to a remote virtual desktop.</span></span> 
  
<span data-ttu-id="b6895-105">在某些组织中，在安全和合规性问题尤其敏感的组织中使用虚拟桌面基础结构（VDI）环境。</span><span class="sxs-lookup"><span data-stu-id="b6895-105">A Virtual Desktop Infrastructure (VDI) environment is used in some organizations where security and compliance issues are especially sensitive.</span></span> <span data-ttu-id="b6895-106">他们的用户使用远程桌面服务或类似的远程连接在虚拟机上完成其所有桌面应用程序和文件的工作。</span><span class="sxs-lookup"><span data-stu-id="b6895-106">Their users do their work on a virtual desktop with all their desktop applications and files using Remote Desktop Services or a similar remote connection.</span></span> <span data-ttu-id="b6895-107">在连接上使用 Skype for Business （如这样的连接）需要大量在虚拟机上托管客户端上的音频和视频处理负载。</span><span class="sxs-lookup"><span data-stu-id="b6895-107">Using Skype for Business with full audio and video on a connection like that requires heavy loads of audio and video processing on the client homed on a virtual desktop.</span></span> <span data-ttu-id="b6895-108">另外还提供了其他 VDI 插件软件，用于将该处理降到最终用户的本地计算机上，并减少了虚拟机上的负载。</span><span class="sxs-lookup"><span data-stu-id="b6895-108">Additional VDI plug-in software is available that offloads that processing to the end user's local machine, and reduces the load on the virtual desktop.</span></span>
  
<span data-ttu-id="b6895-109">Microsoft、Citrix 或 VMWare 提供了三个可用于 VDI 插件组件的解决方案。</span><span class="sxs-lookup"><span data-stu-id="b6895-109">There are three solutions available for the VDI plug-in component, offered by Microsoft, Citrix, or VMWare.</span></span> <span data-ttu-id="b6895-110">对于新的部署，Microsoft 建议使用 Citrix HDX 实时优化包解决方案或 VMWare 地平线虚拟化包。</span><span class="sxs-lookup"><span data-stu-id="b6895-110">For new deployments, Microsoft recommends using either the Citrix HDX RealTime Optimization Pack solution or the VMWare Horizon Virtualization Pack.</span></span> <span data-ttu-id="b6895-111">原始 Lync VDI 插件仍支持在其生命周期的剩余部分中。</span><span class="sxs-lookup"><span data-stu-id="b6895-111">The original Lync VDI Plug-in is still supported for the remainder of its lifecycle.</span></span>
  
- <span data-ttu-id="b6895-112">**LYNC VDI 插件**是为 lync 2013 开发的，并且与运行在虚拟桌面上的 Lync 2013 或 Skype for business 2015 客户端兼容。</span><span class="sxs-lookup"><span data-stu-id="b6895-112">The **Lync VDI plug-in** was developed for Lync 2013 and is compatible with either the Lync 2013 or Skype for Business 2015 client running on a virtual desktop.</span></span> <span data-ttu-id="b6895-113">它是一个独立的应用程序，在本地计算机上安装，允许在虚拟桌面上将本地音频和视频设备与客户端一起使用。</span><span class="sxs-lookup"><span data-stu-id="b6895-113">It's a stand-alone application that installs on the local computer and allows the use of local audio and video devices with a client on a virtual desktop.</span></span> <span data-ttu-id="b6895-114">该插件不需要在本地计算机或瘦客户端上安装 Skype for Business 客户端，该客户端必须运行 Windows 7、Windows 8 或 Windows Server 2008 操作系统。</span><span class="sxs-lookup"><span data-stu-id="b6895-114">The plug-in does not require a Skype for Business client to be installed on the local computer or thin client, which must run Windows 7, Windows 8, or Windows Server 2008 operating systems.</span></span> <span data-ttu-id="b6895-115">（使用这些操作系统并受 Microsoft 支持的瘦客户端设备包括： Dell Wyse Z90D7、Dell Wyse R90L7、Dell Wyse X90m7、HP t610 和 HP t5740e。）此插件仍受支持，但不计划将来的任何更新。</span><span class="sxs-lookup"><span data-stu-id="b6895-115">(Thin client devices using these operating systems and supported by Microsoft include: Dell Wyse Z90D7, Dell Wyse R90L7, Dell Wyse X90m7, HP t610 and HP t5740e.) This plug-in is still supported, but no future updates are planned.</span></span> <span data-ttu-id="b6895-116">对于基于 Citrix 的虚拟环境，建议使用 Citrix 实时优化包。</span><span class="sxs-lookup"><span data-stu-id="b6895-116">For Citrix-based virtual environments, the Citrix RealTime Optimization Pack is recommended.</span></span>
    
- <span data-ttu-id="b6895-117">**Citrix 实时优化包**建立在 lync VDI 插件之上，可在虚拟机上与 Lync 2013 或 Skype for business 2016 客户端配合使用。</span><span class="sxs-lookup"><span data-stu-id="b6895-117">The **Citrix RealTime Optimization Pack** builds on the Lync VDI plug-in and works with Lync 2013 or Skype for Business 2016 clients on a virtual desktop.</span></span> <span data-ttu-id="b6895-118">它由 Citrix 和 Microsoft 共同开发，可在原始 VDI 插件上进行改进。</span><span class="sxs-lookup"><span data-stu-id="b6895-118">It was co-developed by Citrix and Microsoft to improve upon the original VDI Plug-in.</span></span> <span data-ttu-id="b6895-119">它可以安装在具有 Windows 和非 Windows 操作系统（包括 Windows 10、Mac 和 Linux）的客户端上。</span><span class="sxs-lookup"><span data-stu-id="b6895-119">It can be installed on clients with Windows and non-Windows operating systems (including Windows 10, Mac and Linux).</span></span> <span data-ttu-id="b6895-120">它包含两个组件：实时连接器（安装在虚拟机上）和实时媒体引擎（安装在最终用户的本地计算机上）。</span><span class="sxs-lookup"><span data-stu-id="b6895-120">It consists of two components: the RealTime Connector (which is installed on the virtual desktop) and the RealTime Media Engine (which is installed on the end user's local machine).</span></span> <span data-ttu-id="b6895-121">这两个组件允许用户的本地计算机使用在虚拟桌面上运行的 Skype for Business 客户端，并将 A/V 处理移动到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="b6895-121">These two components allow the user's local computer to use the Skype for Business client running on the virtual desktop with the A/V processing moved to the local computer.</span></span> <span data-ttu-id="b6895-122">对于基于 Citrix 的虚拟桌面环境，建议使用 Citrix 实时优化包，并规划进一步的支持。</span><span class="sxs-lookup"><span data-stu-id="b6895-122">For Citrix-based virtual desktop environments, the Citrix RealTime Optimization Pack is recommended, and further support is planned.</span></span>
    
- <span data-ttu-id="b6895-123">适用于 Skype for business 的**VMWare 地平线虚拟化包**（与 VMWare 协作开发）使您能够在虚拟桌面中提供 Skype for business，同时提供极好的用户体验。</span><span class="sxs-lookup"><span data-stu-id="b6895-123">The **VMWare Horizon Virtualization Pack** for Skype for Business, developed in collaboration with VMWare, allows you to deliver Skype for Business in a virtual desktop while delivering a great user experience.</span></span> <span data-ttu-id="b6895-124">此解决方案的工作原理是，在客户端上利用媒体引擎创建优化的解决方案，客户端终结点为音频和视频呼叫提供媒体卸载功能。</span><span class="sxs-lookup"><span data-stu-id="b6895-124">The solution works by leveraging a media engine at the client to create an optimized solution, with the client endpoint providing media offload capabilities for audio and video calls.</span></span> <span data-ttu-id="b6895-125">这种解决方案可以直接在终结点之间直接传递单一单一协作的音频和视频，也可以将其卸载到多方会议呼叫或会议的中央 Multipoint 控制单元（MCU）。</span><span class="sxs-lookup"><span data-stu-id="b6895-125">This solution that can deliver audio and video either directly between endpoints for one-on-one collaboration, or offload it to a central Multipoint Control Unit (MCU) for multiparty conference calls or meetings.</span></span>
    
> [!NOTE]
> <span data-ttu-id="b6895-126">在 Citrix HDX 实时优化包或 VMWare 地平线虚拟化包中不支持 Skype for Business 基本客户端。</span><span class="sxs-lookup"><span data-stu-id="b6895-126">The Skype for Business Basic clients are not supported with the Citrix HDX RealTime Optimization Pack or the VMWare Horizon Virtualization Pack.</span></span> 
  
## <a name="citrix-hdx-realtime-optimization-pack"></a><span data-ttu-id="b6895-127">Citrix HDX 实时优化包</span><span class="sxs-lookup"><span data-stu-id="b6895-127">Citrix HDX RealTime Optimization Pack</span></span>
<span data-ttu-id="b6895-128"><a name="Citrix_RT"> </a></span><span class="sxs-lookup"><span data-stu-id="b6895-128"><a name="Citrix_RT"> </a></span></span>

<span data-ttu-id="b6895-129">Citrix 的 VDI 环境插件（XenApp 和 XenDesktop 的功能）与 Lync 2013 和 Skype for Business 2015 和2016（使用任意单击运行安装程序的完整客户端，或在已安装在虚拟机上的年1月 1 2017 日之后发布的 MSI 安装程序）兼容desktop.</span><span class="sxs-lookup"><span data-stu-id="b6895-129">Citrix's VDI environment plugin (a feature of XenApp and XenDesktop) is compatible with Lync 2013 and Skype for Business 2015 and 2016 (Full clients using any click to run installer, or MSI installers released after January 2017 PU) clients installed on a virtual desktop.</span></span> <span data-ttu-id="b6895-130">其总体功能基于 Microsoft Lync VDI 插件，但在更广泛的客户端操作系统（包括 Windows 10、Macintosh 和 Linux）上运行。</span><span class="sxs-lookup"><span data-stu-id="b6895-130">Its overall functioning is based on the Microsoft Lync VDI plug-in, but works on a wider variety of client operating systems, including Windows 10, Macintosh, and Linux.</span></span>
  
<span data-ttu-id="b6895-131">在将[Microsoft Skype For Business 发送到 XenApp 和 XenDesktop 用户](https://www.citrix.com/content/dam/citrix/en_us/documents/products-solutions/delivering-microsoft-lync-to-xenapp-and-xendesktop-users.pdf)的 Citrix 网站上，可以找到功能和受支持的技术的完整列表。</span><span class="sxs-lookup"><span data-stu-id="b6895-131">A full list of features and supported technologies can be found on the Citrix website at [Delivering Microsoft Skype for Business to XenApp and XenDesktop Users](https://www.citrix.com/content/dam/citrix/en_us/documents/products-solutions/delivering-microsoft-lync-to-xenapp-and-xendesktop-users.pdf).</span></span>
  
<span data-ttu-id="b6895-132">有关详细信息，请参阅以下链接：</span><span class="sxs-lookup"><span data-stu-id="b6895-132">Review the following links for more information:</span></span>
  
- <span data-ttu-id="b6895-133">Citrix [HDX 实时优化包 2.1](https://docs.citrix.com/en-us/hdx-optimization/2-1.mdl)</span><span class="sxs-lookup"><span data-stu-id="b6895-133">Citrix [HDX RealTime Optimization Pack 2.1](https://docs.citrix.com/en-us/hdx-optimization/2-1.mdl)</span></span>
    
- [<span data-ttu-id="b6895-134">技术概述</span><span class="sxs-lookup"><span data-stu-id="b6895-134">Technical Overview</span></span>](https://docs.citrix.com/en-us/hdx-optimization/2-1/about.mdl)
    
- [<span data-ttu-id="b6895-135">CTX200279 Skype for Business 功能支持</span><span class="sxs-lookup"><span data-stu-id="b6895-135">CTX200279 Skype for Business Feature Support</span></span>](https://support.citrix.com/article/CTX200279)
    
## <a name="vmware-horizon-virtualization-pack"></a><span data-ttu-id="b6895-136">VMWare 地平线虚拟化包</span><span class="sxs-lookup"><span data-stu-id="b6895-136">VMWare Horizon Virtualization Pack</span></span>
<span data-ttu-id="b6895-137"><a name="Citrix_RT"> </a></span><span class="sxs-lookup"><span data-stu-id="b6895-137"><a name="Citrix_RT"> </a></span></span>

<span data-ttu-id="b6895-138">VMWare 的 VDI 环境解决方案与安装在虚拟桌面上的 Skype for Business 2015 和2016完全客户端兼容。</span><span class="sxs-lookup"><span data-stu-id="b6895-138">VMWare's VDI environment solution is compatible with Skype for Business 2015 and 2016 Full clients installed on a virtual desktop.</span></span> <span data-ttu-id="b6895-139">其总体功能基于 Microsoft Lync VDI 插件，但在更广泛的客户端操作系统（包括 Windows 10、Macintosh 和 Linux）上运行。</span><span class="sxs-lookup"><span data-stu-id="b6895-139">Its overall functioning is based on the Microsoft Lync VDI plug-in, but works on a wider variety of client operating systems, including Windows 10, Macintosh, and Linux.</span></span> 
  
<span data-ttu-id="b6895-140">可在 VMWare 网站上找到有关功能和受支持的技术的完整讨论，这些链接如下所示：</span><span class="sxs-lookup"><span data-stu-id="b6895-140">A full discussion of features and supported technologies can be found on the VMWare website at the following links:</span></span>
  
- [<span data-ttu-id="b6895-141">VMware 地平线 7.4 &amp;地平线客户端4.7 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="b6895-141">What's New in VMware Horizon 7.4 &amp; Horizon Client 4.7</span></span>](https://blogs.vmware.com/euc/2018/01/vmware-horizon-7-4-horizon-client-4-7-whats-new.mdl)
    
- [<span data-ttu-id="b6895-142">Skype for business 的地平线虚拟化包</span><span class="sxs-lookup"><span data-stu-id="b6895-142">Horizon Virtualization Pack for Skype for Business</span></span>](https://www.vmware.com/products/horizon/skype-for-business.mdl)
    
- [<span data-ttu-id="b6895-143">使用 VMWare 的 Microsoft Skype for Business 范围</span><span class="sxs-lookup"><span data-stu-id="b6895-143">Microsoft Skype for Business With VMWare Horizon</span></span>](https://www.vmware.com/content/dam/digitalmarketing/vmware/en/pdf/products/horizon/vmware-skype-for-business-solution-brief.pdf)
    
## <a name="microsofts-lync-vdi-plug-in"></a><span data-ttu-id="b6895-144">Microsoft 的 Lync VDI 插件</span><span class="sxs-lookup"><span data-stu-id="b6895-144">Microsoft's Lync VDI plug-in</span></span>
<span data-ttu-id="b6895-145"><a name="Citrix_RT"> </a></span><span class="sxs-lookup"><span data-stu-id="b6895-145"><a name="Citrix_RT"> </a></span></span>

<span data-ttu-id="b6895-146">使用 Microsoft Lync VDI 插件解决方案，用户必须在 Windows 计算机或瘦客户端上，并已安装 Microsoft 的 Lync VDI 插件，以便在虚拟机上处理来自客户端的音频/视频流。</span><span class="sxs-lookup"><span data-stu-id="b6895-146">With the Microsoft Lync VDI plug-in solution, the user has to be on a Windows computer or thin client and have Microsoft's Lync VDI plugin installed to handle audio/video streams from the client on the virtual desktop.</span></span> <span data-ttu-id="b6895-147">用户将：</span><span class="sxs-lookup"><span data-stu-id="b6895-147">A user will:</span></span>
  
1. <span data-ttu-id="b6895-148">将音频/视频设备（如耳机或相机）连接到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="b6895-148">Connect an audio/video device (like a headset or camera) to a local computer.</span></span>
    
2. <span data-ttu-id="b6895-149">使用 Lync 2013 或 Skype for Business 2015 客户端连接到远程虚拟桌面。</span><span class="sxs-lookup"><span data-stu-id="b6895-149">Connect to a remote virtual desktop with a Lync 2013 or Skype for Business 2015 client.</span></span>
    
3. <span data-ttu-id="b6895-150">在虚拟机上输入 Skype for Business 的凭据。</span><span class="sxs-lookup"><span data-stu-id="b6895-150">Enter credentials for Skype for Business on the virtual desktop.</span></span>
    
4. <span data-ttu-id="b6895-151">重新输入用户凭据以在本地 Windows 计算机或瘦客户端上建立与 Lync VDI 插件的连接。</span><span class="sxs-lookup"><span data-stu-id="b6895-151">Re-enter user credentials to establish a connection with the Lync VDI plug-in on the local Windows computer or thin client.</span></span>
    
<span data-ttu-id="b6895-152">建立连接后，用户可以发出和接收音频和视频呼叫。</span><span class="sxs-lookup"><span data-stu-id="b6895-152">After a connection is established, the user is ready to make and receive audio and video calls.</span></span> <span data-ttu-id="b6895-153">因为本地计算机处理音频/视频处理，所以网络上的流量和虚拟桌面上的负载都将最小化。</span><span class="sxs-lookup"><span data-stu-id="b6895-153">Traffic on the network and the load on the virtual desktop are minimized, since the local computer handles the audio/video processing.</span></span>
  
<span data-ttu-id="b6895-154">Microsoft 的 Lync VDI 插件仅在某些 Windows 操作系统上受支持，并且仅支持 Lync 2013 或 Skype for Business 2015 客户端。</span><span class="sxs-lookup"><span data-stu-id="b6895-154">Microsoft's Lync VDI plug-in is only supported on certain Windows operating systems and only supports Lync 2013 or Skype for Business 2015 clients.</span></span> <span data-ttu-id="b6895-155">有关受支持的技术和限制的更多详细信息，请参阅[支持的虚拟化技术和已知限制](vdi-environments.md#Supported_virt)。</span><span class="sxs-lookup"><span data-stu-id="b6895-155">See [Supported virtualization technologies and known limitations](vdi-environments.md#Supported_virt) for more details on supported technologies and limitations.</span></span>
  
<span data-ttu-id="b6895-156">有关详细信息，请参阅以下链接：</span><span class="sxs-lookup"><span data-stu-id="b6895-156">Review the following links for more information:</span></span>
  
- [<span data-ttu-id="b6895-157">支持的虚拟化技术和已知限制</span><span class="sxs-lookup"><span data-stu-id="b6895-157">Supported virtualization technologies and known limitations</span></span>](vdi-environments.md#Supported_virt)
    
- [<span data-ttu-id="b6895-158">Lync VDI 插件先决条件</span><span class="sxs-lookup"><span data-stu-id="b6895-158">Lync VDI plug-in prerequisites</span></span>](vdi-environments.md#VDI_prereq)
    
- [<span data-ttu-id="b6895-159">使用 Skype for Business Server 部署 Lync VDI 插件</span><span class="sxs-lookup"><span data-stu-id="b6895-159">Deploy the Lync VDI plug-in with Skype for Business Server</span></span>](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)
    
- <span data-ttu-id="b6895-160">Citrix 知识中心文章[CTX138408](https://support.citrix.com/article/CTX138408)</span><span class="sxs-lookup"><span data-stu-id="b6895-160">Citrix Knowledge Center article [CTX138408](https://support.citrix.com/article/CTX138408)</span></span>
    
<span data-ttu-id="b6895-161">Microsoft VDI 插件在[Microsoft LYNC vdi 2013 插件（32位）](https://www.microsoft.com/download/details.aspx?id=35457)或[microsoft lync vdi 2013 插件（64位）](https://www.microsoft.com/download/details.aspx?id=35454)中可用。</span><span class="sxs-lookup"><span data-stu-id="b6895-161">The Microsoft VDI plugin is available at [Microsoft Lync VDI 2013 plugin (32 bit)](https://www.microsoft.com/download/details.aspx?id=35457) or [Microsoft Lync VDI 2013 plugin (64 bit)](https://www.microsoft.com/download/details.aspx?id=35454).</span></span> <span data-ttu-id="b6895-162">无论名称是什么，Skype for Business 2015 客户端都支持此插件。</span><span class="sxs-lookup"><span data-stu-id="b6895-162">This plugin is supported with the Skype for Business 2015 client, despite the name.</span></span>
  
### <a name="supported-virtualization-technologies-and-known-limitations"></a><span data-ttu-id="b6895-163">支持的虚拟化技术和已知限制</span><span class="sxs-lookup"><span data-stu-id="b6895-163">Supported virtualization technologies and known limitations</span></span>
<span data-ttu-id="b6895-164"><a name="Supported_virt"> </a></span><span class="sxs-lookup"><span data-stu-id="b6895-164"><a name="Supported_virt"> </a></span></span>

<span data-ttu-id="b6895-165">Lync VDI 插件允许音频和视频呼叫支持的虚拟化技术。</span><span class="sxs-lookup"><span data-stu-id="b6895-165">The Lync VDI plug-in allows audio and video calling for supported virtualization technologies.</span></span> <span data-ttu-id="b6895-166">在遵守标准电话法规的情况下，还包括对 E911 的支持。</span><span class="sxs-lookup"><span data-stu-id="b6895-166">In compliance with standard telephone regulations, support for E911 is also included.</span></span> <span data-ttu-id="b6895-167">以下各节介绍了 Lync VDI 插件支持的虚拟化技术和已知的功能限制。</span><span class="sxs-lookup"><span data-stu-id="b6895-167">The following sections describe the virtualization technologies that are supported by the Lync VDI plug-in and the known feature limitations.</span></span>
  
#### <a name="support-for-virtualization-technologies"></a><span data-ttu-id="b6895-168">对虚拟化技术的支持</span><span class="sxs-lookup"><span data-stu-id="b6895-168">Support for Virtualization Technologies</span></span>

<span data-ttu-id="b6895-169">Lync VDI 插件支持个人虚拟桌面方案中的完整桌面远程会话，但不支持在远程桌面会话方案中。</span><span class="sxs-lookup"><span data-stu-id="b6895-169">The Lync VDI plug-in supports full desktop remote sessions in the personal virtual desktop scenario, but not in the remote desktop session scenario.</span></span> <span data-ttu-id="b6895-170">可以按如下所述描述这些方案：</span><span class="sxs-lookup"><span data-stu-id="b6895-170">These scenarios can be described as follows:</span></span>
  
- <span data-ttu-id="b6895-171">**支持：个性化虚拟桌面或虚拟桌面基础结构（VDI）。**</span><span class="sxs-lookup"><span data-stu-id="b6895-171">**Supported: Personalized Virtual Desktops or Virtual Desktop Infrastructure (VDI).**</span></span> <span data-ttu-id="b6895-172">在这种情况下，每个用户都登录到可自定义的虚拟桌面，并且能够在桌面上保存跨会话保留的文件。</span><span class="sxs-lookup"><span data-stu-id="b6895-172">In this scenario, each user logs on to a customizable virtual desktop and is able to save files on the desktop that persist across sessions.</span></span> <span data-ttu-id="b6895-173">Microsoft 远程桌面服务和 VMware 地平线视图是已经过测试用于 Skype for Business 2015 的示例实现。</span><span class="sxs-lookup"><span data-stu-id="b6895-173">Microsoft Remote Desktop Services and VMware Horizon View are example implementations that have been tested for use with Skype for Business 2015.</span></span> <span data-ttu-id="b6895-174">正在进行验证的其他实施包括 Citrix XenDesktop。</span><span class="sxs-lookup"><span data-stu-id="b6895-174">Other implementations undergoing validation include Citrix XenDesktop.</span></span> <span data-ttu-id="b6895-175">有关已由 Microsoft 测试的供应商特定的 VDI 环境和客户端硬件的信息，请参阅[适用于 Microsoft Lync 的基础结构限定](https://go.microsoft.com/fwlink/?LinkID=313435)。</span><span class="sxs-lookup"><span data-stu-id="b6895-175">For information about vendor-specific VDI environments and client hardware that have been tested by Microsoft, see [Infrastructure qualified for Microsoft Lync](https://go.microsoft.com/fwlink/?LinkID=313435).</span></span>
    
- <span data-ttu-id="b6895-176">**不支持：远程桌面会话。**</span><span class="sxs-lookup"><span data-stu-id="b6895-176">**Not supported: Remote Desktop Sessions.**</span></span> <span data-ttu-id="b6895-177">在这种情况下，每个用户登录到无法自定义的通用虚拟桌面会话。</span><span class="sxs-lookup"><span data-stu-id="b6895-177">In this scenario, each user logs on to a generic virtual desktop session that can't be customized.</span></span> <span data-ttu-id="b6895-178">示例包括 Microsoft 远程桌面会话（RDSH）和与 Citrix 接收器组合的 Citrix XenApp。</span><span class="sxs-lookup"><span data-stu-id="b6895-178">Examples include Microsoft Remote Desktop Sessions (RDSH) and Citrix XenApp combined with Citrix Receiver.</span></span>
    
<span data-ttu-id="b6895-179">Lync VDI 插件不支持其他虚拟化技术，如应用程序虚拟化，它允许使用应用程序，而无需在本地安装完整应用程序。</span><span class="sxs-lookup"><span data-stu-id="b6895-179">The Lync VDI plug-in does not support other virtualization technologies, such as application virtualization, which allows the use of an application without requiring installation of the full application locally.</span></span> <span data-ttu-id="b6895-180">示例实现包括 Citrix XenApp 和 Microsoft Application Virtualization （App-v）。</span><span class="sxs-lookup"><span data-stu-id="b6895-180">Example implementations include Citrix XenApp and Microsoft Application Virtualization (App-V).</span></span> <span data-ttu-id="b6895-181">不支持应用程序流式处理、应用程序远程处理和混合虚拟化模式（例如，在完整桌面远程处理中进行应用程序远程处理）。</span><span class="sxs-lookup"><span data-stu-id="b6895-181">Application streaming, application remoting, and mixed virtualization modes (for example, application remoting in full desktop remoting) are not supported.</span></span>
  
<span data-ttu-id="b6895-182">Lync VDI 插件旨在使用称为 "动态虚拟通道" （Dvc）的独立于平台的 Api。</span><span class="sxs-lookup"><span data-stu-id="b6895-182">The Lync VDI plug-in was designed to use platform-independent APIs called Dynamic Virtual Channels (DVCs).</span></span> <span data-ttu-id="b6895-183">对于未明确支持的方案，请参阅 VDI 解决方案提供商提供的支持声明。</span><span class="sxs-lookup"><span data-stu-id="b6895-183">For scenarios that are not explicitly supported, refer to support statements from the VDI solution provider.</span></span>
  
#### <a name="lync-vdi-plug-in-prerequisites"></a><span data-ttu-id="b6895-184">Lync VDI 插件先决条件</span><span class="sxs-lookup"><span data-stu-id="b6895-184">Lync VDI plug-in prerequisites</span></span>
<span data-ttu-id="b6895-185"><a name="VDI_prereq"> </a></span><span class="sxs-lookup"><span data-stu-id="b6895-185"><a name="VDI_prereq"> </a></span></span>

<span data-ttu-id="b6895-186">在 VDI 环境中，虚拟机和用户的本地计算机必须满足本节中概述的要求。</span><span class="sxs-lookup"><span data-stu-id="b6895-186">In a VDI environment, the virtual machines and the user's local computer must meet the requirements outlined in this section.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="b6895-187">您的虚拟化解决方案提供商可提供有关如何安装和部署其环境的详细信息。</span><span class="sxs-lookup"><span data-stu-id="b6895-187">Your virtualization solution provider can supply details about how to install and deploy their environment.</span></span> <span data-ttu-id="b6895-188">有关基于 Hyper-v 和远程桌面服务部署虚拟化环境的一般信息，请参阅 Microsoft Library 中的以下文章： [hyper-v](https://go.microsoft.com/fwlink/p/?linkid=247514)， [Windows Server 2008 R2 中的远程桌面服务](https://go.microsoft.com/fwlink/p/?linkid=247513)</span><span class="sxs-lookup"><span data-stu-id="b6895-188">For general information about deploying a virtualized environment based on Hyper-V and Remote Desktop Services, see the following articles in the Microsoft Library: [Hyper-V](https://go.microsoft.com/fwlink/p/?linkid=247514), [Remote Desktop Services in Windows Server 2008 R2](https://go.microsoft.com/fwlink/p/?linkid=247513)</span></span> 
  
<span data-ttu-id="b6895-189">虚拟机必须使用 Windows 8、Windows 7 或 Windows Server 2008 R2 以及最新的 service pack 进行配置。</span><span class="sxs-lookup"><span data-stu-id="b6895-189">Virtual machines must be configured with Windows 8, Windows 7, or Windows Server 2008 R2 with the latest service packs.</span></span>
  
<span data-ttu-id="b6895-190">用户的本地计算机必须满足以下要求：</span><span class="sxs-lookup"><span data-stu-id="b6895-190">The user's local computer must meet the following requirements:</span></span>
  
- <span data-ttu-id="b6895-191">用户必须驻留在 Skype for Business Server 或 Lync Server 2013 上。</span><span class="sxs-lookup"><span data-stu-id="b6895-191">The user must be homed on Skype for Business Server or Lync Server 2013.</span></span>
    
- <span data-ttu-id="b6895-192">本地计算机必须运行 Windows Embedded Standard 7 with SP1、Windows 7 SP1 （SP1）或 Windows 8。</span><span class="sxs-lookup"><span data-stu-id="b6895-192">The local computer must be running Windows Embedded Standard 7 with SP1, Windows 7 with SP1, or Windows 8.</span></span>
    
- <span data-ttu-id="b6895-193">如果正在使用远程桌面服务，请选择32位或64位 Lync VDI 插件以匹配本地计算机的操作系统。</span><span class="sxs-lookup"><span data-stu-id="b6895-193">If you're using Remote Desktop Services, choose the 32-bit or 64-bit Lync VDI plug-in to match the local computer's operating system.</span></span> <span data-ttu-id="b6895-194">本地计算机和虚拟机都不需要具有32位或64位的操作系统。</span><span class="sxs-lookup"><span data-stu-id="b6895-194">It's not required for both the local computer and the virtual machine to have 32-bit or 64-bit operating systems.</span></span> <span data-ttu-id="b6895-195">如果使用的是其他虚拟化解决方案或平台，请参考提供商的要求。</span><span class="sxs-lookup"><span data-stu-id="b6895-195">If you're using another virtualization solution or platform, refer to your provider's requirements.</span></span>
    
- <span data-ttu-id="b6895-196">本地计算机必须运行[最新版本的远程桌面客户端](https://go.microsoft.com/fwlink/p/?LinkId=268032)。</span><span class="sxs-lookup"><span data-stu-id="b6895-196">The local computer must be running the [latest version of the remote desktop client](https://go.microsoft.com/fwlink/p/?LinkId=268032).</span></span> <span data-ttu-id="b6895-197">从虚拟化解决方案提供商处安装来自 Microsoft 或最新远程桌面客户端软件的远程桌面服务客户端的最新更新。</span><span class="sxs-lookup"><span data-stu-id="b6895-197">Install the latest updates of Remote Desktop Services client from Microsoft or the latest remote desktop client software from your virtualization solution provider.</span></span> 
    
- <span data-ttu-id="b6895-198">在本地计算机上，必须配置远程桌面客户端设置，以便在本地计算机上播放音频，并禁用远程录制。</span><span class="sxs-lookup"><span data-stu-id="b6895-198">On the local computer, the remote desktop client settings must be configured so that audio plays on the local computer and remote recording is disabled.</span></span> <span data-ttu-id="b6895-199">若要在 Windows 中为远程桌面连接配置这些设置，请参阅下一节 "配置远程桌面连接设置"。</span><span class="sxs-lookup"><span data-stu-id="b6895-199">To configure these settings for Remote Desktop Connection in Windows, see the next section, "To configure Remote Desktop Connection settings."</span></span> 
    
<span data-ttu-id="b6895-200">Microsoft VDI 插件在[Microsoft LYNC vdi 2013 插件（32位）](https://www.microsoft.com/download/details.aspx?id=35457)或[microsoft lync vdi 2013 插件（64位）](https://www.microsoft.com/download/details.aspx?id=35454)中可用。</span><span class="sxs-lookup"><span data-stu-id="b6895-200">The Microsoft VDI plugin is available at [Microsoft Lync VDI 2013 plugin (32 bit)](https://www.microsoft.com/download/details.aspx?id=35457) or [Microsoft Lync VDI 2013 plugin (64 bit)](https://www.microsoft.com/download/details.aspx?id=35454).</span></span>
  
#### <a name="known-feature-limitations"></a><span data-ttu-id="b6895-201">已知功能限制</span><span class="sxs-lookup"><span data-stu-id="b6895-201">Known Feature Limitations</span></span>
<span data-ttu-id="b6895-202"><a name="VDI_prereq"> </a></span><span class="sxs-lookup"><span data-stu-id="b6895-202"><a name="VDI_prereq"> </a></span></span>

<span data-ttu-id="b6895-203">在 VDI 环境中使用 Skype for Business 2015 客户端时，以下是已知限制：</span><span class="sxs-lookup"><span data-stu-id="b6895-203">The following are known limitations when you use the Skype for Business 2015 client in a VDI environment:</span></span>
  
<span data-ttu-id="b6895-204">对呼叫委派和响应组代理 Anonymization 功能的支持有限。</span><span class="sxs-lookup"><span data-stu-id="b6895-204">There is limited support for Call Delegation and Response Group Agent Anonymization features.</span></span>
  
<span data-ttu-id="b6895-205">不支持以下功能：</span><span class="sxs-lookup"><span data-stu-id="b6895-205">There is no support for the following features:</span></span>
  
- <span data-ttu-id="b6895-206">集成音频设备和视频设备优化页。</span><span class="sxs-lookup"><span data-stu-id="b6895-206">Integrated Audio Device and Video Device tuning pages.</span></span>
    
- <span data-ttu-id="b6895-207">多视图视频。</span><span class="sxs-lookup"><span data-stu-id="b6895-207">Multiple-view video.</span></span>
    
- <span data-ttu-id="b6895-208">录制对话。</span><span class="sxs-lookup"><span data-stu-id="b6895-208">Recording of conversations.</span></span>
    
- <span data-ttu-id="b6895-209">匿名加入会议（即，加入由不与您的组织联合的组织托管的 Skype for Business 会议）。</span><span class="sxs-lookup"><span data-stu-id="b6895-209">Joining meetings anonymously (that is, joining Skype for Business meetings hosted by an organization that does not federate with your organization).</span></span>
    
- <span data-ttu-id="b6895-210">将 Lync VDI 插件与 Lync Phone Edition 设备结合使用。</span><span class="sxs-lookup"><span data-stu-id="b6895-210">Using the Lync VDI plug-in along with a Lync Phone Edition device.</span></span>
    
- <span data-ttu-id="b6895-211">发生网络中断时的呼叫连续性。</span><span class="sxs-lookup"><span data-stu-id="b6895-211">Call continuity in case of a network outage.</span></span>
    
- <span data-ttu-id="b6895-212">自定义铃声和保持音乐功能。</span><span class="sxs-lookup"><span data-stu-id="b6895-212">Customized ringtones and music-on-hold features.</span></span>
    
<span data-ttu-id="b6895-213">Office 365 环境不支持 Lync VDI 插件。</span><span class="sxs-lookup"><span data-stu-id="b6895-213">The Lync VDI plug-in is not supported in an Office 365 environment.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b6895-214">Citrix 实时优化包支持 Office 365。</span><span class="sxs-lookup"><span data-stu-id="b6895-214">The Citrix RealTime Optimization Pack does support Office 365.</span></span> <span data-ttu-id="b6895-215">对于基于 Citrix 的虚拟环境，请查看 Citrix 的[技术概述](https://docs.citrix.com/en-us/hdx-optimization/2-0/hdx-realtime-optimization-pack-about.mdl)文档，了解支持的功能和版本的列表。</span><span class="sxs-lookup"><span data-stu-id="b6895-215">For Citrix-based virtual environments, review Citrix's [Technical Overview](https://docs.citrix.com/en-us/hdx-optimization/2-0/hdx-realtime-optimization-pack-about.mdl) documentation for the list of supported features and versions.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b6895-216">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b6895-216">See also</span></span>
<span data-ttu-id="b6895-217"><a name="Citrix_RT"> </a></span><span class="sxs-lookup"><span data-stu-id="b6895-217"><a name="Citrix_RT"> </a></span></span>

[<span data-ttu-id="b6895-218">使用 Skype for Business Server 部署 Lync VDI 插件</span><span class="sxs-lookup"><span data-stu-id="b6895-218">Deploy the Lync VDI plug-in with Skype for Business Server</span></span>](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)

