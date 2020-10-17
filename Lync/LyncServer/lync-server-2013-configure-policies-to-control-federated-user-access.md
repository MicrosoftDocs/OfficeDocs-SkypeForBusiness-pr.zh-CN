---
title: Lync Server 2013：配置策略以控制联盟用户访问
description: Lync Server 2013：配置策略以控制联合用户访问。
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
ms.openlocfilehash: d69f35baa16086b0c4e93a2a015474f87e08b736
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548738"
---
# <a name="configure-policies-to-control-federated-user-access-in-lync-server-2013"></a><span data-ttu-id="69365-103">在 Lync Server 2013 中配置用于控制联合用户访问的策略</span><span class="sxs-lookup"><span data-stu-id="69365-103">Configure policies to control federated user access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="69365-104">_**上次修改的主题：** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="69365-104">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="69365-105">如果将策略配置为支持与联盟伙伴进行通信，则策略将适用于联盟域用户。</span><span class="sxs-lookup"><span data-stu-id="69365-105">When you configure policies to support communications with federated partners, the policies apply to users of federated domains.</span></span> <span data-ttu-id="69365-106">您可以配置一个或多个外部用户访问策略，以控制联盟域的用户是否可以与 Lync Server 2013 用户进行协作。</span><span class="sxs-lookup"><span data-stu-id="69365-106">You can configure one or more external user access policies to control whether users of federated domains can collaborate with your Lync Server 2013 users.</span></span> <span data-ttu-id="69365-107">要控制联盟用户访问，可以在全局、站点和用户级别配置策略。</span><span class="sxs-lookup"><span data-stu-id="69365-107">To control federated user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="69365-108">在一个策略级别应用的 Lync Server 策略设置可以覆盖在另一个策略级别应用的设置。</span><span class="sxs-lookup"><span data-stu-id="69365-108">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="69365-109">Lync Server 策略优先级为：用户策略 (影响最大的) 替代网站策略，然后网站策略将覆盖全局策略 (最小影响) 。</span><span class="sxs-lookup"><span data-stu-id="69365-109">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="69365-110">这意味着，策略设置越接近策略影响的对象，它对对象的影响就越大。</span><span class="sxs-lookup"><span data-stu-id="69365-110">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="69365-111">即使没有为组织启用联盟，也可以配置控制联盟用户访问的策略。</span><span class="sxs-lookup"><span data-stu-id="69365-111">You can configure policies to control federated user access, even if you have not enabled federation for your organization.</span></span> <span data-ttu-id="69365-112">但是，只有为组织启用联盟后，配置的策略才会生效。</span><span class="sxs-lookup"><span data-stu-id="69365-112">However, the policies that you configure are in effect only when you have federation enabled for your organization.</span></span> <span data-ttu-id="69365-113">有关启用联合的详细信息，请参阅部署文档或操作文档中的在 <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Lync Server 2013 中启用或禁用远程用户访问</A> 。</span><span class="sxs-lookup"><span data-stu-id="69365-113">For details about enabling federation, see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span> <span data-ttu-id="69365-114">此外，如果您指定了用于控制联合用户访问的用户策略，则该策略仅适用于启用了 Lync Server 2013 的用户并配置为使用该策略。</span><span class="sxs-lookup"><span data-stu-id="69365-114">Additionally, if you specify a user policy to control federated user access, the policy applies only to users that are enabled for Lync Server 2013 and configured to use the policy.</span></span>



</div>

<div>

## <a name="to-configure-a-policy-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="69365-115">配置策略以支持联盟域用户访问</span><span class="sxs-lookup"><span data-stu-id="69365-115">To configure a policy to support access by users of federated domains</span></span>

