---
title: tblPrincipal
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 79a24502-b4ce-41f0-8979-8caddf535338
description: tblPrincipal 包含所有主体，包括用户、 文件夹和组。
ms.openlocfilehash: 847af7f719b15161738d488408ac11b81d9c57a3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipal"></a>tblPrincipal
 
tblPrincipal 包含所有主体，包括用户、 文件夹和组。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|prinID  <br/> |int，不为空  <br/> |主体标识。  <br/> |
|prinGuid  <br/> |GUID，不为空  <br/> |主体的 GUID。 这广泛用作备用的主键因为其含义跨到 Active Directory 域服务空间。 （缓存主体的 GUID 是等于相应 Active Directory 对象的 GUID。  <br/> |
|prinUri  <br/> |nvarchar (256) 不为空  <br/> |主体的 URI。 对于用户，使用 SIP 方案和 ma 组适用于几乎所有其他内容。  <br/> |
|prinName  <br/> |nvarchar (256)  <br/> |公用名。 仅供用户类型。  <br/> |
|prinDisplayName  <br/> |Nvarchar (256)  <br/> |显示名称。 仅供用户类型。  <br/> |
|prinCompanyName  <br/> |nvarchar (256)  <br/> |公司名称。 仅供用户类型。  <br/> |
|prinEmail  <br/> |nvarchar (256)  <br/> |电子邮件。 仅供用户类型。  <br/> |
|prinADPath  <br/> |nvarchar (384)  <br/> |主体的缓存的版本的 Active Directory 对象的域的名称。 可以为 Null 的类型不是 Active Directory 对象 （如系统的用户）。  <br/> |
|prinADUserPrincipalName  <br/> |nvarchar (256)  <br/> |用户的用户主体名称 (UPN)。 仅使用常规用户类型。  <br/> |
|prinDisabled  <br/> |smallint，不为空  <br/> | 0： 主体处于活动状态。 <br/>  1： 主体被禁用，因为用户的 SIP 功能都会被禁用。 <br/>  2： 主体被删除，因为关联的 AD 对象已被删除。 <br/> |
|prinTypeID  <br/> |smallint，不为空  <br/> |（从 tblPrincipalType 表） 的主体类型。  <br/> |
|prinPoolID  <br/> |Int  <br/> |Skype 的业务客户池分配的主体。  <br/> |
|prinPolicyID  <br/> |Int  <br/> |用户，如果标记类型策略存在持久聊天服务器的策略值。  <br/> |
|prinAddedBy  <br/> |int  <br/> |主要创建者 ID。  <br/> |
|prinAddedOn  <br/> |bigint，不为空  <br/> |创建时间的时间戳。  <br/> |
|prinUpdatedBy  <br/> |int  <br/> |上次更新此主体的 ID。  <br/> |
|prinUpdatedOn  <br/> |bigint，不为空  <br/> |上次更新的时间戳。  <br/> |
|prinVerifiedOn  <br/> |日期时间不为空  <br/> |上次活动目录同步的日期和时间刷新的主体。  <br/> |
   
**密钥**

|**列**|**说明**|
|:-----|:-----|
|prinID  <br/> |为主键。  <br/> |
|prinTypeID  <br/> |TblPrincipalType.ptypeID 表中查找与外键。  <br/> |
   

