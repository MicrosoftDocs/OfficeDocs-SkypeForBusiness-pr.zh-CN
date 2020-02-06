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
localization_priority: Normal
ms.assetid: cd2889c4-0eb1-4752-9274-93a5a68a8080
description: 'Update-CcServerCertificate cmdlet 用于在 Skype for Business 云连接器版本的证书即将过期或已过期时续订这些证书。 '
ms.openlocfilehash: da52efcd3fdf6a0793e085098bf6f72725115e9c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824106"
---
# <a name="update-ccservercertificate"></a>Update-CcServerCertificate
 
Update-CcServerCertificate cmdlet 用于在 Skype for Business 云连接器版本的证书即将过期或已过期时续订这些证书。  
  
```powershell
Update-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

以下示例在中央管理存储、中介服务器和边缘服务器的证书即将过期或已过期时续订这些证书：
  
```powershell
Update-CcServerCertificate
```

### <a name="example-2"></a>示例 2

以下示例在中介服务器和边缘服务器的证书即将过期或已过期时续订这些证书：
  
```powershell
Update-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a>详细说明
<a name="DetailedDescription"> </a>

颁发给中央管理存储、中介服务器和边缘服务器的云连接器内部证书在从证书颁发机构服务发出的两年后有效。 如果证书即将过期或已过期，请运行 Update-CcServerCertificate cmdlet 来续订证书。 
  
在云连接器 2.0 版和更高版本中，此命令将替代 Renew-CcServerCertificate cmdle。
  
## <a name="parameters"></a>参数
<a name="DetailedDescription"> </a>

|**参数**|**必需**|**类型**|**说明**|
|:-----|:-----|:-----|:-----|
|角色  <br/> |可选  <br/> |System.Array  <br/> | 云连接器服务器角色的阵列。 <br/> |
   
## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

无。 Update-CcServerCertificate cmdlet 不接受主线输入。
  
## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

无
  
## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

