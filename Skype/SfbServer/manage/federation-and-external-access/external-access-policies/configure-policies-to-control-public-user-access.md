---
title: 配置策略以控制公共用户访问
ms.reviewer: ''
ms:assetid: 090aea0f-ef0b-49da-9c80-02d9279f2fa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520946(v=OCS.15)
ms:contentKeyID: 48183343
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 通过即时消息 (IM) 连接，您的组织中的用户可以使用 IM 与公共 IM 服务提供商提供的 IM 服务的用户进行通信。
ms.openlocfilehash: 28bb1c94cb42068fe99f07a6608a3ac1c50991ad
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823584"
---
# <a name="configure-policies-to-control-public-user-access-in-skype-for-business-server"></a><span data-ttu-id="4443c-103">配置策略以控制 Skype for Business Server 中的公共用户访问</span><span class="sxs-lookup"><span data-stu-id="4443c-103">Configure policies to control public user access in Skype for Business Server</span></span>

<span data-ttu-id="4443c-104">公共即时消息 (IM) 连接使组织用户可以使用 IM 与公共 IM 服务提供商提供的 IM 服务的用户进行通信。</span><span class="sxs-lookup"><span data-stu-id="4443c-104">Public instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by public IM service providers.</span></span> <span data-ttu-id="4443c-105">配置一个或多个外部用户访问策略，以控制公共用户是否可以与内部 Skype for Business Server 用户进行协作。</span><span class="sxs-lookup"><span data-stu-id="4443c-105">You configure one or more external user access policies to control whether public users can collaborate with internal Skype for Business Server users.</span></span> <span data-ttu-id="4443c-106">公共即时消息连接是一项附加功能，它依赖于部署和用户的配置。</span><span class="sxs-lookup"><span data-stu-id="4443c-106">Public instant messaging connectivity is an added feature that relies on configuration of your deployment and users.</span></span> <span data-ttu-id="4443c-107">它还取决于在公共 IM 提供商处设置服务。</span><span class="sxs-lookup"><span data-stu-id="4443c-107">It also depends on the provisioning of the service at the public IM provider.</span></span> 

<span data-ttu-id="4443c-108">若要控制公共用户访问，可以在全局、站点和用户级别配置策略。</span><span class="sxs-lookup"><span data-stu-id="4443c-108">To control public user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="4443c-109">在一个策略级别应用的 Skype for Business Server 策略设置可以覆盖在另一个策略级别应用的设置。</span><span class="sxs-lookup"><span data-stu-id="4443c-109">Skype for Business Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="4443c-110">Skype for Business 服务器策略优先级是：用户策略（最大影响力）覆盖站点策略，然后站点策略覆盖全局策略（最小影响）。</span><span class="sxs-lookup"><span data-stu-id="4443c-110">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="4443c-111">这意味着，策略设置越接近策略影响的对象，它对对象的影响就越大。</span><span class="sxs-lookup"><span data-stu-id="4443c-111">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>

<span data-ttu-id="4443c-p103">对于 IM 邀请，响应取决于客户端软件。除非外部发件人被用户配置的规则（即，用户客户端的“允许”和“阻止”列表中的设置）显式阻止，否则将接受请求。此外，如果用户选择阻止来自其“允许”列表之外的用户的所有 IM，也可以阻止 IM 邀请。</span><span class="sxs-lookup"><span data-stu-id="4443c-p103">In the case of IM invitations, the response depends on the client software. The request is accepted unless external senders are explicitly blocked by a user-configured rule (that is, the settings in the user’s client **Allow** and **Block** lists). Additionally, IM invitations can be blocked if a user elects to block all IM from users who are not on his or her **Allow** list.</span></span>



> [!NOTE]  
> <span data-ttu-id="4443c-115">即使没有为组织启用联盟，也可以配置控制公共用户访问的策略。</span><span class="sxs-lookup"><span data-stu-id="4443c-115">You can configure policies to control public user access, even if you have not enabled federation for your organization.</span></span> <span data-ttu-id="4443c-116">但是，只有为组织启用联盟后，配置的策略才会生效。</span><span class="sxs-lookup"><span data-stu-id="4443c-116">However, the policies that you configure are in effect only when you have federation enabled for your organization.</span></span> <span data-ttu-id="4443c-117">有关启用联盟的详细信息，请参阅["启用或禁用远程用户访问"。](../access-edge/enable-or-disable-remote-user-access.md)</span><span class="sxs-lookup"><span data-stu-id="4443c-117">For details about enabling federation, see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span> <span data-ttu-id="4443c-118">此外，如果指定用户策略来控制公共用户访问，则此策略仅适用于已启用 Skype for Business Server 且配置为使用该策略的用户。</span><span class="sxs-lookup"><span data-stu-id="4443c-118">Additionally, if you specify a user policy to control public user access, the policy applies only to users that are enabled for Skype for Business Server and configured to use the policy.</span></span> <span data-ttu-id="4443c-119">有关指定可登录到 Skype for Business Server 的公共用户的详细信息，请参阅"[分配外部用户访问策略"。](assign-an-external-user-access-policy.md)</span><span class="sxs-lookup"><span data-stu-id="4443c-119">For details about specifying public users that can sign in to Skype for Business Server, see [Assign an external user access policy](assign-an-external-user-access-policy.md).</span></span>


