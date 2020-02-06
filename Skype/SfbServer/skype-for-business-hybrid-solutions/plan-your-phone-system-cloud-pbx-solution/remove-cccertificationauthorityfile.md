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
description: CcCertificationAuthorityFile cmdlet 将在适用于 Skype for business 云连接器版本的网站共享目录下的 CA 文件夹中删除证书颁发机构服务备份文件。
ms.openlocfilehash: 49a8f0f313b4153288ebdf037a41dc92f30e60d6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824288"
---
# <a name="remove-cccertificationauthorityfile"></a>Remove-CcCertificationAuthorityFile
 
CcCertificationAuthorityFile cmdlet 将在 Skype for business Cloud Connector Edition 的网站共享&lt;目录&gt;下的 CA 文件夹中删除证书颁发机构服务备份文件 "SiteRootDirectory \CA\SfB CCE Root. p12"。 
  
```powershell
Remove-CcCertificationAuthorityFile
```

## <a name="parameters"></a>参数

无
  
## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

以下示例将在网站共享目录下的 CA 文件夹&lt;中&gt;删除证书颁发机构服务备份文件 "SiteRootDirectory \CA\SfB CCE Root. p12"：
  
```powershell
Remove-CcCertificationAuthorityFile
```

## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

无。Remove-CcCertificationAuthorityFile cmdlet 不接受主线输入。
  
## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

无
  
## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

[Backup-CcCertificationAuthority](backup-cccertificationauthority.md)
  

