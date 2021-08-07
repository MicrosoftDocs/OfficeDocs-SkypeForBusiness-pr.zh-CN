---
title: IPAddress 表
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
ms.assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
description: IPAddress 表将 IP 地址映射到可在用户体验质量数据库中的任何其他位置使用的唯一 IP 地址标识符。 此表在 Microsoft Lync Server 2013 中引入。
ms.openlocfilehash: db9405a05335974456f77d8117f9e3f64e9832750c3d2c23441a5a587ca91d7a
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54305094"
---
# <a name="ipaddress-table"></a>IPAddress 表
 
IPAddress 表将 IP 地址映射到可在用户体验质量数据库中的任何其他位置使用的唯一 IP 地址标识符。 此表在 Microsoft Lync Server 2013 中引入。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**IPAddressKey** <br/> |int  <br/> |主  <br/> |指定的 IP 地址的唯一标识符。  <br/> |
|**IPAddress** <br/> |varchar (50)   <br/> |独特  <br/> |映射到 IpAddressKey 的唯一 IP 地址（例如，189.168.1.1）。这可能是 IPv4 地址或 IPv6 地址。  <br/> |
   

