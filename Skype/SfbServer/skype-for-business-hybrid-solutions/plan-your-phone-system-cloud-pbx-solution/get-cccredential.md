---
title: Get-CcCredential
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b2b5aefb-a08d-4bec-9204-76597d413849
description: Get-CcCredential cmdlet 返回当前部署Skype for Business 云连接器版本凭据。
ms.openlocfilehash: 277062068c6e5e630fd22cd1bd4c6dbfb873db1cb90b915424aa6e3a3eb6ce50
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54322884"
---
# <a name="get-cccredential"></a>Get-CcCredential
 
Get-CcCredential cmdlet 返回当前部署Skype for Business 云连接器版本凭据。 
  
在版本 2.0 及更高版本中，您还可以使用 -DisplayPassword 参数显示 TenantAdmin、DomainAdmin 和 VMAdmin 的密码。
  
```powershell
Get-CcCredential [[-AccountType] <string> {VmAdmin | DomainAdmin | SafeModeAdmin | ExternalCert | TenantAdmin}]
```

## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

以下示例返回云连接器虚拟机域的域管理员凭据：
  
```powershell
Get-CcCredential -AccountType DomainAdmin
```

## <a name="detailed-description"></a>详细说明
<a name="DetailedDescription"> </a>

the Get-CcCredential cmdlet returns the credential information about the specified account type. 这些凭据由在部署当前设备时运行 Register-CcAppliance Install-CcAppliance cmdlet 的管理员指定。 
  
此Get-CcCredential cmdlet 返回 System.Management.Automation.PSCredential 对象的实例。 返回对象的密码属性为 System.Security.SecureString。
  
如果要获取域管理员密码的清除文本，请确保密码由主机服务器上当前登录帐户输入，然后以管理员角色打开 PowerShell 控制台并运行以下脚本：
  
```powershell
$cred = Get-CcCredential -AccountType DomainAdmin
$password =  $cred.Password
$bstr = [System.Runtime.InteropServices.Marshal]::SecureStringToBSTR($password);
$text = [System.Runtime.InteropServices.Marshal]::PtrToStringAuto($bstr);
[System.Runtime.InteropServices.Marshal]::ZeroFreeBSTR($bstr);
Write-Host $text
```

## <a name="parameters"></a>参数
<a name="DetailedDescription"> </a>

|**参数**|**Required**|**类型**|**说明**|
|:-----|:-----|:-----|:-----|
| AccountType <br/> |必需  <br/> | System.String <br/> | AccountType 值可以是下列值之一： <br/>  VmAdmin：云连接器虚拟机的本地管理员。 <br/>  DomainAdmin：云连接器虚拟机域的域管理员。 <br/>  SafeModeAdmin：云连接器虚拟机域控制器的 SafeModeAdmin。 <br/>  ExternalCert：边缘服务器上安装的外部证书的帐户。 <br/>  TenantAdmin：O365 租户的管理员。 <br/> |
   
## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

无。 Get-CcCredential cmdlet 不接受通过管道的输入。
  
## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

此Get-CcCredential cmdlet 返回 System.Management.Automation.PSCredential 对象的实例。
  
## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

[Set-CcCredential](set-cccredential.md)
  

