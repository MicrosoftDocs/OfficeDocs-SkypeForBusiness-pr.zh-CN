---
title: Microsoft Teams 中的来宾访问
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: rafarhi
audience: admin
search.appverid: MET150
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.orgwidesettings.guestaccess.overview
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
description: 利用 Microsoft Teams 中的来宾访问功能，贵组织中的团队可以通过为贵组织外的人员授予访问团队和频道的权限来与其协作。
ms.openlocfilehash: 388fb68196a6e68c13066b7b94a1b24a31834b37
ms.sourcegitcommit: 43e5a4aac11c20dd5a4c35b59695f309e1559e82
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/03/2020
ms.locfileid: "48346163"
---
# <a name="guest-access-in-microsoft-teams"></a>Microsoft Teams 中的来宾访问

有了来宾访问权限，您可以为组织外部的人员提供对团队、频道、资源、聊天和应用程序的访问权限，同时保持对公司数据的控制。

来宾是贵组织的员工、学生和成员以外的任何人。 他们在贵组织没有学校或工作帐户。 例如，来宾可以包括合作伙伴、供应商、提供商或顾问。 不属于你的组织的任何人都可作为来宾添加到 Teams 中。 这意味着拥有商业帐户 (的任何人（如 Azure Active Directory 帐户) 或使用者电子邮件帐户 (具有 Outlook.com、Gmail.com 或其他) ）都可以通过访问团队和频道体验加入到团队中的来宾。

作为团队管理员，你可以 [控制来宾可以 (和不能在团队中) 使用的功能](manage-guests.md)。 团队中的来宾受与 Microsoft 365 其余部分相同的合规性和审核保护涵盖，并且可以在 Azure AD 中托管。 来宾访问受到 Azure AD 和 Microsoft 365 或 Office 365 服务限制的约束。

来宾体验体验在设计上有限制。 有关来宾可以和不能在团队中执行哪些操作的完整列表，请参阅[团队成员和来宾功能的比较](guest-experience.md#comparison-of-team-member-and-guest-capabilities)。

> [!IMPORTANT]
> 来宾用户遵循 Teams 组织范围内的共存升级模式设置。 此选项无法更改。

要将外部访问（联合身份验证）与来宾访问进行比较（并决定应使用哪个），请阅读[与 Teams 中其他组织的用户通信](communicate-with-users-from-other-organizations.md)。

## <a name="set-up-guest-access"></a>设置来宾访问

团队中的来宾访问需要在 Microsoft 365 中配置其他设置，包括 Azure AD、Microsoft 365 组和 SharePoint 中的设置。 如果你已准备好开始邀请团队加入团队，请阅读下列内容之一：

- 若要为团队配置常规使用的来宾访问，请参阅 [与团队中的来宾协作](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)。
- 若要与使用 Azure Active Directory 的合作伙伴组织进行协作，并允许来宾自行注册团队访问，请参阅 [使用托管来宾创建 B2B extranet](https://docs.microsoft.com/microsoft-365/solutions/b2b-extranet)。

团队中的来宾访问权限是组织范围的设置，默认情况下处于关闭状态。 您可以使用 [灵敏度标签](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)控制对单个团队的来宾访问。

## <a name="how-a-guest-becomes-a-member-of-a-team"></a>来宾如何成为团队成员

1. 团队所有者或 Microsoft 365 管理员 [将来宾添加到团队](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f)。
2. 来宾会收到一封来自团队所有者的欢迎电子邮件，其中内附团队信息及其现在作为成员应执行的操作。
3. 来宾接受邀请。
  在 Azure Active Directory 中拥有工作或学校帐户的来宾用户可以接受邀请并直接进行身份验证。 将向其他用户发送一次性传递代码，以验证其身份 () 所需的 [一次性密码验证](https://docs.microsoft.com/azure/active-directory/external-identities/one-time-passcode) 。
4. 接受邀请后，来宾可[参与团队和频道](https://support.office.com/article/df38ae23-8f85-46d3-b071-cb11b9de5499)、接收和答复频道消息、[访问频道中的文件](https://support.office.com/article/access-files-in-channels-c593c78a-27c4-4661-a598-682baa30ca7e)，还能参与聊天、加入会议并协作处理文档等等。 

在 Teams 中，可清楚地识别来宾。 来宾用户的姓名包含 **(来宾)** 标签，而频道中有一个图标来表示团队中存在来宾。 有关更多详细信息，请参阅[来宾体验介绍](guest-experience.md)。
  
来宾可以随时在 Teams 中离开团队。 有关详细信息，请参阅[如何离开团队？](https://support.office.com/article/leave-a-team-e481005d-3ec6-4694-b300-375472ba4076)

> [!NOTE]
> 离开团队不会从你的组织的目录中删除来宾帐户。 这必须由 Microsoft 365 全局管理员或 Azure AD 管理员完成。

## <a name="licensing-for-guest-access"></a>来宾访问的许可

来宾访问包括在所有 Microsoft 365 商业标准、Microsoft 365 企业版和 Microsoft 365 教育版订阅中。 不需要额外的 Microsoft 365 许可证。 Teams 不对可添加的来宾数量进行限制。 但是，可添加到你的租户的来宾总数可能受到 Azure AD 的付费功能的限制。 有关详细信息，请参阅 [Azure AD B2B 协作授权](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance)。

> [!NOTE]
> 你的组织中仅有独立 Microsoft 365 订阅计划（如 Exchange Online 计划2）的用户不能被邀请加入你的组织的来宾，因为团队会将这些用户视为属于同一组织。 要让这些用户使用 Teams，必须向他们分配 Microsoft 365 商业标准版、Office 365 企业版或 Office 365 教育版订阅。 

## <a name="guest-access-reviews"></a>来宾访问评论

你可以使用 Azure AD 为组成员或分配到应用程序的用户创建访问审核。 创建定期访问评论可节省您的时间。 如果需要定期查看有权访问应用程序、团队或组成员的用户，您可以定义这些评审的频率。 

你可以自行执行来宾访问检查、要求来宾查看其自己的成员身份，或者要求应用程序所有者或业务决策人执行访问权审核。 使用 Azure 门户执行来宾访问评论。 有关详细信息，请参阅 [使用 AZURE AD 访问审核管理来宾访问](https://docs.microsoft.com/azure/active-directory/governance/manage-guest-access-with-access-reviews)。

## <a name="related-topics"></a>相关主题

[与组织外部的人员进行协作](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization)

[阻止来自特定 Microsoft 365 组或 Microsoft 团队团队的来宾用户](https://docs.microsoft.com/microsoft-365/solutions/per-group-guest-access)

[创建安全的来宾共享环境](https://docs.microsoft.com/microsoft-365/solutions/create-secure-guest-sharing-environment)

[联系商业版产品的支持人员 - 管理员帮助](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)

[配置具有三层保护的团队](https://docs.microsoft.com/microsoft-365/solutions/configure-teams-three-tiers-protection)
