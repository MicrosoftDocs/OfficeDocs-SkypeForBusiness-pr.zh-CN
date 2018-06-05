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
description: 摘要： 管理 Skype 中的业务服务器 2015年的双重身份验证。
ms.openlocfilehash: c72e998b7e12993f328aa4e331c67d5b660e94aa
ms.sourcegitcommit: a5b8b0a1e5ae5eb718e296ca6df6687368ee9174
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2018
ms.locfileid: "19504514"
---
# <a name="manage-two-factor-authentication-in-skype-for-business-server-2015"></a><span data-ttu-id="41a49-103">管理 Skype for Business Server 2015 中的双重身份验证</span><span class="sxs-lookup"><span data-stu-id="41a49-103">Manage two-factor authentication in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="41a49-104">**摘要：** 管理 Skype 中的业务服务器 2015年的双重身份验证。</span><span class="sxs-lookup"><span data-stu-id="41a49-104">**Summary:** Manage two-factor authentication in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="41a49-105">双重身份验证要求用户提供两种形式的身份验证或身份识别，即用户名/密码组合以及令牌或证书，从而提供了更高的安全性。</span><span class="sxs-lookup"><span data-stu-id="41a49-105">Two-factor authentication provides improved security by requiring users to provide two forms of authentication or identification, namely a user name/password combination and a token or certificate.</span></span> <span data-ttu-id="41a49-106">这是也称为"的内容，您知道。"</span><span class="sxs-lookup"><span data-stu-id="41a49-106">This is also known as "something you have, something you know."</span></span> 
  
<span data-ttu-id="41a49-p102">使用证书进行双重身份验证的一个典型示例是使用智能卡。智能卡包含与用户帐户相关联的证书，可对照服务器上存储的用户和证书信息进行验证。通过将用户信息（用户名和密码）与提供的证书进行比较，服务器将验证凭据并验证用户身份。</span><span class="sxs-lookup"><span data-stu-id="41a49-p102">A typical example of two-factor authentication with a certificate is the use of smart cards. A smart card contains a certificate associated with the user account, and can be validated against user and certificate information stored on a server. By comparing the user information (user name and password) to the certificate provided, the server validates the credentials and authenticates the user.</span></span>
  
<span data-ttu-id="41a49-110">配置业务服务器 2015年环境 Skype 以支持双重身份验证时，请考虑以下主题。</span><span class="sxs-lookup"><span data-stu-id="41a49-110">Consider the following subjects when configuring a Skype for Business Server 2015 environment to support two-factor authentication.</span></span>
  
## <a name="client-support"></a><span data-ttu-id="41a49-111">客户端支持</span><span class="sxs-lookup"><span data-stu-id="41a49-111">Client Support</span></span>

<span data-ttu-id="41a49-112">Lync Server 2013 累积更新： 2013 年 7 月桌面客户端和业务客户端 Skype 是当前支持双重身份验证的唯一客户端。</span><span class="sxs-lookup"><span data-stu-id="41a49-112">The Cumulative Updates for Lync Server 2013: July 2013 desktop client and the Skype for Business client are the only clients that currently support two-factor authentication.</span></span>
  
## <a name="topology-requirements"></a><span data-ttu-id="41a49-113">拓扑要求</span><span class="sxs-lookup"><span data-stu-id="41a49-113">Topology Requirements</span></span>

<span data-ttu-id="41a49-114">强烈建议，部署使用专用的 Skype 的业务服务器 2015年边缘、 控制器和用户池的双重身份验证的客户。</span><span class="sxs-lookup"><span data-stu-id="41a49-114">Customers are strongly encouraged to deploy two-factor authentication using dedicated Skype for Business Server 2015 with Edge, Director, and User Pools.</span></span> <span data-ttu-id="41a49-115">要为用户启用被动身份验证，必须为其他角色和服务禁用其他身份验证方法，包括以下各项：</span><span class="sxs-lookup"><span data-stu-id="41a49-115">To enable passive authentication for users, other authentication methods must be disabled for other roles and services, including the following:</span></span>
  
