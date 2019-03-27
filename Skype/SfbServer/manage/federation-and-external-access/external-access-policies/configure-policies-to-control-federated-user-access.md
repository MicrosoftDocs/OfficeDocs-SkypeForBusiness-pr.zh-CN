---
title: 配置策略以控制联盟用户访问
ms.reviewer: ''
ms:assetid: 5485e208-81e4-4e59-9aeb-1232c11dd8a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398359(v=OCS.15)
ms:contentKeyID: 48184180
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: '配置策略以支持与联盟伙伴通信时，策略应用于联盟域用户。 '
ms.openlocfilehash: df5702fb217d238a26a8a9975e7e4a0792787399
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895074"
---
# <a name="configure-policies-to-control-federated-user-access-in-skype-for-business-server"></a><span data-ttu-id="19dda-103">配置策略以控制业务服务器中 Skype 的联盟的用户访问</span><span class="sxs-lookup"><span data-stu-id="19dda-103">Configure policies to control federated user access in Skype for Business Server</span></span>

<span data-ttu-id="19dda-104">配置策略以支持与联盟伙伴通信时，策略应用于联盟域用户。</span><span class="sxs-lookup"><span data-stu-id="19dda-104">When you configure policies to support communications with federated partners, the policies apply to users of federated domains.</span></span> <span data-ttu-id="19dda-105">您可以配置一个或多个外部用户访问策略以控制是否联盟域用户可以与您 Skype 业务 Server 用户进行协作。</span><span class="sxs-lookup"><span data-stu-id="19dda-105">You can configure one or more external user access policies to control whether users of federated domains can collaborate with your Skype for Business Server users.</span></span> <span data-ttu-id="19dda-106">若要控制联盟的用户访问，可以配置策略在全局、 站点和用户级别。</span><span class="sxs-lookup"><span data-stu-id="19dda-106">To control federated user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="19dda-107">Skype 的于一个策略级别的企业服务器策略设置可以覆盖其他策略级别应用的设置。</span><span class="sxs-lookup"><span data-stu-id="19dda-107">Skype for Business Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="19dda-108">业务服务器策略优先顺序的 Skype 是： 用户策略 （大多数影响） 将覆盖站点策略，然后网站策略将覆盖全局策略 （最低影响）。</span><span class="sxs-lookup"><span data-stu-id="19dda-108">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="19dda-109">这意味着，策略设置与策略所影响的对象距离越近，它对该对象的影响力越大。</span><span class="sxs-lookup"><span data-stu-id="19dda-109">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>


