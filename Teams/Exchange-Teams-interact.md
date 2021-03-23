---
title: Exchange 与 Microsoft Teams 如何交互
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: dstrome
description: 了解 Microsoft Teams 与各种 Exchange 设置之间存在哪些功能，例如，创建和加入团队、创建频道等。
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9790cfb186e1745d7233bf23232ac4b4a69b00e0
ms.sourcegitcommit: 2eaf80bca6dfad367283e57662d81a809c9437e8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/22/2021
ms.locfileid: "50997320"
---
# <a name="how-exchange-and-microsoft-teams-interact"></a>Exchange 与 Microsoft Teams 如何交互

> [!Tip]
> 观看以下会话，以了解 Teams 如何与 Azure Active Directory (AAD)、Microsoft 365 组、Exchange、SharePoint 和 OneDrive for Business 进行交互：[Microsoft Teams 基础知识](https://aka.ms/teams-foundations)

为了获得全面的 Teams 体验，应该为每个用户启用 Exchange Online、SharePoint Online 和 Microsoft 365 组创建。

用户的 Exchange 邮箱可以托管在线上或本地。

Exchange Online 或 Exchange Dedicated vNext 上托管的用户可以使用 Teams 的所有功能。 他们可以创建和加入团队和频道，创建和查看会议、通话和聊天，修改用户个人资料图片（如果 Outlook 网页版邮箱策略允许他们这样做）以及添加和配置连接器、选项卡和聊天机器人。 有关可用功能的更全面列表，请参阅下表。

在 Exchange Online 专用（旧版）上托管的用户必须同步到 Microsoft 365 或 Office 365 上的 Azure Active Directory。 他们可以创建和加入团队与频道、添加和配置选项卡与聊天机器人以及使用聊天和通话功能。 但是，他们无法修改个人资料图片、管理会议、访问 Outlook 联系人或管理连接器。

> [!IMPORTANT]
> 为了与本地集成，强烈建议你使用 Exchange Server 2016 或更高版本进行 Exchange 完整经典混合部署。 新式混合支持仅限于忙/闲，并且不提供从 Teams 到本地邮箱的日历等集成。 有关设置混合部署的详细信息，请参阅 [Exchange Server 混合部署](https://docs.microsoft.com/exchange/exchange-hybrid)。

拥有本地托管邮箱的用户必须同步到 Azure Active Directory。 他们可以利用上述方案中的所有功能，但是，如果满足[本地托管的邮箱的要求](#requirements-to-create-and-view-meetings-for-mailboxes-hosted-on-premises)部分中列出的要求，则他们可以管理会议。

下表为基于 Exchange 环境的功能可用性提供了有用的快速参考。

**支持的操作：**

| 用户的邮箱托管在：                                        | 电子数据展示       | 合法&nbsp;保留    | 保留  | 团队和频道管理 | 在 Teams 中创建和查看会议 | 修改用户个人资料图片 | 呼叫历史记录 | 管理联系人 | 访问 Outlook 联系人 | 语音邮件  | 添加和配置连接器 | 添加和配置选项卡 | 添加和配置聊天机器人 |
|---------------------------------------------------------------------|------------------|--------------------|------------|-----------------------|-----------------------------------|-----------------------------|--------------|-----------------|-------------------------|------------|------------------------------|------------------------|------------------------|
| **Exchange Online**                                                 | 是 <sup>1</sup> | 支持<sup>1</sup>   | 是        | 是                   | 是                               | 是<sup>7</sup>             | 是          | 是             | 是 <sup>6</sup>        | 是        | 是                          | 是                    | 是                    |
| **Exchange Online Dedicated vNext**                                 | 是 <sup>1</sup> | 支持<sup>1</sup>   | 是        | 是                   | 是                               | 是<sup>7</sup>             | 是          | 是             | 是 <sup>6</sup>        | 是        | 是                          | 是                    | 是                    |
| **Exchange Online Dedicated - Legacy**（同步到所需 Azure AD）  | 是 <sup>1</sup> | 是 <sup>1、2</sup> | 是 <sup>3</sup> | 是                   | 否                                | 否                          | 是          | 是             | 否                      | 是 <sup>4</sup> | 是 <sup>5</sup>                   | 是                    | 是                    |
| **Exchange 本地**（同步到 Azure AD） | 是 <sup>1，9</sup> | 是 <sup>1</sup>   | 是 <sup>3</sup> | 是                   | 是 <sup>8</sup>         | 否                          | 是          | 是             | 否                      | 是 <sup>4</sup> | 是 <sup>5</sup>                   | 是                    | 是                    |

<sup>1</sup> 所有托管选项均支持电子数据展示和合法保留，以实现频道消息合规性。

<sup>2</sup> 此托管选项尚不支持 Teams 私密聊天消息合法保留。

<sup>3</sup> 保留将使用联机用户的影子邮箱来存储消息。

<sup>4</sup> 具有本地 Exchange 邮箱的 Teams 用户可以在 Teams 中使用语音邮件，并在 Outlook 中接收语音邮件，但是无法在 Teams 客户端中查看或播放语音邮件。

<sup>5</sup> 如果团队的所有者之一可以添加连接器，则该团队中的其他人都将能够执行此操作，即使其邮箱驻留在本地也是如此。

<sup>6</sup> 仅默认联系人文件夹中的联系人。 不支持访问其他联系人文件夹或子文件夹。

<sup>7</sup> Teams 将遵循租户管理员配置的 [Outlook 网页版邮箱策略](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy)设置来控制用户是否可以更改个人资料图片。 如果在策略中关闭 **-SetPhotoEnabled** 设置，则用户无法添加、更改或删除其个人资料图片，因此，如果管理员更改了照片，则 porfile 图片不会同步到团队。
<sup>8</sup> 需要满足[为本地托管的邮箱创建和查看会议的要求](#requirements-to-create-and-view-meetings-for-mailboxes-hosted-on-premises)部分中列出的要求。

<sup>9</sup> 还需要至少一个 Exchange Online 计划 1 许可证。 有关详细信息，请参阅 [搜索本地用户的 Teams 聊天数据](https://docs.microsoft.com/microsoft-365/compliance/search-cloud-based-mailboxes-for-on-premises-users)。

## <a name="requirements-to-get-the-most-out-of-microsoft-teams"></a>充分利用 Microsoft Teams 的要求

Microsoft Teams 可与许多 Microsoft 365 和 Office 365 服务协同工作，为用户提供丰富的体验。 若要支持此体验，需启用某些功能或服务并分配许可证。

- 必须向用户分配 Exchange Online 许可证。

- 若要在团队对话中共享和存储文件，需要 SharePoint Online。 Microsoft Teams 不支持 SharePoint 本地环境。

- 如果用户希望在聊天中共享文件，则必须为其分配 SharePoint Online 许可证。 如果没有为用户分配和启用 SharePoint Online 许可证，则他们在 Microsoft 365 或 Office 365 中没有 OneDrive for Business 存储空间。 在频道中可以继续共享文件，但在 Microsoft 365 或 Office 365 中没有 OneDrive for Business 存储空间的情况下，用户无法在聊天中共享文件。

- 必须为用户启用 Microsoft 365 组创建，用户才能在 Microsoft Teams 中创建团队。

  > [!IMPORTANT]
  > 如果在将用户移动到“**仅 Teams**”模式后卸载 Skype for Business 客户端，则在 Outlook 和其他 Office 应用中，状态可能会停止工作。 状态在 Teams 中显示良好。 若要解决此问题，请选择 Microsoft Teams 右上角的个人资料图片，然后选择“**设置**”。 在“**应用程序**”下的“**常规**”选项卡上，选择“**将 Teams 注册为 Office 的聊天应用（需要重新启动 Office 应用程序）**”。 选择此选项后，请关闭并重新打开所有 Office 应用，包括 Outlook。 打开 Outlook 后，状态信息将可用。

## <a name="requirements-to-create-and-view-meetings-for-mailboxes-hosted-on-premises"></a>为本地托管的邮箱创建和查看会议的要求

如果邮箱在本地托管，若要创建和查看会议，必须满足以下要求：

- 需要为 Azure Active Directory 同步的用户分配所需的 Teams 许可证。

- 用户必须同步到 Azure Active Directory。 有关如何使用 Azure AD Connect 与 Azure Active Directory 同步的信息，请参阅[混合标识文档](https://docs.microsoft.com/azure/active-directory/hybrid/)。

- 邮箱托管在 Exchange Server 2016 累积更新 3 或更高版本中。

- 自动发现和 Exchange Web 服务是在外部发布的。

- OAuth 身份验证最好通过运行完整混合配置（经典或新式）的 Exchange 混合配置向导进行配置。 如果无法使用混合配置向导，请按[配置 Exchange 和 Exchange Online 组织之间的 OAuth 身份验证](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)所述配置 OAuth。

  > [!NOTE]
  > Exchange 信任来自 Teams 服务（称为 EvoSTS）的 OAuth 令牌。 步骤 1 应足够，但是仅 EvoSTS; ACS 用于日历中的忙/闲查找。

- 设置 Azure AD Connect 中 Exchange 混合部署功能的复选框。

- 对于面向 Mac 的日历应用支持和 Teams Outlook 加载项，Exchange Web 服务 Url 必须在 Exchange 服务主体的租户 Azure AD 中配置为 SPN。 此步骤可通过混合配置向导或[混合现代身份验证的以下手动步骤](https://docs.microsoft.com/microsoft-365/enterprise/configure-exchange-server-for-hybrid-modern-authentication#add-on-premises-web-service-urls-as-spns-in-azure-ad)完成。

若要为这些用户启用日历委派，请执行以下操作：

- 还必须完成在 Skype for Business Online 和 Skype for Business Online 之间配置集成和 [OAuth 中所述Exchange Server;](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)这些步骤将为 Teams 计划应用程序提供确认委派权限所需的权限。
 
  > [!NOTE]
  > 步骤 2 包括 ArchiveApplication 的角色分配，这不是委派所必需的。

- 代表其他人安排会议时，适用于 Outlook 的 Teams 计划加载项需要 Exchange 2013 CU19 或更高版本。 这是为了支持我们的服务对邮箱进行未经身份验证的发现，以检查代理人对委托人邮箱的权限。 代理人和委托人位置可以是 Exchange 2013 或更高版本，或者是 Exchange Online，但自动发现必须解析为 Exchange 2013 CU19 或更高版本。

## <a name="additional-considerations"></a>其他注意事项

下面是在组织中实施 Microsoft Teams 时要考虑的一些额外事项。

- 在 Microsoft Teams 中，安全性和合规性功能（例如，电子数据展示、内容搜索、存档和法定保留）在 Exchange Online 和 SharePoint Online 环境中完全正常。 对于频道对话，消息会记录到 Exchange Online 中的组邮箱，它们在此可用于电子数据展示。 如果在组织中为用户启用了 SharePoint Online 和 OneDrive for Business（使用工作帐户或学校帐户），也可以对 Teams 中的所有文件使用这些合规性功能。

- 使用条件访问控制和保护 Teams 和 Exchange 中合规性策略的配置。 有关详细信息，请参阅[条件访问策略如何在 Teams 中发挥作用？](security-compliance-overview.md#how-conditional-access-policies-work-for-teams)

- 如果你的组织具有合规性要求以确保可以发现所有会议讨论，则在组织者具有 Exchange 本地邮箱的情况下，应禁用私人会议。 有关详细信息，请参阅[允许安排私人会议](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams#allow-scheduling-private-meetings)。

- 在 Exchange 混合部署中，无论聊天参与者是基于云的邮箱还是本地邮箱，都可以搜索聊天消息中的内容。 若要了解详细信息，请参阅[搜索本地用户基于云的邮箱](https://docs.microsoft.com/office365/securitycompliance/search-cloud-based-mailboxes-for-on-premises-users)。 若要了解如何在 Teams 中搜索内容，请阅读 [Microsoft 365 合规中心中的内容搜索](https://docs.microsoft.com/Office365/SecurityCompliance/content-search#searching-microsoft-teams-and-office-365-groups)。

- 对于状态，Microsoft Teams 必须检查邮箱是托管在 Exchange Online 上还是本地。 然后，该服务会决定在何处访问邮箱。 若要使 Teams 服务能够对 Exchange Online 服务进行 REST API 调用来检查邮箱位置，必须运行 Exchange 混合配置向导来部署 Exchange 混合环境，如[使用混合配置向导创建混合部署](https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid)中所述。

## <a name="troubleshooting"></a>疑难解答

有关主题的完整疑难解答指南，请务必查看[解决 Microsoft Teams 和 Exchange Server 交互问题](https://docs.microsoft.com/microsoftteams/troubleshoot/known-issues/teams-exchange-interaction-issue)。
