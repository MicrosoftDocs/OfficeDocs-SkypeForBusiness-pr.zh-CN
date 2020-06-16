---
title: 将多个用户移动到引导池
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Move multiple users to the pilot pool
ms:assetid: 90d0590c-922c-4933-b778-9dd850b59310
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205096(v=OCS.15)
ms:contentKeyID: 48184838
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a5a92b0438e72be0ecb5acaa1b8e1886768ad59
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755396"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-multiple-users-to-the-pilot-pool"></a><span data-ttu-id="d64c0-102">将多个用户移动到引导池</span><span class="sxs-lookup"><span data-stu-id="d64c0-102">Move multiple users to the pilot pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d64c0-103">_**上次修改的主题：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="d64c0-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="d64c0-104">您可以使用 Lync Server 2013 控制面板或 Lync Server 2013 命令行管理程序将您的 Lync Server 2010 池中的多个用户移动到 Lync Server 2013 引导池。</span><span class="sxs-lookup"><span data-stu-id="d64c0-104">You can move multiple users from your Lync Server 2010 pool to your Lync Server 2013 pilot pool using Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-control-panel"></a><span data-ttu-id="d64c0-105">使用 Lync Server 2013 控制面板移动多个用户</span><span class="sxs-lookup"><span data-stu-id="d64c0-105">To move multiple users by using the Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="d64c0-106">打开“Lync Server 控制面板”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d64c0-106">Open **Lync Server Control Panel**.</span></span>

2.  <span data-ttu-id="d64c0-107">单击“用户”\*\*\*\*，再单击“搜索”，然后单击“查找”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d64c0-107">Click **Users**, click Search, and then click **Find**.</span></span>

3.  <span data-ttu-id="d64c0-108">选择要移至 Lync Server 2013 池的两个用户。</span><span class="sxs-lookup"><span data-stu-id="d64c0-108">Select two users that you want to move to the Lync Server 2013 pool.</span></span> <span data-ttu-id="d64c0-109">在本例中，我们将移动用户 Chen Yang 和 Claus Hansen。</span><span class="sxs-lookup"><span data-stu-id="d64c0-109">In this example, we will move users Chen Yang and Claus Hansen.</span></span>
    
    <span data-ttu-id="d64c0-110">![将用户移动到特定的注册池](images/JJ205096.70d510e1-8e6b-40a5-a80b-27cbc63fc337(OCS.15).jpg "将用户移动到特定的注册池")</span><span class="sxs-lookup"><span data-stu-id="d64c0-110">![Move users to specific register pool](images/JJ205096.70d510e1-8e6b-40a5-a80b-27cbc63fc337(OCS.15).jpg "Move users to specific register pool")</span></span>  

4.  <span data-ttu-id="d64c0-111">在“操作”\*\*\*\* 菜单中，选择“将所选用户移动到池”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d64c0-111">From the **Action** menu, select **Move selected users to pool**.</span></span>

5.  <span data-ttu-id="d64c0-112">从下拉列表中，选择 "Lync Server 2013" 池。</span><span class="sxs-lookup"><span data-stu-id="d64c0-112">From the drop-down list, select the Lync Server 2013 pool.</span></span>

