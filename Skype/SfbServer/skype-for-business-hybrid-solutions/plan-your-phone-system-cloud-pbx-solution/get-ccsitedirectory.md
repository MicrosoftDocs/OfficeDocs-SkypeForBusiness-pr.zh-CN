---
title: Get-CcSiteDirectory
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
ms.assetid: a243758e-6774-4437-ad2e-d5cea5f04eb6
description: 此Get-CcSiteDirectory cmdlet 显示存储站点级别配置文件的当前目录。 该文件夹包含基本 VHD 和 Skype for Business 云连接器版本安装文件。 此文件夹应该与云连接器站点的所有其他设备共享。
ms.openlocfilehash: 04b1460b9743c3d19ca4db77f67d057d400f400b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58616368"
---
# <a name="get-ccsitedirectory"></a>Get-CcSiteDirectory
 
此Get-CcSiteDirectory cmdlet 显示存储站点级别配置文件的当前目录。 该文件夹包含基本 VHD 和 Skype for Business 云连接器版本安装文件。 此文件夹应该与云连接器站点的所有其他设备共享。
  
此 cmdlet 适用于云连接器版本 1.4.1、1.4.2。
  
```powershell
Get-CcSiteDirectory
```

## <a name="parameters"></a>参数

无
  
## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

以下示例显示存储云连接器组件的配置和虚拟机文件的当前文件夹：
  
```powershell
Get-CcSiteDirectory
```

## <a name="detailed-description"></a>详细说明
<a name="DetailedDescription"> </a>

为了提供网关相关性和高可用性，可以在站点中组合使用云连接器设备。 将用户分配给站点，而不是云连接器设备。 每个站点都有一个共享文件夹，其中存储基本 VHD 和云连接器安装文件。 设备在部署期间使用此文件夹。 默认文件夹为 C：\Users \% userprofile%\CloudConnector\SiteRoot。 可以使用 cmdlet 更改Set-CcSiteDirectory路径。
  
## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

无。 Get-CcSiteDirectory cmdlet 不接受通过管道的输入。
  
## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

此命令返回文件路径。
  
## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

[Set-CcSiteDirectory](set-ccsitedirectory.md)
  

