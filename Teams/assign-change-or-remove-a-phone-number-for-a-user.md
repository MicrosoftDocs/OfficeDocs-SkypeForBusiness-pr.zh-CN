---
title: 为用户分配、更改或删除电话号码
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 91089761-cb87-4119-885b-3713840dd9f7
ms.tgt.pltfrm: cloud
audience: admin
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: 了解如何为 Teams 用户分配、更改或删除工作电话号码，以便外部企业和客户可以呼叫。
ms.openlocfilehash: e606885aee1e87dfdfc9b36a5247eedba225a185
ms.sourcegitcommit: 91fbc7c9cd43c2a5b7e6dfedf2388939f2f77d57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2021
ms.locfileid: "50589616"
---
# <a name="assign-change-or-remove-a-phone-number-for-a-user-calling-plans"></a>为呼叫计划用户分配、更改或删除 (电话号码) 

设置呼叫计划时，会向用户分配电话号码。 在 Microsoft Teams 中，当用户单击"呼叫"时，将列出你分配 **的电话号码**。 有关在直接路由方案中为用户分配、更改或删除电话号码的说明，请参阅"为用户启用直接路由、语音和[语音邮件"。](https://docs.microsoft.com/microsoftteams/direct-routing-enable-users)

![Teams 中显示的用户电话号码。](media/teams-phone-number.png)

设置用户以便他们可以拨打和接听电话呼叫时，必须先使用 Microsoft Teams 管理中心并分配电话号码。 如果需要，可以更改或删除电话号码。
  
若要了解如何在 Teams 中获取通话套餐及其费用，请参阅 [Teams 附加许可](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)。
  
> [!NOTE]
> 查看用户是否分配了许可证的一种方式是，通过访问 Microsoft Teams 管理中心> **用户**。 如果分配了许可证，将在页面上指示该许可证。  您也可以使用 Microsoft 365 管理中心。
  
## <a name="assign-a-phone-number-to-a-user"></a>向用户分配电话号码
 
![一个显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**
    
1. 在左侧导航栏中，单击 **"语音**  >  **电话号码"。**
2. 在 **"电话号码"** 页面上，选择列表中的未分配号码，然后单击"编辑 **"。**  
3. 在"**编辑"****窗格的"** 分配到"下，按显示名称或用户名搜索用户，然后单击"分配 **"。**
4. 若要分配或更改关联的紧急位置，请在"紧急位置"下搜索并选择该位置。
5. 根据是否要向用户发送包含其电话号码信息的电子邮件，请关闭或打开包含电话号码 **信息的电子邮件用户**。 默认情况下，此选项为打开状态。 
6. 单击“**保存**”。

有关 PowerShell 示例，请参阅[Set-CsOnlineVoiceUser。](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps)

    > [!NOTE]
    > Because of the latency between Microsoft 365 or Office 365 and Teams, it can take up to 24 hours for users to be enabled. If the phone number isn't assigned correctly after 24 hours, [contact support for business products - Admin Help](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products). We're here to help!

  
## <a name="change-a-phone-number-for-a-user"></a>更改用户的电话号码
 
![一个显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**
    
1. 在左侧导航中，单击"用户"，找到并双击用户，单击"帐户"，然后在"常规信息"下记下分配给用户的电话号码。 
2. 在左侧导航栏中，单击 **"语音**  >  **电话号码"。**
3. 在"**电话号码"** 页面上，选择在步骤 1 中标识的号码，然后单击"编辑 **"。**  
4. 在" **编辑"** 窗格的 **"分配到"下**，单击 **"X"** 以删除用户。
5. 单击“**保存**”。
6. 在 **"电话号码"** 页面上，选择列表中的未分配号码，然后单击"编辑 **"。**  
7. 在"**编辑"****窗格的"** 分配到"下，按显示名称或用户名搜索用户，然后单击"分配 **"。**
8. 若要分配或更改关联的紧急位置，请在"紧急位置"下搜索并选择该位置。
9. 单击“**保存**”。

有关 PowerShell 示例，请参阅[Set-CsOnlineVoiceUser。](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps)

## <a name="remove-a-phone-number-from-a-user"></a>删除用户的电话号码
 
![一个显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**

1. 在左侧导航中，单击"用户"，找到并双击用户，单击"帐户"，然后在"常规信息"下记下分配给用户的电话号码。 
2. 在左侧导航栏中，单击 **"语音**  >  **电话号码"。**
3. 在"**电话号码"** 页面上，选择在步骤 2 中标识的号码，然后单击"编辑 **"。**  
4. 在" **编辑"** 窗格的 **"分配到"下**，单击 **"X"** 以删除用户。
5. 单击“**保存**”。

有关 PowerShell 示例，请参阅[Set-CsOnlineVoiceUser。](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps)

## <a name="related-topics"></a>相关主题

[什么是地址验证？](/skypeforbusiness/what-are-calling-plans-in-office-365/what-is-address-validation)

[管理你的组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization)

[紧急呼叫条款和条件](/microsoftteams/emergency-calling-terms-and-conditions)

[紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[Set-CsOnlineVoiceUser](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps)

[调用 Microsoft 365 计划](https://docs.microsoft.com/MicrosoftTeams/calling-plans-for-office-365)
