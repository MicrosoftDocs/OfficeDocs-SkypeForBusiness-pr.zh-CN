---
title: Lync Server 2013：将外部用户访问策略分配给启用 Lync 的用户
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign an external user access policy to a Lync enabled user
ms:assetid: 736fcaad-9f95-4896-b767-e199d86a00a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398551(v=OCS.15)
ms:contentKeyID: 48184483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 28d8dffe68b9eb1e4c21bc937075f5fcb5ff23f5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134378"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="assign-an-external-user-access-policy-to-a-lync-enabled-user-in-lync-server-2013"></a><span data-ttu-id="e897a-102">在 Lync Server 2013 中将外部用户访问策略分配给启用 Lync 的用户</span><span class="sxs-lookup"><span data-stu-id="e897a-102">Assign an external user access policy to a Lync enabled user in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e897a-103">_**上次修改的主题：** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="e897a-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="e897a-104">如果已为用户启用 Lync Server，则可以通过将适当的策略应用于特定用户，在 Lync Server 控制面板中配置 SIP 联合身份验证、XMPP 联合身份验证、远程用户访问和公共即时消息（IM）连接。</span><span class="sxs-lookup"><span data-stu-id="e897a-104">If a user has been enabled for Lync Server, you can configure SIP federation, XMPP federation, remote user access, and public instant messaging (IM) connectivity in the Lync Server Control Panel by applying the appropriate policies to specific users.</span></span> <span data-ttu-id="e897a-105">例如，如果创建了一个支持远程用户访问的策略，则必须将其应用于用户，然后用户才能从远程位置连接到 Lync Server，并从远程位置与内部用户进行协作。</span><span class="sxs-lookup"><span data-stu-id="e897a-105">For example, if you created a policy to support remote user access, you must apply it to the user before the user can connect to Lync Server from a remote location and collaborate with internal users from the remote location.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e897a-106">要支持外部用户访问，必须启用对要支持的每种外部用户访问类型的支持，并配置相应的策略及其他选项以控制其使用。</span><span class="sxs-lookup"><span data-stu-id="e897a-106">To support external user access, you must enable support for each type of external user access you want to support, and configure the appropriate policies and other options to control its use.</span></span> <span data-ttu-id="e897a-107">有关详细信息，请参阅部署文档中的在<A href="lync-server-2013-configuring-support-for-external-user-access.md">Lync server 2013 中配置外部用户访问支持</A>或在操作文档中<A href="lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md">管理联合身份验证和外部访问 lync server 2013</A> 。</span><span class="sxs-lookup"><span data-stu-id="e897a-107">For details, see <A href="lync-server-2013-configuring-support-for-external-user-access.md">Configuring support for external user access in Lync Server 2013</A> in the Deployment documentation or <A href="lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md">Managing federation and external access to Lync Server 2013</A> in the Operations documentation.</span></span>



</div>

<span data-ttu-id="e897a-108">使用本主题中的过程将以前创建的外部用户访问策略应用于一个或多个用户帐户。</span><span class="sxs-lookup"><span data-stu-id="e897a-108">Use the procedure in this topic to apply a previously created external user access policy to one or more user accounts.</span></span>

<div>

## <a name="to-apply-an-external-user-policy-to-a-user-account"></a><span data-ttu-id="e897a-109">将外部用户策略应用于用户帐户</span><span class="sxs-lookup"><span data-stu-id="e897a-109">To apply an external user policy to a user account</span></span>

1.  <span data-ttu-id="e897a-110">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="e897a-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e897a-111">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="e897a-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e897a-112">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="e897a-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e897a-113">在左侧导航栏中，单击“用户”\*\*\*\*，然后搜索要配置的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="e897a-113">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>

4.  <span data-ttu-id="e897a-114">在列出搜索结果的表中，单击相应的用户帐户，再单击“编辑”\*\*\*\*，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e897a-114">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="e897a-115">在“编辑 Lync Server 用户”\*\*\*\* 中的“外部访问策略”\*\*\*\* 下，选择要应用的用户策略。</span><span class="sxs-lookup"><span data-stu-id="e897a-115">In **Edit Lync Server User** under **External access policy**, select the user policy that you want to apply.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e897a-116">" <STRONG> &lt;自动&gt; </STRONG> " 设置将应用默认服务器或全局策略设置。</span><span class="sxs-lookup"><span data-stu-id="e897a-116">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server or global policy settings.</span></span>

    
    </div>

</div>

<div>

## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="e897a-117">使用 Windows PowerShell Cmdlet 分配每用户外部访问策略</span><span class="sxs-lookup"><span data-stu-id="e897a-117">Assigning Per-User External Access Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="e897a-118">可以使用 Windows PowerShell 和 Set-csexternalaccesspolicy cmdlet 分配每用户外部访问策略。</span><span class="sxs-lookup"><span data-stu-id="e897a-118">Per-user external access policies can be assigned by using Windows PowerShell and the Grant-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="e897a-119">此 cmdlet 可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行。</span><span class="sxs-lookup"><span data-stu-id="e897a-119">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="e897a-120">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。</span><span class="sxs-lookup"><span data-stu-id="e897a-120">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a><span data-ttu-id="e897a-121">向单个用户分配每用户外部访问策略</span><span class="sxs-lookup"><span data-stu-id="e897a-121">To assign a per-user external access policy to a single user</span></span>

  - <span data-ttu-id="e897a-122">此命令向用户 Ken Myer 分配每用户外部访问策略 RedmondExternalAccessPolicy。</span><span class="sxs-lookup"><span data-stu-id="e897a-122">This command assigns the per-user external access policy RedmondExternalAccessPolicy to the user Ken Myer.</span></span>
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a><span data-ttu-id="e897a-123">为多个用户分配每用户外部访问策略</span><span class="sxs-lookup"><span data-stu-id="e897a-123">To assign a per-user external access policy to multiple users</span></span>

  - <span data-ttu-id="e897a-124">此命令向在 Active Directory 的 UnitedStates OU 中拥有帐户的所有用户分配每用户外部访问策略 USAExternalAccessPolicy。</span><span class="sxs-lookup"><span data-stu-id="e897a-124">This command assigns the per-user external access policy USAExternalAccessPolicy to all the users who have accounts in the UnitedStates OU in Active Directory.</span></span> <span data-ttu-id="e897a-125">有关此命令中使用的 OU 参数的详细信息，请参阅[get-csuser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) cmdlet 的相关文档。</span><span class="sxs-lookup"><span data-stu-id="e897a-125">For more information on the OU parameter used in this command, see the documentation for the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) cmdlet.</span></span>
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"

</div>

<div>

## <a name="to-unassign-a-per-user-external-access-policy"></a><span data-ttu-id="e897a-126">取消分配每用户外部访问策略</span><span class="sxs-lookup"><span data-stu-id="e897a-126">To unassign a per-user external access policy</span></span>

  - <span data-ttu-id="e897a-p106">此命令取消分配之前为 Ken Myer 分配的任何每用户外部访问策略。在取消分配每用户策略后，将自动使用全局策略或本地站点策略（如果有）管理 Ken Myer。站点策略优先于全局策略。</span><span class="sxs-lookup"><span data-stu-id="e897a-p106">This command unassigns any per-user external access policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null

</div>

<span data-ttu-id="e897a-130">有关详细信息，请参阅[set-csexternalaccesspolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="e897a-130">For more information, see the help topic for the [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

