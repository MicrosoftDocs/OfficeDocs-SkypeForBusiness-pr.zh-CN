---
title: Register-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 01eed3c5-af68-4db7-90b3-d28ebe7ffef1
description: 此Register-CcAppliance cmdlet 将设备信息注册到联机租户配置中的 PSTN 站点。 设备必须先注册，然后才能由 Skype for Business 云连接器版本管理服务进行部署和管理。
ms.openlocfilehash: 5b63ce38b358d41fea15551df1e8134d1b56db00851317cbc5c81ac8f3aea058
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54288800"
---
# <a name="register-ccappliance"></a>Register-CcAppliance
 
此Register-CcAppliance cmdlet 将设备信息注册到联机租户配置中的 PSTN 站点。 设备必须先注册，然后才能由 Skype for Business 云连接器版本管理服务进行部署和管理。
  
```powershell
Register-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

以下示例将当前设备信息注册到联机租户配置：
  
```powershell
Register-CcAppliance
```

### <a name="example-2"></a>示例 2

下一个示例检查本地注册的配置，而不连接到联机租户配置：
  
```powershell
Register-CcAppliance -Local
```

### <a name="example-3"></a>示例 3

下一个示例将名称为"Appliance1"的当前设备注册到 PSTN 站点"Site1"：
  
```powershell
Register-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a>详细说明
<a name="DetailedDescription"> </a>

必须提供租户管理员帐户名称和密码。 使用你为云连接器联机管理创建的帐户。 
  
在版本 1.4.2 及更早版本中，按照说明提供外部证书密码、安全模式管理员密码、域管理员密码和 VM 管理员密码。 
  
在 2.0 版及更高版本中，按照说明提供外部证书密码、CceService 密码和 CABackupFile 密码。
  
注册结束时，重新启动云连接器管理服务，然后以 CceService 帐户登录服务。
  
SiteName 与边缘服务器外部 FQDN 组合在CloudConnector.ini被视为 PSTN 站点标识。 如果未使用 SiteName 和边缘服务器外部 FQDN 注册站点，将在联机租户配置中为此设备创建一个新站点。 如果找到 PSTN 站点标识，PSTN 站点将使用此标识，设备将注册到此 PSTN 站点。 
  
在下列情况下，cmdlet 将失败，并指示已注册 Site1： 
  
- SiteName 为 Site1，边缘服务器外部 FQDN edgserver1.contoso.com。 
    
- 站点名称为 Site1 且边缘服务器外部 FQDN 为 pstN edgserver.contoso.com。
    
- 已注册其 SiteName 为 NewSite 和边缘服务器外部 FQDN edgserver1.contoso.com PSTN 站点。 
    
设备名称与中介服务器 FQDN CloudConnector.ini文件被视为设备标识。 如果 ApplianceName 和中介服务器 FQDN 都未用于注册设备，将在联机租户配置中新建设备。 如果设备已注册，该 cmdlet 将失败。
  
在下列情况下，该 cmdlet 将失败，并指示设备已注册： 
  
- ApplianceName 为 Appliance1，中介服务器 FQDN ms1.vdomain.com。
    
- 在当前 PSTN 站点中，如果名称为 Appliance1 和中介服务器 FQDN 的设备为 ms.vdomain.com 或者已注册其名称为 NewAppliance 和中介服务器 FQDN ms1.vdomain.com 设备。
    
## <a name="parameters"></a>参数
<a name="DetailedDescription"> </a>

|**参数**|**Required**|**类型**|**说明**|
|:-----|:-----|:-----|:-----|
|SiteName  <br/> |可选  <br/> |System.String  <br/> |设备注册到的 PSTN 站点名称。 默认值为网站配置文件中的 SiteName CloudConnector.ini值。  <br/> |
|ApplianceName  <br/> |可选  <br/> |System.String  <br/> |当前设备的名称。 默认值是主机服务器的计算机名称。  <br/> |
|本地  <br/> |可选  <br/> |System.Management.Automation.SwitchParameter  <br/> |检查本地注册的配置，而无需连接到联机租户配置。  <br/> |
   
## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

无。 Register-CcAppliance cmdlet 不接受通过管道的输入。
  
## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

无
  
## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

[Unregister-CcAppliance](unregister-ccappliance.md)
  
[Publish-CcAppliance](publish-ccappliance.md)
  
[Install-CcAppliance](install-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  

