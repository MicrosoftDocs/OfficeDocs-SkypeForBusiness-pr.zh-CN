---
title: 获得 CcSiteDirectory
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a243758e-6774-4437-ad2e-d5cea5f04eb6
description: Get-CcSiteDirectory cmdlet 显示存储站点级别配置文件的当前目录。 该文件夹包含基本 VHD 和 Skype for Business 云连接器版本安装文件。 应与云连接器站点的所有其他设备共享此文件夹。
ms.openlocfilehash: e75e20a18960510bf75a8ca4cfc97ffd9daa894f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="get-ccsitedirectory"></a>获得 CcSiteDirectory
 
Get-CcSiteDirectory cmdlet 显示存储站点级别配置文件的当前目录。 该文件夹包含基本 VHD 和 Skype for Business 云连接器版本安装文件。 应与云连接器站点的所有其他设备共享此文件夹。
  
此 cmdlet 适用于云连接器版本 1.4.1、1.4.2。
  
```
Get-CcSiteDirectory
```

## <a name="parameters"></a>参数

无
  
## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

下面的示例显示当前云连接器组件的配置和虚拟机文件的存储位置的文件夹：
  
```
Get-CcSiteDirectory
```

## <a name="detailed-description"></a>详细说明
<a name="DetailedDescription"> </a>

若要提供网关关联和高可用性，可以在网站中组合云接头装置。 用户被分配给站点而不是云接口装置。 每个站点都有一个共享文件夹，用于存储基本 VHD 和云连接器安装文件。 装置在部署期间使用此文件夹。 默认的文件夹是 C:\Users\%userprofile%\CloudConnector\SiteRoot。 可使用 Set-CcSiteDirectory cmdlet 更改此路径。
  
## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

无。Get-CcSiteDirectory cmdlet 不接受主线输入。
  
## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

此命令返回文件路径。
  
## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

[一组 CcSiteDirectory](set-ccsitedirectory.md)
  

