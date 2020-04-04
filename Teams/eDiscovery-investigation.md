---
title: 对内容进行电子数据展示调查
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
f1.keywords:
- NOCSH
description: 了解当你需要执行电子数据展示时需要执行的操作，例如当你需要提交所有电子存储的法律程序存储信息时需要执行的操作。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 955fbf6ba937ca0fc11270cb58c12a0349d46330
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/03/2020
ms.locfileid: "43136682"
---
# <a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a>在 Microsoft Teams 中对内容进行电子数据展示调查

大型企业经常面临高处罚的法律诉讼，要求提交所有电子存储的信息（ESI）。

所有团队1:1 或群组聊天将被记录到各自的用户的邮箱中，并且所有标准信道消息都将记录到代表团队的组邮箱。 在标准频道中上载的文件包含在 SharePoint Online 和 OneDrive for business 的电子数据展示功能下方。 电子数据展示[专用频道](private-channels.md)中的消息和文件与在标准频道中的工作方式不同。 若要了解详细信息，请参阅[电子数据展示专用频道](#ediscovery-of-private-channels)。

> [!NOTE]
> 目前，我们不支持仅在来宾用户是1:1 或1： N 聊天的参与者的方案中聊天消息的电子数据展示。 这些类型的聊天也称为*来宾到来宾*聊天，因为它们不包括家庭租户用户。

1. 若要使用 Microsoft 团队内容执行电子数据展示调查，请查看[此](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da)链接中的步骤1。

2. Microsoft 团队数据将在 Excel 电子数据展示导出输出中显示为即时消息或对话，您可以在 Outlook 中打开该 PST 以查看这些邮件的导出内容。

    查看团队的 PST 时，请注意所有对话都保存在 "对话历史记录" 下的 "工作组聊天" 文件夹中。 消息的标题与团队和频道一致。 查看下面的图像，您可以从 messaged 中看到此消息，这些信息来自于制造规范团队的项目7标准频道。

    ![Outlook 中的用户邮箱中的工作组聊天文件夹的屏幕截图](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

3. 若要查看用户邮箱中的私人聊天，他们还位于 "对话历史记录" 下的 "工作组聊天" 文件夹中。

## <a name="ediscovery-of-private-channels"></a>专用频道的电子数据展示

在私人频道中发送的消息记录将传递到所有私人频道成员的邮箱，而不是传递到组邮箱。 记录的标题已格式化为指示它们是从哪个私人频道发送的。

由于每个专用频道都有自己的 SharePoint 网站集，独立于父团队网站，因此专用通道中的文件独立于父团队进行管理。

团队不支持单个通道的电子数据展示，因此必须搜索整个团队。 若要在专用频道中执行电子数据展示搜索，请在团队中搜索与专用频道相关联的网站集（包括文件）和专用频道成员的邮箱（包括邮件）。

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

## <a name="related-topics"></a>相关主题

- [Teams PowerShell 概览](teams-powershell-overview.md)
