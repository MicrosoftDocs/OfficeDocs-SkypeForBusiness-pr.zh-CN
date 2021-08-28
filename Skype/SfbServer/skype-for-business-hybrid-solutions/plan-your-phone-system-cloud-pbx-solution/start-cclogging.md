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
ms.localizationpriority: medium
ms.assetid: 01b62253-2aaf-43ed-9d63-804e31edc522
description: 此Start-CcLogging cmdlet 为设备生成传入和传出呼叫Skype for Business 云连接器版本日志。
ms.openlocfilehash: 1765a3b92c8e0433725fa9757a9a4b6354006108
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58592366"
---
# <a name="start-cclogging"></a>Start-CcLogging
 
此Start-CcLogging cmdlet 为设备生成传入和传出呼叫Skype for Business 云连接器版本日志。 
  
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

此 Start-CcLogging cmdlet 为管理员提供了一种在云连接器设备中开始记录传入和传出呼叫的方法。 默认情况下，日志记录将在四小时后自动停止。
  
## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

无。 Start-CcLogging cmdlet 不接受通过管道的输入。
  
## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

无
  
## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

[Search-CcLog](search-cclog.md)
  
[Stop-CcLogging](stop-cclogging.md)
  

