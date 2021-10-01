---
title: 为用户分配、更改或删除电话号码
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: davelick, roykuntz, jastark
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
ms.openlocfilehash: a6e2c8075134817b61d99366633f29140599b447
ms.sourcegitcommit: cfc48dc03550c093c4405fb5984648188f523699
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2021
ms.locfileid: "60046178"
---
# <a name="assign-change-or-remove-a-phone-number-for-a-user"></a>为用户分配、更改或删除电话号码

当您设置呼叫计划或接线 **员连接，** 您可以为用户分配电话号码。 在Microsoft Teams，当用户单击"呼叫"时，将列出你 **分配的电话号码**。 

**本文适用于呼叫计划和运营商连接。** 有关在直接路由方案中为用户分配、更改或删除电话号码的信息，请参阅为用户启用直接路由、语音和 [语音邮件](./direct-routing-enable-users.md)。

**为呼叫计划或接线员分配号码连接，必须获取用户的号码。有关详细信息，请参阅获取 [呼叫计划用户的](getting-phone-numbers-for-your-users.md)号码或为"接线员"连接 [号码](operator-connect-configure.md#set-up-phone-numbers)。**

  
> [!NOTE]
> 查看用户是否分配了许可证的一种方式是，在"用户"中Microsoft Teams管理 **>"**。 如果分配了许可证，将在页面上指示该许可证。  也可使用Microsoft 365 管理中心。
  
## <a name="assign-a-phone-number-to-a-user"></a>向用户分配电话号码

若要使用管理中心分配Teams号码：
    
1. 在左侧导航栏中，单击 **"语音**  >  **电话数字"。**

2. 在 **"电话"** 页面上，选择列表中的未分配号码，然后单击"编辑 **"。**  

3. 在"**编辑"** 窗格的"分配到"下，按显示名称或用户名搜索用户，然后单击"分配 **"。**

4. 若要分配或更改关联的紧急位置，请在"紧急位置"下搜索，然后选择该位置。

   > [!NOTE]
   > **如果要将号码分配给接线员连接用户，则可能无法分配或更改关联的紧急位置。此功能将取决于操作员。有关详细信息，请与接线员联系。**

5. 根据是否要向用户发送包含其电话号码信息的电子邮件，请关闭或打开包含 **电话号码信息的电子邮件用户**。 默认情况下，此选项为"打开"。 

6. 单击“**保存**”。

若要使用 PowerShell 分配数字，请使用 [Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser) cmdlet，如下所示：


'''PowerShell Set-CsOnlineVoiceUser -Identity <user>   -TelephoneNumber <phone number> 
```

For example:

```PowerShell
Set-CsOnlineVoiceUser -Identity john@contoso.com -TelephoneNumber +14255550101
```

> [!NOTE]
> 由于 Microsoft 365 和 Teams 之间的延迟，最多可能需要 24 小时才能启用用户。 如果电话号码在 24 小时后未正确分配，请参阅电话[号码服务中心"。](https://pstnsd.powerappsportals.com/) 

  
## <a name="change-a-phone-number-for-a-user"></a>更改用户的电话号码

若要使用管理中心更改用户Teams电话号码：
    
1. 在左侧导航中，单击"用户"，找到并双击用户，单击"帐户"，然后在"常规信息"下记下分配给用户的电话号码。 

2. 在左侧导航栏中，单击 **"语音**  >  **电话数字"。**

3. 在 **"电话"** 页上，选择在步骤 1 中标识的数字，然后单击"编辑 **"。**  

4. 在" **编辑** "窗格的 **"分配到"下**，单击 **"X"** 以删除用户。

5. 单击“**保存**”。

6. 在 **"电话"** 页面上，选择列表中的未分配号码，然后单击"编辑 **"。**  

7. 在"**编辑"** 窗格的"分配到"下，按显示名称或用户名搜索用户，然后单击"分配 **"。**

8. 若要分配或更改关联的紧急位置，请在"紧急位置"下搜索，然后选择该位置。

      > [!NOTE]
      > **如果要更改接线员连接号码，则可能无法分配或更改关联的紧急位置。此功能将取决于操作员。有关详细信息，请与接线员联系。**

9. 单击“**保存**”。

有关 PowerShell 示例，请参阅[Set-CsOnlineVoiceUser。](/powershell/module/skype/set-csonlinevoiceuser)

## <a name="remove-a-phone-number-from-a-user"></a>删除用户的电话号码

若要使用管理中心删除Teams电话号码：

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

