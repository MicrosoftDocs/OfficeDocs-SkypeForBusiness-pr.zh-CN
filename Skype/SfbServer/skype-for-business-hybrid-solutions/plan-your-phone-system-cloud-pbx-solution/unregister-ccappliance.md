---
title: 取消注册 CcAppliance
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d516e65-fb9b-4a0b-8296-969fc9eda334
description: Unregister-CcAppliance cmdlet 在联机租户配置中从 PSTN 站点注销 Skype for Business 云连接器版本设备。
ms.openlocfilehash: 21bd0a7dffc6a395f829af68a61dfd7523d2c09a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="unregister-ccappliance"></a>取消注册 CcAppliance
 
Unregister-CcAppliance cmdlet 在联机租户配置中从 PSTN 站点注销 Skype for Business 云连接器版本设备。
  
```
Unregister-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

以下示例从联机租户配置中注销当前设备：
  
```
Unregister-CcAppliance
```

### <a name="example-2"></a>示例 2

下一个示例将检查本地注销未连接到联机的客户端配置的配置：
  
```
Unregister-CcAppliance -Local
```

### <a name="example-3"></a>示例 3

下一个示例将注销当前的装置名为"Appliance1"到 PSTN 站点"Site1":
  
```
Unregister-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a>详细说明
<a name="DetailedDescription"> </a>

与 Register-CcAppliance cmdlet 类似，CloudConnector.ini 文件中与边缘服务器外部 FQDN 组合在一起的 SiteName 被视为 PSTN 站点标识。同样，CloudConnector.ini 文件中与中介服务器 FQDN 组合在一起的 ApplianceName 被视为设备标识。
  
该装置注销后，重新启动云连接器管理服务和日志上为网络服务帐户。
  
## <a name="parameters"></a>参数
<a name="DetailedDescription"> </a>

|**参数**|**必填**|**类型**|**说明**|
|:-----|:-----|:-----|:-----|
| 站点名 <br/> |可选  <br/> |System.String  <br/> |在其中注册设备的 PSTN 站点名称。默认值是 CloudConnector.ini 文件中的 SiteName 值。  <br/> |
|装置名称  <br/> |可选  <br/> |System.String  <br/> |当前设备的名称。默认值是主机服务器的计算机名称。  <br/> |
|本地  <br/> |可选  <br/> |System.Management.Automation.SwitchParameter  <br/> |检查用于在本地注册的配置，不必连接到联机租户配置。  <br/> |
   
## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

无。Unregister-CcAppliance cmdlet 不接受主线输入。
  
## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

无
  
## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

[注册 CcAppliance](register-ccappliance.md)
  
[安装 CcAppliance](install-ccappliance.md)
  
[卸载-CcAppliance](uninstall-ccappliance.md)
  
[将发布 CcAppliance](publish-ccappliance.md)
  

