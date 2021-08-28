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
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: bbae05f9-d8de-40dc-8968-d225dcde80e4
description: 此Search-CcLog cmdlet 搜索设备日志目录中的Skype for Business 云连接器版本呼叫日志。
ms.openlocfilehash: b96e0bea7c8a7ac9d3a12c135c828440eea9fb32
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58618688"
---
# <a name="search-cclog"></a>Search-CcLog
 
此Search-CcLog cmdlet 搜索设备日志目录中的Skype for Business 云连接器版本呼叫日志。
  
```powershell
Search-CcLog [[-StartTime] <datetime>] [[-EndTime] <datetime>] [[-FileName] <string>]
```

## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

以下示例使用默认文件名搜索设备日志目录中的传入和传出呼叫日志：
  
```powershell
Search-CcLog -StartTime "8/31/2012 8:00AM" -EndTime "8/31/2012 6:00PM"
```

### <a name="example-2"></a>示例 2

下一个示例使用给定的文件路径和名称搜索传入和传出呼叫日志：
  
```powershell
Search-CcLog -StartTime "8/31/2012 8:00AM" -EndTime "8/31/2012 6:00PM" -FileName "C:\Log\LogFile.log"
```

## <a name="detailed-description"></a>详细说明
<a name="DetailedDescription"> </a>

Search-CsClsLogging cmdlet 提供用于搜索集中日志记录服务所生成的日志文件的命令行选项。
  
## <a name="parameters"></a>参数
<a name="DetailedDescription"> </a>

|**参数**|**Required**|**类型**|**说明**|
|:-----|:-----|:-----|:-----|
|StartTime  <br/> | 必需 <br/> |System.Datetime  <br/> | 要搜索的日志条目的开始日期和时间。 指定本地时区。 <br/> |
|EndTime  <br/> |必需  <br/> |System.Datetime  <br/> |要搜索的日志项目的结束日期和时间。 指定本地时区。  <br/> |
|FileName  <br/> |必需  <br/> |System.String  <br/> |指定包含搜索结果的文本文件的完整路径。  <br/> |
   
## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

无。 Search-CcLog cmdlet 不接受通过管道的输入。
  
## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

无
  
## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

[Start-CcLogging](start-cclogging.md)
  
[Stop-CcLogging](stop-cclogging.md)
  

