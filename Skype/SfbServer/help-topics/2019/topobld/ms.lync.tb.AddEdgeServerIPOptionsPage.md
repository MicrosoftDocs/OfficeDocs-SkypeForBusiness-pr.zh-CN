---
title: 添加 Edge Server IP 选项
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerIPOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f458287f-e7a5-45f2-8393-3e1377be81d9
ROBOTS: NOINDEX, NOFOLLOW
description: 'Skype for Business 服务器允许你为 Edge 服务器和边缘池的每个接口配置 IPv4 和 IPv6 地址。 为此, 请执行以下操作:'
ms.openlocfilehash: 12b1cdb36809ac703bd3383795ea92bdf48cdd31
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303789"
---
# <a name="add-edge-server-ip-options"></a><span data-ttu-id="9a473-104">添加 Edge Server IP 选项</span><span class="sxs-lookup"><span data-stu-id="9a473-104">Add Edge Server IP Options</span></span>
 
<span data-ttu-id="9a473-105">Skype for Business 服务器允许你为 Edge 服务器和边缘池的每个接口配置 IPv4 和 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="9a473-105">Skype for Business Server allows you to configure IPv4 and IPv6 addresses for each interface for the Edge Server and Edge pool.</span></span> <span data-ttu-id="9a473-106">为此, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="9a473-106">To do this, you do the following:</span></span>
  
- <span data-ttu-id="9a473-107">**在内部接口上启用 ipv4**: 如果要将 ipv4 地址应用到边缘服务器或边缘池内部接口, 请选中该复选框</span><span class="sxs-lookup"><span data-stu-id="9a473-107">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
- <span data-ttu-id="9a473-108">**在内部接口上启用 ipv6**: 如果要将 ipv6 地址应用到边缘服务器或边缘池内部接口, 请选中该复选框</span><span class="sxs-lookup"><span data-stu-id="9a473-108">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
- <span data-ttu-id="9a473-109">**在外部接口上启用 ipv4**: 如果要将 ipv4 地址应用到边缘服务器或边缘池外部接口, 请选中该复选框</span><span class="sxs-lookup"><span data-stu-id="9a473-109">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
- <span data-ttu-id="9a473-110">**在外部接口上启用 ipv6**: 如果要将 ipv6 地址应用到边缘服务器或边缘池外部接口, 请选中该复选框</span><span class="sxs-lookup"><span data-stu-id="9a473-110">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
<span data-ttu-id="9a473-111">你还可以将 Edge 服务器或边缘池配置为使用外部 IP 地址的网络地址转换地址。</span><span class="sxs-lookup"><span data-stu-id="9a473-111">You can also configure the Edge Server or Edge pool to use a network address translation address for the external IP addresses.</span></span> <span data-ttu-id="9a473-112">要执行此操作, 请选中该复选框**此边缘池的外部 IP 地址由 NAT 转换**。</span><span class="sxs-lookup"><span data-stu-id="9a473-112">You do this by selecting the check box **The external IP address of this Edge pool is translated by NAT**.</span></span>
  
<span data-ttu-id="9a473-113">NAT 支持。</span><span class="sxs-lookup"><span data-stu-id="9a473-113">NAT support.</span></span> <span data-ttu-id="9a473-114">使用硬件负载平衡时, 不支持网络地址转换 (NAT), 因此, 如果你要部署具有硬件负载平衡的 Edge 服务器池, 请不要选择 NAT 选项。</span><span class="sxs-lookup"><span data-stu-id="9a473-114">Network address translation (NAT) is not supported when you are using hardware load balancing, so do not select the NAT option if you are deploying an Edge Server pool with hardware load balancing.</span></span>
  

