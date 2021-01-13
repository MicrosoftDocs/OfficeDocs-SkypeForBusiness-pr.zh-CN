---
title: 在 Microsoft Teams 中管理语音路由策略
author: cichur
ms.author: v-cichur
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
localization_priority: Normal
search.appverid: MET150
description: 了解如何在 Microsoft Teams 创建和管理语音路由策略。
ms.openlocfilehash: 00b70363f0034ebc8d99aa59e037658e406af2a5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802552"
---
# <a name="manage-voice-routing-policies-in-microsoft-teams"></a>在 Microsoft Teams 中管理语音路由策略

如果你在你的组织中部署了电话系统[](direct-routing-landing-page.md)直接路由，则使用语音路由策略允许 Teams 和 Skype for Business Online 用户使用本地电话基础结构接收公用电话交换网 (PSTN) 并拨打电话。

语音路由策略是 PSTN 使用记录的容器。 若要创建和管理语音路由策略，可进入Microsoft Teams 管理中心中的语音路由策略，或者使用  >  语音路由Windows PowerShell。

可以使用全局策略 (组织范围内的默认) 策略，也可以创建和分配自定义策略。 除非创建并分配了自定义策略，否则用户将自动获取全局策略。 请记住，可以在全局策略中编辑设置，但不能重命名或删除它。

请务必了解，向用户分配语音路由策略不会让用户在 Teams 中拨打 PSTN 呼叫。 还需要为用户启用电话系统直接路由并完成其他配置步骤。 若要了解有关详细信息，请参阅"[配置直接路由"。](direct-routing-configure.md)

## <a name="create-a-custom-voice-routing-policy"></a>创建自定义语音路由策略

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

1. 在 Microsoft Teams 管理中心的左侧导航栏中，转到 **"语音**  >  **语音路由策略**"，然后单击"添加 **"。**<br>
    ![Microsoft Teams 管理中心的"添加语音路由策略"页的屏幕截图 ](media/manage-voice-routing-policies.png) 
2. 输入策略的名称和说明。
3. 在 **PSTN 使用情况记录下**，单击"添加 **PSTN 使用情况**"，然后选择要添加的记录。 如果需要创建新的 PSTN 使用记录，请单击"添加 **"。**
4. 如果添加了多个 PSTN 使用记录，请按您需要的顺序排列这些记录。
5. 完成后，单击"应用 **"。**
6. 单击“**保存**”。

### <a name="using-powershell"></a>使用 PowerShell

请参阅[New-CsOnlineVoiceRoutingPolicy。](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy)

## <a name="edit-a-voice-routing-policy"></a>编辑语音路由策略

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

可以编辑全局策略或创建的任何自定义策略。

1. 在 Microsoft Teams 管理中心的左侧导航栏中，转到 **语音**  >  **语音路由策略**。
2. 单击策略名称左侧选择策略，然后单击"编辑 **"。**
3. 单击 **"添加/删除 PSTN 使用记录**"，进行您需要的更改，然后单击"保存 **"。**

### <a name="using-powershell"></a>使用 PowerShell

请参阅[Set-CsOnlineVoiceRoutingPolicy。](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceroutingpolicy)

## <a name="assign-a-custom-voice-routing-policy-to-users"></a>向用户分配自定义语音路由策略

[!INCLUDE [assign-policy](includes/assign-policy.md)]

另请参阅[Grant-CsOnlineVoiceRoutingPolicy。](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy)

## <a name="related-topics"></a>相关主题

[Teams PowerShell 概览](teams-powershell-overview.md)

[为直接路由配置语音路由](direct-routing-voice-routing.md)

[为直接路由启用基于位置的路由](location-based-routing-enable.md)

[在 Teams 中向用户分配策略](assign-policies.md)
