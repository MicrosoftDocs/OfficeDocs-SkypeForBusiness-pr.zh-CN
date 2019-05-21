---
title: 在 Skype for Business 服务器中管理双因素身份验证
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 16f08710-8961-4659-acbf-ebb95a198fb4
description: '摘要: 在 Skype for Business 服务器中管理双因素身份验证。'
ms.openlocfilehash: ccda6795fa5033c792c293701d951e3111666e82
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297559"
---
# <a name="manage-two-factor-authentication-in-skype-for-business-server"></a><span data-ttu-id="05567-103">在 Skype for Business 服务器中管理双因素身份验证</span><span class="sxs-lookup"><span data-stu-id="05567-103">Manage two-factor authentication in Skype for Business Server</span></span>
 
<span data-ttu-id="05567-104">**摘要:** 在 Skype for Business 服务器中管理双因素身份验证。</span><span class="sxs-lookup"><span data-stu-id="05567-104">**Summary:** Manage two-factor authentication in Skype for Business Server.</span></span>
  
<span data-ttu-id="05567-105">双重身份验证要求用户提供两种形式的身份验证或身份识别，即用户名/密码组合以及令牌或证书，从而提供了更高的安全性。</span><span class="sxs-lookup"><span data-stu-id="05567-105">Two-factor authentication provides improved security by requiring users to provide two forms of authentication or identification, namely a user name/password combination and a token or certificate.</span></span> <span data-ttu-id="05567-106">这也称为 "你拥有的内容, 你认识的内容"。</span><span class="sxs-lookup"><span data-stu-id="05567-106">This is also known as "something you have, something you know."</span></span> 
  
<span data-ttu-id="05567-p102">使用证书进行双重身份验证的一个典型示例是使用智能卡。智能卡包含与用户帐户相关联的证书，可对照服务器上存储的用户和证书信息进行验证。通过将用户信息（用户名和密码）与提供的证书进行比较，服务器将验证凭据并验证用户身份。</span><span class="sxs-lookup"><span data-stu-id="05567-p102">A typical example of two-factor authentication with a certificate is the use of smart cards. A smart card contains a certificate associated with the user account, and can be validated against user and certificate information stored on a server. By comparing the user information (user name and password) to the certificate provided, the server validates the credentials and authenticates the user.</span></span>
  
<span data-ttu-id="05567-110">配置 Skype for Business 服务器环境以支持双因素身份验证时, 请考虑以下主题。</span><span class="sxs-lookup"><span data-stu-id="05567-110">Consider the following subjects when configuring a Skype for Business Server environment to support two-factor authentication.</span></span>
  
## <a name="client-support"></a><span data-ttu-id="05567-111">客户端支持</span><span class="sxs-lookup"><span data-stu-id="05567-111">Client Support</span></span>

<span data-ttu-id="05567-112">Lync Server 2013 的累积更新: 7 月2013桌面客户端和 Skype for Business 客户端是唯一支持双因素身份验证的客户端。</span><span class="sxs-lookup"><span data-stu-id="05567-112">The Cumulative Updates for Lync Server 2013: July 2013 desktop client and the Skype for Business client are the only clients that currently support two-factor authentication.</span></span>
  
## <a name="topology-requirements"></a><span data-ttu-id="05567-113">拓扑要求</span><span class="sxs-lookup"><span data-stu-id="05567-113">Topology Requirements</span></span>

<span data-ttu-id="05567-114">强烈建议客户使用专用的 Skype for Business 服务器 (具有边缘、控制器和用户池) 部署双因素身份验证。</span><span class="sxs-lookup"><span data-stu-id="05567-114">Customers are strongly encouraged to deploy two-factor authentication using dedicated Skype for Business Server with Edge, Director, and User Pools.</span></span> <span data-ttu-id="05567-115">要为用户启用被动身份验证，必须为其他角色和服务禁用其他身份验证方法，包括以下各项：</span><span class="sxs-lookup"><span data-stu-id="05567-115">To enable passive authentication for users, other authentication methods must be disabled for other roles and services, including the following:</span></span>
  
