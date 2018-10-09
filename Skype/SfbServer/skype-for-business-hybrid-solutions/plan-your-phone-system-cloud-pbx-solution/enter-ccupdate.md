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
description: Enter-CcUpdate cmdlet 通过将 Skype for Business 云连接器版本主机服务器置于维护模式来为更新过程做准备。 装置 isdrained — 即，所有现有呼叫将完成，但新呼叫被拒绝。
ms.openlocfilehash: f9b789bbd76bd3405617dc170af0695f9cbe94ed
ms.sourcegitcommit: baa4ecf69bdcf499b5b724246f3e9f45c6ca3b7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/08/2018
ms.locfileid: "25450509"
---
# <a name="enter-ccupdate"></a>输入 CcUpdate
 
Enter-CcUpdate cmdlet 通过将 Skype for Business 云连接器版本主机服务器置于维护模式来为更新过程做准备。 装置为"排空"— 即，所有现有呼叫将完成，但新呼叫被拒绝。 
  
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

Enter CcUpdate cmdlet 将立即停止所有服务结束所有后续呼叫，则设备将拒绝任何新的呼叫，被转接到其他生产 appliance。 你必须确保其余生产设备具有足够的能力来处理来自你准备更新的设备的呼叫。
  
如果你的设备启用了自动更新，例如，Microsoft 发布了关键修补程序，维护模式将很有用。如果你决定关闭自动更新，但会定期执行手动更新，维护模式也很有用。
  
安装了更新后，可以通过运行 Exit-CcUpdate cmdlet 将设备恢复到生产模式。
  
> [!NOTE]
> 如果决定手动更新云连接器 appliance，您需要在 Microsoft 发布了下一版本后 60 天内对其进行更新。 Microsoft 支持发布的新版本后 60 天以前发布版云连接器 
  
## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

无。Enter-CCUpdate cmdlet 不接受主线输入。
  
## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

无 
  
## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

[退出 CcUpdate](exit-ccupdate.md)
  

