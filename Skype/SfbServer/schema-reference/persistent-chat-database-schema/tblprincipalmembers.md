---
title: tblPrincipalMembers
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: tblPrincipalMembers 包含主体的成员资格。
ms.openlocfilehash: 77151cc245b90fa22d9da426a1448c49866dccc2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipalmembers"></a>tblPrincipalMembers
 
tblPrincipalMembers 包含主体的成员资格。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|prinID  <br/> |int，不为空  <br/> |主体标识。  <br/> |
|memberADPath  <br/> |nvarchar (384) 不为空  <br/> |成员的可分辨的名称。 成员不需要是一个主体 （在 tblPrincipal 表中）。  <br/> |
   
**密钥**

|**列**|**说明**|
|:-----|:-----|
|\<prinID memberADPath\>  <br/> |为主键。  <br/> |
|prinID  <br/> |在 tblPrincipal.prinID 中查找与外键。  <br/> |
   

