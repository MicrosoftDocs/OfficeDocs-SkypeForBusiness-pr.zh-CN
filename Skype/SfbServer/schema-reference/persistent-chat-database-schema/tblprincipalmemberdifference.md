---
title: tblPrincipalMemberDifference
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: tblPrincipalMemberDifference 包含组成员身份的更改 （添加和删除成员） 尚未处理的后续活动目录域服务同步步骤。
ms.openlocfilehash: 603c8345f2adc2ba7d5eb04835218fd3e83d8ed4
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipalmemberdifference"></a>tblPrincipalMemberDifference
 
tblPrincipalMemberDifference 包含组成员身份的更改 （添加和删除成员） 尚未处理的后续活动目录域服务同步步骤。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID，不为空  <br/> |更改组的主体 GUID。  <br/> |
|memberADPath  <br/> |nvarchar (256)  <br/> |成员的可分辨的名称。  <br/> |
|memberRemoved  <br/> |位，不为空  <br/> |如果添加的成员，则为 false。 如果成员已删除，则为 true。  <br/> |
   
**密钥**

|**列**|**说明**|
|:-----|:-----|
|\<prinGuid memberADPath\>  <br/> |为主键。  <br/> |
   

