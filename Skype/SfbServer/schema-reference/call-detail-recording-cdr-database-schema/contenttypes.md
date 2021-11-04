---
title: Skype for Business Server 2015 中的 ContentTypes 表
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: e3e38035-457c-4173-bdb9-d53a7420eba2
description: ContentTypes 表是一个支持表，用于存储对等会话和会议会话中使用的内容类型的列表。 表中的每条记录都表示一种内容类型。
ms.openlocfilehash: 98e360f218de3cd3e998ae09e5bc4abd83d5b28b
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60744008"
---
# <a name="contenttypes-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的 ContentTypes 表
 
ContentTypes 表是一个支持表，用于存储对等会话和会议会话中使用的内容类型的列表。 表中的每条记录都表示一种内容类型。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**ContentTypeId** <br/> |int  <br/> |主  <br/> |标识内容类型的唯一编号。  <br/> |
|**ContentType** <br/> |nvarchar (256)   <br/> ||内容类型名称。  <br/> |
   

