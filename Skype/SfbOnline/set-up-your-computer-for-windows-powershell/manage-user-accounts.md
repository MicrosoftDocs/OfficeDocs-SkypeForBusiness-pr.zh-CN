---
title: 管理用户帐户
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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
description: Windows PowerShell 中使用 Get-csonlineuser cmdlet 以获取有关您组织的 Skype 针对业务 Online 用户信息。
ms.openlocfilehash: 8f6ca618925b070e1d42a215cb9afb076a1e8197
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881404"
---
# <a name="manage-user-accounts"></a>管理用户帐户

## <a name="manage-user-accounts"></a>管理用户帐户

本主题包括以下部分：

- [返回有关所有 Lync Online 用户的信息](manage-user-accounts.md#BKMKReturnInfoAboutAllUsers)

- [返回业务 online 的 Skype 中的特定用户的信息](manage-user-accounts.md#BKMKReturnInfoSpecificUser)

- [返回业务 online 的 Skype 中的特定用户的特定信息](manage-user-accounts.md#BKMKReturninfoSpecificUsers)

- [返回业务 online 的 Skype 中的用户的已筛选的列表](manage-user-accounts.md#BKMKReturnFilteredListofUsers)

> [!NOTE]
> Skype 到业务 Online 管理员可用的 cmdlet 集，也包含**Set-csuser** cmdlet。 但是， **Set-csuser** ，当前不用来管理 Skype 业务 online，除_AudioVideoDisabled_参数设置。 如果您尝试运行带有任何其他参数的 cmdlet，它将与类似如下的错误消息失败： 无法设置"SipAddress"。 此参数是远程租户 PowerShell 内受限制。

### <a name="return-information-about-all-your-skype-for-business-online-users"></a>返回有关所有 Lync Online 用户的信息
<a name="BKMKReturnInfoAboutAllUsers"> </a>

若要返回所有已启用的 Skype 业务 online 您用户的信息，请调用不带任何其他参数[Get-csonlineuser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet。

```
Get-CsOnlineUser
```

若要返回单个、 随机选择用户 （例如，要用于测试此帐户） 的信息，请调用**Get-csonlineuser** cmdlet，并将_ResultSize_参数设置为 1。

```
Get-CsOnlineUser -ResultSize 1
```

它使**Get-csonlineuser** cmdlet 返回仅仅对一个用户，无论您的组织中有多少用户的信息。 要返回的五个用户的信息，请设置为 5 _ResultSize_参数的值。

```
Get-CsOnlineUser -ResultSize 5
```

### <a name="return-information-for-a-specific-user-in-skype-for-business-online"></a>返回业务 online 的 Skype 中的特定用户的信息
<a name="BKMKReturnInfoSpecificUser"> </a>

有多种方法的调用[Get-csonlineuser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet 时引用特定的用户帐户。 您可以使用用户的 Active Directory 域服务 (AD DS) 显示名称。

```
Get-CsOnlineUser -Identity "Ken Myer"
```

您可以使用用户的 SIP 地址。

```
Get-CsOnlineUser -Identity "sip:kenmyer@litwareinc.com"
```

您可以使用用户的用户主体名称 (UPN)。

```
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

### <a name="return-specific-information-for-specific-users-in-skype-for-business-online"></a>返回业务 online 的 Skype 中的特定用户的特定信息
<a name="BKMKReturninfoSpecificUsers"> </a>

默认情况下， [Get-csonlineuser](https://technet.microsoft.com/library/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx) cmdlet 返回大量的每个 Skype 业务 Online 用户帐户的信息。 如果您感兴趣的信息的子集，通过管道传递到**Select-object** cmdlet 返回的数据。 例如，此命令返回用户 Ken myer 的用户，然后使用**选择对象**cmdlet 来限制信息显示的所有数据屏幕 Ken 的 AD DS 显示名称和拨号计划。

```
Get-CsOnlineUser -Identity "Ken Myer" | Select-Object DisplayName, DialPlan
```

下面的命令返回的显示名称和拨号计划的所有用户。

```
Get-CsOnlineUser | Select-Object DisplayName, DialPlan
```

若要查找业务 Online 用户帐户的 Skype 属性，请使用以下命令。

```
Get-CsOnlineUser | Get-Member
```

### <a name="return-a-filtered-list-of-users-in-skype-for-business-online"></a>返回业务 online 的 Skype 中的用户的已筛选的列表
<a name="BKMKReturnFilteredListofUsers"> </a>

通过使用[Get-csonlineuser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet 和_LdapFilter_或_筛选器_参数，您可以轻松地返回一组目标的用户的信息。 例如，此命令返回财务部门中的所有工作的用户。

```
Get-CsOnlineUser -LdapFilter "department=Finance"
```

## <a name="related-topics"></a>相关主题
[设置您的计算机的业务联机管理使用 Windows PowerShell 的 Skype](set-up-your-computer-for-windows-powershell.md)


