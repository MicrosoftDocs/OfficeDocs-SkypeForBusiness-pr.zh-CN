---
title: 在 Skype for Business Server 2015 中管理注册器配置设置
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eddfbdd2-cfd0-4c03-986e-443d6728db7d
description: 摘要： 管理业务服务器 2015 Skype 的注册器配置的设置。
ms.openlocfilehash: 5cdcf1cba045f5105b1f375fbcebb22b7b00a25d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="manage-registrar-configuration-settings-in-skype-for-business-server-2015"></a><span data-ttu-id="a5e03-103">在 Skype for Business Server 2015 中管理注册器配置设置</span><span class="sxs-lookup"><span data-stu-id="a5e03-103">Manage Registrar configuration settings in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="a5e03-104">**摘要：**管理业务服务器 2015年的 Skype 的注册器配置设置。</span><span class="sxs-lookup"><span data-stu-id="a5e03-104">**Summary:** Manage Registrar configuration settings for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="a5e03-p101">可以使用注册器配置代理服务器身份验证方法。指定的身份验证协议确定池中的服务器向客户端发出的质询类型。可以选择以下协议：</span><span class="sxs-lookup"><span data-stu-id="a5e03-p101">You can use the Registrar to configure proxy server authentication methods. The authentication protocol you specify determines which type of challenges the servers in the pool issue to clients. The available protocols are:</span></span>
  
- <span data-ttu-id="a5e03-108">**Kerberos**这是最强大的基于密码的身份验证方案可用于客户端，但它是通常仅适用于企业客户端的因为它要求客户端连接到密钥发行中心 （Kerberos 域控制器）。</span><span class="sxs-lookup"><span data-stu-id="a5e03-108">**Kerberos** This is the strongest password-based authentication scheme available to clients, but it is normally available only to enterprise clients because it requires client connection to a Key Distribution Center (Kerberos domain controller).</span></span> <span data-ttu-id="a5e03-109">如果服务器仅验证企业客户端的身份，则此设置适用。</span><span class="sxs-lookup"><span data-stu-id="a5e03-109">This setting is appropriate if the server authenticates only enterprise clients.</span></span>
    
- <span data-ttu-id="a5e03-110">**NTLM**这是基于密码的身份验证可用于对密码使用质询响应哈希方案的客户端。</span><span class="sxs-lookup"><span data-stu-id="a5e03-110">**NTLM** This is the password-based authentication available to clients that use a challenge-response hashing scheme on the password.</span></span> <span data-ttu-id="a5e03-111">对于无法连接到密钥发行中心（Kerberos 域控制器）的客户端（例如，远程用户），这是唯一可用的身份验证方案。</span><span class="sxs-lookup"><span data-stu-id="a5e03-111">This is the only form of authentication available to clients without connectivity to a Key Distribution Center (Kerberos domain controller), such as remote users.</span></span> <span data-ttu-id="a5e03-112">如果服务器仅验证远程用户的身份，则应选择 NTLM。</span><span class="sxs-lookup"><span data-stu-id="a5e03-112">If a server authenticates only remote users, you should choose NTLM.</span></span>
    
- <span data-ttu-id="a5e03-113">**证书身份验证**当服务器需要从电话版 Lync 客户端、 公共区域电话、 Skype 业务和 Lync Windows 应用商店应用程序获取证书，这是新的身份验证方法。</span><span class="sxs-lookup"><span data-stu-id="a5e03-113">**Certificate authentication** This is the new authentication method when the server needs to obtain certificates from Lync Phone Edition clients, common area phones, Skype for Business and the Lync Windows Store app.</span></span> <span data-ttu-id="a5e03-114">Lync 电话版客户端，用户登录并验证成功通过提供个人身份验证号码 (PIN)，Skype 的业务服务器 2015年然后提供 SIP URI 的移动电话和 Skype 做好业务服务器签名后上证书或用户证书标识乔 (Ex: SN=joe@contoso.com) 的移动电话。</span><span class="sxs-lookup"><span data-stu-id="a5e03-114">On Lync Phone Edition clients, after a user signs in and is successfully authenticated by providing a personal identification number (PIN), Skype for Business Server 2015 then provisions the SIP URI to the phone and provisions a Skype for Business Server signed certificate or a user certificate that identifies Joe (Ex: SN=joe@contoso.com ) to the phone.</span></span> <span data-ttu-id="a5e03-115">此证书用于使用注册器和 Web 服务进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="a5e03-115">This certificate is used for authenticating with the Registrar and Web Services.</span></span>
    
