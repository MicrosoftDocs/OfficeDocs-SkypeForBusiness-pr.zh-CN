---
title: 配置云连接器与 Microsoft 365 或 Office 365 组织的集成
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0e2f2395-b890-4d16-aa2d-99d52438b89c
description: 了解如何配置与 Microsoft 365 或 Office 365 组织的云连接器集成。
ms.openlocfilehash: 74696023dcffbc91641bb4e9950f2988a89abbdd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095086"
---
# <a name="configure-cloud-connector-integration-with-your-microsoft-365-or-office-365-organization"></a><span data-ttu-id="2517a-103">配置云连接器与 Microsoft 365 或 Office 365 组织的集成</span><span class="sxs-lookup"><span data-stu-id="2517a-103">Configure Cloud Connector integration with your Microsoft 365 or Office 365 organization</span></span>

> [!Important] 
> <span data-ttu-id="2517a-104">云连接器版本将于 2021 年 7 月 31 日与 Skype for Business Online 一起停用。</span><span class="sxs-lookup"><span data-stu-id="2517a-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="2517a-105">组织升级到 Teams 后，了解如何使用直接路由将本地电话网络连接到[Teams。](/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="2517a-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="2517a-106">了解如何配置与 Microsoft 365 或 Office 365 组织的云连接器集成。</span><span class="sxs-lookup"><span data-stu-id="2517a-106">Learn how to configure Cloud Connector integration with your Microsoft 365 or Office 365 organization.</span></span>
  
<span data-ttu-id="2517a-107">Skype for Business 云连接器版本安装完成后，执行本节中的步骤以配置部署，并连接到 Microsoft 365 或 Office 365 组织。</span><span class="sxs-lookup"><span data-stu-id="2517a-107">Once the Skype for Business Cloud Connector Edition installation is complete, perform the steps in this section to configure your deployment and connect it to your Microsoft 365 or Office 365 organization.</span></span>
  
## <a name="configure-firewall-settings"></a><span data-ttu-id="2517a-108">配置防火墙设置</span><span class="sxs-lookup"><span data-stu-id="2517a-108">Configure firewall settings</span></span>

