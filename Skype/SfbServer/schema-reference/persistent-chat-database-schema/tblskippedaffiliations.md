---
title: tblSkippedAffiliations
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
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: tblSkippedAffiliations 包含通常由于 Active Directory 域服务访问错误 (无法读取的附属) 。
ms.openlocfilehash: b0996e3208e760c55b1b9d621d00e92a8e7a7112
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "62394784"
---
# <a name="tblskippedaffiliations"></a>tblSkippedAffiliations
 
tblSkippedAffiliations 包含通常由于 Active Directory 域服务访问错误 (无法读取的附属) 。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|prinID  <br/> |int，不为 null  <br/> |主体 ID。  <br/> |
|affDescription  <br/> |nvarchar (256)，不为 null  <br/> |标识隶属项的字符串。  <br/> 格式为：guid：  _{0}_ uri： _{1}_> id：  _{2}_ <br/> |
|updatedBy  <br/> |int，不为 null  <br/> |更新此行的主体的 ID。该值始终为 1（系统用户），因为 Active Directory 同步是这些条目的唯一来源。  <br/> |
   
**Keys**

|**列 ()**|**说明**|
|:-----|:-----|
|\<prinID, affDescription\>  <br/> |主键。  <br/> |
|prinID  <br/> |其查找包含在 tblPrincipal.prinID 表中的外键。  <br/> |
   

