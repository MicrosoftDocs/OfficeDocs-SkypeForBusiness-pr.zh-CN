---
title: 备份-CcCertificationAuthority
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 47ed4559-fb63-42cd-8ecd-b7d1617e91d3
description: Backup-CcCertificationAuthority cmdlet 将 Skype for Business 云连接器版本证书颁发机构服务备份到一个文件中并将该文件保存到站点共享目录下的 CA 文件夹。
ms.openlocfilehash: b3cb566dc72b3966eaa1480f3e17e4d6b46c06a2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="backup-cccertificationauthority"></a>备份-CcCertificationAuthority
 
Backup-CcCertificationAuthority cmdlet 将 Skype for Business 云连接器版本证书颁发机构服务备份到一个文件中并将该文件保存到站点共享目录下的 CA 文件夹。
  
```
Backup-CcCertificationAuthority 
```

## <a name="parameters"></a>参数

无
  
## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

以下 cmdlet 将证书颁发机构服务备份到一个文件中并将该文件保存到站点共享目录下的 CA 文件夹。
  
```
Backup-CcCertificationAuthority 
```

## <a name="detailed-description"></a>详细说明
<a name="DetailedDescription"> </a>

证书颁发机构备份非常有用，如果您计划重新部署使用同一证书发生灾难，云接头装置或如果您想要移动到新的硬件设备。 命令将云连接器证书颁发机构服务的副本保存到 AD 服务器"\<SiteRootDirectory\>\CA\SfB CCE Root.p12"。
  
## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

无。Backup-CcCertificationAuthority cmdlet 不接受主线输入。
  
## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

无
  
## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

[删除 CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md)
  

