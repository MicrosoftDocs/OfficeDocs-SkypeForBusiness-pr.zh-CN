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
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 管理员可以控制组织者如何使用他们会议的免费电话号码。
ms.openlocfilehash: 541398a760f41effc37e802cafde1141acca2d57
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34306086"
---
# <a name="disabling-toll-free-numbers-for-specific-skype-for-business-online-users"></a>禁用特定 Skype for Business Online 用户的免费电话号码
 
> [!Note]
> 有关禁用团队用户免费电话号码的信息，请参阅 [禁用特定的团队用户免费电话号码](/MicrosoftTeams/disabling-toll-free-numbers-for-specific-teams-users) 。

如果组织在其 Microsoft 音频会议网桥中拥有免费电话号码，可以在特定的组织者的会议中允许或阻止其使用免费电话号码。  

By default, all users in your organization are enabled for using toll-free numbers, meaning that those numbers, if available, can be used by participants to join their meetings. If this is not the desired behavior for some users in your organization, you can restrict specific users from using those numbers in their meetings via a toll-free number enablement control. 

当针对某设定组织者禁用免费电话号码时： 
 - 免费电话号码将不再包含在他或她的会议邀请中。 
 - 免费电话号码将不再在"查找本地号码"页上列出，该页面在他或她的会议邀请中被引用。 
 - 参会者如果拨组织的任何免费电话号码，都将无法参加该设定组织者的会议。 
 - 将自动重新安排该组织者的所有会议，并将从其删除免费电话号码。  

    > [!IMPORTANT]
    > 因此将向这些会议的所有参与者重新发送该组织者的所有电子邮件邀请。 

 - 参会者可以继续使用收费电话号码参加该组织者的会议。 

## <a name="disabling-toll-free-numbers-for-specific-users"></a>为特定用户禁用免费电话号码 

从**Microsoft 团队管理中心**:

1. 在左侧导航中, 单击 "**用户**", 然后从可用用户列表中选择用户。

2. 在**音频会议**旁边，单击**编辑**。

3. 设置**包括来自此用户的会议请求中**的免费电话号码****。 

4. 单击 "**保存"。** 
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
 
**使用 PowerShell**  

可以使用 Set-CsOnlineDialInConferencingUser cmdlet 的 AllowTollFreeDialIn 参数启用或禁用此控件。 例如： 

- Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false
