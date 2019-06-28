---
title: 在 Microsoft Teams 中管理对私人团队的发现
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: shpoddar
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 了解如何通过团队库和搜索结果控制 Microsoft 团队用户是否可以通过建议发现专用团队。
ms.openlocfilehash: 099daaed42e108e63a5f8334bd2ed89744479dbd
ms.sourcegitcommit: 3abc3dcaa79ebd8e4326fa282874500c4425e64f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/28/2019
ms.locfileid: "35347873"
---
# <a name="manage-discovery-of-private-teams-in-microsoft-teams"></a>在 Microsoft Teams 中管理对私人团队的发现

[!INCLUDE [preview-feature](includes/preview-feature.md)]

管理员和团队所有者可以控制你的组织中的 Microsoft 团队用户是否可以发现专用团队。 当私人团队可发现时, 它将显示在搜索结果中, 并包含在团队的团队库和团队中的公共团队的建议中。 这使用户可以轻松地搜索和查找他们想要加入的专用团队。 用户可以请求加入专用团队, 然后团队所有者可以批准或拒绝该请求。

## <a name="overview-of-public-teams-private-teams-and-discovery-in-teams"></a>团队中的公共团队、私人团队和发现概述

大多数组织都具有以下类型的团队: 公共团队、可发现的专用团队和不可发现的专用团队。

![团队库的屏幕截图](media/private-team-discovery-team-gallery.png)

### <a name="public-teams"></a>公共团队

公共团队可供组织中的所有用户加入。 公共团队对于团队库中的每个人都是可见的, 用户可以加入公共团队, 而无需从团队所有者获得批准。 公共团队的示例包括团队讨论技术新闻、团队以获取有关产品的反馈, 以及 carpooling 人员的团队。

### <a name="discoverable-private-teams"></a>可发现的专用团队

只有当团队所有者将用户添加到可发现专用团队时, 才能将其加入。 当您使私人团队可发现时, 团队将包含在团队库中的建议团队和搜索结果列表中。 对你的组织中的项目和组使用可发现的专用团队, 每个人都知道, 并且需要对团队中的对话和文件的访问权限进行控制。 示例包括人力资源部门的团队、组织中所有经理的团队以及经理及其直接下属的团队。

### <a name="non-discoverable-private-teams"></a>不可发现的私人团队

不可发现的专用团队只能在团队所有者向他们添加用户时加入。 当您将某个私人团队设置为 "未发现" 时, 它将隐藏在建议的团队列表中, 并从团队库中的搜索结果中删除。 使用不可发现的团队协作处理敏感和高度机密的主题。 示例包括一个团队, 讨论即将进行的收购和团队讨论组织的战略方向的变化。

## <a name="set-whether-new-private-teams-are-discoverable"></a>设置新的专用团队是否可发现

当团队所有者创建专用团队时, 他们可以通过配置团队的发现设置来选择使其可发现。 默认情况下, 新的专用团队是可搜索和可发现的。 如果团队所有者不希望私人团队显示在搜索结果和建议中, 所有者可以通过选择**此团队**旁边的 "**更改" 设置**来关闭设置。

![新专用团队的发现设置的屏幕截图](media/private-team-discovery-new-team.png)

## <a name="set-whether-existing-private-teams-are-discoverable"></a>设置现有专用团队是否可发现

团队所有者可以直接在团队设置中设置现有专用团队的发现设置, 并且管理员可以通过使用 PowerShell 来执行此操作。

### <a name="in-team-settings"></a>在团队设置中

在 "团队" 中, 转到 "专用团队", 单击 "**更多选项** > **管理团队**"。 在 "**设置**" 选项卡上, 展开 "**团队发现**", 然后清除或选中 "**打开发现**" 复选框。

![现有专用团队的发现设置的屏幕截图](media/private-team-discovery-existing-team.png)

### <a name="using-powershell"></a>使用 PowerShell

使用 "**[设置团队](https://docs.microsoft.com/powershell/module/teams/set-team?view=teams-ps)** cmdlet" 关闭或打开现有专用团队的发现设置。 下面是如何让团队易于发现的示例:
```
    Set-Team -GroupId 0abc123d-e4f5-67gh-i890-jk1m2n345o6p -ShowInSearchAndSuggestions $true
```
你可以在脚本中使用此 cmdlet 来批量设置现有专用团队的发现设置。

## <a name="set-whether-users-can-discover-private-teams"></a>设置用户是否可以发现专用团队

作为管理员, 你还可以控制你的组织中的哪些用户可以在搜索结果和团队中的建议中发现专用团队。 使用**[CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps)** cmdlet 创建策略, 然后将策略分配给用户。
 
将**AllowPrivateTeamDiscovery**参数设置为**true** , 以允许分配了该策略的用户在搜索结果和建议中查看可发现的专用团队。 将**AllowPrivateTeamDiscovery**参数设置为**false**可从搜索结果中删除所有发现的专用团队, 并为分配了该策略的用户提出建议。

默认情况下, 对于组织中的所有用户, **AllowPrivateTeamDiscovery**设置为**true** 。

在此示例中, 我们创建一个名为 VendorPolicy 的策略, 该策略阻止用户发现任何已被发现的专用团队, 然后我们将该策略分配给名为 vendoruser1 的用户。
```
     New-CsTeamsChannelsPolicy -Identity VendorPolicy -AllowPrivateTeamDiscovery $false
     Grant-CsTeamsChannelsPolicy -Identity vendoruser1@company.com -PolicyName VendorPolicy
```

> [!NOTE]
> 不能检测到的私有团队从不会显示在搜索结果和建议中, 而与策略设置无关。 例如, 如果你关闭了专用团队的发现设置, 则用户无法发现团队, 即使在这些用户的策略设置中**AllowPrivateTeamDiscovery**参数设置为 true 也是**如此**。

## <a name="related-topics"></a>相关主题
- [Teams PowerShell 概览](teams-powershell-overview.md)