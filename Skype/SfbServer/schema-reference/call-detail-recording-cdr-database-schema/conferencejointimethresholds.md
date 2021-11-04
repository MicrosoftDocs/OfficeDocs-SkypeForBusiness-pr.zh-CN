---
title: ConferenceJoinTimeThresholds table in Skype for Business Server 2015
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
ms.assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
description: ConferenceJoinTimeThresholds 表包含会议加入时间摘要报告使用的分类边界。会议加入时间摘要报告总结了用户成功加入会议所需的时间；这些时间值都报告为一个平均值，且采用以下类别之一：
ms.openlocfilehash: 61267cb92e543da3b07b97bd344bc07d2845d6a6
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60749901"
---
# <a name="conferencejointimethresholds-table-in-skype-for-business-server-2015"></a>ConferenceJoinTimeThresholds table in Skype for Business Server 2015
 
ConferenceJoinTimeThresholds 表包含会议加入时间摘要报告使用的分类边界。会议加入时间摘要报告总结了用户成功加入会议所需的时间；这些时间值都报告为一个平均值，且采用以下类别之一：
  
- 少于 2 秒。
    
- 2 秒到 5 秒之间。
    
- 5 秒到 10 秒之间。
    
- 长于 10 秒。
    
ConferenceJoinTimeThresholds 表包含分类值 2 秒、5 秒和 10 秒。
  
此表在 Microsoft Lync Server 2013 中引入。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**ThresholdId** <br/> |int  <br/> |主  <br/> |分类的唯一标识符。  <br/> |
|**ThresholdValue** <br/> |int  <br/> || 分类的上限。允许的值包括： <br/>  2 <br/>  5 <br/>  10  <br/> |
   

