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
ms.localizationpriority: medium
ms.assetid: fee9eda7-ad15-40d2-b9fe-21c5462d3309
description: Stop-CcLogging cmdlet 停止为设备生成传入和传出呼叫Skype for Business 云连接器版本日志。
ms.openlocfilehash: cfa07602f8465ce3c931010f835f52acc44e2ee2
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58580337"
---
# <a name="stop-cclogging"></a>Stop-CcLogging
 
Stop-CcLogging cmdlet 停止为设备生成传入和传出呼叫Skype for Business 云连接器版本日志。
  
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

下一个示例将停止生成传入和传出呼叫日志并清理缓存文件：
  
```powershell
Stop-CcLogging -RemoveCache
```

## <a name="detailed-description"></a>详细说明
<a name="DetailedDescription"> </a>

此Stop-CcLogging cmdlet 可停止在设备中记录传入和传出呼叫。 默认情况下，日志记录将在四小时后自动停止。
  
## <a name="parameters"></a>参数
<a name="DetailedDescription"> </a>

|**参数**|**Required**|**类型**|**说明**|
|:-----|:-----|:-----|:-----|
| RemoveCache <br/> | 可选 <br/> | System.Management.Automation.SwitchParameter <br/> |删除日志记录缓存文件。  <br/> |
   
## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

无。 Stop-CcLogging cmdlet 不接受通过管道的输入。
  
## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

无
  
## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

[Search-CcLog](search-cclog.md)
  
[Start-CcLogging](start-cclogging.md)
  

