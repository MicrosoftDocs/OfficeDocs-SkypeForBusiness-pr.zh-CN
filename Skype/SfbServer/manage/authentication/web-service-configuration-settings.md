---
title: 在 Skype for Business Server 中管理 Web 服务配置设置
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
ms.assetid: f3f04d81-8a1f-427f-bd0f-fb659024e096
description: 摘要：在 Skype for Business Server 中管理 Web 服务配置设置。
ms.openlocfilehash: 6d79e0567790f10dd86c68f64d7bde54d3540b44
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099168"
---
# <a name="manage-web-service-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="ee2e0-103">在 Skype for Business Server 中管理 Web 服务配置设置</span><span class="sxs-lookup"><span data-stu-id="ee2e0-103">Manage Web Service configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="ee2e0-104">**摘要：** 在 Skype for Business Server 中管理 Web 服务配置设置。</span><span class="sxs-lookup"><span data-stu-id="ee2e0-104">**Summary:** Manage Web Service configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="ee2e0-105">可以使用 **"Web 服务** "页配置用于访问 Skype for Business Server 相关 Web 服务器和 Web 服务的身份验证方法。</span><span class="sxs-lookup"><span data-stu-id="ee2e0-105">You can use the **Web Service** page to configure the authentication methods for accessing Skype for Business Server related web servers and Web Services.</span></span>
  
<span data-ttu-id="ee2e0-106">按照以下步骤创建新的 Web 服务策略。</span><span class="sxs-lookup"><span data-stu-id="ee2e0-106">Follow these steps to create a new Web Service policy.</span></span>
  
### <a name="to-create-new-web-service-configuration-settings"></a><span data-ttu-id="ee2e0-107">创建新的 Web 服务配置设置</span><span class="sxs-lookup"><span data-stu-id="ee2e0-107">To create new web service configuration settings</span></span>

1.  <span data-ttu-id="ee2e0-108">从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到部署 Skype for Business Server 的网络内的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="ee2e0-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="ee2e0-109">打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="ee2e0-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="ee2e0-110">在左侧导航栏中，单击“安全性”，然后单击“Web 服务”。</span><span class="sxs-lookup"><span data-stu-id="ee2e0-110">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>
    
4. <span data-ttu-id="ee2e0-111">在“Web 服务”页上，单击“新建”，然后执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="ee2e0-111">On the **Web Service** page, click **New**, and then do one of the following:</span></span>
    
   - <span data-ttu-id="ee2e0-p101">要配置站点的 Web 服务，请单击“站点配置”。在“选择站点”中，单击将应用此 Web 服务策略的站点，然后单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="ee2e0-p101">To configure the Web Service for a site, click **Site configuration**. In **Select a Site**, click the site to which the Web Service policy will be applied a site and click **OK**.</span></span>
    
   - <span data-ttu-id="ee2e0-p102">要配置池的 Web 服务，请单击“池配置”。在“选择服务”中，单击将应用此 Web 服务策略的服务，然后单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="ee2e0-p102">To configure the Web Service for a pool, click **Pool configuration**. In **Select a Service**, click the service to which the Web Service policy will be applied and click **OK**.</span></span> 
    
5. <span data-ttu-id="ee2e0-116">在“新建 Web 服务设置”的“集成的 Windows 身份验证”中，选择“协商”、“集成的 Windows 身份验证”或“无”。</span><span class="sxs-lookup"><span data-stu-id="ee2e0-116">In **New Web Service Setting**, in **Integrated Windows authentication**, select **Negotiate**, **Integrated Windows authentication**, or **None**.</span></span>
    
6. <span data-ttu-id="ee2e0-117">根据环境中的客户端功能和支持情况，选择下列一项或多项：</span><span class="sxs-lookup"><span data-stu-id="ee2e0-117">Select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
   - <span data-ttu-id="ee2e0-118">**启用 PIN 身份验证**，允许使用 PIN 号对客户端进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="ee2e0-118">**Enable PIN Authentication** to enable clients to be authenticated using PIN numbers.</span></span>
    
   - <span data-ttu-id="ee2e0-119">**启用证书身份验证**，可使池中的服务器向客户端颁发证书。</span><span class="sxs-lookup"><span data-stu-id="ee2e0-119">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
   - <span data-ttu-id="ee2e0-120">**启用证书链下载**，让具有身份验证证书的服务器下载该证书的证书链。</span><span class="sxs-lookup"><span data-stu-id="ee2e0-120">**Enable certificate chain download** to have servers presented with an authentication certificate download the certificate chain for that certificate.</span></span>
    
