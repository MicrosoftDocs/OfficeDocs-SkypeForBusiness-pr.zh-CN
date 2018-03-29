---
title: 获得 CcApplianceLogDirectory
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
ms.openlocfilehash: 9b7d4853deb9ab16c7ae61279a20a30778774072
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="get-ccappliancelogdirectory"></a>获得 CcApplianceLogDirectory
 
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

下面的示例显示当前文件夹存储日志的云连接器当前装置：
  
```
Get-CcApplianceLogDirectory
```

## <a name="detailed-description"></a>详细说明
<a name="DetailedDescription"> </a>

获得 CcApplianceLogDirectory cmdlet 显示当前目录存储日志的云接口装置。 默认的文件夹是 C:\Users\%userprofile%\CloudConnector\ApplianceRoot\Logs。 
  
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

[一组 CcApplianceDirectory](set-ccappliancedirectory.md)
  

