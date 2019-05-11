---
title: tblPrincipalMembers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: tblPrincipalMembers 包含主体成员身份。
ms.openlocfilehash: be66ee6124c7b0306583bcb10f7d78b777fcf10c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33904158"
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
   

