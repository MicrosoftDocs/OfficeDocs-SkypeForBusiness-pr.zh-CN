---
title: 管理 Microsoft 团队中的呼叫者 ID 策略
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark
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
description: 了解如何使用和管理 Microsoft 团队中的呼叫者 ID 策略更改或阻止组织中的团队用户的来电显示 ID。
ms.openlocfilehash: 41466640f33769a64ce14d5d3dc47959c876a5bc
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/30/2020
ms.locfileid: "44938461"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a>管理 Microsoft 团队中的呼叫者 ID 策略

>[!INCLUDE [new-feature-teams-admin-center](includes/new-feature-teams-admin-center.md)]

作为管理员，你可以使用 Microsoft 团队中的来电显示策略来更改或阻止来电显示（也称为呼叫线路 ID）。 默认情况下，当用户呼叫 PSTN 电话时，可以看到团队用户的电话号码，并且在呼叫团队用户时可以看到 PSTN 呼叫者的电话号码。 可以使用来电显示策略为组织中的团队用户显示备用电话号码，或阻止显示传入号码。

例如，当用户进行呼叫时，您可以更改来电显示以显示组织的主要电话号码，而不是用户的电话号码。

通过转到**Voice**  >  "Microsoft 团队管理中心" 中的 "语音来电显示"**策略**来管理呼叫者 id 策略。 你可以使用全局（组织范围默认）策略或创建并分配自定义策略。 除非你创建并分配了自定义策略，你组织中的用户将自动获取全局策略。

## <a name="create-a-custom-caller-id-policy"></a>创建自定义呼叫方 ID 策略

1. 在 Microsoft 团队管理中心的左侧导航中，转到 "**语音**  >  **呼叫者 ID 策略**"。
2. 单击“添加”****。 <br>
![管理中心中新来电显示策略页面的屏幕截图](media/caller-id-policies-add-policy.png)
3. 输入策略的名称和说明。
4. 在此处，选择所需的设置：

    - **阻止来电呼叫者 id**：启用此设置可阻止显示传入呼叫的来电显示。
    - **替代呼叫方 ID 策略**：启用此设置，让用户覆盖策略中的设置以将其号码显示为 callees。 这意味着用户可以选择是否要显示其呼叫者 ID。 有关详细信息，请参阅[最终用户对出站呼叫程序 ID 的控制](https://docs.microsoft.com/microsoftteams/how-can-caller-id-be-used-in-your-organization#end-user-control-of-outbound-caller-id)。
    - 将**来电显示替换**为：通过选择下列操作之一，设置要为用户显示的呼叫者 id：

        - **用户号码**：显示用户的号码。 
        - **服务号码**：允许您将服务电话号码设置为显示为呼叫方 ID。
        - **匿名**：以匿名方式显示呼叫方 ID。

    - **将呼叫方 Id 替换为此服务号码**：选择服务号码以替换用户的来电显示。 如果在 **"将呼叫方 ID 替换为**" 中选择了 "**服务编号**"，则此选项可用。

5. 单击“**保存**”。

## <a name="edit-a-caller-id-policy"></a>编辑呼叫者 ID 策略

你可以编辑全局策略或你创建的任何自定义策略。 

1. 在 Microsoft 团队管理中心的左侧导航中，转到 "**语音**  >  **呼叫者 ID 策略**"。
2. 通过单击策略名称左侧，然后单击 "**编辑**"，选择策略。
3. 更改所需的设置，然后单击 "**保存**"。

## <a name="assign-a-custom-caller-id-policy-to-users"></a>为用户分配自定义呼叫者 ID 策略

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a>相关主题

[新-CsCallingLineIdentity](https://docs.microsoft.com/powershell/module/skype/new-cscallinglineidentity?view=skype-ps)

[向团队中的用户分配策略](assign-policies.md)
