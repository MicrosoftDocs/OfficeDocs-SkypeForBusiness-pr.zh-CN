---
title: tblPrincipalType
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
description: tblPrincipalType 包含主体的类型进行分类的 tblPrincipal 表中。
ms.openlocfilehash: 3d1ec9b83561f06d3f8b1871223aafdf5c0775cb
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipaltype"></a>tblPrincipalType
 
tblPrincipalType 包含主体的类型进行分类的 tblPrincipal 表中。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|ptypeID  <br/> |smallint，不为空  <br/> |主体的类型 id。  <br/> |
|ptypeDesc  <br/> |nvarchar (256) 不为空  <br/> |类型的说明。  <br/> |
|ptypeIsSystemUser  <br/> |位，不为空  <br/> |如果的类型对应于用于内部目的的主体，则返回 true。  <br/> |
|ptypeIsUser  <br/> |位，不为空  <br/> |如果该类型是一种用户类型，则为 true。  <br/> |
   
**密钥**

|**列**|**说明**|
|:-----|:-----|
|ptypeID  <br/> |为主键。  <br/> |
   
**主体的值**

|**标识**|**角色**|**说明**|**用户**|
|:-----|:-----|:-----|:-----|
|1  <br/> |任何  <br/> |与任何已知的类型的一般主体。 不使用 tblPrincipal 表中。  <br/> ||
|2  <br/> |AnyUser  <br/> |用户类型的一般主体。 不使用 tblPrincipal 表中。  <br/> |是  <br/> |
|3  <br/> |AnyGroup  <br/> |与组语义的一般主体。 不使用 tblPrincipal 表中。  <br/> ||
|4  <br/> |系统用户  <br/> |主体由持久聊天服务器内部使用。  <br/> ||
|5  <br/> |用户  <br/> |普通用户。  <br/> |是  <br/> |
|8  <br/> |DC  <br/> |活动目录域服务域控制器。  <br/> ||
|9  <br/> |组  <br/> |活动目录安全组。  <br/> ||
|10  <br/> |文件夹  <br/> |活动目录容器或组织单位。  <br/> ||
   
## <a name="see-also"></a>另请参阅

#### 

[tblPrincipal](tblprincipal.md)