|<span data-ttu-id="41a49-116">**配置类型**</span><span class="sxs-lookup"><span data-stu-id="41a49-116">**Configuration Type**</span></span>|<span data-ttu-id="41a49-117">**服务类型**</span><span class="sxs-lookup"><span data-stu-id="41a49-117">**Service Type**</span></span>|<span data-ttu-id="41a49-118">**服务器角色**</span><span class="sxs-lookup"><span data-stu-id="41a49-118">**Server Role**</span></span>|<span data-ttu-id="41a49-119">**禁用身份验证类型**</span><span class="sxs-lookup"><span data-stu-id="41a49-119">**Authentication Type to Disable**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="41a49-120">Web 服务</span><span class="sxs-lookup"><span data-stu-id="41a49-120">Web Service</span></span>  <br/> |<span data-ttu-id="41a49-121">Web 服务器</span><span class="sxs-lookup"><span data-stu-id="41a49-121">WebServer</span></span>  <br/> |<span data-ttu-id="41a49-122">控制器</span><span class="sxs-lookup"><span data-stu-id="41a49-122">Director</span></span>  <br/> |<span data-ttu-id="41a49-123">Kerberos、NTLM 和证书</span><span class="sxs-lookup"><span data-stu-id="41a49-123">Kerberos, NTLM, and Certificate</span></span>  <br/> |
|<span data-ttu-id="41a49-124">Web 服务</span><span class="sxs-lookup"><span data-stu-id="41a49-124">Web Service</span></span>  <br/> |<span data-ttu-id="41a49-125">Web 服务器</span><span class="sxs-lookup"><span data-stu-id="41a49-125">WebServer</span></span>  <br/> |<span data-ttu-id="41a49-126">前端</span><span class="sxs-lookup"><span data-stu-id="41a49-126">Front End</span></span>  <br/> |<span data-ttu-id="41a49-127">Kerberos、NTLM 和证书</span><span class="sxs-lookup"><span data-stu-id="41a49-127">Kerberos, NTLM, and Certificate</span></span>  <br/> |
|<span data-ttu-id="41a49-128">代理</span><span class="sxs-lookup"><span data-stu-id="41a49-128">Proxy</span></span>  <br/> |<span data-ttu-id="41a49-129">EdgeServer</span><span class="sxs-lookup"><span data-stu-id="41a49-129">EdgeServer</span></span>  <br/> |<span data-ttu-id="41a49-130">Edge</span><span class="sxs-lookup"><span data-stu-id="41a49-130">Edge</span></span>  <br/> |<span data-ttu-id="41a49-131">Kerberos 和 NTLM</span><span class="sxs-lookup"><span data-stu-id="41a49-131">Kerberos and NTLM</span></span>  <br/> |
|<span data-ttu-id="41a49-132">代理</span><span class="sxs-lookup"><span data-stu-id="41a49-132">Proxy</span></span>  <br/> |<span data-ttu-id="41a49-133">注册器</span><span class="sxs-lookup"><span data-stu-id="41a49-133">Registrar</span></span>  <br/> |<span data-ttu-id="41a49-134">前端</span><span class="sxs-lookup"><span data-stu-id="41a49-134">Front End</span></span>  <br/> |<span data-ttu-id="41a49-135">Kerberos 和 NTLM</span><span class="sxs-lookup"><span data-stu-id="41a49-135">Kerberos and NTLM</span></span>  <br/> |
   
<span data-ttu-id="41a49-136">除非在服务级别禁用这些身份验证类型，否则一旦在您的部署中启用双重身份验证，所有其他版本的客户端将无法成功登录。</span><span class="sxs-lookup"><span data-stu-id="41a49-136">Unless these authentication types are disabled at the service level, all other versions of the client will be unable to sign in successfully once two-factor authentication is enabled within in your deployment.</span></span>
  