|<span data-ttu-id="05567-116">**配置类型**</span><span class="sxs-lookup"><span data-stu-id="05567-116">**Configuration Type**</span></span>|<span data-ttu-id="05567-117">**服务类型**</span><span class="sxs-lookup"><span data-stu-id="05567-117">**Service Type**</span></span>|<span data-ttu-id="05567-118">**服务器角色**</span><span class="sxs-lookup"><span data-stu-id="05567-118">**Server Role**</span></span>|<span data-ttu-id="05567-119">**要禁用的身份验证类型**</span><span class="sxs-lookup"><span data-stu-id="05567-119">**Authentication Type to Disable**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="05567-120">Web 服务</span><span class="sxs-lookup"><span data-stu-id="05567-120">Web Service</span></span>  <br/> |<span data-ttu-id="05567-121">Web 服务器</span><span class="sxs-lookup"><span data-stu-id="05567-121">WebServer</span></span>  <br/> |<span data-ttu-id="05567-122">控制器</span><span class="sxs-lookup"><span data-stu-id="05567-122">Director</span></span>  <br/> |<span data-ttu-id="05567-123">Kerberos、NTLM 和证书</span><span class="sxs-lookup"><span data-stu-id="05567-123">Kerberos, NTLM, and Certificate</span></span>  <br/> |
|<span data-ttu-id="05567-124">Web 服务</span><span class="sxs-lookup"><span data-stu-id="05567-124">Web Service</span></span>  <br/> |<span data-ttu-id="05567-125">Web 服务器</span><span class="sxs-lookup"><span data-stu-id="05567-125">WebServer</span></span>  <br/> |<span data-ttu-id="05567-126">前端</span><span class="sxs-lookup"><span data-stu-id="05567-126">Front End</span></span>  <br/> |<span data-ttu-id="05567-127">Kerberos、NTLM 和证书</span><span class="sxs-lookup"><span data-stu-id="05567-127">Kerberos, NTLM, and Certificate</span></span>  <br/> |
|<span data-ttu-id="05567-128">代理</span><span class="sxs-lookup"><span data-stu-id="05567-128">Proxy</span></span>  <br/> |<span data-ttu-id="05567-129">EdgeServer</span><span class="sxs-lookup"><span data-stu-id="05567-129">EdgeServer</span></span>  <br/> |<span data-ttu-id="05567-130">Edge</span><span class="sxs-lookup"><span data-stu-id="05567-130">Edge</span></span>  <br/> |<span data-ttu-id="05567-131">Kerberos 和 NTLM</span><span class="sxs-lookup"><span data-stu-id="05567-131">Kerberos and NTLM</span></span>  <br/> |
|<span data-ttu-id="05567-132">代理</span><span class="sxs-lookup"><span data-stu-id="05567-132">Proxy</span></span>  <br/> |<span data-ttu-id="05567-133">注册器</span><span class="sxs-lookup"><span data-stu-id="05567-133">Registrar</span></span>  <br/> |<span data-ttu-id="05567-134">前端</span><span class="sxs-lookup"><span data-stu-id="05567-134">Front End</span></span>  <br/> |<span data-ttu-id="05567-135">Kerberos 和 NTLM</span><span class="sxs-lookup"><span data-stu-id="05567-135">Kerberos and NTLM</span></span>  <br/> |
   
<span data-ttu-id="05567-136">除非在服务级别禁用这些身份验证类型，否则一旦在您的部署中启用双重身份验证，所有其他版本的客户端将无法成功登录。</span><span class="sxs-lookup"><span data-stu-id="05567-136">Unless these authentication types are disabled at the service level, all other versions of the client will be unable to sign in successfully once two-factor authentication is enabled within in your deployment.</span></span>
  
