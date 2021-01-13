---
title: 在 Skype for Business Server 中查看用户 PIN 信息
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 59e38117-8112-4851-82ac-a746ffa0f89d
description: 摘要：在 Skype for Business Server 中查看用户 PIN 信息。
ms.openlocfilehash: fa5385c1ca318c4a41e17088368d9928fd6d0e0b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806502"
---
# <a name="view-user-pin-information-in-skype-for-business-server"></a><span data-ttu-id="00411-103">在 Skype for Business Server 中查看用户 PIN 信息</span><span class="sxs-lookup"><span data-stu-id="00411-103">View user PIN information in Skype for Business Server</span></span>
 
<span data-ttu-id="00411-104">**摘要：** 在 Skype for Business Server 中查看用户 PIN 信息。</span><span class="sxs-lookup"><span data-stu-id="00411-104">**Summary:** View user PIN information in Skype for Business Server.</span></span>
  
<span data-ttu-id="00411-105">要以经过身份验证的用户身份加入电话拨入式会议，具有 Active Directory 域服务 (AD DS) 凭据的 Skype for Business Server 用户需要个人标识号 (PIN) 。</span><span class="sxs-lookup"><span data-stu-id="00411-105">To join a dial-in conference as an authenticated user, a Skype for Business Server user with Active Directory Domain Services (AD DS) credentials requires a personal identification number (PIN).</span></span> <span data-ttu-id="00411-106">可以从 Skype for Business Server 控制面板查看用户的 PIN 信息。</span><span class="sxs-lookup"><span data-stu-id="00411-106">You can view a user's PIN information from Skype for Business Server Control Panel.</span></span>
  
