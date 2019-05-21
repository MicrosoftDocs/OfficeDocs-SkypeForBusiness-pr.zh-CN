---
title: 估计 Skype for business 服务器的语音使用和流量
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 621b08fb-f894-4d91-ac38-e443401b098b
description: 你可以使用以下指标估计每个网站上的用户流量以及支持该流量所需的端口数。
ms.openlocfilehash: 09c3e638d25225376b95afd60bdd6d3c311c1f5a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277613"
---
# <a name="estimating-voice-usage-and-traffic-for-skype-for-business-server"></a>估计 Skype for business 服务器的语音使用和流量
 
你可以使用以下指标估计每个网站上的用户流量以及支持该流量所需的端口数。
  
> 对于**低流量**（每个用户每小时一个 PSTN 呼叫），每个端口对应 15 个用户。
> 
> 对于**中等流量**（每个用户每小时 2 个 PSTN 呼叫），每个端口对应 10 个用户。
> 
> 对于**高流量**（每个用户每小时 3 个或更多 PSTN 呼叫），每个端口对应 5 个用户。
    
端口数依次确定所需中介服务器和网关的数量。 大多数组织考虑将范围从2个端口部署到最多960端口的公共交换电话网络 (PSTN) 网关。 (甚至更大的网关, 但主要由电话服务提供商使用。)
  
例如，具有 10,000 个用户和中等流量的组织将需要 1000 个端口。所需的网关数等于所需的端口总数，由网关的总容量决定。
  

