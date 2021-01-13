---
title: 启用或禁用联盟和公共 IM 连接
ms.reviewer: ''
ms:assetid: 8ec58f4b-9f6d-47b4-a187-d18a83fe4577
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182549(v=OCS.15)
ms:contentKeyID: 48184813
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
description: 要使具有受信任客户或伙伴组织帐户的用户（包括伙伴域用户和支持的公共即时消息 (IM) 提供商用户）能够与组织中的用户进行协作，必须具有联盟支持。
ms.openlocfilehash: 390b23a92f91d762c3703a36c063dde54dff1de1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817412"
---
# <a name="enable-or-disable-federation-and-public-im-connectivity-in-skype-for-business-server"></a><span data-ttu-id="93059-103">在 Skype for Business Server 中启用或禁用联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="93059-103">Enable or disable federation and public IM connectivity in Skype for Business Server</span></span>

<span data-ttu-id="93059-104">要使具有受信任客户或伙伴组织帐户的用户（包括伙伴域用户和支持的公共即时消息 (IM) 提供商用户）能够与组织中的用户进行协作，必须具有联盟支持。</span><span class="sxs-lookup"><span data-stu-id="93059-104">Support for federation is required to enable users who have an account with a trusted customer or partner organization, including partner domains and users of public instant messaging (IM) provider users that you support, to collaborate with users in your organization.</span></span> <span data-ttu-id="93059-105">此外，在使用托管 Exchange 服务提供商以便为其邮箱位于托管 Exchange 服务（例如，Microsoft Exchange Online）上的企业语音用户提供语音邮件时，也需要使用联盟。</span><span class="sxs-lookup"><span data-stu-id="93059-105">Federation is also required to use a hosted Exchange service provider to provide voice mail to Enterprise Voice users whose mailboxes are located on a hosted Exchange service such as Microsoft Exchange Online.</span></span> <span data-ttu-id="93059-106">当你与这些外部域建立信任关系后，你可以授权这些域中的用户访问你的部署并参与 Skype for Business Server 通信。</span><span class="sxs-lookup"><span data-stu-id="93059-106">When you have established a trust relationship with these external domains, you can authorize users in those domains to access your deployment and participate in Skype for Business Server communications.</span></span> <span data-ttu-id="93059-107">这种信任关系称为联盟，它与 Active Directory 信任关系无关，也不依赖于 Active Directory 信任关系。</span><span class="sxs-lookup"><span data-stu-id="93059-107">This trust relationship is called a federation and it is not related to, or dependent upon, an Active Directory trust relationship.</span></span>