> [!NOTE]  
> <span data-ttu-id="19dda-110">即使您没有为组织启用联盟，您可以配置策略以控制联盟的用户访问。</span><span class="sxs-lookup"><span data-stu-id="19dda-110">You can configure policies to control federated user access, even if you have not enabled federation for your organization.</span></span> <span data-ttu-id="19dda-111">但是，您配置的策略实际上是将仅当已为组织启用联盟。</span><span class="sxs-lookup"><span data-stu-id="19dda-111">However, the policies that you configure are in effect only when you have federation enabled for your organization.</span></span> <span data-ttu-id="19dda-112">有关启用联合身份验证的详细信息，请参阅[启用或禁用远程用户访问](../access-edge/enable-or-disable-remote-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="19dda-112">For details about enabling federation, see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span>  <span data-ttu-id="19dda-113">此外，如果您指定一个用户策略控制联盟的用户访问，该策略仅适用于 Skype 业务服务器启用和配置为使用该策略的用户。</span><span class="sxs-lookup"><span data-stu-id="19dda-113">Additionally, if you specify a user policy to control federated user access, the policy applies only to users that are enabled for Skype for Business Server and configured to use the policy.</span></span>


## <a name="to-configure-a-policy-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="19dda-114">配置策略以支持联盟域用户访问</span><span class="sxs-lookup"><span data-stu-id="19dda-114">To configure a policy to support access by users of federated domains</span></span>

1.  <span data-ttu-id="19dda-115">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="19dda-115">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="19dda-116">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="19dda-116">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="19dda-117">在左侧的导航栏中，单击**外部用户访问**，然后单击**外部访问策略**。</span><span class="sxs-lookup"><span data-stu-id="19dda-117">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="19dda-118">在**外部访问策略**页上，执行以下任一操作：</span><span class="sxs-lookup"><span data-stu-id="19dda-118">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="19dda-119">要配置全局策略以支持联盟的用户访问，请单击该全局策略，单击**编辑**，然后单击**显示详细信息**。</span><span class="sxs-lookup"><span data-stu-id="19dda-119">To configure the global policy to support federated user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="19dda-120">若要创建新的站点策略，单击**新建**，然后单击**站点策略**。</span><span class="sxs-lookup"><span data-stu-id="19dda-120">To create a new site policy, click **New**, and then click **Site policy**.</span></span> <span data-ttu-id="19dda-121">在**选择站点**单击列表中的相应站点，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="19dda-121">In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="19dda-122">若要创建一个新用户策略，单击**新建**，然后单击**用户策略**。</span><span class="sxs-lookup"><span data-stu-id="19dda-122">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="19dda-123">在**新外部访问策略**中，创建一个唯一的名称，在**名称**字段，该值指示哪些用户策略介绍 (例如， **EnableFederatedUsers**用户策略启用的联盟的域用户的通信的)。</span><span class="sxs-lookup"><span data-stu-id="19dda-123">In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableFederatedUsers** for a user policy that enables communications for federated domain users).</span></span>
    
      - <span data-ttu-id="19dda-124">若要更改现有策略，单击表中列出的相应策略，单击**编辑**，然后单击**显示详细信息**。</span><span class="sxs-lookup"><span data-stu-id="19dda-124">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="19dda-125">（可选）如果您想要添加或编辑说明，请在**说明**指定策略的信息。</span><span class="sxs-lookup"><span data-stu-id="19dda-125">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="19dda-126">请执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="19dda-126">Do one of the following:</span></span>
    
      - <span data-ttu-id="19dda-127">若要启用联盟的用户访问的策略，请选中**启用与联盟用户的通信**复选框。</span><span class="sxs-lookup"><span data-stu-id="19dda-127">To enable federated user access for the policy, select the **Enable communications with federated users** check box.</span></span>
    
      - <span data-ttu-id="19dda-128">若要禁用联盟的用户访问的策略，请清除**启用与联盟用户的通信**复选框。</span><span class="sxs-lookup"><span data-stu-id="19dda-128">To disable federated user access for the policy, clear the **Enable communications with federated users** check box.</span></span>

7.  <span data-ttu-id="19dda-129">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="19dda-129">Click **Commit**.</span></span>

