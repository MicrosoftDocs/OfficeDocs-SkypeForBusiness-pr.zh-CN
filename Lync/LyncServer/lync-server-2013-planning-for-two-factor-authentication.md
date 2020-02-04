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
ms.openlocfilehash: e610990182e01c0e9e2d7199bd3a34f70fbe3132
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41750432"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-two-factor-authentication-in-lync-server-2013"></a><span data-ttu-id="a5eb4-102">在 Lync Server 2013 中规划双因素身份验证</span><span class="sxs-lookup"><span data-stu-id="a5eb4-102">Planning for two-factor authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a5eb4-103">_**主题上次修改时间：** 2015-04-06_</span><span class="sxs-lookup"><span data-stu-id="a5eb4-103">_**Topic Last Modified:** 2015-04-06_</span></span>

<span data-ttu-id="a5eb4-104">以下是配置 Microsoft Lync Server 2013 环境以支持双因素身份验证时的部署注意事项列表。</span><span class="sxs-lookup"><span data-stu-id="a5eb4-104">The following is a list of deployment considerations when configuring a Microsoft Lync Server 2013 environment to support two-factor authentication.</span></span>

<div>

## <a name="client-support"></a><span data-ttu-id="a5eb4-105">客户端支持</span><span class="sxs-lookup"><span data-stu-id="a5eb4-105">Client Support</span></span>

<span data-ttu-id="a5eb4-106">Lync Server 2013 的 Lync 2013 累积更新：7月2013桌面客户端和所有移动客户端当前支持双重身份验证。</span><span class="sxs-lookup"><span data-stu-id="a5eb4-106">The Lync 2013 Cumulative Updates for Lync Server 2013: July 2013 desktop client and all mobile clients currently support two-factor authentication.</span></span>

</div>

<div>

## <a name="topology-requirements"></a><span data-ttu-id="a5eb4-107">拓扑要求</span><span class="sxs-lookup"><span data-stu-id="a5eb4-107">Topology Requirements</span></span>

