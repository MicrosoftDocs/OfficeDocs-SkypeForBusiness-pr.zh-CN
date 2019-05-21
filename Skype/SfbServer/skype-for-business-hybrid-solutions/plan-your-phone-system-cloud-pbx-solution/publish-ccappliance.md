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
localization_priority: Normal
ms.assetid: e7d5b63e-ba7c-4757-8670-f96b2a91e646
description: Publish-CcAppliance cmdlet 从联机租户配置中获取高可用性信息，并将其发布到主机服务器上的 Skype for Business 云连接器版本设备。
ms.openlocfilehash: 2fd17e2afdceabc8fbfb44a808b7e6c9ce6bd894
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287158"
---
# <a name="publish-ccappliance"></a>Publish-CcAppliance
 
Publish-CcAppliance cmdlet 从联机租户配置中获取高可用性信息，并将其发布到主机服务器上的 Skype for Business 云连接器版本设备。 
  
```
Publish-CcAppliance
```

## <a name="parameters"></a>参数

无
  
## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

以下示例从联机租户配置获取高可用性信息, 并将其发布到主机服务器上的云连接器设备:
  
```
Publish-CcAppliance
```

## <a name="detailed-description"></a>详细说明
<a name="DetailedDescription"> </a>

高可用性信息包括 PSTN 站点的中介服务器 FQDN 和 IP 地址。向 AD 服务器添加有关中介服务器 IP 地址的新 DNS A 记录。用新拓扑项来更新中央管理存储中的中介服务器 FQDN 和 IP 地址。 
  
## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

无。 Publish-CcAppliance cmdlet 不接受主线输入。
  
## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

无
  
## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

[Install-CcAppliance](install-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[Unregister-CcAppliance](unregister-ccappliance.md)
  

