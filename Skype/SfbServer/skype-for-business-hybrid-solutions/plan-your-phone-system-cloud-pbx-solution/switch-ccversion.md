---
title: Switch-CcVersion
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
ms.assetid: 95e37b13-525b-4690-be32-839312e4ffe3
description: 'Switch-CcVersion cmdlet 可将正在运行的设备断开连接，并切换到新部署的设备或备份设备。 '
ms.openlocfilehash: 31dbb841caae51de0accedf081fa576ec378044b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824146"
---
# <a name="switch-ccversion"></a>Switch-CcVersion
 
Switch-CcVersion cmdlet 可将正在运行的设备断开连接，并切换到新部署的设备或备份设备。  
  
```powershell
Switch-CcVersion [-Force]
```

## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

以下示例将排出当前正在运行的设备的服务，然后切换到新部署的设备或备份设备：
  
```powershell
Switch-CcVersion
```

### <a name="example-2"></a>示例 2

下一个示例将排出当前正在运行的设备的服务，并在排出服务失败时强制停止服务。 然后，该命令将切换到新部署的设备或备份设备。
  
```powershell
Switch-CcVersion -Force
```

## <a name="detailed-description"></a>详细说明
<a name="DetailedDescription"> </a>

CcVersion cmdlet 用于在中介服务器和 Edge 服务器上消耗云连接器服务。 所有正在运行的呼叫都将完成，但设备将拒绝任何新呼叫。 排出后，cmdlet 会从企业和 Internet 网络中断开正在运行的设备，关闭属于该设备的所有虚拟机，然后将备份设备连接至企业和 Internet 网络。
  
## <a name="parameters"></a>参数
<a name="DetailedDescription"> </a>

|**参数**|**必需**|**类型**|**说明**|
|:-----|:-----|:-----|:-----|
| Force <br/> | 可选 <br/> |System.Management.Automation.SwitchParameter  <br/> |  在排出服务失败时强制停止服务。 <br/> |
   
## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

无
  
## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

无
  
## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

无
  

