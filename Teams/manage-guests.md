---
title: 在 Microsoft Teams 中管理来宾访问
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
ms.date: 11/26/2018
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: sbhatta
search.appverid: MET150
description: IT 管理员可以在租户级别添加来宾、设置和管理来宾用户策略和权限、确定哪些用户可以邀请来宾以及获取有关来宾用户活动的报告。
appliesto:
- Microsoft Teams
ms.openlocfilehash: ef7a62f46a767271f96de6f8540867aa2e8bd917
ms.sourcegitcommit: 31827526894ffb75d64fcb0a7c76ee874ad3c269
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2019
ms.locfileid: "29753607"
---
<a name="manage-guest-access-in-microsoft-teams"></a>在 Microsoft Teams 中管理来宾访问
======================================

**来宾**是随所有 Office 365 企业高级版、 Office 365 Enterprise 和 Office 365 教育版订阅的 Microsoft 团队中的用户/许可证类型。 无需额外的 Office 365 许可证。 Teams 来宾访问是租户级别设置，默认情况下关闭。 有关如何启用来宾访问的详细信息，请参阅[打开或关闭向 Microsoft 工作组的来宾访问](set-up-guests.md)。

**来宾**用户/许可证类型已打开后，您可以配置设置的来宾通过控件中所述[在 Office 365 组织中管理 Microsoft 团队功能](enable-features-office-365.md)和[管理团队转换为新的 Microsoft 的过程团队管理中心](manage-teams-skypeforbusiness-admin-center.md)。     
    
IT 管理员可以在租户级别添加来宾、 设置和管理来宾用户策略和权限，并纳入有关来宾用户活动报告。 这些控件是可通过 Microsoft 团队管理中心。 来宾用户内容和活动与 Office 365 的其他部分一样受到相同的合规性和审核保护。

团队所有者可以邀请新的来宾，并将现有目录来宾用户添加到他们的团队。 团队所有者可以标识来宾用户通过**团队** > **管理团队**和设置通过**组织范围的设置**的来宾通道相关功能 > **来宾访问**，包括允许来宾来创建、 更新和删除通道，如以下屏幕截图中所示。

![团队中的来宾权限设置](media/manage-guest-access-image1.png)
  
您可以使用 Azure Active Directory 门户管理来宾和其访问 Office 365 和团队资源。 Teams 来宾访问利用 Azure Active Directory 企业到企业 (B2B) 协作功能作为基础结构来存储安全主体信息，例如，标识属性、成员身份以及多重身份验证设置。 要详细了解 Azure Active Directory B2B，请参阅 [Azure AD B2B 协作是什么？](https://go.microsoft.com/fwlink/p/?linkid=853011)和[Azure Active Directory B2B 协作 FAQ](https://go.microsoft.com/fwlink/p/?linkid=853020)。

> [!NOTE]
> Microsoft 团队始终采用 Azure Active Directory 外部设置，以允许或阻止来宾用户添加到租户。 有关详细信息，请参阅[Microsoft 团队中的授权来宾访问](Teams-dependencies.md)。
  
## <a name="guest-access-vs-external-access-federation"></a>来宾访问与外部访问 （联合身份验证）

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="review-guest-access-periodically"></a>定期查看来宾访问

在团队中，您可以添加 5 个来宾的每个许可用户。 由于此限制，或您希望用于保存您的租户最新，因为您应当查看来宾访问定期确定具有不再需要它们的访问权的用户。 Azure Active Directory (Azure AD) 可用于创建访问查看组成员或分配给应用程序的用户。 创建定期访问评论可以节省时间。 如果您需要定期查看用户有权访问应用程序用户或组的成员，您可以定义这些评论的频率。 

可以自己执行来宾访问回顾、 提出来宾若要查看其自己的成员身份，或提出的应用程序所有者或业务决策者执行访问评审。 使用 Azure 门户执行来宾访问评论。 有关详细信息，请参阅[管理使用 Azure AD 访问的来宾访问审阅](https://docs.microsoft.com/en-us/azure/active-directory/governance/manage-guest-access-with-access-reviews)。

###  <a name="prerequisites"></a>先决条件

访问评论所具有的 Azure AD，包括在 Microsoft 企业移动 + 安全性、 E5 Premium P2 版本。 有关详细信息，请参阅在[Azure Active Directory 版本](https://docs.microsoft.com/en-us/azure/active-directory/fundamentals/active-directory-whatis)中的"选择 edition"。 每个用户交互具有该功能通过创建回顾、 填写回顾，或确认他们的访问，都必须有许可证。 

团队不会限制您可以添加的来宾数。 但是，可以添加到您的租户的来宾总数取决于哪些您 AAD 许可允许。 有关详细信息，请参阅[Azure AD B2B 协作授权](https://docs.microsoft.com/en-us/azure/active-directory/b2b/licensing-guidance)。

## <a name="guest-access-latencies"></a>来宾访问延迟

在 Azure Active Directory 中设置来宾设置后， 更改在 Office 365 组织中生效需要 2 小时到 24 小时。 如果用户会看到"请与管理员联系"的邮件如果他们尝试将来宾添加到其工作组，，则可能的来宾功能尚未启用或设置尚未有效。

## <a name="more-information"></a>更多信息

有关使用 PowerShell 管理来宾访问信息，请参阅[使用 PowerShell 来控制对团队的来宾访问](guest-access-powershell.md)。


