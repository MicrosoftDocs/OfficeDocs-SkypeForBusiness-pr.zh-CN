---
title: 估计呼叫的语音用法和Skype for Business Server
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
description: 您可以使用以下指标估计每个站点的用户流量以及支持该流量所需的端口数。
ms.openlocfilehash: 470590baf8ce5735b77576292fc6558d916dd3a7173b95c113b74d42f35c5224
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54318835"
---
# <a name="estimating-voice-usage-and-traffic-for-skype-for-business-server"></a>估计呼叫的语音用法和Skype for Business Server
 
您可以使用以下指标估计每个站点的用户流量以及支持该流量所需的端口数。
  
> 对于 **低流量**（每个用户每小时一个 PSTN 呼叫），每个端口对应 15 个用户。
> 
> 对于 **中等流量**（每个用户每小时 2 个 PSTN 呼叫），每个端口对应 10 个用户。
> 
> 对于 **高流量**（每个用户每小时 3 个或更多 PSTN 呼叫），每个端口对应 5 个用户。
    
端口数反过来决定所需的中介服务器和网关的数量。 公用电话交换网 (PSTN) 网关，大多数组织考虑部署大小范围从 2 个端口到最多 960 个端口。  (还有更大的网关，但这些网关主要由电话服务提供商) 
  
例如，具有 10,000 个用户和中等流量的组织将需要 1000 个端口。所需的网关数等于所需的端口总数，由网关的总容量决定。
  

