---
title: 在 Microsoft Teams 中对内容进行电子数据展示调查
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- SPO_Content
ms.reviewer: anach
search.appverid: MET150
description: 了解你需要执行电子数据展示时（例如，你需要提交所有电子方式存储的信息用于法律程序时）要完成的事项。
appliesto:
- Microsoft Teams
ms.openlocfilehash: e645085130b65283a1841661c4e2885e5ea9cba4
ms.sourcegitcommit: ddb4eaf634476680494025a3aa1c91d15fb58413
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/11/2019
ms.locfileid: "38231113"
---
<a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a>在 Microsoft Teams 中对内容进行电子数据展示调查
============================

大型企业经常面临高处罚的法律诉讼，要求提交所有电子存储的信息（ESI）。

所有团队1:1 或群组聊天将被记录到各自的用户的邮箱中，并且所有标准信道消息都将记录到代表团队的组邮箱。 在标准频道中上载的文件包含在 SharePoint Online 和 OneDrive for business 的电子数据展示功能下方。

> [!NOTE]
> 电子数据展示[专用频道](private-channels.md)中的消息和文件与在标准频道中的工作方式不同。 若要了解详细信息，请参阅[电子数据展示专用频道](#ediscovery-of-private-channels)。

1.  若要使用 Microsoft 团队内容执行电子数据展示调查，请查看[此](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da)链接中的步骤1。

2.  Microsoft 团队数据将在 Excel 电子数据展示导出输出中显示为即时消息或对话，你可以装入。Outlook 中的 PST 以查看导出后的邮件。

    装载团队的 .PST 时，请注意，所有对话均保留在“对话历史记录”下的“团队聊天”文件夹中。 消息的标题与团队和频道一致。 查看下面的图像，您可以从 messaged 中看到此消息，这些信息来自于制造规范团队的项目7标准频道。

    ![Outlook 中的用户邮箱中的工作组聊天文件夹的屏幕截图](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

3.  若要查看用户邮箱中的私人聊天，他们还位于 "对话历史记录" 下的团队聊天文件夹内。

## <a name="ediscovery-of-guest-to-guest-chats"></a>电子数据展示的来宾到来宾聊天

如果没有邮箱，来宾至来宾聊天（没有家乡租户用户的1xN 聊天）将不会被编制索引，因此不会包含在电子数据展示中。 为了方便电子数据展示用于来宾到来宾聊天，创建了一个基于云的邮箱（或幻影邮箱）来存储1xN 数据。 团队聊天数据存储在基于云的邮箱中后，将为电子数据展示和合规性内容搜索编制索引。

下图显示了电子数据展示如何处理没有邮箱的来宾到来宾聊天。

![来宾至来宾-无邮箱聊天](media/conduct-an-ediscovery-investigation-of-content-in-microsoft-teams-image2.png)

## <a name="ediscovery-of-private-channels"></a>专用频道的电子数据展示

在专用频道中发送的邮件的记录被发送到所有专用通道成员的邮箱，而不是发送到组邮箱。 对记录的标题进行格式设置，以指示发送的专用频道。

由于每个专用频道都有自己的 SharePoint 网站集，独立于父团队网站，因此专用通道中的文件独立于父团队进行管理。

团队不支持单个通道的电子数据展示，因此必须搜索整个团队。 若要在专用频道中执行电子数据展示搜索，请在团队中搜索与专用频道相关联的网站集（包括文件）和专用频道成员的邮箱（包括邮件）。

使用以下步骤标识要包括在电子数据展示搜索中的专用通道中的文件和邮件。

### <a name="include-private-channel-files-in-an-ediscovery-search"></a>在电子数据展示搜索中包括专用信道文件

在执行这些步骤之前，请安装[Sharepoint Online 命令行管理程序并连接到 SharePoint online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)。

1. 运行以下操作以获取与团队中的专用通道相关联的所有 SharePoint 网站集的列表。

    ```
    Get-SPOSite
    ```
2. 运行以下 PowerShell 脚本，获取与团队和父团队组 ID 中的专用通道相关联的所有 SharePoint 网站集 Url 的列表。

    ```
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url} 
    ```
3. 对于每个团队或组 ID，运行以下 PowerShell 脚本来标识所有相关专用通道网站，其中 $groupID 是团队的组 ID。

    ```
    $sites = get-sposite -template "teamchannel#0"
    $groupID = “e8195240-4a70-4830-9106-80193cf717cb“
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-an-ediscovery-search"></a>在电子数据展示搜索中包括专用信道消息

在执行这些步骤之前，请确保安装了[最新版本的团队 PowerShell 模块](teams-powershell-overview.md)。

1. 运行以下操作以获取团队中的专用通道的列表。

    ```
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```
2. 运行以下操作以获取专用通道成员的列表。

    ```
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```
3. 将团队中每个专用频道的所有成员的邮箱添加为电子数据展示搜索查询的一部分。

## <a name="related-topics"></a>相关主题

- [Teams PowerShell 概览](teams-powershell-overview.md)