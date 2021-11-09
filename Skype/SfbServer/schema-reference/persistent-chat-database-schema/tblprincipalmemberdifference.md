---
title: tblPrincipalMemberDifference
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: tblPrincipalMemberDifference 包含组成员身份更改 (添加和删除的成员) 这些更改尚未由稍后的 Active Directory 域服务同步步骤处理。
ms.openlocfilehash: 6bbf1762d12f242b17598752de4ee62f90238eae
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60864569"
---
# <a name="tblprincipalmemberdifference"></a>tblPrincipalMemberDifference
 
tblPrincipalMemberDifference 包含组成员身份更改 (添加和删除的成员) 这些更改尚未由稍后的 Active Directory 域服务同步步骤处理。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID，不为 null  <br/> |更改的组的主体 GUID。  <br/> |
|memberADPath  <br/> |nvarchar (256)  <br/> |成员的可分辨名称。  <br/> |
|memberRemoved  <br/> |bit，不为 null  <br/> |在添加成员时，设置为 False。在删除成员时，设置为 True。  <br/> |
   
**键**

|**列**|**说明**|
|:-----|:-----|
|\<prinGuid, memberADPath\>  <br/> |主键。  <br/> |
   

