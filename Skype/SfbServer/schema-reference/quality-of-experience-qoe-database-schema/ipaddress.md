---
title: Ip 地址表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
description: Ip 地址表将 IP 地址映射到体验质量数据库中的其他位置使用唯一 IP 地址标识。 在 Microsoft Lync Server 2013 引入了此表。
ms.openlocfilehash: 6372d46b69046f944ba33d4deff6d29e923a94cb
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="ipaddress-table"></a>Ip 地址表
 
Ip 地址表将 IP 地址映射到体验质量数据库中的其他位置使用唯一 IP 地址标识。 在 Microsoft Lync Server 2013 引入了此表。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**IPAddressKey** <br/> |int  <br/> |Primary  <br/> |指定的 IP 地址的唯一标识符。  <br/> |
|**Ip 地址** <br/> |varchar(50)  <br/> |唯一  <br/> |唯一的 IP 地址 (例如，189.168.1.1) 映射到 IpAddressKey。 这可能是 IPv4 或 IPv6 地址。  <br/> |
   

