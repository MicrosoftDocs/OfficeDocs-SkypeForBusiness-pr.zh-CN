---
title: Unregister-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3d516e65-fb9b-4a0b-8296-969fc9eda334
description: 此Unregister-CcAppliance cmdlet 从 PSTN Skype for Business 云连接器版本联机租户配置中注销当前设备。
ms.openlocfilehash: de872082f6a025a736b871a76d41061c888acb1f401739229ba7ad670a0c19ce
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54344541"
---
# <a name="unregister-ccappliance"></a>Unregister-CcAppliance
 
此Unregister-CcAppliance cmdlet 从 PSTN Skype for Business 云连接器版本联机租户配置中注销当前设备。
  
```powershell
Unregister-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

以下示例从联机租户配置中注销当前设备：
  
```powershell
Unregister-CcAppliance
```

### <a name="example-2"></a>示例 2

下一个示例检查配置是否在本地注销，而不连接到联机租户配置：
  
```powershell
Unregister-CcAppliance -Local
```

### <a name="example-3"></a>示例 3

下一个示例将名称为"Appliance1"的当前设备注销至 PSTN 站点"Site1"：
  
```powershell
Unregister-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a>详细说明
<a name="DetailedDescription"> </a>

与 Register-CcAppliance cmdlet 类似，SiteName 与 CloudConnector.ini 文件中的边缘服务器外部 FQDN 组合在一起被视为 PSTN 站点标识。 同样，设备名称与客户端文件中中介服务器 FQDN CloudConnector.ini被视为设备标识。
  
注销设备后，重新启动云连接器管理服务，然后以 NetworkService 帐户登录。
  
## <a name="parameters"></a>参数
<a name="DetailedDescription"> </a>

|**参数**|**Required**|**类型**|**说明**|
|:-----|:-----|:-----|:-----|
| SiteName <br/> |可选  <br/> |System.String  <br/> |注册设备的 PSTN 站点名称。 默认值是网站文件中 SiteName CloudConnector.ini值。  <br/> |
|ApplianceName  <br/> |可选  <br/> |System.String  <br/> |当前设备的名称。 默认值是主机服务器的计算机名称。  <br/> |
|本地  <br/> |可选  <br/> |System.Management.Automation.SwitchParameter  <br/> |检查本地注册的配置，而无需连接到联机租户配置。  <br/> |
   
## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

无。 Unregister-CcAppliance cmdlet 不接受通过管道的输入。
  
## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

无
  
## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

[Register-CcAppliance](register-ccappliance.md)
  
[Install-CcAppliance](install-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  
[Publish-CcAppliance](publish-ccappliance.md)
  

