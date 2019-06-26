---
title: 使用在线连接器管理用户帐户
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
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
description: 使用 Windows PowerShell 中的 CsOnlineUser cmdlet 获取有关你的组织的 Skype for Business Online 用户的信息。
ms.openlocfilehash: 02f3aa50f2256cd0d58f4c53cfa607c011bfa565
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/25/2019
ms.locfileid: "35221770"
---
# <a name="manage-user-accounts-using-the-online-connector"></a>使用在线连接器管理用户帐户

## <a name="manage-user-accounts"></a>管理用户帐户

本主题包括以下部分：

- [返回有关所有 Lync Online 用户的信息](manage-user-accounts-using-the-online-connector.md#BKAllUsers)

- [在 Skype for Business Online 中返回特定用户的信息](manage-user-accounts-using-the-online-connector.md#BKSpecificUser)

- [为 Skype for Business Online 中的特定用户返回特定信息](manage-user-accounts-using-the-online-connector.md#BKSpecificUsers)

- [在 Skype for Business Online 中返回筛选的用户列表](manage-user-accounts-using-the-online-connector.md#BKListofUsers)

> [!NOTE]
> **Move-csuser** cmdlet 还包含在适用于 Skype For business Online 管理员的 cmdlet 组中。 但是, **move-csuser**当前无法用于管理 Skype For business Online, 除非设置_AudioVideoDisabled_参数。 如果你尝试使用任何其他参数运行 cmdlet, 它将失败, 并出现类似于以下内容的错误消息: 无法设置 "SipAddress"。 此参数在远程租户 PowerShell 中受限制。

### <a name="return-information-about-all-your-skype-for-business-online-users"></a>返回有关所有 Lync Online 用户的信息
<a name="BKAllUsers"> </a>

若要返回有关已针对 Skype for Business Online 启用的所有用户的信息, 请调用[CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet, 不要使用任何其他参数。

```
Get-CsOnlineUser
```

若要返回单个随机选定用户 (例如, 将此帐户用于测试目的) 的信息, 请调用**CsOnlineUser** cmdlet 并将_ResultSize_参数设置为1。

```
Get-CsOnlineUser -ResultSize 1
```

这将导致**CsOnlineUser** cmdlet 仅为一个用户返回信息, 而不管你的组织中有多少个用户。 若要返回五个用户的信息, 请将_ResultSize_参数的值设置为5。

```
Get-CsOnlineUser -ResultSize 5
```

### <a name="return-information-for-a-specific-user-in-skype-for-business-online"></a>在 Skype for Business Online 中返回特定用户的信息
<a name="BKSpecificUser"> </a>

调用[CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet 时, 有多种方法可以引用特定用户帐户。 你可以使用用户的 Active Directory 域服务 (AD DS) 显示名称。

```
Get-CsOnlineUser -Identity "Ken Myer"
```

您可以使用用户的 SIP 地址。

```
Get-CsOnlineUser -Identity "sip:kenmyer@litwareinc.com"
```

你可以使用用户的用户主体名称 (UPN)。

```
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

### <a name="return-specific-information-for-specific-users-in-skype-for-business-online"></a>为 Skype for Business Online 中的特定用户返回特定信息
<a name="BKSpecificUsers"> </a>

默认情况下, [CsOnlineUser](https://technet.microsoft.com/library/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx) cmdlet 为每个 Skype For business Online 用户帐户返回大量信息。 如果你仅对该信息的子集感兴趣, 请将返回的数据输送到**Select 对象**cmdlet。 例如, 此命令返回用户 Ken Myer 的所有数据, 然后使用**Select 对象**cmdlet 将显示在屏幕上的信息限制在屏幕上显示为 KEN 的广告 DS 的 "显示名称" 和 "拨号计划"。

```
Get-CsOnlineUser -Identity "Ken Myer" | Select-Object DisplayName, DialPlan
```

以下命令返回所有用户的显示名称和拨号计划。

```
Get-CsOnlineUser | Select-Object DisplayName, DialPlan
```

若要查找 Skype for Business Online 用户帐户的属性, 请使用以下命令。

```
Get-CsOnlineUser | Get-Member
```

### <a name="return-a-filtered-list-of-users-in-skype-for-business-online"></a>在 Skype for Business Online 中返回筛选的用户列表
<a name="BKListofUsers"> </a>

通过使用[CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) Cmdlet 和_LdapFilter_或_Filter_参数, 你可以轻松地返回有关一组目标用户的信息。 例如, 此命令返回在财务部门工作的所有用户。

```
Get-CsOnlineUser -LdapFilter "department=Finance"
```

## <a name="related-topics"></a>相关主题
[使用 Windows PowerShell 为 skype for business online 管理设置计算机](set-up-your-computer-for-windows-powershell.md)


