---
title: Lync Server 2013：锁定或解锁用户 PIN
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lock or unlock a user PIN
ms:assetid: 3d293a8a-e182-4547-8b06-2603c3c77329
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688028(v=OCS.15)
ms:contentKeyID: 49733618
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 698bbb2138978cea9ca5b2aa75b5370ea7e11c14
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186395"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lock-or-unlock-a-user-pin-in-lync-server-2013"></a><span data-ttu-id="d4f13-102">在 Lync Server 2013 中锁定或解锁用户 PIN</span><span class="sxs-lookup"><span data-stu-id="d4f13-102">Lock or unlock a user PIN in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4f13-103">_**上次修改的主题：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="d4f13-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="d4f13-104">您可以从 Lync Server 2013 控制面板的 "**用户**" 部分锁定或解锁用户 PIN。</span><span class="sxs-lookup"><span data-stu-id="d4f13-104">You can lock or unlock a user’s PIN from the **Users** section of Lync Server 2013 Control Panel.</span></span>

<div>

## <a name="to-lock-a-users-pin-in-lync-server-control-panel"></a><span data-ttu-id="d4f13-105">在 Lync Server 控制面板中锁定用户的 PIN</span><span class="sxs-lookup"><span data-stu-id="d4f13-105">To lock a user’s PIN in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="d4f13-106">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="d4f13-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d4f13-107">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="d4f13-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d4f13-108">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="d4f13-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d4f13-109">在左侧导航栏中，单击“用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d4f13-109">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="d4f13-110">使用下列方法之一查找用户：</span><span class="sxs-lookup"><span data-stu-id="d4f13-110">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="d4f13-111">在“搜索用户”\*\*\*\* 框中，键入用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“查找”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d4f13-111">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="d4f13-112">如果具有保存的查询，请单击“打开查询”\*\*\*\* 图标，使用“打开”\*\*\*\* 对话框来检索该查询（.usf 文件），然后单击“查找”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d4f13-112">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="d4f13-113">（可选）指定附加搜索条件以缩小结果的范围：</span><span class="sxs-lookup"><span data-stu-id="d4f13-113">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="d4f13-114">单击“添加筛选器”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d4f13-114">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="d4f13-115">通过键入用户属性，或单击下拉列表中的箭头选择属性来输入用户属性。</span><span class="sxs-lookup"><span data-stu-id="d4f13-115">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="d4f13-116">在“等于”\*\*\*\* 下拉列表中，单击运算符（例如“等于”\*\*\*\* 或“不等于”\*\*\*\*）。</span><span class="sxs-lookup"><span data-stu-id="d4f13-116">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="d4f13-117">根据所选的用户属性，通过键入条件或单击下拉列表中的箭头输入用于筛选搜索结果的条件。</span><span class="sxs-lookup"><span data-stu-id="d4f13-117">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        
        <div>
        

        > [!TIP]  
        > <span data-ttu-id="d4f13-118">要向查询中添加附加搜索子句，请单击“添加筛选器”<STRONG></STRONG>。</span><span class="sxs-lookup"><span data-stu-id="d4f13-118">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

        
        </div>
    
    5.  <span data-ttu-id="d4f13-119">单击“查找”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d4f13-119">Click **Find**.</span></span>
    
    6.  <span data-ttu-id="d4f13-120">单击用户，再单击“操作”\*\*\*\*，然后单击“锁定 PIN”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d4f13-120">Click the user, click **Action**, and then click **Lock PIN**.</span></span>

</div>

<div>

