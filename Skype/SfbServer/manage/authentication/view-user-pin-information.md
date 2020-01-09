---
title: 查看 Skype for Business 服务器中的用户 PIN 信息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 59e38117-8112-4851-82ac-a746ffa0f89d
description: 摘要：查看 Skype for Business 服务器中的用户 PIN 信息。
ms.openlocfilehash: e0a74d980be4c77c5fe92f9e0d871f238a7271f5
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991937"
---
# <a name="view-user-pin-information-in-skype-for-business-server"></a><span data-ttu-id="38299-103">查看 Skype for Business 服务器中的用户 PIN 信息</span><span class="sxs-lookup"><span data-stu-id="38299-103">View user PIN information in Skype for Business Server</span></span>
 
<span data-ttu-id="38299-104">**摘要：** 查看 Skype for Business 服务器中的用户 PIN 信息。</span><span class="sxs-lookup"><span data-stu-id="38299-104">**Summary:** View user PIN information in Skype for Business Server.</span></span>
  
<span data-ttu-id="38299-105">若要将电话拨入式会议作为经过身份验证的用户加入，使用 Active Directory 域服务（AD DS）凭据的 Skype for business 服务器用户需要一个个人识别码（PIN）。</span><span class="sxs-lookup"><span data-stu-id="38299-105">To join a dial-in conference as an authenticated user, a Skype for Business Server user with Active Directory Domain Services (AD DS) credentials requires a personal identification number (PIN).</span></span> <span data-ttu-id="38299-106">您可以从 Skype for Business Server 控制面板查看用户的 PIN 信息。</span><span class="sxs-lookup"><span data-stu-id="38299-106">You can view a user's PIN information from Skype for Business Server Control Panel.</span></span>
  
