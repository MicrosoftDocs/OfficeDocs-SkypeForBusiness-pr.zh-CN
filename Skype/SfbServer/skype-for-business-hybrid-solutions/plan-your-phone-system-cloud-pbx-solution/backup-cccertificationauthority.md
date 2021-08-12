---
title: Backup-CcCertificationAuthority
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 47ed4559-fb63-42cd-8ecd-b7d1617e91d3
description: 此Backup-CcCertificationAuthority cmdlet 将 Skype for Business 云连接器版本 证书颁发机构服务备份到文件，并保存到网站共享目录下的 CA 文件夹。
ms.openlocfilehash: abf94977abe2a0c3548b549ae0101ae399e124769eaaa9f05aabf203c69656a3
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54282954"
---
# <a name="backup-cccertificationauthority"></a>Backup-CcCertificationAuthority
 
此Backup-CcCertificationAuthority cmdlet 将 Skype for Business 云连接器版本 证书颁发机构服务备份到文件，并保存到网站共享目录下的 CA 文件夹。
  
```powershell
Backup-CcCertificationAuthority 
```

## <a name="parameters"></a>参数

无
  
## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

以下示例将证书颁发机构服务备份到文件，并保存到站点共享目录下的 CA 文件夹中：
  
```powershell
Backup-CcCertificationAuthority 
```

## <a name="detailed-description"></a>详细说明
<a name="DetailedDescription"> </a>

如果你计划在灾难时重新部署具有相同证书的云连接器设备，或者如果你想要将设备移动到新硬件，证书颁发机构备份可能很有用。 此命令将云连接器证书颁发机构服务的副本从 AD 服务器保存到" \<SiteRootDirectory\> \CA\SfB CCE Root.p12"。
  
## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

无。 Backup-CcCertificationAuthority cmdlet 不接受通过管道的输入。
  
## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

无
  
## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md)
  