## <a name="skype-for-business-service-discovery"></a><span data-ttu-id="41a49-137">Skype for Business 服务发现</span><span class="sxs-lookup"><span data-stu-id="41a49-137">Skype for Business Service Discovery</span></span>

<span data-ttu-id="41a49-138">应配置内部和/或外部的客户端用于发现 Skype 业务服务的 DNS 记录，解析为未启用的双重身份验证的企业服务器 Skype。</span><span class="sxs-lookup"><span data-stu-id="41a49-138">DNS records used by internal and/or external clients to discover Skype for Business services should be configured to resolve to a Skype for Business server that is not enabled for two-factor authentication.</span></span> <span data-ttu-id="41a49-139">使用此配置，Skype 未启用双重身份验证的业务池的用户将不需要输入 PIN 进行身份验证，将为用户启用了双重身份验证的业务池的 Skype 时要求输入 PIN，以便进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="41a49-139">With this configuration, users from Skype for Business Pools that are not enabled for two-factor authentication will not be required to enter a PIN to authenticate, while users from Skype for Business Pools that are enabled for two-factor authentication will be required to enter their PIN to authenticate.</span></span>
  
## <a name="exchange-authentication"></a><span data-ttu-id="41a49-140">Exchange 身份验证</span><span class="sxs-lookup"><span data-stu-id="41a49-140">Exchange Authentication</span></span>

<span data-ttu-id="41a49-141">客户部署了 Microsoft Exchange 的双重身份验证可能会发现在客户端中的某些功能将不可用。</span><span class="sxs-lookup"><span data-stu-id="41a49-141">Customers who have deployed two-factor authentication for Microsoft Exchange may find that certain features in the client are unavailable.</span></span> <span data-ttu-id="41a49-142">这是当前按照设计，如业务客户端 Skype 取决于 Exchange 集成的功能不支持双重身份验证。</span><span class="sxs-lookup"><span data-stu-id="41a49-142">This is currently by design, as the Skype for Business client does not support two-factor authentication for features that are dependent on Exchange integration.</span></span>
  
## <a name="contacts"></a><span data-ttu-id="41a49-143">联系人</span><span class="sxs-lookup"><span data-stu-id="41a49-143">Contacts</span></span>

<span data-ttu-id="41a49-144">Skype 的业务用户的配置，以便利用统一联系人存储功能会发现的联系人不再可用后登录时双重身份验证。</span><span class="sxs-lookup"><span data-stu-id="41a49-144">Skype for Business users who are configured to leverage the Unified Contact Store feature will find that their contacts are no longer available after signing in with two-factor authentication.</span></span>
  
<span data-ttu-id="41a49-145">应使用**Invoke-csucsrollback** cmdlet 从统一联系人存储库中删除现有的用户联系人并将其存储在 Skype 的业务服务器 2015年启用双重身份验证之前。</span><span class="sxs-lookup"><span data-stu-id="41a49-145">You should use the **Invoke-CsUcsRollback** cmdlet to remove existing user contacts from the Unified Contact Store and store them in Skype for Business Server 2015 before enabling two-factor authentication.</span></span>
  
## <a name="skill-search"></a><span data-ttu-id="41a49-146">技能搜索</span><span class="sxs-lookup"><span data-stu-id="41a49-146">Skill Search</span></span>

<span data-ttu-id="41a49-147">在其 Skype 业务环境中配置的技能搜索功能的客户将发现 for Business 的 Skype 启用双重身份验证时，此功能不工作。</span><span class="sxs-lookup"><span data-stu-id="41a49-147">Customers who have configured the Skill Search feature in their Skype for Business environment will find that this feature does not work when Skype for Business is enabled for two-factor authentication.</span></span> <span data-ttu-id="41a49-148">这是设计使然，因为 Microsoft SharePoint 当前不支持双重身份验证。</span><span class="sxs-lookup"><span data-stu-id="41a49-148">This is by design, as Microsoft SharePoint does not currently support two-factor authentication.</span></span>
  
