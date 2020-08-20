---
title: 执行内容的电子数据展示调查
author: markjjo
ms.author: markjjo
manager: laurawi
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- SPO_Content
ms.reviewer: anwara
search.appverid: MET150
f1.keywords:
- NOCSH
description: 了解在需要提交所有电子数据展示信息以进行行程时要执行的操作。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 4679d8ed59ab8eec0fb856961f646d1f20049ff3
ms.sourcegitcommit: 34f407a6a40317056005e3bf38ce58f792c04810
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814108"
---
# <a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a>在 Microsoft Teams 中对内容进行电子数据展示调查

大型企业通常会面向要求使用热门合法定规定的要求将所有电子信息提交商业 (ESI) 。 可在电子数据展示调查期间搜索和使用 Microsoft Teams 内容。

## <a name="overview"></a>概述

所有 Microsoft Teams 1：1 或群组聊天都通过各自的用户的邮箱进行逐步写入。 所有标准频道邮件都将通过代表团队的组邮箱进行日记。 在标准频道中上传的文件将在 SharePoint Online 和 OneDrive for Business 的电子数据展示功能下介绍。

私人频道中的消息和文件的电子数据展示 [与](private-channels.md) 标准频道中的操作有所不同。 若要了解详细信息 [，请参阅专用频道的电子数据展示](#ediscovery-of-private-channels)。

并非所有 Teams 内容都是可发现。 下表显示了可通过电子数据展示找到的内容类型。

| 内容类型 | eDiscoverable | 注释 |
|:--- | --- |:--- |
| Teams 聊天消息 | 是 |  |
| 私人频道消息 | 是 | |
| 频道名称 | 否 | |
| 会议 IM 对话 | 是 | |
| 会议元数据<sup>1</sup> | 是 |  |
| 已编辑的邮件 | 是 | 如果用户处于保留状态，则会保留以前版本的编辑消息。 |
| 表情符号、GF、贴光 | 是 | |
| 代码片段 | 否 | |
| 聊天链接 | 是 | |
| 对喜 (、听到心等的反应包括)  | 否 | |
| 嵌入式图像 | 是 | |
| 表 | 是 | |
| 主题 | 是 | |
| 引号 | 是 | 可以搜索引发的内容。 但是，搜索结果并不指明内容已引号。 |
| 音频录制 | 否 | |

<sup>1</sup> 会议元数据包括：

- 会议或通话开始时间和结束时间以及持续时间
- 呼叫/加入和关注每个参与者的活动
- VOIP 加入/呼叫
- 匿名加入
- 联合用户加入
- 来宾用户加入

该图像显示了元数据示例。

![图像为 CVR 记录会议元数据。](media/conversationOption3.png)

下面是会议期间参与者之间的 IM 对话的示例。

![参与者之间对话的图像。](media/MeetingIMConversations.png)

![参与者之间对话的图像。](media/MeetingImConversation2.png)

若要与 Microsoft Teams 内容实现电子数据展示调查，请查看"小本电子数据展示"入门 [中的步骤](https://docs.microsoft.com/microsoft-365/compliance/get-started-core-ediscovery)1。

Microsoft Teams 数据在 Excel 电子数据展示导出输出中显示为即时消息或对话。 可以在 `.pst` Outlook 中打开该文件，以便导出后查看这些邮件。

查看该团队的 .pst 文件时，所有对话会保存在"对话历史记录"下的"工作组聊天"文件夹中。 该邮件标题包含团队名称和频道名称。 例如，下图显示了 Bob 发出的消息向 Bob 发送了制造计划团队的 Project 7 标准频道。

![Outlook 中用户邮箱中的"团队聊天"文件夹的屏幕截图](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

用户邮箱中的私有聊天存储在"对话历史记录"下的"团队聊天"文件夹中。

## <a name="ediscovery-of-private-channels"></a>电子数据展示私人频道

在私人频道中发送的消息记录将传递到所有私人频道成员的邮箱，而不是传递到组邮箱。 记录的标题已格式化为指示它们是从哪个私人频道发送的。

由于每个专用频道都具有自己的独立于父团队网站的 SharePoint 网站集，因此专用频道中的文件可独立于父团队管理。

Teams 不支持在团队中搜索单个频道的电子数据展示搜索，因此必须对整个团队进行搜索。 若要对专用频道中的内容执行电子数据展示搜索，请在以下所有团队中搜索内容，与专用频道集关联的网站集 (包括文件) 和专用频道成员 (以包括消息) 。

使用以下步骤识别专用频道中的文件和消息以包括在电子数据展示搜索中。

### <a name="include-private-channel-files-in-an-ediscovery-search"></a>在电子数据展示搜索中包括专用通道文件

执行这些步骤之前，请安装[SharePoint Online 命令行管理程序并连接到 SharePoint Online。](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

1. 运行以下操作获取与团队中的私人频道相关联的所有 SharePoint 网站集的列表。

    ```PowerShell
    Get-SPOSite
    ```

2. 运行以下 PowerShell 脚本可获取与团队和父团队组 ID 中的专用频道关联的所有 SharePoint 网站集 URL 的列表。

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url}
    ```

3. 对于每个团队或组 ID，运行以下 PowerShell 脚本以识别所有相关私人频道网站，其中$groupID是团队的组 ID。

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-an-ediscovery-search"></a>在电子数据展示搜索中包括专用通道消息

执行这些步骤之前，请确保安装 [了最新版本的 Teams PowerShell 模块](teams-powershell-overview.md) 。

1. 运行以下命令可获取团队中的私人频道列表。

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```

2. 运行以下命令可获取专用频道成员的列表。

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```

3. 将团队中每个专用频道中的所有成员的邮箱包含在电子数据展示搜索查询中。

## <a name="advanced-ediscovery"></a>高级电子数据展示

还可以使用高级电子数据展示工作流搜索和 [保留某些](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20)Microsoft Teams 内容。 电子数据展示提供一系列搜索、保持和导出功能，但是高级电子数据展示提供了更多工具，可识别数据源并分析其内容。

### <a name="advanced-ediscovery-custodian-workflow-for-teams-content"></a>Teams 内容的高级电子数据展示环境工作流

"语言管理器"可能是各种团队的成员。 你可以捕获与这些维斯使用的 Teams 内容。 有关维兰工作流的背景和说明，请参阅 ["高级电子数据展示"工作流](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20)。

添加卡通亚语后，单击"下一步" **按钮，** 然后单击"添加 **"** 按钮。 随后会显示一个窗口，提示您选择其他位置，该窗口将向您显示您的所有和员工的成员身份及其数据对应的 SharePoint 网站位置。 在所有这些数据源和团队中，可选择要用于电子数据展示的内容，然后保留该用户以及所有已在保留的数据源中。

可以选择是否包含其 Exchange 内容及其 OneDrive 内容。 Exchange 内容包括用户邮箱中的所有应用程序内容，如电子邮件、存储在其邮箱中的 Teams 内容等等。 OneDrive 内容不仅包括用户的内容，还包括存储在 OneDrive 中的所有 Teams 内容，例如 1：1 聊天、1：N 聊天以及在聊天中共享的文件。

此外，您还可以选择将该聊天机员兼容为一名团队，因此，系统包含该聊天机制可访问的频道聊天消息和文件。 此外，任何其他团队还可以与您的加人关联。 有关详细信息，请参阅 [向高级电子数据展示事例添加技能人员](https://docs.microsoft.com/microsoft-365/compliance/add-custodians-to-case)。

> [!NOTE]
> 私人频道中的消息和文件的电子数据展示 [与](private-channels.md) 标准频道中的操作有所不同。 若要了解详细信息 [，请参阅专用频道的电子数据展示](#ediscovery-of-private-channels)。

### <a name="placing-a-data-source-on-hold"></a>保留数据源

如果没有指定为回收器的特定用户，则可以保留整个数据源。 有关保留的详细信息，请参阅高级 [电子数据展示中的"管理保留](https://docs.microsoft.com/microsoft-365/compliance/managing-holds)"。

为 Teams 内容创建保留时，可以选择希望在保留中包含的所有位置。 即使用户删除或更改内容，保留会保留所有早期版本内容的副本。

您也可以使用可选查询根据关键字、日期范围、作者和其他许多条件设置保留条件。 如果不指定任何关键字，则该数据源中的所有内容将保留。

### <a name="advanced-ediscovery-searches"></a>高级电子数据展示搜索

还可以搜索 Teams 内容。 有关搜索的详细信息，请参阅"高级电子数据展示"中的 [事例数据](https://docs.microsoft.com/microsoft-365/compliance/collecting-data-for-ediscovery)。 如果即使一条邮件与搜索查询匹配，搜索也将返回整个对话。

创建搜索查询时，你可以选择"库"，以便搜索已选择的所有源。 也可以搜索不可信来源（例如未映射到用户的 Teams 网站）的非可信来源。 可选查询还可以用于缩小 Teams 内容中搜索范围的范围。

在创建搜索并选中搜索之后，将显示一个窗口，其中包含可对所选搜索执行的其他详细信息和操作。 如果单击" **统计信息"** 按钮，您可以查看有关搜索的统计信息，包括按位置类型细分、内容的原始来源，以及内容是否位于组邮箱、单个用户邮箱或 SharePoint 网站中。 因此，你可以查看有关源会为搜索结果提供怎一些细目。 也有一 **个可用的查询** 视图，以便您可以查看哪些单个关键字在您的结果中提供。

完成搜索后，可以单击"添加结果"以查看集 **合按钮** 并将其添加到评论集。 有关审阅集的详细信息，请参阅本文后面的"高级 [电](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets) 子数据展示"和"审阅 [设置"工作](#review-sets-workflow) 流。

#### <a name="normal-review-sets-and-conversation-review-sets"></a>普通审阅集和对话评审集

将搜索添加到审阅集时，可从普通审阅集或对话检查集中进行选择。

"正常的评论"集与导出类似;还为 Teams 内容提供单独 `.msg` 的文件，并以基本视图显示内容。 如果计划以后使用其他软件工具重新处理文件，通常会使用正常的审阅集。

对话审阅集提供对话的更直线程度的线程视图;它按正确的顺序一并显示相关邮件。

![对话审阅集的屏幕截图](media/conversationOptions2.png)

两种类型的审阅集均提供了这样的功能，如重新拨出。 有关查看集的详细信息，请参阅 [高级电子数据展示中的"查看对话](https://docs.microsoft.com/microsoft-365/compliance/conversation-review-sets)"。

#### <a name="collection-options"></a>集合选项

添加到审阅集时，窗口的"集合选项"部分下有多个可用选项，其中包括"**Collection Options**对话检索**选项"和****"团队对话**"。 如果启用这些选项，则作为查看集的一部分的任何单独 Teams 消息，其中附加的消息会显示在上下文中。 例如，如果查询非常具体并且只返回一条消息，因此，启用这些选项还将返回使以下一封邮件组成的值，并跟后与您的查询相匹配的消息。

许多逻辑条件用于确定邮件是否对与您的查询相匹配的邮件提供上下文。 例如，对于 Teams 内容，启用这些选项可以检索父消息以及由于消息的来看方式的所有子件。

还会选中消息时间戳。 如果一封邮件与您的查询相匹配，则缩略邮件位于 4 个小时之内的时间段内或者其后面 4 小时的邮件被视为对话的一部分，且也包含在筛选结果中。

如果必须确定哪些上下文消息将与搜索查询匹配的匹配项返回，则不需要使用这些选项。 可收集所有内容，也可加宽搜索的日期范围，以便由查询结果返回更多消息。

### <a name="review-sets-workflow"></a>查看设置工作流

您可以通过单击"审阅设置"选项卡查看现有的审阅 **集或创建新** 库。有关审阅集的详细信息，请参阅高级电子数据展示 [中的管理设置](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets)。

除了文档，还可以在查看集合中添加电子邮件、Teams 消息、Yammer 消息和其他内容。 在审阅集内，您还可以执行许多您可以在其他上下文中执行的相同操作，例如搜索内容和创建自定义查询。 这些操作仅适用于已添加到审阅集的项目。

" **管理审阅设置** "按钮提供其他选项，如分析、汇总报告、已添加的加载组数等。

若要访问数据的可视化效果和图表，请单击 **右**上角的 \> **"单个结果搜索** 个人资料"视图。 你可以单击这些图表中的边缘以交互方式选择要查询的内容类型。 例如，可以选择仅查询 Teams 内容。 你也可以保存这些查询，就像手动保存查询一样。

#### <a name="summary-view-text-view-and-annotate-view"></a>摘要视图、文本视图和注注视图

如果你单击评论集中的 Teams 对话，它会显示摘要 **视图**，其中显示整个 Teams 对话，作为你可以单独交互的消息列表。 单击邮件右侧的向下箭头可显示一个上下文菜单，该菜单允许您查看邮件详细信息或下载单个 `.msg` 文件。 单击邮件详细信息将向您显示邮件的元数据摘要或完整的元数据。

若要下载 PDF，请单击摘要视图右上方的下载按钮。

单击 **"文本** 视图"选项卡可显示 Teams 对话中提取的文本的纯文本视图。 此纯文本内容适合进行导出，您可以使用其他软件工具轻松使用该内容进行处理。

单击" **注阅视图"** 选项卡可以访问注文注明功能。 此选项卡以与 Teams 对话类相类的格式显示内容，但也有用于编辑的其他选项。 有一个可用于做笔记、在邮件上绘图或进行细化的集细边编以实现重新重复目的的移动工具。 这还有 **一个可以** 用来绘制用于将该区域突出的一个复原的框。

以下是用户间的线程对话的已重新阅读文件示例。

!["保留的文件"的屏幕截图](media/RedactedFileExample.png)

"注音" **视图选项卡底部** 是"标记 **文档"** 按钮，它显示了"标记"面板。 在此面板中，你可以将标记应用到 Teams 对话中的所有消息。 可将对话标记为响应或非响应、有权限或不特权限的形式标记它，无论它是否应包含"有趣的项目"，是否应包括在导出中，以及是否需要进一步的评论。 你也可以管理和应用其他可自定义标记。

#### <a name="action-menu"></a>操作菜单

在"审阅"设置窗口内，可以通过单击"操作导出 **"导出** \> **内容**。 导出时有许多可用选项。

要导出包含所有 Teams 邮件的所有元数据的文件，请单击以选中"加 **载文件** "复选框。 若要包括任何已应用于内容的标记，请单击以 **选择"标记"** 复选框。

使用 **本机文件选项** 以文件本机格式导出文件。 您可以选择将对话导出为单独的文件中的单个文件或所有单独的聊天消息。

" **文本文件** "选项允许保存纯文本版本的内容。 有关如何以审阅集获取 Teams 对话的纯文本视图的详细信息，请参阅上方的"摘要视图"、" [文本](#summary-view-text-view-and-annotate-view) 视图"和"注解"。

如果你按上述"摘要"视图、文本视图和"注阅视图[Summary view, text view, and annotate view](#summary-view-text-view-and-annotate-view)"部分所述应用了任何内容缩写，您可以选择"将缩略缓存"选项替换为**转换后的 PDF**选项，以将本机文件替换为转换后的副本。

你可以选择导出到 Microsoft 提供的 Azure Blob 存储容器，也可以提供自己的 Azure Blob 存储容器。

准备好开始导出过程时，单击"导出 **"** 按钮。 有关 [如何访问](https://docs.microsoft.com/microsoft-365/compliance/download-export-jobs) Azure Blob 存储容器以及导出完成后下载导出内容的详细信息，请参阅下载导出作业。

> [!NOTE]
> 导出可能需要更长的时间。 若要跟踪导出过程的状态，请退出"审 **阅"选项卡** 并单击" **导出"** 选项卡。

## <a name="related-topics"></a>相关主题

- [Microsoft 365 中的电子数据展示](https://docs.microsoft.com/microsoft-365/compliance/ediscovery)
- [Teams PowerShell 概览](teams-powershell-overview.md)
