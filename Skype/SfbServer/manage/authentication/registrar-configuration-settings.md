---
title: 在 Skype for Business Server 中管理注册器配置设置
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eddfbdd2-cfd0-4c03-986e-443d6728db7d
description: 摘要：管理 Skype for Business Server 的注册器配置设置。
ms.openlocfilehash: 9a56e803470054ab8c2ba3cf9e2c758d4e71e17a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828322"
---
# <a name="manage-registrar-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="52348-103">在 Skype for Business Server 中管理注册器配置设置</span><span class="sxs-lookup"><span data-stu-id="52348-103">Manage Registrar configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="52348-104">**摘要：** 管理 Skype for Business Server 的注册器配置设置。</span><span class="sxs-lookup"><span data-stu-id="52348-104">**Summary:** Manage Registrar configuration settings for Skype for Business Server.</span></span>
  
<span data-ttu-id="52348-p101">可以使用注册器配置代理服务器身份验证方法。指定的身份验证协议确定池中的服务器向客户端发出的质询类型。可以选择以下协议：</span><span class="sxs-lookup"><span data-stu-id="52348-p101">You can use the Registrar to configure proxy server authentication methods. The authentication protocol you specify determines which type of challenges the servers in the pool issue to clients. The available protocols are:</span></span>
  
- <span data-ttu-id="52348-108">**Kerberos** 这是可供客户端使用的最强基于密码的身份验证方案，但它通常仅适用于企业客户端，因为它需要客户端连接到密钥发行中心 (Kerberos 域控制器) 。</span><span class="sxs-lookup"><span data-stu-id="52348-108">**Kerberos** This is the strongest password-based authentication scheme available to clients, but it is normally available only to enterprise clients because it requires client connection to a Key Distribution Center (Kerberos domain controller).</span></span> <span data-ttu-id="52348-109">如果服务器仅对企业客户端进行身份验证，则此设置适用。</span><span class="sxs-lookup"><span data-stu-id="52348-109">This setting is appropriate if the server authenticates only enterprise clients.</span></span>
    
- <span data-ttu-id="52348-110">**NTLM** 这是对密码使用质询响应哈希方案客户端可用的基于密码的身份验证。</span><span class="sxs-lookup"><span data-stu-id="52348-110">**NTLM** This is the password-based authentication available to clients that use a challenge-response hashing scheme on the password.</span></span> <span data-ttu-id="52348-111">这是对没有连接到 Kerberos 域控制器的密钥发行中心 (客户端（如远程用户) 身份验证的唯一形式。</span><span class="sxs-lookup"><span data-stu-id="52348-111">This is the only form of authentication available to clients without connectivity to a Key Distribution Center (Kerberos domain controller), such as remote users.</span></span> <span data-ttu-id="52348-112">如果服务器仅对远程用户进行身份验证，则应该选择 NTLM。</span><span class="sxs-lookup"><span data-stu-id="52348-112">If a server authenticates only remote users, you should choose NTLM.</span></span>
    
- <span data-ttu-id="52348-113">**证书身份验证** 这是服务器需要从 Lync Phone Edition 客户端、公用区域电话、Skype for Business 和 Lync Windows 应用商店应用获取证书时的新身份验证方法。</span><span class="sxs-lookup"><span data-stu-id="52348-113">**Certificate authentication** This is the new authentication method when the server needs to obtain certificates from Lync Phone Edition clients, common area phones, Skype for Business and the Lync Windows Store app.</span></span> <span data-ttu-id="52348-114">在 Lync Phone Edition 客户端上，在用户登录并且通过提供个人标识号 (PIN) 成功进行身份验证后，Skype for Business Server 随后会设置电话的 SIP URI，并设置 Skype for Business Server 签名证书或标识 Joe (（例如：SN=joe@contoso.com ) ）的用户证书。</span><span class="sxs-lookup"><span data-stu-id="52348-114">On Lync Phone Edition clients, after a user signs in and is successfully authenticated by providing a personal identification number (PIN), Skype for Business Server then provisions the SIP URI to the phone and provisions a Skype for Business Server signed certificate or a user certificate that identifies Joe (Ex: SN=joe@contoso.com ) to the phone.</span></span> <span data-ttu-id="52348-115">此证书用于向注册机构及 Web 服务进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="52348-115">This certificate is used for authenticating with the Registrar and Web Services.</span></span>
    
