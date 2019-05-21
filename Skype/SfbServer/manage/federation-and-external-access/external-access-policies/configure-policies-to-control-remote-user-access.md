---
title: 配置策略以控制远程用户访问
ms.reviewer: ''
ms:assetid: 8f556849-692b-44a0-9514-4468fc9a39d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398725(v=OCS.15)
ms:contentKeyID: 48184825
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 配置一个或多个外部用户访问策略, 以控制远程用户是否可以与内部 Skype for Business 服务器用户进行协作。 若要控制远程用户访问, 可以在全局、网站和用户级别配置策略。
ms.openlocfilehash: 96d91179e7b99910182ff360920f3d46b80aa6f4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280136"
---
# <a name="configure-policies-to-control-remote-user-access-in-skype-for-business-server"></a><span data-ttu-id="9cc57-104">在 Skype for Business Server 中配置用于控制远程用户访问的策略</span><span class="sxs-lookup"><span data-stu-id="9cc57-104">Configure policies to control remote user access in Skype for Business Server</span></span>

<span data-ttu-id="9cc57-105">配置一个或多个外部用户访问策略, 以控制远程用户是否可以与内部 Skype for Business 服务器用户进行协作。</span><span class="sxs-lookup"><span data-stu-id="9cc57-105">You configure one or more external user access policies to control whether remote users can collaborate with internal Skype for Business Server users.</span></span> <span data-ttu-id="9cc57-106">若要控制远程用户访问, 可以在全局、网站和用户级别配置策略。</span><span class="sxs-lookup"><span data-stu-id="9cc57-106">To control remote user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="9cc57-107">网站策略替代全局策略, 而用户策略替代网站和全局策略。</span><span class="sxs-lookup"><span data-stu-id="9cc57-107">Site policies override the global policy, and user policies override site and global policies.</span></span> <span data-ttu-id="9cc57-108">有关可以配置的策略类型的详细信息, 请参阅[管理对 Skype for Business 服务器的联盟和外部访问](../managing-federation-and-external-access.md)。</span><span class="sxs-lookup"><span data-stu-id="9cc57-108">For details about the types of policies that you can configure, see [Managing federation and external access to Skype for Business Server](../managing-federation-and-external-access.md).</span></span> <span data-ttu-id="9cc57-109">在一个策略级别应用的 Skype for business 服务器策略设置可以覆盖在其他策略级别应用的设置。</span><span class="sxs-lookup"><span data-stu-id="9cc57-109">Skype for Business Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="9cc57-110">Skype for Business 服务器策略优先级为: 用户策略 (最受影响) 覆盖网站策略, 然后网站策略覆盖全局策略 (最不影响)。</span><span class="sxs-lookup"><span data-stu-id="9cc57-110">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="9cc57-111">这意味着，策略设置与策略所影响的对象距离越近，它对该对象的影响力越大。</span><span class="sxs-lookup"><span data-stu-id="9cc57-111">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>

