---
title: 配置策略以控制联盟用户访问
ms.reviewer: ''
ms:assetid: 5485e208-81e4-4e59-9aeb-1232c11dd8a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398359(v=OCS.15)
ms:contentKeyID: 48184180
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
description: '如果将策略配置为支持与联盟伙伴进行通信，则策略将适用于联盟域用户。 '
ms.openlocfilehash: 6107615767d0360180baf9f22d5fddc6a5f8e565
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099038"
---
# <a name="configure-policies-to-control-federated-user-access-in-skype-for-business-server"></a><span data-ttu-id="aee8f-103">配置策略以控制 Skype for Business Server 中的联盟用户访问</span><span class="sxs-lookup"><span data-stu-id="aee8f-103">Configure policies to control federated user access in Skype for Business Server</span></span>

<span data-ttu-id="aee8f-104">如果将策略配置为支持与联盟伙伴进行通信，则策略将适用于联盟域用户。</span><span class="sxs-lookup"><span data-stu-id="aee8f-104">When you configure policies to support communications with federated partners, the policies apply to users of federated domains.</span></span> <span data-ttu-id="aee8f-105">可以配置一个或多个外部用户访问策略，以控制联盟域的用户是否可以与 Skype for Business Server 用户进行协作。</span><span class="sxs-lookup"><span data-stu-id="aee8f-105">You can configure one or more external user access policies to control whether users of federated domains can collaborate with your Skype for Business Server users.</span></span> <span data-ttu-id="aee8f-106">要控制联盟用户访问，可以在全局、站点和用户级别配置策略。</span><span class="sxs-lookup"><span data-stu-id="aee8f-106">To control federated user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="aee8f-107">在一个策略级别应用的 Skype for Business Server 策略设置可以覆盖在另一个策略级别应用的设置。</span><span class="sxs-lookup"><span data-stu-id="aee8f-107">Skype for Business Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="aee8f-108">Skype for Business 服务器策略优先级是：用户策略（最大影响力）覆盖站点策略，然后站点策略覆盖全局策略（最小影响）。</span><span class="sxs-lookup"><span data-stu-id="aee8f-108">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="aee8f-109">这意味着，策略设置越接近策略影响的对象，它对对象的影响就越大。</span><span class="sxs-lookup"><span data-stu-id="aee8f-109">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>


> [!NOTE]  
> <span data-ttu-id="aee8f-110">即使没有为组织启用联盟，也可以配置控制联盟用户访问的策略。</span><span class="sxs-lookup"><span data-stu-id="aee8f-110">You can configure policies to control federated user access, even if you have not enabled federation for your organization.</span></span> <span data-ttu-id="aee8f-111">但是，只有为组织启用联盟后，配置的策略才会生效。</span><span class="sxs-lookup"><span data-stu-id="aee8f-111">However, the policies that you configure are in effect only when you have federation enabled for your organization.</span></span> <span data-ttu-id="aee8f-112">有关启用联盟的详细信息，请参阅 [启用或禁用远程用户访问](../access-edge/enable-or-disable-remote-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="aee8f-112">For details about enabling federation, see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span>  <span data-ttu-id="aee8f-113">此外，如果指定用户策略来控制联盟用户访问，则此策略仅适用于启用了 Skype for Business Server 且配置为使用该策略的用户。</span><span class="sxs-lookup"><span data-stu-id="aee8f-113">Additionally, if you specify a user policy to control federated user access, the policy applies only to users that are enabled for Skype for Business Server and configured to use the policy.</span></span>


## <a name="to-configure-a-policy-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="aee8f-114">配置策略以支持联盟域用户访问</span><span class="sxs-lookup"><span data-stu-id="aee8f-114">To configure a policy to support access by users of federated domains</span></span>

1.  <span data-ttu-id="aee8f-115">从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。</span><span class="sxs-lookup"><span data-stu-id="aee8f-115">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="aee8f-116">打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="aee8f-116">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="aee8f-117">在左侧导航栏中，单击“外部用户访问”，然后单击“外部访问策略”。</span><span class="sxs-lookup"><span data-stu-id="aee8f-117">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="aee8f-118">在“外部访问策略”页上，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="aee8f-118">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="aee8f-119">要将全局策略配置为支持联盟用户访问，请单击该全局策略，再单击“编辑”，然后单击“显示详细信息”。</span><span class="sxs-lookup"><span data-stu-id="aee8f-119">To configure the global policy to support federated user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="aee8f-p103">要创建新的站点策略，请单击“新建”，然后单击“站点策略”。在“选择站点”中，单击列表中相应的站点，然后单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="aee8f-p103">To create a new site policy, click **New**, and then click **Site policy**. In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="aee8f-p104">要创建新的用户策略，请单击“新建”，然后单击“用户策略”。在“新建外部访问策略”的“名称”字段中，创建一个唯一的名称以指示用户策略的作用范围（例如，**EnableFederatedUsers** 代表启用联盟域用户通信的用户策略）。</span><span class="sxs-lookup"><span data-stu-id="aee8f-p104">To create a new user policy, click **New**, and then click **User policy**. In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableFederatedUsers** for a user policy that enables communications for federated domain users).</span></span>
    
      - <span data-ttu-id="aee8f-124">要更改现有的策略，请单击表中列出的相应策略，再单击“编辑”，然后单击“显示详细信息”。</span><span class="sxs-lookup"><span data-stu-id="aee8f-124">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="aee8f-125">（可选）如果要添加或编辑说明，请在“说明”中为策略指定相应的信息。</span><span class="sxs-lookup"><span data-stu-id="aee8f-125">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="aee8f-126">执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="aee8f-126">Do one of the following:</span></span>
    
      - <span data-ttu-id="aee8f-127">要为策略启用联盟用户访问，请选中“启用与联盟用户的通信”复选框。</span><span class="sxs-lookup"><span data-stu-id="aee8f-127">To enable federated user access for the policy, select the **Enable communications with federated users** check box.</span></span>
    
      - <span data-ttu-id="aee8f-128">要为策略禁用联盟用户访问，请清除“启用与联盟用户的通信”复选框。</span><span class="sxs-lookup"><span data-stu-id="aee8f-128">To disable federated user access for the policy, clear the **Enable communications with federated users** check box.</span></span>

