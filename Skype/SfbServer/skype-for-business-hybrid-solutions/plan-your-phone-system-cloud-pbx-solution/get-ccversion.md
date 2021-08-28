---
title: Get-CcVersion
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/30/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 7d370abd-0c01-4490-88a1-55b42e51b663
description: 返回云连接器设备的版本。 Get-CCVersion只能在云连接器的主机上使用。
ms.openlocfilehash: a94c15516ff07f908ee8094f7f76347da8c32156
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58605991"
---
# <a name="get-ccversion"></a>Get-CcVersion
 
返回云连接器设备的版本。 Get-CCVersion只能在云连接器的主机上使用。
  
```powershell
Get-CcVersion [[-VersionType] <String>] [<CommonParameters>]
```

## <a name="detailed-description"></a>详细说明

基于安装的 PowerShell 脚本、设备目录中的文件以及主机服务器上部署的虚拟机返回云连接器设备的版本。
  
## <a name="parameters"></a>参数

|**参数**|**Required**|**类型**|**说明**|
|:-----|:-----|:-----|:-----|
|VersionType  <br/> |可选  <br/> |System.String  <br/> |版本类型。 参数的值可以是 RunningScripts、RunningBits、BackupBits 或 All。 默认值为 RunningScripts。  <br/> |
   
## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

以下示例显示了打开的 PowerShell 控制台中当前运行的脚本的云连接器版本：
  
```powershell
Get-CcVersion
```

### <a name="example-2"></a>示例 2

以下示例显示部署到虚拟机的当前运行的二进制文件的云连接器版本。 可以在 Hyper-v 管理器中正在运行的虚拟机名称中查看版本：
  
```powershell
Get-CCVersion -VersionType RunningBits
```

## <a name="input-types"></a>输入类型
<a name="Examples"> </a>

无。 Get-CcVersion cmdlet 不接受通过管道的输入。
  
## <a name="return-types"></a>返回类型
<a name="Examples"> </a>

无。
  
## <a name="see-also"></a>另请参阅
<a name="Examples"> </a>

无。
  

