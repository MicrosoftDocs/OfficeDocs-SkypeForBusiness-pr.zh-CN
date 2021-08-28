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
ms.localizationpriority: medium
ms.assetid: 45fd8484-5837-44d2-85bb-45c83546607c
description: tblPrincipalAffiliations 包含主体附属关系，这些附属关系描述域中 Active Directory 容器中的位置（包括 Active Directory 域服务安全组）中的成员身份。
ms.openlocfilehash: 6126fb32b6b56c9a3ec142ad1b1186763f28d045
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58580376"
---
# <a name="tblprincipalaffiliations"></a>tblPrincipalAffiliations
 
tblPrincipalAffiliations 包含主体附属关系，这些附属关系描述域中 Active Directory 容器中的位置（包括 Active Directory 域服务安全组）中的成员身份。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|principalID  <br/> |int，不为 null  <br/> |附属主体的 ID。  <br/> |
|affiliationID  <br/> |int，不为 null  <br/> |表示附属关系的主体的 ID。每个主体（系统用户类型除外）还具有自附属关系。  <br/> |
|index  <br/> |int，不为 null  <br/> |索引。 自附属关系的值为 -1，对于其他附属关系，该值从每个存储桶中的 1 依次 \<principalID, affiliationId\> 增加。  <br/> |
|updatedBy  <br/> |int，不为 null  <br/> |进行最新更新的主体。这通常为 1，表示 Active Directory 同步。  <br/> |
   
**Keys**

|**列**|**说明**|
|:-----|:-----|
|\<principalID, index, affiliationID\>  <br/> |主键。  <br/> |
|principalID  <br/> |其查找包含在 tblPrincipal.prinID 表中的外键。  <br/> |
|affiliationID  <br/> |其查找包含在 tblPrincipal.prinID 表中的外键。  <br/> |
   

