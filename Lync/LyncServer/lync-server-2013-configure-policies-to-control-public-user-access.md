---
title: Lync Server 2013：配置策略以控制公共用户访问
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure policies to control public user access
ms:assetid: 090aea0f-ef0b-49da-9c80-02d9279f2fa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520946(v=OCS.15)
ms:contentKeyID: 48183343
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a967f186d924a199b007ceba8390bf968253ec72
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520409"
---
# <a name="configure-policies-to-control-public-user-access-in-lync-server-2013"></a><span data-ttu-id="64efb-102">配置策略以控制 Lync Server 2013 中的公共用户访问</span><span class="sxs-lookup"><span data-stu-id="64efb-102">Configure policies to control public user access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="64efb-103">_**上次修改的主题：** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="64efb-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="64efb-104">公共即时消息 (IM) 连接使组织中的用户能够使用 IM 与公共 IM 服务提供商（包括 Internet 服务、Yahoo 和 AOL 的 Windows Live 网络）提供的 IM 服务的用户进行通信 \! 。</span><span class="sxs-lookup"><span data-stu-id="64efb-104">Public instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by public IM service providers, including the Windows Live network of Internet services, Yahoo\!, and AOL.</span></span> <span data-ttu-id="64efb-105">您可以配置一个或多个外部用户访问策略，以控制公用用户是否可以与内部 Lync Server 用户进行协作。</span><span class="sxs-lookup"><span data-stu-id="64efb-105">You configure one or more external user access policies to control whether public users can collaborate with internal Lync Server users.</span></span> <span data-ttu-id="64efb-106">公共即时消息连接是一项附加功能，它依赖于部署和用户的配置。</span><span class="sxs-lookup"><span data-stu-id="64efb-106">Public instant messaging connectivity is an added feature that relies on configuration of your deployment and users.</span></span> <span data-ttu-id="64efb-107">它还取决于在公用 IM 提供商处设置服务。</span><span class="sxs-lookup"><span data-stu-id="64efb-107">It also depends on the provisioning of the service at the public IM provider.</span></span> <span data-ttu-id="64efb-108">有关如何设置部署以使用公共提供程序的信息，请参阅 "适用于 Microsoft Lync Server、Office 通信服务器和实时通信服务器的公共 IM 连接设置指南" 指南： [https://go.microsoft.com/fwlink/?LinkId=269821](https://go.microsoft.com/fwlink/?linkid=269821)</span><span class="sxs-lookup"><span data-stu-id="64efb-108">For information on how to provision your deployment to use the public providers, see the “Public IM Connectivity Provisioning Guide for Microsoft Lync Server, Office Communications Server, and Live Communications Server” guide: [https://go.microsoft.com/fwlink/?LinkId=269821](https://go.microsoft.com/fwlink/?linkid=269821)</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="64efb-109">从2012年9月1日起，Microsoft Lync 公共 IM 连接用户订阅许可证 ( "PIC USL" ) 不再可用于购买新的或更新的协议。</span><span class="sxs-lookup"><span data-stu-id="64efb-109">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="64efb-110">拥有主动许可证的客户将能够继续与 Yahoo！联合联合</span><span class="sxs-lookup"><span data-stu-id="64efb-110">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="64efb-111">信使，直到服务关闭日期。</span><span class="sxs-lookup"><span data-stu-id="64efb-111">Messenger until the service shut down date.</span></span> <span data-ttu-id="64efb-112">AOL 和 Yahoo！的生命周期结束日期为2014年6月</span><span class="sxs-lookup"><span data-stu-id="64efb-112">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="64efb-113">已宣布。</span><span class="sxs-lookup"><span data-stu-id="64efb-113">has been announced.</span></span> <span data-ttu-id="64efb-114">有关详细信息，请参阅 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的支持公用即时信使连接</A>。</span><span class="sxs-lookup"><span data-stu-id="64efb-114">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="64efb-115">PIC USL 是 Lync Server 或 Office 通信服务器与 Yahoo！联合所需的每个用户每月订阅许可证。</span><span class="sxs-lookup"><span data-stu-id="64efb-115">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="64efb-116">Messenger.</span><span class="sxs-lookup"><span data-stu-id="64efb-116">Messenger.</span></span> <span data-ttu-id="64efb-117">Microsoft 提供此服务的能力因 Yahoo！中的支持而受到了支持，其下凸的底层协议。</span><span class="sxs-lookup"><span data-stu-id="64efb-117">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="64efb-118">Lync 是前所未有的强大工具，用于跨组织和世界各地的个人进行连接。</span><span class="sxs-lookup"><span data-stu-id="64efb-118">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="64efb-119">与 Windows Live Messenger 的联盟不需要除 Lync Standard CAL 之外的其他用户/设备许可证。</span><span class="sxs-lookup"><span data-stu-id="64efb-119">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="64efb-120">Skype 联合身份验证将添加到此列表中，使 Lync 用户可以使用即时消息和语音访问成百上千人。</span><span class="sxs-lookup"><span data-stu-id="64efb-120">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="64efb-121">若要访问 Microsoft Lync Server 公共 IM 连接设置网站，请使用以下链接： [https://go.microsoft.com/fwlink/p/?linkId=212638](https://go.microsoft.com/fwlink/p/?linkid=212638)</span><span class="sxs-lookup"><span data-stu-id="64efb-121">To access the Microsoft Lync Server Public IM Connectivity Provisioning site, use the following link: [https://go.microsoft.com/fwlink/p/?linkId=212638](https://go.microsoft.com/fwlink/p/?linkid=212638)</span></span>

