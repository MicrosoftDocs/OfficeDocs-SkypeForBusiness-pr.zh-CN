---
title: 配置策略以控制联盟用户访问
ms.reviewer: ''
ms:assetid: 5485e208-81e4-4e59-9aeb-1232c11dd8a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398359(v=OCS.15)
ms:contentKeyID: 48184180
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: '配置策略以支持与联盟伙伴的通信时, 这些策略适用于联盟域的用户。 '
ms.openlocfilehash: 00552dfd6e2cb92d1bd50cb851bfb8324122c5ff
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280164"
---
# <a name="configure-policies-to-control-federated-user-access-in-skype-for-business-server"></a><span data-ttu-id="16bdd-103">在 Skype for Business Server 中配置用于控制联盟用户访问的策略</span><span class="sxs-lookup"><span data-stu-id="16bdd-103">Configure policies to control federated user access in Skype for Business Server</span></span>

<span data-ttu-id="16bdd-104">配置策略以支持与联盟伙伴的通信时, 这些策略适用于联盟域的用户。</span><span class="sxs-lookup"><span data-stu-id="16bdd-104">When you configure policies to support communications with federated partners, the policies apply to users of federated domains.</span></span> <span data-ttu-id="16bdd-105">你可以配置一个或多个外部用户访问策略, 以控制联盟域的用户是否可以与你的 Skype for Business 服务器用户进行协作。</span><span class="sxs-lookup"><span data-stu-id="16bdd-105">You can configure one or more external user access policies to control whether users of federated domains can collaborate with your Skype for Business Server users.</span></span> <span data-ttu-id="16bdd-106">若要控制联盟用户访问, 可以在全局、网站和用户级别配置策略。</span><span class="sxs-lookup"><span data-stu-id="16bdd-106">To control federated user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="16bdd-107">在一个策略级别应用的 Skype for business 服务器策略设置可以覆盖在其他策略级别应用的设置。</span><span class="sxs-lookup"><span data-stu-id="16bdd-107">Skype for Business Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="16bdd-108">Skype for Business 服务器策略优先级为: 用户策略 (最受影响) 覆盖网站策略, 然后网站策略覆盖全局策略 (最不影响)。</span><span class="sxs-lookup"><span data-stu-id="16bdd-108">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="16bdd-109">这意味着，策略设置与策略所影响的对象距离越近，它对该对象的影响力越大。</span><span class="sxs-lookup"><span data-stu-id="16bdd-109">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>


