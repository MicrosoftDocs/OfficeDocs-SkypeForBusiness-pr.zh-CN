---
title: 管理用户帐户使用在线连接器
ms.author: tonysmit
author: tonysmit
manager: serdars
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
description: 使用在 Windows PowerShell Get CsOnlineUser cmdlet 以获得有关信息组织的 Skype 业务联机用户。
ms.openlocfilehash: 74982485d33cc3a5e1ad76cc3978f81142ad6ea9
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="manage-user-accounts-using-the-online-connector"></a><span data-ttu-id="f246f-103">管理用户帐户使用在线连接器</span><span class="sxs-lookup"><span data-stu-id="f246f-103">Manage user accounts using the Online Connector</span></span>

## <a name="manage-user-accounts"></a><span data-ttu-id="f246f-104">管理用户帐户</span><span class="sxs-lookup"><span data-stu-id="f246f-104">Manage user accounts</span></span>

<span data-ttu-id="f246f-105">本主题包括以下部分：</span><span class="sxs-lookup"><span data-stu-id="f246f-105">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="f246f-106">返回有关所有您 Skype 的在线业务用户的信息</span><span class="sxs-lookup"><span data-stu-id="f246f-106">Return information about all your Skype for Business Online users</span></span>](manage-user-accounts-using-the-online-connector.md#BKAllUsers)
    
- [<span data-ttu-id="f246f-107">返回某一特定用户的信息在 Skype 在线业务</span><span class="sxs-lookup"><span data-stu-id="f246f-107">Return information for a specific user in Skype for Business Online</span></span>](manage-user-accounts-using-the-online-connector.md#BKSpecificUser)
    
- [<span data-ttu-id="f246f-108">返回有关特定用户的特定信息在 Skype 在线业务</span><span class="sxs-lookup"><span data-stu-id="f246f-108">Return specific information for specific users in Skype for Business Online</span></span>](manage-user-accounts-using-the-online-connector.md#BKSpecificUsers)
    
- [<span data-ttu-id="f246f-109">在 Skype 的用户的筛选的列表返回的在线业务</span><span class="sxs-lookup"><span data-stu-id="f246f-109">Return a filtered list of users in Skype for Business Online </span></span>](manage-user-accounts-using-the-online-connector.md#BKListofUsers)
    
> [!NOTE]
> <span data-ttu-id="f246f-110">集中供联机业务管理员 Skype 的 cmdlet 的也包括**集 CsUser** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f246f-110">The **Set-CsUser** cmdlet is also included in the set of cmdlets available to Skype for Business Online admins.</span></span> <span data-ttu-id="f246f-111">但是，**集 CsUser**不能当前用于管理 Skype 的在线业务，除了将_AudioVideoDisabled_参数设置。</span><span class="sxs-lookup"><span data-stu-id="f246f-111">However, **Set-CsUser** cannot currently be used to manage Skype for Business Online, except for setting the _AudioVideoDisabled_ parameter.</span></span> <span data-ttu-id="f246f-112">如果您尝试使用任何其他参数运行该 cmdlet，它将失败，并与以下类似的错误消息： 无法设置"SipAddress"。</span><span class="sxs-lookup"><span data-stu-id="f246f-112">If you attempt to run the cmdlet with any other parameter, it will fail with an error message similar to this: Unable to set "SipAddress".</span></span> <span data-ttu-id="f246f-113">此参数将被限制在远程租户 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="f246f-113">This parameter is restricted within Remote Tenant PowerShell.</span></span>
  
### <a name="return-information-about-all-your-skype-for-business-online-users"></a><span data-ttu-id="f246f-114">返回有关所有 Lync Online 用户的信息</span><span class="sxs-lookup"><span data-stu-id="f246f-114">Return information about all your Skype for Business Online users</span></span>
<span data-ttu-id="f246f-115"><a name="BKAllUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="f246f-115"></span></span>

<span data-ttu-id="f246f-116">若要返回所有用户已启用为 Skype 的在线业务的有关信息，请调用不带任何附加参数[获取 CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f246f-116">To return information about all your users who have been enabled for Skype for Business Online, call the [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet without any additional parameters.</span></span>
  
```
Get-CsOnlineUser
```

<span data-ttu-id="f246f-117">若要返回单一、 随机选中用户 （例如，若要将此帐户用于测试目的） 的信息，请调用**Get CsOnlineUser** cmdlet，将_ResultSize_参数设置为 1。</span><span class="sxs-lookup"><span data-stu-id="f246f-117">To return information for a single, randomly selected user (for example, to use this account for test purposes), call the **Get-CsOnlineUser** cmdlet and set the _ResultSize_ parameter to 1.</span></span>
  
```
Get-CsOnlineUser -ResultSize 1
```

<span data-ttu-id="f246f-118">它使**Get CsOnlineUser** cmdlet 返回只是一个用户，而不考虑您的组织中有多少个用户的信息。</span><span class="sxs-lookup"><span data-stu-id="f246f-118">That causes the **Get-CsOnlineUser** cmdlet to return information for just one user, regardless of how many users you have in your organization.</span></span> <span data-ttu-id="f246f-119">若要返回五个用户的信息，请_ResultSize_参数的值设置为 5。</span><span class="sxs-lookup"><span data-stu-id="f246f-119">To return information for five users, set the value of the _ResultSize_ parameter to 5.</span></span>
  
```
Get-CsOnlineUser -ResultSize 5
```

### <a name="return-information-for-a-specific-user-in-skype-for-business-online"></a><span data-ttu-id="f246f-120">返回某一特定用户的信息在 Skype 在线业务</span><span class="sxs-lookup"><span data-stu-id="f246f-120">Return information for a specific user in Skype for Business Online</span></span>
<span data-ttu-id="f246f-121"><a name="BKSpecificUser"> </a></span><span class="sxs-lookup"><span data-stu-id="f246f-121"></span></span>

<span data-ttu-id="f246f-122">有多个引用特定的用户帐户，在调用[Get CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet 的方法。</span><span class="sxs-lookup"><span data-stu-id="f246f-122">There are multiple ways of referencing a specific user account when calling the [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet.</span></span> <span data-ttu-id="f246f-123">您可以使用该用户的 Active Directory 域服务 (AD DS) 显示名称。</span><span class="sxs-lookup"><span data-stu-id="f246f-123">You can use the user's Active Directory Domain Services (AD DS) display name.</span></span>
  
```
Get-CsOnlineUser -Identity "Ken Myer"
```

<span data-ttu-id="f246f-124">您可以使用该用户的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="f246f-124">You can use the user's SIP address.</span></span>
  
```
Get-CsOnlineUser -Identity "sip:kenmyer@litwareinc.com"
```

<span data-ttu-id="f246f-125">您可以使用该用户的用户主体名称 (UPN)。</span><span class="sxs-lookup"><span data-stu-id="f246f-125">You can use the user's user principal name (UPN).</span></span>
  
```
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

### <a name="return-specific-information-for-specific-users-in-skype-for-business-online"></a><span data-ttu-id="f246f-126">返回有关特定用户的特定信息在 Skype 在线业务</span><span class="sxs-lookup"><span data-stu-id="f246f-126">Return specific information for specific users in Skype for Business Online</span></span>
<span data-ttu-id="f246f-127"><a name="BKSpecificUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="f246f-127"></span></span>

<span data-ttu-id="f246f-128">默认情况下， [Get CsOnlineUser](http://technet.microsoft.com/library/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx) cmdlet 返回大量每个 Skype 的在线业务的用户帐户的信息。</span><span class="sxs-lookup"><span data-stu-id="f246f-128">By default, the [Get-CsOnlineUser](http://technet.microsoft.com/library/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx) cmdlet returns a huge amount of information for each Skype for Business Online user account.</span></span> <span data-ttu-id="f246f-129">如果您感兴趣信息的子集，管道为**对象选择的**cmdlet 返回的数据。</span><span class="sxs-lookup"><span data-stu-id="f246f-129">If you are interested in only a subset of that information, pipe the returned data to the **Select-Object** cmdlet.</span></span> <span data-ttu-id="f246f-130">例如，此命令返回用户 Ken Myer，然后使用**选择对象**cmdlet 来限制信息显示的所有数据在屏幕上对 Ken 的 AD DS 显示名称和拨号计划。</span><span class="sxs-lookup"><span data-stu-id="f246f-130">For example, this command returns all the data for the user Ken Myer, and then uses the **Select-Object** cmdlet to limit the information displayed onscreen to Ken's AD DS display name and dial plan.</span></span>
  
```
Get-CsOnlineUser -Identity "Ken Myer" | Select-Object DisplayName, DialPlan
```

<span data-ttu-id="f246f-131">以下命令返回的显示名称和拨号计划为您的所有用户。</span><span class="sxs-lookup"><span data-stu-id="f246f-131">The following command returns the display name and dial plan for all your users.</span></span>
  
```
Get-CsOnlineUser | Select-Object DisplayName, DialPlan
```

<span data-ttu-id="f246f-132">Skype 的属性查找在线业务的用户帐户，请使用下面的命令。</span><span class="sxs-lookup"><span data-stu-id="f246f-132">To find the properties of a Skype for Business Online user account, use the following command.</span></span>
  
```
Get-CsOnlineUser | Get-Member
```

### <a name="return-a-filtered-list-of-users-in-skype-for-business-online"></a><span data-ttu-id="f246f-133">在 Skype 的用户的筛选的列表返回的在线业务</span><span class="sxs-lookup"><span data-stu-id="f246f-133">Return a filtered list of users in Skype for Business Online</span></span>
<span data-ttu-id="f246f-134"><a name="BKListofUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="f246f-134"></span></span>

<span data-ttu-id="f246f-135">通过使用[Get CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet 和_LdapFilter_或_筛选器_参数，可以轻松地返回一组目标用户有关的信息。</span><span class="sxs-lookup"><span data-stu-id="f246f-135">By using the [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet and the _LdapFilter_ or _Filter_ parameters, you can easily return information about a targeted set of users.</span></span> <span data-ttu-id="f246f-136">例如，此命令返回工作的所有用户在财务部门。</span><span class="sxs-lookup"><span data-stu-id="f246f-136">For example, this command returns all the users who work in the Finance department.</span></span>
  
```
Get-CsOnlineUser -LdapFilter "department=Finance"
```

## <a name="related-topics"></a><span data-ttu-id="f246f-137">相关主题</span><span class="sxs-lookup"><span data-stu-id="f246f-137">Related topics</span></span>
[<span data-ttu-id="f246f-138">设置计算机上的 Skype 业务在线管理使用 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f246f-138">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
 