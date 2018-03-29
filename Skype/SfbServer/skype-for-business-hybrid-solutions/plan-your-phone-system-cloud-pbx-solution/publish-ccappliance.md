---
title: 将发布 CcAppliance
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e7d5b63e-ba7c-4757-8670-f96b2a91e646
description: Publish-CcAppliance cmdlet 从联机租户配置中获取高可用性信息，并将其发布到主机服务器上的 Skype for Business 云连接器版本设备。
ms.openlocfilehash: c0a2639156a0794ec34fd62a58027255d24d461e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="publish-ccappliance"></a>将发布 CcAppliance
 
Publish-CcAppliance cmdlet 从联机租户配置中获取高可用性信息，并将其发布到主机服务器上的 Skype for Business 云连接器版本设备。 
  
```
Publish-CcAppliance
```

## <a name="parameters"></a>参数

无
  
## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

下面的示例获取从联机租户配置高可用性的信息，并将其发布到主机服务器上云接头装置：
  
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

[安装 CcAppliance](install-ccappliance.md)
  
[卸载-CcAppliance](uninstall-ccappliance.md)
  
[注册 CcAppliance](register-ccappliance.md)
  
[取消注册 CcAppliance](unregister-ccappliance.md)
  

