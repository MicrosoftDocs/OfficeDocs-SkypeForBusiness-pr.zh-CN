---
title: 添加 Lync Server 2010 的边缘服务器选项
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerOptionsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b059af5-e83f-4564-90b2-d7ebb9e551c2
description: 定义新的边缘服务器或边缘池，并有机会定义新服务器或池的功能。 可以选择的选项有：
ms.openlocfilehash: b6f6e07c3555101103aeaad7f1c45f4449c25078
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835512"
---
# <a name="add-edge-server-options-for-lync-server-2010"></a><span data-ttu-id="39e08-104">添加 Lync Server 2010 的边缘服务器选项</span><span class="sxs-lookup"><span data-stu-id="39e08-104">Add Edge Server Options for Lync Server 2010</span></span>

<span data-ttu-id="39e08-105">定义新的边缘服务器或边缘池，并有机会定义新服务器或池的功能。</span><span class="sxs-lookup"><span data-stu-id="39e08-105">You define a new Edge Server or Edge pool and are presented with the opportunity to define features for the new server or pool.</span></span> <span data-ttu-id="39e08-106">可以选择的选项有：</span><span class="sxs-lookup"><span data-stu-id="39e08-106">The options that you can choose are:</span></span>

- <span data-ttu-id="39e08-107">**使用一个 FQDN 和 IP 地址**：选中此复选框可将单个 IPv4 或 IPv6（如果选择同时使用 IPv4 和 IPv6，则需要为每种 IP 地址类型定义一个）地址和完全限定的域名 (FQDN) 用于外部边缘接口。</span><span class="sxs-lookup"><span data-stu-id="39e08-107">**Use a single FQDN and IP address**: Select the check box to use a single IPv4 or IPv6 (if you choose to use both IPv4 and IPv6, then you will need to define one of each IP address type) address and fully qualified domain name (FQDN) for the external Edge interfaces.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="39e08-108">如果选择此选项，则仅使用一个 IP 地址，或一个 IPv4 和一个 IPv6 地址，但是必须将不同的端口号分配给每个边缘接口。</span><span class="sxs-lookup"><span data-stu-id="39e08-108">If you choose this option, you will use only one IP address, or one IPv4 and one IPv6, but you must assign different port numbers to each Edge interface.</span></span>

- <span data-ttu-id="39e08-109">**启用联盟(端口 5061)**：如果要与使用会话初始协议 (SIP) 的其他 SIP 联盟、提供程序或托管服务进行联盟，则选中此复选框。</span><span class="sxs-lookup"><span data-stu-id="39e08-109">**Enable federation (port 5061)**: Select this check box if you will federate with other SIP federations, providers, or hosted offerings that use the session initiation protocol (SIP).</span></span>

- <span data-ttu-id="39e08-110">此边缘池的外部 IP 地址由 **NAT** 转换：如果对边缘外部接口使用专用 IP 地址，并且将提供网络地址转换 (NAT) 设备以在逻辑上将边缘服务器或边缘池放置到后面，请选中此复选框。</span><span class="sxs-lookup"><span data-stu-id="39e08-110">**The external IP address of this Edge pool is translated by NAT**: Select this check box if you use private IP addresses for the Edge external interfaces and will provide a network address translation (NAT) device to place the Edge Server or Edge pool logically behind.</span></span>

## <a name="see-also"></a><span data-ttu-id="39e08-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="39e08-111">See also</span></span>

[<span data-ttu-id="39e08-112">规划外部用户访问</span><span class="sxs-lookup"><span data-stu-id="39e08-112">Planning for External User Access</span></span>](https://technet.microsoft.com/library/ea098933-eff5-461e-aba3-e7f128784dc2.aspx)

[<span data-ttu-id="39e08-113">部署边缘服务器</span><span class="sxs-lookup"><span data-stu-id="39e08-113">Deploying External User Access</span></span>](https://technet.microsoft.com/library/d40c9574-c16b-4fe6-b848-21ae0b7e4f0e.aspx)
