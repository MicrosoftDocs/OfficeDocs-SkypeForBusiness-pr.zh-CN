---
title: Exit-CcUpdate
ms.reviewer: ''
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
ms.openlocfilehash: 7ac36e9cbab8e479a4ec7b070b773b3585370e8f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32234039"
---
# <a name="exit-ccupdate"></a>Exit-CcUpdate
 
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

[Enter-CcUpdate](enter-ccupdate.md)
  

