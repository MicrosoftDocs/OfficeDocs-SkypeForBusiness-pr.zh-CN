---
title: 配置与 Microsoft 365 或 Office 365 组织的云连接器集成
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
ms.openlocfilehash: 2c65551ce75efce61f82d47ac2b9c16db555ab42
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221242"
---
# <a name="configure-cloud-connector-integration-with-your-microsoft-365-or-office-365-organization"></a><span data-ttu-id="bbcc2-103">配置与 Microsoft 365 或 Office 365 组织的云连接器集成</span><span class="sxs-lookup"><span data-stu-id="bbcc2-103">Configure Cloud Connector integration with your Microsoft 365 or Office 365 organization</span></span>
 
<span data-ttu-id="bbcc2-104">了解如何配置与 Microsoft 365 或 Office 365 组织的云连接器集成。</span><span class="sxs-lookup"><span data-stu-id="bbcc2-104">Learn how to configure Cloud Connector integration with your Microsoft 365 or Office 365 organization.</span></span>
  
<span data-ttu-id="bbcc2-105">在 Skype for Business 云连接器版本安装完成后，执行本节中的步骤以配置部署，并将其连接到 Microsoft 365 或 Office 365 组织。</span><span class="sxs-lookup"><span data-stu-id="bbcc2-105">Once the Skype for Business Cloud Connector Edition installation is complete, perform the steps in this section to configure your deployment and connect it to your Microsoft 365 or Office 365 organization.</span></span>
  
## <a name="configure-firewall-settings"></a><span data-ttu-id="bbcc2-106">配置防火墙设置</span><span class="sxs-lookup"><span data-stu-id="bbcc2-106">Configure firewall settings</span></span>

