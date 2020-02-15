---
title: Lync Server 2013：分配每用户移动策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user mobility policy
ms:assetid: d8bf997f-4bc7-48d3-973b-323505f55e9d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721902(v=OCS.15)
ms:contentKeyID: 49733836
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1014bce74e0e7dcd789c9b2948c029f4b40ecb9a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030135"
---
# <a name="assign-a-per-user-mobility-policy-in-lync-server-2013"></a><span data-ttu-id="68c51-102">在 Lync Server 2013 中分配每用户移动策略</span><span class="sxs-lookup"><span data-stu-id="68c51-102">Assign a per-user mobility policy in Lync Server 2013</span></span>

 


<span data-ttu-id="68c51-103">移动策略是您可以在 Lync Server 控制面板或 Lync Server 命令行管理程序中配置的用户帐户的个人设置之一。</span><span class="sxs-lookup"><span data-stu-id="68c51-103">The mobility policy is one of the individual settings of a user account that you can configure in Lync Server Control Panel or Lync Server Management Shell.</span></span>

## <a name="to-assign-a-per-user-mobility-policy-with-lync-server-control-panel"></a><span data-ttu-id="68c51-104">使用 Lync Server 控制面板分配每用户移动策略</span><span class="sxs-lookup"><span data-stu-id="68c51-104">To assign a per-user mobility policy with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="68c51-105">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="68c51-105">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="68c51-106">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="68c51-106">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="68c51-107">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="68c51-107">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="68c51-108">在左侧导航栏中，单击“用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="68c51-108">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="68c51-109">使用下列方法之一查找用户：</span><span class="sxs-lookup"><span data-stu-id="68c51-109">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="68c51-110">在“搜索用户”\*\*\*\* 框中，键入用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“查找”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="68c51-110">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="68c51-111">如果具有保存的查询，请单击“打开查询”\*\*\*\* 图标，使用“打开”\*\*\*\* 对话框来检索该查询（.usf 文件），然后单击“查找”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="68c51-111">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="68c51-112">（可选）指定附加搜索条件以缩小结果的范围：</span><span class="sxs-lookup"><span data-stu-id="68c51-112">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="68c51-113">单击“添加筛选器”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="68c51-113">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="68c51-114">通过键入用户属性，或单击下拉列表中的箭头选择属性来输入用户属性。</span><span class="sxs-lookup"><span data-stu-id="68c51-114">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="68c51-115">在“等于”\*\*\*\* 下拉列表中，单击运算符（例如“等于”\*\*\*\* 或“不等于”\*\*\*\*）。</span><span class="sxs-lookup"><span data-stu-id="68c51-115">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="68c51-116">根据所选的用户属性，通过键入条件或单击下拉列表中的箭头输入用于筛选搜索结果的条件。</span><span class="sxs-lookup"><span data-stu-id="68c51-116">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="68c51-117">要向查询中添加附加搜索子句，请单击“添加筛选器”<STRONG></STRONG>。</span><span class="sxs-lookup"><span data-stu-id="68c51-117">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="68c51-118">单击“查找”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="68c51-118">Click **Find**.</span></span>

