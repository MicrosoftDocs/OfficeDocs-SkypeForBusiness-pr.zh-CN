---
title: 配置云连接器与 Office 365 租户的集成
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0e2f2395-b890-4d16-aa2d-99d52438b89c
description: 了解如何配置云连接器与 Office 365 租户的集成。
ms.openlocfilehash: 01a3eac7356846b7d3b153ff4e01c9b52c3744ce
ms.sourcegitcommit: 5943c41bac520558733d08f4a9ecc4425c422ff9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22599412"
---
# <a name="configure-cloud-connector-integration-with-your-office-365-tenant"></a><span data-ttu-id="a2360-103">配置云连接器与 Office 365 租户的集成</span><span class="sxs-lookup"><span data-stu-id="a2360-103">Configure Cloud Connector integration with your Office 365 tenant</span></span>
 
<span data-ttu-id="a2360-104">了解如何配置云连接器与 Office 365 租户的集成。</span><span class="sxs-lookup"><span data-stu-id="a2360-104">Learn how to configure Cloud Connector integration with your Office 365 tenant.</span></span>
  
<span data-ttu-id="a2360-105">Skype for Business Cloud Connector Edition 安装完成后，执行本节中的步骤，以配置你的部署并将其连接到你的 Office 365 租户。</span><span class="sxs-lookup"><span data-stu-id="a2360-105">Once the Skype for Business Cloud Connector Edition installation is complete, perform the steps in this section to configure your deployment and connect it to your Office 365 tenant.</span></span>
  
## <a name="configure-firewall-settings"></a><span data-ttu-id="a2360-106">配置防火墙设置</span><span class="sxs-lookup"><span data-stu-id="a2360-106">Configure firewall settings</span></span>

