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
localization_priority: Normal
ms.assetid: 7d370abd-0c01-4490-88a1-55b42e51b663
description: 返回云连接器设备的版本。 Get-CCVersion 只能用于云连接器的主机。
ms.openlocfilehash: 706b480c2f8e277b7f41fe28e88cc062fea6603a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799842"
---
# <a name="get-ccversion"></a>Get-CcVersion
 
返回云连接器设备的版本。 Get-CCVersion 只能用于云连接器的主机。
  
```powershell
Get-CcVersion [[-VersionType] <String>] [<CommonParameters>]
```

## <a name="detailed-description"></a>详细说明

基于安装的 PowerShell 脚本、装置目录中的文件和在主机服务器上部署的虚拟机返回云连接器装置的版本。
  
## <a name="parameters"></a>参数

|**参数**|**必需**|**类型**|**说明**|
|:-----|:-----|:-----|:-----|
|VersionType  <br/> |可选  <br/> |System.String  <br/> |版本类型。 参数值可为 RunningScripts、RunningBits、BackupBits 或 All。 默认值为 RunningScripts。   <br/> |
   
## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

以下示例显示打开的 PowerShell 控制台中当前正在运行的脚本的云连接器版本：
  
```powershell
Get-CcVersion
```

### <a name="example-2"></a>示例 2

以下示例显示了部署到虚拟机的当前正在运行的二进制文件的云连接器版本。 可在 Hyper-v 管理器中正在运行的虚拟机名称中查看版本。
  
```powershell
Get-CCVersion -VersionType RunningBits
```

## <a name="input-types"></a>输入类型
<a name="Examples"> </a>

无。 Get-CcVersion cmdlet 不接受主线输入。
  
## <a name="return-types"></a>返回类型
<a name="Examples"> </a>

无。
  
## <a name="see-also"></a>另请参阅
<a name="Examples"> </a>

无。
  

