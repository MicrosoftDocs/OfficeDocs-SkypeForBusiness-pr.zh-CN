---
title: 管理 Skype for Business Server 2015 中的双重身份验证
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 16f08710-8961-4659-acbf-ebb95a198fb4
description: 摘要： 管理在 Skype 的业务服务器 2015年的双因素身份验证。
ms.openlocfilehash: 5933afc311514e841d7fb96f41988d8f495d0bee
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="manage-two-factor-authentication-in-skype-for-business-server-2015"></a><span data-ttu-id="89e07-103">管理 Skype for Business Server 2015 中的双重身份验证</span><span class="sxs-lookup"><span data-stu-id="89e07-103">Manage two-factor authentication in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="89e07-104">**摘要：**管理在 Skype 的业务服务器 2015年的双因素身份验证。</span><span class="sxs-lookup"><span data-stu-id="89e07-104">**Summary:** Manage two-factor authentication in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="89e07-105">双重身份验证要求用户提供两种形式的身份验证或身份识别，即用户名/密码组合以及令牌或证书，从而提供了更高的安全性。</span><span class="sxs-lookup"><span data-stu-id="89e07-105">Two-factor authentication provides improved security by requiring users to provide two forms of authentication or identification, namely a user name/password combination and a token or certificate.</span></span> <span data-ttu-id="89e07-106">这正是所谓"，您知道的某种信息。"</span><span class="sxs-lookup"><span data-stu-id="89e07-106">This is also known as "something you have, something you know."</span></span> 
  
<span data-ttu-id="89e07-p102">使用证书进行双重身份验证的一个典型示例是使用智能卡。智能卡包含与用户帐户相关联的证书，可对照服务器上存储的用户和证书信息进行验证。通过将用户信息（用户名和密码）与提供的证书进行比较，服务器将验证凭据并验证用户身份。</span><span class="sxs-lookup"><span data-stu-id="89e07-p102">A typical example of two-factor authentication with a certificate is the use of smart cards. A smart card contains a certificate associated with the user account, and can be validated against user and certificate information stored on a server. By comparing the user information (user name and password) to the certificate provided, the server validates the credentials and authenticates the user.</span></span>
  
<span data-ttu-id="89e07-110">配置业务服务器 2015年环境 Skype 来支持两因素身份验证时，应考虑以下主题。</span><span class="sxs-lookup"><span data-stu-id="89e07-110">Consider the following subjects when configuring a Skype for Business Server 2015 environment to support two-factor authentication.</span></span>
  
## <a name="client-support"></a><span data-ttu-id="89e07-111">客户端支持</span><span class="sxs-lookup"><span data-stu-id="89e07-111">Client Support</span></span>

<span data-ttu-id="89e07-112">Lync Server 2013 累积更新： 2013 年 7 月的桌面客户端和 Skype 业务客户机是目前支持两因素身份验证的唯一客户端。</span><span class="sxs-lookup"><span data-stu-id="89e07-112">The Cumulative Updates for Lync Server 2013: July 2013 desktop client and the Skype for Business client are the only clients that currently support two-factor authentication.</span></span>
  
## <a name="topology-requirements"></a><span data-ttu-id="89e07-113">拓扑要求</span><span class="sxs-lookup"><span data-stu-id="89e07-113">Topology Requirements</span></span>

<span data-ttu-id="89e07-114">强烈建议使用专用的 Skype 业务服务器 2015年的边缘、 部门主任和用户池的双因子验证部署的客户。</span><span class="sxs-lookup"><span data-stu-id="89e07-114">Customers are strongly encouraged to deploy two-factor authentication using dedicated Skype for Business Server 2015 with Edge, Director, and User Pools.</span></span> <span data-ttu-id="89e07-115">要为用户启用被动身份验证，必须为其他角色和服务禁用其他身份验证方法，包括以下各项：</span><span class="sxs-lookup"><span data-stu-id="89e07-115">To enable passive authentication for users, other authentication methods must be disabled for other roles and services, including the following:</span></span>
  
