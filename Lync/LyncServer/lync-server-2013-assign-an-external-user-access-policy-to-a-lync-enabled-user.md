---
title: Lync Server 2013：将外部用户访问策略分配到启用 Lync 的用户
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign an external user access policy to a Lync enabled user
ms:assetid: 736fcaad-9f95-4896-b767-e199d86a00a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398551(v=OCS.15)
ms:contentKeyID: 48184483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec487f8aacdc26f910f30a0864ecead1fdb1a745
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837989"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-an-external-user-access-policy-to-a-lync-enabled-user-in-lync-server-2013"></a><span data-ttu-id="04db1-102">在 Lync Server 2013 中将外部用户访问策略分配到启用 Lync 的用户</span><span class="sxs-lookup"><span data-stu-id="04db1-102">Assign an external user access policy to a Lync enabled user in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="04db1-103">_**主题上次修改时间:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="04db1-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="04db1-104">如果已启用 Lync Server 的用户, 则可以通过向特定用户应用适当的策略来在 Lync Server 控制面板中配置 SIP 联盟、XMPP 联盟、远程用户访问和公共即时消息 (IM) 连接。</span><span class="sxs-lookup"><span data-stu-id="04db1-104">If a user has been enabled for Lync Server, you can configure SIP federation, XMPP federation, remote user access, and public instant messaging (IM) connectivity in the Lync Server Control Panel by applying the appropriate policies to specific users.</span></span> <span data-ttu-id="04db1-105">例如, 如果你创建了支持远程用户访问的策略, 则必须先将其应用于用户, 然后用户才能从远程位置连接到 Lync 服务器, 并从远程位置与内部用户进行协作。</span><span class="sxs-lookup"><span data-stu-id="04db1-105">For example, if you created a policy to support remote user access, you must apply it to the user before the user can connect to Lync Server from a remote location and collaborate with internal users from the remote location.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="04db1-106">若要支持外部用户访问, 必须启用对要支持的每种类型的外部用户访问的支持, 并配置相应的策略和其他选项以控制其使用。</span><span class="sxs-lookup"><span data-stu-id="04db1-106">To support external user access, you must enable support for each type of external user access you want to support, and configure the appropriate policies and other options to control its use.</span></span> <span data-ttu-id="04db1-107">有关详细信息, 请参阅在部署文档中<A href="lync-server-2013-configuring-support-for-external-user-access.md">配置 Lync server 2013 中的外部用户访问支持</A>或在操作文档中<A href="lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md">管理 lync server 2013 的联合访问和外部访问</A>。</span><span class="sxs-lookup"><span data-stu-id="04db1-107">For details, see <A href="lync-server-2013-configuring-support-for-external-user-access.md">Configuring support for external user access in Lync Server 2013</A> in the Deployment documentation or <A href="lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md">Managing federation and external access to Lync Server 2013</A> in the Operations documentation.</span></span>



</div>

<span data-ttu-id="04db1-108">使用本主题中的过程将以前创建的外部用户访问策略应用于一个或多个用户帐户。</span><span class="sxs-lookup"><span data-stu-id="04db1-108">Use the procedure in this topic to apply a previously created external user access policy to one or more user accounts.</span></span>

<div>

## <a name="to-apply-an-external-user-policy-to-a-user-account"></a><span data-ttu-id="04db1-109">将外部用户策略应用于用户帐户</span><span class="sxs-lookup"><span data-stu-id="04db1-109">To apply an external user policy to a user account</span></span>

1.  <span data-ttu-id="04db1-110">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="04db1-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="04db1-111">打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="04db1-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="04db1-112">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="04db1-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="04db1-113">在左侧导航栏中，单击“**用户**”，然后搜索要配置的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="04db1-113">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>

