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
description: 此Reset-CcCACertificate cmdlet 将重新安装证书颁发机构服务 AD 服务器以创建新的根 CA 证书。
ms.openlocfilehash: 8e0cb93e6f10f28df28213579674a6cda6e7e2cd1cf201319f77dc26be69de80
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54340718"
---
# <a name="reset-cccacertificate"></a>Reset-CcCACertificate
 
此Reset-CcCACertificate cmdlet 将重新安装证书颁发机构服务 AD 服务器以创建新的根 CA 证书。
  
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

如果根 CA 证书受到威胁或不再安全，则必须更新根 CA 证书以及根 CA 颁发的所有证书。 此Reset-CcCACertificate cmdlet 将吊销所有证书，卸载并重新安装证书颁发机构，然后清除与旧证书颁发机构服务相关的所有证书。 
  
有关详细信息，请参阅云连接器部署疑难解答中的"颁发给 CMS、中介服务器和边缘服务器的证书颁发机构证书或内部证书即将过期或受到威胁"。
  
## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

无。 Reset-CcCACertificate cmdlet 不接受通过管道的输入。
  
## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

无。
  
## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

[Renew-CcCACertificate](renew-cccacertificate.md) 仅版本 1.4.2
  
[Renew-CcServerCertificate](renew-ccservercertificate.md) 仅版本 1.4.2
  
[Update-CcCACertificate](update-cccacertificate.md) 版本 2.0 及更高版本
  
[Renew-CcServerCertificate](renew-ccservercertificate.md) 版本 2.0 及更高版本
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

