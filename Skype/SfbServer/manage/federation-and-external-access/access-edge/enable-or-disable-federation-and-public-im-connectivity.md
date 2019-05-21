---
title: 启用或禁用联盟和公共 IM 连接
ms.reviewer: ''
ms:assetid: 8ec58f4b-9f6d-47b4-a187-d18a83fe4577
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182549(v=OCS.15)
ms:contentKeyID: 48184813
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 若要使拥有具有受信任客户或合作伙伴组织的帐户的用户 (包括合作伙伴域和你支持的公共即时消息 (IM) 提供者用户) 与你所支持的公共即时消息 (IM) 提供者的用户协作, 必须支持联合身份验证所在.
ms.openlocfilehash: 86cc3e66b2e3252b6b25ff4bef09d3abeb4badf0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280241"
---
# <a name="enable-or-disable-federation-and-public-im-connectivity-in-skype-for-business-server"></a><span data-ttu-id="a3d22-103">在 Skype for Business 服务器中启用或禁用联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="a3d22-103">Enable or disable federation and public IM connectivity in Skype for Business Server</span></span>

<span data-ttu-id="a3d22-104">若要使拥有具有受信任客户或合作伙伴组织的帐户的用户 (包括合作伙伴域和你支持的公共即时消息 (IM) 提供者用户) 与你所支持的公共即时消息 (IM) 提供者的用户协作, 必须支持联合身份验证所在.</span><span class="sxs-lookup"><span data-stu-id="a3d22-104">Support for federation is required to enable users who have an account with a trusted customer or partner organization, including partner domains and users of public instant messaging (IM) provider users that you support, to collaborate with users in your organization.</span></span> <span data-ttu-id="a3d22-105">若要使用托管 Exchange 服务提供程序向企业语音用户提供语音邮件 (其邮箱位于 Microsoft Exchange Online 等托管 Exchange 服务), 还需要联合身份验证。</span><span class="sxs-lookup"><span data-stu-id="a3d22-105">Federation is also required to use a hosted Exchange service provider to provide voice mail to Enterprise Voice users whose mailboxes are located on a hosted Exchange service such as Microsoft Exchange Online.</span></span> <span data-ttu-id="a3d22-106">与这些外部域建立信任关系后, 您可以授权这些域中的用户访问您的部署并参与 Skype for Business 服务器通信。</span><span class="sxs-lookup"><span data-stu-id="a3d22-106">When you have established a trust relationship with these external domains, you can authorize users in those domains to access your deployment and participate in Skype for Business Server communications.</span></span> <span data-ttu-id="a3d22-107">此信任关系称为联合体, 它与 Active Directory 信任关系无关, 或不依赖。</span><span class="sxs-lookup"><span data-stu-id="a3d22-107">This trust relationship is called a federation and it is not related to, or dependent upon, an Active Directory trust relationship.</span></span>