6.  <span data-ttu-id="d64c0-113">单击“操作”\*\*\*\*，然后单击“将所选用户移动到池”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d64c0-113">Click **Action** and then click **Move selected users to pool**.</span></span> <span data-ttu-id="d64c0-114">单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="d64c0-114">Click OK.</span></span>
    
    <span data-ttu-id="d64c0-115">!["移动用户，目标注册器池" 对话框](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png ""移动用户，目标注册器池" 对话框")</span><span class="sxs-lookup"><span data-stu-id="d64c0-115">![Move Users, destination registrar pool dialog box](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Move Users, destination registrar pool dialog box")</span></span>  

7.  <span data-ttu-id="d64c0-116">确认用户的 "**注册器池**" 列现在包含 Lync Server 2013 池，这表明已成功移动用户。</span><span class="sxs-lookup"><span data-stu-id="d64c0-116">Verify that the **Registrar pool** column for the users now contains the Lync Server 2013 pool, which indicates that the users have been successfully moved.</span></span>

</div>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="d64c0-117">使用 Lync Server 2013 命令行管理程序移动多个用户</span><span class="sxs-lookup"><span data-stu-id="d64c0-117">To move multiple users by using the Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="d64c0-118">打开 Lync Server 2013 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="d64c0-118">Open the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="d64c0-119">在命令行中，键入以下内容，并**User1**将 User1**和用户**2 替换为要移动的特定用户名，并将**池 \_ FQDN**替换为目标池的名称。</span><span class="sxs-lookup"><span data-stu-id="d64c0-119">At the command line, type the following and replace **User1** and **User2** with specific user names you want to move and replace **pool\_FQDN** with the name of the destination pool.</span></span> <span data-ttu-id="d64c0-120">在本例中，我们将移动用户 Hao Chen 和 Katie Jordan。</span><span class="sxs-lookup"><span data-stu-id="d64c0-120">In this example we will move users Hao Chen and Katie Jordan.</span></span>
    
        Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
    
    <span data-ttu-id="d64c0-121">![PowerShell Get-csuser cmdlet 示例](images/JJ205096.767ff9fc-755d-4a80-a710-5b1367aecbe0(OCS.15).jpg "PowerShell Get-csuser cmdlet 示例")</span><span class="sxs-lookup"><span data-stu-id="d64c0-121">![Example of PowerShell Get-CsUser cmdlet](images/JJ205096.767ff9fc-755d-4a80-a710-5b1367aecbe0(OCS.15).jpg "Example of PowerShell Get-CsUser cmdlet")</span></span>  

3.  <span data-ttu-id="d64c0-122">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="d64c0-122">At the command line, type the following</span></span>
    
        Get-CsUser -Identity "User1"

4.  <span data-ttu-id="d64c0-123">**注册器池**标识现在应指向您在上一步中指定为**池 \_ FQDN**的池。</span><span class="sxs-lookup"><span data-stu-id="d64c0-123">The **Registrar Pool** identity should now point to the pool you specified as **pool\_FQDN** in the previous step.</span></span> <span data-ttu-id="d64c0-124">存在该标识即可确认已成功移动用户。</span><span class="sxs-lookup"><span data-stu-id="d64c0-124">The presence of this identity confirms that the user has been successfully moved.</span></span> <span data-ttu-id="d64c0-125">重复此步骤以确认 **User2** 已移动。</span><span class="sxs-lookup"><span data-stu-id="d64c0-125">Repeat step to verify **User2** has been moved.</span></span>
    
    <span data-ttu-id="d64c0-126">![PowerShell UsUser cmdlet 的输出](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "PowerShell UsUser cmdlet 的输出")</span><span class="sxs-lookup"><span data-stu-id="d64c0-126">![Output of PowerShell Get-UsUser -Identity cmdlet](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "Output of PowerShell Get-UsUser -Identity  cmdlet")</span></span>  

</div>

<div>

## <a name="to-move-all-users-at-the-same-time-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="d64c0-127">使用 Lync Server 2013 命令行管理程序同时移动所有用户</span><span class="sxs-lookup"><span data-stu-id="d64c0-127">To move all users at the same time by using the Lync Server 2013 Management Shell</span></span>

<span data-ttu-id="d64c0-128">在此示例中，所有用户都已返回到 Lync Server 2010 池（pool01.contoso.net）。</span><span class="sxs-lookup"><span data-stu-id="d64c0-128">In this example, all users have been returned to the Lync Server 2010 pool (pool01.contoso.net).</span></span> <span data-ttu-id="d64c0-129">使用 Lync Server 2013 命令行管理程序，我们将同时将所有用户移动到 Lync Server 2013 池（pool02.contoso.net）。</span><span class="sxs-lookup"><span data-stu-id="d64c0-129">Using the Lync Server 2013 Management Shell, we will move all users at the same time to the Lync Server 2013 pool (pool02.contoso.net).</span></span>

1.  <span data-ttu-id="d64c0-130">打开**Lync Server 2013 命令行管理**程序。</span><span class="sxs-lookup"><span data-stu-id="d64c0-130">Open the **Lync Server 2013 Management Shell**.</span></span>

2.  <span data-ttu-id="d64c0-131">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="d64c0-131">At the command line, type the following:</span></span>
    
        Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
    
    <span data-ttu-id="d64c0-132">![PowerShell cmdlet 和命令行管理程序中的结果](images/JJ205096.1e57ccb1-9378-4dc7-82b7-dcaa63a285c6(OCS.15).png "PowerShell cmdlet 和命令行管理程序中的结果")</span><span class="sxs-lookup"><span data-stu-id="d64c0-132">![PowerShell cmdlet and results in Management Shell](images/JJ205096.1e57ccb1-9378-4dc7-82b7-dcaa63a285c6(OCS.15).png "PowerShell cmdlet and results in Management Shell")</span></span>  

3.  <span data-ttu-id="d64c0-133">接下来，为试点用户之一运行 **Get-CsUser**。</span><span class="sxs-lookup"><span data-stu-id="d64c0-133">Next, run **Get-CsUser** for one of the pilot users.</span></span>
    
        Get-CsUser -Identity "Hao Chen"

4.  <span data-ttu-id="d64c0-134">每个用户的**注册器池**标识现在指向您 \_ 在上一步中指定为 "池 FQDN" 的池。</span><span class="sxs-lookup"><span data-stu-id="d64c0-134">The **Registrar Pool** identity for each user now points to the pool you specified as “pool\_FQDN” in the previous step.</span></span> <span data-ttu-id="d64c0-135">存在该标识即可确认已成功移动用户。</span><span class="sxs-lookup"><span data-stu-id="d64c0-135">The presence of this identity confirms that the user has been successfully moved.</span></span>

5.  <span data-ttu-id="d64c0-136">此外，我们还可以查看 Lync Server 2013 控制面板中的用户列表，并验证注册器池值是否现在指向 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="d64c0-136">Additionally, we can view the list of users in the Lync Server 2013 Control Panel and verify that the Registrar Pool value now points to the Lync Server 2013 pool.</span></span>
    
    <span data-ttu-id="d64c0-137">![Lync Server 2013 控制面板用户列表](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Lync Server 2013 控制面板用户列表")</span><span class="sxs-lookup"><span data-stu-id="d64c0-137">![Lync Server 2013 Control Panel user list](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Lync Server 2013 Control Panel user list")</span></span>  

</div>

</div>

<span> </span>

</div>

</div>

</div>

