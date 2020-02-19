---
title: Lync Server 2013：分配每用户 PIN 策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user PIN policy
ms:assetid: d8211c64-0b63-4193-a074-673da7d14287
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182594(v=OCS.15)
ms:contentKeyID: 48185475
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 889fbc962654edbd7b6d13523fc5dc43dc426de2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134398"
---
# <a name="assign-a-per-user-pin-policy-in-lync-server-2013"></a><span data-ttu-id="4378e-102">在 Lync Server 2013 中分配每用户 PIN 策略</span><span class="sxs-lookup"><span data-stu-id="4378e-102">Assign a per-user PIN policy in Lync Server 2013</span></span>

 


<span data-ttu-id="4378e-103">电话拨入式会议个人识别码（PIN）策略是可在 Lync Server 2013 控制面板中配置的用户帐户的个人设置之一。</span><span class="sxs-lookup"><span data-stu-id="4378e-103">The dial-in conferencing personal identification number (PIN) policy is one of the individual settings of a user account that can be configured in the Lync Server 2013 Control Panel.</span></span>

<span data-ttu-id="4378e-p101">部署一个或多个每用户 PIN 策略是可选的。还可以只部署一个全局级别的 PIN 策略或站点级别的 PIN 策略。如果要部署每用户策略，则必须将其明确分配给用户、组或联系人对象。未分配特定的站点级别或每用户策略时，用户在电话拨入式会议中使用 PIN 的权限将自动默认为全局级别的 PIN 策略中定义的用户权限。</span><span class="sxs-lookup"><span data-stu-id="4378e-p101">Deploying one or more per-user PIN policies is optional. You can also deploy only a global-level PIN policy or site-level PIN policy. If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact object. User rights and permissions regarding the use of PINs for dial-in conferencing automatically default to those defined in the global-level PIN policy when no specific site-level or per-user policy is assigned.</span></span>

<span data-ttu-id="4378e-108">创建至少一个每用户 PIN 策略之后，请使用本主题中的过程分配策略，该策略指定您希望服务器对特定用户创建和使用的 PIN 施加的约束。</span><span class="sxs-lookup"><span data-stu-id="4378e-108">After creating at least one per-user PIN policy, use the procedures in this topic to assign the policy that specifies the constraints you want the server to impose on the PINs created by and used by a particular user.</span></span>

<span data-ttu-id="4378e-109">有关创建每用户电话拨入式会议 PIN 策略的详细信息，请参阅[在 Lync Server 2013 for a site or users 组中创建或修改电话拨入式会议 pin 设置](lync-server-2013-create-or-modify-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md)。</span><span class="sxs-lookup"><span data-stu-id="4378e-109">For details about creating per-user dial-in conferencing PIN policies, see [Create or modify dial-in conferencing PIN settings in Lync Server 2013 for a site or group of users](lync-server-2013-create-or-modify-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md).</span></span>

## <a name="to-assign-a-per-user-pin-policy"></a><span data-ttu-id="4378e-110">分配每用户 PIN 策略</span><span class="sxs-lookup"><span data-stu-id="4378e-110">To assign a per-user PIN policy</span></span>

1.  <span data-ttu-id="4378e-111">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="4378e-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4378e-112">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="4378e-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4378e-113">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="4378e-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4378e-114">在左侧导航栏中，单击“用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4378e-114">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="4378e-115">使用下列方法之一查找用户：</span><span class="sxs-lookup"><span data-stu-id="4378e-115">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="4378e-116">在“搜索用户”\*\*\*\* 框中，键入用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“查找”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4378e-116">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="4378e-117">如果具有保存的查询，请单击“打开查询”\*\*\*\* 图标，使用“打开”\*\*\*\* 对话框来检索该查询（.usf 文件），然后单击“查找”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4378e-117">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="4378e-118">（可选）指定附加搜索条件以缩小结果的范围：</span><span class="sxs-lookup"><span data-stu-id="4378e-118">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="4378e-119">单击“添加筛选器”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4378e-119">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="4378e-120">通过键入用户属性，或单击下拉列表中的箭头选择属性来输入用户属性。</span><span class="sxs-lookup"><span data-stu-id="4378e-120">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="4378e-121">在“等于”\*\*\*\* 下拉列表中，单击运算符（例如“等于”\*\*\*\* 或“不等于”\*\*\*\*）。</span><span class="sxs-lookup"><span data-stu-id="4378e-121">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="4378e-122">根据所选的用户属性，通过键入条件或单击下拉列表中的箭头输入用于筛选搜索结果的条件。</span><span class="sxs-lookup"><span data-stu-id="4378e-122">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="4378e-123">要向查询中添加附加搜索子句，请单击“添加筛选器”<STRONG></STRONG>。</span><span class="sxs-lookup"><span data-stu-id="4378e-123">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="4378e-124">单击“查找”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4378e-124">Click **Find**.</span></span>