> [!NOTE]
> <span data-ttu-id="a5e03-p105">如果服务器支持对远程客户端和企业客户端进行身份验证，我们建议您同时启用 Kerberos 和 NTLM。边缘服务器与内部服务器通信，以确保只向远程客户端提供 NTLM 身份验证。如果在这些服务器上只启用 Kerberos，则无法对远程用户进行身份验证。如果该服务器也对企业用户进行身份验证，则会使用 Kerberos。</span><span class="sxs-lookup"><span data-stu-id="a5e03-p105">We recommend that you enable both Kerberos and NTLM when a server supports authentication for both remote and enterprise clients. The Edge Server and internal servers communicate to ensure that only NTLM authentication is offered to remote clients. If only Kerberos is enabled on these servers, they cannot authenticate remote users. If enterprise users also authenticate against the server, Kerberos is used.</span></span> 
  
<span data-ttu-id="a5e03-120">如果您将使用 Lync Windows 应用商店应用程序客户端，您必须启用证书身份验证。</span><span class="sxs-lookup"><span data-stu-id="a5e03-120">If you will use Lync Windows Store app clients, you must enable certificate authentication.</span></span>
  
### <a name="to-create-new-registrar-configuration-settings"></a><span data-ttu-id="a5e03-121">创建新的注册器配置设置</span><span class="sxs-lookup"><span data-stu-id="a5e03-121">To create new Registrar configuration settings</span></span>

1.  <span data-ttu-id="a5e03-122">从一个用户帐户，是 RTCUniversalServerAdmins 组的成员 （或具有相当的用户的权限），或者是指派到 CsServerAdministrator 或 CsAdministrator 的角色，在其中您部署 Skype 业务服务器的网络中任何计算机的登录2015。</span><span class="sxs-lookup"><span data-stu-id="a5e03-122">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2015.</span></span>
    
2. <span data-ttu-id="a5e03-123">打开浏览器窗口，然后输入管理员 URL 打开 Skype 业务服务器控件面板。</span><span class="sxs-lookup"><span data-stu-id="a5e03-123">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="a5e03-124">在左侧导航栏中，单击“安全性”****，然后单击“注册器”****。</span><span class="sxs-lookup"><span data-stu-id="a5e03-124">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>
    
4. <span data-ttu-id="a5e03-125">在“注册器”****页上，单击“新建”****。</span><span class="sxs-lookup"><span data-stu-id="a5e03-125">On the **Registrar** page, click **New**</span></span>
    
5. <span data-ttu-id="a5e03-126">在“选择服务”****中，单击将应用此注册器的服务，然后单击“确定”****。</span><span class="sxs-lookup"><span data-stu-id="a5e03-126">In **Select a Service**, click the service to which the Registrar is to be applied and then click **OK**.</span></span>
    
6. <span data-ttu-id="a5e03-127">在“新建注册器设置”****中，根据客户端的功能和环境支持，选择下列一项或多项：</span><span class="sxs-lookup"><span data-stu-id="a5e03-127">In **New Registrar Setting**, select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
   - <span data-ttu-id="a5e03-128">**启用 Kerberos 身份验证**，可使池中的服务器使用 Kerberos 身份验证发出质询。</span><span class="sxs-lookup"><span data-stu-id="a5e03-128">**Enable Kerberos authentication** to have the servers in the pool issue challenges using Kerberos authentication.</span></span>
    
   - <span data-ttu-id="a5e03-129">**启用 NTLM 身份验证**，可使池中的服务器使用 NTLM 发出质询。</span><span class="sxs-lookup"><span data-stu-id="a5e03-129">**Enable NTLM authentication** to have the servers in the pool issue challenges using NTLM.</span></span>
    
   - <span data-ttu-id="a5e03-130">**启用证书身份验证**，可使池中的服务器向客户端颁发证书。</span><span class="sxs-lookup"><span data-stu-id="a5e03-130">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
7. <span data-ttu-id="a5e03-131">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="a5e03-131">Click **Commit**.</span></span>
    
## <a name="modify-existing-registrar-configuration-settings"></a><span data-ttu-id="a5e03-132">修改现有的注册器配置设置</span><span class="sxs-lookup"><span data-stu-id="a5e03-132">Modify existing Registrar configuration settings</span></span>

