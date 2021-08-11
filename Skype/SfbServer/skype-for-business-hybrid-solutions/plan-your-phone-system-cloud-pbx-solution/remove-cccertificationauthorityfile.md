---
title: Remove-CcCertificationAuthorityFile
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3600af8d-04de-4b9a-88ac-2491ca06494d
description: 此Remove-CcCertificationAuthorityFile cmdlet 删除网站共享目录下的 CA 文件夹中的证书颁发机构服务备份Skype for Business 云连接器版本。
ms.openlocfilehash: aaff21023a63e8933235f4c462c1152339381ca0d9571ded57f6b43742679624
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54288770"
---
# <a name="remove-cccertificationauthorityfile"></a>Remove-CcCertificationAuthorityFile
 
此 Remove-CcCertificationAuthorityFile cmdlet 删除 Skype for Business 云连接器版本 的网站共享目录下的 CA 文件夹中的证书颁发机构服务备份文件 &lt; "SiteRootDirectory &gt; \CA\SfB CCE Root.p12"。 
  
```powershell
Remove-CcCertificationAuthorityFile
```

## <a name="parameters"></a>参数

无
  
## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

以下示例删除站点共享目录下的 CA 文件夹中的证书颁发机构服务备份文件 &lt; "SiteRootDirectory &gt; \CA\SfB CCE Root.p12"：
  
```powershell
Remove-CcCertificationAuthorityFile
```

## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

无。 Remove-CcCertificationAuthorityFile cmdlet 不接受通过管道的输入。
  
## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

无
  
## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

[Backup-CcCertificationAuthority](backup-cccertificationauthority.md)
  

