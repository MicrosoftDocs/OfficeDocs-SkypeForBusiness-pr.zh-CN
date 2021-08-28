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
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: e1b3cdd7-08e9-41a6-843a-3b4baf886cd0
description: 此Uninstall-CcAppliance cmdlet 从主机Skype for Business 云连接器版本正在运行的设备。
ms.openlocfilehash: 12a15e7bc338fc503a1fafbd6e3059f73dcd40d4
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58624944"
---
# <a name="uninstall-ccappliance"></a>Uninstall-CcAppliance
 
此Uninstall-CcAppliance cmdlet 从主机Skype for Business 云连接器版本正在运行的设备。 
  
```powershell
Uninstall-CcAppliance [-Version <string>] [-Force] [-Confirm <bool>] [<CommonParameters>]
```

## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

以下示例从主机服务器排出和卸载云连接器设备：
  
```powershell
Uninstall-CcAppliance
```

### <a name="example-2"></a>示例 2

下一个示例排出并强制卸载主机服务器上正在运行的云连接器设备，即使排出过程失败：
  
```powershell
Uninstall-CcAppliance -Force
```

### <a name="example-3"></a>示例 3

下一个示例卸载云连接器备份版本，无需用户确认：
  
```powershell
Uninstall-CcAppliance -Version 1.3.8 -Confirm:$false
```

## <a name="detailed-description"></a>详细说明
<a name="DetailedDescription"> </a>

如果要卸载当前正在运行的云连接器版本，则首先在中介服务器和边缘服务器上运行排出服务，以允许并发呼叫在卸载虚拟机之前完成。 如果要卸载备份版本，则不执行排出操作。
  
## <a name="parameters"></a>参数
<a name="DetailedDescription"> </a>

|**参数**|**Required**|**类型**|**说明**|
|:-----|:-----|:-----|:-----|
| 版本 <br/> | 可选 <br/> |System.String  <br/> | 从主机服务器卸载的云连接器的版本。 如果未指定，请卸载当前运行的版本。 <br/> |
|Force  <br/> |可选  <br/> |System.Management.Automation.SwitchParameter  <br/> |如果卸载当前运行的版本，尝试在卸载虚拟机之前排出中介服务器和边缘服务器中的服务器。 如果指定"Force"开关，即使排出服务失败，也会卸载虚拟机。 此参数仅用于卸载当前运行的版本。  <br/> |
|确认  <br/> |可选  <br/> |System.Management.Automation.SwitchParameter  <br/> |要求用户确认卸载虚拟机。 默认值为 TRUE。  <br/> |
   
## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

无。 Uninstall-CcAppliance cmdlet 不接受通过管道的输入。
  
## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

无
  
## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

[Install-CcAppliance](install-ccappliance.md)
  
[Publish-CcAppliance](publish-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[Unregister-CcAppliance](unregister-ccappliance.md)
  

