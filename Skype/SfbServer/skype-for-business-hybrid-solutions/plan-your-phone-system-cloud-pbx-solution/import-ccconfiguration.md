---
title: 导入 CcConfiguration
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 10/11/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 461361a0-9aa9-469d-ace0-dc70b95cd4a3
description: 将 Skype 商务云连接器版配置从本地文件导入到云连接器宿主服务器上。
ms.openlocfilehash: 46f4099258ce4090fa23ec980801e55f7300895f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="import-ccconfiguration"></a>导入 CcConfiguration
 
将 Skype 商务云连接器版配置从本地文件导入到云连接器宿主服务器上。
  
```

Import-CcConfiguration [-Force] [<CommonParameters>]
```

## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

下面的示例将从云连接器实例的设备目录 CloudConnector.ini 复制到 %SystemDrive%\ProgramData\CloudConnector 目录中：
  
```
Import-CcConfiguration
```

## <a name="detailed-description"></a>详细说明
<a name="Examples"> </a>

此 cmdlet 将云接口装置的设备目录 CloudConnector.ini 复制到 %SystemDrive%\ProgramData\CloudConnector 目录。 设备目录通过使用 Set-CcApplianceDirectory cmdlet 来指定。 该 cmdlet 将覆盖任何现有文件，%systemdrive%\programdata\cloudconnector 中。 本命令适用于云连接器版本 2.0.1 版及更高版本。
  
## <a name="parameters"></a>参数
<a name="Examples"> </a>

|**参数**|**必填**|**类型**|**说明**|
|:-----|:-----|:-----|:-----|
|强制  <br/> |可选  <br/> |System.Management.Automation.SwitchParameter  <br/> |覆盖现有文件中 %SystemDrive%\ProgramData\CloudConnector 而不另行通知。  <br/> |
   
## <a name="input-types"></a>输入类型
<a name="Examples"> </a>

无。 导入 CcConfiguration cmdlet 不接受管道的输入。
  
## <a name="return-types"></a>返回类型
<a name="Examples"> </a>

无。
  
## <a name="see-also"></a>另请参阅
<a name="Examples"> </a>

导出 CcConfiguration
  

