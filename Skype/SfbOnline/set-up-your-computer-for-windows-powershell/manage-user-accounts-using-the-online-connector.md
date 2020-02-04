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
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: 使用 Windows PowerShell 中的 CsOnlineUser cmdlet 获取有关你的组织的 Skype for Business Online 用户的信息。
ms.openlocfilehash: 370150de08493507d7b401d7907c90f343802d88
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41692647"
---
# <a name="manage-user-accounts-using-the-online-connector"></a><span data-ttu-id="d901a-103">使用在线连接器管理用户帐户</span><span class="sxs-lookup"><span data-stu-id="d901a-103">Manage user accounts using the Online Connector</span></span>

## <a name="manage-user-accounts"></a><span data-ttu-id="d901a-104">管理用户帐户</span><span class="sxs-lookup"><span data-stu-id="d901a-104">Manage user accounts</span></span>

<span data-ttu-id="d901a-105">本主题包括以下部分：</span><span class="sxs-lookup"><span data-stu-id="d901a-105">This topic contains the following sections:</span></span>

- [<span data-ttu-id="d901a-106">返回有关所有 Lync Online 用户的信息</span><span class="sxs-lookup"><span data-stu-id="d901a-106">Return information about all your Skype for Business Online users</span></span>](manage-user-accounts-using-the-online-connector.md#BKAllUsers)

- [<span data-ttu-id="d901a-107">在 Skype for Business Online 中返回特定用户的信息</span><span class="sxs-lookup"><span data-stu-id="d901a-107">Return information for a specific user in Skype for Business Online</span></span>](manage-user-accounts-using-the-online-connector.md#BKSpecificUser)

- [<span data-ttu-id="d901a-108">为 Skype for Business Online 中的特定用户返回特定信息</span><span class="sxs-lookup"><span data-stu-id="d901a-108">Return specific information for specific users in Skype for Business Online</span></span>](manage-user-accounts-using-the-online-connector.md#BKSpecificUsers)

- [<span data-ttu-id="d901a-109">在 Skype for Business Online 中返回筛选的用户列表</span><span class="sxs-lookup"><span data-stu-id="d901a-109">Return a filtered list of users in Skype for Business Online</span></span>](manage-user-accounts-using-the-online-connector.md#BKListofUsers)

> [!NOTE]
> <span data-ttu-id="d901a-110">**Move-csuser** cmdlet 还包含在适用于 Skype For business Online 管理员的 cmdlet 组中。</span><span class="sxs-lookup"><span data-stu-id="d901a-110">The **Set-CsUser** cmdlet is also included in the set of cmdlets available to Skype for Business Online admins.</span></span> <span data-ttu-id="d901a-111">但是， **move-csuser**当前无法用于管理 Skype For business Online，除非设置_AudioVideoDisabled_参数。</span><span class="sxs-lookup"><span data-stu-id="d901a-111">However, **Set-CsUser** cannot currently be used to manage Skype for Business Online, except for setting the _AudioVideoDisabled_ parameter.</span></span> <span data-ttu-id="d901a-112">如果你尝试使用任何其他参数运行 cmdlet，它将失败，并出现类似于以下内容的错误消息：无法设置 "SipAddress"。</span><span class="sxs-lookup"><span data-stu-id="d901a-112">If you attempt to run the cmdlet with any other parameter, it will fail with an error message similar to this: Unable to set "SipAddress".</span></span> <span data-ttu-id="d901a-113">此参数在远程租户 PowerShell 中受限制。</span><span class="sxs-lookup"><span data-stu-id="d901a-113">This parameter is restricted within Remote Tenant PowerShell.</span></span>

### <a name="return-information-about-all-your-skype-for-business-online-users"></a><span data-ttu-id="d901a-114">返回有关所有 Lync Online 用户的信息</span><span class="sxs-lookup"><span data-stu-id="d901a-114">Return information about all your Skype for Business Online users</span></span>
<span data-ttu-id="d901a-115"><a name="BKAllUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="d901a-115"><a name="BKAllUsers"> </a></span></span>

<span data-ttu-id="d901a-116">若要返回有关已针对 Skype for Business Online 启用的所有用户的信息，请调用[CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet，不要使用任何其他参数。</span><span class="sxs-lookup"><span data-stu-id="d901a-116">To return information about all your users who have been enabled for Skype for Business Online, call the [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet without any additional parameters.</span></span>

```PowerShell
Get-CsOnlineUser
```

<span data-ttu-id="d901a-117">若要返回单个随机选定用户（例如，将此帐户用于测试目的）的信息，请调用**CsOnlineUser** cmdlet 并将_ResultSize_参数设置为1。</span><span class="sxs-lookup"><span data-stu-id="d901a-117">To return information for a single, randomly selected user (for example, to use this account for test purposes), call the **Get-CsOnlineUser** cmdlet and set the _ResultSize_ parameter to 1.</span></span>

```PowerShell
Get-CsOnlineUser -ResultSize 1
```

<span data-ttu-id="d901a-118">这将导致**CsOnlineUser** cmdlet 仅为一个用户返回信息，而不管你的组织中有多少个用户。</span><span class="sxs-lookup"><span data-stu-id="d901a-118">That causes the **Get-CsOnlineUser** cmdlet to return information for just one user, regardless of how many users you have in your organization.</span></span> <span data-ttu-id="d901a-119">若要返回五个用户的信息，请将_ResultSize_参数的值设置为5。</span><span class="sxs-lookup"><span data-stu-id="d901a-119">To return information for five users, set the value of the _ResultSize_ parameter to 5.</span></span>

```PowerShell
Get-CsOnlineUser -ResultSize 5
```

### <a name="return-information-for-a-specific-user-in-skype-for-business-online"></a><span data-ttu-id="d901a-120">在 Skype for Business Online 中返回特定用户的信息</span><span class="sxs-lookup"><span data-stu-id="d901a-120">Return information for a specific user in Skype for Business Online</span></span>
<span data-ttu-id="d901a-121"><a name="BKSpecificUser"> </a></span><span class="sxs-lookup"><span data-stu-id="d901a-121"><a name="BKSpecificUser"> </a></span></span>

<span data-ttu-id="d901a-122">调用[CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet 时，有多种方法可以引用特定用户帐户。</span><span class="sxs-lookup"><span data-stu-id="d901a-122">There are multiple ways of referencing a specific user account when calling the [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet.</span></span> <span data-ttu-id="d901a-123">你可以使用用户的 Active Directory 域服务（AD DS）显示名称。</span><span class="sxs-lookup"><span data-stu-id="d901a-123">You can use the user's Active Directory Domain Services (AD DS) display name.</span></span>

```PowerShell
Get-CsOnlineUser -Identity "Ken Myer"
```

<span data-ttu-id="d901a-124">您可以使用用户的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="d901a-124">You can use the user's SIP address.</span></span>

```PowerShell
Get-CsOnlineUser -Identity "sip:kenmyer@litwareinc.com"
```

<span data-ttu-id="d901a-125">你可以使用用户的用户主体名称（UPN）。</span><span class="sxs-lookup"><span data-stu-id="d901a-125">You can use the user's user principal name (UPN).</span></span>

```PowerShell
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

### <a name="return-specific-information-for-specific-users-in-skype-for-business-online"></a><span data-ttu-id="d901a-126">为 Skype for Business Online 中的特定用户返回特定信息</span><span class="sxs-lookup"><span data-stu-id="d901a-126">Return specific information for specific users in Skype for Business Online</span></span>
<span data-ttu-id="d901a-127"><a name="BKSpecificUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="d901a-127"><a name="BKSpecificUsers"> </a></span></span>

<span data-ttu-id="d901a-128">默认情况下， [CsOnlineUser](https://technet.microsoft.com/library/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx) cmdlet 为每个 Skype For business Online 用户帐户返回大量信息。</span><span class="sxs-lookup"><span data-stu-id="d901a-128">By default, the [Get-CsOnlineUser](https://technet.microsoft.com/library/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx) cmdlet returns a huge amount of information for each Skype for Business Online user account.</span></span> <span data-ttu-id="d901a-129">如果你仅对该信息的子集感兴趣，请将返回的数据输送到**Select 对象**cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d901a-129">If you are interested in only a subset of that information, pipe the returned data to the **Select-Object** cmdlet.</span></span> <span data-ttu-id="d901a-130">例如，此命令返回用户 Ken Myer 的所有数据，然后使用**Select 对象**cmdlet 将显示在屏幕上的信息限制在屏幕上显示为 KEN 的广告 DS 的 "显示名称" 和 "拨号计划"。</span><span class="sxs-lookup"><span data-stu-id="d901a-130">For example, this command returns all the data for the user Ken Myer, and then uses the **Select-Object** cmdlet to limit the information displayed onscreen to Ken's AD DS display name and dial plan.</span></span>

```PowerShell
Get-CsOnlineUser -Identity "Ken Myer" | Select-Object DisplayName, DialPlan
```

<span data-ttu-id="d901a-131">以下命令返回所有用户的显示名称和拨号计划。</span><span class="sxs-lookup"><span data-stu-id="d901a-131">The following command returns the display name and dial plan for all your users.</span></span>

```PowerShell
Get-CsOnlineUser | Select-Object DisplayName, DialPlan
```

<span data-ttu-id="d901a-132">若要查找 Skype for Business Online 用户帐户的属性，请使用以下命令。</span><span class="sxs-lookup"><span data-stu-id="d901a-132">To find the properties of a Skype for Business Online user account, use the following command.</span></span>

```PowerShell
Get-CsOnlineUser | Get-Member
```

### <a name="return-a-filtered-list-of-users-in-skype-for-business-online"></a><span data-ttu-id="d901a-133">在 Skype for Business Online 中返回筛选的用户列表</span><span class="sxs-lookup"><span data-stu-id="d901a-133">Return a filtered list of users in Skype for Business Online</span></span>
<span data-ttu-id="d901a-134"><a name="BKListofUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="d901a-134"><a name="BKListofUsers"> </a></span></span>

<span data-ttu-id="d901a-135">通过使用[CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) Cmdlet 和_LdapFilter_或_Filter_参数，你可以轻松地返回有关一组目标用户的信息。</span><span class="sxs-lookup"><span data-stu-id="d901a-135">By using the [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet and the _LdapFilter_ or _Filter_ parameters, you can easily return information about a targeted set of users.</span></span> <span data-ttu-id="d901a-136">例如，此命令返回在财务部门工作的所有用户。</span><span class="sxs-lookup"><span data-stu-id="d901a-136">For example, this command returns all the users who work in the Finance department.</span></span>

```PowerShell
Get-CsOnlineUser -LdapFilter "department=Finance"
```

## <a name="related-topics"></a><span data-ttu-id="d901a-137">相关主题</span><span class="sxs-lookup"><span data-stu-id="d901a-137">Related topics</span></span>
[<span data-ttu-id="d901a-138">使用 Windows PowerShell 为 skype for business online 管理设置计算机</span><span class="sxs-lookup"><span data-stu-id="d901a-138">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)


