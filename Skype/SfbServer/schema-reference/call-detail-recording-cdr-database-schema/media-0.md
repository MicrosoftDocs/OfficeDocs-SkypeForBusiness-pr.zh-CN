---
title: 媒体视图
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
description: “媒体”视图存储有关在对等会话中使用的一种媒体类型的信息。 如果使用多个媒体类型，则一个会话由表中的多条记录表示。 此视图在 Microsoft Lync Server 2013 中引入。
ms.openlocfilehash: 2ed8d66bf55594e3524a43b35df3bfa6d859055a
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60828555"
---
# <a name="media-view"></a>媒体视图
 
“媒体”视图存储有关在对等会话中使用的一种媒体类型的信息。 如果使用多个媒体类型，则一个会话由表中的多条记录表示。 此视图在 Microsoft Lync Server 2013 中引入。
  
> [!NOTE]
> “媒体”视图不应用来计算会话的媒体持续时间。此视图包含会话中的媒体交换信号详情。媒体交换通过 INVITE 请求实现，StartTime 指示发出 INVITE 的时间。邀请时间不一定表示媒体的启动时间，因为仅在会话被接受后，媒体才启动。 
  
媒体视图包含 [SessionDetails](sessiondetails-0.md) 视图中的所有列以及下面列出的列。
  
|**列**|**数据类型**|**详细信息**|
|:-----|:-----|:-----|
|**Media** <br/> |nvarchar (256)   <br/> |媒体类型。 有关详细信息， [请参阅 MediaList](medialist.md) 表。 <br/> |
|**MediaStartTime** <br/> |datetime  <br/> |发出媒体请求的时间。  <br/> |
|**MediaEndTime** <br/> |datetime  <br/> |会话的结束时间。  <br/> |
   

