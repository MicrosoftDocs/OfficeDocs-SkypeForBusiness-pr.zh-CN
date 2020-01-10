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
localization_priority: Normal
ms.assetid: 01eed3c5-af68-4db7-90b3-d28ebe7ffef1
description: Register-CcAppliance cmdlet 将设备信息注册到联机租户配置中的 PSTN 站点。 必须先注册设备，Skype for Business 云连接器版本管理服务才能对其进行部署和管理。
ms.openlocfilehash: 93f1fe59a199214615c5ecdf8445f6c363ce6bbe
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003302"
---
# <a name="register-ccappliance"></a>Register-CcAppliance
 
Register-CcAppliance cmdlet 将设备信息注册到联机租户配置中的 PSTN 站点。 必须先注册设备，Skype for Business 云连接器版本管理服务才能对其进行部署和管理。
  
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

以下示例在本地检查用于注册的配置，而不连接到联机租户配置：
  
```powershell
Register-CcAppliance -Local
```

### <a name="example-3"></a>示例 3

以下示例将当前设备以名称“Appliance1”注册到 PSTN 站点“Site1”：
  
```powershell
Register-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a>详细说明
<a name="DetailedDescription"> </a>

必须提供租户管理员帐户名称和密码。 请使用你为云连接器在线管理创建的帐户。 
  
在版本1.4.2 及更早版本中，按照说明提供外部证书密码、安全模式管理员密码、域管理员密码和 VM 管理员密码。 
  
在 2.0 版和更高版本中，按照说明提供外部证书密码、CceService 密码和 CABackupFile 密码。
  
注册结束后，重新启动云连接器管理服务，并以 CceService 帐户身份登录服务。
  
CloudConnector.ini 文件中与边缘服务器外部 FQDN 组合在一起的 SiteName 被视为 PSTN 站点标识。如果注册站点时既未使用 SiteName 也未使用边缘服务器外部 FQDN，将在联机租户配置中为此设备创建新站点。如果找到 PSTN 站点标识，PSTN 站点将使用此标识，并且设备将注册到此 PSTN 站点。 
  
在下面的情况下，cmdlet 将失败，并指示 Site1 已注册。 
  
- SiteName 为 Site1 且边缘服务器外部 FQDN 为 edgserver1.contoso.com。 
    
- 其 SiteName 为 Site1 且边缘服务器外部 FQDN 为 edgserver.contoso.com 的 PSTN 站点。
    
- 其 SiteName 为 NewSite 且边缘服务器外部 FQDN 为 edgserver1.contoso.com 的 PSTN 站点已注册。 
    
CloudConnector.ini 文件中与中介服务器 FQDN 组合在一起的 ApplianceName 被视为设备标识。如果注册设备时既未使用 ApplianceName 也未使用中介服务器外部 FQDN，将在联机租户配置中创建新设备。如果设备已注册，cmdlet 将失败。
  
在下面的情况下，cmdlet 将失败，并指示设备已注册。 
  
- ApplianceName 为 Appliance1 且中介服务器 FQDN 为 ms1.vdomain.com。
    
- 在当前 PSTN 站点中，如果其名称为 Appliance1 且中介服务器 FQDN 为 ms.vdomain.com 的设备或其名称为 NewAppliance 且中介服务器 FQDN 为 ms1.vdomain.com 的设备已注册。
    
## <a name="parameters"></a>参数
<a name="DetailedDescription"> </a>

|**参数**|**必需**|**类型**|**说明**|
|:-----|:-----|:-----|:-----|
|SiteName  <br/> |可选  <br/> |System.String  <br/> |向其注册设备的 PSTN 站点名称。默认值是 CloudConnector.ini 文件中的 SiteName 值。  <br/> |
|ApplianceName  <br/> |可选  <br/> |System.String  <br/> |当前设备的名称。默认值是主机服务器的计算机名称。  <br/> |
|本地  <br/> |可选  <br/> |System.Management.Automation.SwitchParameter  <br/> |在本地检查用于注册的配置，而不连接到联机租户配置。  <br/> |
   
## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

无。Register-CcAppliance cmdlet 不接受主线输入。
  
## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

无
  
## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

[Unregister-CcAppliance](unregister-ccappliance.md)
  
[Publish-CcAppliance](publish-ccappliance.md)
  
[Install-CcAppliance](install-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  

