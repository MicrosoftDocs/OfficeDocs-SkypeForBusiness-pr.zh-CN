---
title: 配置策略以控制公共用户访问
ms.reviewer: ''
ms:assetid: 090aea0f-ef0b-49da-9c80-02d9279f2fa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520946(v=OCS.15)
ms:contentKeyID: 48183343
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ublic 即时消息 (IM) 连接使组织中的用户能够使用 IM 与由公共 IM 服务提供商提供的 IM 服务的用户进行通信。
ms.openlocfilehash: 230c3405a9d0a551758bee63fae8f927fdc5af19
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280157"
---
# <a name="configure-policies-to-control-public-user-access-in-skype-for-business-server"></a><span data-ttu-id="5c293-103">在 Skype for Business Server 中配置用于控制公共用户访问的策略</span><span class="sxs-lookup"><span data-stu-id="5c293-103">Configure policies to control public user access in Skype for Business Server</span></span>

<span data-ttu-id="5c293-104">公共即时消息 (IM) 连接使组织中的用户能够使用 IM 与由公共 IM 服务提供商提供的 IM 服务的用户进行通信。</span><span class="sxs-lookup"><span data-stu-id="5c293-104">Public instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by public IM service providers.</span></span> <span data-ttu-id="5c293-105">配置一个或多个外部用户访问策略, 以控制公共用户是否可以与内部 Skype for Business 服务器用户进行协作。</span><span class="sxs-lookup"><span data-stu-id="5c293-105">You configure one or more external user access policies to control whether public users can collaborate with internal Skype for Business Server users.</span></span> <span data-ttu-id="5c293-106">公共即时消息连接是一种附加的功能, 可依赖于部署和用户的配置。</span><span class="sxs-lookup"><span data-stu-id="5c293-106">Public instant messaging connectivity is an added feature that relies on configuration of your deployment and users.</span></span> <span data-ttu-id="5c293-107">它还取决于在公共 IM 提供商处提供的服务。</span><span class="sxs-lookup"><span data-stu-id="5c293-107">It also depends on the provisioning of the service at the public IM provider.</span></span> 

<span data-ttu-id="5c293-108">若要控制公共用户访问, 可以在全局、网站和用户级别配置策略。</span><span class="sxs-lookup"><span data-stu-id="5c293-108">To control public user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="5c293-109">在一个策略级别应用的 Skype for business 服务器策略设置可以覆盖在其他策略级别应用的设置。</span><span class="sxs-lookup"><span data-stu-id="5c293-109">Skype for Business Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="5c293-110">Skype for Business 服务器策略优先级为: 用户策略 (最受影响) 覆盖网站策略, 然后网站策略覆盖全局策略 (最不影响)。</span><span class="sxs-lookup"><span data-stu-id="5c293-110">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="5c293-111">这意味着，策略设置与策略所影响的对象距离越近，它对该对象的影响力越大。</span><span class="sxs-lookup"><span data-stu-id="5c293-111">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>

<span data-ttu-id="5c293-112">对于 IM 邀请, 响应取决于客户端软件。</span><span class="sxs-lookup"><span data-stu-id="5c293-112">In the case of IM invitations, the response depends on the client software.</span></span> <span data-ttu-id="5c293-113">除非由用户配置的规则明确阻止外部发件人 (即用户的客户端**允许**和**阻止**名单中的设置), 否则将接受该请求。</span><span class="sxs-lookup"><span data-stu-id="5c293-113">The request is accepted unless external senders are explicitly blocked by a user-configured rule (that is, the settings in the user’s client **Allow** and **Block** lists).</span></span> <span data-ttu-id="5c293-114">此外, 如果用户将阻止来自不在其**允许**列表中的用户的所有 IM, 则可以阻止 IM 邀请。</span><span class="sxs-lookup"><span data-stu-id="5c293-114">Additionally, IM invitations can be blocked if a user elects to block all IM from users who are not on his or her **Allow** list.</span></span>



