---
title: Microsoft Teams 中的来宾访问
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: rafarhi
audience: admin
search.appverid: MET150
ms.localizationpriority: high
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.orgwidesettings.guestaccess.overview
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
appliesto:
- Microsoft Teams
description: 利用 Microsoft Teams 中的来宾访问功能，贵组织中的团队可以通过为贵组织外的人员授予访问团队和频道的权限来与其协作。
ms.openlocfilehash: 2064ca1fdd816f1948af1f0efcda3021a1c7d2cb
ms.sourcegitcommit: 279ab5236431961c5181e2c01a69e5aa4290d381
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2021
ms.locfileid: "60462336"
---
# <a name="guest-access-in-microsoft-teams"></a>Microsoft Teams 中的来宾访问

借助来宾访问，可以为组织外部的人员提供对团队、频道中的文档、资源、聊天和应用程序的访问，同时保持对公司数据的控制。请参阅 [使用 Microsoft 365 和 Microsoft Teams 设置安全协作](/microsoft-365/solutions/setup-secure-collaboration-with-teams)。

> [!NOTE]
> 如果只希望查找、通话、聊天以及安排与其他组织人员的会议，请使用[外部访问](manage-external-access.md)。

来宾是贵组织的员工、学生和成员以外的任何人。 他们在贵组织没有学校或工作帐户。 例如，来宾可以包括合作伙伴、供应商、提供商或顾问。 不属于你的组织的任何人都可作为来宾添加到 Teams 中。 这意味着具有企业帐户（即 Azure Active Directory 帐户）或消费者电子邮件帐户（带有 Outlook.com 和 Gmail.com 等）的任何人都可以在 Teams 中作为来宾进行参与，并且能够访问团队和频道体验。

Teams 中的来宾都可享受其余 Microsoft 365 产品中同样的合规性和审核保护，而且可以在 Azure AD 中进行管理。 来宾访问受到 Azure AD 和 Microsoft 365 或 Office 365 服务限制的约束。

