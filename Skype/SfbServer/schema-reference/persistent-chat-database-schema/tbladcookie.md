---
title: tblADCookie
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
description: tblADCookie 包含当前轻型目录访问协议 (LDAP) 同步 cookie。
ms.openlocfilehash: d990d02e73be9a4d6178037a314e36add448ad40
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929943"
---
# <a name="tbladcookie"></a>tblADCookie
 
tblADCookie 包含当前轻型目录访问协议 (LDAP) 同步 cookie。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID，不为 null  <br/> |要监控的域的主体 GUID。  <br/> |
|prinDCHost  <br/> |nvarchar (255)  <br/> |完全限定的域名 (FQDN) 的当前用于 Active Directory 域服务同步的域控制器。具有信息的价值。  <br/> |
|adcContent  <br/> |图像 （二进制）  <br/> |Active Directory 同步 cookie。  <br/> |
|lastUpdated  <br/> |datetime  <br/> |具有行更新时间的时间戳。  <br/> |
|lockedUntil  <br/> |datetime  <br/> |行锁定更改时间。 这是软件互锁机制，以确保只有一个聊天服务的每次执行 Active Directory 同步的一部分。  <br/> |
   
**键**

|**列**|**说明**|
|:-----|:-----|
|prinGuid  <br/> |主键。  <br/> |
|prinGuid  <br/> |在 Principal.prinGuid 表中查找的外键。  <br/> |
   

