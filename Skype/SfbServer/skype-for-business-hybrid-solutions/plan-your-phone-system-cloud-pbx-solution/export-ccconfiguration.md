---
title: Export-CcConfiguration
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: e3775bd6-682c-4f62-aafc-974fe3a65c61
description: 将Skype for Business 云连接器版本配置导出到主机服务器上Skype for Business 云连接器版本文件。
ms.openlocfilehash: b2b3ea0171b68701b47b8ae2ed239f2e0495855b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58625004"
---
# <a name="export-ccconfiguration"></a>Export-CcConfiguration
 
将Skype for Business 云连接器版本配置导出到主机服务器上Skype for Business 云连接器版本文件。
  
```powershell
Export-CcConfiguration [-Path] <String> [<CommonParameters>]
```

## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

以下示例将 Path 参数设置为完整文件路径，将配置导出到该文件。
  
```powershell
Export-CcConfiguration -Path "C:\test\CloudConnector.ini" 
```

## <a name="detailed-description"></a>详细说明
<a name="Examples"> </a>

使用 Export-CcConfiguration cmdlet，你可以将云连接器配置保存到选定路径中的文件。 此命令在云连接器版本 2.0 版中引入。
  
## <a name="parameters"></a>参数
<a name="Examples"> </a>

|**参数**|**Required**|**类型**|**说明**|
|:-----|:-----|:-----|:-----|
|路径  <br/> |必需  <br/> |System.String  <br/> |存储云连接器配置的完整文件路径。  <br/> |
   
## <a name="input-types"></a>输入类型
<a name="Examples"> </a>

无。 Export-CcConfiguration cmdlet 不接受通过管道的输入。
  
## <a name="return-types"></a>返回类型
<a name="Examples"> </a>

无。
  
## <a name="see-also"></a>另请参阅
<a name="Examples"> </a>

Import-CcConfiguration
  

