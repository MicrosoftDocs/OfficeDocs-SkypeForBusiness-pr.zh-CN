---
title: VideoClientEvent 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
description: 每条记录包含视频呼叫中一个终结点的客户端事件。 通常，一个通话有两个记录，一个用于呼叫方，另一个用于被呼叫方。
ms.openlocfilehash: 9acd7277fd6bc32074487be1db9874ef6a5c91aa
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41804990"
---
# <a name="videoclientevent-table"></a>VideoClientEvent 表
 
每条记录包含视频呼叫中一个终结点的客户端事件。 通常，一个通话有两个记录，一个用于呼叫方，另一个用于被呼叫方。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |从[MediaLine 表](medialine-0.md)中引用。  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |从[MediaLine 表](medialine-0.md)中引用。  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |从[MediaLine 表](medialine-0.md)中引用。  <br/> |
|**FromCaller** <br/> |bit  <br/> |Primary  <br/> |0：被调用方的数据  <br/> 1：调用方的数据  <br/> |
|**NetworkBandwidthLowEventRatio** <br/> || <br/> |会话百分比为 "坏" 状态引发 LowBandwidth 事件的百分比。 可用带宽不足以获得可接受的语音体验。  <br/> |
|**NetworkReceiveQualityEventRatio** <br/> || <br/> |会话百分比为 "坏" 状态引发 ReceiveSendQuality 事件的百分比。  <br/> "抖动" 或 "数据包丢失" 方面的网络质量非常严重，影响接收音频的质量。  <br/> |
   

