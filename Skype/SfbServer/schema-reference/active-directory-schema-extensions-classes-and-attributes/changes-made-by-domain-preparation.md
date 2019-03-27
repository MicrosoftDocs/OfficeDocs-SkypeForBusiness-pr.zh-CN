---
title: Skype 中的业务服务器的域准备所做的更改
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9191221e-6166-4c2b-837e-fa73d90fdf80
description: 下表列出域准备在域根创建访问控制项 (Ace)。 除非另行说明，所有 Ace 都被都继承。
ms.openlocfilehash: 5cf239e37badafee9980140d08fd20a11e3c233d
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30877697"
---
# <a name="changes-made-by-domain-preparation-in-skype-for-business-server"></a>Skype 中的业务服务器的域准备所做的更改
 
下表列出域准备在域根创建访问控制项 (Ace)。 除非另行说明，所有 Ace 都被都继承。
  
**添加到域根的 Ace**

|**ACE**|**RTCUniversal UserReadOnly 组**|**RTCUniversal ServerReadOnly 组**|**RTCUniversal UserAdmins**|**RTCHSUniversal 服务**|**验证用户**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|读取容器 （非继承）  <br/> |**是的** <br/> |**是的** <br/> |否  <br/> |否  <br/> |否  <br/> |
|读取用户属性集的用户帐户限制  <br/> |**是的** <br/> |否  <br/> |否  <br/> |否  <br/> |否  <br/> |
|读取用户属性集 Personal-information  <br/> |**是的** <br/> |否  <br/> |否  <br/> |否  <br/> |否  <br/> |
|读取用户属性集 General-information  <br/> |**是的** <br/> |否  <br/> |否  <br/> |否  <br/> |否  <br/> |
|读取用户属性集 Public-information  <br/> |**是的** <br/> |否  <br/> |否  <br/> |否  <br/> |否  <br/> |
|读取用户属性集 Rtcusersearchproperty-set  <br/> |**是的** <br/> |否  <br/> |否  <br/> |否  <br/> |**是** <br/> |
|读取用户属性集 RTCPropertySet  <br/> |**是的** <br/> |否  <br/> |否  <br/> |否  <br/> |否  <br/> |
|写入用户属性 Proxy-addresses  <br/> |否  <br/> |否  <br/> |**是的** <br/> |否  <br/> |否  <br/> |
|写入用户属性集 Rtcusersearchproperty-set  <br/> |否  <br/> |否  <br/> |**是的** <br/> |否  <br/> |否  <br/> |
|写入用户属性集 RTCPropertySet  <br/> |否  <br/> |否  <br/> |**是的** <br/> |否  <br/> |否  <br/> |
|读取属性集 DS-复制-Get-更改的所有 Active Directory 对象  <br/> |否  <br/> |否  <br/> |否  <br/> |**是的** <br/> |否  <br/> |
   
下表列出域准备在三个内置容器中创建的 Ace： 用户、 计算机和域控制器。 除非另行说明，所有 Ace 都被都继承。
**添加到内置容器的 Ace**

|**ACE**|**RTCUniversal UserReadOnly 组**|**RTCUniversal ServerReadOnly 组**|
|:-----|:-----|:-----|
|读取容器 （非继承）  <br/> |**是的** <br/> |**是** <br/> |
   

