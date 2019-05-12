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
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 您可以配置一个或多个外部用户访问策略以控制是否远程用户可以与内部 Skype 业务 Server 用户进行协作。 若要控制远程用户访问，可以配置策略在全局、 站点和用户级别。
ms.openlocfilehash: 3355ee979bdf0e5be954aea69f365084271223fd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920451"
---
# <a name="configure-policies-to-control-remote-user-access-in-skype-for-business-server"></a><span data-ttu-id="b0d72-104">配置策略以控制远程用户访问在 Skype 业务服务器</span><span class="sxs-lookup"><span data-stu-id="b0d72-104">Configure policies to control remote user access in Skype for Business Server</span></span>

<span data-ttu-id="b0d72-105">您可以配置一个或多个外部用户访问策略以控制是否远程用户可以与内部 Skype 业务 Server 用户进行协作。</span><span class="sxs-lookup"><span data-stu-id="b0d72-105">You configure one or more external user access policies to control whether remote users can collaborate with internal Skype for Business Server users.</span></span> <span data-ttu-id="b0d72-106">若要控制远程用户访问，可以配置策略在全局、 站点和用户级别。</span><span class="sxs-lookup"><span data-stu-id="b0d72-106">To control remote user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="b0d72-107">网站策略将覆盖全局策略和用户策略将覆盖站点和全局策略。</span><span class="sxs-lookup"><span data-stu-id="b0d72-107">Site policies override the global policy, and user policies override site and global policies.</span></span> <span data-ttu-id="b0d72-108">有关您可以配置的策略的类型的详细信息，请参阅[Managing 联盟和外部访问 Skype 业务服务器](../managing-federation-and-external-access.md)。</span><span class="sxs-lookup"><span data-stu-id="b0d72-108">For details about the types of policies that you can configure, see [Managing federation and external access to Skype for Business Server](../managing-federation-and-external-access.md).</span></span> <span data-ttu-id="b0d72-109">Skype 的于一个策略级别的企业服务器策略设置可以覆盖其他策略级别应用的设置。</span><span class="sxs-lookup"><span data-stu-id="b0d72-109">Skype for Business Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="b0d72-110">业务服务器策略优先顺序的 Skype 是： 用户策略 （大多数影响） 将覆盖站点策略，然后网站策略将覆盖全局策略 （最低影响）。</span><span class="sxs-lookup"><span data-stu-id="b0d72-110">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="b0d72-111">这意味着，策略设置与策略所影响的对象距离越近，它对该对象的影响力越大。</span><span class="sxs-lookup"><span data-stu-id="b0d72-111">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>

