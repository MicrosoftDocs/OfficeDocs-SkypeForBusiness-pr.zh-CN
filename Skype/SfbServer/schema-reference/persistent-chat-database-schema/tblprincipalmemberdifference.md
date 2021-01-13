---
title: tblPrincipalMemberDifference
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
localization_priority: Normal
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: tblPrincipalMemberDifference 包含组成员身份更改 (添加和删除) 尚未由稍后的 Active Directory 域服务同步步骤处理的成员。
ms.openlocfilehash: 8fac76f1abfbd55d13d89c96bb23a6953d38edf9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809702"
---
# <a name="tblprincipalmemberdifference"></a>tblPrincipalMemberDifference
 
tblPrincipalMemberDifference 包含组成员身份更改 (添加和删除) 尚未由稍后的 Active Directory 域服务同步步骤处理的成员。
  
**Columns**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID，不为 null  <br/> |更改的组的主体 GUID。  <br/> |
|memberADPath  <br/> |nvarchar (256)  <br/> |成员的可分辨名称。  <br/> |
|memberRemoved  <br/> |bit，不为 null  <br/> |在添加成员时，设置为 False。在删除成员时，设置为 True。  <br/> |
   
**注册表项**

|**列**|**说明**|
|:-----|:-----|
|\<prinGuid, memberADPath\>  <br/> |主键。  <br/> |
   

