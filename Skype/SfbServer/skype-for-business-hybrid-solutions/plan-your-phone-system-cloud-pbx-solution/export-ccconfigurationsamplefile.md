---
title: Export-CcConfigurationSampleFile
ms.reviewer: ''
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
ms.openlocfilehash: 3154ff3492899de244c3033e4e35345132d04f20
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32233986"
---
# <a name="export-ccconfigurationsamplefile"></a>Export-CcConfigurationSampleFile
 
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

下面的示例从 Microsoft 网站下载一个示例配置文件，并将其写入云连接器装置的装置目录：
  
```
Export-CcConfigurationSampleFile
```

## <a name="detailed-description"></a>详细说明
<a name="DetailedDescription"> </a>

云连接器的当前版本要求您提供几个参数中的.ini 文件;例如，参数，如云连接器组件、 组件名称、 网关参数等的虚拟机的 IP 地址。
  
此 cmdlet，云连接符的主机计算机上运行时将从 Microsoft 网站下载示例.ini 文件与配置示例。 此 cmdlet 将文件写入到云连接器装置的装置目录。 设备目录通过使用 Set-CcApplianceDirectory cmdlet 来指定。
  
## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

无。Export-CcConfigurationSampleFile cmdlet 不接受主线输入。 
  
## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

无
  
## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

[Set-CcApplianceDirectory](set-ccappliancedirectory.md)
  

