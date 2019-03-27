---
title: tblPrincipal
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 79a24502-b4ce-41f0-8979-8caddf535338
description: tblPrincipal 包含所有主体，其中包括用户、 文件夹和组。
ms.openlocfilehash: adeb4e52ea9bd276de09d90945443431fb3be94f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30880971"
---
# <a name="tblprincipal"></a>tblPrincipal
 
tblPrincipal 包含所有主体，其中包括用户、 文件夹和组。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|prinID  <br/> |int，不为 null  <br/> |主体 id。  <br/> |
|prinGuid  <br/> |GUID，不为 null  <br/> |主体 GUID。 这基本上用作备用的主键，因为其含义跨到 Active Directory 域服务空间。 （缓存的主体 GUID 等于相应 Active Directory 对象的 GUID。）  <br/> |
|prinUri  <br/> |nvarchar (256)，不为 null  <br/> |主体的 URI。 对于用户，使用 SIP 方案和 ma 组使用的几乎所有其他人。  <br/> |
|prinName  <br/> |nvarchar (256)  <br/> |公用名。 仅由用户类型。  <br/> |
|prinDisplayName  <br/> |Nvarchar (256)  <br/> |显示名称。 仅由用户类型。  <br/> |
|prinCompanyName  <br/> |nvarchar (256)  <br/> |公司名称。 仅由用户类型。  <br/> |
|prinEmail  <br/> |nvarchar (256)  <br/> |电子邮件。 仅由用户类型。  <br/> |
|prinADPath  <br/> |nvarchar (384)  <br/> |Active Directory 对象的主体的缓存的版本的域名。 可以为不是 Active Directory 对象 （例如系统用户） 的类型为 Null。  <br/> |
|prinADUserPrincipalName  <br/> |nvarchar (256)  <br/> |用户的用户主体名称 (UPN)。 仅由常规用户类型。  <br/> |
|prinDisabled  <br/> |smallint，不为 null  <br/> | 0： 主体处于活动状态。 <br/>  1： 禁用主体，因为用户的 SIP 功能被禁用。 <br/>  2： 删除主体，因为关联的 AD 对象已被删除。 <br/> |
|prinTypeID  <br/> |smallint，不为 null  <br/> |主体类型 （来自 tblPrincipalType 表）。  <br/> |
|prinPoolID  <br/> |Int  <br/> |Skype 的主体的业务客户端池分配。  <br/> |
|prinPolicyID  <br/> |Int  <br/> |用户，如果标签类型策略存在的持久聊天服务器策略值。  <br/> |
|prinAddedBy  <br/> |int  <br/> |创建者的主体 ID。  <br/> |
|prinAddedOn  <br/> |bigint，不为 null  <br/> |创建时间的时间戳。  <br/> |
|prinUpdatedBy  <br/> |int  <br/> |上次更新此主体的 ID。  <br/> |
|prinUpdatedOn  <br/> |bigint，不为 null  <br/> |上次更新的时间戳。  <br/> |
|prinVerifiedOn  <br/> |datetime，不为 null  <br/> |日期和时间的最后一个 Active Directory 同步刷新的主体。  <br/> |
   
**键**

|**列**|**说明**|
|:-----|:-----|
|prinID  <br/> |主键。  <br/> |
|prinTypeID  <br/> |包含在 tblPrincipalType.ptypeID 表中查找的外键。  <br/> |
   

