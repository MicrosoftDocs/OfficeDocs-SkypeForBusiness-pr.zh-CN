---
title: 媒体视图
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
description: 媒体视图存储信息的对等会话中使用的一种媒体类型。 如果使用多个媒体类型，将可以由多个记录在表中，表示一个会话。 在 Microsoft Lync Server 2013 引入了此视图。
ms.openlocfilehash: 0cbcb353ec768b9d3ee66f1a10d59b5c4523acea
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="media-view"></a>媒体视图
 
媒体视图存储信息的对等会话中使用的一种媒体类型。 如果使用多个媒体类型，将可以由多个记录在表中，表示一个会话。 在 Microsoft Lync Server 2013 引入了此视图。
  
> [!NOTE]
> 媒体视图不应该用于计算会话的媒体持续时间。 该视图包含媒体交换会话中信号传输的详细的信息。 媒体交换通过 INVITE 请求，并开始时间指示已发出邀请的时间。邀请时间并不意味着媒体开始时间，因为媒体开始仅在会话被接受后。 
  
媒体视图它包含[SessionDetails 视图](sessiondetails-0.md)中的列的所有除了下面列出的。
  
|**列**|**数据类型**|**详细信息**|
|:-----|:-----|:-----|
|**媒体** <br/> |nvarchar(256)  <br/> |媒体类型。 [MediaList 表](medialist.md)的详细信息，请参阅。 <br/> |
|**MediaStartTime** <br/> |datetime  <br/> |已发出介质请求的时间。  <br/> |
|**MediaEndTime** <br/> |datetime  <br/> |会话的结束时间。  <br/> |
   

