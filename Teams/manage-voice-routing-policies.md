---
title: 管理 Microsoft 团队中的语音路由策略
author: lanachin
ms.author: v-lanac
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
description: 了解如何在 Microsoft 团队中创建和管理语音路由策略。
ms.openlocfilehash: 2bef422f22dc212b2c615e2ca2ab98806b396e9f
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217653"
---
# <a name="manage-voice-routing-policies-in-microsoft-teams"></a>管理 Microsoft 团队中的语音路由策略

如果你已在组织中部署了 [手机系统直接路由](direct-routing-landing-page.md) ，则使用 "语音路由策略" 允许团队和 Skype For business Online 用户使用本地电话基础结构接收和拨打电话给公共交换电话网络 (PSTN) 。

"语音路由策略" 是 PSTN 使用记录的容器。 通过转到**Voice**  >  Microsoft 团队管理中心或使用 Windows PowerShell 中的语音**语音路由策略**来创建和管理语音路由策略。

你可以使用全局 (组织范围默认) 策略，或者创建和分配自定义策略。 除非你创建并分配自定义策略，否则用户将自动获取全局策略。 请记住，你可以编辑全局策略中的设置，但不能重命名或删除它。

请务必知道，向用户分配语音路由策略不会使其能够在团队中进行 PSTN 呼叫。 您还需要为用户启用 "电话系统直接路由"，并完成其他配置步骤。 若要了解详细信息，请参阅 [配置直接路由](direct-routing-configure.md)。

## <a name="create-a-custom-voice-routing-policy"></a>创建自定义语音路由策略

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

1. 在 Microsoft 团队管理中心的左侧导航中，转到 "**语音**  >  **语音路由策略**"，然后单击 "**添加**"。<br>
    ![Microsoft 团队管理中心中 "添加语音路由策略" 页面的屏幕截图 ](media/manage-voice-routing-policies.png) 
2. 输入策略的名称和说明。
3. 在 " **PSTN 使用记录**" 下，单击 " **添加 PSTN 使用情况**"，然后选择要添加的记录。 如果需要创建新的 PSTN 使用记录，请单击 " **添加**"。
4. 如果您添加了多个 PSTN 使用记录，请按所需顺序排列它们。
5. 完成后，单击 " **应用**"。
6. 单击“**保存**”。

### <a name="using-powershell"></a>使用 PowerShell

请参阅 [新-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy)。

## <a name="edit-a-voice-routing-policy"></a>编辑语音路由策略

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

你可以编辑全局策略或你创建的任何自定义策略。

1. 在 Microsoft 团队管理中心的左侧导航中，转到 "**语音**  >  **语音路由策略**"。
2. 通过单击策略名称左侧，然后单击 " **编辑**"，选择策略。
3. 单击 " **添加/删除 PSTN 使用记录**"，进行所需的更改，然后单击 " **保存**"。

### <a name="using-powershell"></a>使用 PowerShell

请参阅 [设置-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceroutingpolicy)。

## <a name="assign-a-custom-voice-routing-policy-to-users"></a>为用户分配自定义语音路由策略

[!INCLUDE [assign-policy](includes/assign-policy.md)]

另请参阅 [授权 CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy)。

## <a name="related-topics"></a>相关主题

[Teams PowerShell 概览](teams-powershell-overview.md)

[为直接路由配置语音路由](direct-routing-voice-routing.md)

[为直接路由启用基于位置的路由](location-based-routing-enable.md)

[向团队中的用户分配策略](assign-policies.md)
