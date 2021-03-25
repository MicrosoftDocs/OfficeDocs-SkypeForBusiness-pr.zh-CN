---
title: 添加边缘服务器 NAT IP
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerNatIpPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa97fd0e-48b9-4a66-b55a-12291641c967
ROBOTS: NOINDEX, NOFOLLOW
description: 公共 IP 地址是网络地址转换 (NAT) 使用的 IP 地址。 IP 地址必须为公共可路由的地址。 由于在此向导的“选择功能”页上选择了“此边缘池的外部 IP 地址由 NAT 转换”选项，因此这一点是必需的。
ms.openlocfilehash: e08e804adaddc409e7f5838e25768822b236b3d8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116440"
---
# <a name="add-edge-server-nat-ip"></a><span data-ttu-id="345fe-105">添加边缘服务器 NAT IP</span><span class="sxs-lookup"><span data-stu-id="345fe-105">Add Edge Server NAT IP</span></span>

<span data-ttu-id="345fe-p102">公共 IP 地址是网络地址转换 (NAT) 使用的 IP 地址。IP 地址必须为公共可路由的地址。由于在此向导的“选择功能”页上选择了“此边缘池的外部 IP 地址是由 NAT 转换的”选项，因此这一点是必需的。</span><span class="sxs-lookup"><span data-stu-id="345fe-p102">The public IP address is the IP address that is used by network address translation (NAT). The IP address must be publicly routable. This is required because you selected **The external IP address of this Edge pool is translated by NAT** option on the **Select features** page of this wizard.</span></span>

> [!NOTE]
> <span data-ttu-id="345fe-p103">网络地址转换 (NAT) 允许专用网络（例如 192.168.0.0 范围）上的客户端或服务器通过公共 Internet 网络与远程网络上的系统进行通信。NAT 通过使用外部接口上的单个公共 IP 地址并将内部 IP 地址与一个公共 IP 地址相关联而起作用。NAT 映射可将内部地址映射到外部公共 IP 地址。远程系统只能看到源的公共地址。远程系统响应源，而源将参考 NAT 映射来确定应当将响应返回到哪个内部 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="345fe-p103">Network address translation (NAT) enables clients or servers on a private network (for example, the 192.168.0.0 range) to communicate with systems on remote networks over the public Internet networks. NAT works by using a single public IP address on an external interface and associating internal IP addresses with the one public IP address. NAT mapping maps an internal address to the external public IP address. The remote system sees only the public address of the source. The remote system responds to the source, and the source refers to the NAT map to determine what internal IP address the response should be returned to.</span></span>

<span data-ttu-id="345fe-114">可以在部署初始拓扑时或在部署后添加对外部用户访问的支持。</span><span class="sxs-lookup"><span data-stu-id="345fe-114">You can add support for external user access when you deploy your initial topology or afterward.</span></span> <span data-ttu-id="345fe-115">有关向现有拓扑中添加边缘服务器的详细信息，请参阅边缘服务器部署文档中的[Define Your Edge Topology](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology)。</span><span class="sxs-lookup"><span data-stu-id="345fe-115">For details about adding Edge Servers to an existing topology, see [Define Your Edge Topology](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology) in the Edge Server Deployment documentation.</span></span>