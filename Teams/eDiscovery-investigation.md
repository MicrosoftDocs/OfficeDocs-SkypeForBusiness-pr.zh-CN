---
title: 对内容进行电子数据展示调查
author: LolaJacobsen
ms.author: hakank
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- SPO_Content
ms.reviewer: anach
search.appverid: MET150
f1.keywords:
- NOCSH
description: 了解需要执行电子数据展示时需要执行的操作，如需要提交所有电子存储的法律程序存储信息。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 67006fba94a58514fa33c91edd0a46312396b31a
ms.sourcegitcommit: 0835f4335ebc8ca53b8348e0b1b906828eb4e13e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2020
ms.locfileid: "43918580"
---
# <a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a>在 Microsoft Teams 中对内容进行电子数据展示调查

大型企业经常面临高处罚的法律诉讼，要求提交所有电子存储的信息（ESI）。 Microsoft 团队内容可在电子数据展示调查期间进行搜索和使用。

## <a name="overview"></a>概述

将向相应用户的邮箱中记录所有团队1:1 或群组聊天。 所有标准频道消息都将记录到代表团队的组邮箱。 在标准频道中上载的文件包含在 SharePoint Online 和 OneDrive for business 的电子数据展示功能下方。

电子数据展示[专用频道](private-channels.md)中的消息和文件的工作方式与在标准信道中的工作方式不同。 若要了解详细信息，请参阅[电子数据展示专用频道](#ediscovery-of-private-channels)。

并非所有团队内容都是 eDiscoverable。 下表显示了可以通过电子数据展示找到的内容类型。

| 内容类型 | eDiscoverable | 注释 |
|:--- | --- |:--- |
| 团队聊天消息 | 是 | 聊天来自聊天的消息，其中来宾用户是1:1 或1： N 聊天中的唯一参与者不 eDiscoverable。 |
| 录音 | 否 | |
| 专用频道消息 | 否 | |
| 表情符号、Gif、贴纸 | 是 | |
| 代码片段 | 否 | |
| 聊天链接 | 是 | |
| 反应（赞、红心大战等） | 否 | |
| 已编辑邮件 | 是 | 如果用户处于保留状态，将保留已编辑邮件的以前版本。 |
| 内联图像 | 是 | |
| 题注 | 是 | |
| 主题 | 是 | |
| 引述 | 是 | 已引用内容可搜索。 但是，搜索结果不表示内容已加引号。 |
| 频道的名称 | 否 | |

- 若要使用 Microsoft 团队内容执行电子数据展示调查，请查看["安全 & 合规中心" 链接中的 "管理电子数据展示事例"](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da)中的步骤1。

- Microsoft 团队数据将在 Excel 电子数据展示导出输出中显示为即时消息或对话。 可以在 Outlook 中`.pst`打开文件以在导出后查看这些邮件。

    查看团队的`.pst`文件时，请注意所有对话都保存在 "对话历史记录" 下的 "工作组聊天" 文件夹中。 邮件标题包含团队名称和频道名称。 例如，下面的图像显示来自 Bob 的一条消息，messaged 制造规范团队的项目7标准频道。

    ![Outlook 中的用户邮箱中的工作组聊天文件夹的屏幕截图](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

- 用户邮箱中的私人聊天存储在 "对话历史记录" 下的 "工作组聊天" 文件夹中。

## <a name="ediscovery-of-private-channels"></a>专用频道的电子数据展示

在私人频道中发送的消息记录将传递到所有私人频道成员的邮箱，而不是传递到组邮箱。 记录的标题已格式化为指示它们是从哪个私人频道发送的。

由于每个专用频道都有自己的 SharePoint 网站集，独立于父团队网站，因此专用通道中的文件独立于父团队进行管理。

团队不支持团队中的单个频道的电子数据展示搜索，因此必须搜索整个团队。 若要在专用频道中执行电子数据展示搜索，请在团队中搜索与专用频道相关联的网站集（包括文件）和专用频道成员的邮箱（包括邮件）。

使用以下步骤标识要包括在电子数据展示搜索中的专用通道中的文件和邮件。

### <a name="include-private-channel-files-in-an-ediscovery-search"></a>在电子数据展示搜索中包括专用信道文件

在执行这些步骤之前，请安装[Sharepoint Online 命令行管理程序并连接到 SharePoint online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)。

1. 运行以下操作以获取与团队中的专用通道相关联的所有 SharePoint 网站集的列表。

    ```PowerShell
    Get-SPOSite
    ```

2. 运行以下 PowerShell 脚本，获取与团队和父团队组 ID 中的专用通道相关联的所有 SharePoint 网站集 Url 的列表。

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url} 
    ```

3. 对于每个团队或组 ID，运行以下 PowerShell 脚本来标识所有相关专用通道网站，其中 $groupID 是团队的组 ID。

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-an-ediscovery-search"></a>在电子数据展示搜索中包括专用信道消息

在执行这些步骤之前，请确保安装了[最新版本的团队 PowerShell 模块](teams-powershell-overview.md)。

1. 运行以下操作以获取团队中的专用通道的列表。

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```

2. 运行以下操作以获取专用通道成员的列表。

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```

3. 将团队中每个专用频道的所有成员的邮箱添加为电子数据展示搜索查询的一部分。

## <a name="advanced-ediscovery"></a>高级电子数据展示

还可以使用[高级电子数据展示工作流](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20)搜索和保留某些 Microsoft 团队内容。 虽然电子数据展示提供了一系列搜索、保留和导出功能，但高级电子数据展示为合规性管理员提供了更多用于识别数据源和分析其内容的工具。

### <a name="advanced-ediscovery-custodian-workflow-for-teams-content"></a>工作组内容的高级电子数据展示保管人工作流

保管人可能是各种团队的成员。 你可以捕获与这些保管人相关的团队内容。 有关保管人工作流的背景和说明，请参阅[高级电子数据展示工作流](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20)。

添加保管人后，单击 "**下一步**" 按钮，然后单击 "**添加**" 按钮。 此时将显示一个窗口，提示你选择其他位置，这将向你显示所有保管人成员的成员身份以及对应的 SharePoint 网站位置。 从所有这些数据源和团队中，你可以选择要用于电子数据展示的内容，然后将该用户和你已标识的所有数据源置于保持状态。

你可以选择是否包括 Exchange 内容、其 OneDrive 内容或两者。 Exchange 内容包括用户邮箱中的所有应用程序内容，例如其电子邮件、存储在其邮箱中的团队内容等。 OneDrive 内容不仅包括用户的内容，还包括存储在 OneDrive 中的所有团队内容，如1:1 聊天、1： N 聊天和聊天中共享的文件。

你还可以选择将保管人成员与保管人成员相关联，以便包括保管人对其具有访问权限的频道聊天消息和文件。 此外，任何其他团队都可以与管理员关联。 有关详细信息，请参阅[将保管人添加到高级电子数据展示事例](https://docs.microsoft.com/microsoft-365/compliance/add-custodians-to-case)。

> [!NOTE]
> 电子数据展示[专用频道](private-channels.md)中的消息和文件的工作方式与在标准信道中的工作方式不同。 若要了解详细信息，请参阅[电子数据展示专用频道](#ediscovery-of-private-channels)。

### <a name="placing-a-data-source-on-hold"></a>将数据源置于保持状态

如果没有特定用户指定为保管人，则可以将整个数据源置于保持状态。 有关保留的详细信息，请参阅[管理高级电子数据展示中的保留](https://docs.microsoft.com/microsoft-365/compliance/managing-holds)。

为团队内容创建保留时，可以选择要包含在保留中的所有位置。 即使用户正在删除或更改内容，保留仍将保留该内容所有以前版本的副本。

你还可以使用可选查询基于关键字、日期范围、作者和许多其他条件设置保留条件。 如果不指定关键字，则来自该数据源的所有内容都将受到保留。

### <a name="advanced-ediscovery-searches"></a>高级电子数据展示搜索

还可以搜索团队内容。 有关搜索的详细信息，请参阅[在高级电子数据展示中收集事例的数据](https://docs.microsoft.com/microsoft-365/compliance/collecting-data-for-ediscovery)。 如果即使一条消息与搜索查询匹配，搜索也会返回整个对话。

创建搜索查询时，可以选择 "保管人"，以便搜索已选择的所有源。 您还可以搜索非 custodial 源，如未映射到用户的团队网站。 还可使用可选查询缩小团队内容中的搜索范围。

创建搜索并选中它后，将显示一个窗口，其中包含可在所选搜索上执行的其他详细信息和操作。 如果单击 "**统计**" 按钮，则可以查看有关搜索的统计信息，包括根据位置类型、内容的原始源以及内容位于组邮箱、单个用户邮箱还是 SharePoint 网站中的细目。 这样，您就可以看到对搜索结果有哪些来源的细目。 还有可用的 "**查询**" 视图，以便你可以查看哪些单个关键字对你的结果有影响。

完成搜索后，您可以单击 "**将结果添加到审阅集**" 按钮并将其添加到审阅集。 有关审阅集的详细信息，请参阅本文后面的[管理高级电子数据展示和审阅中的审阅集](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets)[工作流](#review-sets-workflow)。

#### <a name="normal-review-sets-and-conversation-review-sets"></a>常规审阅集和对话审阅集

向审阅集添加搜索时，可以从 "常规" 审阅集或 "对话审阅" 集进行选择。

常规审阅集类似于导出;它为团队内容`.msg`提供单个文件，并在基本视图中显示内容。 当你计划使用其他软件工具在以后重新处理文件时，通常会使用常规的审阅集。

对话审核集提供了更直观的对话视图;它以正确的顺序显示相关邮件。

在两种类型的审阅集中都提供了密文之类的功能。

有关审阅集的详细信息，请参阅[在高级电子数据展示中查看对话](https://docs.microsoft.com/microsoft-365/compliance/conversation-review-sets)。

#### <a name="collection-options"></a>收集选项

添加到审阅集时，窗口的 "**集合选项**" 部分下有多个选项可用作复选框，包括**对话检索选项**和**团队对话**。 如果你启用这些选项，则属于你的审阅集的任何单个团队邮件也将显示在其上下文中的其他消息周围。 例如，如果你的查询非常具体且仅返回一条消息，则启用这些选项还将返回指向和关注与查询匹配的消息的多条消息。

许多逻辑条件用于确定其他消息是否提供与查询匹配的消息的上下文。 例如，对于团队内容，启用这些选项将检索父消息和所有子消息，因为消息的串接方式。

还会检查消息时间戳。 如果某条消息与你的查询相匹配，则在4小时以内或在4小时范围内关注它的相邻消息将被视为对话的一部分，并且也包含在结果中。

如果你必须确定将返回哪些上下文消息与搜索查询匹配项，则无需使用这些选项。 你可以收集所有内容，也可以放宽搜索的日期范围，以便更多邮件作为查询结果返回。

### <a name="review-sets-workflow"></a>审阅集工作流

通过单击 "**审阅集**" 选项卡，可以查看现有的审阅集或创建新的审阅集。有关审阅集的详细信息，请参阅[在高级电子数据展示中管理审阅集](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets)。

除了文档之外，您还可以将电子邮件、团队邮件、Yammer 邮件和其他内容添加到你的审阅集。 在审阅集内，你也可以执行可以在其他上下文中执行的许多相同的操作，例如搜索内容和创建自定义查询。 这些操作仅适用于已添加到审阅集的项目。

"**管理审阅集**" 按钮提供其他选项，例如 "分析"、"摘要报告"、已添加的加载集等。

若要访问数据的可视化效果和图表，**请单击右上** \>角的 "**搜索个人资料" 视图**。 可以单击这些图表中的楔形，以交互方式选择要查询的内容类型。 例如，您可以选择仅查询团队内容。 您也可以像保存手动编写的查询一样保存这些查询。

#### <a name="summary-view-text-view-and-annotate-view"></a>摘要视图、文本视图和批注视图

如果您单击 "审阅" 集中的团队对话，它将显示 "**摘要" 视图**，其中显示整个团队对话，作为可单独与之交互的消息列表。 单击消息右侧的向下箭头以显示上下文菜单，可在其中查看消息详细信息或下载单个`.msg`文件。 单击 "消息详细信息" 将显示元数据的摘要或消息的完整元数据。

若要下载 PDF，请单击 "摘要" 视图右上角的 "下载" 按钮。

单击 "**文本视图**" 选项卡以显示 "团队对话" 的提取文本的纯文本视图。 这适合导出，并且你可以使用其他软件工具轻松处理此提取的文本。

单击 "**批注视图**" 选项卡以访问 "批注" 功能。 此选项卡以类似团队对话的格式显示内容，但还有其他编辑选项。 有一个铅笔工具可用于在邮件上进行笔记、绘制邮件或进行细化的 scratching，以供密文使用。 还有一种**区域密文**工具，可用于绘制黑色缩小区域的矩形，并将其标记为 "Redacted"。

"**批注视图**" 选项卡底部是 "**标记文档**" 按钮，用于显示 "标记" 面板。 在此面板中，你可以将标记应用到团队对话中的所有邮件。 你可以将对话标记为 "响应" 或 "无响应"、"特权" 或 "无权限"，无论它是否包含 "感兴趣的项目"、是否应包括在导出中以及是否需要进一步查看。 您还可以管理和应用其他可自定义的标记。

#### <a name="action-menu"></a>操作菜单

在 "审阅集" 窗口中，可以通过单击 "**操作** \> **导出**" 来导出内容。 导出时有许多选项可供使用。

若要导出包含所有团队邮件的所有元数据的文件，请单击以选中 "**加载文件**" 复选框。 若要将已应用于内容的任何标记包含在您的文件中，请单击以选中 "**标记**" 复选框。

使用 "**本机文件**" 选项以其本机格式导出文件。 你可以选择将对话作为一个文件或所有单独的聊天消息导出到各自的单独文件中。

"**文本文件**" 选项允许保存纯文本版本的内容。 有关如何在审阅集中获取团队对话的纯文本视图的详细信息，请参阅上面的[摘要视图、文本视图和批注视图](#summary-view-text-view-and-annotate-view)。

如果在上面的 "[摘要视图"、"文本视图" 和 "批注视图](#summary-view-text-view-and-annotate-view)" 部分中所述对内容应用了任何密文，则可以选择 "将**redacted natives 替换为转换的 pdf** " 选项，以将本机文件替换为 PDF 中的已转换副本。

你可以选择导出到 Microsoft 提供的 Azure blob 存储容器，或者你可以提供你自己的 Azure Blob 存储容器。

准备好开始导出过程时，请单击 "**导出**" 按钮。 导出完成后，有关如何访问 Azure blob 存储容器和下载导出的内容的详细信息，请参阅[下载导出作业](https://docs.microsoft.com/microsoft-365/compliance/download-export-jobs)。

> [!NOTE]
> 导出可能会延长一段时间。 若要跟踪导出过程的状态，请退出 "**审阅集**" 选项卡，然后单击 "**导出**" 选项卡。

## <a name="related-topics"></a>相关主题

- [Microsoft 365 中的电子数据展示](https://docs.microsoft.com/microsoft-365/compliance/ediscovery)
- [Teams PowerShell 概览](teams-powershell-overview.md)
