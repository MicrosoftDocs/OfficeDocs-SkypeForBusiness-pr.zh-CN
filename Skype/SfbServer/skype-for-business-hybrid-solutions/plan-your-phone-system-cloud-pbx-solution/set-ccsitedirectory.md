---
title: Set-CcSiteDirectory
ms.reviewer: ''
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
ms.openlocfilehash: 1c03d0f91b3a724df6ce61d216138bb281fb0b87
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885580"
---
# <a name="set-ccsitedirectory"></a>Set-CcSiteDirectory
 
Set-CcSiteDirectory cmdlet 用于设置将存储 Skype for Business 云连接器版本的站点级别配置文件的目录。 该文件夹将包含基本 VHD 和云连接器配置文件。
  
此 cmdlet 适用于 Skype for Business 云连接器版本 1.4.1、1.4.2。
  
```
Set-CcSiteDirectory [[-Path] <string>]
```

## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

下面的示例将网站的根目录下设置为\\SiteShare\CloudConnector:
  
```
Set-CcSiteDirectory -Path "\\SiteShare\CloudConnector"
```

## <a name="detailed-description"></a>详细说明
<a name="DetailedDescription"> </a>

若要提供网关关联和高可用性，可以在网站中结合云连接器 appliance。 用户分配到网站而不是云连接器 appliance。 每个网站具有基本 VHD 和云连接器安装文件的存储位置的共享的文件夹。 设备在部署过程中会使用此文件夹。 应与云连接器网站中的所有其他设备共享该文件夹。
  
默认文件夹已 C:\Users\%userprofile%\CloudConnector\SiteRoot。 可以使用 Get-CcSiteDirectory cmdlet 查看路径。
  
## <a name="parameters"></a>参数
<a name="DetailedDescription"> </a>

|**参数**|**必需**|**类型**|**说明**|
|:-----|:-----|:-----|:-----|
| 路径 <br/> | 必需 <br/> | System.String <br/> |提供存储云连接器网站文件的文件夹的路径。  <br/> |
   
## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

无。 Set-CcSiteDirectory cmdlet 不接受主线输入。
  
## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

无
  
## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

[Get-CcSiteDirectory](get-ccsitedirectory.md)
  

