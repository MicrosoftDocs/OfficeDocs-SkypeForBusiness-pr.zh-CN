---
title: 域中的域准备所做的更改Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 9191221e-6166-4c2b-837e-fa73d90fdf80
description: 下表列出域准备在域根上创建的访问控制项 (ACE)。除非另行说明，否则所有 ACE 都是继承的。
ms.openlocfilehash: 4bf190e0b74e082cf187cde94b3a3062906f0c53
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "62389914"
---
# <a name="changes-made-by-domain-preparation-in-skype-for-business-server"></a>域中的域准备所做的更改Skype for Business Server
 
下表列出域准备在域根上创建的访问控制项 (ACE)。除非另行说明，否则所有 ACE 都是继承的。
  
**添加到域根的 ACE**

|**ACE**|**RTCUniversal-UserReadOnly-Group**|**RTCUniversal-ServerReadOnly-Group**|**RTCUniversal-UserAdmins**|**RTCHSUniversal-Services**|**Authenticated-Users**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|读取容器（非继承）  <br/> |**是** <br/> |**是** <br/> |否  <br/> |否  <br/> |否  <br/> |
|读取用户属性集 User-Account-Restrictions  <br/> |**是** <br/> |否  <br/> |否  <br/> |否  <br/> |否  <br/> |
|读取用户属性集 Personal-Information  <br/> |**是** <br/> |否  <br/> |否  <br/> |否  <br/> |否  <br/> |
|读取用户属性集 General-Information  <br/> |**是** <br/> |否  <br/> |否  <br/> |否  <br/> |否  <br/> |
|读取用户属性集 Public-Information  <br/> |**是** <br/> |否  <br/> |否  <br/> |否  <br/> |否  <br/> |
|读取用户属性集 RTCUserSearchProperty-Set  <br/> |**是** <br/> |否  <br/> |否  <br/> |否  <br/> |**是** <br/> |
|读取用户属性集 RTCPropertySet  <br/> |**是** <br/> |否  <br/> |否  <br/> |否  <br/> |否  <br/> |
|写入用户属性 Proxy-Addresses  <br/> |否  <br/> |否  <br/> |**是** <br/> |否  <br/> |否  <br/> |
|写入用户属性集 RTCUserSearchProperty-Set  <br/> |否  <br/> |否  <br/> |**是** <br/> |否  <br/> |否  <br/> |
|写入用户属性集 RTCPropertySet  <br/> |否  <br/> |否  <br/> |**是** <br/> |否  <br/> |否  <br/> |
|读取所有 Active Directory 对象的属性集 DS-Replication-Get-Changes  <br/> |否  <br/> |否  <br/> |否  <br/> |**是** <br/> |否  <br/> |
   
下表列出域准备在以下三个内置容器中创建的 ACE：用户、计算机和域控制器。 除非另行说明，否则所有 ACE 都是继承的。
**添加到内置容器的 ACE**

|**ACE**|**RTCUniversal-UserReadOnly-Group**|**RTCUniversal-ServerReadOnly-Group**|
|:-----|:-----|:-----|
|读取容器（非继承）  <br/> |**是** <br/> |**是** <br/> |
   

