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
ms.openlocfilehash: 6e2e6af198c578279e2af8928e8a6ac299f262a5
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/12/2020
ms.locfileid: "49661897"
---
# <a name="how-exchange-and-microsoft-teams-interact"></a>Exchange 与 Microsoft Teams 如何交互

> [!Tip]
> 观看以下会话，了解 Teams 如何与 Azure Active Directory (AAD) 、Microsoft 365 组、Exchange、SharePoint 和 OneDrive for Business 交互[：Microsoft Teams](https://aka.ms/teams-foundations)的基础

为获得完整的 Teams 体验，应为每个用户启用 Exchange Online、SharePoint Online 和 Microsoft 365 组创建。

用户的 Exchange 邮箱可以托管在线上或本地。

Exchange Online 或 Exchange Dedicated vNext 上托管的用户可以使用 Teams 的所有功能。 他们可以创建和加入团队和频道、创建和查看会议、呼叫和聊天、修改用户配置文件图片 (（如果 Outlook 网页邮箱策略允许他们这样做) ）以及添加和配置连接器、选项卡和机器人。 有关可用功能的更全面列表，请参阅下表。

在旧版 Exchange Online 专用 (托管) 必须同步到 Microsoft 365 或 Office 365 上的 Azure Active Directory。 他们可以创建和加入团队和频道、添加和配置选项卡和机器人，以及利用聊天和通话功能。 但是，他们不能修改个人资料图片、管理会议、访问 Outlook 联系人或管理连接器。

> [!IMPORTANT]
> 为了与本地集成，强烈建议使用 Exchange Server 2016 或更高版本部署 Exchange 完整经典混合部署。 例如，新式混合支持仅限于闲/忙，不提供从 Teams 到本地邮箱的日历集成。 有关设置混合部署的信息，请参阅Exchange Server [部署](https://docs.microsoft.com/exchange/exchange-hybrid)。

具有本地托管邮箱的用户必须同步到 Azure Active Directory。 他们可以使用上述方案的所有功能，但此外，如果满足"本地托管邮箱的要求"部分中列出的要求，他们还可以管理[](#requirements-to-create-and-view-meetings-for-mailboxes-hosted-on-premises)会议。

下表提供了基于 Exchange 环境的功能可用性的有用快速参考。

**支持的操作：**

| 用户的邮箱托管在：                                        | 电子数据展示       | 法定 &nbsp; 保留    | 保留期  | 团队和频道管理 | 在 Teams 创建和查看会议 | 修改用户个人资料图片 | 呼叫历史记录 | 管理联系人 | 访问 Outlook 联系人 | 语音邮件  | 添加和配置连接器 | 添加和配置选项卡 | 添加和配置聊天机器人 |
|---------------------------------------------------------------------|------------------|--------------------|------------|-----------------------|-----------------------------------|-----------------------------|--------------|-----------------|-------------------------|------------|------------------------------|------------------------|------------------------|
| **Exchange Online**                                                 | 是 <sup>1</sup> | 是 <sup>1</sup>   | 是        | 是                   | 是                               | 是<sup>7</sup>             | 是          | 是             | 是 <sup>6</sup>        | 是        | 是                          | 是                    | 是                    |
| **Exchange Online Dedicated vNext**                                 | 是 <sup>1</sup> | 是 <sup>1</sup>   | 是        | 是                   | 是                               | 是<sup>7</sup>             | 是          | 是             | 是 <sup>6</sup>        | 是        | 是                          | 是                    | 是                    |
| **Exchange Online Dedicated - Legacy**（同步到所需 Azure AD）  | 是 <sup>1</sup> | 是 <sup>1，2</sup> | 是 <sup>3</sup> | 是                   | 否                                | 否                          | 是          | 是             | 否                      | 是 <sup>4</sup> | 是 <sup>5</sup>                   | 是                    | 是                    |
| **Exchange 本地同步** (Azure AD)  | 是 <sup>1</sup> | 是 <sup>1</sup>   | 是 <sup>3</sup> | 是                   | 是 <sup>8</sup>         | 否                          | 是          | 是             | 否                      | 是 <sup>4</sup> | 是 <sup>5</sup>                   | 是                    | 是                    |

所有托管选项都支持<sup>1</sup>个电子数据展示和法定保留，以确保通道消息的合规性。

<sup>2</sup> Teams 私人聊天消息尚不支持此托管选项的法定保留。

<sup>3</sup> 保留期将使用阴影邮箱供联机用户存储邮件。

具有本地 Exchange 邮箱的<sup>4</sup>个 Teams 用户可以对 Teams 使用语音邮件，在 Outlook 中接收语音邮件消息，但语音邮件在 Teams 客户端中无法查看或播放。

<sup>5</sup> 如果团队的其中一个所有者可以添加连接器，则该团队中的其他人将能够添加连接器，即使其邮箱位于本地。

<sup>6</sup> 仅默认联系人文件夹中的联系人。 不支持访问其他联系人文件夹或子文件夹。

<sup>7</sup> Teams 遵守 [由](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy) 租户管理员配置的 Outlook 网页版邮箱策略设置，以控制用户是否可以更改其个人资料图片。 如果在 **策略中关闭 -SetPhotoEnabled** 设置，则用户无法添加、更改或删除其个人资料图片。 例如，如果用户上传经组织 IT 或人力资源部门批准的配置文件图片，则无需任何操作。 但是，如果用户上载不适宜的图片，请根据组织的内部策略更改该图片。

<sup>8</sup>您需要满足"要求"中列出的要求，以便为托管在本地的邮箱创建和[查看会议。](#requirements-to-create-and-view-meetings-for-mailboxes-hosted-on-premises)

## <a name="requirements-to-get-the-most-out-of-microsoft-teams"></a>从 Microsoft Teams 中获得最大功能的要求

Microsoft Teams 与多个 Microsoft 365 和 Office 365 服务合作，为用户提供丰富的体验。 若要支持此体验，需要启用某些功能或服务并分配许可证。

- 必须为用户分配 Exchange Online 许可证。

- 要在团队对话中共享和存储文件，需要 SharePoint Online。 Microsoft Teams 不支持本地 SharePoint。

- 如果用户想要在聊天中共享文件，则必须为用户分配 SharePoint Online 许可证。 如果未为用户分配 SharePoint Online 许可证并为其启用，则他们在 Microsoft 365 或 Office 365 中没有 OneDrive for Business 存储空间。 文件共享将继续在频道中工作，但用户在没有 Microsoft 365 或 Office 365 中的 OneDrive for Business 存储的情况下无法在聊天中共享文件。

- 必须允许用户创建 Microsoft 365 组，以在 Microsoft Teams 中创建团队。

  > [!IMPORTANT]
  > 如果将用户移动到"仅 Teams"模式后卸载 Skype  for Business 客户端，状态可能会停止在 Outlook 和其他 Office 应用中工作。 状态在 Teams 中显示良好。 若要解决此问题，请选择 Microsoft Teams 右上角的个人资料图片，然后选择"设置 **"。** 在"**应用程序"** 下的"常规"选项卡上，选择"将 Teams 注册为 Office 聊天 (**需要重启 Office 应用程序**) 。 选择此选项后，关闭并再次打开所有 Office 应用，包括 Outlook。 打开 Outlook 后，状态信息将可用。

## <a name="requirements-to-create-and-view-meetings-for-mailboxes-hosted-on-premises"></a>为本地托管的邮箱创建和查看会议的要求

如果邮箱托管在本地，若要创建和查看会议，必须满足以下要求：

- 需要为 Azure Active Directory 同步的用户分配所需的 Teams 许可证。

- 用户必须同步到 Azure Active Directory。 有关如何使用 Azure AD Connect 与 Azure Active Directory 同步的信息，请参阅 [混合标识文档](https://docs.microsoft.com/azure/active-directory/hybrid/)。

- 邮箱托管在 Exchange Server 2016 累积更新 3 或更高版本中。

- 自动发现和 Exchange Web 服务在外部发布。

- 最好是通过 Exchange 混合配置向导配置 OAuth 身份验证，该向导在经典或新式 (混合配置) 。 如果无法使用混合配置向导，请根据在 Exchange 和 Exchange Online 组织之间配置 OAuth 身份验证中所述配置[OAuth。](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

  > [!NOTE]
  > Exchange 信任来自 Teams 服务（称为 EvoSTS）的 OAuth 令牌。 步骤 1 应该足够，但只有 EvoSTS;ACS 用于在日历中查找忙/闲。

- 已设置 Azure AD Connect 中 Exchange 混合部署功能复选框。

- 对于日历应用支持和适用于 Mac 的 Teams Outlook Add-In，必须在租户 Azure AD 中为 Exchange 服务主体将 Exchange Web 服务 URL 配置为 SNS。 此步骤是使用混合配置向导或遵循混合新式[身份验证的手动步骤完成。](https://docs.microsoft.com/microsoft-365/enterprise/configure-exchange-server-for-hybrid-modern-authentication#add-on-premises-web-service-urls-as-spns-in-azure-ad)

为这些用户启用日历委派：

- 还必须完成步骤 2-3，如 Skype for Business Online 和 Exchange Server 之间配置集成 [和 OAuth 中所述](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises);这些步骤将为 Teams 计划应用程序提供确认委托权限所需的权限。
 
  > [!NOTE]
  > 步骤 2 角色分配 ArchiveApplication，这是委派不需要的。

- 代表某人安排会议时，Teams 计划 Outlook 加载项需要 Exchange 2013 CU19 或更高版本。 这是为了支持我们的服务对邮箱进行未经身份验证的发现，以检查委派者邮箱的代理权限。 代理人和代理人的位置可以是 Exchange 2013 或更高版本或 Exchange Online，但自动发现必须解析为 Exchange 2013 CU19 或更高版本。

## <a name="additional-considerations"></a>其他注意事项

以下是在组织中实施 Microsoft Teams 时需考虑的一些额外问题。

- 在 Microsoft Teams 中，安全性和合规性功能（例如，电子数据展示、内容搜索、存档和法定保留）在 Exchange Online 和 SharePoint Online 环境中完全正常。 对于频道对话，消息会记录到 Exchange Online 中的组邮箱，它们在此可用于电子数据展示。 如果在组织中为用户启用了 SharePoint Online 和 OneDrive for Business（使用工作帐户或学校帐户），也可以对 Teams 中的所有文件使用这些合规性功能。

- 使用条件访问控制和保护 Teams 和 Exchange 中符合性策略的配置。 有关详细信息，请参阅条件 [访问策略如何适用于 Teams？](security-compliance-overview.md#how-conditional-access-policies-work-for-teams)

- 如果您的组织有合规性要求，以确保所有会议讨论均可发现，则如果组织者具有 Exchange 本地邮箱，您应该禁用私人会议。 有关详细信息，请参阅"[允许安排私人会议"。](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams#allow-scheduling-private-meetings)

- 在 Exchange 混合部署中，聊天消息中的内容可搜索，无论聊天参与者是具有基于云的邮箱还是本地邮箱。 若要了解有关详细信息，请阅读["搜索本地用户的基于云的邮箱"。](https://docs.microsoft.com/office365/securitycompliance/search-cloud-based-mailboxes-for-on-premises-users) 若要了解如何在 Teams 中搜索内容，请阅读 [Microsoft 365 合规中心的内容搜索](https://docs.microsoft.com/Office365/SecurityCompliance/content-search#searching-microsoft-teams-and-office-365-groups)。

- 对于状态，Microsoft Teams 必须检查邮箱是托管在 Exchange Online 还是本地。 然后，服务将决定在何处访问邮箱。 若要使 Teams 服务能够通过 REST API 调用 Exchange Online 服务来检查邮箱位置，必须运行 Exchange 混合配置向导来部署 Exchange 混合环境，如使用混合配置向导创建混合部署 [中所述](https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid)。

## <a name="troubleshooting"></a>疑难解答

有关该主题的完整故障排除指南，请确保查看 [Microsoft Teams](https://docs.microsoft.com/microsoftteams/troubleshoot/known-issues/teams-exchange-interaction-issue)疑难解答和Exchange Server问题。
