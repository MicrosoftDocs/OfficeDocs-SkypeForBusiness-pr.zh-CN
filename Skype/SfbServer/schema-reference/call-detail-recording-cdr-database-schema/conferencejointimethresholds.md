---
title: 在业务服务器 2015年的 Skype 的 ConferenceJoinTimeThresholds 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
description: ConferenceJoinTimeThresholds 表中包含分类边界使用会议加入时间摘要报告。 会议加入时间摘要报告总结了用户成功加入会议; 所需的时间量两个时间值报告平均，而且在以下几个类别之一：
ms.openlocfilehash: 3646337c9e9f20ac0b1dabfdd5504ce83dfa5c40
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="conferencejointimethresholds-table-in-skype-for-business-server-2015"></a>在业务服务器 2015年的 Skype 的 ConferenceJoinTimeThresholds 表
 
ConferenceJoinTimeThresholds 表中包含分类边界使用会议加入时间摘要报告。 会议加入时间摘要报告总结了用户成功加入会议; 所需的时间量两个时间值报告平均，而且在以下几个类别之一：
  
- 2 秒之内。
    
- 介于 2 秒到 5 秒。
    
- 之间 5 秒到 10 秒。
    
- 10 秒钟以上。
    
ConferenceJoinTimeThresholds 表包含分类值 2 秒、 5 秒到 10 秒。
  
在 Microsoft Lync Server 2013 引入了此表。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**ThresholdId** <br/> |int  <br/> |Primary  <br/> |分类的唯一标识符。  <br/> |
|**ThresholdValue** <br/> |int  <br/> || 分类的上限。 允许的值包括： <br/>  2 <br/>  5 <br/>  10 <br/> |
   

