---
title: 为特定 Skype 业务联机用户禁用免费电话号码
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 管理员可以控制如何组织者可以为他们的会议使用免费电话号码。
ms.openlocfilehash: 1cd144af4f57b3c4ecb19de6c4aeea36f5d2baed
ms.sourcegitcommit: 6207b98e8395f6c640b61cfb3f6c85d96520e33b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2018
ms.locfileid: "22490542"
---
# <a name="disabling-toll-free-numbers-for-specific-skype-for-business-online-users"></a>为特定 Skype 业务联机用户禁用免费电话号码

> [!Note]
> 有关为团队用户禁用工具免费号码的信息，请参阅[特定的团队用户禁用免费电话号码](/MicrosoftTeams/disabling-toll-free-numbers-for-specific-teams-users)。

如果您的组织具有其 Microsoft 音频会议网桥中免费电话号码，您可以允许或阻止特定的组织者的会议中其使用情况。  

默认情况下，您的组织中的所有用户都启用使用免费电话号码，这意味着，这些号码，如果可用，可用于参与者加入他们的会议。 如果不为您的组织中的一些用户所需的行为，您可以限制特定用户在其通过免费电话号码启用控件的会议中使用这些号码。 

当给定管理器禁用免费电话号码： 
 - 免费电话号码将不再包括在他或她的会议邀请。 
 - 免费电话号码将不再列出其中引用的"查找本地号码"页上，或她的会议邀请。 
 - 参与者将无法加入给定组织者的会议，如果拨组织的任何免费电话号码。 
 - 将自动重新安排的组织者的所有会议，并将从其删除免费电话号码。  

    > [!IMPORTANT]
    > 这将向这些会议的所有参与者重新组织者的电子邮件邀请的所有发送。 

 - 参与者可以继续加入会议的组织者使用收费电话号码。 

## <a name="disabling-toll-free-numbers-for-specific-users"></a>禁用特定用户的免费电话号码 


1. 在**业务管理中心的 Skype**，在左侧导航窗格中，转到**音频会议** > **用户**，然后选择用户可用的用户列表。 

2. 在"操作"窗格中，单击" **编辑**"。 

3. 清除**允许使用免费电话号码加入此用户的会议**。 
 
4. 单击" **保存**"。 
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
 
**使用 PowerShell**  

您可以使用集 CsOnlineDialInConferencingUser cmdlet 的 AllowTollFreeDialIn 参数启用或禁用此控件。 例如： 

 - 设置 CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false
