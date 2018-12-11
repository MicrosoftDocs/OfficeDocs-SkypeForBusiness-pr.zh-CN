---
title: 启用或禁用联盟和公共 IM 连接
ms:assetid: 8ec58f4b-9f6d-47b4-a187-d18a83fe4577
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182549(v=OCS.15)
ms:contentKeyID: 48184813
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 支持的联合身份验证，则需要启用具有与受信任客户或合作伙伴组织，包括伙伴域和公共即时消息 (IM) 提供程序用户的支持，与中的用户进行协作的用户帐户的用户您组织。
ms.openlocfilehash: 9e293c70565832944a10e3c6d2533425c747197e
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222994"
---
# <a name="enable-or-disable-federation-and-public-im-connectivity-in-skype-for-business-server"></a><span data-ttu-id="70119-103">启用或禁用联盟和公共 IM 连接中 Skype 业务服务器</span><span class="sxs-lookup"><span data-stu-id="70119-103">Enable or disable federation and public IM connectivity in Skype for Business Server</span></span>

<span data-ttu-id="70119-104">支持的联合身份验证，则需要启用具有与受信任客户或合作伙伴组织，包括伙伴域和公共即时消息 (IM) 提供程序用户的支持，与中的用户进行协作的用户帐户的用户您组织。</span><span class="sxs-lookup"><span data-stu-id="70119-104">Support for federation is required to enable users who have an account with a trusted customer or partner organization, including partner domains and users of public instant messaging (IM) provider users that you support, to collaborate with users in your organization.</span></span> <span data-ttu-id="70119-105">使用承载的 Exchange 服务提供商向其邮箱位于托管 Exchange 服务，如 Microsoft Exchange Online 的企业语音用户提供语音邮件还需要联合身份验证。</span><span class="sxs-lookup"><span data-stu-id="70119-105">Federation is also required to use a hosted Exchange service provider to provide voice mail to Enterprise Voice users whose mailboxes are located on a hosted Exchange service such as Microsoft Exchange Online.</span></span> <span data-ttu-id="70119-106">建立与这些外部域的信任关系之后，您可以授权这些域中的用户能够访问您的部署和参与 Skype 的业务服务器通信。</span><span class="sxs-lookup"><span data-stu-id="70119-106">When you have established a trust relationship with these external domains, you can authorize users in those domains to access your deployment and participate in Skype for Business Server communications.</span></span> <span data-ttu-id="70119-107">此信任关系称为联盟，它不相关，或取决于，Active Directory 信任关系。</span><span class="sxs-lookup"><span data-stu-id="70119-107">This trust relationship is called a federation and it is not related to, or dependent upon, an Active Directory trust relationship.</span></span>

