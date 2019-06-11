---
title: 'Lync Server 2013: 将用户移动到另一个池'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Move users to another pool
ms:assetid: e7b4968c-0e9d-4d56-b5f1-9edf0f7206f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182600(v=OCS.15)
ms:contentKeyID: 48185879
ms.date: 02/09/2018
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0fb716c0b551475a53cacf09be10ffdc039f5db8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826652"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-users-to-another-pool-in-lync-server-2013"></a><span data-ttu-id="c096f-102">在 Lync Server 2013 中将用户移动到另一个池中</span><span class="sxs-lookup"><span data-stu-id="c096f-102">Move users to another pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="c096f-103">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="c096f-103"></span></span>

<span data-ttu-id="c096f-104">_**主题上次修改时间:** 2018-02-09_</span><span class="sxs-lookup"><span data-stu-id="c096f-104">_**Topic Last Modified:** 2018-02-09_</span></span>

<span data-ttu-id="c096f-105">可以使用 Lync Server 控制面板将用户分配到特定的服务器或池。</span><span class="sxs-lookup"><span data-stu-id="c096f-105">You can use Lync Server Control Panel to assign users to a specific server or pool.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="c096f-106">将所有现有用户从运行 Lync Server 2010 或更早版本的源池中移动到复杂的 Active Directory 环境中的 Lync Server 2013 目标池可能会导致 Active Directory 复制速度较慢。</span><span class="sxs-lookup"><span data-stu-id="c096f-106">Moving all existing users from a source pool that is running Lync Server 2010 or earlier to a Lync Server 2013 destination pool in a complex Active Directory environment might result in slower Active Directory replication.</span></span> <span data-ttu-id="c096f-107">为避免这种情况, 您可以使用搜索筛选器从运行 Lync Server 2010 或更早版本的池中移动用户, 也可以使用 Lync Server Management Shell 将用户与 cmdlet 一起移动。</span><span class="sxs-lookup"><span data-stu-id="c096f-107">To avoid this, you can use search filters to move users from pools that are running Lync Server 2010 or earlier separately, or you can use Lync Server Management Shell to move users with cmdlets.</span></span> <span data-ttu-id="c096f-108">此外, 筛选器功能适用于 Lync Server 2013 用户。</span><span class="sxs-lookup"><span data-stu-id="c096f-108">Also, the filter functionality works with Lync Server 2013 users.</span></span>



</div>

<div>

## <a name="to-move-selected-users-to-a-different-server-or-pool"></a><span data-ttu-id="c096f-109">将所选用户移动到其他服务器或池</span><span class="sxs-lookup"><span data-stu-id="c096f-109">To move selected users to a different server or pool</span></span>

1.  <span data-ttu-id="c096f-110">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="c096f-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c096f-111">打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="c096f-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c096f-112">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="c096f-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c096f-113">在左导航栏中，单击“用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c096f-113">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="c096f-114">在 "**搜索用户**" 框中, 键入所需用户帐户的所有或第一部分的显示名称、"名字"、"姓氏"、安全帐户管理器 (SAM) 帐户名、SIP 地址或行统一资源标识符 (URI), 然后单击 "**查找"**.</span><span class="sxs-lookup"><span data-stu-id="c096f-114">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span>

5.  <span data-ttu-id="c096f-115">在表中, 选择列表中的特定用户或用户。</span><span class="sxs-lookup"><span data-stu-id="c096f-115">In the table, select a specific user or users in the list.</span></span>

6.  <span data-ttu-id="c096f-116">在 "**操作**" 菜单上, 单击 "**将所选用户移至池**"。</span><span class="sxs-lookup"><span data-stu-id="c096f-116">On the **Action** menu, click **Move selected users to pool**.</span></span>

7.  <span data-ttu-id="c096f-117">在 "**移动用户**" 中, 选择要将用户移动到 "**目标注册机构" 池中**的池。</span><span class="sxs-lookup"><span data-stu-id="c096f-117">In **Move Users**, select the pool that you want to move the users to in **Destination registrar pool**.</span></span>

