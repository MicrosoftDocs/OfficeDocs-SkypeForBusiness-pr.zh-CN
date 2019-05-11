---
title: 为 Lync Server 2010 添加 Edge Server 选项
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerOptionsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b059af5-e83f-4564-90b2-d7ebb9e551c2
description: 定义新的边缘服务器或边缘池和显示定义的新服务器或池的功能的机会。 您可以选择的选项包括：
ms.openlocfilehash: cb2b7f1df7da9abbe5eb4d8e5b451f7f0db05d0f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33886288"
---
# <a name="add-edge-server-options-for-lync-server-2010"></a><span data-ttu-id="59b57-104">为 Lync Server 2010 添加 Edge Server 选项</span><span class="sxs-lookup"><span data-stu-id="59b57-104">Add Edge Server Options for Lync Server 2010</span></span>

<span data-ttu-id="59b57-105">定义新的边缘服务器或边缘池和显示定义的新服务器或池的功能的机会。</span><span class="sxs-lookup"><span data-stu-id="59b57-105">You define a new Edge Server or Edge pool and are presented with the opportunity to define features for the new server or pool.</span></span> <span data-ttu-id="59b57-106">您可以选择的选项包括：</span><span class="sxs-lookup"><span data-stu-id="59b57-106">The options that you can choose are:</span></span>

- <span data-ttu-id="59b57-107">**使用单个 FQDN 和 IP 地址**： 选中的复选框 （如果您选择使用 IPv4 和 IPv6，则您将需要定义每个 IP 地址类型之一） 使用单个 IPv4 或 IPv6 地址和完全限定的域名 (FQDN) 的外部边缘接口。</span><span class="sxs-lookup"><span data-stu-id="59b57-107">**Use a single FQDN and IP address**: Select the check box to use a single IPv4 or IPv6 (if you choose to use both IPv4 and IPv6, then you will need to define one of each IP address type) address and fully qualified domain name (FQDN) for the external Edge interfaces.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="59b57-108">如果您选择此选项，您将使用只有一个 IP 地址，或一个 IPv4 和一个 IPv6，但必须将不同的端口号分配给每个边缘接口。</span><span class="sxs-lookup"><span data-stu-id="59b57-108">If you choose this option, you will use only one IP address, or one IPv4 and one IPv6, but you must assign different port numbers to each Edge interface.</span></span>

- <span data-ttu-id="59b57-109">**启用联盟 （端口 5061）**： 如果您将与其他 SIP 联盟、 提供程序或使用会话初始协议 (SIP) 的托管的服务建立联盟，请选中此复选框。</span><span class="sxs-lookup"><span data-stu-id="59b57-109">**Enable federation (port 5061)**: Select this check box if you will federate with other SIP federations, providers, or hosted offerings that use the session initiation protocol (SIP).</span></span>

- <span data-ttu-id="59b57-110">**此边缘池的外部 IP 地址由 NAT 转换**： 选中此复选框，如果您使用的边缘外部接口的专用 IP 地址并将提供一个网络地址转换 (NAT) 设备，以将边缘服务器或边缘池逻辑隐藏。</span><span class="sxs-lookup"><span data-stu-id="59b57-110">**The external IP address of this Edge pool is translated by NAT**: Select this check box if you use private IP addresses for the Edge external interfaces and will provide a network address translation (NAT) device to place the Edge Server or Edge pool logically behind.</span></span>

## <a name="see-also"></a><span data-ttu-id="59b57-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="59b57-111">See also</span></span>

[<span data-ttu-id="59b57-112">规划外部用户访问</span><span class="sxs-lookup"><span data-stu-id="59b57-112">Planning for External User Access</span></span>](https://technet.microsoft.com/library/ea098933-eff5-461e-aba3-e7f128784dc2.aspx)

[<span data-ttu-id="59b57-113">部署外部用户访问</span><span class="sxs-lookup"><span data-stu-id="59b57-113">Deploying External User Access</span></span>](https://technet.microsoft.com/library/d40c9574-c16b-4fe6-b848-21ae0b7e4f0e.aspx)
