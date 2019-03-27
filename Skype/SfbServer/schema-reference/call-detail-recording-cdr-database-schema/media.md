---
title: Media 表
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1e1b427f-59b5-4564-bde5-1002a80439ee
description: 每条记录代表一个的对等会话中使用的媒体类型。 将由多个记录在表中，表示一个会话，如果使用多个媒体类型。
ms.openlocfilehash: f0525b279fbef5cc7d4a1bc2ce0fce9212636a96
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30893024"
---
# <a name="media-table"></a>Media 表
 
每条记录代表一个的对等会话中使用的媒体类型。 将由多个记录在表中，表示一个会话，如果使用多个媒体类型。
  
> [!NOTE]
> Media 表不应用于计算会话的媒体持续时间。 此表包含会话中的媒体交换的信号详细信息。 媒体交换通过 INVITE 请求，并 StartTime 指示邀请已发送的时间。邀请时间不一定意味着媒体开始时间，因为媒体开始仅后 sessionee 接受会话。 EndTime 通常意味着此会话的结束时间。 
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |主、 外  <br/> |会话请求的时间。 与**SessionIdSeq**结合使用，来唯一地标识会话。 [Dialogs 表中的业务服务器 2015 Skype](dialogs.md)的详细信息，请参阅。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主、 外  <br/> |标识会话的 ID 号。 与**SessionIdTime**结合使用，来唯一地标识会话。 [Dialogs 表中的业务服务器 2015 Skype](dialogs.md)的详细信息，请参阅。 <br/> |
|**MediaId** <br/> |tinyint  <br/> |主、 外  <br/> |标识此媒体类型的唯一编号。 请参阅[MediaList 表](medialist.md)的详细信息。 <br/> |
|**StartTime** <br/> |datetime  <br/> |Primary  <br/> |这是出发送媒体请求的时间，不是实际的媒体开始时间。 **StartTime**包括会话建立时间。 <br/> |
|**EndTime** <br/> |datetime  <br/> ||这是会话的结束时间。  <br/> |
   