7. <span data-ttu-id="ee2e0-121">单击“提交”。</span><span class="sxs-lookup"><span data-stu-id="ee2e0-121">Click **Commit**.</span></span>
    
## <a name="modify-existing-web-service-configuration-settings"></a><span data-ttu-id="ee2e0-122">修改现有 Web 服务配置设置</span><span class="sxs-lookup"><span data-stu-id="ee2e0-122">Modify existing Web Service configuration settings</span></span>

<span data-ttu-id="ee2e0-123">可以使用 **"Web 服务** "页配置用于访问 Skype for Business Server 相关 Web 服务器和 Web 服务的身份验证方法。</span><span class="sxs-lookup"><span data-stu-id="ee2e0-123">You can use the **Web Service** page to configure the authentication methods for accessing Skype for Business Server related web servers and Web Services.</span></span>
  
<span data-ttu-id="ee2e0-124">按照以下步骤修改现有的 Web 服务策略。</span><span class="sxs-lookup"><span data-stu-id="ee2e0-124">Follow these steps to modify an existing Web Service policy.</span></span>
  
### <a name="to-modify-existing-web-service-configuration-settings"></a><span data-ttu-id="ee2e0-125">修改现有 Web 服务配置设置</span><span class="sxs-lookup"><span data-stu-id="ee2e0-125">To modify existing Web service configuration settings</span></span>

1.  <span data-ttu-id="ee2e0-126">从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到部署 Skype for Business Server 的网络内的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="ee2e0-126">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="ee2e0-127">打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="ee2e0-127">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="ee2e0-128">在左侧导航栏中，单击“安全性”，然后单击“Web 服务”。</span><span class="sxs-lookup"><span data-stu-id="ee2e0-128">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>
    
4. <span data-ttu-id="ee2e0-129">在“Web 服务”页上，单击某个配置，再单击“编辑”，然后单击“显示详细信息”。</span><span class="sxs-lookup"><span data-stu-id="ee2e0-129">On the **Web Service** page, click a configuration, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="ee2e0-130">在“编辑 Web 服务设置”的“集成 Windows 身份验证”中，选择“协商”、“集成 Windows 身份验证”或“无”。</span><span class="sxs-lookup"><span data-stu-id="ee2e0-130">In **Edit Web Service Setting**, in **Integrated Windows authentication**, select **Negotiate**, **Integrated Windows authentication**, or **None**.</span></span>
    
6. <span data-ttu-id="ee2e0-131">根据环境中的客户端功能和支持情况，选择下列一项或多项：</span><span class="sxs-lookup"><span data-stu-id="ee2e0-131">Select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
   - <span data-ttu-id="ee2e0-132">**启用 PIN 身份验证**，允许使用 PIN 号对客户端进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="ee2e0-132">**Enable PIN Authentication** to enable clients to be authenticated using PIN numbers.</span></span>
    
   - <span data-ttu-id="ee2e0-133">**启用证书身份验证**，可使池中的服务器向客户端颁发证书。</span><span class="sxs-lookup"><span data-stu-id="ee2e0-133">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
   - <span data-ttu-id="ee2e0-134">**启用证书链下载**，让具有身份验证证书的服务器下载该证书的证书链。</span><span class="sxs-lookup"><span data-stu-id="ee2e0-134">**Enable certificate chain download** to have servers presented with an authentication certificate download the certificate chain for that certificate.</span></span>
    
7. <span data-ttu-id="ee2e0-135">单击“提交”。</span><span class="sxs-lookup"><span data-stu-id="ee2e0-135">Click **Commit**.</span></span>
    
## <a name="delete-existing-web-service-configuration-settings"></a><span data-ttu-id="ee2e0-136">删除现有 Web 服务配置设置</span><span class="sxs-lookup"><span data-stu-id="ee2e0-136">Delete existing Web Service configuration settings</span></span>

<span data-ttu-id="ee2e0-137">按照以下步骤删除 Web 服务配置设置。</span><span class="sxs-lookup"><span data-stu-id="ee2e0-137">Follow these steps to delete web service configuration settings.</span></span>
  
### <a name="to-delete-web-service-configuration-settings"></a><span data-ttu-id="ee2e0-138">删除 Web 服务配置设置</span><span class="sxs-lookup"><span data-stu-id="ee2e0-138">To delete web service configuration settings</span></span>

1.  <span data-ttu-id="ee2e0-139">从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到部署 Skype for Business Server 的网络内的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="ee2e0-139">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="ee2e0-140">打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="ee2e0-140">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="ee2e0-141">在左侧导航栏中，单击“安全性”，然后单击“Web 服务”。</span><span class="sxs-lookup"><span data-stu-id="ee2e0-141">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>
    
