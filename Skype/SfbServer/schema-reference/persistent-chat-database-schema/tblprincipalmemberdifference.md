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
description: tblPrincipalMemberDifference 包含组成员身份更改 (添加和删除的成员) 这些更改尚未由稍后的 Active Directory 域服务同步步骤处理。
ms.openlocfilehash: c1d5a0d492d228b5a8292fde608fbd66c3b586c393aba8eb5bc0fbbddd45a5e2
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54276577"
---
# <a name="tblprincipalmemberdifference"></a>tblPrincipalMemberDifference
 
tblPrincipalMemberDifference 包含组成员身份更改 (添加和删除的成员) 这些更改尚未由稍后的 Active Directory 域服务同步步骤处理。
  
**Columns**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID，不为 null  <br/> |更改的组的主体 GUID。  <br/> |
|memberADPath  <br/> |nvarchar (256)  <br/> |成员的可分辨名称。  <br/> |
|memberRemoved  <br/> |bit，不为 null  <br/> |在添加成员时，设置为 False。在删除成员时，设置为 True。  <br/> |
   
**键**

|**列**|**说明**|
|:-----|:-----|
|\<prinGuid, memberADPath\>  <br/> |主键。  <br/> |
   

