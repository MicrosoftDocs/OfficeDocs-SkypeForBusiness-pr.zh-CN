---
title: 配置策略以控制远程用户访问
ms.reviewer: ''
ms:assetid: 8f556849-692b-44a0-9514-4468fc9a39d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398725(v=OCS.15)
ms:contentKeyID: 48184825
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
description: 配置一个或多个外部用户访问策略，以控制远程用户是否可以与内部 Skype for Business Server 用户进行协作。 若要控制远程用户访问，可以在全局、站点和用户级别配置策略。
ms.openlocfilehash: 0fd24f7c57cfaa4a131bcd1648cb1b6e6eb5f05a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817292"
---
# <a name="configure-policies-to-control-remote-user-access-in-skype-for-business-server"></a><span data-ttu-id="7c533-104">配置策略以控制 Skype for Business Server 中的远程用户访问</span><span class="sxs-lookup"><span data-stu-id="7c533-104">Configure policies to control remote user access in Skype for Business Server</span></span>

<span data-ttu-id="7c533-105">配置一个或多个外部用户访问策略，以控制远程用户是否可以与内部 Skype for Business Server 用户进行协作。</span><span class="sxs-lookup"><span data-stu-id="7c533-105">You configure one or more external user access policies to control whether remote users can collaborate with internal Skype for Business Server users.</span></span> <span data-ttu-id="7c533-106">若要控制远程用户访问，可以在全局、站点和用户级别配置策略。</span><span class="sxs-lookup"><span data-stu-id="7c533-106">To control remote user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="7c533-107">站点策略将覆盖全局策略，而用户策略将覆盖站点策略和全局策略。</span><span class="sxs-lookup"><span data-stu-id="7c533-107">Site policies override the global policy, and user policies override site and global policies.</span></span> <span data-ttu-id="7c533-108">有关可以配置的策略类型的详细信息，请参阅"管理对 Skype for Business Server 的联盟和[外部访问"。](../managing-federation-and-external-access.md)</span><span class="sxs-lookup"><span data-stu-id="7c533-108">For details about the types of policies that you can configure, see [Managing federation and external access to Skype for Business Server](../managing-federation-and-external-access.md).</span></span> <span data-ttu-id="7c533-109">在一个策略级别应用的 Skype for Business Server 策略设置可以覆盖在另一个策略级别应用的设置。</span><span class="sxs-lookup"><span data-stu-id="7c533-109">Skype for Business Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="7c533-110">Skype for Business 服务器策略优先级是：用户策略（最大影响力）覆盖站点策略，然后站点策略覆盖全局策略（最小影响）。</span><span class="sxs-lookup"><span data-stu-id="7c533-110">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="7c533-111">这意味着，策略设置越接近策略影响的对象，它对对象的影响就越大。</span><span class="sxs-lookup"><span data-stu-id="7c533-111">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>

