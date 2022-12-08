---
title: 在 Teams 中管理策略包
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
- m365initiative-meetings
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.policypackages.overview
- seo-marvel-apr2020
ms.localizationpriority: medium
search.appverid: MET150
description: 了解如何在 Microsoft Teams 中使用、管理和自定义策略包，以便在管理用户组的策略时简化、简化并帮助提供一致性。
ms.openlocfilehash: c2c5884261a4e55c64f3164fd805f708ed42598d
ms.sourcegitcommit: aa398950cc2f10b268c72a2b25caa0cf893e8230
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/08/2022
ms.locfileid: "69318408"
---
# <a name="managing-policy-packages-in-teams"></a>在 Teams 中管理策略包

[!INCLUDE[Teams Premium](includes/teams-premium-ecm.md)]

Microsoft Teams 中的策略包是一组预定义的策略和策略设置，你可以将其分配给组织中具有类似角色的用户。 我们构建了策略包，以便在管理组织中用户组的策略时简化、简化并帮助提供一致性。  

可以使用 [Teams 中包含的策略包](#policy-packages-included-in-teams) ，也可以 [创建自己的自定义策略包](#custom-policy-packages)。

:::image type="content" source="media/policy-packages-admin-center.png" alt-text="管理中心“策略包”页的屏幕截图。" lightbox="media/policy-packages-admin-center.png":::

可以自定义策略包中的策略设置，以满足用户的需求。 更改包中的策略设置时，分配到该包的所有用户都会获得更新的设置。 使用 Microsoft Teams 管理中心或 PowerShell 管理策略包。

## <a name="what-is-a-policy-package"></a>什么是策略包？

策略包允许你控制要允许或限制组织中特定人员集的 Teams 功能。 Teams 中的每个策略包都是围绕用户角色设计的，包括预定义的策略和策略设置，这些策略和策略设置支持该角色的典型协作和通信活动。

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
|教育 (高等教育学生)     |创建一组适用于高等教育学生的策略和策略设置。|
|教育 (小学生)    |创建一组适用于小学生的策略和策略设置。|
|教育 (中学生)     |创建一组适用于中学生的策略和策略设置。         |
|教育 (教师)     |创建一组适用于教师的策略和策略设置。      |
|教育 (小学教师使用远程学习)     |创建一组适用于主要教师的策略，在远程学习中最大化学生的安全和协作。      |
|使用远程学习) 教育 (小学生    |创建一组适用于主要学生的策略，在远程学习中最大化学生的安全和协作。      |
|一线经理 |创建一组策略，并将这些设置应用于组织中的一线经理。 |
|一线工作人员 |创建一组策略，并将这些设置应用于组织中的一线员工。 |
|医疗保健临床工作者  |创建一组策略和策略设置，以使临床工作者（例如注册护士、护士长、医师和社会工作者）可以完全访问聊天、通话、轮班管理和会议。 |
|医疗保健信息工作者  |创建一组策略和策略设置，以使信息工作者（例如 IT 人员、信息学人员、财务人员和合规专员）可以完全访问聊天、通话和会议。|
|医疗保健病房  |创建一组适用于医疗保健组织中病房的策略和策略设置。 |
|公共安全官员   |创建一组策略和策略设置，这些策略和策略设置适用于组织中的公共安全官员。|
|中小型企业用户 (商务语音)  |创建应用设置策略，该策略包括用户业务语音体验的应用。|
|没有商务语音) 的中小型企业用户 ( |创建与不具有任何业务语音功能的中小型企业 Teams 用户相关的应用设置策略。

> [!NOTE]
> 我们将在 Teams 的未来版本中添加更多策略包，因此请回来查看最新信息。  

将为每个单独的策略提供策略包的名称，以便你可以轻松识别链接到该策略包的策略。
例如，将教育 (教师) 策略包分配给学校中的教师时，会为包中的每个策略创建名为 Education_Teacher 的策略。

:::image type="content" source="media/teams-policy-packages-education.png" alt-text="教育 (教师) 策略包的屏幕截图。" lightbox="media/teams-policy-packages-education.png":::

## <a name="custom-policy-packages"></a>自定义策略包

> [!NOTE]
> 自定义策略包需要 Teams Premium。

自定义策略包允许将自己的策略集捆绑到组织中具有类似角色的用户。 通过添加所需的策略类型和策略来创建自己的策略包。

若要创建新的自定义策略包，请执行以下操作：

1. 在 Microsoft Teams 管理中心的左窗格中，选择“**策略包**”，然后单击“**添加**”。

    :::image type="content" source="media/policy-packages-add.png" alt-text="管理中心“策略包”页上的“添加”按钮的屏幕截图。" lightbox="media/policy-packages-add.png":::

2. 输入包的名称和说明。

    :::image type="content" source="media/policy-packages-add-custom.png" alt-text="添加新自定义策略包的屏幕截图。" lightbox="media/policy-packages-add-custom.png":::

3. 选择要包含在包中的策略类型和策略名称。

4. 选择“**保存**”。

## <a name="how-to-use-policy-packages"></a>如何使用策略包

下面概述了如何在组织中使用策略包。

![概述如何使用策略包。](media/manage-policy-packages-overview.png)

- **[视图](#view-the-settings-of-a-policy-in-a-policy-package)**：查看策略包中的策略。 然后，在分配包之前，查看包中每个策略的设置。 请确保了解每个设置。 确定预定义值是否适合组织，或者是否需要根据组织的需求将其更改为更严格或更宽松。

    如果删除了策略，仍可以查看设置，但无法更改任何设置。 分配策略包时，将使用预定义设置重新创建已删除的策略。

- **[自定义](#customize-policies-in-a-policy-package)**：自定义策略包中的策略设置，以满足组织的需求。

- **[分配](#assign-a-policy-package)**：将策略包分配给用户。  

> [!NOTE]
> 分配包后，还可以更改策略包中的策略设置。 对策略设置所做的任何更改都将自动应用到已分配了该包的用户。

下面是有关如何在 Microsoft Teams 管理中心查看、分配和自定义策略包的步骤。

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a>在策略包中查看策略的设置

1. 在 Microsoft Teams 管理中心的左窗格中，选择“**策略包**”，然后通过单击包名称左侧选择策略包。

2. 选择要查看的策略。

### <a name="customize-policies-in-a-policy-package"></a>自定义策略包中的策略

可以通过“**策略包**”页或直接转到 Microsoft Teams 管理中心中的策略页来编辑策略设置。

1. 在 Microsoft Teams 管理中心的左窗格中，执行以下操作之一：
    - 选择“ **策略包**”，然后通过单击包名称左侧选择策略包。
    - 选择策略类型。  例如，单击“ **消息传递策略**”。

2. 选择要编辑的策略。 链接到策略包的策略与策略包同名。

3. 进行所需的更改，然后单击“ **保存**”。

### <a name="assign-a-policy-package"></a>分配策略包

可以将策略包分配给单个用户、组或一批用户。 有关如何分配策略包的详细信息，请参阅 [将策略包分配给用户和组](assign-policy-packages.md)。

## <a name="related-topics"></a>相关主题

- [分配策略包](assign-policy-packages.md)
- [适用于 EDU 管理员的 Teams 策略包](policy-packages-edu.md)
- [Teams 医疗保健策略包](policy-packages-healthcare.md)
- [适用于政府的 Teams 策略包](policy-packages-gov.md)
