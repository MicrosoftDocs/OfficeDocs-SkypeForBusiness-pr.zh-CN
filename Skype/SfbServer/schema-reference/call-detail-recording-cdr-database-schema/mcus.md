---
title: 在业务服务器 2015年的 Skype 的 Mcu 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
description: Mcu 表是支持表。 每个记录都存储着一个会议服务有关的信息。 这些可以包括 IM 会议服务和电话服务会议服务 （它作为进程运行在前端服务器上），和 Web 会议服务和 A / V 会议服务。
ms.openlocfilehash: 2a85d46e733d230dc7c8096c8804146b19766bcf
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a>在业务服务器 2015年的 Skype 的 Mcu 表
 
Mcu 表是支持表。 每个记录都存储着一个会议服务有关的信息。 这些可以包括 IM 会议服务和电话服务会议服务 （它作为进程运行在前端服务器上），和 Web 会议服务和 A / V 会议服务。 
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**McuId** <br/> |int  <br/> |Primary  <br/> |标识此会议服务器的唯一编号。  <br/> |
|**McuUri** <br/> |nvarchar(450)  <br/> | <br/> | <br/> |
|**McuTypeId** <br/> |inyint  <br/> | 外 <br/> |会议服务器类型，（用于 IMs) conf:chat 和 conf:audio 的视频。 [UriTypes 表](uritypes.md)的详细信息，请参阅。 <br/> |
   

