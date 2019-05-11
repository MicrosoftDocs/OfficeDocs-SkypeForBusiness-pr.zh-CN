---
title: IPAddress 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
description: IPAddress 表将 IP 地址映射到其他位置的用户体验质量数据库中使用的唯一的 IP 地址标识符。 此表是在 Microsoft Lync Server 2013 中引入的。
ms.openlocfilehash: d7d3b5f9192c2385836f42f9c430da5b99752892
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920031"
---
# <a name="ipaddress-table"></a>IPAddress 表
 
IPAddress 表将 IP 地址映射到其他位置的用户体验质量数据库中使用的唯一的 IP 地址标识符。 此表是在 Microsoft Lync Server 2013 中引入的。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**IPAddressKey** <br/> |int  <br/> |Primary  <br/> |指定的 IP 地址的唯一标识符。  <br/> |
|**IPAddress** <br/> |varchar(50)  <br/> |唯一  <br/> |唯一的 IP 地址 (例如，189.168.1.1) 映射到 IpAddressKey。 这可能是 IPv4 或 IPv6 地址。  <br/> |
   

