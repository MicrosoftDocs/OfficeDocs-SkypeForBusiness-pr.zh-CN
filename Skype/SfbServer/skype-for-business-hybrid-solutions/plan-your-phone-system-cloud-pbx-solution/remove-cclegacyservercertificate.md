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
ms.localizationpriority: medium
ms.assetid: ff21cecb-5035-48fd-9705-11ea81ce7df6
description: 执行 Remove-CcLegacyServerCertificate cmdlet 或续订 Renew-CcCACertificate ccServerCertificate cmdlet 后，Remove-CcLegacyServerCertificate cmdlet 删除中央管理存储、中介服务器和边缘服务器上旧服务器证书。
ms.openlocfilehash: 93df3e8658cecdb4a6cc8b14d59d61a716dab8fc
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58589946"
---
# <a name="remove-cclegacyservercertificate"></a>Remove-CcLegacyServerCertificate
 
执行 Remove-CcLegacyServerCertificate cmdlet 或续订 Renew-CcCACertificate ccServerCertificate cmdlet 后，Remove-CcLegacyServerCertificate cmdlet 删除中央管理存储、中介服务器和边缘服务器上旧服务器证书。
  
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

下一个示例在续订证书后删除为中介服务器和边缘服务器颁发的证书： 
  
```powershell
Remove-CcLegacyServerCertificate -Roles @("MS", "Edge") 
```

## <a name="parameters"></a>参数
<a name="Examples"> </a>

|**参数**|**Required**|**类型**|**说明**|
|:-----|:-----|:-----|:-----|
| 角色 <br/> |可选  <br/> |System.Array  <br/> | 云连接器服务器角色数组。 <br/> |
   
## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

无。 Remove-CcLegacyServerCertificate cmdlet 不接受通过管道的输入。
  
## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

无
  
## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcCACertificate](renew-cccacertificate.md)
  
[Update-CcCACertificate](update-cccacertificate.md)
  