> [!NOTE]
> <span data-ttu-id="52348-p105">如果服务器支持对远程客户端和企业客户端进行身份验证，我们建议您同时启用 Kerberos 和 NTLM。边缘服务器与内部服务器通信，以确保只向远程客户端提供 NTLM 身份验证。如果在这些服务器上只启用 Kerberos，则无法对远程用户进行身份验证。如果该服务器也对企业用户进行身份验证，则会使用 Kerberos。</span><span class="sxs-lookup"><span data-stu-id="52348-p105">We recommend that you enable both Kerberos and NTLM when a server supports authentication for both remote and enterprise clients. The Edge Server and internal servers communicate to ensure that only NTLM authentication is offered to remote clients. If only Kerberos is enabled on these servers, they cannot authenticate remote users. If enterprise users also authenticate against the server, Kerberos is used.</span></span> 
  
<span data-ttu-id="52348-120">如果使用 Lync Windows 应用商店应用客户端，则必须启用证书身份验证。</span><span class="sxs-lookup"><span data-stu-id="52348-120">If you will use Lync Windows Store app clients, you must enable certificate authentication.</span></span>
  
### <a name="to-create-new-registrar-configuration-settings"></a><span data-ttu-id="52348-121">创建新的注册器配置设置</span><span class="sxs-lookup"><span data-stu-id="52348-121">To create new Registrar configuration settings</span></span>

1.  <span data-ttu-id="52348-122">从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到部署 Skype for Business Server 的网络内的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="52348-122">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="52348-123">打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="52348-123">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="52348-124">在左侧导航栏中，单击“安全性”，然后单击“注册器”。</span><span class="sxs-lookup"><span data-stu-id="52348-124">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>
    
4. <span data-ttu-id="52348-125">在“注册器”页上，单击“新建”。</span><span class="sxs-lookup"><span data-stu-id="52348-125">On the **Registrar** page, click **New**</span></span>
    
5. <span data-ttu-id="52348-126">在“选择服务”中，单击将应用此注册器的服务，然后单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="52348-126">In **Select a Service**, click the service to which the Registrar is to be applied and then click **OK**.</span></span>
    
6. <span data-ttu-id="52348-127">在“新建注册器设置”中，根据客户端的功能和环境支持，选择下列一项或多项：</span><span class="sxs-lookup"><span data-stu-id="52348-127">In **New Registrar Setting**, select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
   - <span data-ttu-id="52348-128">**启用 Kerberos 身份验证**，可使池中的服务器使用 Kerberos 身份验证发出质询。</span><span class="sxs-lookup"><span data-stu-id="52348-128">**Enable Kerberos authentication** to have the servers in the pool issue challenges using Kerberos authentication.</span></span>
    
   - <span data-ttu-id="52348-129">**启用 NTLM 身份验证**，可使池中的服务器使用 NTLM 发出质询。</span><span class="sxs-lookup"><span data-stu-id="52348-129">**Enable NTLM authentication** to have the servers in the pool issue challenges using NTLM.</span></span>
    
   - <span data-ttu-id="52348-130">**启用证书身份验证**，可使池中的服务器向客户端颁发证书。</span><span class="sxs-lookup"><span data-stu-id="52348-130">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
7. <span data-ttu-id="52348-131">单击“提交”。</span><span class="sxs-lookup"><span data-stu-id="52348-131">Click **Commit**.</span></span>
    
## <a name="modify-existing-registrar-configuration-settings"></a><span data-ttu-id="52348-132">修改现有注册器配置设置</span><span class="sxs-lookup"><span data-stu-id="52348-132">Modify existing Registrar configuration settings</span></span>

