---
title: 用于医疗保健的 Teams 策略包
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: aaglick
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
localization_priority: Normal
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: 了解如何为医疗保健组织使用和管理 Teams 策略包。
ms.openlocfilehash: af6f5923d5c97fc03c77585ba94292264aacc027
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812852"
---
# <a name="teams-policy-packages-for-healthcare"></a>用于医疗保健的 Teams 策略包

## <a name="overview"></a>概述

Microsoft Teams [中的](manage-policy-packages.md) 策略包是预定义的策略和策略设置的集合，可将其分配给组织中具有类似角色的用户。 策略包可简化并有助于提供一致的策略管理。 可以自定义程序包中策略的设置以满足用户的需求。 更改策略包中的策略设置时，分配到该包的所有用户将获取更新的设置。 可以使用 Microsoft Teams 管理中心或 PowerShell 管理策略包。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Ht2o]

策略包根据包为以下内容预定义策略：

- 消息传递
- 会议
- 通话
- 应用设置
- 实时事件

Teams 当前包括以下医疗保健策略包。

|Microsoft Teams 管理中心中的程序包名称|最适合用于|说明 |
|---------|---------|---------|
|医疗保健医生  |医疗保健组织的医疗工作者  |创建一组策略和策略设置，为注册的医生、医生、医生和社交工作者等医疗工作者提供聊天、呼叫、轮班管理和会议的完全访问权限。 |
|医疗保健信息工作者  |医疗保健组织的信息工作者 |创建一组策略和策略设置，为信息工作者（例如 IT 人员、信息工作者、财务人员和合规官）提供聊天、呼叫和会议的完全访问权限。|
|医疗保健患者室  |患者房间设备|创建一组适用于医疗保健组织中患者室的策略和策略设置。|

![医疗保健策略包的屏幕截图](media/policy-packages-healthcare.png)

每个策略都有策略包的名称，因此可以轻松识别链接到策略包的策略。 例如，将医疗保健医疗医疗工作者策略包分配给贵组织的医生时，会Healthcare_ClinicalWorker每个策略创建一个名为 Healthcare_ClinicalWorker 的策略。

![医疗保健患者包中策略的屏幕截图](media/policy-packages-healthcare-clinical-worker.png)

## <a name="get-started-with-policy-packages"></a>策略包入门

若要开始使用医疗保健策略包，请在 Microsoft 管理中心载入中心选择 **"** 医疗保健"，然后选择"按角色分配 **策略设置"。** 准备好开始后，确定要向组织中个人分配的策略包。

选择 **"查看策略** 详细信息"，了解有关程序包中特定策略及其相应设置的详细信息。 在 [Teams 管理中心](manage-policy-packages.md#customize-policies-in-a-policy-package) 进行分配后，可以自定义这些设置。

选择要分配的一个或多个程序包，然后单击"下一 **步"。** 可以搜索人员，并将其添加到最适合其角色的策略包中。 不能一次将一个策略包分配给多个策略包。

将人员添加到正确的策略包后， **完成完成选择** 。 你可以继续在 Microsoft Teams 管理中心自定义和管理策略包。

## <a name="manage-policy-packages"></a>管理策略包

### <a name="view"></a>查看

在分配包前查看策略包中每个策略的设置。 在 Microsoft Teams 管理中心的左侧导航栏中，转到"策略包"，选择包名称，然后选择策略名称。

确定预定义值是否适合你的组织，或是否需要根据组织的需求对其进行自定义，使其更具限制性或更宽松。

### <a name="customize"></a>自定义

根据需要自定义策略包中的策略设置，满足组织的需求。 对策略设置所做的任何更改都将自动应用到已分配了该包的用户。 若要编辑策略包中的策略设置，请在 Microsoft Teams 管理中心的左侧导航栏中，转到"策略包"，选择策略包，选择要编辑的策略的名称，然后选择"编辑"。  

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

使用批处理策略包分配，每次向大型用户组分配策略包。 使用 [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet 提交要分配的一批用户和策略包。 作业将作为后台操作处理，并为每个批处理生成操作 ID。

批处理最多可包含 5,000 个用户。 可通过对象 Id、UPN、SIP 地址或电子邮件地址指定用户。 若要了解详细信息，请参阅[将策略包分配给批次用户](assign-policies.md#assign-a-policy-package-to-a-batch-of-users)。

## <a name="related-topics"></a>相关主题

[在 Teams 中管理策略包](manage-policy-packages.md)

[在 Teams 中向用户分配策略](assign-policies.md)
