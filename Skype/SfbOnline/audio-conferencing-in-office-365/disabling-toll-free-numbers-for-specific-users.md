---
title: "禁用对特定用户的免费电话号码"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 02/23/2018
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "管理员可以控制如何组织者可以使用免费电话号码，为他们的会议。"
ms.openlocfilehash: fb4b0f8725608928e686307845871b4f5c1976d9
ms.sourcegitcommit: 997c03395fd1966607cef0df8ee884303401cd64
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2018
---
# <a name="disabling-toll-free-numbers-for-specific-users"></a>禁用对特定用户的免费电话号码

如果您的组织在其 Microsoft 音频会议桥有免费电话号码，您可以允许或阻止特定组织的会议中它们的用法。  

默认情况下，您的组织中的所有用户使用免费电话号码，意味着这些数字，如果可用，可以使用由参与者参加他们的会议都启用。 如果这不是您组织中的某些用户所需的行为，可以从免费电话的号码启用控件通过其会议中使用这些数字来限制特定用户。 

当给定组织禁用免费电话号码： 
 - 免费电话号码将不再包含在他或她的会议邀请。 
 - 免费电话号码将不再列出中他引用了"查找本地号码"页面上，或者她会议邀请。 
 - 参与者不能加入给定组织者的会议，如果他们拨组织任何免费电话号码。 
 - 将自动重新安排所有会议的组织者，和免费电话号码将它们从中删除。  

    > [!IMPORTANT]
    > 这将重新组织者的电子邮件邀请的所有发送给这些会议的所有参与者。 

 - 参与者可以继续参加会议的组织者使用免费电话号码。 

## <a name="disabling-toll-free-numbers-for-specific-users-using-the-skype-for-business-admin-center"></a>禁用对特定用户使用 Skype 业务管理中心的免费电话号码 
 1. Go to the **Office 365 admin center** > **Skype for Business**. 
 2. 在有关业务管理中心在左侧的导航中，Skype 转到**音频会议** > **用户**，然后选择可用的用户列表中用户。 
 3. 在"操作"窗格中，单击" **编辑**"。 
 4. 选中或清除**允许使用免费电话号码加入此用户的会议**。 
 5. 单击" **保存**"。 
 
## <a name="disabling-toll-free-numbers-for-specific-users-using-powershell"></a>禁用对特定用户使用 PowerShell 的免费电话号码  

可以使用一组 CsOnlineDialInConferencingUser cmdlet 的 AllowTollFreeDialIn 参数来启用或禁用此控件。 例如： 

 - 一组 CsOnlineDialInConferencingUser user@contoso.com-AllowTollFreeDialIn $false
