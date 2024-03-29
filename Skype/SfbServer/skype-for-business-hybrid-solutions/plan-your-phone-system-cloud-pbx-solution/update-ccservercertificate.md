---
title: Update-CcServerCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/11/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: cd2889c4-0eb1-4752-9274-93a5a68a8080
description: Update-CcServerCertificate cmdlet 在证书即将过期Skype for Business 云连接器版本过期时续订证书。
ms.openlocfilehash: 1e8afb05d691a1e3e696b619c816cfc45dd26f1e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58623374"
---
# <a name="update-ccservercertificate"></a>Update-CcServerCertificate
 
Update-CcServerCertificate cmdlet 在证书即将过期Skype for Business 云连接器版本过期时续订证书。 
  
```powershell
Update-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

下面的示例在中央管理存储、中介服务器和边缘服务器的证书即将过期或已过期时续订这些证书：
  
```powershell
Update-CcServerCertificate
```

### <a name="example-2"></a>示例 2

下一个示例在中介服务器和边缘服务器即将过期或已过期时续订这些证书：
  
```powershell
Update-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a>详细说明
<a name="DetailedDescription"> </a>

颁发给中央管理存储、中介服务器和边缘服务器的云连接器内部证书在从证书颁发机构服务颁发后有效期为两年。 如果证书即将过期或已过期，请运行 Update-CcServerCertificate cmdlet 来续订证书。 
  
此命令将替换云Renew-CcServerCertificate 2.0 及更高版本中的 cmdlet。
  
## <a name="parameters"></a>参数
<a name="DetailedDescription"> </a>

|**参数**|**Required**|**类型**|**说明**|
|:-----|:-----|:-----|:-----|
|角色  <br/> |可选  <br/> |System.Array  <br/> | 云连接器服务器角色数组。 <br/> |
   
## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

无。 Update-CcServerCertificate cmdlet 不接受通过管道的输入。
  
## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

无
  
## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

