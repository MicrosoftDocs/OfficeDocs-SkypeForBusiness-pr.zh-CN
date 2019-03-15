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
ms.openlocfilehash: e69c559c4ed56010dac3a81a97837f1131e62a2e
ms.sourcegitcommit: 27f1ecb730355dcfac2f4be3f5642f383d5532ad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2019
ms.locfileid: "25376005"
---
# <a name="estimating-voice-usage-and-traffic-for-skype-for-business-server"></a>为业务服务器的 Skype 估计语音的使用和流量
 
您可以使用以下任一指标来估计每个站点和支持该流量所需的端口数的用户通信。
  
> 对于**低流量**（每个用户每小时一个 PSTN 呼叫），每个端口对应 15 个用户。
> 
> 对于**中等流量**（每个用户每小时 2 个 PSTN 呼叫），每个端口对应 10 个用户。
> 
> 对于**高流量**（每个用户每小时 3 个或更多 PSTN 呼叫），每个端口对应 5 个用户。
    
反过来的端口数确定的中介服务器和网关都需要的数目。 大多数组织考虑部署大小在 2 端口到 960 端口公用电话交换网 (pstn) 网关。 （有更大的网关，但是这些主要由电话服务提供程序。）
  
例如，具有 10,000 个用户和中等流量的组织将需要 1000 个端口。所需的网关数等于所需的端口总数，由网关的总容量决定。
  

