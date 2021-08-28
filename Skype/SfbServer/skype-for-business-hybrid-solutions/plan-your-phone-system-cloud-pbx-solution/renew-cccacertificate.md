---
title: Renew-CcCACertificate
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
ms.localizationpriority: medium
ms.assetid: 44da2f8d-0bf5-4f3e-b2e7-bb181dbbe646
description: 此Renew-CcCACertificate cmdlet 续订Skype for Business 云连接器版本即将过期或已过期的根 CA 证书。 在云连接器 2.0 Update-CcCACertificate版本中，此命令更改为 Update-CcCACertificate。
ms.openlocfilehash: f48839360af0be72279547e1e1f9cbd695c48b39
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58624974"
---
# <a name="renew-cccacertificate"></a>Renew-CcCACertificate
 
此Renew-CcCACertificate cmdlet 续订Skype for Business 云连接器版本即将过期或已过期的根 CA 证书。 在云连接器 2.0 Update-CcCACertificate版本中，此命令更改为 Update-CcCACertificate。
  
```powershell
Renew-CcCACertificate
```

## <a name="parameters"></a>参数

无
  
## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

以下示例续订根 CA 证书： 
  
```powershell
Renew-CcCACertificate 
```

## <a name="detailed-description"></a>详细说明
<a name="DetailedDescription"> </a>

云连接器根 CA 证书的有效期为自安装证书颁发机构服务之日起 5 年。
  
如果根证书即将过期或已过期，请运行 Renew-CcCACertificate cmdlet 来续订证书。 续订根证书后，将自动向 AD 服务器、中央管理存储和边缘服务器颁发新证书。
  
如果同一 PSTN 站点中有多个设备，请Renew-CcCACertificate PSTN 站点的所有设备中运行该 cmdlet。
  
最后一步，运行 Export-CcRootCertificate 将根证书导出到第一个设备中的本地文件，然后将导出的证书复制并安装到 PSTN 网关。
  
## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

无。 Renew-CcCACertificate cmdlet 不接受通过管道的输入。
  
## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

无
  
## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

