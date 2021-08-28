---
title: 报告中的故障Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b6f3a605-e0c6-461e-b17a-41d8039ace9d
description: 摘要：了解 Skype for Business Server 中的故障列表报告。
ms.openlocfilehash: 3943c802bd6f6bce593c8fdfafb05179252712b5
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58582736"
---
# <a name="failure-list-report-in-skype-for-business-server"></a>报告中的故障Skype for Business Server 
 
**摘要：** 了解报告中的故障列表Skype for Business Server。
  
故障列表报告提供有关参与失败的对等会话或会议会话的单个参与者的信息。 此信息包括遇到问题的用户的 URI，以及与故障关联的 SIP 响应代码和诊断 ID。
  
## <a name="accessing-the-failure-list-report"></a>访问故障列表报告

通过单击"故障分布报告"中的下列任一指标来访问故障列表[Skype for Business Server：](failure-distribution-report.md)
  
- 主要诊断原因（会话）
    
- 主要形式（会话）
    
- 主要池（会话）
    
- 主要来源（会话）
    
- 主要组件（会话）
    
- 主要来源用户（会话）
    
- 主要目标用户（会话）
    
- 主要来源用户代理（会话）
    
从故障列表报告中，可以通过单击对等会话的"会话详细信息["](peer-to-peer-session-detail-report.md)指标来访问 Skype for Business Server 中的对等会话详细信息报告。 您还可以通过单击会议的"会议"指标来访问会议详细信息报告。
  
## <a name="making-the-best-use-of-the-failure-list-report"></a>充分利用故障列表报告

在故障列表报告中，只需将鼠标悬停在该值上即可查看每个响应代码或每个诊断 ID 的说明。 例如，如果你将鼠标悬停在诊断 ID 7025 上，你将看到工具提示中显示以下内容：
  
为用户创建媒体时出现内部服务器错误。
  
值得注意的是，故障列表报告未提供直接检索至少参与一个失败会话的所有用户的列表的直观方法，也不提供一种确定失败会话中通常涉及的用户的方法。  (首先，故障列表报告没有筛选功能。) 但是，如果您导出数据并将其转换为逗号分隔值文件，您可以使用 Windows PowerShell 查找类似这些问题的解答。 例如，假设您将数据保存到名为 .CSV 的文件C:\Data\Failure_List.csv。 根据该文件中保存的数据，此命令将列出至少一个失败会话中涉及的所有用户： 
  
```PowerShell
$failures = Import-Csv -Path " C:\Data\Failure_List.csv"
$failure |Sort-Object "From user" | Select-Object "From user" -Unique
```

该命令将返回类似于以下的列表：
  
<pre>
    From user
    ----
    Pilar.Ackerman@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    David.Ahs@litwareinc.com
    Ken.Myer@litwareinc.com
</pre>

以下两个命令报告每个用户参与的失败会话总数：
  
```PowerShell
$failures = Import-Csv -Path "C:\Data\Failure_List.csv"
$failures | Group-Object "From user" | Select-Object Count, Name | Sort-Object -Property Count -Descending
```

这将返回与以下内容类似的数据：
  
<pre>
Count    Name
 -----    ----
    20    Pilar.Ackerman@litwareinc.com
    20    David.Ahs@litwareinc.com
    16    Gilead.Amosnino@litwareinc.com
    16    Ken.Myero@litwareinc.com
    14    Henrik.Jensen@litwareinc.com
</pre>

## <a name="filters"></a>筛选器

无。 无法筛选故障列表报告。
  
## <a name="metrics"></a>度量标准

下表列出了每个失败呼叫的故障列表报告中提供的信息。
  
**故障列表报告指标**

|**名称**|**是否可按此项排序？**|**说明**|
|:-----|:-----|:-----|
|**报告的时间** <br/> |否  <br/> |记录报告的日期和时间。  <br/> |
|**请求** <br/> |否  <br/> |失败的 SIP 请求类型。 例如 INVITE 或 BYE。  <br/> |
|**响应代码** <br/> |否  <br/> |会议失败时发送的 SIP 响应代码。  <br/> |
|**诊断 ID** <br/> |否  <br/> |附加到 SIP 消息的唯一标识符（采用 ms-diagnostics 标头的形式），提供的信息在排查错误时通常很有帮助。  <br/> |
|**加入成本时间 (毫秒)** <br/> |否  <br/> |用户 (会议) 所需时间（以毫秒为单位）。  <br/> |
|**来源用户** <br/> |否  <br/> |发起呼叫的用户的 SIP 地址。  <br/> |
|**源用户代理** <br/> |否  <br/> |发起呼叫的用户的终结点使用的软件。  <br/> |
|**目标用户** <br/> |否  <br/> |被叫用户的 SIP 地址。  <br/> |
   

