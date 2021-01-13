---
title: 在 VDI 环境中规划 Skype for Business
author: cichur
ms.author: v-cichur
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
ms.openlocfilehash: 66fe9dd0be2dd079597837b8d25c29b3f047b0c6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816102"
---
# <a name="plan-for-skype-for-business-in-vdi-environments"></a><span data-ttu-id="9d352-103">在 VDI 环境中规划 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="9d352-103">Plan for Skype for Business in VDI environments</span></span>
 
<span data-ttu-id="9d352-104">本主题讨论在连接到远程虚拟桌面时使用 Skype for Business 的规划注意事项。</span><span class="sxs-lookup"><span data-stu-id="9d352-104">This topic discusses planning considerations for using Skype for Business while connecting to a remote virtual desktop.</span></span> 
  
<span data-ttu-id="9d352-105">VDI (虚拟桌面基础结构) 安全与合规性问题特别敏感的某些组织使用。</span><span class="sxs-lookup"><span data-stu-id="9d352-105">A Virtual Desktop Infrastructure (VDI) environment is used in some organizations where security and compliance issues are especially sensitive.</span></span> <span data-ttu-id="9d352-106">用户使用远程桌面服务或类似的远程连接，使用其所有桌面应用程序和文件在虚拟桌面上工作。</span><span class="sxs-lookup"><span data-stu-id="9d352-106">Their users do their work on a virtual desktop with all their desktop applications and files using Remote Desktop Services or a similar remote connection.</span></span> <span data-ttu-id="9d352-107">在类似连接上将 Skype for Business 与完整的音频和视频一同使用需要在虚拟桌面上的客户端上执行大量音频和视频处理。</span><span class="sxs-lookup"><span data-stu-id="9d352-107">Using Skype for Business with full audio and video on a connection like that requires heavy loads of audio and video processing on the client homed on a virtual desktop.</span></span> <span data-ttu-id="9d352-108">其他 VDI 插件软件可用于将处理卸载到最终用户的本地计算机，并减少虚拟桌面上的负载。</span><span class="sxs-lookup"><span data-stu-id="9d352-108">Additional VDI plug-in software is available that offloads that processing to the end user's local machine, and reduces the load on the virtual desktop.</span></span>
  
<span data-ttu-id="9d352-109">有三种解决方案可用于由 Microsoft、Citrix 或 VMWare 提供的 VDI 插件组件。</span><span class="sxs-lookup"><span data-stu-id="9d352-109">There are three solutions available for the VDI plug-in component, offered by Microsoft, Citrix, or VMWare.</span></span> <span data-ttu-id="9d352-110">对于新部署，Microsoft 建议使用 Citrix HDX RealTime Optimization Pack 解决方案或 VMWare Horizon Virtualization Pack。</span><span class="sxs-lookup"><span data-stu-id="9d352-110">For new deployments, Microsoft recommends using either the Citrix HDX RealTime Optimization Pack solution or the VMWare Horizon Virtualization Pack.</span></span> <span data-ttu-id="9d352-111">原始 Lync VDI 插件在其剩余生命周期内仍受支持。</span><span class="sxs-lookup"><span data-stu-id="9d352-111">The original Lync VDI Plug-in is still supported for the remainder of its lifecycle.</span></span>
  
- <span data-ttu-id="9d352-112">**Lync VDI** 插件针对 Lync 2013 开发，与在虚拟桌面上运行的 Lync 2013 或 Skype for Business 2015 客户端兼容。</span><span class="sxs-lookup"><span data-stu-id="9d352-112">The **Lync VDI plug-in** was developed for Lync 2013 and is compatible with either the Lync 2013 or Skype for Business 2015 client running on a virtual desktop.</span></span> <span data-ttu-id="9d352-113">它是一个安装在本地计算机上并允许将本地音频和视频设备与虚拟桌面上的客户端一起使用独立应用程序。</span><span class="sxs-lookup"><span data-stu-id="9d352-113">It's a stand-alone application that installs on the local computer and allows the use of local audio and video devices with a client on a virtual desktop.</span></span> <span data-ttu-id="9d352-114">该插件不需要在本地计算机或瘦客户端上安装 Skype for Business 客户端，该客户端必须运行 Windows 7、Windows 8 或 Windows Server 2008 操作系统。</span><span class="sxs-lookup"><span data-stu-id="9d352-114">The plug-in does not require a Skype for Business client to be installed on the local computer or thin client, which must run Windows 7, Windows 8, or Windows Server 2008 operating systems.</span></span> <span data-ttu-id="9d352-115"> (使用这些操作系统且受 Microsoft 支持的瘦客户端设备包括：Dell Wyse Z90D7、Dell Wyse R90L7、Dell Wyse X90m7、HP t610 和 HP t5740e.) 此插件仍受支持，但计划将来不会更新。</span><span class="sxs-lookup"><span data-stu-id="9d352-115">(Thin client devices using these operating systems and supported by Microsoft include: Dell Wyse Z90D7, Dell Wyse R90L7, Dell Wyse X90m7, HP t610 and HP t5740e.) This plug-in is still supported, but no future updates are planned.</span></span> <span data-ttu-id="9d352-116">对于基于 Citrix 的虚拟环境，建议使用 Citrix RealTime 优化包。</span><span class="sxs-lookup"><span data-stu-id="9d352-116">For Citrix-based virtual environments, the Citrix RealTime Optimization Pack is recommended.</span></span>
    
