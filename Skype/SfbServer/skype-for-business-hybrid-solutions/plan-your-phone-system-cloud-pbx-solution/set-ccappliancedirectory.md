---
title: Set-CcApplianceDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/21/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 6da93ddb-ca99-4b5d-9b33-3d70659730b2
description: 此Set-CcApplianceDirectory cmdlet 可设置主机Skype for Business 云连接器版本工作目录。 所有部署文件都存储在此目录中。
ms.openlocfilehash: 0f64fbb52cd12020104e98051564379d1fbc4985
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58617664"
---
# <a name="set-ccappliancedirectory"></a>Set-CcApplianceDirectory
 
此Set-CcApplianceDirectory cmdlet 可设置主机Skype for Business 云连接器版本工作目录。 所有部署文件都存储在此目录中。
  
```powershell
Set-CcApplianceDirectory[[-Path] <string>]
```

## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

以下示例将主机服务器上的工作目录设置为 c：\cloudconnector\applianceroot：
  
```powershell
Set-CcApplianceDirectory -Path "c:\cloudconnector\applianceroot"
```

## <a name="parameters"></a>参数
<a name="Examples"> </a>

|**参数**|**Required**|**类型**|**说明**|
|:-----|:-----|:-----|:-----|
| 路径 <br/> | 必需 <br/> |System.String  <br/> | 指定存储所有部署文件的路径。 <br/> |
   
## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

无。 Set-CcApplianceDirectory cmdlet 不接受通过管道的输入。
  
## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

无
  
## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

无
  

