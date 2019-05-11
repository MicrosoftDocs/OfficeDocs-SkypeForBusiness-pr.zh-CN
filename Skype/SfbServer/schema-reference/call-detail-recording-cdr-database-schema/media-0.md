---
title: 媒体视图
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
description: 媒体视图中存储的对等会话中使用的一个媒体类型的信息。 将由多个记录在表中，表示一个会话，如果使用多个媒体类型。 此视图是在 Microsoft Lync Server 2013 中引入的。
ms.openlocfilehash: 83caf609efae4e97961e7c62c3a1ed6c6004e8e8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930691"
---
# <a name="media-view"></a>媒体视图
 
媒体视图中存储的对等会话中使用的一个媒体类型的信息。 将由多个记录在表中，表示一个会话，如果使用多个媒体类型。 此视图是在 Microsoft Lync Server 2013 中引入的。
  
> [!NOTE]
> 媒体视图不应用于计算会话的媒体持续时间。 该视图包含会话中的媒体交换的信号详细信息。 媒体交换通过 INVITE 请求，并 StartTime 指示邀请已发送的时间。邀请时间不一定意味着媒体开始时间，因为媒体的起始位置仅接受会话。 
  
媒体视图它包含[SessionDetails view](sessiondetails-0.md)中的列的所有此外下面列出的内容。
  
|**列**|**数据类型**|**详细信息**|
|:-----|:-----|:-----|
|**媒体** <br/> |nvarchar(256)  <br/> |媒体类型。 请参阅[MediaList 表](medialist.md)的详细信息。 <br/> |
|**MediaStartTime** <br/> |datetime  <br/> |已发送媒体请求的时间。  <br/> |
|**MediaEndTime** <br/> |datetime  <br/> |会话的结束时间。  <br/> |
   

