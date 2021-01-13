---
title: NetworkConnectionDetail 表
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
description: NetworkConnectionDetail 表可将网络连接类型映射到在体验质量数据库中的其他位置使用的网络连接标识符。 此表在 Microsoft Lync Server 2013 中引入。
ms.openlocfilehash: 2e03e7935370e71a8070ed1882f61ac5480f312e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806302"
---
# <a name="networkconnectiondetail-table"></a>NetworkConnectionDetail 表
 
NetworkConnectionDetail 表可将网络连接类型映射到在体验质量数据库中的其他位置使用的网络连接标识符。 此表在 Microsoft Lync Server 2013 中引入。
  
|**列**|**数据类型**|**键/索引**|**Details**|
|:-----|:-----|:-----|:-----|
|**NetworkConnectionDetailKey** <br/> |tinyint  <br/> |主  <br/> |网络连接类型的唯一标识符。  <br/> |
|**NetworkConnectionDetail** <br/> |varchar (256)   <br/> |独特  <br/> |对应于 NetworkConnectionDetailKey 的网络连接类型。允许的值包括：  <br/> 0 -- 有线  <br/> 1 -- WiFi  <br/> 2 -- 以太网  <br/> 3 -- MobileBB  <br/> 4 -- 其他  <br/> 5 -- 隧道  <br/> |
   

