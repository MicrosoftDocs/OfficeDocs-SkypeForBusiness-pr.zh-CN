---
title: Lync Server 2013：规划双因素身份验证
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for two-factor authentication
ms:assetid: 16f08710-8961-4659-acbf-ebb95a198fb4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308562(v=OCS.15)
ms:contentKeyID: 54973683
ms.date: 04/06/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b973a1eeb704788eb07e02afc502ac4bbe41544c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139273"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-two-factor-authentication-in-lync-server-2013"></a><span data-ttu-id="0cf58-102">在 Lync Server 2013 中规划双因素身份验证</span><span class="sxs-lookup"><span data-stu-id="0cf58-102">Planning for two-factor authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0cf58-103">_**上次修改的主题：** 2015-04-06_</span><span class="sxs-lookup"><span data-stu-id="0cf58-103">_**Topic Last Modified:** 2015-04-06_</span></span>

<span data-ttu-id="0cf58-104">以下是配置 Microsoft Lync Server 2013 环境以支持双重身份验证时的部署注意事项列表。</span><span class="sxs-lookup"><span data-stu-id="0cf58-104">The following is a list of deployment considerations when configuring a Microsoft Lync Server 2013 environment to support two-factor authentication.</span></span>

<div>

## <a name="client-support"></a><span data-ttu-id="0cf58-105">客户端支持</span><span class="sxs-lookup"><span data-stu-id="0cf58-105">Client Support</span></span>

<span data-ttu-id="0cf58-106">Lync Server 2013 的 Lync 2013 累积更新：7月2013桌面客户端和所有移动客户端当前支持双重身份验证。</span><span class="sxs-lookup"><span data-stu-id="0cf58-106">The Lync 2013 Cumulative Updates for Lync Server 2013: July 2013 desktop client and all mobile clients currently support two-factor authentication.</span></span>

</div>

<div>

## <a name="topology-requirements"></a><span data-ttu-id="0cf58-107">拓扑要求</span><span class="sxs-lookup"><span data-stu-id="0cf58-107">Topology Requirements</span></span>

