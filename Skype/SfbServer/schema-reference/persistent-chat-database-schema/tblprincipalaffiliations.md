---
title: tblPrincipalAffiliations
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 45fd8484-5837-44d2-85bb-45c83546607c
description: tblPrincipalAffiliations 包含的主体附属关系介绍中位置，包括 Active Directory 容器中以及域中的 Active Directory 域服务安全组的成员身份。
ms.openlocfilehash: c93edb552c63ebd4f7344926a7d43858b42506ae
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212500"
---
# <a name="tblprincipalaffiliations"></a>tblPrincipalAffiliations
 
tblPrincipalAffiliations 包含的主体附属关系介绍中位置，包括 Active Directory 容器中以及域中的 Active Directory 域服务安全组的成员身份。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|principalID  <br/> |int，不为 null  <br/> |附属主体的 ID。  <br/> |
|affiliationID  <br/> |int，不为 null  <br/> |表示隶属项的主体 ID。 （除系统用户类型） 的每个主体具有自我从属关系以及。  <br/> |
|索引  <br/> |int，不为 null  <br/> |索引。 自我隶属项的值为-1，并且其他隶属项的会增加按顺序从 1 中每个\<principalID，affiliationId\>地址散列表元。  <br/> |
|updatedBy  <br/> |int，不为 null  <br/> |执行最新更新的主体。 这通常是 1，这意味着 Active Directory 同步。  <br/> |
   
**键**

|**列**|**说明**|
|:-----|:-----|
|\<principalID、 索引、 affiliationID\>  <br/> |主键。  <br/> |
|principalID  <br/> |在 tblPrincipal.prinID 表中查找的外键。  <br/> |
|affiliationID  <br/> |在 tblPrincipal.prinID 表中查找的外键。  <br/> |
   

