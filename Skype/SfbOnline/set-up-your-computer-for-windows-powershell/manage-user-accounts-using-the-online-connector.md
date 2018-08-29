---
title: 管理用户帐户使用 Online Connector
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
description: Windows PowerShell 中使用 Get-csonlineuser cmdlet 以获取有关您组织的 Skype 针对业务 Online 用户信息。
ms.openlocfilehash: 96f4025b062e13086bcc878fd9166ced9325fbee
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/28/2018
ms.locfileid: "23250191"
---
# <a name="manage-user-accounts-using-the-online-connector"></a><span data-ttu-id="38160-103">管理用户帐户使用 Online Connector</span><span class="sxs-lookup"><span data-stu-id="38160-103">Manage user accounts using the Online Connector</span></span>

## <a name="manage-user-accounts"></a><span data-ttu-id="38160-104">管理用户帐户</span><span class="sxs-lookup"><span data-stu-id="38160-104">Manage user accounts</span></span>

<span data-ttu-id="38160-105">本主题包括以下部分：</span><span class="sxs-lookup"><span data-stu-id="38160-105">This topic contains the following sections:</span></span>

- [<span data-ttu-id="38160-106">返回有关所有 Lync Online 用户的信息</span><span class="sxs-lookup"><span data-stu-id="38160-106">Return information about all your Skype for Business Online users</span></span>](manage-user-accounts-using-the-online-connector.md#BKAllUsers)

- [<span data-ttu-id="38160-107">返回业务 online 的 Skype 中的特定用户的信息</span><span class="sxs-lookup"><span data-stu-id="38160-107">Return information for a specific user in Skype for Business Online</span></span>](manage-user-accounts-using-the-online-connector.md#BKSpecificUser)

- [<span data-ttu-id="38160-108">返回业务 online 的 Skype 中的特定用户的特定信息</span><span class="sxs-lookup"><span data-stu-id="38160-108">Return specific information for specific users in Skype for Business Online</span></span>](manage-user-accounts-using-the-online-connector.md#BKSpecificUsers)

- [<span data-ttu-id="38160-109">返回业务 online 的 Skype 中的用户的已筛选的列表</span><span class="sxs-lookup"><span data-stu-id="38160-109">Return a filtered list of users in Skype for Business Online </span></span>](manage-user-accounts-using-the-online-connector.md#BKListofUsers)

> [!NOTE]
> <span data-ttu-id="38160-110">Skype 到业务 Online 管理员可用的 cmdlet 集，也包含**Set-csuser** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="38160-110">The **Set-CsUser** cmdlet is also included in the set of cmdlets available to Skype for Business Online admins.</span></span> <span data-ttu-id="38160-111">但是， **Set-csuser** ，当前不用来管理 Skype 业务 online，除_AudioVideoDisabled_参数设置。</span><span class="sxs-lookup"><span data-stu-id="38160-111">However, **Set-CsUser** cannot currently be used to manage Skype for Business Online, except for setting the _AudioVideoDisabled_ parameter.</span></span> <span data-ttu-id="38160-112">如果您尝试运行带有任何其他参数的 cmdlet，它将与类似如下的错误消息失败： 无法设置"SipAddress"。</span><span class="sxs-lookup"><span data-stu-id="38160-112">If you attempt to run the cmdlet with any other parameter, it will fail with an error message similar to this: Unable to set "SipAddress".</span></span> <span data-ttu-id="38160-113">此参数是远程租户 PowerShell 内受限制。</span><span class="sxs-lookup"><span data-stu-id="38160-113">This parameter is restricted within Remote Tenant PowerShell.</span></span>

### <a name="return-information-about-all-your-skype-for-business-online-users"></a><span data-ttu-id="38160-114">返回有关所有 Lync Online 用户的信息</span><span class="sxs-lookup"><span data-stu-id="38160-114">Return information about all your Skype for Business Online users</span></span>
<span data-ttu-id="38160-115"><a name="BKAllUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="38160-115"></span></span>

<span data-ttu-id="38160-116">若要返回所有已启用的 Skype 业务 online 您用户的信息，请调用不带任何其他参数[Get-csonlineuser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="38160-116">To return information about all your users who have been enabled for Skype for Business Online, call the [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet without any additional parameters.</span></span>

```
Get-CsOnlineUser
```

<span data-ttu-id="38160-117">若要返回单个、 随机选择用户 （例如，要用于测试此帐户） 的信息，请调用**Get-csonlineuser** cmdlet，并将_ResultSize_参数设置为 1。</span><span class="sxs-lookup"><span data-stu-id="38160-117">To return information for a single, randomly selected user (for example, to use this account for test purposes), call the **Get-CsOnlineUser** cmdlet and set the _ResultSize_ parameter to 1.</span></span>

```
Get-CsOnlineUser -ResultSize 1
```

<span data-ttu-id="38160-118">它使**Get-csonlineuser** cmdlet 返回仅仅对一个用户，无论您的组织中有多少用户的信息。</span><span class="sxs-lookup"><span data-stu-id="38160-118">That causes the **Get-CsOnlineUser** cmdlet to return information for just one user, regardless of how many users you have in your organization.</span></span> <span data-ttu-id="38160-119">要返回的五个用户的信息，请设置为 5 _ResultSize_参数的值。</span><span class="sxs-lookup"><span data-stu-id="38160-119">To return information for five users, set the value of the _ResultSize_ parameter to 5.</span></span>

```
Get-CsOnlineUser -ResultSize 5
```

### <a name="return-information-for-a-specific-user-in-skype-for-business-online"></a><span data-ttu-id="38160-120">返回业务 online 的 Skype 中的特定用户的信息</span><span class="sxs-lookup"><span data-stu-id="38160-120">Return information for a specific user in Skype for Business Online</span></span>
<span data-ttu-id="38160-121"><a name="BKSpecificUser"> </a></span><span class="sxs-lookup"><span data-stu-id="38160-121"></span></span>

<span data-ttu-id="38160-122">有多种方法的调用[Get-csonlineuser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet 时引用特定的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="38160-122">There are multiple ways of referencing a specific user account when calling the [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet.</span></span> <span data-ttu-id="38160-123">您可以使用用户的 Active Directory 域服务 (AD DS) 显示名称。</span><span class="sxs-lookup"><span data-stu-id="38160-123">You can use the user's Active Directory Domain Services (AD DS) display name.</span></span>

```
Get-CsOnlineUser -Identity "Ken Myer"
```

<span data-ttu-id="38160-124">您可以使用用户的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="38160-124">You can use the user's SIP address.</span></span>

```
Get-CsOnlineUser -Identity "sip:kenmyer@litwareinc.com"
```

<span data-ttu-id="38160-125">您可以使用用户的用户主体名称 (UPN)。</span><span class="sxs-lookup"><span data-stu-id="38160-125">You can use the user's user principal name (UPN).</span></span>

```
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

### <a name="return-specific-information-for-specific-users-in-skype-for-business-online"></a><span data-ttu-id="38160-126">返回业务 online 的 Skype 中的特定用户的特定信息</span><span class="sxs-lookup"><span data-stu-id="38160-126">Return specific information for specific users in Skype for Business Online</span></span>
<span data-ttu-id="38160-127"><a name="BKSpecificUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="38160-127"></span></span>

<span data-ttu-id="38160-128">默认情况下， [Get-csonlineuser](https://technet.microsoft.com/library/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx) cmdlet 返回大量的每个 Skype 业务 Online 用户帐户的信息。</span><span class="sxs-lookup"><span data-stu-id="38160-128">By default, the [Get-CsOnlineUser](https://technet.microsoft.com/library/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx) cmdlet returns a huge amount of information for each Skype for Business Online user account.</span></span> <span data-ttu-id="38160-129">如果您感兴趣的信息的子集，通过管道传递到**Select-object** cmdlet 返回的数据。</span><span class="sxs-lookup"><span data-stu-id="38160-129">If you are interested in only a subset of that information, pipe the returned data to the **Select-Object** cmdlet.</span></span> <span data-ttu-id="38160-130">例如，此命令返回用户 Ken myer 的用户，然后使用**选择对象**cmdlet 来限制信息显示的所有数据屏幕 Ken 的 AD DS 显示名称和拨号计划。</span><span class="sxs-lookup"><span data-stu-id="38160-130">For example, this command returns all the data for the user Ken Myer, and then uses the **Select-Object** cmdlet to limit the information displayed onscreen to Ken's AD DS display name and dial plan.</span></span>

```
Get-CsOnlineUser -Identity "Ken Myer" | Select-Object DisplayName, DialPlan
```

<span data-ttu-id="38160-131">下面的命令返回的显示名称和拨号计划的所有用户。</span><span class="sxs-lookup"><span data-stu-id="38160-131">The following command returns the display name and dial plan for all your users.</span></span>

```
Get-CsOnlineUser | Select-Object DisplayName, DialPlan
```

<span data-ttu-id="38160-132">若要查找业务 Online 用户帐户的 Skype 属性，请使用以下命令。</span><span class="sxs-lookup"><span data-stu-id="38160-132">To find the properties of a Skype for Business Online user account, use the following command.</span></span>

```
Get-CsOnlineUser | Get-Member
```

### <a name="return-a-filtered-list-of-users-in-skype-for-business-online"></a><span data-ttu-id="38160-133">返回业务 online 的 Skype 中的用户的已筛选的列表</span><span class="sxs-lookup"><span data-stu-id="38160-133">Return a filtered list of users in Skype for Business Online</span></span>
<span data-ttu-id="38160-134"><a name="BKListofUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="38160-134"></span></span>

<span data-ttu-id="38160-135">通过使用[Get-csonlineuser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet 和_LdapFilter_或_筛选器_参数，您可以轻松地返回一组目标的用户的信息。</span><span class="sxs-lookup"><span data-stu-id="38160-135">By using the [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet and the _LdapFilter_ or _Filter_ parameters, you can easily return information about a targeted set of users.</span></span> <span data-ttu-id="38160-136">例如，此命令返回财务部门中的所有工作的用户。</span><span class="sxs-lookup"><span data-stu-id="38160-136">For example, this command returns all the users who work in the Finance department.</span></span>

```
Get-CsOnlineUser -LdapFilter "department=Finance"
```

## <a name="related-topics"></a><span data-ttu-id="38160-137">相关主题</span><span class="sxs-lookup"><span data-stu-id="38160-137">Related topics</span></span>
[<span data-ttu-id="38160-138">设置您的计算机的业务联机管理使用 Windows PowerShell 的 Skype</span><span class="sxs-lookup"><span data-stu-id="38160-138">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)