|<span data-ttu-id="89e07-116">**配置类型**</span><span class="sxs-lookup"><span data-stu-id="89e07-116">**Configuration Type**</span></span>|<span data-ttu-id="89e07-117">**服务类型**</span><span class="sxs-lookup"><span data-stu-id="89e07-117">**Service Type**</span></span>|<span data-ttu-id="89e07-118">**服务器角色**</span><span class="sxs-lookup"><span data-stu-id="89e07-118">**Server Role**</span></span>|<span data-ttu-id="89e07-119">**身份验证类型设置为禁用**</span><span class="sxs-lookup"><span data-stu-id="89e07-119">**Authentication Type to Disable**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="89e07-120">Web 服务</span><span class="sxs-lookup"><span data-stu-id="89e07-120">Web Service</span></span>  <br/> |<span data-ttu-id="89e07-121">Web 服务器</span><span class="sxs-lookup"><span data-stu-id="89e07-121">WebServer</span></span>  <br/> |<span data-ttu-id="89e07-122">控制器</span><span class="sxs-lookup"><span data-stu-id="89e07-122">Director</span></span>  <br/> |<span data-ttu-id="89e07-123">Kerberos、NTLM 和证书</span><span class="sxs-lookup"><span data-stu-id="89e07-123">Kerberos, NTLM, and Certificate</span></span>  <br/> |
|<span data-ttu-id="89e07-124">Web 服务</span><span class="sxs-lookup"><span data-stu-id="89e07-124">Web Service</span></span>  <br/> |<span data-ttu-id="89e07-125">Web 服务器</span><span class="sxs-lookup"><span data-stu-id="89e07-125">WebServer</span></span>  <br/> |<span data-ttu-id="89e07-126">前端</span><span class="sxs-lookup"><span data-stu-id="89e07-126">Front End</span></span>  <br/> |<span data-ttu-id="89e07-127">Kerberos、NTLM 和证书</span><span class="sxs-lookup"><span data-stu-id="89e07-127">Kerberos, NTLM, and Certificate</span></span>  <br/> |
|<span data-ttu-id="89e07-128">代理</span><span class="sxs-lookup"><span data-stu-id="89e07-128">Proxy</span></span>  <br/> |<span data-ttu-id="89e07-129">EdgeServer</span><span class="sxs-lookup"><span data-stu-id="89e07-129">EdgeServer</span></span>  <br/> |<span data-ttu-id="89e07-130">Edge</span><span class="sxs-lookup"><span data-stu-id="89e07-130">Edge</span></span>  <br/> |<span data-ttu-id="89e07-131">Kerberos 和 NTLM</span><span class="sxs-lookup"><span data-stu-id="89e07-131">Kerberos and NTLM</span></span>  <br/> |
|<span data-ttu-id="89e07-132">代理</span><span class="sxs-lookup"><span data-stu-id="89e07-132">Proxy</span></span>  <br/> |<span data-ttu-id="89e07-133">注册器</span><span class="sxs-lookup"><span data-stu-id="89e07-133">Registrar</span></span>  <br/> |<span data-ttu-id="89e07-134">前端</span><span class="sxs-lookup"><span data-stu-id="89e07-134">Front End</span></span>  <br/> |<span data-ttu-id="89e07-135">Kerberos 和 NTLM</span><span class="sxs-lookup"><span data-stu-id="89e07-135">Kerberos and NTLM</span></span>  <br/> |
   
<span data-ttu-id="89e07-136">除非在服务级别禁用这些身份验证类型，否则一旦在您的部署中启用双重身份验证，所有其他版本的客户端将无法成功登录。</span><span class="sxs-lookup"><span data-stu-id="89e07-136">Unless these authentication types are disabled at the service level, all other versions of the client will be unable to sign in successfully once two-factor authentication is enabled within in your deployment.</span></span>
  