<span data-ttu-id="19dda-130">若要启用联盟的用户访问，您还必须在组织中启用联盟支持。</span><span class="sxs-lookup"><span data-stu-id="19dda-130">To enable federated user access, you must also enable support for federation in your organization.</span></span> <span data-ttu-id="19dda-131">有关详细信息，请参阅[启用或禁用联盟和公共 IM 连接](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="19dda-131">For details, see [Enable or disable federation and public IM connectivity](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md).</span></span>

<span data-ttu-id="19dda-132">如果这是用户策略，您必须向您希望能够与联盟用户进行协作的用户应用策略。</span><span class="sxs-lookup"><span data-stu-id="19dda-132">If this is a user policy, you must also apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="19dda-133">有关详细信息，请参阅[将外部用户访问策略分配](assign-an-external-user-access-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="19dda-133">For details, see [Assign an external user access policy](assign-an-external-user-access-policy.md).</span></span>

## <a name="to-configure-an-existing-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="19dda-134">若要配置现有策略使用 Windows PowerShell 以支持联盟域用户访问</span><span class="sxs-lookup"><span data-stu-id="19dda-134">To configure an existing policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="19dda-135">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="19dda-135">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="19dda-136">为业务 Server 命令行管理程序启动 Skype： 单击**开始**，单击**所有程序**、 都单击**Skype 业务服务器**，，然后都单击**Skype 的业务 Server Management Shell**。</span><span class="sxs-lookup"><span data-stu-id="19dda-136">Start the Skype for Busines Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="19dda-137">Skype 中键入以下内容的业务 Server 命令行管理程序：</span><span class="sxs-lookup"><span data-stu-id="19dda-137">Type the following in the Skype for Business Server Management Shell:</span></span>
    
    ```
    Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAcess <$true, $false> -EnablePublicCloudAudioVideoAcess <$true, $false> -EnableOutsideAcess <$true, $false>
    ```
       

    > [!TIP]  
    > <span data-ttu-id="19dda-138">参数"EnablePublicCloudAudioVideoAccess"对应的所选内容中没有 Skype 的业务 Server Control Panel</span><span class="sxs-lookup"><span data-stu-id="19dda-138">The parameter “EnablePublicCloudAudioVideoAccess” does not have a corresponding selection in the Skype for Business Server Control Panel</span></span>


## <a name="to-create-a-new-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="19dda-139">若要创建新策略使用 Windows PowerShell 以支持联盟域用户访问</span><span class="sxs-lookup"><span data-stu-id="19dda-139">To create a new policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="19dda-140">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="19dda-140">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="19dda-141">为业务 Server 命令行管理程序启动 Skype： 单击**开始**，单击**所有程序**，都单击**Microsoft Skype 业务服务器**，，然后都单击**Skype 的业务 Server Management Shell**。</span><span class="sxs-lookup"><span data-stu-id="19dda-141">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="19dda-142">Skype 中键入以下内容的业务 Server 命令行管理程序：</span><span class="sxs-lookup"><span data-stu-id="19dda-142">Type the following in the Skype for Business Server Management Shell:</span></span>
    
    ```
    New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    ```
    
    <span data-ttu-id="19dda-143">创建新的站点策略的示例：</span><span class="sxs-lookup"><span data-stu-id="19dda-143">An example of creating a new site policy:</span></span>
    
    ```
    New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    ```


## <a name="to-delete-or-reset-a-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="19dda-144">删除或重置使用 Windows PowerShell 以支持联盟域用户访问策略</span><span class="sxs-lookup"><span data-stu-id="19dda-144">To delete or reset a policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="19dda-145">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="19dda-145">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="19dda-146">Skype 中键入以下内容的业务 Server 命令行管理程序</span><span class="sxs-lookup"><span data-stu-id="19dda-146">Type the following in the Skype for Business Server Management Shell</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>`
    
    <span data-ttu-id="19dda-147">下面举例说明重置全局策略 （全局策略只能有其设置已删除。</span><span class="sxs-lookup"><span data-stu-id="19dda-147">An example of resetting the global policy (The global policy can only have its setting removed.</span></span> <span data-ttu-id="19dda-148">无法删除策略）：</span><span class="sxs-lookup"><span data-stu-id="19dda-148">The policy cannot be deleted):</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity global`
    
    <span data-ttu-id="19dda-149">若要删除的站点策略，请键入：</span><span class="sxs-lookup"><span data-stu-id="19dda-149">To remove a site policy, type:</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity site:Redmond` 
    
    <span data-ttu-id="19dda-150">删除 Redmond 的站点策略。</span><span class="sxs-lookup"><span data-stu-id="19dda-150">Deletes the site policy Redmond.</span></span> <span data-ttu-id="19dda-151">若要删除名为 UserEAPPolicy 的用户策略，请键入：</span><span class="sxs-lookup"><span data-stu-id="19dda-151">To delete a user policy named UserEAPPolicy, type:</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity UserEAPPolicy`


## <a name="see-also"></a><span data-ttu-id="19dda-152">另请参阅</span><span class="sxs-lookup"><span data-stu-id="19dda-152">See Also</span></span>


[<span data-ttu-id="19dda-153">启用或禁用联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="19dda-153">Enable or disable federation and public IM connectivity</span></span>](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md) 

[<span data-ttu-id="19dda-154">分配外部用户访问策略</span><span class="sxs-lookup"><span data-stu-id="19dda-154">Assign an external user access policy</span></span>](assign-an-external-user-access-policy.md)

[<span data-ttu-id="19dda-155">管理组织的 SIP 联盟域</span><span class="sxs-lookup"><span data-stu-id="19dda-155">Manage SIP federated domains for your organization</span></span>](../sip-domains/manage-sip-federated-domains-for-your-organization.md)
 
[<span data-ttu-id="19dda-156">管理组织的 SIP 联盟提供程序</span><span class="sxs-lookup"><span data-stu-id="19dda-156">Manage SIP federated providers for your organization</span></span>](../sip-providers/manage-sip-federated-providers-for-your-organization.md)

[<span data-ttu-id="19dda-157">设置 CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="19dda-157">Set-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsExternalAccessPolicy)  
[<span data-ttu-id="19dda-158">新 CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="19dda-158">New-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsExternalAccessPolicy)  
[<span data-ttu-id="19dda-159">Get-csexternalaccesspolicy</span><span class="sxs-lookup"><span data-stu-id="19dda-159">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="19dda-160">Remove-csexternalaccesspolicy</span><span class="sxs-lookup"><span data-stu-id="19dda-160">Remove-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[<span data-ttu-id="19dda-161">Grant-csexternalaccesspolicy</span><span class="sxs-lookup"><span data-stu-id="19dda-161">Grant-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

