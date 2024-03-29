---
title: 禁用特定 Skype for Business Online 用户的免费电话号码
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 管理员可以控制组织者如何使用他们会议的免费电话号码。
ms.openlocfilehash: 5ae82a1eef27793f700c50936e9dec37cd6c9ddd
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58587932"
---
# <a name="disabling-toll-free-numbers-for-specific-skype-for-business-online-users"></a>禁用特定 Skype for Business Online 用户的免费电话号码

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]
 
> [!Note]
> 有关禁用团队用户免费电话号码的信息，请参阅 [禁用特定的团队用户免费电话号码](/MicrosoftTeams/disabling-toll-free-numbers-for-specific-teams-users) 。

如果组织在其 Microsoft 音频会议网桥中拥有免费电话号码，可以在特定的组织者的会议中允许或阻止其使用免费电话号码。  

默认方式，组织中的所有用户均启用免费电话号码，这意味着，这些号码，如果可用，参会者可使用它们参加会议。 如果不希望组织中的某些用户可以这样参会，可以通过免费电话号码启用控件限制特定用户在其会议中使用这些号码。 

当针对某设定组织者禁用免费电话号码时： 
 - 免费电话号码将不再包含在他或她的会议邀请中。 
 - 免费电话号码将不再在"查找本地号码"页上列出，该页面在他或她的会议邀请中被引用。 
 - 参会者如果拨组织的任何免费电话号码，都将无法参加该设定组织者的会议。 
 - 将自动重新安排该组织者的所有会议，并将从其删除免费电话号码。  

    > [!IMPORTANT]
    > 因此将向这些会议的所有参与者重新发送该组织者的所有电子邮件邀请。 

 - 参会者可以继续使用收费电话号码参加该组织者的会议。 

## <a name="disabling-toll-free-numbers-for-specific-users"></a>禁用特定用户的免费电话号码 

从 **Microsoft Teams管理中心**：

1. 在左侧导航栏中， **单击"用户**"，然后从可用用户列表中选择用户。

2. 在 **音频会议** 旁边，单击 **编辑**。

3. 将 **"在此用户的会议请求中包括** 免费号码"设置为"**关闭"。** 

4. 单击" **保存"。** 
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
 
**使用 PowerShell**  

可以使用 Set-CsOnlineDialInConferencingUser cmdlet 的 AllowTollFreeDialIn 参数启用或禁用此控件。 例如： 

- Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false
