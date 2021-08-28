---
title: Teams 医疗保健策略包
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
ms.localizationpriority: medium
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: 了解如何使用和管理适用于医疗保健组织的 Teams 策略包。
ms.openlocfilehash: e81741e40928ec92717b686773078781b51b73be
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58608839"
---
# <a name="teams-policy-packages-for-healthcare"></a>Teams 医疗保健策略包

## <a name="overview"></a>概述

Microsoft Teams 中的[策略包](manage-policy-packages.md)是一组预定义的策略和策略设置，你可以将其分配给组织中具有类似角色的用户。 策略包可简化并有助于提供一致的策略管理。 你可以自定义包中策略的设置以满足用户的需求。 当你更改策略包中策略的设置时，分配了该包的所有用户均会获得更新后的设置。 你可以使用 Microsoft Teams 管理中心或 PowerShell 管理策略包。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Ht2o]

策略包针对以下各项预定义了策略，具体内容因策略包而异：

- 消息传递
- 会议
- 通话
- 应用设置
- 实时事件

Teams 当前包括以下医疗保健策略包。

|Microsoft Teams 管理中心中的策略包名称|最适合用于|说明 |
|---------|---------|---------|
|医疗保健临床工作者  |医疗保健组织的临床工作者  |创建一组策略和策略设置，以使临床工作者（例如注册护士、护士长、医师和社会工作者）可以完全访问聊天、通话、轮班管理和会议。 |
|医疗保健信息工作者  |医疗保健组织的信息工作者 |创建一组策略和策略设置，以使信息工作者（例如 IT 人员、信息学人员、财务人员和合规专员）可以完全访问聊天、通话和会议。|
|医疗保健病房  |病房设备|创建一组适用于医疗保健组织中病房的策略和策略设置。|

![医疗保健策略包的屏幕截图](media/policy-packages-healthcare.png)

将为每个单独的策略提供策略包的名称，以便你可以轻松识别链接到该策略包的策略。 例如，当你将医疗保健临床工作者策略包分配给组织中的临床医师时，系统将为该策略包中的每个策略创建一个名为 Healthcare_ClinicalWorker 的策略。

![医疗保健临床工作者策略包中策略的屏幕截图](media/policy-packages-healthcare-clinical-worker.png)

## <a name="get-started-with-policy-packages"></a>开始使用策略包

若要开始使用医疗保健策略包，请在 Microsoft 管理中心载入中心上选择“**医疗保健**”，然后选择“**按角色分配策略设置**”。 准备好开始使用后，请确定要将组织中的个人分配给哪些策略包。

选择“**查看策略详细信息**”，以了解有关策略包中的特定策略及其各自设置的更多信息。 分配后可在 Teams 管理中心中[自定义](manage-policy-packages.md#customize-policies-in-a-policy-package)这些设置。

选择要分配的一个或多个包，然后单击“**下一步**”。 可以搜索人员并将其添加到最适合其角色的策略包。 不能一次将一个人分配给多个策略包。

将人员添加到正确的策略包后，请单击“**完成**”以最终确定你所做的选择。 可在 Microsoft Teams 管理中心中继续自定义和管理策略包。

## <a name="manage-policy-packages"></a>管理策略包

### <a name="view"></a>查看

在分配包前查看策略包中每个策略的设置。 在 Microsoft Teams 管理中心的左侧导航栏中，转至“**策略包**”，选择策略包名称，然后选择策略名称。

确定预定义值是否适合你的组织，或是否需要根据组织的需求对其进行自定义，使其更具限制性或更宽松。

### <a name="customize"></a>自定义

根据需要自定义策略包中的策略设置，满足组织的需求。 对策略设置所做的任何更改都将自动应用到已分配了该包的用户。 若要编辑策略包中某个策略的设置，请在 Microsoft Teams 管理中心的左侧导航栏中，转至“**策略包**”，选择策略包，选择要编辑的策略的名称，然后选择“**编辑**”。

请记住，在分配策略包之后，你还可以更改包中的策略设置。 若要了解详细信息，请参阅[自定义策略包](manage-policy-packages.md#customize-policies-in-a-policy-package)中的策略。

### <a name="assign"></a>分配

将策略包分配给用户。如果用户已分配策略，稍后又分配了另一个策略，则最近分配的优先级将会更高。

> [!NOTE]
> 为了接受自定义策略包分配，每位用户都需要高级通信加载附加产品。 有关详细信息，请参阅 [Microsoft Teams 高级通信附加产品](/microsoftteams/teams-add-on-licensing/advanced-communications)。

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

## <a name="related-topics"></a>相关主题

[在 Teams 中管理策略包](manage-policy-packages.md)

[将策略包分配给用户和组](assign-policy-packages.md)
