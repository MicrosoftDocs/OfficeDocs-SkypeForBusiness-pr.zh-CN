---
title: Microsoft Teams 中的私人频道
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: suchakr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 了解如何在 Microsoft Teams 中使用和管理私人频道。
ms.openlocfilehash: 54fd36bd78f1d9ea263fe3e79a3d12a08741c389
ms.sourcegitcommit: 8acc2ed4cb807f941a6526ec8aad562536f45aa6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/18/2020
ms.locfileid: "44804686"
---
# <a name="private-channels-in-microsoft-teams"></a>Microsoft Teams 中的私人频道

Microsoft Teams 中的私人频道创建专用空间供团队展开协作。 仅属于私人频道的所有者或成员的团队用户可以访问此频道。 只要已是团队的成员（包括来宾），均可将其添加为专用渠道的成员。

如果想要将协作限制为有知情需求的人员之间，或者想要促进分配到特定项目的一组人员之间的通信，你可能会需要使用私人频道，而不必创建额外的团队并进行管理。

例如，在以下情景中，私人频道非常有用：

- 团队中的一组人员希望有一个专用空间来展开协作，而不必创建单独的团队。
- 团队中的一部分人员希望使用私人频道来讨论敏感信息，如预算、资源、战略定位等。

锁定图标表示私人频道。 只有私人频道的成员才能查看和参与他们添加到的私人频道。

![团队中的私人频道的屏幕截图](media/private-channels-in-teams.png)

## <a name="what-you-need-to-know-about-private-channels"></a>你需要了解的私人频道相关信息

目前，私人频道支持连接器和选项卡（Stream、Planner 和 Forms 除外）。 我们正致力于为私人频道（包括消息传递扩展和机器人）提供完整的应用支持。

每个团队最多可拥有 30 个私人频道，每个私人频道最多可拥有 250 个成员。 30 个私人频道限制是对每个团队 200 个标准频道限制的补充。 

从现有团队创建团队时，不会复制现有团队中的任何专用频道。


> [!NOTE]
> 我们会不断为私人频道添加功能，因此请经常回来看看，以获取有关应用、频道会议以及为大型团队扩展私人频道的最新信息。

## <a name="when-to-create-a-private-channel"></a>何时创建私人频道

若要确定私人频道是否合适，请考虑以下问题：谁需要一起工作以及协作的内容。

|这些人员是否已作为团队成员加入某个团队？  |这项工作是否需要对其他人保密？  |是否需要针对多个不同的主题展开讨论？  |建议  |
|---------|---------|---------|---------|
|是      |是         |是          |在现有团队中创建私人频道，或考虑为每个主题创建专用的私人频道。         |
|是     |是         |否         |在现有团队中创建私人频道。         |
|是     |否         |否         |在现有团队中创建频道。         |
|否     |否         |否         |考虑创建新的团队。         |
|否     |否         |是         |考虑创建新的团队，然后根据各个主题的保密性，考虑为每个主题创建单独的标准或私人频道。         |
|否     |是         |否         |创建新的团队，并考虑创建私人频道。         |

创建私人频道后，它将链接到父团队，并且无法移动到其他团队。 此外，不能将私人频道转换为标准频道，反之亦然。

## <a name="private-channel-creation-and-membership"></a>私人频道创建和成员资格

### <a name="who-can-create-private-channels"></a>谁可以创建私人频道？

默认情况下，任何团队所有者或团队成员都可以创建私人频道。 来宾无法创建私人频道。 可以在团队级别和组织级别管理创建专用通道的功能。

 1. 转到管理中心 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 。

 2. 使用[策略](teams-policies.md)控制允许组织中的哪些用户创建专用频道。
    设置策略后，团队所有者可以关闭或打开成员在团队的 "**设置**" 选项卡中创建专用频道的功能。

