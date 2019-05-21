---
title: Phones 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: "\"电话\" 表是支持表。 表中的每条记录存储了在具有数据库中的记录的 VoIP 呼叫中涉及的一个电话号码的相关信息。"
ms.openlocfilehash: 684586f21b16c785bcc75458e5330c42aad2ccb4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295942"
---
# <a name="phones-table"></a>Phones 表
 
"电话" 表是支持表。 表中的每条记录存储了在具有数据库中的记录的 VoIP 呼叫中涉及的一个电话号码的相关信息。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**PhoneId** <br/> |int  <br/> |Primary  <br/> |标识此电话的唯一号码。  <br/> |
|**PhoneUri** <br/> |nvarchar (450)  <br/> | <br/> |电话号码。  <br/> |
|**NextUpdateTS** <br/> |从中  <br/> ||时间戳 (仅供内部使用)。  <br/> 此字段是在 Microsoft Lync Server 2013 中引入的。  <br/> |
   

