---
title: 面向 EDU 管理员的 Microsoft Teams 策略和策略包
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.reviewer: prkuch
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
- Teams_ITAdmin_RemoteWorkers
- remotework
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.policypackages.overview
localization_priority: Priority
search.appverid: MET150
description: 了解教育或 EDU 设置中的策略，以及如何在 Microsoft Teams 中使用和管理策略包。
ms.openlocfilehash: 10b87a804523758df69a68ff9c5812a6ea5b448c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117790"
---
# <a name="teams-policies-and-policy-packages-for-education"></a>用于教育的 Teams 策略和策略包

[!INCLUDE [policy-wizard-edu](includes/policy-wizard-edu.md)]

> [!NOTE]
> 有关 Microsoft Teams 中策略的更多信息，请查看[向 Microsoft Teams 中的用户分配策略](assign-policies.md)。

## <a name="admins-getting-started-with-microsoft-teams-policy-management"></a>管理员：Microsoft Teams 策略管理入门

Microsoft Teams 让用户能够执行诸如参加在线会议或实时事件、聊天、拨打电话和使用应用之类的事情。 设置恰当的 Microsoft Teams 管理员策略是为学生营造安全的 Teams 学习环境的关键一步。 作为管理员，你可以使用策略来控制你的教育机构中的用户可以使用的 Teams 功能。 在大多数情况下，必须为学生和教师调整策略，保持安全的学习环境。  

下面是你将在 Microsoft Teams 中找到的主要策略区域列表。 若要详细了解每个区域中的策略及其控制的功能，请使用下面的链接：

- [会议](meeting-policies-in-teams.md)
- [实时事件](teams-live-events/configure-teams-live-events.md)
- [通话](teams-calling-policy.md) 
- [消息传递](messaging-policies-in-teams.md)
- [Teams](teams-policies.md)
- [应用权限](teams-app-permission-policies.md)

:::image type="content" source="media/edu-admin-center-users.png" alt-text="应用了策略的用户的屏幕截图。":::

