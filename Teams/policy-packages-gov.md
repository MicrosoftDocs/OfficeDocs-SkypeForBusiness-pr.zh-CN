---
title: 适用于政府的 Teams 策略包
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
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
localization_priority: Normal
search.appverid: MET150
description: 了解如何为政府组织使用和管理 Teams 策略包。
ms.openlocfilehash: 2841fbf523f49c5784045cc6cf960e846b45aa9b
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909076"
---
# <a name="teams-policy-packages-for-government"></a>适用于政府的 Teams 策略包

> [!NOTE]
> Microsoft 365 政府版 GCC High 或 DoD 部署中当前未提供策略包。

## <a name="overview"></a>概述

Microsoft Teams [中的](manage-policy-packages.md) 策略包是预定义的策略和策略设置的集合，可将其分配给组织中具有类似角色的用户。 策略包可简化并有助于提供一致的策略管理。 可以自定义程序包中策略的设置以满足用户的需求。 更改策略包中的策略设置时，分配到该包的所有用户将获取更新的设置。 可以使用 Microsoft Teams 管理中心或 PowerShell 管理策略包。

策略包根据包为以下内容预定义策略：

- 消息传递
- 会议
- 通话
- 应用设置
- 实时事件

Teams 当前包括以下适用于政府的策略包。

|Microsoft Teams 管理中心中的程序包名称|最适合用于|说明 |
|---------|---------|---------|
|公共安全主管  |政府组织的公共安全人员  |创建一组适用于组织中公共安全人员的策略和策略设置。 |
|前端管理器  |政府组织的一线经理 |创建一组策略，将这些设置应用到组织的一线经理。|
|一线辅助角色  |政府组织的一线员工 |创建一组策略，将这些设置应用到组织的一线员工。|

![医疗保健策略包的屏幕截图](media/policy-packages-gov.png)

每个策略都有策略包的名称，因此可以轻松识别链接到策略包的策略。 例如，将公共安全主管策略包分配给组织中用户时，会PublicSafety_Officer包中每个策略创建名为 PublicSafety_Officer 的策略。

![医疗保健患者包中策略的屏幕截图](media/policy-packages-public-safety-officer.png)

## <a name="manage-policy-packages"></a>管理策略包

### <a name="view"></a>查看

在分配包前查看策略包中每个策略的设置。 在 Microsoft Teams 管理中心的左侧导航栏中，依次选择 **策略包**、程序包名称，然后选择策略名称。

确定预定义值是否适合你的组织，或是否需要根据组织的需求对其进行自定义，使其更具限制性或更宽松。

### <a name="customize"></a>自定义

根据需要自定义策略包中的策略设置，满足组织的需求。 对策略设置所做的任何更改都将自动应用到已分配了该包的用户。 若要编辑策略包中的策略设置，请在 Microsoft Teams 管理中心中，依次选择策略包、要编辑的策略的名称，然后选择 **编辑**。

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
