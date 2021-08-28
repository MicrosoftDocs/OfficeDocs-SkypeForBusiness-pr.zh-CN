---
title: Exit-CcUpdate
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
ms.assetid: 463dce1e-fb60-487d-bcf1-69e7b03ecd14
description: 此Exit-CcUpdate cmdlet 在主机服务器上退出更新Skype for Business 云连接器版本模式。
ms.openlocfilehash: 11499950a3332de31fe045ea23c1aa8f567da072
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58625014"
---
# <a name="exit-ccupdate"></a>Exit-CcUpdate
 
此Exit-CcUpdate cmdlet 在主机服务器上退出更新Skype for Business 云连接器版本模式。 
  
此 cmdlet 适用于 Skype for Business 云连接器版本 1.4.1、1.4.2。 
  
```powershell
Exit-CcUpdate
```

## <a name="parameters"></a>参数

无
  
## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

以下命令将运行该设备的设备重新置于生产模式下： 
  
```powershell
Exit-CcUpdate
```

## <a name="detailed-description"></a>详细说明
<a name="DetailedDescription"> </a>

如果有通过指定 Enter-CcUpdate cmdlet 进入维护模式的设备，Exit-CcUpdate cmdlet 会重新进入生产模式。 
  
有关将设备置于维护模式详细信息，请参阅 Enter-CcUpdate。
  
## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

无。 Exit-CcUpdate cmdlet 不接受通过管道的输入。
  
## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

无 
  
## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

[Enter-CcUpdate](enter-ccupdate.md)
  