<span data-ttu-id="2517a-109">为外围网络配置内部和外部防火墙设置的防火墙设置，以打开所需端口，如 Plan for Skype [](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) for Business Cloud Connector Edition 中的端口和[协议中所述](plan-skype-for-business-cloud-connector-edition.md)。</span><span class="sxs-lookup"><span data-stu-id="2517a-109">Configure the firewall settings for your internal and external firewall settings for you perimeter network to open the required ports as described in [Ports and protocols](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span>
  
## <a name="set-up-public-switched-telephone-network-pstn-gateways"></a><span data-ttu-id="2517a-110">设置 PSTN 网关 (公用电话) 网</span><span class="sxs-lookup"><span data-stu-id="2517a-110">Set up Public Switched Telephone Network (PSTN) gateways</span></span>

<span data-ttu-id="2517a-111">在每个 PSTN 网关上设置中继，以针对所有设备重新指向中介服务器。</span><span class="sxs-lookup"><span data-stu-id="2517a-111">Set up trunks on each PSTN gateway to point back to Mediation Servers for all appliances.</span></span> <span data-ttu-id="2517a-112">由于池中所有服务器的池 FQDN 都相同，因此每个中继应指向一个中介服务器 FQDN 或 IP 地址，而不是中介服务器池 FQDN。</span><span class="sxs-lookup"><span data-stu-id="2517a-112">Because the pool FQDN is the same for all servers in the pool, each trunk should point to one Mediation Server FQDN or IP address instead of the Mediation Server pool FQDN.</span></span> <span data-ttu-id="2517a-113">应设置相同优先级的中继。</span><span class="sxs-lookup"><span data-stu-id="2517a-113">Trunks should be set in the same priority.</span></span>
  
<span data-ttu-id="2517a-114">如果在中介服务器和网关之间使用 TLS，则需要将网关和中介服务器配置为支持 MTLS，如下所示：</span><span class="sxs-lookup"><span data-stu-id="2517a-114">If you are using TLS between Mediation Servers and gateways, you will need to configure the gateways and Mediation Servers to support MTLS as follows:</span></span>
  
1. <span data-ttu-id="2517a-115">从云连接器 Active Directory 计算机导出根 CA。</span><span class="sxs-lookup"><span data-stu-id="2517a-115">Export the Root CA from the Cloud Connector Active Directory computer.</span></span>
    
2. <span data-ttu-id="2517a-116">按照 PSTN 网关供应商说明导入根 CA。</span><span class="sxs-lookup"><span data-stu-id="2517a-116">Follow the PSTN gateway vendor instructions for importing the Root CA.</span></span>
    
3. <span data-ttu-id="2517a-117">导入在中介服务器上颁发给网关的证书的根 CA 证书。</span><span class="sxs-lookup"><span data-stu-id="2517a-117">Import the Root CA certificate for the certificate issued to your gateway on the Mediation Servers.</span></span> <span data-ttu-id="2517a-118">如果需要获取网关的 SSL 证书，可以使用云连接器 Active Directory 计算机上运行的证书颁发机构服务进行此操作，如下所示：</span><span class="sxs-lookup"><span data-stu-id="2517a-118">If you need to obtain an SSL certificate for the gateway, you may do this using the Certificate Authority service running on the Cloud Connector Active Directory computer as follows:</span></span>
    
   - <span data-ttu-id="2517a-119">修改现有 Web 服务器模板以允许经过身份验证的用户注册，或创建新的 Web 服务器模板以配置其他属性并启用经过身份验证的用户进行注册。</span><span class="sxs-lookup"><span data-stu-id="2517a-119">Modify the existing Web Server template to enable Authenticated users to enroll, or create a new Web Server template to configure other properties and enable Authenticated users to enroll.</span></span> <span data-ttu-id="2517a-120">有关详细说明，请参阅证书 [模板](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc730705(v=ws.11))。</span><span class="sxs-lookup"><span data-stu-id="2517a-120">For detailed instructions, see [Certificate Templates](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc730705(v=ws.11)).</span></span>
    
   - <span data-ttu-id="2517a-121">使用"证书"管理单元（选择已启用的 Web 服务器模板）请求证书。</span><span class="sxs-lookup"><span data-stu-id="2517a-121">Request a certificate using Certificate snap-in selecting the Web Server template that you have enabled.</span></span> <span data-ttu-id="2517a-122">请确保在"主题"中添加"公用名"，在"备用名称"中添加 DNS 名称以及网关的 FQDN，并确认在"私钥"上"使私钥可导出"在"密钥选项"下选中。</span><span class="sxs-lookup"><span data-stu-id="2517a-122">Be sure to add Common name in Subject and DNS name in Alternative name with FQDN of the gateway, and confirm on the Private Key that Make private key exportable is selected under key options.</span></span> 
    
4. <span data-ttu-id="2517a-123">使用私钥导出 SSL 证书，并按照 PSTN 网关供应商提供的说明导入证书。</span><span class="sxs-lookup"><span data-stu-id="2517a-123">Export the SSL certificate with Private key and follow the instructions from your PSTN gateway vendor for importing the certificate.</span></span>
    
## <a name="update-the-domain-for-your-tenant"></a><span data-ttu-id="2517a-124">更新租户的域</span><span class="sxs-lookup"><span data-stu-id="2517a-124">Update the domain for your tenant</span></span>

<span data-ttu-id="2517a-125">请确保已完成在 Microsoft 365 或 Office 365 中更新域的步骤，并且能够添加 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="2517a-125">Make sure that you've completed the steps to update your domain in Microsoft 365 or Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="2517a-126">若要详细了解如何在 Microsoft 365 或 Office 365 中设置域，请参阅将域添加到[Microsoft 365 或 Office 365。](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)</span><span class="sxs-lookup"><span data-stu-id="2517a-126">For more information about how to set up your domain in Microsoft 365 or Office 365, see [Add a domain to Microsoft 365 or Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
  
## <a name="add-dns-records-for-your-edge"></a><span data-ttu-id="2517a-127">为边缘添加 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="2517a-127">Add DNS records for your Edge</span></span>

<span data-ttu-id="2517a-128">将以下 DNS 记录添加到 Microsoft 365 或 Office 365 组织。</span><span class="sxs-lookup"><span data-stu-id="2517a-128">Add the following DNS records to your Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="2517a-129">若要了解如何添加 DNS 记录，请参阅在 [Microsoft 365 或 Office 365](https://support.office.com/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1)中添加或编辑自定义 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="2517a-129">For information about how to add DNS records, see [Add or edit custom DNS records in Microsoft 365 or Office 365](https://support.office.com/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).</span></span>
  
1. <span data-ttu-id="2517a-130">为访问边缘添加 DNS A 记录。</span><span class="sxs-lookup"><span data-stu-id="2517a-130">Add a DNS A record for Access Edge.</span></span>
    
2. <span data-ttu-id="2517a-131">SRV 记录将自动由 Microsoft 365 或 Office 365 和部署脚本创建。</span><span class="sxs-lookup"><span data-stu-id="2517a-131">SRV records will automatically be created by Microsoft 365 or Office 365 and the deployment scripts.</span></span> <span data-ttu-id="2517a-132">确认您可以在边缘上查找以下两个 SIP 服务 \_ ：sip 和 \_ sipfederationtls。</span><span class="sxs-lookup"><span data-stu-id="2517a-132">Confirm that you can look up the following two SIP services on the Edge: \_sip and \_sipfederationtls.</span></span>
    
     ![SRV 记录确认](../../media/3c353a29-6dcc-4ed3-98db-3a6bed3e929e.png)
  
## <a name="set-up-hybrid-connectivity-between-cloud-connector-edition-and-microsoft-365-or-office-365"></a><span data-ttu-id="2517a-134">设置云连接器版本与 Microsoft 365 或 Office 365 之间的混合连接</span><span class="sxs-lookup"><span data-stu-id="2517a-134">Set up hybrid connectivity between Cloud Connector Edition and Microsoft 365 or Office 365</span></span>

<span data-ttu-id="2517a-135">若要配置 Skype for Business 云连接器版本部署与 Microsoft 365 或 Office 365 组织之间的混合连接，在远程 PowerShell 会话中运行以下 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2517a-135">To configure hybrid connectivity between your Skype for Business Cloud Connector Edition deployment and your Microsoft 365 or Office 365 organization, run the following cmdlet in a remote PowerShell session.</span></span> <span data-ttu-id="2517a-136">若要了解如何建立远程 PowerShell 会话，请参阅：为计算机设置[Windows PowerShell。](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="2517a-136">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
<span data-ttu-id="2517a-137">此 cmdlet 设置访问边缘外部 FQDN。</span><span class="sxs-lookup"><span data-stu-id="2517a-137">The cmdlet sets the Access Edge external FQDN.</span></span> <span data-ttu-id="2517a-138">在命令的第一个中， \<External Access Edge FQDN\> 应为 SIP 访问边缘角色的 。</span><span class="sxs-lookup"><span data-stu-id="2517a-138">In the first of the commands, the \<External Access Edge FQDN\> should be the one for the SIP Access Edge role.</span></span> <span data-ttu-id="2517a-139">默认情况下，这应该是 ap. \<Domain Name\> 。</span><span class="sxs-lookup"><span data-stu-id="2517a-139">By default, this should be ap.\<Domain Name\>.</span></span>
  
```powershell
Set-CsTenantHybridConfiguration -PeerDestination <External Access Edge FQDN> -UseOnPremDialPlan $false
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
```

> [!NOTE]
> <span data-ttu-id="2517a-140">用于对等目标的外部访问边缘 FQDN 应设置为 PSTN 站点，该站点仅在用户未分配到 PSTN 站点时用作回退。</span><span class="sxs-lookup"><span data-stu-id="2517a-140">The External Access Edge FQDN used for Peer Destination should be set to a PSTN site that will only be used as a fallback in case a user isn't assigned to a PSTN site.</span></span> <span data-ttu-id="2517a-141">有关详细信息，请参阅在云 [连接器](deploy-a-single-site-in-cloud-connector.md) 中部署单个站点和在云连接器 [中部署多个站点](deploy-multiple-sites-in-cloud-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="2517a-141">For more information, see [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) and [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 
  
## <a name="set-up-pstn-gateways"></a><span data-ttu-id="2517a-142">设置 PSTN 网关</span><span class="sxs-lookup"><span data-stu-id="2517a-142">Set up PSTN gateways</span></span>

<span data-ttu-id="2517a-143">在每个 PSTN 网关上设置中继，以针对所有设备重新指向中介服务器。</span><span class="sxs-lookup"><span data-stu-id="2517a-143">Set up trunks on each PSTN gateway to point back to Mediation Servers for all appliances.</span></span> <span data-ttu-id="2517a-144">每个中继应指向一个中介服务器 FQDN 或 IP 地址，而不是中介服务器池 FQDN，因为池中所有服务器的池 FQDN 都相同。</span><span class="sxs-lookup"><span data-stu-id="2517a-144">Each trunk should point to one Mediation Server FQDN or IP address instead of the Mediation Server pool FQDN because the pool FQDN is the same for all servers in the pool.</span></span> <span data-ttu-id="2517a-145">应设置相同优先级的中继。</span><span class="sxs-lookup"><span data-stu-id="2517a-145">Trunks should be set in the same priority.</span></span>
  
<span data-ttu-id="2517a-146">如果在中介服务器和网关之间使用 TLS，则需要将网关和中介服务器配置为支持 MTLS，如下所示：</span><span class="sxs-lookup"><span data-stu-id="2517a-146">If you are using TLS between Mediation Servers and gateways, you will need to configure the gateways and Mediation Servers to support MTLS as follows:</span></span>
  
1. <span data-ttu-id="2517a-147">从云连接器 Active Directory 计算机导出根 CA。</span><span class="sxs-lookup"><span data-stu-id="2517a-147">Export the Root CA from the Cloud Connector Active Directory computer.</span></span>
    
2. <span data-ttu-id="2517a-148">按照 PSTN 网关供应商说明导入根 CA。</span><span class="sxs-lookup"><span data-stu-id="2517a-148">Follow the PSTN gateway vendor instructions for importing the Root CA.</span></span>
    
3. <span data-ttu-id="2517a-149">导入在中介服务器上颁发给网关的证书的根 CA 证书。</span><span class="sxs-lookup"><span data-stu-id="2517a-149">Import the Root CA certificate for the certificate issued to your gateway on the Mediation Servers.</span></span> <span data-ttu-id="2517a-150">如果需要获取网关的 SSL 证书，可以使用云连接器 Active Directory 计算机上运行的证书颁发机构服务进行此操作，如下所示：</span><span class="sxs-lookup"><span data-stu-id="2517a-150">If you need to obtain an SSL certificate for the gateway, you may do this using the Certificate Authority service running on the Cloud Connector Active Directory computer as follows:</span></span>
    
   - <span data-ttu-id="2517a-151">修改现有 Web 服务器模板以允许经过身份验证的用户注册，或创建新的 Web 服务器模板以配置其他属性并启用经过身份验证的用户进行注册。</span><span class="sxs-lookup"><span data-stu-id="2517a-151">Modify the existing Web Server template to enable Authenticated users to Enroll, or create a new Web Server template to configure other properties and enable Authenticated users to enroll.</span></span> <span data-ttu-id="2517a-152">有关详细说明，请参阅证书 [模板](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc730705(v=ws.11))。</span><span class="sxs-lookup"><span data-stu-id="2517a-152">For detailed instructions, see [Certificate Templates](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc730705(v=ws.11)).</span></span>
    
   - <span data-ttu-id="2517a-153">使用"证书"管理单元（选择已启用的 Web 服务器模板）请求证书。</span><span class="sxs-lookup"><span data-stu-id="2517a-153">Request a certificate using Certificate snap-in selecting the Web Server template that you have enabled.</span></span> <span data-ttu-id="2517a-154">请确保在"主题"中添加"公用名"，在"备用名称"中添加 DNS 名称以及网关的 FQDN，并确认在"私钥"上"使私钥可导出"在"密钥选项"下选中。</span><span class="sxs-lookup"><span data-stu-id="2517a-154">Be sure to add Common name in Subject and DNS name in Alternative name with FQDN of the gateway, and confirm on the Private Key that Make private key exportable is selected under key options.</span></span> 
    
4. <span data-ttu-id="2517a-155">使用私钥导出 SSL 证书，并按照 PSTN 网关供应商提供的说明导入证书。</span><span class="sxs-lookup"><span data-stu-id="2517a-155">Export the SSL certificate with Private key and follow the instructions from your PSTN gateway vendor for importing the certificate.</span></span>
    
5. <span data-ttu-id="2517a-156">一个 PSTN (PSTN) PSTN 网关应仅连接到同一站点 (中介) 服务器。</span><span class="sxs-lookup"><span data-stu-id="2517a-156">PSTN gateway(s) in one PSTN site should only connect to the Mediation Server(s) in the same site.</span></span>
    
## <a name="set-up-your-users"></a><span data-ttu-id="2517a-157">设置用户</span><span class="sxs-lookup"><span data-stu-id="2517a-157">Set up your users</span></span>

<span data-ttu-id="2517a-158">登录到 Microsoft 365 管理中心，添加将启用联机语音服务的用户，并将 E5 许可证或电话系统加载项分配给这些用户的 E3 许可证。</span><span class="sxs-lookup"><span data-stu-id="2517a-158">Log in to the Microsoft 365 admin center, add the users that will be enabled for online voice services, and assign an E5 license or Phone System add-on to the E3 license to these users.</span></span> <span data-ttu-id="2517a-159">有关添加用户的信息，请参阅 [将用户添加到 Microsoft 365 商业版](https://support.office.com/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc)。</span><span class="sxs-lookup"><span data-stu-id="2517a-159">For information about adding users, see [Add users to Microsoft 365 for business](https://support.office.com/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc).</span></span>
  
## <a name="enable-users-for-phone-system-voice-and-voicemail-services"></a><span data-ttu-id="2517a-160">为用户启用电话系统语音和语音邮件服务</span><span class="sxs-lookup"><span data-stu-id="2517a-160">Enable users for Phone System voice and voicemail services</span></span>
 
<span data-ttu-id="2517a-161">将用户添加到 Microsoft 365 或 Office 365 后，为他们的帐户启用电话系统语音服务，包括语音邮件。</span><span class="sxs-lookup"><span data-stu-id="2517a-161">After adding your users to Microsoft 365 or Office 365, enable their accounts for Phone System voice services, including voicemail.</span></span> <span data-ttu-id="2517a-162">若要启用这些功能，必须使用具有全局管理员角色的帐户登录到 Microsoft 365 或 Office 365 组织，并能够运行远程 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="2517a-162">To enable these capabilities, you must log in to your Microsoft 365 or Office 365 organization with an account that is a Global Administrator role, and be able to run remote PowerShell.</span></span> <span data-ttu-id="2517a-163">若要了解如何建立远程 PowerShell 会话，请参阅： [为计算机设置Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="2517a-163">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span></span>
  
- <span data-ttu-id="2517a-164">将策略分配给用户并配置用户的业务语音电话号码（使用 **Identity** 参数的值指定）：</span><span class="sxs-lookup"><span data-stu-id="2517a-164">Assign the policy to your user and configure the user's business voice phone number, which you specify with the value of the **Identity** parameter:</span></span>
    
  ```powershell
  Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI <tel:+phonenumber>
  ```

    > [!NOTE]
    > <span data-ttu-id="2517a-165">可以使用用户的 SIP 地址、用户主体名称 (UPN) 或用户的 Active Directory 显示名称 (例如，"Bob Kelly") 。</span><span class="sxs-lookup"><span data-stu-id="2517a-165">A user identity can be specified using the user's SIP address, user principal name (UPN), or the user's Active Directory display name (for example, "Bob Kelly").</span></span> <span data-ttu-id="2517a-166">星号字符 \* () 显示名称作为用户标识。</span><span class="sxs-lookup"><span data-stu-id="2517a-166">The asterisk (\*) character can also be used with the Display Name as the user Identity.</span></span> <span data-ttu-id="2517a-167">例如，标识"Smith"返回具有以字符串值 \* "Smith"显示名称的所有用户。</span><span class="sxs-lookup"><span data-stu-id="2517a-167">For example, the Identity "\*Smith" returns all the users who have a display name that ends with the string value "Smith".</span></span>
  
<span data-ttu-id="2517a-168">然后，可以使用以下脚本验证用户是否添加和启用：</span><span class="sxs-lookup"><span data-stu-id="2517a-168">You can then verify that the users were added and enabled using the following script:</span></span>
  
```powershell
# Input the user name you want to verify
$user = Get-CsOnlineUser <User name>

# For a hybrid user, the value of $user.EnterpriseVoiceEnabled should be True
$user.EnterpriseVoiceEnabled

# For a hybrid user, the value of $user.HostedVoiceMail should be True
$user.HostedVoiceMail

# For a hybrid user, the value of $user.VoicePolicy should be "HybridVoice"
$user.VoicePolicy
```

<span data-ttu-id="2517a-169">你需要确定你的用户是否应该能够进行国际呼叫。</span><span class="sxs-lookup"><span data-stu-id="2517a-169">You'll need to decide whether your users should be able to make international calls.</span></span> <span data-ttu-id="2517a-170">默认情况下，将启用国际呼叫。</span><span class="sxs-lookup"><span data-stu-id="2517a-170">By default, international calling is enabled.</span></span> <span data-ttu-id="2517a-171">可以使用联机 Skype for Business 管理中心禁用或启用用户进行国际拨号。</span><span class="sxs-lookup"><span data-stu-id="2517a-171">You can disable or enable users for international dialing using the online Skype for Business admin center.</span></span>
  
<span data-ttu-id="2517a-172">若要基于每个用户禁用国际呼叫，请运行 Skype for Business Online PowerShell 中的以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="2517a-172">To disable international calling on a per user basis, run the following cmdlet in Skype for Business Online PowerShell:</span></span>
  
```powershell
Grant-CsVoiceRoutingPolicy -PolicyName InternationalCallsDisallowed -Identity $user
```

<span data-ttu-id="2517a-173">若要在禁用国际呼叫后基于每个用户重新启用该呼叫，请运行相同的 cmdlet，但将 **PolicyName** 的值更改为 *InternationalCallsAllowed*  。</span><span class="sxs-lookup"><span data-stu-id="2517a-173">To re-enable international calling on a per user basis after it has been disabled, run the same cmdlet, but change the value for **PolicyName** to *InternationalCallsAllowed*  .</span></span>
  
## <a name="assign-users-to-pstn-sites"></a><span data-ttu-id="2517a-174">向 PSTN 站点分配用户</span><span class="sxs-lookup"><span data-stu-id="2517a-174">Assign users to PSTN sites</span></span>

<span data-ttu-id="2517a-175">使用租户远程 PowerShell 将网站分配给用户，即使仅部署了一个站点。</span><span class="sxs-lookup"><span data-stu-id="2517a-175">Use tenant remote PowerShell to assign a site to users even if you only deployed a single site.</span></span> <span data-ttu-id="2517a-176">若要了解如何建立远程 PowerShell 会话，请参阅：为计算机设置[Windows PowerShell。](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="2517a-176">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
```powershell
# Set the site to users
Set-CsUserPstnSettings -Identity <User Name> -HybridPstnSite <PSTN Site Name>

# Review the site setting for a user
Get-CsUserPstnSettings -Identity <User Name> 

# See all the user settings in one tenant
Get-CsOnlineUser | Get-CsUserPstnSettings
```

> [!NOTE]
> <span data-ttu-id="2517a-177">如果没有向用户分配 PSTN 站点，Skype for Business 云连接器版本部署与 Microsoft 365 或 Office 365 组织之间的混合连接将回退到使用租户级别默认一个 (对等目标) 以便可以完成呼叫。</span><span class="sxs-lookup"><span data-stu-id="2517a-177">If no PSTN site is assigned to a user, hybrid connectivity between your Skype for Business Cloud Connector Edition deployment and your Microsoft 365 or Office 365 organization will fall back to use the tenant level default one (Peer Destination) so that calls can be completed.</span></span> 
  
## <a name="configure-online-hybrid-mediation-server-settings"></a><span data-ttu-id="2517a-178">配置联机混合中介服务器设置</span><span class="sxs-lookup"><span data-stu-id="2517a-178">Configure online hybrid Mediation Server Settings</span></span>
<span data-ttu-id="2517a-179"><a name="BKMK_ConfigureMediationServer"> </a></span><span class="sxs-lookup"><span data-stu-id="2517a-179"><a name="BKMK_ConfigureMediationServer"> </a></span></span>

<span data-ttu-id="2517a-180">当 P2P 呼叫升级为 PSTN 会议时，Skype for Business Online 会议服务器将向云连接器中介服务器发送邀请。</span><span class="sxs-lookup"><span data-stu-id="2517a-180">When a P2P call is escalated to a PSTN conference, the Skype for Business Online conferencing server will send an invite to the Cloud Connector Mediation Server.</span></span> <span data-ttu-id="2517a-181">若要确保 Microsoft 365 或 Office 365 可以成功路由此邀请，你需要在联机租户中为每个云连接器中介服务器配置设置，如下所示：</span><span class="sxs-lookup"><span data-stu-id="2517a-181">To ensure that Microsoft 365 or Office 365 can route this invite successfully, you need to configure a setting in your online tenant for each Cloud Connector Mediation Server as follows:</span></span> 
  
1. <span data-ttu-id="2517a-182">在 Microsoft 365 管理中心创建用户。</span><span class="sxs-lookup"><span data-stu-id="2517a-182">Create a user in the Microsoft 365 admin center.</span></span> <span data-ttu-id="2517a-183">使用您想要的任何用户名，例如"MediationServer1"。</span><span class="sxs-lookup"><span data-stu-id="2517a-183">Use any user name you want, such as "MediationServer1."</span></span>
    
    <span data-ttu-id="2517a-184">使用云连接器的默认 SIP 域 (.ini 文件的第一个 SIP 域) 用户域。</span><span class="sxs-lookup"><span data-stu-id="2517a-184">Use the default SIP domain of Cloud Connector (the first SIP domain in the .ini file) as the user domain.</span></span>
    
    <span data-ttu-id="2517a-185">请注意，用户传播到 Skype for Business Online 目录仅需要许可证分配。</span><span class="sxs-lookup"><span data-stu-id="2517a-185">Please note that license assignment is only required for the user propagation into the Skype for Business online directory.</span></span> <span data-ttu-id="2517a-186">将 Microsoft 365 或 Office 365 许可证 (（如 E5) ）分配给你创建的帐户，最多允许传播更改一小时，通过运行以下 cmdlet 验证用户帐户是否正确预配到 Skype for Business Online 目录，然后从此帐户中删除许可证。</span><span class="sxs-lookup"><span data-stu-id="2517a-186">Assign a Microsoft 365 or Office 365 license (such as E5) to the account you create, allow up to one hour for the changes to propagate,verify the user accounts has been provisioned correctly to the Skype for Business online directory by running following cmdlet, then remove the license from this account.</span></span>
    ```powershell
   Get-CsOnlineUser -Identity <UserPrincipalName>
   ```
    
2. <span data-ttu-id="2517a-187">使用全局或用户管理员凭据启动租户 Azure AD 远程 PowerShell 会话，然后运行以下 cmdlet，将步骤 1 中配置的 Azure AD 用户帐户的部门设置为"HybridMediationServer"：</span><span class="sxs-lookup"><span data-stu-id="2517a-187">Start a tenant Azure AD remote PowerShell session using your global or user admin credentials, and then run the following cmdlet to set the department for the Azure AD user account configured in step 1 to "HybridMediationServer":</span></span>

   ```powershell
   Set-MsolUser -UserPrincipalName <UserPrincipalName> -Department "HybridMediationServer"
   ```

3. <span data-ttu-id="2517a-188">使用你的 Skype for Business 租户管理员凭据启动租户 Skype for Business 远程 PowerShell 会话，然后运行以下 cmdlet 将中介服务器和边缘服务器 FQDN 设置为该用户帐户，将 替换为你在步骤 1 中创建的帐户的用户的显示名称 \<DisplayName\> ：</span><span class="sxs-lookup"><span data-stu-id="2517a-188">Start a tenant Skype for Business remote PowerShell session using your Skype for Business tenant admin credentials, and then run the following cmdlet to set the Mediation Server and Edge Server FQDN to that user account, replacing \<DisplayName\> with the Display Name of the user for the account you created in step 1:</span></span>
    
   ```powershell
   Set-CsHybridMediationServer -Identity <DisplayName> -Fqdn <MediationServerFQDN> -AccessProxyExternalFqdn <EdgeServerExternalFQDN>
   ```

    <span data-ttu-id="2517a-189">对于 Identity，请使用为此中介服务器创建的用户帐户的显示名称。</span><span class="sxs-lookup"><span data-stu-id="2517a-189">For Identity, use the Display Name of the user account you created for this Mediation Server.</span></span>
    
    <span data-ttu-id="2517a-190">对于  *MediationServerFQDN，*  请使用为中介服务器定义的内部 FQDN。</span><span class="sxs-lookup"><span data-stu-id="2517a-190">For  *MediationServerFQDN*  , use the internal FQDN defined for your Mediation Server.</span></span>
    
    <span data-ttu-id="2517a-191">对于  *EdgeServerExternalFQDN，*  使用为边缘服务器访问代理定义的外部 FQDN。</span><span class="sxs-lookup"><span data-stu-id="2517a-191">For  *EdgeServerExternalFQDN*  , use the external FQDN defined for Edge Server Access Proxy.</span></span> <span data-ttu-id="2517a-192">如果有多个云连接器 PSTN 站点，请选择分配给中介服务器所在的站点的边缘服务器访问代理 FQDN。</span><span class="sxs-lookup"><span data-stu-id="2517a-192">If there are multiple Cloud Connector PSTN sites, choose the Edge Server Access Proxy FQDN assigned to the site where the Mediation Server is located.</span></span>
    
4. <span data-ttu-id="2517a-193">如果有多个云连接器中介服务器 (站点 HA) ，请对每个服务器重复上述步骤。</span><span class="sxs-lookup"><span data-stu-id="2517a-193">If there are multiple Cloud Connector Mediation Servers (multiple-site, HA), please repeat the previous steps for each of them.</span></span>
