---
title: 估计 Skype for Business Server 的语音使用情况和流量
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 621b08fb-f894-4d91-ac38-e443401b098b
description: 您可以使用以下指标来估计每个站点上的用户流量以及支持该流量所需的端口数。
ms.openlocfilehash: c631361a7ef6d4706632f59366adac3384a6d255
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827682"
---
# <a name="estimating-voice-usage-and-traffic-for-skype-for-business-server"></a><span data-ttu-id="f4f5c-103">估计 Skype for Business Server 的语音使用情况和流量</span><span class="sxs-lookup"><span data-stu-id="f4f5c-103">Estimating voice usage and traffic for Skype for Business Server</span></span>
 
<span data-ttu-id="f4f5c-104">您可以使用以下指标来估计每个站点上的用户流量以及支持该流量所需的端口数。</span><span class="sxs-lookup"><span data-stu-id="f4f5c-104">You can use the following metric to estimate user traffic at each site and the number of ports that are required to support that traffic.</span></span>
  
> <span data-ttu-id="f4f5c-105">对于 **低流量**（每个用户每小时一个 PSTN 呼叫），每个端口对应 15 个用户。</span><span class="sxs-lookup"><span data-stu-id="f4f5c-105">For **Light traffic** (one PSTN call per user per hour), figure 15 users per port.</span></span>
> 
> <span data-ttu-id="f4f5c-106">对于 **中等流量**（每个用户每小时 2 个 PSTN 呼叫），每个端口对应 10 个用户。</span><span class="sxs-lookup"><span data-stu-id="f4f5c-106">For **Medium traffic** (2 PSTN calls per user per hour), figure 10 users per port.</span></span>
> 
> <span data-ttu-id="f4f5c-107">对于 **高流量**（每个用户每小时 3 个或更多 PSTN 呼叫），每个端口对应 5 个用户。</span><span class="sxs-lookup"><span data-stu-id="f4f5c-107">For **Heavy traffic** (3 or more PSTN per user calls per hour), figure 5 users per port.</span></span>
    
<span data-ttu-id="f4f5c-108">端口数反过来决定所需的中介服务器和网关的数量。</span><span class="sxs-lookup"><span data-stu-id="f4f5c-108">The number of ports in turn determines the number of Mediation Servers and gateways that will be required.</span></span> <span data-ttu-id="f4f5c-109">公用电话交换网 (PSTN) 网关，大多数组织都考虑部署大小范围从 2 个端口到最多 960 个端口。</span><span class="sxs-lookup"><span data-stu-id="f4f5c-109">The public switched telephone network (PSTN) gateways that most organizations consider deploying range in size from 2 ports to as many as 960 ports.</span></span> <span data-ttu-id="f4f5c-110"> (还有更大的网关，但这些网关主要由电话服务提供商使用。) </span><span class="sxs-lookup"><span data-stu-id="f4f5c-110">(There are even larger gateways, but these are used mainly by telephony service providers.)</span></span>
  
<span data-ttu-id="f4f5c-p102">例如，具有 10,000 个用户和中等流量的组织将需要 1000 个端口。所需的网关数等于所需的端口总数，由网关的总容量决定。</span><span class="sxs-lookup"><span data-stu-id="f4f5c-p102">For example, an organization with 10,000 users and medium traffic would require 1000 ports. The number of gateways required would equal the total number of ports required as determined by the total capacity of the gateways.</span></span>
  

