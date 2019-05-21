---
title: NetworkConnectionDetail 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
description: NetworkConnectionDetail 表将网络连接类型映射到 "体验质量" 数据库中其他位置使用的网络连接标识符。 此表是在 Microsoft Lync Server 2013 中引入的。
ms.openlocfilehash: c13725e7df8a164766faa6847fc8097a24a9df53
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294815"
---
# <a name="networkconnectiondetail-table"></a>NetworkConnectionDetail 表
 
NetworkConnectionDetail 表将网络连接类型映射到 "体验质量" 数据库中其他位置使用的网络连接标识符。 此表是在 Microsoft Lync Server 2013 中引入的。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**NetworkConnectionDetailKey** <br/> |tinyint  <br/> |Primary  <br/> |网络连接类型的唯一标识符。  <br/> |
|**NetworkConnectionDetail** <br/> |varchar (256)  <br/> |唯一  <br/> |与 NetworkConnectionDetailKey 对应的网络连接类型。 允许的值包括：  <br/> 0--有线  <br/> 1--WiFi  <br/> 2--以太网  <br/> 3--MobileBB  <br/> 4--其他  <br/> 5--隧道  <br/> |
   

