---
title: 在 VDI 环境中规划 Skype for Business
author: lanachin
ms.author: v-lanac
ms.reviewer: krishra
manager: serdars
ms.date: 1/9/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ea68414b-bb7e-483a-b731-b6b5a44372b1
description: 本主题讨论使用 Skype for Business 连接到远程虚拟桌面时的规划注意事项。
ms.openlocfilehash: ac4a0d214edf33c6966b7fcd8fa2ce33114dc505
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33886443"
---
# <a name="plan-for-skype-for-business-in-vdi-environments"></a><span data-ttu-id="17e03-103">在 VDI 环境中规划 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="17e03-103">Plan for Skype for Business in VDI environments</span></span>
 
<span data-ttu-id="17e03-104">本主题讨论使用 Skype for Business 连接到远程虚拟桌面时的规划注意事项。</span><span class="sxs-lookup"><span data-stu-id="17e03-104">This topic discusses planning considerations for using Skype for Business while connecting to a remote virtual desktop.</span></span> 
  
<span data-ttu-id="17e03-105">某些对安全问题及合规性问题特别敏感的组织使用虚拟桌面基础结构 (Virtual Desktop Infrastructure, VDI) 环境。</span><span class="sxs-lookup"><span data-stu-id="17e03-105">A Virtual Desktop Infrastructure (VDI) environment is used in some organizations where security and compliance issues are especially sensitive.</span></span> <span data-ttu-id="17e03-106">这些组织的用户在虚拟桌面上进行工作，在该虚拟桌面上，用户的所有桌面应用程序和文件均使用远程桌面服务或类似的远程连接。</span><span class="sxs-lookup"><span data-stu-id="17e03-106">Their users do their work on a virtual desktop with all their desktop applications and files using Remote Desktop Services or a similar remote connection.</span></span> <span data-ttu-id="17e03-107">For Business 与使用 Skype 完整的音频和视频连接这样需要过重的音频和视频处理客户端上驻留在虚拟机上。</span><span class="sxs-lookup"><span data-stu-id="17e03-107">Using Skype for Business with full audio and video on a connection like that requires heavy loads of audio and video processing on the client homed on a virtual desktop.</span></span> <span data-ttu-id="17e03-108">其他 VDI 插件软件是可用的减轻到最终用户的本地计算机的处理和减少了虚拟桌面上的负载。</span><span class="sxs-lookup"><span data-stu-id="17e03-108">Additional VDI plug-in software is available that offloads that processing to the end user's local machine, and reduces the load on the virtual desktop.</span></span>
  
<span data-ttu-id="17e03-109">为 VDI 插件的组件，提供 Microsoft、 Citrix 或 VMWare 提供了三个解决方案。</span><span class="sxs-lookup"><span data-stu-id="17e03-109">There are three solutions available for the VDI plug-in component, offered by Microsoft, Citrix, or VMWare.</span></span> <span data-ttu-id="17e03-110">对于新的部署，Microsoft 建议使用 Citrix HDX 实时 Optimization Pack 解决方案或 VMWare 范围虚拟化包。</span><span class="sxs-lookup"><span data-stu-id="17e03-110">For new deployments, Microsoft recommends using either the Citrix HDX RealTime Optimization Pack solution or the VMWare Horizon Virtualization Pack.</span></span> <span data-ttu-id="17e03-111">原始 Lync VDI 插件仍然支持生命周期的其余部分。</span><span class="sxs-lookup"><span data-stu-id="17e03-111">The original Lync VDI Plug-in is still supported for the remainder of its lifecycle.</span></span>
  
- <span data-ttu-id="17e03-112">**Lync VDI 插件**为 Lync 2013 开发的在虚拟机上运行的业务 2015年客户端的 Lync 2013 或 Skype 兼容。</span><span class="sxs-lookup"><span data-stu-id="17e03-112">The **Lync VDI plug-in** was developed for Lync 2013 and is compatible with either the Lync 2013 or Skype for Business 2015 client running on a virtual desktop.</span></span> <span data-ttu-id="17e03-113">它是一个独立的应用程序的本地计算机上安装并允许有虚拟桌面上的客户端使用本地音频和视频设备。</span><span class="sxs-lookup"><span data-stu-id="17e03-113">It's a stand-alone application that installs on the local computer and allows the use of local audio and video devices with a client on a virtual desktop.</span></span> <span data-ttu-id="17e03-114">插件不需要 Skype 业务客户端安装本地计算机或瘦客户端，它必须运行 Windows 7、 Windows 8 或 Windows Server 2008 操作系统上。</span><span class="sxs-lookup"><span data-stu-id="17e03-114">The plug-in does not require a Skype for Business client to be installed on the local computer or thin client, which must run Windows 7, Windows 8, or Windows Server 2008 operating systems.</span></span> <span data-ttu-id="17e03-115">(使用这些操作系统和支持 Microsoft 瘦客户端设备包括： Dell Wyse Z90D7、 Dell Wyse R90L7、 Dell Wyse X90m7、 HP t610 和 HP t5740e。)仍然支持此插件，但没有将来的更新计划。</span><span class="sxs-lookup"><span data-stu-id="17e03-115">(Thin client devices using these operating systems and supported by Microsoft include: Dell Wyse Z90D7, Dell Wyse R90L7, Dell Wyse X90m7, HP t610 and HP t5740e.) This plug-in is still supported, but no future updates are planned.</span></span> <span data-ttu-id="17e03-116">对于基于 Citrix 虚拟环境中，建议 Citrix 实时 Optimization Pack。</span><span class="sxs-lookup"><span data-stu-id="17e03-116">For Citrix-based virtual environments, the Citrix RealTime Optimization Pack is recommended.</span></span>
    