4. <span data-ttu-id="ee2e0-142">在“Web 服务”页上的搜索字段中，键入要删除的策略的全部或部分名称。</span><span class="sxs-lookup"><span data-stu-id="ee2e0-142">On the **Web Service** page, and in the search field, type all or part of the name of the policy you want to delete.</span></span>
    
5. <span data-ttu-id="ee2e0-143">在策略列表中，单击所需的策略，再单击“编辑”，然后单击“删除”。</span><span class="sxs-lookup"><span data-stu-id="ee2e0-143">In the list of policies, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>
    
6. <span data-ttu-id="ee2e0-144">单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="ee2e0-144">Click **OK**.</span></span>
    
## <a name="deleting-web-service-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="ee2e0-145">使用 Cmdlet 删除 Web 服务Windows PowerShell设置</span><span class="sxs-lookup"><span data-stu-id="ee2e0-145">Deleting Web Service Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="ee2e0-146">可以通过使用 Windows PowerShell **和 Remove-CsWebServiceConfiguration** cmdlet 删除 Web 服务配置设置。</span><span class="sxs-lookup"><span data-stu-id="ee2e0-146">You can delete web service configuration settings by using Windows PowerShell and the **Remove-CsWebServiceConfiguration** cmdlet.</span></span> <span data-ttu-id="ee2e0-147">还可从 Skype for Business Server Management Shell 或 Windows PowerShell 远程会话运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ee2e0-147">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="ee2e0-148">有关使用远程 Windows PowerShell连接到 Skype for Business Server 的详细信息，请参阅博客文章"快速入门：使用远程 PowerShell 管理[Microsoft Lync Server 2010"。](https://go.microsoft.com/fwlink/p/?linkId=255876)</span><span class="sxs-lookup"><span data-stu-id="ee2e0-148">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="ee2e0-149">此过程在 Skype for Business Server 中是相同的。</span><span class="sxs-lookup"><span data-stu-id="ee2e0-149">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-delete-a-specific-collection-of-web-service-configuration-settings"></a><span data-ttu-id="ee2e0-150">删除特定的 Web 服务配置设置集合</span><span class="sxs-lookup"><span data-stu-id="ee2e0-150">To delete a specific collection of web service configuration settings</span></span>

- <span data-ttu-id="ee2e0-151">以下命令会删除应用到 Redmond 站点的 Web 服务安全设置：</span><span class="sxs-lookup"><span data-stu-id="ee2e0-151">The following command removes the Web Service security settings applied to the Redmond site:</span></span>
    
  ```PowerShell
  Remove-CsWebServiceConfiguration -Identity "site:Redmond"
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="ee2e0-152">删除应用于站点范围的所有 Web 服务配置设置</span><span class="sxs-lookup"><span data-stu-id="ee2e0-152">To delete all of the web service configuration settings applied to the site scope</span></span>

<span data-ttu-id="ee2e0-153">以下命令会删除应用到服务范围的所有 Web 服务安全设置：</span><span class="sxs-lookup"><span data-stu-id="ee2e0-153">The following command removes all of the Web Service security settings applied to the service scope:</span></span>
    
  ```PowerShell
  Get-CsWebServiceConfiguration -Filter "service:*" | Remove-CsWebServiceConfiguration
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-that-allow-certificate-authentication"></a><span data-ttu-id="ee2e0-154">删除允许证书身份验证的所有 Web 服务配置设置</span><span class="sxs-lookup"><span data-stu-id="ee2e0-154">To delete all of the web service configuration settings that allow certificate authentication</span></span>

<span data-ttu-id="ee2e0-155">以下命令会删除允许使用证书身份验证的所有 Web 服务安全设置：</span><span class="sxs-lookup"><span data-stu-id="ee2e0-155">The following command removes all the Web Service security settings that allow the use of certificate authentication:</span></span>
    
  ```PowerShell
  Get-CsWebServiceConfiguration | Where-Object {$_.UseCertificateAuth -eq $True} | Remove-CsWebServiceConfiguration
  ```

<span data-ttu-id="ee2e0-156">有关详细信息，请参阅 [Remove-CsWebServiceConfiguration](/powershell/module/skype/remove-cswebserviceconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="ee2e0-156">For details, see [Remove-CsWebServiceConfiguration](/powershell/module/skype/remove-cswebserviceconfiguration?view=skype-ps).</span></span>
