---
title: 在 Microsoft Teams 中管理来宾访问
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 06/21/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: IT 管理员可以在租户级别添加来宾、设置和管理来宾用户策略和权限、确定哪些用户可以邀请来宾以及获取有关来宾用户活动的报告。
appliesto:
- Microsoft Teams
ms.openlocfilehash: f3ede35352436074cbf7c94fc9df78100a73a017
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36241807"
---
<a name="manage-guest-access-in-microsoft-teams"></a>在 Microsoft Teams 中管理来宾访问
======================================

**来宾**是 Microsoft 团队中的一种用户/许可证类型, 包含在所有 Office 365 Business Premium、Office 365 企业版和 Office 365 教育版订阅中。 无需额外的 Office 365 许可证。 Teams 来宾访问是租户级别设置，默认情况下关闭。 有关如何启用来宾访问的详细信息, 请参阅[打开或关闭对 Microsoft 团队的来宾访问](set-up-guests.md)。

打开**来宾**用户/许可证类型后, 您可以通过组织的 "[管理 Microsoft 团队设置](enable-features-office-365.md)" 中所述的控件配置来宾的设置, 并在[过渡到新的 Microsoft 团队期间管理团队。管理中心](manage-teams-skypeforbusiness-admin-center.md)。     
    
IT 管理员可以在租户级别添加来宾、设置和管理来宾用户策略和权限, 以及获取有关来宾用户活动的报告。 可通过 Microsoft 团队管理中心获取这些控件。 来宾用户内容和活动与 Office 365 的其他部分一样受到相同的合规性和审核保护。

团队所有者可以邀请新来宾, 并将现有的目录来宾用户添加到其团队。 团队所有者可以通过**团队** > **管理团队**来标识来宾用户, 并通过**组织范围内的设置** > **来宾访问**为来宾设置频道相关的功能, 包括允许来宾创建、更新和删除频道, 如下图所示。

![团队中的来宾权限设置](media/manage-guest-access-image1.png)
  
你可以使用 Azure Active Directory (Azure AD) 门户管理来宾及其对 Office 365 和团队资源的访问权限。 团队来宾访问利用 Azure AD 企业对企业 (B2B) 协作功能, 作为存储安全原则信息 (如标识属性、成员身份和多重身份验证设置) 的基础基础结构。 若要了解有关 Azure AD B2B 的详细信息, 请参阅[什么是 AZURE AD b2b 协作？](https://go.microsoft.com/fwlink/p/?linkid=853011)和[AZURE Active Directory b2b 协作常见问题解答](https://go.microsoft.com/fwlink/p/?linkid=853020)。

> [!NOTE]
> Microsoft 团队始终采用 Azure AD 外部设置, 以允许或阻止来宾用户对租户的添加。 有关更多详细信息, 请参阅[在 Microsoft 团队中授权来宾访问](Teams-dependencies.md)。
  
## <a name="guest-access-vs-external-access-federation"></a>来宾访问与外部访问（联合身份验证）

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="review-guest-access-periodically"></a>定期查看来宾访问权限

在团队中, 你可以为每个许可用户添加5个来宾。 由于此限制, 或者你希望让你的租户保持最新状态, 你应定期查看来宾访问权限, 以标识有权不再需要的访问权限的用户。 你可以使用 Azure AD 为组成员或分配到应用程序的用户创建访问审核。 创建定期访问评论可节省您的时间。 如果需要定期查看有权访问应用程序或组成员的用户, 您可以定义这些评论的频率。 

你可以自行执行来宾访问检查、要求来宾查看其自己的成员身份, 或者要求应用程序所有者或业务决策人执行访问权审核。 使用 Azure 门户执行来宾访问审核。 有关详细信息, 请参阅[使用 AZURE AD 访问审核管理来宾访问](https://docs.microsoft.com/en-us/azure/active-directory/governance/manage-guest-access-with-access-reviews)。

###  <a name="prerequisites"></a>先决条件

Access 评论适用于 Azure AD 高级 P2 版本, 它包含在 Microsoft 企业移动性 + 安全性, E5 中。 有关详细信息, 请参阅[Azure Active Directory 版本](https://docs.microsoft.com/en-us/azure/active-directory/fundamentals/active-directory-whatis)。 通过创建评论、填写评论或确认其访问来与此功能交互的每个用户都必须有许可证。

团队不会限制可添加的来宾数量。 但是, 可添加到租户的来宾总数取决于 AAD 授权所允许的内容。 有关详细信息, 请参阅[AZURE AD B2B 协作授权](https://docs.microsoft.com/en-us/azure/active-directory/b2b/licensing-guidance)。

## <a name="guest-access-latencies"></a>来宾访问延迟

来宾设置在 Azure AD 中设置。 更改在 Office 365 组织中生效需要 2 小时到 24 小时。 如果用户尝试向其团队中添加来宾时看到消息 "请联系你的管理员", 则很可能是来宾功能尚未启用或设置尚未生效。

## <a name="more-information"></a>详细信息

有关使用 PowerShell 管理来宾访问权限的信息, 请参阅[使用 powershell 控制对团队的来宾访问](guest-access-powershell.md)。