来宾体验在设计上具有局限性。有关来宾在 Teams 中可以和不可执行的操作完整列表，请参阅 [团队成员与来宾功能比较](guest-experience.md#comparison-of-team-member-and-guest-capabilities)。

> [!IMPORTANT]
> 来宾用户遵循共存升级模式下的 Teams 组织范围内设置。此设置不能更改。

若要设置来宾访问，请参阅[在团队中与来宾协作](/microsoft-365/solutions/collaborate-as-team)。 

要将外部访问（联合身份验证）与来宾访问进行比较（并决定应使用哪个），请阅读[与 Teams 中其他组织的用户通信](communicate-with-users-from-other-organizations.md)。

## <a name="set-up-guest-access"></a>设置来宾访问

Teams 中的来宾访问需要在 Microsoft 365 中配置其他设置，包括 Azure AD、Microsoft 365 组和 SharePoint 中的设置。 如果你已准备好开始邀请来宾加入 Teams，请阅读以下内容之一：

- 若要为 Teams 配置来宾访问以供一般使用，请参阅[在团队中与来宾协作](/microsoft-365/solutions/collaborate-as-team)。
- 若要与使用 Azure Active Directory 的合作伙伴组织进行协作，并允许来宾自行注册以实现团队访问，请参阅[创建托管有来宾的 B2B 外联网](/microsoft-365/solutions/b2b-extranet)。

Teams 中的来宾访问是组织范围的设置，默认情况下处于打开状态。 可使用[敏感度标签](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)控制来宾对各个团队的访问。

> [!NOTE]
> 如果你是管理员，并且在 Microsoft Teams 中遇到来宾访问问题，请在下面选择 **运行测试**，这将在 Microsoft 365 管理中心弹出来宾访问诊断。 这些测试将检查你的配置，并快速建议后续步骤，以便为租户启用来宾访问。
>> [!div class="nextstepaction"]
>> [运行测试: 来宾访问](https://aka.ms/TeamsGuestAccessDiagDMC)

### <a name="turning-guest-access-off"></a>关闭来宾访问权限

如果在 Teams 中关闭来宾访问权限，现有来宾将失去对其团队的访问权限。 但不会从团队中删除他们。 他们仍然对团队成员可见，并且后者可以 @提及他们。 如果再次启用 Teams 来宾访问权限，他们将重新获得访问权限。

如果计划关闭来宾访问权限，可能需要建议团队所有者手动从其团队中删除来宾帐户。 虽然这些来宾无权访问，但其帐户在团队中可见可能会导致其他团队成员感到困惑。

## <a name="how-a-guest-becomes-a-member-of-a-team"></a>来宾如何成为团队成员

1. 团队所有者或 Microsoft 365 管理员[向团队添加来宾](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f)。
2. 来宾会收到一封来自团队所有者的欢迎电子邮件，其中内附团队信息及其现在作为成员应执行的操作。
3. 来宾接受邀请。
  在 Azure Active Directory 中拥有工作或学校帐户的来宾用户可以接受邀请并直接进行身份验证。 将向其他用户发送一次性密码，以验证其身份（需要[一次性密码验证](/azure/active-directory/external-identities/one-time-passcode)）。
4. 接受邀请后，来宾可[参与团队和频道](https://support.office.com/article/df38ae23-8f85-46d3-b071-cb11b9de5499)、接收和答复频道消息、[访问频道中的文件](https://support.office.com/article/access-files-in-channels-c593c78a-27c4-4661-a598-682baa30ca7e)，还能参与聊天、加入会议并协作处理文档等等。 

在 Teams 中，可清楚地识别来宾。 来宾用户的姓名包含 **（来宾）** 标签，而频道中有一个图标表示团队中存在来宾。 有关更多详细信息，请参阅[来宾体验介绍](guest-experience.md)。
  
来宾可以随时在 Teams 中离开团队。 有关详细信息，请参阅[如何离开团队？](https://support.office.com/article/leave-a-team-e481005d-3ec6-4694-b300-375472ba4076)

> [!NOTE]
> 退出团队不会从你的组织的租户中删除来宾帐户。 必须由 Microsoft 365 全局管理员或 Azure AD 管理员执行此操作。

## <a name="licensing-for-guest-access"></a>来宾访问的许可

所有 Microsoft 365 商业标准版、Microsoft 365 企业版和 Microsoft 365 教育版订阅均可与来宾访问功能一起使用。 无需额外的 Microsoft 365 许可证。 [Azure Active Directory for External Identities 的计费模式](/azure/active-directory/b2b/licensing-guidance)适用于 Microsoft 365 中的来宾。 只能邀请组织外部的人员作为来宾。

## <a name="guest-access-reviews"></a>来宾访问评审

可使用 Azure AD 为分配给应用程序的组成员或用户创建访问评审。 创建定期访问评审可以节省你的时间。 如果需要定期评审有权访问应用程序、团队或者属于组成员的用户，则可以定义这些评审的频率。 

你可以自行执行来宾访问评审，要求来宾评审其自身的成员身份，或要求应用程序所有者或业务决策者执行访问评审。 使用 Azure 门户执行来宾访问评审。 有关详细信息，请参阅[使用 Azure AD 访问评审管理来宾访问](/azure/active-directory/governance/manage-guest-access-with-access-reviews)。

## <a name="related-topics"></a>相关主题

[与组织外部人员进行协作](/microsoft-365/solutions/collaborate-with-people-outside-your-organization)

[阻止来自特定 Microsoft 365 组或 Microsoft Teams 团队的来宾用户](/microsoft-365/solutions/per-group-guest-access)

[创建安全的来宾共享环境](/microsoft-365/solutions/create-secure-guest-sharing-environment)

[联系商业版产品的支持人员 - 管理员帮助](/microsoft-365/admin/contact-support-for-business-products)

[配置具有三层保护的 Teams](/microsoft-365/solutions/configure-teams-three-tiers-protection)
