---
title: 为 Lync Server 2010 添加 Edge Server 选项
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerOptionsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b059af5-e83f-4564-90b2-d7ebb9e551c2
description: '定义新的边缘服务器或边缘池, 并向用户提供定义新服务器或池功能的机会。 可供选择的选项包括:'
ms.openlocfilehash: 4bb364ee24f2e85ec16ff2f972dfe05aea9306cd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34289992"
---
# <a name="add-edge-server-options-for-lync-server-2010"></a><span data-ttu-id="9ab39-104">为 Lync Server 2010 添加 Edge Server 选项</span><span class="sxs-lookup"><span data-stu-id="9ab39-104">Add Edge Server Options for Lync Server 2010</span></span>

<span data-ttu-id="9ab39-105">定义新的边缘服务器或边缘池, 并向用户提供定义新服务器或池功能的机会。</span><span class="sxs-lookup"><span data-stu-id="9ab39-105">You define a new Edge Server or Edge pool and are presented with the opportunity to define features for the new server or pool.</span></span> <span data-ttu-id="9ab39-106">可供选择的选项包括:</span><span class="sxs-lookup"><span data-stu-id="9ab39-106">The options that you can choose are:</span></span>

- <span data-ttu-id="9ab39-107">**使用单个 FQDN 和 IP 地址**: 选中复选框以使用单个 IPv4 或 ipv6 (如果选择使用 Ipv4 和 ipv6, 则需要为外部边缘接口定义每个 IP 地址类型) 地址和完全限定的域名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="9ab39-107">**Use a single FQDN and IP address**: Select the check box to use a single IPv4 or IPv6 (if you choose to use both IPv4 and IPv6, then you will need to define one of each IP address type) address and fully qualified domain name (FQDN) for the external Edge interfaces.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="9ab39-108">如果选择此选项, 你将仅使用一个 IP 地址, 或使用一个 IPv4 和一个 IPv6, 但必须为每个 Edge 接口分配不同的端口号。</span><span class="sxs-lookup"><span data-stu-id="9ab39-108">If you choose this option, you will use only one IP address, or one IPv4 and one IPv6, but you must assign different port numbers to each Edge interface.</span></span>

- <span data-ttu-id="9ab39-109">**启用联盟 (端口 5061)**: 如果你将与使用会话初始协议 (SIP) 的其他 SIP 联合、提供程序或托管产品联盟, 请选中此复选框。</span><span class="sxs-lookup"><span data-stu-id="9ab39-109">**Enable federation (port 5061)**: Select this check box if you will federate with other SIP federations, providers, or hosted offerings that use the session initiation protocol (SIP).</span></span>

- <span data-ttu-id="9ab39-110">**此 Edge 池的外部 IP 地址由 NAT 转换**: 如果你对 edge 外部接口使用专用 IP 地址, 并且将提供网络地址转换 (NAT) 设备以逻辑方式放置边缘服务器或边缘池, 请选中此复选框。处于.</span><span class="sxs-lookup"><span data-stu-id="9ab39-110">**The external IP address of this Edge pool is translated by NAT**: Select this check box if you use private IP addresses for the Edge external interfaces and will provide a network address translation (NAT) device to place the Edge Server or Edge pool logically behind.</span></span>

## <a name="see-also"></a><span data-ttu-id="9ab39-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9ab39-111">See also</span></span>

[<span data-ttu-id="9ab39-112">规划外部用户访问</span><span class="sxs-lookup"><span data-stu-id="9ab39-112">Planning for External User Access</span></span>](https://technet.microsoft.com/library/ea098933-eff5-461e-aba3-e7f128784dc2.aspx)

[<span data-ttu-id="9ab39-113">部署外部用户访问</span><span class="sxs-lookup"><span data-stu-id="9ab39-113">Deploying External User Access</span></span>](https://technet.microsoft.com/library/d40c9574-c16b-4fe6-b848-21ae0b7e4f0e.aspx)
