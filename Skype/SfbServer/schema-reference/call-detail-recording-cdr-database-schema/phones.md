---
title: Phones 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: 电话表是支持表。 表中的每条记录存储信息涉及数据库中具有记录的 VoIP 电话一个电话号码。
ms.openlocfilehash: 8ec2095b857ba474a92bf0766d86119500919f51
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="phones-table"></a>Phones 表
 
电话表是支持表。 表中的每条记录存储信息涉及数据库中具有记录的 VoIP 电话一个电话号码。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**PhoneId** <br/> |int  <br/> |Primary  <br/> |标识此电话的唯一编号。  <br/> |
|**PhoneUri** <br/> |nvarchar(450)  <br/> | <br/> |电话号码。  <br/> |
|**NextUpdateTS** <br/> |日期时间  <br/> ||时间戳 （仅供内部使用）。  <br/> 在 Microsoft Lync Server 2013 引入了此字段。  <br/> |
   

