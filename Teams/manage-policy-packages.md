---
title: 管理策略包Microsoft Teams
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
description: 了解如何在管理用户组的策略时Microsoft Teams管理策略包，以便简化、简化和帮助提供一致性。
ms.openlocfilehash: 63900f301a8b3a48a8c17c6278808cd52e2445da
ms.sourcegitcommit: 8ad05b37c0b714adb069bc2503e88366ab75c57d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/07/2021
ms.locfileid: "52810183"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a>管理策略包Microsoft Teams

Microsoft Teams 中的策略包是一组预定义的策略和策略设置，你可以将其分配给组织中具有类似角色的用户。 我们构建了策略包，用于简化、简化和帮助在管理组织中用户组的策略时提供一致性。  

可以使用应用程序[中包含的策略包](#policy-packages-included-in-teams)Teams[或创建自己的自定义策略包](#custom-policy-packages)。

:::image type="content" source="media/policy-packages-admin-center.png" alt-text="管理中心中"策略包"页的屏幕截图":::

可以自定义策略包中策略的设置以满足用户的需求。 更改包中的策略设置时，分配到该包的所有用户将获取更新的设置。 可以使用管理中心或 PowerShell Microsoft Teams策略包。

> [!NOTE]
> 每个用户都需要高级通信加载项才能接收自定义策略包分配。 有关详细信息，请参阅适用于 Microsoft Teams[的高级通信Microsoft Teams。](/microsoftteams/teams-add-on-licensing/advanced-communications)

## <a name="what-is-a-policy-package"></a>什么是策略包？

策略包允许你Teams组织中特定人员集允许或限制的特定功能。 每个策略包Teams用户角色设计，包括预定义的策略和策略设置，这些策略和策略设置支持该角色的典型协作和通信活动。

策略包支持以下Teams策略类型：

- 消息传递策略
- 会议策略
- 应用设置策略
- 呼叫策略
- 实时事件策略

## <a name="policy-packages-included-in-teams"></a>包含在策略包Teams

Teams包括以下策略包。

| 包名称 | 说明 |
|---------|---------|
|教育 (教育学生)     |创建一组适用于教育程度学生的策略和策略设置。|
|教育 (中学生)    |创建一组适用于主要学生的策略和策略设置。|
|教育 (中学生)     |创建一组适用于学生的策略和策略设置。         |
|教育 (教师)     |创建一组适用于教师的策略和策略设置。      |
|使用 (远程学习的教师)     |创建一组适用于主要教师的策略，在远程学习中最大化学生的安全和协作。      |
|使用 (远程学习工具的"教育)     |创建一组适用于主要学生的策略，在远程学习中最大化学生的安全和协作。      |
|前端管理器 |创建一组策略，将这些设置应用于组织的一线经理。 |
|一线辅助角色 |创建一组策略，将这些设置应用到组织的一线员工。 |
|医疗保健临床工作者  |创建一组策略和策略设置，以使临床工作者（例如注册护士、护士长、医师和社会工作者）可以完全访问聊天、通话、轮班管理和会议。 |
|医疗保健信息工作者  |创建一组策略和策略设置，以使信息工作者（例如 IT 人员、信息学人员、财务人员和合规专员）可以完全访问聊天、通话和会议。|
|医疗保健病房  |创建一组适用于医疗保健组织中病房的策略和策略设置。|
|小型企业和中型企业用户 (Business Voice)  |创建一个应用设置策略，其中包含用于业务语音体验的应用。|
|没有 Business Voice (的中小型企业)  |创建与中小型企业用户相关的应用设置策略Teams用户 (非业务语音体验) 。
|公共安全人员   |创建一组适用于组织中公共安全人员的策略和策略设置。|

> [!NOTE]
> 我们将在将来的 Teams 版本中添加更多策略包，因此请返回查看最新信息。  

将为每个单独的策略提供策略包的名称，以便你可以轻松识别链接到该策略包的策略。
例如，将教育 (教师) 策略包分配给学校中的教师时，会为包中的每个策略创建名为 Education_Teacher 的策略。

![教育教师教师 (策略) 屏幕截图](media/policy-packages-education_teacher.png)

## <a name="custom-policy-packages"></a>自定义策略包

**自定义策略包尚不可用于政府社区云 (GCC)**

自定义策略包允许为组织中具有类似角色的用户捆绑自己的策略集。 通过添加所需的策略类型和策略创建自己的策略包。

创建新的自定义策略包：

1. 在管理中心左侧导航Microsoft Teams，选择"**策略包**"，然后单击"添加 **"。**

    :::image type="content" source="media/policy-packages-add.png" alt-text="管理中心中"策略包"页面上的"添加"按钮的屏幕截图":::

2. 输入包的名称和说明。

    :::image type="content" source="media/policy-packages-add-custom.png" alt-text="添加新的自定义策略包的屏幕截图":::

3. 选择要包括在包中的策略类型和策略名称。

4. 单击“**保存**”。

## <a name="how-to-use-policy-packages"></a>如何使用策略包

下面概述了如何在组织中使用策略包。

![如何使用策略包的概述](media/manage-policy-packages-overview.png)

- **[视图](#view-the-settings-of-a-policy-in-a-policy-package)**：查看策略包中的策略。 然后，在分配包之前，查看包中每个策略的设置。 请确保了解每个设置。 根据组织的需求，确定预定义值是否适合组织，或者是否需要更改这些值，以更严格或宽松。

    如果策略已删除，仍可查看设置，但无法更改任何设置。 分配策略包时，会使用预定义设置重新创建已删除的策略。

- **[自定义](#customize-policies-in-a-policy-package)**：自定义策略包中的策略设置，以满足组织的需求。

- **[分配](#assign-a-policy-package)**：将策略包分配给用户。  

> [!NOTE]
> 分配包后，还可以更改策略包中的策略设置。 对策略设置所做的任何更改都将自动应用到已分配了该包的用户。

下面是在管理中心中查看、分配和自定义策略Microsoft Teams的步骤。

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a>查看策略包中的策略设置

1. 在管理中心的左侧导航Microsoft Teams，选择"策略包 **"，然后单击** 程序包名称左侧选择策略包。

2. 单击要查看的策略。

### <a name="customize-policies-in-a-policy-package"></a>自定义策略包中的策略

可以通过"策略包"页或直接进入管理中心中的策略页来编辑Microsoft Teams设置。

1. 在管理中心Microsoft Teams导航中，执行下列操作之一：
    - 单击 **"策略** 包"，然后单击包名称左侧选择策略包。
    - 单击策略类型。  例如，单击"**消息传送策略"。**

2. 选择要编辑的策略。 链接到策略包的策略与策略包同名。

3. 进行您需要的更改，然后单击"保存 **"。**

### <a name="assign-a-policy-package"></a>分配策略包

可以将策略包分配给单个用户、组或一批用户。 若要详细了解如何分配策略包，请参阅 [向用户和组分配策略包](assign-policy-packages.md)。

## <a name="related-topics"></a>相关主题

- [分配策略包](assign-policy-packages.md)
- [Teams EDU 管理员部署策略包](policy-packages-edu.md)
- [Teams 医疗保健策略包](policy-packages-healthcare.md)
- [Teams政府部署策略包](policy-packages-gov.md)
