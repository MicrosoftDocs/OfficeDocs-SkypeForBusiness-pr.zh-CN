---
title: Media 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1e1b427f-59b5-4564-bde5-1002a80439ee
description: 每个记录表示的对等会话中使用的一种媒体类型。 如果使用多个媒体类型，将可以由多个记录在表中，表示一个会话。
ms.openlocfilehash: 8833e7272c82dcbb7eef0da89d915680198589b5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="media-table"></a>Media 表
 
每个记录表示的对等会话中使用的一种媒体类型。 如果使用多个媒体类型，将可以由多个记录在表中，表示一个会话。
  
> [!NOTE]
> 媒体表不应该用于计算会话的媒体持续时间。 此表包含媒体交换会话中信号传输的详细的信息。 媒体交换通过 INVITE 请求，并开始时间指示已发出邀请的时间。邀请的时间并不意味着媒体开始时，因为媒体开始 sessionee 接受会话后才。 结束时间通常意味着此会话的结束时间。 
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |主键和外  <br/> |会议请求的时间。 与**SessionIdSeq**配合使用，以唯一标识会话。 [对话框中业务服务器 2015年的 Skype 的表](dialogs.md)的详细信息，请参阅。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主键和外  <br/> |以标识会话的 ID 号。 与**SessionIdTime**配合使用，以唯一标识会话。 [对话框中业务服务器 2015年的 Skype 的表](dialogs.md)的详细信息，请参阅。 <br/> |
|**MediaId** <br/> |tinyint  <br/> |主键和外  <br/> |标识此媒体类型的唯一编号。 [MediaList 表](medialist.md)的详细信息，请参阅。 <br/> |
|**开始时间** <br/> |datetime  <br/> |Primary  <br/> |这是媒体请求被发送出去的时间，不实的媒体开始时间。 **开始时间**包括会话设置时间。 <br/> |
|**结束时间** <br/> |datetime  <br/> ||这是会话的结束时间。  <br/> |
   

