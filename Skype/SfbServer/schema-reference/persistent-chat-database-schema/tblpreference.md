---
title: tblPreference
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference 包含用户的客户端首选项。 这通常使用 Lync 2013 之前的客户端。
ms.openlocfilehash: 28656951c80e6e4010e6ca559e3f650e2b9bac4b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="tblpreference"></a>tblPreference
 
tblPreference 包含用户的客户端首选项。 这通常使用 Lync 2013 之前的客户端。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|prefLabel  <br/> |nvarchar (255) 不为空  <br/> |如标签的格式：\<用户的 sip uri\>|用户名。\<的首选项组\>。  <br/> |
|prefSeqID  <br/> |int，不为空  <br/> |顺序编号 （每个标签） 用于版本控制的目的。  <br/> |
|prefContent  <br/> |nvarchar （最大）  <br/> |已编码的内容。  <br/> |
|lastModifiedBy  <br/> |int，不为空  <br/> |更新首选项的主要用户的 ID。  <br/> |
   
**密钥**

|**列**|**说明**|
|:-----|:-----|
|\<prefLabel prefSeqID\>  <br/> |为主键。  <br/> |
   

