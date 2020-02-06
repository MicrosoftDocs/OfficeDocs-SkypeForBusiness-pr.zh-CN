---
title: Remove-CcLegacyServerCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/22/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ff21cecb-5035-48fd-9705-11ea81ce7df6
description: 在执行 Renew-CcCACertificate 或 Renew CcServerCertificate cmdlet 后，执行 Remove-CcLegacyServerCertificate cmdlet 可删除中央管理存储、中介服务器和边缘服务器上的旧服务器证书。
ms.openlocfilehash: f3fe17e8c6c559d1a2c8ab14543807f82c4b6813
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824278"
---
# <a name="remove-cclegacyservercertificate"></a>Remove-CcLegacyServerCertificate
 
在执行 Renew-CcCACertificate 或 Renew CcServerCertificate cmdlet 后，执行 Remove-CcLegacyServerCertificate cmdlet 可删除中央管理存储、中介服务器和边缘服务器上的旧服务器证书。
  
```powershell
Remove-CcLegacyServerCertificate [[-Roles] <array> {Cms | MS | Edge}] 
```

## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

以下示例在续订证书后删除为中央管理存储、中介服务器和边缘服务器颁发的旧证书：
  
```powershell
Remove-CcLegacyServerCertificate
```

### <a name="example-2"></a>示例 2

以下示例在续订证书后删除为中介服务器和边缘服务器颁发的旧证书： 
  
```powershell
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
  

