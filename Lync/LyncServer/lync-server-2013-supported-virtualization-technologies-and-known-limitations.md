---
title: Lync Server 2013：支持的虚拟化技术和已知限制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported virtualization technologies and known limitations
ms:assetid: 6d3d749d-e840-4c05-afae-d6e69e7616aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204982(v=OCS.15)
ms:contentKeyID: 48184428
ms.date: 02/07/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cf513e9dee4e6a27708c8882519099c825f903f2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731642"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-virtualization-technologies-and-known-limitations-in-lync-server-2013"></a><span data-ttu-id="3aa07-102">Lync Server 2013 中支持的虚拟化技术和已知限制</span><span class="sxs-lookup"><span data-stu-id="3aa07-102">Supported virtualization technologies and known limitations in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3aa07-103">_**主题上次修改时间：** 2017-02-06_</span><span class="sxs-lookup"><span data-stu-id="3aa07-103">_**Topic Last Modified:** 2017-02-06_</span></span>

<span data-ttu-id="3aa07-104">Lync VDI 插件允许针对受支持的虚拟化技术进行音频和视频通话。</span><span class="sxs-lookup"><span data-stu-id="3aa07-104">The Lync VDI plug-in allows audio and video calling for supported virtualization technologies.</span></span> <span data-ttu-id="3aa07-105">这将在[Microsoft lync 2010 白皮书的客户端虚拟化](https://go.microsoft.com/fwlink/?linkid=330447)中扩展 Microsoft Lync Server 2010 所示的功能。</span><span class="sxs-lookup"><span data-stu-id="3aa07-105">This extends the functionality outlined for Microsoft Lync Server 2010 in the [Client Virtualization in Microsoft Lync 2010](https://go.microsoft.com/fwlink/?linkid=330447) white paper.</span></span> <span data-ttu-id="3aa07-106">遵守标准电话规章，还包括对 E911 的支持。</span><span class="sxs-lookup"><span data-stu-id="3aa07-106">In compliance with standard telephone regulations, support for E911 is also included.</span></span> <span data-ttu-id="3aa07-107">以下部分介绍 Lync VDI 插件支持的虚拟化技术和已知功能限制。</span><span class="sxs-lookup"><span data-stu-id="3aa07-107">The following sections describe the virtualization technologies that are supported by the Lync VDI plug-in and the known feature limitations.</span></span>

<div>

## <a name="support-for-virtualization-technologies"></a><span data-ttu-id="3aa07-108">虚拟化技术支持</span><span class="sxs-lookup"><span data-stu-id="3aa07-108">Support for Virtualization Technologies</span></span>

<span data-ttu-id="3aa07-109">Lync VDI 插件支持个人虚拟桌面方案中的完整桌面远程处理，但不支持远程桌面会话方案中的完整桌面远程处理。</span><span class="sxs-lookup"><span data-stu-id="3aa07-109">The Lync VDI plug-in supports full desktop remoting in the personal virtual desktop scenario, but not in the remote desktop session scenario.</span></span> <span data-ttu-id="3aa07-110">这些方案可描述如下：</span><span class="sxs-lookup"><span data-stu-id="3aa07-110">These scenarios can be described as follows:</span></span>

  - <span data-ttu-id="3aa07-111">**支持：个性化的虚拟桌面或虚拟桌面基础结构（VDI）。**   在此方案中，每个用户都登录到一个可自定义的虚拟桌面，并且能够保存桌面上跨会话保留的文件。</span><span class="sxs-lookup"><span data-stu-id="3aa07-111">**Supported: Personalized Virtual Desktops or Virtual Desktop Infrastructure (VDI).**   In this scenario, each user logs on to a customizable virtual desktop and is able to save files on the desktop that persist across sessions.</span></span> <span data-ttu-id="3aa07-112">Microsoft 远程桌面服务、VMware 地平线视图和 Citrix XenDesktop 是已测试用于 Lync 的实现。</span><span class="sxs-lookup"><span data-stu-id="3aa07-112">Microsoft Remote Desktop Services, VMware Horizon View, and Citrix XenDesktop are implementations that have been tested for use with Lync.</span></span> <span data-ttu-id="3aa07-113">有关已由 Microsoft 测试的特定于供应商的 VDI 环境和客户端硬件的信息，请参阅[Microsoft Lync 合格的基础结构](https://go.microsoft.com/fwlink/?linkid=313435)。</span><span class="sxs-lookup"><span data-stu-id="3aa07-113">For information about vendor-specific VDI environments and client hardware that have been tested by Microsoft, see [Infrastructure qualified for Microsoft Lync](https://go.microsoft.com/fwlink/?linkid=313435).</span></span>

  - <span data-ttu-id="3aa07-114">**不支持：远程桌面会话。**   在此方案中，每个用户登录到无法自定义的一般虚拟桌面会话。</span><span class="sxs-lookup"><span data-stu-id="3aa07-114">**Not supported: Remote Desktop Sessions.**   In this scenario, each user logs on to a generic virtual desktop session that cannot be customized.</span></span> <span data-ttu-id="3aa07-115">示例实施包括 Microsoft 远程桌面会话 (RDSH) 和与 Citrix Receiver 组合的 Citrix XenApp。</span><span class="sxs-lookup"><span data-stu-id="3aa07-115">Example implementations include Microsoft Remote Desktop Sessions (RDSH) and Citrix XenApp combined with Citrix Receiver.</span></span>

<span data-ttu-id="3aa07-116">Lync VDI 插件不支持其他虚拟化技术（如应用程序虚拟化），它允许在不需要本地安装完整应用程序的情况下使用应用程序。</span><span class="sxs-lookup"><span data-stu-id="3aa07-116">The Lync VDI plug-in does not support other virtualization technologies, such as application virtualization, which allows the use of an application without requiring installation of the full application locally.</span></span> <span data-ttu-id="3aa07-117">示例实现包括 Citrix XenApp 和 Microsoft Application Virtualization （App-v）。</span><span class="sxs-lookup"><span data-stu-id="3aa07-117">Example implementations include Citrix XenApp and Microsoft Application Virtualization (App-V).</span></span> <span data-ttu-id="3aa07-118">不支持应用程序流、应用程序远程处理和混合虚拟化模式（例如，完全桌面远程处理中的应用程序远程处理）。</span><span class="sxs-lookup"><span data-stu-id="3aa07-118">Application streaming, application remoting, and mixed virtualization modes (for example, application remoting in full desktop remoting) are not supported.</span></span>

<span data-ttu-id="3aa07-119">为了允许扩展性，Lync VDI 插件设计为使用名为 "动态虚拟通道（DVCs）" 的独立于平台的 Api。</span><span class="sxs-lookup"><span data-stu-id="3aa07-119">To allow extensibility, the Lync VDI plug-in was designed to use platform-independent APIs called Dynamic Virtual Channels (DVCs).</span></span> <span data-ttu-id="3aa07-120">对于不是由 Lync 明确支持的方案，请参阅来自 VDI 解决方案提供商的支持声明。</span><span class="sxs-lookup"><span data-stu-id="3aa07-120">For scenarios that are not explicitly supported by Lync, refer to support statements from the VDI solution provider.</span></span>

</div>

<div>

## <a name="known-feature-limitations"></a><span data-ttu-id="3aa07-121">已知功能限制</span><span class="sxs-lookup"><span data-stu-id="3aa07-121">Known Feature Limitations</span></span>

<span data-ttu-id="3aa07-122">在 VDI 环境中使用 Lync 2013 时，以下是已知限制：</span><span class="sxs-lookup"><span data-stu-id="3aa07-122">The following are known limitations when you use Lync 2013 in a VDI environment:</span></span>

  - <span data-ttu-id="3aa07-123">对呼叫委派和响应组代理匿名化功能的支持有限。</span><span class="sxs-lookup"><span data-stu-id="3aa07-123">There is limited support for Call Delegation and Response Group Agent Anonymization features.</span></span>

  - <span data-ttu-id="3aa07-124">不支持以下功能：</span><span class="sxs-lookup"><span data-stu-id="3aa07-124">There is no support for the following features:</span></span>
    
      - <span data-ttu-id="3aa07-125">集成音频设备和视频设备优化页。</span><span class="sxs-lookup"><span data-stu-id="3aa07-125">Integrated Audio Device and Video Device tuning pages.</span></span>
    
      - <span data-ttu-id="3aa07-126">多视图视频。</span><span class="sxs-lookup"><span data-stu-id="3aa07-126">Multiple-view video.</span></span>
    
      - <span data-ttu-id="3aa07-127">录制对话。</span><span class="sxs-lookup"><span data-stu-id="3aa07-127">Recording of conversations.</span></span>
    
      - <span data-ttu-id="3aa07-128">远程桌面服务（RDS）。</span><span class="sxs-lookup"><span data-stu-id="3aa07-128">Remote Desktop Services (RDS).</span></span>
    
      - <span data-ttu-id="3aa07-129">匿名加入会议（即，加入由不与您的组织联盟的组织托管的 Lync 会议）。</span><span class="sxs-lookup"><span data-stu-id="3aa07-129">Joining meetings anonymously (that is, joining Lync meetings hosted by an organization that does not federate with your organization).</span></span>
    
      - <span data-ttu-id="3aa07-130">将 Lync VDI 插件与 Lync Phone Edition 设备结合使用。</span><span class="sxs-lookup"><span data-stu-id="3aa07-130">Using the Lync VDI plug-in along with a Lync Phone Edition device.</span></span>
    
      - <span data-ttu-id="3aa07-131">发生网络中断时的呼叫连续性。</span><span class="sxs-lookup"><span data-stu-id="3aa07-131">Call continuity in case of a network outage.</span></span>
    
      - <span data-ttu-id="3aa07-132">自定义铃声和保持音乐功能。</span><span class="sxs-lookup"><span data-stu-id="3aa07-132">Customized ringtones and music-on-hold features.</span></span>

  - <span data-ttu-id="3aa07-133">Office 365 环境中不支持 Lync VDI 插件。</span><span class="sxs-lookup"><span data-stu-id="3aa07-133">The Lync VDI plug-in is not supported in an Office 365 environment.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

