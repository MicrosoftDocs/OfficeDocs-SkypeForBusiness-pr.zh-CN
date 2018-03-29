---
title: 在 Skype 的授予 CsOUPermission 业务服务器所做更改
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d744d352-1ad9-4447-8e2b-28e768d2ed1b
description: 若要委派 Skype 业务服务器管理，可以添加权限到指定的组织单位 (Ou)，以便创建林准备过程的 RTC 通用组的成员可以访问 Ou 不是域管理员组的成员。
ms.openlocfilehash: 1313394248da2dcaeb9843bd689b2e2da3c51f96
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="changes-made-by-grant-csoupermission-in-skype-for-business-server"></a>在 Skype 的授予 CsOUPermission 业务服务器所做更改
 
若要委派 Skype 业务服务器管理，可以添加权限到指定的组织单位 (Ou)，以便创建林准备过程的 RTC 通用组的成员可以访问 Ou 不是域管理员组的成员。 
  
**授予 CsOuPermission** cmdlet 授予指定下表中指定的 OU 中的对象的权限。
  
## <a name="granting-permission-for-user-objects"></a>授予用户对象的权限

OU 上运行**授予 CsOuPermission** cmdlet 的用户对象时，组的权限如下表所示。
  
**授予用户对象的权限**

|**组**|**权限**|**适用于**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |复制目录更改  <br/> |只是这个对象  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |列表内容  <br/> 读取所有属性  <br/> 读取权限  <br/> |只是这个对象  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |列表内容  <br/> 读取所有属性  <br/> 读取权限  <br/> |只是这个对象  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |阅读 RTCUserSearchPropertySet  <br/> 阅读 RTCUserProvisioningPropertySet  <br/> 阅读 RTCPropertySet  <br/> 阅读公共信息  <br/> 阅读常规信息  <br/> 读取用户帐户限制  <br/> |子代的用户对象  <br/> |
|RTCUniversalUserAdmins  <br/> |写 RTCUserSearchPropertySet  <br/> 写 msExchUCVoiceMailSettings  <br/> 写 RTCUserProvisioningPropertySet  <br/> 写 RTCPropertySet  <br/> 写入代理地址  <br/> |子代的用户对象  <br/> |
   
## <a name="granting-permission-for-computer-objects"></a>授予对计算机对象的权限

运行时**授予 CsOuPermission** cmdlet 的计算机对象的 OU 上，组授予权限，如下表所示。
  
**授予对计算机对象权限**

|**组**|**权限**|**适用于**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |复制目录更改  <br/> |只是这个对象  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |列表内容  <br/> 读取所有属性  <br/> 读取权限  <br/> |只是这个对象  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |列表内容  <br/> 读取所有属性  <br/> 读取权限  <br/> |只是这个对象  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |阅读公共信息  <br/> 阅读验证 DNS 主机名  <br/> |子代的计算机对象  <br/> |
|RTCUniversalUserAdmins  <br/> |阅读公共信息  <br/> 阅读验证 DNS 主机名  <br/> |子代的计算机对象  <br/> |
   
## <a name="granting-permission-for-contact-or-appcontact-objects"></a>为联系人或 AppContact 对象授予权限

在 OU 上运行**授予 CsOuPermission** cmdlet 的联系人对象或 AppContact 对象时，组被授予权限，如下表中所示。
  
**为联系人或 AppContact 对象授予权限**

|**组**|**权限**|**适用于**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |复制目录更改  <br/> |只是这个对象  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |列表内容  <br/> 读取所有属性  <br/> 读取权限  <br/> |只是这个对象  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |列表内容  <br/> 读取所有属性  <br/> 读取权限  <br/> |只是这个对象  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |阅读 RTCUserSearchPropertySet  <br/> 阅读 RTCUserProvisioningPropertySet  <br/> 阅读 RTCPropertySet  <br/> 阅读公共信息  <br/> 阅读常规信息  <br/> 阅读个人信息  <br/> 读取用户帐户限制  <br/> |子代的联系人对象  <br/> |
|RTCUniversalUserAdmins  <br/> |写 RTCUserSearchPropertySet  <br/> 写 otherIpPhone  <br/> 写显示名称  <br/> 编写的说明  <br/> 写 telephoneNumber  <br/> 写 msExchUCVoiceMailSettings  <br/> 写 RTCUserProvisioningPropertySet  <br/> 写 RTCPropertySet  <br/> 写入代理地址  <br/> |子代的联系人对象  <br/> |
   
## <a name="granting-permission-for-device-objects"></a>设备对象授予权限

当您在 OU 上运行**授予 CsOuPermission** cmdlet 的设备对象时，组被授予权限如下表中所示。
  
**设备对象授予权限**

|**组**|**权限**|**适用于**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |复制目录更改  <br/> |只是这个对象  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |列表内容  <br/> 读取所有属性  <br/> 读取权限  <br/> |只是这个对象  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |列表内容  <br/> 读取所有属性  <br/> 读取权限  <br/> |只是这个对象  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |阅读 RTCUserSearchPropertySet  <br/> 阅读 RTCUserProvisioningPropertySet  <br/> 阅读 RTCPropertySet  <br/> 阅读公共信息  <br/> 阅读个人信息  <br/> 阅读常规信息  <br/> 读取用户帐户限制  <br/> |子代的联系人对象  <br/> |
|RTCUniversalUserAdmins  <br/> |创建子  <br/> 删除子  <br/> 删除目录树  <br/> |联系人  <br/> |
|RTCUniversalUserAdmins  <br/> |写显示名称  <br/> 编写的说明  <br/> 写 telephoneNumber  <br/> |子代的用户对象  <br/> |
|RTCUniversalUserAdmins  <br/> |写 RTCUserSearchPropertySet  <br/> 写 otherIpPhone  <br/> 写显示名称  <br/> 编写的说明  <br/> 写 telephoneNumber  <br/> 写 msExchUCVoiceMailSettings  <br/> 写 RTCUserProvisioningPropertySet  <br/> 写 RTCPropertySet  <br/> 写入代理地址  <br/> |子代的联系人对象  <br/> |
   
## <a name="granting-permission-for-inetorgperson-objects"></a>对于 InetOrgPerson 对象授予权限

OU 上运行**授予 CsOuPermission** cmdlet InetOrgPerson 对象时，组的权限如下表所示。
  
**对于 InetOrgPerson 对象授予权限**

|**组**|**权限**|**适用于**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |复制目录更改  <br/> |只是这个对象  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |列表内容  <br/> 读取所有属性  <br/> 读取权限  <br/> |只是这个对象  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |列表内容  <br/> 读取所有属性  <br/> 读取权限  <br/> |只是这个对象  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |阅读 RTCUserSearchPropertySet  <br/> 阅读 RTCUserProvisioningPropertySet  <br/> 阅读 RTCPropertySet  <br/> 阅读个人信息  <br/> 阅读公共信息  <br/> 阅读常规信息  <br/> 读取用户帐户限制  <br/> |子代 inetOrgPerson 对象  <br/> |
|RTCUniversalUserAdmins  <br/> |写 RTCUserSearchPropertySet  <br/> 写 RTCUserProvisioningPropertySet  <br/> 写 RTCPropertySet  <br/> 写入代理地址  <br/> |子代 inetOrgPerson 对象  <br/> |
   