> [!NOTE]  
> <span data-ttu-id="7c533-112">即使没有为组织启用远程用户访问，也可以配置策略来控制远程用户访问。</span><span class="sxs-lookup"><span data-stu-id="7c533-112">You can configure policies to control remote user access, even if you have not enabled remote user access for your organization.</span></span> <span data-ttu-id="7c533-113">但是，只有为组织启用远程用户访问后，配置的策略才会生效。</span><span class="sxs-lookup"><span data-stu-id="7c533-113">However, the policies that you configure are in effect only when you have remote user access enabled for your organization.</span></span> <span data-ttu-id="7c533-114">此外，如果指定用户策略来控制远程用户访问，则此策略仅适用于已启用 Skype for Business Server 且配置为使用该策略的用户。</span><span class="sxs-lookup"><span data-stu-id="7c533-114">Additionally, if you specify a user policy to control remote user access, the policy applies only to users that are enabled for Skype for Business Server and configured to use the policy.</span></span> <span data-ttu-id="7c533-115">有关指定可以从远程位置登录到 Skype for Business Server 的用户的详细信息，请参阅分配 [外部用户访问策略](assign-an-external-user-access-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="7c533-115">For details about specifying users that can sign in to Skype for Business Server from remote locations, see [Assign an external user access policy](assign-an-external-user-access-policy.md).</span></span>

<span data-ttu-id="7c533-116">按照以下过程配置要用于控制远程用户访问的每个外部访问策略。</span><span class="sxs-lookup"><span data-stu-id="7c533-116">Use the following procedure to configure each external access policy that you want to use to control remote user access.</span></span>


> [!NOTE]  
> <span data-ttu-id="7c533-117">此过程描述如何配置策略以便仅启用与远程用户的通信，但配置为支持远程用户访问的每个策略也可以配置联盟用户访问和公共用户访问。</span><span class="sxs-lookup"><span data-stu-id="7c533-117">This procedure describes how to configure a policy only to enable communications with remote users, but each policy that you configure to support remote user access can also configure federated user access and public user access.</span></span> <span data-ttu-id="7c533-118">有关配置策略以支持联盟用户的详细信息，请参阅配置策略以控制 Skype for Business Server 中的 [联盟用户访问](configure-policies-to-control-federated-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="7c533-118">For details about configuring policies to support federated users, see [Configure policies to control federated user access in Skype for Business Server](configure-policies-to-control-federated-user-access.md).</span></span> <span data-ttu-id="7c533-119">有关配置策略以支持公共用户的详细信息，请参阅在 Skype for Business Server 中管理组织的 [SIP 联盟提供程序](../sip-providers/manage-sip-federated-providers-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="7c533-119">For details about configuring policies to support public users, see [Manage SIP federated providers for your organization in Skype for Business Server](../sip-providers/manage-sip-federated-providers-for-your-organization.md).</span></span>


## <a name="to-configure-an-external-access-policy-to-support-remote-user-access"></a><span data-ttu-id="7c533-120">配置外部访问策略以支持远程用户访问</span><span class="sxs-lookup"><span data-stu-id="7c533-120">To configure an external access policy to support remote user access</span></span>

1.  <span data-ttu-id="7c533-121">从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或已分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。</span><span class="sxs-lookup"><span data-stu-id="7c533-121">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7c533-122">打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="7c533-122">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="7c533-123">在左侧导航栏中，单击“外部用户访问”，然后单击“外部访问策略”。</span><span class="sxs-lookup"><span data-stu-id="7c533-123">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="7c533-124">在“外部访问策略”页上，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="7c533-124">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="7c533-125">要将全局策略配置为支持远程用户访问，请单击该全局策略，再单击“编辑”，然后单击“显示详细信息”。</span><span class="sxs-lookup"><span data-stu-id="7c533-125">To configure the global policy to support remote user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="7c533-p105">要创建新的站点策略，请单击“新建”，然后单击“站点策略”。在“选择站点”中，单击列表中相应的站点，然后单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="7c533-p105">To create a new site policy, click **New**, and then click **Site policy**. In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="7c533-p106">要创建新的用户策略，请单击“新建”，然后单击“用户策略”。在“新建外部访问策略”的“名称”字段中，创建一个唯一的名称以指示用户策略的作用范围（例如，**EnableRemoteUsers** 代表启用远程用户通信的用户策略）。</span><span class="sxs-lookup"><span data-stu-id="7c533-p106">To create a new user policy, click **New**, and then click **User policy**. In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableRemoteUsers** for a user policy that enables communications for remote users).</span></span>
    
      - <span data-ttu-id="7c533-130">要更改现有的策略，请单击表中列出的相应策略，再单击“编辑”，然后单击“显示详细信息”。</span><span class="sxs-lookup"><span data-stu-id="7c533-130">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="7c533-131">（可选）如果要添加或编辑说明，请在“说明”中为策略指定相应的信息。</span><span class="sxs-lookup"><span data-stu-id="7c533-131">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="7c533-132">执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="7c533-132">Do one of the following:</span></span>
    
      - <span data-ttu-id="7c533-133">要为策略启用远程用户访问，请选中“启用与远程用户的通信”复选框。</span><span class="sxs-lookup"><span data-stu-id="7c533-133">To enable remote user access for the policy, select the **Enable communications with remote users** check box.</span></span>
    
      - <span data-ttu-id="7c533-134">要为策略禁用远程用户访问，请清除“启用与远程用户的通信”复选框。</span><span class="sxs-lookup"><span data-stu-id="7c533-134">To disable remote user access for the policy, clear the **Enable communications with remote users** check box.</span></span>

7.  <span data-ttu-id="7c533-135">单击“提交”。</span><span class="sxs-lookup"><span data-stu-id="7c533-135">Click **Commit**.</span></span>

<span data-ttu-id="7c533-136">要启用远程用户访问，还必须在组织中启用对远程用户访问的支持。</span><span class="sxs-lookup"><span data-stu-id="7c533-136">To enable remote user access, you must also enable support for remote user access in your organization.</span></span> <span data-ttu-id="7c533-137">有关详细信息，请参阅启用 [或禁用联盟和公共 IM 连接](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="7c533-137">For details, see [Enable or disable federation and public IM connectivity](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md).</span></span>

<span data-ttu-id="7c533-138">如果这是一个用户策略，则还必须将此策略应用于希望其可以进行远程连接的用户。</span><span class="sxs-lookup"><span data-stu-id="7c533-138">If this is a user policy, you must also apply the policy to users that you want to be able to connect remotely.</span></span> <span data-ttu-id="7c533-139">有关详细信息，请参阅["分配外部用户访问策略"。](assign-an-external-user-access-policy.md)</span><span class="sxs-lookup"><span data-stu-id="7c533-139">For details, see [Assign an external user access policy](assign-an-external-user-access-policy.md).</span></span>