<span data-ttu-id="a2360-107">配置外围网络的内部和外部防火墙设置，以打开所需的端口[的端口和协议](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports)中[规划商业云连接器 edition Skype](plan-skype-for-business-cloud-connector-edition.md)中所述的防火墙设置。</span><span class="sxs-lookup"><span data-stu-id="a2360-107">Configure the firewall settings for your internal and external firewall settings for you perimeter network to open the required ports as described in [Ports and protocols](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span>
  
## <a name="set-up-public-switched-telephone-network-pstn-gateways"></a><span data-ttu-id="a2360-108">设置公用电话交换网 (PSTN) 网关</span><span class="sxs-lookup"><span data-stu-id="a2360-108">Set up Public Switched Telephone Network (PSTN) gateways</span></span>

<span data-ttu-id="a2360-p101">将每个 PSTN 网关上的中继设置为重新指向所有设备的中介服务器。由于池中所有服务器具有相同的池 FQDN，因此每个中继应指向一个中介服务器 FQDN 或 IP 地址，而不是中介服务器池 FQDN。应为中继设置相同的优先级。</span><span class="sxs-lookup"><span data-stu-id="a2360-p101">Set up trunks on each PSTN gateway to point back to Mediation Servers for all appliances. Because the pool FQDN is the same for all servers in the pool, each trunk should point to one Mediation Server FQDN or IP address instead of the Mediation Server pool FQDN. Trunks should be set in the same priority.</span></span>
  
<span data-ttu-id="a2360-112">如果在中介服务器和网关之间使用 TLS，则需要将网关和中介服务器配置为支持 MTLS，如下所述：</span><span class="sxs-lookup"><span data-stu-id="a2360-112">If you are using TLS between Mediation Servers and gateways, you will need to configure the gateways and Mediation Servers to support MTLS as follows:</span></span>
  
1. <span data-ttu-id="a2360-113">从云连接器 Active Directory 计算机导出根 CA。</span><span class="sxs-lookup"><span data-stu-id="a2360-113">Export the Root CA from the Cloud Connector Active Directory computer.</span></span>
    
2. <span data-ttu-id="a2360-114">按照 PSTN 网关供应商的说明导入根 CA。</span><span class="sxs-lookup"><span data-stu-id="a2360-114">Follow the PSTN gateway vendor instructions for importing the Root CA.</span></span>
    
3. <span data-ttu-id="a2360-p102">在中介服务器上导入颁发给网关的证书的根 CA 证书。如果需要为网关获取 SSL 证书，可以使用云连接器 Active Directory 计算机上运行的证书颁发机构服务执行此操作，如下所述：</span><span class="sxs-lookup"><span data-stu-id="a2360-p102">Import the Root CA certificate for the certificate issued to your gateway on the Mediation Servers. If you need to obtain an SSL certificate for the gateway, you may do this using the Certificate Authority service running on the Cloud Connector Active Directory computer as follows:</span></span>
    
  - <span data-ttu-id="a2360-117">修改现有 Web 服务器模板，以允许经过身份验证的用户注册，或创建新的 Web 服务器模板，以配置其他属性并允许经过身份验证的用户注册。</span><span class="sxs-lookup"><span data-stu-id="a2360-117">Modify the existing Web Server template to enable Authenticated users to enroll, or create a new Web Server template to configure other properties and enable Authenticated users to enroll.</span></span> <span data-ttu-id="a2360-118">有关详细说明，请参阅[证书模板](https://technet.microsoft.com/en-us/library/cc730705.aspx)。</span><span class="sxs-lookup"><span data-stu-id="a2360-118">For detailed instructions, see [Certificate Templates](https://technet.microsoft.com/en-us/library/cc730705.aspx).</span></span>
    
  - <span data-ttu-id="a2360-119">使用证书管理单元申请证书，选择你已启用的 Web 服务器模板。</span><span class="sxs-lookup"><span data-stu-id="a2360-119">Request a certificate using Certificate snap-in selecting the Web Server template that you have enabled.</span></span> <span data-ttu-id="a2360-120">请确保使用网关的 FQDN 在“使用者名称”中添加公用名，在“备用名称”中添加 DNS 名称，并确认在“私钥”上选中“密钥选项”下的“使私钥可以导出”。</span><span class="sxs-lookup"><span data-stu-id="a2360-120">Be sure to add Common name in Subject and DNS name in Alternative name with FQDN of the gateway, and confirm on the Private Key that Make private key exportable is selected under key options.</span></span> 
    
4. <span data-ttu-id="a2360-121">使用私有密钥导出 SSL 证书，并按照 PSTN 网关供应商的说明导入证书。</span><span class="sxs-lookup"><span data-stu-id="a2360-121">Export the SSL certificate with Private key and follow the instructions from your PSTN gateway vendor for importing the certificate.</span></span>
    
## <a name="update-the-domain-for-your-tenant"></a><span data-ttu-id="a2360-122">为你的租户更新域</span><span class="sxs-lookup"><span data-stu-id="a2360-122">Update the domain for your tenant</span></span>

<span data-ttu-id="a2360-123">确保你已完成在 Office 365 中更新域的步骤并且能够添加 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="a2360-123">Make sure that you've completed the steps to update your domain in Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="a2360-124">有关如何设置您在 Office 365 中的域的详细信息，请参阅[添加到 Office 365 域](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)。</span><span class="sxs-lookup"><span data-stu-id="a2360-124">For more information about how to set up your domain in Office 365, see [Add a domain to Office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
  
## <a name="add-dns-records-in-office-365-for-your-edge"></a><span data-ttu-id="a2360-125">在 Office 365 中为边缘添加 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="a2360-125">Add DNS records in Office 365 for your Edge</span></span>

<span data-ttu-id="a2360-126">将以下 DNS 记录添加到 Office 365 租户。</span><span class="sxs-lookup"><span data-stu-id="a2360-126">Add the following DNS records to your Office 365 tenant.</span></span> <span data-ttu-id="a2360-127">有关如何将 DNS 记录添加到 Office 365 租户的信息，请参阅[添加或编辑自定义中的 DNS 记录 Office 365](https://support.office.com/en-us/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1)。</span><span class="sxs-lookup"><span data-stu-id="a2360-127">For information about how to add DNS records to your Office 365 tenant, see [Add or edit custom DNS records in Office 365](https://support.office.com/en-us/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).</span></span>
  
1. <span data-ttu-id="a2360-128">为访问边缘添加 DNS A 记录。</span><span class="sxs-lookup"><span data-stu-id="a2360-128">Add a DNS A record for Access Edge.</span></span>
    
2. <span data-ttu-id="a2360-p107">SRV 记录将由 Office 365 和部署脚本自动创建。确认你可以在边缘上查找以下两个 SIP 服务：_sip 和 _sipfederationtls。</span><span class="sxs-lookup"><span data-stu-id="a2360-p107">SRV records will automatically be created by Office 365 and the deployment scripts. Confirm that you can look up the following two SIP services on the Edge: _sip and _sipfederationtls.</span></span>
    
     ![SRV 记录确认](../../media/3c353a29-6dcc-4ed3-98db-3a6bed3e929e.png)
  
## <a name="set-up-hybrid-connectivity-between-cloud-connector-edition-and-office-365"></a><span data-ttu-id="a2360-132">在云连接器版本与 Office 365 之间设置混合连接</span><span class="sxs-lookup"><span data-stu-id="a2360-132">Set up hybrid connectivity between Cloud Connector Edition and Office 365</span></span>

<span data-ttu-id="a2360-133">若要配置混合部署业务云连接器 Edition 您 Skype 和 Office 365 租户之间的连接，请在远程 PowerShell 会话中运行以下 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a2360-133">To configure hybrid connectivity between your Skype for Business Cloud Connector Edition deployment and your Office 365 tenant, run the following cmdlet in a remote PowerShell session.</span></span> <span data-ttu-id="a2360-134">若要了解如何建立一个远程 PowerShell 会话，请参阅： [Windows PowerShell 将计算机设置](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="a2360-134">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx).</span></span>
  
<span data-ttu-id="a2360-135">此 cmdlet 会设置访问边缘外部 FQDN。</span><span class="sxs-lookup"><span data-stu-id="a2360-135">The cmdlet sets the Access Edge external FQDN.</span></span> <span data-ttu-id="a2360-136">在第一个命令，\<访问的外部边缘 FQDN\>应为 SIP 访问边缘角色。</span><span class="sxs-lookup"><span data-stu-id="a2360-136">In the first of the commands, the \<External Access Edge FQDN\> should be the one for the SIP Access Edge role.</span></span> <span data-ttu-id="a2360-137">默认情况下，应为 ap.\<域名\>。</span><span class="sxs-lookup"><span data-stu-id="a2360-137">By default, this should be ap.\<Domain Name\>.</span></span>
  
```
Set-CsTenantHybridConfiguration -PeerDestination <External Access Edge FQDN> -UseOnPremDialPlan $false
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
```

> [!NOTE]
> <span data-ttu-id="a2360-138">用于对等方目标外部访问边缘 FQDN 应设置为一个 PSTN 网站，仅将在用户未分配到 PSTN 站点的情况下使用用作后备。</span><span class="sxs-lookup"><span data-stu-id="a2360-138">The External Access Edge FQDN used for Peer Destination should be set to a PSTN site that will only be used as a fallback in case a user isn't assigned to a PSTN site.</span></span> <span data-ttu-id="a2360-139">有关详细信息，请参阅[部署云 Connector 中单个网站](deploy-a-single-site-in-cloud-connector.md)和[部署云 Connector 中的多个网站](deploy-multiple-sites-in-cloud-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="a2360-139">For more information, see [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) and [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 
  
## <a name="set-up-pstn-gateways"></a><span data-ttu-id="a2360-140">设置 PSTN 网关</span><span class="sxs-lookup"><span data-stu-id="a2360-140">Set up PSTN gateways</span></span>

<span data-ttu-id="a2360-p111">将每个 PSTN 网关上的中继设置为重新指向所有设备的中介服务器。由于池中所有服务器具有相同的池 FQDN，因此每个中继应指向一个中介服务器 FQDN 或 IP 地址，而不是中介服务器池 FQDN。应为中继设置相同的优先级。</span><span class="sxs-lookup"><span data-stu-id="a2360-p111">Set up trunks on each PSTN gateway to point back to Mediation Servers for all appliances. Each trunk should point to one Mediation Server FQDN or IP address instead of the Mediation Server pool FQDN because the pool FQDN is the same for all servers in the pool. Trunks should be set in the same priority.</span></span>
  
<span data-ttu-id="a2360-144">如果在中介服务器和网关之间使用 TLS，则需要将网关和中介服务器配置为支持 MTLS，如下所述：</span><span class="sxs-lookup"><span data-stu-id="a2360-144">If you are using TLS between Mediation Servers and gateways, you will need to configure the gateways and Mediation Servers to support MTLS as follows:</span></span>
  
1. <span data-ttu-id="a2360-145">从云连接器 Active Directory 计算机导出根 CA。</span><span class="sxs-lookup"><span data-stu-id="a2360-145">Export the Root CA from the Cloud Connector Active Directory computer.</span></span>
    
2. <span data-ttu-id="a2360-146">按照 PSTN 网关供应商的说明导入根 CA。</span><span class="sxs-lookup"><span data-stu-id="a2360-146">Follow the PSTN gateway vendor instructions for importing the Root CA.</span></span>
    
3. <span data-ttu-id="a2360-p112">在中介服务器上导入颁发给网关的证书的根 CA 证书。如果需要为网关获取 SSL 证书，可以使用云连接器 Active Directory 计算机上运行的证书颁发机构服务执行此操作，如下所述：</span><span class="sxs-lookup"><span data-stu-id="a2360-p112">Import the Root CA certificate for the certificate issued to your gateway on the Mediation Servers. If you need to obtain an SSL certificate for the gateway, you may do this using the Certificate Authority service running on the Cloud Connector Active Directory computer as follows:</span></span>
    
  - <span data-ttu-id="a2360-149">修改现有 Web 服务器模板，以允许经过身份验证的用户注册，或创建新的 Web 服务器模板，以配置其他属性并允许经过身份验证的用户注册。</span><span class="sxs-lookup"><span data-stu-id="a2360-149">Modify the existing Web Server template to enable Authenticated users to Enroll, or create a new Web Server template to configure other properties and enable Authenticated users to enroll.</span></span> <span data-ttu-id="a2360-150">有关详细说明，请参阅[证书模板](https://technet.microsoft.com/library/cc730705.aspx)。</span><span class="sxs-lookup"><span data-stu-id="a2360-150">For detailed instructions, see [Certificate Templates](https://technet.microsoft.com/library/cc730705.aspx).</span></span>
    
  - <span data-ttu-id="a2360-151">使用证书管理单元申请证书，选择你已启用的 Web 服务器模板。</span><span class="sxs-lookup"><span data-stu-id="a2360-151">Request a certificate using Certificate snap-in selecting the Web Server template that you have enabled.</span></span> <span data-ttu-id="a2360-152">请确保使用网关的 FQDN 在“使用者名称”中添加公用名，在“备用名称”中添加 DNS 名称，并确认在“私钥”上选中“密钥选项”下的“使私钥可以导出”。</span><span class="sxs-lookup"><span data-stu-id="a2360-152">Be sure to add Common name in Subject and DNS name in Alternative name with FQDN of the gateway, and confirm on the Private Key that Make private key exportable is selected under key options.</span></span> 
    
4. <span data-ttu-id="a2360-153">使用私有密钥导出 SSL 证书，并按照 PSTN 网关供应商的说明导入证书。</span><span class="sxs-lookup"><span data-stu-id="a2360-153">Export the SSL certificate with Private key and follow the instructions from your PSTN gateway vendor for importing the certificate.</span></span>
    
5. <span data-ttu-id="a2360-154">一个 PSTN 站点中的 PSTN 网关应只连接到同一站点中的中介服务器。</span><span class="sxs-lookup"><span data-stu-id="a2360-154">PSTN gateway(s) in one PSTN site should only connect to the Mediation Server(s) in the same site.</span></span>
    
## <a name="set-up-your-users-in-office-365"></a><span data-ttu-id="a2360-155">在 Office 365 中设置用户</span><span class="sxs-lookup"><span data-stu-id="a2360-155">Set up your users in Office 365</span></span>

<span data-ttu-id="a2360-156">登录 Office 365 管理门户，添加将启用在线语音服务的用户，并向这些用户分配 E5 许可证或基于 E3 许可证的 Office 365 电话系统附加许可证。</span><span class="sxs-lookup"><span data-stu-id="a2360-156">Log in to the Office 365 admin portal, add the users that will be enabled for online voice services, and assign an E5 license or Phone System in Office 365 add-on to the E3 license to these users.</span></span> <span data-ttu-id="a2360-157">有关添加用户的信息，请参阅[添加用户移动到 Office 365 的业务](https://support.office.com/en-US/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc)。</span><span class="sxs-lookup"><span data-stu-id="a2360-157">For information about adding users, see [Add users to Office 365 for business](https://support.office.com/en-US/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc).</span></span>
  
## <a name="enable-users-for-phone-system-in-office-365-voice-and-voicemail-services"></a><span data-ttu-id="a2360-158">为用户启用 Office 365 电话系统语音和语音邮件服务</span><span class="sxs-lookup"><span data-stu-id="a2360-158">Enable users for Phone System in Office 365 voice and voicemail services</span></span>

<span data-ttu-id="a2360-159">将用户添加到 Office 365 之后，为其帐户启用 Office 365 电话系统语音服务，包括语音邮件。</span><span class="sxs-lookup"><span data-stu-id="a2360-159">After adding your users to Office 365, enable their accounts for Phone System in Office 365 voice services, including voicemail.</span></span> <span data-ttu-id="a2360-160">要启用这些功能，必须使用具有 Office 365 全局管理员角色的帐户登录你的 Office 365 租户，并且能够运行远程 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="a2360-160">To enable these capabilities, you must log in to your Office 365 tenant with an account that is an Office 365 Global Administrator role, and be able to run remote PowerShell.</span></span> <span data-ttu-id="a2360-161">若要了解如何建立一个远程 PowerShell 会话，请参阅： [Windows PowerShell 将计算机设置](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a2360-161">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx)</span></span>
  
- <span data-ttu-id="a2360-162">向用户分配策略和配置用户的企业语音电话号码，指定**Identity**参数的值：</span><span class="sxs-lookup"><span data-stu-id="a2360-162">Assign the policy to your user and configure the user's business voice phone number, which you specify with the value of the **Identity** parameter:</span></span>
    
  ```
  Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI <tel:+phonenumber>
  ```

    > [!NOTE]
    > <span data-ttu-id="a2360-163">也可以通过用户的 SIP 地址、用户主体名称 (UPN)、域名和用户名（域\用户名）以及 Active Directory 中的显示名称（“Bob Kelly”）来指定用户身份。</span><span class="sxs-lookup"><span data-stu-id="a2360-163">You can also specify a user's Identity by their SIP address, User Principal name (UPN), domain name and username (domain\username), and display name in Active Directory ("Bob Kelly").</span></span> 
  
<span data-ttu-id="a2360-164">然后，可以使用以下脚本验证是否已添加并启用用户：</span><span class="sxs-lookup"><span data-stu-id="a2360-164">You can then verify that the users were added and enabled using the following script:</span></span>
  
```
# Input the user name you want to verify
$user = Get-CsOnlineUser <User name>

# For a hybrid user, the value of $user.EnterpriseVoiceEnabled should be True
$user.EnterpriseVoiceEnabled

# For a hybrid user, the value of $user.HostedVoiceMail should be True
$user.HostedVoiceMail

# For a hybrid user, the value of $user.VoicePolicy should be "HybridVoice"
$user.VoicePolicy
```

<span data-ttu-id="a2360-p117">你将需要确定用户是否可以进行国际呼叫。默认情况下，启用国际呼叫。你可以使用在线 Skype for Business 管理中心禁止或允许用户进行国际呼叫。</span><span class="sxs-lookup"><span data-stu-id="a2360-p117">You'll need to decide whether your users should be able to make international calls. By default, international calling is enabled. You can disable or enable users for international dialing using the online Skype for Business admin center.</span></span>
  
<span data-ttu-id="a2360-168">要按用户禁用国际呼叫，请在 Skype for Business Online PowerShell 中运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="a2360-168">To disable international calling on a per user basis, run the following cmdlet in Skype for Business Online PowerShell:</span></span>
  
```
Grant-CsVoiceRoutingPolicy -PolicyName InternationalCallsDisallowed -Identity $user
```

<span data-ttu-id="a2360-169">若要重新启用国际后已禁用调用基于每个用户，请运行相同 cmdlet，但将值更改为*InternationalCallsAllowed* **PolicyName** 。</span><span class="sxs-lookup"><span data-stu-id="a2360-169">To re-enable international calling on a per user basis after it has been disabled, run the same cmdlet, but change the value for **PolicyName** to *InternationalCallsAllowed*  .</span></span>
  
## <a name="assign-users-to-pstn-sites"></a><span data-ttu-id="a2360-170">将用户分配到 PSTN 站点</span><span class="sxs-lookup"><span data-stu-id="a2360-170">Assign users to PSTN sites</span></span>

<span data-ttu-id="a2360-171">使用租户远程 PowerShell 向用户分配站点，即使只部署了一个站点也需要执行此操作。</span><span class="sxs-lookup"><span data-stu-id="a2360-171">Use tenant remote PowerShell to assign a site to users even if you only deployed a single site.</span></span> <span data-ttu-id="a2360-172">若要了解如何建立一个远程 PowerShell 会话，请参阅： [Windows PowerShell 将计算机设置](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="a2360-172">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx).</span></span>
  
```
# Set the site to users
Set-CsUserPstnSettings -Identity <User Name> -HybridPstnSite <PSTN Site Name>

# Review the site setting for a user
Get-CsUserPstnSettings -Identity <User Name> 

# See all the user settings in one tenant
Get-CsOnlineUser | Get-CsUserPstnSettings
```

> [!NOTE]
> <span data-ttu-id="a2360-173">如果没有向用户分配 PSTN 站点，Skype for Business 云连接器版本部署与 Office 365 租户之间的混合连接将回退到使用租户级默认站点（对等目的），才能完成呼叫。</span><span class="sxs-lookup"><span data-stu-id="a2360-173">If no PSTN site is assigned to a user, hybrid connectivity between your Skype for Business Cloud Connector Edition deployment and your Office 365 tenant will fall back to use the tenant level default one (Peer Destination) so that calls can be completed.</span></span> 
  
## <a name="configure-online-hybrid-mediation-server-settings"></a><span data-ttu-id="a2360-174">配置联机混合中介服务器设置</span><span class="sxs-lookup"><span data-stu-id="a2360-174">Configure online hybrid Mediation Server Settings</span></span>
<span data-ttu-id="a2360-175"><a name="BKMK_ConfigureMediationServer"> </a></span><span class="sxs-lookup"><span data-stu-id="a2360-175"></span></span>

<span data-ttu-id="a2360-176">当 P2P 呼叫提升到 PSTN 会议，否则时，业务联机会议服务器的 Skype 将发送到云连接器中介服务器的邀请。</span><span class="sxs-lookup"><span data-stu-id="a2360-176">When a P2P call is escalated to a PSTN conference, the Skype for Business Online conferencing server will send an invite to the Cloud Connector Mediation Server.</span></span> <span data-ttu-id="a2360-177">若要确保 Office 365 可以成功路由该邀请，您需要 online 租户的每台云连接器中介服务器中，如下所示配置设置：</span><span class="sxs-lookup"><span data-stu-id="a2360-177">To ensure that Office 365 can route this invite successfully, you need to configure a setting in your online tenant for each Cloud Connector Mediation Server as follows:</span></span> 
  
1. <span data-ttu-id="a2360-178">在 Office 365 管理门户中创建一个用户。</span><span class="sxs-lookup"><span data-stu-id="a2360-178">Create a user in the Office 365 admin portal.</span></span> <span data-ttu-id="a2360-179">使用任何用户名称您希望，如"MediationServer1。"</span><span class="sxs-lookup"><span data-stu-id="a2360-179">Use any user name you want, such as "MediationServer1."</span></span>
    
    <span data-ttu-id="a2360-180">用作用户域云连接器 （.ini 文件中的第一个 SIP 域） 的默认 SIP 域。</span><span class="sxs-lookup"><span data-stu-id="a2360-180">Use the default SIP domain of Cloud Connector (the first SIP domain in the .ini file) as the user domain.</span></span>
    
    <span data-ttu-id="a2360-181">请注意，只是许可证分配所需的用户传播到业务联机目录 Skype。</span><span class="sxs-lookup"><span data-stu-id="a2360-181">Please note that license assignment is only required for the user propagation into the Skype for Business online directory.</span></span> <span data-ttu-id="a2360-182">将 Office 365 许可证 （如 E5) 分配给创建，允许达 1 小时，更改将传播，然后从该帐户删除许可证的帐户。</span><span class="sxs-lookup"><span data-stu-id="a2360-182">Assign an Office 365 licenses (such as E5) to the account you create, allow up to one hour for the changes to propagate, then remove the license from this account.</span></span>
    
2. <span data-ttu-id="a2360-183">开始使用您全局租户 Azure AD 远程 PowerShell 会话或用户管理员凭据，并向"HybridMediationServer"，然后运行以下 cmdlet，以设置 Azure AD 用户帐户的部门中的配置步骤 1:</span><span class="sxs-lookup"><span data-stu-id="a2360-183">Start a tenant Azure AD remote PowerShell session using your global or user admin credentials, and then run the following cmdlet to set the department for the Azure AD user account configured in step 1 to "HybridMediationServer":</span></span>

 ```
  Set-MsolUser -UserPrincipalName <UserPrincipalName> -Department "HybridMediationServer"
  ```

3. <span data-ttu-id="a2360-184">使用您 Skype 业务租户管理凭据，然后运行以下 cmdlet 以将中介服务器和边缘服务器 FQDN 设置为该用户帐户，替换业务远程 PowerShell 会话启动租户 Skype \<DisplayName\>用户帐户的显示名称与您创建在步骤 1 中：</span><span class="sxs-lookup"><span data-stu-id="a2360-184">Start a tenant Skype for Business remote PowerShell session using your Skype for Business tenant admin credentials, and then run the following cmdlet to set the Mediation Server and Edge Server FQDN to that user account, replacing \<DisplayName\> with the Display Name of the user for the account you created in step 1:</span></span>
    
  ```
  Set-CsHybridMediationServer -Identity <DisplayName> -Fqdn <MediationServerFQDN> -AccessProxyExternalFqdn <EdgeServerExternalFQDN>
  ```

    <span data-ttu-id="a2360-185">对于“标识”，请使用你为此中介服务器创建的 Office 365 用户帐户的显示名称。</span><span class="sxs-lookup"><span data-stu-id="a2360-185">For Identity, use the Display Name of the Office 365 user account you created for this Mediation Server.</span></span>
    
    <span data-ttu-id="a2360-186">对于*MediationServerFQDN* ，使用定义中介服务器的内部 FQDN。</span><span class="sxs-lookup"><span data-stu-id="a2360-186">For  *MediationServerFQDN*  , use the internal FQDN defined for your Mediation Server.</span></span>
    
    <span data-ttu-id="a2360-187">对于*EdgeServerExternalFQDN* ，使用定义为边缘服务器访问代理服务器的外部 FQDN。</span><span class="sxs-lookup"><span data-stu-id="a2360-187">For  *EdgeServerExternalFQDN*  , use the external FQDN defined for Edge Server Access Proxy.</span></span> <span data-ttu-id="a2360-188">如果存在多个云连接器 PSTN 站点，请选择分配给中介服务器所在站点的边缘服务器访问代理 FQDN。</span><span class="sxs-lookup"><span data-stu-id="a2360-188">If there are multiple Cloud Connector PSTN sites, choose the Edge Server Access Proxy FQDN assigned to the site where the Mediation Server is located.</span></span>
    
3. <span data-ttu-id="a2360-189">如果存在多台云连接器中介服务器（多站点，高可用性），请对每台服务器重复执行上述步骤。</span><span class="sxs-lookup"><span data-stu-id="a2360-189">If there are multiple Cloud Connector Mediation Servers (multiple-site, HA), please repeat the previous steps for each of them.</span></span>
    

