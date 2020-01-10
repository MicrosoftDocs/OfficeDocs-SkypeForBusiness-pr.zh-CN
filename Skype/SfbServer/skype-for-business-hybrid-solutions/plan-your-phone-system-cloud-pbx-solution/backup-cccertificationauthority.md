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
localization_priority: Normal
ms.assetid: 47ed4559-fb63-42cd-8ecd-b7d1617e91d3
description: Backup-CcCertificationAuthority cmdlet 将 Skype for Business 云连接器版本证书颁发机构服务备份到一个文件中并将该文件保存到站点共享目录下的 CA 文件夹。
ms.openlocfilehash: f99745e1dd5e28e2d7d8d10d4d152c7ada913fbf
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003022"
---
# <a name="backup-cccertificationauthority"></a>Backup-CcCertificationAuthority
 
Backup-CcCertificationAuthority cmdlet 将 Skype for Business 云连接器版本证书颁发机构服务备份到一个文件中并将该文件保存到站点共享目录下的 CA 文件夹。
  
```powershell
Backup-CcCertificationAuthority 
```

## <a name="parameters"></a>参数

无
  
## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

以下 cmdlet 将证书颁发机构服务备份到一个文件中并将该文件保存到站点共享目录下的 CA 文件夹。
  
```powershell
Backup-CcCertificationAuthority 
```

## <a name="detailed-description"></a>详细说明
<a name="DetailedDescription"> </a>

如果你计划在发生灾难的情况下重新部署云连接器设备，或者希望将设备移动到新硬件，则证书颁发机构备份可能很有用。 该命令将云连接器证书颁发机构服务的副本从广告服务器保存到 "\<SITEROOTDIRECTORY\>\CA\SfB CCE Root. p12"。
  
## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

无。Backup-CcCertificationAuthority cmdlet 不接受主线输入。
  
## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

无
  
## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md)
  

