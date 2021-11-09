---
title: Skype for Business Server 2015 中的 ContentTypes 表
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.openlocfilehash: ca6497cad38c6e4e59f4da725ab03b8d027f2d93
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60827395"
---
# <a name="contenttypes-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的 ContentTypes 表
 
ContentTypes 表是一个支持表，用于存储对等会话和会议会话中使用的内容类型的列表。 表中的每条记录都表示一种内容类型。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**ContentTypeId** <br/> |int  <br/> |主  <br/> |标识内容类型的唯一编号。  <br/> |
|**ContentType** <br/> |nvarchar (256)   <br/> ||内容类型名称。  <br/> |
   