4.  <span data-ttu-id="04db1-114">在列出搜索结果的表中，单击相应的用户帐户，再单击“**编辑**”，然后单击“**显示详细信息**”。</span><span class="sxs-lookup"><span data-stu-id="04db1-114">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="04db1-115">在 "在**外部访问策略**中**编辑 Lync 服务器用户**" 下, 选择要应用的用户策略。</span><span class="sxs-lookup"><span data-stu-id="04db1-115">In **Edit Lync Server User** under **External access policy**, select the user policy that you want to apply.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="04db1-116">" <STRONG> &lt;自动&gt; </STRONG>设置" 将应用默认服务器或全局策略设置。</span><span class="sxs-lookup"><span data-stu-id="04db1-116">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server or global policy settings.</span></span>

    
    </div>

</div>

<div>

## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="04db1-117">使用 Windows PowerShell Cmdlet 分配每用户外部访问策略</span><span class="sxs-lookup"><span data-stu-id="04db1-117">Assigning Per-User External Access Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="04db1-118">可以使用 Windows PowerShell 和 CsExternalAccessPolicy cmdlet 分配每用户外部访问策略。</span><span class="sxs-lookup"><span data-stu-id="04db1-118">Per-user external access policies can be assigned by using Windows PowerShell and the Grant-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="04db1-119">此 cmdlet 既可以从 Lync Server 2013 管理外壳运行, 也可以从 Windows PowerShell 的远程会话运行。</span><span class="sxs-lookup"><span data-stu-id="04db1-119">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="04db1-120">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息, 请参阅 Lync Server Windows PowerShell 博客文章 "快速入门: 使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="04db1-120">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a><span data-ttu-id="04db1-121">将每用户外部访问策略分配给单个用户</span><span class="sxs-lookup"><span data-stu-id="04db1-121">To assign a per-user external access policy to a single user</span></span>

  - <span data-ttu-id="04db1-122">此命令将每用户外部访问策略 RedmondExternalAccessPolicy 分配给用户 Ken Myer。</span><span class="sxs-lookup"><span data-stu-id="04db1-122">This command assigns the per-user external access policy RedmondExternalAccessPolicy to the user Ken Myer.</span></span>
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a><span data-ttu-id="04db1-123">为多个用户分配每个用户的外部访问策略</span><span class="sxs-lookup"><span data-stu-id="04db1-123">To assign a per-user external access policy to multiple users</span></span>

  - <span data-ttu-id="04db1-124">此命令将每用户外部访问策略 USAExternalAccessPolicy 分配给在 Active Directory 中的美国组织单位中拥有帐户的所有用户。</span><span class="sxs-lookup"><span data-stu-id="04db1-124">This command assigns the per-user external access policy USAExternalAccessPolicy to all the users who have accounts in the UnitedStates OU in Active Directory.</span></span> <span data-ttu-id="04db1-125">有关此命令中使用的 OU 参数的详细信息, 请参阅[move-csuser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) cmdlet 的文档。</span><span class="sxs-lookup"><span data-stu-id="04db1-125">For more information on the OU parameter used in this command, see the documentation for the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) cmdlet.</span></span>
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"

</div>

<div>

## <a name="to-unassign-a-per-user-external-access-policy"></a><span data-ttu-id="04db1-126">取消分配每用户外部访问策略</span><span class="sxs-lookup"><span data-stu-id="04db1-126">To unassign a per-user external access policy</span></span>

  - <span data-ttu-id="04db1-127">此命令取消之前分配给 Ken Myer 的任何每用户外部访问策略。</span><span class="sxs-lookup"><span data-stu-id="04db1-127">This command unassigns any per-user external access policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="04db1-128">取消分配每用户策略后，将自动使用全局策略或本地站点策略（如果存在）管理 Ken Myer。</span><span class="sxs-lookup"><span data-stu-id="04db1-128">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="04db1-129">站点策略优先于全局策略。</span><span class="sxs-lookup"><span data-stu-id="04db1-129">A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null

</div>

<span data-ttu-id="04db1-130">有关详细信息, 请参阅[CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="04db1-130">For more information, see the help topic for the [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

