---
title: 导出 CcConfigurationSampleFile
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0aaacc05-3430-4579-acbf-d7c7670c3864
description: Export-CcConfigurationSampleFile cmdlet 用于将 Skype for Business 云连接器版本示例配置文件 (.ini) 导出到云连接器设备的设备目录。你可以修改和重命名该文件以用于你的部署。
ms.openlocfilehash: f91b9c7eb8ade4e5edcf1c83c5ddef205e0f3721
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="export-ccconfigurationsamplefile"></a>导出 CcConfigurationSampleFile
 
Export-CcConfigurationSampleFile cmdlet 用于将 Skype for Business 云连接器版本示例配置文件 (.ini) 导出到云连接器设备的设备目录。你可以修改和重命名该文件以用于你的部署。
  
此 cmdlet 适用于 Skype for Business 云连接器版本 1.4.1、1.4.2。
  
```
Export-CcConfigurationSampleFile
```

## <a name="parameters"></a>参数

无
  
## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

下面的示例从 Microsoft 网站下载一个示例配置文件并将其写入云接口装置的设备目录：
  
```
Export-CcConfigurationSampleFile
```

## <a name="detailed-description"></a>详细说明
<a name="DetailedDescription"> </a>

当前版本的云接头要求您提供几个参数的.ini 文件。例如，参数如云接头组件、 组件名称、 网关参数等的虚拟机的 IP 地址。
  
此 cmdlet，云连接器的主机上运行时将从 Microsoft 网站下载示例.ini 文件与配置示例。 该 cmdlet 将文件写入云接口装置的设备目录。 设备目录通过使用 Set-CcApplianceDirectory cmdlet 来指定。
  
## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

无。Export-CcConfigurationSampleFile cmdlet 不接受主线输入。 
  
## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

无
  
## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

[一组 CcApplianceDirectory](set-ccappliancedirectory.md)
  

