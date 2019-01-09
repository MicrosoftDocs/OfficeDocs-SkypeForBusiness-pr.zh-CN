---
title: 向团队添加来宾
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
ms.date: 11/26/2018
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
search.appverid: MET150
ms.reviewer: sbhatta
description: 了解管理员可用于将新来宾用户添加到组织的工具，包括 Microsoft Teams 桌面客户端和 Web 客户端以及 Azure Active Directory B2B 协作门户。
appliesto:
- Microsoft Teams
ms.openlocfilehash: efd44fade33f611148dc2ab4ca9afb4040705123
ms.sourcegitcommit: 454ded73af5854d7b81a3b996702a6464b3fc313
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2019
ms.locfileid: "27772735"
---
<a name="add-a-guest-to-a-team"></a>向团队添加来宾
=====================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

具有业务或使用者的电子邮件帐户，如 Outlook、 Gmail，或其他任何人都可以作为来宾团队中参与。


作为管理员，你可以采用多种方式将新来宾用户添加到组织： 
- 身为团队所有者的全局管理员和团队所有者可以通过 Microsoft Teams 桌面客户端或 Web 客户端将来宾添加到团队。
- 通过 Azure Active Directory B2B 协作将来宾添加到贵组织。 利用 Azure Active Directory B2B 协作，全局管理员可以通过将不超过 2,000 行的逗号分隔值 (CSV) 文件上载到 B2B 协作门户来邀请和授权一组外部用户。 有关更多详细信息，请参阅 [Azure Active Directory B2B 协作](https://go.microsoft.com/fwlink/p/?linkid=826383)。



利用 Azure Active Directory B2B 协作，组织可以对 B2B 用户强制应用条件访问和多重身份验证 (MFA) 策略。 可以在租户、应用或单个用户级别强制应用这些策略，方式与对组织的全职员工和成员启用它们一样。 此类策略在资源组织上强制应用。 有关详细信息，请参阅 [B2B 协作用户的条件访问](https://go.microsoft.com/fwlink/?linkid=857454)。 无法阻止单个来宾用户。



来宾通过 Azure Active Directory B2B、 Office 365 组或 SharePoint Online 已添加的用户便准备好转。 Office 365 管理员或团队所有者可以向其各自团队添加那些来宾。 如果某个团队已使用某个 Office 365 组，向该组添加来宾后，该来宾将有权访问该团队。 通过 Office 365 组添加来宾不会为该来宾生成邀请电子邮件，因此该团队中的人员应通知该来宾。

> [!NOTE]
> 来宾受 [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) 和 [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) 服务限制约束。



你可以在 Azure Active Directory 或 Office 365 安全性&amp;和合规性中心中跟踪来宾添加情况。 在 Microsoft Teams 中添加来宾会进行审核并记录为 Azure AD 组管理活动“已向组添加成员”。 有关更多详细信息，请参阅[审核和报告 B2B 协作用户](https://go.microsoft.com/fwlink/p/?linkid=858884)和[在 Office 365 安全性&amp;和合规性中心中搜索审核日志](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c)。

## <a name="more-information"></a>更多信息

[在 Microsoft Teams 中授权来宾访问](teams-dependencies.md)</br>
[打开或关闭来宾访问中的 Microsoft 团队](set-up-guests.md)</br>
[使用 PowerShell 控制来宾对团队的访问](guest-access-powershell.md)