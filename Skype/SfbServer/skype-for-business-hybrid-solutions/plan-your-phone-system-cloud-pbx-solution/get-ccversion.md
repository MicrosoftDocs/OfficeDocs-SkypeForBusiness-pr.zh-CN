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
localization_priority: Normal
ms.assetid: 7d370abd-0c01-4490-88a1-55b42e51b663
description: 返回云连接器设备的版本。 Get-CCVersion 只能用于云连接器的主机。
ms.openlocfilehash: b002b4a9f0cae34a2cdd7b8817e86a3e4ec2eb9a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287249"
---
# <a name="get-ccversion"></a>Get-CcVersion
 
返回云连接器设备的版本。 Get-CCVersion 只能用于云连接器的主机。
  
```
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

以下示例显示打开的 PowerShell 控制台中当前正在运行的脚本的云连接器版本:
  
```
Get-CcVersion
```

### <a name="example-2"></a>示例 2

以下示例显示了部署到虚拟机的当前正在运行的二进制文件的云连接器版本。 可在 Hyper-v 管理器中正在运行的虚拟机名称中查看版本。
  
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
  

