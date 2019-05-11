---
title: ConferenceJoinTimeThresholds 表中的业务服务器 2015 Skype
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
description: ConferenceJoinTimeThresholds 表包含会议加入时间摘要报表所使用的分类边界。 会议加入时间摘要报告总结了所需的用户，以便成功加入会议; 的时间量这些时间值报告作为平均和以下类别之一：
ms.openlocfilehash: 75df75e16d2a4ed34f667c94f2b2f0960f56e7ff
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901434"
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
   

