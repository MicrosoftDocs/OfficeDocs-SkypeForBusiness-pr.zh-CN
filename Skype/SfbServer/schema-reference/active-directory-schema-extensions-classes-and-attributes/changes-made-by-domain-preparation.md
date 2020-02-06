---
title: Skype for Business Server 中的域准备所做的更改
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9191221e-6166-4c2b-837e-fa73d90fdf80
description: 下表列出了域准备在域根上创建的访问控制条目（Ace）。 除非另有说明，否则将继承所有 Ace。
ms.openlocfilehash: 8a087dfbbd8b670467727803f996694a816cc065
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815540"
---
# <a name="changes-made-by-domain-preparation-in-skype-for-business-server"></a>Skype for Business Server 中的域准备所做的更改
 
下表列出了域准备在域根上创建的访问控制条目（Ace）。 除非另有说明，否则将继承所有 Ace。
  
**添加到域根的 Ace**

|**棒**|**RTCUniversal-UserReadOnly**|**RTCUniversal-ServerReadOnly**|**RTCUniversal-UserAdmins**|**RTCHSUniversal-服务**|**已验证-用户**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|读取容器（不是继承的）  <br/> |**是的** <br/> |**是** <br/> |否  <br/> |否  <br/> |否  <br/> |
|阅读用户 PropertySet 用户帐户-限制  <br/> |**是** <br/> |否  <br/> |否  <br/> |否  <br/> |否  <br/> |
|阅读用户 PropertySet 个人信息  <br/> |**是** <br/> |否  <br/> |否  <br/> |否  <br/> |否  <br/> |
|阅读用户 PropertySet 常规信息  <br/> |**是** <br/> |否  <br/> |否  <br/> |否  <br/> |否  <br/> |
|读取用户 PropertySet 公共信息  <br/> |**是** <br/> |否  <br/> |否  <br/> |否  <br/> |否  <br/> |
|Read User PropertySet RTCUserSearchProperty-Set  <br/> |**是** <br/> |否  <br/> |否  <br/> |否  <br/> |**是** <br/> |
|阅读用户 PropertySet RTCPropertySet  <br/> |**是** <br/> |否  <br/> |否  <br/> |否  <br/> |否  <br/> |
|编写用户属性代理-地址  <br/> |否  <br/> |否  <br/> |**是** <br/> |否  <br/> |否  <br/> |
|编写用户 PropertySet RTCUserSearchProperty-Set  <br/> |否  <br/> |否  <br/> |**是** <br/> |否  <br/> |否  <br/> |
|编写用户 PropertySet RTCPropertySet  <br/> |否  <br/> |否  <br/> |**是** <br/> |否  <br/> |否  <br/> |
|读取 PropertySet DS-复制-对所有 Active Directory 对象的获取更改  <br/> |否  <br/> |否  <br/> |否  <br/> |**是** <br/> |否  <br/> |
   
下表列出了域准备在三个内置容器中创建的 Ace：用户、计算机和域控制器。 除非另有说明，否则将继承所有 Ace。
**添加到内置容器的 Ace**

|**棒**|**RTCUniversal-UserReadOnly**|**RTCUniversal-ServerReadOnly**|
|:-----|:-----|:-----|
|读取容器（不是继承的）  <br/> |**是的** <br/> |**是** <br/> |
   