<span data-ttu-id="93059-p102">要支持联盟域用户访问，必须启用联盟。如果为组织启用联盟，则还必须指定是否实现以下选项：</span><span class="sxs-lookup"><span data-stu-id="93059-p102">To support access by users of federated domains, you must enable federation. If you enable federation for your organization, you must also specify whether to implement the following options:</span></span>

  - <span data-ttu-id="93059-110">**启用合作伙伴域发现**   如果启用此选项，Skype for Business Server 将使用域名系统 (DNS) 记录尝试发现未在允许域列表中列出的域，自动评估发现的联盟伙伴的传入流量，并基于信任级别、流量和管理员设置限制或阻止该流量。</span><span class="sxs-lookup"><span data-stu-id="93059-110">**Enable partner domain discovery**   If you enable this option, Skype for Business Server uses Domain Name System (DNS) records to try to discover domains not listed in the allowed domains list, automatically evaluating incoming traffic from discovered federated partners and limiting or blocking that traffic based on trust level, amount of traffic, and administrator settings.</span></span> <span data-ttu-id="93059-111">如果不选择此选项，则仅对包括在允许域列表上的域中的用户启用联盟用户访问。</span><span class="sxs-lookup"><span data-stu-id="93059-111">If you do not select this option, federated user access is enabled only for users in the domains that you include on the allowed domains list.</span></span> <span data-ttu-id="93059-112">无论你是否选择此选项，都可以指定要阻止或允许的单个域，包括限制对在联盟域中运行访问边缘服务的特定服务器的访问。</span><span class="sxs-lookup"><span data-stu-id="93059-112">Whether or not you select this option, you can specify that individual domains to be blocked or allowed, including restricting access to specific servers running the Access Edge service in the federated domain.</span></span> <span data-ttu-id="93059-113">有关控制联盟域访问的详细信息，请参阅配置 [对允许的外部域的支持](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)。</span><span class="sxs-lookup"><span data-stu-id="93059-113">For details about controlling access by federated domains, see [Configure support for allowed external domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span></span>

  - <span data-ttu-id="93059-114">**向联盟伙伴发送存档免责声明**    免责声明通知将发送给联盟伙伴，表明部署中的存档已就位。</span><span class="sxs-lookup"><span data-stu-id="93059-114">**Send an archiving disclaimer to federated partners**    Disclaimer notice is sent to federated partners that archiving in your deployment is in place.</span></span> <span data-ttu-id="93059-115">如果支持存档与联盟伙伴域的外部通信，应启用存档免责声明通知，以警告合作伙伴其邮件正在存档。</span><span class="sxs-lookup"><span data-stu-id="93059-115">If you support archiving of external communications with federated partner domains, you should enable the archiving disclaimer notification to warn partners that their messages are being archived.</span></span>

<span data-ttu-id="93059-p105">如果稍后要暂时或永久阻止联盟域用户访问，则可以为组织禁用联盟。可以使用本节中的过程为组织启用或禁用联盟用户访问，包括指定组织所支持的相应联盟选项。</span><span class="sxs-lookup"><span data-stu-id="93059-p105">If you later want to temporarily or permanently prevent access by users of federated domains, you can disable federation for your organization. Use the procedure in this section to enable or disable federated user access for your organization, including specifying the appropriate federation options to be supported for your organization.</span></span>

> [!NOTE]  
> <span data-ttu-id="93059-118">为组织启用联盟只能指定运行访问边缘服务的服务器支持路由到联盟域。</span><span class="sxs-lookup"><span data-stu-id="93059-118">Enabling federation for your organization only specifies that your servers running the Access Edge service support routing to federated domains.</span></span> <span data-ttu-id="93059-119">只有至少再配置一个策略以支持联盟用户访问，联盟域中的用户才能参与组织中的 IM 或会议。</span><span class="sxs-lookup"><span data-stu-id="93059-119">Users in federated domains cannot participate in IM or conferences in your organization until you also configure at least one policy to support federated user access.</span></span> <span data-ttu-id="93059-120">只有至少再配置一个策略以支持公共 IM 连接，公共 IM 服务提供商的用户才能参与组织中的 IM 或会议。</span><span class="sxs-lookup"><span data-stu-id="93059-120">Users of public IM service providers cannot participate in IM or conferences in your organization until you also configure at least one policy to support public IM connectivity.</span></span> <span data-ttu-id="93059-121">在配置提供路由信息的托管语音邮件策略之前，Skype for Business Server 无法使用托管 Exchange 服务为邮箱位于托管 Exchange 服务上的用户提供呼叫应答、Outlook Voice Access (包括语音邮件) 或自动助理服务。</span><span class="sxs-lookup"><span data-stu-id="93059-121">Skype for Business Server cannot use a hosted Exchange service to provide call answering, Outlook Voice Access (including voice mail), or auto-attendant services for users whose mailboxes are located on a hosted Exchange service until you configure a hosted voice mail policy that provides routing information.</span></span> <span data-ttu-id="93059-122">有关配置与其他组织中联盟域用户通信的策略的详细信息，请参阅"管理[组织的 SIP 联盟域"。](../sip-domains/manage-sip-federated-domains-for-your-organization.md)</span><span class="sxs-lookup"><span data-stu-id="93059-122">For details about configuring policies for communication with users of federated domains in other organizations, see [Manage SIP federated domains for your organization](../sip-domains/manage-sip-federated-domains-for-your-organization.md).</span></span> <span data-ttu-id="93059-123">此外，如果要支持与 IM 服务提供商用户的通信，必须配置支持此类通信的策略，还必须配置对要支持的各个服务提供商的支持。</span><span class="sxs-lookup"><span data-stu-id="93059-123">Additionally, if you want to support communication with users of IM service providers, you must configure policies to support it and also configure support for the individual service providers that you want to support.</span></span> <span data-ttu-id="93059-124">有关详细信息，请参阅["管理组织的 SIP 联盟提供程序"。](../sip-providers/manage-sip-federated-providers-for-your-organization.md)</span><span class="sxs-lookup"><span data-stu-id="93059-124">For details, see   [Manage SIP federated providers for your organization](../sip-providers/manage-sip-federated-providers-for-your-organization.md).</span></span>


## <a name="to-enable-or-disable-federated-user-access-for-your-organization"></a><span data-ttu-id="93059-125">为组织启用或禁用联盟用户访问</span><span class="sxs-lookup"><span data-stu-id="93059-125">To enable or disable federated user access for your organization</span></span>

