---
title: 管理 Microsoft 团队中的策略程序包
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: sekrantz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1keywords: ms.teamsadmincenter.policypackages.overview
localization_priority: Normal
search.appverid: MET150
description: 了解如何使用和管理 Microsoft 团队中的策略程序包。
ms.openlocfilehash: fb01a7e15d43c18e115ecfbd0edb73b4808c2a59
ms.sourcegitcommit: 30b4b979e20066253e32ab9e44d79c48a97e6211
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2019
ms.locfileid: "37972433"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a>管理 Microsoft 团队中的策略程序包

Microsoft 团队中的策略包是预定义策略和策略设置的集合，可分配给在组织中具有类似角色的用户。 我们构建了策略程序包，以便在管理组织内的用户组策略时提供简化、简化和帮助。  

向用户分配策略包时，将创建程序包中的策略，然后你可以自定义程序包中的策略设置以满足组织的需求。

## <a name="what-is-a-policy-package"></a>什么是策略包？

通过策略程序包，你可以控制你希望允许或限制你的组织中的特定人员组的团队功能。 团队中的每个策略包都围绕用户角色进行设计，其中包括预定义的策略和策略设置，这些策略和策略设置支持为该角色典型的协作和通信活动。

团队当前包含以下策略程序包。

|**程序包名称**  |**说明** |
|---------|---------|
|Education_Teacher 程序包     |创建一组适用于教师的策略和策略设置。      |
|Education_PrimaryStudent 程序包    |创建一组适用于主要学生的策略和策略设置。|
|Education_SecondaryStudent 程序包    |创建一组适用于次要学生的策略和策略设置。         |
|Education_HigherEducationStudent 程序包    |创建一组适用于更高教育学生的策略和策略设置。|

> [!NOTE]
> 我们将在未来版本的团队中添加更多策略程序包，请查看最新信息。  

每个单独策略都被授予策略程序包的名称，以便你可以轻松地识别链接到策略包的策略。
例如，将 Education_Teacher 策略包分配给学校中的教师时，将为程序包中的每个策略创建一个名为 Education_Teacher 的策略。

![Education_Teacher 策略程序包的屏幕截图](media/policy-packages-education_teacher.png)

## <a name="how-to-use-policy-packages"></a>如何使用策略程序包

以下概述了如何使用组织中的策略包。

![如何使用策略程序包概述](media/manage-policy-packages-overview.png)

- **[查看](#view-the-settings-of-a-policy-in-a-policy-package)**：在分配程序包之前查看策略包中每个策略的设置。 请确保你了解每个设置，然后确定预定义的值是否适合你的组织，或者你是否需要根据组织的需要将其更改为更具限制性或 lenient。

    如果删除策略，您仍然可以查看设置，但不能更改任何设置。 分配策略包时，将使用预定义的设置重新创建已删除的策略。

- **[分配](#assign-a-policy-package)**：将策略包分配给用户。 请记住，在分配程序包之前，不会创建策略包中的策略，之后，你可以在程序包中更改单个策略的设置。  

- **[自定义](#customize-policies-in-a-policy-package)**：自定义策略包中的策略设置以满足组织的需求。 对策略设置所做的任何更改都将自动应用到分配了该程序包的用户。

下面是有关如何在 Microsoft 团队管理中心中查看、分配和自定义策略包的步骤。

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a>查看策略包中的策略设置

1. 在 Microsoft 团队管理中心的左侧导航中，单击 "**策略包**"，然后通过单击程序包名称左侧的 "策略包" 进行选择。
2. 单击要查看的策略。

### <a name="assign-a-policy-package"></a>分配策略包

#### <a name="assign-a-policy-package-to-one-user"></a>为一个用户分配策略包

1. 在 Microsoft 团队管理中心的左侧导航中，转到 "**用户**"，然后单击 "用户"。
2. 在用户的页面上，单击 "**策略**"，然后单击 "**策略程序包**" 旁边的 "**编辑**"。
3. 在 "**分配策略包**" 窗格中，选择要分配的程序包，然后单击 "**保存**"。

#### <a name="assign-a-policy-package-to-multiple-users"></a>向多个用户分配策略包

1. 在 Microsoft 团队管理中心的左侧导航中，转到 "**策略程序包**"，然后通过单击程序包名称左侧的 "选择要分配的策略包"。
2. 单击 "**管理用户**"。
3. 在 "**管理用户**" 窗格中，按 "显示名称" 或 "按用户名搜索用户"，选择名称，然后单击 "**添加**"。 对要添加的每个用户重复此步骤。
4. 添加完用户后，单击 "**保存**"。

### <a name="customize-policies-in-a-policy-package"></a>自定义策略包中的策略

你可以通过 "**策略包**" 页面编辑策略的设置，或直接转到 Microsoft 团队管理中心中的 "策略" 页面。

1. 在 Microsoft 团队管理中心的左侧导航中，执行下列操作之一：
    - 单击 "**策略程序包**"，然后单击 "程序包名称" 左侧的 "策略程序包" 进行选择。
    - 单击 "策略类型"。  例如，单击 "**邮件策略**"。
2. 单击要编辑的策略。 链接到策略包的策略与策略包的名称相同。
3. 进行所需的更改，然后单击 "**保存**"。

## <a name="troubleshooting"></a>疑难解答

**分配策略包时收到错误**

如果程序包中的一个或多个策略未成功创建或应用，可能会发生这种情况。 将策略程序包重新分配给你的用户。 重试操作通常会修复此问题。
