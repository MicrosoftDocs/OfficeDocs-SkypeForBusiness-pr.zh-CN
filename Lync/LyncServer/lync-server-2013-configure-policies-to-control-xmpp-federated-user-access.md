---
title: Lync Server 2013：配置策略以控制 XMPP 联盟用户访问
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure policies to control XMPP federated user access
ms:assetid: 0fe0ff75-e52a-4e3e-923a-64f6412ac4e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552446(v=OCS.15)
ms:contentKeyID: 48679557
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ec90a1b079935713ce6f13e7b74763e7004dedf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837343"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-xmpp-federated-user-access-in-lync-server-2013"></a><span data-ttu-id="e5321-102">在 Lync Server 2013 中配置策略以控制 XMPP 联盟用户访问</span><span class="sxs-lookup"><span data-stu-id="e5321-102">Configure policies to control XMPP federated user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5321-103">_**主题上次修改时间:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="e5321-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="e5321-104">本文档是预备文档，可能随时更改。</span><span class="sxs-lookup"><span data-stu-id="e5321-104">This is preliminary documentation and is subject to change.</span></span> <span data-ttu-id="e5321-105">空白主题均以占位符的形式包含在内。</span><span class="sxs-lookup"><span data-stu-id="e5321-105">Blank topics are included as placeholders.</span></span>

