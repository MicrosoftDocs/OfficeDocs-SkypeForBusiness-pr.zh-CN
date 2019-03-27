---
title: Get-CcApplianceLogDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8f16d8ea-8161-4b07-9c79-d57e786b3e78
description: Get-CcApplianceLogDirectory cmdlet 显示存储 Skype for Business 云连接器版本设备的日志的当前目录。
ms.openlocfilehash: d1298454bb347356718fdf24d6761acfea1b71b1
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30890358"
---
# <a name="get-ccappliancelogdirectory"></a>Get-CcApplianceLogDirectory
 
Get-CcApplianceLogDirectory cmdlet 显示存储 Skype for Business 云连接器版本设备的日志的当前目录。
  
此 cmdlet 适用于 Skype for Business 云连接器版本 1.4.1、1.4.2。
  
```
Get-CcApplianceLogDirectory
```

## <a name="parameters"></a>参数

无
  
## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

下面的示例显示当前文件夹存储为当前 appliance 云连接器的日志：
  
```
Get-CcApplianceLogDirectory
```

## <a name="detailed-description"></a>详细说明
<a name="DetailedDescription"> </a>

Get CcApplianceLogDirectory cmdlet 显示在当前目录为云连接器 appliance 日志存储在何处。 默认文件夹已 C:\Users\%userprofile%\CloudConnector\ApplianceRoot\Logs。 
  
可以通过使用 Set-CcApplianceDirectory cmdlet 来更改目录。 
  
请注意：没有只更改日志文件夹位置而不更改设备目录的 cmdlet。
  
## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

无。Get-CcApplianceLogDirectory cmdlet 不接受主线输入。
  
## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

此命令返回文件路径。
  
## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

[Set-CcApplianceDirectory](set-ccappliancedirectory.md)
  

