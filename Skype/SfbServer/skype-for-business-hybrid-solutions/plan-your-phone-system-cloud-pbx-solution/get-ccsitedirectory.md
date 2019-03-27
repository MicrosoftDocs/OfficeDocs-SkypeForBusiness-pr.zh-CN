---
title: Get-CcSiteDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a243758e-6774-4437-ad2e-d5cea5f04eb6
description: Get-CcSiteDirectory cmdlet 显示存储站点级别配置文件的当前目录。 该文件夹包含基本 VHD 和 Skype for Business 云连接器版本安装文件。 应与云连接器网站的所有其他设备共享该文件夹。
ms.openlocfilehash: d0869f3cbd1c43e523107a0ff8dce6fd769889a8
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30882395"
---
# <a name="get-ccsitedirectory"></a>Get-CcSiteDirectory
 
Get-CcSiteDirectory cmdlet 显示存储站点级别配置文件的当前目录。 该文件夹包含基本 VHD 和 Skype for Business 云连接器版本安装文件。 应与云连接器网站的所有其他设备共享该文件夹。
  
此 cmdlet 适用于云连接器版本 1.4.1、1.4.2。
  
```
Get-CcSiteDirectory
```

## <a name="parameters"></a>参数

无
  
## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

下面的示例显示当前文件夹云连接器组件配置和虚拟机文件的存储位置：
  
```
Get-CcSiteDirectory
```

## <a name="detailed-description"></a>详细说明
<a name="DetailedDescription"> </a>

若要提供网关关联和高可用性，可以在网站中结合云连接器 appliance。 用户分配到网站而不是云连接器 appliance。 每个网站具有基本 VHD 和云连接器安装文件的存储位置的共享的文件夹。 设备在部署过程中会使用此文件夹。 默认文件夹已 C:\Users\%userprofile%\CloudConnector\SiteRoot。 可使用 Set-CcSiteDirectory cmdlet 更改此路径。
  
## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

无。Get-CcSiteDirectory cmdlet 不接受主线输入。
  
## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

此命令返回文件路径。
  
## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

[Set-CcSiteDirectory](set-ccsitedirectory.md)
  

