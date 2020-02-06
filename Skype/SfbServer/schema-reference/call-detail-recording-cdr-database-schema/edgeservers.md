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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: aeda8c01-c88c-4f56-b3d0-bac475fae449
description: EdgeServers 表是支持表。 每个记录存储有关在数据库中具有记录的通话中涉及的一个边缘服务器的信息。
ms.openlocfilehash: 7a1621e3416b6cff48c430e7bc2e45057ecb3e14
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815260"
---
# <a name="edgeservers-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的 EdgeServers 表
 
EdgeServers 表是支持表。 每个记录存储有关在数据库中具有记录的通话中涉及的一个边缘服务器的信息。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**EdgeServerId** <br/> |int  <br/> |Primary  <br/> |标识此边缘服务器的唯一编号。  <br/> |
|**EdgeServer** <br/> |nvarchar(256)  <br/> | <br/> |边缘服务器名称。  <br/> |
   

