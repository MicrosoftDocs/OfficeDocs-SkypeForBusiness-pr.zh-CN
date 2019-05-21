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
localization_priority: Normal
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: 终结点表是一个支持表, 用于存储参与数据库中记录的会话的终结点的相关信息。 表中的每条记录表示一个终结点。
ms.openlocfilehash: 7d582d382784d04d4495de972aa20673862284f4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294990"
---
# <a name="endpoint-table"></a>Endpoint 表
 
终结点表是一个支持表, 用于存储参与数据库中记录的会话的终结点的相关信息。 表中的每条记录表示一个终结点。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**EndpointKey** <br/> |int  <br/> |Primary  <br/> |标识此终结点的唯一号码。  <br/> |
|**名称** - 按 WAN 链路进行筛选（筛选器位于图形右侧）。 <br/> |nvarchar(256)  <br/> |唯一  <br/> |终结点名称。  <br/> |
|**OS** <br/> |nvarchar  <br/> | <br/> |终结点的操作系统 (OS)。  <br/> |
|**CPUName** <br/> |nvarchar  <br/> ||终结点的 CPU 名称。  <br/> |
|**CPUNumberOfCores** <br/> |smallint  <br/> ||终结点的 CPU 内核数。  <br/> |
|**CPUProcessorSpeed** <br/> |int  <br/> ||终结点的 CPU 处理器速度。  <br/> |
|**VirtualizationFlag** <br/> |tinyint  <br/> || 指示系统是否在虚拟化环境中运行的位标志: <br/>  0x0000-无 <br/>  0x0001-HyperV <br/>  0x0002-VMWare <br/>  0x0004-虚拟电脑 <br/>  0x0008-Xen 电脑 <br/> |
   

