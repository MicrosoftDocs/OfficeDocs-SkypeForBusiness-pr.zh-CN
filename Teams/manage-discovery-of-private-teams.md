---
title: 管理中的 Microsoft 团队的专用工作组的发现
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 4/25/2019
ms.reviewer: shpoddar
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 了解如何控制是否可以发现的 Microsoft 团队用户通过团队库和搜索结果中的建议的专用工作组。
ms.openlocfilehash: 3609a592c3c940e9f7cbec6ca5c58fd072322c46
ms.sourcegitcommit: 0bb55cad74b15fc821ae916799aa8c0cb13dd31d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/30/2019
ms.locfileid: "33497950"
---
# <a name="manage-discovery-of-private-teams-in-microsoft-teams"></a>管理中的 Microsoft 团队的专用工作组的发现

> [!INCLUDE [preview feature](includes/preview-feature.md)] 

管理员和团队所有者可以控制是否可以发现您的组织中的 Microsoft 团队用户的专用工作组。 可供搜索的专用工作组后，它显示在搜索结果中，并包含在公共 リ モ ・ 团队旁的工作组库中的建议。 这样，用户可以方便地搜索和查找要加入的 private 团队。 用户可以请求加入该团队所有者可以然后批准或拒绝的专用工作组。

## <a name="overview-of-public-teams-private-teams-and-discovery-in-teams"></a>公共团队、 专用团队和团队中的发现的概述

大多数组织都有以下几种团队-公共团队、 可供搜索专用团队和非可供搜索的专用工作组。

![团队库](media/private-team-discovery-team-gallery.png)

### <a name="public-teams"></a>公共团队

公共团队是可用于加入您的组织中的所有用户。 公共团队团队库中的所有人都可见，用户可以加入而无需获得团队所有者批准的公共团队。 公共团队的例子包括团队讨论技术、 团队以获取您的产品，试用反馈和人员拼车工作团队的新闻。

### <a name="discoverable-private-teams"></a>可供搜索的专用工作组

可供搜索的专用工作组只能团队所有者将用户添加到其时联接。 当您进行专用团队可供搜索时，团队包含的建议的团队和团队库中的搜索结果列表中。 使用可供搜索的专用工作组的项目和组织中的所有人了解与其中访问对话，团队中的文件需要对其进行控制的组。 示例管理器和其直接下属包括贵公司人力资源部门团队、 团队的所有在您的组织，经理和团队。

### <a name="non-discoverable-private-teams"></a>非可供搜索的专用工作组

非可供搜索的专用工作组只能团队所有者将用户添加到其时联接。 时使专用团队不可被发现，它有隐藏建议团队列表中，从工作组库中的搜索结果中删除。 使用非可供搜索团队协作敏感和高度机密主题。 示例包括工作组讨论即将开始的获取和团队讨论在贵组织的战略方向更改。

## <a name="set-whether-new-private-teams-are-discoverable"></a>设置新的专用工作组是否可供搜索

当团队所有者创建专用团队时，他们可以选择以使其通过配置团队的发现设置发现。 默认情况下，新的专用团队可搜索和可供搜索。 如果团队所有者不希望显示在搜索结果和建议的专用团队，他们可以通过选择**更改设置**旁边**此团队是可搜索和发现**关闭设置。

![发现新的专用工作组设置](media/private-team-discovery-new-team.png)

## <a name="set-whether-existing-private-teams-are-discoverable"></a>设置现有专用团队是否可供搜索

团队所有者可以直接在团队设置中设置现有的专用工作组的发现设置，管理员可以使用 PowerShell 执行操作。

### <a name="in-team-settings"></a>在工作组设置。

在工作组中，转到专用工作组中，单击**多个选项 ˙˙˙** > **管理团队**。 在**设置**选项卡中，展开**团队发现**，然后清除或选中**开启可发现性**复选框。

![现有的专用工作组的发现设置](media/private-team-discovery-existing-team.png)

### <a name="using-powershell-coming-soon"></a>使用 PowerShell （即将推出）

使用**设置团队**cmdlet 可以关闭或打开现有的专用工作组的发现设置。 下面是如何使团队可检测到的一个示例：

    Set-Team -GroupId 0abc123d-e4f5-67gh-i890-jk1m2n345o6p -ShowInSearchAndSuggestions $true
您可以在脚本中使用此 cmdlet 批量设置的现有专用团队发现设置。

## <a name="set-whether-users-can-discover-private-teams"></a>设置是否用户可以发现专用团队

作为一名管理员，您可以控制允许组织中的哪些用户可以发现搜索结果中的专用工作组和团队中的建议。 使用**新建 CsTeamsChannelsPolicy** cmdlet，创建策略，然后将策略分配给用户。
 
**AllowPrivateTeamDiscovery**参数设置为**true**以允许用户分配有该策略以查看可供搜索专用 リ モ ・ 搜索结果和建议。 **AllowPrivateTeamDiscovery**参数设置为**false**可删除所有可检测到的专用工作组搜索结果和建议的分配策略的用户。

默认情况下**AllowPrivateTeamDiscovery**是设置为**true**的组织中的所有用户。

本示例中，我们将创建名为防止用户发现所做可供搜索，任何专用团队的 VendorPolicy 的策略，然后我们将策略分配给名为 vendoruser1 的用户。 
   
     New-CsTeamsChannelsPolicy -Identity VendorPolicy -AllowPrivateTeamDiscovery $false
     Grant-CsTeamsChannelsPolicy -Identity vendoruser1@company.com -PolicyName VendorPolicy

> [!NOTE]
> 不是可供搜索的专用工作组永远不会显示在搜索结果和建议，而不考虑的策略设置。 例如，如果要关闭的专用工作组的发现设置，用户将无法发现团队，即使**AllowPrivateTeamDiscovery**参数设置为**true**这些用户的策略设置。

## <a name="related-topics"></a>相关主题
- [Teams PowerShell 概览](teams-powershell-overview.md)