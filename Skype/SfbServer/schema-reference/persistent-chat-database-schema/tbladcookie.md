---
title: tblADCookie
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
description: tblADCookie 包含当前的轻型目录访问协议 (LDAP) 同步 cookie。
ms.openlocfilehash: bc2c0657caa66a0420bc493bf4b688a2a081db36
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="tbladcookie"></a>tblADCookie
 
tblADCookie 包含当前的轻型目录访问协议 (LDAP) 同步 cookie。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID，不为空  <br/> |被监视的域主体 GUID。  <br/> |
|prinDCHost  <br/> |nvarchar (255)  <br/> |活动目录域服务同步所用的当前域控制器的完全限定的域名称 (FQDN)。有信息的价值。  <br/> |
|adcContent  <br/> |图像 （二进制）  <br/> |活动目录同步 cookie。  <br/> |
|上次更新  <br/> |datetime  <br/> |行更新时间的时间戳。  <br/> |
|lockedUntil  <br/> |datetime  <br/> |行被锁定的更改时间。 这是确保，只有一个聊天服务，看看活动目录同步时间的软件互锁机制的一部分。  <br/> |
   
**密钥**

|**列**|**说明**|
|:-----|:-----|
|prinGuid  <br/> |为主键。  <br/> |
|prinGuid  <br/> |Principal.prinGuid 表中查找与外键。  <br/> |
   

