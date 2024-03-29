---
title: Export-CcConfigurationSampleFile
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
ms.assetid: 0aaacc05-3430-4579-acbf-d7c7670c3864
description: 此Export-CcConfigurationSampleFile cmdlet 将Skype for Business 云连接器版本示例配置文件 (.ini) 云连接器设备的设备目录。 可以修改和重命名文件以用于部署。
ms.openlocfilehash: 409514761c3bfeccebb671d289201fc67f58d220
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58603661"
---
# <a name="export-ccconfigurationsamplefile"></a>Export-CcConfigurationSampleFile
 
此Export-CcConfigurationSampleFile cmdlet 将Skype for Business 云连接器版本示例配置文件 (.ini) 云连接器设备的设备目录。 可以修改和重命名文件以用于部署。
  
此 cmdlet 适用于 Skype for Business 云连接器版本 1.4.1、1.4.2。
  
```powershell
Export-CcConfigurationSampleFile
```

## <a name="parameters"></a>参数

无
  
## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

以下示例从 Microsoft 站点下载示例配置文件，并写入云连接器设备的设备目录：
  
```powershell
Export-CcConfigurationSampleFile
```

## <a name="detailed-description"></a>详细说明
<a name="DetailedDescription"> </a>

云连接器的当前版本要求你在云连接器文件中提供.ini参数;例如，云连接器组件虚拟机的 IP 地址、组件名称、网关参数等参数。
  
此 cmdlet 在云连接器的主机上运行时，会从 Microsoft 站点下载包含.ini示例的示例文件。 此 cmdlet 将文件写入云连接器设备的设备目录。 设备目录使用 Set-CcApplianceDirectory cmdlet 指定。
  
## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

无。 Export-CcConfigurationSampleFile cmdlet 不接受通过管道的输入。 
  
## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

无
  
## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

[Set-CcApplianceDirectory](set-ccappliancedirectory.md)
  

