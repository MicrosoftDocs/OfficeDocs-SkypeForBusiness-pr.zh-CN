---
title: 在 Microsoft Teams 中管理策略包
ms.author: mabond
author: mkbond007
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
ms.localizationpriority: medium
search.appverid: MET150
description: 了解如何在 Microsoft Teams 中使用和管理策略包，以简化、简化和帮助在管理用户组的策略时提供一致性。
ms.openlocfilehash: 10c7eaad9342d1c005c6290ebc957c3580db3962
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2022
ms.locfileid: "67270847"
---
# <a name="manage-policy-packages-for-microsoft-teams"></a>管理 Microsoft Teams 的策略包

Microsoft Teams 中的策略包是一组预定义的策略和策略设置，你可以将其分配给组织中具有类似角色的用户。 我们构建了策略包，以简化、简化和帮助在管理组织中用户组的策略时提供一致性。  

可以使用 [Teams 中包含的策略包](#policy-packages-included-in-teams) ，或 [创建自己的自定义策略包](#custom-policy-packages)。

:::image type="content" source="media/policy-packages-admin-center.png" alt-text="管理中心“策略包”页的屏幕截图。" lightbox="media/policy-packages-admin-center.png":::

可以自定义策略包中策略的设置，以满足用户的需求。 更改包中的策略设置时，分配给该包的所有用户都会获得更新的设置。 使用 Microsoft Teams 管理中心或 PowerShell 管理策略包。

> [!NOTE]
> 此功能在所有 Microsoft Teams 客户的公共预览版中暂时可用。 若要在预览后获取此功能，每个用户都需要高级通信加载项许可证。 有关详细信息，请参阅 [Microsoft Teams 高级通信附加产品](/microsoftteams/teams-add-on-licensing/advanced-communications)。

## <a name="what-is-a-policy-package"></a>什么是策略包？

通过策略包，可以控制想要允许或限制组织中特定人员集的 Teams 功能。 Teams 中的每个策略包都围绕用户角色进行设计，包括预定义的策略和策略设置，这些策略和策略设置支持该角色的典型协作和通信活动。

策略包支持以下 Teams 策略类型：

- 消息传递策略
- 会议策略
- 应用设置策略
- 呼叫策略
- 实时事件策略

## <a name="policy-packages-included-in-teams"></a>Teams 中包含的策略包

Teams 当前包含以下策略包。

| 包名称 | 说明 |
|---------|---------|
|高等教育 (学生)     |创建一组适用于高等教育学生的政策和策略设置。|
|教育 (小学生)    |创建一组适用于小学生的策略和策略设置。|
|教育 (中学生)     |创建一组适用于中学生的策略和策略设置。         |
|教育 (教师)     |创建一组适用于教师的策略和策略设置。      |
|使用远程学习 (小学教师的教育)     |创建一组适用于主要教师的策略，在远程学习中最大化学生的安全和协作。      |
|使用远程学习 (小学生的教育)     |创建一组适用于主要学生的策略，在远程学习中最大化学生的安全和协作。      |
|一线经理 |创建一组策略，并将这些设置应用于组织中的一线经理。 |
|一线工作人员 |创建一组策略，并将这些设置应用到组织中的一线工作人员。 |
|医疗保健临床工作者  |创建一组策略和策略设置，以使临床工作者（例如注册护士、护士长、医师和社会工作者）可以完全访问聊天、通话、轮班管理和会议。 |
|医疗保健信息工作者  |创建一组策略和策略设置，以使信息工作者（例如 IT 人员、信息学人员、财务人员和合规专员）可以完全访问聊天、通话和会议。|
|医疗保健病房  |创建一组适用于医疗保健组织中病房的策略和策略设置。 |
|公共安全官员   |创建一组适用于组织中的公共安全人员的策略和策略设置。|
|中小型企业用户 (商务语音)  |创建一个应用设置策略，其中包含适用于用户的业务语音体验的应用。|
|没有商务语音) 的中小型企业用户 ( |创建与中小型企业 Teams 用户相关的应用设置策略，而无需任何业务语音功能。

> [!NOTE]
> 我们将在 Teams 的未来版本中添加更多策略包，因此请查看最新信息。  

将为每个单独的策略提供策略包的名称，以便你可以轻松识别链接到该策略包的策略。
例如，将教育 (教师) 策略包分配给学校中的教师时，将为包中的每个策略创建一个名为Education_Teacher的策略。

:::image type="content" source="media/teams-policy-packages-education.png" alt-text="教育 (教师) 策略包的屏幕截图。" lightbox="media/teams-policy-packages-education.png":::

## <a name="custom-policy-packages"></a>自定义策略包

自定义策略包允许你为组织中具有类似角色的用户捆绑自己的一组策略。 通过添加所需的策略类型和策略来创建自己的策略包。

若要创建新的自定义策略包，请执行以下操作：

1. 在 Microsoft Teams 管理中心的左窗格中，选择“ **策略”包**，然后单击 **“添加**”。

    :::image type="content" source="media/policy-packages-add.png" alt-text="管理中心“策略包”页上的“添加”按钮的屏幕截图。" lightbox="media/policy-packages-add.png":::

2. 输入包的名称和说明。

    :::image type="content" source="media/policy-packages-add-custom.png" alt-text="添加新的自定义策略包的屏幕截图。" lightbox="media/policy-packages-add-custom.png":::

3. 选择要包含在包中的策略类型和策略名称。

4. 选择“**保存**”。

## <a name="how-to-use-policy-packages"></a>如何使用策略包

下面概述了如何在组织中使用策略包。

![有关如何使用策略包的概述。](media/manage-policy-packages-overview.png)

- **[视图](#view-the-settings-of-a-policy-in-a-policy-package)**：查看策略包中的策略。 然后，在分配包之前，查看包中每个策略的设置。 请确保了解每个设置。 确定预定义的值是否适合你的组织，或者是否需要根据组织的需求将这些值更改为更严格或更宽大。

    如果删除策略，仍可查看设置，但无法更改任何设置。 分配策略包时，将使用预定义的设置重新创建已删除的策略。

- **[自定义](#customize-policies-in-a-policy-package)**：自定义策略包中的策略设置，以满足组织的需求。

- **[分配](#assign-a-policy-package)**：将策略包分配给用户。  

> [!NOTE]
> 分配包后，还可以更改策略包中的策略设置。 对策略设置所做的任何更改都将自动应用到已分配了该包的用户。

下面是有关如何在 Microsoft Teams 管理中心查看、分配和自定义策略包的步骤。

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a>查看策略包中策略的设置

1. 在 Microsoft Teams 管理中心的左窗格中，选择策略 **包**，然后单击包名称左侧选择策略包。

2. 选择要查看的策略。

### <a name="customize-policies-in-a-policy-package"></a>自定义策略包中的策略

可以通过“策略 **包** ”页或直接转到 Microsoft Teams 管理中心的策略页来编辑策略的设置。

1. 在 Microsoft Teams 管理中心的左窗格中，执行以下操作之一：
    - 选择 **“策略”包**，然后单击包名称左侧，选择策略包。
    - 选择策略类型。  例如，单击 **“消息传递”策略**。

2. 选择要编辑的策略。 链接到策略包的策略与策略包的名称相同。

3. 进行所需的更改，然后单击 **“保存**”。

### <a name="assign-a-policy-package"></a>分配策略包

可以将策略包分配给单个用户、组或一批用户。 有关如何分配策略包的详细信息，请参阅 [向用户和组分配策略包](assign-policy-packages.md)。

## <a name="related-topics"></a>相关主题

- [分配策略包](assign-policy-packages.md)
- [适用于 EDU 管理员的 Teams 策略包](policy-packages-edu.md)
- [Teams 医疗保健策略包](policy-packages-healthcare.md)
- [适用于政府的 Teams 策略包](policy-packages-gov.md)
