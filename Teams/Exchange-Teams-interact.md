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
ms.openlocfilehash: 2806d913fb63dcd2a7a25b26153435333282e871
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752974"
---
# <a name="how-exchange-and-microsoft-teams-interact"></a>Exchange 与 Microsoft Teams 如何交互

> [!Tip]
> 观看以下会话，了解团队如何与 Azure Active Directory （AAD）、Microsoft 365 组、Exchange、SharePoint 和 OneDrive for business 进行交互： [Microsoft 团队基础](https://aka.ms/teams-foundations)

对于完整团队体验，应为每个用户启用 Exchange Online、SharePoint Online 和 Microsoft 365 组创建。

用户的 Exchange 邮箱可以托管在线上或本地。 与本地 Exchange 集成需要 Exchange 混合部署。 有关设置混合部署的详细信息，请参阅[Exchange Server 混合部署](https://docs.microsoft.com/exchange/exchange-hybrid)。

Exchange Online 或 Exchange Dedicated vNext 上托管的用户可以使用 Teams 的所有功能。 他们可以创建和加入团队和频道、创建和查看会议、呼叫和聊天、修改用户个人资料图片（如果 Outlook 网页版邮箱策略允许他们执行此操作），以及添加和配置连接器、选项卡和机器人。

托管在 Exchange Online 专用（旧版）上的用户必须同步到 Microsoft 365 或 Office 365 上的 Azure Active Directory。 他们可以创建和加入团队和频道，添加和配置选项卡和机器人，以及利用聊天和通话功能。 但是，他们不能修改个人资料图片、管理会议、访问 outlook 联系人或管理连接线。

拥有内部托管邮箱的用户必须同步到 Azure Active Directory。 它们可以使用上述方案中的所有功能，此外，还可以更改用户个人资料图片（如果 Outlook 网页版邮箱策略允许他们执行此操作），并且管理会议（提供 Exchange Server 2016 （累积更新3）或更高版本）在本地运行时使用 OAuth 配置（最好通过 Exchange 混合配置向导），如在[exchange 和 Exchange Online 组织之间配置 OAuth 身份验证](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)中所述。 若要为这些用户启用日历委派，还必须按照在[Skype For Business Online 和 Exchange Server 之间配置集成和 OAuth](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)中所述完成步骤2-3。这些步骤将向团队安排应用程序提供确认委派权限所需的权限。

下表提供了基于 Exchange 环境的功能可用性的有用快速参考。

> [!NOTE]
> 本地 Exchange 和团队之间的功能集成需要 Exchange 混合部署。 此要求是对下表的某些功能中的特定于版本的要求的补充。

**支持的操作：**

| 用户的邮箱托管在： | 电子数据展示| 法律 &nbsp; 封存 | 保存| 团队和频道管理 |在团队中创建和查看会议| 修改用户个人资料图片 | 通话记录 | 管理联系人 | 访问 Outlook 联系人 | 语音邮件 |添加和配置连接器|添加和配置选项卡|添加和配置聊天机器人|
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
|**Exchange Online**|是<sup>2</sup>|是<sup>2</sup>|必需|是 |是 |是<sup>8</sup>|必需|是 |是<sup>7</sup>|必需|是 |是 |是 |
|**Exchange Online Dedicated vNext**|是<sup>2</sup>|是<sup>2</sup>|必需|是 |是 |是<sup>8</sup>|必需|是 |是<sup>7</sup>|必需|是 |是 |是|
|**Exchange Online Dedicated - Legacy**（同步到所需 Azure AD）|是<sup>2</sup>|是<sup>2，3</sup>|是 <sup> 4|是|否|否|必需|是|否|是 <sup> 5|是 <sup> 6|必需|是 |
|**本地 Exchange** （需要同步至 Azure AD & OAuth 配置）|是<sup>2</sup>| 是<sup>2</sup> |是 <sup> 4|是|是（Exchange 2016 CU3 +）|否|必需|是|否|是 <sup> 5|是 <sup> 6|必需|是 |

<sup>1</sup> EXCHANGE 2016 CU3 及以上版本均受支持。  

所有托管选项均支持<sup>2</sup>个电子数据展示和对通道消息的法律封存。

<sup>3</sup>团队私人聊天消息尚不支持此托管选项的法律封存。

<sup>4</sup>保留将使用用于联机用户存储消息的卷影邮箱。 [Microsoft 团队为 Exchange 混合环境中的团队用户支持电子数据展示](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-supports-eDiscovery-for-Teams-users-in-a/ba-p/200009)。

<sup>5</sup>个团队使用本地 Exchange 邮箱的用户可能在 Outlook 中使用语音邮件和工作组接收语音邮件，但语音邮件在团队客户端中不可用，无法查看或播放语音邮件。

<sup>6</sup>如果团队的其中一个所有者可以添加连接器，则该团队中的其他所有人都可以执行此操作，即使他们的邮箱在本地托管。

<sup>7</sup>仅限默认联系人文件夹中的联系人。 不支持访问其他联系人文件夹或子文件夹。

<sup>8 个</sup>团队负责[Outlook on web 邮箱策略](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy)设置，该设置由租户管理员配置，用于控制用户是否可以更改其个人资料图片。 如果策略中的 **-SetPhotoEnabled**设置处于关闭状态，则用户无法添加、更改或删除其个人资料图片。 例如，如果用户上载由您的组织的 IT 或人力资源部门批准的个人资料图片，则无需执行任何操作。 但是，如果用户上载的图片不合适，请根据组织的内部策略更改图片。

## <a name="requirements-to-get-the-most-out-of-microsoft-teams"></a>充分利用 Microsoft 团队的要求

Microsoft 团队与多个 Microsoft 365 和 Office 365 服务协同工作，为用户提供丰富的体验。 若要支持此体验，你需要启用某些功能或服务并分配许可证。

- 要在团队对话中共享和存储文件，需要 SharePoint Online。 Microsoft Teams 不支持本地 SharePoint。

- 如果用户想要在聊天中共享文件，则必须分配有 SharePoint Online 许可证。 如果未使用 SharePoint Online 许可证分配和启用用户，则他们在 Microsoft 365 或 Office 365 中没有 OneDrive for business 存储。 文件共享将继续在频道中工作，但是在 Microsoft 365 或 Office 365 中，用户无法在不使用 OneDrive for Business 存储的聊天中共享文件。

- 必须为用户启用 Microsoft 365 组创建，才能在 Microsoft 团队中创建团队。

- 若要让 Microsoft 团队使用本地 Exchange，必须配置新的 Exchange OAuth 身份验证协议（最好是运行 Exchange 混合向导），如在[exchange 和 Exchange Online 组织之间配置 OAuth 身份验证](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)中所述。 若要使具有 Exchange 本地邮箱的用户代表另一个用户安排团队会议，还必须按照[配置 Skype For Business Online 和 Exchange Server 之间的配置集成和 OAuth](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)中所述完成步骤2-3。

> [!NOTE]
> Outlook 团队外接程序可用于为托管在本地 Exchange 中的邮箱安排团队会议。 但是，如果使用 Exchange 本地 Exchange 代表另一个用户安排团队会议，则需要 Exchange 2013 CU9 和更高版本以及新的 Exchange OAuth 身份验证协议。 代理人和委托人进行通话都必须在 Exchange 内部部署邮箱。

> [!NOTE]
> 对于 Exchange 本地和团队集成，需要为 AAD 同步用户分配所需的许可证。

> [!IMPORTANT]
> 如果你在将用户移动到 "**仅团队**" 模式后卸载 Skype for business 客户端，则在 Outlook 和其他 Office 应用中，联机状态可能会停止工作。 状态在 Teams 中显示良好。 若要解决此问题，请在 Microsoft 团队的右上角选择您的个人资料图片，然后选择 "**设置**"。 在 "**应用程序**" 下的 "**常规**" 选项卡上，选择 "**注册团队作为 Office 的聊天应用（需要重启 office 应用程序）**"。 选择此选项后，关闭并重新打开所有 Office 应用（包括 Outlook）。 打开 Outlook 后，状态信息将可用。

## <a name="additional-considerations"></a>其他注意事项

下面是在组织中实施 Microsoft 团队时要考虑的一些额外事项。

- 在 Microsoft Teams 中，安全性和合规性功能（例如，电子数据展示、内容搜索、存档和法定保留）在 Exchange Online 和 SharePoint Online 环境中完全正常。 对于频道对话，消息会记录到 Exchange Online 中的组邮箱，它们在此可用于电子数据展示。 如果在组织中为用户启用了 SharePoint Online 和 OneDrive for Business（使用工作帐户或学校帐户），也可以对 Teams 中的所有文件使用这些合规性功能。

- 使用条件访问控制和保护团队和 Exchange 中合规性策略的配置。 有关详细信息，请参阅[如何为团队工作条件访问策略？](security-compliance-overview.md#how-conditional-access-policies-work-for-teams) .

- 如果你的组织具有合规性要求以确保所有会议讨论均可发现，则应禁用私人会议（如果组织者具有 Exchange 本地邮箱）。

- 在 Exchange 混合部署中，无论聊天参与者是否具有基于云的邮箱或本地邮箱，都可以搜索聊天消息中的内容。 若要了解详细信息，请阅读[搜索本地用户的基于云的邮箱](https://docs.microsoft.com/office365/securitycompliance/search-cloud-based-mailboxes-for-on-premises-users)。 若要了解有关在团队中搜索内容的信息，请阅读[Microsoft 365 合规中心中的内容搜索](https://docs.microsoft.com/Office365/SecurityCompliance/content-search#searching-microsoft-teams-and-office-365-groups)。

> [!TIP]
> 有关如何使用 Azure AD Connect 与 Azure Active Directory 同步的信息，请参阅[将本地标识与 Azure Active Directory 集成](https://go.microsoft.com/fwlink/?linkid=854600)。

## <a name="requirements-for-on-premises-exchange-mailbox-user"></a>本地 Exchange 邮箱用户的要求

如果用户希望能够使用 Exchange 安排团队会议，则需要确保以下内容：

- 代理人和委托人进行通话都必须在 Exchange 服务器上有邮箱。

- 自动发现（AutoD） V2 是允许团队服务执行用户邮箱未经身份验证的发现所必需的。 AutoD V2 在 Exchange 2013 CU19 + 中受支持。

- 必须为 EVOSTS 配置认证服务器的 Exchange 服务器。 这将自动配置为 Exchange 的混合向导（HWA）的一部分。

    如果不想运行 HWA，则可以按照以下说明在 exchange Server 上手动创建 EVO STS 的身份验证服务器在[exchange 和 Exchange Online 组织之间配置 OAuth 身份验证](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)。 但是，我们建议你使用 HWA。

- Exchange 服务器必须为合作伙伴应用程序配置了**Skype For business online**的应用程序 ID 00000004-0000-0ff1-ce00-000000000000。 ID 由团队计划服务和具有以下属性的链接的用户帐户使用：

  - 从 Exchange 通讯簿中隐藏。 最佳做法是将其从通讯簿中隐藏，因为它是禁用的用户帐户。

  - **UserApplication**的 Exchange 管理角色分配。

若要完成集成，请按照步骤1-3 操作，[了解如何在本地 Exchange 和 Exchange Online 组织之间配置 OAuth 身份验证？](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help#how-do-you-configure-oauth-authentication-between-your-on-premises-exchange-and-exchange-online-organizations) 请注意，步骤2包括 ArchiveApplication 的角色分配，这不是委派所必需的，而是用于存档 SfB 在线聊天到 Exchange 邮箱。
