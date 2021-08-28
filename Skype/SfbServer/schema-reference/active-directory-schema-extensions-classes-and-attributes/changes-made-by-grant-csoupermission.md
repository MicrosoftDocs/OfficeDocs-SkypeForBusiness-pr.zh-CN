---
title: 由Grant-CsOUPermission所做的更改Skype for Business Server
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
ms.localizationpriority: medium
ms.assetid: d744d352-1ad9-4447-8e2b-28e768d2ed1b
description: 若要Skype for Business Server管理，您可以向指定的组织单位 (OUS) 添加权限，以便林准备创建的 RTC 通用组的成员无需是 Domain Admins 组的成员即可访问这些 US。
ms.openlocfilehash: f700b03f95be05e00d4e5eb032d9dd50ceb1352b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58613902"
---
# <a name="changes-made-by-grant-csoupermission-in-skype-for-business-server"></a>由Grant-CsOUPermission所做的更改Skype for Business Server
 
若要Skype for Business Server管理，您可以向指定的组织单位 (OUS) 添加权限，以便林准备创建的 RTC 通用组的成员无需是 Domain Admins 组的成员即可访问这些 US。 
  
**Grant-CsOuPermission** cmdlet 向指定 OU 中的对象授予权限，如下表所示。
  
## <a name="granting-permission-for-user-objects"></a>为用户对象授予权限

在对 OU 上的用户对象运行 **Grant-CsOuPermission** cmdlet 时，会为组授予如下表所示的权限。
  
**为用户对象授予的权限**

|**Group**|**权限**|**适用对象**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |复制目录更改  <br/> |仅限此对象  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |列出内容  <br/> 读取所有属性  <br/> 读取权限  <br/> |仅限此对象  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |列出内容  <br/> 读取所有属性  <br/> 读取权限  <br/> |仅限此对象  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |读取 RTCUserSearchPropertySet  <br/> 读取 RTCUserProvisioningPropertySet  <br/> 读取 RTCPropertySet  <br/> 读取 Public-Information  <br/> 读取 General-Information  <br/> 读取 User-Account-Restrictions  <br/> |后代用户对象  <br/> |
|RTCUniversalUserAdmins  <br/> |写入 RTCUserSearchPropertySet  <br/> 写入 msExchUCVoiceMailSettings  <br/> 写入 RTCUserProvisioningPropertySet  <br/> 写入 RTCPropertySet  <br/> 写入 proxyAddresses  <br/> |后代用户对象  <br/> |
   
## <a name="granting-permission-for-computer-objects"></a>为计算机对象授予权限

在对 OU 上的计算机对象运行 **Grant-CsOuPermission** cmdlet 时，会为组授予如下表所示的权限。
  
**为计算机对象授予的权限**

|**Group**|**权限**|**适用对象**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |复制目录更改  <br/> |仅限此对象  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |列出内容  <br/> 读取所有属性  <br/> 读取权限  <br/> |仅限此对象  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |列出内容  <br/> 读取所有属性  <br/> 读取权限  <br/> |仅限此对象  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |读取 Public-Information  <br/> 读取 Validated-DNS-Host-Name  <br/> |后代计算机对象  <br/> |
|RTCUniversalUserAdmins  <br/> |读取 Public-Information  <br/> 读取 Validated-DNS-Host-Name  <br/> |后代计算机对象  <br/> |
   
## <a name="granting-permission-for-contact-or-appcontact-objects"></a>为联系人或 AppContact 对象授予权限

在对 OU 上的联系人或 AppContact 对象运行 **Grant-CsOuPermission** cmdlet 时，会为组授予如下表所示的权限。
  
**为联系人对象或 AppContact 对象授予的权限**