> [!NOTE]  
> <span data-ttu-id="b0d72-112">即使您没有为组织启用远程用户访问，您可以配置策略以控制远程用户访问。</span><span class="sxs-lookup"><span data-stu-id="b0d72-112">You can configure policies to control remote user access, even if you have not enabled remote user access for your organization.</span></span> <span data-ttu-id="b0d72-113">但是，您配置的策略实际上是将仅当已为组织启用远程用户访问。</span><span class="sxs-lookup"><span data-stu-id="b0d72-113">However, the policies that you configure are in effect only when you have remote user access enabled for your organization.</span></span> <span data-ttu-id="b0d72-114">此外，如果您指定一个用户策略控制远程用户访问，该策略仅适用于 Skype 业务服务器启用和配置为使用该策略的用户。</span><span class="sxs-lookup"><span data-stu-id="b0d72-114">Additionally, if you specify a user policy to control remote user access, the policy applies only to users that are enabled for Skype for Business Server and configured to use the policy.</span></span> <span data-ttu-id="b0d72-115">有关指定可以登录到 Skype 业务服务器从远程位置的用户详细信息，请参阅[将外部用户访问策略分配](assign-an-external-user-access-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="b0d72-115">For details about specifying users that can sign in to Skype for Business Server from remote locations, see [Assign an external user access policy](assign-an-external-user-access-policy.md).</span></span>

<span data-ttu-id="b0d72-116">使用以下过程配置要用于控制远程用户访问的每个外部访问策略。</span><span class="sxs-lookup"><span data-stu-id="b0d72-116">Use the following procedure to configure each external access policy that you want to use to control remote user access.</span></span>


> [!NOTE]  
> <span data-ttu-id="b0d72-117">此过程介绍如何配置策略仅以启用与远程用户的通信，但您配置为支持远程用户访问的每个策略还可以配置联盟的用户访问和公共用户访问。</span><span class="sxs-lookup"><span data-stu-id="b0d72-117">This procedure describes how to configure a policy only to enable communications with remote users, but each policy that you configure to support remote user access can also configure federated user access and public user access.</span></span> <span data-ttu-id="b0d72-118">有关配置策略以支持联盟的用户的详细信息，请参阅[配置策略以控制联盟用户访问中的业务服务器 Skype](configure-policies-to-control-federated-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="b0d72-118">For details about configuring policies to support federated users, see [Configure policies to control federated user access in Skype for Business Server](configure-policies-to-control-federated-user-access.md).</span></span> <span data-ttu-id="b0d72-119">有关配置策略以支持公共用户的详细信息，请参阅[管理 SIP 联盟提供程序中的业务服务器 Skype 的组织](../sip-providers/manage-sip-federated-providers-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="b0d72-119">For details about configuring policies to support public users, see [Manage SIP federated providers for your organization in Skype for Business Server](../sip-providers/manage-sip-federated-providers-for-your-organization.md).</span></span>


## <a name="to-configure-an-external-access-policy-to-support-remote-user-access"></a><span data-ttu-id="b0d72-120">若要配置外部访问策略以支持远程用户访问</span><span class="sxs-lookup"><span data-stu-id="b0d72-120">To configure an external access policy to support remote user access</span></span>

1.  <span data-ttu-id="b0d72-121">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="b0d72-121">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b0d72-122">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="b0d72-122">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="b0d72-123">在左侧的导航栏中，单击**外部用户访问**，然后单击**外部访问策略**。</span><span class="sxs-lookup"><span data-stu-id="b0d72-123">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="b0d72-124">在**外部访问策略**页上，执行以下任一操作：</span><span class="sxs-lookup"><span data-stu-id="b0d72-124">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="b0d72-125">要配置全局策略以支持远程用户访问，请单击该全局策略，单击**编辑**，然后单击**显示详细信息**。</span><span class="sxs-lookup"><span data-stu-id="b0d72-125">To configure the global policy to support remote user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="b0d72-126">若要创建新的站点策略，单击**新建**，然后单击**站点策略**。</span><span class="sxs-lookup"><span data-stu-id="b0d72-126">To create a new site policy, click **New**, and then click **Site policy**.</span></span> <span data-ttu-id="b0d72-127">在**选择站点**单击列表中的相应站点，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b0d72-127">In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="b0d72-128">若要创建一个新用户策略，单击**新建**，然后单击**用户策略**。</span><span class="sxs-lookup"><span data-stu-id="b0d72-128">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="b0d72-129">在**新外部访问策略**中，创建一个唯一的名称，在**名称**字段，该值指示哪些用户策略介绍 (例如， **EnableRemoteUsers**用户策略启用的远程用户的通信的)。</span><span class="sxs-lookup"><span data-stu-id="b0d72-129">In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableRemoteUsers** for a user policy that enables communications for remote users).</span></span>
    
      - <span data-ttu-id="b0d72-130">若要更改现有策略，单击表中列出的相应策略，单击**编辑**，然后单击**显示详细信息**。</span><span class="sxs-lookup"><span data-stu-id="b0d72-130">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="b0d72-131">（可选）如果您想要添加或编辑说明，请在**说明**指定策略的信息。</span><span class="sxs-lookup"><span data-stu-id="b0d72-131">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="b0d72-132">请执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="b0d72-132">Do one of the following:</span></span>
    
      - <span data-ttu-id="b0d72-133">若要启用远程用户访问的策略，请选中**启用与远程用户的通信**复选框。</span><span class="sxs-lookup"><span data-stu-id="b0d72-133">To enable remote user access for the policy, select the **Enable communications with remote users** check box.</span></span>
    
      - <span data-ttu-id="b0d72-134">若要禁用远程用户访问的策略，请清除**启用与远程用户的通信**复选框。</span><span class="sxs-lookup"><span data-stu-id="b0d72-134">To disable remote user access for the policy, clear the **Enable communications with remote users** check box.</span></span>

7.  <span data-ttu-id="b0d72-135">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="b0d72-135">Click **Commit**.</span></span>

<span data-ttu-id="b0d72-136">若要启用远程用户访问，您还必须在组织中启用对远程用户访问的支持。</span><span class="sxs-lookup"><span data-stu-id="b0d72-136">To enable remote user access, you must also enable support for remote user access in your organization.</span></span> <span data-ttu-id="b0d72-137">有关详细信息，请参阅[启用或禁用联盟和公共 IM 连接](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="b0d72-137">For details, see [Enable or disable federation and public IM connectivity](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md).</span></span>

<span data-ttu-id="b0d72-138">如果这是用户策略，您必须向您想要能够远程连接的用户应用策略。</span><span class="sxs-lookup"><span data-stu-id="b0d72-138">If this is a user policy, you must also apply the policy to users that you want to be able to connect remotely.</span></span> <span data-ttu-id="b0d72-139">有关详细信息，请参阅[将外部用户访问策略分配](assign-an-external-user-access-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="b0d72-139">For details, see [Assign an external user access policy](assign-an-external-user-access-policy.md).</span></span>