- <span data-ttu-id="9d352-117">**Citrix RealTime Optimization Pack** 基于 Lync VDI 插件构建，适用于虚拟桌面上的 Lync 2013 或 Skype for Business 2016 客户端。</span><span class="sxs-lookup"><span data-stu-id="9d352-117">The **Citrix RealTime Optimization Pack** builds on the Lync VDI plug-in and works with Lync 2013 or Skype for Business 2016 clients on a virtual desktop.</span></span> <span data-ttu-id="9d352-118">它由 Citrix 和 Microsoft 共同开发，以改进原始 VDI 插件。</span><span class="sxs-lookup"><span data-stu-id="9d352-118">It was co-developed by Citrix and Microsoft to improve upon the original VDI Plug-in.</span></span> <span data-ttu-id="9d352-119">它可以安装在具有 Windows 和非 Windows 操作系统的客户端上， (Windows 10、Mac 和 Linux) 。</span><span class="sxs-lookup"><span data-stu-id="9d352-119">It can be installed on clients with Windows and non-Windows operating systems (including Windows 10, Mac and Linux).</span></span> <span data-ttu-id="9d352-120">它包含两个组件：安装在虚拟桌面) 上的 RealTime 连接器 (和安装在最终用户的本地计算机上 (的 RealTime 媒体引擎) 。</span><span class="sxs-lookup"><span data-stu-id="9d352-120">It consists of two components: the RealTime Connector (which is installed on the virtual desktop) and the RealTime Media Engine (which is installed on the end user's local machine).</span></span> <span data-ttu-id="9d352-121">这两个组件允许用户的本地计算机使用在虚拟桌面上运行的 Skype for Business 客户端，同时将 A/V 处理移动到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="9d352-121">These two components allow the user's local computer to use the Skype for Business client running on the virtual desktop with the A/V processing moved to the local computer.</span></span> <span data-ttu-id="9d352-122">对于基于 Citrix 的虚拟桌面环境，建议使用 Citrix RealTime Optimization Pack，并计划进一步提供支持。</span><span class="sxs-lookup"><span data-stu-id="9d352-122">For Citrix-based virtual desktop environments, the Citrix RealTime Optimization Pack is recommended, and further support is planned.</span></span>
    
- <span data-ttu-id="9d352-123">**与 VMWare 协作开发的适用于** Skype for Business 的 VMWare 范围虚拟化包允许你在虚拟桌面中交付 Skype for Business，同时提供出色的用户体验。</span><span class="sxs-lookup"><span data-stu-id="9d352-123">The **VMWare Horizon Virtualization Pack** for Skype for Business, developed in collaboration with VMWare, allows you to deliver Skype for Business in a virtual desktop while delivering a great user experience.</span></span> <span data-ttu-id="9d352-124">解决方案的工作方式是利用客户端的媒体引擎来创建优化的解决方案，客户端终结点为音频和视频呼叫提供媒体卸载功能。</span><span class="sxs-lookup"><span data-stu-id="9d352-124">The solution works by leveraging a media engine at the client to create an optimized solution, with the client endpoint providing media offload capabilities for audio and video calls.</span></span> <span data-ttu-id="9d352-125">此解决方案可以直接在终结点之间传送音频和视频，实现一对一协作，或卸载到中央多点控制单元 (MCU) 进行多方电话会议或会议。</span><span class="sxs-lookup"><span data-stu-id="9d352-125">This solution that can deliver audio and video either directly between endpoints for one-on-one collaboration, or offload it to a central Multipoint Control Unit (MCU) for multiparty conference calls or meetings.</span></span>
    
> [!NOTE]
> <span data-ttu-id="9d352-126">Citrix HDX RealTime Optimization Pack 或 VMWare Horizon Virtualization Pack 不支持 Skype for Business Basic 客户端。</span><span class="sxs-lookup"><span data-stu-id="9d352-126">The Skype for Business Basic clients are not supported with the Citrix HDX RealTime Optimization Pack or the VMWare Horizon Virtualization Pack.</span></span> 
  
## <a name="citrix-hdx-realtime-optimization-pack"></a><span data-ttu-id="9d352-127">Citrix HDX RealTime Optimization Pack</span><span class="sxs-lookup"><span data-stu-id="9d352-127">Citrix HDX RealTime Optimization Pack</span></span>
<span data-ttu-id="9d352-128"><a name="Citrix_RT"> </a></span><span class="sxs-lookup"><span data-stu-id="9d352-128"><a name="Citrix_RT"> </a></span></span>

<span data-ttu-id="9d352-129">Citrix 的 VDI 环境插件 (XenApp 和 XenDesktop) 的一项功能与 Lync 2013 和 Skype for Business 2015 和 2016 (完整客户端兼容，只需单击即可运行安装程序，或在虚拟桌面上安装的 2017 年 1 月 PU) 客户端发布 MSI 安装程序。</span><span class="sxs-lookup"><span data-stu-id="9d352-129">Citrix's VDI environment plugin (a feature of XenApp and XenDesktop) is compatible with Lync 2013 and Skype for Business 2015 and 2016 (Full clients using any click to run installer, or MSI installers released after January 2017 PU) clients installed on a virtual desktop.</span></span> <span data-ttu-id="9d352-130">其整体功能基于 Microsoft Lync VDI 插件，但适用于更广泛的客户端操作系统，包括 Windows 10、Macintosh 和 Linux。</span><span class="sxs-lookup"><span data-stu-id="9d352-130">Its overall functioning is based on the Microsoft Lync VDI plug-in, but works on a wider variety of client operating systems, including Windows 10, Macintosh, and Linux.</span></span>
  
<span data-ttu-id="9d352-131">可以在 Citrix 网站上找到功能和支持的技术的完整列表，网址为将 Microsoft Skype for Business 交付到 [XenApp 和 XenDesktop 用户](https://www.citrix.com/content/dam/citrix/en_us/documents/products-solutions/delivering-microsoft-lync-to-xenapp-and-xendesktop-users.pdf)。</span><span class="sxs-lookup"><span data-stu-id="9d352-131">A full list of features and supported technologies can be found on the Citrix website at [Delivering Microsoft Skype for Business to XenApp and XenDesktop Users](https://www.citrix.com/content/dam/citrix/en_us/documents/products-solutions/delivering-microsoft-lync-to-xenapp-and-xendesktop-users.pdf).</span></span>
  
<span data-ttu-id="9d352-132">有关详细信息，请查看以下链接：</span><span class="sxs-lookup"><span data-stu-id="9d352-132">Review the following links for more information:</span></span>
  
- <span data-ttu-id="9d352-133">Citrix [HDX RealTime Optimization Pack 2.1](https://docs.citrix.com/en-us/hdx-optimization/2-1.mdl)</span><span class="sxs-lookup"><span data-stu-id="9d352-133">Citrix [HDX RealTime Optimization Pack 2.1](https://docs.citrix.com/en-us/hdx-optimization/2-1.mdl)</span></span>
    
- [<span data-ttu-id="9d352-134">技术概述</span><span class="sxs-lookup"><span data-stu-id="9d352-134">Technical Overview</span></span>](https://docs.citrix.com/en-us/hdx-optimization/2-1/about.mdl)
    
- [<span data-ttu-id="9d352-135">CTX200279 Skype for Business 功能支持</span><span class="sxs-lookup"><span data-stu-id="9d352-135">CTX200279 Skype for Business Feature Support</span></span>](https://support.citrix.com/article/CTX200279)
    
## <a name="vmware-horizon-virtualization-pack"></a><span data-ttu-id="9d352-136">VMWare Horizon Virtualization Pack</span><span class="sxs-lookup"><span data-stu-id="9d352-136">VMWare Horizon Virtualization Pack</span></span>
<span data-ttu-id="9d352-137"><a name="Citrix_RT"> </a></span><span class="sxs-lookup"><span data-stu-id="9d352-137"><a name="Citrix_RT"> </a></span></span>

<span data-ttu-id="9d352-138">VMWare 的 VDI 环境解决方案与安装在虚拟桌面上的 Skype for Business 2015 和 2016 完整客户端兼容。</span><span class="sxs-lookup"><span data-stu-id="9d352-138">VMWare's VDI environment solution is compatible with Skype for Business 2015 and 2016 Full clients installed on a virtual desktop.</span></span> <span data-ttu-id="9d352-139">其整体功能基于 Microsoft Lync VDI 插件，但适用于更广泛的客户端操作系统，包括 Windows 10、Macintosh 和 Linux。</span><span class="sxs-lookup"><span data-stu-id="9d352-139">Its overall functioning is based on the Microsoft Lync VDI plug-in, but works on a wider variety of client operating systems, including Windows 10, Macintosh, and Linux.</span></span> 
  
<span data-ttu-id="9d352-140">有关功能和支持的技术的完整讨论，可以在 VMWare 网站上找到以下链接：</span><span class="sxs-lookup"><span data-stu-id="9d352-140">A full discussion of features and supported technologies can be found on the VMWare website at the following links:</span></span>
  
- [<span data-ttu-id="9d352-141">VMware Horizon 7.4 Horizon &amp; Client 4.7 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="9d352-141">What's New in VMware Horizon 7.4 &amp; Horizon Client 4.7</span></span>](https://blogs.vmware.com/euc/2018/01/vmware-horizon-7-4-horizon-client-4-7-whats-new.mdl)
    
- [<span data-ttu-id="9d352-142">Horizon Virtualization Pack for Skype for Business</span><span class="sxs-lookup"><span data-stu-id="9d352-142">Horizon Virtualization Pack for Skype for Business</span></span>](https://www.vmware.com/products/horizon/skype-for-business.mdl)
    
- [<span data-ttu-id="9d352-143">具有 VMWare Horizon 的 Microsoft Skype for Business</span><span class="sxs-lookup"><span data-stu-id="9d352-143">Microsoft Skype for Business With VMWare Horizon</span></span>](https://www.vmware.com/content/dam/digitalmarketing/vmware/en/pdf/products/horizon/vmware-skype-for-business-solution-brief.pdf)
    
## <a name="microsofts-lync-vdi-plug-in"></a><span data-ttu-id="9d352-144">Microsoft 的 Lync VDI 插件</span><span class="sxs-lookup"><span data-stu-id="9d352-144">Microsoft's Lync VDI plug-in</span></span>
<span data-ttu-id="9d352-145"><a name="Citrix_RT"> </a></span><span class="sxs-lookup"><span data-stu-id="9d352-145"><a name="Citrix_RT"> </a></span></span>

<span data-ttu-id="9d352-146">使用 Microsoft Lync VDI 插件解决方案，用户必须位于 Windows 计算机或瘦客户端上，并且已安装 Microsoft 的 Lync VDI 插件来处理来自虚拟桌面上的客户端的音频/视频流。</span><span class="sxs-lookup"><span data-stu-id="9d352-146">With the Microsoft Lync VDI plug-in solution, the user has to be on a Windows computer or thin client and have Microsoft's Lync VDI plugin installed to handle audio/video streams from the client on the virtual desktop.</span></span> <span data-ttu-id="9d352-147">用户将：</span><span class="sxs-lookup"><span data-stu-id="9d352-147">A user will:</span></span>
  
1. <span data-ttu-id="9d352-148">将音频/视频设备 (耳机或) 连接到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="9d352-148">Connect an audio/video device (like a headset or camera) to a local computer.</span></span>
    
2. <span data-ttu-id="9d352-149">使用 Lync 2013 或 Skype for Business 2015 客户端连接到远程虚拟桌面。</span><span class="sxs-lookup"><span data-stu-id="9d352-149">Connect to a remote virtual desktop with a Lync 2013 or Skype for Business 2015 client.</span></span>
    
3. <span data-ttu-id="9d352-150">在虚拟桌面上输入 Skype for Business 的凭据。</span><span class="sxs-lookup"><span data-stu-id="9d352-150">Enter credentials for Skype for Business on the virtual desktop.</span></span>
    
4. <span data-ttu-id="9d352-151">重新输入用户凭据以与本地 Windows 计算机或瘦客户端上的 Lync VDI 插件建立连接。</span><span class="sxs-lookup"><span data-stu-id="9d352-151">Re-enter user credentials to establish a connection with the Lync VDI plug-in on the local Windows computer or thin client.</span></span>
    
<span data-ttu-id="9d352-152">建立连接后，用户已准备好拨打和接听音频和视频呼叫。</span><span class="sxs-lookup"><span data-stu-id="9d352-152">After a connection is established, the user is ready to make and receive audio and video calls.</span></span> <span data-ttu-id="9d352-153">网络流量和虚拟桌面上的负载已最小化，因为本地计算机处理音频/视频处理。</span><span class="sxs-lookup"><span data-stu-id="9d352-153">Traffic on the network and the load on the virtual desktop are minimized, since the local computer handles the audio/video processing.</span></span>
  
<span data-ttu-id="9d352-154">Microsoft 的 Lync VDI 插件仅在某些 Windows 操作系统上受支持，并且仅支持 Lync 2013 或 Skype for Business 2015 客户端。</span><span class="sxs-lookup"><span data-stu-id="9d352-154">Microsoft's Lync VDI plug-in is only supported on certain Windows operating systems and only supports Lync 2013 or Skype for Business 2015 clients.</span></span> <span data-ttu-id="9d352-155">有关 [受支持的技术和限制的](vdi-environments.md#Supported_virt) 更多详细信息，请参阅支持的虚拟化技术和已知限制。</span><span class="sxs-lookup"><span data-stu-id="9d352-155">See [Supported virtualization technologies and known limitations](vdi-environments.md#Supported_virt) for more details on supported technologies and limitations.</span></span>
  
<span data-ttu-id="9d352-156">有关详细信息，请查看以下链接：</span><span class="sxs-lookup"><span data-stu-id="9d352-156">Review the following links for more information:</span></span>
  
- [<span data-ttu-id="9d352-157">支持的虚拟化技术和已知限制</span><span class="sxs-lookup"><span data-stu-id="9d352-157">Supported virtualization technologies and known limitations</span></span>](vdi-environments.md#Supported_virt)
    
- [<span data-ttu-id="9d352-158">Lync VDI 插件先决条件</span><span class="sxs-lookup"><span data-stu-id="9d352-158">Lync VDI plug-in prerequisites</span></span>](vdi-environments.md#VDI_prereq)
    
- [<span data-ttu-id="9d352-159">使用 Skype for Business Server 部署 Lync VDI 插件</span><span class="sxs-lookup"><span data-stu-id="9d352-159">Deploy the Lync VDI plug-in with Skype for Business Server</span></span>](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)
    
- <span data-ttu-id="9d352-160">Citrix 知识中心文章 [CTX138408](https://support.citrix.com/article/CTX138408)</span><span class="sxs-lookup"><span data-stu-id="9d352-160">Citrix Knowledge Center article [CTX138408](https://support.citrix.com/article/CTX138408)</span></span>
    
<span data-ttu-id="9d352-161">Microsoft Lync [VDI 2013 插件 (32 位) ](https://www.microsoft.com/download/details.aspx?id=35457) 或 [Microsoft Lync VDI 2013 ](https://www.microsoft.com/download/details.aspx?id=35454)插件 (64 位) 。</span><span class="sxs-lookup"><span data-stu-id="9d352-161">The Microsoft VDI plugin is available at [Microsoft Lync VDI 2013 plugin (32 bit)](https://www.microsoft.com/download/details.aspx?id=35457) or [Microsoft Lync VDI 2013 plugin (64 bit)](https://www.microsoft.com/download/details.aspx?id=35454).</span></span> <span data-ttu-id="9d352-162">Skype for Business 2015 客户端支持此插件，尽管名称已命名。</span><span class="sxs-lookup"><span data-stu-id="9d352-162">This plugin is supported with the Skype for Business 2015 client, despite the name.</span></span>
  
### <a name="supported-virtualization-technologies-and-known-limitations"></a><span data-ttu-id="9d352-163">支持的虚拟化技术和已知限制</span><span class="sxs-lookup"><span data-stu-id="9d352-163">Supported virtualization technologies and known limitations</span></span>
<span data-ttu-id="9d352-164"><a name="Supported_virt"> </a></span><span class="sxs-lookup"><span data-stu-id="9d352-164"><a name="Supported_virt"> </a></span></span>

<span data-ttu-id="9d352-165">Lync VDI 插件允许对受支持的虚拟化技术进行音频和视频呼叫。</span><span class="sxs-lookup"><span data-stu-id="9d352-165">The Lync VDI plug-in allows audio and video calling for supported virtualization technologies.</span></span> <span data-ttu-id="9d352-166">根据标准电话法规，还包括对 E911 的支持。</span><span class="sxs-lookup"><span data-stu-id="9d352-166">In compliance with standard telephone regulations, support for E911 is also included.</span></span> <span data-ttu-id="9d352-167">以下各节介绍 Lync VDI 插件支持的虚拟化技术和已知功能限制。</span><span class="sxs-lookup"><span data-stu-id="9d352-167">The following sections describe the virtualization technologies that are supported by the Lync VDI plug-in and the known feature limitations.</span></span>
  
#### <a name="support-for-virtualization-technologies"></a><span data-ttu-id="9d352-168">对虚拟化技术的支持</span><span class="sxs-lookup"><span data-stu-id="9d352-168">Support for Virtualization Technologies</span></span>

<span data-ttu-id="9d352-169">Lync VDI 插件支持个人虚拟桌面方案中的完整桌面远程会话，但在远程桌面会话方案中则不支持。</span><span class="sxs-lookup"><span data-stu-id="9d352-169">The Lync VDI plug-in supports full desktop remote sessions in the personal virtual desktop scenario, but not in the remote desktop session scenario.</span></span> <span data-ttu-id="9d352-170">这些方案可以描述如下：</span><span class="sxs-lookup"><span data-stu-id="9d352-170">These scenarios can be described as follows:</span></span>
  
- <span data-ttu-id="9d352-171">**支持：个性化虚拟桌面或虚拟桌面基础结构 (VDI) 。**</span><span class="sxs-lookup"><span data-stu-id="9d352-171">**Supported: Personalized Virtual Desktops or Virtual Desktop Infrastructure (VDI).**</span></span> <span data-ttu-id="9d352-172">在此方案中，每个用户登录到可自定义的虚拟桌面，并且能够将跨会话保留的文件保存在桌面上。</span><span class="sxs-lookup"><span data-stu-id="9d352-172">In this scenario, each user logs on to a customizable virtual desktop and is able to save files on the desktop that persist across sessions.</span></span> <span data-ttu-id="9d352-173">Microsoft 远程桌面服务和 VMware 范围视图是经过测试以与 Skype for Business 2015 一同使用的示例实现。</span><span class="sxs-lookup"><span data-stu-id="9d352-173">Microsoft Remote Desktop Services and VMware Horizon View are example implementations that have been tested for use with Skype for Business 2015.</span></span> <span data-ttu-id="9d352-174">正在进行验证的其他实现包括 Citrix XenDesktop。</span><span class="sxs-lookup"><span data-stu-id="9d352-174">Other implementations undergoing validation include Citrix XenDesktop.</span></span> <span data-ttu-id="9d352-175">有关供应商特定的 VDI 环境和已由 Microsoft 测试的客户端硬件的信息，请参阅 Microsoft Lync 限定的 [基础结构](https://go.microsoft.com/fwlink/?LinkID=313435)。</span><span class="sxs-lookup"><span data-stu-id="9d352-175">For information about vendor-specific VDI environments and client hardware that have been tested by Microsoft, see [Infrastructure qualified for Microsoft Lync](https://go.microsoft.com/fwlink/?LinkID=313435).</span></span>
    
- <span data-ttu-id="9d352-176">**不支持：远程桌面会话。**</span><span class="sxs-lookup"><span data-stu-id="9d352-176">**Not supported: Remote Desktop Sessions.**</span></span> <span data-ttu-id="9d352-177">在此方案中，每个用户登录到无法自定义的通用虚拟桌面会话。</span><span class="sxs-lookup"><span data-stu-id="9d352-177">In this scenario, each user logs on to a generic virtual desktop session that can't be customized.</span></span> <span data-ttu-id="9d352-178">示例包括 RDSH (和 Citrix Receiver) Citrix XenApp 的 Microsoft 远程桌面会话。</span><span class="sxs-lookup"><span data-stu-id="9d352-178">Examples include Microsoft Remote Desktop Sessions (RDSH) and Citrix XenApp combined with Citrix Receiver.</span></span>
    
<span data-ttu-id="9d352-179">Lync VDI 插件不支持其他虚拟化技术，如应用程序虚拟化，它允许使用应用程序，而无需在本地安装完整应用程序。</span><span class="sxs-lookup"><span data-stu-id="9d352-179">The Lync VDI plug-in does not support other virtualization technologies, such as application virtualization, which allows the use of an application without requiring installation of the full application locally.</span></span> <span data-ttu-id="9d352-180">示例实现包括 Citrix XenApp 和 Microsoft Application Virtualization (App-V) 。</span><span class="sxs-lookup"><span data-stu-id="9d352-180">Example implementations include Citrix XenApp and Microsoft Application Virtualization (App-V).</span></span> <span data-ttu-id="9d352-181">应用程序流、应用程序远程处理和混合虚拟化模式 (例如，不支持在完整桌面远程处理) 应用程序远程。</span><span class="sxs-lookup"><span data-stu-id="9d352-181">Application streaming, application remoting, and mixed virtualization modes (for example, application remoting in full desktop remoting) are not supported.</span></span>
  
<span data-ttu-id="9d352-182">Lync VDI 插件设计为使用独立于平台的 API，称为动态虚拟通道 (DVD) 。</span><span class="sxs-lookup"><span data-stu-id="9d352-182">The Lync VDI plug-in was designed to use platform-independent APIs called Dynamic Virtual Channels (DVCs).</span></span> <span data-ttu-id="9d352-183">对于未明确支持的方案，请参阅 VDI 解决方案提供商的支持声明。</span><span class="sxs-lookup"><span data-stu-id="9d352-183">For scenarios that are not explicitly supported, refer to support statements from the VDI solution provider.</span></span>
  
#### <a name="lync-vdi-plug-in-prerequisites"></a><span data-ttu-id="9d352-184">Lync VDI 插件先决条件</span><span class="sxs-lookup"><span data-stu-id="9d352-184">Lync VDI plug-in prerequisites</span></span>
<span data-ttu-id="9d352-185"><a name="VDI_prereq"> </a></span><span class="sxs-lookup"><span data-stu-id="9d352-185"><a name="VDI_prereq"> </a></span></span>

<span data-ttu-id="9d352-186">在 VDI 环境中，虚拟机和用户的本地计算机必须满足本节中概述的要求。</span><span class="sxs-lookup"><span data-stu-id="9d352-186">In a VDI environment, the virtual machines and the user's local computer must meet the requirements outlined in this section.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="9d352-187">虚拟化解决方案提供商可以提供有关如何安装和部署其环境的详细信息。</span><span class="sxs-lookup"><span data-stu-id="9d352-187">Your virtualization solution provider can supply details about how to install and deploy their environment.</span></span> <span data-ttu-id="9d352-188">有关部署基于 Hyper-V 和远程桌面服务的虚拟化环境的常规信息，请参阅 Microsoft 库中的以下[文章：Hyper-V](https://go.microsoft.com/fwlink/p/?linkid=247514) [，Windows Server 2008 R2](https://go.microsoft.com/fwlink/p/?linkid=247513)中的远程桌面服务</span><span class="sxs-lookup"><span data-stu-id="9d352-188">For general information about deploying a virtualized environment based on Hyper-V and Remote Desktop Services, see the following articles in the Microsoft Library: [Hyper-V](https://go.microsoft.com/fwlink/p/?linkid=247514), [Remote Desktop Services in Windows Server 2008 R2](https://go.microsoft.com/fwlink/p/?linkid=247513)</span></span> 
  
<span data-ttu-id="9d352-189">虚拟机必须使用具有最新 Service Pack 的 Windows 8、Windows 7 或 Windows Server 2008 R2 进行配置。</span><span class="sxs-lookup"><span data-stu-id="9d352-189">Virtual machines must be configured with Windows 8, Windows 7, or Windows Server 2008 R2 with the latest service packs.</span></span>
  
<span data-ttu-id="9d352-190">用户的本地计算机必须满足以下要求：</span><span class="sxs-lookup"><span data-stu-id="9d352-190">The user's local computer must meet the following requirements:</span></span>
  
- <span data-ttu-id="9d352-191">用户必须位于 Skype for Business Server 或 Lync Server 2013 上。</span><span class="sxs-lookup"><span data-stu-id="9d352-191">The user must be homed on Skype for Business Server or Lync Server 2013.</span></span>
    
- <span data-ttu-id="9d352-192">本地计算机必须运行 Windows Embedded Standard 7 SP1、Windows 7 SP1 或 Windows 8。</span><span class="sxs-lookup"><span data-stu-id="9d352-192">The local computer must be running Windows Embedded Standard 7 with SP1, Windows 7 with SP1, or Windows 8.</span></span>
    
- <span data-ttu-id="9d352-193">如果使用的是远程桌面服务，请选择 32 位或 64 位 Lync VDI 插件，以匹配本地计算机的操作系统。</span><span class="sxs-lookup"><span data-stu-id="9d352-193">If you're using Remote Desktop Services, choose the 32-bit or 64-bit Lync VDI plug-in to match the local computer's operating system.</span></span> <span data-ttu-id="9d352-194">本地计算机和虚拟机不需要具有 32 位或 64 位操作系统。</span><span class="sxs-lookup"><span data-stu-id="9d352-194">It's not required for both the local computer and the virtual machine to have 32-bit or 64-bit operating systems.</span></span> <span data-ttu-id="9d352-195">如果使用的是其他虚拟化解决方案或平台，请参考提供商的要求。</span><span class="sxs-lookup"><span data-stu-id="9d352-195">If you're using another virtualization solution or platform, refer to your provider's requirements.</span></span>
    
- <span data-ttu-id="9d352-196">本地计算机必须运行 [最新版本的远程桌面客户端](https://go.microsoft.com/fwlink/p/?LinkId=268032)。</span><span class="sxs-lookup"><span data-stu-id="9d352-196">The local computer must be running the [latest version of the remote desktop client](https://go.microsoft.com/fwlink/p/?LinkId=268032).</span></span> <span data-ttu-id="9d352-197">从 Microsoft 安装远程桌面服务客户端的最新更新，或安装虚拟化解决方案提供商的最新远程桌面客户端软件。</span><span class="sxs-lookup"><span data-stu-id="9d352-197">Install the latest updates of Remote Desktop Services client from Microsoft or the latest remote desktop client software from your virtualization solution provider.</span></span> 
    
- <span data-ttu-id="9d352-198">在本地计算机上，必须配置远程桌面客户端设置，以便在本地计算机上播放音频并禁用远程录制。</span><span class="sxs-lookup"><span data-stu-id="9d352-198">On the local computer, the remote desktop client settings must be configured so that audio plays on the local computer and remote recording is disabled.</span></span> <span data-ttu-id="9d352-199">若要在 Windows 中为远程桌面连接配置这些设置，请参阅下一节"配置远程桌面连接设置"。</span><span class="sxs-lookup"><span data-stu-id="9d352-199">To configure these settings for Remote Desktop Connection in Windows, see the next section, "To configure Remote Desktop Connection settings."</span></span> 
    
<span data-ttu-id="9d352-200">Microsoft Lync [VDI 2013 插件 (32 位) ](https://www.microsoft.com/download/details.aspx?id=35457) 或 [Microsoft Lync VDI 2013 ](https://www.microsoft.com/download/details.aspx?id=35454)插件 (64 位) 。</span><span class="sxs-lookup"><span data-stu-id="9d352-200">The Microsoft VDI plugin is available at [Microsoft Lync VDI 2013 plugin (32 bit)](https://www.microsoft.com/download/details.aspx?id=35457) or [Microsoft Lync VDI 2013 plugin (64 bit)](https://www.microsoft.com/download/details.aspx?id=35454).</span></span>
  
#### <a name="known-feature-limitations"></a><span data-ttu-id="9d352-201">已知功能限制</span><span class="sxs-lookup"><span data-stu-id="9d352-201">Known Feature Limitations</span></span>
<span data-ttu-id="9d352-202"><a name="VDI_prereq"> </a></span><span class="sxs-lookup"><span data-stu-id="9d352-202"><a name="VDI_prereq"> </a></span></span>

<span data-ttu-id="9d352-203">以下是在 VDI 环境中使用 Skype for Business 2015 客户端时已知的限制：</span><span class="sxs-lookup"><span data-stu-id="9d352-203">The following are known limitations when you use the Skype for Business 2015 client in a VDI environment:</span></span>
  
<span data-ttu-id="9d352-204">对呼叫委派和响应组代理匿名化功能的支持有限。</span><span class="sxs-lookup"><span data-stu-id="9d352-204">There is limited support for Call Delegation and Response Group Agent Anonymization features.</span></span>
  
<span data-ttu-id="9d352-205">不支持以下功能：</span><span class="sxs-lookup"><span data-stu-id="9d352-205">There is no support for the following features:</span></span>
  
- <span data-ttu-id="9d352-206">集成音频设备和视频设备优化页。</span><span class="sxs-lookup"><span data-stu-id="9d352-206">Integrated Audio Device and Video Device tuning pages.</span></span>
    
- <span data-ttu-id="9d352-207">多视图视频。</span><span class="sxs-lookup"><span data-stu-id="9d352-207">Multiple-view video.</span></span>
    
- <span data-ttu-id="9d352-208">录制对话。</span><span class="sxs-lookup"><span data-stu-id="9d352-208">Recording of conversations.</span></span>
    
- <span data-ttu-id="9d352-209">匿名加入会议 (即，加入由组织托管的 Skype for Business 会议，而组织不与组织联盟) 。</span><span class="sxs-lookup"><span data-stu-id="9d352-209">Joining meetings anonymously (that is, joining Skype for Business meetings hosted by an organization that does not federate with your organization).</span></span>
    
- <span data-ttu-id="9d352-210">将 Lync VDI 插件与 Lync Phone Edition 设备一同使用。</span><span class="sxs-lookup"><span data-stu-id="9d352-210">Using the Lync VDI plug-in along with a Lync Phone Edition device.</span></span>
    
- <span data-ttu-id="9d352-211">发生网络中断时的呼叫连续性。</span><span class="sxs-lookup"><span data-stu-id="9d352-211">Call continuity in case of a network outage.</span></span>
    
- <span data-ttu-id="9d352-212">自定义铃声和保持音乐功能。</span><span class="sxs-lookup"><span data-stu-id="9d352-212">Customized ringtones and music-on-hold features.</span></span>
    
<span data-ttu-id="9d352-213">Microsoft 365 或 Office 365 环境中不支持 Lync VDI 插件。</span><span class="sxs-lookup"><span data-stu-id="9d352-213">The Lync VDI plug-in is not supported in Microsoft 365 or Office 365 environments.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9d352-214">Citrix RealTime Optimization Pack 支持 Microsoft 365 和 Office 365。</span><span class="sxs-lookup"><span data-stu-id="9d352-214">The Citrix RealTime Optimization Pack does support Microsoft 365 and Office 365.</span></span> <span data-ttu-id="9d352-215">对于基于 Citrix 的虚拟环境，请查看 Citrix 的技术 [概述](https://docs.citrix.com/en-us/hdx-optimization/2-0/hdx-realtime-optimization-pack-about.mdl) 文档，了解受支持的功能和版本列表。</span><span class="sxs-lookup"><span data-stu-id="9d352-215">For Citrix-based virtual environments, review Citrix's [Technical Overview](https://docs.citrix.com/en-us/hdx-optimization/2-0/hdx-realtime-optimization-pack-about.mdl) documentation for the list of supported features and versions.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9d352-216">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9d352-216">See also</span></span>
<span data-ttu-id="9d352-217"><a name="Citrix_RT"> </a></span><span class="sxs-lookup"><span data-stu-id="9d352-217"><a name="Citrix_RT"> </a></span></span>

[<span data-ttu-id="9d352-218">使用 Skype for Business Server 部署 Lync VDI 插件</span><span class="sxs-lookup"><span data-stu-id="9d352-218">Deploy the Lync VDI plug-in with Skype for Business Server</span></span>](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)