> [!NOTE]
> <span data-ttu-id="00411-107">您可以查看 PIN 状态信息（如是否已设置 PIN 或上次更改 PIN 的时间），但无法通过查看 PIN 状态来查看当前 PIN。</span><span class="sxs-lookup"><span data-stu-id="00411-107">You can view PIN status information such as whether the PIN has been set or when the PIN was last changed, but you cannot see the current PIN by looking at the PIN status.</span></span> <span data-ttu-id="00411-108">如果用户丢失了 PIN，可以按照"在 Skype for Business Server 中设置用户的电话拨入式会议 [PIN"中的过程重置 PIN](set-a-user-s-dial-in-conferencing-pin.md)</span><span class="sxs-lookup"><span data-stu-id="00411-108">If a user has lost their PIN, you can reset it by following the procedures in [Set a user's dial-in conferencing PIN in Skype for Business Server](set-a-user-s-dial-in-conferencing-pin.md)</span></span>
  
### <a name="to-view-a-users-pin-in-skype-for-business-server-control-panel"></a><span data-ttu-id="00411-109">在 Skype for Business Server 控制面板中查看用户的 PIN</span><span class="sxs-lookup"><span data-stu-id="00411-109">To view a user's PIN in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="00411-110">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="00411-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="00411-111">打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="00411-111">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="00411-112">在左侧导航栏中，单击“用户”。</span><span class="sxs-lookup"><span data-stu-id="00411-112">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="00411-113">使用下列方法之一查找用户：</span><span class="sxs-lookup"><span data-stu-id="00411-113">Use one of the following methods to locate a user:</span></span>
    
   - <span data-ttu-id="00411-114">在“搜索用户”框中，键入用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“查找”。</span><span class="sxs-lookup"><span data-stu-id="00411-114">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
   - <span data-ttu-id="00411-115">如果具有保存的查询，请单击“打开查询”图标，使用“打开”对话框来检索该查询（.usf 文件），然后单击“查找”。</span><span class="sxs-lookup"><span data-stu-id="00411-115">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="00411-116">（可选）指定附加搜索条件以缩小结果的范围：</span><span class="sxs-lookup"><span data-stu-id="00411-116">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="00411-117">a.</span><span class="sxs-lookup"><span data-stu-id="00411-117">a.</span></span> <span data-ttu-id="00411-118">单击“添加筛选器”。</span><span class="sxs-lookup"><span data-stu-id="00411-118">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="00411-119">b.</span><span class="sxs-lookup"><span data-stu-id="00411-119">b.</span></span> <span data-ttu-id="00411-120">通过键入用户属性，或单击下拉列表中的箭头选择属性来输入用户属性。</span><span class="sxs-lookup"><span data-stu-id="00411-120">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="00411-121">c.</span><span class="sxs-lookup"><span data-stu-id="00411-121">c.</span></span> <span data-ttu-id="00411-122">在“等于”下拉列表中，单击运算符（例如“等于”或“不等于”）。</span><span class="sxs-lookup"><span data-stu-id="00411-122">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="00411-123">d.</span><span class="sxs-lookup"><span data-stu-id="00411-123">d.</span></span> <span data-ttu-id="00411-124">根据所选的用户属性，通过键入条件或单击下拉列表中的箭头输入用于筛选搜索结果的条件。</span><span class="sxs-lookup"><span data-stu-id="00411-124">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="00411-125">要向查询中添加附加搜索子句，请单击“添加筛选器”。</span><span class="sxs-lookup"><span data-stu-id="00411-125">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="00411-126">e.</span><span class="sxs-lookup"><span data-stu-id="00411-126">e.</span></span> <span data-ttu-id="00411-127">单击“查找”。</span><span class="sxs-lookup"><span data-stu-id="00411-127">Click **Find**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="00411-p108">如果锁定了 PIN，则必须解锁 PIN，然后才能对其进行设置。要解锁 PIN，请单击用户，再单击“操作”，然后单击“解锁 PIN”。</span><span class="sxs-lookup"><span data-stu-id="00411-p108">If the PIN is locked, you must unlock the PIN before you can set it. To unlock the PIN, click the user, click **Action**, and then click **Unlock PIN**.</span></span> 
  
6. <span data-ttu-id="00411-130">在搜索结果中单击某个用户，再单击“操作”，然后单击“查看 PIN 状态”。</span><span class="sxs-lookup"><span data-stu-id="00411-130">Click a user in the search results, click **Action**, and then click **View PIN status**.</span></span>
    
## <a name="viewing-user-pin-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="00411-131">使用 cmdlet 查看Windows PowerShell PIN 信息</span><span class="sxs-lookup"><span data-stu-id="00411-131">Viewing User PIN Information by Using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="00411-132">您可以使用 Get-CsClientPinInfo cmdlet 查看用户 PIN 信息。</span><span class="sxs-lookup"><span data-stu-id="00411-132">You can view user PIN information by using the Get-CsClientPinInfo cmdlet.</span></span> <span data-ttu-id="00411-133">此 cmdlet 可以从 Skype for Business Server 命令行管理程序运行，也可以从远程会话Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="00411-133">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="00411-134">有关使用远程部署Windows PowerShell Skype for Business Server 的详细信息，请参阅博客文章"[快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。](https://go.microsoft.com/fwlink/p/?linkId=255876)</span><span class="sxs-lookup"><span data-stu-id="00411-134">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="00411-135">此过程在 Skype for Business Server 中相同。</span><span class="sxs-lookup"><span data-stu-id="00411-135">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-view-user-pin-information"></a><span data-ttu-id="00411-136">查看用户 PIN 信息</span><span class="sxs-lookup"><span data-stu-id="00411-136">To view user PIN information</span></span>

<span data-ttu-id="00411-137">若要查看用户的 PIN 信息，请在 Skype for Business Server 命令行管理程序 中键入类似如下的命令，然后按 Enter：</span><span class="sxs-lookup"><span data-stu-id="00411-137">To view PIN information for a user, type a command similar to the following in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
  ```PowerShell
  Get-CsClientPinInfo -Identity "Ken Myer"
  ```

<span data-ttu-id="00411-138">这将返回与以下类似的信息：</span><span class="sxs-lookup"><span data-stu-id="00411-138">That will return information similar to this:</span></span>

<pre>
Identity          : sip:kenmyer@litwareinc.com
IsPinSet          : False
IsLockedOut       : False
LastPinChangeTime : 9/25/2012 1:35:03 PM
PinExpirationTime :
</pre>

<span data-ttu-id="00411-139">有关详细信息，请参阅 [Get-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="00411-139">For more information, see the help topic for the [Get-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="00411-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="00411-140">See also</span></span>

[<span data-ttu-id="00411-141">在 Skype for Business Server 中设置用户的电话拨入式会议 PIN</span><span class="sxs-lookup"><span data-stu-id="00411-141">Set a user's dial-in conferencing PIN in Skype for Business Server</span></span>](set-a-user-s-dial-in-conferencing-pin.md)
  
[<span data-ttu-id="00411-142">在 Skype for Business Server 中锁定或解锁用户 PIN</span><span class="sxs-lookup"><span data-stu-id="00411-142">Lock or unlock a user PIN in Skype for Business Server</span></span>](lock-or-unlock-a-user-pin.md)
