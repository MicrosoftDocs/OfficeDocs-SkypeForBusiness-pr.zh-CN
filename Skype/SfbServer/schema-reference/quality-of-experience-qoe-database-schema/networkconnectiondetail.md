---
title: NetworkConnectionDetail 表
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
description: NetworkConnectionDetail 表将网络连接类型映射到其他位置的用户体验质量数据库中使用的网络连接标识符。 此表是在 Microsoft Lync Server 2013 中引入的。
ms.openlocfilehash: 6df2511c2dfee0158b4633be5dfa8549639cfc6d
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212388"
---
# <a name="networkconnectiondetail-table"></a>NetworkConnectionDetail 表
 
NetworkConnectionDetail 表将网络连接类型映射到其他位置的用户体验质量数据库中使用的网络连接标识符。 此表是在 Microsoft Lync Server 2013 中引入的。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**NetworkConnectionDetailKey** <br/> |tinyint  <br/> |Primary  <br/> |网络连接类型的唯一标识符。  <br/> |
|**NetworkConnectionDetail** <br/> |varchar(256)  <br/> |唯一  <br/> |对应于 NetworkConnectionDetailKey 的网络连接类型。 允许的值包括：  <br/> 0-有线  <br/> 1--WiFi  <br/> 2--以太网  <br/> 3-MobileBB  <br/> 4--其他  <br/> 5-隧道  <br/> |
   

