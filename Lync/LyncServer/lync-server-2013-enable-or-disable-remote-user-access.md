---
title: Lync Server 2013：启用或禁用远程用户访问
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable remote user access
ms:assetid: cd9d3ddc-4839-457a-86d9-b15413e74002
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182586(v=OCS.15)
ms:contentKeyID: 48185660
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c673295f2344d2ca3ca853f76775bbae47a74328
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045624"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-remote-user-access-in-lync-server-2013"></a><span data-ttu-id="9b1ac-102">在 Lync Server 2013 中启用或禁用远程用户访问</span><span class="sxs-lookup"><span data-stu-id="9b1ac-102">Enable or disable remote user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9b1ac-103">_**上次修改的主题：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="9b1ac-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="9b1ac-104">远程用户是组织内拥有持久 Active Directory 标识的用户。</span><span class="sxs-lookup"><span data-stu-id="9b1ac-104">Remote users are users in your organization who have a persistent Active Directory identity within the organization.</span></span> <span data-ttu-id="9b1ac-105">当远程用户未连接到您的组织的网络时，他们通常使用虚拟专用网络（VPN）从网络外部登录 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="9b1ac-105">Remote users often sign in to Lync Server from outside your network by using a virtual private network (VPN) when they are not connected to your organization’s network.</span></span> <span data-ttu-id="9b1ac-106">远程用户包括在家或在路上工作的员工以及其他远程工作者，如已被授予企业凭据的受信任供应商。</span><span class="sxs-lookup"><span data-stu-id="9b1ac-106">Remote users include employees working at home or on the road and other remote workers, such as trusted vendors, who have been granted enterprise credentials.</span></span> <span data-ttu-id="9b1ac-107">如果为远程用户启用远程用户访问，则受支持的远程用户通过 Internet 进行连接，并且无需使用 VPN 进行连接，以便与使用 Lync Server 的内部用户进行协作。</span><span class="sxs-lookup"><span data-stu-id="9b1ac-107">If you enable remote user access for remote users, supported remote users connect over the Internet and do not have to connect using a VPN in order to collaborate with internal users using Lync Server.</span></span>

<span data-ttu-id="9b1ac-p102">要支持远程用户访问，必须启用远程用户访问。启用远程用户访问即为整个组织启用。如果稍后要暂时或永久阻止远程用户访问，可以为组织将其禁用。可以使用本节中的步骤为组织启用或禁用远程用户访问。</span><span class="sxs-lookup"><span data-stu-id="9b1ac-p102">To support remote user access, you must enable remote user access. When you enable remote user access, you enable it for your entire organization. If you later want to temporarily or permanently prevent remote user access, you can disable it for your organization. Use the procedure in this section to enable or disable remote user access for your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9b1ac-112">启用远程用户访问仅指定运行访问边缘服务的服务器支持与远程用户的通信，但远程用户无法在您的组织中参与即时消息（IM）或会议，除非您还在配置至少一个用于管理远程用户访问的策略。</span><span class="sxs-lookup"><span data-stu-id="9b1ac-112">Enabling remote user access only specifies that your servers running the Access Edge service support communications with remote users, but remote users cannot participate in instant messaging (IM) or conferences in your organization until you also configure at least one policy to manage the use of remote user access.</span></span> <span data-ttu-id="9b1ac-113">在一个策略级别应用的 Lync Server 策略设置可以覆盖在另一个策略级别应用的设置。</span><span class="sxs-lookup"><span data-stu-id="9b1ac-113">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="9b1ac-114">Lync Server 策略优先级为：用户策略（最具影响力）替代网站策略，然后网站策略将覆盖全局策略（最不影响）。</span><span class="sxs-lookup"><span data-stu-id="9b1ac-114">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="9b1ac-115">这意味着，策略设置越接近策略所影响的对象，它对对象的影响越大。</span><span class="sxs-lookup"><span data-stu-id="9b1ac-115">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> <span data-ttu-id="9b1ac-116">有关为使用远程用户访问配置策略的详细信息，请参阅<A href="lync-server-2013-configure-policies-to-control-remote-user-access.md">在 Lync Server 2013 中配置用于控制远程用户访问的策略</A>。</span><span class="sxs-lookup"><span data-stu-id="9b1ac-116">For details about configuring policies for the use of remote user access, see <A href="lync-server-2013-configure-policies-to-control-remote-user-access.md">Configure policies to control remote user access in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a><span data-ttu-id="9b1ac-117">为组织启用或禁用远程用户访问</span><span class="sxs-lookup"><span data-stu-id="9b1ac-117">To enable or disable remote user access for your organization</span></span>

