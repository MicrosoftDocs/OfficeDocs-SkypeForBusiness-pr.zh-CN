---
title: 向团队添加来宾
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
search.appverid: MET150
ms.reviewer: sbhatta
f1.keywords:
- NOCSH
localization_priority: Priority
description: 了解管理员可用于将新来宾用户添加到组织的工具，包括 Microsoft Teams 桌面客户端和 Web 客户端以及 Azure Active Directory B2B 协作门户。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5b25dc9c5b870b038b95f5df5821581f8c2fae79
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41826940"
---
<a name="add-a-guest-to-a-team"></a>向团队添加来宾
=====================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

拥有企业或消费者电子邮件帐户（如 Outlook、Gmail 或其他）的任何人都可以作为来宾参与 Teams。

作为管理员，你可以通过以下几种方式向组织添加新的来宾用户：
- 全局管理员或 Teams 管理员和团队所有者在 Teams 客户端或 Teams 管理中心内团队添加来宾。 若要了解详细信息，请参阅[向团队添加来宾](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f)。 如果尚未设置来宾访问权限，请按照[来宾访问清单](guest-access-checklist.md)中的步骤进行操作。

> [!NOTE] 
> 这在启用“**管理员和具有“来宾邀请者”角色的用户可以邀请**”的情况下不适用。 这是因为在 Teams 中不支持来宾邀请者角色。

- 通过 Azure Active Directory (Azure AD) B2B 协作将来宾添加到贵组织。 利用 AD B2B 协作，全局管理员可以通过将不超过 2,000 行的逗号分隔值 (CSV) 文件上载到 B2B 协作门户来邀请和授权一组外部用户。 有关更多详细信息，请参阅 [Azure Active Directory B2B 协作](https://go.microsoft.com/fwlink/p/?linkid=826383)。

利用 AD B2B 协作，组织可以对 B2B 用户强制应用条件访问和多重身份验证 (MFA) 策略。 可以在租户、应用或个人用户级别强制实施这些策略，与针对全职员工和组织成员启用这些策略的方式相同。 此类策略在资源组织上强制应用。 有关详细信息，请参阅 [B2B 协作用户的条件访问](https://go.microsoft.com/fwlink/?linkid=857454)。 无法阻止单个来宾用户。

你通过 Azure AD B2B、Office 365 组或 SharePoint Online 添加的来宾用户已准备就绪。 Office 365 管理员或团队所有者可以向其各自团队添加那些来宾。 如果某个团队已使用某个 Office 365 组，向该组添加来宾后，该来宾将有权访问该团队。 通过 Office 365 组添加来宾不会为该来宾生成邀请电子邮件，因此该团队中的人员应通知该来宾。

> [!NOTE]
> 来宾受 [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) 和 [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) 服务限制约束。

你可以在 Azure AD 或 Office 365 安全性&amp;和合规性中心中跟踪来宾添加情况。 在 Microsoft Teams 中添加来宾会进行审核并记录为 Azure AD 组管理活动“已向组添加成员”。 有关更多详细信息，请参阅[审核和报告 B2B 协作用户](https://go.microsoft.com/fwlink/p/?linkid=858884)和[在 Office 365 安全性&amp;和合规性中心中搜索审核日志](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c)。


## <a name="more-information"></a>更多信息

[在 Microsoft Teams 中授权来宾访问](teams-dependencies.md)</br>
[开启或关闭 Microsoft Teams 的来宾访问权](set-up-guests.md)</br>
[使用 PowerShell 控制来宾对团队的访问](guest-access-powershell.md)
