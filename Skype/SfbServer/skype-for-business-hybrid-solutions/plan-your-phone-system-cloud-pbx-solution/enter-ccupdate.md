---
title: 输入 CcUpdate
ms.author: crowe
author: CarolynRowe
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 330367f2-22b0-43e3-b8fb-3e0d2e3b330e
description: Enter-CcUpdate cmdlet 通过将 Skype for Business 云连接器版本主机服务器置于维护模式来为更新过程做准备。 装置 isdrained — — 也就是说，完成将现有的所有调用，但新的呼叫都将被拒绝。
ms.openlocfilehash: ed9f3f614829cd5b6bc2cd5499c6889258d67531
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="enter-ccupdate"></a>输入 CcUpdate
 
Enter-CcUpdate cmdlet 通过将 Skype for Business 云连接器版本主机服务器置于维护模式来为更新过程做准备。 该装置"排放"— — 即完成将现有的所有调用，但会拒绝新的电话。 
  
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

输入 CcUpdate cmdlet 将确保云接头装置上所有正在运行的调用将完成，但设备将拒绝任何新呼叫，将转移到其它生产装置。 使用此 cmdlet 可以在不影响最终用户呼叫的情况下更新设备。 你必须确保其余生产设备具有足够的能力来处理来自你准备更新的设备的呼叫。
  
如果你的设备启用了自动更新，例如，Microsoft 发布了关键修补程序，维护模式将很有用。如果你决定关闭自动更新，但会定期执行手动更新，维护模式也很有用。
  
安装了更新后，可以通过运行 Exit-CcUpdate cmdlet 将设备恢复到生产模式。
  
> [!NOTE]
> 如果决定手动更新云接头装置，您需要在 Microsoft 发布的下一个版本后 60 天内对其进行更新。 新版本发布后的 60 天内，Microsoft 支持云连接器的此前发布版本 
  
## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

无。Enter-CCUpdate cmdlet 不接受主线输入。
  
## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

无 
  
## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

[退出-CcUpdate](exit-ccupdate.md)
  