<span data-ttu-id="52348-133">可以使用注册器配置代理服务器身份验证协议。</span><span class="sxs-lookup"><span data-stu-id="52348-133">You can use the Registrar to configure proxy server authentication protocols.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="52348-p106">如果服务器支持对远程客户端和企业客户端进行身份验证，我们建议您同时启用 Kerberos 和 NTLM。边缘服务器与内部服务器通信，以确保只向远程客户端提供 NTLM 身份验证。如果在这些服务器上只启用 Kerberos，则无法对远程用户进行身份验证。如果该服务器也对企业用户进行身份验证，则会使用 Kerberos。</span><span class="sxs-lookup"><span data-stu-id="52348-p106">We recommend that you enable both Kerberos and NTLM when a server supports authentication for both remote and enterprise clients. The Edge Server and internal servers communicate to ensure that only NTLM authentication is offered to remote clients. If only Kerberos is enabled on these servers, they cannot authenticate remote users. If enterprise users also authenticate against the server, Kerberos is used.</span></span> 
  
<span data-ttu-id="52348-138">按照以下步骤修改现有注册器。</span><span class="sxs-lookup"><span data-stu-id="52348-138">Follow these steps to modify an existing Registrar.</span></span> 
  
### <a name="to-modify-existing-registrar-configuration-settings"></a><span data-ttu-id="52348-139">修改现有注册器配置设置</span><span class="sxs-lookup"><span data-stu-id="52348-139">To modify existing registrar configuration settings</span></span>

1.  <span data-ttu-id="52348-140">从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到部署 Skype for Business Server 的网络内的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="52348-140">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="52348-141">打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="52348-141">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="52348-142">在左侧导航栏中，单击“安全性”，然后单击“注册器”。</span><span class="sxs-lookup"><span data-stu-id="52348-142">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>
    
4. <span data-ttu-id="52348-143">在注册 **器** 页上，单击某个 **服务，再** 单击"编辑"，然后单击"**显示详细信息"。**</span><span class="sxs-lookup"><span data-stu-id="52348-143">On the **Registrar** page, click a service, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="52348-144">在 **"** 编辑注册器设置"中，根据客户端的功能和环境支持，选择以下一个或多个选项：</span><span class="sxs-lookup"><span data-stu-id="52348-144">In **Edit Registrar Setting**, select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
   - <span data-ttu-id="52348-145">**启用 Kerberos 身份验证**，可使池中的服务器使用 Kerberos 身份验证发出质询。</span><span class="sxs-lookup"><span data-stu-id="52348-145">**Enable Kerberos authentication** to have the servers in the pool issue challenges using Kerberos authentication.</span></span>
    
   - <span data-ttu-id="52348-146">**启用 NTLM 身份验证**，可使池中的服务器使用 NTLM 发出质询。</span><span class="sxs-lookup"><span data-stu-id="52348-146">**Enable NTLM authentication** to have the servers in the pool issue challenges using NTLM.</span></span>
    
   - <span data-ttu-id="52348-147">**启用证书身份验证**，可使池中的服务器向客户端颁发证书。</span><span class="sxs-lookup"><span data-stu-id="52348-147">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
6. <span data-ttu-id="52348-148">单击“提交”。</span><span class="sxs-lookup"><span data-stu-id="52348-148">Click **Commit**.</span></span>
    
### <a name="to-delete-registrar-configuration-settings"></a><span data-ttu-id="52348-149">删除注册器配置设置</span><span class="sxs-lookup"><span data-stu-id="52348-149">To delete Registrar configuration settings</span></span>

1. <span data-ttu-id="52348-150">从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到部署 Skype for Business Server 的网络内的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="52348-150">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="52348-151">打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="52348-151">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="52348-152">在左侧导航栏中，单击“安全性”，然后单击“注册器”。</span><span class="sxs-lookup"><span data-stu-id="52348-152">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>
    
4. <span data-ttu-id="52348-153">在 **"注册** 器"页的搜索字段中，键入要删除的注册器的名称的全名或部分名称。</span><span class="sxs-lookup"><span data-stu-id="52348-153">On the **Registrar** page, and in the search field, type all or part of the name of the Registrar you want to delete.</span></span>
    
