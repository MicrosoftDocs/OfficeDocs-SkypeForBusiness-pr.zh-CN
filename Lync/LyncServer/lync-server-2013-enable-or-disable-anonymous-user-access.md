---
title: Lync Server 2013：启用或禁用匿名用户访问
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable or disable anonymous user access
ms:assetid: f10c19e6-b6f9-4d26-9923-0165f36e4af8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619192(v=OCS.15)
ms:contentKeyID: 49733872
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d07bf27f5424f121c5dcf070f5231e2fd8c324f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830312"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-anonymous-user-access-in-lync-server-2013"></a><span data-ttu-id="88801-102">在 Lync Server 2013 中启用或禁用匿名用户访问</span><span class="sxs-lookup"><span data-stu-id="88801-102">Enable or disable anonymous user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="88801-103">_**主题上次修改时间:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="88801-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="88801-104">匿名用户是在组织的 Active Directory 域服务或受支持的联盟域中没有用户帐户的用户, 但可以邀请他们在本地会议中进行远程参与。</span><span class="sxs-lookup"><span data-stu-id="88801-104">Anonymous users are users who do not have a user account in your organization's Active Directory Domain Services or in a supported federated domain, but can be invited to participate remotely in an on-premises conference.</span></span> <span data-ttu-id="88801-105">通过允许匿名参与会议, 你可以启用匿名用户 (即仅通过会议或会议密钥验证身份的用户) 来加入会议。</span><span class="sxs-lookup"><span data-stu-id="88801-105">By allowing anonymous participation in meetings you enable anonymous users (that is, users whose identity is verified through the meeting or conference key only) to join meetings.</span></span> <span data-ttu-id="88801-106">允许匿名参与需要为你的组织启用它。</span><span class="sxs-lookup"><span data-stu-id="88801-106">Allowing anonymous participation requires enabling it for your organization.</span></span>

<span data-ttu-id="88801-107">如果稍后想要临时或永久阻止匿名用户的访问, 则可以为你的组织禁用它。</span><span class="sxs-lookup"><span data-stu-id="88801-107">If you later want to temporarily or permanently prevent access by anonymous users, you can disable it for your organization.</span></span> <span data-ttu-id="88801-108">使用此部分中的过程可为你的组织启用或禁用匿名用户访问权限。</span><span class="sxs-lookup"><span data-stu-id="88801-108">Use the procedure in this section to enable or disable anonymous user access for your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="88801-109">通过为你的组织启用匿名用户访问, 仅指定运行 Access Edge 服务的服务器支持匿名用户的访问。</span><span class="sxs-lookup"><span data-stu-id="88801-109">By enabling anonymous user access for your organization you are only specifying that your servers running the Access Edge service support access by anonymous users.</span></span> <span data-ttu-id="88801-110">匿名用户不能参与您的组织中的任何会议, 除非您还配置了至少一个会议策略并将其应用于一个或多个用户或用户组。</span><span class="sxs-lookup"><span data-stu-id="88801-110">Anonymous users cannot participate in any meetings in your organization until you also configure at least one conferencing policy and apply it to one or more users or user groups.</span></span> <span data-ttu-id="88801-111">只有分配了会议策略 (配置为支持匿名用户) 的用户才可以邀请匿名用户加入会议。</span><span class="sxs-lookup"><span data-stu-id="88801-111">The only users that can invite anonymous users to meetings are those users that are assigned a conferencing policy that is configured to support anonymous users.</span></span> <span data-ttu-id="88801-112">有关配置会议策略以支持邀请匿名用户的详细信息, 请参阅<A href="lync-server-2013-conferencing-policies.md">Lync Server 2013 中的会议策略</A>。</span><span class="sxs-lookup"><span data-stu-id="88801-112">For details about configuring conferencing policies to support inviting anonymous users, see <A href="lync-server-2013-conferencing-policies.md">Conferencing policies in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a><span data-ttu-id="88801-113">为你的组织启用或禁用匿名用户访问</span><span class="sxs-lookup"><span data-stu-id="88801-113">To enable or disable anonymous user access for your organization</span></span>

1.  <span data-ttu-id="88801-114">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="88801-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="88801-115">打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="88801-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="88801-116">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="88801-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="88801-117">在左侧导航栏中, 单击 "**外部用户访问**", 然后单击 "**访问边缘配置**"。</span><span class="sxs-lookup"><span data-stu-id="88801-117">In the left navigation bar, click **External User Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="88801-118">在 "**访问边缘配置**" 页面上, 单击 "**全局**", 单击 "**编辑**", 然后单击 "**显示详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="88801-118">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="88801-119">在 "**编辑访问边缘配置**" 中, 执行下列操作之一:</span><span class="sxs-lookup"><span data-stu-id="88801-119">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="88801-120">若要为你的组织启用匿名用户访问, 请选中 "**启用与匿名用户的通信**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="88801-120">To enable anonymous user access for your organization, select the **Enable communications with anonymous users** check box.</span></span>
    
      - <span data-ttu-id="88801-121">若要为你的组织禁用匿名用户访问, 请清除 "**启用与匿名用户的通信**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="88801-121">To disable anonymous user access for your organization, clear the **Enable communications with anonymous users** check box.</span></span>

6.  <span data-ttu-id="88801-122">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="88801-122">Click **Commit**.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="88801-123">使用 Windows PowerShell Cmdlet 启用或禁用匿名用户访问</span><span class="sxs-lookup"><span data-stu-id="88801-123">Enabling or Disabling Anonymous User Access by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="88801-124">你可以使用 Windows PowerShell 和**CsAccessEdgeConfiguration** cmdlet 管理匿名用户访问。</span><span class="sxs-lookup"><span data-stu-id="88801-124">You can manage anonymous user access by using Windows PowerShell and the **Set-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="88801-125">你可以从 Lync Server 2013 命令行管理程序或 Windows PowerShell 的远程会话运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="88801-125">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="88801-126">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息, 请参阅 Lync Server Windows PowerShell 博客文章 "快速入门: 使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="88801-126">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-anonymous-user-access"></a><span data-ttu-id="88801-127">启用匿名用户访问</span><span class="sxs-lookup"><span data-stu-id="88801-127">To enable anonymous user access</span></span>

  - <span data-ttu-id="88801-128">若要启用匿名用户访问, 请将**AllowAnonymousUsers**属性的值设置为 True ($True):</span><span class="sxs-lookup"><span data-stu-id="88801-128">To enable anonymous user access, set the value of the **AllowAnonymousUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

</div>

<div>

## <a name="to-disable-anonymous-user-access"></a><span data-ttu-id="88801-129">禁用匿名用户访问</span><span class="sxs-lookup"><span data-stu-id="88801-129">To disable anonymous user access</span></span>

  - <span data-ttu-id="88801-130">若要禁用匿名用户访问, 请将**AllowAnonymousUsers**属性的值设置为 False ($False):</span><span class="sxs-lookup"><span data-stu-id="88801-130">To disable anonymous user access, set the value of the **AllowAnonymousUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="88801-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="88801-131">See Also</span></span>


[<span data-ttu-id="88801-132">Lync Server 2013 的会议策略设置参考</span><span class="sxs-lookup"><span data-stu-id="88801-132">Conferencing policy settings reference for Lync Server 2013</span></span>](lync-server-2013-conferencing-policy-settings-reference.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

