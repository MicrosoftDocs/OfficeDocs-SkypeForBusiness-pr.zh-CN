---
title: Lync Server 2013：分配每用户持久聊天策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user Persistent Chat policy
ms:assetid: e22168f2-fde1-4f0a-b194-1fc881436822
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721908(v=OCS.15)
ms:contentKeyID: 49733842
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e06d6c7403bd348b44c6ab36216ed7ee9a1c6d02
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134408"
---
# <a name="assign-a-per-user-persistent-chat-policy-in-lync-server-2013"></a><span data-ttu-id="5b0f0-102">在 Lync Server 2013 中分配每用户持久聊天策略</span><span class="sxs-lookup"><span data-stu-id="5b0f0-102">Assign a per-user Persistent Chat policy in Lync Server 2013</span></span>

 


<span data-ttu-id="5b0f0-103">您可以使用 Lync Server 2013 控制面板或 Lync Server 2013 命令行管理程序分配每用户持久聊天策略。</span><span class="sxs-lookup"><span data-stu-id="5b0f0-103">You can assign a per-user persistent chat policy with either Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="5b0f0-104">有关为持久聊天服务器创建用户策略的详细信息，请参阅[在 Lync Server 2013 中为持久聊天创建用户策略](lync-server-2013-create-a-user-policy-for-persistent-chat.md)。</span><span class="sxs-lookup"><span data-stu-id="5b0f0-104">For details on creating user policies for Persistent Chat Server, see [Create a user policy for Persistent Chat in Lync Server 2013](lync-server-2013-create-a-user-policy-for-persistent-chat.md).</span></span>

## <a name="to-assign-a-per-user-persistent-chat-policy-with-lync-server-control-panel"></a><span data-ttu-id="5b0f0-105">使用 Lync Server 控制面板分配每用户持久聊天策略</span><span class="sxs-lookup"><span data-stu-id="5b0f0-105">To assign a per-user persistent chat policy with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="5b0f0-106">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="5b0f0-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5b0f0-107">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="5b0f0-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="5b0f0-108">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="5b0f0-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="5b0f0-109">在左侧导航栏中，单击“用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5b0f0-109">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="5b0f0-110">使用下列方法之一查找用户：</span><span class="sxs-lookup"><span data-stu-id="5b0f0-110">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="5b0f0-111">在“搜索用户”\*\*\*\* 框中，键入用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“查找”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5b0f0-111">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="5b0f0-112">如果具有保存的查询，请单击“打开查询”\*\*\*\* 图标，使用“打开”\*\*\*\* 对话框来检索该查询（.usf 文件），然后单击“查找”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5b0f0-112">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="5b0f0-113">（可选）指定附加搜索条件以缩小结果的范围：</span><span class="sxs-lookup"><span data-stu-id="5b0f0-113">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="5b0f0-114">单击“添加筛选器”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5b0f0-114">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="5b0f0-115">通过键入用户属性，或单击下拉列表中的箭头选择属性来输入用户属性。</span><span class="sxs-lookup"><span data-stu-id="5b0f0-115">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="5b0f0-116">在“等于”\*\*\*\* 下拉列表中，单击运算符（例如“等于”\*\*\*\* 或“不等于”\*\*\*\*）。</span><span class="sxs-lookup"><span data-stu-id="5b0f0-116">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="5b0f0-117">根据所选的用户属性，通过键入条件或单击下拉列表中的箭头输入用于筛选搜索结果的条件。</span><span class="sxs-lookup"><span data-stu-id="5b0f0-117">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="5b0f0-118">要向查询中添加附加搜索子句，请单击“添加筛选器”<STRONG></STRONG>。</span><span class="sxs-lookup"><span data-stu-id="5b0f0-118">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="5b0f0-119">单击“查找”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5b0f0-119">Click **Find**.</span></span>