创建私人频道的人员是私人频道所有者，只有私人频道所有者才能直接从中添加或删除人员。 私人频道所有者可将任何团队成员添加到自己创建的私人频道，包括来宾。 私人频道的成员具有安全的对话空间，添加新成员后，他们可以查看该私人频道中的所有对话（甚至是旧对话）。

### <a name="what-happens-when-a-team-member-leaves-or-is-removed-from-a-team"></a>当团队成员离开团队或从团队中删除成员时，会发生什么情况？

如果团队成员离开团队或从团队中删除成员，则该用户也将从团队中的所有私人频道中离开或删除。 如果将用户添加回团队，则必须将其添加回团队中的私人频道。

### <a name="what-happens-when-a-private-channel-owner-is-removed-from-a-private-channel"></a>从私人频道中删除私人频道所有者时，会发生什么情况？

如果私人频道所有者是一个或多个私人频道的最后一个所有者，则无法通过 Teams 客户端将其删除。

如果专用频道所有者离开你的组织，或者从与团队关联的 Microsoft 365 组中删除了它们，则专用通道的成员将自动提升为专用通道所有者。

### <a name="what-can-team-owners-and-team-members-see-in-a-private-channel"></a>团队所有者和团队成员可以在私人频道中查看哪些信息？

团队所有者可以查看其团队中所有私人频道的名称，也可以删除该团队中的任何私人频道。 （已删除的私人频道可在删除后的 30 天内还原）。 团队所有者无法查看私人频道中的文件或私人频道的对话和成员列表，除非他们是该私人频道的成员。

下表显示了谁可以在私人频道中查看哪些信息。

|项目  |团队所有者可以查看 |团队成员可以查看 |
|---------|---------|---------|
|名称和说明    |团队中的所有私人频道         |仅限他们添加到的私人频道         |
|对话和选项卡     |仅当添加到私人频道时         |仅当添加到私人频道时         |
|文件和内容    |仅当添加到私人频道时        |仅当添加到私人频道时         |
|私人频道所有者    |团队中的所有私人频道        |仅当添加到私人频道时         |
|上次活动时间戳  |团队中的所有私人频道       |仅当添加到私人频道时         |

## <a name="manage-private-channels"></a>管理私人频道

下表概述了所有者、成员和来宾可以在私人频道中执行的操作。

|操作  |团队所有者|团队成员|团队来宾|私人频道所有者|私人频道成员|私人频道来宾|
|---------|---------|---------|---------|---------|---------|---------|
|创建私人频道|是<sup>1</sup>|是<sup>1、2</sup>|否|不适用|不适用|不适用|
|删除私人频道|是|否|否|是|否|否|
|离开私人频道|不适用|不适用|不适用|是<sup>3</sup>|是|是|
|编辑私人频道|否|不适用|不适用|是|否|否|
|还原已删除的私人频道|是|否|否|是|否|否|
|添加成员|否|不适用|不适用|是|否|否|
|编辑设置|否|不适用|不适用|是|否|否|
|管理选项卡和应用|否|不适用|不适用|是<sup>4</sup>|是<sup>5</sup>|否|

<sup>1</sup> 假设你（管理员）配置的策略允许用户创建私人频道。<br>
<sup>2</sup> 每个团队都有一个设置，团队所有者可以打开或关闭此设置，以允许团队成员创建私人频道。 团队所有者始终可以创建私人频道。<br>
<sup>3</sup> 假设私人频道所有者不是该频道的最后一个所有者。 <br>
<sup>4</sup> 要求团队安装一个应用以供私人频道使用。<br>
<sup>5</sup> 私人频道所有者可以配置它。

### <a name="manage-private-channel-membership-and-settings"></a>管理私人频道成员资格和设置

每个私人频道都有自身的设置，包括添加和删除成员、添加选项卡以及 @提及整个频道的功能。 这些设置独立于父团队设置。 创建私人频道时，它将继承父团队的设置，之后可以独立于父团队设置更改其设置。

私人频道所有者可以单击“**管理频道**”，然后使用“**成员**”和“**设置**”选项卡来添加或删除成员以及编辑设置。  

