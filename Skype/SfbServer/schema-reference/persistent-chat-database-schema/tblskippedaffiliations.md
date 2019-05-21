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
localization_priority: Normal
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: tblSkippedAffiliations 包含无法读取的隶属关系 (通常是由于 Active Directory 域服务访问错误)。
ms.openlocfilehash: 481bf92a4014bf2af8e1c4794d1793f2c93e7c36
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295151"
---
# <a name="tblskippedaffiliations"></a>tblSkippedAffiliations
 
tblSkippedAffiliations 包含无法读取的隶属关系 (通常是由于 Active Directory 域服务访问错误)。
  
**多**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|prinID  <br/> |int, not null  <br/> |主体 ID。  <br/> |
|affDescription  <br/> |nvarchar (256), not null  <br/> |标识隶属关系的字符串。  <br/> 格式为: guid: _{0}_ uri: _{1}_> id:_{2}_ <br/> |
|updatedBy  <br/> |int, not null  <br/> |已更新此行的主体的 ID。 由于 Active Directory 同步是这些条目的唯一源, 因此始终为 1 (系统用户)。  <br/> |
   
**标示**

|**列**|**说明**|
|:-----|:-----|
|\<prinID, affDescription\>  <br/> |主键。  <br/> |
|prinID  <br/> |TblPrincipal 表中的 lookup 的外键。  <br/> |
   

