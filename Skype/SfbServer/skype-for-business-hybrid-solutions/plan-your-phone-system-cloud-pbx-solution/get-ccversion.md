---
title: 获得 CcVersion
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/30/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7d370abd-0c01-4490-88a1-55b42e51b663
description: 返回云连接器设备的版本。 Get-CCVersion 只能用于云连接器的主机。
ms.openlocfilehash: 8391264603a73e3f594122dcdd2eb62b9ba19978
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="get-ccversion"></a>获得 CcVersion
 
返回云连接器设备的版本。 Get-CCVersion 只能用于云连接器的主机。
  
```
Get-CcVersion [[-VersionType] <String>] [<CommonParameters>]
```

## <a name="detailed-description"></a>详细说明

在装置的目录中，并在主机服务器上部署虚拟机返回云接头装置基于 PowerShell 脚本安装，文件的版本。
  
## <a name="parameters"></a>参数

|**参数**|**必填**|**类型**|**说明**|
|:-----|:-----|:-----|:-----|
|VersionType  <br/> |可选  <br/> |System.String  <br/> |版本类型。 参数值可为 RunningScripts、RunningBits、BackupBits 或 All。 默认值为 RunningScripts。  <br/> |
   
## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

下面的示例演示在您打开 PowerShell 控制台云连接器当前正在运行的脚本的版本：
  
```
Get-CcVersion
```

### <a name="example-2"></a>示例 2

下面的示例演示云连接器版本部署到虚拟机的当前正在运行的二进制文件。 可在 Hyper-v 管理器中正在运行的虚拟机名称中查看版本。
  
```
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
  