<span data-ttu-id="a3d22-108">若要支持受联盟域的用户访问, 必须启用联盟。</span><span class="sxs-lookup"><span data-stu-id="a3d22-108">To support access by users of federated domains, you must enable federation.</span></span> <span data-ttu-id="a3d22-109">如果为您的组织启用联盟, 还必须指定是否实现以下选项:</span><span class="sxs-lookup"><span data-stu-id="a3d22-109">If you enable federation for your organization, you must also specify whether to implement the following options:</span></span>

  - <span data-ttu-id="a3d22-110">**启用合作伙伴域发现**   如果启用此选项, 则 Skype for business 服务器将使用域名系统 (DNS) 记录来尝试发现未在 "允许的域" 列表中列出的域, 并自动评估已发现的传入流量联盟伙伴, 并根据信任级别、流量和管理员设置限制或阻止该流量。</span><span class="sxs-lookup"><span data-stu-id="a3d22-110">**Enable partner domain discovery**   If you enable this option, Skype for Business Server uses Domain Name System (DNS) records to try to discover domains not listed in the allowed domains list, automatically evaluating incoming traffic from discovered federated partners and limiting or blocking that traffic based on trust level, amount of traffic, and administrator settings.</span></span> <span data-ttu-id="a3d22-111">如果不选择此选项, 则仅对在 "允许的域" 列表中包含的域中的用户启用 "联盟用户访问"。</span><span class="sxs-lookup"><span data-stu-id="a3d22-111">If you do not select this option, federated user access is enabled only for users in the domains that you include on the allowed domains list.</span></span> <span data-ttu-id="a3d22-112">无论是否选择此选项, 您都可以指定要阻止或允许的单个域, 包括限制对运行联盟域中的访问边缘服务的特定服务器的访问。</span><span class="sxs-lookup"><span data-stu-id="a3d22-112">Whether or not you select this option, you can specify that individual domains to be blocked or allowed, including restricting access to specific servers running the Access Edge service in the federated domain.</span></span> <span data-ttu-id="a3d22-113">有关通过联盟域控制访问的详细信息, 请参阅[配置对允许的外部域的支持](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)。</span><span class="sxs-lookup"><span data-stu-id="a3d22-113">For details about controlling access by federated domains, see [Configure support for allowed external domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span></span>

  - <span data-ttu-id="a3d22-114">**将存档免责声明发送给联盟合作伙伴**   声明通知将发送给联盟合作伙伴, 以便在部署中存档存档。</span><span class="sxs-lookup"><span data-stu-id="a3d22-114">**Send an archiving disclaimer to federated partners**    Disclaimer notice is sent to federated partners that archiving in your deployment is in place.</span></span> <span data-ttu-id="a3d22-115">如果您支持与联盟伙伴域的外部通信的存档, 则应启用 "存档免责声明通知" 以警告合作伙伴其邮件正在存档。</span><span class="sxs-lookup"><span data-stu-id="a3d22-115">If you support archiving of external communications with federated partner domains, you should enable the archiving disclaimer notification to warn partners that their messages are being archived.</span></span>

<span data-ttu-id="a3d22-116">如果稍后希望临时或永久阻止联盟域用户访问, 则可以为你的组织禁用联盟。</span><span class="sxs-lookup"><span data-stu-id="a3d22-116">If you later want to temporarily or permanently prevent access by users of federated domains, you can disable federation for your organization.</span></span> <span data-ttu-id="a3d22-117">使用此部分中的过程可为你的组织启用或禁用联盟用户访问权限, 包括指定你的组织支持的相应联盟选项。</span><span class="sxs-lookup"><span data-stu-id="a3d22-117">Use the procedure in this section to enable or disable federated user access for your organization, including specifying the appropriate federation options to be supported for your organization.</span></span>

> [!NOTE]  
> <span data-ttu-id="a3d22-118">为你的组织启用联盟仅指定运行 Access Edge 服务的服务器支持路由到联盟域。</span><span class="sxs-lookup"><span data-stu-id="a3d22-118">Enabling federation for your organization only specifies that your servers running the Access Edge service support routing to federated domains.</span></span> <span data-ttu-id="a3d22-119">联盟域中的用户无法在你的组织中参与 IM 或会议, 除非你还配置了至少一个策略来支持联合用户访问。</span><span class="sxs-lookup"><span data-stu-id="a3d22-119">Users in federated domains cannot participate in IM or conferences in your organization until you also configure at least one policy to support federated user access.</span></span> <span data-ttu-id="a3d22-120">公共 IM 服务提供商的用户无法在你的组织中参与 IM 或会议, 除非你还配置了至少一个策略来支持公用 IM 连接。</span><span class="sxs-lookup"><span data-stu-id="a3d22-120">Users of public IM service providers cannot participate in IM or conferences in your organization until you also configure at least one policy to support public IM connectivity.</span></span> <span data-ttu-id="a3d22-121">Skype for Business 服务器无法使用托管 Exchange 服务为邮箱位于托管 Exchange 服务上的用户提供呼叫应答、Outlook Voice Access (包括语音邮件) 或自动助理服务, 直到配置托管语音提供路由信息的邮件策略。</span><span class="sxs-lookup"><span data-stu-id="a3d22-121">Skype for Business Server cannot use a hosted Exchange service to provide call answering, Outlook Voice Access (including voice mail), or auto-attendant services for users whose mailboxes are located on a hosted Exchange service until you configure a hosted voice mail policy that provides routing information.</span></span> <span data-ttu-id="a3d22-122">有关配置与其他组织中联盟域的用户进行通信的策略的详细信息, 请参阅[管理组织的 SIP 联合域](../sip-domains/manage-sip-federated-domains-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="a3d22-122">For details about configuring policies for communication with users of federated domains in other organizations, see [Manage SIP federated domains for your organization](../sip-domains/manage-sip-federated-domains-for-your-organization.md).</span></span> <span data-ttu-id="a3d22-123">此外, 如果你想要支持与 IM 服务提供商的用户进行通信, 你必须配置策略来支持它, 还必须配置对要支持的单个服务提供商的支持。</span><span class="sxs-lookup"><span data-stu-id="a3d22-123">Additionally, if you want to support communication with users of IM service providers, you must configure policies to support it and also configure support for the individual service providers that you want to support.</span></span> <span data-ttu-id="a3d22-124">有关详细信息, 请参阅[管理你的组织的 SIP 联合提供商](../sip-providers/manage-sip-federated-providers-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="a3d22-124">For details, see   [Manage SIP federated providers for your organization](../sip-providers/manage-sip-federated-providers-for-your-organization.md).</span></span>


## <a name="to-enable-or-disable-federated-user-access-for-your-organization"></a><span data-ttu-id="a3d22-125">为你的组织启用或禁用联盟用户访问</span><span class="sxs-lookup"><span data-stu-id="a3d22-125">To enable or disable federated user access for your organization</span></span>

1.  <span data-ttu-id="a3d22-126">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="a3d22-126">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a3d22-127">打开一个浏览器窗口, 然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="a3d22-127">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="a3d22-128">在左侧导航栏中, 单击 "**外部用户访问**", 然后单击 "**访问边缘配置**"。</span><span class="sxs-lookup"><span data-stu-id="a3d22-128">In the left navigation bar, click **External User Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="a3d22-129">在 "**访问边缘配置**" 页面上, 单击 "**全局**", 单击 "**编辑**", 然后单击 "**显示详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="a3d22-129">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="a3d22-130">在 "**编辑访问边缘配置**" 中, 执行下列操作之一:</span><span class="sxs-lookup"><span data-stu-id="a3d22-130">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="a3d22-131">若要为你的组织启用联盟用户访问, 请选中 "**启用与联盟用户的通信**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="a3d22-131">To enable federated user access for your organization, select the **Enable communications with federated users** check box.</span></span>
    
      - <span data-ttu-id="a3d22-132">若要为你的组织禁用联盟用户访问, 请清除 "**启用与联盟用户的通信**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="a3d22-132">To disable federated user access for your organization, clear the **Enable communications with federated users** check box.</span></span>

6.  <span data-ttu-id="a3d22-133">如果选中 "**启用与联盟用户的通信**" 复选框, 请执行下列操作:</span><span class="sxs-lookup"><span data-stu-id="a3d22-133">If you selected the **Enable communications with federated users** check box, do the following:</span></span>
    
    1.  <span data-ttu-id="a3d22-134">如果您希望支持自动发现合作伙伴域, 请选中 "**启用合作伙伴域发现**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="a3d22-134">If you want to support automatic discovery of partner domains, select the **Enable partner domain discovery** check box.</span></span>
    
    2.  <span data-ttu-id="a3d22-135">如果您的组织支持外部通信的存档, 请选中 "将**存档声明发送给联盟伙伴**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="a3d22-135">If your organization supports archiving of external communications, select the **Send archiving disclaimer to federated partners** check box.</span></span>

7.  <span data-ttu-id="a3d22-136">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="a3d22-136">Click **Commit**.</span></span>

<span data-ttu-id="a3d22-137">若要使联盟用户能够与 Skype for Business Server 部署中的用户进行协作, 还必须至少配置一个外部访问策略以支持联合用户访问。</span><span class="sxs-lookup"><span data-stu-id="a3d22-137">To enable federated users to collaborate with users in your Skype for Business Server deployment, you must also configure at least one external access policy to support federated user access.</span></span> <span data-ttu-id="a3d22-138">有关详细信息, 请参阅[配置用于控制联盟用户访问的策略](../external-access-policies/configure-policies-to-control-federated-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="a3d22-138">For details, see [Configure policies to control federated user access](../external-access-policies/configure-policies-to-control-federated-user-access.md).</span></span> <span data-ttu-id="a3d22-139">若要控制特定联盟域的访问权限, 请参阅[配置对允许的外部域的支持](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)。</span><span class="sxs-lookup"><span data-stu-id="a3d22-139">To control access for specific federated domains, see [Configure support for allowed external domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span></span>


## <a name="enabling-or-disabling-federation-and-public-im-connectivity-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="a3d22-140">使用 Windows PowerShell cmdlet 启用或禁用联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="a3d22-140">Enabling or disabling federation and public IM connectivity by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="a3d22-141">联盟和公共 IM 连接也可以通过使用 Windows PowerShell 和 CsAccessEdgeConfiguration cmdlet 进行管理。</span><span class="sxs-lookup"><span data-stu-id="a3d22-141">Federation and public IM connectivity can also be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="a3d22-142">此 cmdlet 既可以从 Skype for Business 服务器管理外壳运行, 也可以从 Windows PowerShell 的远程会话运行。</span><span class="sxs-lookup"><span data-stu-id="a3d22-142">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-enable-federation-and-public-im-connectivity"></a><span data-ttu-id="a3d22-143">启用联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="a3d22-143">To enable federation and public IM connectivity</span></span>

  - <span data-ttu-id="a3d22-144">若要启用联盟和公共 IM 连接, 请将**AllowFederatedUsers**属性的值设置为 True ($True):</span><span class="sxs-lookup"><span data-stu-id="a3d22-144">To enable federation and public IM connectivity, set the value of the **AllowFederatedUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True



## <a name="to-disable-federation-and-public-im-connectivity"></a><span data-ttu-id="a3d22-145">禁用联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="a3d22-145">To disable federation and public IM connectivity</span></span>

  - <span data-ttu-id="a3d22-146">若要禁用联盟和公共 IM 连接, 请将**AllowFederatedUsers**属性的值设置为 False ($False):</span><span class="sxs-lookup"><span data-stu-id="a3d22-146">To disable federation and public IM connectivity, set the value of the **AllowFederatedUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $False