<span data-ttu-id="a5eb4-108">强烈建议客户使用专用 Lync Server 2013 进行双因素身份验证，使用 Lync Server 2013 的累积更新：7月 2013 Edge、导演和用户池。</span><span class="sxs-lookup"><span data-stu-id="a5eb4-108">Customers are strongly encouraged to deploy two-factor authentication using dedicated Lync Server 2013 with Cumulative Updates for Lync Server 2013: July 2013 Edge, Director, and User Pools.</span></span> <span data-ttu-id="a5eb4-109">若要为 Lync 用户启用被动身份验证，必须为其他角色和服务禁用其他身份验证方法，包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="a5eb4-109">To enable passive authentication for Lync users, other authentication methods must be disabled for other roles and services, including the following:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a5eb4-110">配置类型</span><span class="sxs-lookup"><span data-stu-id="a5eb4-110">Configuration Type</span></span></th>
<th><span data-ttu-id="a5eb4-111">服务类型</span><span class="sxs-lookup"><span data-stu-id="a5eb4-111">Service Type</span></span></th>
<th><span data-ttu-id="a5eb4-112">服务器角色</span><span class="sxs-lookup"><span data-stu-id="a5eb4-112">Server Role</span></span></th>
<th><span data-ttu-id="a5eb4-113">要禁用的身份验证类型</span><span class="sxs-lookup"><span data-stu-id="a5eb4-113">Authentication Type to Disable</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a5eb4-114">Web 服务</span><span class="sxs-lookup"><span data-stu-id="a5eb4-114">Web Service</span></span></p></td>
<td><p><span data-ttu-id="a5eb4-115">Web 服务器</span><span class="sxs-lookup"><span data-stu-id="a5eb4-115">WebServer</span></span></p></td>
<td><p><span data-ttu-id="a5eb4-116">控制器</span><span class="sxs-lookup"><span data-stu-id="a5eb4-116">Director</span></span></p></td>
<td><p><span data-ttu-id="a5eb4-117">Kerberos、NTLM 和证书</span><span class="sxs-lookup"><span data-stu-id="a5eb4-117">Kerberos, NTLM, and Certificate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5eb4-118">Web 服务</span><span class="sxs-lookup"><span data-stu-id="a5eb4-118">Web Service</span></span></p></td>
<td><p><span data-ttu-id="a5eb4-119">Web 服务器</span><span class="sxs-lookup"><span data-stu-id="a5eb4-119">WebServer</span></span></p></td>
<td><p><span data-ttu-id="a5eb4-120">前端</span><span class="sxs-lookup"><span data-stu-id="a5eb4-120">Front End</span></span></p></td>
<td><p><span data-ttu-id="a5eb4-121">Kerberos、NTLM 和证书</span><span class="sxs-lookup"><span data-stu-id="a5eb4-121">Kerberos, NTLM, and Certificate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5eb4-122">代理</span><span class="sxs-lookup"><span data-stu-id="a5eb4-122">Proxy</span></span></p></td>
<td><p><span data-ttu-id="a5eb4-123">EdgeServer</span><span class="sxs-lookup"><span data-stu-id="a5eb4-123">EdgeServer</span></span></p></td>
<td><p><span data-ttu-id="a5eb4-124">Edge</span><span class="sxs-lookup"><span data-stu-id="a5eb4-124">Edge</span></span></p></td>
<td><p><span data-ttu-id="a5eb4-125">Kerberos 和 NTLM</span><span class="sxs-lookup"><span data-stu-id="a5eb4-125">Kerberos and NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5eb4-126">代理</span><span class="sxs-lookup"><span data-stu-id="a5eb4-126">Proxy</span></span></p></td>
<td><p><span data-ttu-id="a5eb4-127">注册器</span><span class="sxs-lookup"><span data-stu-id="a5eb4-127">Registrar</span></span></p></td>
<td><p><span data-ttu-id="a5eb4-128">前端</span><span class="sxs-lookup"><span data-stu-id="a5eb4-128">Front End</span></span></p></td>
<td><p><span data-ttu-id="a5eb4-129">Kerberos 和 NTLM</span><span class="sxs-lookup"><span data-stu-id="a5eb4-129">Kerberos and NTLM</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a5eb4-130">除非在服务级别禁用这些身份验证类型，否则在你的部署中启用了两个因素身份验证后，Lync 客户端的所有其他版本都将无法成功登录。</span><span class="sxs-lookup"><span data-stu-id="a5eb4-130">Unless these authentication types are disabled at the service level, all other versions of the Lync client will be unable to sign in successfully once two-factor authentication is enabled within in your deployment.</span></span>

</div>

<div>

## <a name="lync-service-discovery"></a><span data-ttu-id="a5eb4-131">Lync 服务发现</span><span class="sxs-lookup"><span data-stu-id="a5eb4-131">Lync Service Discovery</span></span>

<span data-ttu-id="a5eb4-132">内部和/或外部客户端用于发现 Lync 服务的 DNS 记录应配置为解析为未启用双因素身份验证的 Lync 服务器。</span><span class="sxs-lookup"><span data-stu-id="a5eb4-132">DNS records used by internal and/or external clients to discover Lync services should be configured to resolve to a Lync server that is not enabled for two-factor authentication.</span></span> <span data-ttu-id="a5eb4-133">通过此配置，没有为两个因素身份验证启用的 Lync Pool 中的用户输入 PIN 进行身份验证时，不需要使用适用于双因素身份验证的 Lync Pool 中的用户将其 PIN 输入到验证.</span><span class="sxs-lookup"><span data-stu-id="a5eb4-133">With this configuration, users from Lync Pools that are not enabled for two-factor authentication will not be required to enter a PIN to authenticate, while users from Lync Pools that are enabled for two-factor authentication will be required to enter their PIN to authenticate.</span></span>

</div>

<div>

