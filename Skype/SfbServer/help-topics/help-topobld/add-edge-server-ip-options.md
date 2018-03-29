---
title: 添加边缘服务器 IP 选项
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerIPOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f458287f-e7a5-45f2-8393-3e1377be81d9
description: 可以使用 Microsoft Lync Server 2013 边缘服务器和边缘池配置每个接口的 IPv4 和 IPv6 地址。 来做到这一点，请执行以下操作：
ms.openlocfilehash: a6f4dd60355a4e241c70ec28c72fa86d91c66a9e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="add-edge-server-ip-options"></a><span data-ttu-id="edee3-104">添加边缘服务器 IP 选项</span><span class="sxs-lookup"><span data-stu-id="edee3-104">Add Edge Server IP Options</span></span>
 
<span data-ttu-id="edee3-105">可以使用 Microsoft Lync Server 2013 边缘服务器和边缘池配置每个接口的 IPv4 和 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="edee3-105">Microsoft Lync Server 2013 allows you to configure IPv4 and IPv6 addresses for each interface for the Edge Server and Edge pool.</span></span> <span data-ttu-id="edee3-106">来做到这一点，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="edee3-106">To do this, you do the following:</span></span>
  
- <span data-ttu-id="edee3-107">**在内部接口上启用 IPv4**： 如果您想要应用于边缘服务器或边缘池内部接口的 IPv4 地址，请选择复选框</span><span class="sxs-lookup"><span data-stu-id="edee3-107">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
- <span data-ttu-id="edee3-108">**在内部接口上启用 IPv6**： 如果您想要应用于边缘服务器或边缘池内部接口的 IPv6 地址，请选择复选框</span><span class="sxs-lookup"><span data-stu-id="edee3-108">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
- <span data-ttu-id="edee3-109">**在外部接口上启用 IPv4**： 如果您想要应用于边缘服务器或边缘池外部接口的 IPv4 地址，请选择复选框</span><span class="sxs-lookup"><span data-stu-id="edee3-109">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
- <span data-ttu-id="edee3-110">**在外部接口上启用 IPv6**： 如果您想要应用于边缘服务器或边缘池外部接口的 IPv6 地址，请选择复选框</span><span class="sxs-lookup"><span data-stu-id="edee3-110">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
<span data-ttu-id="edee3-111">您还可以配置要用于外部 IP 地址的网络地址翻译地址的边缘服务器或边缘池。</span><span class="sxs-lookup"><span data-stu-id="edee3-111">You can also configure the Edge Server or Edge pool to use a network address translation address for the external IP addresses.</span></span> <span data-ttu-id="edee3-112">通过选择**通过 NAT 转换此边缘池的外部 IP 地址**复选框执行此操作。</span><span class="sxs-lookup"><span data-stu-id="edee3-112">You do this by selecting the check box **The external IP address of this Edge pool is translated by NAT**.</span></span>
  
<span data-ttu-id="edee3-113">NAT 的支持。</span><span class="sxs-lookup"><span data-stu-id="edee3-113">NAT support.</span></span> <span data-ttu-id="edee3-114">网络地址转换 (NAT) 不支持使用硬件负载平衡，因此不选择 NAT 选项，如果您正在部署边缘服务器池使用硬件负载平衡时。</span><span class="sxs-lookup"><span data-stu-id="edee3-114">Network address translation (NAT) is not supported when you are using hardware load balancing, so do not select the NAT option if you are deploying an Edge Server pool with hardware load balancing.</span></span>
  

