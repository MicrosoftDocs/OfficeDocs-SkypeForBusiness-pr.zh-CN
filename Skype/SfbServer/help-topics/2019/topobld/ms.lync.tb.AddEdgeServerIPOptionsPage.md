---
title: 添加边缘服务器 IP 选项
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerIPOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f458287f-e7a5-45f2-8393-3e1377be81d9
ROBOTS: NOINDEX, NOFOLLOW
description: Skype for Business Server 允许你为边缘服务器和边缘池的每个接口配置 IPv4 和 IPv6 地址。 为此，请执行以下操作：
ms.openlocfilehash: f940e0480c51b1a2541386401a71f0d7d9818566
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801072"
---
# <a name="add-edge-server-ip-options"></a><span data-ttu-id="a9da5-104">添加边缘服务器 IP 选项</span><span class="sxs-lookup"><span data-stu-id="a9da5-104">Add Edge Server IP Options</span></span>
 
<span data-ttu-id="a9da5-105">Skype for Business Server 允许你为边缘服务器和边缘池的每个接口配置 IPv4 和 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="a9da5-105">Skype for Business Server allows you to configure IPv4 and IPv6 addresses for each interface for the Edge Server and Edge pool.</span></span> <span data-ttu-id="a9da5-106">为此，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a9da5-106">To do this, you do the following:</span></span>
  
- <span data-ttu-id="a9da5-107">**在内部接口上启用 IPv4：** 如果要将 IPv4 地址应用到边缘服务器或边缘池内部接口，请选中该复选框</span><span class="sxs-lookup"><span data-stu-id="a9da5-107">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
- <span data-ttu-id="a9da5-108">**在内部接口上启用 IPv6：** 如果要将 IPv6 地址应用到边缘服务器或边缘池内部接口，请选中该复选框</span><span class="sxs-lookup"><span data-stu-id="a9da5-108">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
- <span data-ttu-id="a9da5-109">**在外部接口上启用 IPv4：** 如果要将 IPv4 地址应用到边缘服务器或边缘池外部接口，请选中该复选框</span><span class="sxs-lookup"><span data-stu-id="a9da5-109">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
- <span data-ttu-id="a9da5-110">**在外部接口上启用 IPv6：** 如果要将 IPv6 地址应用到边缘服务器或边缘池外部接口，请选中该复选框</span><span class="sxs-lookup"><span data-stu-id="a9da5-110">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
<span data-ttu-id="a9da5-111">还可以将边缘服务器或边缘池配置为对外部 IP 地址使用网络地址转换地址。</span><span class="sxs-lookup"><span data-stu-id="a9da5-111">You can also configure the Edge Server or Edge pool to use a network address translation address for the external IP addresses.</span></span> <span data-ttu-id="a9da5-112">通过选中“此边缘池的外部 IP 地址是由 NAT 转换的”复选框来执行该操作。</span><span class="sxs-lookup"><span data-stu-id="a9da5-112">You do this by selecting the check box **The external IP address of this Edge pool is translated by NAT**.</span></span>
  
<span data-ttu-id="a9da5-p104">NAT 支持。使用硬件负载平衡时不支持网络地址转换 (NAT)，因此如果要部署具有硬件负载平衡的边缘服务器池，请不要选择 NAT 选项。</span><span class="sxs-lookup"><span data-stu-id="a9da5-p104">NAT support. Network address translation (NAT) is not supported when you are using hardware load balancing, so do not select the NAT option if you are deploying an Edge Server pool with hardware load balancing.</span></span>
  