## <a name="exchange-authentication"></a><span data-ttu-id="a5eb4-134">Exchange 身份验证</span><span class="sxs-lookup"><span data-stu-id="a5eb4-134">Exchange Authentication</span></span>

<span data-ttu-id="a5eb4-135">已为 Microsoft Exchange 部署了双因素身份验证的客户可能会发现 Lync 客户端中的某些功能不可用。</span><span class="sxs-lookup"><span data-stu-id="a5eb4-135">Customers who have deployed two-factor authentication for Microsoft Exchange may find that certain features in the Lync client are unavailable.</span></span> <span data-ttu-id="a5eb4-136">这是当前设计的，因为 Lync 客户端不支持依赖于 Exchange 集成的功能的双重身份验证。</span><span class="sxs-lookup"><span data-stu-id="a5eb4-136">This is currently by design, as the Lync client does not support two-factor authentication for features that are dependent on Exchange integration.</span></span>

</div>

<div>

## <a name="lync-contacts"></a><span data-ttu-id="a5eb4-137">Lync 联系人</span><span class="sxs-lookup"><span data-stu-id="a5eb4-137">Lync Contacts</span></span>

<span data-ttu-id="a5eb4-138">配置为利用 "统一联系人存储" 功能的 Lync 用户将发现，使用双因素身份验证登录后，他们的联系人将不再可用。</span><span class="sxs-lookup"><span data-stu-id="a5eb4-138">Lync users who are configured to leverage the Unified Contact Store feature will find that their contacts are no longer available after signing in with two-factor authentication.</span></span>

<span data-ttu-id="a5eb4-139">你应该使用**CsUcsRollback** cmdlet 从 "统一联系人存储" 中删除现有用户联系人，并将其存储在 Lync Server 2013 中，然后再启用双重身份验证。</span><span class="sxs-lookup"><span data-stu-id="a5eb4-139">You should use the **Invoke-CsUcsRollback** cmdlet to remove existing user contacts from the Unified Contact Store and store them in Lync Server 2013 before enabling two-factor authentication.</span></span>

</div>

<div>

## <a name="skill-search"></a><span data-ttu-id="a5eb4-140">技能搜索</span><span class="sxs-lookup"><span data-stu-id="a5eb4-140">Skill Search</span></span>

<span data-ttu-id="a5eb4-141">在 Lync 环境中配置技能搜索功能的客户将发现，当启用 Lync 的双重身份验证时，此功能不起作用。</span><span class="sxs-lookup"><span data-stu-id="a5eb4-141">Customers who have configured the Skill Search feature in their Lync environment will find that this feature does not work when Lync is enabled for two-factor authentication.</span></span> <span data-ttu-id="a5eb4-142">这是设计使然，因为 Microsoft SharePoint 当前不支持双重身份验证。</span><span class="sxs-lookup"><span data-stu-id="a5eb4-142">This is by design, as Microsoft SharePoint does not currently support two-factor authentication.</span></span>

</div>

<div>

## <a name="lync-credentials"></a><span data-ttu-id="a5eb4-143">Lync 凭据</span><span class="sxs-lookup"><span data-stu-id="a5eb4-143">Lync Credentials</span></span>

<span data-ttu-id="a5eb4-144">有许多部署注意事项涉及保存的 Lync 凭据，这可能会影响配置为使用双因素身份验证的用户。</span><span class="sxs-lookup"><span data-stu-id="a5eb4-144">There are a number of deployment considerations involving saved Lync credentials which may impact users who are configured to use two-factor authentication.</span></span>

<div>

## <a name="deleting-saved-credentials"></a><span data-ttu-id="a5eb4-145">删除保存的凭据</span><span class="sxs-lookup"><span data-stu-id="a5eb4-145">Deleting Saved Credentials</span></span>

