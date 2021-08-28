---
title: Get-CcApplianceLogDirectory
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
ms.assetid: 8f16d8ea-8161-4b07-9c79-d57e786b3e78
description: 此Get-CcApplianceLogDirectory cmdlet 显示存储设备日志Skype for Business 云连接器版本的当前目录。
ms.openlocfilehash: 826599ab785d8b4d74f0792c6091b2a5e78b74e3
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58580356"
---
# <a name="get-ccappliancelogdirectory"></a>Get-CcApplianceLogDirectory
 
此Get-CcApplianceLogDirectory cmdlet 显示存储设备日志Skype for Business 云连接器版本的当前目录。
  
此 cmdlet 适用于 Skype for Business 云连接器版本 1.4.1、1.4.2。
  
```powershell
Get-CcApplianceLogDirectory
```

## <a name="parameters"></a>参数

无
  
## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

以下示例显示存储云连接器当前设备的日志的当前文件夹：
  
```powershell
Get-CcApplianceLogDirectory
```

## <a name="detailed-description"></a>详细说明
<a name="DetailedDescription"> </a>

此Get-CcApplianceLogDirectory cmdlet 显示存储云连接器设备的日志的当前目录。 默认文件夹为 C：\Users \% userprofile%\CloudConnector\ApplianceRoot\Logs。 
  
您可以使用 Set-CcApplianceDirectory cmdlet 更改目录。 
  
注意：没有仅更改日志文件夹位置而不更改设备目录的 cmdlet。
  
## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

无。 Get-CcApplianceLogDirectory cmdlet 不接受通过管道的输入。
  
## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

此命令返回文件路径。
  
## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

[Set-CcApplianceDirectory](set-ccappliancedirectory.md)
  