<span data-ttu-id="0cf58-108">强烈建议客户使用专用 Lync Server 2013 和 Lync Server 2013 的累积更新来部署双重身份验证：7月 2013 Edge、Director 和用户池。</span><span class="sxs-lookup"><span data-stu-id="0cf58-108">Customers are strongly encouraged to deploy two-factor authentication using dedicated Lync Server 2013 with Cumulative Updates for Lync Server 2013: July 2013 Edge, Director, and User Pools.</span></span> <span data-ttu-id="0cf58-109">若要为 Lync 用户启用被动身份验证，必须为其他角色和服务禁用其他身份验证方法，包括以下各项：</span><span class="sxs-lookup"><span data-stu-id="0cf58-109">To enable passive authentication for Lync users, other authentication methods must be disabled for other roles and services, including the following:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0cf58-110">配置类型</span><span class="sxs-lookup"><span data-stu-id="0cf58-110">Configuration Type</span></span></th>
<th><span data-ttu-id="0cf58-111">服务类型</span><span class="sxs-lookup"><span data-stu-id="0cf58-111">Service Type</span></span></th>
<th><span data-ttu-id="0cf58-112">服务器角色</span><span class="sxs-lookup"><span data-stu-id="0cf58-112">Server Role</span></span></th>
<th><span data-ttu-id="0cf58-113">要禁用的身份验证类型</span><span class="sxs-lookup"><span data-stu-id="0cf58-113">Authentication Type to Disable</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0cf58-114">Web 服务</span><span class="sxs-lookup"><span data-stu-id="0cf58-114">Web Service</span></span></p></td>
<td><p><span data-ttu-id="0cf58-115">Web</span><span class="sxs-lookup"><span data-stu-id="0cf58-115">WebServer</span></span></p></td>
<td><p><span data-ttu-id="0cf58-116">控制器</span><span class="sxs-lookup"><span data-stu-id="0cf58-116">Director</span></span></p></td>
<td><p><span data-ttu-id="0cf58-117">Kerberos、NTLM 和证书</span><span class="sxs-lookup"><span data-stu-id="0cf58-117">Kerberos, NTLM, and Certificate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0cf58-118">Web 服务</span><span class="sxs-lookup"><span data-stu-id="0cf58-118">Web Service</span></span></p></td>
<td><p><span data-ttu-id="0cf58-119">Web</span><span class="sxs-lookup"><span data-stu-id="0cf58-119">WebServer</span></span></p></td>
<td><p><span data-ttu-id="0cf58-120">前端</span><span class="sxs-lookup"><span data-stu-id="0cf58-120">Front End</span></span></p></td>
<td><p><span data-ttu-id="0cf58-121">Kerberos、NTLM 和证书</span><span class="sxs-lookup"><span data-stu-id="0cf58-121">Kerberos, NTLM, and Certificate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0cf58-122">代理</span><span class="sxs-lookup"><span data-stu-id="0cf58-122">Proxy</span></span></p></td>
<td><p><span data-ttu-id="0cf58-123">EdgeServer</span><span class="sxs-lookup"><span data-stu-id="0cf58-123">EdgeServer</span></span></p></td>
<td><p><span data-ttu-id="0cf58-124">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="0cf58-124">Edge</span></span></p></td>
<td><p><span data-ttu-id="0cf58-125">Kerberos 和 NTLM</span><span class="sxs-lookup"><span data-stu-id="0cf58-125">Kerberos and NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0cf58-126">代理</span><span class="sxs-lookup"><span data-stu-id="0cf58-126">Proxy</span></span></p></td>
<td><p><span data-ttu-id="0cf58-127">注册</span><span class="sxs-lookup"><span data-stu-id="0cf58-127">Registrar</span></span></p></td>
<td><p><span data-ttu-id="0cf58-128">前端</span><span class="sxs-lookup"><span data-stu-id="0cf58-128">Front End</span></span></p></td>
<td><p><span data-ttu-id="0cf58-129">Kerberos 和 NTLM</span><span class="sxs-lookup"><span data-stu-id="0cf58-129">Kerberos and NTLM</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="0cf58-130">除非在服务级别禁用这些身份验证类型，否则在您的部署中启用双重身份验证后，Lync 客户端的所有其他版本都将无法成功登录。</span><span class="sxs-lookup"><span data-stu-id="0cf58-130">Unless these authentication types are disabled at the service level, all other versions of the Lync client will be unable to sign in successfully once two-factor authentication is enabled within in your deployment.</span></span>

</div>

<div>

## <a name="lync-service-discovery"></a><span data-ttu-id="0cf58-131">Lync 服务发现</span><span class="sxs-lookup"><span data-stu-id="0cf58-131">Lync Service Discovery</span></span>

<span data-ttu-id="0cf58-132">应将内部和/或外部客户端使用的 DNS 记录配置为解析为未启用双重身份验证的 Lync server。</span><span class="sxs-lookup"><span data-stu-id="0cf58-132">DNS records used by internal and/or external clients to discover Lync services should be configured to resolve to a Lync server that is not enabled for two-factor authentication.</span></span> <span data-ttu-id="0cf58-133">使用此配置时，未启用双因素身份验证的 Lync 池中的用户不需要输入 PIN 即可进行身份验证，而启用了双重身份验证的 Lync 池中的用户将需要将其 PIN 输入到鉴别.</span><span class="sxs-lookup"><span data-stu-id="0cf58-133">With this configuration, users from Lync Pools that are not enabled for two-factor authentication will not be required to enter a PIN to authenticate, while users from Lync Pools that are enabled for two-factor authentication will be required to enter their PIN to authenticate.</span></span>

</div>

<div>