![私人频道设置的屏幕截图](media/private-channels-in-teams-channel-settings.png)

## <a name="manage-the-life-cycle-of-private-channels"></a>管理私人频道的生命周期

有关如何在组织中管理私人频道生命周期的指南，请参阅[在 Teams 中管理私人频道的生命周期](private-channels-life-cycle-management.md)。 这包括如何控制组织中的用户是否可以创建私人频道、如何代表团队所有者创建私人频道、如何出于存档和审核目的获取所有私人频道消息的列表，以及其他管理任务。  

## <a name="private-channel-sharepoint-sites"></a>私人频道 SharePoint 网站

每个专用频道都有自己的 SharePoint 网站集。 与团队所有者可以访问网站集内所有资产的团队网站相比，单独的网站集可确保只有私人频道的成员才能访问私人频道文件。 默认情况下，这些网站集是使用文档库创建的，并且可通过[网站管理界面](https://support.office.com/article/Enable-or-disable-site-collection-features-A2F2A5C2-093D-4897-8B7F-37F86D83DF04)轻松增强为功能齐全的网站集。 每个网站集都在与父团队网站集相同的地理区域中创建。 这些轻型网站具有自定义模板 ID“TEAMCHANNEL#0”，可通过 PowerShell 和 Graph API 实现更轻松的管理。  根据设计，它们在 SharePoint 管理中心中不可见。

为使每个租户容纳更多的网站集，该限制已从 500,000 个增加到 2,000,000 个。 私人频道网站集可同步数据分类，并从父团队的网站集继承来宾访问权限。  网站集所有者和成员组的成员资格将与 Teams 中私人频道的成员资格保持同步。 在 SharePoint Online 中对所有者或成员组的成员资格所做的任何更改都将在四个小时内自动还原为私人频道成员资格。 在某些用户需要访问文档而无需访问私人频道消息的情况下，请将它们添加到网站上的“访问者”组或与所有者和成员组分开的新组中。

Teams 可管理私人频道 SharePoint 网站集的生命周期。 如果在 Teams 外部删除了网站集，则只要私人频道仍处于活动状态，后台作业将在四个小时内还原该网站。 如果已删除并硬删除网站，则会为私人频道预配一个新的网站集。

如果已还原私人频道或包含私人频道的团队，则网站集会随之还原。 如果已还原私人频道网站集，并且超出了私人频道的 30 天软删除时间段，则该网站集将作为独立网站集运行。

## <a name="private-channel-message-compliance-records"></a>私人频道消息合规记录

在私人频道中发送的消息记录将传递到所有私人频道成员的邮箱，而不是传递到组邮箱。 记录的标题已格式化为指示它们是从哪个私人频道发送的。

有关对私人频道消息执行电子数据展示搜索的详细信息，请参阅[私人频道的电子数据展示](ediscovery-investigation.md#ediscovery-of-private-channels)。

## <a name="considerations-around-access-in-private-channels"></a>有关私人频道中的访问权限的注意事项

在私人频道中创建新的 OneNote 笔记本时，其他用户仍可以访问该笔记本，因为其行为与在私人频道 SharePoint 网站中与用户共享任何其他项目的访问权限相同。

如果通过 SharePoint 向用户授予对私人频道中的笔记本的访问权限，则从团队或私人频道中删除用户将不会删除用户对该笔记本的访问权限。

如果将现有笔记本作为选项卡添加到私人频道，则不会更改对私人频道的访问权限。 这表示：

- 默认情况下，并非私人频道中的每个人都可以访问笔记本。 这是因为他们可能无法访问笔记本的托管位置，例如其他团队的 SharePoint 网站。
- 不是私人频道成员的用户可以查看笔记本。  

## <a name="related-topics"></a>相关主题

- [Teams 中的团队和频道概述](teams-channels-overview.md)
- [Teams PowerShell 概览](teams-powershell-overview.md)
- [将 Microsoft Graph API 与 Teams 结合使用](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0)
