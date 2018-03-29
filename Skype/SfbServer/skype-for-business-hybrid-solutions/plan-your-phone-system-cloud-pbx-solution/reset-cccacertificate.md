---
title: 重置-CcCACertificate
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/22/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5ada7e55-df9b-4b4e-b752-2468f4e28b8a
description: 重置 CcCACertificate cmdlet 将重新安装证书颁发机构服务 AD 服务器创建新的根 CA 证书。
ms.openlocfilehash: dc86c39e844accc789ba7a3503aa6261d40e5cb2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="reset-cccacertificate"></a>重置-CcCACertificate
 
重置 CcCACertificate cmdlet 将重新安装证书颁发机构服务 AD 服务器创建新的根 CA 证书。
  
```
Reset-CcCACertificate
```

## <a name="parameters"></a>参数

无
  
## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

以下示例重新安装证书颁发机构服务 AD 服务器以创建新的根 CA 证书：
  
```
Reset-CcCACertificate
```

## <a name="detailed-description"></a>详细说明
<a name="DetailedDescription"> </a>

如果根 CA 证书已损坏或不再安全，则必须更新根 CA 证书和根 CA 颁发的所有证书。 Reset-CcCACertificate cmdlet 会吊销所有证书、卸载并重新安装证书颁发机构，然后清除与旧证书颁发机构服务相关的所有证书。 
  
有关详细信息，请参阅疑难解答云连接器部署"证书颁发机构的证书颁发给 CMS 中介服务器、 边缘服务器的内部证书临近到期或受到威胁"。
  
## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

无。Reset-CcCACertificate cmdlet 不接受主线输入。
  
## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

无。
  
## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

[续订 CcCACertificate](renew-cccacertificate.md)1.4.2 版只
  
[续订 CcServerCertificate](renew-ccservercertificate.md)1.4.2 版只
  
[更新 CcCACertificate](update-cccacertificate.md)2.0 及更高版本
  
[续订 CcServerCertificate](renew-ccservercertificate.md)2.0 及更高版本
  
[导出 CcRootCertificate](export-ccrootcertificate.md)
  