8.  <span data-ttu-id="c096f-118">可选如果目标服务器或池不可用, 请选中 "**强制**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="c096f-118">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    <div>
    

    > [!Caution]  
    > <span data-ttu-id="c096f-119">如果您选择 "<STRONG>强制</STRONG>", 则用户帐户将被移动, 但相关联的用户数据 (如计划的会议和联系人) 不会移动。</span><span class="sxs-lookup"><span data-stu-id="c096f-119">If you select <STRONG>Force</STRONG>, the user account is moved, but associated user data such scheduled conferences and contacts is not moved.</span></span>

    
    </div>

</div>

<div>

## <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a><span data-ttu-id="c096f-120">将所有用户从一个服务器或池移动到另一个服务器或池</span><span class="sxs-lookup"><span data-stu-id="c096f-120">To move all users from one server or pool to a different server or pool</span></span>

1.  <span data-ttu-id="c096f-121">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="c096f-121">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c096f-122">打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="c096f-122">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c096f-123">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="c096f-123">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c096f-124">在左导航栏中，单击“用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c096f-124">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="c096f-125">在 "**操作**" 菜单上, 单击 "**将所有用户移至池**"。</span><span class="sxs-lookup"><span data-stu-id="c096f-125">On the **Action** menu, click **Move all users to pool**.</span></span>

5.  <span data-ttu-id="c096f-126">在 "**移动用户**" 中, 选择包含要在**源注册机构池中**移动的用户帐户的池。</span><span class="sxs-lookup"><span data-stu-id="c096f-126">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>

6.  <span data-ttu-id="c096f-127">在 "**目标注册机构" 池中**, 选择要将用户移动到的池。</span><span class="sxs-lookup"><span data-stu-id="c096f-127">In **Destination registrar pool**, select the pool that you want to move the users to.</span></span>

7.  <span data-ttu-id="c096f-128">可选如果目标服务器或池不可用, 请选中 "**强制**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="c096f-128">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    <div>
    

    > [!Caution]  
    > <span data-ttu-id="c096f-129">如果您选择 "<STRONG>强制</STRONG>", 则用户帐户将被移动, 但相关联的用户数据 (如计划的会议和联系人) 不会移动。</span><span class="sxs-lookup"><span data-stu-id="c096f-129">If you select <STRONG>Force</STRONG>, the user account is moved, but associated user data such scheduled conferences and contacts is not moved.</span></span>

    
    </div>

</div>

<div>

## <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a><span data-ttu-id="c096f-130">使用筛选器将用户从一个池移动到另一个池</span><span class="sxs-lookup"><span data-stu-id="c096f-130">To move users from one pool to a different pool by using a filter</span></span>

1.  <span data-ttu-id="c096f-131">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="c096f-131">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c096f-132">打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="c096f-132">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c096f-133">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="c096f-133">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c096f-134">在左导航栏中，单击“用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c096f-134">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="c096f-135">在 "**用户搜索**" 中, 单击 "**搜索**", 然后单击 "**添加筛选器**"。</span><span class="sxs-lookup"><span data-stu-id="c096f-135">In **User Search**, click **Search**, and then click **Add Filter**.</span></span>

5.  <span data-ttu-id="c096f-136">在搜索条件中, 选择 "**注册机构池**", 选择 "**等于**", 选择 "**当前池 FQDN**", 然后单击 "**查找**"。</span><span class="sxs-lookup"><span data-stu-id="c096f-136">In the Search criteria, select **Registrar Pool**, select **Equal to**, select **Current Pool FQDN**, and then click **Find**.</span></span>

6.  <span data-ttu-id="c096f-137">在 "**操作**" 菜单上, 单击 "**将所有用户移至池**"。</span><span class="sxs-lookup"><span data-stu-id="c096f-137">On the **Action** menu, click **Move all users to pool**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c096f-138">将筛选器应用于现有用户集时, 选项 "<STRONG>将所有用户移至池中</STRONG>" 将位于已筛选的用户子集的上下文中, 而不是<STRONG><EM>所有</EM></STRONG>可能的用户。</span><span class="sxs-lookup"><span data-stu-id="c096f-138">When a filter is applied to an existing set of users, the option <STRONG>Move all users to pool</STRONG> is in the context of the filtered subset of users, not <STRONG><EM>all</EM></STRONG> possible users.</span></span>

    
    </div>

7.  <span data-ttu-id="c096f-139">在 "**移动用户**" 中, 选择包含要在**源注册机构池中**移动的用户帐户的池。</span><span class="sxs-lookup"><span data-stu-id="c096f-139">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>

