---
title: 对内容进行电子数据展示调查
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
description: 了解需要执行电子数据展示时（例如，需要提交所有电子数据存储信息进行法律诉讼时）应执行的操作。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: aa6b1212fda3983cc612885e41aa1131bb6f496d
ms.sourcegitcommit: 0b584d40e95cbde33cee3691edadb12156d72fb5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "49980456"
---
# <a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a>在 Microsoft Teams 中对内容进行电子数据展示调查

大型企业通常面临高损失诉讼，这些诉讼要求提交所有电子 (ESI) 。 可在电子数据展示调查期间搜索和使用 Microsoft Teams 内容。

## <a name="overview"></a>概述

所有 Microsoft Teams 1：1 或群组聊天都记录到相应用户的邮箱。 所有标准频道邮件都记录在代表团队的组邮箱中。 在标准频道中上传的文件包括在 SharePoint Online 和 OneDrive for Business 的电子数据展示功能下。

私人频道中 [消息和文件](private-channels.md) 电子数据展示的工作方式与标准通道中的工作方式不同。 若要了解有关详细信息，请参阅 [专用通道的电子数据展示](#ediscovery-of-private-channels)。

并非所有 Teams 内容都是可电子数据展示的。 下表显示了可以使用 Microsoft 电子数据展示工具搜索的内容类型：

| 内容类型 | 电子数据展示 | 注释 |
|:--- | :--- |:--- |
|录音 | 否 | |
|卡片内容|是|有关详细信息 [，请参阅"搜索](#search-for-card-content) 卡片内容"。|
|聊天链接 | 是 | |
|聊天消息 | 是 |这包括 Teams 频道中的内容、1 对 1 聊天、1：N 群组聊天以及与来宾用户参与者的聊天。  |
|代码片段 | 否 | |
|已编辑的邮件 | 是 | 如果用户保持保留状态，也会保留以前版本的已编辑消息。 |
|表情符号、GIF 和贴纸 | 是 | |
|内联图像 | 是 | |
|会议 IM 对话 | 是 | |
|会议元数据<sup>1</sup> | 是 |  |
|频道名称 | 否 | |
|专用频道消息 | 是 | |
|引号 | 是 | 引用的内容是可搜索的。 但是，搜索结果不会指示内容已引用。 |
|反应 (如点子、心声和其他反应)  | 否 | |
|主题 | 是 | |
|表 | 是 | |
|||

<sup>1</sup> 会议 (呼叫) 元数据包括以下内容：

- 会议开始时间和结束时间以及持续时间
- 每个参与者的会议加入和离开事件
- VOIP 加入/呼叫
- 匿名加入
- 联合用户加入
- 来宾用户加入

  该图像显示了会议元数据的示例。

  > [!div class="mx-imgBorder"]
  > ![图像是 CVR 记录会议元数据的图像。](media/conversationOption3.png)

下面是会议期间参与者之间的即时消息对话示例。

![Teams 中参与者之间的对话。](media/MeetingIMConversations.png)

> [!div class="mx-imgBorder"]
> ![电子数据展示搜索结果中的参与者之间的对话。](media/MeetingImConversation2.png)

有关执行电子数据展示调查详细信息，请参阅核心 [电子数据展示入门](https://docs.microsoft.com/microsoft-365/compliance/get-started-core-ediscovery)。

Microsoft Teams 数据将在 Excel 电子数据展示导出输出中显示为即时消息或对话。 导出邮件 `.pst` 后，可以在 Outlook 中打开该文件以查看这些邮件。

查看团队的 .pst 文件时，所有对话都保存在"对话历史记录"下的"团队聊天"文件夹中。 消息的标题包含团队名称和频道名称。 例如，下图显示了 Bob 发来的消息，他向制造规范团队的 Project 7 标准频道发送消息。

![Outlook 中用户邮箱中的"团队聊天"文件夹的屏幕截图](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

用户邮箱中的私人聊天存储在"对话历史记录"下的"团队聊天"文件夹中。

## <a name="ediscovery-of-private-channels"></a>专用通道电子数据展示

在私人频道中发送的消息记录将传递到所有私人频道成员的邮箱，而不是传递到组邮箱。 记录的标题已格式化为指示它们是从哪个私人频道发送的。

由于每个专用频道都有自己的 SharePoint 网站，该网站独立于父团队网站，因此专用频道中的文件独立于父团队进行管理。

Teams 不支持对团队中的单个频道进行电子数据展示搜索，因此必须搜索整个团队。 若要在专用频道中对内容执行电子数据展示搜索，请在整个团队中搜索、与专用频道关联的网站集 (以包含文件) 以及专用频道成员的邮箱 (以包含消息) 。

使用以下步骤识别专用通道中要包括在电子数据展示搜索中的文件和消息。

### <a name="include-private-channel-files-in-an-ediscovery-search"></a>在电子数据展示搜索中包括专用频道文件

执行这些步骤之前，请安装[SharePoint Online 命令行管理程序并连接到 SharePoint Online。](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

1. 运行以下代码，获取与团队中的专用频道关联的所有 SharePoint 网站集的列表。

    ```PowerShell
    Get-SPOSite
    ```

2. 运行以下 PowerShell 脚本，获取与团队中的专用频道关联的所有 SharePoint 网站集 URL 的列表和父团队组 ID。

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url}
    ```

3. 对于每个团队或组 ID，请运行以下 PowerShell 脚本来识别所有相关专用频道站点，其中$groupID是团队的组 ID。

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-an-ediscovery-search"></a>在电子数据展示搜索中包括私人频道消息

执行这些步骤之前，请确保已安装最新版本的 Teams [PowerShell 模块](teams-powershell-overview.md) 。

1. 运行以下命令，获取团队中的专用频道列表。

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```

2. 运行以下命令获取专用通道成员的列表。

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```

3. 在电子数据展示搜索查询中包括团队中每个专用频道中所有成员 [的邮箱](https://docs.microsoft.com/microsoft-365/compliance/search-for-content-in-core-ediscovery)。

## <a name="search-for-content-for-guest-users"></a>搜索来宾用户的内容

可以使用电子数据展示工具搜索与组织中来宾用户相关的 Teams 内容。 与来宾用户关联的 Teams 聊天内容保留在基于云的存储位置，并且可以使用电子数据展示进行搜索。 这包括在 1：1 和 1：N 聊天对话中搜索内容，其中来宾用户是组织中其他用户的参与者。 还可以搜索来宾用户是参与者的私人频道消息，在来宾 *：* 来宾聊天对话中搜索内容，其中只有参与者是来宾用户。

搜索来宾用户的内容：

1. 连接到 Azure AD PowerShell。 有关说明，请参阅"使用 PowerShell 连接到 Microsoft 365"中的"使用 Azure Active Directory [PowerShell 进行连接"部分](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)。 请务必完成上一主题中的步骤 1 和步骤 2。

2. 成功连接到 Azure AD PowerShell 后，请运行以下命令，为组织的所有来宾 (UPN) 用户显示用户主体名称。 在步骤 4 创建搜索时，您必须使用来宾用户的 UPN。

   ```powershell
   Get-AzureADUser -Filter "userType eq 'Guest'" -All $true | FL UserPrincipalName
   ```

   > [!TIP]
   > 可以将命令的输出重定向到文本文件，而不是在计算机屏幕上显示用户主体名称列表。 为此，可以追加到上 `> filename.txt` 一命令。 具有用户主体名称的文本文件将保存到当前文件夹。

3. 在不同的安全Windows PowerShell，连接到安全&中心 PowerShell。 有关说明，请参阅["连接到安全&中心 PowerShell"。](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) 可以使用或不使用多重身份验证进行连接。

4. 通过运行以下命令创建内容搜索 (，例如聊天消息和电子邮件) 指定来宾用户是参与者）。

   ```powershell
   New-ComplianceSearch <search name> -ExchangeLocation <guest user UPN>  -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

   例如，若要搜索与来宾用户 Sara Sara 关联的内容，请运行以下命令。

   ```powershell
   New-ComplianceSearch "Sara Davis Guest User" -ExchangeLocation "sara.davis_hotmail.com#EXT#@contoso.onmicrosoft.com" -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

    有关使用 PowerShell 创建内容搜索详细信息，请参阅[New-ComplianceSearch。](https://docs.microsoft.com/powershell/module/exchange/new-compliancesearch)

5. 运行以下命令，启动在步骤 4 中创建的内容搜索：

   ```powershell
   Start-ComplianceSearch <search name>
   ```

6. 转到， [https://compliance.microsoft.com](https://compliance.microsoft.com) 然后单击"显示 **所有**  >  **内容搜索"。**

7. 在搜索列表中，选择在步骤 4 中创建的搜索以显示飞出页。

8. 在"飞出"页上，可以执行以下操作：

   - 单击 **"查看** 结果"以查看搜索结果并预览内容。

   - 在" **查询"字段** 旁边，单击 **"编辑** "进行编辑，然后重新运行搜索。 例如，可以添加搜索查询来缩小结果范围。

   - 单击 **"导出结果** "导出并下载搜索结果。

## <a name="search-for-card-content"></a>搜索卡片内容

Teams 频道、1 对 1 聊天和 1xN 聊天中应用生成的卡内容存储在邮箱中，可以搜索。 *卡* 是一个 UI 容器，用于提供简短的内容。 卡片可以有多个属性和附件，并且可以包含可以触发卡片操作的按钮。 有关详细信息，请参阅 ["卡片"](https://docs.microsoft.com/microsoftteams/platform/task-modules-and-cards/what-are-cards)

与其他 Teams 内容一样，卡片内容的存储位置取决于卡的使用位置。 Teams 频道中使用的卡片内容存储在 Teams 组邮箱中。 1：1 和 1xN 聊天的卡内容存储在聊天参与者的邮箱中。

若要搜索卡内容，可以使用或 `kind:microsoftteams` `itemclass:IPM.SkypeTeams.Message` 搜索条件。 查看搜索结果时，Teams 频道中机器人生成的卡内容具有发件人 **/** 作者电子邮件属性，其中生成卡内容的应用 `<appname>@teams.microsoft.com` `appname` 的名称。 如果卡内容是由用户生成的，则 **发送方/作者的值将** 标识该用户。

在内容搜索结果中查看卡片内容时，内容显示为邮件的附件。 将命名附件 `appname.html` ，其中， `appname` 生成卡内容的应用的名称。 以下屏幕截图显示名为 Asana (应用的卡片内容) Teams 和搜索结果的显示方式。

**Teams 中的卡片内容**

![Teams 频道消息中的卡片内容](media/CardContentTeams.png)

**搜索结果中的卡片内容**
  
![内容搜索结果中的相同卡内容](media/CardContentEdiscoverySearchResults.png)

> [!NOTE]
> 若要在此时在搜索结果中显示卡内容的图像 (如上一屏幕截图) 中的勾号，你必须在用于查看搜索结果的同一浏览器会话的不同选项卡中登录到 Teams (。 https://teams.microsoft.com) 否则会显示图像占位符。

## <a name="advanced-ediscovery"></a>高级电子数据展示

也可使用高级电子数据展示工作流搜索和保留某些 Microsoft Teams [内容](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20)。 虽然电子数据展示提供了一系列搜索、保留和导出功能，但高级电子数据展示为合规性管理员提供了更多工具来识别数据源并分析其内容。

### <a name="advanced-ediscovery-custodian-workflow-for-teams-content"></a>Teams 内容的高级电子数据展示管理员工作流

管理员可能是各种团队的成员。 你可以捕获与这些管理员相关的 Teams 内容。 有关监管员工作流的说明，请参阅"[将管理员添加到高级电子数据展示案例"。](https://docs.microsoft.com/microsoft-365/compliance/add-custodians-to-case)

添加管理员后，单击"下 **一步"** 按钮，然后单击" **添加"** 按钮。 随后将显示一个窗口，提示您选择其他位置，该窗口将显示管理员的所有成员身份及其数据的相应 SharePoint 网站位置。 从所有这些数据源和团队中，您可以选择要用于电子数据展示的内容，然后将该用户和已标识的所有数据源放在保留状态。

可以选择是包括 Exchange 内容、OneDrive 内容还是两者。 Exchange 内容包括用户邮箱中所有应用程序内容，例如其电子邮件、存储在其邮箱中的 Teams 内容，等等。 OneDrive 内容不仅包括用户的内容，还包括 OneDrive 中存储的所有 Teams 内容，例如 1：1 聊天、1：N 聊天和聊天中共享的文件。

您还可以选择关联监管员是其中成员的任何团队，以便包括监管员有权访问的频道聊天消息和文件。 此外，任何其他团队都可以与监管员相关联。

> [!NOTE]
> 私人频道中 [消息和文件](private-channels.md) 电子数据展示的工作方式与标准通道中的工作方式不同。 若要了解有关详细信息，请参阅 [专用通道的电子数据展示](#ediscovery-of-private-channels)。

### <a name="placing-a-data-source-on-hold"></a>保留数据源

如果没有特定用户指定为监管员，您可以保留整个数据源。 有关保留详细信息，请参阅["管理高级电子数据展示中的保留"。](https://docs.microsoft.com/microsoft-365/compliance/managing-holds)

为 Teams 内容创建保留时，可以选择要包括在保留中的所有位置。 即使用户正在删除或更改内容，保留也将保留该内容的所有以前版本的副本。

还可使用可选查询，根据关键字、日期范围、作者和许多其他条件设置保留条件。 如果未指定关键字，则来自该数据源的所有内容都将受到保留。

### <a name="advanced-ediscovery-searches"></a>高级电子数据展示搜索

还可以搜索 Teams 内容。 有关搜索详细信息，请参阅["在高级电子数据展示中收集案例的数据"。](https://docs.microsoft.com/microsoft-365/compliance/collecting-data-for-ediscovery) 即使一条消息与搜索查询匹配，搜索也将返回整个对话。

创建搜索查询时，可以选择监管员，以便搜索已选择的所有源。 还可以搜索非监管源，例如未映射到用户的 Teams 网站。 还可使用可选查询缩小 Teams 内容中的搜索范围。

创建并选中搜索后，会显示一个窗口，该窗口包含对所选搜索可以执行的其他详细信息和操作。 如果单击"统计信息"按钮，您可以查看有关搜索的统计信息，包括根据位置类型、内容的原始源以及内容位于组邮箱、单个用户邮箱还是 SharePoint 网站中的细分。 因此，可以看到哪些源对搜索结果有贡献。 还有一 **个"查询** "视图，可用于查看哪些单个关键字对结果有影响。

完成搜索后，可以单击"添加 **结果以审阅集** "按钮，并将其添加到审阅集。 有关评审集详细信息，请参阅本文稍后在 ["管理高级电子](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets) 数据展示和 [审阅](#review-sets-workflow) 集"工作流中的审阅集。

#### <a name="normal-review-sets-and-conversation-review-sets"></a>普通审阅集和会话审阅集

将搜索添加到评论集时，可以从普通审阅集或对话评审集进行选择。

普通审阅集类似于导出;它提供 Teams `.msg` 内容的单个文件，并且以基本视图显示内容。 如果计划以后使用其他软件工具重新处理文件，通常使用普通审阅集。

对话审阅集提供了更直观、更线程的对话视图;它以正确的顺序一起显示相关消息。

> [!div class="mx-imgBorder"]
> ![对话审阅集的屏幕截图](media/conversationOptions2.png)

两种类型的评审集都提供修订等功能。 有关评审集详细信息，请参阅高级电子数据展示[中的"审阅对话"。](https://docs.microsoft.com/microsoft-365/compliance/conversation-review-sets)

#### <a name="collection-options"></a>集合选项

添加到评审集时，窗口的"集合选项"部分下有几个选项作为复选框提供 **，包括"** 对话检索选项"和 **"Teams 对话"。** 如果启用这些选项，则作为审阅集的一部分的任何单独的 Teams 消息也会显示，并包含附加消息用于上下文。 例如，如果查询是特定的，因此只返回一条消息，则启用这些选项还会返回多条消息，导致并遵循与查询匹配的消息。

许多逻辑条件用于确定其他消息是否为匹配查询的消息提供上下文。 例如，对于 Teams 内容，启用这些选项将检索父消息以及所有子消息，因为消息的线程处理方式。

还会检查邮件时间戳。 如果消息与查询匹配，则 4 小时内位于其前的相邻消息或 4 小时内的相邻消息被视为聊天的一部分，并且也会包含在结果中。

如果必须确定将返回哪些上下文消息，但与搜索查询匹配，则不需要使用这些选项。 可以收集所有内容，也可以扩大搜索的日期范围，以便查询后返回更多消息。

### <a name="review-sets-workflow"></a>审阅集工作流

可以通过单击"审阅集"选项卡查看现有审阅集 **或创建新** 审阅集。有关评审集详细信息，请参阅"[管理高级电子数据展示中的审阅集"。](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets)

除了文档，还可以向审阅集添加电子邮件、Teams 消息、Yammer 消息和其他内容。 在评审集内，还可以执行可在其他上下文中执行的许多相同操作，例如搜索内容和创建自定义查询。 这些操作仅适用于已添加到评审集的项。

" **管理审阅集** "按钮提供了其他选项，例如分析、摘要报告、已添加的负载集数等。

若要访问数据的可视化效果和图表，请单击右上角的"单个 **结果** 搜索 \> 配置文件"视图。 可以单击这些图表中的"拨片"以交互方式选择要查询的内容类型。 例如，可以选择仅查询 Teams 内容。 也可以保存这些查询，就像保存手动写入的查询一样。

#### <a name="summary-view-text-view-and-annotate-view"></a>摘要视图、文本视图和批注视图

如果在评论集内单击 Teams 对话，它将显示"摘要"视图，该视图将整个 Teams 对话显示为可单独交互的消息列表。 单击邮件右侧向下箭头可显示一个上下文菜单，允许您查看消息详细信息或下载单个 `.msg` 文件。 单击消息详细信息会显示元数据摘要或消息的完整元数据。

若要下载 PDF，请单击摘要视图右上角的下载按钮。

单击 **"文本视图** "选项卡可显示 Teams 对话提取文本的纯文本视图。 此纯文本内容适用于导出，可以使用其他软件工具轻松使用它。

单击" **批注视图"选项卡** 访问批注功能。 此选项卡以类似于 Teams 对话的格式显示内容，但还有其他编辑选项。 有一个铅笔工具可用于做笔记、在邮件上绘图或执行精细的划掉以用于修订。 还有 **一个"** 区域修订"工具，可用于绘制一个矩形，用于将该区域标记为"修订"。

下面是用户之间线程聊天的修订文件示例。

> [!div class="mx-imgBorder"]
> ![已修订文件的屏幕截图](media/RedactedFileExample.png)

"批注视图 **"选项卡的底部** 是" **标记文档** "按钮，它显示标记面板。 在此面板中，可以将标记应用到 Teams 对话内的所有消息。 可以将聊天标记为响应性或非响应性、特权或非特权，包括是否包含"有趣项"、是否应包含在导出中，以及是否需要进一步评审。 还可以管理和应用其他可自定义的标记。

#### <a name="action-menu"></a>操作菜单

在"审阅集"窗口中，可以通过单击"操作 **导出"导出** \> **内容**。 导出时有许多选项可用。

若要导出包含所有 Teams 消息的所有元数据的文件，请单击以选中"加载 **文件"** 复选框。 若要在文件中包括已应用到内容的任何标记，请单击以选中"标记 **"** 复选框。

使用 **"本机文件"** 选项以本机格式导出文件。 您可以选择将对话导出为一个文件，或者将单个聊天消息导出到它们自己的单独文件中。

" **文本文件"** 选项允许您保存纯文本版本的内容。 若要详细了解如何在评论集内获取 Teams 对话的纯文本视图，请参阅上面的摘要视图、文本视图和 [批注](#summary-view-text-view-and-annotate-view) 视图。

如果按照上述"摘要视图、文本视图"和"批注视图[](#summary-view-text-view-and-annotate-view)"部分中所述对内容应用了任何修订，可以选择"将修订的本机文件替换为转换后的 PDF"选项，以 PDF 格式将本机文件替换为转换后的副本。

可以选择导出到 Microsoft 提供的 Azure Blob 存储容器，也可以提供自己的 Azure Blob 存储容器。

准备好开始导出过程时，请单击"导出 **"** 按钮。 请参阅 ["下载导出](https://docs.microsoft.com/microsoft-365/compliance/download-export-jobs) 作业"，详细了解如何在导出完成后访问 Azure Blob 存储容器并下载导出的内容。

> [!NOTE]
> 导出可能需要很长时间。 若要跟踪导出过程的状态，请退出"审阅集 **"选项卡，** 然后单击"导出 **"** 选项卡。

## <a name="related-topics"></a>相关主题

- [Microsoft 365 中的电子数据展示](https://docs.microsoft.com/microsoft-365/compliance/ediscovery)
- [Teams PowerShell 概览](teams-powershell-overview.md)
