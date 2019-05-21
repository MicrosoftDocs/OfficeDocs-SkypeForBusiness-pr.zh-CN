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
localization_priority: Normal
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: tblPrincipalMemberDifference 包含后续 Active Directory 域服务同步步骤尚未处理的组成员身份更改 (添加和删除的成员)。
ms.openlocfilehash: 18d0f3f5c8700db0bb81470f5ee90851e8d277ad
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295298"
---
# <a name="tblprincipalmemberdifference"></a>tblPrincipalMemberDifference
 
tblPrincipalMemberDifference 包含后续 Active Directory 域服务同步步骤尚未处理的组成员身份更改 (添加和删除的成员)。
  
**多**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID, not null  <br/> |已更改的组的主体 GUID。  <br/> |
|memberADPath  <br/> |nvarchar (256)  <br/> |成员的可分辨名称。  <br/> |
|memberRemoved  <br/> |位, not null  <br/> |如果添加了成员, 则为 False。 如果删除了该成员, 则为 True。  <br/> |
   
**关键字**

|**列**|**说明**|
|:-----|:-----|
|\<prinGuid, memberADPath\>  <br/> |主键。  <br/> |
   

