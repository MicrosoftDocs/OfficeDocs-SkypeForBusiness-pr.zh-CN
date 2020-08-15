---
title: 在 Microsoft Teams 中管理来宾访问
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
f1.keywords:
- NOCSH
description: 了解如何创建你的第一个团队和通道、板载早期使用者、监视使用情况和反馈以及获取资源以规划组织范围内推出。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: fb7fe026e59bcefb6dc7fb5d586f5458e6b358f9
ms.sourcegitcommit: 20258b691ffc559b1656fd1e57f67f5c3a9e29e1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/15/2020
ms.locfileid: "46761158"
---
# <a name="manage-guest-access-in-microsoft-teams"></a>在 Microsoft Teams 中管理来宾访问

**来宾** 是 microsoft 团队中的一种用户类型，其中包括所有 Microsoft 365 Business Standard、Office 365 企业版、Microsoft 365 Business Basic 和 Office 365 教育版订阅。 不需要额外的 Microsoft 365 许可证。 请阅读下面的有关 [来宾访问许可](#guest-access-licensing-limits) 的详细信息。

Teams 来宾访问是租户级别设置，默认情况下关闭。 有关如何启用来宾访问的详细信息，请参阅 [在团队中与来宾协作](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)。

打开来宾访问后，您可以使用在组织的 " [管理团队设置](enable-features-office-365.md) " 中介绍的控件配置来宾的设置，并在 [切换到新的 Microsoft 团队管理中心时管理团队](manage-teams-skypeforbusiness-admin-center.md)。     
    
IT 管理员可以在租户级别添加来宾、设置和管理来宾用户策略和权限，以及获取有关来宾用户活动的报告。 这些控件在团队管理中心中可用。 来宾用户内容和活动与 Microsoft 365 的其余部分具有相同的合规性和审核保护。

团队所有者可以邀请新来宾，并将现有的目录来宾用户添加到团队管理中心中的团队。 在 "**团队**  >  **管理团队**" 页面上标识来宾用户，并在 "**组织范围设置**  >  **来宾访问**" 页面上为来宾设置与频道相关的功能。 设置包括允许来宾创建、更新和删除频道，如下图所示。

> [!IMPORTANT]
> 您可能需要等待几个小时才能使所做的更改生效。 

![团队中的来宾权限设置](media/manage-guest-access-image1.png)
  
你可以使用 Azure Active Directory (Azure AD) 门户管理来宾及其对 Microsoft 365 和团队资源的访问权限。 团队来宾访问利用 Azure AD 企业到企业 (B2B) 协作功能，作为存储安全原则信息（如标识属性、成员身份和多重身份验证设置）的基础基础结构。 若要了解有关 Azure AD B2B 的详细信息，请参阅 [什么是 AZURE AD b2b 协作？](https://go.microsoft.com/fwlink/p/?linkid=853011) 和 [AZURE Active Directory b2b 协作常见问题解答](https://go.microsoft.com/fwlink/p/?linkid=853020)。

> [!NOTE]
> Microsoft 团队始终采用 Azure AD 外部设置，以允许或阻止来宾用户对租户的添加。 有关更多详细信息，请参阅 [在 Microsoft 团队中授权来宾访问](Teams-dependencies.md)。


## <a name="guest-access-licensing-limits"></a>来宾访问许可限制

Teams 不限制可添加的来宾数量。 但是，可添加到租户的来宾总数取决于 Azure AD 许可所允许的数量（通常为每个许可用户可添加 5 个来宾）。 有关详细信息，请参阅 [Azure AD B2B 协作授权](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance)。

由于这些许可限制 (并使你的租户保持最新) ，因此应定期查看来宾访问权限，以标识有权不再需要的用户。 你可以使用 Azure AD 为组成员或分配到应用程序的用户创建访问审核。 创建定期访问评论可节省您的时间。 如果需要定期查看有权访问应用程序或组成员的用户，您可以定义这些评论的频率。 

你可以自行执行来宾访问检查、要求来宾查看其自己的成员身份，或者要求应用程序所有者或业务决策人执行访问权审核。 使用 Azure 门户执行来宾访问评论。 有关详细信息，请参阅 [使用 AZURE AD 访问审核管理来宾访问](https://docs.microsoft.com/azure/active-directory/governance/manage-guest-access-with-access-reviews)。

## <a name="lag-time-for-guest-access-settings-to-take-effect"></a>使来宾访问设置生效的延隔时间

对于 Azure Active Directory 中的来宾访问设置，需要几个小时才能使更改在 Microsoft 365 中生效。 如果用户尝试向其团队中添加来宾时看到消息 "请联系你的管理员"，则很可能是来宾功能尚未打开，或者设置尚未生效。 有关设置来宾访问时出现问题的帮助，请阅读 [团队中的来宾访问的疑难解答](troubleshoot-guest-access.md)。
  
## <a name="external-access-federation-vs-guest-access"></a>外部访问（联合身份验证）与来宾访问

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="more-information"></a>更多信息

有关使用 PowerShell 管理来宾访问权限的信息，请参阅 [使用 powershell 控制对团队的来宾访问](guest-access-powershell.md)。