## <a name="exchange-authentication"></a><span data-ttu-id="0cf58-134">Exchange 身份验证</span><span class="sxs-lookup"><span data-stu-id="0cf58-134">Exchange Authentication</span></span>

<span data-ttu-id="0cf58-135">已为 Microsoft Exchange 部署双重身份验证的客户可能会发现 Lync 客户端中的某些功能不可用。</span><span class="sxs-lookup"><span data-stu-id="0cf58-135">Customers who have deployed two-factor authentication for Microsoft Exchange may find that certain features in the Lync client are unavailable.</span></span> <span data-ttu-id="0cf58-136">这是当前设计的，因为 Lync 客户端不支持依赖 Exchange 集成的功能的双重身份验证。</span><span class="sxs-lookup"><span data-stu-id="0cf58-136">This is currently by design, as the Lync client does not support two-factor authentication for features that are dependent on Exchange integration.</span></span>

</div>

<div>

## <a name="lync-contacts"></a><span data-ttu-id="0cf58-137">Lync 联系人</span><span class="sxs-lookup"><span data-stu-id="0cf58-137">Lync Contacts</span></span>

<span data-ttu-id="0cf58-138">配置为利用统一联系人存储功能的 Lync 用户将会发现，在使用双重身份验证登录后，他们的联系人将不再可用。</span><span class="sxs-lookup"><span data-stu-id="0cf58-138">Lync users who are configured to leverage the Unified Contact Store feature will find that their contacts are no longer available after signing in with two-factor authentication.</span></span>

<span data-ttu-id="0cf58-139">应使用**invoke-csucsrollback** Cmdlet 从统一的联系人存储库中删除现有用户联系人，并将其存储在 Lync Server 2013 中，然后再启用双重身份验证。</span><span class="sxs-lookup"><span data-stu-id="0cf58-139">You should use the **Invoke-CsUcsRollback** cmdlet to remove existing user contacts from the Unified Contact Store and store them in Lync Server 2013 before enabling two-factor authentication.</span></span>

</div>

<div>

## <a name="skill-search"></a><span data-ttu-id="0cf58-140">技能搜索</span><span class="sxs-lookup"><span data-stu-id="0cf58-140">Skill Search</span></span>

<span data-ttu-id="0cf58-141">在 Lync 环境中配置技能搜索功能的客户将会发现启用了双因素身份验证的 Lync 后，此功能不起作用。</span><span class="sxs-lookup"><span data-stu-id="0cf58-141">Customers who have configured the Skill Search feature in their Lync environment will find that this feature does not work when Lync is enabled for two-factor authentication.</span></span> <span data-ttu-id="0cf58-142">这是由设计决定的，因为 Microsoft SharePoint 目前不支持双重身份验证。</span><span class="sxs-lookup"><span data-stu-id="0cf58-142">This is by design, as Microsoft SharePoint does not currently support two-factor authentication.</span></span>

</div>

<div>

## <a name="lync-credentials"></a><span data-ttu-id="0cf58-143">Lync 凭据</span><span class="sxs-lookup"><span data-stu-id="0cf58-143">Lync Credentials</span></span>

<span data-ttu-id="0cf58-144">有许多部署注意事项涉及保存的 Lync 凭据，这可能会影响配置为使用双重身份验证的用户。</span><span class="sxs-lookup"><span data-stu-id="0cf58-144">There are a number of deployment considerations involving saved Lync credentials which may impact users who are configured to use two-factor authentication.</span></span>

<div>

## <a name="deleting-saved-credentials"></a><span data-ttu-id="0cf58-145">删除保存的凭据</span><span class="sxs-lookup"><span data-stu-id="0cf58-145">Deleting Saved Credentials</span></span>

