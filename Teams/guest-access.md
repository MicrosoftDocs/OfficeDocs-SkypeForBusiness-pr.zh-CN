---
title: Microsoft Teams 中的来宾访问
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 11/25/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: sbhatta
search.appverid: MET150
description: 利用 Microsoft Teams 中的来宾访问功能，贵组织中的团队可以通过为贵组织外的人员授予访问团队和频道的权限来与其协作。
localization_priority: Priority
f1keywords: ms.teamsadmincenter.orgwidesettings.guestaccess.overview
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d3b194be61baa0a10594649ac00c97e503d15993
ms.sourcegitcommit: a78fee3cad5b58bf41dd014a79f4316cf310c8d1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/29/2019
ms.locfileid: "35925309"
---
<a name="guest-access-in-microsoft-teams"></a>Microsoft Teams 中的来宾访问
======================================

“来宾访问”是客户需求最强烈的的功能之一。 你可按此处所述了解来宾访问功能的最新进展并将你的想法告诉我们：

- 如果你在使用来宾访问时遇到问题，请查看 [Microsoft Teams 的已知问题](Known-issues.md)。
- 请在 [Teams 路线图](https://aka.ms/teamsroadmap)中了解即将发布的新功能或更新功能。
- 请在 [Teams UserVoice](https://aka.ms/TeamsUserVoice) 中将你想要的功能告诉我们。
- 在下面的“注释”部分中分享你的体验。

## <a name="guest-access-overview"></a>来宾访问概述

借助“来宾访问”功能，你组织中的团队可通过在你的一个或多个租户中向组织外部人员授予现有团队和频道的访问权限，与他们进行协作。 具有企业或消费者电子邮件帐户（例如 Outlook、Gmail 或其他帐户）的任何人都能以访客身份参与 Teams，并对团队聊天、会议和文件具有完全访问权限。

许多 Office 365 订阅都包含来宾访问功能，而无额外的许可要求。 有关许可的详细信息，请参阅 [Azure Active Directory B2B 协作许可指南](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance)。

来宾访问是 Microsoft Teams 中的租户级别设置且默认关闭。 来宾访问受制于 Azure AD 和 Office 365 服务限制。

> [!NOTE]
> 你组织中仅拥有独立 Office 365 订阅计划（例如 Exchange Online 计划 2）的用户不可作为来宾被邀请加入你的组织，因为 Teams 将这些用户视为属于该组织。 要让这些用户使用 Teams，必须向他们分配 Office 365 商业高级版、Office 365 企业版或 Office 365 教育版订阅。 

## <a name="who-is-a-guest"></a>来宾具体是什么？

来宾是贵组织的员工、学生和成员以外的任何人。 他们在贵组织没有学校或工作帐户。 例如，来宾可以包括合作伙伴、供应商、提供商或顾问。 不属于你的组织的任何人都可作为来宾添加到 Teams 中。 这意味着具有业务帐户（即 Azure Active Directory 帐户）或客户电子邮件帐户（带有 Outlook.com 和 Gmail.com 等）的任何人都可作为来宾参与 Teams，并且可完全访问团队和频道体验。 （有关来宾限制，可参阅[在 Microsoft Teams 中授予来宾访问权限](teams-dependencies.md)。）Teams 中的所有来宾与其他 Office 365 产品享受同样的合规性和审核保护，而且可在 Azure AD 中安全托管。

## <a name="why-use-guest-access"></a>为何要使用来宾访问？

借助来宾访问权限，使用 Teams 的组织可向其合作伙伴提供对团队、频道中的文档、资源、聊天和应用的外部访问权限，同时对其自己的公司数据维护完全控制。 Teams 中的所有来宾与其他 Office 365 产品享受同样的合规性和审核保护，而且可在 Azure AD 中安全托管。  

Teams 建立在 Office 365 组之上，为 Office 365 组提供访问共享资产的全新方式。 Teams 是实现在组/团队成员之间进行持久聊天的最佳解决方案。 Office 365 是针对一组共享团队资产（例如 SharePoint 网站或 Power BI 仪表板）提供跨应用成员身份的服务，以便团队可以有效且安全地协作。 

## <a name="how-does-guest-access-compare-to-external-access-federation"></a>与外部访问（联合身份验证）相比，来宾访问如何？

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="more-information"></a>详细信息

[联系商业版产品的支持人员 - 管理员帮助](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?toc=/microsoftteams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)  

  [Office 365 组的来宾访问](https://support.office.com/zh-CN/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6?ui=en-US&rs=en-US&ad=US#bkmk_usepowershell&PickTab=FAQ) 
  
