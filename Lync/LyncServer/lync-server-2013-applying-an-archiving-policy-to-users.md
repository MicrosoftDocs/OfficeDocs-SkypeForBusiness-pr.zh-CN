---
title: Lync Server 2013：将存档策略应用于用户
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Applying an Archiving policy to users
ms:assetid: 624a7d3e-389d-403a-97e5-f7bb17023ef3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521004(v=OCS.15)
ms:contentKeyID: 48184290
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff273b4c7afd8bf0a1280b37118eede9f95d3c76
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204411"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="applying-an-archiving-policy-to-users-in-lync-server-2013"></a><span data-ttu-id="6aec7-102">在 Lync Server 2013 中向用户应用存档策略</span><span class="sxs-lookup"><span data-stu-id="6aec7-102">Applying an Archiving policy to users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6aec7-103">_**上次修改的主题：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="6aec7-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="6aec7-104">如果已为用户启用 Lync Server 2013，并且已为驻留在 Lync Server 2013 上的用户创建了一个或多个用户策略，则可以通过向这些用户或用户组应用适当的策略来实现对特定用户的存档支持。</span><span class="sxs-lookup"><span data-stu-id="6aec7-104">If a user has been enabled for Lync Server 2013 and you have created one or more user policies for archiving for users homed on Lync Server 2013, you can implement archiving support for specific users by applying the appropriate policies to those users or user groups.</span></span> <span data-ttu-id="6aec7-105">例如，如果您创建一个策略来支持对内部通信的存档，则可以将其应用到至少一个用户或用户组，以支持用户的 Lync Server 2013 通信的存档。</span><span class="sxs-lookup"><span data-stu-id="6aec7-105">For example, if you create a policy to support archiving of internal communications, you can apply it to at least one user or user group to support archiving of the user’s Lync Server 2013 communications.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6aec7-106">如果为您的部署启用了 Microsoft Exchange 集成，则 Exchange 就地保留策略控制是否为驻留在 Exchange 2013 上的用户启用存档，并将其邮箱置于就地保留状态。</span><span class="sxs-lookup"><span data-stu-id="6aec7-106">If you enabled Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="6aec7-107">有关详细信息，请参阅部署文档中的<A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">使用 Exchange Server 集成时，请参阅在 Lync Server 2013 中设置存档策略</A>。</span><span class="sxs-lookup"><span data-stu-id="6aec7-107">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="6aec7-108">在启用存档之前，应在存档配置中指定所有适当选项。</span><span class="sxs-lookup"><span data-stu-id="6aec7-108">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span> <span data-ttu-id="6aec7-109">有关详细信息，请参阅 Operations 文档中的在<A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Lync Server 2013 中管理存档配置选项（针对组织、网站和池</A>）。</span><span class="sxs-lookup"><span data-stu-id="6aec7-109">For details, see <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</A> in the Operations documentation.</span></span>



</div>

<span data-ttu-id="6aec7-110">使用本主题中的过程将以前创建的存档用户策略应用于一个或多个用户帐户或用户组。</span><span class="sxs-lookup"><span data-stu-id="6aec7-110">Use the procedure in this topic to apply a previously created Archiving user policy to one or more user accounts or user groups.</span></span>

<div>

## <a name="to-apply-an-archiving-user-policy-to-a-user-account"></a><span data-ttu-id="6aec7-111">将存档用户策略应用于用户帐户</span><span class="sxs-lookup"><span data-stu-id="6aec7-111">To apply an archiving user policy to a user account</span></span>

1.  <span data-ttu-id="6aec7-112">使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="6aec7-112">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="6aec7-113">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="6aec7-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="6aec7-114">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="6aec7-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="6aec7-115">在左侧导航栏中，单击“用户”\*\*\*\*，然后搜索要配置的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="6aec7-115">In the left navigation bar, click **Users**, and then search for the user account that you want to configure.</span></span>

4.  <span data-ttu-id="6aec7-116">在列出搜索结果的表中，单击相应的用户帐户，再单击“编辑”\*\*\*\*，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6aec7-116">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="6aec7-117">在 "**编辑 Lync Server 用户**" 中的 "**存档策略**" 下，选择要应用的存档用户策略。</span><span class="sxs-lookup"><span data-stu-id="6aec7-117">In **Edit Lync Server User** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6aec7-118">" <STRONG> &lt;自动&gt; </STRONG>设置" 应用默认服务器安装设置。</span><span class="sxs-lookup"><span data-stu-id="6aec7-118">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server installation settings.</span></span> <span data-ttu-id="6aec7-119">服务器将自动应用这些设置。</span><span class="sxs-lookup"><span data-stu-id="6aec7-119">These settings are applied automatically by the server.</span></span>

    
    </div>

