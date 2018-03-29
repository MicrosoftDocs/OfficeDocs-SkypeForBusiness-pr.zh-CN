---
title: 为业务服务器 2015年估计为 Skype 语音用法和通信
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 10/22/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 621b08fb-f894-4d91-ac38-e443401b098b
description: 可以使用以下指标来估计用户通信： 每个站点支持该通讯所需的端口数。
ms.openlocfilehash: dffcfdf7dcf70162b2a9c9ce65ab56b9025a4db0
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="estimating-voice-usage-and-traffic-for-skype-for-business-server-2015"></a><span data-ttu-id="689f8-103">为业务服务器 2015年估计为 Skype 语音用法和通信</span><span class="sxs-lookup"><span data-stu-id="689f8-103">Estimating voice usage and traffic for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="689f8-104">可以使用以下指标来估计用户通信： 每个站点支持该通讯所需的端口数。</span><span class="sxs-lookup"><span data-stu-id="689f8-104">You can use the following metric to estimate user traffic at each site and the number of ports that are required to support that traffic.</span></span>
  
> <span data-ttu-id="689f8-105">对于**低流量**（每个用户每小时一个 PSTN 呼叫），每个端口对应 15 个用户。</span><span class="sxs-lookup"><span data-stu-id="689f8-105">For **Light traffic** (one PSTN call per user per hour), figure 15 users per port.</span></span>
    
> <span data-ttu-id="689f8-106">对于**中等流量**（每个用户每小时 2 个 PSTN 呼叫），每个端口对应 10 个用户。</span><span class="sxs-lookup"><span data-stu-id="689f8-106">For **Medium traffic** (2 PSTN calls per user per hour), figure 10 users per port.</span></span>
    
> <span data-ttu-id="689f8-107">对于**高流量**（每个用户每小时 3 个或更多 PSTN 呼叫），每个端口对应 5 个用户。</span><span class="sxs-lookup"><span data-stu-id="689f8-107">For **Heavy traffic** (3 or more PSTN per user calls per hour), figure 5 users per port.</span></span>
    
<span data-ttu-id="689f8-108">端口数又确定中介服务器和网关所需的数目。</span><span class="sxs-lookup"><span data-stu-id="689f8-108">The number of ports in turn determines the number of Mediation Servers and gateways that will be required.</span></span> <span data-ttu-id="689f8-109">大多数组织考虑部署范围的大小从 2 个端口到端口多达 960 公用交换的电话网络 (PSTN) 网关。</span><span class="sxs-lookup"><span data-stu-id="689f8-109">The public switched telephone network (PSTN) gateways that most organizations consider deploying range in size from 2 ports to as many as 960 ports.</span></span> <span data-ttu-id="689f8-110">（有更大的网关，但这些都主要由电话服务提供程序）。</span><span class="sxs-lookup"><span data-stu-id="689f8-110">(There are even larger gateways, but these are used mainly by telephony service providers.)</span></span>
  
<span data-ttu-id="689f8-p102">例如，具有 10,000 个用户和中等流量的组织将需要 1000 个端口。所需的网关数等于所需的端口总数，由网关的总容量决定。</span><span class="sxs-lookup"><span data-stu-id="689f8-p102">For example, an organization with 10,000 users and medium traffic would require 1000 ports. The number of gateways required would equal the total number of ports required as determined by the total capacity of the gateways.</span></span>
  

