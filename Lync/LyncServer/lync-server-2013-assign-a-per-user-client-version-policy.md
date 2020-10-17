---
title: Lync Server 2013：分配每用户客户端版本策略
description: Lync Server 2013：分配每用户客户端版本策略。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user client version policy
ms:assetid: f7e8ba2f-62dc-4e7d-8b63-682986f10240
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182607(v=OCS.15)
ms:contentKeyID: 48185868
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ec2fcbf9c005806a97dfbdceb22095fe0ff8f33
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559974"
---
# <a name="assign-a-per-user-client-version-policy-in-lync-server-2013"></a><span data-ttu-id="1a8d0-103">在 Lync Server 2013 中分配每用户客户端版本策略</span><span class="sxs-lookup"><span data-stu-id="1a8d0-103">Assign a per-user client version policy in Lync Server 2013</span></span>

 


<span data-ttu-id="1a8d0-104">客户端版本策略是您可以在 Lync Server 控制面板中配置的用户帐户的个人设置之一。</span><span class="sxs-lookup"><span data-stu-id="1a8d0-104">The client version policy is one of the individual settings of a user account that you can configure in the Lync Server Control Panel.</span></span>

<span data-ttu-id="1a8d0-105">部署一个或多个每用户客户端版本策略是可选的。</span><span class="sxs-lookup"><span data-stu-id="1a8d0-105">Deploying one or more per-user client version policies is optional.</span></span> <span data-ttu-id="1a8d0-106">还可以只部署一个全局级别的客户端版本策略，或者站点级别或池级别的客户端版本策略。</span><span class="sxs-lookup"><span data-stu-id="1a8d0-106">You can also deploy only a global-level client version policy, or site-level or pool-level client version policies.</span></span> <span data-ttu-id="1a8d0-107">如果要部署每用户策略，则必须将其明确分配给用户、组或联系人对象。</span><span class="sxs-lookup"><span data-stu-id="1a8d0-107">If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact object.</span></span> <span data-ttu-id="1a8d0-108">如果未分配特定的网站级别、池级别或每用户策略，则允许向 Lync Server 2013 注册的默认客户端是在全局级别客户端版本策略中定义的客户端。</span><span class="sxs-lookup"><span data-stu-id="1a8d0-108">When no specific site-level, pool-level, or per-user policy is assigned, the default clients that are allowed to register with Lync Server 2013 are those defined in the global-level client version policy.</span></span>

<span data-ttu-id="1a8d0-109">创建至少一个每用户客户端版本策略后，请使用本主题中的过程来分配指定您希望允许在 Lync Server 中注册的客户端版本的策略。</span><span class="sxs-lookup"><span data-stu-id="1a8d0-109">After creating at least one per-user client version policy, use the procedures in this topic to assign the policy that specifies the client versions that you want to allow to register with Lync Server.</span></span>

