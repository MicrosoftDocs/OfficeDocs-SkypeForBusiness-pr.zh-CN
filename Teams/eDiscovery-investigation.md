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
ms.openlocfilehash: b9010bb233438029d6e755cf1fcd8b78b7cba6eb
ms.sourcegitcommit: 79d20fa2c45173d5a990551e79571caff06d7f82
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2021
ms.locfileid: "53486162"
---
# <a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a>在 Microsoft Teams 中对内容进行电子数据展示调查

大型企业经常面临高处罚诉讼，这些诉讼要求提交所有电子存储信息 (ESI) 。 Microsoft Teams电子数据展示调查期间可以搜索和利用内容。

## <a name="overview"></a>概述

所有Microsoft Teams 1：1 或群组聊天都记录到相应用户的邮箱。 所有标准频道邮件都记录到代表团队的组邮箱。 在标准通道中上传的文件在 SharePoint Online 和 OneDrive for Business 电子数据展示功能下OneDrive for Business。

在专用通道中电子数据展示消息和[](private-channels.md)文件的工作方式与在标准通道中的工作方式不同。 若要了解有关详细信息，请参阅 [专用频道的电子数据展示](#ediscovery-of-private-channels)。

并非所有Teams内容都是可电子数据展示的。 下表显示了可以使用 Microsoft 电子数据展示工具搜索的内容类型：

| 内容类型 | 电子数据展示 | 注释 |
|:--- | :--- |:--- |
|录音 | 弱 | |
|卡片内容|是|有关详细信息 [，请参阅搜索](#search-for-card-content) 卡片内容。|
|聊天链接 | 是 | |
|聊天消息 | 是 |这包括以下Teams中的内容、1：1 聊天、1：N 群组聊天，以及与来宾用户参与者的聊天。  |
|代码片段 | 弱 | |
|已编辑的消息 | 是 | 如果用户保持保留状态，也会保留以前版本的已编辑消息。 |
|表情符号、GIF 和贴纸 | 是 | |
|内联图像 | 是 | |
|会议 IM 对话 | 是 | |
|会议元数据<sup>1</sup> | 是 |  |
|频道名称 | 弱 | |
|专用频道消息 | 是 | |
|引号 | 是 | 引用的内容可搜索。 但是，搜索结果并不指示内容已引用。 |
|反应 (，如喜欢、心声和其他反应)  | 弱 | |
|主题 | 是 | |
|表 | 是 | |
|源通知 | 弱 | |
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
  > ![图像是 CVR 记录会议元数据。](media/conversationOption3.png)

下面是会议期间参与者之间的即时消息对话示例。

![对话中参与者Teams。](media/MeetingIMConversations.png)

> [!div class="mx-imgBorder"]
> ![电子数据展示搜索结果中的参与者之间的对话。](media/MeetingImConversation2.png)

有关执行电子数据展示调查的信息，请参阅核心 [电子数据展示入门](/microsoft-365/compliance/get-started-core-ediscovery)。

Microsoft Teams电子数据展示导出输出中，Excel IM 或对话。 导出邮件 `.pst` 后，Outlook打开文件以查看这些邮件。

查看团队的 .pst 文件时，所有对话都位于"对话历史记录"下的"团队聊天"文件夹中。 消息的标题包含团队名称和频道名称。 例如，下图显示了 Bob 发来的消息，他向制造规范Project 7 标准频道发送消息。

![用户邮箱中的团队聊天文件夹的屏幕截图Outlook](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

用户邮箱中的私人聊天存储在"对话历史记录"下的"团队聊天"文件夹中。

## <a name="ediscovery-of-private-channels"></a>私人频道电子数据展示

在私人频道中发送的消息记录将传递到所有私人频道成员的邮箱，而不是传递到组邮箱。 记录的标题已格式化为指示它们是从哪个私人频道发送的。

由于每个专用频道都有自己的SharePoint网站，与父团队网站分开，因此专用频道中的文件独立于父团队进行管理。

Teams不支持对团队中的单个频道进行电子数据展示搜索，因此必须搜索整个团队。 若要在专用频道中对内容执行电子数据展示搜索，请在整个团队中搜索与专用频道关联的网站集 (以包含文件) ，以及专用频道成员 (以包含消息) 。

使用以下步骤在专用通道中标识要包括在电子数据展示搜索中的文件和消息。

### <a name="include-private-channel-files-in-an-ediscovery-search"></a>在电子数据展示搜索中包括专用频道文件

执行这些步骤之前，请安装[SharePoint Online 命令行管理程序并连接到 SharePoint Online。](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

1. 运行以下代码，获取与SharePoint专用频道关联的所有网站集的列表。

    ```PowerShell
    Get-SPOSite
    ```

2. 运行以下 PowerShell 脚本，获取与团队中专用SharePoint关联的所有网站集 URL 的列表，以及父团队组 ID。

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url}
    ```

3. 对于每个团队或组 ID，请运行以下 PowerShell 脚本来标识所有相关的专用频道网站，其中$groupID是团队的组 ID。

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-an-ediscovery-search"></a>在电子数据展示搜索中包括私人频道消息

执行这些步骤之前，请确保已安装最新版本Teams [PowerShell 模块](teams-powershell-overview.md)。

1. 运行以下命令，获取团队中的专用频道列表。

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```

2. 运行以下命令，获取专用通道成员的列表。

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```

3. 在电子数据展示搜索查询 中包括团队中每个专用频道中所有成员 [的邮箱](/microsoft-365/compliance/search-for-content-in-core-ediscovery)。

## <a name="search-for-content-for-guest-users"></a>搜索来宾用户的内容

可以使用电子数据展示工具搜索Teams来宾用户相关的内容。 Teams与来宾用户关联的聊天内容保存在基于云的存储位置，并且可以使用电子数据展示进行搜索。 这包括在 1：1 和 1：N 聊天对话中搜索内容，其中来宾用户是组织中其他用户的参与者。 还可以搜索来宾用户是参与者的私人频道消息，并搜索来宾 *：* 来宾聊天对话中仅参与者是来宾用户的内容。

搜索来宾用户的内容：

1. 连接 Azure AD PowerShell。 有关说明，请参阅连接 PowerShell Azure Active Directory中的"连接[powerShell](/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)Microsoft 365部分。 请务必完成上一主题中的步骤 1 和步骤 2。

2. 成功连接到 Azure AD PowerShell 后，运行以下命令，显示组织中所有来宾 (UPN) 用户主体名称。 在步骤 4 创建搜索时，必须使用来宾用户的 UPN。

   ```powershell
   Get-AzureADUser -Filter "userType eq 'Guest'" -All $true | FL UserPrincipalName
   ```

   > [!TIP]
   > 可以将命令的输出重定向到文本文件，而不是在计算机屏幕上显示用户主体名称列表。 为此，可以追加到上 `> filename.txt` 一命令。 包含用户主体名称的文本文件将保存到当前文件夹。

3. 在不同的安全Windows PowerShell，连接到安全&中心 PowerShell。 有关说明，请参阅连接[安全&中心 PowerShell。](/powershell/exchange/connect-to-scc-powershell) 可以使用或无需使用多重身份验证进行连接。

4. 通过运行以下命令创建内容搜索 (搜索所有内容，例如聊天消息) 指定来宾用户是参与者的电子邮件。

   ```powershell
   New-ComplianceSearch <search name> -ExchangeLocation <guest user UPN>  -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

   例如，若要搜索与来宾用户 Sara Davis 关联的内容，请运行以下命令。

   ```powershell
   New-ComplianceSearch "Sara Davis Guest User" -ExchangeLocation "sara.davis_hotmail.com#EXT#@contoso.onmicrosoft.com" -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

    有关使用 PowerShell 创建内容搜索的信息，请参阅[New-ComplianceSearch。](/powershell/module/exchange/new-compliancesearch)

5. 运行以下命令以启动在步骤 4 中创建的内容搜索：

   ```powershell
   Start-ComplianceSearch <search name>
   ```

6. 转到 ， [https://compliance.microsoft.com](https://compliance.microsoft.com) 然后单击"**显示所有**  >  **内容搜索"。**

7. 在搜索列表中，选择在步骤 4 中创建的搜索以显示飞出页。

8. 在"飞出"页上，可以执行以下操作：

   - 单击 **"查看** 结果"以查看搜索结果并预览内容。

   - 在" **查询"字段** 旁边，单击 **"编辑** "进行编辑，然后重新运行搜索。 例如，可以添加搜索查询来缩小结果范围。

   - 单击 **"导出** 结果"导出并下载搜索结果。

## <a name="search-for-card-content"></a>搜索卡片内容

由应用在 Teams、1：1 聊天和 1xN 聊天中生成的卡内容存储在邮箱中，可以搜索。 卡 *是* 一个 UI 容器，用于提供简短的内容。 卡片可以有多个属性和附件，并且可以包含可触发卡操作的按钮。 有关详细信息，请参阅 [卡片](/microsoftteams/platform/task-modules-and-cards/what-are-cards)

与其他Teams一样，卡内容的存储位置取决于卡的使用位置。 在组邮箱中Teams卡片的内容存储在Teams邮箱中。 1：1 和 1xN 聊天的卡内容存储在聊天参与者的邮箱中。

若要搜索卡片内容，可以使用 `kind:microsoftteams` 或 `itemclass:IPM.SkypeTeams.Message` 搜索条件。 查看搜索结果时，Teams 通道中机器人生成的卡内容将发件人 **/** 作者电子邮件属性作为 ，其中 是生成卡内容 `<appname>@teams.microsoft.com` `appname` 的应用的名称。 如果卡内容是由用户生成的，则"发件人/作者 **"的值将** 标识该用户。

在内容搜索结果中查看卡片内容时，内容显示为邮件的附件。 附件名为 `appname.html` ，其中 `appname` 是生成卡内容的应用的名称。 以下屏幕截图显示名为 Asana (应用的卡片内容) 显示在Teams和搜索结果中。

**卡片内容Teams**

![频道消息Teams卡片内容](media/CardContentTeams.png)

**搜索结果中的卡片内容**
  
![内容搜索结果中的同一卡内容](media/CardContentEdiscoverySearchResults.png)

> [!NOTE]
> 若要在 (此时在搜索结果中显示卡片内容的图像，例如上一屏幕截图) 中的选中标记，您必须在用于查看搜索结果的同一浏览器会话中的不同选项卡中登录到 Teams (。 https://teams.microsoft.com) 否则，会显示图像占位符。

## <a name="related-topics"></a>相关主题

- [Microsoft 365电子数据展示解决方案](/microsoft-365/compliance/ediscovery)
- [核心电子数据展示入门](/microsoft-365/compliance/get-started-core-ediscovery)
- [Teams工作流Advanced eDiscovery](/microsoft-365/compliance/teams-workflow-in-advanced-ediscovery)
- [Teams PowerShell 概览](teams-powershell-overview.md)
