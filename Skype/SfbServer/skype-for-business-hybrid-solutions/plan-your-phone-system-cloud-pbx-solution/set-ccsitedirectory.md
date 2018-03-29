---
title: 一组 CcSiteDirectory
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/23/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1cd89fd-6968-4ace-a4aa-c4105231cf7b
description: Set-CcSiteDirectory cmdlet 用于设置将存储 Skype for Business 云连接器版本的站点级别配置文件的目录。 该文件夹将包含基本 VHD 和云连接器配置文件。
ms.openlocfilehash: d34945a17f32c275240e2cef0435f6e0ca3e63a0
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="set-ccsitedirectory"></a>一组 CcSiteDirectory
 
Set-CcSiteDirectory cmdlet 用于设置将存储 Skype for Business 云连接器版本的站点级别配置文件的目录。 该文件夹将包含基本 VHD 和云连接器配置文件。
  
此 cmdlet 适用于 Skype for Business 云连接器版本 1.4.1、1.4.2。
  
```
Set-CcSiteDirectory [[-Path] <string>]
```

## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

下面的示例设置站点根目录下\\SiteShare\CloudConnector:
  
```
Set-CcSiteDirectory -Path "\\SiteShare\CloudConnector"
```

## <a name="detailed-description"></a>详细说明
<a name="DetailedDescription"> </a>

若要提供网关关联和高可用性，可以在网站中组合云接头装置。 用户被分配给站点而不是云接口装置。 每个站点都有一个共享文件夹，用于存储基本 VHD 和云连接器安装文件。 装置在部署期间使用此文件夹。 应与云连接器站点中的所有其他设备共享此文件夹。
  
默认的文件夹是 C:\Users\%userprofile%\CloudConnector\SiteRoot。 可以使用 Get-CcSiteDirectory cmdlet 查看路径。
  
## <a name="parameters"></a>参数
<a name="DetailedDescription"> </a>

|**参数**|**必填**|**类型**|**说明**|
|:-----|:-----|:-----|:-----|
| 路径 <br/> | 必需 <br/> | System.String <br/> |提供了存储云连接器网站文件的文件夹的路径。  <br/> |
   
## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

无。 Set-CcSiteDirectory cmdlet 不接受主线输入。
  
## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

无
  
## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

[获得 CcSiteDirectory](get-ccsitedirectory.md)
  