## <a name="skype-for-business-service-discovery"></a><span data-ttu-id="05567-137">Skype for Business 服务发现</span><span class="sxs-lookup"><span data-stu-id="05567-137">Skype for Business Service Discovery</span></span>

<span data-ttu-id="05567-138">内部和/或外部客户端用于发现 Skype for Business 服务的 DNS 记录应配置为解析为未启用双因素身份验证的 Skype for business 服务器。</span><span class="sxs-lookup"><span data-stu-id="05567-138">DNS records used by internal and/or external clients to discover Skype for Business services should be configured to resolve to a Skype for Business server that is not enabled for two-factor authentication.</span></span> <span data-ttu-id="05567-139">通过此配置, 没有为两个因素身份验证启用的 Skype for business 池中的用户输入 PIN 进行身份验证时, 将不需要输入 PIN 来进行身份验证, 而启用了双因素身份验证的 Skype for business 池中的用户将需要输入其 PIN 才能进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="05567-139">With this configuration, users from Skype for Business Pools that are not enabled for two-factor authentication will not be required to enter a PIN to authenticate, while users from Skype for Business Pools that are enabled for two-factor authentication will be required to enter their PIN to authenticate.</span></span>
  
## <a name="exchange-authentication"></a><span data-ttu-id="05567-140">Exchange 身份验证</span><span class="sxs-lookup"><span data-stu-id="05567-140">Exchange Authentication</span></span>

<span data-ttu-id="05567-141">已为 Microsoft Exchange 部署了双因素身份验证的客户可能会发现客户端中的某些功能不可用。</span><span class="sxs-lookup"><span data-stu-id="05567-141">Customers who have deployed two-factor authentication for Microsoft Exchange may find that certain features in the client are unavailable.</span></span> <span data-ttu-id="05567-142">这是当前设计的, 因为 Skype for Business 客户端不支持依赖于 Exchange 集成的功能的双因素身份验证。</span><span class="sxs-lookup"><span data-stu-id="05567-142">This is currently by design, as the Skype for Business client does not support two-factor authentication for features that are dependent on Exchange integration.</span></span>
  
## <a name="contacts"></a><span data-ttu-id="05567-143">联系人</span><span class="sxs-lookup"><span data-stu-id="05567-143">Contacts</span></span>

<span data-ttu-id="05567-144">配置为利用 "统一联系人存储" 功能的 Skype for business 用户将发现, 使用双因素身份验证登录后, 他们的联系人将不再可用。</span><span class="sxs-lookup"><span data-stu-id="05567-144">Skype for Business users who are configured to leverage the Unified Contact Store feature will find that their contacts are no longer available after signing in with two-factor authentication.</span></span>
  
<span data-ttu-id="05567-145">你应该使用**CsUcsRollback** cmdlet 从 "统一联系人存储" 中删除现有用户联系人, 并将其存储在 Skype For business 服务器中, 然后再启用双重身份验证。</span><span class="sxs-lookup"><span data-stu-id="05567-145">You should use the **Invoke-CsUcsRollback** cmdlet to remove existing user contacts from the Unified Contact Store and store them in Skype for Business Server before enabling two-factor authentication.</span></span>
  
## <a name="skill-search"></a><span data-ttu-id="05567-146">技能搜索</span><span class="sxs-lookup"><span data-stu-id="05567-146">Skill Search</span></span>

<span data-ttu-id="05567-147">在 Skype for business 环境中配置技能搜索功能的客户将发现, 当启用了双因素身份验证的 Skype for business 时, 此功能不起作用。</span><span class="sxs-lookup"><span data-stu-id="05567-147">Customers who have configured the Skill Search feature in their Skype for Business environment will find that this feature does not work when Skype for Business is enabled for two-factor authentication.</span></span> <span data-ttu-id="05567-148">这是设计使然，因为 Microsoft SharePoint 当前不支持双重身份验证。</span><span class="sxs-lookup"><span data-stu-id="05567-148">This is by design, as Microsoft SharePoint does not currently support two-factor authentication.</span></span>
  
