---
title: Lync Server 2013：启用或禁用联盟和公共 IM 连接
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable federation and public IM connectivity
ms:assetid: 8ec58f4b-9f6d-47b4-a187-d18a83fe4577
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182549(v=OCS.15)
ms:contentKeyID: 48184813
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c94b75aff1b79650adc846d3d761580e9429035d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526789"
---
# <a name="enable-or-disable-federation-and-public-im-connectivity-in-lync-server-2013"></a><span data-ttu-id="20f8e-102">在 Lync Server 2013 中启用或禁用联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="20f8e-102">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="20f8e-103">_**上次修改的主题：** 2013-06-24_</span><span class="sxs-lookup"><span data-stu-id="20f8e-103">_**Topic Last Modified:** 2013-06-24_</span></span>

<span data-ttu-id="20f8e-104">要使具有受信任客户或伙伴组织帐户的用户（包括伙伴域用户和支持的公共即时消息 (IM) 提供商用户）能够与组织中的用户进行协作，必须具有联盟支持。</span><span class="sxs-lookup"><span data-stu-id="20f8e-104">Support for federation is required to enable users who have an account with a trusted customer or partner organization, including partner domains and users of public instant messaging (IM) provider users that you support, to collaborate with users in your organization.</span></span> <span data-ttu-id="20f8e-105">此外，在使用托管 Exchange 服务提供商以便为其邮箱位于托管 Exchange 服务（例如，Microsoft Exchange Online）上的企业语音用户提供语音邮件时，也需要使用联盟。</span><span class="sxs-lookup"><span data-stu-id="20f8e-105">Federation is also required to use a hosted Exchange service provider to provide voice mail to Enterprise Voice users whose mailboxes are located on a hosted Exchange service such as Microsoft Exchange Online.</span></span> <span data-ttu-id="20f8e-106">建立与这些外部域的信任关系后，您可以授权这些域中的用户访问您的部署并参与 Lync Server 通信。</span><span class="sxs-lookup"><span data-stu-id="20f8e-106">When you have established a trust relationship with these external domains, you can authorize users in those domains to access your deployment and participate in Lync Server communications.</span></span> <span data-ttu-id="20f8e-107">这种信任关系称为联盟，它与 Active Directory 信任关系无关，也不依赖于 Active Directory 信任关系。</span><span class="sxs-lookup"><span data-stu-id="20f8e-107">This trust relationship is called a federation and it is not related to, or dependent upon, an Active Directory trust relationship.</span></span>

