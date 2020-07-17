---
title: 将多个用户移动到引导池
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Move multiple users to the pilot pool
ms:assetid: 9492797f-2a26-4773-8ad2-97cb53fa68fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688143(v=OCS.15)
ms:contentKeyID: 49733745
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 41c663566605529b25d9890bb31cba462364c813
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756461"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-multiple-users-to-the-pilot-pool"></a><span data-ttu-id="c5615-102">将多个用户移动到引导池</span><span class="sxs-lookup"><span data-stu-id="c5615-102">Move multiple users to the pilot pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c5615-103">_**上次修改的主题：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="c5615-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="c5615-104">您可以使用 Lync Server 2013 控制面板或 Lync Server 2013 命令行管理程序，将多个用户从 Office 通信服务器 2007 R2 池移动到 Lync Server 2013 引导池。</span><span class="sxs-lookup"><span data-stu-id="c5615-104">You can move multiple users from your Office Communications Server 2007 R2 pool to your Lync Server 2013 pilot pool using Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-control-panel"></a><span data-ttu-id="c5615-105">使用 Lync Server 2013 控制面板移动多个用户</span><span class="sxs-lookup"><span data-stu-id="c5615-105">To move multiple users by using the Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="c5615-106">打开“Lync Server 控制面板”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c5615-106">Open **Lync Server Control Panel**.</span></span>

2.  <span data-ttu-id="c5615-107">从“用户搜索”\*\*\*\* 选项卡中，单击“搜索”\*\*\*\* 按钮。</span><span class="sxs-lookup"><span data-stu-id="c5615-107">From the **User Search** tab, click the **Search** button.</span></span>

3.  <span data-ttu-id="c5615-108">接下来，单击“添加筛选器”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c5615-108">Next, click **Add Filter**.</span></span>

4.  <span data-ttu-id="c5615-109">创建一个筛选器，其中的 **Office Communications Server 用户**等于 **True**。</span><span class="sxs-lookup"><span data-stu-id="c5615-109">Create a filter where **Office Communications Server user** is equal to **True**.</span></span>

5.  <span data-ttu-id="c5615-110">单击 "**查找**" 以搜索旧版 Office 通信服务器 2007 R2 用户。</span><span class="sxs-lookup"><span data-stu-id="c5615-110">Click **Find** to search for legacy Office Communications Server 2007 R2 users.</span></span>

6.  <span data-ttu-id="c5615-111">选择要移至 Lync Server 2013 池的两个用户。</span><span class="sxs-lookup"><span data-stu-id="c5615-111">Select two users that you want to move to the Lync Server 2013 pool.</span></span> <span data-ttu-id="c5615-112">在本例中，我们将移动用户 Chen Yang 和 Claus Hansen。</span><span class="sxs-lookup"><span data-stu-id="c5615-112">In this example, we will move users Chen Yang and Claus Hansen.</span></span>
    
    <span data-ttu-id="c5615-113">![通过搜索 OCS 用户显示的用户列表](images/JJ688143.76beb4fa-72e0-41ef-b96e-3553e96645c0(OCS.15).jpg "通过搜索 OCS 用户显示的用户列表")</span><span class="sxs-lookup"><span data-stu-id="c5615-113">![User list displayed from searching for OCS users](images/JJ688143.76beb4fa-72e0-41ef-b96e-3553e96645c0(OCS.15).jpg "User list displayed from searching for OCS users")</span></span>  

7.  <span data-ttu-id="c5615-114">在“操作”\*\*\*\* 菜单中，选择“将所选用户移动到池”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c5615-114">From the **Action** menu, select **Move selected users to pool**.</span></span>

8.  <span data-ttu-id="c5615-115">从下拉列表中，选择 "Lync Server 2013" 池。</span><span class="sxs-lookup"><span data-stu-id="c5615-115">From the drop-down list, select the Lync Server 2013 pool.</span></span>