8.  <span data-ttu-id="c096f-140">在 "**目标注册机构" 池中**, 选择要将用户移动到的池。</span><span class="sxs-lookup"><span data-stu-id="c096f-140">In **Destination registrar pool**, select the pool where you want to move the users.</span></span>

9.  <span data-ttu-id="c096f-141">可选如果目标服务器或池不可用, 请选中 "**强制**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="c096f-141">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    <div>
    

    > [!Caution]  
    > <span data-ttu-id="c096f-142">如果您选择 "<STRONG>强制</STRONG>", 则用户帐户将被移动, 但相关联的用户数据 (如计划的会议和联系人) 不会移动。</span><span class="sxs-lookup"><span data-stu-id="c096f-142">If you select <STRONG>Force</STRONG>, the user account is moved, but associated user data such scheduled conferences and contacts is not moved.</span></span>

    
    </div>

</div>

<div>

## <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a><span data-ttu-id="c096f-143">使用 Windows PowerShell cmdlet 将用户从一个池移动到另一个池</span><span class="sxs-lookup"><span data-stu-id="c096f-143">To move users from one pool to another using Windows PowerShell cmdlets</span></span>

1.  <span data-ttu-id="c096f-144">根据你运行的 Windows PowerShell 命令 (本地或远程) 的运行方式, 你需要以正确的 Lync Server 2013 管理角色的成员身份登录, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="c096f-144">Depending on how you run Windows PowerShell commands (that is, locally or remotely), you need to log on as a member of the correct Lync Server 2013 administrative roles as follows:</span></span>
    
    1.  <span data-ttu-id="c096f-145">如果你在本地计算机上运行命令 (例如, 直接登录前端服务器), 请执行以下操作: 登录到安装了 Lync Server 命令行管理程序的计算机上作为 RTCUniversalServerAdmins 组的成员或必要的用户权限在[Lync Server 2013](lync-server-2013-delegate-setup-permissions.md)中的 "委派设置" 权限中介绍。</span><span class="sxs-lookup"><span data-stu-id="c096f-145">If you are running the commands on the local machine (for example, you log on directly to a Front End Server): Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>
    
    2.  <span data-ttu-id="c096f-146">如果您在另一台计算机上远程运行命令 (例如, 登录到计算机并在标准版前端服务器上远程运行命令): 从分配给 CsUserAdministrator 角色或 CsAdministrator 的用户帐户。角色, 请登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="c096f-146">If you are running the commands remotely on another computer (for example, you log on to your computer and run the commands remotely on a Standard Edition Front End Server): From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c096f-147">启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="c096f-147">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="c096f-148">若要移动单个用户, 请使用 Move-csuser cmdlet, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="c096f-148">To move single users, use the Move-CsUser cmdlet as follows:</span></span>
    
        Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    
    <span data-ttu-id="c096f-149">要移动的用户是用户 Pilar Ackerman, 用户将从其当前分配的主池移动到该池 pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="c096f-149">Where the user to move is the user Pilar Ackerman, and the user will be moved from their currently assigned home pool to the pool pool01.contoso.net</span></span>

4.  <span data-ttu-id="c096f-150">若要移动大量用户, 请将筛选器与**move-csuser** cmdlet 配合使用, 并将生成的用户集传递到**move-csuser**:</span><span class="sxs-lookup"><span data-stu-id="c096f-150">To move a large number of users, use filters with the **Get-CsUser** cmdlet and pass the resulting set of users to **Move-CsUser**:</span></span>
    
        Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    
    <span data-ttu-id="c096f-151">**Move-csuser**和**move-csuser**的合并命令可能会导致以下情况:</span><span class="sxs-lookup"><span data-stu-id="c096f-151">The combined commands of the **Get-CsUser** and **Move-CsUser** might result in this:</span></span>
    
        Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c096f-152">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c096f-152">See Also</span></span>


[<span data-ttu-id="c096f-153">在 Lync Server 2013 中修改用户帐户属性</span><span class="sxs-lookup"><span data-stu-id="c096f-153">Modifying user account properties in Lync Server 2013</span></span>](lync-server-2013-modifying-user-account-properties.md)  
  

<span data-ttu-id="c096f-154"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="c096f-154"></span></span></div>

