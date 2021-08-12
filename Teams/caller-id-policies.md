---
title: 在 Microsoft Teams 中管理呼叫方 ID 策略
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: roykuntz; jens
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.voice.callinglineid.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 了解如何使用和管理呼叫者 ID 策略Microsoft Teams更改或阻止组织中Teams用户的来电显示。
ms.openlocfilehash: 7157f1a2a7997a8278ac05ac74db676cb551b20d5858b8732e373429f4b5e5aa
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54341437"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a>在 Microsoft Teams 中管理呼叫方 ID 策略

> [!NOTE]
> 若要将呼叫方 ID 设置为资源帐户电话号码并设置呼叫方名称，请使用 Teams PowerShell 模块 2.3.1 或更高版本中的 PowerShell cmdlet New-CsCallingLineIdentity 或 Set-CsCallingLineIdentity。  (管理中心.) 中目前Microsoft Teams这些选项不可用 

默认情况下，当Teams呼叫 PSTN 电话时，用户的电话号码Teams可见。 同样，当 PSTN 呼叫者呼叫Teams用户时，PSTN 呼叫者的电话号码将可见。

作为管理员，可以使用呼叫方 ID 策略更改或阻止呼叫者 ID (也称为呼叫线路 ID) 。 您可以使用呼叫方 ID 策略显示组织中 Teams 用户的备用电话号码、阻止出站电话号码、阻止显示传入号码，或将呼叫方名称设置为 CNAM (CNAM) 。 例如，当用户进行呼叫时，你可以更改呼叫者 ID 以显示组织的主要电话号码和公司名称，而不是用户的电话号码。

通过访问管理中心中的"语音呼叫者  >  **ID"** 策略Microsoft Teams呼叫者 ID 策略。 可以使用全局（组织范围内的默认）策略，也可以创建并分配自定义策略。 除非你创建并分配自定义策略，否则你组织中的用户将自动获取全局策略。

## <a name="create-a-custom-caller-id-policy"></a>创建自定义来电显示策略

1. 在管理中心左侧导航Microsoft Teams，转到 **"语音呼叫**  >  **者 ID 策略"。**
2. 单击“**添加**”。 <br>
![管理中心中新来电显示策略页面的屏幕截图](media/caller-id-policies-add-policy.png)
3. 输入策略的名称和说明。
4. 从此处选择想要的设置：

    - **阻止来电** 显示：打开此设置，阻止显示传入呼叫的来电显示。
    - **替代呼叫者 ID** 策略：打开此设置，让用户覆盖策略中有关显示其号码以不向被呼叫者显示其号码的设置。 这意味着用户可以选择是否显示其来电显示。 有关详细信息，请参阅 [最终用户控制出站来电显示](./how-can-caller-id-be-used-in-your-organization.md#end-user-control-of-outbound-caller-id)。
    - **将呼叫方 ID 替换为**：通过选择下列选项之一，设置要显示给用户的来电显示：

        - **用户编号**：显示用户编号。 
        - **服务号码**：用于设置要显示为呼叫方 ID 的服务电话号码。
        - **匿名**：将来电显示为"匿名"。

    - **将来电显示替换为此服务号码**：选择服务号码以替换用户的来电显示。 如果在将呼叫方 ID 替换为 **中选择了** "服务号码 **"，则此选项可用**。

5. 单击“**保存**”。

## <a name="edit-a-caller-id-policy"></a>编辑来电显示策略

可以编辑全局策略或创建的任何自定义策略。 

1. 在管理中心左侧导航Microsoft Teams，转到 **"语音呼叫**  >  **者 ID 策略"。**
2. 单击策略名称的左侧以选择用户，然后单击“**编辑**”。
3. 更改想要的设置，然后单击"保存 **"。**

## <a name="assign-a-custom-caller-id-policy-to-users"></a>向用户分配自定义来电显示策略

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a>相关主题

[New-CsCallingLineIdentity](/powershell/module/skype/new-cscallinglineidentity?view=skype-ps)

[Set-CsCallingLineIdentity](/powershell/module/skype/set-cscallinglineidentity?view=skype-ps)

[向 Teams 中的用户分配策略](assign-policies.md)