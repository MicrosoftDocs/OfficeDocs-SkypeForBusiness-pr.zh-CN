---
title: tblPrincipalAffiliations
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
ms.assetid: 45fd8484-5837-44d2-85bb-45c83546607c
description: tblPrincipalAffiliations 包含描述位置（包括 Active Directory 域服务安全组、Active Directory 容器中的域）中成员身份的主体附属关系。
ms.openlocfilehash: 149bb1b4603fa0f0e1909298659b881000464275
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815862"
---
# <a name="tblprincipalaffiliations"></a>tblPrincipalAffiliations
 
tblPrincipalAffiliations 包含描述位置（包括 Active Directory 域服务安全组、Active Directory 容器中的域）中成员身份的主体附属关系。
  
**Columns**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|principalID  <br/> |int，不为 null  <br/> |附属主体的 ID。  <br/> |
|affiliationID  <br/> |int，不为 null  <br/> |表示附属关系的主体的 ID。每个主体（系统用户类型除外）还具有自附属关系。  <br/> |
|index  <br/> |int，不为 null  <br/> |索引。 自附属关系的值为 -1，对于其他附属关系，该值从每个存储桶中的 1 依次 \<principalID, affiliationId\> 增加。  <br/> |
|updatedBy  <br/> |int，不为 null  <br/> |进行最新更新的主体。这通常为 1，表示 Active Directory 同步。  <br/> |
   
**Keys**

|**Columns**|**说明**|
|:-----|:-----|
|\<principalID, index, affiliationID\>  <br/> |主键。  <br/> |
|principalID  <br/> |其查找包含在 tblPrincipal.prinID 表中的外键。  <br/> |
|affiliationID  <br/> |其查找包含在 tblPrincipal.prinID 表中的外键。  <br/> |
   

