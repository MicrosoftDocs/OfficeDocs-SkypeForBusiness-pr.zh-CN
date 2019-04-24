---
title: IPAddress 表
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
description: IPAddress 表将 IP 地址映射到其他位置的用户体验质量数据库中使用的唯一的 IP 地址标识符。 此表是在 Microsoft Lync Server 2013 中引入的。
ms.openlocfilehash: b118d85eff7c0f8e355a43e354f97de3c66da7d0
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212205"
---
# <a name="ipaddress-table"></a>IPAddress 表
 
IPAddress 表将 IP 地址映射到其他位置的用户体验质量数据库中使用的唯一的 IP 地址标识符。 此表是在 Microsoft Lync Server 2013 中引入的。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**IPAddressKey** <br/> |int  <br/> |Primary  <br/> |指定的 IP 地址的唯一标识符。  <br/> |
|**IPAddress** <br/> |varchar(50)  <br/> |唯一  <br/> |唯一的 IP 地址 (例如，189.168.1.1) 映射到 IpAddressKey。 这可能是 IPv4 或 IPv6 地址。  <br/> |
   

