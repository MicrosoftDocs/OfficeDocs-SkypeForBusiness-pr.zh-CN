---
title: NetworkConnectionDetail 表
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
description: NetworkConnectionDetail 表可将网络连接类型映射到在体验质量数据库中的其他位置使用的网络连接标识符。 此表在 Microsoft Lync Server 2013 中引入。
ms.openlocfilehash: d629c3107aa52b06376974b385b874f6956d0156
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60741788"
---
# <a name="networkconnectiondetail-table"></a>NetworkConnectionDetail 表
 
NetworkConnectionDetail 表可将网络连接类型映射到在体验质量数据库中的其他位置使用的网络连接标识符。 此表在 Microsoft Lync Server 2013 中引入。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**NetworkConnectionDetailKey** <br/> |tinyint  <br/> |主  <br/> |网络连接类型的唯一标识符。  <br/> |
|**NetworkConnectionDetail** <br/> |varchar (256)   <br/> |独特  <br/> |对应于 NetworkConnectionDetailKey 的网络连接类型。允许的值包括：  <br/> 0 -- 有线  <br/> 1 -- WiFi  <br/> 2 -- 以太网  <br/> 3 -- MobileBB  <br/> 4 -- 其他  <br/> 5 -- Tunnel  <br/> |
   

