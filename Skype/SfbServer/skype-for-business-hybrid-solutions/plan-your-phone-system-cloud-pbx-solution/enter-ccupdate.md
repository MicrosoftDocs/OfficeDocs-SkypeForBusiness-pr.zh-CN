---
title: Enter-CcUpdate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
ms.date: 3/31/2017
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 330367f2-22b0-43e3-b8fb-3e0d2e3b330e
description: CcUpdate cmdlet 通过将其置于维护模式来为更新过程准备 Skype for business 云连接器 Edition 主机服务器。 本装置将立即停止所有服务、停止任何正在进行的呼叫，并拒绝任何新呼叫。
ms.openlocfilehash: 3ff4c1543e3e882a7ccbaf0b9a216ce902a77c5f
ms.sourcegitcommit: 9fd23cf0e03dd8fcf7ed04ef09dcdac048ebb44a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2019
ms.locfileid: "34740056"
---
# <a name="enter-ccupdate"></a>Enter-CcUpdate

CcUpdate cmdlet 通过将其置于维护模式来为更新过程准备 Skype for business 云连接器 Edition 主机服务器。 本装置将立即停止所有服务、停止任何正在进行的呼叫，并拒绝任何新呼叫。
  
```
Enter-CcUpdate
```

## <a name="parameters"></a>参数

无
  
## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

以下示例通过进入维护模式来为更新过程准备设备：
  
```
Enter-CcUpdate 
```

## <a name="detailed-description"></a>详细说明
<a name="DetailedDescription"> </a>

CcUpdate cmdlet 将立即停止所有终止任何正在进行的通话的服务，并且装置将拒绝任何新呼叫，这些呼叫将被转移到其他生产装置。 你必须确保剩余的生产设备有足够的容量来处理你准备更新的装置的通话。
  
如果你的设备启用了自动更新，例如，Microsoft 发布了关键修补程序，维护模式将很有用。如果你决定关闭自动更新，但会定期执行手动更新，维护模式也很有用。
  
安装更新后，设备可以通过运行 CcUpdate cmdlet 恢复到生产模式。
  
> [!NOTE]
> 如果你决定手动更新云连接器设备，则需要在 Microsoft 发布下一个版本后的60天内更新它。 发布新版本后，Microsoft 支持以前发布的适用于60天的云连接器版本 
  
## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

无。Enter-CCUpdate cmdlet 不接受主线输入。
  
## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

无 
  
## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

[Exit-CcUpdate](exit-ccupdate.md)
  

