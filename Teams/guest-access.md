---
title: Microsoft Teams 中的来宾访问
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: sbhatta
audience: admin
search.appverid: MET150
description: 利用 Microsoft Teams 中的来宾访问功能，贵组织中的团队可以通过为贵组织外的人员授予访问团队和频道的权限来与其协作。
localization_priority: Priority
f1.keywords: ms.teamsadmincenter.orgwidesettings.guestaccess.overview
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e3490d208f95138d9aad57d69f55957dafb8734e
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41707547"
---
<a name="guest-access-in-microsoft-teams"></a>Microsoft Teams 中的来宾访问
======================================

通过来宾访问，可将组织外部的单个用户添加到 Microsoft Teams 中的团队和频道。 

要将外部访问（联合身份验证）与来宾访问进行比较（并决定应使用哪个），请阅读[与 Teams 中其他组织的用户通信](communicate-with-users-from-other-organizations.md)。

如果你已准备好在组织中启用来宾访问，请从[来宾访问清单](guest-access-checklist.md)开始。

## <a name="guest-access-overview"></a>来宾访问概述

利用来宾访问功能，贵组织中的团队可以通过为贵组织外的人员授予访问 Teams 中现有团队和频道的权限来与其协作。 具有企业或消费者电子邮件帐户（例如 Outlook、Gmail 或其他帐户）的任何人都能以访客身份参与 Teams，并对团队聊天、会议和文件具有完全访问权限。 作为 Teams 管理员，你可以控制来宾可以（及不可）在 Teams 中使用的功能 - 请查看[管理来宾访问](manage-guests.md)。

来宾访问是 Teams 组织范围内的设置且默认关闭。 来宾访问受制于 Azure AD 和 Office 365 服务限制。


> [!IMPORTANT]
> 来宾用户遵循 Teams 组织范围内的共存升级模式设置。 此选项无法更改。

## <a name="licensing-for-guest-access"></a>来宾访问的许可

所有 Office 365 商业高级版、Office 365 企业版和 Office 365 教育版订阅均包含来宾访问功能。 无需额外的 Office 365 许可证。 Teams 不限制可添加的来宾数量。 但是，可添加到租户的来宾总数取决于 Azure AD 许可所允许的数量（通常为每个许可用户可添加 5 个来宾）。 有关详细信息，请参阅 [Azure AD B2B 协作授权](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance)。


> [!NOTE]
> 你组织中仅拥有独立 Office 365 订阅计划（例如 Exchange Online 计划 2）的用户不可作为来宾被邀请加入你的组织，因为 Teams 将这些用户视为属于该组织。 要让这些用户使用 Teams，必须向他们分配 Office 365 商业高级版、Office 365 企业版或 Office 365 教育版订阅。 

## <a name="who-is-a-guest"></a>来宾具体是什么？

来宾是贵组织的员工、学生和成员以外的任何人。 他们在贵组织没有学校或工作帐户。 例如，来宾可以包括合作伙伴、供应商、提供商或顾问。 不属于你的组织的任何人都可作为来宾添加到 Teams 中。 这意味着具有业务帐户（即 Azure Active Directory 帐户）或客户电子邮件帐户（带有 Outlook.com 和 Gmail.com 等）的任何人都可作为来宾参与 Teams，并且可完全访问团队和频道体验。

要了解有关来宾可以操作和无法执行的操作的更多信息，请参阅[授权 Microsoft Teams 中的来宾访问](teams-dependencies.md)。 或查看[团队成员和来宾功能比较](guest-experience.md#comparison-of-team-member-and-guest-capabilities)表。 

最后，Teams 中的所有来宾与其他 Office 365 产品享受同样的合规性和审核保护，而且可在 Azure AD 中安全托管。

## <a name="why-use-guest-access"></a>为何要使用来宾访问？

借助来宾访问权限，使用 Teams 的组织可向其合作伙伴提供对团队、频道中的文档、资源、聊天和应用的访问权限，同时对其自己的公司数据维护完全控制。 Teams 中的所有来宾与其他 Office 365 产品享受同样的合规性和审核保护，而且可在 Azure AD 中安全托管。  

## <a name="understand-the-limitations-for-guests"></a>了解来宾的限制

来宾体验体验在设计上有限制。 确保你了解来宾体验，这样你就不会试图去解决一些不成问题的问题。 例如，下面列出了一些 Microsoft Teams 中来宾无法使用的功能：

- OneDrive for Business
- 在 Teams 外进行人员搜索
- 日历、计划的会议或会议详细信息
- PSTN
- 组织结构图
- 创建或修订团队
- 浏览团队
- 将文件上传到个人对个人聊天
- 目前，Teams 仅支持 [Azure B2B](https://docs.microsoft.com/azure/active-directory/b2b/user-properties) 定义的状态 1 和状态 2 类来宾用户。

有关来宾在 Teams 中可以和不可执行的操作的完整列表，请参阅[团队成员和来宾功能比较](guest-experience.md#comparison-of-team-member-and-guest-capabilities)表。 要了解有关 Office 365 级别的来宾访问的更多信息，请参阅[将来宾添加到 Office 365 组](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6)。


## <a name="more-information"></a>更多信息

[联系商业版产品的支持人员 - 管理员帮助](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?toc=/microsoftteams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)  
[Office 365 组的来宾访问](https://support.office.com/en-us/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6?ui=en-US&rs=en-US&ad=US#bkmk_usepowershell&PickTab=FAQ) 
  
