---
title: 准备云连接器设备
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
ms.assetid: 6eacfa99-9759-4c13-aca3-8992c2ff2710
description: 了解如何为你的云连接器设备准备部署并与电话系统（云 PBX）结合使用。
ms.openlocfilehash: d00002719ed8aaac7d0f0fb0e5ceb5722acc289c
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220062"
---
# <a name="prepare-your-cloud-connector-appliance"></a><span data-ttu-id="04633-103">准备云连接器设备</span><span class="sxs-lookup"><span data-stu-id="04633-103">Prepare your Cloud Connector appliance</span></span>

<span data-ttu-id="04633-104">了解如何为你的云连接器设备准备部署并与电话系统（云 PBX）结合使用。</span><span class="sxs-lookup"><span data-stu-id="04633-104">Learn about how to prepare your Cloud Connector appliance for deployment and use with Phone System (Cloud PBX).</span></span>

<span data-ttu-id="04633-105">本节介绍如何获取 Skype for Business 云连接器版本安装文件、安装云连接器软件以及准备云连接器设备以进行部署。</span><span class="sxs-lookup"><span data-stu-id="04633-105">This section describes how to get the Skype for Business Cloud Connector Edition installation files, install Cloud Connector software, and prepare your Cloud Connector appliance for deployment.</span></span> <span data-ttu-id="04633-106">完成本节中的所有步骤后，你将准备为单个网站或多个网站部署云连接器。</span><span class="sxs-lookup"><span data-stu-id="04633-106">After you have completed all steps in this section, you will be ready to deploy Cloud Connector for a single site or multiple sites.</span></span> <span data-ttu-id="04633-107">如果你已有云连接器部署且尚未升级到云连接器版本2.1，请参阅[升级到新版本的云连接器](upgrade-to-a-new-version-of-cloud-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="04633-107">If you have an existing Cloud Connector deployment, and you have not yet upgraded to Cloud Connector version 2.1, see [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span>

> [!NOTE]
> <span data-ttu-id="04633-108">Microsoft 支持当前版本的云连接器版本2.1。</span><span class="sxs-lookup"><span data-stu-id="04633-108">Microsoft supports the current version of Cloud Connector Edition, version 2.1.</span></span> <span data-ttu-id="04633-109">如果配置了自动更新，云连接器将自动更新。</span><span class="sxs-lookup"><span data-stu-id="04633-109">If you configured automatic update, Cloud Connector will update automatically.</span></span> <span data-ttu-id="04633-110">如果配置了手动更新，则需要在版本60天内将其升级到版本2.1。</span><span class="sxs-lookup"><span data-stu-id="04633-110">If you configured manual update, you will need to upgrade to version 2.1 within 60 days of its release.</span></span> <span data-ttu-id="04633-111">Microsoft 将在2.1 发布后的60天内支持早期版本，以允许你进行升级。</span><span class="sxs-lookup"><span data-stu-id="04633-111">Microsoft will support the previous version for 60 days after the release of 2.1 to allow you time to upgrade.</span></span> 

> [!NOTE]
> <span data-ttu-id="04633-112">对于云连接器版本2.1 及更高版本，主机设备必须安装了 .NET Framework 4.6.1 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="04633-112">For Cloud Connector version 2.1 and later, the host appliance must have .NET Framework 4.6.1 or later installed.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="04633-113">若要成功进行部署，运行 cmdlet 以配置 Skype for Business 云连接器版本时，请始终使用与在中启动的相同的控制台会话。</span><span class="sxs-lookup"><span data-stu-id="04633-113">For successful deployment, when you run the cmdlets to configure Skype for Business Cloud Connector Edition, always use the same console session as the one you started in.</span></span> <span data-ttu-id="04633-114">避免在部署和配置过程中切换到不同的会话。</span><span class="sxs-lookup"><span data-stu-id="04633-114">Avoid switching to different sessions during the deployment and configuration.</span></span> 

> [!NOTE]
> <span data-ttu-id="04633-115">仅对部署中的第一台设备执行一些步骤：为网站目录创建共享，下载 bits，并从 Windows Server ISO 映像准备虚拟硬盘（VHDX）文件。</span><span class="sxs-lookup"><span data-stu-id="04633-115">There are some steps that you perform only for the first appliance in your deployment: creating a share for the site directory, downloading the bits, and preparing a virtual hard disk (VHDX) file from the Windows Server ISO image.</span></span> 

## <a name="download-the-skype-for-business-cloud-connector-edition-installer"></a><span data-ttu-id="04633-116">下载 Skype for Business 云连接器版本安装程序</span><span class="sxs-lookup"><span data-stu-id="04633-116">Download the Skype for Business Cloud Connector Edition installer</span></span>

1. <span data-ttu-id="04633-117">在将运行云连接器虚拟机的主机服务器上，下载安装文件： [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) 。</span><span class="sxs-lookup"><span data-stu-id="04633-117">On the host server where the Cloud Connector VMs will run, download the installation files: [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span> 

    > [!IMPORTANT]
    > <span data-ttu-id="04633-118">在安装云连接器的过程中，主机服务器必须能够访问 Internet，因为在安装过程中会下载其他文件。</span><span class="sxs-lookup"><span data-stu-id="04633-118">The host server must be able to access the Internet during the installation of Cloud Connector because additional files are downloaded during the installation.</span></span> 

2. <span data-ttu-id="04633-119">运行安装程序，并在安装过程中接受默认值。</span><span class="sxs-lookup"><span data-stu-id="04633-119">Run the installer and accept the default values during the installation.</span></span>

3. <span data-ttu-id="04633-120">确认安装已成功完成。</span><span class="sxs-lookup"><span data-stu-id="04633-120">Confirm that the installation completed successfully.</span></span>

## <a name="verify-the-installation-and-configure-the-environment"></a><span data-ttu-id="04633-121">验证安装并配置环境</span><span class="sxs-lookup"><span data-stu-id="04633-121">Verify the installation and configure the environment</span></span>

1. <span data-ttu-id="04633-122">以管理员身份打开 PowerShell 控制台，并使用以下 cmdlet 确认是否可以使用 Skype for Business 云连接器版本 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="04633-122">Open a PowerShell console as administrator and confirm that the Skype for Business Cloud Connector Edition cmdlets are available using the following cmdlet:</span></span>

   ```powershell
   Get-Command *-Cc*
   ```

    <span data-ttu-id="04633-123">该命令应返回适用于 Skype for Business 云连接器版本的 cmdlet 的列表。</span><span class="sxs-lookup"><span data-stu-id="04633-123">The command should return a list of cmdlets for Skype for Business Cloud Connector Edition.</span></span>

2. <span data-ttu-id="04633-124">Vhd、SfBBits 和 VersionInfo 文件将存储在**网站目录**中。</span><span class="sxs-lookup"><span data-stu-id="04633-124">The VHDs, SfBBits, and VersionInfo files will be stored in the **Site Directory**.</span></span>

    <span data-ttu-id="04633-125">您可以使用以下 cmdlet 找到**网站目录**的位置：</span><span class="sxs-lookup"><span data-stu-id="04633-125">You can find the location of the **Site Directory** with the following cmdlet:</span></span>

   ```powershell
   Get-CcSiteDirectory
   ```

    <span data-ttu-id="04633-126">该命令应返回文件系统中的某个位置。</span><span class="sxs-lookup"><span data-stu-id="04633-126">The command should return a location in your file system.</span></span> <span data-ttu-id="04633-127">该位置可以是本地文件夹或文件共享。</span><span class="sxs-lookup"><span data-stu-id="04633-127">The location can be a local folder or a file share.</span></span> <span data-ttu-id="04633-128">"**网站目录**" 的默认位置是：%USERPROFILE%\CloudConnector\SiteRoot。</span><span class="sxs-lookup"><span data-stu-id="04633-128">The default location for the **Site Directory** is: %USERPROFILE%\CloudConnector\SiteRoot.</span></span> <span data-ttu-id="04633-129">应将默认位置更改为在每个站点中创建的第一个设备上的文件共享。</span><span class="sxs-lookup"><span data-stu-id="04633-129">The default location should be changed to a file share on the first appliance created in each site.</span></span>

    <span data-ttu-id="04633-130">您选择的位置必须为：</span><span class="sxs-lookup"><span data-stu-id="04633-130">The location you select must be:</span></span>

   - <span data-ttu-id="04633-131">在每个站点中创建的第一个设备上创建。</span><span class="sxs-lookup"><span data-stu-id="04633-131">Created on the first appliance created in each site.</span></span>

   - <span data-ttu-id="04633-132">同一站点中的其他主机服务器（设备）可访问的共享文件夹。</span><span class="sxs-lookup"><span data-stu-id="04633-132">A shared folder that is accessible by the other host servers (appliances) in the same site.</span></span>

     <span data-ttu-id="04633-133">若要将**网站目录**设置为默认位置以外的位置，请运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="04633-133">To set the **Site Directory** to a location other than the default, run the following cmdlet:</span></span>

   ```powershell
   Set-CcSiteDirectory <UNC File path>
   ```

    <span data-ttu-id="04633-134">如果要为网站部署高可用性（HA），请确保运行 cmdlet 以将**网站目录**设置为站点中每台主机服务器上的相同位置。</span><span class="sxs-lookup"><span data-stu-id="04633-134">If you are deploying High Availability (HA) for the site, make sure you run the cmdlet to set the **Site Directory** to the same location on each host server within the site.</span></span>

    <span data-ttu-id="04633-135">当您登录并在站点中部署每台设备时，请确保您的当前登录帐户具有对**网站目录**的正确访问权限。</span><span class="sxs-lookup"><span data-stu-id="04633-135">When you log on and deploy each appliance in the site, make sure your current logon account has the right access to the **Site Directory**.</span></span>

3. <span data-ttu-id="04633-136">**设备目录**是 Skype For Business 云连接器版本的本地工作根目录，以及保存外部证书、实例和日志的位置。</span><span class="sxs-lookup"><span data-stu-id="04633-136">The **Appliance Directory** is the local working root directory for Skype for Business Cloud Connector Edition, and the location where external certificates, instances, and logs are saved.</span></span> <span data-ttu-id="04633-137">默认位置为：%USERPROFILE%\CloudConnector\ApplianceRoot。</span><span class="sxs-lookup"><span data-stu-id="04633-137">The default location is: %USERPROFILE%\CloudConnector\ApplianceRoot.</span></span>

    <span data-ttu-id="04633-138">若要查找**设备目录**的位置，请运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="04633-138">To find the location of the **Appliance Directory**, run the following cmdlet:</span></span>

   ```powershell
   Get-CcApplianceDirectory
   ```

    <span data-ttu-id="04633-139">若要将**设备目录**设置为默认位置以外的位置，请运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="04633-139">To set the **Appliance Directory** to a location other than the default, run the following cmdlet:</span></span>

   ```powershell
   Set-CcApplianceDirectory <File path>
   ```

    <span data-ttu-id="04633-140">应将设备目录设置为设备上的本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="04633-140">The Appliance Directory should be set to a local folder on the appliance.</span></span> <span data-ttu-id="04633-141">你应仅在启动 Skype for Business 云连接器版本部署之前设置**设备目录**。</span><span class="sxs-lookup"><span data-stu-id="04633-141">You should only set the **Appliance Directory** before you start the Skype for Business Cloud Connector Edition deployment.</span></span> <span data-ttu-id="04633-142">如果在部署后更改它，则需要重新部署主机服务器。</span><span class="sxs-lookup"><span data-stu-id="04633-142">If you change it after deployment, you'll need to redeploy the host server.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="04633-143">**设备目录**的路径不能包含任何空格。</span><span class="sxs-lookup"><span data-stu-id="04633-143">The path to the **Appliance Directory** must not contain any spaces.</span></span>

## <a name="set-the-path-for-the-external-edge-certificate"></a><span data-ttu-id="04633-144">设置外部边缘证书的路径</span><span class="sxs-lookup"><span data-stu-id="04633-144">Set the path for the external Edge certificate</span></span>

- <span data-ttu-id="04633-145">运行以下 cmdlet 以设置外部边缘证书的路径，包括文件名。</span><span class="sxs-lookup"><span data-stu-id="04633-145">Run the following cmdlet to set the path, including the file name, to the external Edge certificate.</span></span> <span data-ttu-id="04633-146">例如： C:\certs\cce\ap.contoso.com.pfx。</span><span class="sxs-lookup"><span data-stu-id="04633-146">For example: C:\certs\cce\ap.contoso.com.pfx.</span></span> <span data-ttu-id="04633-147">证书必须包含私钥。</span><span class="sxs-lookup"><span data-stu-id="04633-147">The certificate must contain private keys.</span></span>

  ```powershell
  Set-CcExternalCertificateFilePath -Path <Full path to External certificate, including file name> -Target EdgeServer
  ```

    > [!NOTE]
    > <span data-ttu-id="04633-148">请注意，-Target 参数特定于1.4.2 版和更高版本。</span><span class="sxs-lookup"><span data-stu-id="04633-148">Note that the -Target parameter is specific to versions 1.4.2 and later.</span></span> 

    <span data-ttu-id="04633-149">指定外部证书的完整路径，包括文件名。</span><span class="sxs-lookup"><span data-stu-id="04633-149">Specify the full path to the external certificate, including the file name.</span></span> <span data-ttu-id="04633-150">证书可以存储在本地或文件共享中。</span><span class="sxs-lookup"><span data-stu-id="04633-150">The certificate can be stored locally or on a file share.</span></span> <span data-ttu-id="04633-151">如果证书存储在共享文件夹中，则必须在每个站点的第一个设备上创建共享文件夹，并且该共享文件夹必须可供属于同一站点的其他设备访问。</span><span class="sxs-lookup"><span data-stu-id="04633-151">If the certificate is stored in a shared folder, the shared folder must be created on the first appliance of each site and must be accessible by other appliances belonging to the same site.</span></span> <span data-ttu-id="04633-152">此 cmdlet 可将外部证书复制到**设备目录**。</span><span class="sxs-lookup"><span data-stu-id="04633-152">This cmdlet copies the external certificate to the **Appliance Directory**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="04633-153">**如果已更新到云连接器1.4.2 版或更高版本**，请确保准备好的外部证书包含私钥和完整证书链，包括根 ca 证书和中间 ca 证书。</span><span class="sxs-lookup"><span data-stu-id="04633-153">**If you have updated to Cloud Connector version 1.4.2 or later**, make sure your prepared external certificate contains private keys and the full certificate chain including the root CA certificate and the intermediate CA certificates.</span></span> <span data-ttu-id="04633-154">**如果您尚未更新云连接器1.4.2 版**，请确保准备好的外部证书包含私钥。</span><span class="sxs-lookup"><span data-stu-id="04633-154">**If you have NOT yet updated to Cloud Connector version 1.4.2**, make sure your prepared external certificate contains private keys.</span></span> <span data-ttu-id="04633-155">此外部证书必须由 Windows 默认情况下受 Windows 信任的证书颁发机构颁发。</span><span class="sxs-lookup"><span data-stu-id="04633-155">This external certificate must be issued by a Certificate Authority that is trusted by Windows by default.</span></span>

## <a name="set-the-path-for-the-external-pstn-gatewaysbc-certificate"></a><span data-ttu-id="04633-156">设置外部 PSTN 网关/SBC 证书的路径</span><span class="sxs-lookup"><span data-stu-id="04633-156">Set the path for the external PSTN gateway/SBC certificate</span></span>

<span data-ttu-id="04633-157">如果要在中介服务器和 PSTN 网关/SBC 之间使用 TLS，请运行以下 cmdlet，以将路径（包括文件名）设置为网关证书。</span><span class="sxs-lookup"><span data-stu-id="04633-157">If you are using TLS between the Mediation Server and the PSTN gateway/SBC, run the following cmdlet to set the path, including the file name, to the gateway certificate.</span></span> <span data-ttu-id="04633-158">例如： C:\certs\cce\sbc.contoso.com.cer。</span><span class="sxs-lookup"><span data-stu-id="04633-158">For example: C:\certs\cce\sbc.contoso.com.cer.</span></span> <span data-ttu-id="04633-159">证书必须包含为分配给网关的证书的根 CA 和中间链：</span><span class="sxs-lookup"><span data-stu-id="04633-159">The certificate must contain the root CA and the intermediate chain for the certificate assigned to the gateway:</span></span>

```powershell
Set-CcExternalCertificateFilePath -Path <Full path to gateway certificate, including file name> -Target MediationServer 
```

> [!NOTE]
> <span data-ttu-id="04633-160">请注意，-Target 参数特定于1.4.2 版和更高版本。</span><span class="sxs-lookup"><span data-stu-id="04633-160">Note that the -Target parameter is specific to versions 1.4.2 and later.</span></span> 

## <a name="create-virtual-switches-in-hyper-v-manager"></a><span data-ttu-id="04633-161">在 Hyper-v 管理器中创建虚拟交换机</span><span class="sxs-lookup"><span data-stu-id="04633-161">Create virtual switches in Hyper-V Manager</span></span>

1. <span data-ttu-id="04633-162">打开**hyper-v 管理器**  >  **虚拟交换机管理器**，然后选择 "**新建虚拟交换机管理器**"。</span><span class="sxs-lookup"><span data-stu-id="04633-162">Open **Hyper-V Manager** > **Virtual Switch Manager**, and select **New Virtual Switch Manager**.</span></span>

2. <span data-ttu-id="04633-163">创建外部虚拟交换机并将其绑定到连接到内部网络域的物理网络适配器：</span><span class="sxs-lookup"><span data-stu-id="04633-163">Create an External virtual switch and bind it to the physical network adapter that is connected to your internal network domain:</span></span>

    <span data-ttu-id="04633-164">为此虚拟交换机选择 "**允许管理操作系统共享此网络适配器**"。</span><span class="sxs-lookup"><span data-stu-id="04633-164">Select **Allow management operating system to share this network adapter** for this virtual switch.</span></span>

3. <span data-ttu-id="04633-165">创建外部虚拟交换机并将其绑定到路由到 Internet 的物理网络适配器：</span><span class="sxs-lookup"><span data-stu-id="04633-165">Create an External virtual switch and bind it to the physical network adapter that is routed to the Internet:</span></span>

    <span data-ttu-id="04633-166">取消选择 "**允许管理操作系统为此虚拟交换机共享此网络适配器**"。</span><span class="sxs-lookup"><span data-stu-id="04633-166">De-select **Allow management operating system to share this network adapter** for this virtual switch.</span></span>

4. <span data-ttu-id="04633-167">设置将外围网络连接到内部网络域的交换机的名称**SFB CCE 公司网络交换机**。</span><span class="sxs-lookup"><span data-stu-id="04633-167">Set the name of the switch that connects your perimeter network to your internal network domain **SfB CCE Corpnet Switch**.</span></span>

    <span data-ttu-id="04633-168">设置将外围网络连接到 Internet **SFB CCE Internet 交换机**的交换机的名称。</span><span class="sxs-lookup"><span data-stu-id="04633-168">Set the name of the switch that connects your perimeter network to the Internet **SfB CCE Internet Switch**.</span></span>

## <a name="update-the-cloudconnectorini-configuration-file"></a><span data-ttu-id="04633-169">更新 Cloudconnector.ini 配置文件</span><span class="sxs-lookup"><span data-stu-id="04633-169">Update the CloudConnector.ini configuration file</span></span>

<span data-ttu-id="04633-170">使用在[Plan For Skype For Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md)主题中的[确定部署参数](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams)中收集的信息准备 cloudconnector.ini 文件。</span><span class="sxs-lookup"><span data-stu-id="04633-170">Prepare the CloudConnector.ini file using the information you gathered in [Determine deployment parameters](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) in the [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) topic.</span></span>

<span data-ttu-id="04633-171">若要更新该文件，请先运行以下 cmdlet 以获取示例模板（Cloudconnector.ini）：</span><span class="sxs-lookup"><span data-stu-id="04633-171">To update the file, first run the following cmdlet to get the sample template (CloudConnector.Sample.ini):</span></span>

```powershell
Export-CcConfigurationSampleFile
```

<span data-ttu-id="04633-172">示例模板存储在**设备目录**中。</span><span class="sxs-lookup"><span data-stu-id="04633-172">The sample template is stored in the **Appliance Directory**.</span></span>

<span data-ttu-id="04633-173">在使用您的环境的值对其进行更新之后，请在**设备目录**中将该文件另存为 cloudconnector.ini。</span><span class="sxs-lookup"><span data-stu-id="04633-173">After you update it with the values for your environment, save the file as CloudConnector.ini in the **Appliance Directory**.</span></span> <span data-ttu-id="04633-174">您可以运行**set-ccappliancedirectory**以确定**设备目录**的路径。</span><span class="sxs-lookup"><span data-stu-id="04633-174">You can run **Get-CcApplianceDirectory** to determine the path to the **Appliance Directory**.</span></span>

<span data-ttu-id="04633-175">更新 .ini 文件时，请考虑以下事项：</span><span class="sxs-lookup"><span data-stu-id="04633-175">When updating the .ini file, consider the following:</span></span>

> [!NOTE]
> <span data-ttu-id="04633-176">并非 .ini 文件的所有值都在此部分中进行讨论，此处仅介绍了那些具有特殊注意事项的值。</span><span class="sxs-lookup"><span data-stu-id="04633-176">Not all values for the .ini file are discussed in this section, only those with a special consideration are covered here.</span></span> <span data-ttu-id="04633-177">有关完整列表，请参阅[Plan For Skype For Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md)主题中的 "[确定部署参数](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams)" 部分。</span><span class="sxs-lookup"><span data-stu-id="04633-177">For a full list, see the [Determine deployment parameters](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) section of the [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) topic.</span></span> <span data-ttu-id="04633-178">有关需要为其他设备或新网站更改的值的详细信息，请参阅在[云连接器中部署多个站点](deploy-multiple-sites-in-cloud-connector.md)中[与多站点部署相比的具有高可用性（HA）的单站点部署](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site)。</span><span class="sxs-lookup"><span data-stu-id="04633-178">For more information about what values need to be changed for additional appliances or new sites, see [Single site with High Availability (HA) compared to multi-site deployments](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site) in the topic [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 

- <span data-ttu-id="04633-179">**SiteName：** 默认值为**Site1**。</span><span class="sxs-lookup"><span data-stu-id="04633-179">**SiteName:** The default value is **Site1**.</span></span> <span data-ttu-id="04633-180">您必须在部署云连接器之前对其进行更新，因为在运行**register-ccappliance**将设备注册到现有或新网站时，cmdlet 将使用**SiteName**确定要注册的网站。</span><span class="sxs-lookup"><span data-stu-id="04633-180">You must update it before you deploy Cloud Connector, because when you run **Register-CcAppliance** to register an appliance to an existing or new site, the cmdlet will use **SiteName** to determine which site to register.</span></span>

     <span data-ttu-id="04633-181">如果要将设备注册到新网站， **SiteName**的值必须是唯一的，并且不同于现有网站。</span><span class="sxs-lookup"><span data-stu-id="04633-181">If you want to register the appliance to a new site, the value of **SiteName** must be unique and different from existing sites.</span></span> <span data-ttu-id="04633-182">如果要将设备注册到现有站点，则 .ini 文件中的**SiteName**的值必须与在 Microsoft 365 或 Office 365 组织配置中定义的名称相匹配。</span><span class="sxs-lookup"><span data-stu-id="04633-182">If you want to register the appliance to an existing site, the value for **SiteName** in .ini file must match the name defined in your Microsoft 365 or Office 365 organization configuration.</span></span> <span data-ttu-id="04633-183">如果要将配置文件从一个网站复制到另一个网站，请确保相应地为每个网站更新**SiteName**的值。</span><span class="sxs-lookup"><span data-stu-id="04633-183">If you are copying a configuration file from one site to another, make sure you update the value for **SiteName** for each site accordingly.</span></span>

- <span data-ttu-id="04633-184">**ServerName：** 服务器名称不应包含域名，且不应超过15个字符。</span><span class="sxs-lookup"><span data-stu-id="04633-184">**ServerName:** The server name should not contain the domain name and should be limited to 15 characters.</span></span>

- <span data-ttu-id="04633-185">**HardwareType：** 如果不设置或将值保留为 null，则将使用默认值**Normal** 。</span><span class="sxs-lookup"><span data-stu-id="04633-185">**HardwareType:** If you don't set or leave the value to null, the default value of **Normal** will be used.</span></span> <span data-ttu-id="04633-186">如果您计划部署更大版本的云连接器以支持按[plan For Skype for Business 云连接器版本](plan-skype-for-business-cloud-connector-edition.md)中所述，每台主机同时支持500并发呼叫，请使用**Normal** 。</span><span class="sxs-lookup"><span data-stu-id="04633-186">Use **Normal** if you plan to deploy the larger version of Cloud Connector to support 500 simultaneous calls per host machine as described in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span> <span data-ttu-id="04633-187">对支持同时调用50的较小部署使用**最小值**。</span><span class="sxs-lookup"><span data-stu-id="04633-187">Use **Minimum** for a smaller deployment that supports 50 simultaneous calls.</span></span>

- <span data-ttu-id="04633-188">**Internet/公司网络/管理虚拟交换机：**：添加已创建的虚拟交换机的名称。</span><span class="sxs-lookup"><span data-stu-id="04633-188">**Internet/Corpnet/Management virtual switches:**: Add the name of the virtual switches you have created.</span></span> <span data-ttu-id="04633-189">对于管理虚拟交换机，保留默认值。</span><span class="sxs-lookup"><span data-stu-id="04633-189">For the management virtual switch, leave the default value.</span></span> <span data-ttu-id="04633-190">部署脚本将在部署开始时创建管理虚拟交换机，并在部署完成后将其删除。</span><span class="sxs-lookup"><span data-stu-id="04633-190">The deployment script will create the management virtual switch at the beginning of deployment and delete it when the deployment finishes.</span></span>

- <span data-ttu-id="04633-191">**ManagementIPPrefix：**"网络" 部分中的 ManagementIPPrefix 必须是其他内部 Ip 的不同子网。</span><span class="sxs-lookup"><span data-stu-id="04633-191">**ManagementIPPrefix:** ManagementIPPrefix in the Network section must be a different subnet from other internal IPs.</span></span> <span data-ttu-id="04633-192">例如，默认值为 ManagementIPPrefix 为192.168.213.0，而 AD IPAddress 为192.168.0.238。</span><span class="sxs-lookup"><span data-stu-id="04633-192">For example, as the default value shows, ManagementIPPrefix is 192.168.213.0, while AD IPAddress is 192.168.0.238.</span></span>

    <span data-ttu-id="04633-193">部署脚本在每个虚拟机上创建一个管理网络适配器，分配一个管理 IP，并将其连接到管理虚拟交换机。</span><span class="sxs-lookup"><span data-stu-id="04633-193">The deployment scripts create a management network adapter on each virtual machine, assign a management IP, and connect it to a management virtual switch.</span></span> <span data-ttu-id="04633-194">这使主机服务器可以通过此管理网络连接并管理每个虚拟机。</span><span class="sxs-lookup"><span data-stu-id="04633-194">This enables the host server to connect to and manage each virtual machine via this management network.</span></span> <span data-ttu-id="04633-195">部署完成后，将删除管理虚拟交换机。</span><span class="sxs-lookup"><span data-stu-id="04633-195">The management virtual switch is deleted when the deployment is finished.</span></span>

- <span data-ttu-id="04633-196">**基本虚拟机特定配置：** 必须为**convert-ccisotovhdx** cmdlet 配置本节中的设置。</span><span class="sxs-lookup"><span data-stu-id="04633-196">**Base VM specific configurations:** Settings in this section must be configured for the **Convert-CcIsoToVhdx** cmdlet.</span></span>

    <span data-ttu-id="04633-197">在基本 VM 映像准备期间，基本虚拟机将连接到内部网络交换机。</span><span class="sxs-lookup"><span data-stu-id="04633-197">During base VM image preparation, the base VM will be connected to the internal network switch.</span></span> <span data-ttu-id="04633-198">若要使 VM 能够访问 Internet，以下设置至关重要：</span><span class="sxs-lookup"><span data-stu-id="04633-198">The following settings are critical for the VM to be able to access the Internet:</span></span>

  - <span data-ttu-id="04633-199">共BaseVMIP：要分配给基本虚拟机的企业网络 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="04633-199">[Common]BaseVMIP: the corpnet IP address to be assigned to the base VM.</span></span>

  - <span data-ttu-id="04633-200">NetworkCorpnetDefaultGateway：要分配给基本虚拟机的默认网关。</span><span class="sxs-lookup"><span data-stu-id="04633-200">[Network]CorpnetDefaultGateway: the default gateway to be assigned to the base VM.</span></span>

  - <span data-ttu-id="04633-201">NetworkCorpnetDNSIPAddress：要分配给基本虚拟机的 DNS IP 地址。</span><span class="sxs-lookup"><span data-stu-id="04633-201">[Network]CorpnetDNSIPAddress: the DNS IP address to be assigned to the base VM.</span></span>

  - <span data-ttu-id="04633-202">NetworkWSUSServer： Windows Server Update Service 的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="04633-202">[Network]WSUSServer: the IP address of Windows Server Update Service.</span></span>

  - <span data-ttu-id="04633-203">NetworkWSUSStatusServer： Windows Server Update Service 状态服务器的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="04633-203">[Network]WSUSStatusServer: the IP address of Windows Server Update Service status server.</span></span>

  - <span data-ttu-id="04633-204">NetworkEnableReferSupport：此操作将定义是否在 IP/PBX 的中继配置上启用或禁用 SIP。</span><span class="sxs-lookup"><span data-stu-id="04633-204">[Network]EnableReferSupport: this will define whether SIP REFER support is enabled or disabled on the Trunk Configuration to your IP/PBX.</span></span>

- <span data-ttu-id="04633-205">**内部 Ip：**</span><span class="sxs-lookup"><span data-stu-id="04633-205">**Internal IPs:**</span></span>

  - <span data-ttu-id="04633-206">请确保子网掩码 CorpnetIPPrefixLength 正确无误。</span><span class="sxs-lookup"><span data-stu-id="04633-206">Make sure subnet mask CorpnetIPPrefixLength is correct.</span></span>

  - <span data-ttu-id="04633-207">请确保这些内部 Ip 没有 IP 冲突。</span><span class="sxs-lookup"><span data-stu-id="04633-207">Make sure there are no IP conflicts for these internal IPs.</span></span>

- <span data-ttu-id="04633-208">**外部 Ip：**</span><span class="sxs-lookup"><span data-stu-id="04633-208">**External IPs:**</span></span>

  - <span data-ttu-id="04633-209">对于尊敬的公共 IP，请为非 NAT 或 ExternalMRPublicIPs 指定 ExternalMRIPs for NAT。</span><span class="sxs-lookup"><span data-stu-id="04633-209">For MR public IP: specify either ExternalMRIPs for non-NAT or ExternalMRPublicIPs for NAT.</span></span>

  - <span data-ttu-id="04633-210">ExternalSIPIPs 和 ExternalMRIPs 可以相同。</span><span class="sxs-lookup"><span data-stu-id="04633-210">ExternalSIPIPs and ExternalMRIPs can be the same.</span></span>

  - <span data-ttu-id="04633-211">请确保子网掩码 InternetIPPrefixLength 正确无误。</span><span class="sxs-lookup"><span data-stu-id="04633-211">Make sure subnet mask InternetIPPrefixLength is correct.</span></span>

  - <span data-ttu-id="04633-212">请确保这些外部 Ip 没有 IP 冲突。</span><span class="sxs-lookup"><span data-stu-id="04633-212">Make sure there are no IP conflicts for these external IPs.</span></span>

- <span data-ttu-id="04633-213">**版**</span><span class="sxs-lookup"><span data-stu-id="04633-213">**Gateways:**</span></span>

  - <span data-ttu-id="04633-214">如果只有一个网关，请删除辅助网关的部分。</span><span class="sxs-lookup"><span data-stu-id="04633-214">If you have only one gateway, remove the section for the secondary gateway.</span></span> <span data-ttu-id="04633-215">如果您有两个以上的网关，请通过复制并粘贴现有分区并将其更新来创建其他分区。</span><span class="sxs-lookup"><span data-stu-id="04633-215">If you have more than two gateways, create additional sections by copying and pasting the existing one and then updating it.</span></span>

  - <span data-ttu-id="04633-216">请确保网关的 IP 地址和端口正确无误。</span><span class="sxs-lookup"><span data-stu-id="04633-216">Make sure that the IP address and port of the gateway(s) are correct.</span></span>

  - <span data-ttu-id="04633-217">若要支持 PSTN 网关级别 HA，请保留辅助网关，然后添加将使用的任何其他网关。</span><span class="sxs-lookup"><span data-stu-id="04633-217">To support PSTN gateway level HA, leave the secondary gateway, and add any additional gateways you will use.</span></span> <span data-ttu-id="04633-218">您可以复制并粘贴现有条目，然后对其进行更新。</span><span class="sxs-lookup"><span data-stu-id="04633-218">You can copy and paste an existing entry and then update it.</span></span>

- <span data-ttu-id="04633-219">（可选）您可以更新 LocalRoute 值以限制出站呼叫号码。</span><span class="sxs-lookup"><span data-stu-id="04633-219">Optionally, you can update the LocalRoute value to restrict outbound call numbers.</span></span>

## <a name="download-the-bits-to-the-site-directory"></a><span data-ttu-id="04633-220">将 bits 下载到网站目录</span><span class="sxs-lookup"><span data-stu-id="04633-220">Download the bits to the Site Directory</span></span>

<span data-ttu-id="04633-221">运行以下 cmdlet 以将 bits 和版本信息文件下载到**网站目录**：</span><span class="sxs-lookup"><span data-stu-id="04633-221">Run the following cmdlet to download the bits and version information files to the **Site Directory**:</span></span>

```powershell
Start-CcDownload
```

> [!NOTE]
> <span data-ttu-id="04633-222">只需为第一台设备执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="04633-222">You need to perform this step for the first appliance only.</span></span> 

## <a name="prepare-base-virtual-disk-vhdx-from-the-downloaded-iso-file"></a><span data-ttu-id="04633-223">从下载的 ISO 文件准备基本虚拟磁盘（VHDX）</span><span class="sxs-lookup"><span data-stu-id="04633-223">Prepare base virtual disk (VHDX) from the downloaded ISO file</span></span>

<span data-ttu-id="04633-224">此步骤将从 Windows Server 2012 ISO 映像准备虚拟硬盘（VHDX）文件。</span><span class="sxs-lookup"><span data-stu-id="04633-224">This step prepares a virtual hard disk (VHDX) file from the Windows Server 2012 ISO image.</span></span> <span data-ttu-id="04633-225">VHDX 将用于在部署过程中创建虚拟机。</span><span class="sxs-lookup"><span data-stu-id="04633-225">The VHDX will be used to create virtual machines during deployment.</span></span> <span data-ttu-id="04633-226">将创建一个临时虚拟机（基本虚拟机），并从 ISO 文件安装 Windows Server 2012。</span><span class="sxs-lookup"><span data-stu-id="04633-226">A temporary virtual machine (base VM) will be created and Windows Server 2012 will be installed from the ISO file.</span></span> <span data-ttu-id="04633-227">创建虚拟机后，将会安装一些必要的组件，并将应用最新的 Windows 更新。</span><span class="sxs-lookup"><span data-stu-id="04633-227">After the VM is created, some necessary components will be installed and the latest Windows update will be applied.</span></span> <span data-ttu-id="04633-228">最终，基本虚拟机将进行一般化（sysprep）和清理，仅留下生成的虚拟磁盘文件。</span><span class="sxs-lookup"><span data-stu-id="04633-228">At the end, the base VM will be generalized (sysprep) and cleaned up, leaving only the generated virtual disk file.</span></span>

> [!NOTE]
> <span data-ttu-id="04633-229">只需为第一台设备执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="04633-229">You need to perform this step for the first appliance only.</span></span> 

<span data-ttu-id="04633-230">在继续执行此步骤之前，请确保已创建公司网络交换机。</span><span class="sxs-lookup"><span data-stu-id="04633-230">Before proceeding with this step, make sure that the corpnet switch is created.</span></span> <span data-ttu-id="04633-231">此外，请确认 Cloudconnector.ini 文件中正确配置了以下设置：</span><span class="sxs-lookup"><span data-stu-id="04633-231">Also, confirm that the following settings are correctly configured in the CloudConnector.ini file:</span></span>

- <span data-ttu-id="04633-232">NetworkCorpnetSwitchName</span><span class="sxs-lookup"><span data-stu-id="04633-232">[Network]CorpnetSwitchName</span></span>

- <span data-ttu-id="04633-233">共BaseVMIP</span><span class="sxs-lookup"><span data-stu-id="04633-233">[Common]BaseVMIP</span></span>

- <span data-ttu-id="04633-234">NetworkCorpnetIPPrefixLength</span><span class="sxs-lookup"><span data-stu-id="04633-234">[Network]CorpnetIPPrefixLength</span></span>

- <span data-ttu-id="04633-235">NetworkCorpnetDefaultGateway</span><span class="sxs-lookup"><span data-stu-id="04633-235">[Network]CorpnetDefaultGateway</span></span>

- <span data-ttu-id="04633-236">NetworkCorpnetDNSIPAddress</span><span class="sxs-lookup"><span data-stu-id="04633-236">[Network]CorpnetDNSIPAddress</span></span>

<span data-ttu-id="04633-237">以管理员身份启动 PowerShell 控制台，并运行以下 cmdlet 以将 ISO 映像转换为虚拟硬盘（VHD）：</span><span class="sxs-lookup"><span data-stu-id="04633-237">Start a PowerShell console as administrator and run the following cmdlet to convert the ISO image to a virtual hard disk (VHD):</span></span>

```powershell
Convert-CcIsoToVhdx -IsoFilePath <Windows ISO File Path, including file name>
```

<span data-ttu-id="04633-238">指定 ISO 映像的完整路径，包括文件名。</span><span class="sxs-lookup"><span data-stu-id="04633-238">Specify the full path, including file name, to the ISO image.</span></span> <span data-ttu-id="04633-239">例如： C:\ISO\WindowsServer2012R2.iso。</span><span class="sxs-lookup"><span data-stu-id="04633-239">For example: C:\ISO\WindowsServer2012R2.iso.</span></span>

<span data-ttu-id="04633-240">创建的 VHD 文件存储在 "**网站目录**" \Bits\VHD 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="04633-240">The created VHD file is stored in the **Site Directory** \Bits\VHD folder.</span></span> <span data-ttu-id="04633-241">您可以通过运行**get-ccsitedirectory**获取**网站目录**的路径。</span><span class="sxs-lookup"><span data-stu-id="04633-241">You can get the path to the **Site Directory** by running the **Get-CcSiteDirectory**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="04633-242">默认情况下，不会在基本虚拟机上配置代理设置。</span><span class="sxs-lookup"><span data-stu-id="04633-242">By default, proxy settings are not configured on the base VM.</span></span> <span data-ttu-id="04633-243">如果网络环境中需要代理通过 Windows 更新来更新 VM，则应在运行 "Convert-ccisotovhdx" 时添加-PauseBeforeUpdate 开关。</span><span class="sxs-lookup"><span data-stu-id="04633-243">If a proxy is required in your network environment to update the VM via Windows Update, you should add the -PauseBeforeUpdate switch when you run "Convert-CcIsoToVhdx".</span></span> <span data-ttu-id="04633-244">脚本将在 Windows 更新之前暂停，并且你将有机会在 VM 上手动设置代理。</span><span class="sxs-lookup"><span data-stu-id="04633-244">The script will pause before Windows Update and you'll have a chance to manually set up proxy on the VM.</span></span> <span data-ttu-id="04633-245">在设置代理且 VM 可以访问 Internet 后，可以恢复脚本以完成其余步骤。</span><span class="sxs-lookup"><span data-stu-id="04633-245">After the proxy is setup and the VM can access Internet, you can resume the script to complete the remaining steps.</span></span> 

### <a name="create-vhds-for-a-multi-site-deployment"></a><span data-ttu-id="04633-246">为多站点部署创建 Vhd</span><span class="sxs-lookup"><span data-stu-id="04633-246">Create VHDs for a multi-site deployment</span></span>

<span data-ttu-id="04633-247">这是一个仅适用于多站点部署的可选步骤。</span><span class="sxs-lookup"><span data-stu-id="04633-247">This is an optional step that applies only to multi-site deployments.</span></span>

<span data-ttu-id="04633-248">如果要部署多站点部署，则无需将 ISO 转换为每个站点的 VHD。</span><span class="sxs-lookup"><span data-stu-id="04633-248">If you are deploying a multi-site deployment, you do not need to convert the ISO to a VHD for each site.</span></span> <span data-ttu-id="04633-249">您可以将为第一个站点创建的 VHDX 复制到第二个站点的主机服务器。</span><span class="sxs-lookup"><span data-stu-id="04633-249">You can copy the VHDX created for the first site to the host server for a second site.</span></span>

 <span data-ttu-id="04633-250">将该文件复制到主机服务器上的相同文件位置（**网站目录**\Bits\VHD 文件夹），并使用相同的文件名在其他站点的主机服务器上。</span><span class="sxs-lookup"><span data-stu-id="04633-250">Copy the file to the same file location ( **Site Directory** \Bits\VHD folder), and with the same file name, on the host server for an additional site.</span></span>

## <a name="set-the-powershell-execution-policy-to-remotesigned"></a><span data-ttu-id="04633-251">将 PowerShell 执行策略设置为 RemoteSigned</span><span class="sxs-lookup"><span data-stu-id="04633-251">Set the PowerShell Execution policy to RemoteSigned</span></span>

<span data-ttu-id="04633-252">提供的 PowerShell 脚本要求将执行策略设置为 RemoteSigned。</span><span class="sxs-lookup"><span data-stu-id="04633-252">The PowerShell scripts provided require that the execution policy be set to RemoteSigned.</span></span> <span data-ttu-id="04633-253">若要查看当前设置，请以管理员身份打开 PowerShell 控制台，然后运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="04633-253">To see the current setting, open a PowerShell console as administrator and then run the following cmdlet:</span></span>

```powershell
Get-ExecutionPolicy
```

<span data-ttu-id="04633-254">如果未设置为 "RemoteSigned"，请运行以下 cmdlet 来更改它：</span><span class="sxs-lookup"><span data-stu-id="04633-254">If it is not set to "RemoteSigned," run the following cmdlet to change it:</span></span>

```powershell
Set-ExecutionPolicy RemoteSigned
```

## <a name="change-local-group-policy-on-the-host-machine-versions-141-and-earlier"></a><span data-ttu-id="04633-255">更改主机上的本地组策略（版本1.4.1 和更早版本）</span><span class="sxs-lookup"><span data-stu-id="04633-255">Change local Group Policy on the host machine (versions 1.4.1 and earlier)</span></span>

> [!NOTE]
> <span data-ttu-id="04633-256">云连接器版本1.4.2 和更高版本不需要执行此任务。</span><span class="sxs-lookup"><span data-stu-id="04633-256">This task is not required for Cloud Connector versions 1.4.2 and later.</span></span> 

<span data-ttu-id="04633-257">在 Skype for Business 云连接器版本部署过程中，将创建 CceService 帐户。</span><span class="sxs-lookup"><span data-stu-id="04633-257">The CceService account is created during the Skype for Business Cloud Connector Edition deployment.</span></span> <span data-ttu-id="04633-258">它运行云连接器管理服务，并需要具有卸载 cloudconnector.ini 的权限。</span><span class="sxs-lookup"><span data-stu-id="04633-258">It runs the Cloud Connector Management Service and requires permission to uninstall the cloudconnector.msi.</span></span> <span data-ttu-id="04633-259">您必须更改云连接器主机上的组策略设置，以指定用户注销时不应卸载用户注册表。</span><span class="sxs-lookup"><span data-stu-id="04633-259">You must change the group policy setting on the Cloud Connector host machine to specify that the user registry should not be unloaded when the user logs off.</span></span> <span data-ttu-id="04633-260">请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="04633-260">Follow the steps below:</span></span>

### <a name="to-change-the-group-policy-setting"></a><span data-ttu-id="04633-261">更改组策略设置</span><span class="sxs-lookup"><span data-stu-id="04633-261">To change the Group Policy setting</span></span>

1. <span data-ttu-id="04633-262">通过运行 gpedit.msc 打开**组策略编辑器**。</span><span class="sxs-lookup"><span data-stu-id="04633-262">Open the **Group Policy Editor** by running gpedit.msc.</span></span>

2. <span data-ttu-id="04633-263">在 "**组策略编辑器**" 中，导航到 "管理模板" > System > UserProfile > 不要在用户注销时强制卸载用户注册表。</span><span class="sxs-lookup"><span data-stu-id="04633-263">In the **Group Policy Editor**, navigate to Administrative Templates > System > UserProfile > Do not forcefully unload the user registry at user logoff.</span></span> 

3. <span data-ttu-id="04633-264">将其值设置为 "**启用**"。</span><span class="sxs-lookup"><span data-stu-id="04633-264">Set its value to **Enabled**.</span></span>

## <a name="set-up-your-microsoft-365-or-office-365-organization"></a><span data-ttu-id="04633-265">设置你的 Microsoft 365 或 Office 365 组织</span><span class="sxs-lookup"><span data-stu-id="04633-265">Set up your Microsoft 365 or Office 365 organization</span></span>

<span data-ttu-id="04633-266">具有 Skype for Business Online 和电话系统的 Microsoft 365 或 Office 365 组织是必需的。</span><span class="sxs-lookup"><span data-stu-id="04633-266">A Microsoft 365 or Office 365 organization with Skype for Business Online and Phone System is required.</span></span> <span data-ttu-id="04633-267">在尝试使用云连接器之前，请确保已设置并配置租户。</span><span class="sxs-lookup"><span data-stu-id="04633-267">Make sure your tenant is set up and configured before attempting to use Cloud Connector.</span></span>

<span data-ttu-id="04633-268">某些 Microsoft 365 和 Office 365 安装步骤要求使用租户远程 PowerShell （TRPS）配置 Microsoft 365 或 Office 365 组织。</span><span class="sxs-lookup"><span data-stu-id="04633-268">Some Microsoft 365 and Office 365 setup steps require you to use Tenant Remote PowerShell (TRPS) to configure your Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="04633-269">**此项应安装在主机服务器上。**</span><span class="sxs-lookup"><span data-stu-id="04633-269">**This should be installed on the host server.**</span></span> <span data-ttu-id="04633-270">您可以从： [skype For Business online、Windows PowerShell 模块](https://www.microsoft.com/download/details.aspx?id=39366)下载适用于 PowerShell 的 skype For business online 模块： Skype For business online。</span><span class="sxs-lookup"><span data-stu-id="04633-270">You can download the Skype for Business Online module for PowerShell from: [Skype for Business Online, Windows PowerShell Module](https://www.microsoft.com/download/details.aspx?id=39366).</span></span>

<span data-ttu-id="04633-271">为云连接器在线管理创建专用的 Skype for Business 管理员帐户，例如 CceOnlineManagmentAdministrator。</span><span class="sxs-lookup"><span data-stu-id="04633-271">Create a dedicated Skype for Business administrator account for Cloud Connector online management, for example CceOnlineManagmentAdministrator.</span></span> <span data-ttu-id="04633-272">设备将使用此帐户添加或删除设备、启用或禁用自动 OS 更新、启用或禁用自动二进制更新。</span><span class="sxs-lookup"><span data-stu-id="04633-272">This account will be used by appliance to add or remove appliance, enable or disable automatic OS update, enable or disable automatic binary update.</span></span> <span data-ttu-id="04633-273">将此帐户的密码设置为永不过期，这样就无需在每次过期时为其更改服务。</span><span class="sxs-lookup"><span data-stu-id="04633-273">Set the password for this account to never expire so that you do not need to change it for the service each time it expires.</span></span>