> [!NOTE]  
> <span data-ttu-id="9cc57-112">你可以配置策略来控制远程用户访问, 即使你没有为你的组织启用远程用户访问。</span><span class="sxs-lookup"><span data-stu-id="9cc57-112">You can configure policies to control remote user access, even if you have not enabled remote user access for your organization.</span></span> <span data-ttu-id="9cc57-113">但是, 仅当你的组织启用了远程用户访问时, 你配置的策略才有效。</span><span class="sxs-lookup"><span data-stu-id="9cc57-113">However, the policies that you configure are in effect only when you have remote user access enabled for your organization.</span></span> <span data-ttu-id="9cc57-114">此外, 如果你指定了用于控制远程用户访问的用户策略, 该策略将仅应用于已启用 Skype for business 服务器的用户, 并且配置为使用该策略。</span><span class="sxs-lookup"><span data-stu-id="9cc57-114">Additionally, if you specify a user policy to control remote user access, the policy applies only to users that are enabled for Skype for Business Server and configured to use the policy.</span></span> <span data-ttu-id="9cc57-115">有关从远程位置指定可登录 Skype for business 服务器的用户的详细信息, 请参阅[分配外部用户访问策略](assign-an-external-user-access-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="9cc57-115">For details about specifying users that can sign in to Skype for Business Server from remote locations, see [Assign an external user access policy](assign-an-external-user-access-policy.md).</span></span>

<span data-ttu-id="9cc57-116">使用以下过程配置要用于控制远程用户访问的每个外部访问策略。</span><span class="sxs-lookup"><span data-stu-id="9cc57-116">Use the following procedure to configure each external access policy that you want to use to control remote user access.</span></span>


> [!NOTE]  
> <span data-ttu-id="9cc57-117">此过程介绍如何配置策略以启用与远程用户的通信, 但配置为支持远程用户访问的每个策略也可以配置联合用户访问和公共用户访问。</span><span class="sxs-lookup"><span data-stu-id="9cc57-117">This procedure describes how to configure a policy only to enable communications with remote users, but each policy that you configure to support remote user access can also configure federated user access and public user access.</span></span> <span data-ttu-id="9cc57-118">有关配置支持联盟用户的策略的详细信息, 请参阅[在 Skype For Business 服务器中配置用于控制联盟用户访问的策略](configure-policies-to-control-federated-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="9cc57-118">For details about configuring policies to support federated users, see [Configure policies to control federated user access in Skype for Business Server](configure-policies-to-control-federated-user-access.md).</span></span> <span data-ttu-id="9cc57-119">有关配置策略以支持公共用户的详细信息, 请参阅[在 Skype For Business 服务器中管理组织的 SIP 联合提供商](../sip-providers/manage-sip-federated-providers-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="9cc57-119">For details about configuring policies to support public users, see [Manage SIP federated providers for your organization in Skype for Business Server](../sip-providers/manage-sip-federated-providers-for-your-organization.md).</span></span>


## <a name="to-configure-an-external-access-policy-to-support-remote-user-access"></a><span data-ttu-id="9cc57-120">将外部访问策略配置为支持远程用户访问</span><span class="sxs-lookup"><span data-stu-id="9cc57-120">To configure an external access policy to support remote user access</span></span>

1.  <span data-ttu-id="9cc57-121">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="9cc57-121">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9cc57-122">打开一个浏览器窗口, 然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="9cc57-122">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="9cc57-123">在左侧导航栏中, 单击 "**外部用户访问**", 然后单击 "**外部访问策略**"。</span><span class="sxs-lookup"><span data-stu-id="9cc57-123">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="9cc57-124">在 "**外部访问策略**" 页面上, 执行下列操作之一:</span><span class="sxs-lookup"><span data-stu-id="9cc57-124">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="9cc57-125">若要将全局策略配置为支持远程用户访问, 请单击全局策略, 单击 "**编辑**", 然后单击 "**显示详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="9cc57-125">To configure the global policy to support remote user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="9cc57-126">若要创建新的网站策略, 请单击 "**新建**", 然后单击 "**网站策略**"。</span><span class="sxs-lookup"><span data-stu-id="9cc57-126">To create a new site policy, click **New**, and then click **Site policy**.</span></span> <span data-ttu-id="9cc57-127">在 "**选择网站**" 中, 从列表中单击相应的网站, 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="9cc57-127">In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="9cc57-128">若要创建新的用户策略, 请单击 "**新建**", 然后单击 "**用户策略**"。</span><span class="sxs-lookup"><span data-stu-id="9cc57-128">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="9cc57-129">在 "**新的外部访问策略**" 中, 在 "**名称**" 字段中创建一个唯一名称, 用于指示用户策略所涉及的内容 (例如, **EnableRemoteUsers**为远程用户启用通信的用户策略)。</span><span class="sxs-lookup"><span data-stu-id="9cc57-129">In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableRemoteUsers** for a user policy that enables communications for remote users).</span></span>
    
      - <span data-ttu-id="9cc57-130">若要更改现有策略, 请单击表中列出的相应策略, 单击 "**编辑**", 然后单击 "**显示详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="9cc57-130">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="9cc57-131">可选如果要添加或编辑说明, 请在 "**说明**" 中指定策略的信息。</span><span class="sxs-lookup"><span data-stu-id="9cc57-131">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="9cc57-132">请执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="9cc57-132">Do one of the following:</span></span>
    
      - <span data-ttu-id="9cc57-133">若要启用该策略的远程用户访问权限, 请选中 "**启用与远程用户的通信**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="9cc57-133">To enable remote user access for the policy, select the **Enable communications with remote users** check box.</span></span>
    
      - <span data-ttu-id="9cc57-134">若要禁用该策略的远程用户访问权限, 请清除 "**启用与远程用户的通信**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="9cc57-134">To disable remote user access for the policy, clear the **Enable communications with remote users** check box.</span></span>

7.  <span data-ttu-id="9cc57-135">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="9cc57-135">Click **Commit**.</span></span>

<span data-ttu-id="9cc57-136">若要启用远程用户访问, 还必须启用对组织中的远程用户访问的支持。</span><span class="sxs-lookup"><span data-stu-id="9cc57-136">To enable remote user access, you must also enable support for remote user access in your organization.</span></span> <span data-ttu-id="9cc57-137">有关详细信息, 请参阅[启用或禁用联盟和公用 IM 连接](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="9cc57-137">For details, see [Enable or disable federation and public IM connectivity](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md).</span></span>

<span data-ttu-id="9cc57-138">如果这是用户策略, 你还必须将策略应用于你希望能够远程连接的用户。</span><span class="sxs-lookup"><span data-stu-id="9cc57-138">If this is a user policy, you must also apply the policy to users that you want to be able to connect remotely.</span></span> <span data-ttu-id="9cc57-139">有关详细信息, 请参阅[分配外部用户访问策略](assign-an-external-user-access-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="9cc57-139">For details, see [Assign an external user access policy](assign-an-external-user-access-policy.md).</span></span>