## <a name="credentials"></a><span data-ttu-id="41a49-149">凭据</span><span class="sxs-lookup"><span data-stu-id="41a49-149">Credentials</span></span>

<span data-ttu-id="41a49-150">有大量涉及的业务凭据，这可能会影响配置为使用双重身份验证的用户的已保存的 Skype 的部署注意事项。</span><span class="sxs-lookup"><span data-stu-id="41a49-150">There are a number of deployment considerations involving saved Skype for Business credentials which may impact users who are configured to use two-factor authentication.</span></span>
  
### <a name="deleting-saved-credentials"></a><span data-ttu-id="41a49-151">删除保存的凭据</span><span class="sxs-lookup"><span data-stu-id="41a49-151">Deleting Saved Credentials</span></span>

<span data-ttu-id="41a49-152">用户应使用**删除我登录信息**选项中 Skype for Business 客户端并删除其 SIP 配置文件文件夹从 %localappdata%\Microsoft\Office\15.0\Skype for Business 尝试使用双重首次登录之前身份验证。</span><span class="sxs-lookup"><span data-stu-id="41a49-152">Users should use the **Delete my sign-in info** option in the Skype for Business client and delete their SIP profile folder from %localappdata%\Microsoft\Office\15.0\Skype for Business before attempting to sign for the first time using two-factor authentication.</span></span>
  
### <a name="disablentcredentials"></a><span data-ttu-id="41a49-153">DisableNTCredentials</span><span class="sxs-lookup"><span data-stu-id="41a49-153">DisableNTCredentials</span></span>

<span data-ttu-id="41a49-154">采用 Kerberos 或 NTLM 身份验证方法时，身份验证可以自动使用用户的 Windows 凭据。</span><span class="sxs-lookup"><span data-stu-id="41a49-154">With the Kerberos or NTLM authentication method, the user's Windows credentials are used automatically for authentication.</span></span> <span data-ttu-id="41a49-155">在启用了 Kerberos 和/或 NTLM 是身份验证的业务服务器 2015年部署典型 Skype，用户不必输入其凭据登录每次。</span><span class="sxs-lookup"><span data-stu-id="41a49-155">In a typical Skype for Business Server 2015 deployment where Kerberos and/or NTLM is enabled for authentication, users should not have to enter their credentials every time that they sign in.</span></span>
  
<span data-ttu-id="41a49-156">如果在提示用户输入其 PIN 之前无意中提示用户输入凭据，则可能通过组策略在客户端计算机上无意中配置了 **DisableNTCredentials** 注册表项。</span><span class="sxs-lookup"><span data-stu-id="41a49-156">If users are unintentionally prompted for credentials before they are prompted to enter their PIN, the **DisableNTCredentials** registry key may be unintentionally configured on client computers, possibly through Group Policy.</span></span>
  
<span data-ttu-id="41a49-157">若要防止额外提示输入凭据，在本地工作站上创建以下注册表项，或者使用业务管理模板 Skype 于给定池使用组策略的所有用户：</span><span class="sxs-lookup"><span data-stu-id="41a49-157">To prevent the additional prompt for credentials, create the following registry entry on the local workstation or use the Skype for Business administrative template to apply to all users for a given pool using Group Policy:</span></span>
  
    HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Office\15.0\Lync
  
    REG_DWORD: DisableNTCredentials
  
    Value: 0x0
  
### <a name="savepassword"></a><span data-ttu-id="41a49-158">SavePassword</span><span class="sxs-lookup"><span data-stu-id="41a49-158">SavePassword</span></span>

<span data-ttu-id="41a49-159">当用户登录到 for Business 的 Skype 第一次时，提示用户保存他/她的密码。</span><span class="sxs-lookup"><span data-stu-id="41a49-159">When a user signs in to Skype for Business for the first time, the user is prompted to save his or her password.</span></span> <span data-ttu-id="41a49-160">如果选中，则此选项允许用户的客户端证书存储中的个人证书存储和用户的 Windows 凭据存储在凭据管理器中的本地计算机。</span><span class="sxs-lookup"><span data-stu-id="41a49-160">If selected, this option allows the user's client certificate to be stored in the personal certificate store and the user's Windows credentials to be stored in the Credential Manager of the local computer.</span></span>
  
