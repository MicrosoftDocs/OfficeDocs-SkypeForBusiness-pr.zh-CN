---
title: Get-CcApplianceDirectory
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
ms.assetid: c2fda202-db2f-4122-b630-7df11a697c5f
description: 此Get-CcApplianceDirectory cmdlet 检索主服务器上Skype for Business 云连接器版本目录。 所有部署文件都存储在此目录中。
ms.openlocfilehash: 9b049b0227f923518ae682415df48afeb044c3c3
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58599857"
---
# <a name="get-ccappliancedirectory"></a>Get-CcApplianceDirectory
 
此Get-CcApplianceDirectory cmdlet 检索主服务器上Skype for Business 云连接器版本目录。 所有部署文件都存储在此目录中。 
  
此 cmdlet 适用于 Skype for Business 云连接器版本 1.4.1、1.4.2。
  
```powershell
Get-CcApplianceDirectory
```

## <a name="parameters"></a>参数

无
  
## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

以下示例显示存储云连接器组件的配置和虚拟机文件的当前文件夹：
  
```powershell
Get-CcApplianceDirectory
```

## <a name="detailed-description"></a>详细说明
<a name="DetailedDescription"> </a>

此Get-CcApplianceDirectory cmdlet 显示存储云连接器设备的所有配置和虚拟机文件、日志和外部证书的位置。
  
每个云连接器设备都有四个组件：中介服务器、中央管理存储、边缘服务器和域控制器。 默认文件夹为 C：\Users \% userprofile%\CloudConnector\ApplianceRoot。 您可以使用 Set-CCApplianceDirectory cmdlet 更改此文件夹。
  
## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

无。 Get-CCApplianceDirectory cmdlet 不接受通过管道的输入。
  
## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

该命令返回文件路径。
  
## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

[Set-CcApplianceDirectory](set-ccappliancedirectory.md)
  

