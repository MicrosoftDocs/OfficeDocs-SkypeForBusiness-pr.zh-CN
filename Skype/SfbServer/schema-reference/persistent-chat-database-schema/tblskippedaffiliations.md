---
title: tblSkippedAffiliations
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
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: tblSkippedAffiliations 包含无法读取的隶属关系（通常是由于 Active Directory 域服务访问错误）。
ms.openlocfilehash: 8a138993e12a49f72842808d720a5f778195c6ff
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812010"
---
# <a name="tblskippedaffiliations"></a>tblSkippedAffiliations
 
tblSkippedAffiliations 包含无法读取的隶属关系（通常是由于 Active Directory 域服务访问错误）。
  
**多**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|prinID  <br/> |int，not null  <br/> |主体 ID。  <br/> |
|affDescription  <br/> |nvarchar （256），not null  <br/> |标识隶属关系的字符串。  <br/> 格式为： guid： _{0}_ uri： _{1}_> id：_{2}_ <br/> |
|updatedBy  <br/> |int，not null  <br/> |已更新此行的主体的 ID。 由于 Active Directory 同步是这些条目的唯一源，因此始终为1（系统用户）。  <br/> |
   
**标示**

|**列**|**说明**|
|:-----|:-----|
|\<prinID, affDescription\>  <br/> |主键。  <br/> |
|prinID  <br/> |TblPrincipal 表中的 lookup 的外键。  <br/> |
   

