---
title: Skype for Business Server 2015 中的 ContentTypes 表
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e3e38035-457c-4173-bdb9-d53a7420eba2
description: ContentTypes 表是一个支持表，用于存储对等会话和会议会话中使用的内容类型列表。 表中的每条记录表示一种内容类型。
ms.openlocfilehash: 461631c8fc824a23f0e4b22b65a3cbc8cf6a2c73
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816082"
---
# <a name="contenttypes-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的 ContentTypes 表
 
ContentTypes 表是一个支持表，用于存储对等会话和会议会话中使用的内容类型列表。 表中的每条记录表示一种内容类型。
  
|**列**|**数据类型**|**键/索引**|**Details**|
|:-----|:-----|:-----|:-----|
|**ContentTypeId** <br/> |int  <br/> |主  <br/> |标识内容类型的唯一编号。  <br/> |
|**ContentType** <br/> |nvarchar (256)   <br/> ||内容类型名称。  <br/> |
   

