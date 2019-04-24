---
title: Exchange 与 Microsoft Teams 如何交互
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: crowe
description: 了解 Microsoft Teams 与各种 Exchange 设置之间存在哪些功能，例如，创建和加入团队、创建频道等。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: bdb998587eefd0eb15477b26799d487e041df220
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32180365"
---
<a name="how-exchange-and-microsoft-teams-interact"></a>Exchange 与 Microsoft Teams 如何交互 
=========================================

> [!Tip]
> 观看下面的会话，若要了解与 Azure Active Directory (AAD)、 Office 365 组、 Exchange、 SharePoint 和 OneDrive for Business 团队交互的方式：[基础的 Microsoft 团队](https://aka.ms/teams-foundations)

为了获得全面的 Teams 体验，应该为每个用户启用 Exchange Online、SharePoint Online 和 Office 365 组创建。

用户的 Exchange 邮箱可以托管在线上或本地。 Exchange Online 或 Exchange Dedicated vNext 上托管的用户可以使用 Teams 的所有功能。 他们可以创建和加入团队与频道、创建和查看会议、通话和聊天、修改用户个人资料图片以及添加和配置连接器、选项卡与聊天机器人。

对于 Office 365，Exchange Online Dedicated - Legacy 或本地 Exchange 上托管的用户必须同步到 Azure Active Directory。 他们可以创建和加入团队与频道、添加和配置选项卡与聊天机器人以及聊天和通话。 但是，他们无法修改用户个人资料图片以及添加和配置连接器。 他们可以接收来自其他用户配置的连接器的消息。 对于创建和查看会议，这是一个混合包：Exchange 2016 累积更新3 (CU3) 和更高版本支持创建和查看会议，但 Exchange 2016 CU3 之前的版本不支持。

下表提供了适用于使用各种环境中托管的 Exchange Online 的用户的信息。

**支持的操作：** 

| 用户的邮箱托管在： | 电子数据展示| 法律&nbsp;保留 | 保留| 团队和频道的管理 |创建和查看会议| 修改用户个人资料图片 | 呼叫历史记录 | 管理联系人 | 访问 Outlook 联系人 | 语音邮件 |添加和配置连接器|添加和配置选项卡|添加和配置聊天机器人| 
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
|**Exchange Online**|是<sup>2</sup>|是<sup>2</sup>|是 |是|是|是|是|是|是|是|是|是 |是|
|**Exchange Online Dedicated vNext**|是<sup>2</sup>|是<sup>2</sup>|是 |是 |是|是|是 |是|是|是|是 |是 |是 |
|**Exchange Online Dedicated - Legacy**（同步到所需 Azure AD）|是<sup>2</sup>|是<sup>2,3</sup>|是<sup>4|是|否|否|是|是 |否|是<sup>5|是 |是 |是|
|**本地 Exchange**（同步到所需 Azure AD）|是<sup>2</sup>| 是<sup>2,3</sup> |是<sup>4|是|是 （Exchange 2016 CU3 +）|是 （Exchange 2016 CU3 +）|是 |是 |否|是<sup>5|是 |是 |是 |

<sup>1</sup> exchange 2016 CU3 和上方支持  
<sup>2</sup>电子数据展示和合规性上通道消息的法律挂起支持所有承载选项。  
<sup>3</sup>团队专用聊天消息是尚不支持的法律挂起对此托管选项。

<sup>4</sup>保留将使用联机用户的卷影邮箱存储的邮件。 [Exchange 混合环境中的团队用户的 Microsoft 团队支持电子数据展示](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-supports-eDiscovery-for-Teams-users-in-a/ba-p/200009)。

<sup>5</sup>不可用来查看或团队客户端中播放团队用户与内部部署 Exchange 邮箱可能与团队使用语音邮件和接收语音邮件消息在 Outlook 中，但语音邮件消息。

其他信息：

-   Microsoft Teams 不支持本地 SharePoint。

-   要在团队对话中共享和存储文件，需要 SharePoint Online。

-   要在私人聊天中共享和存储文件，需要 OneDrive for Business。

-   如果没有为用户分配和启用 SharePoint Online 许可证，则他们在 Office 365 中没有 OneDrive for Business 存储空间。 在频道中可以继续共享文件，但在 Office 365 中没有 OneDrive for Business 存储空间的情况下，用户无法在聊天中共享文件。

-   必须为用户启用 Office 365 组创建，用户才能在 Microsoft Teams 中创建团队。

-   在 Microsoft Teams 中，安全性和合规性功能（例如，电子数据展示、内容搜索、存档和法定保留）在 Exchange Online 和 SharePoint Online 环境中完全正常。 对于频道对话，消息会记录到 Exchange Online 中的组邮箱，它们在此可用于电子数据展示。 如果在组织中为用户启用了 SharePoint Online 和 OneDrive for Business（使用工作帐户或学校帐户），也可以对 Teams 中的所有文件使用这些合规性功能。

-   对于 Exchange 内部部署，您必须配置新的 Exchange OAuth 身份验证协议，如[Exchange 和 Exchange Online 组织之间配置 OAuth 身份验证](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)中所述。 

-  控制和保护团队和 Exchange 使用条件 Access 中的合规性策略的配置。 有关详细信息，请参阅[条件访问策略的工作原理团队？](security-compliance-overview.md#how-do-conditional-access-policies-work-for-teams) .

> [!NOTE]
> 目前，如果您的组织具有合规性要求才能确保所有会议讨论可供搜索，则应禁用专用的会议，如果组织者具有 Exchange 内部部署邮箱。
> 
> [!IMPORTANT]
> Exchange 混合部署，在聊天消息中的内容是可不管聊天参与者是否具有一个基于云的邮箱或内部部署邮箱搜索。 若要了解详细信息，请阅读[搜索基于云的邮箱的内部部署 Office 365 中的用户](https://docs.microsoft.com/office365/securitycompliance/search-cloud-based-mailboxes-for-on-premises-users)。 若要了解有关搜索团队中的内容，请阅读[Office 365 安全性 & 合规性中心中的内容搜索](https://docs.microsoft.com/Office365/SecurityCompliance/content-search#searching-microsoft-teams-and-office-365-groups)。
> 
> [!TIP]
> 有关如何使用 Azure AD 连接将与 Azure Active Directory 同步的信息，请参阅[将您的本地标识与 Azure Active Directory 集成](https://go.microsoft.com/fwlink/?linkid=854600)。
