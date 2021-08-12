---
title: tblPrincipal
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 79a24502-b4ce-41f0-8979-8caddf535338
description: tblPrincipal 包含所有主体，其中包括用户、文件夹和组。
ms.openlocfilehash: 50d20aee156a4a919effac26ff29c371ec2cf886c12300ecd07268576730ae49
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54338020"
---
# <a name="tblprincipal"></a>tblPrincipal
 
tblPrincipal 包含所有主体，其中包括用户、文件夹和组。
  
**Columns**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|prinID  <br/> |int，不为 null  <br/> |主体 ID。  <br/> |
|prinGuid  <br/> |GUID，不为 null  <br/> |主体 GUID。 这通常用作备用主键，因为它的含义会跨越到 Active Directory 域服务空间。  (缓存主体的 GUID 等于对应的 Active Directory 对象 GUID.)   <br/> |
|prinUri  <br/> |nvarchar (256)，不为 null  <br/> |主体 URI。SIP 方案用于用户，ma-grp 用于几乎其他的一切对象。  <br/> |
|prinName  <br/> |nvarchar (256)  <br/> |公用名。仅供用户类型使用。  <br/> |
|prinDisplayName  <br/> |Nvarchar (256)  <br/> |显示名称。仅供用户类型使用。  <br/> |
|prinCompanyName  <br/> |nvarchar (256)  <br/> |公司名称。仅供用户类型使用。  <br/> |
|prinEmail  <br/> |nvarchar (256)  <br/> |电子邮件。仅供用户类型使用。  <br/> |
|prinADPath  <br/> |nvarchar (384)  <br/> |主体是其缓存版本的 Active Directory 对象的域名。对于非 Active Directory 对象的类型（例如系统用户），可以为 Null。  <br/> |
|prinADUserPrincipalName  <br/> |nvarchar (256)  <br/> |用户的用户主体名称 (UPN) 。 仅供常规用户类型使用。  <br/> |
|prinDisabled  <br/> |smallint，不为 null  <br/> | 0：主体处于活动状态。 <br/>  1：主体已禁用，因为用户的 SIP 功能已禁用。 <br/>  2：删除主体，因为关联的 AD 对象已被删除。 <br/> |
|prinTypeID  <br/> |smallint，不为 null  <br/> |主体类型（来自 tblPrincipalType 表）。  <br/> |
|prinPoolID  <br/> |Int  <br/> |Skype for Business主体的客户端池分配。  <br/> |
|prinPolicyID  <br/> |Int  <br/> |用户的持久聊天服务器策略值（如果存在标记类型策略）。  <br/> |
|prinAddedBy  <br/> |int  <br/> |创建者的主体 ID。  <br/> |
|prinAddedOn  <br/> |bigint，不为 null  <br/> |创建时间的时间戳。  <br/> |
|prinUpdatedBy  <br/> |int  <br/> |上次更新它的主体的 ID。  <br/> |
|prinUpdatedOn  <br/> |bigint，不为 null  <br/> |上次更新的时间戳。  <br/> |
|prinVerifiedOn  <br/> |datetime，不为 null  <br/> |主体上次进行 Active Directory 同步刷新的日期和时间。  <br/> |
   
**Keys**

|**列**|**说明**|
|:-----|:-----|
|prinID  <br/> |主键。  <br/> |
|prinTypeID  <br/> |其查找包含在 tblPrincipalType.ptypeID 表中的外键。  <br/> |
   