## <a name="skype-for-business-service-discovery"></a><span data-ttu-id="89e07-137">Skype for Business 服务发现</span><span class="sxs-lookup"><span data-stu-id="89e07-137">Skype for Business Service Discovery</span></span>

<span data-ttu-id="89e07-138">应该配置 DNS 记录内部和/或外部客户端用来发现 Skype 业务服务解析为 Skype 业务服务器未启用双因素身份验证。</span><span class="sxs-lookup"><span data-stu-id="89e07-138">DNS records used by internal and/or external clients to discover Skype for Business services should be configured to resolve to a Skype for Business server that is not enabled for two-factor authentication.</span></span> <span data-ttu-id="89e07-139">使用此配置，Skype 业务池未启用双因素身份验证的用户不需要输入 pin 码以进行身份验证，而 Skype 业务池启用的双因素身份验证的用户将成为要求输入他们的 PIN 进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="89e07-139">With this configuration, users from Skype for Business Pools that are not enabled for two-factor authentication will not be required to enter a PIN to authenticate, while users from Skype for Business Pools that are enabled for two-factor authentication will be required to enter their PIN to authenticate.</span></span>
  
## <a name="exchange-authentication"></a><span data-ttu-id="89e07-140">Exchange 身份验证</span><span class="sxs-lookup"><span data-stu-id="89e07-140">Exchange Authentication</span></span>

<span data-ttu-id="89e07-141">已部署 Microsoft Exchange 的双因素身份验证的用户可能会发现客户端中的某些功能将不可用。</span><span class="sxs-lookup"><span data-stu-id="89e07-141">Customers who have deployed two-factor authentication for Microsoft Exchange may find that certain features in the client are unavailable.</span></span> <span data-ttu-id="89e07-142">这是当前设计中，通过 Skype 业务客户端不支持双因素身份验证依赖于交换集成的功能。</span><span class="sxs-lookup"><span data-stu-id="89e07-142">This is currently by design, as the Skype for Business client does not support two-factor authentication for features that are dependent on Exchange integration.</span></span>
  
## <a name="contacts"></a><span data-ttu-id="89e07-143">联系人</span><span class="sxs-lookup"><span data-stu-id="89e07-143">Contacts</span></span>

<span data-ttu-id="89e07-144">配置以利用统一联系人存储功能的业务用户的 Skype 会发现其联系人不再可用后登录两因素身份验证。</span><span class="sxs-lookup"><span data-stu-id="89e07-144">Skype for Business users who are configured to leverage the Unified Contact Store feature will find that their contacts are no longer available after signing in with two-factor authentication.</span></span>
  
<span data-ttu-id="89e07-145">您应该使用**调用 CsUcsRollback** cmdlet 从统一联系人存储库中删除现有用户的联系人并将其存储在 Skype 的业务服务器 2015年启用双因素身份验证之前。</span><span class="sxs-lookup"><span data-stu-id="89e07-145">You should use the **Invoke-CsUcsRollback** cmdlet to remove existing user contacts from the Unified Contact Store and store them in Skype for Business Server 2015 before enabling two-factor authentication.</span></span>
  
## <a name="skill-search"></a><span data-ttu-id="89e07-146">技能搜索</span><span class="sxs-lookup"><span data-stu-id="89e07-146">Skill Search</span></span>

<span data-ttu-id="89e07-147">客户在其 Skype 的业务环境中配置了技能搜索功能将 Skype 业务两因素身份验证为启用时，此功能不能发现。</span><span class="sxs-lookup"><span data-stu-id="89e07-147">Customers who have configured the Skill Search feature in their Skype for Business environment will find that this feature does not work when Skype for Business is enabled for two-factor authentication.</span></span> <span data-ttu-id="89e07-148">这是设计使然，因为 Microsoft SharePoint 当前不支持双重身份验证。</span><span class="sxs-lookup"><span data-stu-id="89e07-148">This is by design, as Microsoft SharePoint does not currently support two-factor authentication.</span></span>
  
## <a name="credentials"></a><span data-ttu-id="89e07-149">凭据</span><span class="sxs-lookup"><span data-stu-id="89e07-149">Credentials</span></span>

