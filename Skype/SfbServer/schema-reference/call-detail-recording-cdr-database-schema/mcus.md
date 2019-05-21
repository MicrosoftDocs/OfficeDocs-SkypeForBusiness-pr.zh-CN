---
title: Skype for Business Server 2015 中的 Mcus 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
description: Mcus 表是支持表。 每条记录存储有关一个会议服务的信息。 这些服务可以包括 IM 会议服务和电话会议服务 (该服务作为前端服务器上的进程运行)、Web 会议服务和 A/V 会议服务。
ms.openlocfilehash: fcd12bcc8da7aa6513d78e1a9c4a6f11930065aa
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296040"
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的 Mcus 表
 
Mcus 表是支持表。 每条记录存储有关一个会议服务的信息。 这些服务可以包括 IM 会议服务和电话会议服务 (该服务作为前端服务器上的进程运行)、Web 会议服务和 A/V 会议服务。 
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**McuId** <br/> |int  <br/> |Primary  <br/> |标识此会议服务器的唯一号码。  <br/> |
|**McuUri** <br/> |nvarchar (450)  <br/> | <br/> | <br/> |
|**McuTypeId** <br/> |inyint  <br/> | 外表 <br/> |会议服务器类型, 例如会议: 聊天 (适用于 Im) 或会议: 音频视频。 有关详细信息, 请参阅[UriTypes 表](uritypes.md)。 <br/> |
   

