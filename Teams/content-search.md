---
title: 在 Microsoft Teams 中使用内容搜索
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: anach
search.appverid: MET150
description: 了解 Microsoft 团队中的内容搜索以及如何搜索来自 Exchange 的频道对话、来自 SharePoint 的文件上载和修改以及 OneNote 更改。
appliesto:
- Microsoft Teams
ms.openlocfilehash: faed09a5fafaec559bc4277b75a60d8cc594fa85
ms.sourcegitcommit: 4a22bf77f529cfc2e68a6498a0c4aa9030ee2168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2019
ms.locfileid: "37968283"
---
<a name="use-content-search-in-microsoft-teams"></a>在 Microsoft Teams 中使用内容搜索
=====================================

> [!NOTE]
> [专用频道](private-channels.md)中的邮件和文件的内容搜索与在标准频道中的工作方式不同。 若要了解详细信息，请参阅[私人频道的内容搜索](#content-search-of-private-channels)。

内容搜索提供了一种方法，可查询 Microsoft 团队信息，跨越 Exchange、SharePoint Online 和 OneDrive for business。

若要了解详细信息，请阅读[Office 365 中的内容搜索](https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a)。

例如，针对制造规范邮箱和制造规范 SharePoint 网站使用**内容搜索**，您可以从 Exchange、文件上载和 sharepoint Online 的修改中搜索团队标准频道对话。和 OneNote 更改。

您还可以将查询条件添加到**内容搜索**，以缩小返回的结果范围。 在上面的示例中，你可以查找使用 "**新工厂规范"** 关键字的内容。

> [!TIP]
> 添加搜索条件后，您可以将报表或数据导出到计算机进行分析。

## <a name="content-search-of-private-channels"></a>专用频道的内容搜索

在专用频道中发送的邮件的记录被发送到所有专用通道成员的邮箱，而不是发送到组邮箱。 对记录的标题进行格式设置，以指示发送的专用频道。

由于每个专用频道都有自己的 SharePoint 网站集，独立于父团队网站，因此专用通道中的文件独立于父团队进行管理。

团队不支持对单个频道进行内容搜索，因此必须搜索整个团队。 若要执行私人频道的内容搜索，请搜索整个团队、与专用频道相关联的网站集（包括文件）和专用频道成员的邮箱（包括邮件）。

使用以下步骤标识要包括在内容搜索中的专用频道中的文件和邮件。

### <a name="include-private-channel-files-in-a-content-search"></a>在内容搜索中包括专用通道文件

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
3. 对于每个团队或组 ID，请运行以下 PowerShell 脚本以标识所有相关的专用通道站点。

    ```
    $sites = get-sposite -template "teamchannel#0"
    $groupID = “e8195240-4a70-4830-9106-80193cf717cb“
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-a-content-search"></a>在内容搜索中包括专用频道消息

在执行这些步骤之前，请确保安装了[最新版本的团队 PowerShell 模块](teams-powershell-overview.md)。

1. 运行以下操作以获取团队中的专用通道的列表。

    ```
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```
2. 运行以下操作以获取专用通道成员的列表。

    ```
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```
3. 将团队中每个专用频道的所有成员的邮箱添加为内容搜索查询的一部分。

## <a name="related-topics"></a>相关主题

- [Office 365 安全 & 合规中心中的电子数据展示事例](https://docs.microsoft.com/Office365/SecurityCompliance/ediscovery-cases) 