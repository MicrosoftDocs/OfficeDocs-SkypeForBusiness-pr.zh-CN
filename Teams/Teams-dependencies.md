---
title: 在 Microsoft Teams 中授权来宾访问
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- SPO_Content
- m365initiative-externalcollab
ms.reviewer: rafarhi
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
description: 通过四种不同级别的授权来管理 Microsoft Teams 来宾访问功能。
ms.openlocfilehash: 40bc8c68ac3f1ad3117fa47aa0aad5f14ff3be69
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2020
ms.locfileid: "49030988"
---
# <a name="authorize-guest-access-in-microsoft-teams"></a>在 Microsoft Teams 中授权来宾访问

为满足贵组织的要求，你可以通过四种不同级别的授权来管理 Teams 来宾访问功能。 所有这些授权级别都将应用于你的 Microsoft 365 组织。 每个授权级别按如下所示控制来宾体验：

- **Azure Active Directory**：Teams 中的来宾访问依赖于 Azure AD 企业到企业 (B2B) 平台。 此授权级别控制目录、租户和应用程序级别的来宾体验。
- **Teams**：仅控制 Teams 中的来宾体验。
- **Microsoft 365 组**：控制 Microsoft 365 组和 Teams 中的来宾体验。
- **SharePoint 和 OneDrive**：控制 SharePoint、OneDrive、Microsoft 365 组和 Teams 中的来宾体验。

这些不同的授权级别可让你灵活选择为组织设置来宾访问的方式。 例如，如果你不想在 Microsoft Teams 组织中允许来宾用户，但想在组织中全面允许，只需在 Microsoft Teams 中关闭来宾访问即可。 其他示例：你可以在 Azure AD、Teams 和组级别启用来宾访问，然后[对匹配一个或多个条件（如数据分类为机密）的选定团队禁用添加来宾用户的功能](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)。 SharePoint 和 OneDrive 具有自己的不依赖 Microsoft 365 组的来宾访问设置。

如需端到端的来宾访问配置说明，请参阅[在团队中与来宾协作](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)。

> [!NOTE]
> 来宾应遵守 [Microsoft 365 和 Office 365 服务说明](https://go.microsoft.com/fwlink/p/?linkid=282347)和 [Azure AD B2B 协作限制](https://docs.microsoft.com/azure/active-directory/external-identities/current-limitations)中描述的服务限制。 

下面的示意图显示了如何授予并在 Azure Active Directory、Teams 和 Microsoft 365 之间集成来宾访问授权相关性。

> [!div class="mx-imgBorder"]
> ![用于来宾访问的授权相关性示意图。](media/teams_dependencies_image1.png)

下一张示意图概括性地显示了用户体验如何通过典型的来宾访问邀请和兑换流程与权限模型结合使用。

> [!div class="mx-imgBorder"]
> ![显示邀请和兑换流程的示意图](media/authorize-guest-image1.png)

此处有必要注意的是，应用、机器人和连接器可能需要自己的一套特定于用户帐户的权限和/或同意。 这些可能需要单独授予。 同样，SharePoint 可能针对特定用户、用户组，甚至在站点级别设置了额外的外部共享界限。

上两张示意图还可在 [Visio](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/media/teams_dependencies.vsdx?raw=true) 中查看。

## <a name="control-guest-access-in-azure-active-directory"></a>控制 Azure Active Directory 中的条件访问

使用 Azure AD 来确定外部协作者能否受邀以来宾的身份加入你的租户以及如何加入。 有关 Azure B2B 来宾访问的详细信息，请参阅[什么是 Azure Active Directory B2B 中的来宾用户访问权限](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b)。 要了解 Azure AD 角色，请参阅[在 Azure Active Directory 租户中向来自合作伙伴组织的用户授予权限](https://docs.microsoft.com/azure/active-directory/b2b/add-guest-to-role)。

邀请设置在组织级别应用，可控制目标和应用程序级别的来宾体验。 你可以在[外部协作设置](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/CompanyRelationshipsMenuBlade/Settings)中配置这些设置。

Azure AD 包含用于配置外部用户的以下设置：

- [来宾用户访问限制](https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-restrict-guest-permissions)

- **管理员和具有“来宾邀请者”角色的用户可以邀请**：“**是**”表示管理员和具有“来宾邀请者”角色的用户将能够邀请来宾加入租户。 “**否**”表示管理员和用户不可邀请来宾加入租户。
- **成员可邀请**：要允许目录的非管理员成员邀请来宾，请将此策略设置为 **是**（建议设置）。 如果你希望仅管理员能够添加来宾，可以将此策略设置为 **否**。 请记住，设置为 **否** 将会限制非管理员团队所有者的来宾体验；他们只能向管理员已在 AAD 中添加的团队添加来宾。
- **来宾可邀请**：“**是**”表示目录中的来宾可邀请其他来宾协作处理受到 Azure AD 保护的资源，例如 SharePoint 网站或 Azure 资源。 “**否**”表示来宾不可邀请其他来宾与你的组织协作。 即使设置为“**是**”，来宾也不能在 Teams 中邀请其他来宾。
 
有关控制谁可以邀请来宾的详细信息，请参阅[启用 B2B 外部协作并管理可邀请来宾的人员](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)。

> [!NOTE]
> 还可管理哪些域可以被邀请作为来宾进入你的租户。 请参阅[允许或阻止来自特定组织的给 B2B 用户的邀请](https://docs.microsoft.com/azure/active-directory/external-identities/allow-deny-list)。

无需将用户来宾帐户手动添加到 Azure AD B2B 中，因为在你向 Teams 添加来宾时，该帐户将自动添加到目录中。

### <a name="licensing-for-guest-access"></a>来宾访问的许可

来宾访问许可使用 Azure AD 外部标识定价，且基于月度活动来宾。 请参阅 [Azure AD 外部标识的计费模型](https://docs.microsoft.com/azure/active-directory/external-identities/external-identities-pricing)获取详细信息。

> [!NOTE]
> 你组织中仅拥有独立 Office 365 订阅计划（例如 Exchange Online 计划 2）的用户不可作为来宾被邀请加入你的组织，因为 Teams 将这些用户视为属于该组织。 要让这些用户使用 Teams，必须向他们分配 Microsoft 365 商业标准版、Office 365 企业版或 Office 365 教育版订阅。 

## <a name="external-access-federation-vs-guest-access"></a>外部访问（联合身份验证）与来宾访问

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="related-topics"></a>相关主题

- [Microsoft 365 来宾共享设置参考](https://docs.microsoft.com/Office365/Enterprise/microsoft-365-guest-settings)

[与 Microsoft 365 建立安全协作](https://docs.microsoft.com/microsoft-365/solutions/setup-secure-collaboration-with-teams)
