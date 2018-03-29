---
title: Stop CcLogging
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fee9eda7-ad15-40d2-b9fe-21c5462d3309
description: Stop CcLogging cmdlet 将停止为商务云连接器版装置 Skype 生成传入和传出的呼叫日志。
ms.openlocfilehash: abecc5acc6a454b2965fbf79caadb23f2256e4cd
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="stop-cclogging"></a>Stop CcLogging
 
Stop CcLogging cmdlet 将停止为商务云连接器版装置 Skype 生成传入和传出的呼叫日志。
  
```
Stop-CcLogging [-RemoveCache]
```

## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

以下示例停止生成传入和传出呼叫日志： 
  
```
Stop-CcLogging
```

### <a name="example-2"></a>示例 2

以下示例停止生成传入和传出呼叫日志，并清除缓存文件：
  
```
Stop-CcLogging -RemoveCache
```

## <a name="detailed-description"></a>详细说明
<a name="DetailedDescription"> </a>

Stop-CcLogging cmdlet 用于停止设备上的传入和传出呼叫的日志记录。默认情况下，日志记录将在四个小时后自动停止。
  
## <a name="parameters"></a>参数
<a name="DetailedDescription"> </a>

|**参数**|**必填**|**类型**|**说明**|
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

[搜索-CcLog](search-cclog.md)
  
[开始-CcLogging](start-cclogging.md)
  

