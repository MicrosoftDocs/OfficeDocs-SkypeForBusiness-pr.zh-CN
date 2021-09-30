---
title: 数据中的信息Microsoft Teams
description: 本文介绍数据中的信息屏障Microsoft Teams如何影响Teams。
author: robmazz
ms.author: robmazz
manager: laurawi
ms.reviewer: vikramju
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e829cb078ee334c36c69aa489c9dec6f3c5eaa10
ms.sourcegitcommit: 5eb5acd7910724f7f4a598ecc28b003e5bbe5ea5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/29/2021
ms.locfileid: "60007782"
---
# <a name="information-barriers-in-microsoft-teams"></a>数据中的信息Microsoft Teams

信息屏障 (数据库) 管理员可以配置策略，以防止个人或组相互通信。 例如，如果一个部门正在处理不应与其他部门共享的信息，则 IB 非常有用。 当需要隔离或阻止组与该组外部的任何人通信时，数据库也很有用。

例如Microsoft Teams，信息屏障可以确定并阻止以下类型的未经授权的协作：

- 将用户添加到团队或频道
- 用户访问团队或频道内容
- 用户访问 1：1 和群组聊天
- 用户对会议的访问权限
- 阻止查找和发现，用户不会显示在人员选取器中。

>[!NOTE]
>- 无法跨租户创建信息屏障组。
>- 版本 1 Azure Active Directory (不支持使用Azure Active Directory (Azure AD) 应用、用于发送活动源通知的 API 以及用于添加用户的一些 API。
>- 专用通道符合配置的信息屏障策略。
>- 有关对连接到SharePoint网站的支持屏障Teams，请参阅与网站关联的[Microsoft Teams段](/sharepoint/information-barriers#segments-associated-with-microsoft-teams-sites)。

## <a name="background"></a>背景

IB 的主要驱动因素来自金融服务行业。 金融行业监管局 ([FINRA]( https://www.finra.org)) 评审成员公司内部的数据库和利益冲突，并提供有关管理此类冲突的指导 (FINRA 2241，债务研究法规通知[15-31。](https://www.finra.org/sites/default/files/Regulatory-Notice-15-31_0.pdf)

但是，自引入数据库以来，许多其他领域发现它们很有用。 其他常见方案包括：

- **教育**：一个学校的学生无法查找其他学校学生的联系人详细信息。
- **法律**：维护由一个客户的律师获取的数据的保密性，并防止代表不同客户的同一家公司的律师访问这些数据。
- **政府**：信息访问和控制在部门和组中受到限制。
- **Professional服务**：公司中的一组人员只能在客户参与期间通过来宾访问与客户或特定客户聊天。

例如，Enrico 属于银行段，Pradeep 属于财务顾问段。 Enrico 和 Pradeep 无法相互通信，因为组织的 IB 策略阻止这两个段之间的通信和协作。 但是，Enrico 和 Pradeep 可以在 HR 中与 Lee 通信。

![显示阻止段之间通信的信息屏障的示例。](media/information-barriers-example.png)

## <a name="when-to-use-information-barriers"></a>何时使用信息屏障

你可能希望使用以下情况下的 IB：

- 必须禁止团队与特定其他团队通信或共享数据。
- 团队不得与团队外部的任何人通信或共享数据。

信息屏障策略评估服务确定通信是否符合 IB 策略。

## <a name="managing-information-barrier-policies"></a>管理信息屏障策略

IB 策略在标准合规Microsoft 365 SCC (SCC) PowerShell cmdlet 进行管理。 有关详细信息，请参阅 [定义信息屏障的策略](/office365/securitycompliance/information-barriers-policies)。

>[!IMPORTANT]
>在设置或定义策略之前，必须在目录中启用范围目录Microsoft Teams。 启用作用域目录搜索后，请至少等待几个小时，然后设置或定义信息屏障的策略。 有关详细信息，请参阅 [定义信息屏障策略](/office365/securitycompliance/information-barriers-policies#prerequisites)。

## <a name="information-barriers-administrator-role"></a>信息屏障管理员角色

IB 合规性管理角色负责管理 IB 策略。 有关此角色的信息，请参阅合规性中心[中Microsoft 365权限](/office365/securitycompliance/permissions-in-the-security-and-compliance-center)。

## <a name="information-barrier-triggers"></a>信息屏障触发器

发生以下事件时，将Teams IB 策略：

- **将成员添加到团队**：每当将用户添加到团队时，都必须根据其他团队成员的 IB 策略评估用户策略。 成功添加用户后，用户无需进一步检查即可在团队中执行所有功能。 如果用户的策略阻止他们添加到团队，该用户不会显示在搜索中。

    ![屏幕截图：搜索要添加到团队的新功能，并查找任何匹配项。](media/information-barriers-add-members.png)

- **请求新的聊天**：每次用户请求与一个或多个其他用户进行新聊天时，会评估聊天以确保它未违反任何 IB 策略。 如果聊天违反 IB 策略，则聊天不会启动。

    下面是一对一聊天的示例。

    ![显示 1：1 聊天中阻止通信的屏幕截图。](media/information-barriers-one-one-chat.png)

    下面是群组聊天的示例。

    ![显示群组聊天的屏幕截图。](media/information-barriers-group-chat.png)

- **邀请用户** 加入会议：当邀请用户加入会议时，将针对适用于其他团队成员的 IB 策略评估适用于该用户的 IB 策略。 如果存在冲突，则不允许用户加入会议。

    ![显示用户被阻止参加会议的屏幕截图。](media/information-barriers-meeting.png)

- **屏幕在两个或多个** 用户之间共享：当用户与其他用户共享屏幕时，必须评估共享以确保它不会违反其他用户的 IB 策略。 如果违反 IB 策略，则不允许屏幕共享。

    下面是应用策略之前屏幕共享的示例。

    ![显示用户聊天的屏幕截图。](media/ib-before-screen-share-policy.png)

    下面是应用策略后屏幕共享的示例。 屏幕共享和呼叫图标不可见。

    ![显示具有阻止设置的用户字符的屏幕截图。](media/ib-after-screen-share-policy.png)

- 用户在 **Teams** 中发起电话呼叫：每当用户通过 VOIP) 向其他用户或用户组发起语音呼叫 (时，都会评估该呼叫，以确保它不会违反其他团队成员的 IB 策略。 如果存在任何冲突，语音呼叫将被阻止。

- **来宾Teams：IB** 策略也适用于Teams中的来宾。 如果需要在组织的全局地址列表中发现来宾，请参阅管理组Microsoft 365[访问](/microsoft-365/admin/create-groups/manage-guest-access-in-groups)。 来宾可发现后，可以定义 [IB 策略](/office365/securitycompliance/information-barriers-policies)。

## <a name="how-policy-changes-impact-existing-chats"></a>策略更改如何影响现有聊天

当 IB 策略管理员对策略进行更改，或者由于用户的个人资料 (（例如作业更改) ）而激活策略更改时，信息屏障策略评估服务会自动搜索成员，以确保他们在团队中的成员身份不会违反任何策略。

如果用户之间存在现有聊天或其他通信，并且设置了新策略或更改了现有策略，该服务将评估现有通信，以确保仍允许通信发生。 

- **1：1** 聊天：如果由于向阻止通信的策略的一个或多个用户 (两个用户而不再允许两个用户之间的通信，则进一) 通信将被阻止。 他们现有的聊天对话将变为只读。

    下面是显示聊天可见的示例。

    ![显示可用用户聊天的屏幕截图。](media/ib-before-1-1chat-policy.png)

    以下示例显示聊天已禁用。

    ![显示用户聊天已禁用的屏幕截图。](media/ib-after-1-1chat-policy.png)

- 群组聊天：如果不再允许从一个用户到组的通信 (例如，由于用户更改了作业) ，则用户（及其参与违反策略的其他用户）可能会从群组聊天中删除，并且不允许与组进一步通信。 用户仍可以看到旧对话，但无法查看或参与与组的任何新对话。 如果阻止通信的新策略或已更改策略应用于多个用户，则受该策略影响的用户可能会从群组聊天中删除。 他们仍可以看到旧对话。

  此示例中，Enrico 已移至组织内部的不同部门，已从群组聊天中删除。

  ![已从中删除用户的群组聊天的屏幕截图。](media/information-barriers-user-changes-job.png)

  Enrico 无法再向群组聊天发送消息。

  ![由于用户已从组中删除，无法向群组聊天发送消息的屏幕截图。](media/information-barriers-user-changes-job-2.png)

- **团队**：已从组中删除的任何用户将从团队中删除，并且无法查看或参与现有或新对话。

## <a name="scenario-a-user-in-an-existing-chat-becomes-blocked"></a>场景：现有聊天中的用户被阻止

目前，如果 IB 策略阻止其他用户，则用户遇到以下情况：

- **"人员**"选项卡：用户在"人员"选项卡上看不到 **被阻止** 的用户。

- **人员选取** 器：被阻止的用户在人员选取器中不可见。

    ![屏幕截图Teams警告用户策略阻止显示其他用户的信息。](media/information-barriers-people-picker.png)

- **"活动**"选项卡：如果用户访问被阻止用户的"活动"选项卡，则不显示任何帖子。 **("活动**"选项卡仅显示频道帖子，并且两个用户之间将不存在常见的) 

    下面是被阻止的活动选项卡视图的示例。

    ![显示被阻止的活动选项卡的屏幕截图。](media/ib-after-activity-tab-policy.png)

- **组织结构图**：如果用户访问显示被阻止用户的组织结构图，则被阻止的用户不会显示在组织结构图上。 而是会显示一条错误消息。

- **人员** 卡片：如果用户参与对话后被阻止，其他用户将鼠标悬停在被阻止用户的姓名上时，会看到一条错误消息，而不是人员卡片。 卡上列出的操作 (例如通话和聊天) 将不可用。

- **建议的联系人**：被阻止的用户不会显示在建议联系人列表中， (新用户显示的初始联系人列表) 。

- **聊天联系人**：用户可以在聊天联系人列表上看到被阻止的用户，但被阻止的用户将被识别。 用户可以对被阻止的用户执行的唯一操作是删除他们。 用户还可以选择他们以查看其过去的对话。

- **呼叫联系人**：用户可以在通话联系人列表上看到被阻止的用户，但被阻止的用户将被识别。 用户可以对阻止用户执行的唯一操作是删除他们。

    下面是通话联系人列表中被阻止的用户的示例。

    > [!div class="mx-imgBorder"]
    > ![显示用户用户聊天的屏幕截图。](media/ib-before-chat-contacts-policy.png)

    下面是在通话内容列表中为用户禁用聊天的示例。

    > [!div class="mx-imgBorder"]
    > ![显示阻止聊天的用户的屏幕截图。](media/ib-after-chat-contacts-policy.png)

- **Skype** 迁移Teams：从 Skype for Business 迁移到 Teams 期间，所有用户（即使是被 IB 策略阻止的用户）都将迁移到 Teams。 然后，如上所述处理这些用户。

## <a name="teams-policies-and-sharepoint-sites"></a>Teams策略和SharePoint网站

创建团队时，将预配SharePoint网站，并关联Microsoft Teams体验。 默认情况下，此信息屏障策略不SharePoint网站和文件。 若要在 SharePoint 和 OneDrive 中启用信息屏障，请遵循将信息屏障与 SharePoint[一文的指导和](/sharepoint/information-barriers#enable-sharepoint-and-onedrive-information-barriers-in-your-organization)步骤。

## <a name="information--barrier-modes-and-teams"></a>信息屏障模式Teams

信息屏障模式有助于增强可添加到团队或从团队中删除哪些人。 将信息屏障与 Teams时，支持以下 IB 模式：

- **打开**：此配置是启用信息屏障之前预配的所有现有组的默认 IB 模式。 在此模式下，没有适用的 IB 策略。
- **隐式**：启用信息屏障后预配团队时，此配置是默认的 IB 模式。 隐式模式允许添加组内的所有兼容用户。

Microsoft 365默认情况下，激活信息屏障策略之前创建的组会自动设置为 *"打开* 模式"。 在租户上激活 IB 策略后，需要更新模式，重新评估组和网站，导致不合规的用户自动从这些组和网站中删除。 如果需要更改现有已连接Teams 的组的开放模式配置以满足组织的合规性要求，则需要更新连接到 Teams 团队的 SharePoint 网站的[IB](/sharepoint/information-barriers.md#view-and-manage-IB-mode-as-an-administrator-with-SharePoint-PowerShell)模式。

将 *Set-UnifiedGroup* cmdlet 与 *InformationBarrierMode* 参数一起使用，该参数对应于要用于段的模式。 *InformationBarrierMode* 参数的允许值列表为 *Open 和* *Implicit。*

例如，若要为组配置隐式Microsoft 365，请使用以下 PowerShell 命令：

```powershell
Set-UnifiedGroup -InformationBarrierMode Implicit
```

>[!NOTE]
>如果全局管理员将连接到 Microsoft Teams 隐式的现有 Microsoft 365 组的 IB 模式更新为 *隐式*，请确保将已连接Teams的 IB 模式更新为 *隐式*。 有关详细信息，请参阅 [信息屏障](/microsoft-365/compliance-information-barriers.md#information-barriers-modes-preview)入门 ]

有关用户如何自动从组中删除的详细信息，请参阅信息屏障合规性助手 ([预览版) ](/sharepoint/information-barriers-compliance-assistant) 文章。

## <a name="required-licenses-and-permissions"></a>所需的许可证和权限

有关许可证和权限、计划和定价的详细信息，请参阅安全Microsoft 365安全许可&[指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。

## <a name="known-issues"></a>已知问题

- **用户无法** 加入临时会议：如果启用了 IB 策略，则如果会议花名册的大小大于会议出席限制，则不允许用户 [加入会议](limits-specifications-teams.md)。 根本原因是 IB 检查依赖于是否可以将用户添加到会议聊天名单，并且只有当用户可以添加到花名册时，才允许他们加入会议。 加入会议一次的用户会将该用户添加到名单;因此对于定期会议，花名册可以快速填满。 聊天名单达到会议 [出席限制后](limits-specifications-teams.md)，无法将其他用户添加到会议。 如果为组织启用了 IB 并且会议聊天花名册已满，则新用户 (那些未加入花名册的用户) 不允许加入会议。 但是，如果未为组织启用 IB 且会议聊天名单已满，则新用户 (那些尚未加入花名册) 的用户可以加入会议，但他们在会议中看不到聊天选项。 短期解决方案是从会议聊天名单中删除非活动成员，为新用户提供空间。 但是，我们将在以后增加会议聊天花名册的大小。
- **用户无法加入频道会议**：如果启用了 IB 策略，则如果用户不是团队的成员，则不允许他们加入频道会议。 根本原因是 IB 检查依赖于是否可以将用户添加到会议聊天名单，并且只有当用户可以添加到花名册时，才允许他们加入会议。 频道会议中的聊天线程仅适用于团队/频道成员，非成员无法查看或访问聊天线程。 如果为组织启用了 IB，并且非团队成员尝试加入频道会议，则不允许该用户加入会议。 但是，如果未为组织启用 IB，并且非团队成员尝试加入频道会议，则用户可以加入会议，但他们在会议中看不到聊天选项。
- **组织允许的最大段数**：每个组织在配置 IB 策略时最多可以设置 100 个段。 可以配置的策略数量没有限制。
- **IB 策略对** 联合用户不起作用：如果允许与外部组织联合，则这些组织的用户不受 IB 策略的限制。 如果组织的用户加入由外部联合用户组织的聊天或会议，则 IB 策略也不会限制组织用户之间的通信。

## <a name="more-information"></a>更多信息

- 若要详细了解数据库，请参阅 [信息屏障](/office365/securitycompliance/information-barriers)。
- 若要设置 IB 策略，请参阅 [信息屏障入门](/office365/securitycompliance/information-barriers-policies)。
- 若要编辑或删除 IB 策略，请参阅 [管理信息屏障策略](/microsoft-365/compliance/information-barriers-edit-segments-policies)。

## <a name="availability"></a>可用性

- 此功能在我们的公有云中可用;2021 年 1 月，我们在云中推出了GCC屏障。
- 此功能尚未在云 - 高GCC DOD 云中提供。
