---
title: '管理 QoS (服务质量) '
ms.reviewer: ''
ms:assetid: ab1051c3-8380-4d72-86df-37a61b1e4a41
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg405409(v=OCS.15)
ms:contentKeyID: 48185049
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: QoS (服务质量) 是一种网络技术，在某些组织中用于帮助为音频和视频通信提供最佳最终用户体验。
ms.openlocfilehash: 77fae69a6ceeaf65f80dd38e78e42e186786c4ed
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814152"
---
# <a name="managing-quality-of-service-qos-in-skype-for-business-server"></a><span data-ttu-id="156d5-103">在 Skype for Business Server (QoS) 服务质量</span><span class="sxs-lookup"><span data-stu-id="156d5-103">Managing Quality of Service (QoS) in Skype for Business Server</span></span>


<span data-ttu-id="156d5-p101">服务质量 (QoS) 是某些组织中所使用的一种网络技术，目的是有助于针对音频和视频通信提供最佳的最终用户体验。QoS 最常用于带宽有限的网络上：其中大量的网络数据包争用相对数量较小的可用带宽。服务质量为管理员提供一种为承载音频或视频数据的数据包分配较高优先级的方法。通过为这些数据包提供较高的优先级，与涉及诸如文件传输、Web 浏览或数据库备份等内容的网络会话相比，音频和视频通信可能会以更快的速度完成，并且发生更少的中断。这是因为针对用于文件传输或数据库备份的网络数据包分配了“最佳效果”优先级。</span><span class="sxs-lookup"><span data-stu-id="156d5-p101">Quality of Service (QoS) is a networking technology used in some organizations to help provide an optimal end-user experience for audio and video communications. QoS is most-commonly used on networks where bandwidth is limited: with a large number of network packets competing for a relatively small amount of available bandwidth, Quality of Service provides a way for administrators to assign higher priorities to packets carrying audio or video data. By giving these packets a higher priority, audio and video communications are likely to complete faster, and with less interruption, than network sessions involving things like file transfers, web browsing, or database backups. That's because network packets used for file transfers or database backups are assigned a "best effort" priority.</span></span>


> [!NOTE]  
> <span data-ttu-id="156d5-p102">一般而言，服务质量仅适用于内部网络上的通信会话。在实施 QoS 时，您可以将服务器和路由器配置为支持数据包标记；但是，应以特定的方式将这些设备配置为支持数据包标记。您不能假设将在 Internet 或其他网络上支持服务质量。即使在其他网络上支持服务质量，也不能保证以配置您的网络上的服务的相同方式来配置 QoS。</span><span class="sxs-lookup"><span data-stu-id="156d5-p102">As a general rule, Quality of Service applies only to communication sessions on your internal network. When you implement QoS, you configure your servers and routers to support packet marking; however, you configure these devices to support packet marking in a particular manner. You cannot assume that Quality of Service will be supported on the Internet or on other networks. Even if Quality if Service is supported on other networks, there is no guarantee that QoS will be configured the same way that you configured the service on your network.</span></span>

<span data-ttu-id="156d5-112">Skype for Business Server 不需要服务质量;如果你当前不使用 QoS，则不需要在安装 Skype for Business Server 之前安装该服务。</span><span class="sxs-lookup"><span data-stu-id="156d5-112">Skype for Business Server does not require Quality of Service; if you do not currently use QoS there is no requirement that you install the service before installing Skype for Business Server.</span></span> <span data-ttu-id="156d5-113">如果在您的网络上发生大量的数据包丢失，建议用来缓解此问题的方法是添加额外的带宽。</span><span class="sxs-lookup"><span data-stu-id="156d5-113">If you experience a considerable amount of packet loss on your network the recommended way to alleviate this problem is to add additional bandwidth.</span></span> <span data-ttu-id="156d5-114">如果无法添加更多的带宽，您可能想要改为实施服务质量。</span><span class="sxs-lookup"><span data-stu-id="156d5-114">If adding more bandwidth is not possible, then you might want to implement Quality of Service instead.</span></span>

