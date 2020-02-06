---
title: Endpoint 表
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
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: 终结点表是一个支持表，用于存储参与数据库中记录的会话的终结点的相关信息。 表中的每条记录表示一个终结点。
ms.openlocfilehash: b64b19a3149fa3d490ea8dc957699c0a114f763c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41809550"
---
# <a name="endpoint-table"></a>Endpoint 表
 
终结点表是一个支持表，用于存储参与数据库中记录的会话的终结点的相关信息。 表中的每条记录表示一个终结点。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**EndpointKey** <br/> |int  <br/> |Primary  <br/> |标识此终结点的唯一号码。  <br/> |
|**名称** - 按 WAN 链路进行筛选（筛选器位于图形右侧）。 <br/> |nvarchar(256)  <br/> |唯一  <br/> |终结点名称。  <br/> |
|**OS** <br/> |nvarchar  <br/> | <br/> |终结点的操作系统（OS）。  <br/> |
|**CPUName** <br/> |nvarchar  <br/> ||终结点的 CPU 名称。  <br/> |
|**CPUNumberOfCores** <br/> |smallint  <br/> ||终结点的 CPU 内核数。  <br/> |
|**CPUProcessorSpeed** <br/> |int  <br/> ||终结点的 CPU 处理器速度。  <br/> |
|**VirtualizationFlag** <br/> |tinyint  <br/> || 指示系统是否在虚拟化环境中运行的位标志： <br/>  0x0000-无 <br/>  0x0001-HyperV <br/>  0x0002-VMWare <br/>  0x0004-虚拟电脑 <br/>  0x0008-Xen 电脑 <br/> |
   

