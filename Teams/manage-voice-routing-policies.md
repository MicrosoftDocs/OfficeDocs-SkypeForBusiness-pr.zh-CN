---
title: 管理直接路由的语音路由策略
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
description: 了解如何在语音路由服务中创建和管理Microsoft Teams。
ms.openlocfilehash: d9bd26f2322d9b99b0e2ff8e8ba01f0569abc24e
ms.sourcegitcommit: 3a8bec0445cee5cd776fb1991f093a0ec4351852
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/28/2021
ms.locfileid: "60605574"
---
# <a name="manage-voice-routing-policies-for-direct-routing"></a>管理直接路由的语音路由策略

如果已在你的组织中部署了[电话系统 直接](direct-routing-landing-page.md)路由，则使用语音路由策略允许 Teams 和 Skype for Business Online 用户使用本地电话基础结构接收公用电话交换网 (PSTN) 并拨打电话。

语音路由策略是 PSTN 使用记录的容器。 若要创建和管理语音路由策略，可Microsoft Teams管理中心中的语音语音路由  >  Windows PowerShell。

可以使用全局（组织范围内的默认）策略，也可以创建并分配自定义策略。 除非创建并分配自定义策略，否则用户将自动获取全局策略。 请记住，可以在全局策略中编辑设置，但不能重命名或删除设置。

请务必注意，向用户分配语音路由策略并不能让用户在 Teams。 还需要为用户启用直接路由电话系统完成其他配置步骤。 有关详细信息，请参阅配置 [直接路由](direct-routing-configure.md)。

## <a name="create-a-custom-voice-routing-policy"></a>创建自定义语音路由策略

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

1. 在管理中心的左侧导航Microsoft Teams，转到 **"**  >  **语音语音路由** 策略"，然后单击"添加 **"。**<br>
    ![管理中心 中的"添加语音路由策略"Microsoft Teams屏幕截图。](media/manage-voice-routing-policies.png) 
2. 输入策略的名称和说明。
3. 在 **"PSTN 使用记录"** 下，单击"添加 **PSTN** 使用情况"，然后选择要添加的记录。 如果需要创建新的 PSTN 使用记录，请单击"添加 **"。**
4. 如果添加了多个 PSTN 使用记录，请按您需要的顺序排列这些记录。
5. 完成后，单击"应用 **"。**
6. 单击“**保存**”。

### <a name="using-powershell"></a>使用 PowerShell

请参阅 [New-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/new-csonlinevoiceroutingpolicy)。

## <a name="edit-a-voice-routing-policy"></a>编辑语音路由策略

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

可以编辑全局策略或创建的任何自定义策略。

1. 在管理中心的左侧导航Microsoft Teams，转到 **"语音**  >  **语音路由策略"。**
2. 单击策略名称的左侧以选择用户，然后单击“**编辑**”。
3. 单击 **"添加/删除 PSTN 使用** 记录"，进行您需要的更改，然后单击"保存 **"。**

### <a name="using-powershell"></a>使用 PowerShell

请参阅[Set-CsOnlineVoiceRoutingPolicy。](/powershell/module/skype/set-csonlinevoiceroutingpolicy)

## <a name="assign-a-custom-voice-routing-policy-to-users"></a>向用户分配自定义语音路由策略

[!INCLUDE [assign-policy](includes/assign-policy.md)]

另请参阅 [Grant-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/grant-csonlinevoiceroutingpolicy)。

## <a name="related-topics"></a>相关主题

[Teams PowerShell 概览](teams-powershell-overview.md)

[为直接路由配置语音路由](direct-routing-voice-routing.md)

[为直接路由启用基于位置的路由](location-based-routing-enable.md)

[向 Teams 中的用户分配策略](policy-assignment-overview.md)