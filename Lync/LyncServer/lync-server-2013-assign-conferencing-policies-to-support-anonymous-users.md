---
title: Lync Server 2013：分配会议策略以支持匿名用户
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign conferencing policies to support anonymous users
ms:assetid: 662de022-1111-40f7-bad4-f2b686f30973
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521007(v=OCS.15)
ms:contentKeyID: 48184333
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 94ff3fe520b776d6f6043abb66f9926da5acaa22
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845990"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-conferencing-policies-to-support-anonymous-users-in-lync-server-2013"></a><span data-ttu-id="0c497-102">在 Lync Server 2013 中分配会议策略以支持匿名用户</span><span class="sxs-lookup"><span data-stu-id="0c497-102">Assign conferencing policies to support anonymous users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0c497-103">_**主题上次修改时间:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="0c497-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="0c497-104">默认情况下, 将阻止所有用户邀请匿名用户参与会议。</span><span class="sxs-lookup"><span data-stu-id="0c497-104">By default, all users are prevented from inviting anonymous users to participate in a meeting.</span></span> <span data-ttu-id="0c497-105">你可以通过配置会议策略来控制哪些人可以邀请匿名用户, 并将该会议策略应用于特定用户。</span><span class="sxs-lookup"><span data-stu-id="0c497-105">You control who can invite anonymous users by configuring a conferencing policy to support anonymous users, and applying that conferencing policy to specific users.</span></span> <span data-ttu-id="0c497-106">有关如何配置会议策略以支持匿名用户的详细信息, 请参阅[在 Lync server 2013 中创建或修改会议策略](lync-server-2013-create-or-modify-a-conferencing-policy.md)以及[管理对 lync server 2013 的联盟和外部访问](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="0c497-106">For details about how to configure a conferencing policies to support anonymous users, see [Create or modify a conferencing policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md) and [Managing federation and external access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md).</span></span>

<span data-ttu-id="0c497-107">使用此部分中的过程将已创建的会议策略应用于一个或多个用户或用户组。</span><span class="sxs-lookup"><span data-stu-id="0c497-107">Use the procedure in this section to apply a conferencing policy that you have already created to one or more users or user groups.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0c497-108">除了配置和应用策略以允许用户邀请匿名用户之外, 还必须为你的组织启用匿名用户支持。</span><span class="sxs-lookup"><span data-stu-id="0c497-108">In addition to configuring and applying a policy to enable users to invite anonymous users, you must also enable support for anonymous users for your organization.</span></span> <span data-ttu-id="0c497-109">有关详细信息, 请参阅<A href="lync-server-2013-configure-policies-to-control-public-user-access.md">在 Lync Server 2013 中配置控制公共用户访问的策略</A>。</span><span class="sxs-lookup"><span data-stu-id="0c497-109">For details, see <A href="lync-server-2013-configure-policies-to-control-public-user-access.md">Configure policies to control public user access in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a><span data-ttu-id="0c497-110">配置匿名参与会议的用户策略</span><span class="sxs-lookup"><span data-stu-id="0c497-110">To configure a user policy for anonymous participation in meetings</span></span>

1.  <span data-ttu-id="0c497-111">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="0c497-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0c497-112">打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="0c497-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="0c497-113">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="0c497-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="0c497-114">在左侧导航栏中, 单击 "**会议**", 然后执行下列操作之一:</span><span class="sxs-lookup"><span data-stu-id="0c497-114">In the left navigation bar, click **Conferencing**, and then do one of the following:</span></span>
    
    1.  <span data-ttu-id="0c497-115">若要创建新的用户策略, 请单击 "**新建**", 然后单击 "**用户策略**"。</span><span class="sxs-lookup"><span data-stu-id="0c497-115">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="0c497-116">在 "**名称**" 字段中创建一个唯一名称, 用于指示用户策略所涉及的内容 (例如, **EnableAnonymous**适用于启用与匿名用户的通信的用户策略)。</span><span class="sxs-lookup"><span data-stu-id="0c497-116">Create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableAnonymous** for a user policy that enables communications with anonymous users).</span></span>
    
    2.  <span data-ttu-id="0c497-117">若要配置现有用户策略, 请单击表中列出的相应策略, 单击 "**编辑**", 然后单击 "**显示详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="0c497-117">To configure an existing user policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

4.  <span data-ttu-id="0c497-118">在 "**会议策略**" 对话框中, 选中 "**允许参与者邀请匿名用户**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="0c497-118">In the **Conferencing Policies** dialog box, select the **Allow participants to invite anonymous users** check box.</span></span>

5.  <span data-ttu-id="0c497-119">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="0c497-119">Click **Commit**.</span></span>

6.  <span data-ttu-id="0c497-120">在左侧导航栏中, 单击 "**用户**", 搜索要配置的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="0c497-120">In the left navigation bar, click **Users**, search on the user account that you want to configure.</span></span>

7.  <span data-ttu-id="0c497-121">在列出搜索结果的表中，单击相应的用户帐户，再单击“**编辑**”，然后单击“**显示详细信息**”。</span><span class="sxs-lookup"><span data-stu-id="0c497-121">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

8.  <span data-ttu-id="0c497-122">在 "在**会议策略**中**编辑 Lync 服务器用户**" 下, 选择包含要应用于此用户的匿名用户访问配置的用户策略。</span><span class="sxs-lookup"><span data-stu-id="0c497-122">In **Edit Lync Server User** under **Conferencing policy**, select the user policy with the anonymous user access configuration that you want to apply to this user.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0c497-123">" <STRONG> &lt;自动&gt; </STRONG>设置" 应用默认服务器安装设置, 并由服务器自动应用。</span><span class="sxs-lookup"><span data-stu-id="0c497-123">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server installation settings and are applied automatically by the server.</span></span>

    
    </div>

<span data-ttu-id="0c497-124">若要使用户能够邀请匿名用户加入会议, 还必须在组织中启用匿名用户支持。</span><span class="sxs-lookup"><span data-stu-id="0c497-124">To enable users to invite anonymous users to conferences, you must also enable support for anonymous users in your organization.</span></span> <span data-ttu-id="0c497-125">有关详细信息, 请参阅在部署文档或操作文档中,[配置控制在 Lync Server 2013 中控制公共用户访问的策略](lync-server-2013-configure-policies-to-control-public-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="0c497-125">For details, see [Configure policies to control public user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md) in the Deployment documentation or the Operations documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

