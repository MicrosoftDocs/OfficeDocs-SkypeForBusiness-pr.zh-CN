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
localization_priority: Normal
ms.assetid: 461361a0-9aa9-469d-ace0-dc70b95cd4a3
description: 将 Skype for Business Cloud Connector Edition 配置从本地文件导入到云连接器主机服务器。
ms.openlocfilehash: 3e165250b5158513aa683770d5eb1768c0e1e29c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287277"
---
# <a name="import-ccconfiguration"></a>Import-CcConfiguration
 
将 Skype for Business Cloud Connector Edition 配置从本地文件导入到云连接器主机服务器。
  
```
Import-CcConfiguration [-Force] [<CommonParameters>]
```

## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

下面的示例将 CloudConnector 从云连接器实例的装置目录复制到%SystemDrive%\ProgramData\CloudConnector 目录:
  
```
Import-CcConfiguration
```

## <a name="detailed-description"></a>详细说明
<a name="Examples"> </a>

此 cmdlet 将 CloudConnector 从云连接器装置的装置目录复制到%SystemDrive%\ProgramData\CloudConnector 目录。 设备目录通过使用 Set-CcApplianceDirectory cmdlet 来指定。 此 cmdlet 将覆盖%SystemDrive%\ProgramData\CloudConnector. 中的任何现有文件 此命令适用于云连接器版本2.0.1 及更高版本。
  
## <a name="parameters"></a>参数
<a name="Examples"> </a>

|**参数**|**必需**|**类型**|**说明**|
|:-----|:-----|:-----|:-----|
|Force  <br/> |可选  <br/> |System.Management.Automation.SwitchParameter  <br/> |在%SystemDrive%\ProgramData\CloudConnector 中覆盖现有文件, 但不发出通知。  <br/> |
   
## <a name="input-types"></a>输入类型
<a name="Examples"> </a>

无。 CcConfiguration cmdlet 不接受流水线输入。
  
## <a name="return-types"></a>返回类型
<a name="Examples"> </a>

无。
  
## <a name="see-also"></a>另请参阅
<a name="Examples"> </a>

Export-CcConfiguration
  