使用管理员凭据登录后，可在 [ Microsoft Teams 管理中心](https://admin.teams.microsoft.com)中管理所有 Teams 策略。

### <a name="where-to-find-microsoft-teams-policies"></a>在哪里可以找到 Microsoft Teams 策略

登录 Teams 管理中心后，可单击 Teams 管理中心左侧导航中的策略选项，转到需要管理的任何 Teams 区域的策略设置。 我们提供了消息传递策略位置的屏幕截图。

:::image type="content" source="media/edu-messaging-policies.png" alt-text="Teams 管理中心中的消息策略位置。":::

### <a name="how-to-create-and-update-a-policy-definition"></a>如何创建和更新策略定义

在向用户分配策略之前，你需要首先通过 Teams 为每个功能区域添加和创建策略定义。

> [!NOTE]
> 建议为学生和教师设置不同的策略定义。

默认情况下，将为每个新用户（学生或教师）分配每个功能区域的全局（组织范围默认）策略定义。 建议对最严格的策略集定义使用全局（组织范围内的默认设置）。 在大多数情况下，更严格的策略集更适合学生。 通过这种方式使用全局（组织范围内的默认设置）策略定义，可确保新用户添加到租户时严格限制。 若要遵守本指南，建议你按照以下步骤进行操作：

1. 为每个团队创建一个自定义策略定义功能区域，其中包含适合你的教育版需求的策略值（否则教师的访问权限将与全局（组织范围内的默认设置）策略定义中定义的学生的限制相同）。

1. 向教师分配这些新的自定义策略定义。

1. 使用适用于学生的值编辑每个功能区域的全局（组织范围内的默认设置）策略定义。

1. 只要全局（组织范围内的默认设置）策略定义未分配其他策略定义，它们就会应用到你的学生。


若要创建或编辑策略定义，请转到要使用的策略功能区域（例如，消息传递策略）。 选择“**添加**”，创建新的自定义策略定义。 若要更改现有策略定义，请选择“**编辑**”。

:::image type="content" source="media/edu-messaging-policies-add-closeup.png" alt-text="消息传递策略部分的特写，可看到“添加”按钮。":::

无论选择添加还是编辑策略定义，你都将进入一个视图，其中列出了与此策略区域相关的所有策略选项。 使用此列表可选择要在策略定义中设置的值。

![包含与所选策略区域相关的策略选项的页面。](media/edu-global-policy-definition.png)

> [!IMPORTANT]
> 离开页面前，请不要忘记选择“**保存**”。

### <a name="assigning-policy-definitions"></a>分配策略定义 
有多种方法可用于向用户分配策略定义。 每个方法都有其自己的优缺点，具体取决于你的机构的独特需求。  

在大多数情况下，我们建议使用组策略分配为用户分配策略。 通过此方法，可实现更快、更无缝的策略应用。  将用户添加到已向其分配策略定义的组时，新用户将自动继承该组的策略。  这样，当向环境添加大量的用户并将其删除时（例如，学校学期的开始和结束），就可以更轻松地管理策略。  

对于大型组织，我们还建议批处理策略分配，该策略针对需要向大型用户组分配策略的情况进行量身定制。 若要了解有关这些应用程序方法的详细信息，请参阅[向学校](batch-group-policy-assignment-edu.md)中的大用户组分配策略。

如果机构较小或需要更新单个学生或教师的策略设置，请按照以下说明进行操作。  

> [!IMPORTANT]
> 在单个用户级别给定的策略分配将覆盖分配给该用户的任何组策略。 在希望覆盖组策略设置时，请确保仅使用单独的策略分配。 

#### <a name="how-to-assign-a-policy-definition-to-a-user"></a>如何向用户分配策略定义

> [!NOTE]
> 分配策略定义时，可能需要一段时间才能传播给所有用户和客户端。 首次在 Azure/M365 中创建用户帐户时，以及每当有新学生加入教育机构时，你都可能需要执行此操作。


创建或更新策略定义后，可通过在策略页面中选择“**管理用户**”，搜索所需的用户，然后应用策略，将其分配给用户。

![消息传递策略页面顶部右侧的“管理用户”面板。](media/edu-manage-users-pane.png)

你还可以通过导航到 **“用户”**，选择要为其更新策略的用户，选择 **“策略”**，然后选择 **“编辑”**，将策略分配给用户。 在此处，可以选择对于每个功能区域要分配给用户的策略定义。

![“编辑用户策略”窗格，位于“已分配的策略”页面右上方。](media/edu-edit-user-policies-pane.png)

### <a name="policy-packages-in-microsoft-teams"></a>Microsoft Teams 中的策略包
> [!NOTE]
> 有关详细信息，可查看[管理 Microsoft Teams 中的策略包](manage-policy-packages.md)，了解有关向单个用户分配包、向多达 5000 个用户批量分配包以及管理和更新链接到每个包的策略的分步指导。

Teams 中的策略包将收集预定义策略和上述策略设置，并将其分配给机构中具有相似角色的用户。 策略包可简化并有助于提供一致的策略管理。 通常，为每个用户分配一个策略包，然后根据需要重新定义每个包中的策略，以满足该用户组的需要。 更新包中的设置时，分配给该包的所有用户都将作为批量更新进行更改。

一般情况下，教育机构的许多用户有其独特的需求，部分取决于学生的年龄和成熟度。 例如，你可能想要授予教师和教职员工对 Microsoft Teams 的完全访问权限，但想要对学生限制 Microsoft Teams 功能，以便鼓励营造安全且专注的学习环境。 可使用策略包根据教育机构社区中不同群体的需求来定制设置。

> [!IMPORTANT] 
> 我们主要建议为学生使用全局（组织范围内的默认设置）策略定义，而不是策略包。 这可确保组织中的新用户始终具有适用于学生的最严格的策略集。 如果此建议不符合机构的需求，下面的一个学生策略包可能是一个不错的选择。 

就像本文前面的策略列表一样，策略包预定义以下各项的策略：

- 会议
- 实时事件
- 通话
- 消息传递
- 应用权限

Microsoft Teams 当前包含以下策略包：

|Microsoft Teams 管理中心中列出的包名称 |最适合用于  |说明 |
|:--- |:--- |:--- |
|**Education_Teacher**| 教师和教职员工| 使用这组策略和策略设置可以为组织中的教师和教职员工授予通过 Microsoft Teams 进行聊天、通话和会议的完全访问权限。 |
|**Education_PrimaryStudent**| 小学适龄学生  | 你所在机构内年幼的小学适龄学生可能需要 Microsoft Teams 中的更多限制。 使用这组策略和策略设置可限制会议创建和管理、聊天管理和私人通话等功能。 |
|**Education_SecondaryStudent**| 中学学龄学生 | 你所在机构内的中学适龄学生可能需要 Microsoft Teams 中的更多限制。 使用这组策略和策略设置可限制会议创建和管理、聊天管理和私人通话等功能。 |
|**Education_HigherEducationStudent**| 高等教育学生 | 你所在机构内的高等教育学生所需的限制可能比年幼学生要少，但是可能建议采用某些限制。 可以使用这组策略和策略设置来授予对组织内的聊天、通话和会议的访问权限，但限制学生与外部参与者一起使用 Microsoft Teams 的方式。 |
|**Education_PrimaryTeacher_RemoteLearning**| 教师和教职员工 | 创建一组适用于主要教师的策略，在远程学习中最大化学生的安全和协作。 |
|**Education_PrimaryStudent_RemoteLearning**| 小学适龄学生| 创建一组适用于主要学生的策略，在远程学习中最大化学生的安全和协作。
|||

:::image type="content" source="media/edu-policy-packages-list.png" alt-text="策略包页面，其中包含可供选择的策略包列表。":::

将为每个单独的策略提供策略包的名称，以便你识别链接到该策略包的策略。 例如，当你将 Education_Teacher 策略包分配给教育机构中的教师时，将为包中的每个策略创建一个名为 Education_Teacher 的策略。

![Education_Teacher 策略包的屏幕截图](media/policy-packages-education_teacher.png)

> [!NOTE]
> 如果确定教师和管理支持人员需要不同的策略，则可以重新调整现有包：识别当前不使用的包，并更改设置以适合该组。 你可能需要自己记录哪个小组拥有哪个包，但这是重新调整包的唯一障碍。

## <a name="manage-policy-packages"></a>管理策略包

### <a name="view"></a>查看

在分配包前查看策略包中每个策略的设置。 在 Microsoft Teams 管理中心的左侧导航栏中，依次选择 **策略包**、程序包名称，然后选择策略名称。

确定预定义值是否适合你的组织，或是否需要根据组织的需求对其进行自定义，使其更具限制性或更宽松。

### <a name="customize"></a>自定义

根据需要自定义策略包中的策略设置，满足组织的需求。 对策略设置所做的任何更改都将自动应用到已分配了该包的用户。 若要编辑策略包中的策略设置，请在 Microsoft Teams 管理中心中，依次选择策略包、要编辑的策略的名称，然后选择 **编辑**。

请记住，在分配策略包之后，你还可以更改包中的策略设置。 若要了解详细信息，请参阅[自定义策略包](manage-policy-packages.md#customize-policies-in-a-policy-package)中的策略。 

### <a name="assign"></a>分配

将策略包分配给用户。 如果用户已分配策略，稍后又分配了另一个策略，则最近分配的优先级将会更高。

#### <a name="assign-a-policy-package-to-one-or-several-users"></a>向一个或多个用户分配策略包

若要将策略包分配给一个或多个用户，请在 Microsoft Teams 管理中心的左侧导航中，转到 **策略包**，然后选择 **管理用户**。  

![有关如何在管理中心分配策略包的屏幕截图](media/policy-packages-healthcare-assign.png)

若要了解详细信息，请参阅[分配策略包](manage-policy-packages.md#assign-a-policy-package)。

如果用户已分配策略，稍后又分配了另一个策略，则最近分配的优先级将会更高。

#### <a name="assign-a-policy-package-to-a-group"></a>将策略包分配给组。

**此功能在私有预览版中**

通过将策略包分配到组，可将多个策略分配给一组用户，例如安全组或通讯组列表。 根据优先级规则，将策略分配传播到组中的成员。 将成员添加到组或从组中删除成员时，将相应更新其继承的策略分配。 建议将此方法用于最多 50,000 个用户的组，但也可使用更大的组。

若要了解详细信息，请参阅[将策略包分配到组](assign-policies.md#assign-a-policy-package-to-a-group)。

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a>向大型组（批处理）分配策略包

使用批处理策略包分配，每次向大型用户组分配策略包。 使用 [New-CsBatchPolicyPackageAssignmentOperation](/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet 提交要分配的一批用户和策略包。 作业将作为后台操作处理，并为每个批处理生成操作 ID。

批处理最多可包含 5,000 个用户。 可通过对象 Id、UPN、SIP 地址或电子邮件地址指定用户。 若要了解详细信息，请参阅[将策略包分配给批次用户](assign-policies.md#assign-a-policy-package-to-a-batch-of-users)。

## <a name="policies-that-should-be-assigned-for-student-safety"></a>应为学生安全分配的策略

有关对环境中的学生执行保护所需步骤的详细信息，请仔细查看[使用 Teams 进行远程学习时确保学生安全](https://support.office.com/article/keeping-students-safe-while-using-meetings-in-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8)。