---
title: tblSkippedAffiliations
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: tblSkippedAffiliations 包含 （通常因为 Active Directory 域服务访问错误） 无法读取的附属关系。
ms.openlocfilehash: 7072cf1d9ebef1040b78bc2fe93ccac02808099a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212605"
---
# <a name="tblskippedaffiliations"></a>tblSkippedAffiliations
 
tblSkippedAffiliations 包含 （通常因为 Active Directory 域服务访问错误） 无法读取的附属关系。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|prinID  <br/> |int，不为 null  <br/> |主体 id。  <br/> |
|affDescription  <br/> |nvarchar (256)，不为 null  <br/> |标识隶属项的字符串。  <br/> 格式为： guid: _{0}_ uri: _{1}_> id:_{2}_ <br/> |
|updatedBy  <br/> |int，不为 null  <br/> |更新此行的主体的 ID。 由于 Active Directory 同步这些条目的唯一源，它始终是 1 （系统用户）。  <br/> |
   
**键**

|**列**|**说明**|
|:-----|:-----|
|\<prinID affDescription\>  <br/> |主键。  <br/> |
|prinID  <br/> |在 tblPrincipal.prinID 表中查找的外键。  <br/> |
   

