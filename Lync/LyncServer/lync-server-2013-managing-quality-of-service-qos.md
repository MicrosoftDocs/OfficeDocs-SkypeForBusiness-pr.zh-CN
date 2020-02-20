---
title: Lync Server 2013：管理服务质量（QoS）
ms.reviewer: ''
f1.keywords:
- NOCSH
TOCTitle: Managing Quality of Service (QoS)
author: lanachin
ms.author: v-lanac
ms.manager: serdars
ms:assetid: ab1051c3-8380-4d72-86df-37a61b1e4a41
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg405409(v=OCS.15)
ms:contentKeyID: 48185049
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b72fbd1275060ce01d56cb64e11cdd27f38b2e54
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150183"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-quality-of-service-qos-in-lync-server-2013"></a><span data-ttu-id="19c82-102">在 Lync Server 2013 中管理服务质量（QoS）</span><span class="sxs-lookup"><span data-stu-id="19c82-102">Managing Quality of Service (QoS) in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="19c82-103">_**上次修改的主题：** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="19c82-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="19c82-p101">服务质量 (QoS) 是某些组织中所使用的一种网络技术，目的是有助于针对音频和视频通信提供最佳的最终用户体验。QoS 最常用于带宽有限的网络上：其中大量的网络数据包争用相对数量较小的可用带宽。服务质量为管理员提供一种为承载音频或视频数据的数据包分配较高优先级的方法。通过为这些数据包提供较高的优先级，与涉及诸如文件传输、Web 浏览或数据库备份等内容的网络会话相比，音频和视频通信可能会以更快的速度完成，并且发生更少的中断。这是因为针对用于文件传输或数据库备份的网络数据包分配了“最佳效果”优先级。</span><span class="sxs-lookup"><span data-stu-id="19c82-p101">Quality of Service (QoS) is a networking technology used in some organizations to help provide an optimal end-user experience for audio and video communications. QoS is most-commonly used on networks where bandwidth is limited: with a large number of network packets competing for a relatively small amount of available bandwidth, Quality of Service provides a way for administrators to assign higher priorities to packets carrying audio or video data. By giving these packets a higher priority, audio and video communications are likely to complete faster, and with less interruption, than network sessions involving things like file transfers, web browsing, or database backups. That's because network packets used for file transfers or database backups are assigned a "best effort" priority.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="19c82-p102">一般而言，服务质量仅适用于内部网络上的通信会话。在实施 QoS 时，您可以将服务器和路由器配置为支持数据包标记；但是，应以特定的方式将这些设备配置为支持数据包标记。您不能假设将在 Internet 或其他网络上支持服务质量。即使在其他网络上支持服务质量，也不能保证以配置您的网络上的服务的相同方式来配置 QoS。</span><span class="sxs-lookup"><span data-stu-id="19c82-p102">As a general rule, Quality of Service applies only to communication sessions on your internal network. When you implement QoS, you configure your servers and routers to support packet marking; however, you configure these devices to support packet marking in a particular manner. You cannot assume that Quality of Service will be supported on the Internet or on other networks. Even if Quality if Service is supported on other networks, there is no guarantee that QoS will be configured the same way that you configured the service on your network.</span></span>



</div>

<span data-ttu-id="19c82-112">Microsoft Lync Server 2013 不需要服务质量;如果当前不使用 QoS，则无需在安装 Lync Server 2013 之前安装服务。</span><span class="sxs-lookup"><span data-stu-id="19c82-112">Microsoft Lync Server 2013 does not require Quality of Service; if you do not currently use QoS there is no requirement that you install the service before installing Lync Server 2013.</span></span> <span data-ttu-id="19c82-113">如果在您的网络上发生大量的数据包丢失，建议用来缓解此问题的方法是添加额外的带宽。</span><span class="sxs-lookup"><span data-stu-id="19c82-113">If you experience a considerable amount of packet loss on your network the recommended way to alleviate this problem is to add additional bandwidth.</span></span> <span data-ttu-id="19c82-114">如果无法添加更多的带宽，您可能想要改为实施服务质量。</span><span class="sxs-lookup"><span data-stu-id="19c82-114">If adding more bandwidth is not possible, then you might want to implement Quality of Service instead.</span></span>

