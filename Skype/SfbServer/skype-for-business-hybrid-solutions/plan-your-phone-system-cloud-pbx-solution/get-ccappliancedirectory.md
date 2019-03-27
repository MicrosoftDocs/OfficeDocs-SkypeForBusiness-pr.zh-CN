---
title: Get-CcApplianceDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c2fda202-db2f-4122-b630-7df11a697c5f
description: Get-CcApplianceDirectory cmdlet 用于检索 Skype for Business 云连接器版本主机服务器上的工作目录。所有部署文件都存储在此目录中。
ms.openlocfilehash: bcd80018b2286865945638f66c13e4c5198346dc
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30891481"
---
# <a name="get-ccappliancedirectory"></a>Get-CcApplianceDirectory
 
Get-CcApplianceDirectory cmdlet 用于检索 Skype for Business 云连接器版本主机服务器上的工作目录。所有部署文件都存储在此目录中。 
  
此 cmdlet 适用于 Skype for Business 云连接器版本 1.4.1、1.4.2。
  
```
Get-CcApplianceDirectory
```

## <a name="parameters"></a>参数

无
  
## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

下面的示例显示当前文件夹的云连接器组件的配置和虚拟机文件的存储位置：
  
```
Get-CcApplianceDirectory
```

## <a name="detailed-description"></a>详细说明
<a name="DetailedDescription"> </a>

Get CcApplianceDirectory cmdlet 显示所有配置和虚拟机文件、 日志和外部证书云连接器装置的都存储位置。
  
每个云连接器设备具有四个组件： 中介服务器、 中央管理存储、 边缘服务器和域控制器。 默认文件夹已 C:\Users\%userprofile%\CloudConnector\ApplianceRoot。 可以使用 Set-CCApplianceDirectory cmdlet 更改此文件夹。
  
## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

无。Get-CCApplianceDirectory cmdlet 不接受主线输入。
  
## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

该命令返回文件路径。
  
## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

[Set-CcApplianceDirectory](set-ccappliancedirectory.md)
  

