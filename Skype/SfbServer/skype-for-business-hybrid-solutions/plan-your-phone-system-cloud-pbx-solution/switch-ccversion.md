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
ms.localizationpriority: medium
ms.assetid: 95e37b13-525b-4690-be32-839312e4ffe3
description: 该Switch-CcVersion cmdlet 断开正在运行的设备，并切换到新部署的或备份的设备。
ms.openlocfilehash: 9b15310956f80a9269c8fb611a0f7c6c06f561e7
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58580326"
---
# <a name="switch-ccversion"></a>Switch-CcVersion
 
该Switch-CcVersion cmdlet 断开正在运行的设备，并切换到新部署的或备份的设备。 
  
```powershell
Switch-CcVersion [-Force]
```

## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

以下示例排出当前正在运行的设备的服务，然后切换到新部署的或备份的设备：
  
```powershell
Switch-CcVersion
```

### <a name="example-2"></a>示例 2

下一个示例将排出当前正在运行的设备的服务，如果排出服务失败，将强制停止服务。 然后，该命令将切换到新部署的或备份设备：
  
```powershell
Switch-CcVersion -Force
```

## <a name="detailed-description"></a>详细说明
<a name="DetailedDescription"> </a>

此Switch-CcVersion cmdlet 会排出中介服务器和边缘服务器上云连接器服务。 所有正在运行的呼叫都将完成，但设备将拒绝任何新呼叫。 排出后，该 cmdlet 会断开正在运行的设备与企业网络和 Internet 网络连接，关闭属于该设备的所有虚拟机，然后将备份设备连接到企业网络和 Internet 网络。
  
## <a name="parameters"></a>参数
<a name="DetailedDescription"> </a>

|**参数**|**Required**|**类型**|**说明**|
|:-----|:-----|:-----|:-----|
| Force <br/> | 可选 <br/> |System.Management.Automation.SwitchParameter  <br/> | 如果排出服务失败，强制停止服务。 <br/> |
   
## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

无
  
## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

无
  
## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

无
  

