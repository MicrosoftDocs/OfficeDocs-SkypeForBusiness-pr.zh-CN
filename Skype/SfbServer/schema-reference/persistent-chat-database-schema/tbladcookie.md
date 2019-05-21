---
title: tblADCookie
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
description: tblADCookie 包含当前的轻型目录访问协议 (LDAP) 同步 cookie。
ms.openlocfilehash: d75b1dc90d36aa0535fdac62b9e1a7061694cc76
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295529"
---
# <a name="tbladcookie"></a>tblADCookie
 
tblADCookie 包含当前的轻型目录访问协议 (LDAP) 同步 cookie。
  
**多**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID, not null  <br/> |正在监视的域的主体 GUID。  <br/> |
|prinDCHost  <br/> |nvarchar (255)  <br/> |用于 Active Directory 域服务同步的当前域控制器的完全限定的域名 (FQDN)。有信息值。  <br/> |
|adcContent  <br/> |图像 (二进制)  <br/> |Active Directory 同步 cookie。  <br/> |
|lastUpdated  <br/> |datetime  <br/> |带有行更新时间的时间戳。  <br/> |
|lockedUntil  <br/> |datetime  <br/> |对行进行更改锁定的时间。 这是一种软件互操作机制的一部分, 可确保每次只有一个聊天服务执行 Active Directory 同步。  <br/> |
   
**标示**

|**列**|**说明**|
|:-----|:-----|
|prinGuid  <br/> |主键。  <br/> |
|prinGuid  <br/> |PrinGuid 表中的 lookup 的外键。  <br/> |
   