## <a name="credentials"></a><span data-ttu-id="05567-149">凭据</span><span class="sxs-lookup"><span data-stu-id="05567-149">Credentials</span></span>

<span data-ttu-id="05567-150">有许多部署注意事项涉及保存的 Skype for Business 凭据, 这可能会影响配置为使用双因素身份验证的用户。</span><span class="sxs-lookup"><span data-stu-id="05567-150">There are a number of deployment considerations involving saved Skype for Business credentials which may impact users who are configured to use two-factor authentication.</span></span>
  
### <a name="deleting-saved-credentials"></a><span data-ttu-id="05567-151">删除保存的凭据</span><span class="sxs-lookup"><span data-stu-id="05567-151">Deleting Saved Credentials</span></span>

<span data-ttu-id="05567-152">用户应在 Skype for Business 客户端中使用 "**删除我的登录信息**" 选项, 然后在尝试使用双因素首次登录时从%Localappdata%\Microsoft\Office\15.0\Skype for business 中删除其 SIP 配置文件文件夹身份验证.</span><span class="sxs-lookup"><span data-stu-id="05567-152">Users should use the **Delete my sign-in info** option in the Skype for Business client and delete their SIP profile folder from %localappdata%\Microsoft\Office\15.0\Skype for Business before attempting to sign for the first time using two-factor authentication.</span></span>
  
### <a name="disablentcredentials"></a><span data-ttu-id="05567-153">DisableNTCredentials</span><span class="sxs-lookup"><span data-stu-id="05567-153">DisableNTCredentials</span></span>

<span data-ttu-id="05567-154">通过 Kerberos 或 NTLM 身份验证方法, 用户的 Windows 凭据会自动用于身份验证。</span><span class="sxs-lookup"><span data-stu-id="05567-154">With the Kerberos or NTLM authentication method, the user's Windows credentials are used automatically for authentication.</span></span> <span data-ttu-id="05567-155">在支持 Kerberos 和/或 NTLM 进行身份验证的典型 Skype for Business 服务器部署中, 用户每次登录时都不应输入其凭据。</span><span class="sxs-lookup"><span data-stu-id="05567-155">In a typical Skype for Business Server deployment where Kerberos and/or NTLM is enabled for authentication, users should not have to enter their credentials every time that they sign in.</span></span>
  
<span data-ttu-id="05567-156">如果在提示用户输入其 PIN 之前无意中提示用户输入凭据，则可能通过组策略在客户端计算机上无意中配置了 **DisableNTCredentials** 注册表项。</span><span class="sxs-lookup"><span data-stu-id="05567-156">If users are unintentionally prompted for credentials before they are prompted to enter their PIN, the **DisableNTCredentials** registry key may be unintentionally configured on client computers, possibly through Group Policy.</span></span>
  
<span data-ttu-id="05567-157">若要阻止额外的凭据提示, 请在本地工作站上创建以下注册表项, 或使用 "Skype for Business 管理模板" 应用到使用组策略的给定池的所有用户:</span><span class="sxs-lookup"><span data-stu-id="05567-157">To prevent the additional prompt for credentials, create the following registry entry on the local workstation or use the Skype for Business administrative template to apply to all users for a given pool using Group Policy:</span></span>
  
    HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Office\15.0\Lync
  
    REG_DWORD: DisableNTCredentials
  
    Value: 0x0
  
### <a name="savepassword"></a><span data-ttu-id="05567-158">SavePassword</span><span class="sxs-lookup"><span data-stu-id="05567-158">SavePassword</span></span>

