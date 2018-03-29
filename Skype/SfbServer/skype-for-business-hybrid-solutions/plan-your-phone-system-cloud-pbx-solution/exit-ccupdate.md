---
title: 退出-CcUpdate
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 463dce1e-fb60-487d-bcf1-69e7b03ecd14
description: Exit-CcUpdate cmdlet 用于在 Skype for Business 云连接器版本主机服务器上退出更新维护模式。
ms.openlocfilehash: f7b913fd6aaa77a18df66fd86a36d5d4838f69d4
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="exit-ccupdate"></a>退出-CcUpdate
 
Exit-CcUpdate cmdlet 用于在 Skype for Business 云连接器版本主机服务器上退出更新维护模式。 
  
此 cmdlet 适用于 Skype for Business 云连接器版本 1.4.1、1.4.2。 
  
```
Exit-CcUpdate
```

## <a name="parameters"></a>参数

无
  
## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

以下命令将运行它的设备恢复到生产模式： 
  
```
Exit-CcUpdate
```

## <a name="detailed-description"></a>详细说明
<a name="DetailedDescription"> </a>

如果有通过指定 Enter-CcUpdate cmdlet 被置于维护模式的设备，Exit-CcUpdate cmdlet 可将这些设备恢复到生产模式。 
  
有关将设备置于维护模式的详细信息，请参阅 Enter-CcUpdate。
  
## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

无。Exit-CcUpdate cmdlet 不接受主线输入。
  
## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

无 
  
## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

[输入 CcUpdate](enter-ccupdate.md)
  

