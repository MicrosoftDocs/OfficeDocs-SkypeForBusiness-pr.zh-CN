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
localization_priority: Normal
ms.assetid: 45fd8484-5837-44d2-85bb-45c83546607c
description: tblPrincipalAffiliations 包含描述位置中的成员身份的主体成员, 包括 Active directory 域服务安全组, 位于 Active Directory 容器中的域中。
ms.openlocfilehash: cda9827f4a4ab7e17a156cc867e4925c88d06ff3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295312"
---
# <a name="tblprincipalaffiliations"></a>tblPrincipalAffiliations
 
tblPrincipalAffiliations 包含描述位置中的成员身份的主体成员, 包括 Active directory 域服务安全组, 位于 Active Directory 容器中的域中。
  
**多**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|principalID  <br/> |int, not null  <br/> |关联主体的 ID。  <br/> |
|affiliationID  <br/> |int, not null  <br/> |表示隶属关系的承担者的 ID。 每个主体 (除系统用户类型外) 还具有自我隶属关系。  <br/> |
|食指  <br/> |int, not null  <br/> |食指. 自隶属关系的值是-1, 对于其他隶属关系, 在每个\<PrincipalID、affiliationId\>存储桶中, 它将按从1开始递增。  <br/> |
|updatedBy  <br/> |int, not null  <br/> |已进行最新更新的主体。 这通常是 1, 这意味着 Active Directory 同步。  <br/> |
   
**标示**

|**多**|**说明**|
|:-----|:-----|
|\<principalID、index、affiliationID\>  <br/> |主键。  <br/> |
|principalID  <br/> |TblPrincipal 表中的 lookup 的外键。  <br/> |
|affiliationID  <br/> |TblPrincipal 表中的 lookup 的外键。  <br/> |
   

