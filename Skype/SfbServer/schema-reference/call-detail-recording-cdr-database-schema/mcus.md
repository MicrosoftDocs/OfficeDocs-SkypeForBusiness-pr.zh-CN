---
title: Mcus 表中的业务服务器 2015 Skype
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
description: Mcus 表是一个支持表。 每个记录存储有关一个会议服务的信息。 其中可以包括 IM 会议服务和电话会议服务 （它作为进程运行前端服务器），以及 Web 会议服务和 A / V 会议服务。
ms.openlocfilehash: 6b5df793008fcf7586d62cab77a1b362848374ac
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930670"
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a>Mcus 表中的业务服务器 2015 Skype
 
Mcus 表是一个支持表。 每个记录存储有关一个会议服务的信息。 其中可以包括 IM 会议服务和电话会议服务 （它作为进程运行前端服务器），以及 Web 会议服务和 A / V 会议服务。 
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**McuId** <br/> |int  <br/> |Primary  <br/> |标识此会议服务器的唯一编号。  <br/> |
|**McuUri** <br/> |nvarchar(450)  <br/> | <br/> | <br/> |
|**McuTypeId** <br/> |inyint  <br/> | 外 <br/> |会议服务器类型，如 conf:chat （对于 Im) 或 conf:audio-视频。 请参阅[UriTypes 表](uritypes.md)的详细信息。 <br/> |
   

