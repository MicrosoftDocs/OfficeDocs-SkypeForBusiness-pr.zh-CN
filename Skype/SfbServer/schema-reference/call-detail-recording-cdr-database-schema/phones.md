---
title: Phones 表
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: Phones 表是一个支持表。 每个表中的记录存储有关数据库中包含记录的 VoIP 呼叫中所涉及的一个电话号码的信息。
ms.openlocfilehash: 733adec46e948c3b7f1d804f57011110355078f4
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30894640"
---
# <a name="phones-table"></a>Phones 表
 
Phones 表是一个支持表。 每个表中的记录存储有关数据库中包含记录的 VoIP 呼叫中所涉及的一个电话号码的信息。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**PhoneId** <br/> |int  <br/> |Primary  <br/> |标识此电话的唯一编号。  <br/> |
|**PhoneUri** <br/> |nvarchar(450)  <br/> | <br/> |电话号码。  <br/> |
|**NextUpdateTS** <br/> |dateTime  <br/> ||时间戳 （仅供内部使用）。  <br/> 此字段是在 Microsoft Lync Server 2013 中引入的。  <br/> |
   

