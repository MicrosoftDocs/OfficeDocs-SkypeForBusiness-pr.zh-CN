---
title: tblPrincipalMemberDifference
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
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: tblPrincipalMemberDifference 包含后续 Active Directory 域服务同步步骤尚未处理的组成员身份更改（添加和删除的成员）。
ms.openlocfilehash: c7e965658c9e351a7a2d079921b7abe8166b48ad
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814070"
---
# <a name="tblprincipalmemberdifference"></a>tblPrincipalMemberDifference
 
tblPrincipalMemberDifference 包含后续 Active Directory 域服务同步步骤尚未处理的组成员身份更改（添加和删除的成员）。
  
**多**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID，not null  <br/> |已更改的组的主体 GUID。  <br/> |
|memberADPath  <br/> |nvarchar （256）  <br/> |成员的可分辨名称。  <br/> |
|memberRemoved  <br/> |位，not null  <br/> |如果添加了成员，则为 False。 如果删除了该成员，则为 True。  <br/> |
   
**Key**

|**列**|**说明**|
|:-----|:-----|
|\<prinGuid, memberADPath\>  <br/> |主键。  <br/> |
   

