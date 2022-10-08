---
title: 对内容进行电子数据展示调查
description: 了解在需要执行电子数据展示时应执行的操作，例如需要提交所有电子存储信息以进行法律诉讼。
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- tier1
- purview-compliance
- M365-collaboration
- ediscovery
ms.reviewer: anwara
search.appverid: MET150
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a44245d31e6fc9f4b58c17832e596c6d73b56635
ms.sourcegitcommit: 507e186972bcbc56c1547a1b9f357bfd38170b5a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/27/2022
ms.locfileid: "68046652"
---
# <a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a>在 Microsoft Teams 中对内容进行电子数据展示调查

大型企业往往面临高罚法律诉讼，要求提交所有电子存储信息 (ESI) 。 可以在电子数据展示调查期间搜索和使用 Microsoft Teams 内容。

## <a name="overview"></a>概述

所有 Microsoft Teams 1：1 或群聊都会记录到各自用户的邮箱。 所有标准频道消息都会记录到代表团队的组邮箱。 SharePoint Online 和 OneDrive for Business 的电子数据展示功能涵盖了在标准频道中上传的文件。

[在专用通道](private-channels.md)中，消息和文件的电子数据展示的工作方式不同于标准通道中的工作方式。 若要了解详细信息，请参阅 [专用频道的电子数据展示](#ediscovery-of-private-and-shared-channels)。

并非所有 Teams 内容都是可电子数据展示的。 下表显示了可以使用 Microsoft 电子数据展示工具搜索的内容类型：

|**内容类型**|**注释**|
|:---------------|:--------|
|音频录制||
|卡片内容|有关详细信息，请参阅 [“搜索卡片内容](#search-for-card-content) ”。|
|聊天链接||
|聊天消息|这包括标准 Teams 频道中的内容、1：1 聊天、1：N 组聊天以及与来宾用户参与者的聊天。|
|代码片段||
|编辑的消息|如果用户处于保留状态，则还会保留以前版本的编辑消息。|
|表情符号、GIF 和贴纸||
|内联图像||
|循环组件|循环组件中的内容保存在存储在发送循环组件的用户的OneDrive for Business帐户中的 .fluid 文件中。 这意味着，在循环组件中搜索内容时，必须将 OneDrive 作为数据源。|
|会议 IM 对话||
|会议元数据<sup>1</sup>||
|通道的名称||
|报价|引用的内容是可搜索的。 但是，搜索结果并不指示已引用内容。|
|喜欢、心和其他反应等 (反应) |2022 年 6 月 1 日之后，所有商业客户都支持响应。 此日期之前的反应不可用于电子数据展示。 已计划政府云支持。 没有法律上对反应的支持。|
|主题||
|表||
|Teams 视频剪辑 (TVC) |通过右键单击预览 (按关键字搜索，搜索带有“Video-Clip”关键字和“另存为”每个 TVC 附件的.mp4文件将在 2022 年 10 月) 提供。 可在电子数据展示 [审阅集中](/microsoft-365/compliance/add-data-to-review-set)发现 TVC 数据。

<sup>1</sup> 会议 (和呼叫) 元数据包括：

- 会议开始和结束时间以及持续时间
- 会议加入并为每个参与者保留事件
- VOIP 联接/调用
- 匿名联接
- 联合用户联接
- 来宾用户联接

下面是会议期间参与者之间的聊天对话的示例。

![Teams 中参与者之间的对话。](media/MeetingIMConversations.png)

下面是电子数据展示工具中查看的同一聊天对话的符合性副本的示例。

![电子数据展示搜索结果中参与者之间的对话。](media/MeetingImConversation2.png)

下面是会议元数据的示例。

![符合性副本中的会议元数据。](media/conversationOption3.png)

有关进行电子数据展示调查的详细信息，请参阅电子数据 [展示 (标准) ](/microsoft-365/compliance/get-started-core-ediscovery)入门。

Microsoft Teams 数据将在 Excel 电子数据展示导出输出中显示为即时消息或对话。 可以在 Outlook 中打开 `.pst` 该文件，以便在导出这些消息后查看这些消息。

查看团队的 .pst 文件时，所有对话都位于对话历史记录下的“团队聊天”文件夹中。 消息的标题包含团队名称和频道名称。 例如，下图显示了 Bob 的一条消息，该消息向制造规范团队的 Project 7 标准频道发送了消息。

![Outlook 中用户邮箱中的“团队聊天”文件夹屏幕截图。](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

用户邮箱中的私人聊天存储在对话历史记录下的团队聊天文件夹中。

## <a name="ediscovery-of-private-and-shared-channels"></a>专用和共享通道的电子数据展示

专用和共享通道中邮件的符合性副本将发送到不同的邮箱，具体取决于通道类型。 这意味着，必须根据用户所属通道的类型搜索不同的邮箱位置。

- **专用频道**。 合规性副本将发送到专用频道成员的所有成员的邮箱。 这意味着，在搜索专用频道邮件中的内容时，必须搜索用户邮箱。

- **共享通道**。 合规性副本将发送到与父团队关联的系统邮箱。 由于 Teams 不支持对共享频道的单个系统邮箱进行电子数据展示搜索，因此，在共享频道中搜索邮件内容时，必须选择团队邮箱) 名称来搜索 (父团队的邮箱。

每个专用和共享频道都有其自己的 SharePoint 网站，独立于父团队网站。 这意味着专用和共享通道中的文件存储在其自己的网站中，并独立于父团队进行管理。 这意味着，在文件和频道消息附件中搜索内容时，必须标识和搜索与通道关联的特定网站。

使用以下部分来帮助标识要包含在电子数据展示搜索中的专用通道或共享通道。

### <a name="identifying-the-members-of-a-private-channel"></a>标识专用频道的成员

使用本部分中的过程标识专用频道的成员，以便可以使用电子数据展示工具在成员的邮箱中搜索专用频道邮件中的内容。

在执行这些步骤之前，请确保已安装 [最新版本的 Teams PowerShell 模块](teams-powershell-overview.md) 。

1. 运行以下命令以获取包含要搜索的共享通道的团队的组 ID。

   ```powershell
   Get-Team -DisplayName <display name of the the parent team>
   ```

   > [!TIP]
   > 在没有任何参数的情况下运行 **Get-Team** cmdlet 以显示组织中所有 Teams 的列表。 该列表包含每个团队的组 ID 和 DisplayName。

2. 运行以下命令以获取父团队中的专用频道列表。 对在步骤 1 中获取的团队使用组 ID。

   ```PowerShell
    Get-TeamChannel -GroupId <parent team GroupId> -MembershipType Private
   ```

3. 运行以下命令，获取特定专用频道的专用频道所有者和成员的列表。

   ```PowerShell
    Get-TeamChannelUser -GroupId <parent team GroupId> -DisplayName "Partner Shared Channel"
   ```

4. 在电子数据 [展示 (标准) ](/microsoft-365/compliance/search-for-content-in-core-ediscovery) 或在电子数据展示 (高级) [中标识和收集保管人内容 ](/microsoft-365/compliance/add-custodians-to-case)时，包括专用频道的所有者和成员的邮箱作为电子数据展示搜索查询的一部分。

### <a name="identifying-the-sharepoint-site-for-private-and-shared-channels"></a>标识专用和共享频道的 SharePoint 网站

如前所述，在专用通道和共享通道中共享的文件 (和附加到通道消息) 的文件存储在与通道关联的网站集中。 使用本部分中的过程标识与特定专用通道或共享通道关联的站点的 URL。 然后，可以使用电子数据展示工具搜索网站中的内容。

在执行这些步骤之前， [请安装 SharePoint Online Management Shell 并连接到 SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)。

1. （可选）运行以下命令以获取与父团队中的共享频道关联的所有 SharePoint 网站集的列表。

   ```PowerShell
    Get-SPOSite
   ```

   > [!TIP]
   > 与专用通道和共享通道关联的网站的 URL 的命名约定是 `[SharePoint domain]/sites/[Name of parent team]-[Name of private or shared channel]`。 例如，名为“合作伙伴协作”的共享通道的 URL 位于 Contoso 组织 `https://contoso.sharepoint.com/sites/EngineeringTeam-PartnerCollaboration`中的“工程师团队”父团队中。

2. 运行以下 PowerShell 命令，显示与组织中的专用频道和共享频道关联的所有 SharePoint 网站的 URL。 脚本的输出还包括父团队的组 ID，需要在步骤 3 中运行命令。

    ```PowerShell
    $sites = Get-SPOSite -Template "TEAMCHANNEL#1"
    foreach ($site in $sites) {$x= Get-SPOSite -Identity $site.url -Detail; $x.relatedgroupID; $x.url}
    ```

   > [!NOTE]
   > 2021 年 6 月 28 日之前创建的专用频道的 SharePoint 网站使用自定义模板 ID 的值 `"TEAMCHANNEL#0"` 。 若要显示在此日期之后创建的专用通道，请在运行前两个脚本时使用该值 `"TEAMCHANNEL#1"` 。 共享通道仅使用值 `"TEAMCHANNEL#1"`。

3. 对于每个父团队，运行以下 PowerShell 命令来标识专用和共享通道站点，父团队的组 ID 在哪里 `$groupID` 。

    ```PowerShell
    $sites = Get-SPOSite -Template "TEAMCHANNEL#1"
    $groupID = "<group ID of parent team)"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

4. 在电子数据展示 [ (标准) ](/microsoft-365/compliance/search-for-content-in-core-ediscovery) 或在电子数据展示 ([高级) 中标识和收集保管人内容 ](/microsoft-365/compliance/add-custodians-to-case)时，包括与专用或共享通道关联的网站作为电子数据展示搜索查询的一部分。

## <a name="search-for-content-for-guest-users"></a>搜索来宾用户的内容

可以使用电子数据展示工具搜索与组织中的来宾用户相关的 Teams 内容。 与来宾用户关联的 Teams 聊天内容会保留在基于云的存储位置中，并且可以使用电子数据展示进行搜索。 这包括在 1：1 和 1：N 聊天对话中搜索内容，其中来宾用户是组织中其他用户的参与者。 还可以搜索来宾用户参与的专用频道消息，并在 *来宾聊天* 对话中搜索内容，其中唯一参与者是来宾用户。

若要搜索来宾用户的内容，请执行以下操作：

1. 连接到 Azure AD PowerShell。 有关说明，请参阅 [PowerShell 连接到 Microsoft 365](/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module) 中的“与 Azure Active Directory PowerShell 连接”部分。 请务必完成上一篇文章中的步骤 1 和步骤 2。

2. 成功连接到 Azure AD PowerShell 后，请运行以下命令，为组织中的所有来宾用户显示用户主体名称 (UPN) 。 在步骤 4 中创建搜索时，必须使用来宾用户的 UPN。

   ```powershell
   Get-AzureADUser -Filter "userType eq 'Guest'" -All $true | FL UserPrincipalName
   ```

   > [!TIP]
   > 可以将命令的输出重定向到文本文件，而不是在计算机屏幕上显示用户主体名称列表。 可以通过追加 `> filename.txt` 到上一个命令来执行此操作。 具有用户主体名称的文本文件将保存到当前文件夹。

3. 在其他Windows PowerShell窗口中，连接到安全&合规中心 PowerShell。 有关说明，请参阅 [“连接到安全&合规中心 PowerShell](/powershell/exchange/connect-to-scc-powershell)。 可以使用或不使用多重身份验证进行连接。

4. 创建一个内容搜索，搜索所有内容 (，例如聊天消息和电子邮件) 指定的来宾用户在其中是参与者，运行以下命令。

   ```powershell
   New-ComplianceSearch <search name> -ExchangeLocation <guest user UPN>  -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

   例如，若要搜索与来宾用户 Sara Davis 相关联的内容，请运行以下命令。

   ```powershell
   New-ComplianceSearch "Sara Davis Guest User" -ExchangeLocation "sara.davis_hotmail.com#EXT#@contoso.onmicrosoft.com" -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

    有关使用 PowerShell 创建内容搜索的详细信息，请参阅 [New-ComplianceSearch](/powershell/module/exchange/new-compliancesearch)。

5. 运行以下命令以启动在步骤 4 中创建的内容搜索：

   ```powershell
   Start-ComplianceSearch <search name>
   ```

6. 转到 [https://compliance.microsoft.com](https://compliance.microsoft.com) ，然后单击 **“显示所有** > **内容搜索**”。

7. 在搜索列表中，选择在步骤 4 中创建的搜索以显示浮出控件页。

8. 在浮出控件页上，可以执行以下操作：

   - 单击 **“查看结果** ”以查看搜索结果并预览内容。

   - 在 **“查询** ”字段旁边，单击 **“编辑** ”进行编辑，然后重新运行搜索。 例如，可以添加搜索查询以缩小结果范围。

   - 单击 **“导出结果** ”以导出并下载搜索结果。

## <a name="search-for-card-content"></a>搜索卡片内容

Teams 频道中的应用生成的卡片内容、1：1 聊天和 1xN 聊天存储在邮箱中，可以搜索。 *卡片* 是短片内容的 UI 容器。 卡片可以具有多个属性和附件，并且可以包含可以触发卡片操作的按钮。 有关详细信息，请参阅 [卡片](/microsoftteams/platform/task-modules-and-cards/what-are-cards)

与其他 Teams 内容一样，存储卡片内容的位置基于卡片的使用位置。 Teams 频道中使用的卡片内容存储在 Teams 组邮箱中。 1：1 和 1xN 聊天的卡片内容存储在聊天参与者的邮箱中。

若要搜索卡片内容，可以使用 `kind:microsoftteams` 或 `itemclass:IPM.SkypeTeams.Message` 搜索条件。 查看搜索结果时，Teams 通道中机器人生成的卡片内容具有 **发件人/作者** 电子邮件属性，生成 `<appname>@teams.microsoft.com`卡片内容的应用的名称在哪里 `appname` 。 如果卡片内容是由用户生成的， **则 Sender/Author** 的值将标识用户。

在内容搜索结果中查看卡片内容时，内容将显示为邮件的附件。 附件命名 `appname.html`，生成卡片内容的应用的名称在哪里 `appname` 。 以下屏幕截图显示了名为 Asana) 的应用的卡片内容 (如何出现在 Teams 和搜索结果中。

### <a name="card-content-in-teams"></a>Teams 中的卡片内容

![Teams 频道消息中的卡片内容。](media/CardContentTeams.png)

### <a name="card-content-in-search-results"></a>搜索结果中的卡片内容

![内容搜索结果中的相同卡片内容。](media/CardContentEdiscoverySearchResults.png)

> [!NOTE]
> 若要在搜索结果中显示卡片内容中的图像， (如上一个屏幕截图) 中的复选标记，必须在用于查看搜索结果的同一浏览器会话的不同选项卡中) 登录 Teams (<https://teams.microsoft.com> 。 否则，将显示图像占位符。

## <a name="ediscovery-in-federated-and-non-federated-environments"></a>联合环境和非联合环境中的电子数据展示

管理员可以使用电子数据展示在称为 *外部访问*) 和非联合 (（称为 *来宾访问*) 环境）的联合 (的 Teams 会议中搜索聊天消息中的内容，具体取决于以下限制：

- **联合**：在与组织中的用户和外部组织 (具有组织外部访问权限的用户) 的 Teams 会议中，两个组织的管理员都可以从会议中搜索聊天消息中的内容。

- **非联合**：在与组织用户和来宾用户的 Teams 会议中，只有托管 Teams 会议的组织中的管理员才能在会议的聊天消息中搜索内容。

## <a name="related-topics"></a>相关主题

- [Microsoft 365 电子数据展示解决方案](/microsoft-365/compliance/ediscovery)
- [电子数据展示 (标准) 入门 ](/microsoft-365/compliance/get-started-core-ediscovery)
- [电子数据展示 (高级) 中的 Teams 工作流 ](/microsoft-365/compliance/teams-workflow-in-advanced-ediscovery)
- [Teams PowerShell 概览](teams-powershell-overview.md)
