---
title: IPAddress 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
description: IPAddress 表将 IP 地址映射到 "体验质量" 数据库中其他位置使用的唯一 IP 地址标识符。 此表是在 Microsoft Lync Server 2013 中引入的。
ms.openlocfilehash: 74d74636b7183d1369db85c363997460a434d8f3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294920"
---
# <a name="ipaddress-table"></a>IPAddress 表
 
IPAddress 表将 IP 地址映射到 "体验质量" 数据库中其他位置使用的唯一 IP 地址标识符。 此表是在 Microsoft Lync Server 2013 中引入的。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**IPAddressKey** <br/> |int  <br/> |Primary  <br/> |指定 IP 地址的唯一标识符。  <br/> |
|**IPAddress** <br/> |varchar(50)  <br/> |唯一  <br/> |映射到 IpAddressKey 的唯一 IP 地址 (例如, 189.168.1.1)。 这可能是 IPv4 地址或 IPv6 地址。  <br/> |
   

