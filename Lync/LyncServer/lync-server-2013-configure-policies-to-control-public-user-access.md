---
title: Lync Server 2013：配置策略以控制公共用户访问
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure policies to control public user access
ms:assetid: 090aea0f-ef0b-49da-9c80-02d9279f2fa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520946(v=OCS.15)
ms:contentKeyID: 48183343
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e259082aa73d4354e8e4aa93eb7a0cc8d7ed7a6e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837356"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-public-user-access-in-lync-server-2013"></a><span data-ttu-id="f2a81-102">在 Lync Server 2013 中配置策略以控制公共用户访问</span><span class="sxs-lookup"><span data-stu-id="f2a81-102">Configure policies to control public user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f2a81-103">_**主题上次修改时间:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="f2a81-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="f2a81-104">公共即时消息 (IM) 连接使组织中的用户能够使用 IM 与由公共 IM 服务提供商提供的 IM 服务的用户进行通信, 包括 Internet 服务、Yahoo\!和 AOL 的 Windows Live 网络。</span><span class="sxs-lookup"><span data-stu-id="f2a81-104">Public instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by public IM service providers, including the Windows Live network of Internet services, Yahoo\!, and AOL.</span></span> <span data-ttu-id="f2a81-105">配置一个或多个外部用户访问策略, 以控制公共用户是否可以与内部 Lync Server 用户进行协作。</span><span class="sxs-lookup"><span data-stu-id="f2a81-105">You configure one or more external user access policies to control whether public users can collaborate with internal Lync Server users.</span></span> <span data-ttu-id="f2a81-106">公共即时消息连接是一种附加的功能, 可依赖于部署和用户的配置。</span><span class="sxs-lookup"><span data-stu-id="f2a81-106">Public instant messaging connectivity is an added feature that relies on configuration of your deployment and users.</span></span> <span data-ttu-id="f2a81-107">它还取决于在公共 IM 提供商处提供的服务。</span><span class="sxs-lookup"><span data-stu-id="f2a81-107">It also depends on the provisioning of the service at the public IM provider.</span></span> <span data-ttu-id="f2a81-108">有关如何设置你的部署以使用公共提供程序的信息, 请参阅 Microsoft Lync Server、Office 通信服务器和实时通信服务器的公共 IM 连接预配指南:[http://go.microsoft.com/fwlink/?LinkId=269821](http://go.microsoft.com/fwlink/?linkid=269821)</span><span class="sxs-lookup"><span data-stu-id="f2a81-108">For information on how to provision your deployment to use the public providers, see the “Public IM Connectivity Provisioning Guide for Microsoft Lync Server, Office Communications Server, and Live Communications Server” guide: [http://go.microsoft.com/fwlink/?LinkId=269821](http://go.microsoft.com/fwlink/?linkid=269821)</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="f2a81-109">从2012年9月1日起, Microsoft Lync 公共 IM 连接用户订阅许可证 ("PIC USL") 不再可用于购买新的或续订协议。</span><span class="sxs-lookup"><span data-stu-id="f2a81-109">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="f2a81-110">具有活动许可证的客户将能够继续与 Yahoo! 进行联盟</span><span class="sxs-lookup"><span data-stu-id="f2a81-110">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="f2a81-111">Messenger, 直到服务关闭日期。</span><span class="sxs-lookup"><span data-stu-id="f2a81-111">Messenger until the service shut down date.</span></span> <span data-ttu-id="f2a81-112">AOL 和 Yahoo! 的有效期结束日期为2014年6月</span><span class="sxs-lookup"><span data-stu-id="f2a81-112">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="f2a81-113">已宣布。</span><span class="sxs-lookup"><span data-stu-id="f2a81-113">has been announced.</span></span> <span data-ttu-id="f2a81-114">有关详细信息, 请参阅<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公共即时消息连接支持</A>。</span><span class="sxs-lookup"><span data-stu-id="f2a81-114">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="f2a81-115">PIC USL 是 Lync Server 或 Office 通信服务器与 Yahoo! 联合所需的每个每个用户每月订阅许可证。</span><span class="sxs-lookup"><span data-stu-id="f2a81-115">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="f2a81-116">Messenger.</span><span class="sxs-lookup"><span data-stu-id="f2a81-116">Messenger.</span></span> <span data-ttu-id="f2a81-117">Microsoft 提供此服务的能力已作为对 Yahoo! 的支持, 它的底层协议被向下缠绕。</span><span class="sxs-lookup"><span data-stu-id="f2a81-117">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="f2a81-118">Lync 比以往更多, 是一种强大的工具, 用于跨组织和全球各地的人员进行连接。</span><span class="sxs-lookup"><span data-stu-id="f2a81-118">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="f2a81-119">与 Windows Live Messenger 的联盟不需要除 Lync 标准 CAL 之外的其他用户/设备许可证。</span><span class="sxs-lookup"><span data-stu-id="f2a81-119">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="f2a81-120">Skype 联盟将添加到此列表, 使 Lync 用户可以通过 IM 和语音与成百上千人联系。</span><span class="sxs-lookup"><span data-stu-id="f2a81-120">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="f2a81-121">若要访问 Microsoft Lync Server 公共 IM 连接设置网站, 请使用以下链接:[http://go.microsoft.com/fwlink/p/?linkId=212638](http://go.microsoft.com/fwlink/p/?linkid=212638)</span><span class="sxs-lookup"><span data-stu-id="f2a81-121">To access the Microsoft Lync Server Public IM Connectivity Provisioning site, use the following link: [http://go.microsoft.com/fwlink/p/?linkId=212638](http://go.microsoft.com/fwlink/p/?linkid=212638)</span></span>

<span data-ttu-id="f2a81-122">若要控制公共用户访问, 可以在全局、网站和用户级别配置策略。</span><span class="sxs-lookup"><span data-stu-id="f2a81-122">To control public user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="f2a81-123">有关可以配置的策略类型的详细信息, 请参阅在部署文档或规划文档中[配置 Lync Server 2013 中的外部用户访问支持](lync-server-2013-configuring-support-for-external-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="f2a81-123">For details about the types of policies that you can configure, see [Configuring support for external user access in Lync Server 2013](lync-server-2013-configuring-support-for-external-user-access.md) in the Deployment documentation or the Planning documentation.</span></span> <span data-ttu-id="f2a81-124">在一个策略级别应用的 Lync Server 策略设置可以覆盖在其他策略级别应用的设置。</span><span class="sxs-lookup"><span data-stu-id="f2a81-124">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="f2a81-125">Lync 服务器策略优先级为: 用户策略 (最受影响) 覆盖网站策略, 然后网站策略覆盖全局策略 (最不影响)。</span><span class="sxs-lookup"><span data-stu-id="f2a81-125">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="f2a81-126">这意味着，策略设置与策略所影响的对象距离越近，它对该对象的影响力越大。</span><span class="sxs-lookup"><span data-stu-id="f2a81-126">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>

<span data-ttu-id="f2a81-127">对于 IM 邀请, 响应取决于客户端软件。</span><span class="sxs-lookup"><span data-stu-id="f2a81-127">In the case of IM invitations, the response depends on the client software.</span></span> <span data-ttu-id="f2a81-128">除非由用户配置的规则明确阻止外部发件人 (即用户的客户端**允许**和**阻止**名单中的设置), 否则将接受该请求。</span><span class="sxs-lookup"><span data-stu-id="f2a81-128">The request is accepted unless external senders are explicitly blocked by a user-configured rule (that is, the settings in the user’s client **Allow** and **Block** lists).</span></span> <span data-ttu-id="f2a81-129">此外, 如果用户将阻止来自不在其**允许**列表中的用户的所有 IM, 则可以阻止 IM 邀请。</span><span class="sxs-lookup"><span data-stu-id="f2a81-129">Additionally, IM invitations can be blocked if a user elects to block all IM from users who are not on his or her **Allow** list.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f2a81-130">你可以配置策略来控制公共用户访问, 即使你没有为组织启用联盟。</span><span class="sxs-lookup"><span data-stu-id="f2a81-130">You can configure policies to control public user access, even if you have not enabled federation for your organization.</span></span> <span data-ttu-id="f2a81-131">但是, 仅当你的组织启用了联合身份验证时, 你配置的策略才有效。</span><span class="sxs-lookup"><span data-stu-id="f2a81-131">However, the policies that you configure are in effect only when you have federation enabled for your organization.</span></span> <span data-ttu-id="f2a81-132">有关启用联盟的详细信息, 请参阅在部署文档或操作文档中<A href="lync-server-2013-enable-or-disable-remote-user-access.md">启用或禁用 Lync Server 2013 中的远程用户访问</A>。</span><span class="sxs-lookup"><span data-stu-id="f2a81-132">For details about enabling federation, see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span> <span data-ttu-id="f2a81-133">此外, 如果你指定用于控制公共用户访问的用户策略, 该策略将仅应用于已启用 Lync Server 且配置为使用该策略的用户。</span><span class="sxs-lookup"><span data-stu-id="f2a81-133">Additionally, if you specify a user policy to control public user access, the policy applies only to users that are enabled for Lync Server and configured to use the policy.</span></span> <span data-ttu-id="f2a81-134">有关指定可登录 Lync Server 的公共用户的详细信息, 请参阅部署文档或操作文档中的<A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">Lync server 2013 中的 "将外部用户访问策略分配给启用 lync 的用户</A>"。</span><span class="sxs-lookup"><span data-stu-id="f2a81-134">For details about specifying public users that can sign in to Lync Server, see <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">Assign an external user access policy to a Lync enabled user in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span>



</div>

<span data-ttu-id="f2a81-135">使用以下过程配置策略以支持一个或多个公共 IM 提供商的用户访问。</span><span class="sxs-lookup"><span data-stu-id="f2a81-135">Use the following procedure to configure a policy to support access by users of one or more public IM providers.</span></span>

<div>

## <a name="to-configure-an-external-access-policy-to-support-public-user-access"></a><span data-ttu-id="f2a81-136">将外部访问策略配置为支持公共用户访问</span><span class="sxs-lookup"><span data-stu-id="f2a81-136">To configure an external access policy to support public user access</span></span>

1.  <span data-ttu-id="f2a81-137">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="f2a81-137">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f2a81-138">打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="f2a81-138">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f2a81-139">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="f2a81-139">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f2a81-140">在左侧导航栏中, 单击 "**外部用户访问**", 然后单击 "**外部访问策略**"。</span><span class="sxs-lookup"><span data-stu-id="f2a81-140">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="f2a81-141">在 "**外部访问策略**" 页面上, 执行下列操作之一:</span><span class="sxs-lookup"><span data-stu-id="f2a81-141">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="f2a81-142">若要将全局策略配置为支持公共用户访问, 请单击全局策略, 单击 "**编辑**", 然后单击 "**显示详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="f2a81-142">To configure the global policy to support public user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="f2a81-143">若要创建新的网站策略, 请单击 "**新建**", 然后单击 "**网站策略**"。</span><span class="sxs-lookup"><span data-stu-id="f2a81-143">To create a new site policy, click **New**, and then click **Site policy**.</span></span> <span data-ttu-id="f2a81-144">在 "**选择网站**" 中, 从列表中单击相应的网站, 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="f2a81-144">In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="f2a81-145">若要创建新的用户策略, 请单击 "**新建**", 然后单击 "**用户策略**"。</span><span class="sxs-lookup"><span data-stu-id="f2a81-145">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="f2a81-146">在 "**新的外部访问策略**" 中, 在 "**名称**" 字段中创建一个唯一名称, 用于指示用户策略所涉及的内容 (例如, **EnablePublicUsers**为公共用户启用通信的用户策略)。</span><span class="sxs-lookup"><span data-stu-id="f2a81-146">In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnablePublicUsers** for a user policy that enables communications for public users).</span></span>
    
      - <span data-ttu-id="f2a81-147">若要更改现有策略, 请单击表中列出的相应策略, 单击 "**编辑**", 然后单击 "**显示详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="f2a81-147">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="f2a81-148">可选如果要添加或编辑说明, 请在 "**说明**" 中指定策略的信息。</span><span class="sxs-lookup"><span data-stu-id="f2a81-148">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="f2a81-149">请执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="f2a81-149">Do one of the following:</span></span>
    
      - <span data-ttu-id="f2a81-150">若要为策略启用公共用户访问权限, 请选中 "**启用与公共用户的通信**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="f2a81-150">To enable public user access for the policy, select the **Enable communications with public users** check box.</span></span>
    
      - <span data-ttu-id="f2a81-151">若要禁用该策略的公共用户访问权限, 请清除 "**启用与公共用户的通信**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="f2a81-151">To disable public user access for the policy, clear the **Enable communications with public users** check box.</span></span>

7.  <span data-ttu-id="f2a81-152">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="f2a81-152">Click **Commit**.</span></span>

<span data-ttu-id="f2a81-153">若要启用公共用户访问, 还必须在组织中启用联盟支持。</span><span class="sxs-lookup"><span data-stu-id="f2a81-153">To enable public user access, you must also enable support for federation in your organization.</span></span> <span data-ttu-id="f2a81-154">有关详细信息, 请参阅[在 Lync Server 2013 中配置用于控制联盟用户访问的策略](lync-server-2013-configure-policies-to-control-federated-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="f2a81-154">For details, see [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span></span>

<span data-ttu-id="f2a81-155">如果这是用户策略, 你还必须将策略应用于你希望能够与公共用户协作的公共用户。</span><span class="sxs-lookup"><span data-stu-id="f2a81-155">If this is a user policy, you must also apply the policy to public users that you want to be able to collaborate with public users.</span></span> <span data-ttu-id="f2a81-156">有关详细信息, 请参阅[在 Lync Server 2013 中分配每个用户的策略](lync-server-2013-assigning-per-user-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="f2a81-156">For details, see [Assigning per-user policies in Lync Server 2013](lync-server-2013-assigning-per-user-policies.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f2a81-157">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f2a81-157">See Also</span></span>


[<span data-ttu-id="f2a81-158">在 Lync Server 2013 中创建或编辑公共 SIP 联盟提供程序</span><span class="sxs-lookup"><span data-stu-id="f2a81-158">Create or edit public SIP federated providers in Lync Server 2013</span></span>](lync-server-2013-create-or-edit-public-sip-federated-providers.md)  


[<span data-ttu-id="f2a81-159">在 Lync Server 2013 中管理组织的 SIP 联盟提供程序</span><span class="sxs-lookup"><span data-stu-id="f2a81-159">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

