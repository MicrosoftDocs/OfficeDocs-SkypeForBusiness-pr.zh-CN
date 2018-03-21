---
title: "管理用户帐户"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: a226b0d4-6359-42b8-808d-4b8ab3736d3b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
description: "使用在 Windows PowerShell Get CsOnlineUser cmdlet 以获得有关信息组织的 Skype 业务联机用户。"
ms.openlocfilehash: f51f2c1f723a26bfa3a815bfe7641b68c5d23b26
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2018
---
# <a name="manage-user-accounts"></a>管理用户帐户

## <a name="manage-user-accounts"></a>管理用户帐户

本主题包括以下部分：
  
- [返回有关所有您 Skype 的在线业务用户的信息](manage-user-accounts.md#BKMKReturnInfoAboutAllUsers)
    
- [返回某一特定用户的信息在 Skype 在线业务](manage-user-accounts.md#BKMKReturnInfoSpecificUser)
    
- [返回有关特定用户的特定信息在 Skype 在线业务](manage-user-accounts.md#BKMKReturninfoSpecificUsers)
    
- [在 Skype 的用户的筛选的列表返回的在线业务](manage-user-accounts.md#BKMKReturnFilteredListofUsers)
    
> [!NOTE]
> 集中供联机业务管理员 Skype 的 cmdlet 的也包括**集 CsUser** cmdlet。 但是，**集 CsUser**不能当前用于管理 Skype 的在线业务，除了将_AudioVideoDisabled_参数设置。 如果您尝试使用任何其他参数运行该 cmdlet，它将失败，并与以下类似的错误消息： 无法设置"SipAddress"。 此参数将被限制在远程租户 PowerShell。
  
### <a name="return-information-about-all-your-skype-for-business-online-users"></a>返回有关所有 Lync Online 用户的信息
<a name="BKMKReturnInfoAboutAllUsers"> </a>

若要返回所有用户已启用为 Skype 的在线业务的有关信息，请调用不带任何附加参数[获取 CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet。
  
```
Get-CsOnlineUser
```

若要返回单一、 随机选中用户 （例如，若要将此帐户用于测试目的） 的信息，请调用**Get CsOnlineUser** cmdlet，将_ResultSize_参数设置为 1。
  
```
Get-CsOnlineUser -ResultSize 1
```

它使**Get CsOnlineUser** cmdlet 返回只是一个用户，而不考虑您的组织中有多少个用户的信息。 若要返回五个用户的信息，请_ResultSize_参数的值设置为 5。
  
```
Get-CsOnlineUser -ResultSize 5
```

### <a name="return-information-for-a-specific-user-in-skype-for-business-online"></a>返回某一特定用户的信息在 Skype 在线业务
<a name="BKMKReturnInfoSpecificUser"> </a>

有多个引用特定的用户帐户，在调用[Get CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet 的方法。 您可以使用该用户的 Active Directory 域服务 (AD DS) 显示名称。
  
```
Get-CsOnlineUser -Identity "Ken Myer"
```

您可以使用该用户的 SIP 地址。
  
```
Get-CsOnlineUser -Identity "sip:kenmyer@litwareinc.com"
```

您可以使用该用户的用户主体名称 (UPN)。
  
```
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

### <a name="return-specific-information-for-specific-users-in-skype-for-business-online"></a>返回有关特定用户的特定信息在 Skype 在线业务
<a name="BKMKReturninfoSpecificUsers"> </a>

默认情况下， [Get CsOnlineUser](http://technet.microsoft.com/library/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx) cmdlet 返回大量每个 Skype 的在线业务的用户帐户的信息。 如果您感兴趣信息的子集，管道为**对象选择的**cmdlet 返回的数据。 例如，此命令返回用户 Ken Myer，然后使用**选择对象**cmdlet 来限制信息显示的所有数据在屏幕上对 Ken 的 AD DS 显示名称和拨号计划。
  
```
Get-CsOnlineUser -Identity "Ken Myer" | Select-Object DisplayName, DialPlan
```

以下命令返回的显示名称和拨号计划为您的所有用户。
  
```
Get-CsOnlineUser | Select-Object DisplayName, DialPlan
```

Skype 的属性查找在线业务的用户帐户，请使用下面的命令。
  
```
Get-CsOnlineUser | Get-Member
```

### <a name="return-a-filtered-list-of-users-in-skype-for-business-online"></a>在 Skype 的用户的筛选的列表返回的在线业务
<a name="BKMKReturnFilteredListofUsers"> </a>

通过使用[Get CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet 和_LdapFilter_或_筛选器_参数，可以轻松地返回一组目标用户有关的信息。 例如，此命令返回工作的所有用户在财务部门。
  
```
Get-CsOnlineUser -LdapFilter "department=Finance"
```

## <a name="related-topics"></a>相关主题
[设置计算机上的 Skype 业务在线管理使用 Windows PowerShell](set-up-your-computer-for-windows-powershell.md)
