---
title: 通过在 Skype 业务服务器的域准备工作所做的更改
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9191221e-6166-4c2b-837e-fa73d90fdf80
description: 下表列出了域准备工作将在域根目录创建访问控制项 (Ace)。 除非另有说明，否则所有 Ace 都继承。
ms.openlocfilehash: 3602e04082dbf4af9a2ab40fc3318761ebc08c21
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="changes-made-by-domain-preparation-in-skype-for-business-server"></a>通过在 Skype 业务服务器的域准备工作所做的更改
 
下表列出了域准备工作将在域根目录创建访问控制项 (Ace)。 除非另有说明，否则所有 Ace 都继承。
  
**添加到域根的 Ace**

|**ACE**|**RTCUniversal UserReadOnly 组**|**RTCUniversal ServerReadOnly 组**|**RTCUniversal UserAdmins**|**RTCHSUniversal 服务**|**经过身份验证的用户**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|读取 （不继承） 的容器  <br/> |**是的** <br/> |**是的** <br/> |否  <br/> |否  <br/> |否  <br/> |
|读取用户 PropertySet 用户帐户限制  <br/> |**是的** <br/> |否  <br/> |否  <br/> |否  <br/> |否  <br/> |
|读取用户 PropertySet 个人信息  <br/> |**是的** <br/> |否  <br/> |否  <br/> |否  <br/> |否  <br/> |
|读取用户 PropertySet 常规信息  <br/> |**是的** <br/> |否  <br/> |否  <br/> |否  <br/> |否  <br/> |
|读取用户 PropertySet 公共信息  <br/> |**是的** <br/> |否  <br/> |否  <br/> |否  <br/> |否  <br/> |
|读取用户 PropertySet RTCUserSearchProperty 集  <br/> |**是的** <br/> |否  <br/> |否  <br/> |否  <br/> |**是的** <br/> |
|读取用户 PropertySet RTCPropertySet  <br/> |**是的** <br/> |否  <br/> |否  <br/> |否  <br/> |否  <br/> |
|编写用户属性代理服务器地址  <br/> |否  <br/> |否  <br/> |**是的** <br/> |否  <br/> |否  <br/> |
|编写用户 PropertySet RTCUserSearchProperty 组  <br/> |否  <br/> |否  <br/> |**是的** <br/> |否  <br/> |否  <br/> |
|编写用户 PropertySet RTCPropertySet  <br/> |否  <br/> |否  <br/> |**是的** <br/> |否  <br/> |否  <br/> |
|读 PropertySet DS-复制-获取-更改所有 Active Directory 对象的  <br/> |否  <br/> |否  <br/> |否  <br/> |**是的** <br/> |否  <br/> |
   
下表列出了域准备工作将在三个内置容器中创建的 Ace： 用户、 计算机和域控制器。 除非另有说明，否则所有 Ace 都继承。
**添加到内置容器的 Ace**

|**ACE**|**RTCUniversal UserReadOnly 组**|**RTCUniversal ServerReadOnly 组**|
|:-----|:-----|:-----|
|读取 （不继承） 的容器  <br/> |**是的** <br/> |**是的** <br/> |
   

