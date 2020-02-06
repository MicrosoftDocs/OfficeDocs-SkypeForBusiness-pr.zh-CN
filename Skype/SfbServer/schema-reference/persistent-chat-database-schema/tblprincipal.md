---
title: tblPrincipal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 79a24502-b4ce-41f0-8979-8caddf535338
description: tblPrincipal 包含所有主体，包括用户、文件夹和组。
ms.openlocfilehash: 7924c65745e29cce6dd71dc14b1ecfe7b41fe8b3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814500"
---
# <a name="tblprincipal"></a>tblPrincipal
 
tblPrincipal 包含所有主体，包括用户、文件夹和组。
  
**多**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|prinID  <br/> |int，not null  <br/> |主体 ID。  <br/> |
|prinGuid  <br/> |GUID，not null  <br/> |主体 GUID。 它被广泛用作备用主键，因为它的含义与 Active Directory 域服务空间中的含义相同。 （缓存主体的 GUID 等于相应的 Active Directory 对象 GUID。）  <br/> |
|prinUri  <br/> |nvarchar （256），not null  <br/> |主体 URI。 SIP 方案用于用户，并且 ma-grp 用于几乎所有其他内容。  <br/> |
|prinName  <br/> |nvarchar （256）  <br/> |公用名。 仅由用户类型使用。  <br/> |
|prinDisplayName  <br/> |Nvarchar （256）  <br/> |显示名称。 仅由用户类型使用。  <br/> |
|prinCompanyName  <br/> |nvarchar （256）  <br/> |公司名称。 仅由用户类型使用。  <br/> |
|prinEmail  <br/> |nvarchar （256）  <br/> |电子邮件。 仅由用户类型使用。  <br/> |
|prinADPath  <br/> |nvarchar （384）  <br/> |Active Directory 对象的域名，主体是的缓存版本。 对于非 Active Directory 对象（如系统用户）的类型，可以为 Null。  <br/> |
|prinADUserPrincipalName  <br/> |nvarchar （256）  <br/> |用户的用户主体名称（UPN）。 仅由常规用户类型使用。  <br/> |
|prinDisabled  <br/> |smallint，not null  <br/> | 0：主体处于活动状态。 <br/>  1：主体被禁用，因为用户的 SIP 功能已被禁用。 <br/>  2：删除主体，因为关联的 AD 对象已被删除。 <br/> |
|prinTypeID  <br/> |smallint，not null  <br/> |主体类型（来自 tblPrincipalType 表）。  <br/> |
|prinPoolID  <br/> |整形  <br/> |适用于主体的 Skype for business 客户端池分配。  <br/> |
|prinPolicyID  <br/> |整形  <br/> |用户的持久聊天服务器策略值（如果存在标记类型策略）。  <br/> |
|prinAddedBy  <br/> |int  <br/> |创建者的主体 ID。  <br/> |
|prinAddedOn  <br/> |bigint，not null  <br/> |创建时间的时间戳。  <br/> |
|prinUpdatedBy  <br/> |int  <br/> |上次更新此操作的主体的 ID。  <br/> |
|prinUpdatedOn  <br/> |bigint，not null  <br/> |上次更新的时间戳。  <br/> |
|prinVerifiedOn  <br/> |datetime，not null  <br/> |主体的上次 Active Directory 同步刷新的日期和时间。  <br/> |
   
**标示**

|**列**|**说明**|
|:-----|:-----|
|prinID  <br/> |主键。  <br/> |
|prinTypeID  <br/> |TblPrincipalType 表中的 lookup 的外键。  <br/> |
   

