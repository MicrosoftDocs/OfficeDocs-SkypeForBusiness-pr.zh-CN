---
title: Lync Server 2013：分配会议策略以支持匿名用户
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign conferencing policies to support anonymous users
ms:assetid: 662de022-1111-40f7-bad4-f2b686f30973
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521007(v=OCS.15)
ms:contentKeyID: 48184333
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5077bcc07aa8bf1d32d8774fc0e863a478c9c3a7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030085"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-conferencing-policies-to-support-anonymous-users-in-lync-server-2013"></a><span data-ttu-id="90530-102">在 Lync Server 2013 中分配会议策略以支持匿名用户</span><span class="sxs-lookup"><span data-stu-id="90530-102">Assign conferencing policies to support anonymous users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="90530-103">_**上次修改的主题：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="90530-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="90530-104">默认情况下，禁止所有用户邀请匿名用户参加会议。</span><span class="sxs-lookup"><span data-stu-id="90530-104">By default, all users are prevented from inviting anonymous users to participate in a meeting.</span></span> <span data-ttu-id="90530-105">通过配置支持匿名用户的会议策略并将该会议策略应用于特定用户，可以控制能够邀请匿名用户的用户。</span><span class="sxs-lookup"><span data-stu-id="90530-105">You control who can invite anonymous users by configuring a conferencing policy to support anonymous users, and applying that conferencing policy to specific users.</span></span> <span data-ttu-id="90530-106">有关如何配置会议策略以支持匿名用户的详细信息，请参阅[在 Lync server 2013 中创建或修改会议策略](lync-server-2013-create-or-modify-a-conferencing-policy.md)和[管理对 Lync server 2013 的联盟和外部访问](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="90530-106">For details about how to configure a conferencing policies to support anonymous users, see [Create or modify a conferencing policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md) and [Managing federation and external access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md).</span></span>

<span data-ttu-id="90530-107">使用本节中的过程可将已创建的会议策略应用于一个或多个用户或用户组。</span><span class="sxs-lookup"><span data-stu-id="90530-107">Use the procedure in this section to apply a conferencing policy that you have already created to one or more users or user groups.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="90530-108">除了配置和应用策略以允许用户邀请匿名用户之外，还必须为组织启用对匿名用户的支持。</span><span class="sxs-lookup"><span data-stu-id="90530-108">In addition to configuring and applying a policy to enable users to invite anonymous users, you must also enable support for anonymous users for your organization.</span></span> <span data-ttu-id="90530-109">有关详细信息，请参阅<A href="lync-server-2013-configure-policies-to-control-public-user-access.md">在 Lync Server 2013 中配置控制公用用户访问的策略</A>。</span><span class="sxs-lookup"><span data-stu-id="90530-109">For details, see <A href="lync-server-2013-configure-policies-to-control-public-user-access.md">Configure policies to control public user access in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a><span data-ttu-id="90530-110">为匿名参与会议配置用户策略</span><span class="sxs-lookup"><span data-stu-id="90530-110">To configure a user policy for anonymous participation in meetings</span></span>

1.  <span data-ttu-id="90530-111">从作为 RTCUniversalServerAdmins 组成员的用户帐户（或具有等效的用户权限）或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="90530-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="90530-112">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="90530-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="90530-113">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="90530-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="90530-114">在左侧导航栏中，单击“会议”\*\*\*\*，然后执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="90530-114">In the left navigation bar, click **Conferencing**, and then do one of the following:</span></span>
    
    1.  <span data-ttu-id="90530-p104">要创建新的用户策略，请单击“新建”\*\*\*\*，然后单击“用户策略”\*\*\*\*。在“名称”\*\*\*\* 字段中，创建一个唯一的名称以指示用户策略的作用范围（例如，**EnableAnonymous** 代表允许与匿名用户进行通信的用户策略）。</span><span class="sxs-lookup"><span data-stu-id="90530-p104">To create a new user policy, click **New**, and then click **User policy**. Create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableAnonymous** for a user policy that enables communications with anonymous users).</span></span>
    
    2.  <span data-ttu-id="90530-117">要配置现有用户策略，请单击表中列出的相应策略，再单击“编辑”\*\*\*\*，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="90530-117">To configure an existing user policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

4.  <span data-ttu-id="90530-118">在“会议策略”\*\*\*\* 对话框中，选中“允许参与者邀请匿名用户”\*\*\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="90530-118">In the **Conferencing Policies** dialog box, select the **Allow participants to invite anonymous users** check box.</span></span>

5.  <span data-ttu-id="90530-119">单击“提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="90530-119">Click **Commit**.</span></span>

6.  <span data-ttu-id="90530-120">在左侧导航栏中，单击“用户”\*\*\*\*，搜索要配置的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="90530-120">In the left navigation bar, click **Users**, search on the user account that you want to configure.</span></span>

7.  <span data-ttu-id="90530-121">在列出搜索结果的表中，单击相应的用户帐户，再单击“编辑”\*\*\*\*，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="90530-121">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

8.  <span data-ttu-id="90530-122">在“编辑 Lync Server 用户”\*\*\*\* 中的“会议策略”\*\*\*\* 下，选择具有要应用于此用户的匿名用户访问配置的用户策略。</span><span class="sxs-lookup"><span data-stu-id="90530-122">In **Edit Lync Server User** under **Conferencing policy**, select the user policy with the anonymous user access configuration that you want to apply to this user.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="90530-123">" <STRONG> &lt;自动&gt; </STRONG>设置" 应用默认服务器安装设置并由服务器自动应用。</span><span class="sxs-lookup"><span data-stu-id="90530-123">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server installation settings and are applied automatically by the server.</span></span>

    
    </div>

<span data-ttu-id="90530-124">要允许用户邀请匿名用户参加会议，还必须在组织中启用匿名用户支持。</span><span class="sxs-lookup"><span data-stu-id="90530-124">To enable users to invite anonymous users to conferences, you must also enable support for anonymous users in your organization.</span></span> <span data-ttu-id="90530-125">有关详细信息，请参阅部署文档或操作文档中的[配置策略以控制公共用户访问在 Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md)中。</span><span class="sxs-lookup"><span data-stu-id="90530-125">For details, see [Configure policies to control public user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md) in the Deployment documentation or the Operations documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

