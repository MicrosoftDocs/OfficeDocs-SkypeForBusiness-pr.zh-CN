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
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 330367f2-22b0-43e3-b8fb-3e0d2e3b330e
description: 该Enter-CcUpdate cmdlet 通过将Skype for Business 云连接器版本服务器置于维护模式，为更新过程准备该主机服务器。 设备将立即停止所有服务，结束任何正在进行的呼叫并拒绝任何新呼叫。
ms.openlocfilehash: 26f1874ca6c0b92836716d66031945adc864d0ff
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58620758"
---
# <a name="enter-ccupdate"></a>Enter-CcUpdate

该Enter-CcUpdate cmdlet 通过将Skype for Business 云连接器版本服务器置于维护模式，为更新过程准备该主机服务器。 设备将立即停止所有服务，结束任何正在进行的呼叫并拒绝任何新呼叫。
  
```powershell
Enter-CcUpdate
```

## <a name="parameters"></a>参数

无
  
## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

以下示例通过进入维护模式为设备准备更新过程：
  
```powershell
Enter-CcUpdate 
```

## <a name="detailed-description"></a>详细说明
<a name="DetailedDescription"> </a>

该Enter-CcUpdate cmdlet 将立即停止结束任何正在进行的呼叫的所有服务，设备将拒绝任何转移到其他生产设备的新呼叫。 必须确保剩余生产设备具有足够的容量来处理来自你准备更新的设备的呼叫。
  
维护模式在设备启用了自动更新（例如，Microsoft 发布关键修补程序）时非常有用。 如果你决定关闭自动更新，但以一致的方式执行手动更新，维护模式也很有用。
  
安装更新后，可以通过运行 Exit-CcUpdate cmdlet 将设备返回到生产模式。
  
> [!NOTE]
> 如果你决定手动更新云连接器设备，则需要在 Microsoft 发布下一版本后的 60 天内更新它。 Microsoft 在新版本发布后的 60 天内支持之前发布的云连接器版本 
  
## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

无。 Enter-CCUpdate cmdlet 不接受通过管道的输入。
  
## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

无 
  
## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

[Exit-CcUpdate](exit-ccupdate.md)
  

