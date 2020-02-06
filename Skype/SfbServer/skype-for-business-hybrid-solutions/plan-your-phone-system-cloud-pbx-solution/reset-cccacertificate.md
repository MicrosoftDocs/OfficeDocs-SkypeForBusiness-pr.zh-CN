---
title: Reset-CcCACertificate
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
ms.assetid: 5ada7e55-df9b-4b4e-b752-2468f4e28b8a
description: Reset-CcCACertificate cmdlet 重新安装证书颁发机构服务 AD 服务器以创建新的根 CA 证书。
ms.openlocfilehash: 6a7f377642ca8aa8722933e503a6c0c2f2613544
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824248"
---
# <a name="reset-cccacertificate"></a>Reset-CcCACertificate
 
Reset-CcCACertificate cmdlet 重新安装证书颁发机构服务 AD 服务器以创建新的根 CA 证书。
  
```powershell
Reset-CcCACertificate
```

## <a name="parameters"></a>参数

无
  
## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

以下示例重新安装证书颁发机构服务 AD 服务器以创建新的根 CA 证书：
  
```powershell
Reset-CcCACertificate
```

## <a name="detailed-description"></a>详细说明
<a name="DetailedDescription"> </a>

如果根 CA 证书已损坏或不再安全，则必须更新根 CA 证书和根 CA 颁发的所有证书。 Reset-CcCACertificate cmdlet 会吊销所有证书、卸载并重新安装证书颁发机构，然后清除与旧证书颁发机构服务相关的所有证书。 
  
有关详细信息，请参阅有关云连接器部署疑难解答中的 "证书颁发机构证书或颁发给 CMS、中介服务器和边缘服务器的内部证书已过期或已泄露"。
  
## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

无。Reset-CcCACertificate cmdlet 不接受主线输入。
  
## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

无。
  
## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

[Renew-CcCACertificate](renew-cccacertificate.md) 仅限于版本 1.4.2
  
[Renew-CcServerCertificate](renew-ccservercertificate.md) 仅限于版本 1.4.2
  
[Update-CcCACertificate](update-cccacertificate.md) 2.0 版及更高版本
  
[续订-CcServerCertificate](renew-ccservercertificate.md)版本2.0 和更高版本
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