<span data-ttu-id="a5eb4-146">桌面客户端用户应使用 Lync 客户端中的 "**删除我的登录信息**" 选项，并从% localappdata\\% Microsoft\\Office\\15.0\\Lync 删除其 SIP 配置文件，然后再尝试使用双因素身份验证进行首次登录。</span><span class="sxs-lookup"><span data-stu-id="a5eb4-146">Desktop client users should use the **Delete my sign-in info** option in the Lync client and delete their SIP profile folder from %localappdata%\\Microsoft\\Office\\15.0\\Lync before attempting to sign for the first time using two-factor authentication.</span></span>

</div>

<div>

## <a name="disablentcredentials"></a><span data-ttu-id="a5eb4-147">DisableNTCredentials</span><span class="sxs-lookup"><span data-stu-id="a5eb4-147">DisableNTCredentials</span></span>

<span data-ttu-id="a5eb4-148">使用 Kerberos 或 NTLM 身份验证方法时，将自动使用用户的 Windows 凭据进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="a5eb4-148">With the Kerberos or NTLM authentication method, the user’s Windows credentials are used automatically for authentication.</span></span> <span data-ttu-id="a5eb4-149">在支持 Kerberos 和/或 NTLM 进行身份验证的典型 Lync Server 2013 部署中，用户每次登录时都不应输入其凭据。</span><span class="sxs-lookup"><span data-stu-id="a5eb4-149">In a typical Lync Server 2013 deployment where Kerberos and/or NTLM is enabled for authentication, users should not have to enter their credentials every time that they sign in.</span></span>

<span data-ttu-id="a5eb4-150">如果在提示用户输入其 PIN 之前无意中提示用户输入凭据，则可能通过组策略在客户端计算机上无意中配置了 **DisableNTCredentials** 注册表项。</span><span class="sxs-lookup"><span data-stu-id="a5eb4-150">If users are unintentionally prompted for credentials before they are prompted to enter their PIN, the **DisableNTCredentials** registry key may be unintentionally configured on client computers, possibly through Group Policy.</span></span>

<span data-ttu-id="a5eb4-151">若要阻止额外的凭据提示，请在本地工作站上创建以下注册表项，或使用 Lync 管理模板应用到使用组策略的给定池的所有用户：</span><span class="sxs-lookup"><span data-stu-id="a5eb4-151">To prevent the additional prompt for credentials, create the following registry entry on the local workstation or use the Lync administrative template to apply to all users for a given pool using Group Policy:</span></span>

<span data-ttu-id="a5eb4-152">HKEY\_LOCAL\_MACHINE\\软件\\策略\\Microsoft\\Office\\15.0\\Lync</span><span class="sxs-lookup"><span data-stu-id="a5eb4-152">HKEY\_LOCAL\_MACHINE\\Software\\Policies\\Microsoft\\Office\\15.0\\Lync</span></span>

<span data-ttu-id="a5eb4-153">REG\_DWORD： DisableNTCredentials</span><span class="sxs-lookup"><span data-stu-id="a5eb4-153">REG\_DWORD: DisableNTCredentials</span></span>

<span data-ttu-id="a5eb4-154">值：0x0</span><span class="sxs-lookup"><span data-stu-id="a5eb4-154">Value: 0x0</span></span>

</div>

<div>

## <a name="savepassword"></a><span data-ttu-id="a5eb4-155">SavePassword</span><span class="sxs-lookup"><span data-stu-id="a5eb4-155">SavePassword</span></span>

<span data-ttu-id="a5eb4-156">当用户首次登录 Lync 时，系统会提示用户保存其密码。</span><span class="sxs-lookup"><span data-stu-id="a5eb4-156">When a user signs in to Lync for the first time, the user is prompted to save his or her password.</span></span> <span data-ttu-id="a5eb4-157">如果选中，此选项允许用户的客户端证书存储在个人证书存储中，而用户的 Windows 凭据存储在本地计算机的凭据管理器中。</span><span class="sxs-lookup"><span data-stu-id="a5eb4-157">If selected, this option allows the user’s client certificate to be stored in the personal certificate store and the user’s Windows credentials to be stored in the Credential Manager of the local computer.</span></span>

