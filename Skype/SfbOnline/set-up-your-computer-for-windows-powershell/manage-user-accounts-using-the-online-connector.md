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
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: 使用Get-CsOnlineUser中的 Windows PowerShell cmdlet 获取有关组织的 Skype for Business Online 用户的信息。
ms.openlocfilehash: bdf1d445fa7c0a9ac4f874e0983b8ab7e8cb19e1
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113168"
---
# <a name="manage-user-accounts-using-the-online-connector"></a><span data-ttu-id="288e2-103">使用联机连接器管理用户帐户</span><span class="sxs-lookup"><span data-stu-id="288e2-103">Manage user accounts using the Online Connector</span></span>

## <a name="manage-user-accounts"></a><span data-ttu-id="288e2-104">管理用户帐户</span><span class="sxs-lookup"><span data-stu-id="288e2-104">Manage user accounts</span></span>

<span data-ttu-id="288e2-105">本主题包括以下部分：</span><span class="sxs-lookup"><span data-stu-id="288e2-105">This topic contains the following sections:</span></span>

- [<span data-ttu-id="288e2-106">返回有关所有 Lync Online 用户的信息</span><span class="sxs-lookup"><span data-stu-id="288e2-106">Return information about all your Skype for Business Online users</span></span>](manage-user-accounts-using-the-online-connector.md#BKAllUsers)

- [<span data-ttu-id="288e2-107">返回 Skype for Business Online 中特定用户的信息</span><span class="sxs-lookup"><span data-stu-id="288e2-107">Return information for a specific user in Skype for Business Online</span></span>](manage-user-accounts-using-the-online-connector.md#BKSpecificUser)

- [<span data-ttu-id="288e2-108">在 Skype for Business Online 中返回特定用户的特定信息</span><span class="sxs-lookup"><span data-stu-id="288e2-108">Return specific information for specific users in Skype for Business Online</span></span>](manage-user-accounts-using-the-online-connector.md#BKSpecificUsers)

- [<span data-ttu-id="288e2-109">返回 Skype for Business Online 中的已筛选用户列表</span><span class="sxs-lookup"><span data-stu-id="288e2-109">Return a filtered list of users in Skype for Business Online</span></span>](manage-user-accounts-using-the-online-connector.md#BKListofUsers)

> [!NOTE]
> <span data-ttu-id="288e2-110">**Set-CsUser** cmdlet 也包含在可用于 Skype for Business Online 管理员的 cmdlet 集内。</span><span class="sxs-lookup"><span data-stu-id="288e2-110">The **Set-CsUser** cmdlet is also included in the set of cmdlets available to Skype for Business Online admins.</span></span> <span data-ttu-id="288e2-111">但是 **，Set-CsUser** 当前不能用于管理 Skype for Business Online，但 _设置 AudioVideoDisabled_ 参数除外。</span><span class="sxs-lookup"><span data-stu-id="288e2-111">However, **Set-CsUser** cannot currently be used to manage Skype for Business Online, except for setting the _AudioVideoDisabled_ parameter.</span></span> <span data-ttu-id="288e2-112">如果尝试使用任何其他参数运行 cmdlet，它将失败，并出现类似于以下错误消息：无法设置"SipAddress"。</span><span class="sxs-lookup"><span data-stu-id="288e2-112">If you attempt to run the cmdlet with any other parameter, it will fail with an error message similar to this: Unable to set "SipAddress".</span></span> <span data-ttu-id="288e2-113">此参数在远程租户 PowerShell 中受到限制。</span><span class="sxs-lookup"><span data-stu-id="288e2-113">This parameter is restricted within Remote Tenant PowerShell.</span></span>

### <a name="return-information-about-all-your-skype-for-business-online-users"></a><span data-ttu-id="288e2-114">返回有关所有 Lync Online 用户的信息</span><span class="sxs-lookup"><span data-stu-id="288e2-114">Return information about all your Skype for Business Online users</span></span>
<span data-ttu-id="288e2-115"><a name="BKAllUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="288e2-115"><a name="BKAllUsers"> </a></span></span>

<span data-ttu-id="288e2-116">若要返回有关已启用 Skype for Business Online 的所有用户的信息，请调用 [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) cmdlet，而无需任何其他参数。</span><span class="sxs-lookup"><span data-stu-id="288e2-116">To return information about all your users who have been enabled for Skype for Business Online, call the [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) cmdlet without any additional parameters.</span></span>

```PowerShell
Get-CsOnlineUser
```

<span data-ttu-id="288e2-117">若要返回单个随机选择的用户 (的信息，例如，若要使用此帐户进行测试) ，请调用 **Get-CsOnlineUser** cmdlet，将 _ResultSize_ 参数设置为 1。</span><span class="sxs-lookup"><span data-stu-id="288e2-117">To return information for a single, randomly selected user (for example, to use this account for test purposes), call the **Get-CsOnlineUser** cmdlet and set the _ResultSize_ parameter to 1.</span></span>

```PowerShell
Get-CsOnlineUser -ResultSize 1
```

<span data-ttu-id="288e2-118">这会导致 **Get-CsOnlineUser** cmdlet 仅返回一个用户的信息，而不考虑组织中有多少用户。</span><span class="sxs-lookup"><span data-stu-id="288e2-118">That causes the **Get-CsOnlineUser** cmdlet to return information for just one user, regardless of how many users you have in your organization.</span></span> <span data-ttu-id="288e2-119">若要返回五个用户的信息，将 _ResultSize_ 参数的值设置为 5。</span><span class="sxs-lookup"><span data-stu-id="288e2-119">To return information for five users, set the value of the _ResultSize_ parameter to 5.</span></span>

```PowerShell
Get-CsOnlineUser -ResultSize 5
```

### <a name="return-information-for-a-specific-user-in-skype-for-business-online"></a><span data-ttu-id="288e2-120">返回 Skype for Business Online 中特定用户的信息</span><span class="sxs-lookup"><span data-stu-id="288e2-120">Return information for a specific user in Skype for Business Online</span></span>
<span data-ttu-id="288e2-121"><a name="BKSpecificUser"> </a></span><span class="sxs-lookup"><span data-stu-id="288e2-121"><a name="BKSpecificUser"> </a></span></span>

<span data-ttu-id="288e2-122">调用 [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) cmdlet 时，有多种方法可引用特定用户帐户。</span><span class="sxs-lookup"><span data-stu-id="288e2-122">There are multiple ways of referencing a specific user account when calling the [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) cmdlet.</span></span> <span data-ttu-id="288e2-123">可以使用用户的 Active Directory 域服务 (AD DS) 显示名称。</span><span class="sxs-lookup"><span data-stu-id="288e2-123">You can use the user's Active Directory Domain Services (AD DS) display name.</span></span>

```PowerShell
Get-CsOnlineUser -Identity "Ken Myer"
```

<span data-ttu-id="288e2-124">可以使用用户的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="288e2-124">You can use the user's SIP address.</span></span>

```PowerShell
Get-CsOnlineUser -Identity "sip:kenmyer@litwareinc.com"
```

<span data-ttu-id="288e2-125">可以使用用户的用户主体名称 (UPN) 。</span><span class="sxs-lookup"><span data-stu-id="288e2-125">You can use the user's user principal name (UPN).</span></span>

```PowerShell
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

### <a name="return-specific-information-for-specific-users-in-skype-for-business-online"></a><span data-ttu-id="288e2-126">在 Skype for Business Online 中返回特定用户的特定信息</span><span class="sxs-lookup"><span data-stu-id="288e2-126">Return specific information for specific users in Skype for Business Online</span></span>
<span data-ttu-id="288e2-127"><a name="BKSpecificUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="288e2-127"><a name="BKSpecificUsers"> </a></span></span>

<span data-ttu-id="288e2-128">默认情况下 [，Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) cmdlet 会针对每个 Skype for Business Online 用户帐户返回大量信息。</span><span class="sxs-lookup"><span data-stu-id="288e2-128">By default, the [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) cmdlet returns a huge amount of information for each Skype for Business Online user account.</span></span> <span data-ttu-id="288e2-129">如果只对该信息的子集感兴趣，请通过管道将返回的数据通过管道返回到 **Select-Object** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="288e2-129">If you are interested in only a subset of that information, pipe the returned data to the **Select-Object** cmdlet.</span></span> <span data-ttu-id="288e2-130">例如，此命令返回用户 Ken Myer 的所有数据，然后使用 **Select-Object** cmdlet 将屏幕上显示的信息限制为 Ken 的 AD DS 显示名称和拨号计划。</span><span class="sxs-lookup"><span data-stu-id="288e2-130">For example, this command returns all the data for the user Ken Myer, and then uses the **Select-Object** cmdlet to limit the information displayed onscreen to Ken's AD DS display name and dial plan.</span></span>

```PowerShell
Get-CsOnlineUser -Identity "Ken Myer" | Select-Object DisplayName, DialPlan
```

<span data-ttu-id="288e2-131">以下命令返回显示名称的拨号和拨号计划。</span><span class="sxs-lookup"><span data-stu-id="288e2-131">The following command returns the display name and dial plan for all your users.</span></span>

```PowerShell
Get-CsOnlineUser | Select-Object DisplayName, DialPlan
```

<span data-ttu-id="288e2-132">若要查找 Skype for Business Online 用户帐户的属性，请使用以下命令。</span><span class="sxs-lookup"><span data-stu-id="288e2-132">To find the properties of a Skype for Business Online user account, use the following command.</span></span>

```PowerShell
Get-CsOnlineUser | Get-Member
```

### <a name="return-a-filtered-list-of-users-in-skype-for-business-online"></a><span data-ttu-id="288e2-133">返回 Skype for Business Online 中的已筛选用户列表</span><span class="sxs-lookup"><span data-stu-id="288e2-133">Return a filtered list of users in Skype for Business Online</span></span>
<span data-ttu-id="288e2-134"><a name="BKListofUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="288e2-134"><a name="BKListofUsers"> </a></span></span>

<span data-ttu-id="288e2-135">通过使用 [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) cmdlet 和 _LdapFilter_ 或 _Filter_ 参数，可以轻松返回有关一组目标用户的信息。</span><span class="sxs-lookup"><span data-stu-id="288e2-135">By using the [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) cmdlet and the _LdapFilter_ or _Filter_ parameters, you can easily return information about a targeted set of users.</span></span> <span data-ttu-id="288e2-136">例如，此命令返回财务部门工作的所有用户。</span><span class="sxs-lookup"><span data-stu-id="288e2-136">For example, this command returns all the users who work in the Finance department.</span></span>

```PowerShell
Get-CsOnlineUser -LdapFilter "department=Finance"
```

## <a name="related-topics"></a><span data-ttu-id="288e2-137">相关主题</span><span class="sxs-lookup"><span data-stu-id="288e2-137">Related topics</span></span>
[<span data-ttu-id="288e2-138">使用 skype for business Online 管理设置计算机Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="288e2-138">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)