<span data-ttu-id="89e07-150">有大量涉及业务可能影响配置为使用双因素身份验证的用户的凭据保存的 Skype 的部署注意事项。</span><span class="sxs-lookup"><span data-stu-id="89e07-150">There are a number of deployment considerations involving saved Skype for Business credentials which may impact users who are configured to use two-factor authentication.</span></span>
  
### <a name="deleting-saved-credentials"></a><span data-ttu-id="89e07-151">删除保存的凭据</span><span class="sxs-lookup"><span data-stu-id="89e07-151">Deleting Saved Credentials</span></span>

<span data-ttu-id="89e07-152">用户应该用于企业客户端**删除我的登录信息**选项在 Skype 和删除其 SIP 配置文件文件夹从 %localappdata%\Microsoft\Office\15.0\Skype 业务为使用双因素在第一次登录前身份验证。</span><span class="sxs-lookup"><span data-stu-id="89e07-152">Users should use the **Delete my sign-in info** option in the Skype for Business client and delete their SIP profile folder from %localappdata%\Microsoft\Office\15.0\Skype for Business before attempting to sign for the first time using two-factor authentication.</span></span>
  
### <a name="disablentcredentials"></a><span data-ttu-id="89e07-153">DisableNTCredentials</span><span class="sxs-lookup"><span data-stu-id="89e07-153">DisableNTCredentials</span></span>

<span data-ttu-id="89e07-154">使用 Kerberos 或 NTLM 身份验证方法，身份验证可以自动使用用户的 Windows 凭据。</span><span class="sxs-lookup"><span data-stu-id="89e07-154">With the Kerberos or NTLM authentication method, the user's Windows credentials are used automatically for authentication.</span></span> <span data-ttu-id="89e07-155">在启用了 Kerberos 和/或 NTLM 是用于身份验证的业务服务器 2015年部署典型 Skype，用户应该不需要输入其凭据登录每次。</span><span class="sxs-lookup"><span data-stu-id="89e07-155">In a typical Skype for Business Server 2015 deployment where Kerberos and/or NTLM is enabled for authentication, users should not have to enter their credentials every time that they sign in.</span></span>
  
<span data-ttu-id="89e07-156">如果在提示用户输入其 PIN 之前无意中提示用户输入凭据，则可能通过组策略在客户端计算机上无意中配置了 **DisableNTCredentials** 注册表项。</span><span class="sxs-lookup"><span data-stu-id="89e07-156">If users are unintentionally prompted for credentials before they are prompted to enter their PIN, the **DisableNTCredentials** registry key may be unintentionally configured on client computers, possibly through Group Policy.</span></span>
  
<span data-ttu-id="89e07-157">若要防止其他提示输入凭据，在本地工作站上创建下面的注册表项或使用 Skype 业务管理模板将应用于所有用户的使用组策略指定的池：</span><span class="sxs-lookup"><span data-stu-id="89e07-157">To prevent the additional prompt for credentials, create the following registry entry on the local workstation or use the Skype for Business administrative template to apply to all users for a given pool using Group Policy:</span></span>
  
    HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Office\15.0\Lync
  
    REG_DWORD: DisableNTCredentials
  
    Value: 0x0
  
### <a name="savepassword"></a><span data-ttu-id="89e07-158">SavePassword</span><span class="sxs-lookup"><span data-stu-id="89e07-158">SavePassword</span></span>

<span data-ttu-id="89e07-159">当用户登录 Skype 业务的第一次时，提示用户要保存他或她的密码。</span><span class="sxs-lookup"><span data-stu-id="89e07-159">When a user signs in to Skype for Business for the first time, the user is prompted to save his or her password.</span></span> <span data-ttu-id="89e07-160">如果选中此项，此选项将允许用户的 Windows 凭据存储在凭据管理器中的本地计算机的个人证书存储区中存储的用户的客户端证书。</span><span class="sxs-lookup"><span data-stu-id="89e07-160">If selected, this option allows the user's client certificate to be stored in the personal certificate store and the user's Windows credentials to be stored in the Credential Manager of the local computer.</span></span>
  
