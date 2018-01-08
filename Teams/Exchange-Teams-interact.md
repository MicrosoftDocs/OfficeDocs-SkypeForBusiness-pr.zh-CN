---
title: "Exchange 与 Microsoft Teams 如何交互"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "了解 Microsoft Teams 与各种 Exchange 设置之间存在哪些功能，例如，创建和加入团队、创建频道等。"
MS.collection: Strat_MT_TeamsAdmin
ms.openlocfilehash: 4fc7da7d68c13bbadec935573c827cf767c9afe4
ms.sourcegitcommit: 3faedb6057da8650b06b05f9c9bdd941d5ade175
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/20/2017
---
<a name="how-exchange-and-microsoft-teams-interact"></a>Exchange 与 Microsoft Teams 如何交互 
=========================================

为了获得全面的 Microsoft Teams 体验，应该为每个用户启用 Exchange Online、SharePoint Online 和 Office 365 组创建。

用户的 Exchange 邮箱可以托管在线上或本地。 Exchange Online 或 Exchange Dedicated vNext 上托管的用户可以使用 Teams 的所有功能。 他们可以创建和加入团队与频道、创建和查看会议、通话和聊天、修改用户个人资料图片以及添加和配置连接器、选项卡与聊天机器人。

对于 Office 365，Exchange Online Dedicated - Legacy 或本地 Exchange 上托管的用户必须同步到 Azure Active Directory。 他们可以创建和加入团队与频道、添加和配置选项卡与聊天机器人以及聊天和通话。 但是，他们无法修改用户个人资料图片以及添加和配置连接器。 他们可以接收来自其他用户配置的连接器的消息。 对于创建和查看会议，这是一个混合包：Exchange 2016 累积更新3 (CU3) 和更高版本支持创建和查看会议，但 Exchange 2016 CU3 之前的版本不支持。

下表提供了适用于使用各种环境中托管的 Exchange Online 的用户的信息。

**支持的操作：** 

| 用户的邮箱托管在：   | 创建团队   |加入团队|创建频道|创建和查看会议|修改用户个人资料图片|添加和配置连接器|添加和配置选项卡|添加和配置聊天机器人|
|---|---|---|---|---|---|---|---|---|
|**Exchange Online**|是|是|是|是|是|是|是|是|
|**Exchange Online Dedicated vNext**|是|是|是|是|是|是|是|是|
|**Exchange Online Dedicated - Legacy**（同步到所需 Azure AD）|是|是|是|否|否|否|是| 是|
|**本地 Exchange**（同步到所需 Azure AD）|是|是|是|是*|否|否|是|是|
                                                            
*\*支持 Exchange 2016 CU3 及更高版本*

其他信息：

-   Microsoft Teams 不支持本地 SharePoint。

-   要在团队对话中共享和存储文件，需要 SharePoint Online。

-   要在私人聊天中共享和存储文件，需要 OneDrive for Business。

-   如果没有为用户分配和启用 SharePoint Online 许可证，则他们在 Office 365 中没有 OneDrive for Business 存储空间。 在频道中可以继续共享文件，但在 Office 365 中没有 OneDrive for Business 存储空间的情况下，用户无法在聊天中共享文件。

-   必须为用户启用 Office 365 组创建，用户才能在 Microsoft Teams 中创建团队。

-   在 Microsoft Teams 中，安全性和合规性功能（例如，电子数据展示、内容搜索、存档和法定保留）在 Exchange Online 和 SharePoint Online 环境中完全正常。 对于频道对话，消息会记录到 Exchange Online 中的组邮箱，它们在此可用于电子数据展示。 如果在组织中为用户启用了 SharePoint Online 和 OneDrive for Business（使用工作帐户或学校帐户），也可以对 Teams 中的所有文件使用这些合规性功能。

**重要提示：**   参与属于 Microsoft Teams 中聊天列表的对话的用户必须有 Exchange Online（基于云）邮箱，管理员才能搜索聊天对话。 这是因为属于聊天列表的对话存储在聊天参与者的基于云的邮箱中。 如果聊天参与者没有 Exchange Online 邮箱，管理员将无法搜索聊天对话，也无法将聊天对话中的内容置于保留状态。 例如，在 Exchange 混合部署中，具有本地邮箱的用户也许能参与属于 Microsoft Teams 中聊天列表的对话。 但是，在这种情况下，由于用户没有基于云的邮箱，这些对话中的内容不可搜索，也不可置于保留状态。 有关内容搜索和 Microsoft Teams 的更多详细信息，请参阅 [*Microsoft Teams 和 Office 365 组*](https://support.office.com/en-us/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a)。

**提示：**   有关如何使用 Azure AD Connect 与 Azure Active Directory 同步的信息，请参阅[*将本地标识与 Azure Active Directory 集成*](https://go.microsoft.com/fwlink/?linkid=854600)。