<span data-ttu-id="156d5-115">Skype for Business Server 提供对服务质量的完全支持：这意味着已使用 QoS 的组织可以轻松地将 Skype for Business Server 集成到其现有网络基础结构中。</span><span class="sxs-lookup"><span data-stu-id="156d5-115">Skype for Business Server offers full support for Quality of Service: that means that organizations that are already using QoS can easily integrate Skype for Business Server into their existing network infrastructure.</span></span> <span data-ttu-id="156d5-116">为执行此操作，您必须执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="156d5-116">In order to do this you must perform the following tasks:</span></span>

  - <span data-ttu-id="156d5-117">[为不基于 Windows 的设备启用 QoS。](enabling-qos-for-devices-that-are-not-based-on-windows.md)</span><span class="sxs-lookup"><span data-stu-id="156d5-117">[Enabling QoS for devices that are not based on Windows](enabling-qos-for-devices-that-are-not-based-on-windows.md).</span></span> <span data-ttu-id="156d5-118">默认情况下，会针对运行其他操作系统的计算机和其他设备（如 iPhone）禁用 QoS。</span><span class="sxs-lookup"><span data-stu-id="156d5-118">By default, QoS is disabled for computers and other devices (such as iPhones) that run other operating systems.</span></span> <span data-ttu-id="156d5-119">尽管可以使用 Skype for Business Server 为设备启用和禁用服务质量，但通常无法使用该产品修改这些设备使用的 DSCP 代码。</span><span class="sxs-lookup"><span data-stu-id="156d5-119">Although you can use Skype for Business Server to enable and disable Quality of Service for devices, you typically cannot use the product to modify the DSCP codes used by these devices.</span></span>

  - <span data-ttu-id="156d5-120">[为会议、应用程序和](configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md)中介服务器配置端口范围和服务质量策略。</span><span class="sxs-lookup"><span data-stu-id="156d5-120">[Configuring port ranges and a Quality of Service policy for your Conferencing, Application, and Mediation servers](configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md).</span></span> <span data-ttu-id="156d5-121">您必须为不同的数据包类型（如音频和视频）保留一组唯一的端口。</span><span class="sxs-lookup"><span data-stu-id="156d5-121">You must reserve a unique set of ports for different packet types, such as audio and video.</span></span> <span data-ttu-id="156d5-122">使用 Skype for Business Server 时，不会通过将属性值设置为 True 或 False 来启用或禁用服务质量。</span><span class="sxs-lookup"><span data-stu-id="156d5-122">With Skype for Business Server you do not enable or disable Quality of Service by, say, setting a property value to True or to False.</span></span> <span data-ttu-id="156d5-123">而是可以通过配置端口范围，然后创建并应用组策略，来启用服务质量。</span><span class="sxs-lookup"><span data-stu-id="156d5-123">Instead, you enable Quality of Service by configuring port ranges and then creating and applying Group Policy.</span></span> <span data-ttu-id="156d5-124">如果您稍后决定不使用 QoS，则只需删除相应的组策略对象，即可“禁用”服务质量。</span><span class="sxs-lookup"><span data-stu-id="156d5-124">If you later decide not to use QoS you can “disable” Quality of Service simply by removing the appropriate Group Policy objects.</span></span>

  - <span data-ttu-id="156d5-125">[为边缘服务器配置端口范围和服务质量策略](configuring-port-ranges-for-your-edge-servers.md)。</span><span class="sxs-lookup"><span data-stu-id="156d5-125">[Configuring port ranges and a Quality of Service policy for your Edge Servers](configuring-port-ranges-for-your-edge-servers.md).</span></span> <span data-ttu-id="156d5-126">虽然不需要，但是可以将您的边缘服务器配置为与其他服务器使用相同的端口范围。</span><span class="sxs-lookup"><span data-stu-id="156d5-126">Although not required, you can configure your Edge servers to use the same port ranges as your other servers.</span></span> <span data-ttu-id="156d5-127">只应为边缘服务器的内部端配置服务质量策略。</span><span class="sxs-lookup"><span data-stu-id="156d5-127">Configuring a Quality of Service policy should only be done for the internal side of your Edge servers.</span></span> <span data-ttu-id="156d5-128">原因是服务质量设计用于内部网络而不是 Internet 上。</span><span class="sxs-lookup"><span data-stu-id="156d5-128">That's because Quality of Service is designed for use on your internal network and not on the Internet.</span></span>

- <span data-ttu-id="156d5-129">[在 Skype for Business Server 中](configuring-port-ranges-for-your-skype-clients.md)  为客户端配置端口范围和服务质量策略 这些端口范围仅适用于客户端计算机，并且通常不同于服务器上配置的端口范围。</span><span class="sxs-lookup"><span data-stu-id="156d5-129">[Configuring port ranges and a Quality of Service policy for your clients in Skype for Business Server](configuring-port-ranges-for-your-skype-clients.md)  These port ranges apply only to client computers and are typically different from the port ranges configured on your servers.</span></span> <span data-ttu-id="156d5-130">请注意，Skype for Business Server 不支持除 Windows 10 外的其他 Windows 操作系统的 QoS。</span><span class="sxs-lookup"><span data-stu-id="156d5-130">Note that Skype for Business Server does not support QoS for Windows operating systems other than Windows 10.</span></span>


