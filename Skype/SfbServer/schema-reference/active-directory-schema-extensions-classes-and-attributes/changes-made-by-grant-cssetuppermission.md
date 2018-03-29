---
title: 在 Skype 的授予 CsSetupPermission 业务服务器所做更改
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c5801f48-14e3-4fdd-8f14-d52e7af07a57
description: 若要委派安装程序，您可以授予 RTCUniversalServerAdmins 通用组对特定 Active Directory 组织单位 (OU) 的权限启用该业务服务器安装 Skype 的 OU 中 RTCUniversalServerAdmins 组的成员指定的域不是域管理员组的成员。
ms.openlocfilehash: 6c87ad11e0c125f2a58f2518218060b2a3636f0e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="changes-made-by-grant-cssetuppermission-in-skype-for-business-server"></a>在 Skype 的授予 CsSetupPermission 业务服务器所做更改
 
若要委派安装程序，您可以授予 RTCUniversalServerAdmins 通用组对特定 Active Directory 组织单位 (OU) 的权限启用该业务服务器安装 Skype 的 OU 中 RTCUniversalServerAdmins 组的成员指定的域不是域管理员组的成员。 
  
**授予 CsSetupPermission** cmdlet 将授予 OU，请按照下表中指定的 RTCUniversalServerAdmins 组权限：
  
**授予对该 OU 中的对象的权限**

|**权限将应用于：**|**授予的权限是：**|
|:-----|:-----|
|RTCUniversalServerAdmins  <br/> | 特殊访问权限： <br/>  读 servicePrincipalName <br/>  写 servicePrincipalName <br/>  删除目录树 <br/>  复制目录更改 <br/> |
|子代的 serviceConnectionPoint 对象  <br/> | 特殊访问权限： <br/>  读取权限 <br/>  写入权限 <br/>  创建子 <br/>  删除子 <br/>  列表内容 <br/>  写入属性 <br/>  读取属性 <br/>  删除目录树 <br/> |
|子代的 msRTCSIP 服务器对象  <br/> | 特殊访问权限： <br/>  写入属性 <br/>  读取属性 <br/>  删除目录树 <br/> |
|子代的 msRTCSIP WebComponents 对象  <br/> | 特殊访问权限： <br/>  写入属性 <br/>  读取属性 <br/>  删除目录树 <br/> |
|子代的 msRTCSIP MCU 对象  <br/> | 特殊访问权限： <br/>  写入属性 <br/>  读取属性 <br/>  删除目录树 <br/> |
|子代的 msRTCSIP MediationServer 对象  <br/> | 特殊访问权限： <br/>  写入属性 <br/>  读取属性 <br/>  删除目录树 <br/> |
|子代的 msRTCSIP 应用程序服务器对象  <br/> | 特殊访问权限： <br/>  写入属性 <br/>  读取属性 <br/>  删除目录树 <br/> |
|子代的 msRTCSIP 连接点对象  <br/> | 特殊访问权限： <br/>  写入属性 <br/>  读取属性 <br/>  删除目录树 <br/> |
|子代的计算机对象  <br/> | ServiceConnectionPoint 的特殊访问权限： <br/>  创建子对象 <br/>  删除子对象 <br/>  删除目录树 <br/>  公共信息的特殊访问权限： <br/>  读取属性 <br/>  对于 DNS 主机名称的特殊访问权限： <br/>  读取属性 <br/> |
   