<span data-ttu-id="41a49-161">当 for Business 的 Skype 配置为支持双重身份验证时，应禁用**SavePassword**注册表设置。</span><span class="sxs-lookup"><span data-stu-id="41a49-161">The **SavePassword** registry setting should be disabled when Skype for Business is configured to support two-factor authentication.</span></span> <span data-ttu-id="41a49-162">若要禁止用户保存其密码，更改本地工作站上的以下注册表项或使用业务管理模板 Skype 于给定池使用组策略的所有用户：</span><span class="sxs-lookup"><span data-stu-id="41a49-162">To prevent users from saving their passwords, change the following registry entry on the local workstation or use the Skype for Business administrative template to apply to all users for a given pool using Group Policy:</span></span>
  
    HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync
  
    REG_DWORD: SavePassword
  
    Value: 0x0
  
## <a name="ad-fs-20-token-replay"></a><span data-ttu-id="41a49-163">AD FS 2.0 令牌重播</span><span class="sxs-lookup"><span data-stu-id="41a49-163">AD FS 2.0 Token Replay</span></span>

<span data-ttu-id="41a49-p110">AD FS 2.0 提供了一项功能称为“令牌重播检测”，借助该功能，可以检测并丢弃多个使用相同令牌的令牌请求。启用此功能时，令牌重播检测可确保从不多次使用相同令牌，从而保护 WS 联合被动配置文件和 SAML WebSSO 配置文件中身份验证请求的完整性。</span><span class="sxs-lookup"><span data-stu-id="41a49-p110">AD FS 2.0 provides a feature referred to as token replay detection, by which multiple token requests using the same token can be detected and then discarded. When this feature is enabled, token replay detection protects the integrity of authentication requests in both the WS-Federation passive profile and the SAML WebSSO profile by making sure that the same token is never used more than once.</span></span>
  
<span data-ttu-id="41a49-166">在高度关注安全的环境（例如使用展台时）中，应启用此功能。</span><span class="sxs-lookup"><span data-stu-id="41a49-166">This feature should be enabled in situations where security is a very high concern such as when using kiosks.</span></span> <span data-ttu-id="41a49-167">有关令牌重放检测的详细信息，请参阅[安全规划和部署 AD FS 2.0 的最佳实践](https://go.microsoft.com/fwlink/p/?LinkId=309215)。</span><span class="sxs-lookup"><span data-stu-id="41a49-167">For more information about token replay detection, see [Best Practices for Secure Planning and Deployment of AD FS 2.0](https://go.microsoft.com/fwlink/p/?LinkId=309215).</span></span>
  
## <a name="external-user-access"></a><span data-ttu-id="41a49-168">外部用户访问</span><span class="sxs-lookup"><span data-stu-id="41a49-168">External User Access</span></span>

<span data-ttu-id="41a49-169">这些主题中没有介绍配置 ADFS 代理或反向代理以从外部网络业务双重身份验证支持 Skype。</span><span class="sxs-lookup"><span data-stu-id="41a49-169">Configuring an ADFS Proxy or Reverse Proxy to support Skype for Business two-factor authentication from external networks is not covered in these topics.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="41a49-170">另请参阅</span><span class="sxs-lookup"><span data-stu-id="41a49-170">See also</span></span>

[<span data-ttu-id="41a49-171">在 Skype for Business Server 2015 配置双重身份验证</span><span class="sxs-lookup"><span data-stu-id="41a49-171">Configure two-factor authentication in Skype for Business Server 2015</span></span>](configure.md)
  
[<span data-ttu-id="41a49-172">在 Skype for Business Server 2015 配置双重身份验证</span><span class="sxs-lookup"><span data-stu-id="41a49-172">Configure two-factor authentication in Skype for Business Server 2015</span></span>](configure.md)