7.  <span data-ttu-id="aee8f-129">单击“提交”。</span><span class="sxs-lookup"><span data-stu-id="aee8f-129">Click **Commit**.</span></span>

<span data-ttu-id="aee8f-130">要启用联盟用户访问，还必须在组织中启用对联盟的支持。</span><span class="sxs-lookup"><span data-stu-id="aee8f-130">To enable federated user access, you must also enable support for federation in your organization.</span></span> <span data-ttu-id="aee8f-131">有关详细信息，请参阅启用 [或禁用联盟和公共 IM 连接](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="aee8f-131">For details, see [Enable or disable federation and public IM connectivity](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md).</span></span>

<span data-ttu-id="aee8f-132">如果这是一个用户策略，则还必须将此策略应用于希望其可以与联盟用户进行协作的用户。</span><span class="sxs-lookup"><span data-stu-id="aee8f-132">If this is a user policy, you must also apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="aee8f-133">有关详细信息，请参阅 [分配外部用户访问策略](assign-an-external-user-access-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="aee8f-133">For details, see [Assign an external user access policy](assign-an-external-user-access-policy.md).</span></span>

## <a name="to-configure-an-existing-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="aee8f-134">使用域配置现有Windows PowerShell以支持联盟域用户访问</span><span class="sxs-lookup"><span data-stu-id="aee8f-134">To configure an existing policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="aee8f-135">从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。</span><span class="sxs-lookup"><span data-stu-id="aee8f-135">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="aee8f-136">启动 Skype for Busines 服务器命令行管理程序：单击"开始"，单击"所有程序"，**单击\*\*\*\*"Skype for Business Server"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**</span><span class="sxs-lookup"><span data-stu-id="aee8f-136">Start the Skype for Busines Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="aee8f-137">在 Skype for Business Server 命令行管理程序 中键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="aee8f-137">Type the following in the Skype for Business Server Management Shell:</span></span>
    
    ```PowerShell
    Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAcess <$true, $false> -EnablePublicCloudAudioVideoAcess <$true, $false> -EnableOutsideAcess <$true, $false>
    ```
       

    > [!TIP]  
    > <span data-ttu-id="aee8f-138">参数"EnablePublicCloudAudioVideoAccess"在 Skype for Business Server 控制面板中没有对应的选择</span><span class="sxs-lookup"><span data-stu-id="aee8f-138">The parameter “EnablePublicCloudAudioVideoAccess” does not have a corresponding selection in the Skype for Business Server Control Panel</span></span>


## <a name="to-create-a-new-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="aee8f-139">使用 Windows PowerShell 创建新策略以支持联盟域用户访问</span><span class="sxs-lookup"><span data-stu-id="aee8f-139">To create a new policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="aee8f-140">从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。</span><span class="sxs-lookup"><span data-stu-id="aee8f-140">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="aee8f-141">启动 Skype for Business Server命令行管理程序：单击"开始"，单击"所有程序"，**单击\*\*\*\*"Microsoft Skype for Business Server"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**</span><span class="sxs-lookup"><span data-stu-id="aee8f-141">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="aee8f-142">在 Skype for Business Server 命令行管理程序 中键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="aee8f-142">Type the following in the Skype for Business Server Management Shell:</span></span>
    
    ```PowerShell
    New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    ```
    
    <span data-ttu-id="aee8f-143">创建新站点策略的示例：</span><span class="sxs-lookup"><span data-stu-id="aee8f-143">An example of creating a new site policy:</span></span>
    
    ```PowerShell
    New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    ```


## <a name="to-delete-or-reset-a-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="aee8f-144">使用策略删除或重置Windows PowerShell以支持联盟域用户访问</span><span class="sxs-lookup"><span data-stu-id="aee8f-144">To delete or reset a policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="aee8f-145">从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。</span><span class="sxs-lookup"><span data-stu-id="aee8f-145">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="aee8f-146">在 Skype for Business Server 命令行管理程序 中键入以下内容</span><span class="sxs-lookup"><span data-stu-id="aee8f-146">Type the following in the Skype for Business Server Management Shell</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>`
    
    <span data-ttu-id="aee8f-p107">重置全局策略的示例（只能删除全局策略的设置，而无法删除全局策略本身）：</span><span class="sxs-lookup"><span data-stu-id="aee8f-p107">An example of resetting the global policy (The global policy can only have its setting removed. The policy cannot be deleted):</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity global`
    
    <span data-ttu-id="aee8f-149">若要删除站点策略，请键入：</span><span class="sxs-lookup"><span data-stu-id="aee8f-149">To remove a site policy, type:</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity site:Redmond` 
    
    <span data-ttu-id="aee8f-150">删除站点策略 Redmond。</span><span class="sxs-lookup"><span data-stu-id="aee8f-150">Deletes the site policy Redmond.</span></span> <span data-ttu-id="aee8f-151">若要删除名为 UserEAPPolicy 的用户策略，请键入：</span><span class="sxs-lookup"><span data-stu-id="aee8f-151">To delete a user policy named UserEAPPolicy, type:</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity UserEAPPolicy`


## <a name="see-also"></a><span data-ttu-id="aee8f-152">另请参阅</span><span class="sxs-lookup"><span data-stu-id="aee8f-152">See Also</span></span>


[<span data-ttu-id="aee8f-153">启用或禁用联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="aee8f-153">Enable or disable federation and public IM connectivity</span></span>](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md) 

[<span data-ttu-id="aee8f-154">分配外部用户访问策略</span><span class="sxs-lookup"><span data-stu-id="aee8f-154">Assign an external user access policy</span></span>](assign-an-external-user-access-policy.md)

[<span data-ttu-id="aee8f-155">管理组织的 SIP 联盟域</span><span class="sxs-lookup"><span data-stu-id="aee8f-155">Manage SIP federated domains for your organization</span></span>](../sip-domains/manage-sip-federated-domains-for-your-organization.md)
 
[<span data-ttu-id="aee8f-156">管理组织的 SIP 联盟提供程序</span><span class="sxs-lookup"><span data-stu-id="aee8f-156">Manage SIP federated providers for your organization</span></span>](../sip-providers/manage-sip-federated-providers-for-your-organization.md)

[<span data-ttu-id="aee8f-157">Set-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="aee8f-157">Set-CsExternalAccessPolicy</span></span>](/powershell/module/skype/Set-CsExternalAccessPolicy)  
[<span data-ttu-id="aee8f-158">New-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="aee8f-158">New-CsExternalAccessPolicy</span></span>](/powershell/module/skype/New-CsExternalAccessPolicy)  
[<span data-ttu-id="aee8f-159">Get-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="aee8f-159">Get-CsExternalAccessPolicy</span></span>](/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="aee8f-160">Remove-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="aee8f-160">Remove-CsExternalAccessPolicy</span></span>](/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[<span data-ttu-id="aee8f-161">Grant-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="aee8f-161">Grant-CsExternalAccessPolicy</span></span>](/powershell/module/skype/Grant-CsExternalAccessPolicy)  
