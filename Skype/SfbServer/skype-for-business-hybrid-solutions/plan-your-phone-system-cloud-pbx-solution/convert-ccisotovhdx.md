---
title: 转换-CcIsoToVhdx
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 216abec2-d354-4ee3-9999-0a6b350a4a5f
description: Convert-CcIsoToVhdx cmdlet 使用客户提供的 Windows Server 2012 R2 ISO 文件创建基本虚拟硬盘文件 (VHDX)。该 VHDX 文件将在部署 Skype for Business 云连接器版本过程中使用。
ms.openlocfilehash: 9bf27e7161a3d5c74cc972df12246c36226be8cc
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="convert-ccisotovhdx"></a>转换-CcIsoToVhdx
 
Convert-CcIsoToVhdx cmdlet 使用客户提供的 Windows Server 2012 R2 ISO 文件创建基本虚拟硬盘文件 (VHDX)。该 VHDX 文件将在部署 Skype for Business 云连接器版本过程中使用。
  
```
Convert-CcIsoToVhdx [[-IsoFilePath] <string>] [-GeneralizeOnly] [-PauseBeforeUpdate]
```

## <a name="parameters"></a>参数

|**参数**|**必填**|**类型**|**说明**|
|:-----|:-----|:-----|:-----|
|IsoFilePath  <br/> | 必需 <br/> |System.String  <br/> |  Windows Server 2012 R2 ISO 文件的路径。 <br/> |
|GeneralizeOnly  <br/> |可选  <br/> |System.Management.Automation.SwitchParameter  <br/> |如果在 Windows 更新过程中，转换失败，可以尝试手动配置网络/代理并更新 Windows。完成手动操作后，结合 -GeneralizeOnly 参数运行此 cmdlet，它将完成其余作业。  <br/> |
|PauseBeforeUpdate  <br/> |可选  <br/> |System.Management.Automation.SwitchParameter  <br/> |要更新 Windows，可能需要对基本虚拟机执行一些手动网络/代理配置。如果提供此参数，转换过程将在 Windows 更新之前暂停。完成手动配置后，可以继续该过程。  <br/> |
   
## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

以下示例使用位于“C:\Windows_Server_2012_R2-EN-US-x64.ISO”的 Windows Server 2012 R2 ISO 文件准备基本 VHDX 文件： 
  
```
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" 
```

### <a name="example-2"></a>示例 2

如果转换 CcIsoToVhdx cmdlet 失败过程中 Windows 更新，则可能是由于不正确的网络代理配置。 可以按照错误消息中的说明操作，登录基本虚拟机来手动修复问题并更新 Windows。 完成手动操作后，重新结合 -GeneralizeOnly 参数运行该 cmdlet 以完成其余作业： 
  
```
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -GeneralizeOnly
```

### <a name="example-3"></a>示例 3

如果需要执行手动配置来更新 Windows，你可以使用 -PauseBeforeUpdate 参数。 使用此参数，Windows 更新过程之前，将暂停云连接器。 之后你可以完成手动配置并继续转换过程，如下所示：
  
```
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -PauseBeforeUpdate 
```

## <a name="detailed-description"></a>详细说明
<a name="DetailedDescription"> </a>

将 CcIsoToVhdx cmdlet 创建 VM 首先，安装云连接器取决于，然后再安装 Windows 更新某些基本组件的基础。 最后，其泛化虚拟机 (sysprep) 以获取云接口装置的虚拟机将使用基 VHDX 文件。 
  
## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

无。Convert-CcIsoToVhdx cmdlet 不接受主线输入。 
  
## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

无
  
## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

无
  

