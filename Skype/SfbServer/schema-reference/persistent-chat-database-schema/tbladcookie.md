---
title: tblADCookie
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
description: tblADCookie 包含当前轻型目录访问协议 (LDAP) 同步 Cookie。
ms.openlocfilehash: 770900c7ad5e31173a9e62ea3eb5a8c711afca98
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60743168"
---
# <a name="tbladcookie"></a>tblADCookie
 
tblADCookie 包含当前轻型目录访问协议 (LDAP) 同步 Cookie。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID，不为 null  <br/> |要监控的域的主体 GUID。  <br/> |
|prinDCHost  <br/> |nvarchar (255)  <br/> |Active Directory 域 (同步) 当前域控制器的完全限定域名和 FQDN。具有信息值。  <br/> |
|adcContent  <br/> |image (binary)  <br/> |Active Directory 同步 Cookie。  <br/> |
|lastUpdated  <br/> |datetime  <br/> |具有行更新时间的时间戳。  <br/> |
|lockedUntil  <br/> |datetime  <br/> |为更改锁定行的截止时间。此时间是软件联锁机制的一部分，可确保一次仅使其中一个聊天服务执行 Active Directory 同步。  <br/> |
   
**Keys**

|**列 (列)**|**说明**|
|:-----|:-----|
|prinGuid  <br/> |主键。  <br/> |
|prinGuid  <br/> |其查找包含在 Principal.prinGuid 表中的外键。  <br/> |
   

