---
title: Skype for Business Server 2015 中的 EdgeServers 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aeda8c01-c88c-4f56-b3d0-bac475fae449
description: EdgeServers 表是支持表。 每个记录存储有关在数据库中具有记录的通话中涉及的一个边缘服务器的信息。
ms.openlocfilehash: a78acd3b6297bbef3348ef87047c8cb7f0893231
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296341"
---
# <a name="edgeservers-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的 EdgeServers 表
 
EdgeServers 表是支持表。 每个记录存储有关在数据库中具有记录的通话中涉及的一个边缘服务器的信息。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**EdgeServerId** <br/> |int  <br/> |Primary  <br/> |标识此边缘服务器的唯一编号。  <br/> |
|**EdgeServer** <br/> |nvarchar(256)  <br/> | <br/> |边缘服务器名称。  <br/> |
   

