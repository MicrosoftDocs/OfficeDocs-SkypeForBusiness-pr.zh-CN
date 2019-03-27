---
title: Get-CcSiteLogDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6625494d-1b63-4d99-a589-c8c69c4addba
description: Get-CcSiteLogDirectory cmdlet 显示存储 Skype for Business 云连接器版本的站点级别日志的当前目录。
ms.openlocfilehash: c4354920ac25d076e550c5eda3a641eef0c8b900
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30886125"
---
# <a name="get-ccsitelogdirectory"></a>Get-CcSiteLogDirectory
 
Get-CcSiteLogDirectory cmdlet 显示存储 Skype for Business 云连接器版本的站点级别日志的当前目录。 
  
此 cmdlet 适用于 Skype for Business 云连接器版本 1.4.1、1.4.2。
  
```
Get-CcSiteLogDirectory
```

## <a name="parameters"></a>参数

无
  
## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

下面的示例显示当前文件夹存储云连接器网站的日志文件：
  
```
Get-CcSiteLogDirectory
```

## <a name="detailed-description"></a>详细说明
<a name="DetailedDescription"> </a>

默认文件夹已 C:\Users\%userprofile%\CloudConnector\SiteRoot\Logs。 可以通过运行 Set-CcSiteDirectory cmdlet 来更改文件夹。 没有只更改日志文件夹位置而不更改站点目录的单独 cmdlet。
  
## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

无。Get-CcSiteLogDirectory cmdlet 不接受主线输入。
  
## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

该命令返回文件路径。
  
## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

[Set-CcSiteDirectory](set-ccsitedirectory.md)
  

