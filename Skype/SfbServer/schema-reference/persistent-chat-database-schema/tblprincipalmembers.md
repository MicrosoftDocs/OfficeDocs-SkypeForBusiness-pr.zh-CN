---
title: tblPrincipalMembers
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: tblPrincipalMembers 包含主体成员身份。
ms.openlocfilehash: 2b2b9616c76095ec27178887e69dd482bcf6da92
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212486"
---
# <a name="tblprincipalmembers"></a>tblPrincipalMembers
 
tblPrincipalMembers 包含主体成员身份。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|prinID  <br/> |int，不为 null  <br/> |主体 id。  <br/> |
|memberADPath  <br/> |nvarchar (384)，不为 null  <br/> |成员可分辨的名称。 成员没有要 （在 tblPrincipal 表中） 的主体。  <br/> |
   
**键**

|**列**|**说明**|
|:-----|:-----|
|\<prinID memberADPath\>  <br/> |主键。  <br/> |
|prinID  <br/> |在 tblPrincipal.prinID 中查找的外键。  <br/> |
   

