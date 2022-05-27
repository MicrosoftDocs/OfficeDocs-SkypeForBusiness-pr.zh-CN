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
ms.localizationpriority: medium
ms.assetid: 47ed4559-fb63-42cd-8ecd-b7d1617e91d3
description: Backup-CcCertificationAuthority cmdlet 将Skype for Business 云连接器版本证书颁发机构服务备份到文件，并将其保存到网站共享目录下的 CA 文件夹。
ms.openlocfilehash: 4dc67fa9e1b4a9a52b3e447b09d91a74704be690
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675454"
---
# <a name="backup-cccertificationauthority"></a>Backup-CcCertificationAuthority

Backup-CcCertificationAuthority cmdlet 将Skype for Business 云连接器版本证书颁发机构服务备份到文件。 该 cmdlet 还会将其保存到网站共享目录下的 CA 文件夹。

```powershell
Backup-CcCertificationAuthority
```

## <a name="parameters"></a>参数

无

## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

以下示例将证书颁发机构服务备份到文件，并将其保存到站点共享目录下的 CA 文件夹：

```powershell
Backup-CcCertificationAuthority
```

## <a name="detailed-description"></a>详细说明
<a name="DetailedDescription"> </a>

如果计划使用相同的证书重新部署云连接器设备，则证书颁发机构备份可能很有用。 例如：

- 灾难恢复。
- 将设备移动到新硬件。

该命令将云连接器证书颁发机构服务的副本从 AD Server 保存到 `"<SiteRootDirectory>\CA\SfB CCE Root.p12"`。

## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

无。 Backup-CcCertificationAuthority cmdlet 不接受管道输入。

## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

无

## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md)
  