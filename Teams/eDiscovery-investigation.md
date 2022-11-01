---
title: 对内容进行电子数据展示调查
description: 了解需要执行电子数据展示时（例如需要提交所有电子存储信息以进行法律诉讼）时该执行的操作。
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
ms.openlocfilehash: 8a9e7afdf55fbcb85dcbbf907ef974a62e4e8492
ms.sourcegitcommit: 86b9503eb0085e23176cb346767f880ea3a73e77
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2022
ms.locfileid: "68808291"
---
# <a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a>在 Microsoft Teams 中对内容进行电子数据展示调查

大型企业经常面临高处罚法律程序，要求提交所有电子存储信息 (ESI) 。 可以在电子数据展示调查期间搜索和使用 Microsoft Teams 内容。

## <a name="overview"></a>概述

所有 Microsoft Teams 1：1 或群组聊天都会记录到相应用户的邮箱。 所有标准频道邮件都记录到表示团队的组邮箱。 在标准通道中上传的文件包含在 SharePoint Online 和 OneDrive for Business 电子数据展示功能下。

[专用频道](private-channels.md)中消息和文件的电子数据展示的工作方式与标准频道不同。 若要了解详细信息，请参阅 [专用频道的电子数据展示](#ediscovery-of-private-and-shared-channels)。

并非所有 Teams 内容都是可电子数据展示的。 下表显示了可以使用 Microsoft 电子数据展示工具搜索的内容类型：

|**内容类型**|**注释**|
|:---------------|:--------|
|音频录制||
|卡片内容|有关详细信息 [，请参阅搜索卡片内容](#search-for-card-content) 。|
|聊天链接||
|聊天消息|这包括标准 Teams 频道中的内容、1：1 聊天、1：N 群组聊天，以及与来宾用户参与者的聊天。|
|代码片段||
|已编辑的邮件|如果用户处于保留状态，则还会保留以前版本的已编辑消息。|
|表情符号、GIF 和贴纸||
|内联图像||
|循环组件|循环组件中的内容保存在 .fluid 文件中，该文件存储在发送循环组件的用户的 OneDrive for Business 帐户中。 这意味着，在循环组件中搜索内容时，必须包含 OneDrive 作为数据源。|
|会议即时消息对话||
|会议元数据<sup>1</sup>||
|通道名称||
|报价|引用的内容可搜索。 但是，搜索结果并不指示引用了内容。|
| (的反应，如喜欢、心和其他反应) |2022 年 6 月 1 日之后，所有商业客户都支持响应。 此日期之前的反应不适用于电子数据展示。 现在支持扩展的反应。 若要了解反应历史记录，内容必须处于法律保留状态。|
|主题||
|表||
|Teams 视频剪辑 (TVC) |在 2022 年 10 月) 年 10 月，通过右键单击预览 (按关键字搜索，使用“Video-Clip”关键字和“另存为”来搜索每个 TVC 附件.mp4文件。 TVC 数据可在电子数据展示 [审阅集中](/microsoft-365/compliance/add-data-to-review-set)发现。

<a name="teams-metadata"></a><sup>1</sup> 会议 (和呼叫) 元数据包括以下内容：

- 会议开始和结束时间以及持续时间
- 每个参与者的会议加入和离开事件
- VOIP 联接/呼叫
- 匿名联接
- 联合用户加入
- 来宾用户加入

下面是会议期间参与者之间的聊天对话示例。

![Teams 中参与者之间的对话。](media/MeetingIMConversations.png)

下面是电子数据展示工具中查看的同一聊天对话的符合性副本示例。

![电子数据展示搜索结果中的参与者之间的对话。](media/MeetingImConversation2.png)

下面是会议元数据的示例。

![符合性副本中的会议元数据。](media/conversationOption3.png)

有关进行电子数据展示调查的详细信息，请参阅 [电子数据展示入门 (Standard) ](/microsoft-365/compliance/get-started-core-ediscovery)。

Microsoft Teams 数据将在 Excel 电子数据展示导出输出中显示为即时消息或对话。 可以在 Outlook 中打开 `.pst` 文件，在导出邮件后查看这些邮件。

查看团队的 .pst 文件时，所有对话都位于“对话历史记录”下的“团队聊天”文件夹中。 消息的标题包含团队名称和频道名称。 例如，下图显示了 Bob 发送的一条消息，该消息向制造规格团队的 Project 7 标准频道发送了消息。

![Outlook 中用户邮箱中的“团队聊天”文件夹屏幕截图。](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

用户邮箱中的私人聊天存储在“对话历史记录”下的“团队聊天”文件夹中。

## <a name="ediscovery-of-private-and-shared-channels"></a>专用频道和共享频道的电子数据展示

专用频道和共享频道中邮件的符合性副本将发送到不同的邮箱，具体取决于通道类型。 这意味着你必须根据用户所属的频道类型搜索不同的邮箱位置。

- **专用频道**。 合规性副本将发送到专用频道成员的所有成员的邮箱。 这意味着在搜索私人频道邮件中的内容时，必须搜索用户邮箱。

- **共享频道**。 合规性副本将发送到与父团队关联的系统邮箱。 由于 Teams 不支持对共享频道的单个系统邮箱进行电子数据展示搜索，因此在共享频道中搜索邮件内容时，必须通过选择团队邮箱) 的名称来搜索父团队 (邮箱。

每个专用频道和共享频道都有自己的 SharePoint 网站，该网站独立于父团队网站。 这意味着专用频道和共享频道中的文件存储在其自己的站点中，并且独立于父团队进行管理。 这意味着，在搜索文件和频道邮件附件中的内容时，必须识别并搜索与频道关联的特定网站。

使用以下部分来帮助识别要包含在电子数据展示搜索中的专用频道或共享频道。

### <a name="identifying-the-members-of-a-private-channel"></a>标识专用频道的成员

使用本部分中的过程标识专用频道的成员，以便可以使用电子数据展示工具在成员邮箱中搜索专用频道邮件中的内容。

在执行这些步骤之前，请确保已安装 [最新版本的 Teams PowerShell 模块](teams-powershell-overview.md) 。

1. 运行以下命令，获取包含要搜索的共享频道的团队的组 ID。

   ```powershell
   Get-Team -DisplayName <display name of the the parent team>
   ```

   > [!TIP]
   > 运行不带任何参数的 **Get-Team** cmdlet 以显示组织中所有 Teams 的列表。 该列表包含每个团队的组 ID 和 DisplayName。

2. 运行以下命令，获取父团队中的专用频道列表。 使用在步骤 1 中获取的团队的组 ID。

   ```PowerShell
    Get-TeamChannel -GroupId <parent team GroupId> -MembershipType Private
   ```

3. 运行以下命令，获取特定专用频道的专用频道所有者和成员的列表。

   ```PowerShell
    Get-TeamChannelUser -GroupId <parent team GroupId> -DisplayName "Partner Shared Channel"
   ```

4. 在 [电子数据展示 (Standard) ](/microsoft-365/compliance/search-for-content-in-core-ediscovery) 中或在电子数据展示 ([Premium) 中标识和收集保管人内容 ](/microsoft-365/compliance/add-custodians-to-case)时，将专用频道的所有者和成员的邮箱包含在电子数据展示 (搜索查询中。

### <a name="identifying-the-sharepoint-site-for-private-and-shared-channels"></a>标识专用频道和共享频道的 SharePoint 网站

如前所述，专用频道和共享频道中共享的文件 (以及附加到频道消息) 的文件存储在与通道关联的网站集中。 使用本节中的过程标识与特定专用或共享频道关联的网站的 URL。 然后，可以使用电子数据展示工具来搜索网站中的内容。

在执行这些步骤之前， [请安装 SharePoint Online 命令行管理程序并连接到 SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)。

1. （可选）运行以下命令以获取与父团队中的共享频道关联的所有 SharePoint 网站集的列表。

   ```PowerShell
    Get-SPOSite
   ```

   > [!TIP]
   > 与专用频道和共享频道关联的网站的 URL 的命名约定是 `[SharePoint domain]/sites/[Name of parent team]-[Name of private or shared channel]`。 例如，名为“合作伙伴协作”的共享通道的 URL 位于 Contoso 组织的 `https://contoso.sharepoint.com/sites/EngineeringTeam-PartnerCollaboration`“工程师团队”父团队中。

2. 运行以下 PowerShell 命令以显示与组织中的专用频道和共享频道关联的所有 SharePoint 网站的 URL。 脚本的输出还包括父团队的组 ID，你需要在步骤 3 中运行命令。

    ```PowerShell
    $sites = Get-SPOSite -Template "TEAMCHANNEL#1"
    foreach ($site in $sites) {$x= Get-SPOSite -Identity $site.url -Detail; $x.relatedgroupID; $x.url}
    ```

   > [!NOTE]
   > 2021 年 6 月 28 日之前创建的专用频道的 SharePoint 网站使用自定义模板 ID 的值 `"TEAMCHANNEL#0"` 。 若要显示在此日期之后创建的专用频道，请在运行前两个脚本时使用 值 `"TEAMCHANNEL#1"` 。 共享通道仅使用 的值 `"TEAMCHANNEL#1"`。

3. 对于每个父团队，请运行以下 PowerShell 命令来标识专用和共享频道网站，其中 `$groupID` 是父团队的组 ID。

    ```PowerShell
    $sites = Get-SPOSite -Template "TEAMCHANNEL#1"
    $groupID = "<group ID of parent team)"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

4. 在 [电子数据展示 (Standard) 中或在电子数据展示 (Premium) ](/microsoft-365/compliance/search-for-content-in-core-ediscovery) [中标识和收集保管人内容 ](/microsoft-365/compliance/add-custodians-to-case)时，将与专用或共享频道关联的网站包含在电子数据展示 (电子数据展示搜索查询中。

## <a name="search-for-content-for-guest-users"></a>搜索来宾用户的内容

可以使用电子数据展示工具搜索与组织中的来宾用户相关的 Teams 内容。 与来宾用户关联的 Teams 聊天内容保留在基于云的存储位置中，可以使用电子数据展示进行搜索。 这包括在 1：1 和 1：N 聊天对话中搜索内容，其中来宾用户是组织中其他用户的参与者。 还可以搜索来宾用户是参与者的私人频道消息，并在 *来宾：来宾* 聊天对话中搜索内容，其中只有参与者是来宾用户。

若要搜索来宾用户的内容，请执行以下操作：

1. 连接到 Azure AD PowerShell。 有关说明，请参阅使用 PowerShell [连接到 Microsoft 365 中的“使用 Azure Active Directory PowerShell 进行连接](/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)”部分。 请务必完成上一篇文章中的步骤 1 和步骤 2。

2. 成功连接到 Azure AD PowerShell 后，运行以下命令以显示组织中所有来宾用户的用户主体名称 (UPN) 。 在步骤 4 中创建搜索时，必须使用来宾用户的 UPN。

   ```powershell
   Get-AzureADUser -Filter "userType eq 'Guest'" -All $true | FL UserPrincipalName
   ```

   > [!TIP]
   > 可以将命令的输出重定向到文本文件，而不是在计算机屏幕上显示用户主体名称的列表。 可以通过将 追加 `> filename.txt` 到上一个命令来执行此操作。 具有用户主体名称的文本文件将保存到当前文件夹。

3. 在不同的Windows PowerShell窗口中，连接到安全&合规中心 PowerShell。 有关说明，请参阅 [连接到安全&合规中心 PowerShell](/powershell/exchange/connect-to-scc-powershell)。 可以使用或不使用多重身份验证进行连接。

4. 通过运行以下命令，创建内容搜索，搜索所有内容 (，例如聊天消息和电子邮件) ，其中指定的来宾用户是参与者。

   ```powershell
   New-ComplianceSearch <search name> -ExchangeLocation <guest user UPN>  -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

   例如，若要搜索与来宾用户 Sara Davis 关联的内容，请运行以下命令。

   ```powershell
   New-ComplianceSearch "Sara Davis Guest User" -ExchangeLocation "sara.davis_hotmail.com#EXT#@contoso.onmicrosoft.com" -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

    有关使用 PowerShell 创建内容搜索的详细信息，请参阅 [New-ComplianceSearch](/powershell/module/exchange/new-compliancesearch)。

5. 运行以下命令，开始在步骤 4 中创建的内容搜索：

   ```powershell
   Start-ComplianceSearch <search name>
   ```

6. 转到 [https://compliance.microsoft.com](https://compliance.microsoft.com) ，然后选择 **“显示所有** > **内容搜索**”。

7. 在搜索列表中，选择在步骤 4 中创建的搜索以显示浮出控件页面。

8. 在浮出控件页上，可以执行以下操作：

   - 选择“ **查看结果** ”可查看搜索结果并预览内容。

   - 在 **“查询** ”字段旁边，选择“ **编辑”** 进行编辑，然后重新运行搜索。 例如，可以添加搜索查询以缩小结果范围。

   - 选择“ **导出结果** ”以导出并下载搜索结果。

## <a name="search-for-card-content"></a>搜索卡片内容

Teams 频道、1：1 聊天和 1xN 聊天中的应用生成的卡片内容存储在邮箱中，可以进行搜索。 *卡片* 是用于短内容片段的 UI 容器。 卡片可以有多个属性和附件，并且可以包含可触发卡片操作的按钮。 有关详细信息，请参阅 [卡片](/microsoftteams/platform/task-modules-and-cards/what-are-cards)

与其他 Teams 内容一样，存储卡片内容的位置取决于卡片的使用位置。 Teams 频道中使用的卡片内容存储在 Teams 组邮箱中。 1：1 和 1xN 聊天的卡片内容存储在聊天参与者的邮箱中。

若要搜索卡片内容，可以使用 `kind:microsoftteams` 或 `itemclass:IPM.SkypeTeams.Message` 搜索条件。 查看搜索结果时，Teams 频道中机器人生成的卡片内容将 **发件人/作者** 电子邮件属性设置为 `<appname>@teams.microsoft.com`，其中 `appname` 是生成卡片内容的应用的名称。 如果卡片内容由用户生成，则 **发件人/作者** 的值标识该用户。

在内容搜索结果中查看卡片内容时，内容显示为邮件的附件。 附件名为 `appname.html`，其中 `appname` 是生成卡片内容的应用的名称。 以下屏幕截图显示了名为 Asana 的应用 (卡片内容) 在 Teams 和搜索结果中的显示方式。

### <a name="card-content-in-teams"></a>Teams 中的卡片内容

![Teams 频道消息中的卡片内容。](media/CardContentTeams.png)

### <a name="card-content-in-search-results"></a>搜索结果中的卡片内容

![内容搜索结果中的相同卡片内容。](media/CardContentEdiscoverySearchResults.png)

> [!NOTE]
> 若要此时在搜索结果中显示卡片内容的图像 (如上一屏幕截图) 中的复选标记，则必须在用于查看搜索结果的同一浏览器会话中的不同选项卡中) 登录到 Teams <https://teams.microsoft.com> (。 否则，将显示图像占位符。

## <a name="ediscovery-in-federated-and-non-federated-environments"></a>联合和非联合环境中的电子数据展示

管理员可以根据以下限制，使用电子数据展示在联合 (的 Teams 会议中搜索聊天消息中的内容，称为 *外部访问*) 非联合 (称为 *来宾访问*) 环境：

- **联合**：在与组织用户和外部组织用户 (在组织中具有外部访问权限) 的 Teams 会议中，这两个组织中的管理员可以从会议搜索聊天消息中的内容。

- **非联合**：在与组织用户和来宾用户的 Teams 会议中，只有主持 Teams 会议的组织中的管理员可以从会议中搜索聊天消息中的内容。

## <a name="related-articles"></a>相关文章

- [Microsoft 365 电子数据展示解决方案](/microsoft-365/compliance/ediscovery)
- [电子数据展示 (标准) 入门 ](/microsoft-365/compliance/get-started-core-ediscovery)
- [电子数据展示 (Premium) 中的 Teams 工作流 ](/microsoft-365/compliance/teams-workflow-in-advanced-ediscovery)
- [Teams PowerShell 概览](teams-powershell-overview.md)