1.  <span data-ttu-id="9b1ac-118">从作为 RTCUniversalServerAdmins 组成员的用户帐户（或具有等效的用户权限）或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="9b1ac-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9b1ac-119">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="9b1ac-119">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="9b1ac-120">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="9b1ac-120">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="9b1ac-121">在左侧导航栏中，单击“联盟和外部访问”\*\*\*\*，然后单击“访问边缘配置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9b1ac-121">In the left navigation bar, click **Federation and External Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="9b1ac-122">在“访问边缘配置”\*\*\*\* 页上，单击“全局”\*\*\*\*，再单击“编辑”\*\*\*\*，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9b1ac-122">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="9b1ac-123">在“编辑访问边缘配置”\*\*\*\* 中，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="9b1ac-123">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="9b1ac-124">要为组织启用远程用户访问，请选中“启用远程用户访问”\*\*\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="9b1ac-124">To enable remote user access for your organization, select the **Enable remote user access** check box.</span></span>
    
      - <span data-ttu-id="9b1ac-125">要为组织禁用远程用户访问，请清除“启用远程用户访问”\*\*\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="9b1ac-125">To disable remote user access for your organization, clear the **Enable remote user access** check box.</span></span>

6.  <span data-ttu-id="9b1ac-126">单击“提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9b1ac-126">Click **Commit**.</span></span>

<span data-ttu-id="9b1ac-127">若要使远程用户能够登录到运行 Lync Server 的服务器，您还必须配置至少一个外部访问策略以支持远程用户访问。</span><span class="sxs-lookup"><span data-stu-id="9b1ac-127">To enable remote users to sign in to your servers running Lync Server, you must also configure at least one external access policy to support remote user access.</span></span> <span data-ttu-id="9b1ac-128">有关详细信息，请参阅部署文档中的[配置策略以控制远程用户访问](lync-server-2013-configure-policies-to-control-remote-user-access.md)和操作文档中的 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="9b1ac-128">For details, see [Configure policies to control remote user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md) in the Deployment documentation or the Operations documentation.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="9b1ac-129">使用 Windows PowerShell Cmdlet 启用或禁用远程用户访问</span><span class="sxs-lookup"><span data-stu-id="9b1ac-129">Enabling or Disabling Remote User Access by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="9b1ac-130">可以使用 Windows PowerShell 和 Set-csaccessedgeconfiguration cmdlet 来管理远程用户访问。</span><span class="sxs-lookup"><span data-stu-id="9b1ac-130">Remote user access can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="9b1ac-131">此 cmdlet 可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行。</span><span class="sxs-lookup"><span data-stu-id="9b1ac-131">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="9b1ac-132">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。</span><span class="sxs-lookup"><span data-stu-id="9b1ac-132">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-remote-user-access"></a><span data-ttu-id="9b1ac-133">启用远程用户访问</span><span class="sxs-lookup"><span data-stu-id="9b1ac-133">To enable remote user access</span></span>

  - <span data-ttu-id="9b1ac-134">要启用远程用户访问，请将 **AllowOutsideUsers** 属性的值设置为 True ($True)：</span><span class="sxs-lookup"><span data-stu-id="9b1ac-134">To enable remote user access, set the value of the **AllowOutsideUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

</div>

<div>

## <a name="to-disable-remote-user-access"></a><span data-ttu-id="9b1ac-135">禁用远程用户访问</span><span class="sxs-lookup"><span data-stu-id="9b1ac-135">To disable remote user access</span></span>

  - <span data-ttu-id="9b1ac-136">要禁用远程用户访问，请将 **AllowOutsideUsers** 属性的值设置为 False ($False)：</span><span class="sxs-lookup"><span data-stu-id="9b1ac-136">To disable remote user access, set the value of the **AllowOutsideUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

