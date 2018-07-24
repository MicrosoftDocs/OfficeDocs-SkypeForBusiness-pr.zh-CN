---
title: 添加边缘服务器 NAT IP
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerNatIpPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa97fd0e-48b9-4a66-b55a-12291641c967
description: 公共 IP 地址是由网络地址转换 (NAT) 的 IP 地址。 IP 地址必须公共可路由。 这是必需的因为您选择此边缘池转换 NAT 选项在此向导的选择功能页上的外部 IP 地址。
ms.openlocfilehash: be14b49a0d5ccac83dbee483d45aef91f1182621
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "21003115"
---
# <a name="add-edge-server-nat-ip"></a><span data-ttu-id="d33fc-105">添加边缘服务器 NAT IP</span><span class="sxs-lookup"><span data-stu-id="d33fc-105">Add Edge Server NAT IP</span></span>
 
<span data-ttu-id="d33fc-106">公共 IP 地址是由网络地址转换 (NAT) 的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="d33fc-106">The public IP address is the IP address that is used by network address translation (NAT).</span></span> <span data-ttu-id="d33fc-107">IP 地址必须公共可路由。</span><span class="sxs-lookup"><span data-stu-id="d33fc-107">The IP address must be publicly routable.</span></span> <span data-ttu-id="d33fc-108">这是必需的因为您选择**此边缘池的外部 IP 地址由 NAT 转换**此向导的**选择功能**页上的选项。</span><span class="sxs-lookup"><span data-stu-id="d33fc-108">This is required because you selected **The external IP address of this Edge pool is translated by NAT** option on the **Select features** page of this wizard.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d33fc-109">网络地址转换 (NAT) 启用客户端或服务器上的专用网络 (如 192.168.0.0 范围) 通过公共 Internet 网络与远程网络上的系统进行通信。</span><span class="sxs-lookup"><span data-stu-id="d33fc-109">Network address translation (NAT) enables clients or servers on a private network (for example, the 192.168.0.0 range) to communicate with systems on remote networks over the public Internet networks.</span></span> <span data-ttu-id="d33fc-110">NAT 工作方式是在外部接口上使用单个公用 IP 地址并将与一个公用 IP 地址的内部 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="d33fc-110">NAT works by using a single public IP address on an external interface and associating internal IP addresses with the one public IP address.</span></span> <span data-ttu-id="d33fc-111">NAT 映射将内部地址映射到外部公共 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="d33fc-111">NAT mapping maps an internal address to the external public IP address.</span></span> <span data-ttu-id="d33fc-112">远程系统看到只有源的公共地址。</span><span class="sxs-lookup"><span data-stu-id="d33fc-112">The remote system sees only the public address of the source.</span></span> <span data-ttu-id="d33fc-113">远程系统响应源，和 NAT 映射以确定哪些内部 IP 地址响应应返回到源引用。</span><span class="sxs-lookup"><span data-stu-id="d33fc-113">The remote system responds to the source, and the source refers to the NAT map to determine what internal IP address the response should be returned to.</span></span> 
  
<span data-ttu-id="d33fc-114">可以在部署初始拓扑时或在部署后添加对外部用户访问的支持。</span><span class="sxs-lookup"><span data-stu-id="d33fc-114">You can add support for external user access when you deploy your initial topology or afterward.</span></span> <span data-ttu-id="d33fc-115">有关将边缘服务器添加到现有拓扑的详细信息，请参阅边缘服务器部署文档中的[Define Your Edge Topology](http://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="d33fc-115">For details about adding Edge Servers to an existing topology, see [Define Your Edge Topology](http://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) in the Edge Server Deployment documentation.</span></span>
  