5. <span data-ttu-id="52348-154">在列表中，单击您想要的注册器 **，再单击**"编辑"，然后单击"删除 **"。**</span><span class="sxs-lookup"><span data-stu-id="52348-154">In the list, click the Registrar that you want, click **Edit**, and then click **Delete**.</span></span>
    
6. <span data-ttu-id="52348-155">单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="52348-155">Click **OK**.</span></span>
    
## <a name="removing-registrar-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="52348-156">使用 cmdlet 删除注册器Windows PowerShell设置</span><span class="sxs-lookup"><span data-stu-id="52348-156">Removing Registrar Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="52348-157">可以使用 Windows PowerShell 和 **Remove-CsProxyConfiguration** cmdlet 删除注册器配置设置。</span><span class="sxs-lookup"><span data-stu-id="52348-157">You can delete the Registrar configuration settings by using Windows PowerShell and the **Remove-CsProxyConfiguration** cmdlet.</span></span> <span data-ttu-id="52348-158">还可从 Skype for Business Server Management Shell 或 Windows PowerShell 远程会话运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="52348-158">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="52348-159">有关使用远程部署Windows PowerShell Skype for Business Server 的详细信息，请参阅博客文章"[快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。](https://go.microsoft.com/fwlink/p/?linkId=255876)</span><span class="sxs-lookup"><span data-stu-id="52348-159">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="52348-160">此过程在 Skype for Business Server 中相同。</span><span class="sxs-lookup"><span data-stu-id="52348-160">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-remove-a-specific-set-of-registrar-security-settings"></a><span data-ttu-id="52348-161">删除一组特定的注册器安全设置</span><span class="sxs-lookup"><span data-stu-id="52348-161">To remove a specific set of Registrar security settings</span></span>

- <span data-ttu-id="52348-162">以下命令删除应用于边缘服务器服务器的注册器atl-edge-011.litwareinc.com：</span><span class="sxs-lookup"><span data-stu-id="52348-162">The following command removes the Registrar security settings applied to the edge Server atl-edge-011.litwareinc.com:</span></span>
    
  ```PowerShell
  Remove-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-011.litwareinc.com
  ```

### <a name="to-remove-all-of-the-registrar-security-settings-applied-to-the-site-scope"></a><span data-ttu-id="52348-163">删除应用于站点范围的所有注册器安全设置</span><span class="sxs-lookup"><span data-stu-id="52348-163">To remove all of the Registrar security settings applied to the site scope</span></span>

- <span data-ttu-id="52348-164">以下命令删除应用于注册器服务的所有注册器安全设置：</span><span class="sxs-lookup"><span data-stu-id="52348-164">The following command removes all the Registrar security settings applied to the Registrar service:</span></span>
    
  ```PowerShell
  Get-CsProxyConfiguration -Filter "service:Registrar:*" | Remove-CsProxyConfiguration
  ```

### <a name="to-remove-all-of-the-registrar-security-settings-that-allow-ntlm-authentication"></a><span data-ttu-id="52348-165">删除允许 NTLM 身份验证的所有注册器安全设置</span><span class="sxs-lookup"><span data-stu-id="52348-165">To remove all of the Registrar security settings that allow NTLM authentication</span></span>

- <span data-ttu-id="52348-166">以下命令删除允许使用 NTLM 进行客户端身份验证的所有注册器安全设置：</span><span class="sxs-lookup"><span data-stu-id="52348-166">The following command deletes all the Registrar security settings that allow the use of NTLM for client authentication:</span></span>
    
  ```PowerShell
  Get-CsProxyConfiguration | Where-Object {$_.UseNtlmForClientToProxyAuth -eq $True}| Remove-CsProxyConfiguration
  ```

<span data-ttu-id="52348-167">有关详细信息，请参阅[Remove-CsProxyConfiguration。](https://docs.microsoft.com/powershell/module/skype/remove-csproxyconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="52348-167">For details, see [Remove-CsProxyConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csproxyconfiguration?view=skype-ps).</span></span>
  