- <span data-ttu-id="17e03-117">**Citrix 实时 Optimization Pack**上 Lync VDI 插件生成并与 Lync 2013 或 Skype 适用于业务 2016年客户端，虚拟机上。</span><span class="sxs-lookup"><span data-stu-id="17e03-117">The **Citrix RealTime Optimization Pack** builds on the Lync VDI plug-in and works with Lync 2013 or Skype for Business 2016 clients on a virtual desktop.</span></span> <span data-ttu-id="17e03-118">该解决方案由 Citrix 和 Microsoft 共同开发并在原始 VDI 插件的基础上进行了改进。</span><span class="sxs-lookup"><span data-stu-id="17e03-118">It was co-developed by Citrix and Microsoft to improve upon the original VDI Plug-in.</span></span> <span data-ttu-id="17e03-119">该解决方案可以在安装在使用 Windows 和非 Windows 操作系统（包括 Windows 10、Mac 和 Linux）的客户端上。</span><span class="sxs-lookup"><span data-stu-id="17e03-119">It can be installed on clients with Windows and non-Windows operating systems (including Windows 10, Mac and Linux).</span></span> <span data-ttu-id="17e03-120">两个组件组成： 实时连接器 （其中已安装在虚拟桌面上） 和实时媒体引擎 （这最终用户的本地计算机上安装）。</span><span class="sxs-lookup"><span data-stu-id="17e03-120">It consists of two components: the RealTime Connector (which is installed on the virtual desktop) and the RealTime Media Engine (which is installed on the end user's local machine).</span></span> <span data-ttu-id="17e03-121">这两个组件允许用户的本地计算机 Skype 用于业务客户端运行虚拟桌面上与 A / V 处理移动到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="17e03-121">These two components allow the user's local computer to use the Skype for Business client running on the virtual desktop with the A/V processing moved to the local computer.</span></span> <span data-ttu-id="17e03-122">对于基于 Citrix 的虚拟桌面环境，建议使用 Citrix RealTime Optimization Pack，Microsoft 计划为该解决方案提供进一步支持。</span><span class="sxs-lookup"><span data-stu-id="17e03-122">For Citrix-based virtual desktop environments, the Citrix RealTime Optimization Pack is recommended, and further support is planned.</span></span>
    
- <span data-ttu-id="17e03-123">业务，开发 VMWare，与协作的 Skype **VMWare 范围虚拟化包**允许您在虚拟桌面提供 for Business 的 Skype，同时提供了出色的用户体验。</span><span class="sxs-lookup"><span data-stu-id="17e03-123">The **VMWare Horizon Virtualization Pack** for Skype for Business, developed in collaboration with VMWare, allows you to deliver Skype for Business in a virtual desktop while delivering a great user experience.</span></span> <span data-ttu-id="17e03-124">利用在客户端优化的解决方案，创建与客户端终结点提供媒体的媒体引擎的解决方案的工作原理卸载音频和视频呼叫的功能。</span><span class="sxs-lookup"><span data-stu-id="17e03-124">The solution works by leveraging a media engine at the client to create an optimized solution, with the client endpoint providing media offload capabilities for audio and video calls.</span></span> <span data-ttu-id="17e03-125">此解决方案可提供音频和视频，或者直接之间的一对一协作终结点或卸载它到中央多点控制单元 (MCU) 的多方会议呼叫或会议。</span><span class="sxs-lookup"><span data-stu-id="17e03-125">This solution that can deliver audio and video either directly between endpoints for one-on-one collaboration, or offload it to a central Multipoint Control Unit (MCU) for multiparty conference calls or meetings.</span></span>
    
> [!NOTE]
> <span data-ttu-id="17e03-126">业务基本客户端的 Skype 不支持与 Citrix HDX 实时 Optimization Pack 或 VMWare 范围虚拟化包。</span><span class="sxs-lookup"><span data-stu-id="17e03-126">The Skype for Business Basic clients are not supported with the Citrix HDX RealTime Optimization Pack or the VMWare Horizon Virtualization Pack.</span></span> 
  
## <a name="citrix-hdx-realtime-optimization-pack"></a><span data-ttu-id="17e03-127">Citrix HDX RealTime Optimization Pack</span><span class="sxs-lookup"><span data-stu-id="17e03-127">Citrix HDX RealTime Optimization Pack</span></span>
<span data-ttu-id="17e03-128"><a name="Citrix_RT"> </a></span><span class="sxs-lookup"><span data-stu-id="17e03-128"></span></span>

<span data-ttu-id="17e03-129">是与 Lync 2013 和 Skype 业务 2015年和上一个虚拟安装的 2016年 （使用任何单击运行安装程序或 MSI 安装程序后年 1 月版公共更新 2017 年完整客户端） 客户端兼容 Citrix 的 VDI 环境插件 （XenApp 和 XenDesktop 功能）桌面。</span><span class="sxs-lookup"><span data-stu-id="17e03-129">Citrix's VDI environment plugin (a feature of XenApp and XenDesktop) is compatible with Lync 2013 and Skype for Business 2015 and 2016 (Full clients using any click to run installer, or MSI installers released after January 2017 PU) clients installed on a virtual desktop.</span></span> <span data-ttu-id="17e03-130">其全部功能取决于 Microsoft Lync VDI 插件，但更广泛的客户端操作系统，包括 Windows 10、 Macintosh 和 Linux 上的工作原理。</span><span class="sxs-lookup"><span data-stu-id="17e03-130">Its overall functioning is based on the Microsoft Lync VDI plug-in, but works on a wider variety of client operating systems, including Windows 10, Macintosh, and Linux.</span></span>
  
<span data-ttu-id="17e03-131">可以在[for Business XenApp 和 XenDesktop 用户提供 Microsoft Skype](https://www.citrix.com/content/dam/citrix/en_us/documents/products-solutions/delivering-microsoft-lync-to-xenapp-and-xendesktop-users.pdf)Citrix 网站上找到的功能和支持的技术的完整列表。</span><span class="sxs-lookup"><span data-stu-id="17e03-131">A full list of features and supported technologies can be found on the Citrix website at [Delivering Microsoft Skype for Business to XenApp and XenDesktop Users](https://www.citrix.com/content/dam/citrix/en_us/documents/products-solutions/delivering-microsoft-lync-to-xenapp-and-xendesktop-users.pdf).</span></span>
  
<span data-ttu-id="17e03-132">有关详细信息，请访问以下链接：</span><span class="sxs-lookup"><span data-stu-id="17e03-132">Review the following links for more information:</span></span>
  
- <span data-ttu-id="17e03-133">Citrix [HDX 实时 Optimization Pack 2.1](https://docs.citrix.com/en-us/hdx-optimization/2-1.mdl)</span><span class="sxs-lookup"><span data-stu-id="17e03-133">Citrix [HDX RealTime Optimization Pack 2.1](https://docs.citrix.com/en-us/hdx-optimization/2-1.mdl)</span></span>
    
- [<span data-ttu-id="17e03-134">技术概述</span><span class="sxs-lookup"><span data-stu-id="17e03-134">Technical Overview </span></span>](https://docs.citrix.com/en-us/hdx-optimization/2-1/about.mdl)
    
- [<span data-ttu-id="17e03-135">CTX200279 Skype 业务功能支持</span><span class="sxs-lookup"><span data-stu-id="17e03-135">CTX200279 Skype for Business Feature Support</span></span>](https://support.citrix.com/article/CTX200279)
    
## <a name="vmware-horizon-virtualization-pack"></a><span data-ttu-id="17e03-136">VMWare 范围虚拟化包</span><span class="sxs-lookup"><span data-stu-id="17e03-136">VMWare Horizon Virtualization Pack</span></span>
<span data-ttu-id="17e03-137"><a name="Citrix_RT"> </a></span><span class="sxs-lookup"><span data-stu-id="17e03-137"></span></span>

<span data-ttu-id="17e03-138">与业务 2015年和 2016年完整的客户端安装在虚拟机上的 Skype 兼容 VMWare 的 VDI 环境解决方案。</span><span class="sxs-lookup"><span data-stu-id="17e03-138">VMWare's VDI environment solution is compatible with Skype for Business 2015 and 2016 Full clients installed on a virtual desktop.</span></span> <span data-ttu-id="17e03-139">其全部功能取决于 Microsoft Lync VDI 插件，但更广泛的客户端操作系统，包括 Windows 10、 Macintosh 和 Linux 上的工作原理。</span><span class="sxs-lookup"><span data-stu-id="17e03-139">Its overall functioning is based on the Microsoft Lync VDI plug-in, but works on a wider variety of client operating systems, including Windows 10, Macintosh, and Linux.</span></span> 
  
<span data-ttu-id="17e03-140">可通过以下链接 VMWare 网站上找到的功能和支持的技术的完整讨论：</span><span class="sxs-lookup"><span data-stu-id="17e03-140">A full discussion of features and supported technologies can be found on the VMWare website at the following links:</span></span>
  
- [<span data-ttu-id="17e03-141">What's New in VMware 范围 7.4&amp;范围客户端 4.7</span><span class="sxs-lookup"><span data-stu-id="17e03-141">What's New in VMware Horizon 7.4 &amp; Horizon Client 4.7</span></span>](https://blogs.vmware.com/euc/2018/01/vmware-horizon-7-4-horizon-client-4-7-whats-new.mdl)
    
- [<span data-ttu-id="17e03-142">范围虚拟化包 Skype 业务</span><span class="sxs-lookup"><span data-stu-id="17e03-142">Horizon Virtualization Pack for Skype for Business</span></span>](https://www.vmware.com/products/horizon/skype-for-business.mdl)
    
- [<span data-ttu-id="17e03-143">Microsoft Skype for Business With VMWare 范围</span><span class="sxs-lookup"><span data-stu-id="17e03-143">Microsoft Skype for Business With VMWare Horizon</span></span>](https://www.vmware.com/content/dam/digitalmarketing/vmware/en/pdf/products/horizon/vmware-skype-for-business-solution-brief.pdf)
    
## <a name="microsofts-lync-vdi-plug-in"></a><span data-ttu-id="17e03-144">Microsoft Lync VDI 插件</span><span class="sxs-lookup"><span data-stu-id="17e03-144">Microsoft's Lync VDI plug-in</span></span>
<span data-ttu-id="17e03-145"><a name="Citrix_RT"> </a></span><span class="sxs-lookup"><span data-stu-id="17e03-145"></span></span>

<span data-ttu-id="17e03-146">Microsoft Lync VDI 插件解决方案后，用户必须是 Windows 计算机或瘦客户端上，并且具有 Microsoft Lync VDI 插件才能处理从虚拟桌面客户端的音频/视频流。</span><span class="sxs-lookup"><span data-stu-id="17e03-146">With the Microsoft Lync VDI plug-in solution, the user has to be on a Windows computer or thin client and have Microsoft's Lync VDI plugin installed to handle audio/video streams from the client on the virtual desktop.</span></span> <span data-ttu-id="17e03-147">用户需要执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="17e03-147">A user will:</span></span>
  
1. <span data-ttu-id="17e03-148">将音频/视频设备（例如耳机或摄像头）连接到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="17e03-148">Connect an audio/video device (like a headset or camera) to a local computer.</span></span>
    
2. <span data-ttu-id="17e03-149">连接到业务 2015年客户端与 Lync 2013 或 Skype 远程虚拟桌面。</span><span class="sxs-lookup"><span data-stu-id="17e03-149">Connect to a remote virtual desktop with a Lync 2013 or Skype for Business 2015 client.</span></span>
    
3. <span data-ttu-id="17e03-150">在虚拟桌面上 for Business 的 Skype 输入凭据。</span><span class="sxs-lookup"><span data-stu-id="17e03-150">Enter credentials for Skype for Business on the virtual desktop.</span></span>
    
4. <span data-ttu-id="17e03-151">重新输入用于建立与 Lync VDI 插件的本地 Windows 计算机或瘦客户端上的连接的用户凭据。</span><span class="sxs-lookup"><span data-stu-id="17e03-151">Re-enter user credentials to establish a connection with the Lync VDI plug-in on the local Windows computer or thin client.</span></span>
    
<span data-ttu-id="17e03-p109">建立连接之后，用户已准备好发出和接收音频调用及视频调用。网络流量和虚拟桌面负载将会最大程度减少，因为音频/视频处理在本地计算机上进行。</span><span class="sxs-lookup"><span data-stu-id="17e03-p109">After a connection is established, the user is ready to make and receive audio and video calls. Traffic on the network and the load on the virtual desktop are minimized, since the local computer handles the audio/video processing.</span></span>
  
<span data-ttu-id="17e03-154">Microsoft Lync VDI 插件仅支持某些 Windows 操作系统和业务 2015年客户端仅支持 Lync 2013 或 Skype。</span><span class="sxs-lookup"><span data-stu-id="17e03-154">Microsoft's Lync VDI plug-in is only supported on certain Windows operating systems and only supports Lync 2013 or Skype for Business 2015 clients.</span></span> <span data-ttu-id="17e03-155">有关支持的技术和限制的更多详细信息，请参阅[支持的虚拟化技术和已知限制](vdi-environments.md#Supported_virt)。</span><span class="sxs-lookup"><span data-stu-id="17e03-155">See [Supported virtualization technologies and known limitations](vdi-environments.md#Supported_virt) for more details on supported technologies and limitations.</span></span>
  
<span data-ttu-id="17e03-156">有关详细信息，请访问以下链接：</span><span class="sxs-lookup"><span data-stu-id="17e03-156">Review the following links for more information:</span></span>
  
- [<span data-ttu-id="17e03-157">支持的虚拟化技术和已知限制</span><span class="sxs-lookup"><span data-stu-id="17e03-157">Supported virtualization technologies and known limitations</span></span>](vdi-environments.md#Supported_virt)
    
- [<span data-ttu-id="17e03-158">Lync VDI 插件先决条件</span><span class="sxs-lookup"><span data-stu-id="17e03-158">Lync VDI plug-in prerequisites</span></span>](vdi-environments.md#VDI_prereq)
    
- [<span data-ttu-id="17e03-159">部署 Lync VDI 插件与 Skype 业务服务器</span><span class="sxs-lookup"><span data-stu-id="17e03-159">Deploy the Lync VDI plug-in with Skype for Business Server</span></span>](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)
    
- <span data-ttu-id="17e03-160">Citrix 知识中心文章[CTX138408](https://support.citrix.com/article/CTX138408)</span><span class="sxs-lookup"><span data-stu-id="17e03-160">Citrix Knowledge Center article [CTX138408](https://support.citrix.com/article/CTX138408)</span></span>
    
<span data-ttu-id="17e03-161">可在[Microsoft Lync VDI 2013 插件 （32 位）](https://www.microsoft.com/en-us/download/details.aspx?id=35457)或[Microsoft Lync VDI 2013 插件 （64 位）](https://www.microsoft.com/en-us/download/details.aspx?id=35454)Microsoft VDI 插件。</span><span class="sxs-lookup"><span data-stu-id="17e03-161">The Microsoft VDI plugin is available at [Microsoft Lync VDI 2013 plugin (32 bit)](https://www.microsoft.com/en-us/download/details.aspx?id=35457) or [Microsoft Lync VDI 2013 plugin (64 bit)](https://www.microsoft.com/en-us/download/details.aspx?id=35454).</span></span> <span data-ttu-id="17e03-162">与业务 2015年客户端，尽管名称为 Skype 支持此插件。</span><span class="sxs-lookup"><span data-stu-id="17e03-162">This plugin is supported with the Skype for Business 2015 client, despite the name.</span></span>
  
### <a name="supported-virtualization-technologies-and-known-limitations"></a><span data-ttu-id="17e03-163">支持的虚拟化技术和已知限制</span><span class="sxs-lookup"><span data-stu-id="17e03-163">Supported virtualization technologies and known limitations</span></span>
<span data-ttu-id="17e03-164"><a name="Supported_virt"> </a></span><span class="sxs-lookup"><span data-stu-id="17e03-164"></span></span>

<span data-ttu-id="17e03-165">允许 Lync VDI 插件的音频和视频呼叫支持虚拟化技术。</span><span class="sxs-lookup"><span data-stu-id="17e03-165">The Lync VDI plug-in allows audio and video calling for supported virtualization technologies.</span></span> <span data-ttu-id="17e03-166">符合标准电话法规获得 E911 还包括支持。</span><span class="sxs-lookup"><span data-stu-id="17e03-166">In compliance with standard telephone regulations, support for E911 is also included.</span></span> <span data-ttu-id="17e03-167">以下各节介绍虚拟化技术支持的 Lync VDI 插件和功能的已知的限制。</span><span class="sxs-lookup"><span data-stu-id="17e03-167">The following sections describe the virtualization technologies that are supported by the Lync VDI plug-in and the known feature limitations.</span></span>
  
#### <a name="support-for-virtualization-technologies"></a><span data-ttu-id="17e03-168">虚拟化技术支持</span><span class="sxs-lookup"><span data-stu-id="17e03-168">Support for Virtualization Technologies</span></span>

<span data-ttu-id="17e03-169">Lync VDI 插件支持完整桌面远程会话在个人虚拟桌面方案中，但不能在远程桌面会话方案。</span><span class="sxs-lookup"><span data-stu-id="17e03-169">The Lync VDI plug-in supports full desktop remote sessions in the personal virtual desktop scenario, but not in the remote desktop session scenario.</span></span> <span data-ttu-id="17e03-170">这些方案如下所述：</span><span class="sxs-lookup"><span data-stu-id="17e03-170">These scenarios can be described as follows:</span></span>
  
- <span data-ttu-id="17e03-171">**支持：个性化虚拟桌面或虚拟桌面基础结构 (VDI)。**</span><span class="sxs-lookup"><span data-stu-id="17e03-171">**Supported: Personalized Virtual Desktops or Virtual Desktop Infrastructure (VDI).**</span></span> <span data-ttu-id="17e03-172">在此方案中，每个用户都登录到可自定义的虚拟桌面，并且能够将文件保存到桌面上，这些文件跨会话持续存在。</span><span class="sxs-lookup"><span data-stu-id="17e03-172">In this scenario, each user logs on to a customizable virtual desktop and is able to save files on the desktop that persist across sessions.</span></span> <span data-ttu-id="17e03-173">Microsoft 远程桌面服务和 VMware 范围视图是用于测试与业务 2015年的 Skype 的示例实现的。</span><span class="sxs-lookup"><span data-stu-id="17e03-173">Microsoft Remote Desktop Services and VMware Horizon View are example implementations that have been tested for use with Skype for Business 2015.</span></span> <span data-ttu-id="17e03-174">其他正在进行验证的实施包括 Citrix XenDesktop。</span><span class="sxs-lookup"><span data-stu-id="17e03-174">Other implementations undergoing validation include Citrix XenDesktop.</span></span> <span data-ttu-id="17e03-175">供应商特定 VDI 环境和由 Microsoft 已经过测试的客户端硬件有关的信息，请参阅[基础结构符合 Microsoft Lync 要求](https://go.microsoft.com/fwlink/?LinkID=313435)。</span><span class="sxs-lookup"><span data-stu-id="17e03-175">For information about vendor-specific VDI environments and client hardware that have been tested by Microsoft, see [Infrastructure qualified for Microsoft Lync](https://go.microsoft.com/fwlink/?LinkID=313435).</span></span>
    
- <span data-ttu-id="17e03-176">**不支持：远程桌面会话。**</span><span class="sxs-lookup"><span data-stu-id="17e03-176">**Not supported: Remote Desktop Sessions.**</span></span> <span data-ttu-id="17e03-177">在此方案中，每个用户都登录到无法自定义的常规虚拟桌面会话。</span><span class="sxs-lookup"><span data-stu-id="17e03-177">In this scenario, each user logs on to a generic virtual desktop session that can't be customized.</span></span> <span data-ttu-id="17e03-178">示例包括 Microsoft 远程桌面会话 (RDSH) 和 Citrix XenApp 结合使用 Citrix 接收器。</span><span class="sxs-lookup"><span data-stu-id="17e03-178">Examples include Microsoft Remote Desktop Sessions (RDSH) and Citrix XenApp combined with Citrix Receiver.</span></span>
    
<span data-ttu-id="17e03-179">Lync VDI 插件不支持其他虚拟化技术，如应用程序虚拟化，而不需要本地完整的应用程序安装允许应用程序的使用。</span><span class="sxs-lookup"><span data-stu-id="17e03-179">The Lync VDI plug-in does not support other virtualization technologies, such as application virtualization, which allows the use of an application without requiring installation of the full application locally.</span></span> <span data-ttu-id="17e03-180">示例实现包括 Citrix XenApp 和 Microsoft Application Virtualization (APP-V)。</span><span class="sxs-lookup"><span data-stu-id="17e03-180">Example implementations include Citrix XenApp and Microsoft Application Virtualization (App-V).</span></span> <span data-ttu-id="17e03-181">不支持应用程序流式传输、 应用程序远程处理和混合虚拟化模式 （例如，应用程序中的远程处理完整桌面远程处理）。</span><span class="sxs-lookup"><span data-stu-id="17e03-181">Application streaming, application remoting, and mixed virtualization modes (for example, application remoting in full desktop remoting) are not supported.</span></span>
  
<span data-ttu-id="17e03-182">Lync VDI 插件旨在使用独立于平台的 Api 调用动态虚拟通道 (DVCs)。</span><span class="sxs-lookup"><span data-stu-id="17e03-182">The Lync VDI plug-in was designed to use platform-independent APIs called Dynamic Virtual Channels (DVCs).</span></span> <span data-ttu-id="17e03-183">不明确支持的方案，请参阅支持从 VDI 解决方案提供商的语句。</span><span class="sxs-lookup"><span data-stu-id="17e03-183">For scenarios that are not explicitly supported, refer to support statements from the VDI solution provider.</span></span>
  
#### <a name="lync-vdi-plug-in-prerequisites"></a><span data-ttu-id="17e03-184">Lync VDI 插件先决条件</span><span class="sxs-lookup"><span data-stu-id="17e03-184">Lync VDI plug-in prerequisites</span></span>
<span data-ttu-id="17e03-185"><a name="VDI_prereq"> </a></span><span class="sxs-lookup"><span data-stu-id="17e03-185"></span></span>

<span data-ttu-id="17e03-186">在 VDI 环境中，虚拟机和用户的本地计算机必须满足本节中所述的要求。</span><span class="sxs-lookup"><span data-stu-id="17e03-186">In a VDI environment, the virtual machines and the user's local computer must meet the requirements outlined in this section.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="17e03-187">虚拟化解决方案提供商会提供有关如何安装和部署其环境的详细信息。</span><span class="sxs-lookup"><span data-stu-id="17e03-187">Your virtualization solution provider can supply details about how to install and deploy their environment.</span></span> <span data-ttu-id="17e03-188">有关部署基于 HYPER-V 和远程桌面服务的虚拟化的环境的常规信息，请参阅 Microsoft 库中的以下文章： [HYPER-V](https://go.microsoft.com/fwlink/p/?linkid=247514)、 [Windows Server 2008 R2 中的远程桌面服务](https://go.microsoft.com/fwlink/p/?linkid=247513)</span><span class="sxs-lookup"><span data-stu-id="17e03-188">For general information about deploying a virtualized environment based on Hyper-V and Remote Desktop Services, see the following articles in the Microsoft Library: [Hyper-V](https://go.microsoft.com/fwlink/p/?linkid=247514), [Remote Desktop Services in Windows Server 2008 R2](https://go.microsoft.com/fwlink/p/?linkid=247513)</span></span> 
  
<span data-ttu-id="17e03-189">带有最新的 service pack，虚拟机必须配置与 Windows 8、 Windows 7 或 Windows Server 2008 R2。</span><span class="sxs-lookup"><span data-stu-id="17e03-189">Virtual machines must be configured with Windows 8, Windows 7, or Windows Server 2008 R2 with the latest service packs.</span></span>
  
<span data-ttu-id="17e03-190">用户的本地计算机必须满足以下要求：</span><span class="sxs-lookup"><span data-stu-id="17e03-190">The user's local computer must meet the following requirements:</span></span>
  
- <span data-ttu-id="17e03-191">用户必须驻留在 Skype，业务服务器或 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="17e03-191">The user must be homed on Skype for Business Server or Lync Server 2013.</span></span>
    
- <span data-ttu-id="17e03-192">本地计算机必须运行 Windows Embedded Standard 7 SP1、 Windows 7 SP1 或 Windows 8。</span><span class="sxs-lookup"><span data-stu-id="17e03-192">The local computer must be running Windows Embedded Standard 7 with SP1, Windows 7 with SP1, or Windows 8.</span></span>
    
- <span data-ttu-id="17e03-193">如果您正在使用远程桌面服务，则选择 32 位或 64 位 Lync VDI 插件匹配本地计算机的操作系统。</span><span class="sxs-lookup"><span data-stu-id="17e03-193">If you're using Remote Desktop Services, choose the 32-bit or 64-bit Lync VDI plug-in to match the local computer's operating system.</span></span> <span data-ttu-id="17e03-194">本地计算机和虚拟机不必都使用 32 位或 64 位操作系统。</span><span class="sxs-lookup"><span data-stu-id="17e03-194">It's not required for both the local computer and the virtual machine to have 32-bit or 64-bit operating systems.</span></span> <span data-ttu-id="17e03-195">如果使用其他虚拟化解决方案或平台，请参阅提供商的要求。</span><span class="sxs-lookup"><span data-stu-id="17e03-195">If you're using another virtualization solution or platform, refer to your provider's requirements.</span></span>
    
- <span data-ttu-id="17e03-196">本地计算机必须运行[的远程桌面客户端的最新版本](https://go.microsoft.com/fwlink/p/?LinkId=268032)。</span><span class="sxs-lookup"><span data-stu-id="17e03-196">The local computer must be running the [latest version of the remote desktop client](https://go.microsoft.com/fwlink/p/?LinkId=268032).</span></span> <span data-ttu-id="17e03-197">可以安装由 Microsoft 提供的最新远程桌面服务客户端更新，也可以安装由虚拟化解决方案提供商提供的最新远程桌面客户端软件。</span><span class="sxs-lookup"><span data-stu-id="17e03-197">Install the latest updates of Remote Desktop Services client from Microsoft or the latest remote desktop client software from your virtualization solution provider.</span></span> 
    
- <span data-ttu-id="17e03-198">在本地计算机上，必须配置远程桌面客户端设置，以便在本地计算机上播放音频并禁用远程录制。</span><span class="sxs-lookup"><span data-stu-id="17e03-198">On the local computer, the remote desktop client settings must be configured so that audio plays on the local computer and remote recording is disabled.</span></span> <span data-ttu-id="17e03-199">若要在 Windows 中配置这些设置用于远程桌面连接，请参阅下一节"以"配置远程桌面连接设置。</span><span class="sxs-lookup"><span data-stu-id="17e03-199">To configure these settings for Remote Desktop Connection in Windows, see the next section, "To configure Remote Desktop Connection settings."</span></span> 
    
<span data-ttu-id="17e03-200">可在[Microsoft Lync VDI 2013 插件 （32 位）](https://www.microsoft.com/en-us/download/details.aspx?id=35457)或[Microsoft Lync VDI 2013 插件 （64 位）](https://www.microsoft.com/en-us/download/details.aspx?id=35454)Microsoft VDI 插件。</span><span class="sxs-lookup"><span data-stu-id="17e03-200">The Microsoft VDI plugin is available at [Microsoft Lync VDI 2013 plugin (32 bit)](https://www.microsoft.com/en-us/download/details.aspx?id=35457) or [Microsoft Lync VDI 2013 plugin (64 bit)](https://www.microsoft.com/en-us/download/details.aspx?id=35454).</span></span>
  
#### <a name="known-feature-limitations"></a><span data-ttu-id="17e03-201">已知功能限制</span><span class="sxs-lookup"><span data-stu-id="17e03-201">Known Feature Limitations</span></span>
<span data-ttu-id="17e03-202"><a name="VDI_prereq"> </a></span><span class="sxs-lookup"><span data-stu-id="17e03-202"></span></span>

<span data-ttu-id="17e03-203">Skype 用于在 VDI 环境中的业务 2015年客户端时，以下是已知限制：</span><span class="sxs-lookup"><span data-stu-id="17e03-203">The following are known limitations when you use the Skype for Business 2015 client in a VDI environment:</span></span>
  
<span data-ttu-id="17e03-204">支持是有限的呼叫委派和响应组代理匿名处理功能。</span><span class="sxs-lookup"><span data-stu-id="17e03-204">There is limited support for Call Delegation and Response Group Agent Anonymization features.</span></span>
  
<span data-ttu-id="17e03-205">不支持以下功能：</span><span class="sxs-lookup"><span data-stu-id="17e03-205">There is no support for the following features:</span></span>
  
- <span data-ttu-id="17e03-206">集成音频设备和视频设备优化页。</span><span class="sxs-lookup"><span data-stu-id="17e03-206">Integrated Audio Device and Video Device tuning pages.</span></span>
    
- <span data-ttu-id="17e03-207">多视图视频。</span><span class="sxs-lookup"><span data-stu-id="17e03-207">Multiple-view video.</span></span>
    
- <span data-ttu-id="17e03-208">录制对话。</span><span class="sxs-lookup"><span data-stu-id="17e03-208">Recording of conversations.</span></span>
    
- <span data-ttu-id="17e03-209">加入会议以匿名方式 （即，承载与您的组织不未联盟的组织的业务会议加入 Skype）。</span><span class="sxs-lookup"><span data-stu-id="17e03-209">Joining meetings anonymously (that is, joining Skype for Business meetings hosted by an organization that does not federate with your organization).</span></span>
    
- <span data-ttu-id="17e03-210">使用 Lync VDI 插件与 Lync Phone Edition 设备。</span><span class="sxs-lookup"><span data-stu-id="17e03-210">Using the Lync VDI plug-in along with a Lync Phone Edition device.</span></span>
    
- <span data-ttu-id="17e03-211">发生网络中断时的呼叫连续性。</span><span class="sxs-lookup"><span data-stu-id="17e03-211">Call continuity in case of a network outage.</span></span>
    
- <span data-ttu-id="17e03-212">自定义铃声和保持音乐功能。</span><span class="sxs-lookup"><span data-stu-id="17e03-212">Customized ringtones and music-on-hold features.</span></span>
    
<span data-ttu-id="17e03-213">Office 365 环境中不支持 Lync VDI 插件。</span><span class="sxs-lookup"><span data-stu-id="17e03-213">The Lync VDI plug-in is not supported in an Office 365 environment.</span></span>
  
> [!NOTE]
> <span data-ttu-id="17e03-214">Citrix RealTime Optimization Pack 明确支持 Office 365。</span><span class="sxs-lookup"><span data-stu-id="17e03-214">The Citrix RealTime Optimization Pack does support Office 365.</span></span> <span data-ttu-id="17e03-215">为基于 Citrix 虚拟环境中，查看受支持的功能和版本的列表的 Citrix 的[技术概述](https://docs.citrix.com/en-us/hdx-optimization/2-0/hdx-realtime-optimization-pack-about.mdl)文档。</span><span class="sxs-lookup"><span data-stu-id="17e03-215">For Citrix-based virtual environments, review Citrix's [Technical Overview ](https://docs.citrix.com/en-us/hdx-optimization/2-0/hdx-realtime-optimization-pack-about.mdl) documentation for the list of supported features and versions.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="17e03-216">另请参阅</span><span class="sxs-lookup"><span data-stu-id="17e03-216">See also</span></span>
<span data-ttu-id="17e03-217"><a name="Citrix_RT"> </a></span><span class="sxs-lookup"><span data-stu-id="17e03-217"></span></span>

[<span data-ttu-id="17e03-218">部署 Lync VDI 插件与 Skype 业务服务器</span><span class="sxs-lookup"><span data-stu-id="17e03-218">Deploy the Lync VDI plug-in with Skype for Business Server</span></span>](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)

