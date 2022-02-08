---
title: tblPrincipalType
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
description: tblPrincipalType 包含用于对 tblPrincipal 表中的内容进行分类的主体类型。
ms.openlocfilehash: cafc8ef175cd3a24178331ce308cf66942c55324
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "62394804"
---
# <a name="tblprincipaltype"></a>tblPrincipalType
 
tblPrincipalType 包含用于对 tblPrincipal 表中的内容进行分类的主体类型。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|ptypeID  <br/> |smallint，不为 null  <br/> |主体类型 ID。  <br/> |
|ptypeDesc  <br/> |nvarchar (256)，不为 null  <br/> |类型描述。  <br/> |
|ptypeIsSystemUser  <br/> |bit，不为 null  <br/> |在类型与供内部使用的主体对应时为 True。  <br/> |
|ptypeIsUser  <br/> |bit，不为 null  <br/> |在类型为用户类型时为 True。  <br/> |
   
**键**

|**列**|**说明**|
|:-----|:-----|
|ptypeID  <br/> |主键。  <br/> |
   
**主体值**

|**ID**|**角色**|**说明**|**用户**|
|:-----|:-----|:-----|:-----|
|1  <br/> |任何  <br/> |未知类型的通用主体。不用于 tblPrincipal 表。  <br/> ||
|2  <br/> |AnyUser  <br/> |用户类型的通用主体。不用于 tblPrincipal 表。  <br/> |是  <br/> |
|3  <br/> |AnyGroup  <br/> |组语义的通用主体。不用于 tblPrincipal 表。  <br/> ||
|4  <br/> |SystemUser  <br/> |持久聊天服务器内部使用的主体。  <br/> ||
|5  <br/> |用户  <br/> |常规用户。  <br/> |是  <br/> |
|8   <br/> |DC  <br/> |Active Directory 域服务域控制器。  <br/> ||
|9   <br/> |组  <br/> |Active Directory 安全组。  <br/> ||
|10   <br/> |Folder  <br/> |Active Directory 容器或组织单位。  <br/> ||
   
## <a name="see-also"></a>另请参阅

[tblPrincipal](tblprincipal.md)
