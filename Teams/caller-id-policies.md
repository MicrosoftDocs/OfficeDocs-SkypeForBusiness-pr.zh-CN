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
ms.localizationpriority: medium
search.appverid: MET150
description: 了解如何在 Microsoft Teams 中使用和管理来电显示策略来更改或阻止组织中 Teams 用户的来电显示。
ms.openlocfilehash: 4abeccb7a536885707ec43874d00f2a05a14551d
ms.sourcegitcommit: 321de0e5d8846caaaab944826f6ca06394e707ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/16/2022
ms.locfileid: "69414700"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a>在 Microsoft Teams 中管理呼叫方 ID 策略

默认情况下，当 Teams 用户呼叫 PSTN 电话时，Teams 用户的电话号码可见。 同样，当 PSTN 呼叫者向 Teams 用户发出呼叫时，PSTN 呼叫者的电话号码也可见。

管理员可以使用呼叫方 ID 策略来更改或阻止呼叫方 ID (也称为呼叫线路 ID) 。 可以使用呼叫方 ID 策略为组织中的 Teams 用户显示备用电话号码、阻止出站电话号码、阻止显示传入号码，或设置呼叫方名称 (CNAM) 。 例如，当用户拨打电话时，可以更改呼叫者 ID 以显示组织的主要电话号码和公司名称，而不是用户的电话号码。

可通过转到 Microsoft Teams 管理中心中的 **“语音** > **呼叫者 ID 策略”来管理呼叫方 ID 策略**。 可以使用全局（组织范围内的默认）策略，也可以创建并分配自定义策略。 除非你创建并分配自定义策略，否则你组织中的用户将自动获取全局策略。

## <a name="create-a-custom-caller-id-policy"></a>创建自定义呼叫方 ID 策略

1. 在 Microsoft Teams 管理中心的左侧导航栏中，转到 **“语音** > **呼叫方 ID 策略**”。
2. 单击“**添加**”。 <br>
![管理中心中新来电显示策略页的屏幕截图。](media/caller-id-policies-add-policy.png)
3. 输入策略的名称和说明。
4. 在此处，选择所需的设置：

    - **阻止传入呼叫方 ID**：启用此设置可阻止显示来电的呼叫方 ID。
    - **重写呼叫方 ID 策略**：启用此设置可让用户覆盖策略中有关向被呼叫方显示号码的设置。 这意味着用户可以选择是否显示其呼叫方 ID。 有关详细信息，请参阅 [最终用户对出站呼叫方 ID 的控制](./how-can-caller-id-be-used-in-your-organization.md#end-user-control-of-outbound-caller-id)。
    - **将呼叫方 ID 替换为**：通过选择以下选项之一，设置要向用户显示的呼叫方 ID：

        - **用户编号**：显示用户编号。 
        - **服务号码**：用于设置要显示为呼叫方 ID 的服务电话号码。
        - **匿名**：将呼叫方 ID 显示为“匿名”。

    - **将呼叫方 ID 替换为此服务号码**：选择服务号码以替换用户的呼叫方 ID。 如果在 **“将呼叫方 ID 替换为**”中选择了 **“服务号码**”，则此选项可用。

5. 单击“**保存**”。

## <a name="edit-a-caller-id-policy"></a>编辑呼叫方 ID 策略

可以编辑全局策略或创建的任何自定义策略。 

1. 在 Microsoft Teams 管理中心的左侧导航栏中，转到 **“语音** > **呼叫方 ID 策略**”。
2. 单击策略名称的左侧以选择用户，然后单击“**编辑**”。
3. 更改所需的设置，然后单击“ **保存**”。

## <a name="assign-a-custom-caller-id-policy-to-users"></a>向用户分配自定义呼叫方 ID 策略

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a>相关主题

[New-CsCallingLineIdentity](/powershell/module/skype/new-cscallinglineidentity)

[Set-CsCallingLineIdentity](/powershell/module/skype/set-cscallinglineidentity)

[向 Teams 中的用户分配策略](policy-assignment-overview.md)
