---
title: Publish-CcAppliance
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
ms.assetid: e7d5b63e-ba7c-4757-8670-f96b2a91e646
description: 此 Publish-CcAppliance cmdlet 从联机租户配置获取高可用性信息，并发布到主机Skype for Business 云连接器版本上的 Skype for Business 云连接器版本 设备。
ms.openlocfilehash: 83b0a7e3806a271a358085bb0cca2a2ef6a518e67e124f0be97c1ff4616e3dcc
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54326178"
---
# <a name="publish-ccappliance"></a>Publish-CcAppliance
 
此 Publish-CcAppliance cmdlet 从联机租户配置获取高可用性信息，并发布到主机Skype for Business 云连接器版本上的 Skype for Business 云连接器版本 设备。 
  
```powershell
Publish-CcAppliance
```

## <a name="parameters"></a>参数

无
  
## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

以下示例从联机租户配置获取高可用性信息，并发布到主机服务器的云连接器设备：
  
```powershell
Publish-CcAppliance
```

## <a name="detailed-description"></a>详细说明
<a name="DetailedDescription"> </a>

高可用性信息包含 PSTN 站点的中介服务器 FQDN 和 IP 地址。 新的 DNS A 记录将添加到中介服务器 IP 地址的 AD 服务器。 新的拓扑项目将更新到中介服务器 FQN 和 IP 地址的中央管理存储。 
  
## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

无。 Publish-CcAppliance cmdlet 不接受通过管道的输入。
  
## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

无
  
## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

[Install-CcAppliance](install-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[Unregister-CcAppliance](unregister-ccappliance.md)
  