6.  <span data-ttu-id="5b0f0-120">在搜索结果中单击某个用户，再单击“操作”\*\*\*\*，然后单击“分配策略”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5b0f0-120">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="5b0f0-121">如果要将相同的每用户持久聊天策略应用于多个用户，请在搜索结果中选择 "多个用户"，然后单击 "<STRONG>操作</STRONG>"，然后单击 "<STRONG>分配策略</STRONG>"。</span><span class="sxs-lookup"><span data-stu-id="5b0f0-121">If you want the same per-user persistent Chat policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="5b0f0-122">在 "**分配策略**" 中的 "**持久聊天策略**" 下，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="5b0f0-122">In **Assign Policies**, under **Persistent Chat policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="5b0f0-123">由于有多个策略可以使用 "<STRONG>分配策略</STRONG>" 对话框进行配置，因此默认情况下会为对话框中的每个策略选择 " <STRONG> &lt;保持为&gt; </STRONG> "。</span><span class="sxs-lookup"><span data-stu-id="5b0f0-123">Because there are multiple policies that you can configure by using the <STRONG>Assign Policies</STRONG> dialog box, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="5b0f0-124">如果不对此设置进行任何更改，则将继续使用先前分配给用户的策略。</span><span class="sxs-lookup"><span data-stu-id="5b0f0-124">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="5b0f0-125">选择\*\* \<"\>自动\*\*" 以允许 Lync Server 2013 自动选择全局级别策略或网站级别策略（如果已定义）。</span><span class="sxs-lookup"><span data-stu-id="5b0f0-125">Select **\<Automatic\>** to allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
      - <span data-ttu-id="5b0f0-126">单击先前在**持久聊天策略**页上定义的每用户持久聊天策略的名称。</span><span class="sxs-lookup"><span data-stu-id="5b0f0-126">Click the name of a per-user Persistent Chat policy you previously defined on the **Persistent Chat Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="5b0f0-127">为帮助您确定要分配的策略，请在单击策略名称后单击“查看”<STRONG></STRONG>以查看策略中定义的用户权限。</span><span class="sxs-lookup"><span data-stu-id="5b0f0-127">To help you decide the policy you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="5b0f0-128">完成后，单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5b0f0-128">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-persistent-chat-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="5b0f0-129">使用 Windows PowerShell Cmdlet 分配每用户持久聊天策略</span><span class="sxs-lookup"><span data-stu-id="5b0f0-129">Assigning a Per-User Persistent Chat Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="5b0f0-130">您还可以使用**CsPersistentChatPolicy** cmdlet 分配每用户持久聊天策略。</span><span class="sxs-lookup"><span data-stu-id="5b0f0-130">You can also assign per-user persistent chat policies by using the **Grant-CsPersistentChatPolicy** cmdlet.</span></span> <span data-ttu-id="5b0f0-131">您可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="5b0f0-131">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="5b0f0-132">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。</span><span class="sxs-lookup"><span data-stu-id="5b0f0-132">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-persistent-chat-policy-to-a-single-user"></a><span data-ttu-id="5b0f0-133">向单个用户分配每用户持久聊天策略</span><span class="sxs-lookup"><span data-stu-id="5b0f0-133">To assign a per-user persistent chat policy to a single user</span></span>

  - <span data-ttu-id="5b0f0-134">以下命令将每个用户的持久聊天策略 RedmondPersistentChatPolicy 分配给用户 Ken Myer。</span><span class="sxs-lookup"><span data-stu-id="5b0f0-134">The following command assigns the per-user Persistent Chat policy RedmondPersistentChatPolicy to the user Ken Myer.</span></span>
    
        Grant-CsPersistentChatPolicy -Identity "Ken Myer" -PolicyName "RedmondPersistentChatPolicy"

## <a name="to-assign-a-per-user-persistent-chat-policy-to-multiple-users"></a><span data-ttu-id="5b0f0-135">为多个用户分配每用户持久聊天策略</span><span class="sxs-lookup"><span data-stu-id="5b0f0-135">To assign a per-user persistent chat policy to multiple users</span></span>

  - <span data-ttu-id="5b0f0-136">此命令将每用户持久聊天策略 RedmondUsersPersistentChatPolicy 分配给为 IT 部门工作的所有用户。</span><span class="sxs-lookup"><span data-stu-id="5b0f0-136">This command assigns the per-user Persistent Chat policy RedmondUsersPersistentChatPolicy to all the users who work for the IT department.</span></span> <span data-ttu-id="5b0f0-137">有关此命令中使用的 LdapFilter 参数的详细信息，请参阅[get-csuser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet 的文档。</span><span class="sxs-lookup"><span data-stu-id="5b0f0-137">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -LdapFilter "Department=IT" | Grant-CsPersistentChatPolicy -PolicyName "RedmondUsersPersistentChatPolicy"

## <a name="to-unassign-a-per-user-persistent-chat-policy"></a><span data-ttu-id="5b0f0-138">取消分配每用户持久聊天策略</span><span class="sxs-lookup"><span data-stu-id="5b0f0-138">To unassign a per-user persistent chat policy</span></span>

  - <span data-ttu-id="5b0f0-139">以下命令取消分配之前分配给 Ken Myer 的任何每用户持久聊天策略。</span><span class="sxs-lookup"><span data-stu-id="5b0f0-139">The following command unassigns any per-user Persistent Chat policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="5b0f0-140">取消分配每用户策略后，将使用全局策略或其本地站点策略（如果存在）自动管理 Ken Myer。</span><span class="sxs-lookup"><span data-stu-id="5b0f0-140">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="5b0f0-141">站点策略优先于全局策略。</span><span class="sxs-lookup"><span data-stu-id="5b0f0-141">A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsPersistentChatPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="5b0f0-142">有关详细信息，请参阅[CsPersistentChatPolicy](https://technet.microsoft.com/library/jj204907\(v=ocs.15\)) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="5b0f0-142">For more information, see the help topic for the [Grant-CsPersistentChatPolicy](https://technet.microsoft.com/library/jj204907\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="5b0f0-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5b0f0-143">See Also</span></span>


[<span data-ttu-id="5b0f0-144">在 Lync Server 2013 中为持久聊天创建用户策略</span><span class="sxs-lookup"><span data-stu-id="5b0f0-144">Create a user policy for Persistent Chat in Lync Server 2013</span></span>](lync-server-2013-create-a-user-policy-for-persistent-chat.md)

