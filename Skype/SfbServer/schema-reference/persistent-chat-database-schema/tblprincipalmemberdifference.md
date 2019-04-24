---
title: tblPrincipalMemberDifference
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: Principalmemberdifference 包含组的成员身份更改 （添加和删除的成员） 尚未由后面的 Active Directory 域服务同步步骤处理。
ms.openlocfilehash: 77b246e96dbd13464b5655fe87d5a10861db30c7
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212444"
---
# <a name="tblprincipalmemberdifference"></a>tblPrincipalMemberDifference
 
Principalmemberdifference 包含组的成员身份更改 （添加和删除的成员） 尚未由后面的 Active Directory 域服务同步步骤处理。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID，不为 null  <br/> |更改的组的主体 GUID。  <br/> |
|memberADPath  <br/> |nvarchar (256)  <br/> |成员的可分辨的名称。  <br/> |
|memberRemoved  <br/> |bit，不为 null  <br/> |如果已添加成员，则为 false。 如果已删除成员，则为 true。  <br/> |
   
**关键字**

|**列**|**说明**|
|:-----|:-----|
|\<prinGuid memberADPath\>  <br/> |主键。  <br/> |
   

