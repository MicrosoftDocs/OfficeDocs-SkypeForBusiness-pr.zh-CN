---
title: Get-CcCredential
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b2b5aefb-a08d-4bec-9204-76597d413849
description: Get-CcCredential cmdlet 用于返回当前 Skype for Business 云连接器版本部署的凭据。
ms.openlocfilehash: 651190f31ad44e0bb2375bbf4a70951c2011e1a7
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898393"
---
# <a name="get-cccredential"></a>Get-CcCredential
 
Get-CcCredential cmdlet 用于返回当前 Skype for Business 云连接器版本部署的凭据。 
  
使用版本 2.0 及更高版本，您还可以使用-DisplayPassword 参数 TenantAdmin、 DomainAdmin，和 VMAdmin 显示相应的密码。
  
```
Get-CcCredential [[-AccountType] <string> {VmAdmin | DomainAdmin | SafeModeAdmin | ExternalCert | TenantAdmin}]
```

## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

以下示例返回云连接器虚拟机域的域管理员凭据：
  
```
Get-CcCredential -AccountType DomainAdmin
```

## <a name="detailed-description"></a>详细说明
<a name="DetailedDescription"> </a>

Get-CcCredential cmdlet 用于返回有关指定帐户类型的凭据信息。这些凭据由部署当前设备时运行 Register-CcAppliance 和 Install-CcAppliance cmdlet 的管理员指定。 
  
Get-CcCredential cmdlet 返回 System.Management.Automation.PSCredential 对象的实例。返回对象的密码属性是 System.Security.SecureString。
  
如果你希望获得域管理员密码的明文，请确保密码由你的当前登录帐户在主机服务器上输入，然后以管理员身份打开 PowerShell 控制台并运行以下脚本：
  
```
$cred = Get-CcCredential -AccountType DomainAdmin
$password =  $cred.Password
$bstr = [System.Runtime.InteropServices.Marshal]::SecureStringToBSTR($password);
$text = [System.Runtime.InteropServices.Marshal]::PtrToStringAuto($bstr);
[System.Runtime.InteropServices.Marshal]::ZeroFreeBSTR($bstr);
Write-Host $text
```

## <a name="parameters"></a>参数
<a name="DetailedDescription"> </a>

|**参数**|**必需**|**类型**|**说明**|
|:-----|:-----|:-----|:-----|
| AccountType <br/> |必需  <br/> | System.String <br/> | AccountType 值可以是以下项之一： <br/>  VmAdmin： 云连接器虚拟机的本地管理员。 <br/>  DomainAdmin：云连接器虚拟机域的域管理员。 <br/>  SafeModeAdmin：云连接器虚拟机域控制器的 SafeModeAdmin。 <br/>  ExternalCert：边缘服务器上安装的外部证书的帐户。 <br/>  TenantAdmin：O365 租户的管理员。 <br/> |
   
## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

无。Get-CcCredential cmdlet 不接受主线输入。
  
## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

Get-CcCredential cmdlet 返回 System.Management.Automation.PSCredential 对象的实例。
  
## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

[Set-CcCredential](set-cccredential.md)
  