<span data-ttu-id="70119-108">若要支持联盟域用户访问，必须启用联合身份验证。</span><span class="sxs-lookup"><span data-stu-id="70119-108">To support access by users of federated domains, you must enable federation.</span></span> <span data-ttu-id="70119-109">如果您为组织启用联盟，您还必须指定是否要实现以下选项：</span><span class="sxs-lookup"><span data-stu-id="70119-109">If you enable federation for your organization, you must also specify whether to implement the following options:</span></span>

  - <span data-ttu-id="70119-110">**启用伙伴域发现**   Skype 业务服务器如果您启用此选项，使用域名系统 (DNS) 记录尝试发现不在允许的域列表中，列出来自自动计算传入通信发现的域联盟伙伴和限制或阻止基于信任级别，请量通信和管理员设置的通信。</span><span class="sxs-lookup"><span data-stu-id="70119-110">**Enable partner domain discovery**   If you enable this option, Skype for Business Server uses Domain Name System (DNS) records to try to discover domains not listed in the allowed domains list, automatically evaluating incoming traffic from discovered federated partners and limiting or blocking that traffic based on trust level, amount of traffic, and administrator settings.</span></span> <span data-ttu-id="70119-111">如果您未选择此选项，仅对您在允许的域列表包含的域中的用户启用联盟的用户访问。</span><span class="sxs-lookup"><span data-stu-id="70119-111">If you do not select this option, federated user access is enabled only for users in the domains that you include on the allowed domains list.</span></span> <span data-ttu-id="70119-112">是否选择此选项，您可以指定的单个域阻止或允许，包括限制对特定服务器的联盟域中运行访问边缘服务的访问。</span><span class="sxs-lookup"><span data-stu-id="70119-112">Whether or not you select this option, you can specify that individual domains to be blocked or allowed, including restricting access to specific servers running the Access Edge service in the federated domain.</span></span> <span data-ttu-id="70119-113">有关控制联盟域访问的详细信息，请参阅[支持的允许的外部域的配置](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)。</span><span class="sxs-lookup"><span data-stu-id="70119-113">For details about controlling access by federated domains, see [Configure support for allowed external domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span></span>

  - <span data-ttu-id="70119-114">**向联盟伙伴发送存档免责声明**   免责声明通知发送给联盟伙伴的就地存档部署中是。</span><span class="sxs-lookup"><span data-stu-id="70119-114">**Send an archiving disclaimer to federated partners**    Disclaimer notice is sent to federated partners that archiving in your deployment is in place.</span></span> <span data-ttu-id="70119-115">如果您支持与联盟的伙伴域的外部通信的存档，则应启用存档放弃通知以提醒伙伴已存档其消息。</span><span class="sxs-lookup"><span data-stu-id="70119-115">If you support archiving of external communications with federated partner domains, you should enable the archiving disclaimer notification to warn partners that their messages are being archived.</span></span>

<span data-ttu-id="70119-116">如果您以后想要临时或永久阻止的联盟域用户访问，您可以为组织禁用联盟。</span><span class="sxs-lookup"><span data-stu-id="70119-116">If you later want to temporarily or permanently prevent access by users of federated domains, you can disable federation for your organization.</span></span> <span data-ttu-id="70119-117">使用本节中的过程以启用或禁用您的组织，包括指定相应的联合身份验证选项为您的组织支持的联盟的用户访问。</span><span class="sxs-lookup"><span data-stu-id="70119-117">Use the procedure in this section to enable or disable federated user access for your organization, including specifying the appropriate federation options to be supported for your organization.</span></span>

> [!NOTE]  
> <span data-ttu-id="70119-118">启用联盟的组织仅指定运行访问边缘服务的服务器支持传送到联盟域。</span><span class="sxs-lookup"><span data-stu-id="70119-118">Enabling federation for your organization only specifies that your servers running the Access Edge service support routing to federated domains.</span></span> <span data-ttu-id="70119-119">联盟域中的用户不能参与 IM 或会议组织也配置至少一个策略以支持联盟的用户访问之前。</span><span class="sxs-lookup"><span data-stu-id="70119-119">Users in federated domains cannot participate in IM or conferences in your organization until you also configure at least one policy to support federated user access.</span></span> <span data-ttu-id="70119-120">公共 IM 服务提供商的用户不能参与 IM 或会议组织也配置至少一个策略以支持公共 IM 连接之前。</span><span class="sxs-lookup"><span data-stu-id="70119-120">Users of public IM service providers cannot participate in IM or conferences in your organization until you also configure at least one policy to support public IM connectivity.</span></span> <span data-ttu-id="70119-121">Skype 业务服务器不能使用托管的 Exchange 服务来提供呼叫应答、 Outlook Voice Access （包括语音邮件） 或位于其邮箱的用户的自动助理服务托管 Exchange 服务上配置托管的语音之前提供的路由信息的邮件策略。</span><span class="sxs-lookup"><span data-stu-id="70119-121">Skype for Business Server cannot use a hosted Exchange service to provide call answering, Outlook Voice Access (including voice mail), or auto-attendant services for users whose mailboxes are located on a hosted Exchange service until you configure a hosted voice mail policy that provides routing information.</span></span> <span data-ttu-id="70119-122">有关配置与其他组织中的联盟域的用户进行通信的策略的详细信息，请参阅[管理 SIP 联盟域为您的组织](../sip-domains/manage-sip-federated-domains-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="70119-122">For details about configuring policies for communication with users of federated domains in other organizations, see [Manage SIP federated domains for your organization](../sip-domains/manage-sip-federated-domains-for-your-organization.md).</span></span> <span data-ttu-id="70119-123">此外，如果您想要支持与用户的 IM 服务提供商的通信，则必须配置策略以支持和还配置您想要支持的单个服务提供程序的支持。</span><span class="sxs-lookup"><span data-stu-id="70119-123">Additionally, if you want to support communication with users of IM service providers, you must configure policies to support it and also configure support for the individual service providers that you want to support.</span></span> <span data-ttu-id="70119-124">有关详细信息，请参阅[管理 SIP 联盟提供程序为您的组织](../sip-providers/manage-sip-federated-providers-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="70119-124">For details, see   [Manage SIP federated providers for your organization](../sip-providers/manage-sip-federated-providers-for-your-organization.md).</span></span>


## <a name="to-enable-or-disable-federated-user-access-for-your-organization"></a><span data-ttu-id="70119-125">启用或禁用组织的联盟的用户访问</span><span class="sxs-lookup"><span data-stu-id="70119-125">To enable or disable federated user access for your organization</span></span>

1.  <span data-ttu-id="70119-126">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="70119-126">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="70119-127">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="70119-127">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="70119-128">在左侧的导航栏中，单击**外部用户访问**，然后单击**访问边缘配置**。</span><span class="sxs-lookup"><span data-stu-id="70119-128">In the left navigation bar, click **External User Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="70119-129">在**访问边缘配置**页上，单击**全局**，单击**编辑**，然后单击**显示详细信息**。</span><span class="sxs-lookup"><span data-stu-id="70119-129">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="70119-130">在**编辑访问边缘配置**中，执行下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="70119-130">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="70119-131">要为组织的联盟的用户访问，请选中**启用与联盟用户的通信**复选框。</span><span class="sxs-lookup"><span data-stu-id="70119-131">To enable federated user access for your organization, select the **Enable communications with federated users** check box.</span></span>
    
      - <span data-ttu-id="70119-132">若要禁用组织的联盟的用户访问，请清除**启用与联盟用户的通信**复选框。</span><span class="sxs-lookup"><span data-stu-id="70119-132">To disable federated user access for your organization, clear the **Enable communications with federated users** check box.</span></span>

6.  <span data-ttu-id="70119-133">如果您选择**启用与联盟用户的通信**复选框，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="70119-133">If you selected the **Enable communications with federated users** check box, do the following:</span></span>
    
    1.  <span data-ttu-id="70119-134">如果您想要支持伙伴域的自动发现，选择**启用伙伴域发现**复选框。</span><span class="sxs-lookup"><span data-stu-id="70119-134">If you want to support automatic discovery of partner domains, select the **Enable partner domain discovery** check box.</span></span>
    
    2.  <span data-ttu-id="70119-135">如果您的组织支持外部通信的存档，请选中**向联盟伙伴发送存档免责声明**复选框。</span><span class="sxs-lookup"><span data-stu-id="70119-135">If your organization supports archiving of external communications, select the **Send archiving disclaimer to federated partners** check box.</span></span>

7.  <span data-ttu-id="70119-136">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="70119-136">Click **Commit**.</span></span>

<span data-ttu-id="70119-137">若要启用联盟的用户与您 Skype 业务服务器部署中的用户进行协作，还必须配置至少一个外部访问策略以支持联盟的用户访问。</span><span class="sxs-lookup"><span data-stu-id="70119-137">To enable federated users to collaborate with users in your Skype for Business Server deployment, you must also configure at least one external access policy to support federated user access.</span></span> <span data-ttu-id="70119-138">有关详细信息，请参阅[配置策略以控制联盟用户访问](../external-access-policies/configure-policies-to-control-federated-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="70119-138">For details, see [Configure policies to control federated user access](../external-access-policies/configure-policies-to-control-federated-user-access.md).</span></span> <span data-ttu-id="70119-139">若要控制特定联盟域的访问，请参阅[配置允许的外部域的支持](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)。</span><span class="sxs-lookup"><span data-stu-id="70119-139">To control access for specific federated domains, see [Configure support for allowed external domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span></span>


## <a name="enabling-or-disabling-federation-and-public-im-connectivity-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="70119-140">启用或禁用联盟和公共 IM 连接使用 Windows PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="70119-140">Enabling or disabling federation and public IM connectivity by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="70119-141">也可以通过使用 Windows PowerShell 和 Set-csaccessedgeconfiguration cmdlet 来管理联盟和公共 IM 连接。</span><span class="sxs-lookup"><span data-stu-id="70119-141">Federation and public IM connectivity can also be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="70119-142">从业务 Server 命令行管理程序 Skype 或 Windows PowerShell 远程会话，则可以运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="70119-142">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-enable-federation-and-public-im-connectivity"></a><span data-ttu-id="70119-143">要启用联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="70119-143">To enable federation and public IM connectivity</span></span>

  - <span data-ttu-id="70119-144">要启用联盟和公共 IM 连接，请将**AllowFederatedUsers**属性的值设置为 True ($True):</span><span class="sxs-lookup"><span data-stu-id="70119-144">To enable federation and public IM connectivity, set the value of the **AllowFederatedUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True



## <a name="to-disable-federation-and-public-im-connectivity"></a><span data-ttu-id="70119-145">若要禁用联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="70119-145">To disable federation and public IM connectivity</span></span>

  - <span data-ttu-id="70119-146">要禁用联盟和公共 IM 连接，请将**AllowFederatedUsers**属性的值设置为 False ($False) 中：</span><span class="sxs-lookup"><span data-stu-id="70119-146">To disable federation and public IM connectivity, set the value of the **AllowFederatedUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $False

