---
title: tblPrincipalType
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
description: tblPrincipalType 包含用于对 tblPrincipal 表中的内容进行分类的主体类型。
ms.openlocfilehash: 473b718a8a863432a71ff04d709bef4c0ac1327f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295242"
---
# <a name="tblprincipaltype"></a>tblPrincipalType
 
tblPrincipalType 包含用于对 tblPrincipal 表中的内容进行分类的主体类型。
  
**多**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|ptypeID  <br/> |smallint, not null  <br/> |主体类型 ID。  <br/> |
|ptypeDesc  <br/> |nvarchar (256), not null  <br/> |类型的说明。  <br/> |
|ptypeIsSystemUser  <br/> |位, not null  <br/> |如果类型对应于用于内部用途的主体, 则为 True。  <br/> |
|ptypeIsUser  <br/> |位, not null  <br/> |如果类型为用户类型, 则为 True。  <br/> |
   
**关键字**

|**列**|**说明**|
|:-----|:-----|
|ptypeID  <br/> |主键。  <br/> |
   
**主体值**

|**ID**|**角色**|**说明**|**User**|
|:-----|:-----|:-----|:-----|
|1  <br/> |任意  <br/> |没有已知类型的泛型主体。 未在 tblPrincipal 表中使用。  <br/> ||
|2  <br/> |AnyUser  <br/> |用户类型的一般主体。 未在 tblPrincipal 表中使用。  <br/> |是  <br/> |
|3  <br/> |AnyGroup  <br/> |具有组语义的常规主体。 未在 tblPrincipal 表中使用。  <br/> ||
|4  <br/> |SystemUser  <br/> |持久聊天服务器在内部使用的主体。  <br/> ||
|5  <br/> |用户  <br/> |普通用户。  <br/> |是  <br/> |
|个  <br/> |电源  <br/> |Active Directory 域服务域控制器。  <br/> ||
|db-9  <br/> |团队  <br/> |Active Directory 安全组。  <br/> ||
|10  <br/> |收藏夹  <br/> |Active Directory 容器或组织单位。  <br/> ||
   
## <a name="see-also"></a>另请参阅

[tblPrincipal](tblprincipal.md)
