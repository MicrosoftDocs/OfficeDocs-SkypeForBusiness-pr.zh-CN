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
f1.keywords: ''
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 了解如何在 Microsoft 团队中创建和管理语音路由策略。
ms.openlocfilehash: 7fa2530e170d398598e56d4b4f846cc316871b16
ms.sourcegitcommit: 6e24ea8aa9cccf8a1a964c8ed414ef5c7de3dc17
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2020
ms.locfileid: "44160966"
---
# <a name="manage-voice-routing-policies-in-microsoft-teams"></a>管理 Microsoft 团队中的语音路由策略

如果你已在组织中部署了[手机系统直接路由](direct-routing-landing-page.md)，则使用语音路由策略允许团队和 Skype For business Online 用户使用本地电话基础结构接收和拨打电话给公共交换电话网络（PSTN）。

"语音路由策略" 是 PSTN 使用记录的容器。 通过转到 Microsoft 团队管理中心或使用 Windows PowerShell 中的**语音** > **语音路由策略**来创建和管理语音路由策略。

你可以使用全局（组织范围默认）策略或创建并分配自定义策略。 除非你创建并分配自定义策略，否则用户将自动获取全局策略。 请记住，你可以编辑全局策略中的设置，但不能重命名或删除它。

请务必知道，向用户分配语音路由策略不会使其能够在团队中进行 PSTN 呼叫。 您还需要为用户启用 "电话系统直接路由"，并完成其他配置步骤。 若要了解详细信息，请参阅[配置直接路由](direct-routing-configure.md)。

## <a name="create-a-custom-voice-routing-policy"></a>创建自定义语音路由策略

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

1. 在 Microsoft 团队管理中心的左侧导航中，转到 "**语音** > **语音路由策略**"，然后单击 "**添加**"。<br>
    ![Microsoft 团队管理中心中 "添加语音路由策略" 页面的屏幕截图](media/manage-voice-routing-policies.png) 
2. 输入策略的名称和说明。
3. 在 " **PSTN 使用记录**" 下，单击 "**添加 PSTN 使用情况**"，然后选择要添加的记录。 如果需要创建新的 PSTN 使用记录，请单击 "**添加**"。
4. 如果您添加了多个 PSTN 使用记录，请按所需顺序排列它们。
5. 完成后，单击 "**应用**"。
6. 单击“**保存**”。

### <a name="using-powershell"></a>使用 PowerShell

请参阅[新-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy)。

## <a name="edit-a-voice-routing-policy"></a>编辑语音路由策略

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

你可以编辑全局策略或你创建的任何自定义策略。

1. 在 Microsoft 团队管理中心的左侧导航中，转到 "**语音** > **语音路由策略**"。
2. 通过单击策略名称左侧，然后单击 "**编辑**"，选择策略。
3. 单击 "**添加/删除 PSTN 使用记录**"，进行所需的更改，然后单击 "**保存**"。

### <a name="using-powershell"></a>使用 PowerShell

请参阅[设置-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceroutingpolicy)。

## <a name="assign-a-custom-voice-routing-policy-to-users"></a>为用户分配自定义语音路由策略

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

1. 在 Microsoft Teams 管理员中心的左侧导航中，转到“用户”，然后单击相应的用户。****
2. 单击 "**策略**"，然后单击 "**分配的策略**" 旁边的 "**编辑**"。
3. 在 "**语音路由策略**" 下，选择要分配的策略，然后单击 "**保存**"。

若要一次为多个用户分配自定义团队策略，请参阅[批量编辑团队用户设置](edit-user-settings-in-bulk.md)。

或者，您也可以执行以下操作：

1. 在 Microsoft 团队管理中心的左侧导航中，转到 "**语音** > **语音路由策略**"。
2. 单击策略名称的左侧以选择该策略。
3. 选择“管理用户”****。
4. 在“**管理用户**”窗格中，按显示名称或用户名搜索用户，选择用户名，然后选择“**添加**”。 对想要添加的每一个用户重复此步骤。
5. 添加完用户后，单击 "**保存**"。

### <a name="using-powershell"></a>使用 PowerShell

请参阅[授权-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy)。

## <a name="related-topics"></a>相关主题

- [Teams PowerShell 概览](teams-powershell-overview.md)
- [为直接路由配置语音路由](direct-routing-voice-routing.md)
- [为直接路由启用基于位置的路由](location-based-routing-enable.md)
