---
title: 使用联机连接器管理用户帐户
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: a226b0d4-6359-42b8-808d-4b8ab3736d3b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: 使用 Get-CsOnlineUser 中的 Windows PowerShell cmdlet 获取有关组织 Skype for Business Online 用户的信息。
ms.openlocfilehash: 6f5caf9df905364c078226501d880db5271db92f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58590596"
---
# <a name="manage-user-accounts-using-the-online-connector"></a>使用联机连接器管理用户帐户

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

## <a name="manage-user-accounts"></a>管理用户帐户

本主题包括以下部分：

- [返回有关所有 Lync Online 用户的信息](manage-user-accounts-using-the-online-connector.md#BKAllUsers)

- [返回 Skype for Business Online 中特定用户的信息](manage-user-accounts-using-the-online-connector.md#BKSpecificUser)

- [在 Skype for Business Online 中返回特定用户的特定信息](manage-user-accounts-using-the-online-connector.md#BKSpecificUsers)

- [返回 Skype for Business Online 中的已筛选用户列表](manage-user-accounts-using-the-online-connector.md#BKListofUsers)

> [!NOTE]
> **Set-CsUser** cmdlet 也包含在可供联机管理员Skype for Business cmdlet 集。 但是 **，Set-CsUser** 当前不能用于管理 Skype for Business Online，但 _设置 AudioVideoDisabled_ 参数除外。 如果尝试使用任何其他参数运行 cmdlet，它将失败，并出现类似于以下错误消息：无法设置"SipAddress"。 此参数在远程租户 PowerShell 中受到限制。

### <a name="return-information-about-all-your-skype-for-business-online-users"></a>返回有关所有 Lync Online 用户的信息
<a name="BKAllUsers"> </a>

若要返回有关已启用 Skype for Business Online 的所有用户的信息，请调用[Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) cmdlet，而无需任何其他参数。

```PowerShell
Get-CsOnlineUser
```

若要返回单个随机选择的用户 (的信息，例如，若要使用此帐户进行测试) ，请调用 **Get-CsOnlineUser** cmdlet，将 _ResultSize_ 参数设置为 1。

```PowerShell
Get-CsOnlineUser -ResultSize 1
```

这会导致 **Get-CsOnlineUser** cmdlet 仅返回一个用户的信息，而不考虑组织中有多少用户。 若要返回五个用户的信息，将 _ResultSize_ 参数的值设置为 5。

```PowerShell
Get-CsOnlineUser -ResultSize 5
```

### <a name="return-information-for-a-specific-user-in-skype-for-business-online"></a>返回 Skype for Business Online 中特定用户的信息
<a name="BKSpecificUser"> </a>

调用 [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) cmdlet 时，有多种方法可引用特定用户帐户。 可以使用用户的 Active Directory 域服务 (AD DS) 显示名称。

```PowerShell
Get-CsOnlineUser -Identity "Ken Myer"
```

可以使用用户的 SIP 地址。

```PowerShell
Get-CsOnlineUser -Identity "sip:kenmyer@litwareinc.com"
```

可以使用用户的用户主体名称 (UPN) 。

```PowerShell
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

### <a name="return-specific-information-for-specific-users-in-skype-for-business-online"></a>在 Skype for Business Online 中返回特定用户的特定信息
<a name="BKSpecificUsers"> </a>

默认情况下[，Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) cmdlet 会针对每个 Skype for Business 用户帐户返回大量信息。 如果只对该信息的子集感兴趣，请通过管道将返回的数据通过管道返回到 **Select-Object** cmdlet。 例如，此命令返回用户 Ken Myer 的所有数据，然后使用 **Select-Object** cmdlet 将屏幕上显示的信息限制为 Ken 的 AD DS 显示名称和拨号计划。

```PowerShell
Get-CsOnlineUser -Identity "Ken Myer" | Select-Object DisplayName, DialPlan
```

以下命令返回显示名称的拨号和拨号计划。

```PowerShell
Get-CsOnlineUser | Select-Object DisplayName, DialPlan
```

若要查找 Skype for Business Online 用户帐户的属性，请使用以下命令。

```PowerShell
Get-CsOnlineUser | Get-Member
```

### <a name="return-a-filtered-list-of-users-in-skype-for-business-online"></a>返回 Skype for Business Online 中的已筛选用户列表
<a name="BKListofUsers"> </a>

通过使用 [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) cmdlet 和 _LdapFilter_ 或 _Filter_ 参数，可以轻松返回有关一组目标用户的信息。 例如，此命令返回财务部门中的所有用户。

```PowerShell
Get-CsOnlineUser -LdapFilter "department=Finance"
```

## <a name="related-topics"></a>相关主题
[使用 skype for business Online 管理设置Windows PowerShell](set-up-your-computer-for-windows-powershell.md)
