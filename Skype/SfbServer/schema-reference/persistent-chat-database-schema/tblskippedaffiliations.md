---
title: tblSkippedAffiliations
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: tblSkippedAffiliations 包含 （通常因为 Active Directory 域服务访问错误） 无法读取的附属关系。
ms.openlocfilehash: 85fe836e75409a0a6aae22583358f9f88dc8d4e1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924939"
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
   