<span data-ttu-id="a5e03-133">可以使用注册器配置代理服务器身份验证协议。</span><span class="sxs-lookup"><span data-stu-id="a5e03-133">You can use the Registrar to configure proxy server authentication protocols.</span></span> <span data-ttu-id="a5e03-134">有关可用的协议的信息，请参阅[管理注册商 Skype 业务服务器 2015年的配置设置](registrar-configuration-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="a5e03-134">For information about the available protocols, see [Manage Registrar configuration settings in Skype for Business Server 2015](registrar-configuration-settings.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="a5e03-p107">如果服务器支持对远程客户端和企业客户端进行身份验证，我们建议您同时启用 Kerberos 和 NTLM。边缘服务器与内部服务器通信，以确保只向远程客户端提供 NTLM 身份验证。如果在这些服务器上只启用 Kerberos，则无法对远程用户进行身份验证。如果该服务器也对企业用户进行身份验证，则会使用 Kerberos。</span><span class="sxs-lookup"><span data-stu-id="a5e03-p107">We recommend that you enable both Kerberos and NTLM when a server supports authentication for both remote and enterprise clients. The Edge Server and internal servers communicate to ensure that only NTLM authentication is offered to remote clients. If only Kerberos is enabled on these servers, they cannot authenticate remote users. If enterprise users also authenticate against the server, Kerberos is used.</span></span> 
  
<span data-ttu-id="a5e03-139">按照以下步骤修改现有的注册器。</span><span class="sxs-lookup"><span data-stu-id="a5e03-139">Follow these steps to modify an existing Registrar.</span></span> 
  
### <a name="to-modify-existing-registrar-configuration-settings"></a><span data-ttu-id="a5e03-140">修改现有的注册器配置设置</span><span class="sxs-lookup"><span data-stu-id="a5e03-140">To modify existing registrar configuration settings</span></span>

1.  <span data-ttu-id="a5e03-141">从一个用户帐户，是 RTCUniversalServerAdmins 组的成员 （或具有相当的用户的权限），或者是指派到 CsServerAdministrator 或 CsAdministrator 的角色，在其中您部署 Skype 业务服务器的网络中任何计算机的登录2015。</span><span class="sxs-lookup"><span data-stu-id="a5e03-141">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2015.</span></span>
    
2. <span data-ttu-id="a5e03-142">打开浏览器窗口，然后输入管理员 URL 打开 Skype 业务服务器控件面板。</span><span class="sxs-lookup"><span data-stu-id="a5e03-142">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="a5e03-143">在左侧导航栏中，单击“安全性”****，然后单击“注册器”****。</span><span class="sxs-lookup"><span data-stu-id="a5e03-143">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>
    
4. <span data-ttu-id="a5e03-144">在“注册器”****页上，单击某个服务，再单击“编辑”****，然后单击“显示详细信息”****。</span><span class="sxs-lookup"><span data-stu-id="a5e03-144">On the **Registrar** page, click a service, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="a5e03-145">在“编辑注册器设置”****中，根据环境中的客户端功能和支持情况，选择下列一项或多项：</span><span class="sxs-lookup"><span data-stu-id="a5e03-145">In **Edit Registrar Setting**, select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
   - <span data-ttu-id="a5e03-146">**启用 Kerberos 身份验证**，可使池中的服务器使用 Kerberos 身份验证发出质询。</span><span class="sxs-lookup"><span data-stu-id="a5e03-146">**Enable Kerberos authentication** to have the servers in the pool issue challenges using Kerberos authentication.</span></span>
    
   - <span data-ttu-id="a5e03-147">**启用 NTLM 身份验证**，可使池中的服务器使用 NTLM 发出质询。</span><span class="sxs-lookup"><span data-stu-id="a5e03-147">**Enable NTLM authentication** to have the servers in the pool issue challenges using NTLM.</span></span>
    
   - <span data-ttu-id="a5e03-148">**启用证书身份验证**，可使池中的服务器向客户端颁发证书。</span><span class="sxs-lookup"><span data-stu-id="a5e03-148">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
6. <span data-ttu-id="a5e03-149">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="a5e03-149">Click **Commit**.</span></span>
    
### <a name="to-delete-registrar-configuration-settings"></a><span data-ttu-id="a5e03-150">删除现有注册器配置设置</span><span class="sxs-lookup"><span data-stu-id="a5e03-150">To delete Registrar configuration settings</span></span>

1. <span data-ttu-id="a5e03-151">从一个用户帐户，是 RTCUniversalServerAdmins 组的成员 （或具有相当的用户的权限），或者是指派到 CsServerAdministrator 或 CsAdministrator 的角色，在其中您部署 Skype 业务服务器的网络中任何计算机的登录2015。</span><span class="sxs-lookup"><span data-stu-id="a5e03-151">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2015.</span></span>
    
2. <span data-ttu-id="a5e03-152">打开浏览器窗口，然后输入管理员 URL 打开 Skype 业务服务器控件面板。</span><span class="sxs-lookup"><span data-stu-id="a5e03-152">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="a5e03-153">在左侧导航栏中，单击“安全性”****，然后单击“注册器”****。</span><span class="sxs-lookup"><span data-stu-id="a5e03-153">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>
    
4. <span data-ttu-id="a5e03-154">在“注册器”****页上的搜索字段中，键入要删除的注册器的全部或部分名称。</span><span class="sxs-lookup"><span data-stu-id="a5e03-154">On the **Registrar** page, and in the search field, type all or part of the name of the Registrar you want to delete.</span></span>
    
5. <span data-ttu-id="a5e03-155">在列表中，单击所需的注册器，再单击“编辑”****，然后单击“删除”****。</span><span class="sxs-lookup"><span data-stu-id="a5e03-155">In the list, click the Registrar that you want, click **Edit**, and then click **Delete**.</span></span>
    
6. <span data-ttu-id="a5e03-156">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="a5e03-156">Click **OK**.</span></span>
    
## <a name="removing-registrar-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="a5e03-157">通过使用 Windows PowerShell Cmdlet 删除注册配置设置</span><span class="sxs-lookup"><span data-stu-id="a5e03-157">Removing Registrar Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="a5e03-158">通过使用 Windows PowerShell 和**删除 CsProxyConfiguration** cmdlet，您可以删除注册配置设置。</span><span class="sxs-lookup"><span data-stu-id="a5e03-158">You can delete the Registrar configuration settings by using Windows PowerShell and the **Remove-CsProxyConfiguration** cmdlet.</span></span> <span data-ttu-id="a5e03-159">从业务服务器管理外壳的 Skype 或 Windows PowerShell 的远程会话，您可以运行该 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a5e03-159">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="a5e03-160">有关使用远程 Windows PowerShell Skype 业务服务器的连接的详细信息，请参阅博客文章["快速启动:: 管理 Microsoft Lync 服务器 2010年使用远程 PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876)。</span><span class="sxs-lookup"><span data-stu-id="a5e03-160">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="a5e03-161">该过程是相同的 Skype 业务服务器。</span><span class="sxs-lookup"><span data-stu-id="a5e03-161">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-remove-a-specific-set-of-registrar-security-settings"></a><span data-ttu-id="a5e03-162">删除一组特定的注册器安全设置</span><span class="sxs-lookup"><span data-stu-id="a5e03-162">To remove a specific set of Registrar security settings</span></span>

- <span data-ttu-id="a5e03-163">以下命令会删除应用到边缘服务器 atl-edge-011.litwareinc.com 的注册器安全设置：</span><span class="sxs-lookup"><span data-stu-id="a5e03-163">The following command removes the Registrar security settings applied to the edge Server atl-edge-011.litwareinc.com:</span></span>
    
  ```
  Remove-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-011.litwareinc.com
  ```

### <a name="to-remove-all-of-the-registrar-security-settings-applied-to-the-site-scope"></a><span data-ttu-id="a5e03-164">删除应用到站点范围的所有注册器安全设置</span><span class="sxs-lookup"><span data-stu-id="a5e03-164">To remove all of the Registrar security settings applied to the site scope</span></span>

- <span data-ttu-id="a5e03-165">以下命令会删除应用到注册器服务的所有注册器安全设置：</span><span class="sxs-lookup"><span data-stu-id="a5e03-165">The following command removes all the Registrar security settings applied to the Registrar service:</span></span>
    
  ```
  Get-CsProxyConfiguration -Filter "service:Registrar:*" | Remove-CsProxyConfiguration
  ```

### <a name="to-remove-all-of-the-registrar-security-settings-that-allow-ntlm-authentication"></a><span data-ttu-id="a5e03-166">删除允许 NTLM 身份验证的所有注册器安全设置</span><span class="sxs-lookup"><span data-stu-id="a5e03-166">To remove all of the Registrar security settings that allow NTLM authentication</span></span>

- <span data-ttu-id="a5e03-167">以下命令会删除允许使用 NTLM 进行客户端身份验证的所有注册器安全设置：</span><span class="sxs-lookup"><span data-stu-id="a5e03-167">The following command deletes all the Registrar security settings that allow the use of NTLM for client authentication:</span></span>
    
  ```
  Get-CsProxyConfiguration | Where-Object {$_.UseNtlmForClientToProxyAuth -eq $True}| Remove-CsProxyConfiguration
  ```

<span data-ttu-id="a5e03-168">有关详细信息，请参阅[删除 CsProxyConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csproxyconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="a5e03-168">For details, see [Remove-CsProxyConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csproxyconfiguration?view=skype-ps).</span></span>
  

