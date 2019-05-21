---
title: 媒体视图
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
description: 媒体视图存储对等会话中使用的一种媒体类型的相关信息。 如果使用多个媒体类型, 则表中的多个记录将表示一个会话。 此视图已在 Microsoft Lync Server 2013 中引入。
ms.openlocfilehash: 044a31381d4e1e48c465f7ee6de89acab10ab54e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295998"
---
# <a name="media-view"></a>媒体视图
 
媒体视图存储对等会话中使用的一种媒体类型的相关信息。 如果使用多个媒体类型, 则表中的多个记录将表示一个会话。 此视图已在 Microsoft Lync Server 2013 中引入。
  
> [!NOTE]
> 不应使用 "媒体" 视图计算会话的媒体持续时间。 此视图包含会话中媒体交换的信号详细信息。 媒体交换由邀请请求完成, 并且 StartTime 指示发送邀请的时间。邀请时间不一定意味着媒体开始时间, 因为媒体仅在接受会话后才开始。 
  
"媒体" 视图包含 " [SessionDetails" 视图](sessiondetails-0.md)中的所有列以及下面列出的列。
  
|**列**|**数据类型**|**详细信息**|
|:-----|:-----|:-----|
|**媒体** <br/> |nvarchar(256)  <br/> |媒体类型。 有关详细信息, 请参阅[MediaList 表](medialist.md)。 <br/> |
|**MediaStartTime** <br/> |datetime  <br/> |媒体请求发出的时间。  <br/> |
|**MediaEndTime** <br/> |datetime  <br/> |会话的结束时间。  <br/> |
   

