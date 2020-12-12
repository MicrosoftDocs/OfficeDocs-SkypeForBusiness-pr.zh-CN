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
- m365initiative-externalcollab
search.appverid: MET150
ms.reviewer: rafarhi
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
description: 管理员可以了解如何在 Microsoft Teams 桌面和 Web 客户端以及 Azure Active Directory B2B 协作门户中向组织添加新来宾。
ms.openlocfilehash: 7f75589c5252998fb0389c743b951c0fe88e613b
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662437"
---
# <a name="add-a-guest-to-a-team"></a>向团队添加来宾

拥有企业或消费者电子邮件帐户（如 Outlook、Gmail 或其他）的任何人都可以作为来宾参与 Teams。

作为管理员，可以通过多种方式向组织添加新来宾：

- 全局管理员或 Teams 管理员和团队所有者在 Teams 客户端或 Teams 管理中心内团队添加来宾。 若要了解详细信息，请参阅[向团队添加来宾](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f)。 如果尚未设置来宾访问权限，请按照“[在团队中与来宾协作](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)”的步骤进行操作。

- 通过 Azure Active Directory (Azure AD) B2B 协作将来宾添加到贵组织。 有关详细信息，请查看 [快速入门：在 Azure](https://docs.microsoft.com/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal)门户中将来宾添加到目录。

管理员还可以通过分配“来宾邀请者”角色来委派将来宾添加到组织中其他人的权限。 有关详细信息，请参阅[启用 B2B 外部协作并管理可邀请来宾的人员](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations)。

利用 AD B2B 协作，组织可以对 B2B 用户强制应用条件访问和多重身份验证 (MFA) 策略。 可以在租户、应用或个人用户级别强制实施这些策略，与针对全职员工和组织成员启用这些策略的方式相同。 此类策略在资源组织上强制应用。 有关详细信息，请参阅 [B2B 协作用户的条件访问](https://go.microsoft.com/fwlink/?linkid=857454)。 无法阻止单个来宾。

已通过 Azure AD B2B、Microsoft 365 组或 SharePoint 添加的来宾已准备就绪。 Microsoft 365 管理员或团队所有者可以将这些来宾添加到各自的团队。 如果直接向与团队关联的 Microsoft 365 组添加来宾，来宾将有权访问该团队，但 Microsoft 365 组不会生成给来宾的邀请电子邮件，因此团队中的人应通知来宾。

> [!NOTE]
> 来宾受 [Microsoft 365 或 Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) 和 [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) 服务限制约束。

你可以在 Azure AD 或 Microsoft 365 安全中心中跟踪来宾添加情况。 在 Microsoft Teams 中添加来宾会进行审核并记录为 Azure AD 组管理活动“已向组添加成员”。 有关详细信息，请参阅审核和报告 [B2B](https://docs.microsoft.com/azure/active-directory/external-identities/auditing-and-reporting) 协作用户，以及 [搜索审核日志中心中的用户](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)。


## <a name="related-topics"></a>相关主题

[在 Microsoft Teams 中授权来宾访问](teams-dependencies.md)

[开启或关闭 Microsoft Teams 的来宾访问权](set-up-guests.md)
