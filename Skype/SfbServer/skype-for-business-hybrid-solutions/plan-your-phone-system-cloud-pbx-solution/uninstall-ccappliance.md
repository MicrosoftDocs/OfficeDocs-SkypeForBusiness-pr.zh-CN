---
title: Uninstall-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/23/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e1b3cdd7-08e9-41a6-843a-3b4baf886cd0
description: Uninstall-CcAppliance cmdlet 用于从主机服务器中卸载正在运行的 Skype for Business 云连接器版本设备。
ms.openlocfilehash: 337c5c489846facb1da3c177cac7a965d7550ae5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286892"
---
# <a name="uninstall-ccappliance"></a>Uninstall-CcAppliance
 
Uninstall-CcAppliance cmdlet 用于从主机服务器中卸载正在运行的 Skype for Business 云连接器版本设备。 
  
```
Uninstall-CcAppliance [-Version <string>] [-Force] [-Confirm <bool>] [<CommonParameters>]
```

## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

下面的示例从主服务器中耗尽和卸载云连接器装置:
  
```
Uninstall-CcAppliance
```

### <a name="example-2"></a>示例 2

下一个示例将排出并强制卸载主机服务器上正在运行的云连接器装置, 即使排出过程失败:
  
```
Uninstall-CcAppliance -Force
```

### <a name="example-3"></a>示例 3

下一示例在没有用户确认的情况下卸载云连接器备份版本:
  
```
Uninstall-CcAppliance -Version 1.3.8 -Confirm:$false
```

## <a name="detailed-description"></a>详细说明
<a name="DetailedDescription"> </a>

如果你卸载的是当前运行的云连接器版本, 将首先在中介服务器和 Edge 服务器上运行排水管服务, 以便在卸载虚拟机之前, 让并发调用完成。 如果你要卸载备份版本，则不执行排出操作。
  
## <a name="parameters"></a>参数
<a name="DetailedDescription"> </a>

|**参数**|**必需**|**类型**|**说明**|
|:-----|:-----|:-----|:-----|
| 版本 <br/> | 可选 <br/> |System.String  <br/> | 将从主机服务器卸载的云连接器的版本。 如果未指定，将卸载当前正在运行的版本。 <br/> |
|强制  <br/> |可选  <br/> |System.Management.Automation.SwitchParameter  <br/> |如果卸载当前正在运行的版本，将先尝试在中介服务器和边缘服务器上排出服务，然后卸载虚拟机。如果指定“Force”开关，即使排出服务失败，也会卸载虚拟机。此参数仅用于卸载当前正在运行的版本。  <br/> |
|确认  <br/> |可选  <br/> |System.Management.Automation.SwitchParameter  <br/> |询问用户确认以卸载虚拟机。 默认值为 TRUE。  <br/> |
   
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
  

