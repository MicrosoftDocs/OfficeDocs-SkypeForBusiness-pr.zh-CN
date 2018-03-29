---
title: NetworkConnectionDetail 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
description: NetworkConnectionDetail 表映射到网络连接标识符体验质量数据库中的其他位置使用的网络连接类型。 在 Microsoft Lync Server 2013 引入了此表。
ms.openlocfilehash: cc1eb91d3c633ed9455a0476b613430dfa8e3d6b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="networkconnectiondetail-table"></a>NetworkConnectionDetail 表
 
NetworkConnectionDetail 表映射到网络连接标识符体验质量数据库中的其他位置使用的网络连接类型。 在 Microsoft Lync Server 2013 引入了此表。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**NetworkConnectionDetailKey** <br/> |tinyint  <br/> |Primary  <br/> |网络连接类型的唯一标识符。  <br/> |
|**NetworkConnectionDetail** <br/> |varchar(256)  <br/> |唯一  <br/> |对应于 NetworkConnectionDetailKey 的网络连接类型。 允许的值包括：  <br/> 0--有线  <br/> 1-WiFi  <br/> 2-以太网  <br/> 3-MobileBB  <br/> 4-其他  <br/> 5 — 隧道  <br/> |
   

