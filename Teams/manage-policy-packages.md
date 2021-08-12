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
description: 了解如何在管理用户组的策略时Microsoft Teams和管理策略包，以简化、简化和帮助保持一致。
ms.openlocfilehash: 2fd892bc440996c7c1f000402122ad268a402ebb6bf382672813efa296de819f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54341779"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a>管理策略包Microsoft Teams

Microsoft Teams中的策略包是预定义策略和策略设置的集合，您可以将其分配给组织中具有类似角色的用户。 我们构建了策略包，以简化、简化和帮助在管理组织中用户组的策略时保持一致。  

可以使用策略[包中包含的策略Teams](#policy-packages-included-in-teams)[或创建自己的自定义策略包](#custom-policy-packages)。

:::image type="content" source="media/policy-packages-admin-center.png" alt-text="管理中心中"策略包"页面的屏幕截图":::

你可以自定义策略包中的策略设置，以满足用户的需要。 更改包中的策略设置时，分配到该包的所有用户将获取更新的设置。 可以使用管理中心或 PowerShell Microsoft Teams策略包。

> [!NOTE]
> 每个用户都需要高级通信加载项才能接收自定义策略包分配。 有关详细信息，请参阅[Advanced Communications add-on for Microsoft Teams](/microsoftteams/teams-add-on-licensing/advanced-communications)。

## <a name="what-is-a-policy-package"></a>什么是策略包？

策略包允许你Teams组织中特定人员组允许或限制的专用功能。 每个策略包Teams用户角色设计，并包括预定义的策略和策略设置，它们支持该角色典型的协作和通信活动。

策略包支持以下Teams策略类型：

- 邮件策略
- 会议策略
- 应用设置策略
- 呼叫策略
- 实时事件策略

## <a name="policy-packages-included-in-teams"></a>策略包包含在Teams

Teams当前包括以下策略包。

| 程序包名称 | 说明 |
|---------|---------|
|教育 (教育学生)     |创建一组适用于教育程度较高的学生的策略和策略设置。|
|教育 (中学生)    |创建一组适用于主要学生的策略和策略设置。|
|教育 (中学生)     |创建一组适用于中学生的策略和策略设置。         |
|教育 (教师)     |创建一组适用于教师的策略和策略设置。      |
|教育 (学校教师使用远程学习)     |创建一组适用于主要教师的策略，以在使用远程学习时最大化学生安全和协作。      |
|教育 (使用远程学习工具的中)     |创建一组适用于主要学生的策略，以在使用远程学习时最大化学生安全和协作。      |
|前端管理器 |创建一组策略，将这些设置应用于您组织的一线经理。 |
|前端工作线程 |创建一组策略，将这些设置应用于您组织的一线工作人员。 |
|医疗保健工作者  |创建一组策略和策略设置，这些策略和策略设置为家庭工作人员（如已注册的医生、医生、医生和社交工作者）提供对聊天、通话、轮班管理和会议的完全访问权限。 |
|医疗保健信息工作者  |创建一组策略和策略设置，为信息工作者（如 IT 人员、信息工作者、财务人员和合规部官员）提供对聊天、通话和会议的完全访问权限。|
|医疗保健患者室  |创建一组应用于医疗保健组织中患者房间的策略和策略设置。|
|小型企业用户 (商务语音)  |创建一个应用设置策略，其中包含用于商务语音体验的应用。|
|没有商务语音 (的中小型企业)  |创建与中小型企业相关的应用设置策略Teams用户 (商务语音体验) 。
|公共安全部主管   |创建一组适用于组织中公共安全官员的策略和策略设置。|

> [!NOTE]
> 我们将在将来的 Teams 版本中添加更多策略包，因此请重新查看最新信息。  

每个单独的策略都给定策略包的名称，以便你可以轻松标识链接到策略包的策略。
例如，当你将教育 (教师) 策略包分配给学校中的教师时，会为该包中每个策略创建一个名为 Education_Teacher 的策略。

![教育教育 (教师) 包的屏幕截图](media/policy-packages-education_teacher.png)

## <a name="custom-policy-packages"></a>自定义策略包

**自定义策略包尚不可用于政府社区云 (GCC)**

自定义策略包使你可以为组织中具有相似角色的用户捆绑自己的策略集。 通过添加所需的策略类型和策略创建自己的策略包。

创建新的自定义策略包：

1. 在管理中心左侧导航Microsoft Teams，选择"策略 **包**"，然后单击"添加 **"。**

    :::image type="content" source="media/policy-packages-add.png" alt-text="管理中心中"策略包"页面上的"添加"按钮的屏幕截图":::

2. 输入程序包的名称和说明。

    :::image type="content" source="media/policy-packages-add-custom.png" alt-text="添加新的自定义策略包的屏幕截图":::

3. 选择要包括在程序包中的策略类型和策略名称。

4. 单击 **保存**。

## <a name="how-to-use-policy-packages"></a>如何使用策略包

下面概述了如何在组织中使用策略包。

![如何使用策略包概述](media/manage-policy-packages-overview.png)

- **[视图](#view-the-settings-of-a-policy-in-a-policy-package)**：查看策略包中的策略。 然后，在分配包之前查看包中每个策略的设置。 确保你了解每个设置。 确定预定义值是否适合贵组织，或者是否需要根据组织的需求将它们更改为更具限制性或更宽松。

    如果策略被删除，仍可以查看设置，但无法更改任何设置。 分配策略包时，会使用预定义设置重新创建已删除的策略。

- **[自定义](#customize-policies-in-a-policy-package)**：自定义策略包中的策略设置，以满足组织的需求。

- **[分配](#assign-a-policy-package)**：将策略包分配给用户。  

> [!NOTE]
> 还可以在分配包后更改策略包中的策略设置。 对策略设置进行的任何更改都将自动应用于分配了程序包的用户。

下面是在管理中心内查看、分配和自定义策略Microsoft Teams的步骤。

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a>查看策略包中的策略设置

1. 在管理中心的左侧导航Microsoft Teams，选择策略包，然后单击程序包名称左侧选择策略包。

2. 单击要查看的策略。

### <a name="customize-policies-in-a-policy-package"></a>自定义策略包中的策略

可以通过"策略包"页或直接进入管理中心中的策略页面来编辑Microsoft Teams设置。

1. 在 Microsoft Teams 管理中心 的左侧导航中，执行以下其中一个操作:
    - 单击 **"策略** 包"，然后单击程序包名称左侧选择策略包。
    - 单击策略类型。  例如，单击"**消息策略"。**

2. 选择要编辑的策略。链接到策略包的策略名称与策略包相同。

3. 进行您需要的更改，然后单击"保存 **"。**

### <a name="assign-a-policy-package"></a>分配策略包

可以将策略包分配给单个用户、组或一批用户。 若要详细了解如何分配策略包，请参阅将策略包 [分配给用户和组](assign-policy-packages.md)。

## <a name="related-topics"></a>相关主题

- [分配策略包](assign-policy-packages.md)
- [Teams EDU 管理员部署策略包](policy-packages-edu.md)
- [Teams医疗保健策略包](policy-packages-healthcare.md)
- [Teams政府策略包](policy-packages-gov.md)