> [!NOTE]  
> <span data-ttu-id="5c293-115">你可以配置策略来控制公共用户访问, 即使你没有为组织启用联盟。</span><span class="sxs-lookup"><span data-stu-id="5c293-115">You can configure policies to control public user access, even if you have not enabled federation for your organization.</span></span> <span data-ttu-id="5c293-116">但是, 仅当你的组织启用了联合身份验证时, 你配置的策略才有效。</span><span class="sxs-lookup"><span data-stu-id="5c293-116">However, the policies that you configure are in effect only when you have federation enabled for your organization.</span></span> <span data-ttu-id="5c293-117">有关启用联盟的详细信息, 请参阅[启用或禁用远程用户访问](../access-edge/enable-or-disable-remote-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="5c293-117">For details about enabling federation, see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span> <span data-ttu-id="5c293-118">此外, 如果你指定用于控制公共用户访问的用户策略, 则该策略仅适用于已启用 Skype for business 服务器的用户, 并且配置为使用该策略。</span><span class="sxs-lookup"><span data-stu-id="5c293-118">Additionally, if you specify a user policy to control public user access, the policy applies only to users that are enabled for Skype for Business Server and configured to use the policy.</span></span> <span data-ttu-id="5c293-119">有关指定可登录到 Skype for Business 服务器的公共用户的详细信息, 请参阅[分配外部用户访问策略](assign-an-external-user-access-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="5c293-119">For details about specifying public users that can sign in to Skype for Business Server, see [Assign an external user access policy](assign-an-external-user-access-policy.md).</span></span>


<span data-ttu-id="5c293-120">使用以下过程配置策略以支持一个或多个公共 IM 提供商的用户访问。</span><span class="sxs-lookup"><span data-stu-id="5c293-120">Use the following procedure to configure a policy to support access by users of one or more public IM providers.</span></span>

## <a name="to-configure-an-external-access-policy-to-support-public-user-access"></a><span data-ttu-id="5c293-121">将外部访问策略配置为支持公共用户访问</span><span class="sxs-lookup"><span data-stu-id="5c293-121">To configure an external access policy to support public user access</span></span>

1.  <span data-ttu-id="5c293-122">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="5c293-122">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5c293-123">打开一个浏览器窗口, 然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="5c293-123">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="5c293-124">在左侧导航栏中, 单击 "**外部用户访问**", 然后单击 "**外部访问策略**"。</span><span class="sxs-lookup"><span data-stu-id="5c293-124">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="5c293-125">在 "**外部访问策略**" 页面上, 执行下列操作之一:</span><span class="sxs-lookup"><span data-stu-id="5c293-125">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="5c293-126">若要将全局策略配置为支持公共用户访问, 请单击全局策略, 单击 "**编辑**", 然后单击 "**显示详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="5c293-126">To configure the global policy to support public user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="5c293-127">若要创建新的网站策略, 请单击 "**新建**", 然后单击 "**网站策略**"。</span><span class="sxs-lookup"><span data-stu-id="5c293-127">To create a new site policy, click **New**, and then click **Site policy**.</span></span> <span data-ttu-id="5c293-128">在 "**选择网站**" 中, 从列表中单击相应的网站, 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="5c293-128">In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="5c293-129">若要创建新的用户策略, 请单击 "**新建**", 然后单击 "**用户策略**"。</span><span class="sxs-lookup"><span data-stu-id="5c293-129">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="5c293-130">在 "**新的外部访问策略**" 中, 在 "**名称**" 字段中创建一个唯一名称, 用于指示用户策略所涉及的内容 (例如, **EnablePublicUsers**为公共用户启用通信的用户策略)。</span><span class="sxs-lookup"><span data-stu-id="5c293-130">In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnablePublicUsers** for a user policy that enables communications for public users).</span></span>
    
      - <span data-ttu-id="5c293-131">若要更改现有策略, 请单击表中列出的相应策略, 单击 "**编辑**", 然后单击 "**显示详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="5c293-131">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="5c293-132">可选如果要添加或编辑说明, 请在 "**说明**" 中指定策略的信息。</span><span class="sxs-lookup"><span data-stu-id="5c293-132">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="5c293-133">请执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="5c293-133">Do one of the following:</span></span>
    
      - <span data-ttu-id="5c293-134">若要为策略启用公共用户访问权限, 请选中 "**启用与公共用户的通信**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="5c293-134">To enable public user access for the policy, select the **Enable communications with public users** check box.</span></span>
    
      - <span data-ttu-id="5c293-135">若要禁用该策略的公共用户访问权限, 请清除 "**启用与公共用户的通信**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="5c293-135">To disable public user access for the policy, clear the **Enable communications with public users** check box.</span></span>

7.  <span data-ttu-id="5c293-136">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="5c293-136">Click **Commit**.</span></span>

<span data-ttu-id="5c293-137">若要启用公共用户访问, 还必须在组织中启用联盟支持。</span><span class="sxs-lookup"><span data-stu-id="5c293-137">To enable public user access, you must also enable support for federation in your organization.</span></span> <span data-ttu-id="5c293-138">有关详细信息, 请参阅[在 Skype For Business 服务器中配置用于控制联盟用户访问的策略](configure-policies-to-control-federated-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="5c293-138">For details, see [Configure policies to control federated user access in Skype for Business Server](configure-policies-to-control-federated-user-access.md).</span></span>

<span data-ttu-id="5c293-139">如果这是用户策略, 你还必须将策略应用于你希望能够与公共用户协作的公共用户。</span><span class="sxs-lookup"><span data-stu-id="5c293-139">If this is a user policy, you must also apply the policy to public users that you want to be able to collaborate with public users.</span></span> 


## <a name="see-also"></a><span data-ttu-id="5c293-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5c293-140">See Also</span></span>

[<span data-ttu-id="5c293-141">管理组织的 SIP 联盟提供程序</span><span class="sxs-lookup"><span data-stu-id="5c293-141">Manage SIP federated providers for your organization</span></span>](../sip-providers/manage-sip-federated-providers-for-your-organization.md)
