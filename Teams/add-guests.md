---
title: 向团队添加来宾
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
search.appverid: MET150
ms.reviewer: rafarhi
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
description: 管理员可以在 Microsoft Teams 桌面和 Web 客户端以及 Azure Active Directory B2B协作门户中了解如何向组织添加新来宾用户。
ms.openlocfilehash: e74819ba46af8a9f6bcf3b2198f78354bf7bfb79
ms.sourcegitcommit: 43e5a4aac11c20dd5a4c35b59695f309e1559e82
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/03/2020
ms.locfileid: "48346173"
---
# <a name="add-a-guest-to-a-team"></a>向团队添加来宾

拥有企业或消费者电子邮件帐户（如 Outlook、Gmail 或其他）的任何人都可以作为来宾参与 Teams。

作为管理员，你可以通过以下几种方式向组织添加新的来宾用户：

- 全局管理员或 Teams 管理员和团队所有者在 Teams 客户端或 Teams 管理中心内团队添加来宾。 若要了解详细信息，请参阅[向团队添加来宾](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f)。 如果尚未设置来宾访问权限，请按照“[在团队中与来宾协作](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)”的步骤进行操作。

- 通过 Azure Active Directory (Azure AD) B2B 协作将来宾添加到贵组织。 有关详细信息，请参阅 [快速入门：将来宾用户添加到 Azure 门户中的目录](https://docs.microsoft.com/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal)。

管理员还可以通过分配“来宾邀请者”角色来委派将来宾添加到组织中其他人的权限。 有关详细信息，请参阅[启用 B2B 外部协作并管理可邀请来宾的人员](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations)。

利用 AD B2B 协作，组织可以对 B2B 用户强制应用条件访问和多重身份验证 (MFA) 策略。 可以在租户、应用或个人用户级别强制实施这些策略，与针对全职员工和组织成员启用这些策略的方式相同。 此类策略在资源组织上强制应用。 有关详细信息，请参阅 [B2B 协作用户的条件访问](https://go.microsoft.com/fwlink/?linkid=857454)。 无法阻止单个来宾用户。

已通过 Azure AD B2B、Microsoft 365 组或 SharePoint 添加的来宾用户已准备好。 Microsoft 365 管理员或团队所有者可以将这些来宾添加到其各自的团队。 如果将来宾直接添加到与团队关联的 Microsoft 365 组，则来宾将获得对团队的访问权限，但 Microsoft 365 组不会为来宾生成邀请电子邮件，因此团队中的人员应通知来宾。

> [!NOTE]
> 来宾受 [Microsoft 365 或 Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) 和 [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) 服务限制约束。

你可以在 Azure AD 或 Microsoft 365 安全中心中跟踪来宾添加情况。 在 Microsoft Teams 中添加来宾会进行审核并记录为 Azure AD 组管理活动“已向组添加成员”。 有关更多详细信息，请参阅 [审核和报告 B2B 协作用户](https://docs.microsoft.com/azure/active-directory/external-identities/auditing-and-reporting) 和 [在合规中心中搜索审核日志](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)。


## <a name="related-topics"></a>相关主题

[在 Microsoft Teams 中授权来宾访问](teams-dependencies.md)

[开启或关闭 Microsoft Teams 的来宾访问权](set-up-guests.md)
