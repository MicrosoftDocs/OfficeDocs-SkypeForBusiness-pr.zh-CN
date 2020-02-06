---
title: Start-CcLogging
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
ms.assetid: 01b62253-2aaf-43ed-9d63-804e31edc522
description: Start-CcLogging cmdlet 用于为 Skype for Business 云连接器版本设备生成传入和传出呼叫日志。
ms.openlocfilehash: bf84b55484e7f1d4f557730408676e337063a040
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824166"
---
# <a name="start-cclogging"></a>Start-CcLogging
 
Start-CcLogging cmdlet 用于为 Skype for Business 云连接器版本设备生成传入和传出呼叫日志。 
  
```powershell
Start-CcLogging
```

## <a name="parameters"></a>参数

无
  
## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

以下示例生成传入和传出呼叫日志：
  
```powershell
Start-CcLogging
```

## <a name="detailed-description"></a>详细说明
<a name="DetailedDescription"> </a>

CcLogging cmdlet 为管理员提供了一种在云连接器设备上开始记录传入和传出调用的方法。 默认情况下，日志记录将在四个小时后自动停止。
  
## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

无。Start-CcLogging cmdlet 不接受主线输入。
  
## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

无
  
## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

[Search-CcLog](search-cclog.md)
  
[Stop-CcLogging](stop-cclogging.md)
  

