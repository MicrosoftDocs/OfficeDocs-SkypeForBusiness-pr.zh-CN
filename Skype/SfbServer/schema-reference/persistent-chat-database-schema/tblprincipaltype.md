---
title: tblPrincipalType
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
description: tblPrincipalType 包含要分类 tblPrincipal 表中的主体类型。
ms.openlocfilehash: 804997c0cb25dff6566d21a26626550982d0075f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924456"
---
# <a name="tblprincipaltype"></a>tblPrincipalType
 
tblPrincipalType 包含要分类 tblPrincipal 表中的主体类型。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|ptypeID  <br/> |smallint，不为 null  <br/> |主体类型 id。  <br/> |
|ptypeDesc  <br/> |nvarchar (256)，不为 null  <br/> |类型的说明。  <br/> |
|ptypeIsSystemUser  <br/> |bit，不为 null  <br/> |如果类型对应于供内部使用的主体，则为 true。  <br/> |
|ptypeIsUser  <br/> |bit，不为 null  <br/> |如果类型为用户类型，则为 true。  <br/> |
   
**关键字**

|**列**|**说明**|
|:-----|:-----|
|ptypeID  <br/> |主键。  <br/> |
   
**主体值**

|**ID**|**角色**|**说明**|**User**|
|:-----|:-----|:-----|:-----|
|1  <br/> |任意  <br/> |没有已知类型的通用主体。 不使用 tblPrincipal 表中。  <br/> ||
|2  <br/> |AnyUser  <br/> |用户类型的通用主体。 不使用 tblPrincipal 表中。  <br/> |是  <br/> |
|3  <br/> |AnyGroup  <br/> |与语义组的通用主体。 不使用 tblPrincipal 表中。  <br/> ||
|4  <br/> |系统用户  <br/> |持久聊天服务器供内部使用的主体。  <br/> ||
|5  <br/> |用户  <br/> |常规用户。  <br/> |是  <br/> |
|8  <br/> |DC  <br/> |Active Directory 域服务的域控制器。  <br/> ||
|9  <br/> |组  <br/> |Active Directory 安全组。  <br/> ||
|10  <br/> |文件夹  <br/> |Active Directory 容器或组织单位。  <br/> ||
   
## <a name="see-also"></a>另请参阅

[tblPrincipal](tblprincipal.md)
