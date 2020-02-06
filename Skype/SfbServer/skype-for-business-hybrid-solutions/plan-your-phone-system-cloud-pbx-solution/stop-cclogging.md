---
title: Stop-CcLogging
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
ms.assetid: fee9eda7-ad15-40d2-b9fe-21c5462d3309
description: Stop-CcLogging cmdlet 用于停止为 Skype for Business 云连接器版本设备生成传入和传出呼叫日志。
ms.openlocfilehash: 8a012e9b1a94c3698cc61da4326eb0ccbb27bca2
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824156"
---
# <a name="stop-cclogging"></a>Stop-CcLogging
 
Stop-CcLogging cmdlet 用于停止为 Skype for Business 云连接器版本设备生成传入和传出呼叫日志。
  
```powershell
Stop-CcLogging [-RemoveCache]
```

## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

以下示例停止生成传入和传出呼叫日志： 
  
```powershell
Stop-CcLogging
```

### <a name="example-2"></a>示例 2

以下示例停止生成传入和传出呼叫日志，并清除缓存文件：
  
```powershell
Stop-CcLogging -RemoveCache
```

## <a name="detailed-description"></a>详细说明
<a name="DetailedDescription"> </a>

Stop-CcLogging cmdlet 用于停止设备上的传入和传出呼叫的日志记录。 默认情况下，日志记录将在四个小时后自动停止。
  
## <a name="parameters"></a>参数
<a name="DetailedDescription"> </a>

|**参数**|**必需**|**类型**|**说明**|
|:-----|:-----|:-----|:-----|
| RemoveCache <br/> | 可选 <br/> | System.Management.Automation.SwitchParameter <br/> |删除日志记录缓存文件。  <br/> |
   
## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

无。Stop-CcLogging cmdlet 不接受主线输入。
  
## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

无
  
## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

[Search-CcLog](search-cclog.md)
  
[Start-CcLogging](start-cclogging.md)
  

