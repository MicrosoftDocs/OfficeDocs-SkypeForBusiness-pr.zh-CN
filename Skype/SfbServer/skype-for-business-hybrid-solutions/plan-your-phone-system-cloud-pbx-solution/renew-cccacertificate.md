---
title: Renew-CcCACertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 44da2f8d-0bf5-4f3e-b2e7-bb181dbbe646
description: Renew-CcCACertificate cmdlet 可续订即将过期或已过期的 Skype for Business 云连接器版本根 CA 证书。 此命令已更改为云连接器 2.0 和更高版本中的更新 CcCACertificate。
ms.openlocfilehash: 616abb35d577b816368854396a201b9f07b40d12
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32250882"
---
# <a name="renew-cccacertificate"></a>Renew-CcCACertificate
 
Renew-CcCACertificate cmdlet 可续订即将过期或已过期的 Skype for Business 云连接器版本根 CA 证书。 此命令已更改为云连接器 2.0 和更高版本中的更新 CcCACertificate。
  
```
Renew-CcCACertificate
```

## <a name="parameters"></a>参数

无
  
## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

以下示例续订根 CA 证书： 
  
```
Renew-CcCACertificate 
```

## <a name="detailed-description"></a>详细说明
<a name="DetailedDescription"> </a>

云连接器根 CA 证书的有效期是自安装证书颁发机构服务之日起的 5 年。
  
如果根证书即将过期或已过期，请运行 Renew-CcCACertificate cmdlet 来续订证书。续订了根证书后，将自动为 AD 服务器、中央管理存储及边缘服务器颁发新证书。
  
如果同一 PSTN 站点中有多台设备，请在同一 PSTN 站点中的所有设备上运行 Renew-CcCACertificate cmdlet。
  
最后一步，运行 Export-CcRootCertificate 以将根证书导出为第一台设备上的本地文件，然后将导出的证书复制并安装到 PSTN 网关。
  
## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

无。Renew-CcCACertificate cmdlet 不接受主线输入。
  
## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

无
  
## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

