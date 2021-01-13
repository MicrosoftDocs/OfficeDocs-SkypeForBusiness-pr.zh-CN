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
# <a name="estimating-voice-usage-and-traffic-for-skype-for-business-server"></a>估计 Skype for Business Server 的语音使用情况和流量
 
您可以使用以下指标来估计每个站点上的用户流量以及支持该流量所需的端口数。
  
> 对于 **低流量**（每个用户每小时一个 PSTN 呼叫），每个端口对应 15 个用户。
> 
> 对于 **中等流量**（每个用户每小时 2 个 PSTN 呼叫），每个端口对应 10 个用户。
> 
> 对于 **高流量**（每个用户每小时 3 个或更多 PSTN 呼叫），每个端口对应 5 个用户。
    
端口数反过来决定所需的中介服务器和网关的数量。 公用电话交换网 (PSTN) 网关，大多数组织都考虑部署大小范围从 2 个端口到最多 960 个端口。  (还有更大的网关，但这些网关主要由电话服务提供商使用。) 
  
例如，具有 10,000 个用户和中等流量的组织将需要 1000 个端口。所需的网关数等于所需的端口总数，由网关的总容量决定。
  

