---
title: Media 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1e1b427f-59b5-4564-bde5-1002a80439ee
description: 每条记录表示对等会话中使用的一种媒体类型。 如果使用多个媒体类型, 则表中的多个记录将表示一个会话。
ms.openlocfilehash: 181a78a9fc3fabe8c166f4cdc8c452b5a16b016b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296005"
---
# <a name="media-table"></a>Media 表
 
每条记录表示对等会话中使用的一种媒体类型。 如果使用多个媒体类型, 则表中的多个记录将表示一个会话。
  
> [!NOTE]
> 不应使用 Media 表计算会话的媒体持续时间。 此表包含会话中媒体交换的信号详细信息。 媒体交换由邀请请求完成, 并且 StartTime 指示发送邀请的时间。邀请时间不一定表示媒体开始时间, 因为媒体仅在 sessionee 接受会话后才开始。 "结束时间" 通常表示本次会话的结束时间。 
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |主、外部  <br/> |会话请求的时间。 与**SessionIdSeq**结合使用以唯一标识会话。 有关详细信息, 请参阅[Skype For Business Server 2015 中的对话框表](dialogs.md)。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主、外部  <br/> |标识会话的 ID 号。 与**SessionIdTime**结合使用以唯一标识会话。 有关详细信息, 请参阅[Skype For Business Server 2015 中的对话框表](dialogs.md)。 <br/> |
|**MediaId** <br/> |tinyint  <br/> |主、外部  <br/> |标识此媒体类型的唯一号码。 有关详细信息, 请参阅[MediaList 表](medialist.md)。 <br/> |
|**StartTime** <br/> |datetime  <br/> |Primary  <br/> |这是发送媒体请求的时间, 而不是真正的媒体开始时间。 **StartTime**包括会话设置时间。 <br/> |
|**EndTime** <br/> |datetime  <br/> ||这是会话的结束时间。  <br/> |
   

