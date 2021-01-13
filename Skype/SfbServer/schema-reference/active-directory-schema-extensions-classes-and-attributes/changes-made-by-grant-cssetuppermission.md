---
title: Skype for Business Server Grant-CsSetupPermission所做的更改
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
ms.assetid: c5801f48-14e3-4fdd-8f14-d52e7af07a57
description: 若要委派安装程序，您可以授予特定 Active Directory 组织单位 (OU) 的 RTCUniversalServerAdmins 通用组的权限，从而使该 OU 中的 RTCUniversalServerAdmins 组的成员无需是 Domain Admins 组的成员即可在指定的域中安装 Skype for Business Server。
ms.openlocfilehash: 3f6de30e7068f9f44ca6d958f8ca30af866b536a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831832"
---
# <a name="changes-made-by-grant-cssetuppermission-in-skype-for-business-server"></a>Skype for Business Server Grant-CsSetupPermission所做的更改
 
若要委派安装程序，您可以授予特定 Active Directory 组织单位 (OU) 的 RTCUniversalServerAdmins 通用组的权限，从而使该 OU 中的 RTCUniversalServerAdmins 组的成员无需是 Domain Admins 组的成员即可在指定的域中安装 Skype for Business Server。 
  
**Grant-CsSetupPermission** cmdlet 向 OU 授予 RTCUniversalServerAdmins 组权限，如下表中所述：
  
**向 OU 中的对象授予的权限**

|**权限适用于：**|**授予的权限为：**|
|:-----|:-----|
|RTCUniversalServerAdmins  <br/> | 特殊访问： <br/>  读取 servicePrincipalName <br/>  写入 servicePrincipalName <br/>  删除树 <br/>  复制目录更改 <br/> |
|后代 serviceConnectionPoint 对象  <br/> | 特殊访问： <br/>  读取权限 <br/>  写入权限 <br/>  创建子级 <br/>  删除子级 <br/>  列出内容 <br/>  写入属性 <br/>  读取属性 <br/>  删除树 <br/> |
|后代 msRTCSIP-Server 对象  <br/> | 特殊访问： <br/>  写入属性 <br/>  读取属性 <br/>  删除树 <br/> |
|后代 msRTCSIP-WebComponents 对象  <br/> | 特殊访问： <br/>  写入属性 <br/>  读取属性 <br/>  删除树 <br/> |
|后代 msRTCSIP-MCU 对象  <br/> | 特殊访问： <br/>  写入属性 <br/>  读取属性 <br/>  删除树 <br/> |
|后代 msRTCSIP-MediationServer 对象  <br/> | 特殊访问： <br/>  写入属性 <br/>  读取属性 <br/>  删除树 <br/> |
|后代 msRTCSIP-ApplicationServer 对象  <br/> | 特殊访问： <br/>  写入属性 <br/>  读取属性 <br/>  删除树 <br/> |
|后代 msRTCSIP-ConnectionPoint 对象  <br/> | 特殊访问： <br/>  写入属性 <br/>  读取属性 <br/>  删除树 <br/> |
|后代计算机对象  <br/> | 对 serviceConnectionPoint 的特殊访问： <br/>  创建子对象 <br/>  删除子对象 <br/>  删除树 <br/>  对公共信息的特殊访问： <br/>  读取属性 <br/>  对 DNS 主机名的特殊访问： <br/>  读取属性 <br/> |
   

