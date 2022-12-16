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
description: 了解如何为 Teams 用户分配、更改或删除工作电话号码，以便外部企业和客户端可以呼叫。
ms.openlocfilehash: 0dd126f3aa19e0b65b7a0c789f769cef1803f8c8
ms.sourcegitcommit: 321de0e5d8846caaaab944826f6ca06394e707ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/16/2022
ms.locfileid: "69414680"
---
# <a name="assign-change-or-remove-a-phone-number-for-a-user"></a>为用户分配、更改或删除电话号码

设置通话套餐、运营商连接或 Teams 电话移动版时，可以向用户分配电话号码。 在 Microsoft Teams 中，当用户单击“**呼叫**”时，将列出你分配的电话号码。

本文适用于通话套餐、运营商连接和 Teams 电话移动版。 有关在直接路由方案中为用户分配、更改或删除电话号码的信息，请参阅 [为用户启用直接路由、语音和语音邮件](./direct-routing-enable-users.md)。

在为通话套餐、运营商连接或 Teams 电话移动用户分配号码之前，必须获取用户的号码。 有关详细信息，请参阅 [获取通话套餐用户的号码](getting-phone-numbers-for-your-users.md)、 [为 Operator Connect 用户设置号码](operator-connect-configure.md#set-up-phone-numbers)或 [为 Teams Phone Mobile 用户设置号码](operator-connect-mobile-configure.md)。

> [!NOTE]
> 查看用户是否分配了许可证的一种方法是转到 Microsoft Teams 管理中心>**用户**。 如果分配了许可证，则会在页面上指示该许可证。  还可以使用 Microsoft 365 管理中心。

> [!NOTE]
> 此说明适用于使用本地 Active Directory进行混合部署的客户。 如果要将通话套餐或运营商连接电话号码分配给用户或资源帐户，必须确保已删除本地 Active Directory中用户或资源帐户对象的 msRTCSIP-Line 属性中存储的任何电话号码，并且更改已同步到 Microsoft 365。

## <a name="assign-a-phone-number-to-a-user"></a>向用户分配电话号码

向用户分配电话号码时，请确保用户的电话号码和使用位置位于同一国家/地区。

若要使用 Teams 管理中心分配号码，请执行以下操作：

[!INCLUDE [assign-phone-numbers-to-users-steps](./includes/assign-phone-numbers-to-users-steps.md)]


若要使用 PowerShell 分配号码，请使用 [Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment) cmdlet，如下所示：

对于通话套餐号码：

```PowerShell
Set-CsPhoneNumberAssignment -Identity <user> -PhoneNumber <phone number> -PhoneNumberType CallingPlan
```

对于 Operator Connect 号码：

```PowerShell
Set-CsPhoneNumberAssignment -Identity <user> -PhoneNumber <phone number> -PhoneNumberType OperatorConnect
```

对于 Teams 电话移动电话号码：

```PowerShell
Set-CsPhoneNumberAssignment -Identity <user> -PhoneNumber <phone number> -PhoneNumberType OCMobile
```

例如：

```PowerShell
Set-CsPhoneNumberAssignment -Identity john@contoso.com -PhoneNumber "+14255550101" -PhoneNumberType CallingPlan
Set-CsPhoneNumberAssignment -Identity jack@contoso.com -PhoneNumber "+14255550102" -PhoneNumberType OperatorConnect
Set-CsPhoneNumberAssignment -Identity jack@contoso.com -PhoneNumber "+14255550103" -PhoneNumberType OCMobile
```

> [!NOTE]
> 由于 Microsoft 365 和 Teams 之间存在延迟，因此可能需要长达 24 小时才能启用用户。 如果在 24 小时后未正确分配电话号码，请参阅 [电话号码服务中心](https://pstnsd.powerappsportals.com/)。

> [!NOTE]
> 分配电话号码时，EnterpriseVoiceEnabled 标志会自动设置为 True。

## <a name="change-a-phone-number-for-a-user"></a>更改用户的电话号码

若要使用 Teams 管理中心更改用户的电话号码，请执行以下操作：

1. 在左侧导航中，单击“ **用户**”，找到并双击所需用户，单击“ **帐户**”，然后在“ **常规信息**”下记下分配给用户的电话号码。

2. 在左侧导航栏中，单击“ **语音** \> **电话号码**”。

3. 在“ **电话号码** ”页上，选择在步骤 1 中标识的号码，然后单击“ **编辑**”。

4. 在 **“编辑** ”窗格中的“ **分配到**”下，单击 **“X** ”以删除该用户。

5. 单击“**保存**”。

6. 在“ **电话号码** ”页上，在列表中选择未分配的号码，然后单击“ **编辑**”。

7. 在 **“编辑** ”窗格中的“ **分配到**”下，按显示名称或用户名搜索用户，然后单击“ **分配**”。

8. 若要分配或更改关联的紧急位置，请在 **“紧急位置”** 下搜索并选择位置。

      > [!NOTE]
      > 如果要更改 Operator Connect 或 Teams Phone Mobile 用户的号码，则可能无法分配或更改关联的紧急位置。 此功能将取决于操作员。 有关详细信息，请联系操作员。

9. 单击“**保存**”。

有关 PowerShell 示例，请参阅 [Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment)。

## <a name="remove-a-phone-number-from-a-user"></a>从用户中删除电话号码

若要使用 Teams 管理中心删除电话号码，请执行以下操作：

1. 在左侧导航中，单击“ **用户**”，找到并双击所需用户，单击“ **帐户**”，然后在“ **常规信息**”下记下分配给用户的电话号码。

2. 在左侧导航栏中，单击“ **语音** \> **电话号码**”。

3. 在“ **电话号码** ”页上，选择在步骤 2 中标识的号码，然后单击“ **编辑**”。

4. 在 **“编辑** ”窗格中的“ **分配到**”下，单击 **“X** ”以删除该用户。

5. 单击“**保存**”。

有关 PowerShell 示例，请参阅 [Remove-CsPhoneNumberAssignment](/powershell/module/teams/remove-csphonenumberassignment)。

## <a name="related-topics"></a>相关主题

[什么是地址验证？](/skypeforbusiness/what-are-calling-plans-in-office-365/what-is-address-validation)

[管理组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization)

[紧急呼叫条款和条件](./emergency-calling-terms-and-conditions.md)

[紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment)

[Remove-CsPhoneNumberAssignment](/powershell/module/teams/remove-csphonenumberassignment)