## <a name="to-unlock-a-users-pin-in-lync-server-control-panel"></a><span data-ttu-id="d4f13-121">在 Lync Server 控制面板中解锁用户的 PIN</span><span class="sxs-lookup"><span data-stu-id="d4f13-121">To unlock a user’s PIN in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="d4f13-122">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="d4f13-122">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d4f13-123">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="d4f13-123">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d4f13-124">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="d4f13-124">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d4f13-125">在左侧导航栏中，单击“用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d4f13-125">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="d4f13-126">使用下列方法之一查找用户：</span><span class="sxs-lookup"><span data-stu-id="d4f13-126">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="d4f13-127">在“搜索用户”\*\*\*\* 框中，键入用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“查找”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d4f13-127">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="d4f13-128">如果具有保存的查询，请单击“打开查询”\*\*\*\* 图标，使用“打开”\*\*\*\* 对话框来检索该查询（.usf 文件），然后单击“查找”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d4f13-128">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="d4f13-129">（可选）指定附加搜索条件以缩小结果的范围：</span><span class="sxs-lookup"><span data-stu-id="d4f13-129">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="d4f13-130">单击“添加筛选器”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d4f13-130">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="d4f13-131">通过键入用户属性，或单击下拉列表中的箭头选择属性来输入用户属性。</span><span class="sxs-lookup"><span data-stu-id="d4f13-131">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="d4f13-132">在“等于”\*\*\*\* 下拉列表中，单击运算符（例如“等于”\*\*\*\* 或“不等于”\*\*\*\*）。</span><span class="sxs-lookup"><span data-stu-id="d4f13-132">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="d4f13-133">根据所选的用户属性，通过键入条件或单击下拉列表中的箭头输入用于筛选搜索结果的条件。</span><span class="sxs-lookup"><span data-stu-id="d4f13-133">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        
        <div>
        

        > [!TIP]  
        > <span data-ttu-id="d4f13-134">要向查询中添加附加搜索子句，请单击“添加筛选器”<STRONG></STRONG>。</span><span class="sxs-lookup"><span data-stu-id="d4f13-134">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

        
        </div>
    
    5.  <span data-ttu-id="d4f13-135">单击“查找”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d4f13-135">Click **Find**.</span></span>
    
    6.  <span data-ttu-id="d4f13-136">单击用户，再单击“操作”\*\*\*\*，然后单击“解锁 PIN”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d4f13-136">Click the user, click **Action**, and then click **Unlock PIN**.</span></span>

</div>

<div>

## <a name="locking-and-unlocking-user-pins-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="d4f13-137">使用 Windows PowerShell Cmdlet 锁定和解锁用户 Pin</span><span class="sxs-lookup"><span data-stu-id="d4f13-137">Locking and Unlocking User PINs by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="d4f13-138">您可以使用 Windows PowerShell 和 Unlock-csclientpin 和 Unlock-csclientpin cmdlet 锁定和解锁用户 Pin。</span><span class="sxs-lookup"><span data-stu-id="d4f13-138">You can lock and unlock user PINs by using Windows PowerShell and the Lock-CsClientPin and Unlock-CsClientPin cmdlets.</span></span> <span data-ttu-id="d4f13-139">您可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行这些 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d4f13-139">You can run these cmdlets either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="d4f13-140">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。</span><span class="sxs-lookup"><span data-stu-id="d4f13-140">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-lock-a-user-pin"></a><span data-ttu-id="d4f13-141">锁定用户 PIN</span><span class="sxs-lookup"><span data-stu-id="d4f13-141">To lock a user PIN</span></span>

  - <span data-ttu-id="d4f13-p104">若要锁定用户 PIN，请使用 Lock-CsClientPin cmdlet。例如：</span><span class="sxs-lookup"><span data-stu-id="d4f13-p104">To lock a user’s PIN, use the Lock-CsClientPin cmdlet. For example:</span></span>
    
        Lock-CsClientPin -Identity "Ken Myer"

</div>

<div>

## <a name="to-unlock-a-user-pin"></a><span data-ttu-id="d4f13-144">解锁用户 PIN</span><span class="sxs-lookup"><span data-stu-id="d4f13-144">To unlock a user PIN</span></span>

  - <span data-ttu-id="d4f13-p105">若要解锁用户 PIN，请使用 Unlock-CsClientPin cmdlet。例如：</span><span class="sxs-lookup"><span data-stu-id="d4f13-p105">To unlock a user’s PIN, use the Unlock-CsClientPin cmdlet. For example:</span></span>
    
        Unlock-CsClientPin -Identity "Ken Myer"

</div>

<span data-ttu-id="d4f13-147">有关详细信息，请参阅[unlock-csclientpin](https://docs.microsoft.com/powershell/module/skype/Lock-CsClientPin)和[unlock-csclientpin](https://docs.microsoft.com/powershell/module/skype/Unlock-CsClientPin) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="d4f13-147">For more information, see the help topic for the [Lock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/Lock-CsClientPin) and [Unlock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/Unlock-CsClientPin) cmdlets.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

