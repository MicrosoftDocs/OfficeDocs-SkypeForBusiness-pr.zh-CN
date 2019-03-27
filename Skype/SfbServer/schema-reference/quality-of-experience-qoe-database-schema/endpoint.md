---
title: Endpoint 表
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: Endpoint 表是一个支持表，用于存储已参与记录数据库中的会话的终结点的信息。 表中的每条记录代表一个终结点。
ms.openlocfilehash: f9c304408006ef9caf5521b8f0bbe28c2d917abe
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30882995"
---
# <a name="endpoint-table"></a>Endpoint 表
 
Endpoint 表是一个支持表，用于存储已参与记录数据库中的会话的终结点的信息。 表中的每条记录代表一个终结点。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**EndpointKey** <br/> |int  <br/> |Primary  <br/> |标识此终结点的唯一编号。  <br/> |
|**名称** - 按 WAN 链路进行筛选（筛选器位于图形右侧）。 <br/> |nvarchar(256)  <br/> |唯一  <br/> |终结点名称。  <br/> |
|**OS** <br/> |nvarchar(128)  <br/> | <br/> |操作系统 (OS) 的终结点。  <br/> |
|**CPUName** <br/> |nvarchar(128)  <br/> ||终结点的 CPU 名称。  <br/> |
|**CPUNumberOfCores** <br/> |smallint  <br/> ||终结点的 CPU 内核数。  <br/> |
|**CPUProcessorSpeed** <br/> |int  <br/> ||终结点的 CPU 处理器速度。  <br/> |
|**VirtualizationFlag** <br/> |tinyint  <br/> || 指示系统是否正在运行的虚拟化环境中的位标志： <br/>  0x0000-无 <br/>  0x0001-HyperV <br/>  0x0002-VMWare <br/>  0x0004-虚拟 PC <br/>  0x0008-Xen PC <br/> |
   

