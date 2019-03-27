---
title: 锁定或解锁用户 PIN Skype 中的业务服务器
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3d293a8a-e182-4547-8b06-2603c3c77329
description: 摘要： 锁定或解锁的 Skype 业务服务器的用户的电话拨入式会议 PIN。
ms.openlocfilehash: fb90cd54ac5f339050adc51378e42d2542e489fa
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895389"
---
# <a name="lock-or-unlock-a-user-pin-in-skype-for-business-server"></a><span data-ttu-id="25ecc-103">锁定或解锁用户 PIN Skype 中的业务服务器</span><span class="sxs-lookup"><span data-stu-id="25ecc-103">Lock or unlock a user PIN in Skype for Business Server</span></span>
 
<span data-ttu-id="25ecc-104">**摘要：** 锁定或解锁的 Skype 业务服务器的用户的电话拨入式会议 PIN。</span><span class="sxs-lookup"><span data-stu-id="25ecc-104">**Summary:** Lock or unlock a user's dial-in conferencing PIN for Skype for Business Server.</span></span>
  
<span data-ttu-id="25ecc-105">可以锁定或解锁用户 PIN，从**用户**部分的 Skype 的业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="25ecc-105">You can lock or unlock a user's PIN from the **Users** section of Skype for Business Server Control Panel.</span></span>
  
### <a name="to-lock-a-users-pin-in-skype-for-business-server-control-panel"></a><span data-ttu-id="25ecc-106">为业务 Server Control Panel Skype 中锁定用户 PIN</span><span class="sxs-lookup"><span data-stu-id="25ecc-106">To lock a user's PIN in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="25ecc-107">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="25ecc-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="25ecc-108">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="25ecc-108">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="25ecc-109">在左导航栏中，单击“用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="25ecc-109">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="25ecc-110">使用下列方法之一查找用户：</span><span class="sxs-lookup"><span data-stu-id="25ecc-110">Use one of the following methods to locate a user:</span></span>
    
    - <span data-ttu-id="25ecc-111">在“搜索用户”\*\*\*\* 框中，键入用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“查找”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="25ecc-111">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
    - <span data-ttu-id="25ecc-112">如果具有保存的查询，请单击“打开查询”\*\*\*\* 图标，使用“打开”\*\*\*\* 对话框来检索该查询（.usf 文件），然后单击“查找”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="25ecc-112">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="25ecc-113">（可选）指定附加搜索条件以缩小结果的范围：</span><span class="sxs-lookup"><span data-stu-id="25ecc-113">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="25ecc-114">a.</span><span class="sxs-lookup"><span data-stu-id="25ecc-114">a.</span></span> <span data-ttu-id="25ecc-115">单击“添加筛选器”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="25ecc-115">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="25ecc-116">b.</span><span class="sxs-lookup"><span data-stu-id="25ecc-116">b.</span></span> <span data-ttu-id="25ecc-117">通过键入用户属性，或单击下拉列表中的箭头选择属性来输入用户属性。</span><span class="sxs-lookup"><span data-stu-id="25ecc-117">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="25ecc-118">c.</span><span class="sxs-lookup"><span data-stu-id="25ecc-118">c.</span></span> <span data-ttu-id="25ecc-119">在“等于”\*\*\*\* 下拉列表中，单击运算符（例如“等于”\*\*\*\* 或“不等于”\*\*\*\*）。</span><span class="sxs-lookup"><span data-stu-id="25ecc-119">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="25ecc-120">d.</span><span class="sxs-lookup"><span data-stu-id="25ecc-120">d.</span></span> <span data-ttu-id="25ecc-121">根据所选的用户属性，通过键入条件或单击下拉列表中的箭头输入用于筛选搜索结果的条件。</span><span class="sxs-lookup"><span data-stu-id="25ecc-121">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="25ecc-122">要向查询中添加附加搜索子句，请单击“添加筛选器”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="25ecc-122">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="25ecc-123">e。</span><span class="sxs-lookup"><span data-stu-id="25ecc-123">e.</span></span> <span data-ttu-id="25ecc-124">单击“查找”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="25ecc-124">Click **Find**.</span></span>
    
   <span data-ttu-id="25ecc-125">f。</span><span class="sxs-lookup"><span data-stu-id="25ecc-125">f.</span></span> <span data-ttu-id="25ecc-126">单击用户，再单击“操作”\*\*\*\*，然后单击“锁定 PIN”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="25ecc-126">Click the user, click **Action**, and then click **Lock PIN**.</span></span>
    