<span data-ttu-id="e5321-106">当您为支持可扩展消息和状态协议 (XMPP) 联盟伙伴的策略配置策略时, 这些策略适用于 XMPP 联盟域的用户, 但不适用于会话初始协议 (SIP) 的用户 (IM) 服务提供商(例如, Windows Live) 或 SIP 联盟域。</span><span class="sxs-lookup"><span data-stu-id="e5321-106">When you configure policies for support of extensible messaging and presence protocol (XMPP) federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers (for example, Windows Live), or SIP federated domains.</span></span> <span data-ttu-id="e5321-107">为你希望允许用户添加联系人并与之通信的每个 XMPP 联盟域配置**XMPP 联盟合作伙伴**。</span><span class="sxs-lookup"><span data-stu-id="e5321-107">You configure an **XMPP Federated Partner** for each XMPP federated domain that you want to allow your users to add contacts and communicate with.</span></span> <span data-ttu-id="e5321-108">XMPP 联盟伙伴策略仅在单个作用域内可用, 但它不是作为全局策略定义的作为全局策略。</span><span class="sxs-lookup"><span data-stu-id="e5321-108">XMPP federated partners policies are only available in a single scope, though it is not defined as a global policy, acts as a global policy.</span></span> <span data-ttu-id="e5321-109">若要为 XMPP 联合合作伙伴定义全局、网站或用户策略, 请通过首先创建和配置所需作用域的外部访问策略来配置策略范围。</span><span class="sxs-lookup"><span data-stu-id="e5321-109">To define a global, site or user policy for XMPP Federation Partners, you configure the policy scope by first creating and configuring the External Access Policy for the scope you require.</span></span> <span data-ttu-id="e5321-110">有关可针对外部访问和联盟配置的策略类型的详细信息, 请参阅在操作文档中[管理 Lync Server 2013 的联合身份验证和外部访问](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="e5321-110">For details about the types of policies that you can configure for external access and federation, see [Managing federation and external access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md) in the Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e5321-111">所有<STRONG>联盟和外部访问</STRONG>策略均通过带内配置应用。</span><span class="sxs-lookup"><span data-stu-id="e5321-111">All <STRONG>Federation and External Access</STRONG> policies are applied through in-band provisioning.</span></span> <span data-ttu-id="e5321-112">在登录期间, 应用于用户、属于网站或全局范围内的策略将传递给客户端。</span><span class="sxs-lookup"><span data-stu-id="e5321-112">The policies that apply to the user, belong to a site, or are global in scope are communicated to the client during login.</span></span> <span data-ttu-id="e5321-113">你可以配置策略来控制 XMPP 联盟合作伙伴的访问权限, 即使你没有为你的组织启用 XMPP 联盟也是如此。</span><span class="sxs-lookup"><span data-stu-id="e5321-113">You can configure policies to control XMPP federated partner access, even if you have not enabled XMPP federation for your organization.</span></span> <span data-ttu-id="e5321-114">但是, 仅当为你的组织部署、启用和配置了 XMPP 合作伙伴联合身份验证时, 你配置的策略才会生效。</span><span class="sxs-lookup"><span data-stu-id="e5321-114">However, the policies that you configure take effect only when you have XMPP partner federation deployed, enabled and configured for your organization.</span></span> <span data-ttu-id="e5321-115">有关部署和配置 XMPP 合作伙伴联盟的详细信息, 请参阅部署文档中的<A href="lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md">Lync Server 2013 中的 "配置 SIP 联合"、"XMPP 联盟" 和 "公共即时消息</A>"。</span><span class="sxs-lookup"><span data-stu-id="e5321-115">For details about deploying and configuring XMPP partner federation, see <A href="lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md">Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013</A> in the Deployment documentation.</span></span> <span data-ttu-id="e5321-116">此外, 如果在外部访问策略中指定了用于控制 XMPP 联盟伙伴的用户策略, 该策略将仅应用于已启用 Lync Server 2013 的用户, 并且配置为使用该策略。</span><span class="sxs-lookup"><span data-stu-id="e5321-116">Additionally, if you specify a user policy in External Access Policy to control XMPP federated partners, the policy applies only to users that are enabled for Lync Server 2013 and configured to use the policy.</span></span>



</div>

<div>

## <a name="to-edit-a-global-policy-for-xmpp-federated-partners"></a><span data-ttu-id="e5321-117">编辑 XMPP 联盟合作伙伴的全局策略</span><span class="sxs-lookup"><span data-stu-id="e5321-117">To edit a global policy for XMPP federated partners</span></span>

1.  <span data-ttu-id="e5321-118">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="e5321-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e5321-119">打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="e5321-119">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e5321-120">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="e5321-120">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e5321-121">在左侧导航栏中, 单击 "**外部用户访问**", 然后单击 "**外部访问策略**"。</span><span class="sxs-lookup"><span data-stu-id="e5321-121">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="e5321-122">在 "**外部访问策略**" 页面上, 对全局策略执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="e5321-122">On the **External Access Policy** page, do the following for the global policy:</span></span>

5.  <span data-ttu-id="e5321-123">单击 "全局策略", 单击 "**编辑**", 然后单击 "显示详细信息"。</span><span class="sxs-lookup"><span data-stu-id="e5321-123">Click the global policy, click **Edit**, and then click Show details.</span></span>

6.  <span data-ttu-id="e5321-124">提供全局策略的说明 (可选)。</span><span class="sxs-lookup"><span data-stu-id="e5321-124">Provide a description for the Global policy (optional).</span></span>

7.  <span data-ttu-id="e5321-125">选择 "**启用与联盟用户的通信**"。</span><span class="sxs-lookup"><span data-stu-id="e5321-125">Select **Enable communications with federated users**.</span></span>

8.  <span data-ttu-id="e5321-126">选择 "**启用与 XMPP 联盟用户的通信**"。</span><span class="sxs-lookup"><span data-stu-id="e5321-126">Select **Enable communications with XMPP federated users**.</span></span>

9.  <span data-ttu-id="e5321-127">单击 "**提交**" 以将更改保存到全局策略。</span><span class="sxs-lookup"><span data-stu-id="e5321-127">Click **Commit** to save your changes to the Global policy.</span></span>

</div>

<div>

## <a name="to-create-a-site-or-user-policy-for-xmpp-federated-partners"></a><span data-ttu-id="e5321-128">为 XMPP 联盟合作伙伴创建网站或用户策略</span><span class="sxs-lookup"><span data-stu-id="e5321-128">To create a site or user policy for XMPP federated partners</span></span>

1.  <span data-ttu-id="e5321-129">单击 "**新建**", 然后单击 "**网站策略**" 或 "**用户策略**"。</span><span class="sxs-lookup"><span data-stu-id="e5321-129">Click **New**, and then click **Site policy** or **User policy**.</span></span> <span data-ttu-id="e5321-130">在 "**选择网站**" 中, 从列表中单击相应的网站, 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="e5321-130">In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>

2.  <span data-ttu-id="e5321-131">提供网站策略的说明 (可选)。</span><span class="sxs-lookup"><span data-stu-id="e5321-131">Provide a description for the Site policy (optional).</span></span>

3.  <span data-ttu-id="e5321-132">在 "网站或用户策略" 中, 选择 "**启用与联盟用户的通信**"。</span><span class="sxs-lookup"><span data-stu-id="e5321-132">In the site or user policy, select **Enable communications with federated users**.</span></span>

4.  <span data-ttu-id="e5321-133">选择 "**启用与 XMPP 联盟用户的通信**"。</span><span class="sxs-lookup"><span data-stu-id="e5321-133">Select **Enable communications with XMPP federated users**.</span></span>

5.  <span data-ttu-id="e5321-134">单击 "**提交**" 将更改保存到 "网站" 或 "用户策略"。</span><span class="sxs-lookup"><span data-stu-id="e5321-134">Click **Commit** to save your changes to the site or user policy.</span></span>

</div>

<div>

## <a name="to-edit-an-existing-policy-for-xmpp-federated-partners"></a><span data-ttu-id="e5321-135">编辑 XMPP 联盟合作伙伴的现有策略</span><span class="sxs-lookup"><span data-stu-id="e5321-135">To edit an existing policy for XMPP federated partners</span></span>

1.  <span data-ttu-id="e5321-136">若要更改现有策略, 请在列表中选择相应的策略, 单击 "**编辑**", 然后单击 "**显示详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="e5321-136">To change an existing policy, select the appropriate policy in the list, click **Edit**, and then click **Show details**.</span></span>

2.  <span data-ttu-id="e5321-137">更改或更新策略的说明 (可选)。</span><span class="sxs-lookup"><span data-stu-id="e5321-137">Change or update the description for the policy (optional).</span></span>

3.  <span data-ttu-id="e5321-138">选择或取消选择 "**启用与联盟用户的通信**"。</span><span class="sxs-lookup"><span data-stu-id="e5321-138">Select or unselect **Enable communications with federated users**.</span></span>

4.  <span data-ttu-id="e5321-139">选择或取消选择 "**启用与 XMPP 联盟用户的通信**"。</span><span class="sxs-lookup"><span data-stu-id="e5321-139">Select or unselect **Enable communications with XMPP federated users**.</span></span>

5.  <span data-ttu-id="e5321-140">单击 "**提交**" 以保存对策略所做的更改。</span><span class="sxs-lookup"><span data-stu-id="e5321-140">Click **Commit** to save your changes to the policy.</span></span>

</div>

<div>

## <a name="to-edit-an-existing-policy-for-xmpp-federated-partners-by-using-windows-powershell"></a><span data-ttu-id="e5321-141">使用 Windows PowerShell 编辑 XMPP 联盟合作伙伴的现有策略</span><span class="sxs-lookup"><span data-stu-id="e5321-141">To edit an existing policy for XMPP federated partners by using Windows PowerShell</span></span>

1.  <span data-ttu-id="e5321-142">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="e5321-142">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e5321-143">启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="e5321-143">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="e5321-144">在 Lync Server 命令行管理程序中键入以下内容:</span><span class="sxs-lookup"><span data-stu-id="e5321-144">Type the following in the Lync Server Management Shell:</span></span>
    
        Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    <span data-ttu-id="e5321-145">将联盟用户访问的全局策略设置为 True (enabled), 并将 XMPP 域访问设置为 True (已启用) 的示例命令:</span><span class="sxs-lookup"><span data-stu-id="e5321-145">An example command that will set the global policy for Federated user access to True (enabled) and XMPP domain access to True (enabled):</span></span>
    
        Set-CsExternalAccessPolicy -Identity global -EnableFederationAccess $true -EnableXmppAccess $true

</div>

<div>

## <a name="to-create-a-site-or-user-policy-for-xmpp-federated-partners-using-windows-powershell"></a><span data-ttu-id="e5321-146">使用 Windows PowerShell 为 XMPP 联盟合作伙伴创建网站或用户策略</span><span class="sxs-lookup"><span data-stu-id="e5321-146">To create a site or user policy for XMPP federated partners using Windows PowerShell</span></span>

1.  <span data-ttu-id="e5321-147">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="e5321-147">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e5321-148">启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="e5321-148">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="e5321-149">在 Lync Server 命令行管理程序中键入以下内容:</span><span class="sxs-lookup"><span data-stu-id="e5321-149">Type the following in the Lync Server Management Shell:</span></span>
    
        New-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    <span data-ttu-id="e5321-150">一个示例命令, 将为 Redmond 用户访问启用和 XMPP 域访问启用的 "Redmond" 网站设置网站策略。</span><span class="sxs-lookup"><span data-stu-id="e5321-150">An example command that will set a site policy for the Redmond site for Federated user access to enabled and XMPP domain access to enabled:</span></span>
    
        New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true

</div>

<div>

## <a name="to-delete-an-existing-policy-for-xmpp-federated-partners-by-using-windows-powershell"></a><span data-ttu-id="e5321-151">使用 Windows PowerShell 删除 XMPP 联盟合作伙伴的现有策略</span><span class="sxs-lookup"><span data-stu-id="e5321-151">To delete an existing policy for XMPP federated partners by using Windows PowerShell</span></span>

1.  <span data-ttu-id="e5321-152">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="e5321-152">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e5321-153">启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="e5321-153">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="e5321-154">在 Lync Server 命令行管理程序中键入以下内容:</span><span class="sxs-lookup"><span data-stu-id="e5321-154">Type the following in the Lync Server Management Shell:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>
    
    <span data-ttu-id="e5321-155">将删除用户策略的示例命令:</span><span class="sxs-lookup"><span data-stu-id="e5321-155">An example command that will delete a user policy:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity EAPUserPolicySetXMPP

4.  <span data-ttu-id="e5321-156">将全局策略重置为默认值的示例命令:</span><span class="sxs-lookup"><span data-stu-id="e5321-156">An example command that will reset the global policy to defaults:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity global

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e5321-157">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e5321-157">See Also</span></span>


[<span data-ttu-id="e5321-158">在 Lync Server 2013 中将外部用户访问策略分配到启用 Lync 的用户</span><span class="sxs-lookup"><span data-stu-id="e5321-158">Assign an external user access policy to a Lync enabled user in Lync Server 2013</span></span>](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)  
[<span data-ttu-id="e5321-159">在 Lync Server 2013 中启用或禁用联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="e5321-159">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  


[<span data-ttu-id="e5321-160">在 Lync Server 2013 中管理组织的 XMPP 联盟伙伴</span><span class="sxs-lookup"><span data-stu-id="e5321-160">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
[<span data-ttu-id="e5321-161">Set-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="e5321-161">Set-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy)  
[<span data-ttu-id="e5321-162">新-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="e5321-162">New-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsExternalAccessPolicy)  
[<span data-ttu-id="e5321-163">CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="e5321-163">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="e5321-164">Remove-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="e5321-164">Remove-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[<span data-ttu-id="e5321-165">授权-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="e5321-165">Grant-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

