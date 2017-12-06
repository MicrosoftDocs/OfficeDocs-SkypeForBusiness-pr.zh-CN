---
title: "管理用户帐户使用 for Business Online 连接器的 Skype"
ms.author: tonysmit
author: tonysmit
ms.date: 5/23/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.assetid: a226b0d4-6359-42b8-808d-4b8ab3736d3b
description: "Use the Get-CsOnlineUser cmdlet in Windows PowerShell to get information about your organization's Skype for Business Online users."
---

# 管理用户帐户使用 for Business Online 连接器的 Skype

> [!IMPORTANT]
> 本文是由机器翻译的，请参阅[免责声明](a226b0d4-6359-42b8-808d-4b8ab3736d3b.md#MT_Footer)。请在 [此处](https://support.office.com/en-us/article/a226b0d4-6359-42b8-808d-4b8ab3736d3b) 中查找本文的英文版本以便参考。
  
## 管理用户帐户

本主题包含以下部分：
  
- [返回有关所有您 Skype for Business Online 用户的信息](a226b0d4-6359-42b8-808d-4b8ab3736d3b.md#BKMK_ReturnInfoAboutAllUsers)
    
- [返回在 Skype for Business Online 的特定用户的信息](a226b0d4-6359-42b8-808d-4b8ab3736d3b.md#BKMK_ReturnInfoSpecificUser)
    
- [返回在 Skype for Business Online 的特定用户的特定信息](a226b0d4-6359-42b8-808d-4b8ab3736d3b.md#BKMK_ReturninfoSpecificUsers)
    
- [返回在 Skype for Business Online 的用户已筛选的列表](a226b0d4-6359-42b8-808d-4b8ab3736d3b.md#BKMK_ReturnFilteredListofUsers)
    
> [!NOTE]
> Cmdlet 适用于Skype for Business Online管理员组中，也包括 **Set-CsUser** cmdlet。但是， **Set-CsUser** ，当前不能使用管理Skype for Business Online，除 _AudioVideoDisabled_参数设置。如果您尝试运行 cmdlet 与任何其他参数，它将失败，并与此类似一条错误消息： 无法设置"SipAddress"。此参数是受限租户的远程 PowerShell 内。 
  
### 返回有关所有您 Skype for Business Online 用户的信息
<a name="BKMK_ReturnInfoAboutAllUsers"> </a>

若要返回所有已启用的Skype for Business Online您用户的信息，请致电[获取 CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet 不带任何其他参数。
  
```
Get-CsOnlineUser
```

若要返回一个随机选择用户 （例如，要用于测试目的使用该帐户） 的信息，请致电 **Get-CsOnlineUser** cmdlet 和 _ResultSize_ 参数设置为 1。
  
```
Get-CsOnlineUser -ResultSize 1
```

导致 **Get-CsOnlineUser** cmdlet 返回为一个用户，无论您在您的组织中有多少位用户的信息。若要返回五个用户的信息，请 _ResultSize_参数的值设置为 5。
  
```
Get-CsOnlineUser -ResultSize 5
```

### 返回在 Skype for Business Online 的特定用户的信息
<a name="BKMK_ReturnInfoSpecificUser"> </a>

有多种方法调用[获取 CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet 时引用特定用户帐户。您可以使用该用户的Active Directory 域服务 (AD DS)显示名称。
  
```
Get-CsOnlineUser -Identity "Ken Myer"
```

您可以使用该用户的 SIP 地址。
  
```
Get-CsOnlineUser -Identity "sip:kenmyer@litwareinc.com"
```

您可以使用用户的用户主体名称 (UPN)。
  
```
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

### 返回在 Skype for Business Online 的特定用户的特定信息
<a name="BKMK_ReturninfoSpecificUsers"> </a>

默认情况下，[获取 CsOnlineUser](https://support.office.com/article/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx) cmdlet 返回大量的每个Skype for Business Online用户帐户信息。如果您感兴趣的信息的子集，管道给 **Select-Object** cmdlet 返回的数据。例如，此命令返回所有数据用户鸿波，然后使用 **Select-Object** cmdlet 来限制信息显示在屏幕上 Ken 的 AD DS 显示名称和拨号计划。
  
```
Get-CsOnlineUser -Identity "Ken Myer" | Select-Object DisplayName, DialPlan
```

以下命令返回的显示名称和拨号计划为您的用户。
  
```
Get-CsOnlineUser | Select-Object DisplayName, DialPlan
```

若要查找的Skype for Business Online用户帐户的属性，请使用以下命令。
  
```
Get-CsOnlineUser | Get-Member
```

### 返回在 Skype for Business Online 的用户已筛选的列表
<a name="BKMK_ReturnFilteredListofUsers"> </a>

通过使用[获取 CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet 和参数 _LdapFilter_或 _Filter_ ，您可以轻松地返回目标的一组用户的信息。例如，此命令返回财务部门中的所有用户的工作。
  
```
Get-CsOnlineUser -LdapFilter "department=Finance"
```

## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **机器翻译免责声明**：本文是由无人工介入的计算机系统翻译的。Microsoft 提供机器翻译是为了帮助非英语国家/地区用户方便阅读有关 Microsoft 产品、服务和技术的内容。由于机器翻译的原因，本文可能包含词汇、语法或文法方面的错误。 
  

