---
title: Media 表
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
ms.assetid: 1e1b427f-59b5-4564-bde5-1002a80439ee
description: 每条记录表示一个用于点对点会话的媒体类型。如果使用多个媒体类型，则一个会话由表中的多条记录表示。
ms.openlocfilehash: ce5b5a2b312307e608367279e4e871ed03063860
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800102"
---
# <a name="media-table"></a>Media 表
 
每条记录表示一个用于点对点会话的媒体类型。如果使用多个媒体类型，则一个会话由表中的多条记录表示。
  
> [!NOTE]
> 不应使用媒体表计算会话的媒体持续时间。该表包含会话中的媒体交换信号详情。媒体交换通过 INVITE 请求实现，StartTime 指示发出 INVITE 的时间。邀请时间不一定表示媒体的启动时间，因为仅在会话接收方接受会话后，媒体才启动。EndTime 通常表示该会话的结束时间。 
  
|**列**|**数据类型**|**键/索引**|**Details**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |主、外  <br/> |会话请求的时间。 与 **SessionIdSeq** 结合使用来唯一地标识会话。 有关详细信息，请参阅 [Skype for Business Server 2015 中的 Dialogs](dialogs.md) 表。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主、外  <br/> |用于标识会话的 ID 号。 与 **SessionIdTime** 结合使用来唯一地标识会话。 有关详细信息，请参阅 [Skype for Business Server 2015 中的 Dialogs](dialogs.md) 表。 <br/> |
|**MediaId** <br/> |tinyint  <br/> |主、外  <br/> |标识媒体类型的唯一编号。 有关详细信息， [请参阅 MediaList](medialist.md) 表。 <br/> |
|**StartTime** <br/> |datetime  <br/> |主  <br/> |这是发出媒体请求的时间，而不是实际的媒体启动时间。**StartTime** 包括会话建立时间。<br/> |
|**EndTime** <br/> |datetime  <br/> ||这是会话的结束时间。  <br/> |
   