6.  <span data-ttu-id="4378e-125">在搜索结果中单击某个用户，再单击“操作”\*\*\*\*，然后单击“分配策略”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4378e-125">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="4378e-126">如果您希望将相同的每用户 PIN 策略应用于多个用户，请在搜索结果中选择多个用户，单击“操作”<STRONG></STRONG>，然后单击“分配策略”<STRONG></STRONG>。</span><span class="sxs-lookup"><span data-stu-id="4378e-126">If you want the same per-user PIN policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="4378e-127">在“分配策略”\*\*\*\* 中的“PIN 策略”\*\*\*\* 下，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="4378e-127">In **Assign Policies**, under **PIN policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="4378e-128">由于有多个策略可以使用 "<STRONG>分配策略</STRONG>" 对话框进行配置，因此默认情况下会为对话框中的每个策略选择 " <STRONG> &lt;保持为&gt; </STRONG> "。</span><span class="sxs-lookup"><span data-stu-id="4378e-128">Because there are multiple policies that you can configure by using the <STRONG>Assign Policies</STRONG> dialog box, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="4378e-129">如果不对此设置进行任何更改，则将继续使用先前分配给用户的策略。</span><span class="sxs-lookup"><span data-stu-id="4378e-129">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="4378e-130">允许 Lync Server 2013 自动选择全局级别策略或网站级别策略（如果已定义）。</span><span class="sxs-lookup"><span data-stu-id="4378e-130">Allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
      - <span data-ttu-id="4378e-131">单击之前在“PIN 策略”\*\*\*\* 页中定义的每用户 PIN 策略的名称。</span><span class="sxs-lookup"><span data-stu-id="4378e-131">Click the name of a per-user PIN policy you previously defined on the **PIN Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="4378e-132">为帮助您确定要分配的策略，请在单击策略名称后单击“查看”<STRONG></STRONG>以查看策略中定义的用户权限。</span><span class="sxs-lookup"><span data-stu-id="4378e-132">To help you decide the policy you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="4378e-133">完成后，单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4378e-133">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-pin-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="4378e-134">使用 Windows PowerShell Cmdlet 分配每用户 PIN 策略</span><span class="sxs-lookup"><span data-stu-id="4378e-134">Assigning a Per-User PIN Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="4378e-135">您可以使用 Windows PowerShell 和**get-cspinpolicy** cmdlet 分配每用户 PIN 策略。</span><span class="sxs-lookup"><span data-stu-id="4378e-135">You can assign per-user PIN policies by using Windows PowerShell and the **Grant-CsPinPolicy** cmdlet.</span></span> <span data-ttu-id="4378e-136">您可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="4378e-136">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="4378e-137">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。</span><span class="sxs-lookup"><span data-stu-id="4378e-137">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-pin-policy-to-a-single-user"></a><span data-ttu-id="4378e-138">为单个用户分配每用户 PIN 策略</span><span class="sxs-lookup"><span data-stu-id="4378e-138">To assign a per-user PIN policy to a single user</span></span>

  - <span data-ttu-id="4378e-139">以下命令为用户 Ken Myer 分配每用户 PIN 策略 RedmondPinPolicy。</span><span class="sxs-lookup"><span data-stu-id="4378e-139">The following command assigns the per-user PIN policy RedmondPinPolicy to the user Ken Myer.</span></span>
    
        Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName "RedmondPinPolicy"

## <a name="to-assign-a-per-user-pin-policy-to-multiple-users"></a><span data-ttu-id="4378e-140">为多个用户分配每用户 PIN 策略</span><span class="sxs-lookup"><span data-stu-id="4378e-140">To assign a per-user PIN policy to multiple users</span></span>

  - <span data-ttu-id="4378e-141">以下命令为工作于 Redmond 市的所有用户分配每用户 PIN 策略 RedmondUsersPinPolicy。</span><span class="sxs-lookup"><span data-stu-id="4378e-141">The following command assigns the per-user PIN policy RedmondUsersPinPolicy to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="4378e-142">有关此命令中使用的 LdapFilter 参数的详细信息，请参阅[get-csuser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\))。</span><span class="sxs-lookup"><span data-stu-id="4378e-142">For details about the LdapFilter parameter used in this command, see [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)).</span></span>
    
        Get-CsUser -LdapFilter "l=Redmond" | Grant-CsPinPolicy -PolicyName "RedmondUsersPinPolicy"

## <a name="to-unassign-a-per-user-pin-policy"></a><span data-ttu-id="4378e-143">取消分配每用户 PIN 策略</span><span class="sxs-lookup"><span data-stu-id="4378e-143">To unassign a per-user PIN policy</span></span>

  - <span data-ttu-id="4378e-p106">以下命令取消分配之前分配给 Ken Myer 的任何每用户 PIN 策略。取消分配每用户策略后，将自动使用全局策略或本地站点策略（如果存在）管理 Ken Myer。站点策略优先于全局策略。</span><span class="sxs-lookup"><span data-stu-id="4378e-p106">The following command unassigns any per-user PIN policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="4378e-147">有关详细信息，请参阅[get-cspinpolicy](https://technet.microsoft.com/library/gg398871\(v=ocs.15\))。</span><span class="sxs-lookup"><span data-stu-id="4378e-147">For details, see [Grant-CsPinPolicy](https://technet.microsoft.com/library/gg398871\(v=ocs.15\)).</span></span>

## <a name="see-also"></a><span data-ttu-id="4378e-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4378e-148">See Also</span></span>


[<span data-ttu-id="4378e-149">在 Lync Server 2013 中创建新的 PIN 策略</span><span class="sxs-lookup"><span data-stu-id="4378e-149">Create a new PIN policy in Lync Server 2013</span></span>](lync-server-2013-create-a-new-pin-policy.md)  


[<span data-ttu-id="4378e-150">在 Lync Server 2013 中分配每用户策略</span><span class="sxs-lookup"><span data-stu-id="4378e-150">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)