### <a name="to-unlock-a-users-pin-in-skype-for-business-server-control-panel"></a><span data-ttu-id="25ecc-127">Skype 中的用户的 PIN 解锁的业务 Server Control Panel</span><span class="sxs-lookup"><span data-stu-id="25ecc-127">To unlock a user's PIN in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="25ecc-128">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="25ecc-128">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="25ecc-129">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="25ecc-129">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="25ecc-130">在左导航栏中，单击“用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="25ecc-130">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="25ecc-131">使用下列方法之一查找用户：</span><span class="sxs-lookup"><span data-stu-id="25ecc-131">Use one of the following methods to locate a user:</span></span>
    
   - <span data-ttu-id="25ecc-132">在“搜索用户”\*\*\*\* 框中，键入用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“查找”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="25ecc-132">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
   - <span data-ttu-id="25ecc-133">如果具有保存的查询，请单击“打开查询”\*\*\*\* 图标，使用“打开”\*\*\*\* 对话框来检索该查询（.usf 文件），然后单击“查找”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="25ecc-133">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="25ecc-134">（可选）指定附加搜索条件以缩小结果的范围：</span><span class="sxs-lookup"><span data-stu-id="25ecc-134">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="25ecc-135">a.</span><span class="sxs-lookup"><span data-stu-id="25ecc-135">a.</span></span> <span data-ttu-id="25ecc-136">单击“添加筛选器”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="25ecc-136">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="25ecc-137">b.</span><span class="sxs-lookup"><span data-stu-id="25ecc-137">b.</span></span> <span data-ttu-id="25ecc-138">通过键入用户属性，或单击下拉列表中的箭头选择属性来输入用户属性。</span><span class="sxs-lookup"><span data-stu-id="25ecc-138">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="25ecc-139">c.</span><span class="sxs-lookup"><span data-stu-id="25ecc-139">c.</span></span> <span data-ttu-id="25ecc-140">在“等于”\*\*\*\* 下拉列表中，单击运算符（例如“等于”\*\*\*\* 或“不等于”\*\*\*\*）。</span><span class="sxs-lookup"><span data-stu-id="25ecc-140">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="25ecc-141">d.</span><span class="sxs-lookup"><span data-stu-id="25ecc-141">d.</span></span> <span data-ttu-id="25ecc-142">根据所选的用户属性，通过键入条件或单击下拉列表中的箭头输入用于筛选搜索结果的条件。</span><span class="sxs-lookup"><span data-stu-id="25ecc-142">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="25ecc-143">要向查询中添加附加搜索子句，请单击“添加筛选器”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="25ecc-143">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="25ecc-144">e。</span><span class="sxs-lookup"><span data-stu-id="25ecc-144">e.</span></span> <span data-ttu-id="25ecc-145">单击“查找”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="25ecc-145">Click **Find**.</span></span>
    
   <span data-ttu-id="25ecc-146">f。</span><span class="sxs-lookup"><span data-stu-id="25ecc-146">f.</span></span> <span data-ttu-id="25ecc-147">单击用户，再单击“操作”\*\*\*\*，然后单击“解锁 PIN”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="25ecc-147">Click the user, click **Action**, and then click **Unlock PIN**.</span></span>
    
## <a name="locking-and-unlocking-user-pins-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="25ecc-148">使用 Windows PowerShell Cmdlet 锁定和解锁用户 Pin</span><span class="sxs-lookup"><span data-stu-id="25ecc-148">Locking and Unlocking User PINs by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="25ecc-149">您可以锁定和解锁用户 Pin by using Windows PowerShell 和 Lock-csclientpin 和 Unlock-csclientpin cmdlet。</span><span class="sxs-lookup"><span data-stu-id="25ecc-149">You can lock and unlock user PINs by using Windows PowerShell and the Lock-CsClientPin and Unlock-CsClientPin cmdlets.</span></span> <span data-ttu-id="25ecc-150">可以从 Skype 业务 Server 命令行管理程序或从 Windows PowerShell 远程会话来运行这些 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="25ecc-150">You can run these cmdlets either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="25ecc-151">有关使用远程 Windows PowerShell 连接到 Skype 业务服务器的详细信息，请参阅博客文章["快速启动:: 管理 Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876)。</span><span class="sxs-lookup"><span data-stu-id="25ecc-151">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="25ecc-152">过程是相同的 Skype 业务服务器。</span><span class="sxs-lookup"><span data-stu-id="25ecc-152">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-lock-a-user-pin"></a><span data-ttu-id="25ecc-153">锁定用户 PIN</span><span class="sxs-lookup"><span data-stu-id="25ecc-153">To lock a user PIN</span></span>

- <span data-ttu-id="25ecc-154">若要锁定用户 PIN，请使用 Lock-csclientpin cmdlet。</span><span class="sxs-lookup"><span data-stu-id="25ecc-154">To lock a user's PIN, use the Lock-CsClientPin cmdlet.</span></span> <span data-ttu-id="25ecc-155">例如：</span><span class="sxs-lookup"><span data-stu-id="25ecc-155">For example:</span></span>
    
  ```
  Lock-CsClientPin -Identity "Ken Myer"
  ```

### <a name="to-unlock-a-user-pin"></a><span data-ttu-id="25ecc-156">解锁用户 PIN</span><span class="sxs-lookup"><span data-stu-id="25ecc-156">To unlock a user PIN</span></span>

- <span data-ttu-id="25ecc-157">若要解除锁定用户 PIN，请使用 Unlock-csclientpin cmdlet。</span><span class="sxs-lookup"><span data-stu-id="25ecc-157">To unlock a user's PIN, use the Unlock-CsClientPin cmdlet.</span></span> <span data-ttu-id="25ecc-158">例如：</span><span class="sxs-lookup"><span data-stu-id="25ecc-158">For example:</span></span>
    
  ```
  Unlock-CsClientPin -Identity "Ken Myer"
  ```

<span data-ttu-id="25ecc-159">有关详细信息，请参阅[Lock-csclientpin](https://docs.microsoft.com/powershell/module/skype/lock-csclientpin?view=skype-ps)和[Unlock-csclientpin](https://docs.microsoft.com/powershell/module/skype/unlock-csclientpin?view=skype-ps) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="25ecc-159">For more information, see the help topic for the [Lock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/lock-csclientpin?view=skype-ps) and [Unlock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/unlock-csclientpin?view=skype-ps) cmdlets.</span></span>