<span data-ttu-id="1a8d0-110">有关创建每用户客户端版本策略的详细信息，请参阅 [指定可用于登录 Lync Server 2013 的客户端应用程序](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="1a8d0-110">For details about creating per-user client version policies, see [Specifying the client applications that can be used to log on to Lync Server 2013](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md).</span></span>

## <a name="to-assign-a-per-user-client-version-policy"></a><span data-ttu-id="1a8d0-111">分配每用户客户端版本策略</span><span class="sxs-lookup"><span data-stu-id="1a8d0-111">To assign a per-user client version policy</span></span>

1.  <span data-ttu-id="1a8d0-112">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="1a8d0-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1a8d0-113">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="1a8d0-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1a8d0-114">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="1a8d0-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1a8d0-115">在左侧导航栏中，单击“用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1a8d0-115">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="1a8d0-116">使用下列方法之一查找用户：</span><span class="sxs-lookup"><span data-stu-id="1a8d0-116">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="1a8d0-117">在“搜索用户”\*\*\*\* 框中，键入用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“查找”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1a8d0-117">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="1a8d0-118">如果具有保存的查询，请单击“打开查询”\*\*\*\* 图标，使用“打开”\*\*\*\* 对话框来检索该查询（.usf 文件），然后单击“查找”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1a8d0-118">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="1a8d0-119">（可选）指定附加搜索条件以缩小结果的范围：</span><span class="sxs-lookup"><span data-stu-id="1a8d0-119">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="1a8d0-120">单击“添加筛选器”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1a8d0-120">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="1a8d0-121">通过键入用户属性，或单击下拉列表中的箭头选择属性来输入用户属性。</span><span class="sxs-lookup"><span data-stu-id="1a8d0-121">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="1a8d0-122">在“等于”\*\*\*\* 下拉列表中，单击运算符（例如“等于”\*\*\*\* 或“不等于”\*\*\*\*）。</span><span class="sxs-lookup"><span data-stu-id="1a8d0-122">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="1a8d0-123">根据所选的用户属性，通过键入条件或单击下拉列表中的箭头输入用于筛选搜索结果的条件。</span><span class="sxs-lookup"><span data-stu-id="1a8d0-123">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="1a8d0-124">要向查询中添加附加搜索子句，请单击“添加筛选器”<STRONG></STRONG>。</span><span class="sxs-lookup"><span data-stu-id="1a8d0-124">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="1a8d0-125">单击“查找”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1a8d0-125">Click **Find**.</span></span>

6.  <span data-ttu-id="1a8d0-126">在搜索结果中单击某个用户，再单击“操作”\*\*\*\*，然后单击“分配策略”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1a8d0-126">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="1a8d0-127">如果您希望将相同的每用户客户端版本策略应用于多个用户，请在搜索结果中选择多个用户，单击“操作”<STRONG></STRONG>，然后单击“分配策略”<STRONG></STRONG>。</span><span class="sxs-lookup"><span data-stu-id="1a8d0-127">If you want the same per-user client version policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="1a8d0-128">在“分配策略”\*\*\*\* 中的“客户端版本策略”\*\*\*\* 下，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="1a8d0-128">In **Assign Policies**, under **Client version policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="1a8d0-129">由于有多个策略可以使用 "<STRONG>分配策略</STRONG>" 对话框进行配置，因此默认情况下会为对话框中的每个策略选择 " <STRONG> &lt; &gt; 保持为</STRONG>"。</span><span class="sxs-lookup"><span data-stu-id="1a8d0-129">Because there are multiple policies that you can configure by using the <STRONG>Assign Policies</STRONG> dialog box, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="1a8d0-130">如果不对此设置进行任何更改，则将继续使用先前分配给用户的策略。</span><span class="sxs-lookup"><span data-stu-id="1a8d0-130">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="1a8d0-131">允许 Lync Server 自动选择全局级别策略或站点级别策略或池级别策略（如果已定义）。</span><span class="sxs-lookup"><span data-stu-id="1a8d0-131">Allow Lync Server to automatically choose either the global-level policy or, if defined, the site-level policy or pool-level policy.</span></span>
    
      - <span data-ttu-id="1a8d0-132">单击之前在“客户端版本策略”\*\*\*\* 页中定义的每用户客户端版本策略的名称。</span><span class="sxs-lookup"><span data-stu-id="1a8d0-132">Click the name of a per-user client version policy you previously defined on the **Client Version Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="1a8d0-133">为帮助您确定要分配的策略，请在单击策略名称后单击“查看”<STRONG></STRONG>以查看策略中定义的用户权限。</span><span class="sxs-lookup"><span data-stu-id="1a8d0-133">To help you decide the policy you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="1a8d0-134">完成后，单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1a8d0-134">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-client-version-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="1a8d0-135">使用 Windows PowerShell Cmdlet 分配 Per-User 客户端版本策略</span><span class="sxs-lookup"><span data-stu-id="1a8d0-135">Assigning a Per-User Client Version Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="1a8d0-136">您可以使用 Grant-CsClientVersionPolicy cmdlet 分配每用户客户端版本策略。</span><span class="sxs-lookup"><span data-stu-id="1a8d0-136">You can assign per-user client version policies by using the Grant-CsClientVersionPolicy cmdlet.</span></span> <span data-ttu-id="1a8d0-137">您可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1a8d0-137">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="1a8d0-138">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上的 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="1a8d0-138">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-client-version-policy-to-a-single-user"></a><span data-ttu-id="1a8d0-139">将每用户客户端版本策略分配到单个用户</span><span class="sxs-lookup"><span data-stu-id="1a8d0-139">To assign a per-user client version policy to a single user</span></span>

  - <span data-ttu-id="1a8d0-140">下列命令可用于将每用户版本策略 RedmondClientVersionPolicy 分配到用户 Ken Myer。</span><span class="sxs-lookup"><span data-stu-id="1a8d0-140">The following command assigns the per-user client version policy RedmondClientVersionPolicy to the user Ken Myer.</span></span>
    
        Grant-CsClientVersionPolicy -Identity "Ken Myer" -PolicyName "RedmondClientVersionPolicy"

## <a name="to-assign-a-per-user-client-version-policy-to-multiple-users"></a><span data-ttu-id="1a8d0-141">将每用户客户端版本策略分配到多个用户</span><span class="sxs-lookup"><span data-stu-id="1a8d0-141">To assign a per-user client version policy to multiple users</span></span>

  - <span data-ttu-id="1a8d0-142">此命令用于将每用户客户端版本策略 RedmondClientVersionPolicy 分配到当前分配了语音策略 RedmondVoicePolicy 的所有用户。</span><span class="sxs-lookup"><span data-stu-id="1a8d0-142">This command assigns the per-user client version policy RedmondClientVersionPolicy to all the users who are currently assigned the voice policy RedmondVoicePolicy.</span></span> <span data-ttu-id="1a8d0-143">有关此命令中使用的 Filter 参数的详细信息，请参阅 [get-csuser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet 的相关文档。</span><span class="sxs-lookup"><span data-stu-id="1a8d0-143">For more information on the Filter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -Filter {VoicePolicy -eq "RedmondVoicePolicy"} | Grant-CsClientVersionPolicy -PolicyName "RedmondClientVersionPolicy"

## <a name="to-unassign-a-per-user-client-version-policy"></a><span data-ttu-id="1a8d0-144">取消分配每用户客户端版本策略</span><span class="sxs-lookup"><span data-stu-id="1a8d0-144">To unassign a per-user client version policy</span></span>

  - <span data-ttu-id="1a8d0-p106">下列命令可用于取消先前分配到 Ken Myer 的任何每用户客户端版本策略。取消分配每用户策略后，将自动使用全局策略、其本地站点策略（如果存在该策略）或分配到其注册器的服务作用域策略自动管理 Ken Myer。服务作用域策略优先于任何站点策略，而站点策略优先于全局策略。</span><span class="sxs-lookup"><span data-stu-id="1a8d0-p106">The following command unassigns any per-user client version policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy, his local site policy (if one exists), or the service-scope policy assigned to his Registrar. A service scope policy takes precedence over any site policy, and a site policy takes precedence over the global policy.</span></span>
    
        Grant-CsClientVersionPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="1a8d0-148">有关详细信息，请参阅 [CsClientVersionPolicy](https://technet.microsoft.com/library/gg412903\(v=ocs.15\)) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="1a8d0-148">For more information, see the help topic for the [Grant-CsClientVersionPolicy](https://technet.microsoft.com/library/gg412903\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="1a8d0-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1a8d0-149">See Also</span></span>


[<span data-ttu-id="1a8d0-150">在 Lync Server 2013 中分配每用户策略</span><span class="sxs-lookup"><span data-stu-id="1a8d0-150">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)  
[<span data-ttu-id="1a8d0-151">在 Lync Server 2013 中管理设备、电话和客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="1a8d0-151">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)