1.  <span data-ttu-id="93059-126">从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或已分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。</span><span class="sxs-lookup"><span data-stu-id="93059-126">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="93059-127">打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="93059-127">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="93059-128">在左侧导航栏中，单击“外部用户访问”，然后单击“访问边缘配置”。</span><span class="sxs-lookup"><span data-stu-id="93059-128">In the left navigation bar, click **External User Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="93059-129">在“访问边缘配置”页上，单击“全局”，再单击“编辑”，然后单击“显示详细信息”。</span><span class="sxs-lookup"><span data-stu-id="93059-129">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="93059-130">在“编辑访问边缘配置”中，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="93059-130">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="93059-131">要为组织启用联盟用户访问，请选中“启用与联盟用户的通信”复选框。</span><span class="sxs-lookup"><span data-stu-id="93059-131">To enable federated user access for your organization, select the **Enable communications with federated users** check box.</span></span>
    
      - <span data-ttu-id="93059-132">要为组织禁用联盟用户访问，请清除“启用与联盟用户的通信”复选框。</span><span class="sxs-lookup"><span data-stu-id="93059-132">To disable federated user access for your organization, clear the **Enable communications with federated users** check box.</span></span>

6.  <span data-ttu-id="93059-133">如果已选中“启用与联盟用户的通信”复选框，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="93059-133">If you selected the **Enable communications with federated users** check box, do the following:</span></span>
    
    1.  <span data-ttu-id="93059-134">如果要支持伙伴域的自动发现，请选中“启用伙伴域发现”复选框。</span><span class="sxs-lookup"><span data-stu-id="93059-134">If you want to support automatic discovery of partner domains, select the **Enable partner domain discovery** check box.</span></span>
    
    2.  <span data-ttu-id="93059-135">如果组织支持外部通信的存档，请选中“向联盟伙伴发送存档免责声明”复选框。</span><span class="sxs-lookup"><span data-stu-id="93059-135">If your organization supports archiving of external communications, select the **Send archiving disclaimer to federated partners** check box.</span></span>

7.  <span data-ttu-id="93059-136">单击“提交”。</span><span class="sxs-lookup"><span data-stu-id="93059-136">Click **Commit**.</span></span>

<span data-ttu-id="93059-137">若要使联盟用户能够与 Skype for Business Server 部署中的用户进行协作，还必须配置至少一个外部访问策略以支持联盟用户访问。</span><span class="sxs-lookup"><span data-stu-id="93059-137">To enable federated users to collaborate with users in your Skype for Business Server deployment, you must also configure at least one external access policy to support federated user access.</span></span> <span data-ttu-id="93059-138">有关详细信息，请参阅 [配置策略以控制联盟用户访问](../external-access-policies/configure-policies-to-control-federated-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="93059-138">For details, see [Configure policies to control federated user access](../external-access-policies/configure-policies-to-control-federated-user-access.md).</span></span> <span data-ttu-id="93059-139">若要控制对特定联盟域的访问，请参阅配置 [对允许的外部域的支持](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)。</span><span class="sxs-lookup"><span data-stu-id="93059-139">To control access for specific federated domains, see [Configure support for allowed external domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span></span>


## <a name="enabling-or-disabling-federation-and-public-im-connectivity-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="93059-140">使用 cmdlet 启用或禁用联盟Windows PowerShell IM 连接</span><span class="sxs-lookup"><span data-stu-id="93059-140">Enabling or disabling federation and public IM connectivity by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="93059-141">联盟和公共 IM 连接也可通过使用 Windows PowerShell 和 Set-CsAccessEdgeConfiguration cmdlet 进行管理。</span><span class="sxs-lookup"><span data-stu-id="93059-141">Federation and public IM connectivity can also be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="93059-142">此 cmdlet 可以从 Skype for Business Server 命令行管理程序运行，也可以从远程会话Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="93059-142">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-enable-federation-and-public-im-connectivity"></a><span data-ttu-id="93059-143">启用联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="93059-143">To enable federation and public IM connectivity</span></span>

  - <span data-ttu-id="93059-144">若要启用联盟和公共 IM 连接，请将 **AllowFederatedUsers** 属性的值设置为 True ($True)：</span><span class="sxs-lookup"><span data-stu-id="93059-144">To enable federation and public IM connectivity, set the value of the **AllowFederatedUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True



## <a name="to-disable-federation-and-public-im-connectivity"></a><span data-ttu-id="93059-145">禁用联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="93059-145">To disable federation and public IM connectivity</span></span>

  - <span data-ttu-id="93059-146">若要禁用联盟和公共 IM 连接，请将 **AllowFederatedUsers** 属性的值设置为 False ($False)：</span><span class="sxs-lookup"><span data-stu-id="93059-146">To disable federation and public IM connectivity, set the value of the **AllowFederatedUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $False

