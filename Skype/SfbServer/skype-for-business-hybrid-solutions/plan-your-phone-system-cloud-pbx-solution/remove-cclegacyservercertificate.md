---
title: Remove-CcLegacyServerCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/22/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ff21cecb-5035-48fd-9705-11ea81ce7df6
description: 在执行 Renew-CcCACertificate 或 Renew CcServerCertificate cmdlet 后，执行 Remove-CcLegacyServerCertificate cmdlet 可删除中央管理存储、中介服务器和边缘服务器上的旧服务器证书。
ms.openlocfilehash: 5f148aa083b646565adf0158f34fb15314296170
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30882458"
---
# <a name="remove-cclegacyservercertificate"></a>Remove-CcLegacyServerCertificate
 
在执行 Renew-CcCACertificate 或 Renew CcServerCertificate cmdlet 后，执行 Remove-CcLegacyServerCertificate cmdlet 可删除中央管理存储、中介服务器和边缘服务器上的旧服务器证书。
  
```
Remove-CcLegacyServerCertificate [[-Roles] <array> {Cms | MS | Edge}] 
```

## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

以下示例在续订证书后删除为中央管理存储、中介服务器和边缘服务器颁发的旧证书：
  
```
Remove-CcLegacyServerCertificate
```

### <a name="example-2"></a>示例 2

以下示例在续订证书后删除为中介服务器和边缘服务器颁发的旧证书： 
  
```
Remove-CcLegacyServerCertificate -Roles @("MS", "Edge") 
```

## <a name="parameters"></a>参数
<a name="Examples"> </a>

|**参数**|**必需**|**类型**|**说明**|
|:-----|:-----|:-----|:-----|
| 角色 <br/> |可选  <br/> |System.Array  <br/> | 云连接器服务器角色的阵列。 <br/> |
   
## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

无。Remove-CcLegacyServerCertificate cmdlet 不接主线输入。
  
## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

无
  
## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcCACertificate](renew-cccacertificate.md)
  
[Update-CcCACertificate](update-cccacertificate.md)
  

