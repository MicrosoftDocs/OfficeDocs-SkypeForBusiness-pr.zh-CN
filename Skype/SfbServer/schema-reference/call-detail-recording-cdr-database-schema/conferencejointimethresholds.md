---
title: Skype for Business Server 2015 中的 ConferenceJoinTimeThresholds 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
description: 'ConferenceJoinTimeThresholds 表包含 "会议加入时间摘要" 报表使用的分类边界。 "会议加入时间摘要" 报表汇总了用户成功加入会议所需的时间量;这些时间值以平均值和以下类别之一报告:'
ms.openlocfilehash: 4b2f27b6ab826ff95c1478cf54e8a21c148b1d3c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296495"
---
# <a name="conferencejointimethresholds-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的 ConferenceJoinTimeThresholds 表
 
ConferenceJoinTimeThresholds 表包含 "会议加入时间摘要" 报表使用的分类边界。 "会议加入时间摘要" 报表汇总了用户成功加入会议所需的时间量;这些时间值以平均值和以下类别之一报告:
  
- 不到2秒。
    
- 介于2秒和5秒之间。
    
- 介于5秒和10秒之间。
    
- 10秒以上。
    
ConferenceJoinTimeThresholds 表包含分类值2秒、5秒和10秒钟。
  
此表是在 Microsoft Lync Server 2013 中引入的。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**ThresholdId** <br/> |int  <br/> |Primary  <br/> |分类的唯一标识符。  <br/> |
|**ThresholdValue** <br/> |int  <br/> || 分类的上限。 允许的值包括： <br/>  2 <br/>  5 <br/>  10 <br/> |
   