9.  <span data-ttu-id="c5615-116">单击“操作”\*\*\*\*，然后单击“将所选用户移动到池”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c5615-116">Click **Action** and then click **Move selected users to pool**.</span></span> <span data-ttu-id="c5615-117">单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="c5615-117">Click OK.</span></span>
    
    <span data-ttu-id="c5615-118">!["移动用户，目标注册器池" 对话框](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png ""移动用户，目标注册器池" 对话框")</span><span class="sxs-lookup"><span data-stu-id="c5615-118">![Move Users, destination registrar pool dialog box](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Move Users, destination registrar pool dialog box")</span></span>  

10. <span data-ttu-id="c5615-119">确认用户的 "**注册器池**" 列现在包含 Lync Server 2013 池，这表明已成功移动用户。</span><span class="sxs-lookup"><span data-stu-id="c5615-119">Verify that the **Registrar pool** column for the users now contains the Lync Server 2013 pool, which indicates that the users have been successfully moved.</span></span>

</div>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="c5615-120">使用 Lync Server 2013 命令行管理程序移动多个用户</span><span class="sxs-lookup"><span data-stu-id="c5615-120">To move multiple users by using the Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="c5615-121">打开 Lync Server 2013 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="c5615-121">Open the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="c5615-122">在命令行中，键入以下内容，并**User1**将 User1**和用户**2 替换为要移动的特定用户名，并将**池 \_ FQDN**替换为目标池的名称。</span><span class="sxs-lookup"><span data-stu-id="c5615-122">At the command line, type the following and replace **User1** and **User2** with specific user names you want to move and replace **pool\_FQDN** with the name of the destination pool.</span></span> <span data-ttu-id="c5615-123">在本例中，我们将移动用户 Hao Chen 和 Katie Jordan。</span><span class="sxs-lookup"><span data-stu-id="c5615-123">In this example we will move users Hao Chen and Katie Jordan.</span></span>
    
        Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsLegacyUser -Target "pool_FQDN"
    
    <span data-ttu-id="c5615-124">![移动旧版用户的示例 cmdlet](images/JJ688143.57cfc28e-3df5-459f-83ef-8b0edf182a25(OCS.15).jpg "移动旧版用户的示例 cmdlet")</span><span class="sxs-lookup"><span data-stu-id="c5615-124">![Example cmdlet to move a legacy user](images/JJ688143.57cfc28e-3df5-459f-83ef-8b0edf182a25(OCS.15).jpg "Example cmdlet to move a legacy user")</span></span>  

3.  <span data-ttu-id="c5615-125">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="c5615-125">At the command line, type the following</span></span>
    
        Get-CsUser -Identity "User1"

4.  <span data-ttu-id="c5615-126">**注册器池**标识现在应指向您在上一步中指定为**池 \_ FQDN**的池。</span><span class="sxs-lookup"><span data-stu-id="c5615-126">The **Registrar Pool** identity should now point to the pool you specified as **pool\_FQDN** in the previous step.</span></span> <span data-ttu-id="c5615-127">存在该标识即可确认已成功移动用户。</span><span class="sxs-lookup"><span data-stu-id="c5615-127">The presence of this identity confirms that the user has been successfully moved.</span></span> <span data-ttu-id="c5615-128">重复此步骤以确认 **User2** 已移动。</span><span class="sxs-lookup"><span data-stu-id="c5615-128">Repeat step to verify **User2** has been moved.</span></span>
    
    <span data-ttu-id="c5615-129">![PowerShell UsUser cmdlet 的输出](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "PowerShell UsUser cmdlet 的输出")</span><span class="sxs-lookup"><span data-stu-id="c5615-129">![Output of PowerShell Get-UsUser -Identity cmdlet](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "Output of PowerShell Get-UsUser -Identity  cmdlet")</span></span>  

</div>

<div>

## <a name="to-move-all-users-at-the-same-time-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="c5615-130">使用 Lync Server 2013 命令行管理程序同时移动所有用户</span><span class="sxs-lookup"><span data-stu-id="c5615-130">To move all users at the same time by using the Lync Server 2013 Management Shell</span></span>

<span data-ttu-id="c5615-131">在此示例中，所有用户都已返回到 Office 通信服务器 2007 R2 池（pool01.contoso.net）。</span><span class="sxs-lookup"><span data-stu-id="c5615-131">In this example, all users have been returned to the Office Communications Server 2007 R2 pool (pool01.contoso.net).</span></span> <span data-ttu-id="c5615-132">使用 Lync Server 2013 命令行管理程序，我们将同时将所有用户移动到 Lync Server 2013 池（pool02.contoso.net）。</span><span class="sxs-lookup"><span data-stu-id="c5615-132">Using the Lync Server 2013 Management Shell, we will move all users at the same time to the Lync Server 2013 pool (pool02.contoso.net).</span></span>

1.  <span data-ttu-id="c5615-133">打开**Lync Server 2013 命令行管理**程序。</span><span class="sxs-lookup"><span data-stu-id="c5615-133">Open the **Lync Server 2013 Management Shell**.</span></span>

2.  <span data-ttu-id="c5615-134">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="c5615-134">At the command line, type the following:</span></span>
    
        Get-CsUser -OnOfficeCommunicationServer | Move-CsLegacyUser -Target "pool_FQDN"
    
    <span data-ttu-id="c5615-135">![移动池中的所有旧版用户的示例 cmdlet](images/JJ688143.e6a2d578-296e-476c-bd45-d757917ea853(OCS.15).jpg "移动池中的所有旧版用户的示例 cmdlet")</span><span class="sxs-lookup"><span data-stu-id="c5615-135">![Example cmdlet to move all legacy users in a pool](images/JJ688143.e6a2d578-296e-476c-bd45-d757917ea853(OCS.15).jpg "Example cmdlet to move all legacy users in a pool")</span></span>  

3.  <span data-ttu-id="c5615-136">接下来，为试点用户之一运行 **Get-CsUser**。</span><span class="sxs-lookup"><span data-stu-id="c5615-136">Next, run **Get-CsUser** for one of the pilot users.</span></span>
    
        Get-CsUser -Identity "Hao Chen"

4.  <span data-ttu-id="c5615-137">每个用户的**注册器池**标识现在指向您 \_ 在上一步中指定为 "池 FQDN" 的池。</span><span class="sxs-lookup"><span data-stu-id="c5615-137">The **Registrar Pool** identity for each user now points to the pool you specified as “pool\_FQDN” in the previous step.</span></span> <span data-ttu-id="c5615-138">存在该标识即可确认已成功移动用户。</span><span class="sxs-lookup"><span data-stu-id="c5615-138">The presence of this identity confirms that the user has been successfully moved.</span></span>

5.  <span data-ttu-id="c5615-139">此外，我们还可以查看 Lync Server 2013 控制面板中的用户列表，并验证注册器池值是否现在指向 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="c5615-139">Additionally, we can view the list of users in the Lync Server 2013 Control Panel and verify that the Registrar Pool value now points to the Lync Server 2013 pool.</span></span>
    
    <span data-ttu-id="c5615-140">![Lync Server 2013 控制面板用户列表](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Lync Server 2013 控制面板用户列表")</span><span class="sxs-lookup"><span data-stu-id="c5615-140">![Lync Server 2013 Control Panel user list](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Lync Server 2013 Control Panel user list")</span></span>  

</div>

</div>

<span> </span>

</div>

</div>

</div>

