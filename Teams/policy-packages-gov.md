---
title: 适用于政府的 Teams 策略包
ms.author: mabond
author: mkbond007
manager: serdars
ms.reviewer: aaglick
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
ms.localizationpriority: medium
search.appverid: MET150
description: 了解如何为你的政府组织使用和管理 Teams 策略包。
ms.openlocfilehash: fdaacb8b551c1031d71c522dffdbc4afd9f551a8
ms.sourcegitcommit: 472e46b6eb907f41920516616683a61f0fc6f741
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/30/2022
ms.locfileid: "66564090"
---
# <a name="teams-policy-packages-for-government"></a>适用于政府的 Teams 策略包

> [!NOTE]
> 策略包当前在 Microsoft 365 政府 GCC High 或 DoD 部署中不可用。

## <a name="overview"></a>概述

Microsoft Teams 中的[策略包](manage-policy-packages.md)是一组预定义的策略和策略设置，你可以将其分配给组织中具有类似角色的用户。 策略包可简化并有助于提供一致的策略管理。 你可以自定义包中策略的设置以满足用户的需求。 当你更改策略包中策略的设置时，分配了该包的所有用户均会获得更新后的设置。 你可以使用 Microsoft Teams 管理中心或 PowerShell 管理策略包。

策略包针对以下各项预定义了策略，具体内容因策略包而异：

- 消息传递
- 会议
- 通话
- 应用设置
- 实时事件

Teams 当前包括以下政府策略包。

|Microsoft Teams 管理中心中的策略包名称|最适合用于|说明 |
|---------|---------|---------|
|公共安全官员  |你的政府组织中的公共安全官员  |创建一组适用于组织中的公共安全人员的策略和策略设置。 |
|前线经理  |政府组织中的一线经理 |创建一组策略，并将这些设置应用于组织中的一线管理器。|
|一线工作人员  |政府组织中的一线工作者 |创建一组策略，并将这些设置应用到组织中的一线工作者。|

![医疗保健策略包的屏幕截图。](media/policy-packages-gov.png)

将为每个单独的策略提供策略包的名称，以便你可以轻松识别链接到该策略包的策略。 例如，将公共安全官员策略包分配给组织中的用户时，将为包中的每个策略创建一个名为PublicSafety_Officer的策略。

![医疗保健临床辅助角色包中策略的屏幕截图。](media/policy-packages-public-safety-officer.png)

## <a name="manage-policy-packages"></a>管理策略包

### <a name="view"></a>查看

在分配包前查看策略包中每个策略的设置。 在 Microsoft Teams 管理中心的左侧导航栏中，依次选择 **策略包**、程序包名称，然后选择策略名称。

确定预定义值是否适合你的组织，或是否需要根据组织的需求对其进行自定义，使其更具限制性或更宽松。

### <a name="customize"></a>自定义

根据需要自定义策略包中的策略设置，满足组织的需求。 对策略设置所做的任何更改都将自动应用到已分配了该包的用户。 若要编辑策略包中的策略设置，请在 Microsoft Teams 管理中心中，依次选择策略包、要编辑的策略的名称，然后选择 **编辑**。

请记住，在分配策略包之后，你还可以更改包中的策略设置。 若要了解详细信息，请参阅[自定义策略包](manage-policy-packages.md#customize-policies-in-a-policy-package)中的策略。 

### <a name="assign"></a>分配

将策略包分配给用户。如果用户已分配策略，稍后又分配了另一个策略，则最近分配的优先级将会更高。

> [!NOTE]
> 为了接受自定义策略包分配，每位用户都需要高级通信加载附加产品。 有关详细信息，请参阅 [Microsoft Teams 高级通信附加产品](/microsoftteams/teams-add-on-licensing/advanced-communications)。

#### <a name="assign-a-policy-package-to-one-or-several-users"></a>向一个或多个用户分配策略包

若要将策略包分配给一个或多个用户，请在 Microsoft Teams 管理中心的左侧导航中，转到 **策略包**，然后选择 **管理用户**。  

![如何在管理中心分配策略包的屏幕截图。](media/policy-packages-healthcare-assign.png)

若要了解详细信息，请参阅[分配策略包](assign-policy-packages.md)。

如果用户已分配策略，稍后又分配了另一个策略，则最近分配的优先级将会更高。

#### <a name="assign-a-policy-package-to-a-group"></a>将策略包分配给组。

**此功能在私有预览版中**

通过将策略包分配到组，可将多个策略分配给一组用户，例如安全组或通讯组列表。 根据优先级规则，将策略分配传播到组中的成员。 将成员添加到组或从组中删除成员时，将相应更新其继承的策略分配。 建议将此方法用于最多 50,000 个用户的组，但也可使用更大的组。

若要了解详细信息，请参阅[将策略包分配到组](assign-policy-packages.md#assign-a-policy-package-to-a-group)。

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a>向大型组（批处理）分配策略包

使用批处理策略包分配，每次向大型用户组分配策略包。 使用 [New-CsBatchPolicyPackageAssignmentOperation](/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet 提交要分配的一批用户和策略包。 作业将作为后台操作处理，并为每个批处理生成操作 ID。

批处理最多可包含 5,000 个用户。 可通过对象 Id、UPN、SIP 地址或电子邮件地址指定用户。 若要了解详细信息，请参阅[将策略包分配给批次用户](assign-policy-packages.md#assign-a-policy-package-to-a-batch-of-users)。

## <a name="related-topics"></a>相关主题

[在 Teams 中管理策略包](manage-policy-packages.md)

[将策略包分配给用户和组](assign-policy-packages.md)
