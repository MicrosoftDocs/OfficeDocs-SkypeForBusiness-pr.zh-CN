---
title: 政府团队政策包
author: lanachin
ms.author: v-lanac
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
description: 了解如何使用和管理政府组织的团队策略包。
ms.openlocfilehash: 8ef632689cb52180e8fd18cf4047fb9a25150885
ms.sourcegitcommit: ee217e1d7188842c7becd19387fd421b485c3575
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2020
ms.locfileid: "48908591"
---
# <a name="teams-policy-packages-for-government"></a>政府团队政策包

> [!NOTE]
> 策略程序包目前在 Microsoft 365 政府版或 DoD 部署中不可用。

## <a name="overview"></a>概述

Microsoft 团队中的 [策略包](manage-policy-packages.md) 是预定义策略和策略设置的集合，可分配给在组织中具有类似角色的用户。 策略包可简化并有助于提供一致的策略管理。 你可以自定义程序包中的策略设置以满足你的用户需求。 当您更改策略包中的策略设置时，分配到该程序包的所有用户都将获得更新的设置。 你可以使用 Microsoft 团队管理中心或 PowerShell 管理策略包。

策略程序包针对以下情况预定义策略，具体取决于程序包：

- 消息传递
- 会议
- 通话
- 应用设置
- 实时事件

团队当前包括适用于政府的以下政策包。

|Microsoft 团队管理中心中的程序包名称|最适合用于|说明 |
|---------|---------|---------|
|公共安全专员  |政府组织中的公共安全官员  |创建一组策略和策略设置，这些策略设置适用于您的组织中的公共安全专员。 |
|一线管理器  |政府组织中的一线经理 |创建一组策略，并将这些设置应用到组织中的一线管理员。|
|一线工作人员  |您的政府组织中的一线工作者 |创建一组策略，并将这些设置应用于您的组织中的一线工作人员。|

![医疗保健策略程序包的屏幕截图](media/policy-packages-gov.png)

每个单独策略都被授予策略程序包的名称，以便你可以轻松地识别链接到策略包的策略。 例如，当您将公共安全专员策略包分配给您的组织中的用户时，将为程序包中的每个策略创建一个名为 PublicSafety_Officer 的策略。

![医疗保健临床工作者程序包中的策略的屏幕截图](media/policy-packages-public-safety-officer.png)

## <a name="manage-policy-packages"></a>管理策略包

### <a name="view"></a>查看

在分配程序包之前查看策略包中每个策略的设置。 在 Microsoft 团队管理中心的左侧导航中，选择 " **策略包** "，选择程序包名称，然后选择 "策略名称"。

确定预定义的值是否适合你的组织，或者你是否需要根据组织的需求自定义它们以使其更具限制性或 lenient。

### <a name="customize"></a>自定义

根据需要自定义策略包中的策略设置，以满足组织的需要。 对策略设置所做的任何更改都将自动应用到分配了该程序包的用户。 若要编辑策略包中的策略设置，请在 Microsoft 团队管理中心中，选择 "策略" 程序包，选择要编辑的策略的名称，然后选择 " **编辑** "。

请记住，你还可以在分配策略包后更改程序包中的策略设置。 若要了解详细信息，请参阅 [自定义策略包中的策略](manage-policy-packages.md#customize-policies-in-a-policy-package)。 

### <a name="assign"></a>分配

将策略包分配给用户。 如果用户分配了策略，然后你分配了其他策略，则最新作业的优先级将会更高。

#### <a name="assign-a-policy-package-to-one-or-several-users"></a>将策略包分配给一个或多个用户

若要向一个或多个用户分配策略包，请在 Microsoft 团队管理中心的左侧导航中，转到 " **策略程序包** "，然后选择 " **管理用户** "。  

![如何在管理中心分配策略包的屏幕截图](media/policy-packages-healthcare-assign.png)

若要了解详细信息，请参阅 [分配策略包](manage-policy-packages.md#assign-a-policy-package)。

如果用户分配了策略，然后你分配了其他策略，则最新作业的优先级将会更高。

#### <a name="assign-a-policy-package-to-a-group"></a>为组分配策略包

**此功能在私人预览版中**

通过将策略包分配给组，你可以将多个策略分配给一组用户，如安全组或通讯组列表。 根据优先级规则，策略分配将传播到组的成员。 将成员添加到组或从组中删除成员后，将相应地更新其继承的策略分配。 对于多达50000用户的组，建议使用此方法，但也可使用较大的组。

若要了解详细信息，请参阅向 [组分配策略包](assign-policies.md#assign-a-policy-package-to-a-group)。

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a>将策略包分配给大型集 (批处理) 用户

使用批处理策略程序包分配来一次为大型用户分配一个策略包。 使用 [CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet 提交要分配的一批用户和策略包。 作业作为后台操作处理，并为每个批处理生成操作 ID。

批处理最多可包含5000个用户。 你可以按对象 Id、UPN、SIP 地址或电子邮件地址指定用户。 若要了解详细信息，请参阅向 [一批用户分配策略包](assign-policies.md#assign-a-policy-package-to-a-batch-of-users)。

## <a name="related-topics"></a>相关主题

[在 Teams 中管理策略包](manage-policy-packages.md)

[向团队中的用户分配策略](assign-policies.md) 