<span data-ttu-id="05567-159">当用户首次登录 Skype for Business 时, 系统会提示用户保存其密码。</span><span class="sxs-lookup"><span data-stu-id="05567-159">When a user signs in to Skype for Business for the first time, the user is prompted to save his or her password.</span></span> <span data-ttu-id="05567-160">如果选中此选项, 将允许用户的客户端证书存储在个人证书存储和用户的 Windows 凭据中, 以便存储在本地计算机的凭据管理器中。</span><span class="sxs-lookup"><span data-stu-id="05567-160">If selected, this option allows the user's client certificate to be stored in the personal certificate store and the user's Windows credentials to be stored in the Credential Manager of the local computer.</span></span>
  
<span data-ttu-id="05567-161">当 Skype for Business 配置为支持双因素身份验证时, 应禁用**SavePassword**注册表设置。</span><span class="sxs-lookup"><span data-stu-id="05567-161">The **SavePassword** registry setting should be disabled when Skype for Business is configured to support two-factor authentication.</span></span> <span data-ttu-id="05567-162">若要防止用户保存其密码, 请在本地工作站上更改以下注册表项, 或使用 "Skype for Business 管理模板" 应用到使用组策略的给定池的所有用户:</span><span class="sxs-lookup"><span data-stu-id="05567-162">To prevent users from saving their passwords, change the following registry entry on the local workstation or use the Skype for Business administrative template to apply to all users for a given pool using Group Policy:</span></span>
  
    HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync
  
    REG_DWORD: SavePassword
  
    Value: 0x0
  
## <a name="ad-fs-20-token-replay"></a><span data-ttu-id="05567-163">AD FS 2.0 令牌重播</span><span class="sxs-lookup"><span data-stu-id="05567-163">AD FS 2.0 Token Replay</span></span>

<span data-ttu-id="05567-p110">AD FS 2.0 提供了一项功能称为“令牌重播检测”，借助该功能，可以检测并丢弃多个使用相同令牌的令牌请求。启用此功能时，令牌重播检测可确保从不多次使用相同令牌，从而保护 WS 联合被动配置文件和 SAML WebSSO 配置文件中身份验证请求的完整性。</span><span class="sxs-lookup"><span data-stu-id="05567-p110">AD FS 2.0 provides a feature referred to as token replay detection, by which multiple token requests using the same token can be detected and then discarded. When this feature is enabled, token replay detection protects the integrity of authentication requests in both the WS-Federation passive profile and the SAML WebSSO profile by making sure that the same token is never used more than once.</span></span>
  
<span data-ttu-id="05567-166">在高度关注安全的环境（例如使用展台时）中，应启用此功能。</span><span class="sxs-lookup"><span data-stu-id="05567-166">This feature should be enabled in situations where security is a very high concern such as when using kiosks.</span></span> <span data-ttu-id="05567-167">有关令牌重播检测的详细信息, 请参阅[安全规划和部署 AD FS 2.0 的最佳做法](https://go.microsoft.com/fwlink/p/?LinkId=309215)。</span><span class="sxs-lookup"><span data-stu-id="05567-167">For more information about token replay detection, see [Best Practices for Secure Planning and Deployment of AD FS 2.0](https://go.microsoft.com/fwlink/p/?LinkId=309215).</span></span>
  
## <a name="external-user-access"></a><span data-ttu-id="05567-168">外部用户访问</span><span class="sxs-lookup"><span data-stu-id="05567-168">External User Access</span></span>

<span data-ttu-id="05567-169">将 ADFS 代理或反向代理配置为支持 Skype for business 来自外部网络的双重身份验证不包括在这些主题中。</span><span class="sxs-lookup"><span data-stu-id="05567-169">Configuring an ADFS Proxy or Reverse Proxy to support Skype for Business two-factor authentication from external networks is not covered in these topics.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="05567-170">另请参阅</span><span class="sxs-lookup"><span data-stu-id="05567-170">See also</span></span>

[<span data-ttu-id="05567-171">在 Skype for Business 服务器中配置双因素身份验证</span><span class="sxs-lookup"><span data-stu-id="05567-171">Configure two-factor authentication in Skype for Business Server</span></span>](configure-two-factor.md)
  
