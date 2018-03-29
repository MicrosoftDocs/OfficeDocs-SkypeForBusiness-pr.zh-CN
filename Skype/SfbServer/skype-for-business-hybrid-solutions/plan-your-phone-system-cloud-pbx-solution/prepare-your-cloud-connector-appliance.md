---
title: 准备云连接器设备
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Hybrid
ms.assetid: 6eacfa99-9759-4c13-aca3-8992c2ff2710
description: 了解有关如何准备部署云接头装置和使用 Office 365 (云 PBX) 中的电话系统。
ms.openlocfilehash: 8dcc15d2feb12516025afb5e60d916f94a81fa57
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="prepare-your-cloud-connector-appliance"></a><span data-ttu-id="3b345-103">准备云连接器设备</span><span class="sxs-lookup"><span data-stu-id="3b345-103">Prepare your Cloud Connector appliance</span></span>
 
<span data-ttu-id="3b345-104">了解有关如何准备部署云接头装置和使用 Office 365 (云 PBX) 中的电话系统。</span><span class="sxs-lookup"><span data-stu-id="3b345-104">Learn about how to prepare your Cloud Connector appliance for deployment and use with Phone System in Office 365 (Cloud PBX).</span></span>
  
<span data-ttu-id="3b345-105">本节介绍如何获取 Skype for Business 云连接器版本安装文件、安装云连接器软件以及准备云连接器设备以便进行部署。</span><span class="sxs-lookup"><span data-stu-id="3b345-105">This section describes how to get the Skype for Business Cloud Connector Edition installation files, install Cloud Connector software, and prepare your Cloud Connector appliance for deployment.</span></span> <span data-ttu-id="3b345-106">完成本节中的所有步骤后，便可为单个站点或多个站点部署云连接器。</span><span class="sxs-lookup"><span data-stu-id="3b345-106">After you have completed all steps in this section, you will be ready to deploy Cloud Connector for a single site or multiple sites.</span></span> <span data-ttu-id="3b345-107">如果您有现有的云连接器部署，并且尚未升级到云连接器 2.1 版，请参阅[升级到新版本的云连接器](upgrade-to-a-new-version-of-cloud-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="3b345-107">If you have an existing Cloud Connector deployment, and you have not yet upgraded to Cloud Connector version 2.1, see [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="3b345-108">Microsoft 支持云连接器版，2.1 版的当前版本。</span><span class="sxs-lookup"><span data-stu-id="3b345-108">Microsoft supports the current version of Cloud Connector Edition, version 2.1.</span></span> <span data-ttu-id="3b345-109">如果你配置了自动更新，云连接器将自动更新。</span><span class="sxs-lookup"><span data-stu-id="3b345-109">If you configured automatic update, Cloud Connector will update automatically.</span></span> <span data-ttu-id="3b345-110">如果您配置了手动更新，您需要发布的 60 天内升级到 2.1 版。</span><span class="sxs-lookup"><span data-stu-id="3b345-110">If you configured manual update, you will need to upgrade to version 2.1 within 60 days of its release.</span></span> <span data-ttu-id="3b345-111">Microsoft 将支持早期版本的时间升级 2.1 允许发布后的 60 天。</span><span class="sxs-lookup"><span data-stu-id="3b345-111">Microsoft will support the previous version for 60 days after the release of 2.1 to allow you time to upgrade.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="3b345-112">对于云连接器版本 2.1 或更高版本，主机装置必须安装.NET Framework 4.6.1 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="3b345-112">For Cloud Connector version 2.1 and later, the host appliance must have .NET Framework 4.6.1 or later installed.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="3b345-113">对于成功部署，运行时配置的商务云连接器版的 Skype 的 cmdlet，总是用作同一控制台会话中启动的一个。</span><span class="sxs-lookup"><span data-stu-id="3b345-113">For successful deployment, when you run the cmdlets to configure Skype for Business Cloud Connector Edition, always use the same console session as the one you started in.</span></span> <span data-ttu-id="3b345-114">避免在部署和配置期间切换到不同的会话。</span><span class="sxs-lookup"><span data-stu-id="3b345-114">Avoid switching to different sessions during the deployment and configuration.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="3b345-115">只需为部署中的第一台设备执行的一些步骤包括：为站点目录创建共享、下载 bits 以及通过 Windows Server ISO 映像准备虚拟硬盘 (VHDX) 文件。</span><span class="sxs-lookup"><span data-stu-id="3b345-115">There are some steps that you perform only for the first appliance in your deployment: creating a share for the site directory, downloading the bits, and preparing a virtual hard disk (VHDX) file from the Windows Server ISO image.</span></span> 
  
## <a name="download-the-skype-for-business-cloud-connector-edition-installer"></a><span data-ttu-id="3b345-116">下载 Skype for Business 云连接器版本安装程序</span><span class="sxs-lookup"><span data-stu-id="3b345-116">Download the Skype for Business Cloud Connector Edition installer</span></span>

1. <span data-ttu-id="3b345-117">在云接口虚拟机将运行在主机服务器上，将安装文件下载： [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller)。</span><span class="sxs-lookup"><span data-stu-id="3b345-117">On the host server where the Cloud Connector VMs will run, download the installation files: [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="3b345-118">在安装云连接器期间，主机服务器必须能够访问 Internet，因为在安装过程中会下载其他文件。</span><span class="sxs-lookup"><span data-stu-id="3b345-118">The host server must be able to access the Internet during the installation of Cloud Connector because additional files are downloaded during the installation.</span></span> 
  
2. <span data-ttu-id="3b345-119">运行安装程序并在安装过程中接受默认值。</span><span class="sxs-lookup"><span data-stu-id="3b345-119">Run the installer and accept the default values during the installation.</span></span>
    
3. <span data-ttu-id="3b345-120">确认安装已成功完成。</span><span class="sxs-lookup"><span data-stu-id="3b345-120">Confirm that the installation completed successfully.</span></span>
    
## <a name="verify-the-installation-and-configure-the-environment"></a><span data-ttu-id="3b345-121">验证安装并配置环境</span><span class="sxs-lookup"><span data-stu-id="3b345-121">Verify the installation and configure the environment</span></span>

1. <span data-ttu-id="3b345-122">打开 PowerShell 控制台以管理员的身份，确认为商务云连接器版 cmdlet Skype 可使用以下 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="3b345-122">Open a PowerShell console as administrator and confirm that the Skype for Business Cloud Connector Edition cmdlets are available using the following cmdlet:</span></span>
    
  ```
  Get-Command *-Cc*
  ```

    <span data-ttu-id="3b345-123">命令将返回 cmdlet 的为 Skype 业务云连接器版。</span><span class="sxs-lookup"><span data-stu-id="3b345-123">The command should return a list of cmdlets for Skype for Business Cloud Connector Edition.</span></span>
    
2. <span data-ttu-id="3b345-124">VHD、SfBBits 和 VersionInfo 文件将存储在**网站目录**中。</span><span class="sxs-lookup"><span data-stu-id="3b345-124">The VHDs, SfBBits, and VersionInfo files will be stored in the **Site Directory**.</span></span>
    
    <span data-ttu-id="3b345-125">你可以使用以下 cmdlet 找到**网站目录**的位置：</span><span class="sxs-lookup"><span data-stu-id="3b345-125">You can find the location of the **Site Directory** with the following cmdlet:</span></span>
    
  ```
  Get-CcSiteDirectory
  ```

    <span data-ttu-id="3b345-126">此命令会返回文件系统中的某个位置。</span><span class="sxs-lookup"><span data-stu-id="3b345-126">The command should return a location in your file system.</span></span> <span data-ttu-id="3b345-127">该位置可以是本地文件夹或文件共享。</span><span class="sxs-lookup"><span data-stu-id="3b345-127">The location can be a local folder or a file share.</span></span> <span data-ttu-id="3b345-128">**网站目录**的默认位置为：%USERPROFILE%\CloudConnector\SiteRoot。</span><span class="sxs-lookup"><span data-stu-id="3b345-128">The default location for the **Site Directory** is: %USERPROFILE%\CloudConnector\SiteRoot.</span></span> <span data-ttu-id="3b345-129">默认位置会更改为在每个站点上创建的第一个设备上的文件共享。</span><span class="sxs-lookup"><span data-stu-id="3b345-129">The default location should be changed to a file share on the first appliance created in each site.</span></span>
    
    <span data-ttu-id="3b345-130">所选位置必须满足以下要求：</span><span class="sxs-lookup"><span data-stu-id="3b345-130">The location you select must be:</span></span>
    
  - <span data-ttu-id="3b345-131">在每个站点中创建的第一个设备上创建。</span><span class="sxs-lookup"><span data-stu-id="3b345-131">Created on the first appliance created in each site.</span></span>
    
  - <span data-ttu-id="3b345-132">是同一站点中的其他主机服务器（设备）可以访问的共享文件夹。</span><span class="sxs-lookup"><span data-stu-id="3b345-132">A shared folder that is accessible by the other host servers (appliances) in the same site.</span></span>
    
    <span data-ttu-id="3b345-133">要将**网站目录**设置为默认位置以外的位置，请运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="3b345-133">To set the **Site Directory** to a location other than the default, run the following cmdlet:</span></span>
    
  ```
  Set-CcSiteDirectory <UNC File path>
  ```

    <span data-ttu-id="3b345-134">如果要为站点部署高可用性 (HA)，请确保运行该 cmdlet 将**网站目录**设置为每个站点内的主机服务器上的同一位置。</span><span class="sxs-lookup"><span data-stu-id="3b345-134">If you are deploying High Availability (HA) for the site, make sure you run the cmdlet to set the **Site Directory** to the same location on each host server within the site.</span></span>
    
    <span data-ttu-id="3b345-135">当您登录并部署站点中的每个设备时，请确保您当前的登录帐户具有适当访问权限**网站目录**。</span><span class="sxs-lookup"><span data-stu-id="3b345-135">When you log on and deploy each appliance in the site, make sure your current logon account has the right access to the **Site Directory**.</span></span>
    
3. <span data-ttu-id="3b345-136">**装置的目录**是 Skype 的商务云连接器版和保存外部证书、 实例和日志的位置的本地工作根目录。</span><span class="sxs-lookup"><span data-stu-id="3b345-136">The **Appliance Directory** is the local working root directory for Skype for Business Cloud Connector Edition, and the location where external certificates, instances, and logs are saved.</span></span> <span data-ttu-id="3b345-137">默认位置为：%USERPROFILE%\CloudConnector\ApplianceRoot。</span><span class="sxs-lookup"><span data-stu-id="3b345-137">The default location is: %USERPROFILE%\CloudConnector\ApplianceRoot.</span></span>
    
    <span data-ttu-id="3b345-138">要找到**设备目录**的位置，请运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="3b345-138">To find the location of the **Appliance Directory**, run the following cmdlet:</span></span>
    
  ```
  Get-CcApplianceDirectory
  ```

    <span data-ttu-id="3b345-139">要将**设备目录**设置为默认位置以外的位置，请运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="3b345-139">To set the **Appliance Directory** to a location other than the default, run the following cmdlet:</span></span>
    
  ```
  Set-CcApplianceDirectory <File path>
  ```

    <span data-ttu-id="3b345-140">设备目录应该设置为设备上的本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="3b345-140">The Appliance Directory should be set to a local folder on the appliance.</span></span> <span data-ttu-id="3b345-141">启动业务云连接器版部署 Skype 之前，只应设置**设备目录**。</span><span class="sxs-lookup"><span data-stu-id="3b345-141">You should only set the **Appliance Directory** before you start the Skype for Business Cloud Connector Edition deployment.</span></span> <span data-ttu-id="3b345-142">如果在部署之后更改了该目录，则需要重新部署主机服务器。</span><span class="sxs-lookup"><span data-stu-id="3b345-142">If you change it after deployment, you'll need to redeploy the host server.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="3b345-143">**设备目录**的路径中不得包含任何空格。</span><span class="sxs-lookup"><span data-stu-id="3b345-143">The path to the **Appliance Directory** must not contain any spaces.</span></span>
  
## <a name="set-the-path-for-the-external-edge-certificate"></a><span data-ttu-id="3b345-144">设置外部边缘证书的路径</span><span class="sxs-lookup"><span data-stu-id="3b345-144">Set the path for the external Edge certificate</span></span>

- <span data-ttu-id="3b345-p107">运行以下 cmdlet 以设置外部边缘证书的路径，包括文件名。例如：C:\certs\cce\ap.contoso.com.pfx。证书必须包含私钥。</span><span class="sxs-lookup"><span data-stu-id="3b345-p107">Run the following cmdlet to set the path, including the file name, to the external Edge certificate. For example: C:\certs\cce\ap.contoso.com.pfx. The certificate must contain private keys.</span></span>
    
  ```
  Set-CcExternalCertificateFilePath -Path <Full path to External certificate, including file name> -Target EdgeServer
  ```

    > [!NOTE]
    > <span data-ttu-id="3b345-148">请注意：-Target 参数是 1.4.2 版及更高版本特定的。</span><span class="sxs-lookup"><span data-stu-id="3b345-148">Note that the -Target parameter is specific to versions 1.4.2 and later.</span></span> 
  
    <span data-ttu-id="3b345-149">指定外部证书的完整路径，包括文件名。</span><span class="sxs-lookup"><span data-stu-id="3b345-149">Specify the full path to the external certificate, including the file name.</span></span> <span data-ttu-id="3b345-150">证书可以存储在本地或文件共享中。</span><span class="sxs-lookup"><span data-stu-id="3b345-150">The certificate can be stored locally or on a file share.</span></span> <span data-ttu-id="3b345-151">如果证书存储在共享文件夹中，该共享文件夹必须创建在每个站点的第一个设备上，且必须可由属于同一站点的其他设备访问。</span><span class="sxs-lookup"><span data-stu-id="3b345-151">If the certificate is stored in a shared folder, the shared folder must be created on the first appliance of each site and must be accessible by other appliances belonging to the same site.</span></span> <span data-ttu-id="3b345-152">此 cmdlet 将外部证书复制到**设备目录**。</span><span class="sxs-lookup"><span data-stu-id="3b345-152">This cmdlet copies the external certificate to the **Appliance Directory**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="3b345-153">**如果已经更新到云接口版本 1.4.2 或更高版本**，请确保准备好外部证书包含私钥和 CA 根证书和中间 CA 证书。 包括整个证书链 > **，如果您有尚未更新到云连接器 1.4.2 版**，请确保您已准备好外部证书包含私钥。</span><span class="sxs-lookup"><span data-stu-id="3b345-153">**If you have updated to Cloud Connector version 1.4.2 or later**, make sure your prepared external certificate contains private keys and the full certificate chain including the root CA certificate and the intermediate CA certificates.> **If you have NOT yet updated to Cloud Connector version 1.4.2**, make sure your prepared external certificate contains private keys.</span></span> <span data-ttu-id="3b345-154">默认情况下，此外部证书必须由 Windows 信任的证书颁发机构颁发。</span><span class="sxs-lookup"><span data-stu-id="3b345-154">This external certificate must be issued by a Certificate Authority that is trusted by Windows by default.</span></span>
  
## <a name="set-the-path-for-the-external-pstn-gatewaysbc-certificate"></a><span data-ttu-id="3b345-155">设置外部 PSTN 网关/SBC 证书的路径</span><span class="sxs-lookup"><span data-stu-id="3b345-155">Set the path for the external PSTN gateway/SBC certificate</span></span>

<span data-ttu-id="3b345-156">如果你要在中介服务器与 PSTN 网关/SBC 之间使用 TLS，请运行以下 cmdlet 来设置网关证书的路径（包括文件名）。</span><span class="sxs-lookup"><span data-stu-id="3b345-156">If you are using TLS between the Mediation Server and the PSTN gateway/SBC, run the following cmdlet to set the path, including the file name, to the gateway certificate.</span></span> <span data-ttu-id="3b345-157">例如： C:\certs\cce\sbc.contoso.com.cer。</span><span class="sxs-lookup"><span data-stu-id="3b345-157">For example: C:\certs\cce\sbc.contoso.com.cer.</span></span> <span data-ttu-id="3b345-158">证书必须包含分配给网关的证书的根 CA 和中间链。</span><span class="sxs-lookup"><span data-stu-id="3b345-158">The certificate must contain the root CA and the intermediate chain for the certificate assigned to the gateway:</span></span>
  
```
Set-CcExternalCertificateFilePath -Path <Full path to gateway certificate, including file name> -Target MediationServer 

```

> [!NOTE]
> <span data-ttu-id="3b345-159">请注意：-Target 参数是 1.4.2 版及更高版本特定的。</span><span class="sxs-lookup"><span data-stu-id="3b345-159">Note that the -Target parameter is specific to versions 1.4.2 and later.</span></span> 
  
## <a name="create-virtual-switches-in-hyper-v-manager"></a><span data-ttu-id="3b345-160">在 Hyper-V 管理器中创建虚拟交换机</span><span class="sxs-lookup"><span data-stu-id="3b345-160">Create virtual switches in Hyper-V Manager</span></span>

1. <span data-ttu-id="3b345-161">打开**Hyper-V 管理器** > **虚拟交换机管理器**，并选择**新的虚拟交换机管理**。</span><span class="sxs-lookup"><span data-stu-id="3b345-161">Open **Hyper-V Manager** > **Virtual Switch Manager**, and select **New Virtual Switch Manager**.</span></span>
    
2. <span data-ttu-id="3b345-162">创建外部虚拟交换机并将其绑定到与你的内部网络域连接的物理网络适配器：</span><span class="sxs-lookup"><span data-stu-id="3b345-162">Create an External virtual switch and bind it to the physical network adapter that is connected to your internal network domain:</span></span>
    
    <span data-ttu-id="3b345-163">为该虚拟交换机选择“**允许管理操作系统共享此网络适配器**”。</span><span class="sxs-lookup"><span data-stu-id="3b345-163">Select **Allow management operating system to share this network adapter** for this virtual switch.</span></span>
    
3. <span data-ttu-id="3b345-164">创建外部虚拟交换机并将其绑定到被路由到 Internet 的物理网络适配器：</span><span class="sxs-lookup"><span data-stu-id="3b345-164">Create an External virtual switch and bind it to the physical network adapter that is routed to the Internet:</span></span>
    
    <span data-ttu-id="3b345-165">取消选择此虚拟开关**允许管理操作系统共享此网络适配器**。</span><span class="sxs-lookup"><span data-stu-id="3b345-165">De-select **Allow management operating system to share this network adapter** for this virtual switch.</span></span>
    
4. <span data-ttu-id="3b345-166">设置将您的外围网络连接到内部网络域**SfB CCE Corpnet 切换**开关的名称。</span><span class="sxs-lookup"><span data-stu-id="3b345-166">Set the name of the switch that connects your perimeter network to your internal network domain **SfB CCE Corpnet Switch**.</span></span>
    
    <span data-ttu-id="3b345-167">设置将您的外围网络连接到互联网， **SfB CCE 互联网切换**开关的名称。</span><span class="sxs-lookup"><span data-stu-id="3b345-167">Set the name of the switch that connects your perimeter network to the Internet **SfB CCE Internet Switch**.</span></span>
    
## <a name="update-the-cloudconnectorini-configuration-file"></a><span data-ttu-id="3b345-168">更新 CloudConnector.ini 配置文件</span><span class="sxs-lookup"><span data-stu-id="3b345-168">Update the CloudConnector.ini configuration file</span></span>

<span data-ttu-id="3b345-169">准备使用[Skype 业务云连接器版规划](plan-skype-for-business-cloud-connector-edition.md)主题[确定部署参数](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams)中收集的信息的 CloudConnector.ini 文件。</span><span class="sxs-lookup"><span data-stu-id="3b345-169">Prepare the CloudConnector.ini file using the information you gathered in [Determine deployment parameters](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) in the [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) topic.</span></span>
  
<span data-ttu-id="3b345-170">要更新文件，应首先运行以下 cmdlet 以获取示例模板 (CloudConnector.Sample.ini)：</span><span class="sxs-lookup"><span data-stu-id="3b345-170">To update the file, first run the following cmdlet to get the sample template (CloudConnector.Sample.ini):</span></span>
  
```
Export-CcConfigurationSampleFile
```

<span data-ttu-id="3b345-171">示例模板存储在**设备目录**中。</span><span class="sxs-lookup"><span data-stu-id="3b345-171">The sample template is stored in the **Appliance Directory**.</span></span>
  
<span data-ttu-id="3b345-172">使用环境的值更新文件后，在**设备目录**中将其另存为 CloudConnector.ini。</span><span class="sxs-lookup"><span data-stu-id="3b345-172">After you update it with the values for your environment, save the file as CloudConnector.ini in the **Appliance Directory**.</span></span> <span data-ttu-id="3b345-173">您可以运行**Get CcApplianceDirectory**来确定**装置的目录**的路径。</span><span class="sxs-lookup"><span data-stu-id="3b345-173">You can run **Get-CcApplianceDirectory** to determine the path to the **Appliance Directory**.</span></span>
  
<span data-ttu-id="3b345-174">更新 .ini 文件时，请考虑以下内容：</span><span class="sxs-lookup"><span data-stu-id="3b345-174">When updating the .ini file, consider the following:</span></span>
  
> [!NOTE]
> <span data-ttu-id="3b345-175">本节并未讨论 .ini 文件中的所有值，只涵盖了需要特别注意的值。</span><span class="sxs-lookup"><span data-stu-id="3b345-175">Not all values for the .ini file are discussed in this section, only those with a special consideration are covered here.</span></span> <span data-ttu-id="3b345-176">有关完整列表，请参阅[规划业务云连接器版 Skype](plan-skype-for-business-cloud-connector-edition.md)主题。 的[确定部署参数](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams)部分 > 值需要更改为其他装置或新网站的详细信息，请参见[单个站点的高可用性 (HA) 与多站点部署](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site)[部署云连接器中的多个网站](deploy-multiple-sites-in-cloud-connector.md)的主题中。</span><span class="sxs-lookup"><span data-stu-id="3b345-176">For a full list, see the [Determine deployment parameters](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) section of the [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) topic.> For more information about what values need to be changed for additional appliances or new sites, see [Single site with High Availability (HA) compared to multi-site deployments](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site) in the topic[Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 
  
- <span data-ttu-id="3b345-p113">**SiteName：**默认值为 **Site1**。你必须在部署云连接器之前更新该值，因为当通过运行 **Register-CcAppliance** 将设备注册到现有站点或新站点时，该 cmdlet 将使用 **SiteName** 来确定要注册到的站点。</span><span class="sxs-lookup"><span data-stu-id="3b345-p113">**SiteName:** The default value is **Site1**. You must update it before you deploy Cloud Connector, because when you run **Register-CcAppliance** to register an appliance to an existing or new site, the cmdlet will use **SiteName** to determine which site to register.</span></span>
    
     <span data-ttu-id="3b345-179">如果要将设备注册到新站点，**SiteName** 值必须唯一，并且与现有站点不同。</span><span class="sxs-lookup"><span data-stu-id="3b345-179">If you want to register the appliance to a new site, the value of **SiteName** must be unique and different from existing sites.</span></span> <span data-ttu-id="3b345-180">如果您想要注册装置向现有站点，**站点名**.ini 文件中的值必须与 Office 365 租户配置中定义的名称匹配。</span><span class="sxs-lookup"><span data-stu-id="3b345-180">If you want to register the appliance to an existing site, the value for **SiteName** in .ini file must match the name defined in your Office 365 tenant configuration.</span></span> <span data-ttu-id="3b345-181">如果要将配置文件从一个站点复制到另一个站点，请确保相应地更新每个站点的 **SiteName** 值。</span><span class="sxs-lookup"><span data-stu-id="3b345-181">If you are copying a configuration file from one site to another, make sure you update the value for **SiteName** for each site accordingly.</span></span>
    
- <span data-ttu-id="3b345-182">**ServerName：**服务器名称不应包含域名，且不应超过 15 个字符。</span><span class="sxs-lookup"><span data-stu-id="3b345-182">**ServerName:** The server name should not contain the domain name and should be limited to 15 characters.</span></span>
    
- <span data-ttu-id="3b345-183">**HardwareType:**如果未设置，或将值保留为空，将使用**标准**的默认值。</span><span class="sxs-lookup"><span data-stu-id="3b345-183">**HardwareType:** If you don't set or leave the value to null, the default value of **Normal** will be used.</span></span> <span data-ttu-id="3b345-184">如果您打算部署云接头，可支持 500 个呼叫每个主机机[商务云连接器版的 Skype 的计划](plan-skype-for-business-cloud-connector-edition.md)中所述的较大版本，请使用**普通**。</span><span class="sxs-lookup"><span data-stu-id="3b345-184">Use **Normal** if you plan to deploy the larger version of Cloud Connector to support 500 simultaneous calls per host machine as described in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span> <span data-ttu-id="3b345-185">用于支持 50 个呼叫小部署**最小值**。</span><span class="sxs-lookup"><span data-stu-id="3b345-185">Use **Minimum** for a smaller deployment that supports 50 simultaneous calls.</span></span>
    
- <span data-ttu-id="3b345-186">**Internet/公司网络/管理虚拟交换机**：添加已创建的虚拟交换机的名称。</span><span class="sxs-lookup"><span data-stu-id="3b345-186">**Internet/Corpnet/Management virtual switches:**: Add the name of the virtual switches you have created.</span></span> <span data-ttu-id="3b345-187">对于管理虚拟交换机，只需保留默认值即可。</span><span class="sxs-lookup"><span data-stu-id="3b345-187">For the management virtual switch, leave the default value.</span></span> <span data-ttu-id="3b345-188">部署脚本将在部署开始时创建管理虚拟交换机，在部署结束时将其删除。</span><span class="sxs-lookup"><span data-stu-id="3b345-188">The deployment script will create the management virtual switch at the beginning of deployment and delete it when the deployment finishes.</span></span>
    
- <span data-ttu-id="3b345-p117">**ManagementIPPrefix：**“网络”部分中的 ManagementIPPrefix 必须是不同于其他内部 IP 的子网。例如，如默认值所示，ManagementIPPrefix 为 192.168.213.0，而 AD IP 地址为 192.168.0.238。</span><span class="sxs-lookup"><span data-stu-id="3b345-p117">**ManagementIPPrefix:** ManagementIPPrefix in the Network section must be a different subnet from other internal IPs. For example, as the default value shows, ManagementIPPrefix is 192.168.213.0, while AD IPAddress is 192.168.0.238.</span></span>
    
    <span data-ttu-id="3b345-p118">部署脚本会在每台虚拟机上创建管理网络适配器，分配管理 IP，并将其连接到管理虚拟交换机。这样可使主机服务器通过此管理网络连接到每台虚拟机并对其进行管理。部署结束时，会删除管理虚拟交换机。</span><span class="sxs-lookup"><span data-stu-id="3b345-p118">The deployment scripts create a management network adapter on each virtual machine, assign a management IP, and connect it to a management virtual switch. This enables the host server to connect to and manage each virtual machine via this management network. The management virtual switch is deleted when the deployment is finished.</span></span>
    
- <span data-ttu-id="3b345-194">**基 VM 特定配置：**必须为**转换 CcIsoToVhdx** cmdlet 配置本部分中的设置。</span><span class="sxs-lookup"><span data-stu-id="3b345-194">**Base VM specific configurations:** Settings in this section must be configured for the **Convert-CcIsoToVhdx** cmdlet.</span></span>
    
    <span data-ttu-id="3b345-p119">在准备基本虚拟机映像期间，基本虚拟机将连接到内部网络交换机。为使虚拟机能够访问 Internet，以下设置至关重要：</span><span class="sxs-lookup"><span data-stu-id="3b345-p119">During base VM image preparation, the base VM will be connected to the internal network switch. The following settings are critical for the VM to be able to access the Internet:</span></span>
    
  - <span data-ttu-id="3b345-197">[Common]BaseVMIP：要分配给基本虚拟机的公司网络 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="3b345-197">[Common]BaseVMIP: the corpnet IP address to be assigned to the base VM.</span></span>
    
  - <span data-ttu-id="3b345-198">[Network]CorpnetDefaultGateway：要分配给基本虚拟机的默认网关。</span><span class="sxs-lookup"><span data-stu-id="3b345-198">[Network]CorpnetDefaultGateway: the default gateway to be assigned to the base VM.</span></span>
    
  - <span data-ttu-id="3b345-199">[Network]CorpnetDNSIPAddress：要分配给基本虚拟机的 DNS IP 地址。</span><span class="sxs-lookup"><span data-stu-id="3b345-199">[Network]CorpnetDNSIPAddress: the DNS IP address to be assigned to the base VM.</span></span>
    
  - <span data-ttu-id="3b345-200">[Network]WSUSServer：Windows Server Update Service 的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="3b345-200">[Network]WSUSServer: the IP address of Windows Server Update Service.</span></span>
    
  - <span data-ttu-id="3b345-201">[Network]WSUSStatusServer：Windows Server Update Service 状态服务器的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="3b345-201">[Network]WSUSStatusServer: the IP address of Windows Server Update Service status server.</span></span>
    
  - <span data-ttu-id="3b345-202">[Network]EnableReferSupport：用于定义在 IP/PBX 的中继配置上是启用还是禁用 SIP REFER 支持。</span><span class="sxs-lookup"><span data-stu-id="3b345-202">[Network]EnableReferSupport: this will define whether SIP REFER support is enabled or disabled on the Trunk Configuration to your IP/PBX.</span></span>
    
- <span data-ttu-id="3b345-203">**内部 IP：**</span><span class="sxs-lookup"><span data-stu-id="3b345-203">**Internal IPs:**</span></span>
    
  - <span data-ttu-id="3b345-204">请确保子网掩码 CorpnetIPPrefixLength 是正确的。</span><span class="sxs-lookup"><span data-stu-id="3b345-204">Make sure subnet mask CorpnetIPPrefixLength is correct.</span></span>
    
  - <span data-ttu-id="3b345-205">请确保没有为这些内部的 Ip IP 冲突。</span><span class="sxs-lookup"><span data-stu-id="3b345-205">Make sure there are no IP conflicts for these internal IPs.</span></span>
    
- <span data-ttu-id="3b345-206">**外部 IP：**</span><span class="sxs-lookup"><span data-stu-id="3b345-206">**External IPs:**</span></span>
    
  - <span data-ttu-id="3b345-207">MR 公用 ip： 指定为非 NAT ExternalMRIPs 或 ExternalMRPublicIPs 的 nat。</span><span class="sxs-lookup"><span data-stu-id="3b345-207">For MR public IP: specify either ExternalMRIPs for non-NAT or ExternalMRPublicIPs for NAT.</span></span>
    
  - <span data-ttu-id="3b345-208">ExternalSIPIPs 和 ExternalMRIPs 可以是相同的。</span><span class="sxs-lookup"><span data-stu-id="3b345-208">ExternalSIPIPs and ExternalMRIPs can be the same.</span></span>
    
  - <span data-ttu-id="3b345-209">请确保子网掩码 InternetIPPrefixLength 是正确的。</span><span class="sxs-lookup"><span data-stu-id="3b345-209">Make sure subnet mask InternetIPPrefixLength is correct.</span></span>
    
  - <span data-ttu-id="3b345-210">请确保没有为这些外部 Ip IP 冲突。</span><span class="sxs-lookup"><span data-stu-id="3b345-210">Make sure there are no IP conflicts for these external IPs.</span></span>
    
- <span data-ttu-id="3b345-211">**网关：**</span><span class="sxs-lookup"><span data-stu-id="3b345-211">**Gateways:**</span></span>
    
  - <span data-ttu-id="3b345-p120">如果只有一个网关，请删除辅助网关的部分。如果网关超过两个，请通过复制并粘贴现有部分、再进行更新来创建其他部分。</span><span class="sxs-lookup"><span data-stu-id="3b345-p120">If you have only one gateway, remove the section for the secondary gateway. If you have more than two gateways, create additional sections by copying and pasting the existing one and then updating it.</span></span>
    
  - <span data-ttu-id="3b345-214">请确保网关的 IP 地址和端口正确无误。</span><span class="sxs-lookup"><span data-stu-id="3b345-214">Make sure that the IP address and port of the gateway(s) are correct.</span></span>
    
  - <span data-ttu-id="3b345-215">要支持 PSTN 网关级别高可用性，请保留辅助网关，然后添加将使用的任何其他网关。</span><span class="sxs-lookup"><span data-stu-id="3b345-215">To support PSTN gateway level HA, leave the secondary gateway, and add any additional gateways you will use.</span></span> <span data-ttu-id="3b345-216">您可以复制和粘贴现有条目，然后更新该。</span><span class="sxs-lookup"><span data-stu-id="3b345-216">You can copy and paste an existing entry and then update it.</span></span>
    
- <span data-ttu-id="3b345-217">（可选） 您可以更新的 LocalRoute 值来限制出站呼叫电话号码。</span><span class="sxs-lookup"><span data-stu-id="3b345-217">Optionally, you can update the LocalRoute value to restrict outbound call numbers.</span></span>
    
## <a name="download-the-bits-to-the-site-directory"></a><span data-ttu-id="3b345-218">将 bits 下载到“网站目录”</span><span class="sxs-lookup"><span data-stu-id="3b345-218">Download the bits to the Site Directory</span></span>

<span data-ttu-id="3b345-219">运行以下 cmdlet，将 bits 和版本信息文件下载到**站点目录**：</span><span class="sxs-lookup"><span data-stu-id="3b345-219">Run the following cmdlet to download the bits and version information files to the **Site Directory**:</span></span>
  
```
Start-CcDownload
```

> [!NOTE]
> <span data-ttu-id="3b345-220">只需对第一台设备执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="3b345-220">You need to perform this step for the first appliance only.</span></span> 
  
## <a name="prepare-base-virtual-disk-vhdx-from-the-downloaded-iso-file"></a><span data-ttu-id="3b345-221">通过下载的 ISO 文件准备基本虚拟磁盘 (VHDX)</span><span class="sxs-lookup"><span data-stu-id="3b345-221">Prepare base virtual disk (VHDX) from the downloaded ISO file</span></span>

<span data-ttu-id="3b345-222">此步骤将通过 Windows Server 2012 ISO 映像准备虚拟硬盘 (VHDX) 文件。</span><span class="sxs-lookup"><span data-stu-id="3b345-222">This step prepares a virtual hard disk (VHDX) file from the Windows Server 2012 ISO image.</span></span> <span data-ttu-id="3b345-223">在部署期间，将使用 VHDX 创建虚拟机。</span><span class="sxs-lookup"><span data-stu-id="3b345-223">The VHDX will be used to create virtual machines during deployment.</span></span> <span data-ttu-id="3b345-224">将创建一个临时的虚拟机 (VM 基) 和 Windows Server 2012 将安装的 ISO 文件。</span><span class="sxs-lookup"><span data-stu-id="3b345-224">A temporary virtual machine (base VM) will be created and Windows Server 2012 will be installed from the ISO file.</span></span> <span data-ttu-id="3b345-225">创建虚拟机后，将安装一些必要组件，并应用最新的 Windows 更新。</span><span class="sxs-lookup"><span data-stu-id="3b345-225">After the VM is created, some necessary components will be installed and the latest Windows update will be applied.</span></span> <span data-ttu-id="3b345-226">最后，集中 (sysprep) 并清理基本虚拟机，仅保留生成的虚拟磁盘文件。</span><span class="sxs-lookup"><span data-stu-id="3b345-226">At the end, the base VM will be generalized (sysprep) and cleaned up, leaving only the generated virtual disk file.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3b345-227">只需对第一台设备执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="3b345-227">You need to perform this step for the first appliance only.</span></span> 
  
<span data-ttu-id="3b345-p123">继续执行此步骤前，请确保已创建公司网络交换机。另外，请确认在 CloudConnector.ini 文件中正确配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="3b345-p123">Before proceeding with this step, make sure that the corpnet switch is created. Also, confirm that the following settings are correctly configured in the CloudConnector.ini file:</span></span>
  
- <span data-ttu-id="3b345-230">[网络]CorpnetSwitchName</span><span class="sxs-lookup"><span data-stu-id="3b345-230">[Network]CorpnetSwitchName</span></span>
    
- <span data-ttu-id="3b345-231">[公共]BaseVMIP</span><span class="sxs-lookup"><span data-stu-id="3b345-231">[Common]BaseVMIP</span></span>
    
- <span data-ttu-id="3b345-232">[网络]CorpnetIPPrefixLength</span><span class="sxs-lookup"><span data-stu-id="3b345-232">[Network]CorpnetIPPrefixLength</span></span>
    
- <span data-ttu-id="3b345-233">[网络]CorpnetDefaultGateway</span><span class="sxs-lookup"><span data-stu-id="3b345-233">[Network]CorpnetDefaultGateway</span></span>
    
- <span data-ttu-id="3b345-234">[网络]CorpnetDNSIPAddress</span><span class="sxs-lookup"><span data-stu-id="3b345-234">[Network]CorpnetDNSIPAddress</span></span>
    
<span data-ttu-id="3b345-235">以管理员身份启动 PowerShell 控制台，然后运行以下 cmdlet 以将 ISO 映像转换为虚拟硬盘 (VHD)：</span><span class="sxs-lookup"><span data-stu-id="3b345-235">Start a PowerShell console as administrator and run the following cmdlet to convert the ISO image to a virtual hard disk (VHD):</span></span>
  
```
Convert-CcIsoToVhdx -IsoFilePath <Windows ISO File Path, including file name>
```

<span data-ttu-id="3b345-p124">指定 ISO 映像的完整路径，包括文件名。例如：C:\ISO\WindowsServer2012R2.iso。</span><span class="sxs-lookup"><span data-stu-id="3b345-p124">Specify the full path, including file name, to the ISO image. For example: C:\ISO\WindowsServer2012R2.iso.</span></span>
  
<span data-ttu-id="3b345-238">创建的 VHD 文件存储在**网站目录**的 \Bits\VHD 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="3b345-238">The created VHD file is stored in the **Site Directory** \Bits\VHD folder.</span></span> <span data-ttu-id="3b345-239">可以通过运行 **Get-CcSiteDirectory** 获取**网站目录**的路径。</span><span class="sxs-lookup"><span data-stu-id="3b345-239">You can get the path to the **Site Directory** by running the **Get-CcSiteDirectory**.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="3b345-240">默认情况下，不在基本虚拟机上配置代理设置。</span><span class="sxs-lookup"><span data-stu-id="3b345-240">By default, proxy settings are not configured on the base VM.</span></span> <span data-ttu-id="3b345-241">如果代理服务器在您的网络环境中需要更新通过 Windows Update VM，则应添加-PauseBeforeUpdate 开关时运行"转换-CcIsoToVhdx"。</span><span class="sxs-lookup"><span data-stu-id="3b345-241">If a proxy is required in your network environment to update the VM via Windows Update, you should add the -PauseBeforeUpdate switch when you run "Convert-CcIsoToVhdx".</span></span> <span data-ttu-id="3b345-242">该脚本将暂停之前 Windows 更新，您将有机会来手动设置虚拟机上的代理。</span><span class="sxs-lookup"><span data-stu-id="3b345-242">The script will pause before Windows Update and you'll have a chance to manually set up proxy on the VM.</span></span> <span data-ttu-id="3b345-243">在设置代理并且虚拟机可以访问 Internet 后，可恢复脚本以完成剩余的步骤。</span><span class="sxs-lookup"><span data-stu-id="3b345-243">After the proxy is setup and the VM can access Internet, you can resume the script to complete the remaining steps.</span></span> 
  
### <a name="create-vhds-for-a-multi-site-deployment"></a><span data-ttu-id="3b345-244">为多站点部署创建 VHD</span><span class="sxs-lookup"><span data-stu-id="3b345-244">Create VHDs for a multi-site deployment</span></span>

<span data-ttu-id="3b345-245">这是一个可选步骤，仅适用于多站点部署。</span><span class="sxs-lookup"><span data-stu-id="3b345-245">This is an optional step that applies only to multi-site deployments.</span></span>
  
<span data-ttu-id="3b345-p127">如果要部署多站点部署，不需要为每个站点将 ISO 转换的 VHD。你可以将为第一个站点创建的 VHDX 复制到第二个站点的主机服务器。</span><span class="sxs-lookup"><span data-stu-id="3b345-p127">If you are deploying a multi-site deployment, you do not need to convert the ISO to a VHD for each site. You can copy the VHDX created for the first site to the host server for a second site.</span></span>
  
 <span data-ttu-id="3b345-248">将该文件复制到相同的文件位置 （**网站目录**\Bits\VHD 文件夹），并与其他网站的宿主服务器上相同的文件名。</span><span class="sxs-lookup"><span data-stu-id="3b345-248">Copy the file to the same file location ( **Site Directory** \Bits\VHD folder), and with the same file name, on the host server for an additional site.</span></span>
  
## <a name="set-the-powershell-execution-policy-to-remotesigned"></a><span data-ttu-id="3b345-249">将 PowerShell 执行策略设置为 RemoteSigned</span><span class="sxs-lookup"><span data-stu-id="3b345-249">Set the PowerShell Execution policy to RemoteSigned</span></span>

<span data-ttu-id="3b345-p128">提供的 PowerShell 脚本要求将执行策略设置为 RemoteSigned。要查看当前设置，请以管理员身份打开 PowerShell 控制台，然后运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="3b345-p128">The PowerShell scripts provided require that the execution policy be set to RemoteSigned. To see the current setting, open a PowerShell console as administrator and then run the following cmdlet:</span></span>
  
```
Get-ExecutionPolicy
```

<span data-ttu-id="3b345-252">如果执行策略未设置为“RemoteSigned”，则运行以下 cmdlet 进行更改：</span><span class="sxs-lookup"><span data-stu-id="3b345-252">If it is not set to "RemoteSigned," run the following cmdlet to change it:</span></span>
  
```
Set-ExecutionPolicy RemoteSigned
```

## <a name="change-local-group-policy-on-the-host-machine-versions-141-and-earlier"></a><span data-ttu-id="3b345-253">更改主机上的本地组策略（1.4.1 版及更低版本）</span><span class="sxs-lookup"><span data-stu-id="3b345-253">Change local Group Policy on the host machine (versions 1.4.1 and earlier)</span></span>

> [!NOTE]
> <span data-ttu-id="3b345-254">对于云连接器 1.4.2 版及更高版本，不需要执行此任务。</span><span class="sxs-lookup"><span data-stu-id="3b345-254">This task is not required for Cloud Connector versions 1.4.2 and later.</span></span> 
  
<span data-ttu-id="3b345-255">在部署 Skype for Business 云连接器版本时已创建 CceService 帐户。</span><span class="sxs-lookup"><span data-stu-id="3b345-255">The CceService account is created during the Skype for Business Cloud Connector Edition deployment.</span></span> <span data-ttu-id="3b345-256">它运行云连接器管理服务，并要求卸载 cloudconnector.msi 的权限。</span><span class="sxs-lookup"><span data-stu-id="3b345-256">It runs the Cloud Connector Management Service and requires permission to uninstall the cloudconnector.msi.</span></span> <span data-ttu-id="3b345-257">你必须更改云连接器主机上的组策略设置，指定用户注销时不会卸载用户注册表。</span><span class="sxs-lookup"><span data-stu-id="3b345-257">You must change the group policy setting on the Cloud Connector host machine to specify that the user registry should not be unloaded when the user logs off.</span></span> <span data-ttu-id="3b345-258">请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="3b345-258">Follow the steps below:</span></span>
  
### <a name="to-change-the-group-policy-setting"></a><span data-ttu-id="3b345-259">更改组策略设置</span><span class="sxs-lookup"><span data-stu-id="3b345-259">To change the Group Policy setting</span></span>

1. <span data-ttu-id="3b345-260">通过运行 gpedit.msc 打开**组策略编辑器**。</span><span class="sxs-lookup"><span data-stu-id="3b345-260">Open the **Group Policy Editor** by running gpedit.msc.</span></span>
    
2. <span data-ttu-id="3b345-261">在“**组策略编辑器**”中，导航到“管理模板”>“系统”>“用户配置文件”>“在用户注销时不强制卸载用户注册表”。</span><span class="sxs-lookup"><span data-stu-id="3b345-261">In the **Group Policy Editor**, navigate to Administrative Templates > System > UserProfile > Do not forcefully unload the user registry at user logoff.</span></span> 
    
3. <span data-ttu-id="3b345-262">将其值设置为**启用**。</span><span class="sxs-lookup"><span data-stu-id="3b345-262">Set its value to **Enabled**.</span></span>
    
## <a name="set-up-your-office-365-tenant"></a><span data-ttu-id="3b345-263">设置你的 Office 365 租户</span><span class="sxs-lookup"><span data-stu-id="3b345-263">Set up your Office 365 tenant</span></span>

<span data-ttu-id="3b345-264">Office 365 租户与 Skype 的在线业务和 Office 365 中的电话系统是必需的。</span><span class="sxs-lookup"><span data-stu-id="3b345-264">An Office 365 tenant with Skype for Business Online and Phone System in Office 365 is required.</span></span> <span data-ttu-id="3b345-265">请确保设置，然后再尝试使用云连接器配置您的租户。</span><span class="sxs-lookup"><span data-stu-id="3b345-265">Make sure your tenant is set up and configured before attempting to use Cloud Connector.</span></span>
  
<span data-ttu-id="3b345-266">一些 Office 365 安装步骤要求您使用远程 PowerShell 租户 (TRPS) 来配置 Office 365 租户。</span><span class="sxs-lookup"><span data-stu-id="3b345-266">Some Office 365 setup steps require you to use Tenant Remote PowerShell (TRPS) to configure your Office 365 tenant.</span></span> <span data-ttu-id="3b345-267">**它应安装在主机服务器上。**</span><span class="sxs-lookup"><span data-stu-id="3b345-267">**This should be installed on the host server.**</span></span> <span data-ttu-id="3b345-268">您也可以下载 Skype 的在线业务模块从 PowerShell:[Skype 业务在线，Windows PowerShell 模块](https://www.microsoft.com/en-us/download/details.aspx?id=39366)。</span><span class="sxs-lookup"><span data-stu-id="3b345-268">You can download the Skype for Business Online module for PowerShell from:[Skype for Business Online, Windows PowerShell Module](https://www.microsoft.com/en-us/download/details.aspx?id=39366).</span></span>
  
<span data-ttu-id="3b345-269">创建专用的 Skype 的业务管理员帐户的云连接器在线管理，例如 CceOnlineManagmentAdministrator。</span><span class="sxs-lookup"><span data-stu-id="3b345-269">Create a dedicated Skype for Business administrator account for Cloud Connector online management, for example CceOnlineManagmentAdministrator.</span></span> <span data-ttu-id="3b345-270">设备将使用该帐户添加或删除设备、启用或禁用操作系统自动更新、启用或禁用二进制文件自动更新。</span><span class="sxs-lookup"><span data-stu-id="3b345-270">This account will be used by appliance to add or remove appliance, enable or disable automatic OS update, enable or disable automatic binary update.</span></span> <span data-ttu-id="3b345-271">请将该帐户的密码设置为永不过期，从而无需在每次过期时为服务更改密码。</span><span class="sxs-lookup"><span data-stu-id="3b345-271">Set the password for this account to never expire so that you do not need to change it for the service each time it expires.</span></span>
  