6.  <span data-ttu-id="68c51-119">在搜索结果中单击某个用户，再单击“操作”\*\*\*\*，然后单击“分配策略”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="68c51-119">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="68c51-120">如果要将相同的每用户移动策略应用于多个用户，请在搜索结果中选择 "多个用户"，然后单击 "<STRONG>操作</STRONG>"，然后单击 "<STRONG>分配策略</STRONG>"。</span><span class="sxs-lookup"><span data-stu-id="68c51-120">If you want the same per-user mobility policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="68c51-121">在 "**分配策略**" 中的 "**移动策略**" 下，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="68c51-121">In **Assign Policies**, under **Mobility policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="68c51-122">由于可以在 "<STRONG>分配策略</STRONG>" 中配置多个策略，因此默认情况下将为对话框中的每个策略选择 " <STRONG> &lt;保持为&gt; </STRONG> "。</span><span class="sxs-lookup"><span data-stu-id="68c51-122">Because there are multiple policies that you can configure in <STRONG>Assign Policies</STRONG>, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="68c51-123">如果不对此设置进行任何更改，则将继续使用先前分配给用户的策略。</span><span class="sxs-lookup"><span data-stu-id="68c51-123">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="68c51-124">选择\*\* \<"\>自动\*\*" 以允许 Lync Server 2013 自动选择全局级别策略或网站级别策略（如果已定义）。</span><span class="sxs-lookup"><span data-stu-id="68c51-124">Select **\<Automatic\>** to allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
      - <span data-ttu-id="68c51-125">单击先前在**移动策略**页上定义的每用户移动性策略的名称。</span><span class="sxs-lookup"><span data-stu-id="68c51-125">Click the name of a per-user mobility policy you previously defined on the **Mobility Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="68c51-126">为帮助您确定要分配的策略，请在单击策略名称后单击“查看”<STRONG></STRONG>以查看策略中定义的用户权限。</span><span class="sxs-lookup"><span data-stu-id="68c51-126">To help you decide the policy you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="68c51-127">完成后，单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="68c51-127">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-mobility-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="68c51-128">使用 Windows PowerShell Cmdlet 分配每用户移动策略</span><span class="sxs-lookup"><span data-stu-id="68c51-128">Assigning a Per-User Mobility Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="68c51-129">您可以使用 Windows PowerShell 和**set-csmobilitypolicy** cmdlet 分配每用户移动性策略。</span><span class="sxs-lookup"><span data-stu-id="68c51-129">You can assign per-user mobility policies by using Windows PowerShell and the **Grant-CsMobilityPolicy** cmdlet.</span></span> <span data-ttu-id="68c51-130">您可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="68c51-130">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="68c51-131">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。</span><span class="sxs-lookup"><span data-stu-id="68c51-131">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-mobility-policy-to-a-single-user"></a><span data-ttu-id="68c51-132">向单个用户分配每用户移动策略</span><span class="sxs-lookup"><span data-stu-id="68c51-132">To assign a per-user mobility policy to a single user</span></span>

  - <span data-ttu-id="68c51-133">以下命令将每用户移动策略 RedmondMobilityPolicy 分配给用户 Ken Myer。</span><span class="sxs-lookup"><span data-stu-id="68c51-133">The following command assigns the per-user mobility policy RedmondMobilityPolicy to the user Ken Myer.</span></span>
    
        Grant-CsMobilityPolicy -Identity "Ken Myer" -PolicyName "RedmondMobilityPolicy"

## <a name="to-assign-a-per-user-mobility-policy-to-multiple-users"></a><span data-ttu-id="68c51-134">为多个用户分配每用户移动策略</span><span class="sxs-lookup"><span data-stu-id="68c51-134">To assign a per-user mobility policy to multiple users</span></span>

  - <span data-ttu-id="68c51-135">以下命令将每用户移动策略 RedmondMobilityPolicy 分配给当前分配了 policy NorthAmericaMobilityPolicy 的所有用户。</span><span class="sxs-lookup"><span data-stu-id="68c51-135">The following command assigns the per-user mobility policy RedmondMobilityPolicy to all the users who are currently assigned the policy NorthAmericaMobilityPolicy.</span></span> <span data-ttu-id="68c51-136">有关此命令中使用的 Filter 参数的详细信息，请参阅[get-csuser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\))。</span><span class="sxs-lookup"><span data-stu-id="68c51-136">For details about the Filter parameter used in this command, see [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)).</span></span>
    
        Get-CsUser -Filter {MobilityPolicy -eq "NorthAmericaMobilityPolicy"} | Grant-CsMobilityPolicy -PolicyName "RedmondMobilityPolicy"

## <a name="to-unassign-a-per-user-mobility-policy"></a><span data-ttu-id="68c51-137">取消分配每用户移动策略</span><span class="sxs-lookup"><span data-stu-id="68c51-137">To unassign a per-user mobility policy</span></span>

  - <span data-ttu-id="68c51-138">以下命令取消分配之前分配给 Ken Myer 的任何每用户移动性策略。</span><span class="sxs-lookup"><span data-stu-id="68c51-138">The following command unassigns any per-user mobility policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="68c51-139">取消分配每用户策略后，将使用全局策略或其本地站点策略（如果存在）自动管理 Ken Myer。</span><span class="sxs-lookup"><span data-stu-id="68c51-139">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="68c51-140">站点策略优先于全局策略。</span><span class="sxs-lookup"><span data-stu-id="68c51-140">A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsMobilityPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="68c51-141">有关详细信息，请参阅[set-csmobilitypolicy](https://technet.microsoft.com/library/hh690038\(v=ocs.15\))。</span><span class="sxs-lookup"><span data-stu-id="68c51-141">For details, see [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/hh690038\(v=ocs.15\)).</span></span>

## <a name="see-also"></a><span data-ttu-id="68c51-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="68c51-142">See Also</span></span>


[<span data-ttu-id="68c51-143">在 Lync Server 2013 中配置移动策略</span><span class="sxs-lookup"><span data-stu-id="68c51-143">Configuring mobility policy in Lync Server 2013</span></span>](lync-server-2013-configuring-mobility-policy.md)

