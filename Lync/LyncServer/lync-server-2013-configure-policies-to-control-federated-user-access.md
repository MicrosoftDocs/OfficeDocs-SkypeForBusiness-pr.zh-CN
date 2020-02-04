---
title: Lync Server 2013：配置策略以控制联盟用户访问
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure policies to control federated user access
ms:assetid: 5485e208-81e4-4e59-9aeb-1232c11dd8a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398359(v=OCS.15)
ms:contentKeyID: 48184180
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e1aeb1b29637fd3f4a8add770470069e8b4a6eb8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763284"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-federated-user-access-in-lync-server-2013"></a><span data-ttu-id="3faae-102">在 Lync Server 2013 中配置策略以控制联盟用户访问</span><span class="sxs-lookup"><span data-stu-id="3faae-102">Configure policies to control federated user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3faae-103">_**主题上次修改时间：** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="3faae-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="3faae-104">配置策略以支持与联盟伙伴的通信时，这些策略适用于联盟域的用户。</span><span class="sxs-lookup"><span data-stu-id="3faae-104">When you configure policies to support communications with federated partners, the policies apply to users of federated domains.</span></span> <span data-ttu-id="3faae-105">你可以配置一个或多个外部用户访问策略，以控制联盟域的用户是否可以与 Lync Server 2013 用户协作。</span><span class="sxs-lookup"><span data-stu-id="3faae-105">You can configure one or more external user access policies to control whether users of federated domains can collaborate with your Lync Server 2013 users.</span></span> <span data-ttu-id="3faae-106">若要控制联盟用户访问，可以在全局、网站和用户级别配置策略。</span><span class="sxs-lookup"><span data-stu-id="3faae-106">To control federated user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="3faae-107">在一个策略级别应用的 Lync Server 策略设置可以覆盖在其他策略级别应用的设置。</span><span class="sxs-lookup"><span data-stu-id="3faae-107">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="3faae-108">Lync 服务器策略优先级为：用户策略（最受影响）覆盖网站策略，然后网站策略覆盖全局策略（最不影响）。</span><span class="sxs-lookup"><span data-stu-id="3faae-108">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="3faae-109">这意味着，策略设置与策略所影响的对象距离越近，它对该对象的影响力越大。</span><span class="sxs-lookup"><span data-stu-id="3faae-109">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3faae-110">你可以配置策略来控制联盟用户访问，即使你没有为组织启用联盟也是如此。</span><span class="sxs-lookup"><span data-stu-id="3faae-110">You can configure policies to control federated user access, even if you have not enabled federation for your organization.</span></span> <span data-ttu-id="3faae-111">但是，仅当你的组织启用了联合身份验证时，你配置的策略才有效。</span><span class="sxs-lookup"><span data-stu-id="3faae-111">However, the policies that you configure are in effect only when you have federation enabled for your organization.</span></span> <span data-ttu-id="3faae-112">有关启用联盟的详细信息，请参阅在部署文档或操作文档中<A href="lync-server-2013-enable-or-disable-remote-user-access.md">启用或禁用 Lync Server 2013 中的远程用户访问</A>。</span><span class="sxs-lookup"><span data-stu-id="3faae-112">For details about enabling federation, see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span> <span data-ttu-id="3faae-113">此外，如果你指定用于控制联盟用户访问的用户策略，该策略将仅应用于已启用 Lync Server 2013 的用户，并且配置为使用该策略。</span><span class="sxs-lookup"><span data-stu-id="3faae-113">Additionally, if you specify a user policy to control federated user access, the policy applies only to users that are enabled for Lync Server 2013 and configured to use the policy.</span></span>



</div>

<div>

## <a name="to-configure-a-policy-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="3faae-114">将策略配置为支持由联盟域的用户访问</span><span class="sxs-lookup"><span data-stu-id="3faae-114">To configure a policy to support access by users of federated domains</span></span>