<span data-ttu-id="64efb-122">若要控制公共用户访问，可以在全局、站点和用户级别配置策略。</span><span class="sxs-lookup"><span data-stu-id="64efb-122">To control public user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="64efb-123">有关您可以配置的策略类型的详细信息，请参阅部署文档或规划文档中的在 [Lync Server 2013 中配置对外部用户访问的支持](lync-server-2013-configuring-support-for-external-user-access.md) 。</span><span class="sxs-lookup"><span data-stu-id="64efb-123">For details about the types of policies that you can configure, see [Configuring support for external user access in Lync Server 2013](lync-server-2013-configuring-support-for-external-user-access.md) in the Deployment documentation or the Planning documentation.</span></span> <span data-ttu-id="64efb-124">在一个策略级别应用的 Lync Server 策略设置可以覆盖在另一个策略级别应用的设置。</span><span class="sxs-lookup"><span data-stu-id="64efb-124">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="64efb-125">Lync Server 策略优先级为：用户策略 (影响最大的) 替代网站策略，然后网站策略将覆盖全局策略 (最小影响) 。</span><span class="sxs-lookup"><span data-stu-id="64efb-125">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="64efb-126">这意味着，策略设置越接近策略影响的对象，它对对象的影响就越大。</span><span class="sxs-lookup"><span data-stu-id="64efb-126">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>

<span data-ttu-id="64efb-p106">对于 IM 邀请，响应取决于客户端软件。除非外部发件人被用户配置的规则（即，用户客户端的“允许”\*\*\*\* 和“阻止”\*\*\*\* 列表中的设置）显式阻止，否则将接受请求。此外，如果用户选择阻止来自其“允许”\*\*\*\* 列表之外的用户的所有 IM，也可以阻止 IM 邀请。</span><span class="sxs-lookup"><span data-stu-id="64efb-p106">In the case of IM invitations, the response depends on the client software. The request is accepted unless external senders are explicitly blocked by a user-configured rule (that is, the settings in the user’s client **Allow** and **Block** lists). Additionally, IM invitations can be blocked if a user elects to block all IM from users who are not on his or her **Allow** list.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="64efb-130">即使没有为组织启用联盟，也可以配置控制公共用户访问的策略。</span><span class="sxs-lookup"><span data-stu-id="64efb-130">You can configure policies to control public user access, even if you have not enabled federation for your organization.</span></span> <span data-ttu-id="64efb-131">但是，只有为组织启用联盟后，配置的策略才会生效。</span><span class="sxs-lookup"><span data-stu-id="64efb-131">However, the policies that you configure are in effect only when you have federation enabled for your organization.</span></span> <span data-ttu-id="64efb-132">有关启用联合的详细信息，请参阅部署文档或操作文档中的在 <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Lync Server 2013 中启用或禁用远程用户访问</A> 。</span><span class="sxs-lookup"><span data-stu-id="64efb-132">For details about enabling federation, see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span> <span data-ttu-id="64efb-133">此外，如果您指定了用于控制公用用户访问的用户策略，则该策略仅适用于启用了 Lync Server 并配置为使用该策略的用户。</span><span class="sxs-lookup"><span data-stu-id="64efb-133">Additionally, if you specify a user policy to control public user access, the policy applies only to users that are enabled for Lync Server and configured to use the policy.</span></span> <span data-ttu-id="64efb-134">有关指定可登录到 Lync Server 的公共用户的详细信息，请参阅部署文档或操作文档中的在 <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">Lync server 2013 中将外部用户访问策略分配给启用 Lync 的用户</A> 。</span><span class="sxs-lookup"><span data-stu-id="64efb-134">For details about specifying public users that can sign in to Lync Server, see <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">Assign an external user access policy to a Lync enabled user in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span>



</div>

<span data-ttu-id="64efb-135">使用以下过程来配置策略，以支持一个或多个公共 IM 提供商的用户进行访问。</span><span class="sxs-lookup"><span data-stu-id="64efb-135">Use the following procedure to configure a policy to support access by users of one or more public IM providers.</span></span>

