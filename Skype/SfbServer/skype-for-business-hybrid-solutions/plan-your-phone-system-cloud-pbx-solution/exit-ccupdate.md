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
localization_priority: Normal
ms.assetid: 463dce1e-fb60-487d-bcf1-69e7b03ecd14
description: 此Exit-CcUpdate cmdlet 在主机服务器上退出更新Skype for Business 云连接器版本模式。
ms.openlocfilehash: d55004f071caa67492d5368e36007d9c3c307b90aabbc33d79d1feeb4aa37356
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54288831"
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
  

