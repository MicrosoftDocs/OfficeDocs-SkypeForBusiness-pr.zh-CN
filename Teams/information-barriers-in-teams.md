---
title: Microsoft Teams中的信息障碍
description: 本文介绍如何在Microsoft Teams中支持信息屏障。
author: robmazz
ms.author: robmazz
manager: laurawi
ms.reviewer: smahadevan
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
ms.openlocfilehash: 38698179e2a3b4c6ca402190c98f89f329820d6e
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675404"
---
# <a name="information-barriers-in-microsoft-teams"></a>Microsoft Teams中的信息障碍

[Microsoft Purview信息屏障](/microsoft-365/compliance/information-barriers) (IB) 是管理员可以配置的策略，以防止个人或组相互通信。 例如，如果一个部门正在处理不应与其他部门共享的信息，则 IB 非常有用。 当需要隔离或阻止组与该组外部的任何人通信时，IB 也非常有用。 信息屏障支持Microsoft Teams中的共享通道。 根据共享类型，信息屏障策略可能会以某些方式限制共享。 有关共享通道和信息屏障行为的详细信息，请参阅 [信息屏障和共享通道](information-barriers-shared-channels.md)。

对于Microsoft Teams，信息屏障可以确定和防止以下类型的未经授权的协作：

- 将用户添加到团队或频道
- 用户对团队或频道内容的访问权限
- 用户对 1：1 和群聊的访问权限
- 用户对会议的访问权限
- 防止查找和发现，用户在人员选取器中将不可见。

