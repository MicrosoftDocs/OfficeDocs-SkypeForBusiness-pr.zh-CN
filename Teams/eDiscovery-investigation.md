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
description: 了解需要执行电子数据展示（例如，需要提交所有电子数据存储信息进行诉讼）时要执行的操作。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b78ec3ad6741d2c7f83d7732400d5f1154747d5e
ms.sourcegitcommit: 5ca04ee10e3f254e1b24506de116591fdfd51d18
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2022
ms.locfileid: "62929157"
---
# <a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a>在 Microsoft Teams 中对内容进行电子数据展示调查

大型企业通常面临高处罚诉讼，这些诉讼要求提交所有电子存储信息 (ESI) 。 Microsoft Teams电子数据展示调查期间可以搜索和使用内容。

## <a name="overview"></a>概述

所有Microsoft Teams 1：1 或群组聊天都记录到相应用户的邮箱。 所有标准频道邮件都记录到代表团队的组邮箱。 在标准通道中上传的文件在 SharePoint Online 和 OneDrive for Business 电子数据展示功能下OneDrive for Business。

在专用频道中电子数据展示消息和[](private-channels.md)文件的工作方式与在标准通道中不同。 若要了解更多信息，请参阅 [私人频道电子数据展示](#ediscovery-of-private-channels)。

并非所有 Teams内容都是可电子数据展示的。 下表显示了可以使用 Microsoft 电子数据展示工具搜索的内容类型：

| 内容类型 | 电子数据展示 | 注释 |
|:--- | :--- |:--- |
|录音 | 否 | |
|卡片内容|是|有关详细信息 [，请参阅搜索](#search-for-card-content) 卡片内容。|
|聊天链接 | 是 | |
|聊天消息 | 是 |这包括来自Teams、1：1 聊天、1：N 群组聊天以及与来宾用户参与者聊天的内容。  |
|代码片段 | 否 | |
|已编辑的消息 | 是 | 如果用户保持保留状态，也会保留以前版本的已编辑消息。 |
|表情符号、GIF 和贴纸 | 是 | |
|源通知 | 否 | |
|内联图像 | 是 | |
|循环组件| 否|包含循环组件的聊天消息是可搜索的。 但是，循环组件的内容不会为搜索编制索引，也不会在搜索结果中返回。 如果搜索结果包含包含循环组件的消息，可以查看循环组件内容。  |
|会议 IM 对话 | 是 | |
|会议元数据<sup>1</sup> | 是 |  |
|频道名称 | 是 | |
|专用频道消息 | 是 | |
|引号 | 是 | 引用的内容可搜索。 但是，搜索结果并不指示内容已引用。 |
|反应 (，如喜欢、心声和其他反应)  | 否 | |
|主题 | 是 | |
|表 | 是 | |
||||

<sup>1</sup> 会议 (和) 元数据包括以下内容：

- 会议开始时间和结束时间以及持续时间
- 每个参与者的会议加入和离开事件
- VOIP 加入/呼叫
- 匿名加入
- 联合用户加入
- 来宾用户加入

  该图像显示了会议元数据的示例。

  > [!div class="mx-imgBorder"]
  > ![合规性副本中的会议元数据。](media/conversationOption3.png)

下面是会议期间参与者之间的即时消息对话示例。

![对话中参与者Teams。](media/MeetingIMConversations.png)

> [!div class="mx-imgBorder"]
> ![电子数据展示搜索结果中的参与者之间的对话。](media/MeetingImConversation2.png)

有关执行电子数据展示调查的信息，请参阅核心 [电子数据展示入门](/microsoft-365/compliance/get-started-core-ediscovery)。

Microsoft Teams电子数据展示导出输出中，Excel IM 或对话。 导出邮件后`.pst`，Outlook打开文件以查看这些邮件。

查看团队的 .pst 文件时，所有对话都位于"对话历史记录"下的"团队聊天"文件夹中。 消息的标题包含团队名称和频道名称。 例如，下图显示了 Bob 发来的消息，他向制造规格Project 7 标准频道发送消息。

![Outlook 中用户邮箱中的“团队聊天”文件夹屏幕截图。](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

用户邮箱中的私人聊天存储在"对话历史记录"下的"团队聊天"文件夹中。

## <a name="ediscovery-of-private-channels"></a>私人频道电子数据展示

在专用频道中发送的邮件的合规性副本将传递到所有专用频道成员的邮箱，而不是发送到组邮箱。 合规性副本的标题经过格式化，以指示它们从哪个专用频道发送。

由于每个专用频道都有自己的SharePoint网站，与父团队网站分开，因此专用频道中的文件独立于父团队进行管理。

Teams不支持对团队中的单个频道进行电子数据展示搜索，因此必须搜索整个团队。 若要在专用频道中对内容执行电子数据展示搜索，请在整个团队中搜索、与专用频道关联的网站集 (以包含文件) 以及专用频道成员的邮箱 (以包含邮件) 。

使用以下步骤在专用通道中标识要包括在电子数据展示搜索中的文件和消息。

### <a name="include-private-channel-files-in-an-ediscovery-search"></a>在电子数据展示搜索中包括专用频道文件

执行这些步骤之前，请安装 [SharePoint Online 命令行管理程序并连接到 SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)。

1. 运行以下代码，获取与SharePoint频道关联的所有网站集的列表。

    ```PowerShell
    Get-SPOSite
    ```

2. 运行以下 PowerShell 脚本，获取与团队中专用SharePoint关联的所有网站集 URL 的列表，以及父团队组 ID。

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url}
    ```

3. 对于每个团队或组 ID，请运行以下 PowerShell 脚本来标识所有相关的专用频道网站，其中 `$groupID` 是团队的组 ID。

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```
> [!NOTE]
> SharePoint 2021 `teamchannel#1` 年 6 月 28 日之后创建的专用频道的网站使用 值作为自定义模板 ID。 因此，对于在此日期之后创建的专用通道，在运行 `teamchannel#1` 前两个脚本时请使用 值。

### <a name="include-private-channel-messages-in-an-ediscovery-search"></a>在电子数据展示搜索中包括私人频道消息

执行这些步骤之前，请确保已安装最新版本的 [Teams PowerShell 模块](teams-powershell-overview.md)。

1. 运行以下命令，获取包含要搜索的专用频道的团队的组 ID。

   ```powershell
   Get-Team -MailNickName <mail alias of the associated Office 365 Group>
   ```

   > [!TIP]
   > 运行 **不带任何参数的 Get-Team** cmdlet 以显示组织中Teams列表。 该列表包含每个团队的组 ID 和 MailNickName。

2. 运行以下命令，获取团队中的专用频道列表。 使用在步骤 1 中获取的团队的组 ID。

    ```PowerShell
    Get-TeamChannel -GroupId <GroupId> -MembershipType Private
    ```

3. 运行以下命令，获取专用频道所有者和成员的列表。

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupId> -DisplayName "Engineering" 
    ```

4. 在电子数据展示搜索查询中包括团队中每个专用频道的所有所有者和成员的 [邮箱](/microsoft-365/compliance/search-for-content-in-core-ediscovery)。

## <a name="search-for-content-for-guest-users"></a>搜索来宾用户的内容

可以使用电子数据展示工具搜索Teams来宾用户的相关内容。 Teams与来宾用户关联的聊天内容保存在基于云的存储位置，并且可以使用电子数据展示进行搜索。 这包括在 1：1 和 1：N 聊天对话中搜索内容，其中来宾用户是组织中其他用户的参与者。 还可以搜索来宾用户是参与者的私人频道消息，并搜索来宾 *：* 来宾聊天对话中仅参与者是来宾用户的内容。

搜索来宾用户的内容：

1. 连接 PowerShell Azure AD。 有关说明，请参阅使用 [PowerShell](/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module) 连接"Azure Active Directory PowerShell 连接"Microsoft 365部分。 请务必完成上一主题中的步骤 1 和步骤 2。

2. 成功连接到 PowerShell Azure AD，请运行以下命令，为组织的所有来宾用户 (UPN) 用户主体名称。 在步骤 4 创建搜索时，必须使用来宾用户的 UPN。

   ```powershell
   Get-AzureADUser -Filter "userType eq 'Guest'" -All $true | FL UserPrincipalName
   ```

   > [!TIP]
   > 可以将命令的输出重定向到文本文件，而不是在计算机屏幕上显示用户主体名称列表。 为此，可以追加到上 `> filename.txt` 一命令。 具有用户主体名称的文本文件将保存到当前文件夹。

3. 在不同的安全Windows PowerShell，连接到安全&中心 PowerShell。 有关说明，请参阅[连接安全&中心 PowerShell](/powershell/exchange/connect-to-scc-powershell)。 可以使用或无需使用多重身份验证进行连接。

4. 通过运行以下命令，创建内容搜索 (，例如聊天消息和电子邮件) 指定来宾用户是参与者。

   ```powershell
   New-ComplianceSearch <search name> -ExchangeLocation <guest user UPN>  -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

   例如，若要搜索与来宾用户 Sara Davis 关联的内容，请运行以下命令。

   ```powershell
   New-ComplianceSearch "Sara Davis Guest User" -ExchangeLocation "sara.davis_hotmail.com#EXT#@contoso.onmicrosoft.com" -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

    有关使用 PowerShell 创建内容搜索的信息，请参阅 [New-ComplianceSearch](/powershell/module/exchange/new-compliancesearch)。

5. 运行以下命令以启动在步骤 4 中创建的内容搜索：

   ```powershell
   Start-ComplianceSearch <search name>
   ```

6. 转到 ， [https://compliance.microsoft.com](https://compliance.microsoft.com) 然后单击" **显示所有** > **内容搜索"**。

7. 在搜索列表中，选择在步骤 4 中创建的搜索以显示飞出页。

8. 在"飞出"页上，可以执行以下操作：

   - 单击 **"查看** 结果"以查看搜索结果并预览内容。

   - 在" **查询"字段** 旁边，单击 **"编辑** "进行编辑，然后重新运行搜索。 例如，可以添加搜索查询来缩小结果范围。

   - 单击 **"导出** 结果"导出并下载搜索结果。

## <a name="search-for-card-content"></a>搜索卡片内容

由应用在 Teams、1：1 聊天和 1xN 聊天中生成的卡内容存储在邮箱中，可以搜索。 *卡是* 一个 UI 容器，用于提供简短的内容。 卡片可以有多个属性和附件，并且可以包含可以触发卡片操作的按钮。 有关详细信息，请参阅 [卡片](/microsoftteams/platform/task-modules-and-cards/what-are-cards)

与其他Teams一样，卡内容的存储位置取决于卡的使用位置。 在组邮箱中Teams卡片的内容存储在Teams邮箱中。 1：1 和 1xN 聊天的卡内容存储在聊天参与者的邮箱中。

若要搜索卡片内容，可以使用 或 `kind:microsoftteams` 搜索 `itemclass:IPM.SkypeTeams.Message` 条件。 查看搜索结果时，Teams 通道中机器人生成的卡内容将发件人 **/** 作者电子邮件属性作为 `<appname>@teams.microsoft.com`，`appname`其中 是生成卡内容的应用的名称。 如果卡内容是由用户生成的，则"发件人/作者 **"的值将** 标识该用户。

在内容搜索结果中查看卡片内容时，内容显示为邮件的附件。 附件名为 `appname.html`，其中 `appname` 是生成卡内容的应用的名称。 以下屏幕截图显示名为 Asana (应用的卡片内容) 显示在Teams和搜索结果中。

**卡片内容Teams**

![频道消息中的Teams内容。](media/CardContentTeams.png)

**搜索结果中的卡片内容**
  
![内容搜索结果中的卡内容相同。](media/CardContentEdiscoverySearchResults.png)

> [!NOTE]
> 若要在此时在搜索结果中显示卡内容的图像 (如上一屏幕截图) 中的选中标记，您必须在用于查看搜索结果的同一浏览器会话的不同选项卡https://teams.microsoft.com)中登录到 Teams (。 否则，会显示图像占位符。

## <a name="related-topics"></a>相关主题

- [Microsoft 365电子数据展示解决方案](/microsoft-365/compliance/ediscovery)
- [核心电子数据展示入门](/microsoft-365/compliance/get-started-core-ediscovery)
- [Teams工作流Advanced eDiscovery](/microsoft-365/compliance/teams-workflow-in-advanced-ediscovery)
- [Teams PowerShell 概览](teams-powershell-overview.md)
