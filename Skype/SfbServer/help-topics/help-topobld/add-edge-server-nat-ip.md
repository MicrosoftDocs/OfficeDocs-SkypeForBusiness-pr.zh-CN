---
title: 添加 Edge Server NAT IP
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerNatIpPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa97fd0e-48b9-4a66-b55a-12291641c967
description: 公共 IP 地址是网络地址转换 (NAT) 使用的 IP 地址。 IP 地址必须是公共可路由的。 这是必需的, 因为你选择了此向导的 "选择功能" 页面上的 NAT "通过 NAT 转换此边缘池的外部 IP 地址" 选项。
ms.openlocfilehash: 55200991a0674c6372de9f44c2511e700166bebf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34293943"
---
# <a name="add-edge-server-nat-ip"></a><span data-ttu-id="be2a7-105">添加 Edge Server NAT IP</span><span class="sxs-lookup"><span data-stu-id="be2a7-105">Add Edge Server NAT IP</span></span>

<span data-ttu-id="be2a7-106">公共 IP 地址是网络地址转换 (NAT) 使用的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="be2a7-106">The public IP address is the IP address that is used by network address translation (NAT).</span></span> <span data-ttu-id="be2a7-107">IP 地址必须是公共可路由的。</span><span class="sxs-lookup"><span data-stu-id="be2a7-107">The IP address must be publicly routable.</span></span> <span data-ttu-id="be2a7-108">这是必需的, 因为你选择了此向导的 "**选择功能**" 页面上的**NAT "通过 NAT 转换此边缘池的外部 IP 地址"** 选项。</span><span class="sxs-lookup"><span data-stu-id="be2a7-108">This is required because you selected **The external IP address of this Edge pool is translated by NAT** option on the **Select features** page of this wizard.</span></span>

> [!NOTE]
> <span data-ttu-id="be2a7-109">网络地址转换 (NAT) 允许专用网络上的客户端或服务器 (如192.168.0.0 范围) 通过公共 Internet 网络与远程网络上的系统通信。</span><span class="sxs-lookup"><span data-stu-id="be2a7-109">Network address translation (NAT) enables clients or servers on a private network (for example, the 192.168.0.0 range) to communicate with systems on remote networks over the public Internet networks.</span></span> <span data-ttu-id="be2a7-110">NAT 的工作原理是使用外部接口上的单个公共 IP 地址, 并将内部 IP 地址与一个公共 IP 地址相关联。</span><span class="sxs-lookup"><span data-stu-id="be2a7-110">NAT works by using a single public IP address on an external interface and associating internal IP addresses with the one public IP address.</span></span> <span data-ttu-id="be2a7-111">NAT 映射将内部地址映射到外部公共 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="be2a7-111">NAT mapping maps an internal address to the external public IP address.</span></span> <span data-ttu-id="be2a7-112">远程系统仅看到源的公共地址。</span><span class="sxs-lookup"><span data-stu-id="be2a7-112">The remote system sees only the public address of the source.</span></span> <span data-ttu-id="be2a7-113">远程系统响应源, 源指向 NAT 映射以确定应返回响应的内部 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="be2a7-113">The remote system responds to the source, and the source refers to the NAT map to determine what internal IP address the response should be returned to.</span></span>

<span data-ttu-id="be2a7-p104">可以在部署初始拓扑时或在部署后添加对外部用户访问的支持。有关向现有拓扑中添加边缘服务器的详细信息，请参阅边缘服务器部署文档中的[Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx)。</span><span class="sxs-lookup"><span data-stu-id="be2a7-p104">You can add support for external user access when you deploy your initial topology or afterward. For details about adding Edge Servers to an existing topology, see [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) in the Edge Server Deployment documentation.</span></span>


