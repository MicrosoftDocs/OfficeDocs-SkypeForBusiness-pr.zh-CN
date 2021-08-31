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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: 了解如何为用户分配、更改或删除工作电话号码Teams以便外部企业和客户可以呼叫。
ms.openlocfilehash: 44254c8d8c8886e72b699c3890017a2b817cd135
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2021
ms.locfileid: "58727501"
---
# <a name="assign-change-or-remove-a-phone-number-for-a-user-calling-plans"></a>为呼叫计划用户分配、更改或删除 (电话号码) 

设置呼叫计划时，你向用户分配电话号码。 在Microsoft Teams，当用户单击"呼叫"时，将列出你 **分配的电话号码**。 有关在直接路由方案中为用户分配、更改或删除电话号码的说明，请参阅为用户启用直接路由、语音和 [语音邮件](./direct-routing-enable-users.md)。

![用户的电话号码显示在Teams。](media/teams-phone-number.png)

当您设置用户以便他们可以拨打和接听电话呼叫时，您必须首先使用 Microsoft Teams管理中心并分配电话号码。 如果需要，可以更改或删除电话号码。
  
若要了解如何在附加Teams套餐及其费用，请参阅Teams[附加许可。](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
  
> [!NOTE]
> 查看用户是否分配了许可证的一种方式是，在"用户"中Microsoft Teams管理>**许可证**。 如果分配了许可证，将在页面上指示该许可证。  也可使用Microsoft 365 管理中心。
  
## <a name="assign-a-phone-number-to-a-user"></a>向用户分配电话号码
 
![一个图标，显示Microsoft Teams徽标。](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**
    
1. 在左侧导航栏中，单击 **"语音**  >  **电话数字"。**
2. 在 **"电话"** 页面上，选择列表中的未分配号码，然后单击"编辑 **"。**  
3. 在"**编辑"** 窗格的 **"** 分配到"下，按显示名称或用户名搜索用户，然后单击"分配 **"。**
4. 若要分配或更改关联的紧急位置，请在"紧急位置"下搜索，然后选择该位置。
5. 根据是否要向用户发送包含其电话号码信息的电子邮件，请关闭或打开包含 **电话号码信息的电子邮件用户**。 默认情况下，此选项为"打开"。 
6. 单击“**保存**”。

有关 PowerShell 示例，请参阅[Set-CsOnlineVoiceUser。](/powershell/module/skype/set-csonlinevoiceuser)

> [!NOTE]
> 由于 Microsoft 365 或 Office 365 Teams 之间的延迟，用户最多可能需要 24 小时才能启用。 如果电话号码在 24 小时后未正确分配，请联系商业产品 [支持人员 - 管理员帮助](/microsoft-365/admin/contact-support-for-business-products)。 我们随时为你提供帮助！

  
## <a name="change-a-phone-number-for-a-user"></a>更改用户的电话号码
 
![一个图标，显示Microsoft Teams徽标。](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**
    
1. 在左侧导航中，单击"用户"，找到并双击用户，单击"帐户"，然后在"常规信息"下记下分配给用户的电话号码。 
2. 在左侧导航栏中，单击 **"语音**  >  **电话数字"。**
3. 在 **"电话"** 页面上，选择在步骤 1 中标识的数字，然后单击"编辑 **"。**  
4. 在" **编辑** "窗格的 **"分配到"下**，单击 **"X"** 以删除用户。
5. 单击“**保存**”。
6. 在 **"电话"** 页面上，选择列表中的未分配号码，然后单击"编辑 **"。**  
7. 在"**编辑"** 窗格的 **"** 分配到"下，按显示名称或用户名搜索用户，然后单击"分配 **"。**
8. 若要分配或更改关联的紧急位置，请在"紧急位置"下搜索，然后选择该位置。
9. 单击“**保存**”。

有关 PowerShell 示例，请参阅[Set-CsOnlineVoiceUser。](/powershell/module/skype/set-csonlinevoiceuser)

## <a name="remove-a-phone-number-from-a-user"></a>删除用户的电话号码
 
![一个图标，显示Microsoft Teams徽标。](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**

1. 在左侧导航中，单击"用户"，找到并双击用户，单击"帐户"，然后在"常规信息"下记下分配给用户的电话号码。 
2. 在左侧导航栏中，单击 **"语音**  >  **电话数字"。**
3. 在 **"电话"** 页上，选择在步骤 2 中标识的数字，然后单击"编辑 **"。**  
4. 在" **编辑** "窗格的 **"分配到"下**，单击 **"X"** 以删除用户。
5. 单击“**保存**”。

有关 PowerShell 示例，请参阅[Set-CsOnlineVoiceUser。](/powershell/module/skype/set-csonlinevoiceuser)

## <a name="related-topics"></a>相关主题

[什么是地址验证？](/skypeforbusiness/what-are-calling-plans-in-office-365/what-is-address-validation)

[管理你的组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization)

[紧急呼叫条款和条件](./emergency-calling-terms-and-conditions.md)

[紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser)

[呼叫套餐Microsoft 365](./calling-plans-for-office-365.md)
