---
title: tblPrincipalAffiliations
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 45fd8484-5837-44d2-85bb-45c83546607c
description: tblPrincipalAffiliations 包含描述位置中的成员身份的主体成员，包括 Active directory 域服务安全组，位于 Active Directory 容器中的域中。
ms.openlocfilehash: 542bcc333d815b0577aec1fb11d4070540150d3c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814470"
---
# <a name="tblprincipalaffiliations"></a>tblPrincipalAffiliations
 
tblPrincipalAffiliations 包含描述位置中的成员身份的主体成员，包括 Active directory 域服务安全组，位于 Active Directory 容器中的域中。
  
**多**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|principalID  <br/> |int，not null  <br/> |关联主体的 ID。  <br/> |
|affiliationID  <br/> |int，not null  <br/> |表示隶属关系的承担者的 ID。 每个主体（除系统用户类型外）还具有自我隶属关系。  <br/> |
|食指  <br/> |int，not null  <br/> |食指. 自隶属关系的值是-1，对于其他隶属关系，在每个\<PrincipalID、affiliationId\>存储桶中，它将按从1开始递增。  <br/> |
|updatedBy  <br/> |int，not null  <br/> |已进行最新更新的主体。 这通常是1，这意味着 Active Directory 同步。  <br/> |
   
**标示**

|**多**|**说明**|
|:-----|:-----|
|\<principalID、index、affiliationID\>  <br/> |主键。  <br/> |
|principalID  <br/> |TblPrincipal 表中的 lookup 的外键。  <br/> |
|affiliationID  <br/> |TblPrincipal 表中的 lookup 的外键。  <br/> |
   

