---
title: Phones 表
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: Phones 表是一个支持表。 表中的每条记录都存储有关数据库中具有记录的 VoIP 呼叫中涉及的一个电话号码的信息。
ms.openlocfilehash: 938e00267f5f356c646d363033ef9a8917b910261f873637c0f6b3a6b9ff8742
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54329456"
---
# <a name="phones-table"></a>Phones 表
 
Phones 表是一个支持表。 表中的每条记录都存储有关数据库中具有记录的 VoIP 呼叫中涉及的一个电话号码的信息。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**PhoneId** <br/> |int  <br/> |主  <br/> |标识此电话的唯一号码。  <br/> |
|**PhoneUri** <br/> |nvarchar (450)   <br/> | <br/> |电话个数。  <br/> |
|**NextUpdateTS** <br/> |dateTime  <br/> ||时间戳 (供内部使用) 。  <br/> 此字段在 Microsoft Lync Server 2013 中引入。  <br/> |
   

