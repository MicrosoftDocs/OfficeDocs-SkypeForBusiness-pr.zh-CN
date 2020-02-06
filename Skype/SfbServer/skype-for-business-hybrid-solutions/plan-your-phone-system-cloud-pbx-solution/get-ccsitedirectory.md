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
localization_priority: Normal
ms.assetid: a243758e-6774-4437-ad2e-d5cea5f04eb6
description: Get-CcSiteDirectory cmdlet 显示存储站点级别配置文件的当前目录。 该文件夹包含基本 VHD 和 Skype for Business 云连接器版本安装文件。 此文件夹应与云连接器网站的所有其他装置共享。
ms.openlocfilehash: 6722b66f6c71feec158adaf442f9e57ef9943c84
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799862"
---
# <a name="get-ccsitedirectory"></a>Get-CcSiteDirectory
 
Get-CcSiteDirectory cmdlet 显示存储站点级别配置文件的当前目录。 该文件夹包含基本 VHD 和 Skype for Business 云连接器版本安装文件。 此文件夹应与云连接器网站的所有其他装置共享。
  
此 cmdlet 适用于云连接器版本 1.4.1、1.4.2。
  
```powershell
Get-CcSiteDirectory
```

## <a name="parameters"></a>参数

无
  
## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

以下示例显示了存储云连接器组件的配置和虚拟机文件的当前文件夹：
  
```powershell
Get-CcSiteDirectory
```

## <a name="detailed-description"></a>详细说明
<a name="DetailedDescription"> </a>

为了提供网关相关性和高可用性，可以将云连接器装置合并到网站中。 用户被分配到网站，而不是云连接器设备。 每个网站都有一个共享文件夹，其中存储了基本 VHD 和云连接器安装文件。 设备在部署过程中会使用此文件夹。 默认文件夹为 C:\Users\%userprofile%\CloudConnector\SiteRoot。 可使用 Set-CcSiteDirectory cmdlet 更改此路径。
  
## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

无。Get-CcSiteDirectory cmdlet 不接受主线输入。
  
## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

此命令返回文件路径。
  
## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

[Set-CcSiteDirectory](set-ccsitedirectory.md)
  

