---
title: 为业务服务器的 Skype 估计语音的使用和流量
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 621b08fb-f894-4d91-ac38-e443401b098b
description: 您可以使用以下任一指标来估计每个站点和支持该流量所需的端口数的用户通信。
ms.openlocfilehash: ec4079608bedc19e9cba2e6c1e872d770e6bce46
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20980462"
---
# <a name="estimating-voice-usage-and-traffic-for-skype-for-business-server"></a><span data-ttu-id="481a5-103">为业务服务器的 Skype 估计语音的使用和流量</span><span class="sxs-lookup"><span data-stu-id="481a5-103">Estimating voice usage and traffic for Skype for Business Server</span></span>
 
<span data-ttu-id="481a5-104">您可以使用以下任一指标来估计每个站点和支持该流量所需的端口数的用户通信。</span><span class="sxs-lookup"><span data-stu-id="481a5-104">You can use the following metric to estimate user traffic at each site and the number of ports that are required to support that traffic.</span></span>
  
> <span data-ttu-id="481a5-105">对于**低流量**（每个用户每小时一个 PSTN 呼叫），每个端口对应 15 个用户。</span><span class="sxs-lookup"><span data-stu-id="481a5-105">For **Light traffic** (one PSTN call per user per hour), figure 15 users per port.</span></span>
    
> <span data-ttu-id="481a5-106">对于**中等流量**（每个用户每小时 2 个 PSTN 呼叫），每个端口对应 10 个用户。</span><span class="sxs-lookup"><span data-stu-id="481a5-106">For **Medium traffic** (2 PSTN calls per user per hour), figure 10 users per port.</span></span>
    
> <span data-ttu-id="481a5-107">对于**高流量**（每个用户每小时 3 个或更多 PSTN 呼叫），每个端口对应 5 个用户。</span><span class="sxs-lookup"><span data-stu-id="481a5-107">For **Heavy traffic** (3 or more PSTN per user calls per hour), figure 5 users per port.</span></span>
    
<span data-ttu-id="481a5-108">反过来的端口数确定的中介服务器和网关都需要的数目。</span><span class="sxs-lookup"><span data-stu-id="481a5-108">The number of ports in turn determines the number of Mediation Servers and gateways that will be required.</span></span> <span data-ttu-id="481a5-109">大多数组织考虑部署大小在 2 端口到 960 端口公用电话交换网 (pstn) 网关。</span><span class="sxs-lookup"><span data-stu-id="481a5-109">The public switched telephone network (PSTN) gateways that most organizations consider deploying range in size from 2 ports to as many as 960 ports.</span></span> <span data-ttu-id="481a5-110">（有更大的网关，但是这些主要由电话服务提供程序。）</span><span class="sxs-lookup"><span data-stu-id="481a5-110">(There are even larger gateways, but these are used mainly by telephony service providers.)</span></span>
  
<span data-ttu-id="481a5-p102">例如，具有 10,000 个用户和中等流量的组织将需要 1000 个端口。所需的网关数等于所需的端口总数，由网关的总容量决定。</span><span class="sxs-lookup"><span data-stu-id="481a5-p102">For example, an organization with 10,000 users and medium traffic would require 1000 ports. The number of gateways required would equal the total number of ports required as determined by the total capacity of the gateways.</span></span>
  

