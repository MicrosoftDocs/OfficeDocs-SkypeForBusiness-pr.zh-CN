---
title: Backup-CcCertificationAuthority
ms.reviewer: ''
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
ms.openlocfilehash: 2f85a4da58a586852b3331f1f8e482ee17e29e02
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32234549"
---
# <a name="backup-cccertificationauthority"></a>Backup-CcCertificationAuthority
 
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

如果您打算使用同一证书在发生灾难时为云连接器 appliance 重新部署或您要移动到新硬件的设备，证书颁发机构备份很有用。 该命令将云连接器证书颁发机构服务的副本保存从 AD 服务器到"\<SiteRootDirectory\>\CA\SfB CCE Root.p12"。
  
## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

无。Backup-CcCertificationAuthority cmdlet 不接受主线输入。
  
## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

无
  
## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md)
  

