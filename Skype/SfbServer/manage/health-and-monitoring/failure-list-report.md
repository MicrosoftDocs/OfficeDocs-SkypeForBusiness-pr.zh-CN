---
title: Skype 中的业务服务器的故障列表报告
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6f3a605-e0c6-461e-b17a-41d8039ace9d
description: 摘要： 了解有关的故障列表报告中 Skype 业务服务器。
ms.openlocfilehash: 3d40d7d73b6a4cb63e3885736a9a32f8b64ed989
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20992631"
---
# <a name="failure-list-report-in-skype-for-business-server"></a>Skype 中的业务服务器的故障列表报告 
 
**摘要：** 了解有关的故障列表报告中 Skype 业务服务器。
  
故障列表报告提供有关参加失败的对等会话或会议会话的各个参与者的信息。此信息包括遇到问题的用户的 URI，以及与故障相关联的 SIP 响应代码和诊断 ID。
  
## <a name="accessing-the-failure-list-report"></a>访问故障列表报告

通过单击以下指标[故障分布报告中 Skype 业务服务器](failure-distribution-report.md)上的任何访问故障列表报告：
  
- 主要诊断原因（会话）
    
- 主要形式（会话）
    
- 主要池（会话）
    
- 主要来源（会话）
    
- 主要组件（会话）
    
- 主要来源用户（会话）
    
- 主要目标用户（会话）
    
- 主要来源用户代理（会话）
    
从故障列表报告可以通过单击对等会话的会话详细信息指标来访问[对等会话中的业务服务器 Skype 的详细信息报告](peer-to-peer-session-detail-report.md)。 也可以单击会议的”会议“指标，以访问会议详细信息报告。
  
## <a name="making-the-best-use-of-the-failure-list-report"></a>充分利用故障列表报告

在故障列表报告中，您只需将鼠标置于每个响应代码或每个诊断 ID 上，即可查看它们的说明。例如，如果您将鼠标置于诊断 ID 7025 上，则将会看到在工具提示中显示以下内容：
  
为用户创建媒体时发生内部服务器错误。
  
务必注意，故障列表报告并未提供一种简单直观的方式来直接检索至少参加一次失败会话的所有用户列表，也未提供一种用来确定失败会话中最常涉及哪些用户的方法。 （一方面，Failure List Report 具有没有筛选功能。）但是，如果将数据导出，然后将其转换为以逗号分隔值文件，您可以使用 Windows PowerShell 查找类似的问题的解答。 例如，假设将数据保存到名为 C:\Data\Failure_List.csv 的 .CSV 文件。 根据该文件中所保存的数据，以下命令会列出至少一次失败会话中所涉及的所有用户： 
  
```
$failures = Import-Csv -Path " C:\Data\Failure_List.csv"
$failure |Sort-Object "From user" | Select-Object "From user" -Unique
```

该命令将返回与以下类似的列表：
  
<pre>
    From user
    ----
    Pilar.Ackerman@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    David.Ahs@litwareinc.com
    Ken.Myer@litwareinc.com
</pre>

以下两个命令将返回涉及每个用户的失败会话总数：
  
```
$failures = Import-Csv -Path "C:\Data\Failure_List.csv"
$failures | Group-Object "From user" | Select-Object Count, Name | Sort-Object -Property Count -Descending
```

这将返回与以下类似的数据：
  
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

无。您无法筛选故障列表报告。
  
## <a name="metrics"></a>指标

下表列出了各失败呼叫的故障列表报告中提供的信息。
  
**故障列表报告指标**

|**名称** - 按 WAN 链路进行筛选（筛选器位于图形右侧）。|**是否可按此项排序？**|**说明**|
|:-----|:-----|:-----|
|**报告时间** <br/> |否  <br/> |记录报告的日期和时间。  <br/> |
|**请求** <br/> |否  <br/> |失败的 SIP 请求类型。例如 INVITE 或 BYE。  <br/> |
|**响应代码** <br/> |否  <br/> |会议失败时发送的 SIP 响应代码。  <br/> |
|**诊断 ID** <br/> |否  <br/> |附加到 SIP 消息的唯一标识符（采用 ms-diagnostics 标头的形式），提供的信息在排查错误时通常很有帮助。  <br/> |
|**加入成本时间（毫秒）** <br/> |否  <br/> |用户加入会议所需的时间量（以毫秒为单位）。  <br/> |
|**来源用户** <br/> |否  <br/> |发起呼叫的用户的 SIP 地址。  <br/> |
|**源用户代理** <br/> |否  <br/> |呼叫发起用户的终结点使用的软件。  <br/> |
|**目标用户** <br/> |否  <br/> |被呼叫用户的 SIP 地址。  <br/> |
   

