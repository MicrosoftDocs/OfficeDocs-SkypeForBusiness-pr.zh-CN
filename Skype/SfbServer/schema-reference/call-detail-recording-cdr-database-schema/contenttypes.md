---
title: Skype for Business Server 2015 中的 ContentTypes 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e3e38035-457c-4173-bdb9-d53a7420eba2
description: ContentTypes 表是一个支持表, 用于存储对等会话和会议会话中使用的内容类型的列表。 表中的每条记录表示一种内容类型。
ms.openlocfilehash: b8422cbe95425ac79495c0506f4a94e70be3f9af
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296369"
---
# <a name="contenttypes-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的 ContentTypes 表
 
ContentTypes 表是一个支持表, 用于存储对等会话和会议会话中使用的内容类型的列表。 表中的每条记录表示一种内容类型。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**ContentTypeId** <br/> |int  <br/> |Primary  <br/> |标识内容类型的唯一编号。  <br/> |
|**ContentType** <br/> |nvarchar(256)  <br/> ||内容类型名称。  <br/> |
   

