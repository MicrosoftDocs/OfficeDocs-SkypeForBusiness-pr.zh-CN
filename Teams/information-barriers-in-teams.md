---
title: Microsoft Teams 中的信息屏障
author: chrfox
ms.author: chrfox
manager: laurawi
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
ms.reviewer: vikramju
f1.keywords:
- NOCSH
description: 本文介绍 Microsoft Teams 中的信息屏障及其如何影响 Teams。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 87e282673d1fabec5b751b0a3722515585e5e404
ms.sourcegitcommit: 360c78c66386fe00afe535681f51254eda886edf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/17/2021
ms.locfileid: "50837009"
---
# <a name="information-barriers-in-microsoft-teams"></a>Microsoft Teams 中的信息屏障

IB (信息) 是管理员可以配置的策略，以防止个人或组相互通信。 例如，如果一个部门正在处理不应与其他部门共享的信息，则 IB 非常有用。 当需要隔离或阻止组与该组外部的任何人通信时，数据库也很有用。

> [!NOTE]
> - 无法 (IB) 组的信息屏障。
> - 版本 1 不支持使用机器人、Azure Active Directory (Azure AD) 应用以及用于添加用户的一些 API。
> - 专用通道符合配置的 IB 策略。
> - 新增：有关对连接到 Teams 的 SharePoint 网站屏障的支持信息，请参阅与 [Microsoft Teams](https://docs.microsoft.com/sharepoint/information-barriers#segments-associated-with-microsoft-teams-sites)网站关联的段。

IB 策略还会阻止查找和发现。 如果您尝试与不应通信的某人进行通信，您将在人员选取器中找不到该用户。

## <a name="background"></a>背景

IB 的主要驱动因素来自金融服务行业。 金融行业监管局 ([FINRA]( https://www.finra.org)) 评审成员公司内部的数据库和利益冲突，并提供有关管理此类冲突的指导 (FINRA 2241，债务研究法规通知[15-31。](https://www.finra.org/sites/default/files/Regulatory-Notice-15-31_0.pdf)


但是，自引入 IB 以来，许多其他领域发现它们很有用。 其他常见方案包括：

- 教育：一个学校的学生无法查找其他学校学生的联系人详细信息。

- 法律：维护由一个客户的律师获取的数据的保密性，防止代表不同客户的同一家公司的律师访问这些数据。

- 政府：信息访问和控制在部门和组中受到限制。

- 专业服务：公司中的一组人员只能在客户参与期间通过来宾访问与客户或特定客户聊天。

例如，Enrico 属于银行段，Pradeep 属于财务顾问段。 Enrico 和 Pradeep 无法相互通信，因为组织的 IB 策略阻止这两个段之间的通信和协作。 但是，Enrico 和 Pradeep 可以在 HR 中与 Lee 通信。

![显示阻止段之间通信的信息屏障的示例](media/information-barriers-example.png)

## <a name="when-to-use-information-barriers"></a>何时使用信息屏障

你可能希望使用以下情况下的 IB：

- 必须禁止团队与特定其他团队通信或共享数据。
- 团队不得与团队外部的任何人通信或共享数据。

信息屏障策略评估服务确定通信是否符合 IB 策略。

## <a name="managing-information-barrier-policies"></a>管理信息屏障策略

IB 策略在 Microsoft 365 合规中心 (SCC) PowerShell cmdlet 进行管理。 有关详细信息，请参阅 [定义信息屏障的策略](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies)。

> [!IMPORTANT]
> 在设置或定义策略之前，必须在 Microsoft Teams 中启用范围目录搜索。 启用范围目录搜索后，请至少等待几个小时，然后设置或定义信息屏障的策略。 有关详细信息，请参阅定义 [信息屏障策略](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies#prerequisites)。

## <a name="information-barriers-administrator-role"></a>信息屏障管理员角色

IB 合规性管理角色负责管理 IB 策略。 有关此角色的信息，请参阅 [Microsoft 365 合规中心中的权限](https://docs.microsoft.com/office365/securitycompliance/permissions-in-the-security-and-compliance-center)。

## <a name="information-barrier-triggers"></a>信息屏障触发器

当发生以下 Teams 事件时，将激活 IB 策略：

- **将成员添加到团队** - 每当将用户添加到团队时，都必须根据其他团队成员的 IB 策略评估用户策略。 成功添加用户后，用户无需进一步检查即可在团队中执行所有功能。 如果用户的策略阻止他们添加到团队，该用户不会显示在搜索中。

    ![屏幕截图：搜索要添加到团队的新功能并查找任何匹配项](media/information-barriers-add-members.png)

- **请求新的** 聊天 - 每次用户请求与一个或多个其他用户进行新聊天时，会评估聊天以确保它未违反任何 IB 策略。 如果聊天违反 IB 策略，则聊天不会启动。

    下面是一对一聊天的示例。

    > [!div class="mx-imgBorder"]
    > ![显示 1：1 聊天中阻止通信的屏幕截图](media/information-barriers-one-one-chat.png)

    下面是群组聊天的示例。

    > [!div class="mx-imgBorder"]
    > ![显示群组聊天的屏幕截图](media/information-barriers-group-chat.png)

- **邀请用户** 加入会议 - 当邀请用户加入会议时，将针对适用于其他团队成员的 IB 策略评估适用于该用户的 IB 策略。 如果存在冲突，则不允许用户加入会议。

    ![显示用户被阻止参加会议的屏幕截图](media/information-barriers-meeting.png)

- **屏幕在两个或多个** 用户之间共享 - 当用户与其他用户共享屏幕时，必须评估共享以确保它不会违反其他用户的 IB 策略。 如果违反 IB 策略，则不允许屏幕共享。 
 
    下面是应用策略之前屏幕共享的示例。 

    > [!div class="mx-imgBorder"]
    > ![显示用户聊天的屏幕截图](media/ib-before-screen-share-policy.png)

    下面是应用策略后屏幕共享的示例。 屏幕共享和呼叫图标不可见。

    > [!div class="mx-imgBorder"]
    > ![显示具有阻止设置的用户字符的屏幕截图](media/ib-after-screen-share-policy.png)

- 用户在 **Teams** 中发起电话呼叫 - 每当用户通过 VOIP) 向其他用户或用户组发起语音呼叫 (时，将评估该呼叫以确保它不会违反其他团队成员的 IB 策略。 如果存在任何冲突，语音呼叫将被阻止。

- **Teams 中的来宾** - IB 策略也适用于 Teams 中的来宾。 如果需要在组织的全局地址列表中发现来宾，请参阅 [在 Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-guest-access-in-groups)组中管理来宾访问。 来宾可发现后，可以定义 [IB 策略](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies)。

## <a name="how-policy-changes-impact-existing-chats"></a>策略更改如何影响现有聊天

当 IB 策略管理员对策略进行更改，或者由于用户的个人资料 (（例如作业更改) ）而激活策略更改时，信息屏障策略评估服务会自动搜索成员，以确保他们在团队中的成员身份不会违反任何策略。

如果用户之间存在现有聊天或其他通信，并且设置了新策略或更改了现有策略，该服务将评估现有通信，以确保仍允许通信发生。 

- **1：1** 聊天 - 如果由于向阻止通信的策略的一个或两个用户应用了 (，不再允许两个用户之间的通信，) 进一步通信。 他们现有的聊天对话将变为只读。 

    下面是显示聊天可见的示例。

    > [!div class="mx-imgBorder"]
    > ![显示可用用户聊天的屏幕截图](media/ib-before-1-1chat-policy.png)

    以下示例显示聊天已禁用。

    > [!div class="mx-imgBorder"]
    > ![显示用户聊天已禁用的屏幕截图](media/ib-after-1-1chat-policy.png)

- 群组聊天 **-** 如果不再允许从一个用户到组的通信 (例如，由于用户更改了作业) ，则该用户及其参与违反策略的其他用户可能会从群组聊天中删除，并且不允许与组进一步通信。 用户仍可以看到旧对话，但无法查看或参与与组的任何新对话。 如果阻止通信的新策略或已更改策略应用于多个用户，则受该策略影响的用户可能会从群组聊天中删除。 他们仍可以看到旧对话。

  此示例中，Enrico 已移至组织内部的不同部门，已从群组聊天中删除。

  ![已从中删除用户的群组聊天的屏幕截图](media/information-barriers-user-changes-job.png)

  Enrico 无法再向群组聊天发送消息。

  ![由于用户已从组中删除，无法向群组聊天发送消息的屏幕截图](media/information-barriers-user-changes-job-2.png)

- **团队** - 已从组中删除的任何用户将从团队中删除，并且无法查看或参与现有或新对话。

## <a name="scenario-a-user-in-an-existing-chat-becomes-blocked"></a>场景：现有聊天中的用户被阻止

目前，如果 IB 策略阻止其他用户，则用户遇到以下情况：

- **"人员** "选项卡 - 用户在"人员"选项卡上看不到 **被阻止** 的用户。

- **人员选取** 器 - 被阻止的用户在人员选取器中不可见。

    ![Teams 提醒用户策略阻止显示其他用户信息的屏幕截图](media/information-barriers-people-picker.png)
    
- **"活动**"选项卡 - 如果用户访问被阻止用户的"活动"选项卡，则不显示任何帖子。 **("活动**"选项卡仅显示频道帖子，并且两个用户之间将不存在常见的) 

    下面是被阻止的活动选项卡视图的示例。

    > [!div class="mx-imgBorder"]
    > ![显示被阻止的活动选项卡的屏幕截图](media/ib-after-activity-tab-policy.png)


- **组织结构图** - 如果用户访问显示被阻止用户的组织结构图，则被阻止的用户不会显示在组织结构图上。 而是会显示一条错误消息。

- **人员** 卡片 - 如果用户参与对话后被阻止，其他用户将鼠标悬停在被阻止用户的姓名上时，会看到一条错误消息，而不是人员卡片。 卡上列出的操作 (例如通话和聊天) 将不可用。

- **建议的联系人** - 被阻止的用户不会显示在建议联系人列表中， (新用户显示的初始联系人列表) 。

- **聊天联系人** - 用户可以在聊天联系人列表上看到被阻止的用户，但被阻止的用户将被识别。 用户可以对被阻止的用户执行的唯一操作是删除他们。 用户还可以单击他们以查看其过去的对话。

- **呼叫联系人** - 用户可以在通话联系人列表上看到被阻止的用户，但被阻止的用户将被识别。 用户可以对阻止用户执行的唯一操作是删除他们。

    下面是通话联系人列表中被阻止的用户的示例。

    > [!div class="mx-imgBorder"]
    > ![显示用户用户聊天的屏幕截图](media/ib-before-chat-contacts-policy.png)

    下面是在通话内容列表中为用户禁用聊天的示例。

    > [!div class="mx-imgBorder"]
    > ![显示阻止用户聊天的屏幕截图](media/ib-after-chat-contacts-policy.png)

- **Skype 到 Teams 的** 迁移 - 从 Skype for Business 迁移到 Teams 期间，所有用户（即使是被 IB 策略阻止的用户）都将迁移到 Teams。 然后，如上所述处理这些用户。

## <a name="teams-policies-and-sharepoint-sites"></a>Teams 策略和 SharePoint 网站

创建团队后，将预配 SharePoint 网站并与 Microsoft Teams 关联，以体验文件。 默认情况下，此 SharePoint 网站和文件上不遵守 IB 策略。 若要启用 IB 策略，管理员已填写一个表单，请求在 SharePoint 和 OneDrive 上启用 IB 策略 (请参阅"信息屏障") 。 [](https://docs.microsoft.com/sharepoint/information-barriers#prerequisites) 如果在 SharePoint 和 OneDrive 中启用 IB 策略，则 IB 策略将在使用 Microsoft Teams 创建团队时预配的 SharePoint 网站上工作。

团队的 **SharePoint** 站点上的 IB 策略示例：在 Contoso Bank 公司中，用户"Sesha@contosobank.onmicrosoft.com"属于投资银行业务段，用户"Nikita@contosobank.onmicrosoft.com"属于顾问段。 组织的 IB 策略阻止这两个部分之间的通信和协作。
当用户 Sesha 为 Investment Banking 段创建团队时，支持它的团队和 SharePoint 网站将仅可供 Investment Banking 用户访问。 即使 Nikita 用户具有网站链接，她也无法访问该网站。

有关详细信息，请参阅对 [SharePoint 使用信息屏障](https://docs.microsoft.com/sharepoint/information-barriers#segments-associated-with-microsoft-teams-sites)。

## <a name="required-licenses-and-permissions"></a>所需的许可证和权限

有关许可证和权限（包括计划和定价）的详细信息，请参阅 Microsoft [365](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)安全与合规&指南。

## <a name="known-issues"></a>已知问题
- **用户无法** 加入临时会议：如果启用了 IB 策略，则如果会议花名册的大小大于会议出席限制，则不允许用户 [加入会议](limits-specifications-teams.md)。 根本原因是 IB 检查依赖于是否可以将用户添加到会议聊天名单，并且只有当用户可以添加到花名册时，才允许他们加入会议。 加入会议一次的用户会将该用户添加到名单;因此对于定期会议，花名册可以快速填满。 聊天名单达到 [会议出席限制后](limits-specifications-teams.md)，不允许向会议添加其他用户。 如果为租户启用了 IB 且会议聊天花名册已满，则新用户 (那些未加入花名册的用户) 不允许加入会议。 但是，如果未为租户启用 IB 且会议聊天名单已满，则新用户 (那些尚未加入花名册) 的用户可以加入会议，但他们在会议中看不到聊天选项。 短期解决方案是从会议聊天名单中删除非活动成员，为新用户提供空间。 但是，我们将在以后增加会议聊天花名册的大小。

- **用户无法加入频道会议**：如果启用了 IB 策略，则如果用户不是团队的成员，则不允许他们加入频道会议。 根本原因是 IB 检查依赖于是否可以将用户添加到会议聊天名单，并且只有当用户可以添加到花名册时，才允许他们加入会议。 频道会议中的聊天线程仅适用于团队/频道成员，非成员无法查看或访问聊天线程。 如果为租户启用了 IB，并且非团队成员尝试加入频道会议，则不允许该用户加入会议。 但是，如果未为租户启用 IB 且非团队成员尝试加入频道会议，则用户可以加入会议，但他们在会议中看不到聊天选项。

- **不会删除** 团队所有者：如果应用了新的 IB 策略，导致 Teams 频道中出现两个或多个冲突段，则具有团队所有者的段会获得更高的首选项，并且会删除其他段用户。 此外，目前不会删除团队所有者，即使他们与其他所有者/用户冲突。 租户管理员和其他通道所有者必须手动删除有冲突的所有者。 我们正在努力修复。

## <a name="more-information"></a>更多信息

- 若要详细了解数据库，请参阅 [信息屏障](https://docs.microsoft.com/office365/securitycompliance/information-barriers)。

- 若要设置 IB 策略，请参阅 [定义信息屏障的策略](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies)。

- 若要编辑或删除 IB 策略，请参阅编辑 ([或删除) 策略](https://docs.microsoft.com/microsoft-365/compliance/information-barriers-edit-segments-policies)。

## <a name="availability"></a>可用性
- 此功能在我们的公有云中可用;我们于 2021 年 1 月推出了 GCC 云中的信息屏障。
- 此功能在 GCCH 和 DOD 云中尚不可用。
