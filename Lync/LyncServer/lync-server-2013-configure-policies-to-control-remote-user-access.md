---
title: Lync Server 2013：配置策略以控制远程用户访问
description: Lync Server 2013：配置策略以控制远程用户访问。
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
ms.openlocfilehash: 6408747cfbbc5e7dff8fd198c0de162f49fc5ff2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548708"
---
# <a name="configure-policies-to-control-remote-user-access-in-lync-server-2013"></a><span data-ttu-id="5e3b9-103">在 Lync Server 2013 中配置策略以控制远程用户访问</span><span class="sxs-lookup"><span data-stu-id="5e3b9-103">Configure policies to control remote user access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5e3b9-104">_**上次修改的主题：** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="5e3b9-104">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="5e3b9-105">您可以配置一个或多个外部用户访问策略以控制远程用户是否可以与内部 Lync Server 用户进行协作。</span><span class="sxs-lookup"><span data-stu-id="5e3b9-105">You configure one or more external user access policies to control whether remote users can collaborate with internal Lync Server users.</span></span> <span data-ttu-id="5e3b9-106">若要控制远程用户访问，可以在全局、站点和用户级别配置策略。</span><span class="sxs-lookup"><span data-stu-id="5e3b9-106">To control remote user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="5e3b9-107">站点策略将覆盖全局策略，而用户策略将覆盖站点策略和全局策略。</span><span class="sxs-lookup"><span data-stu-id="5e3b9-107">Site policies override the global policy, and user policies override site and global policies.</span></span> <span data-ttu-id="5e3b9-108">有关您可以配置的策略类型的详细信息，请参阅 [管理对 Lync Server 2013 的联盟和外部访问](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="5e3b9-108">For details about the types of policies that you can configure, see [Managing federation and external access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md).</span></span> <span data-ttu-id="5e3b9-109">在一个策略级别应用的 Lync Server 策略设置可以覆盖在另一个策略级别应用的设置。</span><span class="sxs-lookup"><span data-stu-id="5e3b9-109">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="5e3b9-110">Lync Server 策略优先级为：用户策略 (影响最大的) 替代网站策略，然后网站策略将覆盖全局策略 (最小影响) 。</span><span class="sxs-lookup"><span data-stu-id="5e3b9-110">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="5e3b9-111">这意味着，策略设置越接近策略影响的对象，它对对象的影响就越大。</span><span class="sxs-lookup"><span data-stu-id="5e3b9-111">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5e3b9-112">即使没有为组织启用远程用户访问，也可以配置策略来控制远程用户访问。</span><span class="sxs-lookup"><span data-stu-id="5e3b9-112">You can configure policies to control remote user access, even if you have not enabled remote user access for your organization.</span></span> <span data-ttu-id="5e3b9-113">但是，只有为组织启用远程用户访问后，配置的策略才会生效。</span><span class="sxs-lookup"><span data-stu-id="5e3b9-113">However, the policies that you configure are in effect only when you have remote user access enabled for your organization.</span></span> <span data-ttu-id="5e3b9-114">有关启用远程用户访问的详细信息，请参阅 <A href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">在 Lync Server 2013 中启用或禁用联盟和公共 IM 连接</A>。</span><span class="sxs-lookup"><span data-stu-id="5e3b9-114">For details about enabling remote user access, see <A href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</A>.</span></span> <span data-ttu-id="5e3b9-115">此外，如果您指定了用于控制远程用户访问的用户策略，则该策略仅适用于启用了 Lync Server 并配置为使用该策略的用户。</span><span class="sxs-lookup"><span data-stu-id="5e3b9-115">Additionally, if you specify a user policy to control remote user access, the policy applies only to users that are enabled for Lync Server and configured to use the policy.</span></span> <span data-ttu-id="5e3b9-116">有关指定可从远程位置登录 Lync Server 的用户的详细信息，请参阅 <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">在 Lync server 2013 中向启用 lync 的用户分配外部用户访问策略</A>。</span><span class="sxs-lookup"><span data-stu-id="5e3b9-116">For details about specifying users that can sign in to Lync Server from remote locations, see <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">Assign an external user access policy to a Lync enabled user in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="5e3b9-117">按照以下过程配置要用于控制远程用户访问的每个外部访问策略。</span><span class="sxs-lookup"><span data-stu-id="5e3b9-117">Use the following procedure to configure each external access policy that you want to use to control remote user access.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5e3b9-118">此过程描述如何配置策略以便仅启用与远程用户的通信，但配置为支持远程用户访问的每个策略也可以配置联盟用户访问和公共用户访问。</span><span class="sxs-lookup"><span data-stu-id="5e3b9-118">This procedure describes how to configure a policy only to enable communications with remote users, but each policy that you configure to support remote user access can also configure federated user access and public user access.</span></span> <span data-ttu-id="5e3b9-119">有关配置策略以支持联合用户的详细信息，请参阅 <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">在 Lync Server 2013 中配置用于控制联合用户访问的策略</A>。</span><span class="sxs-lookup"><span data-stu-id="5e3b9-119">For details about configuring policies to support federated users, see <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configure policies to control federated user access in Lync Server 2013</A>.</span></span> <span data-ttu-id="5e3b9-120">有关配置策略以支持公用用户的详细信息，请参阅 <A href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">在 Lync Server 2013 中创建或编辑公用 SIP 联合提供程序</A>。</span><span class="sxs-lookup"><span data-stu-id="5e3b9-120">For details about configuring policies to support public users, see <A href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Create or edit public SIP federated providers in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-configure-an-external-access-policy-to-support-remote-user-access"></a><span data-ttu-id="5e3b9-121">配置外部访问策略以支持远程用户访问</span><span class="sxs-lookup"><span data-stu-id="5e3b9-121">To configure an external access policy to support remote user access</span></span>

