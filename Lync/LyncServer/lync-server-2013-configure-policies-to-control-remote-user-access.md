---
title: Lync Server 2013：配置策略以控制远程用户访问
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure policies to control remote user access
ms:assetid: 8f556849-692b-44a0-9514-4468fc9a39d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398725(v=OCS.15)
ms:contentKeyID: 48184825
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d8542e7d64198cb83df58885b9240e07066288d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763264"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-remote-user-access-in-lync-server-2013"></a><span data-ttu-id="1a0f9-102">在 Lync Server 2013 中配置策略以控制远程用户访问</span><span class="sxs-lookup"><span data-stu-id="1a0f9-102">Configure policies to control remote user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1a0f9-103">_**主题上次修改时间：** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="1a0f9-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="1a0f9-104">配置一个或多个外部用户访问策略，以控制远程用户是否可以与内部 Lync Server 用户进行协作。</span><span class="sxs-lookup"><span data-stu-id="1a0f9-104">You configure one or more external user access policies to control whether remote users can collaborate with internal Lync Server users.</span></span> <span data-ttu-id="1a0f9-105">若要控制远程用户访问，可以在全局、网站和用户级别配置策略。</span><span class="sxs-lookup"><span data-stu-id="1a0f9-105">To control remote user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="1a0f9-106">网站策略替代全局策略，而用户策略替代网站和全局策略。</span><span class="sxs-lookup"><span data-stu-id="1a0f9-106">Site policies override the global policy, and user policies override site and global policies.</span></span> <span data-ttu-id="1a0f9-107">有关可以配置的策略类型的详细信息，请参阅[管理 Lync Server 2013 的联盟和外部访问](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="1a0f9-107">For details about the types of policies that you can configure, see [Managing federation and external access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md).</span></span> <span data-ttu-id="1a0f9-108">在一个策略级别应用的 Lync Server 策略设置可以覆盖在其他策略级别应用的设置。</span><span class="sxs-lookup"><span data-stu-id="1a0f9-108">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="1a0f9-109">Lync 服务器策略优先级为：用户策略（最受影响）覆盖网站策略，然后网站策略覆盖全局策略（最不影响）。</span><span class="sxs-lookup"><span data-stu-id="1a0f9-109">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="1a0f9-110">这意味着，策略设置与策略所影响的对象距离越近，它对该对象的影响力越大。</span><span class="sxs-lookup"><span data-stu-id="1a0f9-110">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1a0f9-111">你可以配置策略来控制远程用户访问，即使你没有为你的组织启用远程用户访问。</span><span class="sxs-lookup"><span data-stu-id="1a0f9-111">You can configure policies to control remote user access, even if you have not enabled remote user access for your organization.</span></span> <span data-ttu-id="1a0f9-112">但是，仅当你的组织启用了远程用户访问时，你配置的策略才有效。</span><span class="sxs-lookup"><span data-stu-id="1a0f9-112">However, the policies that you configure are in effect only when you have remote user access enabled for your organization.</span></span> <span data-ttu-id="1a0f9-113">有关启用远程用户访问的详细信息，请参阅<A href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">在 Lync Server 2013 中启用或禁用联盟和公共 IM 连接</A>。</span><span class="sxs-lookup"><span data-stu-id="1a0f9-113">For details about enabling remote user access, see <A href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</A>.</span></span> <span data-ttu-id="1a0f9-114">此外，如果你指定用于控制远程用户访问的用户策略，该策略将仅应用于为 Lync Server 启用且配置为使用该策略的用户。</span><span class="sxs-lookup"><span data-stu-id="1a0f9-114">Additionally, if you specify a user policy to control remote user access, the policy applies only to users that are enabled for Lync Server and configured to use the policy.</span></span> <span data-ttu-id="1a0f9-115">有关从远程位置指定可登录 Lync Server 的用户的详细信息，请参阅<A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">在 Lync server 2013 中将外部用户访问策略分配给启用 lync 的用户</A>。</span><span class="sxs-lookup"><span data-stu-id="1a0f9-115">For details about specifying users that can sign in to Lync Server from remote locations, see <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">Assign an external user access policy to a Lync enabled user in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="1a0f9-116">使用以下过程配置要用于控制远程用户访问的每个外部访问策略。</span><span class="sxs-lookup"><span data-stu-id="1a0f9-116">Use the following procedure to configure each external access policy that you want to use to control remote user access.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1a0f9-117">此过程介绍如何配置策略以启用与远程用户的通信，但配置为支持远程用户访问的每个策略也可以配置联合用户访问和公共用户访问。</span><span class="sxs-lookup"><span data-stu-id="1a0f9-117">This procedure describes how to configure a policy only to enable communications with remote users, but each policy that you configure to support remote user access can also configure federated user access and public user access.</span></span> <span data-ttu-id="1a0f9-118">有关配置支持联盟用户的策略的详细信息，请参阅<A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">在 Lync Server 2013 中配置用于控制联盟用户访问的策略</A>。</span><span class="sxs-lookup"><span data-stu-id="1a0f9-118">For details about configuring policies to support federated users, see <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configure policies to control federated user access in Lync Server 2013</A>.</span></span> <span data-ttu-id="1a0f9-119">有关配置策略以支持公共用户的详细信息，请参阅<A href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">在 Lync Server 2013 中创建或编辑公共 SIP 联合提供商</A>。</span><span class="sxs-lookup"><span data-stu-id="1a0f9-119">For details about configuring policies to support public users, see <A href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Create or edit public SIP federated providers in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-configure-an-external-access-policy-to-support-remote-user-access"></a><span data-ttu-id="1a0f9-120">将外部访问策略配置为支持远程用户访问</span><span class="sxs-lookup"><span data-stu-id="1a0f9-120">To configure an external access policy to support remote user access</span></span>

1.  <span data-ttu-id="1a0f9-121">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="1a0f9-121">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1a0f9-122">打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="1a0f9-122">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1a0f9-123">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="1a0f9-123">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1a0f9-124">在左侧导航栏中，单击 "**外部用户访问**"，然后单击 "**外部访问策略**"。</span><span class="sxs-lookup"><span data-stu-id="1a0f9-124">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="1a0f9-125">在 "**外部访问策略**" 页面上，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="1a0f9-125">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="1a0f9-126">若要将全局策略配置为支持远程用户访问，请单击全局策略，单击 "**编辑**"，然后单击 "**显示详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="1a0f9-126">To configure the global policy to support remote user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="1a0f9-127">若要创建新的网站策略，请单击 "**新建**"，然后单击 "**网站策略**"。</span><span class="sxs-lookup"><span data-stu-id="1a0f9-127">To create a new site policy, click **New**, and then click **Site policy**.</span></span> <span data-ttu-id="1a0f9-128">在 "**选择网站**" 中，从列表中单击相应的网站，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="1a0f9-128">In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="1a0f9-129">若要创建新的用户策略，请单击 "**新建**"，然后单击 "**用户策略**"。</span><span class="sxs-lookup"><span data-stu-id="1a0f9-129">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="1a0f9-130">在 "**新的外部访问策略**" 中，在 "**名称**" 字段中创建一个唯一名称，用于指示用户策略所涉及的内容（例如， **EnableRemoteUsers**为远程用户启用通信的用户策略）。</span><span class="sxs-lookup"><span data-stu-id="1a0f9-130">In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableRemoteUsers** for a user policy that enables communications for remote users).</span></span>
    
      - <span data-ttu-id="1a0f9-131">若要更改现有策略，请单击表中列出的相应策略，单击 "**编辑**"，然后单击 "**显示详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="1a0f9-131">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="1a0f9-132">可选如果要添加或编辑说明，请在 "**说明**" 中指定策略的信息。</span><span class="sxs-lookup"><span data-stu-id="1a0f9-132">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="1a0f9-133">请执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="1a0f9-133">Do one of the following:</span></span>
    
      - <span data-ttu-id="1a0f9-134">若要启用该策略的远程用户访问权限，请选中 "**启用与远程用户的通信**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="1a0f9-134">To enable remote user access for the policy, select the **Enable communications with remote users** check box.</span></span>
    
      - <span data-ttu-id="1a0f9-135">若要禁用该策略的远程用户访问权限，请清除 "**启用与远程用户的通信**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="1a0f9-135">To disable remote user access for the policy, clear the **Enable communications with remote users** check box.</span></span>

