---
title: 管理 Microsoft 团队中的策略程序包
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: sekrantz, aaglick
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.policypackages.overview
- seo-marvel-apr2020
localization_priority: Normal
search.appverid: MET150
description: 了解如何在 Microsoft 团队中使用和管理策略程序包，以便在管理用户组策略时简化、简化和帮助提供一致性。
ms.openlocfilehash: 986d64b11420877e146abc68f9f65c0503f49ff0
ms.sourcegitcommit: ee217e1d7188842c7becd19387fd421b485c3575
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2020
ms.locfileid: "48918642"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a>管理 Microsoft 团队中的策略程序包

> [!NOTE]
> 本文中所述的功能之一是 " [自定义策略" 程序包](#custom-policy-packages)，当前位于 "私人预览" 中。

Microsoft 团队中的策略包是预定义策略和策略设置的集合，可分配给在组织中具有类似角色的用户。 我们构建了策略程序包，以便在管理组织内的用户组策略时提供简化、简化和帮助。  

你可以使用 [团队中包含的策略程序包](#policy-packages-included-in-teams) 或 [创建你自己的自定义策略包](#custom-policy-packages) (在私人预览版) 中。

:::image type="content" source="media/policy-packages-admin-center.png" alt-text="管理中心中 "策略程序包" 页面的屏幕截图":::

你可以自定义策略包中的策略设置以满足你的用户需求。 更改程序包中的策略设置时，分配到该程序包的所有用户都将获得更新的设置。 你可以使用 Microsoft 团队管理中心或 PowerShell 管理策略包。

## <a name="what-is-a-policy-package"></a>什么是策略包？

通过策略程序包，你可以控制你希望允许或限制你的组织中的特定人员组的团队功能。 团队中的每个策略包都围绕用户角色进行设计，其中包括预定义的策略和策略设置，这些策略和策略设置支持为该角色典型的协作和通信活动。

策略程序包支持以下团队策略类型：

- 消息传递策略
- 会议策略
- 应用设置策略
- 呼叫策略
- 实时事件策略

## <a name="policy-packages-included-in-teams"></a>团队中包含的策略包

团队当前包含以下策略程序包。

|**程序包名称**  |**说明** |
|---------|---------|
|教育版 (更高教育学生)     |创建一组适用于更高教育学生的策略和策略设置。|
|教育 (主要学校学生)    |创建一组适用于主要学生的策略和策略设置。|
|教育 (次要学校学生)     |创建一组适用于次要学生的策略和策略设置。         |
| (教师) 教育    |创建一组适用于教师的策略和策略设置。      |
|使用 "远程学习" (主要学校教师的教育)     |创建一组适用于主要教师的策略，在远程学习中最大化学生的安全和协作。      |
|使用远程学习) 的主要教职员工 (教育版教育    |创建一组适用于主要学生的策略，在远程学习中最大化学生的安全和协作。      |
|一线管理器 |创建一组策略，并将这些设置应用到组织中的一线管理员。 |
|一线工作人员 |创建一组策略，并将这些设置应用于您的组织中的一线工作人员。 |
|医疗保健临床工作者  |创建一组策略和策略设置，为临床工作者（如注册的护士、费用护理、医生和社会工作者）提供对聊天、通话、班次管理和会议的完全访问权限。 |
|医疗保健信息工作者  |创建一组策略和策略设置，提供信息工作者，如 IT 人员、informatics 员工、财务人员和合规性监察官、对聊天、通话和会议的完全访问权限。|
|医疗保健患者聊天室  |创建一组策略和策略设置，这些策略设置适用于您的医疗保健组织中的患者聊天室。|
|中小型企业用户 (商务语音)  |创建包含商业语音体验应用的应用安装策略。|
|中小型企业用户 (，无需商用语音)  |创建与中小型企业团队用户 (非企业语音体验) 相关的应用设置策略。
|公共安全专员   |创建一组策略和策略设置，这些策略设置适用于您的组织中的公共安全专员。|

> [!NOTE]
> 我们将在未来版本的团队中添加更多策略程序包，请查看最新信息。  

每个单独策略都被授予策略程序包的名称，以便你可以轻松地识别链接到策略包的策略。
例如，当你向学校中的教师分配教育版 (教师) 策略包时，将为程序包中的每个策略创建一个名为 Education_Teacher 的策略。

![教育版 (教师) 策略包的屏幕截图](media/policy-packages-education_teacher.png)

## <a name="custom-policy-packages"></a>自定义策略程序包

**此功能在私人预览版中**

通过自定义策略程序包，你可以为你的组织中具有类似角色的用户捆绑你自己的策略集。 通过添加所需的策略类型和策略来创建自己的策略程序包。

要创建新的自定义策略程序包，请执行以下操作：

1. 在 Microsoft 团队管理中心的左侧导航中，选择 " **策略包** "，然后单击 " **添加** "。
    :::image type="content" source="media/policy-packages-add.png" alt-text="管理中心中 "策略程序包" 页面上的 "添加" 按钮的屏幕截图":::
2. 输入程序包的名称和说明。
    :::image type="content" source="media/policy-packages-add-custom.png" alt-text="添加新的自定义策略程序包的屏幕截图":::
3. 选择要包括在程序包中的策略类型和策略名称。
4. 单击“ **保存** ”。

## <a name="how-to-use-policy-packages"></a>如何使用策略程序包

以下概述了如何使用组织中的策略包。

![如何使用策略程序包概述](media/manage-policy-packages-overview.png)

- **[查看](#view-the-settings-of-a-policy-in-a-policy-package)** ：查看策略包中的策略。 然后，在分配程序包之前查看程序包中每个策略的设置。 请确保你了解每个设置。 确定预定义的值是否适合你的组织，或者你是否需要根据组织的需要将其更改为更具限制性或 lenient 的值。

    如果删除策略，您仍然可以查看设置，但不能更改任何设置。 分配策略包时，将使用预定义的设置重新创建已删除的策略。

- **[自定义](#customize-policies-in-a-policy-package)** ：自定义策略包中的策略设置以满足组织的需求。

- **[分配](#assign-a-policy-package)** ：将策略包分配给用户。  

> [!NOTE]
> 你还可以在分配程序包后更改策略包中的策略设置。 对策略设置所做的任何更改都将自动应用到分配了该程序包的用户。

下面是有关如何在 Microsoft 团队管理中心中查看、分配和自定义策略包的步骤。

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a>查看策略包中的策略设置

1. 在 "Microsoft 团队管理中心" 的左侧导航中，选择 " **策略程序包** "，然后单击程序包名称左侧的 "策略包" 进行选择。
2. 单击要查看的策略。

### <a name="customize-policies-in-a-policy-package"></a>自定义策略包中的策略

你可以通过 " **策略包** " 页面编辑策略的设置，或直接转到 Microsoft 团队管理中心中的 "策略" 页面。

1. 在 Microsoft 团队管理中心的左侧导航中，执行下列操作之一：
    - 单击 " **策略程序包** "，然后单击 "程序包名称" 左侧的 "策略程序包" 进行选择。
    - 单击 "策略类型"。  例如，单击 " **邮件策略** "。
2. 选择要编辑的策略。 链接到策略包的策略与策略包的名称相同。
3. 进行所需的更改，然后单击 " **保存** "。

### <a name="assign-a-policy-package"></a>分配策略包 

#### <a name="assign-a-policy-package-to-one-user"></a>为一个用户分配策略包

1. 在 Microsoft Teams 管理员中心的左侧导航中，转到“用户”，然后单击相应的用户。
2. 在用户的页面上，单击 " **策略** "，然后单击 " **策略程序包** " 旁边的 " **编辑** "。
3. 在 " **分配策略包** " 窗格中，选择要分配的程序包，然后单击 " **保存** "。

#### <a name="assign-a-policy-package-to-multiple-users"></a>向多个用户分配策略包

1. 在 Microsoft 团队管理中心的左侧导航中，转到 " **策略程序包** "，然后通过单击程序包名称左侧的 "选择要分配的策略包"。
2. 单击 " **管理用户** "。
3. 在“管理用户”窗格中，按显示名称或用户名搜索用户，选择用户名，然后单击“添加”。 对想要添加的每一个用户重复此步骤。
4. 添加完用户后，单击 " **保存** "。

#### <a name="assign-a-policy-package-to-a-group"></a>为组分配策略包

**此功能在私人预览版中**

通过将策略包分配给组，你可以将多个策略分配给一组用户，如安全组或通讯组列表。 根据优先级规则，策略分配将传播到组的成员。 将成员添加到组或从组中删除成员后，将相应地更新其继承的策略分配。 对于多达50000用户的组，建议使用此方法，但也可使用较大的组。

若要了解详细信息，请参阅向 [组分配策略包](assign-policies.md#assign-a-policy-package-to-a-group)。

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a>将策略包分配给大型集 (批处理) 用户

使用批处理策略程序包分配来一次为大型用户分配一个策略包。 使用 [CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet 提交要分配的一批用户和策略包。 作业作为后台操作处理，并为每个批处理生成操作 ID。

批处理最多可包含5000个用户。 你可以按对象 Id、UPN、SIP 地址或电子邮件地址指定用户。 若要了解详细信息，请参阅向 [一批用户分配策略包](assign-policies.md#assign-a-policy-package-to-a-batch-of-users)。

## <a name="troubleshooting"></a>故障排除

**分配策略包时收到错误**

如果程序包中的一个或多个策略未成功创建或应用，可能会发生这种情况。 将策略程序包重新分配给你的用户。 重试操作通常会修复此问题。

## <a name="related-topics"></a>相关主题

[向团队中的用户分配策略](assign-policies.md)

[教育机构管理员的团队策略包](policy-packages-edu.md)

[医疗保健的团队策略程序包](policy-packages-healthcare.md)

[政府团队政策包](policy-packages-gov.md)
