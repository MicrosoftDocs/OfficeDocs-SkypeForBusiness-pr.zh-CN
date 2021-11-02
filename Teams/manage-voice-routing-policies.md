---
title: 管理直接路由的呼叫路由策略
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 了解如何在 Microsoft Teams 中创建和管理呼叫路由Microsoft Teams。
ms.openlocfilehash: dec6f19dea1f2a44f1c550bf4ae6b9c4f4dedc77
ms.sourcegitcommit: 197debacdcd1f7902f6e16940ef9bec8b07641af
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2021
ms.locfileid: "60634931"
---
# <a name="manage-call-routing-policies-for-direct-routing"></a>管理直接路由的呼叫路由策略

如果已在你的组织中部署了[直接](direct-routing-landing-page.md)路由，则使用呼叫路由策略允许 Teams 用户使用本地电话基础结构接收公用电话交换网 (PSTN) 并拨打电话。

呼叫路由策略 (语音路由策略) PSTN 使用记录的容器。 可创建和管理语音路由策略，方法为：在管理中心内Microsoft Teams语音路由策略，或者  >  使用语音Windows PowerShell。

可以使用全局（组织范围内的默认）策略，也可以创建并分配自定义策略。 除非创建并分配自定义策略，否则用户将自动获取全局策略。 请记住，可以在全局策略中编辑设置，但不能重命名或删除设置。

请务必知道，向用户分配语音路由策略并不能让他们在 Teams。 还需要为用户启用直接路由电话系统并完成其他配置步骤。 有关详细信息，请参阅配置 [直接路由](direct-routing-configure.md)。

## <a name="create-a-custom-call-routing-policy"></a>创建自定义呼叫路由策略

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

1. 在管理中心的左侧导航Microsoft Teams，转到 **"语音**  >  **语音路由策略**"，然后单击"添加 **"。**<br>
    ![管理中心 中的"添加语音路由策略"Microsoft Teams屏幕截图。](media/manage-voice-routing-policies.png) 
2. 输入策略的名称和说明。
3. 在 **"PSTN 使用记录"** 下，单击"添加 **PSTN** 使用情况"，然后选择要添加的记录。 如果需要创建新的 PSTN 使用记录，请单击"添加 **"。**
4. 如果添加了多个 PSTN 使用记录，请按您需要的顺序排列这些记录。
5. 完成后，单击"应用 **"。**
6. 单击“**保存**”。

### <a name="using-powershell"></a>使用 PowerShell

请参阅 [New-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/new-csonlinevoiceroutingpolicy)。

## <a name="edit-a-call-routing-policy"></a>编辑呼叫路由策略

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

可以编辑全局策略或创建的任何自定义策略。

1. 在管理中心的左侧导航Microsoft Teams，转到 **"语音**  >  **语音路由策略"。**
2. 单击策略名称的左侧以选择用户，然后单击“**编辑**”。
3. 单击 **"添加/删除 PSTN 使用** 记录"，进行您需要的更改，然后单击"保存 **"。**

### <a name="using-powershell"></a>使用 PowerShell

请参阅 [Set-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/set-csonlinevoiceroutingpolicy)。

## <a name="assign-a-custom-call-routing-policy-to-users"></a>向用户分配自定义呼叫路由策略

[!INCLUDE [assign-policy](includes/assign-policy.md)]

另请参阅 [Grant-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/grant-csonlinevoiceroutingpolicy)。

## <a name="related-topics"></a>相关主题

[Teams PowerShell 概览](teams-powershell-overview.md)

[为直接路由配置呼叫路由](direct-routing-voice-routing.md)

[为直接路由启用基于位置的路由](location-based-routing-enable.md)

[向 Teams 中的用户分配策略](policy-assignment-overview.md)