<span data-ttu-id="89e07-161">在 Skype 业务配置为支持双因素身份验证时，应禁用**SavePassword**注册表设置。</span><span class="sxs-lookup"><span data-stu-id="89e07-161">The **SavePassword** registry setting should be disabled when Skype for Business is configured to support two-factor authentication.</span></span> <span data-ttu-id="89e07-162">若要禁止用户保存他们的密码，更改下面的注册表项在本地工作站上或使用 Skype 业务管理模板将应用于所有用户的使用组策略指定的池：</span><span class="sxs-lookup"><span data-stu-id="89e07-162">To prevent users from saving their passwords, change the following registry entry on the local workstation or use the Skype for Business administrative template to apply to all users for a given pool using Group Policy:</span></span>
  
    HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync
  
    REG_DWORD: SavePassword
  
    Value: 0x0
  
## <a name="ad-fs-20-token-replay"></a><span data-ttu-id="89e07-163">AD FS 2.0 令牌重播</span><span class="sxs-lookup"><span data-stu-id="89e07-163">AD FS 2.0 Token Replay</span></span>

<span data-ttu-id="89e07-p110">AD FS 2.0 提供了一项功能称为“令牌重播检测”，借助该功能，可以检测并丢弃多个使用相同令牌的令牌请求。启用此功能时，令牌重播检测可确保从不多次使用相同令牌，从而保护 WS 联合被动配置文件和 SAML WebSSO 配置文件中身份验证请求的完整性。</span><span class="sxs-lookup"><span data-stu-id="89e07-p110">AD FS 2.0 provides a feature referred to as token replay detection, by which multiple token requests using the same token can be detected and then discarded. When this feature is enabled, token replay detection protects the integrity of authentication requests in both the WS-Federation passive profile and the SAML WebSSO profile by making sure that the same token is never used more than once.</span></span>
  
<span data-ttu-id="89e07-166">在高度关注安全的环境（例如使用展台时）中，应启用此功能。</span><span class="sxs-lookup"><span data-stu-id="89e07-166">This feature should be enabled in situations where security is a very high concern such as when using kiosks.</span></span> <span data-ttu-id="89e07-167">有关标记重做检测的详细信息，请参阅[安全规划和 AD FS 2.0 部署的最佳做法](https://go.microsoft.com/fwlink/p/?LinkId=309215)。</span><span class="sxs-lookup"><span data-stu-id="89e07-167">For more information about token replay detection, see [Best Practices for Secure Planning and Deployment of AD FS 2.0](https://go.microsoft.com/fwlink/p/?LinkId=309215).</span></span>
  
## <a name="external-user-access"></a><span data-ttu-id="89e07-168">外部用户访问</span><span class="sxs-lookup"><span data-stu-id="89e07-168">External User Access</span></span>

<span data-ttu-id="89e07-169">这些主题不介绍配置为从外部网络业务双因素身份验证支持 Skype ADFS 代理或反向代理服务器。</span><span class="sxs-lookup"><span data-stu-id="89e07-169">Configuring an ADFS Proxy or Reverse Proxy to support Skype for Business two-factor authentication from external networks is not covered in these topics.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="89e07-170">另请参阅</span><span class="sxs-lookup"><span data-stu-id="89e07-170">See also</span></span>

#### 

[<span data-ttu-id="89e07-171">在 Skype 为业务服务器 2015年配置两因素身份验证</span><span class="sxs-lookup"><span data-stu-id="89e07-171">Configure two-factor authentication in Skype for Business Server 2015</span></span>](configure.md)
  
[<span data-ttu-id="89e07-172">在 Skype 为业务服务器 2015年配置两因素身份验证</span><span class="sxs-lookup"><span data-stu-id="89e07-172">Configure two-factor authentication in Skype for Business Server 2015</span></span>](configure.md)

