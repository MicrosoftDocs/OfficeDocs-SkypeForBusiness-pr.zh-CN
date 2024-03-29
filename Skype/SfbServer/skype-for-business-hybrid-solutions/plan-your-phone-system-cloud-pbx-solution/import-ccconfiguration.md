---
title: Import-CcConfiguration
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 10/11/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 461361a0-9aa9-469d-ace0-dc70b95cd4a3
description: 将Skype for Business 云连接器版本配置从本地文件导入到云连接器主机服务器。
ms.openlocfilehash: efcc73fd5883c61753688923d44c01e10fc74ea8
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58623394"
---
# <a name="import-ccconfiguration"></a>Import-CcConfiguration
 
将Skype for Business 云连接器版本配置从本地文件导入到云连接器主机服务器。
  
```powershell
Import-CcConfiguration [-Force] [<CommonParameters>]
```

## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

以下示例将云连接器实例CloudConnector.ini设备目录复制到 %SystemDrive%\ProgramData\CloudConnector 目录：
  
```powershell
Import-CcConfiguration
```

## <a name="detailed-description"></a>详细说明
<a name="Examples"> </a>

此 cmdlet 将CloudConnector.ini连接器设备的设备目录复制到 %SystemDrive%\ProgramData\CloudConnector 目录。 设备目录是使用 Set-CcApplianceDirectory cmdlet 指定的。 此 cmdlet 将覆盖 %SystemDrive%\ProgramData\CloudConnector 中的任何现有文件。 此命令适用于云连接器版本 2.0.1 和更高版本。
  
## <a name="parameters"></a>参数
<a name="Examples"> </a>

|**参数**|**Required**|**类型**|**说明**|
|:-----|:-----|:-----|:-----|
|Force  <br/> |可选  <br/> |System.Management.Automation.SwitchParameter  <br/> |覆盖 %SystemDrive%\ProgramData\CloudConnector 中的现有文件，而不通知。  <br/> |
   
## <a name="input-types"></a>输入类型
<a name="Examples"> </a>

无。 Import-CcConfiguration cmdlet 不接受通过管道的输入。
  
## <a name="return-types"></a>返回类型
<a name="Examples"> </a>

无。
  
## <a name="see-also"></a>另请参阅
<a name="Examples"> </a>

Export-CcConfiguration
  

