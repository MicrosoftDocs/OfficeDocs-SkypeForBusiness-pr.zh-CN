---
title: Renew-CcServerCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7844b55e-b7e9-4599-9962-f0322728405a
description: Renew-CcServerCertificate cmdlet 在证书即将过期Skype for Business 云连接器版本过期时续订证书。 在云连接器 2.0 Update-CcServerCertificate版本中，此命令已更改为 Update-CcServerCertificate。
ms.openlocfilehash: 632807f8d6b8dda7b3df6639e8f6166e8ac5e6a22381646616a0637779a9159a
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54340728"
---
# <a name="renew-ccservercertificate"></a>Renew-CcServerCertificate
 
Renew-CcServerCertificate cmdlet 在证书即将过期Skype for Business 云连接器版本过期时续订证书。 在云连接器 2.0 Update-CcServerCertificate版本中，此命令已更改为 Update-CcServerCertificate。 
  
```powershell
Renew-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

下面的示例在中央管理存储、中介服务器和边缘服务器的证书即将过期或已过期时续订这些证书：
  
```powershell
Renew-CcServerCertificate
```

### <a name="example-2"></a>示例 2

下一个示例在中介服务器和边缘服务器即将过期或已过期时续订这些证书：
  
```powershell
Renew-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a>详细说明
<a name="DetailedDescription"> </a>

颁发给中央管理存储、中介服务器和边缘服务器的云连接器内部证书在从证书颁发机构服务颁发后有效期为两年。 如果证书即将过期或已过期，请运行 Renew-CcServerCertificate cmdlet 来续订证书。 
  
## <a name="parameters"></a>参数
<a name="DetailedDescription"> </a>

|**参数**|**Required**|**类型**|**说明**|
|:-----|:-----|:-----|:-----|
|角色  <br/> |可选  <br/> |System.Array  <br/> | 云连接器服务器角色数组。 <br/> |
   
## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

无。 Renew-CcServerCertificate cmdlet 不接受通过管道的输入。
  
## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

无
  
## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

