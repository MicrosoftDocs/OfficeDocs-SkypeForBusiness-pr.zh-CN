---
title: tblPrincipalMembers
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
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
ms.openlocfilehash: 77377a98e7dcf336eb05deb68c170de0c58a1223
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "62389050"
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
   