<span data-ttu-id="19c82-115">Lync Server 2013 提供对服务质量的完全支持：这意味着已使用 QoS 的组织可以轻松地将 Lync Server 集成到其现有的网络基础结构中。</span><span class="sxs-lookup"><span data-stu-id="19c82-115">Lync Server 2013 offers full support for Quality of Service: that means that organizations that are already using QoS can easily integrate Lync Server into their existing network infrastructure.</span></span> <span data-ttu-id="19c82-116">为执行此操作，您必须执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="19c82-116">In order to do this you must perform the following tasks:</span></span>

  - <span data-ttu-id="19c82-117">[在 Lync Server 2013 中为不基于 Windows 的设备启用 QoS](lync-server-2013-enabling-qos-for-devices-that-are-not-based-on-windows.md)。</span><span class="sxs-lookup"><span data-stu-id="19c82-117">[Enabling QoS in Lync Server 2013 for devices that are not based on Windows](lync-server-2013-enabling-qos-for-devices-that-are-not-based-on-windows.md).</span></span> <span data-ttu-id="19c82-118">默认情况下，会针对运行其他操作系统的计算机和其他设备（如 iPhone）禁用 QoS。</span><span class="sxs-lookup"><span data-stu-id="19c82-118">By default, QoS is disabled for computers and other devices (such as iPhones) that run other operating systems.</span></span> <span data-ttu-id="19c82-119">虽然您可以使用 Lync Server 启用和禁用设备的服务质量，但通常无法使用该产品修改这些设备使用的 DSCP 代码。</span><span class="sxs-lookup"><span data-stu-id="19c82-119">Although you can use Lync Server to enable and disable Quality of Service for devices, you typically cannot use the product to modify the DSCP codes used by these devices.</span></span>

  - <span data-ttu-id="19c82-120">[为您的会议、应用程序和中介服务器配置 Lync Server 2013 中的端口范围](lync-server-2013-configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md)。</span><span class="sxs-lookup"><span data-stu-id="19c82-120">[Configuring port ranges in Lync Server 2013 for your Conferencing, Application, and Mediation servers](lync-server-2013-configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md).</span></span> <span data-ttu-id="19c82-121">您必须为不同的数据包类型（如音频和视频）保留一组唯一的端口。</span><span class="sxs-lookup"><span data-stu-id="19c82-121">You must reserve a unique set of ports for different packet types, such as audio and video.</span></span> <span data-ttu-id="19c82-122">在 Lync Server 2013 中，您不能启用或禁用服务质量，例如，将属性值设置为 True 或 False。</span><span class="sxs-lookup"><span data-stu-id="19c82-122">With Lync Server 2013 you do not enable or disable Quality of Service by, say, setting a property value to True or to False.</span></span> <span data-ttu-id="19c82-123">而是可以通过配置端口范围，然后创建并应用组策略，来启用服务质量。</span><span class="sxs-lookup"><span data-stu-id="19c82-123">Instead, you enable Quality of Service by configuring port ranges and then creating and applying Group Policy.</span></span> <span data-ttu-id="19c82-124">如果您稍后决定不使用 QoS，则只需删除相应的组策略对象，即可“禁用”服务质量。</span><span class="sxs-lookup"><span data-stu-id="19c82-124">If you later decide not to use QoS you can “disable” Quality of Service simply by removing the appropriate Group Policy objects.</span></span>

  - <span data-ttu-id="19c82-125">[在 Lync Server 2013 中为边缘服务器配置端口范围](lync-server-2013-configuring-port-ranges-for-your-edge-servers.md)。</span><span class="sxs-lookup"><span data-stu-id="19c82-125">[Configuring port ranges for your Edge Servers in Lync Server 2013](lync-server-2013-configuring-port-ranges-for-your-edge-servers.md).</span></span> <span data-ttu-id="19c82-126">虽然不需要，但是可以将您的边缘服务器配置为与其他服务器使用相同的端口范围。</span><span class="sxs-lookup"><span data-stu-id="19c82-126">Although not required, you can configure your Edge servers to use the same port ranges as your other servers.</span></span>

  - <span data-ttu-id="19c82-127">[在 Lync Server 2013 中为 Microsoft Lync 客户端配置端口范围](lync-server-2013-configuring-port-ranges-for-your-microsoft-lync-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="19c82-127">[Configuring port ranges for your Microsoft Lync clients in Lync Server 2013](lync-server-2013-configuring-port-ranges-for-your-microsoft-lync-clients.md).</span></span> <span data-ttu-id="19c82-128">这些端口范围仅适用于客户端计算机，并且通常与在您的服务器上配置的端口范围有所不同。</span><span class="sxs-lookup"><span data-stu-id="19c82-128">These port ranges apply only to client computers and are typically not the same as the port ranges configured on your servers.</span></span>

  - <span data-ttu-id="19c82-129">[在 Lync Server 2013 中为您的会议、应用程序和中介服务器配置服务质量策略](lync-server-2013-configuring-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers.md)。</span><span class="sxs-lookup"><span data-stu-id="19c82-129">[Configuring a Quality of Service policy in Lync Server 2013 for your Conferencing, Application, and Mediation servers](lync-server-2013-configuring-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers.md).</span></span> <span data-ttu-id="19c82-130">这些策略可确定应用到不同数据包类型的 DSCP 代码。</span><span class="sxs-lookup"><span data-stu-id="19c82-130">These policies determine the DSCP codes that are applied to different packet types.</span></span>

  - <span data-ttu-id="19c82-131">为[Lync Server 2013 中的 a/V 边缘服务器配置服务质量策略](lync-server-2013-configuring-a-quality-of-service-policy-for-your-a-v-edge-servers.md)。</span><span class="sxs-lookup"><span data-stu-id="19c82-131">[Configuring a Quality of Service policy for your A/V Edge Servers in Lync Server 2013](lync-server-2013-configuring-a-quality-of-service-policy-for-your-a-v-edge-servers.md).</span></span> <span data-ttu-id="19c82-132">仅应对边缘服务器的内端执行此操作。</span><span class="sxs-lookup"><span data-stu-id="19c82-132">This should only be done for the internal side of your Edge servers.</span></span> <span data-ttu-id="19c82-133">原因是服务质量设计用于内部网络而不是 Internet 上。</span><span class="sxs-lookup"><span data-stu-id="19c82-133">That's because Quality of Service is designed for use on your internal network and not on the Internet.</span></span>

  - <span data-ttu-id="19c82-134">[为在 windows 7 或 windows 8 上运行的客户端配置 Lync Server 2013 中的服务质量策略](lync-server-2013-configuring-quality-of-service-policies-for-clients-running-on-windows-7-or-windows-8.md)。</span><span class="sxs-lookup"><span data-stu-id="19c82-134">[Configuring Quality of Service policies in Lync Server 2013 for clients running on Windows 7 or Windows 8](lync-server-2013-configuring-quality-of-service-policies-for-clients-running-on-windows-7-or-windows-8.md).</span></span> <span data-ttu-id="19c82-135">请注意，Microsoft Lync Server 2013 不支持其他 Windows 操作系统（如 Windows Vista 或 Windows XP）的 QoS。</span><span class="sxs-lookup"><span data-stu-id="19c82-135">Note that Microsoft Lync Server 2013 does not support QoS for other Windows operating systems, such as Windows Vista or Windows XP.</span></span>

  - <span data-ttu-id="19c82-136">[在 Lync Server 2013 中配置 Microsoft Lync Phone Edition 设备上的服务质量](lync-server-2013-configuring-quality-of-service-on-microsoft-lync-phone-edition-devices.md)。</span><span class="sxs-lookup"><span data-stu-id="19c82-136">[Configuring Quality of Service on Microsoft Lync Phone Edition devices in Lync Server 2013](lync-server-2013-configuring-quality-of-service-on-microsoft-lync-phone-edition-devices.md).</span></span> <span data-ttu-id="19c82-137">默认情况下，将为 Lync Phone Edition 设备启用 QoS。</span><span class="sxs-lookup"><span data-stu-id="19c82-137">By default, QoS is enabled for Lync Phone Edition devices.</span></span> <span data-ttu-id="19c82-138">但是，您可能想要更改默认 DSCP 值，以确保您的组织中的所有音频数据包均使用相同的 DSCP 代码。</span><span class="sxs-lookup"><span data-stu-id="19c82-138">However, you might want to change the default DSCP value in order to ensure that all audio packets in your organization use the same DSCP code.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="19c82-139">如果你使用的是 Microsoft Windows Server 2012 或 Windows Server 2012 R2，你可能会对在该平台上管理服务质量的一组新的 Windows PowerShell cmdlet 感兴趣。</span><span class="sxs-lookup"><span data-stu-id="19c82-139">If you are using Microsoft Windows Server 2012 or Windows Server 2012 R2 you might be interested in the new set of Windows PowerShell cmdlets available for managing Quality of Service on that platform.</span></span> <span data-ttu-id="19c82-140">有关详细信息，请参阅 Windows PowerShell 中的网络服务 Cmdlet 的[https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps](https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps)网络质量。</span><span class="sxs-lookup"><span data-stu-id="19c82-140">For more information, see Network Quality of Service Cmdlets in Windows PowerShell at [https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps](https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps).</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