1.  <span data-ttu-id="5e3b9-122">从作为 RTCUniversalServerAdmins 组成员的用户帐户 (或具有等效的用户权限) 或分配给 CsAdministrator 角色，请登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="5e3b9-122">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5e3b9-123">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="5e3b9-123">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="5e3b9-124">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="5e3b9-124">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="5e3b9-125">在左侧导航栏中，单击“外部用户访问”\*\*\*\*，然后单击“外部访问策略”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5e3b9-125">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="5e3b9-126">在“外部访问策略”\*\*\*\* 页上，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="5e3b9-126">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="5e3b9-127">要将全局策略配置为支持远程用户访问，请单击该全局策略，再单击“编辑”\*\*\*\*，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5e3b9-127">To configure the global policy to support remote user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="5e3b9-p105">要创建新的站点策略，请单击“新建”\*\*\*\*，然后单击“站点策略”\*\*\*\*。在“选择站点”\*\*\*\* 中，单击列表中相应的站点，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5e3b9-p105">To create a new site policy, click **New**, and then click **Site policy**. In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="5e3b9-p106">要创建新的用户策略，请单击“新建”\*\*\*\*，然后单击“用户策略”\*\*\*\*。在“新建外部访问策略”\*\*\*\* 的“名称”\*\*\*\* 字段中，创建一个唯一的名称以指示用户策略的作用范围（例如，**EnableRemoteUsers** 代表启用远程用户通信的用户策略）。</span><span class="sxs-lookup"><span data-stu-id="5e3b9-p106">To create a new user policy, click **New**, and then click **User policy**. In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableRemoteUsers** for a user policy that enables communications for remote users).</span></span>
    
      - <span data-ttu-id="5e3b9-132">要更改现有的策略，请单击表中列出的相应策略，再单击“编辑”\*\*\*\*，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5e3b9-132">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="5e3b9-133">（可选）如果要添加或编辑说明，请在“说明”\*\*\*\* 中为策略指定相应的信息。</span><span class="sxs-lookup"><span data-stu-id="5e3b9-133">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="5e3b9-134">执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="5e3b9-134">Do one of the following:</span></span>
    
      - <span data-ttu-id="5e3b9-135">要为策略启用远程用户访问，请选中“启用与远程用户的通信”\*\*\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="5e3b9-135">To enable remote user access for the policy, select the **Enable communications with remote users** check box.</span></span>
    
      - <span data-ttu-id="5e3b9-136">要为策略禁用远程用户访问，请清除“启用与远程用户的通信”\*\*\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="5e3b9-136">To disable remote user access for the policy, clear the **Enable communications with remote users** check box.</span></span>

7.  <span data-ttu-id="5e3b9-137">单击“提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5e3b9-137">Click **Commit**.</span></span>

<span data-ttu-id="5e3b9-138">要启用远程用户访问，还必须在组织中启用对远程用户访问的支持。</span><span class="sxs-lookup"><span data-stu-id="5e3b9-138">To enable remote user access, you must also enable support for remote user access in your organization.</span></span> <span data-ttu-id="5e3b9-139">有关详细信息，请参阅部署文档或操作文档中的 [在 Lync Server 2013 中启用或禁用联盟和公共 IM 连接](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) 。</span><span class="sxs-lookup"><span data-stu-id="5e3b9-139">For details, see [Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) in the Deployment documentation or the Operations documentation.</span></span>

<span data-ttu-id="5e3b9-140">如果这是一个用户策略，则还必须将此策略应用于希望其可以进行远程连接的用户。</span><span class="sxs-lookup"><span data-stu-id="5e3b9-140">If this is a user policy, you must also apply the policy to users that you want to be able to connect remotely.</span></span> <span data-ttu-id="5e3b9-141">有关详细信息，请参阅部署文档或操作文档中的在 [Lync Server 2013 中将外部用户访问策略分配给启用 lync 的用户](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md) 。</span><span class="sxs-lookup"><span data-stu-id="5e3b9-141">For details, see [Assign an external user access policy to a Lync enabled user in Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md) in the Deployment documentation or the Operations documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

