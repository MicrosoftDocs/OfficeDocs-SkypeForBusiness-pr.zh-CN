---
title: Microsoft Teams 中的来宾访问
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: sbhatta
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
ms.openlocfilehash: f04fce7f75df32111b2577119c12b14eadf963b9
ms.sourcegitcommit: 20258b691ffc559b1656fd1e57f67f5c3a9e29e1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/15/2020
ms.locfileid: "46761238"
---
# <a name="guest-access-in-microsoft-teams"></a>Microsoft Teams 中的来宾访问

利用来宾访问功能，贵组织中的团队可以通过为贵组织外的人员授予访问 Teams 中现有团队和频道的权限来与其协作。 任何拥有企业或消费者电子邮件帐户（例如 Microsoft 365、Outlook、Gmail 或其他人）的人都可以在团队中作为来宾参与团队聊天、会议和文件的完全访问。 作为 Teams 管理员，你可以控制来宾可以（及不可）在 Teams 中使用的功能 - 请查看[管理来宾访问](manage-guests.md)。

要将外部访问（联合身份验证）与来宾访问进行比较（并决定应使用哪个），请阅读[与 Teams 中其他组织的用户通信](communicate-with-users-from-other-organizations.md)。

来宾访问是 Teams 组织范围内的设置且默认关闭。  (您可以使用 [灵敏度标签](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)控制对单个团队的来宾访问。 ) 

如果你已准备好开始邀请团队加入团队，请阅读下列内容之一：

- 若要为团队配置常规使用的来宾访问，请参阅 [与团队中的来宾协作](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)。
- 若要与使用 Azure Active Directory 的合作伙伴组织进行协作，并允许来宾自行注册团队访问，请参阅 [使用托管来宾创建 B2B extranet](https://docs.microsoft.com/microsoft-365/solutions/b2b-extranet)。

来宾访问受到 Azure AD 和 Microsoft 365 或 Office 365 服务限制的约束。

> [!IMPORTANT]
> 来宾用户遵循 Teams 组织范围内的共存升级模式设置。 此选项无法更改。

## <a name="licensing-for-guest-access"></a>来宾访问的许可

所有 Microsoft 365 商业标准版、Office 365 企业版和 Office 365 教育版订阅均包含来宾访问功能。 无需额外的 Microsoft 365 或 Office 365 许可证。 Teams 不对可添加的来宾数量进行限制。 但是，可添加到你的租户的来宾总数可能受到 Azure AD 的付费功能的限制。 有关详细信息，请参阅 [Azure AD B2B 协作授权](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance)。


> [!NOTE]
> 你组织中仅拥有独立Microsoft 365 或 Office 365 订阅计划（例如 Exchange Online 计划 2）的用户不可作为来宾被邀请加入你的组织，因为 Teams 将这些用户视为属于该组织。 要让这些用户使用 Teams，必须向他们分配 Microsoft 365 商业标准版、Office 365 企业版或 Office 365 教育版订阅。 

## <a name="who-is-a-guest"></a>来宾具体是什么？

来宾是贵组织的员工、学生和成员以外的任何人。 他们在贵组织没有学校或工作帐户。 例如，来宾可以包括合作伙伴、供应商、提供商或顾问。 不属于你的组织的任何人都可作为来宾添加到 Teams 中。 这意味着具有业务帐户（即 Azure Active Directory 帐户）或客户电子邮件帐户（带有 Outlook.com 和 Gmail.com 等）的任何人都可作为来宾参与 Teams，并且可完全访问团队和频道体验。

要了解有关来宾可以操作和无法执行的操作的更多信息，请参阅[授权 Microsoft Teams 中的来宾访问](teams-dependencies.md)。 或查看[团队成员和来宾功能比较](guest-experience.md#comparison-of-team-member-and-guest-capabilities)表。 

最后，团队中的所有来宾均被与 Microsoft 365 的其余部分相同的合规性和审核保护涵盖，并且可以在 Azure AD 中托管。

## <a name="why-use-guest-access"></a>为何要使用来宾访问？

借助来宾访问权限，使用 Teams 的组织可向其合作伙伴提供对团队、频道中的文档、资源、聊天和应用的访问权限，同时对其自己的公司数据维护完全控制。 

## <a name="understand-the-limitations-for-guests"></a>了解来宾的限制

来宾体验体验在设计上有限制。 确保你了解来宾体验，这样你就不会试图去解决一些不成问题的问题。 下面是 Microsoft 团队中的来宾无法使用的部分功能的列表：

- OneDrive
- 在 Teams 外进行人员搜索
- 日历、计划的会议或会议详细信息
- PSTN
- 组织结构图
- 创建或修订团队
- 浏览团队
- 将文件上传到个人对个人聊天
- 当前，团队仅支持 [状态1和状态2来宾用户类型](https://docs.microsoft.com/azure/active-directory/b2b/user-properties)

有关来宾在 Teams 中可以和不可执行的操作的完整列表，请参阅[团队成员和来宾功能比较](guest-experience.md#comparison-of-team-member-and-guest-capabilities)表。 若要了解有关 Microsoft 365 级别的来宾访问的详细信息，请阅读 [与组织外部人员进行协作](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization)。


## <a name="related-topics"></a>相关主题

[联系商业版产品的支持人员 - 管理员帮助](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)

[配置具有三层保护的团队](https://docs.microsoft.com/microsoft-365/solutions/configure-teams-three-tiers-protection)