<div>

## <a name="to-configure-an-external-access-policy-to-support-public-user-access"></a><span data-ttu-id="64efb-136">配置外部访问策略以支持公共用户访问</span><span class="sxs-lookup"><span data-stu-id="64efb-136">To configure an external access policy to support public user access</span></span>

1.  <span data-ttu-id="64efb-137">从作为 RTCUniversalServerAdmins 组成员的用户帐户 (或具有等效的用户权限) 或分配给 CsAdministrator 角色，请登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="64efb-137">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="64efb-138">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="64efb-138">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="64efb-139">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="64efb-139">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="64efb-140">在左侧导航栏中，单击“外部用户访问”\*\*\*\*，然后单击“外部访问策略”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="64efb-140">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="64efb-141">在“外部访问策略”\*\*\*\* 页上，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="64efb-141">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="64efb-142">要将全局策略配置为支持公共用户访问，请单击该全局策略，再单击“编辑”\*\*\*\*，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="64efb-142">To configure the global policy to support public user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="64efb-p109">要创建新的站点策略，请单击“新建”\*\*\*\*，然后单击“站点策略”\*\*\*\*。在“选择站点”\*\*\*\* 中，单击列表中相应的站点，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="64efb-p109">To create a new site policy, click **New**, and then click **Site policy**. In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="64efb-p110">要创建新的用户策略，请单击“新建”\*\*\*\*，然后单击“用户策略”\*\*\*\*。在“新建外部访问策略”\*\*\*\* 的“名称”\*\*\*\* 字段中，创建一个唯一的名称以指示用户策略的作用范围（例如，**EnablePublicUsers** 代表启用公共用户通信的用户策略）。</span><span class="sxs-lookup"><span data-stu-id="64efb-p110">To create a new user policy, click **New**, and then click **User policy**. In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnablePublicUsers** for a user policy that enables communications for public users).</span></span>
    
      - <span data-ttu-id="64efb-147">要更改现有的策略，请单击表中列出的相应策略，再单击“编辑”\*\*\*\*，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="64efb-147">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="64efb-148">（可选）如果要添加或编辑说明，请在“说明”\*\*\*\* 中为策略指定相应的信息。</span><span class="sxs-lookup"><span data-stu-id="64efb-148">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="64efb-149">执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="64efb-149">Do one of the following:</span></span>
    
      - <span data-ttu-id="64efb-150">要为策略启用公共用户访问，请选中“启用与公共用户的通信”\*\*\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="64efb-150">To enable public user access for the policy, select the **Enable communications with public users** check box.</span></span>
    
      - <span data-ttu-id="64efb-151">要为策略禁用公共用户访问，请清除“启用与公共用户的通信”\*\*\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="64efb-151">To disable public user access for the policy, clear the **Enable communications with public users** check box.</span></span>

7.  <span data-ttu-id="64efb-152">单击“提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="64efb-152">Click **Commit**.</span></span>

<span data-ttu-id="64efb-153">要启用公共用户访问，还必须在组织中启用对联盟的支持。</span><span class="sxs-lookup"><span data-stu-id="64efb-153">To enable public user access, you must also enable support for federation in your organization.</span></span> <span data-ttu-id="64efb-154">有关详细信息，请参阅 [在 Lync Server 2013 中配置用于控制联盟用户访问的策略](lync-server-2013-configure-policies-to-control-federated-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="64efb-154">For details, see [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span></span>

<span data-ttu-id="64efb-155">如果这是一个用户策略，您还必须将该策略应用到您希望能与公共用户协作的公共用户。</span><span class="sxs-lookup"><span data-stu-id="64efb-155">If this is a user policy, you must also apply the policy to public users that you want to be able to collaborate with public users.</span></span> <span data-ttu-id="64efb-156">有关详细信息，请参阅 [在 Lync Server 2013 中分配每用户策略](lync-server-2013-assigning-per-user-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="64efb-156">For details, see [Assigning per-user policies in Lync Server 2013](lync-server-2013-assigning-per-user-policies.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="64efb-157">另请参阅</span><span class="sxs-lookup"><span data-stu-id="64efb-157">See Also</span></span>


[<span data-ttu-id="64efb-158">在 Lync Server 2013 中创建或编辑公共 SIP 联合提供程序</span><span class="sxs-lookup"><span data-stu-id="64efb-158">Create or edit public SIP federated providers in Lync Server 2013</span></span>](lync-server-2013-create-or-edit-public-sip-federated-providers.md)  


[<span data-ttu-id="64efb-159">在 Lync Server 2013 中管理组织的 SIP 联合提供程序</span><span class="sxs-lookup"><span data-stu-id="64efb-159">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