<span data-ttu-id="0cf58-146">桌面客户端用户应使用 Lync 客户端中的 "**删除我的登录信息**" 选项，并从% localappdata\\% Microsoft\\OFFICE\\15.0\\Lync 中删除其 SIP 配置文件文件夹，然后再尝试使用双重身份验证进行首次签名。</span><span class="sxs-lookup"><span data-stu-id="0cf58-146">Desktop client users should use the **Delete my sign-in info** option in the Lync client and delete their SIP profile folder from %localappdata%\\Microsoft\\Office\\15.0\\Lync before attempting to sign for the first time using two-factor authentication.</span></span>

</div>

<div>

## <a name="disablentcredentials"></a><span data-ttu-id="0cf58-147">DisableNTCredentials</span><span class="sxs-lookup"><span data-stu-id="0cf58-147">DisableNTCredentials</span></span>

<span data-ttu-id="0cf58-148">使用 Kerberos 或 NTLM 身份验证方法时，将自动使用用户的 Windows 凭据进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="0cf58-148">With the Kerberos or NTLM authentication method, the user’s Windows credentials are used automatically for authentication.</span></span> <span data-ttu-id="0cf58-149">在为身份验证启用了 Kerberos 和/或 NTLM 的典型 Lync Server 2013 部署中，用户在每次登录时都不应输入其凭据。</span><span class="sxs-lookup"><span data-stu-id="0cf58-149">In a typical Lync Server 2013 deployment where Kerberos and/or NTLM is enabled for authentication, users should not have to enter their credentials every time that they sign in.</span></span>

<span data-ttu-id="0cf58-150">如果在提示用户输入 PIN 之前，无意中提示用户输入凭据，则可能会在客户端计算机上无意中配置**DisableNTCredentials**注册表项，这可能是通过组策略。</span><span class="sxs-lookup"><span data-stu-id="0cf58-150">If users are unintentionally prompted for credentials before they are prompted to enter their PIN, the **DisableNTCredentials** registry key may be unintentionally configured on client computers, possibly through Group Policy.</span></span>

<span data-ttu-id="0cf58-151">若要阻止额外的凭据提示，请在本地工作站上创建以下注册表项，或使用 Lync 管理模板应用到使用组策略的给定池的所有用户：</span><span class="sxs-lookup"><span data-stu-id="0cf58-151">To prevent the additional prompt for credentials, create the following registry entry on the local workstation or use the Lync administrative template to apply to all users for a given pool using Group Policy:</span></span>

<span data-ttu-id="0cf58-152">HKEY\_本地\_机器\\软件\\策略\\Microsoft\\Office\\15.0\\Lync</span><span class="sxs-lookup"><span data-stu-id="0cf58-152">HKEY\_LOCAL\_MACHINE\\Software\\Policies\\Microsoft\\Office\\15.0\\Lync</span></span>

<span data-ttu-id="0cf58-153">REG\_DWORD： DisableNTCredentials</span><span class="sxs-lookup"><span data-stu-id="0cf58-153">REG\_DWORD: DisableNTCredentials</span></span>

<span data-ttu-id="0cf58-154">值：0x0</span><span class="sxs-lookup"><span data-stu-id="0cf58-154">Value: 0x0</span></span>

</div>

<div>

## <a name="savepassword"></a><span data-ttu-id="0cf58-155">SavePassword</span><span class="sxs-lookup"><span data-stu-id="0cf58-155">SavePassword</span></span>

<span data-ttu-id="0cf58-156">当用户第一次登录 Lync 时，系统会提示用户保存其密码。</span><span class="sxs-lookup"><span data-stu-id="0cf58-156">When a user signs in to Lync for the first time, the user is prompted to save his or her password.</span></span> <span data-ttu-id="0cf58-157">如果选中此选项，则允许将用户的客户端证书存储在个人证书存储中，并允许将用户的 Windows 凭据存储在本地计算机的凭据管理器中。</span><span class="sxs-lookup"><span data-stu-id="0cf58-157">If selected, this option allows the user’s client certificate to be stored in the personal certificate store and the user’s Windows credentials to be stored in the Credential Manager of the local computer.</span></span>