> [!NOTE]  
> <span data-ttu-id="16bdd-110">你可以配置策略来控制联盟用户访问, 即使你没有为组织启用联盟也是如此。</span><span class="sxs-lookup"><span data-stu-id="16bdd-110">You can configure policies to control federated user access, even if you have not enabled federation for your organization.</span></span> <span data-ttu-id="16bdd-111">但是, 仅当你的组织启用了联合身份验证时, 你配置的策略才有效。</span><span class="sxs-lookup"><span data-stu-id="16bdd-111">However, the policies that you configure are in effect only when you have federation enabled for your organization.</span></span> <span data-ttu-id="16bdd-112">有关启用联盟的详细信息, 请参阅[启用或禁用远程用户访问](../access-edge/enable-or-disable-remote-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="16bdd-112">For details about enabling federation, see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span>  <span data-ttu-id="16bdd-113">此外, 如果你指定用于控制联盟用户访问的用户策略, 该策略将仅应用于已启用 Skype for business 服务器的用户, 并且配置为使用该策略。</span><span class="sxs-lookup"><span data-stu-id="16bdd-113">Additionally, if you specify a user policy to control federated user access, the policy applies only to users that are enabled for Skype for Business Server and configured to use the policy.</span></span>


## <a name="to-configure-a-policy-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="16bdd-114">将策略配置为支持由联盟域的用户访问</span><span class="sxs-lookup"><span data-stu-id="16bdd-114">To configure a policy to support access by users of federated domains</span></span>

1.  <span data-ttu-id="16bdd-115">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="16bdd-115">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="16bdd-116">打开一个浏览器窗口, 然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="16bdd-116">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="16bdd-117">在左侧导航栏中, 单击 "**外部用户访问**", 然后单击 "**外部访问策略**"。</span><span class="sxs-lookup"><span data-stu-id="16bdd-117">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="16bdd-118">在 "**外部访问策略**" 页面上, 执行下列操作之一:</span><span class="sxs-lookup"><span data-stu-id="16bdd-118">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="16bdd-119">若要将全局策略配置为支持联合用户访问, 请单击全局策略, 单击 "**编辑**", 然后单击 "**显示详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="16bdd-119">To configure the global policy to support federated user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="16bdd-120">若要创建新的网站策略, 请单击 "**新建**", 然后单击 "**网站策略**"。</span><span class="sxs-lookup"><span data-stu-id="16bdd-120">To create a new site policy, click **New**, and then click **Site policy**.</span></span> <span data-ttu-id="16bdd-121">在 "**选择网站**" 中, 从列表中单击相应的网站, 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="16bdd-121">In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="16bdd-122">若要创建新的用户策略, 请单击 "**新建**", 然后单击 "**用户策略**"。</span><span class="sxs-lookup"><span data-stu-id="16bdd-122">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="16bdd-123">在 "**新的外部访问策略**" 中, 在 "**名称**" 字段中创建一个唯一名称, 以指示用户策略所涉及的内容 (例如, **EnableFederatedUsers**为联合域用户启用通信的用户策略)。</span><span class="sxs-lookup"><span data-stu-id="16bdd-123">In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableFederatedUsers** for a user policy that enables communications for federated domain users).</span></span>
    
      - <span data-ttu-id="16bdd-124">若要更改现有策略, 请单击表中列出的相应策略, 单击 "**编辑**", 然后单击 "**显示详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="16bdd-124">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="16bdd-125">可选如果要添加或编辑说明, 请在 "**说明**" 中指定策略的信息。</span><span class="sxs-lookup"><span data-stu-id="16bdd-125">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="16bdd-126">请执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="16bdd-126">Do one of the following:</span></span>
    
      - <span data-ttu-id="16bdd-127">若要为策略启用联盟用户访问权限, 请选中 "**启用与联盟用户的通信**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="16bdd-127">To enable federated user access for the policy, select the **Enable communications with federated users** check box.</span></span>
    
      - <span data-ttu-id="16bdd-128">若要对策略禁用联盟用户访问权限, 请清除 "**启用与联盟用户的通信**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="16bdd-128">To disable federated user access for the policy, clear the **Enable communications with federated users** check box.</span></span>

7.  <span data-ttu-id="16bdd-129">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="16bdd-129">Click **Commit**.</span></span>

<span data-ttu-id="16bdd-130">若要启用联盟用户访问, 还必须在你的组织中启用联合身份验证支持。</span><span class="sxs-lookup"><span data-stu-id="16bdd-130">To enable federated user access, you must also enable support for federation in your organization.</span></span> <span data-ttu-id="16bdd-131">有关详细信息, 请参阅[启用或禁用联盟和公用 IM 连接](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="16bdd-131">For details, see [Enable or disable federation and public IM connectivity](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md).</span></span>

<span data-ttu-id="16bdd-132">如果这是用户策略, 你还必须将策略应用于你希望能够与联盟用户协作的用户。</span><span class="sxs-lookup"><span data-stu-id="16bdd-132">If this is a user policy, you must also apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="16bdd-133">有关详细信息, 请参阅[分配外部用户访问策略](assign-an-external-user-access-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="16bdd-133">For details, see [Assign an external user access policy](assign-an-external-user-access-policy.md).</span></span>

## <a name="to-configure-an-existing-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="16bdd-134">使用 Windows PowerShell 配置现有策略以支持联盟域的用户访问</span><span class="sxs-lookup"><span data-stu-id="16bdd-134">To configure an existing policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="16bdd-135">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="16bdd-135">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="16bdd-136">启动 Skype for 名片 Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、"skype for business**服务器**", 然后单击 " **skype for business 服务器管理外壳**"。</span><span class="sxs-lookup"><span data-stu-id="16bdd-136">Start the Skype for Busines Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="16bdd-137">在 Skype for Business 服务器管理外壳程序中键入以下内容:</span><span class="sxs-lookup"><span data-stu-id="16bdd-137">Type the following in the Skype for Business Server Management Shell:</span></span>
    
    ```
    Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAcess <$true, $false> -EnablePublicCloudAudioVideoAcess <$true, $false> -EnableOutsideAcess <$true, $false>
    ```
       

    > [!TIP]  
    > <span data-ttu-id="16bdd-138">在 Skype for Business 服务器控制面板中, 参数 "EnablePublicCloudAudioVideoAccess" 没有对应的选择</span><span class="sxs-lookup"><span data-stu-id="16bdd-138">The parameter “EnablePublicCloudAudioVideoAccess” does not have a corresponding selection in the Skype for Business Server Control Panel</span></span>


## <a name="to-create-a-new-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="16bdd-139">使用 Windows PowerShell 创建新策略以支持联盟域的用户访问</span><span class="sxs-lookup"><span data-stu-id="16bdd-139">To create a new policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="16bdd-140">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="16bdd-140">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="16bdd-141">启动 Skype for Business 服务器命令行管理程序: 单击 "**开始**", 单击 "**所有程序**", 单击 " **Microsoft skype**for business 服务器", 然后单击 " **skype for business 服务器管理外壳**"。</span><span class="sxs-lookup"><span data-stu-id="16bdd-141">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="16bdd-142">在 Skype for Business 服务器管理外壳程序中键入以下内容:</span><span class="sxs-lookup"><span data-stu-id="16bdd-142">Type the following in the Skype for Business Server Management Shell:</span></span>
    
    ```
    New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    ```
    
    <span data-ttu-id="16bdd-143">创建新网站策略的示例:</span><span class="sxs-lookup"><span data-stu-id="16bdd-143">An example of creating a new site policy:</span></span>
    
    ```
    New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    ```


## <a name="to-delete-or-reset-a-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="16bdd-144">使用 Windows PowerShell 删除或重置策略以支持联盟域的用户访问</span><span class="sxs-lookup"><span data-stu-id="16bdd-144">To delete or reset a policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="16bdd-145">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="16bdd-145">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="16bdd-146">在 Skype for Business Server 命令行管理程序中键入以下命令</span><span class="sxs-lookup"><span data-stu-id="16bdd-146">Type the following in the Skype for Business Server Management Shell</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>`
    
    <span data-ttu-id="16bdd-147">重置全局策略 (全局策略只能删除其设置) 的示例。</span><span class="sxs-lookup"><span data-stu-id="16bdd-147">An example of resetting the global policy (The global policy can only have its setting removed.</span></span> <span data-ttu-id="16bdd-148">无法删除策略:</span><span class="sxs-lookup"><span data-stu-id="16bdd-148">The policy cannot be deleted):</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity global`
    
    <span data-ttu-id="16bdd-149">若要删除网站策略, 请键入:</span><span class="sxs-lookup"><span data-stu-id="16bdd-149">To remove a site policy, type:</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity site:Redmond` 
    
    <span data-ttu-id="16bdd-150">删除网站策略 Redmond。</span><span class="sxs-lookup"><span data-stu-id="16bdd-150">Deletes the site policy Redmond.</span></span> <span data-ttu-id="16bdd-151">若要删除名为 UserEAPPolicy 的用户策略, 请键入:</span><span class="sxs-lookup"><span data-stu-id="16bdd-151">To delete a user policy named UserEAPPolicy, type:</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity UserEAPPolicy`


## <a name="see-also"></a><span data-ttu-id="16bdd-152">另请参阅</span><span class="sxs-lookup"><span data-stu-id="16bdd-152">See Also</span></span>


[<span data-ttu-id="16bdd-153">启用或禁用联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="16bdd-153">Enable or disable federation and public IM connectivity</span></span>](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md) 

[<span data-ttu-id="16bdd-154">分配外部用户访问策略</span><span class="sxs-lookup"><span data-stu-id="16bdd-154">Assign an external user access policy</span></span>](assign-an-external-user-access-policy.md)

[<span data-ttu-id="16bdd-155">管理组织的 SIP 联盟域</span><span class="sxs-lookup"><span data-stu-id="16bdd-155">Manage SIP federated domains for your organization</span></span>](../sip-domains/manage-sip-federated-domains-for-your-organization.md)
 
[<span data-ttu-id="16bdd-156">管理组织的 SIP 联盟提供程序</span><span class="sxs-lookup"><span data-stu-id="16bdd-156">Manage SIP federated providers for your organization</span></span>](../sip-providers/manage-sip-federated-providers-for-your-organization.md)

[<span data-ttu-id="16bdd-157">Set-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="16bdd-157">Set-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsExternalAccessPolicy)  
[<span data-ttu-id="16bdd-158">新-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="16bdd-158">New-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsExternalAccessPolicy)  
[<span data-ttu-id="16bdd-159">CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="16bdd-159">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="16bdd-160">Remove-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="16bdd-160">Remove-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[<span data-ttu-id="16bdd-161">授权-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="16bdd-161">Grant-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