7.  <span data-ttu-id="1a0f9-136">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="1a0f9-136">Click **Commit**.</span></span>

<span data-ttu-id="1a0f9-137">若要启用远程用户访问，还必须启用对组织中的远程用户访问的支持。</span><span class="sxs-lookup"><span data-stu-id="1a0f9-137">To enable remote user access, you must also enable support for remote user access in your organization.</span></span> <span data-ttu-id="1a0f9-138">有关详细信息，请参阅在部署文档或操作文档中[启用或禁用 Lync Server 2013 中的联盟和公共 IM 连接](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="1a0f9-138">For details, see [Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) in the Deployment documentation or the Operations documentation.</span></span>

<span data-ttu-id="1a0f9-139">如果这是用户策略，你还必须将策略应用于你希望能够远程连接的用户。</span><span class="sxs-lookup"><span data-stu-id="1a0f9-139">If this is a user policy, you must also apply the policy to users that you want to be able to connect remotely.</span></span> <span data-ttu-id="1a0f9-140">有关详细信息，请参阅在部署文档或操作文档中[将外部用户访问策略分配给 Lync Server 2013 中启用 Lync 的用户](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)。</span><span class="sxs-lookup"><span data-stu-id="1a0f9-140">For details, see [Assign an external user access policy to a Lync enabled user in Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md) in the Deployment documentation or the Operations documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