<span data-ttu-id="0cf58-158">将 Lync 配置为支持双重身份验证时，应禁用**SavePassword**注册表设置。</span><span class="sxs-lookup"><span data-stu-id="0cf58-158">The **SavePassword** registry setting should be disabled when Lync is configured to support two-factor authentication.</span></span> <span data-ttu-id="0cf58-159">若要防止用户保存其密码，请更改本地工作站上的以下注册表项，或使用 Lync 管理模板将组策略应用于给定池的所有用户：</span><span class="sxs-lookup"><span data-stu-id="0cf58-159">To prevent users from saving their passwords, change the following registry entry on the local workstation or use the Lync administrative template to apply to all users for a given pool using Group Policy:</span></span>

<span data-ttu-id="0cf58-160">HKEY\_当前\_用户\\软件\\Microsoft\\Office\\15.0\\Lync</span><span class="sxs-lookup"><span data-stu-id="0cf58-160">HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync</span></span>

<span data-ttu-id="0cf58-161">REG\_DWORD： SavePassword</span><span class="sxs-lookup"><span data-stu-id="0cf58-161">REG\_DWORD: SavePassword</span></span>

<span data-ttu-id="0cf58-162">值：0x0</span><span class="sxs-lookup"><span data-stu-id="0cf58-162">Value: 0x0</span></span>

</div>

</div>

<div>

## <a name="ad-fs-20-token-replay"></a><span data-ttu-id="0cf58-163">AD FS 2.0 令牌重播</span><span class="sxs-lookup"><span data-stu-id="0cf58-163">AD FS 2.0 Token Replay</span></span>

<span data-ttu-id="0cf58-164">AD FS 2.0 提供一种称为令牌重播检测的功能，可检测到使用相同令牌的多个令牌请求，然后将其丢弃。</span><span class="sxs-lookup"><span data-stu-id="0cf58-164">AD FS 2.0 provides a feature referred to as token replay detection, by which multiple token requests using the same token can be detected and then discarded.</span></span> <span data-ttu-id="0cf58-165">启用此功能后，令牌重播检测通过确保从不使用同一令牌来保护两个 WS 联合身份验证被动配置文件和 SAML WebSSO 配置文件中的身份验证请求的完整性。</span><span class="sxs-lookup"><span data-stu-id="0cf58-165">When this feature is enabled, token replay detection protects the integrity of authentication requests in both the WS-Federation passive profile and the SAML WebSSO profile by making sure that the same token is never used more than once.</span></span>

<span data-ttu-id="0cf58-166">如果安全性是非常重要的问题（例如使用展台时），应启用此功能。</span><span class="sxs-lookup"><span data-stu-id="0cf58-166">This feature should be enabled in situations where security is a very high concern such as when using kiosks.</span></span> <span data-ttu-id="0cf58-167">有关令牌重播检测的详细信息，请参阅在上[https://go.microsoft.com/fwlink/p/?LinkId=309215](https://go.microsoft.com/fwlink/p/?linkid=309215)安全规划和部署 AD FS 2.0 的最佳实践。</span><span class="sxs-lookup"><span data-stu-id="0cf58-167">For more information about token replay detection, see Best Practices for Secure Planning and Deployment of AD FS 2.0 at [https://go.microsoft.com/fwlink/p/?LinkId=309215](https://go.microsoft.com/fwlink/p/?linkid=309215).</span></span>

</div>

<div>

## <a name="external-user-access"></a><span data-ttu-id="0cf58-168">外部用户访问</span><span class="sxs-lookup"><span data-stu-id="0cf58-168">External User Access</span></span>

<span data-ttu-id="0cf58-169">这些主题不涉及将 AD FS 代理或反向代理配置为支持来自外部网络的 Lync 双重身份验证。</span><span class="sxs-lookup"><span data-stu-id="0cf58-169">Configuring an AD FS Proxy or Reverse Proxy to support Lync two-factor authentication from external networks is not covered in these topics.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

