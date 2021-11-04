---
title: Phones 表
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: Phones 表是一个支持表。 表中的每条记录都存储有关数据库中具有记录的 VoIP 呼叫中涉及的一个电话号码的信息。
ms.openlocfilehash: 81f6b570e168450d457fedabc2ad9d26b3c7abfd
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60767480"
---
# <a name="phones-table"></a>Phones 表
 
Phones 表是一个支持表。 表中的每条记录都存储有关数据库中具有记录的 VoIP 呼叫中涉及的一个电话号码的信息。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**PhoneId** <br/> |int  <br/> |主  <br/> |标识此电话的唯一号码。  <br/> |
|**PhoneUri** <br/> |nvarchar (450)   <br/> | <br/> |电话个数。  <br/> |
|**NextUpdateTS** <br/> |dateTime  <br/> ||仅 (内部使用的时间戳) 。  <br/> 此字段在 Microsoft Lync Server 2013 中引入。  <br/> |
   

