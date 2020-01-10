---
title: Search-CcLog
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bbae05f9-d8de-40dc-8968-d225dcde80e4
description: Search-CcLog cmdlet 用于在 Skype for Business 云连接器版本设备日志目录中搜索传入和传出呼叫日志。
ms.openlocfilehash: c248720931ef1c15d633c51bb6daa6c414631a18
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003232"
---
# <a name="search-cclog"></a>Search-CcLog
 
Search-CcLog cmdlet 用于在 Skype for Business 云连接器版本设备日志目录中搜索传入和传出呼叫日志。
  
```powershell
Search-CcLog [[-StartTime] <datetime>] [[-EndTime] <datetime>] [[-FileName] <string>]
```

## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

以下示例使用默认文件名在设备日志目录中搜索传入和传出呼叫日志：
  
```powershell
Search-CcLog -StartTime "8/31/2012 8:00AM" -EndTime "8/31/2012 6:00PM"
```

### <a name="example-2"></a>示例 2

以下示例使用给定文件路径和名称搜索传入和传出呼叫日志：
  
```powershell
Search-CcLog -StartTime "8/31/2012 8:00AM" -EndTime "8/31/2012 6:00PM" -FileName "C:\Log\LogFile.log"
```

## <a name="detailed-description"></a>详细说明
<a name="DetailedDescription"> </a>

Search-CsClsLogging cmdlet 提供用于搜索集中日志记录服务所生成的日志文件的命令行选项。
  
## <a name="parameters"></a>参数
<a name="DetailedDescription"> </a>

|**参数**|**必需**|**类型**|**说明**|
|:-----|:-----|:-----|:-----|
|StartTime  <br/> | 必需 <br/> |System.Datetime  <br/> | 要搜索的日志条目的开始日期和时间。指定本地时区。 <br/> |
|EndTime  <br/> |必需  <br/> |System.Datetime  <br/> |要搜索的日志条目的结束日期和时间。指定本地时区。  <br/> |
|FileName  <br/> |必需  <br/> |System.String  <br/> |指定包含搜索结果的文本文件的完整路径。  <br/> |
   
## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

无。Search-CcLog cmdlet 不接受主线输入。
  
## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

无
  
## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

[Start-CcLogging](start-cclogging.md)
  
[Stop-CcLogging](stop-cclogging.md)
  

