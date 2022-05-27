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
description: 了解如何为Teams用户分配、更改或删除工作电话号码，以便外部企业和客户端可以呼叫。
ms.openlocfilehash: dc616425b4dce35a2a40179e0ee4a56d31bae12b
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676484"
---
# <a name="assign-change-or-remove-a-phone-number-for-a-user"></a>为用户分配、更改或删除电话号码

设置通话套餐或运营商连接时，可将电话号码分配给用户。 在Microsoft Teams中，当用户单击 **“呼叫**”时，将列出你分配的电话号码。

本文适用于通话套餐和运营商连接。 有关在直接路由方案中从用户分配、更改或删除电话号码的信息，请参阅 [“为用户启用直接路由”、“语音”和“语音邮件](./direct-routing-enable-users.md)”。

为呼叫计划或运营商连接用户分配号码之前，必须为用户获取号码。 有关详细信息，请参阅[“获取呼叫计划用户的号码](getting-phone-numbers-for-your-users.md)”或[为运营商连接用户设置号码](operator-connect-configure.md#set-up-phone-numbers)。

> [!NOTE]
> 查看用户是否分配了许可证的一种方法是转到Microsoft Teams管理中心>**用户**。 如果分配了许可证，则会在页面上指示该许可证。  还可以使用Microsoft 365 管理中心。

> [!NOTE]
> 此说明适用于具有带本地 Active Directory的混合部署的客户。 如果要将通话套餐或运营商连接电话号码分配给用户或资源帐户，则必须确保已删除存储在本地 Active Directory中用户或资源帐户对象的 msRTCSIP-Line 属性中的任何电话号码，并且更改已同步到Microsoft 365。

## <a name="assign-a-phone-number-to-a-user"></a>向用户分配电话号码

将电话号码分配给用户时，请确保该用户的电话号码和使用位置位于同一国家/地区。

使用Teams管理中心分配数字：

1. 在左侧导航栏中，单击 **“语音** > **电话数字**。

2. 在 **电话数字** 页上，在列表中选择一个未分配的数字，然后单击 **“编辑**”。

3. 在 **“编辑** ”窗格的 **“分配到**”下，按显示名称或用户名搜索用户，然后单击 **“分配**”。

4. 若要分配或更改关联的紧急位置，请在 **“紧急”位置** 下搜索，然后选择该位置。

   > [!NOTE]
   > 如果要将数字分配给运营商连接用户，则可能或可能无法分配或更改关联的紧急位置。 此功能将取决于运算符。 有关详细信息，请与操作员联系。

5. 根据是否要使用其电话号码信息向用户发送电子邮件，请关闭或打开 **包含电话号码信息的电子邮件用户**。 默认情况下，此操作处于打开状态。
6. 单击“**保存**”。

若要使用 PowerShell 分配数字，请使用 [Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment) cmdlet，如下所示：

对于呼叫计划号码：

```PowerShell
Set-CsPhoneNumberAssignment -Identity <user> -PhoneNumber <phone number> -PhoneNumberType CallingPlan
```

对于运营商连接数字：

```PowerShell
Set-CsPhoneNumberAssignment -Identity <user> -PhoneNumber <phone number> -PhoneNumberType OperatorConnect
```

例如：

```PowerShell
Set-CsPhoneNumberAssignment -Identity john@contoso.com -PhoneNumber "+14255550101" -PhoneNumberType CallingPlan
Set-CsPhoneNumberAssignment -Identity jack@contoso.com -PhoneNumber "+14255550102" -PhoneNumberType OperatorConnect
```

> [!NOTE]
> 由于Microsoft 365和Teams之间的延迟，最多可能需要 24 小时才能启用用户。 如果 24 小时后未正确分配电话号码，请[参阅电话号码服务中心](https://pstnsd.powerappsportals.com/)。

## <a name="change-a-phone-number-for-a-user"></a>更改用户的电话号码

若要使用Teams管理中心更改用户的电话号码：

1. 在左侧导航栏中，单击 **“用户**”，找到并双击所需的用户，单击 **“帐户**”，然后在“ **常规信息**”下记下分配给用户的电话号码。

2. 在左侧导航栏中，单击 **“语音** \> **电话数字**。

3. 在 **电话数字** 页上，选择在步骤 1 中标识的数字，然后单击 **“编辑**”。

4. 在 **“编辑** ”窗格中的 **“分配到**”下，单击 **X** 以删除用户。

5. 单击“**保存**”。

6. 在 **电话数字** 页上，在列表中选择一个未分配的数字，然后单击 **“编辑**”。

7. 在 **“编辑** ”窗格的 **“分配到**”下，按显示名称或用户名搜索用户，然后单击 **“分配**”。

8. 若要分配或更改关联的紧急位置，请在 **“紧急”位置** 下搜索，然后选择该位置。

      > [!NOTE]
      > 如果要更改运营商连接用户的数字，则可能或无法分配或更改关联的紧急位置。 此功能将取决于运算符。 有关详细信息，请与操作员联系。

9. 单击“**保存**”。

有关 PowerShell 示例，请参阅 [Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment)。

## <a name="remove-a-phone-number-from-a-user"></a>从用户中删除电话号码

若要使用Teams管理中心删除电话号码：

1. 在左侧导航栏中，单击 **“用户**”，找到并双击所需的用户，单击 **“帐户**”，然后在“ **常规信息**”下记下分配给用户的电话号码。

2. 在左侧导航栏中，单击 **“语音** \> **电话数字**。

3. 在 **电话数字** 页上，选择在步骤 2 中标识的数字，然后单击 **“编辑**”。

4. 在 **“编辑** ”窗格中的 **“分配到**”下，单击 **X** 以删除用户。

5. 单击“**保存**”。

有关 PowerShell 示例，请参阅 [Remove-CsPhoneNumberAssignment](/powershell/module/teams/remove-csphonenumberassignment)。

## <a name="related-topics"></a>相关主题

[什么是地址验证？](/skypeforbusiness/what-are-calling-plans-in-office-365/what-is-address-validation)

[管理组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization)

[紧急呼叫条款和条件](./emergency-calling-terms-and-conditions.md)

[紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment)

[Remove-CsPhoneNumberAssignment](/powershell/module/teams/remove-csphonenumberassignment)
