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
description: 了解如何在 Microsoft Purview 合规性门户中使用内容搜索来搜索存储在 Exchange Online、SharePoint Online、OneDrive for Business 和 OneNote 中的Microsoft Teams内容。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 00de0bb3ecdcaf6dc674f08438b896abaaa49448
ms.sourcegitcommit: 1d990582e2deb5f55ba9adada3e17377f792a141
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2022
ms.locfileid: "64922473"
---
# <a name="use-content-search-in-microsoft-teams"></a>在Microsoft Teams中使用内容搜索

> [!NOTE]
> [在专用频道](private-channels.md)中对消息和文件的内容搜索的工作方式不同于标准频道中的内容搜索。 若要了解详细信息，请参阅 [专用频道的内容搜索](#content-search-of-private-channels)。

内容搜索提供了一种查询跨Exchange、SharePoint联机和OneDrive for Business Microsoft Teams信息的方法。

若要了解详细信息，请参阅[Microsoft 365中的内容搜索](/microsoft-365/compliance/content-search)。

例如，对“制造规范”邮箱和制造规范SharePoint网站使用 **内容搜索**，可以搜索来自Exchange的Teams标准频道对话、文件上传和来自 SharePoint Online 的修改，以及OneNote更改。

还可以将查询条件添加到 **内容搜索** ，以缩小返回的结果范围。 在上面的示例中，可以查找使用关键字“**新建工厂规范”** 的内容。

> [!TIP]
> 添加搜索条件后，可以将报表或实际内容导出到计算机进行分析。

## <a name="content-search-of-private-channels"></a>专用频道的内容搜索

在私人频道中发送的消息记录将传递到所有私人频道成员的邮箱，而不是传递到组邮箱。 记录的标题已格式化为指示它们是从哪个私人频道发送的。

由于每个专用频道都有自己的SharePoint与父团队网站分开的网站集，因此专用频道中的文件独立于父团队进行管理。

Teams不支持单个频道的内容搜索，因此必须搜索整个团队。 若要对专用频道执行内容搜索，请在团队中进行搜索，与专用频道关联的网站集 (包含文件) ，以及 (包含邮件) 的专用频道成员的邮箱。

使用以下步骤标识专用通道中要包含在内容搜索中的文件和消息。

### <a name="include-private-channel-files-in-a-content-search"></a>在内容搜索中包括专用频道文件

在执行这些步骤之前，请安装 [SharePoint Online Management Shell 并连接到 SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)。

1. 运行以下命令，获取与团队中的专用频道关联的所有SharePoint网站集的列表。

    ```PowerShell
    Get-SPOSite
    ```
2. 运行以下 PowerShell 脚本，获取与团队中的专用频道和父团队组 ID 关联的所有SharePoint网站集 URL 的列表。

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url} 
    ```
3. 对于每个团队或组 ID，请运行以下 PowerShell 脚本来标识所有相关的专用频道网站。

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-a-content-search"></a>在内容搜索中包括专用频道消息

在执行这些步骤之前，请确保已安装[最新版本的 Teams PowerShell 模块](teams-powershell-overview.md)。

1. 运行以下命令以获取团队中专用频道的列表。

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```
2. 运行以下命令以获取专用频道成员的列表。

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```
3. 将团队中每个专用频道中所有成员的邮箱作为内容搜索查询的一部分。

## <a name="related-topics"></a>相关主题

- [Microsoft Purview 合规性门户中的电子数据展示案例](/Office365/SecurityCompliance/ediscovery-cases)