1.  <span data-ttu-id="3faae-115">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="3faae-115">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3faae-116">打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="3faae-116">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3faae-117">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="3faae-117">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3faae-118">在左侧导航栏中，单击 "**外部用户访问**"，然后单击 "**外部访问策略**"。</span><span class="sxs-lookup"><span data-stu-id="3faae-118">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="3faae-119">在 "**外部访问策略**" 页面上，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="3faae-119">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="3faae-120">若要将全局策略配置为支持联合用户访问，请单击全局策略，单击 "**编辑**"，然后单击 "**显示详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="3faae-120">To configure the global policy to support federated user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="3faae-121">若要创建新的网站策略，请单击 "**新建**"，然后单击 "**网站策略**"。</span><span class="sxs-lookup"><span data-stu-id="3faae-121">To create a new site policy, click **New**, and then click **Site policy**.</span></span> <span data-ttu-id="3faae-122">在 "**选择网站**" 中，从列表中单击相应的网站，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="3faae-122">In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="3faae-123">若要创建新的用户策略，请单击 "**新建**"，然后单击 "**用户策略**"。</span><span class="sxs-lookup"><span data-stu-id="3faae-123">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="3faae-124">在 "**新的外部访问策略**" 中，在 "**名称**" 字段中创建一个唯一名称，以指示用户策略所涉及的内容（例如， **EnableFederatedUsers**为联合域用户启用通信的用户策略）。</span><span class="sxs-lookup"><span data-stu-id="3faae-124">In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableFederatedUsers** for a user policy that enables communications for federated domain users).</span></span>
    
      - <span data-ttu-id="3faae-125">若要更改现有策略，请单击表中列出的相应策略，单击 "**编辑**"，然后单击 "**显示详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="3faae-125">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="3faae-126">可选如果要添加或编辑说明，请在 "**说明**" 中指定策略的信息。</span><span class="sxs-lookup"><span data-stu-id="3faae-126">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="3faae-127">请执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="3faae-127">Do one of the following:</span></span>
    
      - <span data-ttu-id="3faae-128">若要为策略启用联盟用户访问权限，请选中 "**启用与联盟用户的通信**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="3faae-128">To enable federated user access for the policy, select the **Enable communications with federated users** check box.</span></span>
    
      - <span data-ttu-id="3faae-129">若要对策略禁用联盟用户访问权限，请清除 "**启用与联盟用户的通信**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="3faae-129">To disable federated user access for the policy, clear the **Enable communications with federated users** check box.</span></span>

7.  <span data-ttu-id="3faae-130">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="3faae-130">Click **Commit**.</span></span>

