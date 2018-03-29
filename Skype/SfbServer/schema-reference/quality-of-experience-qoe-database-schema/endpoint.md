---
title: Endpoint 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: 终结点表是一个支持的表来存储有关记录在数据库中的会话中参与过的终结点信息。 每个表中的记录表示一个终结点。
ms.openlocfilehash: 64eb55a0c1bebe7f2ce992351ce21db2fdc575d7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="endpoint-table"></a>Endpoint 表
 
终结点表是一个支持的表来存储有关记录在数据库中的会话中参与过的终结点信息。 每个表中的记录表示一个终结点。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**EndpointKey** <br/> |int  <br/> |Primary  <br/> |标识此终结点的唯一编号。  <br/> |
|**名称** - 按 WAN 链路进行筛选（筛选器位于图形右侧）。 <br/> |nvarchar(256)  <br/> |唯一  <br/> |终结点名称。  <br/> |
|**操作系统** <br/> |nvarchar(128)  <br/> | <br/> |操作系统 (OS) 的终结点。  <br/> |
|**CPUName** <br/> |nvarchar(128)  <br/> ||CPU 的终结点名称。  <br/> |
|**CPUNumberOfCores** <br/> |smallint  <br/> ||终结点的 CPU 内核的数量。  <br/> |
|**CPUProcessorSpeed** <br/> |int  <br/> ||终结点的 CPU 处理器速度。  <br/> |
|**VirtualizationFlag** <br/> |tinyint  <br/> || 位标志，指示系统将在虚拟化环境中运行： <br/>  0x0000-无 <br/>  0x0001-HyperV <br/>  0x0002-VMWare <br/>  0x0004-虚拟 PC <br/>  0x0008-Xen 的 PC <br/> |
   