<span data-ttu-id="20f8e-p102">要支持联盟域用户访问，必须启用联盟。如果为组织启用联盟，则还必须指定是否实现以下选项：</span><span class="sxs-lookup"><span data-stu-id="20f8e-p102">To support access by users of federated domains, you must enable federation. If you enable federation for your organization, you must also specify whether to implement the following options:</span></span>

  - <span data-ttu-id="20f8e-110">**启用合作伙伴域发现**    如果启用此选项，Lync Server 将使用域名系统 (DNS) 记录以尝试发现未在 "允许的域" 列表中列出的域，并自动评估已发现的联盟伙伴的传入流量，并根据信任级别、流量量和管理员设置来限制或阻止该流量。</span><span class="sxs-lookup"><span data-stu-id="20f8e-110">**Enable partner domain discovery**   If you enable this option, Lync Server uses Domain Name System (DNS) records to try to discover domains not listed in the allowed domains list, automatically evaluating incoming traffic from discovered federated partners and limiting or blocking that traffic based on trust level, amount of traffic, and administrator settings.</span></span> <span data-ttu-id="20f8e-111">如果未选择此选项，则仅对您在允许的域列表中包含的域中的用户启用联合用户访问权限。</span><span class="sxs-lookup"><span data-stu-id="20f8e-111">If you do not select this option, federated user access is enabled only for users in the domains that you include on the allowed domains list.</span></span> <span data-ttu-id="20f8e-112">无论您是否选择此选项，您都可以指定要阻止或允许的单个域，包括限制对在联合域中运行访问边缘服务的特定服务器的访问。</span><span class="sxs-lookup"><span data-stu-id="20f8e-112">Whether or not you select this option, you can specify that individual domains to be blocked or allowed, including restricting access to specific servers running the Access Edge service in the federated domain.</span></span> <span data-ttu-id="20f8e-113">有关通过联盟域控制访问的详细信息，请参阅 [在 Lync Server 2013 中配置对允许的外部域的支持](lync-server-2013-configure-support-for-allowed-external-domains.md)。</span><span class="sxs-lookup"><span data-stu-id="20f8e-113">For details about controlling access by federated domains, see [Configure support for allowed external domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span></span>

  - <span data-ttu-id="20f8e-114">**向联盟伙伴**     发送存档免责声明将免责声明通知发送给联盟伙伴，以便在您的部署中存档存档。</span><span class="sxs-lookup"><span data-stu-id="20f8e-114">**Send an archiving disclaimer to federated partners**    Disclaimer notice is sent to federated partners that archiving in your deployment is in place.</span></span> <span data-ttu-id="20f8e-115">如果您支持存档与联盟伙伴域的外部通信，则应启用存档免责声明通知，以警告合作伙伴其邮件正在被存档。</span><span class="sxs-lookup"><span data-stu-id="20f8e-115">If you support archiving of external communications with federated partner domains, you should enable the archiving disclaimer notification to warn partners that their messages are being archived.</span></span>

<span data-ttu-id="20f8e-p105">如果稍后要暂时或永久阻止联盟域用户访问，则可以为组织禁用联盟。可以使用本节中的过程为组织启用或禁用联盟用户访问，包括指定组织所支持的相应联盟选项。</span><span class="sxs-lookup"><span data-stu-id="20f8e-p105">If you later want to temporarily or permanently prevent access by users of federated domains, you can disable federation for your organization. Use the procedure in this section to enable or disable federated user access for your organization, including specifying the appropriate federation options to be supported for your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="20f8e-118">为组织启用联盟只能指定运行访问边缘服务的服务器支持路由到联盟域。</span><span class="sxs-lookup"><span data-stu-id="20f8e-118">Enabling federation for your organization only specifies that your servers running the Access Edge service support routing to federated domains.</span></span> <span data-ttu-id="20f8e-119">只有至少再配置一个策略以支持联盟用户访问，联盟域中的用户才能参与组织中的 IM 或会议。</span><span class="sxs-lookup"><span data-stu-id="20f8e-119">Users in federated domains cannot participate in IM or conferences in your organization until you also configure at least one policy to support federated user access.</span></span> <span data-ttu-id="20f8e-120">只有至少再配置一个策略以支持公共 IM 连接，公共 IM 服务提供商的用户才能参与组织中的 IM 或会议。</span><span class="sxs-lookup"><span data-stu-id="20f8e-120">Users of public IM service providers cannot participate in IM or conferences in your organization until you also configure at least one policy to support public IM connectivity.</span></span> <span data-ttu-id="20f8e-121">只有配置提供路由信息的托管语音邮件策略，Lync Server 才能使用托管 Exchange 服务向邮箱位于托管 Exchange 服务上的用户提供呼叫应答、Outlook Voice Access（包括语音邮件）或自助服务。</span><span class="sxs-lookup"><span data-stu-id="20f8e-121">Lync Server cannot use a hosted Exchange service to provide call answering, Outlook Voice Access (including voice mail), or auto-attendant services for users whose mailboxes are located on a hosted Exchange service until you configure a hosted voice mail policy that provides routing information.</span></span> <span data-ttu-id="20f8e-122">有关配置策略以与其他组织中的联盟域的用户进行通信的详细信息，请参阅操作文档中的在 <A href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">Lync Server 2013 中管理组织的 SIP 联盟域</A> 。</span><span class="sxs-lookup"><span data-stu-id="20f8e-122">For details about configuring policies for communication with users of federated domains in other organizations, see <A href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">Manage SIP federated domains for your organization in Lync Server 2013</A> in the Operations documentation.</span></span> <span data-ttu-id="20f8e-123">此外，如果要支持与 IM 服务提供商用户的通信，必须配置支持此类通信的策略，还必须配置对要支持的各个服务提供商的支持。</span><span class="sxs-lookup"><span data-stu-id="20f8e-123">Additionally, if you want to support communication with users of IM service providers, you must configure policies to support it and also configure support for the individual service providers that you want to support.</span></span> <span data-ttu-id="20f8e-124">有关详细信息，请参阅操作文档中的 <A href="lync-server-2013-manage-sip-federated-providers-for-your-organization.md">在 Lync Server 2013 中管理组织的 SIP 联合提供程序</A> 。</span><span class="sxs-lookup"><span data-stu-id="20f8e-124">For details, see <A href="lync-server-2013-manage-sip-federated-providers-for-your-organization.md">Manage SIP federated providers for your organization in Lync Server 2013</A> in the Operations documentation.</span></span> <span data-ttu-id="20f8e-125">有关创建托管语音邮件策略的详细信息，请参阅部署文档中的在 <A href="lync-server-2013-manage-hosted-voice-mail-policies.md">Lync Server 2013 中管理托管的语音邮件策略</A> 。</span><span class="sxs-lookup"><span data-stu-id="20f8e-125">For details about creating a hosted voice mail policy, see <A href="lync-server-2013-manage-hosted-voice-mail-policies.md">Manage hosted voice mail policies in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-federated-user-access-for-your-organization"></a><span data-ttu-id="20f8e-126">为组织启用或禁用联盟用户访问</span><span class="sxs-lookup"><span data-stu-id="20f8e-126">To enable or disable federated user access for your organization</span></span>

1.  <span data-ttu-id="20f8e-127">从作为 RTCUniversalServerAdmins 组成员的用户帐户 (或具有等效的用户权限) 或分配给 CsAdministrator 角色，请登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="20f8e-127">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="20f8e-128">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="20f8e-128">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="20f8e-129">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="20f8e-129">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="20f8e-130">在左侧导航栏中，单击“外部用户访问”\*\*\*\*，然后单击“访问边缘配置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="20f8e-130">In the left navigation bar, click **External User Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="20f8e-131">在“访问边缘配置”\*\*\*\* 页上，单击“全局”\*\*\*\*，再单击“编辑”\*\*\*\*，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="20f8e-131">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="20f8e-132">在“编辑访问边缘配置”\*\*\*\* 中，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="20f8e-132">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="20f8e-133">要为组织启用联盟用户访问，请选中“启用与联盟用户的通信”\*\*\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="20f8e-133">To enable federated user access for your organization, select the **Enable communications with federated users** check box.</span></span>
    
      - <span data-ttu-id="20f8e-134">要为组织禁用联盟用户访问，请清除“启用与联盟用户的通信”\*\*\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="20f8e-134">To disable federated user access for your organization, clear the **Enable communications with federated users** check box.</span></span>

6.  <span data-ttu-id="20f8e-135">如果已选中“启用与联盟用户的通信”\*\*\*\* 复选框，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="20f8e-135">If you selected the **Enable communications with federated users** check box, do the following:</span></span>
    
    1.  <span data-ttu-id="20f8e-136">如果要支持伙伴域的自动发现，请选中“启用伙伴域发现”\*\*\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="20f8e-136">If you want to support automatic discovery of partner domains, select the **Enable partner domain discovery** check box.</span></span>
    
    2.  <span data-ttu-id="20f8e-137">如果组织支持外部通信的存档，请选中“向联盟伙伴发送存档免责声明”\*\*\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="20f8e-137">If your organization supports archiving of external communications, select the **Send archiving disclaimer to federated partners** check box.</span></span>

7.  <span data-ttu-id="20f8e-138">单击“提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="20f8e-138">Click **Commit**.</span></span>

<span data-ttu-id="20f8e-139">若要使联合用户能够与 Lync Server 2013 部署中的用户进行协作，您还必须配置至少一个外部访问策略以支持联合用户访问。</span><span class="sxs-lookup"><span data-stu-id="20f8e-139">To enable federated users to collaborate with users in your Lync Server 2013 deployment, you must also configure at least one external access policy to support federated user access.</span></span> <span data-ttu-id="20f8e-140">有关详细信息，请参阅部署文档或操作文档中的 [配置策略以控制 Lync Server 2013 中的联合用户访问](lync-server-2013-configure-policies-to-control-federated-user-access.md) 。</span><span class="sxs-lookup"><span data-stu-id="20f8e-140">For details, see [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md) in the Deployment documentation or the Operations documentation.</span></span> <span data-ttu-id="20f8e-141">若要控制对特定联盟域的访问权限，请参阅部署文档或操作文档中的在 [Lync Server 2013 中配置对允许的外部域的支持](lync-server-2013-configure-support-for-allowed-external-domains.md) 。</span><span class="sxs-lookup"><span data-stu-id="20f8e-141">To control access for specific federated domains, see [Configure support for allowed external domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md) in the Deployment documentation or Operations documentation.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-federation-and-public-im-connectivity-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="20f8e-142">使用 Windows PowerShell Cmdlet 启用或禁用联合身份验证和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="20f8e-142">Enabling or Disabling Federation and Public IM Connectivity by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="20f8e-143">此外，还可以使用 Windows PowerShell 和 Set-CsAccessEdgeConfiguration cmdlet 来管理联盟和公共 IM 连接。</span><span class="sxs-lookup"><span data-stu-id="20f8e-143">Federation and public IM connectivity can also be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="20f8e-144">此 cmdlet 可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行。</span><span class="sxs-lookup"><span data-stu-id="20f8e-144">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="20f8e-145">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上的 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="20f8e-145">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-federation-and-public-im-connectivity"></a><span data-ttu-id="20f8e-146">启用联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="20f8e-146">To enable federation and public IM connectivity</span></span>

  - <span data-ttu-id="20f8e-147">若要启用联盟和公共 IM 连接，请将 **AllowFederatedUsers** 属性的值设置为 True ($True)：</span><span class="sxs-lookup"><span data-stu-id="20f8e-147">To enable federation and public IM connectivity, set the value of the **AllowFederatedUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

</div>

<div>

## <a name="to-disable-federation-and-public-im-connectivity"></a><span data-ttu-id="20f8e-148">禁用联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="20f8e-148">To disable federation and public IM connectivity</span></span>

  - <span data-ttu-id="20f8e-149">若要禁用联盟和公共 IM 连接，请将 **AllowFederatedUsers** 属性的值设置为 False ($False)：</span><span class="sxs-lookup"><span data-stu-id="20f8e-149">To disable federation and public IM connectivity, set the value of the **AllowFederatedUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

