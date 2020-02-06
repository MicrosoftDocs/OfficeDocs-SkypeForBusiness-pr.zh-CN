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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
description: Mcus 表是支持表。 每条记录存储有关一个会议服务的信息。 这些服务可以包括 IM 会议服务和电话会议服务（该服务作为前端服务器上的进程运行）、Web 会议服务和 A/V 会议服务。
ms.openlocfilehash: 1e5141ee2a103e540d3ac50e99de0036f31262d7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815060"
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的 Mcus 表
 
Mcus 表是支持表。 每条记录存储有关一个会议服务的信息。 这些服务可以包括 IM 会议服务和电话会议服务（该服务作为前端服务器上的进程运行）、Web 会议服务和 A/V 会议服务。 
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**McuId** <br/> |int  <br/> |Primary  <br/> |标识此会议服务器的唯一号码。  <br/> |
|**McuUri** <br/> |nvarchar （450）  <br/> | <br/> | <br/> |
|**McuTypeId** <br/> |inyint  <br/> | 外表 <br/> |会议服务器类型，例如会议：聊天（适用于 Im）或会议：音频视频。 有关详细信息，请参阅[UriTypes 表](uritypes.md)。 <br/> |
   

