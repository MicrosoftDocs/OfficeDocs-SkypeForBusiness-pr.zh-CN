---
title: Uninstall-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/23/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e1b3cdd7-08e9-41a6-843a-3b4baf886cd0
description: Uninstall-CcAppliance cmdlet 用于从主机服务器中卸载正在运行的 Skype for Business 云连接器版本设备。
ms.openlocfilehash: 7b2def71eee17c81b6f178a18d4c248557a0f022
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885646"
---
# <a name="uninstall-ccappliance"></a>Uninstall-CcAppliance
 
Uninstall-CcAppliance cmdlet 用于从主机服务器中卸载正在运行的 Skype for Business 云连接器版本设备。 
  
```
Uninstall-CcAppliance [-Version <string>] [-Force] [-Confirm <bool>] [<CommonParameters>]
```

## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

下面的示例排空并从主机服务器中卸载云连接器设备：
  
```
Uninstall-CcAppliance
```

### <a name="example-2"></a>示例 2

下一个示例排空并强制卸载主机服务器上运行的云连接器设备，即使消耗进程失败：
  
```
Uninstall-CcAppliance -Force
```

### <a name="example-3"></a>示例 3

下一个示例卸载云连接器备份版本，而无需用户确认：
  
```
Uninstall-CcAppliance -Version 1.3.8 -Confirm:$false
```

## <a name="detailed-description"></a>详细说明
<a name="DetailedDescription"> </a>

如果要卸载云连接器正在运行的当前版本，首先让完成之前卸载虚拟机的并发呼叫的中介服务器和边缘服务器上运行消耗服务。 如果你要卸载备份版本，则不执行排出操作。
  
## <a name="parameters"></a>参数
<a name="DetailedDescription"> </a>

|**参数**|**必需**|**类型**|**说明**|
|:-----|:-----|:-----|:-----|
| 版本 <br/> | 可选 <br/> |System.String  <br/> | 将从主机服务器卸载的云连接符的版本。 如果未指定，将卸载当前正在运行的版本。 <br/> |
|强制  <br/> |可选  <br/> |System.Management.Automation.SwitchParameter  <br/> |如果卸载当前正在运行的版本，将先尝试在中介服务器和边缘服务器上排出服务，然后卸载虚拟机。如果指定“Force”开关，即使排出服务失败，也会卸载虚拟机。此参数仅用于卸载当前正在运行的版本。  <br/> |
|确认  <br/> |可选  <br/> |System.Management.Automation.SwitchParameter  <br/> |要求用户确认卸载虚拟机。 默认值为 TRUE。  <br/> |
   
## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

无。Uninstall-CcAppliance cmdlet 不接受主线输入。
  
## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

无
  
## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

[Install-CcAppliance](install-ccappliance.md)
  
[Publish-CcAppliance](publish-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[Unregister-CcAppliance](unregister-ccappliance.md)
  

