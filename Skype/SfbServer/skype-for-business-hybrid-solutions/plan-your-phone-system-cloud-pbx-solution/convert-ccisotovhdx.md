---
title: Convert-CcIsoToVhdx
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
ms.assetid: 216abec2-d354-4ee3-9999-0a6b350a4a5f
description: 该 Convert-CcIsoToVhdx cmdlet 使用客户提供的 R2 ISO (VHDX) 创建基本虚拟Windows Server 2012硬盘文件。 VHDX 文件将在部署部署期间Skype for Business 云连接器版本。
ms.openlocfilehash: dcbe1b4939fd99d6200217925bc52b72f6868873
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58635066"
---
# <a name="convert-ccisotovhdx"></a>Convert-CcIsoToVhdx
 
该 Convert-CcIsoToVhdx cmdlet 使用客户提供的 R2 ISO (VHDX) 创建基本虚拟Windows Server 2012硬盘文件。 VHDX 文件将在部署部署期间Skype for Business 云连接器版本。
  
```powershell
Convert-CcIsoToVhdx [[-IsoFilePath] <string>] [-GeneralizeOnly] [-PauseBeforeUpdate]
```

## <a name="parameters"></a>参数

|**参数**|**Required**|**类型**|**说明**|
|:-----|:-----|:-----|:-----|
|IsoFilePath  <br/> | 必需 <br/> |System.String  <br/> | R2 ISO Windows Server 2012的路径。 <br/> |
|GeneralizeOnly  <br/> |可选  <br/> |System.Management.Automation.SwitchParameter  <br/> |如果在更新过程中转换Windows失败，可以尝试配置网络/代理并手动Windows更新。 完成手动工作后，可以使用 -GeneralizeOnly 参数运行此 cmdlet，它将完成剩余的作业。  <br/> |
|PauseBeforeUpdate  <br/> |可选  <br/> |System.Management.Automation.SwitchParameter  <br/> |若要更新Windows，可能需要在基本 VM 上进行一些手动网络/代理配置。 如果提供此参数，转换过程Windows更新之前暂停。 完成手动配置后，可以继续执行该过程。  <br/> |
   
## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

以下示例使用位于"C：\Windows_Server_2012_R2-EN-US-x64.ISO"的 Windows Server 2012 R2 ISO 文件准备基本 VHDX 文件： 
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" 
```

### <a name="example-2"></a>示例 2

如果 Convert-CcIsoToVhdx cmdlet 在更新Windows失败，可能是因为网络/代理配置不正确。 你可以按照错误消息中的说明操作并登录到基本虚拟机，以修复问题并手动Windows更新。 完成手动工作后，使用 -GeneralizeOnly 参数再次运行 cmdlet 以完成其余作业： 
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -GeneralizeOnly
```

### <a name="example-3"></a>示例 3

如果需要手动配置才能更新Windows，可以使用 -PauseBeforeUpdate 参数。 通过此参数，云连接器将在更新过程Windows暂停。 然后，您可以完成手动配置并恢复转换过程，如下所示：
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -PauseBeforeUpdate 
```

## <a name="detailed-description"></a>详细说明
<a name="DetailedDescription"> </a>

该Convert-CcIsoToVhdx cmdlet 首先创建基本 VM，安装云连接器依赖的一些基本组件，然后安装Windows更新。 最后，它将 (sysprep) ，获取云连接器设备的虚拟机将使用的基 VHDX 文件。 
  
## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

无。 Convert-CcIsoToVhdx cmdlet 不接受通过管道的输入。 
  
## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

无
  
## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

无
  