|**Group**|**权限**|**适用对象**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |复制目录更改  <br/> |仅限此对象  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |列出内容  <br/> 读取所有属性  <br/> 读取权限  <br/> |仅限此对象  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |列出内容  <br/> 读取所有属性  <br/> 读取权限  <br/> |仅限此对象  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |读取 RTCUserSearchPropertySet  <br/> 读取 RTCUserProvisioningPropertySet  <br/> 读取 RTCPropertySet  <br/> 读取 Public-Information  <br/> 读取 General-Information  <br/> 读取 Personal-Information  <br/> 读取 User-Account-Restrictions  <br/> |后代联系人对象  <br/> |
|RTCUniversalUserAdmins  <br/> |写入 RTCUserSearchPropertySet  <br/> 写入 otherIpPhone  <br/> 写入 displayName  <br/> 写入 description  <br/> 写入 telephoneNumber  <br/> 写入 msExchUCVoiceMailSettings  <br/> 写入 RTCUserProvisioningPropertySet  <br/> 写入 RTCPropertySet  <br/> 写入 proxyAddresses  <br/> |后代联系人对象  <br/> |
   
## <a name="granting-permission-for-device-objects"></a>为设备对象授予权限

在对 OU 上的设备对象运行 **Grant-CsOuPermission** cmdlet 时，会为组授予如下表所示的权限。
  
**为设备对象授予的权限**

|**Group**|**权限**|**适用对象**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |复制目录更改  <br/> |仅限此对象  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |列出内容  <br/> 读取所有属性  <br/> 读取权限  <br/> |仅限此对象  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |列出内容  <br/> 读取所有属性  <br/> 读取权限  <br/> |仅限此对象  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |读取 RTCUserSearchPropertySet  <br/> 读取 RTCUserProvisioningPropertySet  <br/> 读取 RTCPropertySet  <br/> 读取 Public-Information  <br/> 读取 Personal-Information  <br/> 读取 General-Information  <br/> 读取 User-Account-Restrictions  <br/> |后代联系人对象  <br/> |
|RTCUniversalUserAdmins  <br/> |创建子级  <br/> 删除子级  <br/> 删除树  <br/> |联系人  <br/> |
|RTCUniversalUserAdmins  <br/> |写入 displayName  <br/> 写入 description  <br/> 写入 telephoneNumber  <br/> |后代用户对象  <br/> |
|RTCUniversalUserAdmins  <br/> |写入 RTCUserSearchPropertySet  <br/> 写入 otherIpPhone  <br/> 写入 displayName  <br/> 写入 description  <br/> 写入 telephoneNumber  <br/> 写入 msExchUCVoiceMailSettings  <br/> 写入 RTCUserProvisioningPropertySet  <br/> 写入 RTCPropertySet  <br/> 写入 proxyAddresses  <br/> |后代联系人对象  <br/> |
   
## <a name="granting-permission-for-inetorgperson-objects"></a>为 InetOrgPerson 对象授予权限

在对 OU 上的 InetOrgPerson 对象运行 **Grant-CsOuPermission** cmdlet 时，会为组授予如下表所示的权限。
  
**为 InetOrgPerson 对象授予的权限**

|**Group**|**权限**|**适用对象**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |复制目录更改  <br/> |仅限此对象  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |列出内容  <br/> 读取所有属性  <br/> 读取权限  <br/> |仅限此对象  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |列出内容  <br/> 读取所有属性  <br/> 读取权限  <br/> |仅限此对象  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |读取 RTCUserSearchPropertySet  <br/> 读取 RTCUserProvisioningPropertySet  <br/> 读取 RTCPropertySet  <br/> 读取 Personal-Information  <br/> 读取 Public-Information  <br/> 读取 General-Information  <br/> 读取 User-Account-Restrictions  <br/> |后代 InetOrgPerson 对象  <br/> |
|RTCUniversalUserAdmins  <br/> |写入 RTCUserSearchPropertySet  <br/> 写入 RTCUserProvisioningPropertySet  <br/> 写入 RTCPropertySet  <br/> 写入 proxyAddresses  <br/> |后代 InetOrgPerson 对象  <br/> |
   