<span data-ttu-id="4443c-120">使用以下过程来配置策略，以支持一个或多个公共 IM 提供商的用户进行访问。</span><span class="sxs-lookup"><span data-stu-id="4443c-120">Use the following procedure to configure a policy to support access by users of one or more public IM providers.</span></span>

## <a name="to-configure-an-external-access-policy-to-support-public-user-access"></a><span data-ttu-id="4443c-121">配置外部访问策略以支持公共用户访问</span><span class="sxs-lookup"><span data-stu-id="4443c-121">To configure an external access policy to support public user access</span></span>

1.  <span data-ttu-id="4443c-122">从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或已分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。</span><span class="sxs-lookup"><span data-stu-id="4443c-122">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4443c-123">打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="4443c-123">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="4443c-124">在左侧导航栏中，单击“外部用户访问”，然后单击“外部访问策略”。</span><span class="sxs-lookup"><span data-stu-id="4443c-124">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="4443c-125">在“外部访问策略”页上，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="4443c-125">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="4443c-126">要将全局策略配置为支持公共用户访问，请单击该全局策略，再单击“编辑”，然后单击“显示详细信息”。</span><span class="sxs-lookup"><span data-stu-id="4443c-126">To configure the global policy to support public user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="4443c-p105">要创建新的站点策略，请单击“新建”，然后单击“站点策略”。在“选择站点”中，单击列表中相应的站点，然后单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="4443c-p105">To create a new site policy, click **New**, and then click **Site policy**. In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="4443c-p106">要创建新的用户策略，请单击“新建”，然后单击“用户策略”。在“新建外部访问策略”的“名称”字段中，创建一个唯一的名称以指示用户策略的作用范围（例如，**EnablePublicUsers** 代表启用公共用户通信的用户策略）。</span><span class="sxs-lookup"><span data-stu-id="4443c-p106">To create a new user policy, click **New**, and then click **User policy**. In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnablePublicUsers** for a user policy that enables communications for public users).</span></span>
    
      - <span data-ttu-id="4443c-131">要更改现有的策略，请单击表中列出的相应策略，再单击“编辑”，然后单击“显示详细信息”。</span><span class="sxs-lookup"><span data-stu-id="4443c-131">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="4443c-132">（可选）如果要添加或编辑说明，请在“说明”中为策略指定相应的信息。</span><span class="sxs-lookup"><span data-stu-id="4443c-132">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="4443c-133">执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="4443c-133">Do one of the following:</span></span>
    
      - <span data-ttu-id="4443c-134">要为策略启用公共用户访问，请选中“启用与公共用户的通信”复选框。</span><span class="sxs-lookup"><span data-stu-id="4443c-134">To enable public user access for the policy, select the **Enable communications with public users** check box.</span></span>
    
      - <span data-ttu-id="4443c-135">要为策略禁用公共用户访问，请清除“启用与公共用户的通信”复选框。</span><span class="sxs-lookup"><span data-stu-id="4443c-135">To disable public user access for the policy, clear the **Enable communications with public users** check box.</span></span>

7.  <span data-ttu-id="4443c-136">单击“提交”。</span><span class="sxs-lookup"><span data-stu-id="4443c-136">Click **Commit**.</span></span>

<span data-ttu-id="4443c-137">要启用公共用户访问，还必须在组织中启用对联盟的支持。</span><span class="sxs-lookup"><span data-stu-id="4443c-137">To enable public user access, you must also enable support for federation in your organization.</span></span> <span data-ttu-id="4443c-138">有关详细信息，请参阅 [配置策略以控制 Skype for Business Server 中的联盟用户访问](configure-policies-to-control-federated-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="4443c-138">For details, see [Configure policies to control federated user access in Skype for Business Server](configure-policies-to-control-federated-user-access.md).</span></span>

<span data-ttu-id="4443c-139">如果这是一个用户策略，您还必须将该策略应用到您希望能与公共用户协作的公共用户。</span><span class="sxs-lookup"><span data-stu-id="4443c-139">If this is a user policy, you must also apply the policy to public users that you want to be able to collaborate with public users.</span></span> 


## <a name="see-also"></a><span data-ttu-id="4443c-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4443c-140">See Also</span></span>

[<span data-ttu-id="4443c-141">管理组织的 SIP 联盟提供程序</span><span class="sxs-lookup"><span data-stu-id="4443c-141">Manage SIP federated providers for your organization</span></span>](../sip-providers/manage-sip-federated-providers-for-your-organization.md)
