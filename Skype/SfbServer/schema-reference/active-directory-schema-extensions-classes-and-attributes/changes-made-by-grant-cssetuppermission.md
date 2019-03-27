---
title: 业务服务器通过在 Skype Grant-cssetuppermission 所做的更改
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c5801f48-14e3-4fdd-8f14-d52e7af07a57
description: 委派安装，您可授予权限向 RTCUniversalServerAdmins 通用组为特定 Active Directory 组织单位 (OU)，启用为业务服务器中安装 Skype 的 OU 中的 RTCUniversalServerAdmins 组的成员指定的域，而无需成为 Domain Admins 组的成员。
ms.openlocfilehash: 3976cb22a947e9a9590989895cf688465c8f5ef0
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889075"
---
# <a name="changes-made-by-grant-cssetuppermission-in-skype-for-business-server"></a>业务服务器通过在 Skype Grant-cssetuppermission 所做的更改
 
委派安装，您可授予权限向 RTCUniversalServerAdmins 通用组为特定 Active Directory 组织单位 (OU)，启用为业务服务器中安装 Skype 的 OU 中的 RTCUniversalServerAdmins 组的成员指定的域，而无需成为 Domain Admins 组的成员。 
  
**Grant-cssetuppermission** cmdlet 授予在对 OU 上，指定下表中的 RTCUniversalServerAdmins 组权限：
  
**向 OU 中的对象授予的权限**

|**权限应用于：**|**授予的权限为：**|
|:-----|:-----|
|RTCUniversalServerAdmins  <br/> | 特殊访问： <br/>  读取 servicePrincipalName <br/>  编写 servicePrincipalName <br/>  删除树 <br/>  复制目录更改 <br/> |
|后代 serviceConnectionPoint 对象  <br/> | 特殊访问： <br/>  读取权限 <br/>  写入权限 <br/>  创建子 <br/>  删除子项 <br/>  列出内容 <br/>  写入属性 <br/>  读取属性 <br/>  删除树 <br/> |
|后代 Msrtcsip-server 对象  <br/> | 特殊访问： <br/>  写入属性 <br/>  读取属性 <br/>  删除树 <br/> |
|后代 Msrtcsip-webcomponents 对象  <br/> | 特殊访问： <br/>  写入属性 <br/>  读取属性 <br/>  删除树 <br/> |
|后代 MSRTCSIP-MCU 对象  <br/> | 特殊访问： <br/>  写入属性 <br/>  读取属性 <br/>  删除树 <br/> |
|后代 Msrtcsip-mediationserver 对象  <br/> | 特殊访问： <br/>  写入属性 <br/>  读取属性 <br/>  删除树 <br/> |
|后代 Msrtcsip-applicationserver 对象  <br/> | 特殊访问： <br/>  写入属性 <br/>  读取属性 <br/>  删除树 <br/> |
|后代 Msrtcsip-connectionpoint 对象  <br/> | 特殊访问： <br/>  写入属性 <br/>  读取属性 <br/>  删除树 <br/> |
|后代计算机对象  <br/> | 对 serviceConnectionPoint 的特殊访问： <br/>  创建子对象 <br/>  删除子对象 <br/>  删除树 <br/>  对公共信息的特殊访问： <br/>  读取属性 <br/>  对 DNS 主机名的特殊访问： <br/>  读取属性 <br/> |
   

