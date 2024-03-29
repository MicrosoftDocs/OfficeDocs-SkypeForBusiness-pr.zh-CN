---
title: 使用监控报告中Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 733577d0-c70f-4c70-ab7b-59b89fb495a8
description: 摘要：了解监控报告中Skype for Business Server。
---

# <a name="using-monitoring-reports-in-skype-for-business-server"></a>使用监控报告中Skype for Business Server 
 
**摘要：** 了解监控报告中Skype for Business Server。
  
Skype for Business Server报告服务发布的一组标准Microsoft SQL Server报告。 这些报告可通过 Web 浏览器进行访问，它们提供了使用情况、呼叫诊断信息和媒体质量信息，所有这些信息全部基于呼叫详细记录 (CDR) 和用户体验质量 (QoE) 数据库中存储的 CDR 和 QoE 记录。
  
若要使用这些报告，必须在运行监控报告实例的计算机上安装监控SQL Server。
  
## <a name="in-this-section"></a>本部分内容

- [Using the Monitoring Dashboard in Skype for Business Server](monitoring-dashboard.md) 为管理员提供其系统运行状况和系统使用情况的快速概述。
    
- [Skype for Business Server中的系统使用情况](system-usage-reports.md)报告 基于由系统中心收集的 CDR 数据提供Skype for Business Server。
    
- [Call Diagnostic Reports (per user) in Skype for Business Server](call-diagnostic-reports-per-user.md) Provides per-user information about failed peer-to-peer and conferencing sessions.
    
- [呼叫诊断报告 Skype for Business Server](call-diagnostic-reports.md)提供失败的对等会话和会议会话的摘要信息和诊断数据。
    
- [Media Quality Diagnostic Reports in Skype for Business Server](media-quality-diagnostic-reports.md) 提供有关呼叫质量的信息，以及失败的呼叫的诊断和故障排除信息。
    
## <a name="locating-records"></a>查找记录

监控报告在任一时刻仅在屏幕上显示有限数量的记录。 屏幕上显示的实际记录数因报告而异。 若要查看屏幕上当前未显示的记录，可以使用每个报表的工具栏 (上找到的标准向前和向后控件) 使您能够分页查看数据。 您还可以快速跳转到数据集的第一页或最后一页。
  
除了使用前进和后退控件，您还可以通过在“当前页”框中键入页码，然后按 Enter 来跳转到数据集中的任一页。
  
除了提供逐页查看数据的功能，每个报告还包括查找记录的有限功能。若要根据给定值查找记录，请在“查找”框中键入该值，然后单击“查找”。报告将开始搜索数据，然后在找到您在“查找”框中输入的值的第一个实例时停止。若要查找符合搜索条件的下一条记录，请单击“下一个”。
  
如前所述，监控报告仅提供最基本的搜索功能。例如，您无法指定应在哪个字段中查找值。搜索机制自动在每条记录中的每个字段中搜索匹配值。您无法在搜索中使用通配符，所有搜索都将查找部分值。这意味着，如果您搜索 111，则搜索不仅将返回值 111，还返回值 11100、811、3112、611A5B 以及在字段中的任何位置包含值 111 的任何其他字段。
  
每个报告配置为显示一组默认记录。 例如，默认情况下，用户注册报告显示上周的用户注册活动。 有些情况下，这可能生成不返回任何记录的报告。 在这种情况下，意味着上周没有发生任何用户注册。 如果您看到消息"没有与报告筛选器匹配的结果"，请尝试更改筛选器值 (例如，将时间段更改为过去一个月而不是上周) 然后重新运行查询。 有关详细信息，请参阅本主题后面的“筛选数据”一节。
  
## <a name="filtering-data"></a>筛选数据

有时您可能希望只查看一部分记录。例如，只查看点对点会话，而非点对点会话和会议会话。同样，有时您需要减少返回的记录数。默认情况下，报告只能显示数据集中的前 1,000 条记录。为解决这些问题，大多数报告都包含大量筛选选项。例如，如果您希望仅查看 2011 年 1 月 1 日至 2011 年 1 月 15 日这个时间段的记录，则您可以在“从”框中输入 2011 年 1 月 1 日，在“到”框中输入 2011 年 1 月 15 日。然后，如果您单击“查看报告”，返回的数据将仅限于在 2011 年 1 月 1 日和 2011 年 1 月 15 日之间发生的活动。
  
可供您使用的筛选器将因您要查看的报告而异。有关特定报告的详细信息，请参阅该报告的帮助主题。
  
## <a name="exporting-data"></a>导出数据

监控报告至少提供两种导出报告中包括的数据的不同方法。可以使用每个报告顶部显示的工具栏中的“导出”选项。若要使用此选项，请从“选择格式”下拉列表中选择所需的导出格式。可使用以下格式：
  
- 具有报告数据的 XML 文件
    
- CSV（逗号分隔）
    
- Acrobat (PDF) 文件
    
- MHTML（Web 存档）
    
- Excel
    
- TIFF 文件
    
- Word
    
选择格式后，单击“导出”。出现“文件下载”对话框时，单击“保存”。在“另存为”对话框中，选择目标文件夹，输入文件名，然后单击“保存”。
  
如果安装了 Microsoft OneNote，还可以将报告数据复制到 OneNote 中。为此，请右键单击工具栏上的“查看报告”按钮。在“在 OneNote 中选择位置”对话框中，选择要将数据复制到的 OneNote 中的节，然后单击“确定”。
  

