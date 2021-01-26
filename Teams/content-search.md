---
title: 在 Microsoft Teams 中使用内容搜索
author: markjjo
ms.author: markjjo
manager: laurawi
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
- SPO_Content
ms.reviewer: anwara
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
description: 了解如何使用 Microsoft 365 合规中心的内容搜索来搜索存储在 Exchange Online、SharePoint Online、OneDrive for Business 和 OneNote 中的 Microsoft Teams 内容。
appliesto:
- Microsoft Teams
ms.openlocfilehash: f91e630b6f0666def3e64e40e68a6a3f18097152
ms.sourcegitcommit: 0b584d40e95cbde33cee3691edadb12156d72fb5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "49980436"
---
<a name="use-content-search-in-microsoft-teams"></a>在 Microsoft Teams 中使用内容搜索
=====================================

> [!NOTE]
> 在专用频道中对消息 [和文件进行内容搜索](private-channels.md) 的方式与在标准通道中不同。 若要了解更多信息，请参阅 [专用频道的内容搜索](#content-search-of-private-channels)。

内容搜索提供了一种跨 Exchange、SharePoint Online 和 OneDrive for Business 查询 Microsoft Teams 信息的方法。

若要了解有关详细信息，请参阅 [Microsoft 365 中的内容搜索](https://docs.microsoft.com/microsoft-365/compliance/content-search)。

例如，对制造规范邮箱和制造规范 SharePoint 网站使用内容搜索，可以针对 Exchange 中的 Teams 标准频道对话、SharePoint Online 中的文件上传和修改以及 OneNote 更改进行搜索。

您还可以向内容搜索添加查询 **条件以** 缩小返回的结果范围。 在以上示例中，可以查找使用了关键字"新工厂规范 **"** 的内容。

> [!TIP]
> 添加搜索条件后，可以将报表或实际内容导出到计算机进行分析。

## <a name="content-search-of-private-channels"></a>专用频道的内容搜索

在私人频道中发送的消息记录将传递到所有私人频道成员的邮箱，而不是传递到组邮箱。 记录的标题已格式化为指示它们是从哪个私人频道发送的。

由于每个专用频道都有自己的 SharePoint 网站集，与父团队网站分开，因此专用频道中的文件独立于父团队进行管理。

Teams 不支持单个频道的内容搜索，因此必须搜索整个团队。 要执行专用频道的内容搜索，请在整个团队中搜索、与专用频道关联的网站集 (以包含文件) ，以及专用频道成员的邮箱 (以包含) 。

使用以下步骤识别专用通道中要包括在内容搜索中的文件和消息。

### <a name="include-private-channel-files-in-a-content-search"></a>在内容搜索中包括专用频道文件

执行这些步骤之前，请安装[SharePoint Online 命令行管理程序并连接到 SharePoint Online。](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

1. 运行以下代码，获取与团队中的专用频道关联的所有 SharePoint 网站集的列表。

    ```PowerShell
    Get-SPOSite
    ```
2. 运行以下 PowerShell 脚本，获取与团队中的专用频道关联的所有 SharePoint 网站集 URL 的列表和父团队组 ID。

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url} 
    ```
3. 对于每个团队或组 ID，请运行以下 PowerShell 脚本来标识所有相关的专用频道站点。

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-a-content-search"></a>在内容搜索中包括专用频道消息

执行这些步骤之前，请确保已安装最新版本的 Teams [PowerShell 模块](teams-powershell-overview.md) 。

1. 运行以下代码，获取团队中的专用频道列表。

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```
2. 运行以下代码获取专用通道成员的列表。

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```
3. 在内容搜索查询中包括团队中每个专用频道中所有成员的邮箱。

## <a name="related-topics"></a>相关主题

- [Microsoft 365 合规中心中的电子数据展示事例](https://docs.microsoft.com/Office365/SecurityCompliance/ediscovery-cases) 