<span data-ttu-id="bbcc2-107">为您的外围网络配置内部和外部防火墙设置的防火墙设置，以按照[Plan For Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md)中的[端口和协议](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports)中所述打开所需端口。</span><span class="sxs-lookup"><span data-stu-id="bbcc2-107">Configure the firewall settings for your internal and external firewall settings for you perimeter network to open the required ports as described in [Ports and protocols](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span>
  
## <a name="set-up-public-switched-telephone-network-pstn-gateways"></a><span data-ttu-id="bbcc2-108">设置公共交换电话网络（PSTN）网关</span><span class="sxs-lookup"><span data-stu-id="bbcc2-108">Set up Public Switched Telephone Network (PSTN) gateways</span></span>

<span data-ttu-id="bbcc2-109">将每个 PSTN 网关上的中继设置为指向所有设备的中介服务器。</span><span class="sxs-lookup"><span data-stu-id="bbcc2-109">Set up trunks on each PSTN gateway to point back to Mediation Servers for all appliances.</span></span> <span data-ttu-id="bbcc2-110">由于池中的所有服务器的池 FQDN 都是相同的，因此每个中继都应指向一个中介服务器 FQDN 或 IP 地址，而不是中介服务器池的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="bbcc2-110">Because the pool FQDN is the same for all servers in the pool, each trunk should point to one Mediation Server FQDN or IP address instead of the Mediation Server pool FQDN.</span></span> <span data-ttu-id="bbcc2-111">应按相同的优先级设置中继。</span><span class="sxs-lookup"><span data-stu-id="bbcc2-111">Trunks should be set in the same priority.</span></span>
  
<span data-ttu-id="bbcc2-112">如果要在中介服务器和网关之间使用 TLS，则需要将网关和中介服务器配置为支持 MTLS，如下所示：</span><span class="sxs-lookup"><span data-stu-id="bbcc2-112">If you are using TLS between Mediation Servers and gateways, you will need to configure the gateways and Mediation Servers to support MTLS as follows:</span></span>
  
1. <span data-ttu-id="bbcc2-113">从云连接器 Active Directory 计算机导出根 CA。</span><span class="sxs-lookup"><span data-stu-id="bbcc2-113">Export the Root CA from the Cloud Connector Active Directory computer.</span></span>
    
2. <span data-ttu-id="bbcc2-114">按照 PSTN 网关供应商的说明导入根 CA。</span><span class="sxs-lookup"><span data-stu-id="bbcc2-114">Follow the PSTN gateway vendor instructions for importing the Root CA.</span></span>
    
3. <span data-ttu-id="bbcc2-115">在中介服务器上导入颁发给您的网关的证书的根 CA 证书。</span><span class="sxs-lookup"><span data-stu-id="bbcc2-115">Import the Root CA certificate for the certificate issued to your gateway on the Mediation Servers.</span></span> <span data-ttu-id="bbcc2-116">如果需要为网关获取 SSL 证书，可以使用在云连接器 Active Directory 计算机上运行的证书颁发机构服务执行此操作，如下所示：</span><span class="sxs-lookup"><span data-stu-id="bbcc2-116">If you need to obtain an SSL certificate for the gateway, you may do this using the Certificate Authority service running on the Cloud Connector Active Directory computer as follows:</span></span>
    
   - <span data-ttu-id="bbcc2-117">修改现有 Web 服务器模板，以允许经过身份验证的用户注册，或创建新的 Web 服务器模板以配置其他属性并允许经过身份验证的用户进行注册。</span><span class="sxs-lookup"><span data-stu-id="bbcc2-117">Modify the existing Web Server template to enable Authenticated users to enroll, or create a new Web Server template to configure other properties and enable Authenticated users to enroll.</span></span> <span data-ttu-id="bbcc2-118">有关详细说明，请参阅[证书模板](https://technet.microsoft.com/library/cc730705.aspx)。</span><span class="sxs-lookup"><span data-stu-id="bbcc2-118">For detailed instructions, see [Certificate Templates](https://technet.microsoft.com/library/cc730705.aspx).</span></span>
    
   - <span data-ttu-id="bbcc2-119">使用 "证书" 管理单元请求证书选择已启用的 Web 服务器模板。</span><span class="sxs-lookup"><span data-stu-id="bbcc2-119">Request a certificate using Certificate snap-in selecting the Web Server template that you have enabled.</span></span> <span data-ttu-id="bbcc2-120">请务必在 "主题" 和 "DNS 名称" 中添加与网关的 FQDN 相同的通用名称，并在 "密钥选项" 下选择 "使密钥可导出的私钥"。</span><span class="sxs-lookup"><span data-stu-id="bbcc2-120">Be sure to add Common name in Subject and DNS name in Alternative name with FQDN of the gateway, and confirm on the Private Key that Make private key exportable is selected under key options.</span></span> 
    
4. <span data-ttu-id="bbcc2-121">使用私钥导出 SSL 证书，并按照来自 PSTN 网关供应商的说明导入证书。</span><span class="sxs-lookup"><span data-stu-id="bbcc2-121">Export the SSL certificate with Private key and follow the instructions from your PSTN gateway vendor for importing the certificate.</span></span>
    
## <a name="update-the-domain-for-your-tenant"></a><span data-ttu-id="bbcc2-122">为你的租户更新域</span><span class="sxs-lookup"><span data-stu-id="bbcc2-122">Update the domain for your tenant</span></span>

<span data-ttu-id="bbcc2-123">请确保您已完成在 Microsoft 365 或 Office 365 中更新域的步骤，并且能够添加 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="bbcc2-123">Make sure that you've completed the steps to update your domain in Microsoft 365 or Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="bbcc2-124">有关如何在 Microsoft 365 或 Office 365 中设置域的详细信息，请参阅[将域添加到 microsoft 365 或 office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)。</span><span class="sxs-lookup"><span data-stu-id="bbcc2-124">For more information about how to set up your domain in Microsoft 365 or Office 365, see [Add a domain to Microsoft 365 or Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
  
## <a name="add-dns-records-for-your-edge"></a><span data-ttu-id="bbcc2-125">为你的边缘添加 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="bbcc2-125">Add DNS records for your Edge</span></span>

<span data-ttu-id="bbcc2-126">将以下 DNS 记录添加到 Microsoft 365 或 Office 365 组织。</span><span class="sxs-lookup"><span data-stu-id="bbcc2-126">Add the following DNS records to your Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="bbcc2-127">有关如何添加 DNS 记录的信息，请参阅[在 Microsoft 365 或 Office 365 中添加或编辑自定义 DNS 记录](https://support.office.com/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1)。</span><span class="sxs-lookup"><span data-stu-id="bbcc2-127">For information about how to add DNS records, see [Add or edit custom DNS records in Microsoft 365 or Office 365](https://support.office.com/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).</span></span>
  
1. <span data-ttu-id="bbcc2-128">为 Access Edge 添加 DNS A 记录。</span><span class="sxs-lookup"><span data-stu-id="bbcc2-128">Add a DNS A record for Access Edge.</span></span>
    
2. <span data-ttu-id="bbcc2-129">SRV 记录将自动由 Microsoft 365 或 Office 365 和部署脚本创建。</span><span class="sxs-lookup"><span data-stu-id="bbcc2-129">SRV records will automatically be created by Microsoft 365 or Office 365 and the deployment scripts.</span></span> <span data-ttu-id="bbcc2-130">确认您可以在边缘上查找以下两个 SIP 服务： \_ SIP 和 \_ sipfederationtls。</span><span class="sxs-lookup"><span data-stu-id="bbcc2-130">Confirm that you can look up the following two SIP services on the Edge: \_sip and \_sipfederationtls.</span></span>
    
     ![SRV 记录确认](../../media/3c353a29-6dcc-4ed3-98db-3a6bed3e929e.png)
  
## <a name="set-up-hybrid-connectivity-between-cloud-connector-edition-and-microsoft-365-or-office-365"></a><span data-ttu-id="bbcc2-132">在云连接器版本与 Microsoft 365 或 Office 365 之间设置混合连接</span><span class="sxs-lookup"><span data-stu-id="bbcc2-132">Set up hybrid connectivity between Cloud Connector Edition and Microsoft 365 or Office 365</span></span>

<span data-ttu-id="bbcc2-133">若要在 Skype for business 云连接器版本部署和 Microsoft 365 或 Office 365 组织之间配置混合连接，请在远程 PowerShell 会话中运行以下 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="bbcc2-133">To configure hybrid connectivity between your Skype for Business Cloud Connector Edition deployment and your Microsoft 365 or Office 365 organization, run the following cmdlet in a remote PowerShell session.</span></span> <span data-ttu-id="bbcc2-134">若要了解如何建立远程 PowerShell 会话，请参阅：[设置 Windows PowerShell 的计算机](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="bbcc2-134">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx).</span></span>
  
<span data-ttu-id="bbcc2-135">Cmdlet 设置访问边缘外部 FQDN。</span><span class="sxs-lookup"><span data-stu-id="bbcc2-135">The cmdlet sets the Access Edge external FQDN.</span></span> <span data-ttu-id="bbcc2-136">在第一个命令中， \< 外部访问边缘 FQDN 应为 " \> SIP 访问边缘" 角色中的一个。</span><span class="sxs-lookup"><span data-stu-id="bbcc2-136">In the first of the commands, the \<External Access Edge FQDN\> should be the one for the SIP Access Edge role.</span></span> <span data-ttu-id="bbcc2-137">默认情况下，这应该是 ap。 \<域名称 \> 。</span><span class="sxs-lookup"><span data-stu-id="bbcc2-137">By default, this should be ap.\<Domain Name\>.</span></span>
  
```powershell
Set-CsTenantHybridConfiguration -PeerDestination <External Access Edge FQDN> -UseOnPremDialPlan $false
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
```

> [!NOTE]
> <span data-ttu-id="bbcc2-138">将用于对等目标的外部访问边缘 FQDN 设置为仅当用户未分配到 PSTN 站点时才用作回退的 PSTN 站点。</span><span class="sxs-lookup"><span data-stu-id="bbcc2-138">The External Access Edge FQDN used for Peer Destination should be set to a PSTN site that will only be used as a fallback in case a user isn't assigned to a PSTN site.</span></span> <span data-ttu-id="bbcc2-139">有关详细信息，请参阅[在云连接器中部署单个站点](deploy-a-single-site-in-cloud-connector.md)和[在云连接器中部署多个站点](deploy-multiple-sites-in-cloud-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="bbcc2-139">For more information, see [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) and [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 
  
## <a name="set-up-pstn-gateways"></a><span data-ttu-id="bbcc2-140">设置 PSTN 网关</span><span class="sxs-lookup"><span data-stu-id="bbcc2-140">Set up PSTN gateways</span></span>

<span data-ttu-id="bbcc2-141">将每个 PSTN 网关上的中继设置为指向所有设备的中介服务器。</span><span class="sxs-lookup"><span data-stu-id="bbcc2-141">Set up trunks on each PSTN gateway to point back to Mediation Servers for all appliances.</span></span> <span data-ttu-id="bbcc2-142">每个中继应指向一个中介服务器 FQDN 或 IP 地址，而不是中介服务器池 FQDN，因为池的 FQDN 对于池中的所有服务器都是相同的。</span><span class="sxs-lookup"><span data-stu-id="bbcc2-142">Each trunk should point to one Mediation Server FQDN or IP address instead of the Mediation Server pool FQDN because the pool FQDN is the same for all servers in the pool.</span></span> <span data-ttu-id="bbcc2-143">应按相同的优先级设置中继。</span><span class="sxs-lookup"><span data-stu-id="bbcc2-143">Trunks should be set in the same priority.</span></span>
  
<span data-ttu-id="bbcc2-144">如果要在中介服务器和网关之间使用 TLS，则需要将网关和中介服务器配置为支持 MTLS，如下所示：</span><span class="sxs-lookup"><span data-stu-id="bbcc2-144">If you are using TLS between Mediation Servers and gateways, you will need to configure the gateways and Mediation Servers to support MTLS as follows:</span></span>
  
1. <span data-ttu-id="bbcc2-145">从云连接器 Active Directory 计算机导出根 CA。</span><span class="sxs-lookup"><span data-stu-id="bbcc2-145">Export the Root CA from the Cloud Connector Active Directory computer.</span></span>
    
2. <span data-ttu-id="bbcc2-146">按照 PSTN 网关供应商的说明导入根 CA。</span><span class="sxs-lookup"><span data-stu-id="bbcc2-146">Follow the PSTN gateway vendor instructions for importing the Root CA.</span></span>
    
3. <span data-ttu-id="bbcc2-147">在中介服务器上导入颁发给您的网关的证书的根 CA 证书。</span><span class="sxs-lookup"><span data-stu-id="bbcc2-147">Import the Root CA certificate for the certificate issued to your gateway on the Mediation Servers.</span></span> <span data-ttu-id="bbcc2-148">如果需要为网关获取 SSL 证书，可以使用在云连接器 Active Directory 计算机上运行的证书颁发机构服务执行此操作，如下所示：</span><span class="sxs-lookup"><span data-stu-id="bbcc2-148">If you need to obtain an SSL certificate for the gateway, you may do this using the Certificate Authority service running on the Cloud Connector Active Directory computer as follows:</span></span>
    
   - <span data-ttu-id="bbcc2-149">修改现有 Web 服务器模板，以允许经过身份验证的用户注册，或创建新的 Web 服务器模板以配置其他属性并允许经过身份验证的用户进行注册。</span><span class="sxs-lookup"><span data-stu-id="bbcc2-149">Modify the existing Web Server template to enable Authenticated users to Enroll, or create a new Web Server template to configure other properties and enable Authenticated users to enroll.</span></span> <span data-ttu-id="bbcc2-150">有关详细说明，请参阅[证书模板](https://technet.microsoft.com/library/cc730705.aspx)。</span><span class="sxs-lookup"><span data-stu-id="bbcc2-150">For detailed instructions, see [Certificate Templates](https://technet.microsoft.com/library/cc730705.aspx).</span></span>
    
   - <span data-ttu-id="bbcc2-151">使用 "证书" 管理单元请求证书选择已启用的 Web 服务器模板。</span><span class="sxs-lookup"><span data-stu-id="bbcc2-151">Request a certificate using Certificate snap-in selecting the Web Server template that you have enabled.</span></span> <span data-ttu-id="bbcc2-152">请务必在 "主题" 和 "DNS 名称" 中添加与网关的 FQDN 相同的通用名称，并在 "密钥选项" 下选择 "使密钥可导出的私钥"。</span><span class="sxs-lookup"><span data-stu-id="bbcc2-152">Be sure to add Common name in Subject and DNS name in Alternative name with FQDN of the gateway, and confirm on the Private Key that Make private key exportable is selected under key options.</span></span> 
    
4. <span data-ttu-id="bbcc2-153">使用私钥导出 SSL 证书，并按照来自 PSTN 网关供应商的说明导入证书。</span><span class="sxs-lookup"><span data-stu-id="bbcc2-153">Export the SSL certificate with Private key and follow the instructions from your PSTN gateway vendor for importing the certificate.</span></span>
    
5. <span data-ttu-id="bbcc2-154">一个 PSTN 站点中的 PSTN 网关应只连接到同一站点中的中介服务器。</span><span class="sxs-lookup"><span data-stu-id="bbcc2-154">PSTN gateway(s) in one PSTN site should only connect to the Mediation Server(s) in the same site.</span></span>
    
## <a name="set-up-your-users"></a><span data-ttu-id="bbcc2-155">设置用户</span><span class="sxs-lookup"><span data-stu-id="bbcc2-155">Set up your users</span></span>

<span data-ttu-id="bbcc2-156">登录到 Microsoft 365 管理中心，添加将为联机语音服务启用的用户，并向这些用户分配对 E3 许可证的 E5 许可证或电话系统加载项。</span><span class="sxs-lookup"><span data-stu-id="bbcc2-156">Log in to the Microsoft 365 admin center, add the users that will be enabled for online voice services, and assign an E5 license or Phone System add-on to the E3 license to these users.</span></span> <span data-ttu-id="bbcc2-157">有关添加用户的信息，请参阅[将用户添加到 Microsoft 365 for business](https://support.office.com/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc)。</span><span class="sxs-lookup"><span data-stu-id="bbcc2-157">For information about adding users, see [Add users to Microsoft 365 for business](https://support.office.com/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc).</span></span>
  
## <a name="enable-users-for-phone-system-voice-and-voicemail-services"></a><span data-ttu-id="bbcc2-158">为用户启用电话系统语音和语音邮件服务</span><span class="sxs-lookup"><span data-stu-id="bbcc2-158">Enable users for Phone System voice and voicemail services</span></span>
 
<span data-ttu-id="bbcc2-159">将用户添加到 Microsoft 365 或 Office 365 之后，为其帐户启用电话系统语音服务，包括语音邮件。</span><span class="sxs-lookup"><span data-stu-id="bbcc2-159">After adding your users to Microsoft 365 or Office 365, enable their accounts for Phone System voice services, including voicemail.</span></span> <span data-ttu-id="bbcc2-160">若要启用这些功能，必须使用全局管理员角色的帐户登录到 Microsoft 365 或 Office 365 组织，并且能够运行远程 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="bbcc2-160">To enable these capabilities, you must log in to your Microsoft 365 or Office 365 organization with an account that is a Global Administrator role, and be able to run remote PowerShell.</span></span> <span data-ttu-id="bbcc2-161">若要了解如何建立远程 PowerShell 会话，请参阅：[设置 Windows PowerShell 的计算机](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="bbcc2-161">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx)</span></span>
  
- <span data-ttu-id="bbcc2-162">将策略分配给用户并配置用户的业务语音电话号码（使用**Identity**参数的值指定）：</span><span class="sxs-lookup"><span data-stu-id="bbcc2-162">Assign the policy to your user and configure the user's business voice phone number, which you specify with the value of the **Identity** parameter:</span></span>
    
  ```powershell
  Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI <tel:+phonenumber>
  ```

    > [!NOTE]
    > <span data-ttu-id="bbcc2-163">可以使用用户的 SIP 地址、用户主体名称（UPN）或用户的 Active Directory 显示名称（例如，"Bob 凯利"）来指定用户标识。</span><span class="sxs-lookup"><span data-stu-id="bbcc2-163">A user identity can be specified using the user's SIP address, user principal name (UPN), or the user's Active Directory display name (for example, "Bob Kelly").</span></span> <span data-ttu-id="bbcc2-164">星号（ \* ）字符还可用于显示名称作为用户标识。</span><span class="sxs-lookup"><span data-stu-id="bbcc2-164">The asterisk (\*) character can also be used with the Display Name as the user Identity.</span></span> <span data-ttu-id="bbcc2-165">例如，标识 " \* smith" 将返回显示名称以字符串值 "smith" 结尾的所有用户。</span><span class="sxs-lookup"><span data-stu-id="bbcc2-165">For example, the Identity "\*Smith" returns all the users who have a display name that ends with the string value "Smith".</span></span>
  
<span data-ttu-id="bbcc2-166">然后，您可以使用以下脚本验证是否已添加并启用了用户：</span><span class="sxs-lookup"><span data-stu-id="bbcc2-166">You can then verify that the users were added and enabled using the following script:</span></span>
  
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

<span data-ttu-id="bbcc2-167">您需要决定您的用户是否能够拨打国际电话。</span><span class="sxs-lookup"><span data-stu-id="bbcc2-167">You'll need to decide whether your users should be able to make international calls.</span></span> <span data-ttu-id="bbcc2-168">默认情况下，启用国际呼叫。</span><span class="sxs-lookup"><span data-stu-id="bbcc2-168">By default, international calling is enabled.</span></span> <span data-ttu-id="bbcc2-169">您可以使用联机 Skype for Business 管理中心禁用或启用对用户进行国际拨号的用户。</span><span class="sxs-lookup"><span data-stu-id="bbcc2-169">You can disable or enable users for international dialing using the online Skype for Business admin center.</span></span>
  
<span data-ttu-id="bbcc2-170">若要基于每个用户禁用国际呼叫，请在 Skype for Business Online PowerShell 中运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="bbcc2-170">To disable international calling on a per user basis, run the following cmdlet in Skype for Business Online PowerShell:</span></span>
  
```powershell
Grant-CsVoiceRoutingPolicy -PolicyName InternationalCallsDisallowed -Identity $user
```

<span data-ttu-id="bbcc2-171">若要在禁用国际呼叫后针对每个用户对其进行重新启用，请运行相同的 cmdlet，但将**PolicyName**的值更改为*InternationalCallsAllowed* 。</span><span class="sxs-lookup"><span data-stu-id="bbcc2-171">To re-enable international calling on a per user basis after it has been disabled, run the same cmdlet, but change the value for **PolicyName** to *InternationalCallsAllowed*  .</span></span>
  
## <a name="assign-users-to-pstn-sites"></a><span data-ttu-id="bbcc2-172">将用户分配到 PSTN 站点</span><span class="sxs-lookup"><span data-stu-id="bbcc2-172">Assign users to PSTN sites</span></span>

<span data-ttu-id="bbcc2-173">使用租户远程 PowerShell 将网站分配给用户，即使仅部署了单个网站也是如此。</span><span class="sxs-lookup"><span data-stu-id="bbcc2-173">Use tenant remote PowerShell to assign a site to users even if you only deployed a single site.</span></span> <span data-ttu-id="bbcc2-174">若要了解如何建立远程 PowerShell 会话，请参阅：[设置 Windows PowerShell 的计算机](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="bbcc2-174">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx).</span></span>
  
```powershell
# Set the site to users
Set-CsUserPstnSettings -Identity <User Name> -HybridPstnSite <PSTN Site Name>

# Review the site setting for a user
Get-CsUserPstnSettings -Identity <User Name> 

# See all the user settings in one tenant
Get-CsOnlineUser | Get-CsUserPstnSettings
```

> [!NOTE]
> <span data-ttu-id="bbcc2-175">如果没有任何 PSTN 站点分配给用户，则您的 Skype for Business 云连接器版本部署和 Microsoft 365 或 Office 365 组织之间的混合连接将回退为使用租户级别默认值（对等目标），以便可以完成呼叫。</span><span class="sxs-lookup"><span data-stu-id="bbcc2-175">If no PSTN site is assigned to a user, hybrid connectivity between your Skype for Business Cloud Connector Edition deployment and your Microsoft 365 or Office 365 organization will fall back to use the tenant level default one (Peer Destination) so that calls can be completed.</span></span> 
  
## <a name="configure-online-hybrid-mediation-server-settings"></a><span data-ttu-id="bbcc2-176">配置联机混合中介服务器设置</span><span class="sxs-lookup"><span data-stu-id="bbcc2-176">Configure online hybrid Mediation Server Settings</span></span>
<span data-ttu-id="bbcc2-177"><a name="BKMK_ConfigureMediationServer"> </a></span><span class="sxs-lookup"><span data-stu-id="bbcc2-177"><a name="BKMK_ConfigureMediationServer"> </a></span></span>

<span data-ttu-id="bbcc2-178">在将 P2P 呼叫升级到 PSTN 会议时，Skype for Business Online 会议服务器将向云连接器中介服务器发送邀请。</span><span class="sxs-lookup"><span data-stu-id="bbcc2-178">When a P2P call is escalated to a PSTN conference, the Skype for Business Online conferencing server will send an invite to the Cloud Connector Mediation Server.</span></span> <span data-ttu-id="bbcc2-179">若要确保 Microsoft 365 或 Office 365 能够成功路由此邀请，您需要为每个云连接器中介服务器在联机租户中配置一个设置，如下所示：</span><span class="sxs-lookup"><span data-stu-id="bbcc2-179">To ensure that Microsoft 365 or Office 365 can route this invite successfully, you need to configure a setting in your online tenant for each Cloud Connector Mediation Server as follows:</span></span> 
  
1. <span data-ttu-id="bbcc2-180">在 Microsoft 365 管理中心中创建一个用户。</span><span class="sxs-lookup"><span data-stu-id="bbcc2-180">Create a user in the Microsoft 365 admin center.</span></span> <span data-ttu-id="bbcc2-181">使用所需的任何用户名，如 "MediationServer1"。</span><span class="sxs-lookup"><span data-stu-id="bbcc2-181">Use any user name you want, such as "MediationServer1."</span></span>
    
    <span data-ttu-id="bbcc2-182">将云连接器（.ini 文件中的第一个 SIP 域）的默认 SIP 域用作用户域。</span><span class="sxs-lookup"><span data-stu-id="bbcc2-182">Use the default SIP domain of Cloud Connector (the first SIP domain in the .ini file) as the user domain.</span></span>
    
    <span data-ttu-id="bbcc2-183">请注意，仅当用户传播到 Skype for Business online 目录中时，才需要许可证分配。</span><span class="sxs-lookup"><span data-stu-id="bbcc2-183">Please note that license assignment is only required for the user propagation into the Skype for Business online directory.</span></span> <span data-ttu-id="bbcc2-184">向您创建的帐户分配 Microsoft 365 或 Office 365 许可证（如 E5），最多允许一个小时来传播所做的更改，并通过运行以下 cmdlet 验证是否已将用户帐户正确设置到 Skype for business online 目录中，然后从此帐户中删除许可证。</span><span class="sxs-lookup"><span data-stu-id="bbcc2-184">Assign a Microsoft 365 or Office 365 license (such as E5) to the account you create, allow up to one hour for the changes to propagate,verify the user accounts has been provisioned correctly to the Skype for Business online directory by running following cmdlet, then remove the license from this account.</span></span>
    ```powershell
   Get-CsOnlineUser -Identity <UserPrincipalName>
   ```
    
2. <span data-ttu-id="bbcc2-185">使用全局或用户管理员凭据启动租户 Azure AD 远程 PowerShell 会话，然后运行以下 cmdlet，以将步骤1中配置的 Azure AD 用户帐户的部门设置为 "HybridMediationServer"：</span><span class="sxs-lookup"><span data-stu-id="bbcc2-185">Start a tenant Azure AD remote PowerShell session using your global or user admin credentials, and then run the following cmdlet to set the department for the Azure AD user account configured in step 1 to "HybridMediationServer":</span></span>

   ```powershell
   Set-MsolUser -UserPrincipalName <UserPrincipalName> -Department "HybridMediationServer"
   ```

3. <span data-ttu-id="bbcc2-186">使用您的 Skype for Business 租户管理员凭据启动租户 Skype for Business 远程 PowerShell 会话，然后运行以下 cmdlet，以将中介服务器和边缘服务器 FQDN 设置为该用户帐户，将 DisplayName 替换为 \< \> 您在步骤1中创建的帐户的显示名称：</span><span class="sxs-lookup"><span data-stu-id="bbcc2-186">Start a tenant Skype for Business remote PowerShell session using your Skype for Business tenant admin credentials, and then run the following cmdlet to set the Mediation Server and Edge Server FQDN to that user account, replacing \<DisplayName\> with the Display Name of the user for the account you created in step 1:</span></span>
    
   ```powershell
   Set-CsHybridMediationServer -Identity <DisplayName> -Fqdn <MediationServerFQDN> -AccessProxyExternalFqdn <EdgeServerExternalFQDN>
   ```

    <span data-ttu-id="bbcc2-187">对于 "标识"，请使用为此中介服务器创建的用户帐户的显示名称。</span><span class="sxs-lookup"><span data-stu-id="bbcc2-187">For Identity, use the Display Name of the user account you created for this Mediation Server.</span></span>
    
    <span data-ttu-id="bbcc2-188">对于*MediationServerFQDN* ，使用为中介服务器定义的内部 FQDN。</span><span class="sxs-lookup"><span data-stu-id="bbcc2-188">For  *MediationServerFQDN*  , use the internal FQDN defined for your Mediation Server.</span></span>
    
    <span data-ttu-id="bbcc2-189">对于*EdgeServerExternalFQDN* ，使用为边缘服务器访问代理定义的外部 FQDN。</span><span class="sxs-lookup"><span data-stu-id="bbcc2-189">For  *EdgeServerExternalFQDN*  , use the external FQDN defined for Edge Server Access Proxy.</span></span> <span data-ttu-id="bbcc2-190">如果有多个云连接器 PSTN 站点，请选择分配给中介服务器所在的站点的边缘服务器访问代理 FQDN。</span><span class="sxs-lookup"><span data-stu-id="bbcc2-190">If there are multiple Cloud Connector PSTN sites, choose the Edge Server Access Proxy FQDN assigned to the site where the Mediation Server is located.</span></span>
    
4. <span data-ttu-id="bbcc2-191">如果有多个云连接器中介服务器（多站点，HA），请对每个服务器重复前面的步骤。</span><span class="sxs-lookup"><span data-stu-id="bbcc2-191">If there are multiple Cloud Connector Mediation Servers (multiple-site, HA), please repeat the previous steps for each of them.</span></span>
    
