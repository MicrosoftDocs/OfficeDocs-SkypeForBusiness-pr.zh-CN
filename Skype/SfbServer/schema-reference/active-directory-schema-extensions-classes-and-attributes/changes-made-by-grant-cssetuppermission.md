---
title: 由 Skype for Business Server 中的 "授权 CsSetupPermission" 所做的更改
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c5801f48-14e3-4fdd-8f14-d52e7af07a57
description: 若要委派设置，您可以向特定 Active Directory 组织单位（OU）的 RTCUniversalServerAdmins 通用组授予权限，从而允许该 OU 中的 RTCUniversalServerAdmins 组成员安装 Skype for Business Server指定域，而不是 "域管理员" 组的成员。
ms.openlocfilehash: 844cfa586523750b804564482146c0e76b39fc38
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815510"
---
# <a name="changes-made-by-grant-cssetuppermission-in-skype-for-business-server"></a>由 Skype for Business Server 中的 "授权 CsSetupPermission" 所做的更改
 
若要委派设置，您可以向特定 Active Directory 组织单位（OU）的 RTCUniversalServerAdmins 通用组授予权限，从而允许该 OU 中的 RTCUniversalServerAdmins 组成员安装 Skype for Business Server指定域，而不是 "域管理员" 组的成员。 
  
**CsSetupPermission** cmdlet 授予对 OU 的 RTCUniversalServerAdmins 组权限，如下表所示：
  
**在 OU 中授予对象的权限**

|**权限适用于：**|**授予的权限为：**|
|:-----|:-----|
|RTCUniversalServerAdmins  <br/> | 特殊访问： <br/>  阅读 servicePrincipalName <br/>  写入 servicePrincipalName <br/>  删除树 <br/>  复制目录更改 <br/> |
|后代 serviceConnectionPoint 对象  <br/> | 特殊访问： <br/>  读取权限 <br/>  写入权限 <br/>  创建子元素 <br/>  删除子元素 <br/>  列表内容 <br/>  Write 属性 <br/>  Read 属性 <br/>  删除树 <br/> |
|子代 msRTCSIP-服务器对象  <br/> | 特殊访问： <br/>  Write 属性 <br/>  Read 属性 <br/>  删除树 <br/> |
|子代 msRTCSIP-WebComponents 对象  <br/> | 特殊访问： <br/>  Write 属性 <br/>  Read 属性 <br/>  删除树 <br/> |
|子体 msRTCSIP-MCU 对象  <br/> | 特殊访问： <br/>  Write 属性 <br/>  Read 属性 <br/>  删除树 <br/> |
|子代 msRTCSIP-MediationServer 对象  <br/> | 特殊访问： <br/>  Write 属性 <br/>  Read 属性 <br/>  删除树 <br/> |
|子代 msRTCSIP-ApplicationServer 对象  <br/> | 特殊访问： <br/>  Write 属性 <br/>  Read 属性 <br/>  删除树 <br/> |
|子代 msRTCSIP-ConnectionPoint 对象  <br/> | 特殊访问： <br/>  Write 属性 <br/>  Read 属性 <br/>  删除树 <br/> |
|子体计算机对象  <br/> | 用于 serviceConnectionPoint 的特殊访问： <br/>  创建子对象 <br/>  删除子对象 <br/>  删除树 <br/>  公共信息的特殊访问权限： <br/>  Read 属性 <br/>  DNS 主机名的特殊访问权限： <br/>  Read 属性 <br/> |
   

