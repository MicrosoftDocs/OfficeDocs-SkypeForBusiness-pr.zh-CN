---
title: 在 Microsoft Teams 中管理策略包
author: cichur
ms.author: v-cichur
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
description: 了解如何使用和管理 Microsoft Teams 中的策略包，以简化、简化和帮助在管理用户组的策略时提供一致性。
ms.openlocfilehash: 9718751ea1d34692718b63cbe90ee6e694577c21
ms.sourcegitcommit: c537b1cf03e7ac5d07f2fbf4ba73d73c510f3d96
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2021
ms.locfileid: "49862582"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a>在 Microsoft Teams 中管理策略包

> [!NOTE]
> 本文讨论的功能之一（ [自定义策略包](#custom-policy-packages)）目前以个人预览版提供。

Microsoft Teams 中的策略包是预定义的策略和策略设置的集合，可将其分配给组织中具有类似角色的用户。 我们构建了策略包，用于简化、简化和帮助在管理整个组织中用户组的策略时提供一致性。  

可以使用 Teams[中包含的策略包](#policy-packages-included-in-teams)，也可以创建自己的[](#custom-policy-packages)自定义策略包 (预览版) 。

:::image type="content" source="media/policy-packages-admin-center.png" alt-text="管理中心中"策略包"页的屏幕截图":::

可以自定义策略包中策略的设置以满足用户的需求。 更改包中策略的设置时，分配到该包的所有用户将获取更新的设置。 可以使用 Microsoft Teams 管理中心或 PowerShell 管理策略包。

## <a name="what-is-a-policy-package"></a>什么是策略包？

使用策略包可以控制要允许或限制整个组织中特定人员集的 Teams 功能。 Teams 中的每个策略包都围绕用户角色设计，包括预定义的策略和策略设置，这些策略和策略设置支持该角色的典型协作和通信活动。

策略包支持以下 Teams 策略类型：

- 消息传递策略
- 会议策略
- 应用设置策略
- 呼叫策略
- 实时事件策略

## <a name="policy-packages-included-in-teams"></a>Teams 中包含的策略包

Teams 当前包括以下策略包。

|**包名称**  |**说明** |
|---------|---------|
|教育 (教育学生)     |创建一组适用于更高教育程度学生的策略和策略设置。|
|教育 (中学生)    |创建一组适用于主要学生的策略和策略设置。|
|教育 (中学生)     |创建一组适用于学生的策略和策略设置。         |
|教育 (教师)     |创建一组适用于教师的策略和策略设置。      |
|使用 (远程学习工具的教师)     |创建一组适用于主要教师的策略，在远程学习中最大化学生的安全和协作。      |
|使用 (远程学习工具的)     |创建一组适用于主要学生的策略，在远程学习中最大化学生的安全和协作。      |
|前端管理器 |创建一组策略，将这些设置应用到组织的 Fronttline 管理器。 |
|前端辅助角色 |创建一组策略，将这些设置应用到组织的 Fronttline 工作人员。 |
|医疗保健医生  |创建一组策略和策略设置，为注册的医生、医生、医生和社交工作者等医疗工作者提供聊天、呼叫、轮班管理和会议的完全访问权限。 |
|医疗保健信息工作者  |创建一组策略和策略设置，为信息工作者（如 IT 人员、信息工作者、财务人员和合规官）提供聊天、呼叫和会议的完全访问权限。|
|医疗保健患者室  |创建一组适用于医疗保健组织中患者室的策略和策略设置。|
|小型企业用户和商业 (语音)  |创建一个应用设置策略，其中包括用于业务语音体验的应用。|
|没有 Business Voice (的中小型企业)  |为具有非业务语音体验的小型企业 Teams 用户创建 (设置) 。
|公共安全主管   |创建一组适用于组织中公共安全人员的策略和策略设置。|

> [!NOTE]
> 我们将在将来的 Teams 版本中添加更多策略包，因此请返回查看最新信息。  

每个单独的策略都获得策略包的名称，因此可以轻松识别链接到策略包的策略。
例如，将教育 (教师) 策略包分配给学校教师时，会为包中的每个策略创建名为 Education_Teacher 的策略。

![教育教师教师 (策略) 的屏幕截图](media/policy-packages-education_teacher.png)

## <a name="custom-policy-packages"></a>自定义策略包

**此功能在私有预览版中**

自定义策略包允许为组织中具有类似角色的用户捆绑自己的一组策略。 通过添加所需的策略类型和策略创建自己的策略包。

创建新的自定义策略包：

1. 在 Microsoft Teams 管理中心的左侧导航栏中，选择"**策略包**"，然后单击"添加 **"。**
    :::image type="content" source="media/policy-packages-add.png" alt-text="管理中心"策略包"页上的"添加"按钮的屏幕截图":::
2. 输入包的名称和说明。
    :::image type="content" source="media/policy-packages-add-custom.png" alt-text="添加新的自定义策略包的屏幕截图":::
3. 选择要包括在包中的策略类型和策略名称。
4. 单击“**保存**”。

## <a name="how-to-use-policy-packages"></a>如何使用策略包

下面概述了如何在组织中使用策略包。

![如何使用策略包的概述](media/manage-policy-packages-overview.png)

- **[视图](#view-the-settings-of-a-policy-in-a-policy-package)**：查看策略包中的策略。 然后，在分配包之前，查看包中每个策略的设置。 请确保了解每个设置。 根据组织的需求决定预定义值是否适合组织，或者是否需要将它们更改为更严格或更宽松。

    如果删除策略，仍可以查看设置，但无法更改任何设置。 分配策略包时，会使用预定义设置重新创建已删除的策略。

- **[自定义](#customize-policies-in-a-policy-package)**：自定义策略包中策略的设置以满足组织的需求。

- **[分配](#assign-a-policy-package)**：将策略包分配给用户。  

> [!NOTE]
> 分配包后，还可以更改策略包中的策略设置。 对策略设置所做的任何更改都将自动应用到已分配了该包的用户。

下面是在 Microsoft Teams 管理中心中查看、分配和自定义策略包的步骤。

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a>查看策略包中的策略设置

1. 在 Microsoft Teams 管理中心的左侧导航栏中，选择"策略包"，然后单击程序包名称左侧选择策略包。
2. 单击要查看的策略。

### <a name="customize-policies-in-a-policy-package"></a>自定义策略包中的策略

可以通过"策略包"页或直接进入Microsoft Teams 管理中心的策略页面来编辑策略设置。

1. 在 Microsoft Teams 管理中心的左侧导航栏中，执行下列操作之一：
    - 单击 **"** 策略包"，然后单击包名称左侧选择策略包。
    - 单击策略类型。  例如，单击 **"消息传送策略"。**
2. 选择要编辑的策略。 链接到策略包的策略与策略包同名。
3. 进行您需要的更改，然后单击"保存 **"。**

### <a name="assign-a-policy-package"></a>分配策略包 

#### <a name="assign-a-policy-package-to-one-user"></a>将策略包分配给一个用户

1. 在 Microsoft Teams 管理员中心的左侧导航中，转到“用户”，然后单击相应的用户。
2. 在用户的页面上，单击"策略"，然后在"策略包"**旁边单击"** 编辑 **"。**
3. 在"**分配策略包"** 窗格中，选择要分配的包，然后单击"保存 **"。**

#### <a name="assign-a-policy-package-to-multiple-users"></a>将策略包分配给多个用户

1. 在 Microsoft Teams 管理中心的左侧导航栏中，转到"策略包"，然后单击程序包名称左侧，选择要分配的策略包。
2. 单击 **"管理用户"。**
3. 在“管理用户”窗格中，按显示名称或用户名搜索用户，选择用户名，然后单击“添加”。 对想要添加的每一个用户重复此步骤。
4. 添加完用户后，单击"保存 **"。**

#### <a name="assign-a-policy-package-to-a-group"></a>将策略包分配给组。

**此功能在私有预览版中**

通过将策略包分配到组，可将多个策略分配给一组用户，例如安全组或通讯组列表。 根据优先级规则，将策略分配传播到组中的成员。 将成员添加到组或从组中删除成员时，将相应更新其继承的策略分配。 建议将此方法用于最多 50,000 个用户的组，但也可使用更大的组。

若要了解详细信息，请参阅[将策略包分配到组](assign-policies.md#assign-a-policy-package-to-a-group)。

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a>向大型组（批处理）分配策略包

使用批处理策略包分配，每次向大型用户组分配策略包。 使用 [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet 提交要分配的一批用户和策略包。 作业将作为后台操作处理，并为每个批处理生成操作 ID。

批处理最多可包含 5,000 个用户。 可通过对象 Id、UPN、SIP 地址或电子邮件地址指定用户。 若要了解详细信息，请参阅[将策略包分配给批次用户](assign-policies.md#assign-a-policy-package-to-a-batch-of-users)。

## <a name="troubleshooting"></a>疑难解答

**分配策略包时收到错误**

如果未成功创建或应用包中的一个或多个策略，则可能会发生这种情况。 将策略包重新分配给用户。 重试操作通常可修复此问题。

## <a name="related-topics"></a>相关主题

[在 Teams 中向用户分配策略](assign-policies.md)

[适用于 EDU 管理员的 Teams 策略包](policy-packages-edu.md)

[用于医疗保健的 Teams 策略包](policy-packages-healthcare.md)

[适用于政府的 Teams 策略包](policy-packages-gov.md)