> [!NOTE]
> <span data-ttu-id="38299-107">您可以查看 PIN 状态信息（如是否已设置 PIN 或上次更改 PIN 的时间），但无法通过查看 PIN 状态来查看当前 PIN。</span><span class="sxs-lookup"><span data-stu-id="38299-107">You can view PIN status information such as whether the PIN has been set or when the PIN was last changed, but you cannot see the current PIN by looking at the PIN status.</span></span> <span data-ttu-id="38299-108">如果用户已丢失 PIN，则可以按照在[Skype For Business 服务器中设置用户的电话拨入式会议 PIN](set-a-user-s-dial-in-conferencing-pin.md)中的过程重置它。</span><span class="sxs-lookup"><span data-stu-id="38299-108">If a user has lost their PIN, you can reset it by following the procedures in [Set a user's dial-in conferencing PIN in Skype for Business Server](set-a-user-s-dial-in-conferencing-pin.md)</span></span>
  
### <a name="to-view-a-users-pin-in-skype-for-business-server-control-panel"></a><span data-ttu-id="38299-109">在 "Skype for Business 服务器" 控制面板中查看用户的 PIN</span><span class="sxs-lookup"><span data-stu-id="38299-109">To view a user's PIN in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="38299-110">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="38299-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="38299-111">打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="38299-111">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="38299-112">在左导航栏中，单击“用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="38299-112">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="38299-113">使用下列方法之一查找用户：</span><span class="sxs-lookup"><span data-stu-id="38299-113">Use one of the following methods to locate a user:</span></span>
    
   - <span data-ttu-id="38299-114">在“搜索用户”\*\*\*\* 框中，键入用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“查找”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="38299-114">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
   - <span data-ttu-id="38299-115">如果具有保存的查询，请单击“打开查询”\*\*\*\* 图标，使用“打开”\*\*\*\* 对话框来检索该查询（.usf 文件），然后单击“查找”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="38299-115">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="38299-116">（可选）指定附加搜索条件以缩小结果的范围：</span><span class="sxs-lookup"><span data-stu-id="38299-116">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="38299-117">a.</span><span class="sxs-lookup"><span data-stu-id="38299-117">a.</span></span> <span data-ttu-id="38299-118">单击“添加筛选器”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="38299-118">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="38299-119">b.</span><span class="sxs-lookup"><span data-stu-id="38299-119">b.</span></span> <span data-ttu-id="38299-120">通过键入用户属性，或单击下拉列表中的箭头选择属性来输入用户属性。</span><span class="sxs-lookup"><span data-stu-id="38299-120">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="38299-121">c.</span><span class="sxs-lookup"><span data-stu-id="38299-121">c.</span></span> <span data-ttu-id="38299-122">在“等于”\*\*\*\* 下拉列表中，单击运算符（例如“等于”\*\*\*\* 或“不等于”\*\*\*\*）。</span><span class="sxs-lookup"><span data-stu-id="38299-122">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="38299-123">d.</span><span class="sxs-lookup"><span data-stu-id="38299-123">d.</span></span> <span data-ttu-id="38299-124">根据所选的用户属性，通过键入条件或单击下拉列表中的箭头输入用于筛选搜索结果的条件。</span><span class="sxs-lookup"><span data-stu-id="38299-124">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="38299-125">要向查询中添加附加搜索子句，请单击“添加筛选器”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="38299-125">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="38299-126">e.i.</span><span class="sxs-lookup"><span data-stu-id="38299-126">e.</span></span> <span data-ttu-id="38299-127">单击“查找”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="38299-127">Click **Find**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="38299-p108">如果锁定了 PIN，则必须解锁 PIN，然后才能对其进行设置。要解锁 PIN，请单击用户，再单击“操作”\*\*\*\*，然后单击“解锁 PIN”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="38299-p108">If the PIN is locked, you must unlock the PIN before you can set it. To unlock the PIN, click the user, click **Action**, and then click **Unlock PIN**.</span></span> 
  
6. <span data-ttu-id="38299-130">在搜索结果中单击某个用户，再单击“操作”\*\*\*\*，然后单击“查看 PIN 状态”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="38299-130">Click a user in the search results, click **Action**, and then click **View PIN status**.</span></span>
    
## <a name="viewing-user-pin-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="38299-131">使用 Windows PowerShell cmdlet 查看用户 PIN 信息</span><span class="sxs-lookup"><span data-stu-id="38299-131">Viewing User PIN Information by Using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="38299-132">您可以使用 Get-CsClientPinInfo cmdlet 查看用户 PIN 信息。</span><span class="sxs-lookup"><span data-stu-id="38299-132">You can view user PIN information by using the Get-CsClientPinInfo cmdlet.</span></span> <span data-ttu-id="38299-133">此 cmdlet 既可以从 Skype for Business 服务器管理外壳运行，也可以从 Windows PowerShell 的远程会话运行。</span><span class="sxs-lookup"><span data-stu-id="38299-133">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="38299-134">有关使用远程 Windows PowerShell 连接到 Skype for Business 服务器的详细信息，请参阅博客文章["快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"](https://go.microsoft.com/fwlink/p/?linkId=255876)。</span><span class="sxs-lookup"><span data-stu-id="38299-134">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="38299-135">在 Skype for Business 服务器中，此过程是相同的。</span><span class="sxs-lookup"><span data-stu-id="38299-135">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-view-user-pin-information"></a><span data-ttu-id="38299-136">查看用户 PIN 信息</span><span class="sxs-lookup"><span data-stu-id="38299-136">To view user PIN information</span></span>

<span data-ttu-id="38299-137">若要查看用户的 PIN 信息，请在 Skype for Business Server 命令行管理器中键入类似于以下内容的命令，然后按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="38299-137">To view PIN information for a user, type a command similar to the following in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
  ```PowerShell
  Get-CsClientPinInfo -Identity "Ken Myer"
  ```

<span data-ttu-id="38299-138">这将返回与以下类似的信息：</span><span class="sxs-lookup"><span data-stu-id="38299-138">That will return information similar to this:</span></span>

<pre>
Identity          : sip:kenmyer@litwareinc.com
IsPinSet          : False
IsLockedOut       : False
LastPinChangeTime : 9/25/2012 1:35:03 PM
PinExpirationTime :
</pre>

<span data-ttu-id="38299-139">有关详细信息，请参阅[CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="38299-139">For more information, see the help topic for the [Get-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="38299-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="38299-140">See also</span></span>

[<span data-ttu-id="38299-141">在 Skype for Business 服务器中设置用户的电话拨入式会议 PIN</span><span class="sxs-lookup"><span data-stu-id="38299-141">Set a user's dial-in conferencing PIN in Skype for Business Server</span></span>](set-a-user-s-dial-in-conferencing-pin.md)
  
[<span data-ttu-id="38299-142">在 Skype for Business 服务器中锁定或解锁用户 PIN</span><span class="sxs-lookup"><span data-stu-id="38299-142">Lock or unlock a user PIN in Skype for Business Server</span></span>](lock-or-unlock-a-user-pin.md)
