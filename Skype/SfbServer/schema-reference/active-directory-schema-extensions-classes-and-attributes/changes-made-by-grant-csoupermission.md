---
title: Grant-csoupermission Skype 中通过 Business 服务器所做的更改
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d744d352-1ad9-4447-8e2b-28e768d2ed1b
description: 若要委派 Skype 业务服务器管理，可以添加权限到指定组织单位 (Ou)，以便林准备创建 RTC 通用组的成员可以访问 Ou，而无需成为 Domain Admins 组的成员。
ms.openlocfilehash: 304f5d905f8839224013a2ce674b98405fd9ce8e
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213702"
---
# <a name="changes-made-by-grant-csoupermission-in-skype-for-business-server"></a>Grant-csoupermission Skype 中通过 Business 服务器所做的更改
 
若要委派 Skype 业务服务器管理，可以添加权限到指定组织单位 (Ou)，以便林准备创建 RTC 通用组的成员可以访问 Ou，而无需成为 Domain Admins 组的成员。 
  
**Grant-csoupermission** cmdlet 授予给指定下表中指定的 OU 中的对象的权限。
  
## <a name="granting-permission-for-user-objects"></a>为用户对象授予权限

在对 OU 上运行的用户对象**Grant-csoupermission** cmdlet 时，会组授予如下表所示的权限。
  
**为用户对象授予的权限**

|**组**|**权限**|**适用于**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |复制目录更改  <br/> |只是这个对象  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |列出内容  <br/> 读取所有属性  <br/> 读取权限  <br/> |只是这个对象  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |列出内容  <br/> 读取所有属性  <br/> 读取权限  <br/> |只是这个对象  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |读取 RTCUserSearchPropertySet  <br/> 读取 RTCUserProvisioningPropertySet  <br/> 读取 RTCPropertySet  <br/> 读取 Public-information  <br/> 读取 General-information  <br/> 读取用户帐户限制  <br/> |后代用户对象  <br/> |
|RTCUniversalUserAdmins  <br/> |写入 RTCUserSearchPropertySet  <br/> 写入 msExchUCVoiceMailSettings  <br/> 写入 RTCUserProvisioningPropertySet  <br/> 写入 RTCPropertySet  <br/> 写入 proxyAddresses  <br/> |后代用户对象  <br/> |
   
## <a name="granting-permission-for-computer-objects"></a>为计算机对象授予权限

在对 OU 上运行**Grant-csoupermission** cmdlet 为计算机对象时，会组授予权限下, 表中所示。
  
**为计算机对象授予的权限**

|**组**|**权限**|**适用于**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |复制目录更改  <br/> |只是这个对象  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |列出内容  <br/> 读取所有属性  <br/> 读取权限  <br/> |只是这个对象  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |列出内容  <br/> 读取所有属性  <br/> 读取权限  <br/> |只是这个对象  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |读取 Public-information  <br/> 读取验证 DNS 主机名  <br/> |后代计算机对象  <br/> |
|RTCUniversalUserAdmins  <br/> |读取 Public-information  <br/> 读取验证 DNS 主机名  <br/> |后代计算机对象  <br/> |
   
## <a name="granting-permission-for-contact-or-appcontact-objects"></a>为联系人或 AppContact 对象授予权限

在对 OU 上运行的联系人或 AppContact 对象**Grant-csoupermission** cmdlet 时，会为组授予的权限下表中所示。
  
**为联系人或 AppContact 对象授予的权限**

|**组**|**权限**|**适用于**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |复制目录更改  <br/> |只是这个对象  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |列出内容  <br/> 读取所有属性  <br/> 读取权限  <br/> |只是这个对象  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |列出内容  <br/> 读取所有属性  <br/> 读取权限  <br/> |只是这个对象  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |读取 RTCUserSearchPropertySet  <br/> 读取 RTCUserProvisioningPropertySet  <br/> 读取 RTCPropertySet  <br/> 读取 Public-information  <br/> 读取 General-information  <br/> 读取 Personal-information  <br/> 读取用户帐户限制  <br/> |后代联系人对象  <br/> |
|RTCUniversalUserAdmins  <br/> |写入 RTCUserSearchPropertySet  <br/> 写入 otherIpPhone  <br/> 写入 displayName  <br/> 写入 description  <br/> 写入 telephoneNumber  <br/> 写入 msExchUCVoiceMailSettings  <br/> 写入 RTCUserProvisioningPropertySet  <br/> 写入 RTCPropertySet  <br/> 写入 proxyAddresses  <br/> |后代联系人对象  <br/> |
   
## <a name="granting-permission-for-device-objects"></a>为设备对象授予权限

在对 OU 上运行**Grant-csoupermission** cmdlet 为设备对象时，会组授予如下表所示的权限。
  
**为设备对象授予的权限**

|**组**|**权限**|**适用于**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |复制目录更改  <br/> |只是这个对象  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |列出内容  <br/> 读取所有属性  <br/> 读取权限  <br/> |只是这个对象  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |列出内容  <br/> 读取所有属性  <br/> 读取权限  <br/> |只是这个对象  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |读取 RTCUserSearchPropertySet  <br/> 读取 RTCUserProvisioningPropertySet  <br/> 读取 RTCPropertySet  <br/> 读取 Public-information  <br/> 读取 Personal-information  <br/> 读取 General-information  <br/> 读取用户帐户限制  <br/> |后代联系人对象  <br/> |
|RTCUniversalUserAdmins  <br/> |创建子  <br/> 删除子项  <br/> 删除树  <br/> |联系人  <br/> |
|RTCUniversalUserAdmins  <br/> |写入 displayName  <br/> 写入 description  <br/> 写入 telephoneNumber  <br/> |后代用户对象  <br/> |
|RTCUniversalUserAdmins  <br/> |写入 RTCUserSearchPropertySet  <br/> 写入 otherIpPhone  <br/> 写入 displayName  <br/> 写入 description  <br/> 写入 telephoneNumber  <br/> 写入 msExchUCVoiceMailSettings  <br/> 写入 RTCUserProvisioningPropertySet  <br/> 写入 RTCPropertySet  <br/> 写入 proxyAddresses  <br/> |后代联系人对象  <br/> |
   
## <a name="granting-permission-for-inetorgperson-objects"></a>为 InetOrgPerson 对象授予权限

在对 OU 上运行**Grant-csoupermission** cmdlet 为 InetOrgPerson 对象时，会组授予如下表所示的权限。
  
**为 InetOrgPerson 对象授予的权限**

|**组**|**权限**|**适用于**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |复制目录更改  <br/> |只是这个对象  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |列出内容  <br/> 读取所有属性  <br/> 读取权限  <br/> |只是这个对象  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |列出内容  <br/> 读取所有属性  <br/> 读取权限  <br/> |只是这个对象  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |读取 RTCUserSearchPropertySet  <br/> 读取 RTCUserProvisioningPropertySet  <br/> 读取 RTCPropertySet  <br/> 读取 Personal-information  <br/> 读取 Public-information  <br/> 读取 General-information  <br/> 读取用户帐户限制  <br/> |后代 inetOrgPerson 对象  <br/> |
|RTCUniversalUserAdmins  <br/> |写入 RTCUserSearchPropertySet  <br/> 写入 RTCUserProvisioningPropertySet  <br/> 写入 RTCPropertySet  <br/> 写入 proxyAddresses  <br/> |后代 inetOrgPerson 对象  <br/> |
   