6.  <span data-ttu-id="6aec7-120">单击“提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6aec7-120">Click **Commit**.</span></span>

</div>

<div>

## <a name="assigning-a-per-user-archiving-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="6aec7-121">使用 Windows PowerShell Cmdlet 分配每用户存档策略</span><span class="sxs-lookup"><span data-stu-id="6aec7-121">Assigning a Per-User Archiving Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="6aec7-122">可以使用 Windows PowerShell 和**new-csarchivingpolicy** cmdlet 分配每用户存档策略。</span><span class="sxs-lookup"><span data-stu-id="6aec7-122">Per-user archiving policies can be assigned by using Windows PowerShell and the **Grant-CsArchivingPolicy** cmdlet.</span></span> <span data-ttu-id="6aec7-123">您可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="6aec7-123">You can run this cmdlet from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="6aec7-124">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。</span><span class="sxs-lookup"><span data-stu-id="6aec7-124">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-assign-a-per-user-archiving-policy-to-a-single-user"></a><span data-ttu-id="6aec7-125">将每用户存档策略分配给单个用户</span><span class="sxs-lookup"><span data-stu-id="6aec7-125">To assign a per-user archiving policy to a single user</span></span>

  - <span data-ttu-id="6aec7-126">以下命令向用户 Ken Myer 分配每用户存档策略 RedmondArchivingPolicy。</span><span class="sxs-lookup"><span data-stu-id="6aec7-126">The following command assigns the per-user archiving policy RedmondArchivingPolicy to the user Ken Myer.</span></span>
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-archiving-policy-to-multiple-users"></a><span data-ttu-id="6aec7-127">将每用户存档策略分配给多个用户</span><span class="sxs-lookup"><span data-stu-id="6aec7-127">To assign a per-user archiving policy to multiple users</span></span>

  - <span data-ttu-id="6aec7-128">此命令向帐户驻留在注册器池 atl-cs-001.litwareinc.com 的所有用户分配每用户存档策略 RedmondArchivingPolicy。</span><span class="sxs-lookup"><span data-stu-id="6aec7-128">This command assigns the per-user archiving policy RedmondArchivingPolicy to all users who have accounts homed on the Registrar pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="6aec7-129">有关此命令中使用的 Filter 参数的详细信息，请参阅[get-csuser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) cmdlet 文档。</span><span class="sxs-lookup"><span data-stu-id="6aec7-129">For details about the Filter parameter used in this command, see the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) cmdlet documentation.</span></span>
    
        Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-archiving-policy"></a><span data-ttu-id="6aec7-130">分配每用户存档策略</span><span class="sxs-lookup"><span data-stu-id="6aec7-130">To assign a per-user archiving policy</span></span>

  - <span data-ttu-id="6aec7-p108">以下命令取消之前已分配给 Ken Myer 的所有每用户存档策略的分配。在取消分配每用户策略后，将自动使用全局策略或本地站点策略（如果有）管理 Ken Myer。站点策略优先于全局策略。</span><span class="sxs-lookup"><span data-stu-id="6aec7-p108">The following command unassigns any per-user archiving policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null

</div>

<span data-ttu-id="6aec7-134">有关详细信息，请参阅[new-csarchivingpolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsArchivingPolicy) cmdlet 文档。</span><span class="sxs-lookup"><span data-stu-id="6aec7-134">For details, see the [Grant-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsArchivingPolicy) cmdlet documentation.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6aec7-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6aec7-135">See Also</span></span>


[<span data-ttu-id="6aec7-136">在 Lync Server 2013 中管理内部和外部通信的存档</span><span class="sxs-lookup"><span data-stu-id="6aec7-136">Managing the Archiving of internal and external communications in Lync Server 2013</span></span>](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)  
[<span data-ttu-id="6aec7-137">在 Lync Server 2013 中分配每用户策略</span><span class="sxs-lookup"><span data-stu-id="6aec7-137">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