1.  <span data-ttu-id="69365-116">从作为 RTCUniversalServerAdmins 组成员的用户帐户 (或具有等效的用户权限) 或分配给 CsAdministrator 角色，请登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="69365-116">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="69365-117">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="69365-117">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="69365-118">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="69365-118">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="69365-119">在左侧导航栏中，单击“外部用户访问”\*\*\*\*，然后单击“外部访问策略”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="69365-119">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="69365-120">在“外部访问策略”\*\*\*\* 页上，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="69365-120">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="69365-121">要将全局策略配置为支持联盟用户访问，请单击该全局策略，再单击“编辑”\*\*\*\*，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="69365-121">To configure the global policy to support federated user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="69365-p104">要创建新的站点策略，请单击“新建”\*\*\*\*，然后单击“站点策略”\*\*\*\*。在“选择站点”\*\*\*\* 中，单击列表中相应的站点，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="69365-p104">To create a new site policy, click **New**, and then click **Site policy**. In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="69365-p105">要创建新的用户策略，请单击“新建”\*\*\*\*，然后单击“用户策略”\*\*\*\*。在“新建外部访问策略”\*\*\*\* 的“名称”\*\*\*\* 字段中，创建一个唯一的名称以指示用户策略的作用范围（例如，**EnableFederatedUsers** 代表启用联盟域用户通信的用户策略）。</span><span class="sxs-lookup"><span data-stu-id="69365-p105">To create a new user policy, click **New**, and then click **User policy**. In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableFederatedUsers** for a user policy that enables communications for federated domain users).</span></span>
    
      - <span data-ttu-id="69365-126">要更改现有的策略，请单击表中列出的相应策略，再单击“编辑”\*\*\*\*，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="69365-126">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="69365-127">（可选）如果要添加或编辑说明，请在“说明”\*\*\*\* 中为策略指定相应的信息。</span><span class="sxs-lookup"><span data-stu-id="69365-127">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="69365-128">执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="69365-128">Do one of the following:</span></span>
    
      - <span data-ttu-id="69365-129">要为策略启用联盟用户访问，请选中“启用与联盟用户的通信”\*\*\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="69365-129">To enable federated user access for the policy, select the **Enable communications with federated users** check box.</span></span>
    
      - <span data-ttu-id="69365-130">要为策略禁用联盟用户访问，请清除“启用与联盟用户的通信”\*\*\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="69365-130">To disable federated user access for the policy, clear the **Enable communications with federated users** check box.</span></span>

7.  <span data-ttu-id="69365-131">单击“提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="69365-131">Click **Commit**.</span></span>