<span data-ttu-id="3faae-131">若要启用联盟用户访问，还必须在你的组织中启用联合身份验证支持。</span><span class="sxs-lookup"><span data-stu-id="3faae-131">To enable federated user access, you must also enable support for federation in your organization.</span></span> <span data-ttu-id="3faae-132">有关详细信息，请参阅[在 Lync Server 2013 中启用或禁用联盟和公共 IM 连接](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="3faae-132">For details, see [Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md).</span></span>

<span data-ttu-id="3faae-133">如果这是用户策略，你还必须将策略应用于你希望能够与联盟用户协作的用户。</span><span class="sxs-lookup"><span data-stu-id="3faae-133">If this is a user policy, you must also apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="3faae-134">有关详细信息，请参阅[在 Lync Server 2013 中将外部用户访问策略分配给启用 Lync 的用户](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)。</span><span class="sxs-lookup"><span data-stu-id="3faae-134">For details, see [Assign an external user access policy to a Lync enabled user in Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md).</span></span>

</div>

<div>

## <a name="to-configure-an-existing-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="3faae-135">使用 Windows PowerShell 配置现有策略以支持联盟域的用户访问</span><span class="sxs-lookup"><span data-stu-id="3faae-135">To configure an existing policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="3faae-136">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="3faae-136">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3faae-137">启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="3faae-137">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="3faae-138">在 Lync Server 命令行管理程序中键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="3faae-138">Type the following in the Lync Server Management Shell:</span></span>
    
        Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    
    <span data-ttu-id="3faae-139">将联盟用户访问的全局策略设置为 "已启用"、"已启用"、"已启用"、"公共访问权限启用" 和 "公共提供者访问" 的全局策略，并授予支持它的公共提供商的音频和视频功能的示例命令：</span><span class="sxs-lookup"><span data-stu-id="3faae-139">An example command that will set the global policy for Federated user access to enabled, XMPP domain access to enabled, Remote user access to enabled, Public provider access to enabled, and grant the ability to use audio and video for public providers that support it:</span></span>
    
        Set-CsExternalAccessPolicy -Identity global -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="3faae-140">在 Lync Server "控制面板" 中，参数 "EnablePublicCloudAudioVideoAccess" 没有对应的选择</span><span class="sxs-lookup"><span data-stu-id="3faae-140">The parameter “EnablePublicCloudAudioVideoAccess” does not have a corresponding selection in the Lync Server Control Panel</span></span>

    
    </div>

</div>

<div>

## <a name="to-create-a-new-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="3faae-141">使用 Windows PowerShell 创建新策略以支持联盟域的用户访问</span><span class="sxs-lookup"><span data-stu-id="3faae-141">To create a new policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="3faae-142">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="3faae-142">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3faae-143">启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="3faae-143">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="3faae-144">在 Lync Server 命令行管理程序中键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="3faae-144">Type the following in the Lync Server Management Shell:</span></span>
    
        New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    
    <span data-ttu-id="3faae-145">创建新网站策略的示例：</span><span class="sxs-lookup"><span data-stu-id="3faae-145">An example of creating a new site policy:</span></span>
    
        New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true

</div>

<div>

## <a name="to-delete-or-reset-a-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="3faae-146">使用 Windows PowerShell 删除或重置策略以支持联盟域的用户访问</span><span class="sxs-lookup"><span data-stu-id="3faae-146">To delete or reset a policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="3faae-147">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="3faae-147">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3faae-148">在 Lync Server 命令行管理程序中键入以下命令</span><span class="sxs-lookup"><span data-stu-id="3faae-148">Type the following in the Lync Server Management Shell</span></span>
    
        Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy> 
    
    <span data-ttu-id="3faae-149">重置全局策略（全局策略只能删除其设置）的示例。</span><span class="sxs-lookup"><span data-stu-id="3faae-149">An example of resetting the global policy (The global policy can only have its setting removed.</span></span> <span data-ttu-id="3faae-150">无法删除策略：</span><span class="sxs-lookup"><span data-stu-id="3faae-150">The policy cannot be deleted):</span></span>
    
        Remove-CsExternalAccessPolicy -Identity global 
    
    <span data-ttu-id="3faae-151">若要删除网站策略，请键入：</span><span class="sxs-lookup"><span data-stu-id="3faae-151">To remove a site policy, type:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity site:Redmond 
    
    <span data-ttu-id="3faae-152">删除网站策略 Redmond。</span><span class="sxs-lookup"><span data-stu-id="3faae-152">Deletes the site policy Redmond.</span></span> <span data-ttu-id="3faae-153">若要删除名为 UserEAPPolicy 的用户策略，请键入：</span><span class="sxs-lookup"><span data-stu-id="3faae-153">To delete a user policy named UserEAPPolicy, type:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity UserEAPPolicy

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3faae-154">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3faae-154">See Also</span></span>


[<span data-ttu-id="3faae-155">在 Lync Server 2013 中启用或禁用联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="3faae-155">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
[<span data-ttu-id="3faae-156">在 Lync Server 2013 中将外部用户访问策略分配到启用 Lync 的用户</span><span class="sxs-lookup"><span data-stu-id="3faae-156">Assign an external user access policy to a Lync enabled user in Lync Server 2013</span></span>](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)  


[<span data-ttu-id="3faae-157">在 Lync Server 2013 中管理组织的 SIP 联盟域</span><span class="sxs-lookup"><span data-stu-id="3faae-157">Manage SIP federated domains for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[<span data-ttu-id="3faae-158">在 Lync Server 2013 中管理组织的 SIP 联盟提供程序</span><span class="sxs-lookup"><span data-stu-id="3faae-158">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
[<span data-ttu-id="3faae-159">Set-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="3faae-159">Set-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy)  
[<span data-ttu-id="3faae-160">新-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="3faae-160">New-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsExternalAccessPolicy)  
[<span data-ttu-id="3faae-161">CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="3faae-161">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="3faae-162">Remove-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="3faae-162">Remove-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[<span data-ttu-id="3faae-163">授权-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="3faae-163">Grant-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

