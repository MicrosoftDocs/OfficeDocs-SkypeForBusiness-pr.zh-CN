---
title: tblPrincipalMembers
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: tblPrincipalMembers 包含主体成员身份。
ms.openlocfilehash: f1763244620d8ffd0ed86837b18eabc97bc72781
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60749731"
---
# <a name="tblprincipalmembers"></a>tblPrincipalMembers
 
tblPrincipalMembers 包含主体成员身份。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|prinID  <br/> |int，不为 null  <br/> |主体 ID。  <br/> |
|memberADPath  <br/> |nvarchar (384)，不为 null  <br/> |成员的可分辨名称。成员不必是主体（在 tblPrincipal 表中）。  <br/> |
   
**Keys**

|**列**|**说明**|
|:-----|:-----|
|\<prinID, memberADPath\>  <br/> |主键。  <br/> |
|prinID  <br/> |在 tblPrincipal.prinID 中查找的外键。  <br/> |
   

