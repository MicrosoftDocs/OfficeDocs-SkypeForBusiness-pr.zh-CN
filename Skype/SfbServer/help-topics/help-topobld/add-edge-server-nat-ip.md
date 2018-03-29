---
title: 将边缘服务器 NAT IP 添加
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerNatIpPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa97fd0e-48b9-4a66-b55a-12291641c967
description: 公共 IP 地址是由网络地址转换 (NAT) 使用的 IP 地址。 必须公开可路由的 IP 地址。 这是必需的因为您选择了池译者在此向导的选择功能页上的 NAT 选项此边的外部 IP 地址。
ms.openlocfilehash: 4bfbcb7d8859dc928c78c8e32b21604ef473317b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="add-edge-server-nat-ip"></a><span data-ttu-id="4731a-105">将边缘服务器 NAT IP 添加</span><span class="sxs-lookup"><span data-stu-id="4731a-105">Add Edge Server NAT IP</span></span>
 
<span data-ttu-id="4731a-106">公共 IP 地址是由网络地址转换 (NAT) 使用的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="4731a-106">The public IP address is the IP address that is used by network address translation (NAT).</span></span> <span data-ttu-id="4731a-107">必须公开可路由的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="4731a-107">The IP address must be publicly routable.</span></span> <span data-ttu-id="4731a-108">这是必需的因为您选择了**此边缘池的外部 IP 地址翻译通过 NAT**此向导的**选择功能**页上的选项。</span><span class="sxs-lookup"><span data-stu-id="4731a-108">This is required because you selected **The external IP address of this Edge pool is translated by NAT** option on the **Select features** page of this wizard.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4731a-109">网络地址转换 (NAT) 允许客户端或专用网络上的服务器 (例如，192.168.0.0 范围) 通过公共互联网网络与远程网络上的系统进行通信。</span><span class="sxs-lookup"><span data-stu-id="4731a-109">Network address translation (NAT) enables clients or servers on a private network (for example, the 192.168.0.0 range) to communicate with systems on remote networks over the public Internet networks.</span></span> <span data-ttu-id="4731a-110">NAT 的工作原理是在外部接口上使用单个公用 IP 地址，并将内部 IP 地址与一个公共 IP 地址相关联。</span><span class="sxs-lookup"><span data-stu-id="4731a-110">NAT works by using a single public IP address on an external interface and associating internal IP addresses with the one public IP address.</span></span> <span data-ttu-id="4731a-111">NAT 映射将内部地址映射到外部的公用 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="4731a-111">NAT mapping maps an internal address to the external public IP address.</span></span> <span data-ttu-id="4731a-112">远程系统可以看到只有源的公用地址。</span><span class="sxs-lookup"><span data-stu-id="4731a-112">The remote system sees only the public address of the source.</span></span> <span data-ttu-id="4731a-113">远程系统的响应到源，而源指 NAT 映射以确定何种内部 IP 地址响应请求应返回到。</span><span class="sxs-lookup"><span data-stu-id="4731a-113">The remote system responds to the source, and the source refers to the NAT map to determine what internal IP address the response should be returned to.</span></span> 
  
<span data-ttu-id="4731a-114">可以在部署初始拓扑时或在部署后添加对外部用户访问的支持。</span><span class="sxs-lookup"><span data-stu-id="4731a-114">You can add support for external user access when you deploy your initial topology or afterward.</span></span> <span data-ttu-id="4731a-115">有关将边缘服务器添加到一个现有的拓扑结构的详细信息，请参阅[定义边拓扑](http://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx)的边缘服务器部署文档。</span><span class="sxs-lookup"><span data-stu-id="4731a-115">For details about adding Edge Servers to an existing topology, see [Define Your Edge Topology](http://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) in the Edge Server Deployment documentation.</span></span>
  