>[!NOTE]
>- 无法跨租户创建信息屏障组。
>- 版本 1 不支持使用机器人、Azure Active Directory (Azure AD) 应用、用于发送活动源通知的 API 以及用于添加用户的某些 API。
>- 专用通道符合你配置的信息屏障策略。
>- 有关支持SharePoint连接到Teams的站点的屏障的信息，请参阅[与Microsoft Teams站点关联的段](/sharepoint/information-barriers#segments-associated-with-microsoft-teams-sites)。

## <a name="background"></a>背景

IB 的主要驱动力来自金融服务行业。 金融行业监管局 ([FINRA]( https://www.finra.org)) 审查成员公司内部的 IP 和利益冲突，并提供有关管理此类冲突的指导 (FINRA 2241， [债务研究监管通知 15-31](https://www.finra.org/sites/default/files/Regulatory-Notice-15-31_0.pdf)。

然而，自引入 IB 以来，许多其他领域都发现它们非常有用。 其他常见方案包括：

- **教育**：一所学校的学生无法查找其他学校学生的联系方式。
- **法律**：保持由一个客户的律师获取的数据的保密性，并防止代表其他客户的同一公司的律师访问该数据。
- **政府**：信息访问和控制在部门和组之间受到限制。
- **Professional服务**：公司中的一组人员只能在客户参与期间通过来宾访问与客户或特定客户聊天。

例如，Enrico 属于银行部门，Pradeep 属于财务顾问部门。 Enrico 和 Pradeep 无法相互通信，因为组织的 IB 策略阻止了这两个细分市场之间的通信和协作。 但是，Enrico 和 Pradeep 可以在 HR 中与 Lee 通信。

![显示阻止段之间通信的信息屏障的示例。](media/information-barriers-example.png)

## <a name="when-to-use-information-barriers"></a>何时使用信息屏障

你可能希望在以下情况下使用 IB：

- 必须阻止团队与特定的其他团队通信或共享数据。
- 团队不得与团队外部的任何人通信或共享数据。

信息屏障策略评估服务确定通信是否符合 IB 策略。

## <a name="managing-information-barrier-policies"></a>管理信息屏障策略

IB 策略使用 PowerShell cmdlet 在 Microsoft Purview 合规门户 (SCC) 中进行管理。 有关详细信息，请参阅 [定义信息屏障的策略](/office365/securitycompliance/information-barriers-policies)。

>[!IMPORTANT]
>在设置或定义策略之前，必须在Microsoft Teams中启用作用域内目录搜索。 启用作用域内目录搜索后，请等待至少几个小时，然后才能为信息屏障设置或定义策略。 有关详细信息，请参阅 [“定义信息屏障策略](/office365/securitycompliance/information-barriers-policies#prerequisites)”。

## <a name="information-barriers-administrator-role"></a>信息屏障管理员角色

IB 合规性管理角色负责管理 IB 策略。 有关此角色的详细信息，请参阅[Microsoft Purview 合规门户中的权限](/office365/securitycompliance/permissions-in-the-security-and-compliance-center)。

## <a name="information-barrier-triggers"></a>信息屏障触发器

发生以下Teams事件时激活 IB 策略：

- **成员将添加到团队**：每当向团队添加用户时，必须根据其他团队成员的 IB 策略评估用户的策略。 成功添加用户后，用户可以在团队中执行所有函数，而无需进一步检查。 如果用户的策略阻止他们添加到团队，则用户不会显示在搜索中。

    ![搜索要添加到团队的新成员并查找任何匹配项的屏幕截图。](media/information-barriers-add-members.png)

- **请求新的聊天**：每次用户请求与其他一个或多个用户进行新聊天时，都会评估聊天以确保它不违反任何 IB 策略。 如果对话违反了 IB 策略，则不会开始对话。

    下面是 1：1 聊天的示例。

    ![显示 1：1 聊天中通信受阻的屏幕截图。](media/information-barriers-one-one-chat.png)

    下面是群聊的示例。

    ![显示群组聊天的屏幕截图。](media/information-barriers-group-chat.png)

- **邀请用户加入会议**：当邀请用户加入会议时，将根据适用于其他团队成员的 IB 策略评估适用于用户的 IB 策略。 如果存在冲突，则不允许用户加入会议。

    ![显示用户被阻止参加会议的屏幕截图。](media/information-barriers-meeting.png)

- **屏幕在两个或更多用户之间共享**：当用户与其他用户共享屏幕时，必须评估共享以确保它不违反其他用户的 IB 策略。 如果违反 IB 策略，则不允许屏幕共享。

    下面是应用策略之前的屏幕共享示例。

    ![显示用户聊天的屏幕截图。](media/ib-before-screen-share-policy.png)

    下面是应用策略后屏幕共享的示例。 屏幕共享和调用图标不可见。

    ![显示包含阻止设置的用户字符的屏幕截图。](media/ib-after-screen-share-policy.png)

- **用户将电话呼叫置于Teams**：每当用户通过 VOIP) 向其他用户或用户组发起语音呼叫 (时，将评估该呼叫以确保它不会违反其他团队成员的 IB 策略。 如果有任何冲突，语音呼叫将被阻止。

- **Teams中的来宾**：IB 策略也适用于Teams中的来宾。 如果需要在组织的全局地址列表中发现来宾，请参阅[Microsoft 365 组中管理来宾访问权限](/microsoft-365/admin/create-groups/manage-guest-access-in-groups)。 可发现来宾后，可以 [定义 IB 策略](/office365/securitycompliance/information-barriers-policies)。

## <a name="how-policy-changes-impact-existing-chats"></a>策略更改如何影响现有聊天

当 IB 策略管理员对策略进行更改，或者由于更改用户配置文件 (（例如作业更改) ）而激活策略更改时，信息屏障策略评估服务会自动搜索成员，以确保其在团队中的成员身份不会违反任何策略。

如果用户之间存在现有聊天或其他通信，并且设置了新策略或更改了现有策略，则服务会评估现有通信，以确保仍允许通信发生。 

- **1：1 聊天**：如果不再允许两个用户之间的通信 (，因为应用程序到一个或两个用户的策略，阻止通信) ，进一步的通信将被阻止。 他们现有的聊天对话变为只读。

    下面的示例显示聊天可见。

    ![显示用户聊天可用的屏幕截图。](media/ib-before-1-1chat-policy.png)

    下面的示例显示聊天已禁用。

    ![显示已禁用用户聊天的屏幕截图。](media/ib-after-1-1chat-policy.png)

- **群聊**：例如，如果不再允许从一个用户到组的通信 (，因为用户更改了作业) ，则用户及其参与违反策略的其他用户可能会从群聊中删除，并且不允许与该组进行进一步通信。 用户仍可以看到旧对话，但无法查看或参与与组的任何新对话。 如果将阻止通信的新策略或更改的策略应用于多个用户，则可能会从群聊中删除受该策略影响的用户。 他们仍然可以看到旧对话。

  在此示例中，Enrico 移动到组织内的不同部门，并从群组聊天中删除。

  ![已从中删除用户的群组聊天的屏幕截图。](media/information-barriers-user-changes-job.png)

  Enrico 不能再向群聊发送消息。

  ![无法将消息发送到组聊天的屏幕截图，因为用户已从组中删除。](media/information-barriers-user-changes-job-2.png)

- **团队**：从组中删除的任何用户都将从团队中删除，并且无法查看或参与现有或新对话。

## <a name="scenario-a-user-in-an-existing-chat-becomes-blocked"></a>方案：现有聊天中的用户被阻止

目前，如果 IB 策略阻止另一个用户，则用户会遇到以下情况：

- **“人员”选项卡**：用户在“ **人员** ”选项卡上看不到被阻止的用户。

- **人员选取器**：被阻止的用户在人员选取器中不可见。

    ![Teams提醒用户策略阻止显示其他用户信息的屏幕截图。](media/information-barriers-people-picker.png)

- **活动选项卡**：如果用户访问被阻止用户的 **“活动”** 选项卡，则不会显示任何帖子。  (**“活动** ”选项卡仅显示频道帖子，并且两个用户之间没有常见的频道。) 

    下面是被阻止的活动选项卡视图的示例。

    ![显示被阻止的活动选项卡的屏幕截图。](media/ib-after-activity-tab-policy.png)

- **组织图**：如果用户访问显示被阻止用户的组织图表，则阻止的用户不会显示在组织图表上。 相反，将显示一条错误消息。

- **人员卡**：如果用户参与对话，并且用户后来被阻止，则当用户将鼠标悬停在被阻止的用户名上时，会看到错误消息而不是人员卡片。 卡片 (（例如呼叫和聊天) ）上列出的操作将不可用。

- **建议的联系人**：被阻止的用户不会出现在建议的联系人列表 (为新用户) 显示的初始联系人列表。

- **聊天联系人**：用户可以在聊天联系人列表中看到被阻止的用户，但会识别被阻止的用户。 用户可以对被阻止的用户执行的唯一操作是删除它们。 用户还可以选择它们来查看他们过去的对话。

- **呼叫联系人**：用户可以在呼叫联系人列表中看到被阻止的用户，但会识别被阻止的用户。 用户可以对阻止用户执行的唯一操作是删除它们。

    下面是呼叫联系人列表中被阻止的用户的示例。

    > [!div class="mx-imgBorder"]
    > ![显示用户用户聊天的屏幕截图。](media/ib-before-chat-contacts-policy.png)

    下面是调用内容列表中用户禁用聊天的示例。

    > [!div class="mx-imgBorder"]
    > ![显示用户被阻止聊天的屏幕截图。](media/ib-after-chat-contacts-policy.png)

- **Skype Teams迁移**：在从Skype for Business迁移到Teams期间，所有用户（甚至被 IB 策略阻止的用户）都将迁移到Teams。 然后按上述方式处理这些用户。

## <a name="teams-policies-and-sharepoint-sites"></a>Teams策略和SharePoint站点

创建团队时，会预配SharePoint站点，并与文件体验的Microsoft Teams相关联。 默认情况下，此SharePoint站点和文件上不遵守信息屏障策略。 若要在SharePoint和OneDrive中启用信息屏障，请按照SharePoint文章中的[“使用信息屏障](/sharepoint/information-barriers#enable-sharepoint-and-onedrive-information-barriers-in-your-organization)”中的指导和步骤操作。

## <a name="information--barrier-modes-and-teams"></a>信息屏障模式和Teams

信息屏障模式有助于加强可添加到团队或从团队中删除的人员。 将信息屏障与Teams配合使用时，支持以下 IB 模式：

- **打开**：此配置是启用信息屏障之前预配的所有现有组的默认 IB 模式。 在此模式下，没有适用的 IB 策略。
- **隐式**：启用信息屏障后预配团队时，此配置为默认 IB 模式。 隐式模式允许在组中添加所有兼容的用户。
- **所有者审查**：当你希望允许由所有者审查的不兼容段用户之间进行协作时，会在团队中设置此模式。 团队所有者可以根据其 IB 策略添加新成员。

默认情况下，在激活租户中的信息屏障策略之前创建的Teams会自动设置为 *“打开*”模式。 激活租户上的 IB 策略后，需要将现有团队的模式更新为 *隐式* ，以确保现有团队符合 IB。

将 [Set-UnifiedGroup](/powershell/module/exchange/set-unifiedgroup) cmdlet 与 *InformationBarrierMode* 参数结合使用，该参数对应于要用于段的模式。 *InformationBarrierMode* 参数的允许值列表为 *Open*、*Implicit* 和 *Owner Moderated*。

例如，若要为Microsoft 365组配置 *隐式* 模式，将使用以下 PowerShell 命令：

```powershell
Set-UnifiedGroup -InformationBarrierMode Implicit
```

若要为所有现有团队更新从“打开”到“隐式”的模式，请使用此 [PowerShell 脚本](information-barriers-mode-script.md)。

如果更改现有连接Teams组的 Open 模式配置以满足组织的合规性要求，则需要更新连接到Teams团队的关联SharePoint站点的 [IB 模式](/sharepoint/information-barriers#view-and-manage-ib-modes-as-an-administrator-with-sharepoint-powershell)。

## <a name="required-licenses-and-permissions"></a>所需的许可证和权限

有关许可证和权限、计划和定价的详细信息，请参阅[Microsoft 365有关安全&合规性的许可指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。

## <a name="known-issues"></a>已知问题

- **用户无法加入即席会议**：如果启用了 IB 策略，则如果会议名册的大小大于 [会议出席限制](limits-specifications-teams.md)，则不允许用户加入会议。 根本原因是，IB 检查取决于是否可以将用户添加到会议聊天名册中，并且只有当他们可以添加到名册上时，他们才被允许加入会议。 加入会议的用户一旦将该用户添加到名册;因此，对于定期会议，名单可以快速填写。 聊天名册达到 [会议出席限制](limits-specifications-teams.md)后，无法将其他用户添加到会议中。 如果为组织启用了 IB，并且聊天名册已满，则不允许新用户 (那些尚未加入) 名册上的用户加入会议。 但是，如果组织未启用 IB，并且会议聊天名册已满，则新用户 (那些尚未加入) 名册上的用户可以加入会议，尽管他们在会议中看不到聊天选项。 短期解决方案是从会议聊天名册中删除非活动成员，以便为新用户腾出空间。 但是，我们将在以后增加会议聊天名册的大小。
- **用户无法加入频道会议**：如果启用了 IB 策略，则如果用户不是团队成员，则不允许他们加入频道会议。 根本原因是，IB 检查取决于是否可以将用户添加到会议聊天名册中，并且只有当他们可以添加到名册上时，他们才被允许加入会议。 频道会议中的聊天线程仅适用于团队/频道成员，非成员无法查看或访问聊天线程。 如果为组织启用了 IB，并且非团队成员尝试加入频道会议，则不允许该用户加入会议。 但是，如果未为组织启用 IB，并且非团队成员尝试加入频道会议，则允许用户加入会议，但他们在会议中看不到聊天选项。
- **组织中允许的最大段数**：每个组织在配置 IB 策略时最多可以设置 100 个段。 可以配置的策略数没有限制。
- **IB 策略不适用于联合用户**：如果允许与外部组织联合，则这些组织的用户不会受到 IB 策略的限制。 如果组织的用户加入由外部联合用户组织的聊天或会议，则 IB 策略也不会限制组织用户之间的通信。

## <a name="more-information"></a>更多信息

- 若要了解有关 IB 的详细信息，请参阅 [信息屏障](/office365/securitycompliance/information-barriers)。
- 若要设置 IB 策略，请参阅[具有信息屏障的开始](/office365/securitycompliance/information-barriers-policies)。
- 若要编辑或删除 IB 策略，请参阅 [“管理信息屏障策略](/microsoft-365/compliance/information-barriers-edit-segments-policies)”。
- [信息屏障和共享通道](information-barriers-shared-channels.md)

## <a name="availability"></a>可用性

我们的公共、GCC、GCC - 高云和 DOD 云中提供了Teams中的信息屏障。
