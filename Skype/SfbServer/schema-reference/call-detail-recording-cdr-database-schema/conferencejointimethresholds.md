---
title: ConferenceJoinTimeThresholds 表中的业务服务器 2015 Skype
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
description: ConferenceJoinTimeThresholds 表包含会议加入时间摘要报表所使用的分类边界。 会议加入时间摘要报告总结了所需的用户，以便成功加入会议; 的时间量这些时间值报告作为平均和以下类别之一：
ms.openlocfilehash: d6fbae0d077719782b3e93c0fe008ee35ce3370e
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895815"
---
# <a name="conferencejointimethresholds-table-in-skype-for-business-server-2015"></a>ConferenceJoinTimeThresholds 表中的业务服务器 2015 Skype
 
ConferenceJoinTimeThresholds 表包含会议加入时间摘要报表所使用的分类边界。 会议加入时间摘要报告总结了所需的用户，以便成功加入会议; 的时间量这些时间值报告作为平均和以下类别之一：
  
- 少于 2 秒。
    
- 之间 2 秒到 5 秒。
    
- 之间 5 秒到 10 秒。
    
- 10 秒之上。
    
ConferenceJoinTimeThresholds 表包含分类值 2 秒、 5 秒到 10 秒。
  
此表是在 Microsoft Lync Server 2013 中引入的。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**ThresholdId** <br/> |int  <br/> |Primary  <br/> |分类的唯一标识符。  <br/> |
|**ThresholdValue** <br/> |int  <br/> || 分类的上限。 允许的值包括： <br/>  2 <br/>  5 <br/>  10 <br/> |
   

