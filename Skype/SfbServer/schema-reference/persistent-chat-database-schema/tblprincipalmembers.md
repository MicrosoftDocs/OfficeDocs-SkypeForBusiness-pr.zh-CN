---
title: tblPrincipalMembers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: tblPrincipalMembers 包含主体成员身份。
ms.openlocfilehash: c56ab16f96322cb295c4eff6fc63e01ba887dd22
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813940"
---
# <a name="tblprincipalmembers"></a>tblPrincipalMembers
 
tblPrincipalMembers 包含主体成员身份。
  
**多**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|prinID  <br/> |int，not null  <br/> |主体 ID。  <br/> |
|memberADPath  <br/> |nvarchar （384），not null  <br/> |成员的可分辨名称。 成员不必是主体（在 tblPrincipal 表中）。  <br/> |
   
**标示**

|**列**|**说明**|
|:-----|:-----|
|\<prinID, memberADPath\>  <br/> |主键。  <br/> |
|prinID  <br/> |在 tblPrincipal 中查找的外键。 prinID。  <br/> |
   

