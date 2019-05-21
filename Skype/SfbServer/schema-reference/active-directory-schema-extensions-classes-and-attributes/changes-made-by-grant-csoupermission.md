---
title: 由 Skype for Business Server 中的 "授权 CsOUPermission" 所做的更改
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d744d352-1ad9-4447-8e2b-28e768d2ed1b
description: 要委派 Skype for Business 服务器管理, 您可以向指定的组织单位 (Ou) 添加权限, 以便林准备创建的 RTC 通用组的成员无需成为域管理员组的成员即可访问 Ou。
ms.openlocfilehash: 48c5921cabf2b1bc8100f796d3e3b7f6a247ff0c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296691"
---
# <a name="changes-made-by-grant-csoupermission-in-skype-for-business-server"></a>由 Skype for Business Server 中的 "授权 CsOUPermission" 所做的更改
 
要委派 Skype for Business 服务器管理, 您可以向指定的组织单位 (Ou) 添加权限, 以便林准备创建的 RTC 通用组的成员无需成为域管理员组的成员即可访问 Ou。 
  
**CsOuPermission** cmdlet 按下表中指定的方式向指定 OU 中的对象授予权限。
  
## <a name="granting-permission-for-user-objects"></a>为用户对象授予权限

在 OU 上运行用户对象的**CsOuPermission** cmdlet 时, 将向组授予下表中所示的权限。
  
**为用户对象授予的权限**

|**团队**|**权限**|**适用于**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |复制目录更改  <br/> |仅此对象  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |列表内容  <br/> 读取所有属性  <br/> 读取权限  <br/> |仅此对象  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |列表内容  <br/> 读取所有属性  <br/> 读取权限  <br/> |仅此对象  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |阅读 RTCUserSearchPropertySet  <br/> 阅读 RTCUserProvisioningPropertySet  <br/> 阅读 RTCPropertySet  <br/> 阅读公共信息  <br/> 阅读常规信息  <br/> 阅读用户-帐户限制  <br/> |子代用户对象  <br/> |
|RTCUniversalUserAdmins  <br/> |写 RTCUserSearchPropertySet  <br/> 写 msExchUCVoiceMailSettings  <br/> 写 RTCUserProvisioningPropertySet  <br/> 写 RTCPropertySet  <br/> 写 proxyAddresses  <br/> |子代用户对象  <br/> |
   
## <a name="granting-permission-for-computer-objects"></a>为计算机对象授予权限

在 OU 上运行计算机对象的**CsOuPermission** cmdlet 时, 将向组授予下表中所示的权限。
  
**为计算机对象授予的权限**

|**团队**|**权限**|**适用于**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |复制目录更改  <br/> |仅此对象  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |列表内容  <br/> 读取所有属性  <br/> 读取权限  <br/> |仅此对象  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |列表内容  <br/> 读取所有属性  <br/> 读取权限  <br/> |仅此对象  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |阅读公共信息  <br/> 读取已验证的 DNS 主机名  <br/> |子体计算机对象  <br/> |
|RTCUniversalUserAdmins  <br/> |阅读公共信息  <br/> 读取已验证的 DNS 主机名  <br/> |子体计算机对象  <br/> |
   
## <a name="granting-permission-for-contact-or-appcontact-objects"></a>授予联系人或 AppContact 对象的权限

当你为某个 OU 上的 Contact 对象或 AppContact 对象运行**CsOuPermission** cmdlet 时, 将向组授予下表中所示的权限。
  
**为联系人或 AppContact 对象授予的权限**

|**团队**|**权限**|**适用于**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |复制目录更改  <br/> |仅此对象  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |列表内容  <br/> 读取所有属性  <br/> 读取权限  <br/> |仅此对象  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |列表内容  <br/> 读取所有属性  <br/> 读取权限  <br/> |仅此对象  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |阅读 RTCUserSearchPropertySet  <br/> 阅读 RTCUserProvisioningPropertySet  <br/> 阅读 RTCPropertySet  <br/> 阅读公共信息  <br/> 阅读常规信息  <br/> 阅读个人信息  <br/> 阅读用户-帐户限制  <br/> |子代联系人对象  <br/> |
|RTCUniversalUserAdmins  <br/> |写 RTCUserSearchPropertySet  <br/> 写 otherIpPhone  <br/> 写入 displayName  <br/> 写入说明  <br/> 写 telephoneNumber  <br/> 写 msExchUCVoiceMailSettings  <br/> 写 RTCUserProvisioningPropertySet  <br/> 写 RTCPropertySet  <br/> 写 proxyAddresses  <br/> |子代联系人对象  <br/> |
   
## <a name="granting-permission-for-device-objects"></a>为设备对象授予权限

在 OU 上运行设备对象的**CsOuPermission** cmdlet 时, 将向组授予下表中所示的权限。
  
**为设备对象授予的权限**

|**团队**|**权限**|**适用于**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |复制目录更改  <br/> |仅此对象  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |列表内容  <br/> 读取所有属性  <br/> 读取权限  <br/> |仅此对象  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |列表内容  <br/> 读取所有属性  <br/> 读取权限  <br/> |仅此对象  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |阅读 RTCUserSearchPropertySet  <br/> 阅读 RTCUserProvisioningPropertySet  <br/> 阅读 RTCPropertySet  <br/> 阅读公共信息  <br/> 阅读个人信息  <br/> 阅读常规信息  <br/> 阅读用户-帐户限制  <br/> |子代联系人对象  <br/> |
|RTCUniversalUserAdmins  <br/> |创建子元素  <br/> 删除子元素  <br/> 删除树  <br/> |联系人  <br/> |
|RTCUniversalUserAdmins  <br/> |写入 displayName  <br/> 写入说明  <br/> 写 telephoneNumber  <br/> |子代用户对象  <br/> |
|RTCUniversalUserAdmins  <br/> |写 RTCUserSearchPropertySet  <br/> 写 otherIpPhone  <br/> 写入 displayName  <br/> 写入说明  <br/> 写 telephoneNumber  <br/> 写 msExchUCVoiceMailSettings  <br/> 写 RTCUserProvisioningPropertySet  <br/> 写 RTCPropertySet  <br/> 写 proxyAddresses  <br/> |子代联系人对象  <br/> |
   
## <a name="granting-permission-for-inetorgperson-objects"></a>为 InetOrgPerson 对象授予权限

当你针对 OU 上的 InetOrgPerson 对象运行**CsOuPermission** cmdlet 时, 将向组授予下表中所示的权限。
  
**为 InetOrgPerson 对象授予的权限**

|**团队**|**权限**|**适用于**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |复制目录更改  <br/> |仅此对象  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |列表内容  <br/> 读取所有属性  <br/> 读取权限  <br/> |仅此对象  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |列表内容  <br/> 读取所有属性  <br/> 读取权限  <br/> |仅此对象  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |阅读 RTCUserSearchPropertySet  <br/> 阅读 RTCUserProvisioningPropertySet  <br/> 阅读 RTCPropertySet  <br/> 阅读个人信息  <br/> 阅读公共信息  <br/> 阅读常规信息  <br/> 阅读用户-帐户限制  <br/> |子代 inetOrgPerson 对象  <br/> |
|RTCUniversalUserAdmins  <br/> |写 RTCUserSearchPropertySet  <br/> 写 RTCUserProvisioningPropertySet  <br/> 写 RTCPropertySet  <br/> 写 proxyAddresses  <br/> |子代 inetOrgPerson 对象  <br/> |
   

