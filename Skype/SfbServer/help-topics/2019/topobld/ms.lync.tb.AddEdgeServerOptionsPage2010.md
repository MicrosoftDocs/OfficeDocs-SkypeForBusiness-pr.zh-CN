---
title: 添加 Lync Server 2010 边缘服务器选项
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerOptionsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b059af5-e83f-4564-90b2-d7ebb9e551c2
description: 定义新的边缘服务器或边缘池和显示定义的新服务器或池的功能的机会。 您可以选择的选项包括：
ms.openlocfilehash: c031480dd3553aa4fc1ca2f2a8ddd03f67d9bc02
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2018
---
# <a name="add-edge-server-options-for-lync-server-2010"></a><span data-ttu-id="da937-104">添加 Lync Server 2010 边缘服务器选项</span><span class="sxs-lookup"><span data-stu-id="da937-104">Add Edge Server Options for Lync Server 2010</span></span>
 
<span data-ttu-id="da937-105">定义新的边缘服务器或边缘池和显示定义的新服务器或池的功能的机会。</span><span class="sxs-lookup"><span data-stu-id="da937-105">You define a new Edge Server or Edge pool and are presented with the opportunity to define features for the new server or pool.</span></span> <span data-ttu-id="da937-106">您可以选择的选项包括：</span><span class="sxs-lookup"><span data-stu-id="da937-106">The options that you can choose are:</span></span>
  
- <span data-ttu-id="da937-107">**使用单个 FQDN 和 IP 地址**： 选中的复选框 （如果您选择使用 IPv4 和 IPv6，则您将需要定义每个 IP 地址类型之一） 使用单个 IPv4 或 IPv6 地址和完全限定的域名 (FQDN) 的外部边缘接口。</span><span class="sxs-lookup"><span data-stu-id="da937-107">**Use a single FQDN and IP address**: Select the check box to use a single IPv4 or IPv6 (if you choose to use both IPv4 and IPv6, then you will need to define one of each IP address type) address and fully qualified domain name (FQDN) for the external Edge interfaces.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="da937-108">如果您选择此选项，您将使用只有一个 IP 地址，或一个 IPv4 和一个 IPv6，但必须将不同的端口号分配给每个边缘接口。</span><span class="sxs-lookup"><span data-stu-id="da937-108">If you choose this option, you will use only one IP address, or one IPv4 and one IPv6, but you must assign different port numbers to each Edge interface.</span></span> 
  
- <span data-ttu-id="da937-109">**启用联盟 （端口 5061）**： 如果您将与其他 SIP 联盟、 提供程序或使用会话初始协议 (SIP) 的托管的服务建立联盟，请选中此复选框。</span><span class="sxs-lookup"><span data-stu-id="da937-109">**Enable federation (port 5061)**: Select this check box if you will federate with other SIP federations, providers, or hosted offerings that use the session initiation protocol (SIP).</span></span>
    
- <span data-ttu-id="da937-110">**此边缘池的外部 IP 地址由 NAT 转换**： 选中此复选框，如果您使用的边缘外部接口的专用 IP 地址并将提供一个网络地址转换 (NAT) 设备，以将边缘服务器或边缘池逻辑隐藏。</span><span class="sxs-lookup"><span data-stu-id="da937-110">**The external IP address of this Edge pool is translated by NAT**: Select this check box if you use private IP addresses for the Edge external interfaces and will provide a network address translation (NAT) device to place the Edge Server or Edge pool logically behind.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="da937-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="da937-111">See also</span></span>

#### 

[<span data-ttu-id="da937-112">规划外部用户访问</span><span class="sxs-lookup"><span data-stu-id="da937-112">Planning for External User Access</span></span>](http://technet.microsoft.com/library/ea098933-eff5-461e-aba3-e7f128784dc2.aspx)
  
[<span data-ttu-id="da937-113">部署外部用户访问</span><span class="sxs-lookup"><span data-stu-id="da937-113">Deploying External User Access</span></span>](http://technet.microsoft.com/library/d40c9574-c16b-4fe6-b848-21ae0b7e4f0e.aspx)

