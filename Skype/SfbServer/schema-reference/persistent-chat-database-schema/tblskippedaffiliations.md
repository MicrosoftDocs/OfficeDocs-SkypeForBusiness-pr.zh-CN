---
title: tblSkippedAffiliations
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: tblSkippedAffiliations 包含无法读取 （通常是因为 Active Directory 域服务访问错误） 隶属关系。
ms.openlocfilehash: 8809e75f7da7f08c3dee9a846cef332d9cba4371
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="tblskippedaffiliations"></a>tblSkippedAffiliations
 
tblSkippedAffiliations 包含无法读取 （通常是因为 Active Directory 域服务访问错误） 隶属关系。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|prinID  <br/> |int，不为空  <br/> |主体标识。  <br/> |
|affDescription  <br/> |nvarchar (256) 不为空  <br/> |一个字符串，它标识该隶属关系。  <br/> 格式是： guid: _{0}_ uri: _{1}_> id: _{2}_ <br/> |
|updatedBy  <br/> |int，不为空  <br/> |更新此行的主要用户的 ID。 它始终是 1 （系统用户），因为活动目录同步是这些条目的唯一来源。  <br/> |
   
**密钥**

|**列**|**说明**|
|:-----|:-----|
|\<prinID affDescription\>  <br/> |为主键。  <br/> |
|prinID  <br/> |TblPrincipal.prinID 表中查找与外键。  <br/> |
   

