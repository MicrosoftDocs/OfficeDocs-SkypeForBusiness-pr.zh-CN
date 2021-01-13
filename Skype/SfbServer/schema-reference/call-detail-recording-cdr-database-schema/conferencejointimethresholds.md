---
title: Skype for Business Server 2015 中的 ConferenceJoinTimeThresholds 表
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
ms.assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
description: ConferenceJoinTimeThresholds 表包含会议加入时间摘要报告使用的分类边界。会议加入时间摘要报告总结了用户成功加入会议所需的时间；这些时间值都报告为一个平均值，且采用以下类别之一：
ms.openlocfilehash: dfa7293307376b5fb5c86cec6f7504d363b005f5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813302"
---
# <a name="conferencejointimethresholds-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的 ConferenceJoinTimeThresholds 表
 
ConferenceJoinTimeThresholds 表包含会议加入时间摘要报告使用的分类边界。会议加入时间摘要报告总结了用户成功加入会议所需的时间；这些时间值都报告为一个平均值，且采用以下类别之一：
  
- 少于 2 秒。
    
- 2 秒到 5 秒之间。
    
- 5 秒到 10 秒之间。
    
- 长于 10 秒。
    
ConferenceJoinTimeThresholds 表包含分类值 2 秒、5 秒和 10 秒。
  
此表在 Microsoft Lync Server 2013 中引入。
  
|**列**|**数据类型**|**键/索引**|**Details**|
|:-----|:-----|:-----|:-----|
|**ThresholdId** <br/> |int  <br/> |主  <br/> |分类的唯一标识符。  <br/> |
|**ThresholdValue** <br/> |int  <br/> || 分类的上限。允许的值包括： <br/>  2  <br/>  5  <br/>  10  <br/> |
   