<span data-ttu-id="69365-132">要启用联盟用户访问，还必须在组织中启用对联盟的支持。</span><span class="sxs-lookup"><span data-stu-id="69365-132">To enable federated user access, you must also enable support for federation in your organization.</span></span> <span data-ttu-id="69365-133">有关详细信息，请参阅 [在 Lync Server 2013 中启用或禁用联盟和公共 IM 连接](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="69365-133">For details, see [Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md).</span></span>

<span data-ttu-id="69365-134">如果这是一个用户策略，则还必须将此策略应用于希望其可以与联盟用户进行协作的用户。</span><span class="sxs-lookup"><span data-stu-id="69365-134">If this is a user policy, you must also apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="69365-135">有关详细信息，请参阅 [在 Lync Server 2013 中向启用 Lync 的用户分配外部用户访问策略](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)。</span><span class="sxs-lookup"><span data-stu-id="69365-135">For details, see [Assign an external user access policy to a Lync enabled user in Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md).</span></span>

</div>

<div>

## <a name="to-configure-an-existing-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="69365-136">使用 Windows PowerShell 配置现有策略以支持由联盟域的用户进行访问</span><span class="sxs-lookup"><span data-stu-id="69365-136">To configure an existing policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="69365-137">从作为 RTCUniversalServerAdmins 组成员的用户帐户 (或具有等效的用户权限) 或分配给 CsAdministrator 角色，请登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="69365-137">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="69365-138">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="69365-138">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="69365-139">在 Lync Server 命令行管理程序中键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="69365-139">Type the following in the Lync Server Management Shell:</span></span>
    
        Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    
    <span data-ttu-id="69365-140">一个示例命令，该命令可将针对联盟用户访问、XMPP 域访问、远程用户访问、公共提供程序访问的全局策略设置为已启用，并允许对支持音频和视频的公共提供程序使用这些音频和视频：</span><span class="sxs-lookup"><span data-stu-id="69365-140">An example command that will set the global policy for Federated user access to enabled, XMPP domain access to enabled, Remote user access to enabled, Public provider access to enabled, and grant the ability to use audio and video for public providers that support it:</span></span>
    
        Set-CsExternalAccessPolicy -Identity global -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="69365-141">"EnablePublicCloudAudioVideoAccess" 参数在 Lync Server 控制面板中没有对应的选择</span><span class="sxs-lookup"><span data-stu-id="69365-141">The parameter “EnablePublicCloudAudioVideoAccess” does not have a corresponding selection in the Lync Server Control Panel</span></span>

    
    </div>

</div>

<div>

## <a name="to-create-a-new-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="69365-142">使用 Windows PowerShell 创建新策略以支持由联盟域的用户进行访问</span><span class="sxs-lookup"><span data-stu-id="69365-142">To create a new policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="69365-143">从作为 RTCUniversalServerAdmins 组成员的用户帐户 (或具有等效的用户权限) 或分配给 CsAdministrator 角色，请登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="69365-143">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="69365-144">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="69365-144">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="69365-145">在 Lync Server 命令行管理程序中键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="69365-145">Type the following in the Lync Server Management Shell:</span></span>
    
        New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    
    <span data-ttu-id="69365-146">创建新站点策略的示例：</span><span class="sxs-lookup"><span data-stu-id="69365-146">An example of creating a new site policy:</span></span>
    
        New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true

</div>

<div>

## <a name="to-delete-or-reset-a-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="69365-147">使用 Windows PowerShell 删除或重置策略以支持由联盟域的用户进行访问</span><span class="sxs-lookup"><span data-stu-id="69365-147">To delete or reset a policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="69365-148">从作为 RTCUniversalServerAdmins 组成员的用户帐户 (或具有等效的用户权限) 或分配给 CsAdministrator 角色，请登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="69365-148">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="69365-149">在 Lync Server 命令行管理程序中键入以下命令</span><span class="sxs-lookup"><span data-stu-id="69365-149">Type the following in the Lync Server Management Shell</span></span>
    
        Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy> 
    
    <span data-ttu-id="69365-p108">重置全局策略的示例（只能删除全局策略的设置，而无法删除全局策略本身）：</span><span class="sxs-lookup"><span data-stu-id="69365-p108">An example of resetting the global policy (The global policy can only have its setting removed. The policy cannot be deleted):</span></span>
    
        Remove-CsExternalAccessPolicy -Identity global 
    
    <span data-ttu-id="69365-152">若要删除站点策略，请键入：</span><span class="sxs-lookup"><span data-stu-id="69365-152">To remove a site policy, type:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity site:Redmond 
    
    <span data-ttu-id="69365-153">删除站点策略 Redmond。</span><span class="sxs-lookup"><span data-stu-id="69365-153">Deletes the site policy Redmond.</span></span> <span data-ttu-id="69365-154">若要删除名为 UserEAPPolicy 的用户策略，请键入：</span><span class="sxs-lookup"><span data-stu-id="69365-154">To delete a user policy named UserEAPPolicy, type:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity UserEAPPolicy

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="69365-155">另请参阅</span><span class="sxs-lookup"><span data-stu-id="69365-155">See Also</span></span>


[<span data-ttu-id="69365-156">在 Lync Server 2013 中启用或禁用联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="69365-156">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
[<span data-ttu-id="69365-157">在 Lync Server 2013 中将外部用户访问策略分配给启用 Lync 的用户</span><span class="sxs-lookup"><span data-stu-id="69365-157">Assign an external user access policy to a Lync enabled user in Lync Server 2013</span></span>](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)  


[<span data-ttu-id="69365-158">在 Lync Server 2013 中管理组织的 SIP 联盟域</span><span class="sxs-lookup"><span data-stu-id="69365-158">Manage SIP federated domains for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[<span data-ttu-id="69365-159">在 Lync Server 2013 中管理组织的 SIP 联合提供程序</span><span class="sxs-lookup"><span data-stu-id="69365-159">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
[<span data-ttu-id="69365-160">Set-csexternalaccesspolicy</span><span class="sxs-lookup"><span data-stu-id="69365-160">Set-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy)  
[<span data-ttu-id="69365-161">新 Set-csexternalaccesspolicy</span><span class="sxs-lookup"><span data-stu-id="69365-161">New-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsExternalAccessPolicy)  
[<span data-ttu-id="69365-162">Set-csexternalaccesspolicy</span><span class="sxs-lookup"><span data-stu-id="69365-162">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="69365-163">Set-csexternalaccesspolicy</span><span class="sxs-lookup"><span data-stu-id="69365-163">Remove-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[<span data-ttu-id="69365-164">Grant-Set-csexternalaccesspolicy</span><span class="sxs-lookup"><span data-stu-id="69365-164">Grant-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

