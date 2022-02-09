---
title: Endpoint 表
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: Endpoint 表是一个支持表，用于存储有关已参与数据库中记录的会话的终结点的信息。 表中的每条记录都代表一个终结点。
ms.openlocfilehash: 4085b8e22aea565054dbb03de10808712c54361e
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "62399556"
---
# <a name="endpoint-table"></a>Endpoint 表
 
Endpoint 表是一个支持表，用于存储有关已参与数据库中记录的会话的终结点的信息。 表中的每条记录都代表一个终结点。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**EndpointKey** <br/> |int  <br/> |主  <br/> |标识此终结点的唯一编号。  <br/> |
|**名称** <br/> |nvarchar (256)   <br/> |独特  <br/> |终结点名称。  <br/> |
|**操作系统** <br/> |nvarchar (128)   <br/> | <br/> |操作系统 (终结点) 操作系统。  <br/> |
|**CPUName** <br/> |nvarchar (128)   <br/> ||终结点的 CPU 名称。  <br/> |
|**CPUNumberOfCores** <br/> |smallint  <br/> ||终结点的 CPU 内核数。  <br/> |
|**CPUProcessorSpeed** <br/> |int  <br/> ||终结点的 CPU 处理器速度。  <br/> |
|**VirtualizationFlag** <br/> |tinyint  <br/> || 指示系统是否正在虚拟化环境中运行的位标志： <br/>  0x0000 - 无 <br/>  0x0001 - HyperV <br/>  0x0002 - VMWare <br/>  0x0004 - 虚拟电脑 <br/>  0x0008 - Xen PC <br/> |
   

