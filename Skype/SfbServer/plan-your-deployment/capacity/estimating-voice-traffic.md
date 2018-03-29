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
# <a name="estimating-voice-usage-and-traffic-for-skype-for-business-server-2015"></a>为业务服务器 2015年估计为 Skype 语音用法和通信
 
可以使用以下指标来估计用户通信： 每个站点支持该通讯所需的端口数。
  
> 对于**低流量**（每个用户每小时一个 PSTN 呼叫），每个端口对应 15 个用户。
    
> 对于**中等流量**（每个用户每小时 2 个 PSTN 呼叫），每个端口对应 10 个用户。
    
> 对于**高流量**（每个用户每小时 3 个或更多 PSTN 呼叫），每个端口对应 5 个用户。
    
端口数又确定中介服务器和网关所需的数目。 大多数组织考虑部署范围的大小从 2 个端口到端口多达 960 公用交换的电话网络 (PSTN) 网关。 （有更大的网关，但这些都主要由电话服务提供程序）。
  
例如，具有 10,000 个用户和中等流量的组织将需要 1000 个端口。所需的网关数等于所需的端口总数，由网关的总容量决定。
  

