---
title: Exchange 与 Microsoft Teams 如何交互
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: crowe
description: 了解 Microsoft Teams 与各种 Exchange 设置之间存在哪些功能，例如，创建和加入团队、创建频道等。
localization_priority: Normal
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: d69ba0fc113667149b212547cd04ed02e814ba50
ms.sourcegitcommit: c864a4b5337960deed01ff8c481326dbbd23c960
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/24/2018
ms.locfileid: "24975121"
---
<a name="how-exchange-and-microsoft-teams-interact"></a>Exchange 与 Microsoft Teams 如何交互 
=========================================

> [!Tip]
> 观看下面的会话，若要了解与 Azure Active Directory (AAD)、 Office 365 组、 Exchange、 SharePoint 和 OneDrive for Business 团队交互的方式：[基础的 Microsoft 团队](https://aka.ms/teams-foundations)

为了获得全面的 Microsoft Teams 体验，应该为每个用户启用 Exchange Online、SharePoint Online 和 Office 365 组创建。

用户的 Exchange 邮箱可以托管在线上或本地。 Exchange Online 或 Exchange Dedicated vNext 上托管的用户可以使用 Teams 的所有功能。 他们可以创建和加入团队与频道、创建和查看会议、通话和聊天、修改用户个人资料图片以及添加和配置连接器、选项卡与聊天机器人。

对于 Office 365，Exchange Online Dedicated - Legacy 或本地 Exchange 上托管的用户必须同步到 Azure Active Directory。 他们可以创建和加入团队与频道、添加和配置选项卡与聊天机器人以及聊天和通话。 但是，他们无法修改用户个人资料图片以及添加和配置连接器。 他们可以接收来自其他用户配置的连接器的消息。 对于创建和查看会议，这是一个混合包：Exchange 2016 累积更新3 (CU3) 和更高版本支持创建和查看会议，但 Exchange 2016 CU3 之前的版本不支持。

下表提供了适用于使用各种环境中托管的 Exchange Online 的用户的信息。

**支持的操作：** 

| 用户的邮箱托管在： | 电子数据展示| 法定保留 | 保留| 团队和频道的管理 |创建和查看会议| 修改用户个人资料图片 | 呼叫历史记录 | 管理联系人 | 访问 Outlook 联系人 | 语音邮件 |添加和配置连接器|添加和配置选项卡|添加和配置聊天机器人| 
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
|**Exchange Online**|是<sup>2</sup>|是<sup>2</sup>|是|是|是|是|是|是|是|是|是|是|是|
|**Exchange Online Dedicated vNext**|是<sup>2</sup>|是<sup>2</sup>|是|是|是|是|是|是|是|是|是|是|是|
|**Exchange Online Dedicated - Legacy**（同步到所需 Azure AD）|是 （[允许列表](https://support.office.com/en-us/article/searching-cloud-based-mailboxes-for-on-premises-users-in-office-365-3f7dde1a-a8ea-4366-86da-8ee6777f357c?ui=en-US&rs=en-US&ad=US)）<sup>2</sup>|是<sup>2，3</sup>|否|是|否|否|是|是|否|否|否|是|是|
|**本地 Exchange**（同步到所需 Azure AD）|是 （[允许列表](https://support.office.com/en-us/article/searching-cloud-based-mailboxes-for-on-premises-users-in-office-365-3f7dde1a-a8ea-4366-86da-8ee6777f357c?ui=en-US&rs=en-US&ad=US)）<sup>2</sup>|是<sup>2，3</sup>|否|是|是 （Exchange 2016 CU3 +）|否|是|是|否|否|否|否|是|
                                                            
<sup>1</sup> exchange 2016 CU3 和上方支持  
<sup>2</sup>电子数据展示和合规性上通道消息的法律挂起支持所有承载选项。  
<sup>3</sup>团队专用聊天消息是尚不支持的法律挂起对此托管选项。

其他信息：

-   Microsoft Teams 不支持本地 SharePoint。

-   要在团队对话中共享和存储文件，需要 SharePoint Online。

-   要在私人聊天中共享和存储文件，需要 OneDrive for Business。

-   如果没有为用户分配和启用 SharePoint Online 许可证，则他们在 Office 365 中没有 OneDrive for Business 存储空间。 在频道中可以继续共享文件，但在 Office 365 中没有 OneDrive for Business 存储空间的情况下，用户无法在聊天中共享文件。

-   必须为用户启用 Office 365 组创建，用户才能在 Microsoft Teams 中创建团队。

-   在 Microsoft Teams 中，安全性和合规性功能（例如，电子数据展示、内容搜索、存档和法定保留）在 Exchange Online 和 SharePoint Online 环境中完全正常。 对于频道对话，消息会记录到 Exchange Online 中的组邮箱，它们在此可用于电子数据展示。 如果在组织中为用户启用了 SharePoint Online 和 OneDrive for Business（使用工作帐户或学校帐户），也可以对 Teams 中的所有文件使用这些合规性功能。

-   对于 Exchange 内部部署 （混合部署中），您需要[Exchange 和 Exchange Online 组织之间配置 OAuth 身份验证](https://technet.microsoft.com/en-us/library/dn594521(v=exchg.150).aspx)中所述配置 OAuth。 

> [!NOTE]
> 当前，如果贵组织具有合规性要求以确保所有会议讨论均可发现，当组织者有本地 Exchange 邮箱时，你应禁用私人会议。

> [!IMPORTANT]
  参与对话的一部分的 Microsoft 团队中的聊天列表中的用户必须拥有管理员可以搜索聊天 Exchange Online （基于云的） 邮箱。 这是因为属于聊天列表的对话存储在聊天参与者的基于云的邮箱中。 如果聊天参与者没有 Exchange Online 邮箱，管理员将无法搜索聊天对话，也无法将聊天对话中的内容置于保留状态。 例如，在 Exchange 混合部署中，具有本地邮箱的用户也许能参与属于 Microsoft Teams 中聊天列表的对话。 但是，在这种情况下，由于用户没有基于云的邮箱，这些对话中的内容不可搜索，也不可置于保留状态。 有关内容搜索和 Microsoft Teams 的更多详细信息，请参阅[在 Office 365 安全与合规中心中运行内容搜索](https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a)。

> [!TIP]
  有关如何使用 Azure AD 连接将与 Azure Active Directory 同步的信息，请参阅[*将您的本地标识与 Azure Active Directory 集成*](https://go.microsoft.com/fwlink/?linkid=854600)。
