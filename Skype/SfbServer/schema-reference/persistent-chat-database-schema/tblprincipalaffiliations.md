---
title: tblPrincipalAffiliations
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 45fd8484-5837-44d2-85bb-45c83546607c
description: tblPrincipalAffiliations 包含主体的隶属关系描述的位置，包括 Active Directory 域服务安全组，请在域中的 Active Directory 容器中的成员。
ms.openlocfilehash: 4e5529590a6a636c28c801392953c7fd69e9f649
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipalaffiliations"></a>tblPrincipalAffiliations
 
tblPrincipalAffiliations 包含主体的隶属关系描述的位置，包括 Active Directory 域服务安全组，请在域中的 Active Directory 容器中的成员。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|principalID  <br/> |int，不为空  <br/> |相关主体的 ID。  <br/> |
|affiliationID  <br/> |int，不为空  <br/> |表示该隶属关系主体的 ID。 每个主体 （除了系统用户类型） 具有自我的隶属关系也。  <br/> |
|索引  <br/> |int，不为空  <br/> |索引。 自我的隶属关系的值为-1，并且为其他附属机构会增加按顺序从 1，其中每个\<principalID，affiliationId\>桶。  <br/> |
|updatedBy  <br/> |int，不为空  <br/> |做最新的更新的主体。 这通常是 1，这意味着活动目录同步。  <br/> |
   
**密钥**

|**列**|**说明**|
|:-----|:-----|
|\<principalID、 索引、 affiliationID\>  <br/> |为主键。  <br/> |
|principalID  <br/> |TblPrincipal.prinID 表中查找与外键。  <br/> |
|affiliationID  <br/> |TblPrincipal.prinID 表中查找与外键。  <br/> |
   

