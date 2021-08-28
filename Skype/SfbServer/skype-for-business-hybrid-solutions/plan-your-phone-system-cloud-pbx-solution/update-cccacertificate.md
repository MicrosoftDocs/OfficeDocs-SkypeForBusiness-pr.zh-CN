---
title: Update-CcCACertificate
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
ms.assetid: 5b474789-75de-443c-89bd-de89be55a1dd
description: 此Update-CcCACertificate cmdlet 续订Skype for Business 云连接器版本即将过期或已过期的根 CA 证书。
ms.openlocfilehash: 824959ab053c7eb7cc71eb60a5d6ecbeb2c7a847
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58628404"
---
# <a name="update-cccacertificate"></a>Update-CcCACertificate
 
此Update-CcCACertificate cmdlet 续订Skype for Business 云连接器版本即将过期或已过期的根 CA 证书。 
  
```powershell
Update-CcCACertificate
```

## <a name="parameters"></a>参数

无。
  
## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

以下示例续订根 CA 证书： 
  
```powershell
Update-CcCACertificate 
```

## <a name="detailed-description"></a>详细说明
<a name="DetailedDescription"> </a>

云连接器根 CA 证书的有效期为自安装证书颁发机构服务之日起 5 年。
  
如果根证书即将过期或已过期，请运行 Update-CcCACertificate cmdlet 来续订证书。 续订根证书后，将自动向 AD 服务器、中央管理存储和边缘服务器颁发新证书。
  
如果同一 PSTN 站点中有多个设备，请Update-CcCACertificate PSTN 站点的所有设备中运行该 cmdlet。
  
最后一步，运行 Export-CcRootCertificate 将根证书导出到第一个设备中的本地文件，然后将导出的证书复制并安装到 PSTN 网关。
  
此命令将替换云Renew-CcCACertificate 2.0 及更高版本中的 cmdlet。
  
## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

无。 Update-CcCACertificate cmdlet 不接受通过管道的输入。
  
## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

无。 
  
## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