<span data-ttu-id="a5eb4-158">当 Lync 配置为支持双因素身份验证时，应禁用**SavePassword**注册表设置。</span><span class="sxs-lookup"><span data-stu-id="a5eb4-158">The **SavePassword** registry setting should be disabled when Lync is configured to support two-factor authentication.</span></span> <span data-ttu-id="a5eb4-159">若要防止用户保存其密码，请在本地工作站上更改以下注册表项，或使用 Lync 管理模板应用到使用组策略的给定池的所有用户：</span><span class="sxs-lookup"><span data-stu-id="a5eb4-159">To prevent users from saving their passwords, change the following registry entry on the local workstation or use the Lync administrative template to apply to all users for a given pool using Group Policy:</span></span>

<span data-ttu-id="a5eb4-160">HKEY\_当前\_用户\\软件\\Microsoft\\Office\\15.0\\Lync</span><span class="sxs-lookup"><span data-stu-id="a5eb4-160">HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync</span></span>

<span data-ttu-id="a5eb4-161">REG\_DWORD： SavePassword</span><span class="sxs-lookup"><span data-stu-id="a5eb4-161">REG\_DWORD: SavePassword</span></span>

<span data-ttu-id="a5eb4-162">值：0x0</span><span class="sxs-lookup"><span data-stu-id="a5eb4-162">Value: 0x0</span></span>

</div>

</div>

<div>

## <a name="ad-fs-20-token-replay"></a><span data-ttu-id="a5eb4-163">AD FS 2.0 令牌重播</span><span class="sxs-lookup"><span data-stu-id="a5eb4-163">AD FS 2.0 Token Replay</span></span>

<span data-ttu-id="a5eb4-p108">AD FS 2.0 提供了一项功能称为“令牌重播检测”，借助该功能，可以检测并丢弃多个使用相同令牌的令牌请求。启用此功能时，令牌重播检测可确保从不多次使用相同令牌，从而保护 WS 联合被动配置文件和 SAML WebSSO 配置文件中身份验证请求的完整性。</span><span class="sxs-lookup"><span data-stu-id="a5eb4-p108">AD FS 2.0 provides a feature referred to as token replay detection, by which multiple token requests using the same token can be detected and then discarded. When this feature is enabled, token replay detection protects the integrity of authentication requests in both the WS-Federation passive profile and the SAML WebSSO profile by making sure that the same token is never used more than once.</span></span>

<span data-ttu-id="a5eb4-166">在高度关注安全的环境（例如使用展台时）中，应启用此功能。</span><span class="sxs-lookup"><span data-stu-id="a5eb4-166">This feature should be enabled in situations where security is a very high concern such as when using kiosks.</span></span> <span data-ttu-id="a5eb4-167">有关令牌重播检测的详细信息，请参阅 "安全规划和部署 AD FS 2.0 的最佳做法[http://go.microsoft.com/fwlink/p/?LinkId=309215](http://go.microsoft.com/fwlink/p/?linkid=309215)"。</span><span class="sxs-lookup"><span data-stu-id="a5eb4-167">For more information about token replay detection, see Best Practices for Secure Planning and Deployment of AD FS 2.0 at [http://go.microsoft.com/fwlink/p/?LinkId=309215](http://go.microsoft.com/fwlink/p/?linkid=309215).</span></span>

</div>

<div>

## <a name="external-user-access"></a><span data-ttu-id="a5eb4-168">外部用户访问</span><span class="sxs-lookup"><span data-stu-id="a5eb4-168">External User Access</span></span>

<span data-ttu-id="a5eb4-169">在这些主题中不涉及配置 AD FS 代理或反向代理以支持来自外部网络的 Lync 双重身份验证。</span><span class="sxs-lookup"><span data-stu-id="a5eb4-169">Configuring an AD FS Proxy or Reverse Proxy to support Lync two-factor authentication from external networks is not covered in these topics.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

