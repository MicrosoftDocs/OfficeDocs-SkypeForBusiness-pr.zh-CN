---
title: Set-CcSiteDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/23/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b1cd89fd-6968-4ace-a4aa-c4105231cf7b
description: 此Set-CcSiteDirectory cmdlet 设置用于存储Skype for Business 云连接器版本配置文件的目录。 该文件夹将包含基本 VHD 和云连接器配置文件。
ms.openlocfilehash: e5685ac8c203338365141a4a7ba59daa82a06ef0
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58610529"
---
# <a name="set-ccsitedirectory"></a>Set-CcSiteDirectory
 
此Set-CcSiteDirectory cmdlet 设置用于存储Skype for Business 云连接器版本配置文件的目录。 该文件夹将包含基本 VHD 和云连接器配置文件。
  
此 cmdlet 适用于 Skype for Business 云连接器版本 1.4.1、1.4.2。
  
```powershell
Set-CcSiteDirectory [[-Path] <string>]
```

## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

以下示例将站点根目录设为 \\ SiteShare\CloudConnector：
  
```powershell
Set-CcSiteDirectory -Path "\\SiteShare\CloudConnector"
```

## <a name="detailed-description"></a>详细说明
<a name="DetailedDescription"> </a>

为了提供网关相关性和高可用性，可以在站点中组合使用云连接器设备。 将用户分配给站点，而不是云连接器设备。 每个站点都有一个共享文件夹，其中存储基本 VHD 和云连接器安装文件。 设备在部署期间使用此文件夹。 此文件夹应该与云连接器站点中的所有其他设备共享。
  
默认文件夹为 C：\Users \% userprofile%\CloudConnector\SiteRoot。 可以使用 cmdlet 查看路径Get-CcSiteDirectory cmdlet。
  
## <a name="parameters"></a>参数
<a name="DetailedDescription"> </a>

|**参数**|**Required**|**类型**|**说明**|
|:-----|:-----|:-----|:-----|
| 路径 <br/> | 必需 <br/> | System.String <br/> |提供将存储云连接器站点文件的文件夹的路径。  <br/> |
   
## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

无。 Set-CcSiteDirectory cmdlet 不接受通过管道的输入。
  
## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

无
  
## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

[Get-CcSiteDirectory](get-ccsitedirectory.md)
  

