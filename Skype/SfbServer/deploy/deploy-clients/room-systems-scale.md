---
title: 使用 System Center Configuration Manager 部署 Skype 会议室系统
ms.author: jambirk
author: jambirk
ms.reviewer: Turgayo
manager: serdars
ms.date: 5/10/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: 阅读此主题以了解有关部署在大型部署的 Skype 会议室系统 v2 的信息。
ms.openlocfilehash: 3602422779a405376893a3a7e6663520ed6a4a4c
ms.sourcegitcommit: e378b8652be6319755a04eb820761364c7faa916
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/22/2019
ms.locfileid: "30210871"
---
# <a name="deploy-skype-room-systems-v2-by-using-system-center-configuration-manager"></a><span data-ttu-id="836bb-103">使用 System Center Configuration Manager 部署 Skype 会议室系统 v2</span><span class="sxs-lookup"><span data-stu-id="836bb-103">Deploy Skype Room Systems v2 by using System Center Configuration Manager</span></span>

<span data-ttu-id="836bb-104">本文为您提供了所有必要的信息以创建 Skype 会议室系统 v2 部署通过使用 System Center Configuration Manager。</span><span class="sxs-lookup"><span data-stu-id="836bb-104">This article gives you all the necessary information to create your Skype Room Systems v2 deployments by using System Center Configuration Manager.</span></span>

<span data-ttu-id="836bb-105">与提供的 System Center Configuration Manager 中的简单易用的方法，您可以部署操作系统和其他应用程序到多个目标设备。</span><span class="sxs-lookup"><span data-stu-id="836bb-105">With the easy-to-use methods provided by System Center Configuration Manager, you can deploy the operating system and other applications to multiple target devices.</span></span>

<span data-ttu-id="836bb-106">使用指导您完成您的配置管理器配置，如下所示的方法和自定义的示例包和脚本提供整个本指南中，根据需要为您的组织。</span><span class="sxs-lookup"><span data-stu-id="836bb-106">Use the approach illustrated below to guide you through your Configuration Manager configuration, and customize the sample packages and scripts provided throughout this guidance as needed for your organization.</span></span>

![使用 Configuration Manager Skype 会议室系统 v2 部署过程](../../media/room-systems-scale-image1.png)

> [!IMPORTANT]
> <span data-ttu-id="836bb-108">仅基于 Surface Pro 部署已测试此解决方案。</span><span class="sxs-lookup"><span data-stu-id="836bb-108">This solution has only been tested with Surface Pro–based deployments.</span></span> <span data-ttu-id="836bb-109">按照配置非基于 Surface Pro 的制造商的指南。</span><span class="sxs-lookup"><span data-stu-id="836bb-109">Follow the manufacturer’s guidelines for configurations that aren’t based on Surface Pro.</span></span>

## <a name="validate-prerequisites"></a><span data-ttu-id="836bb-110">验证先决条件</span><span class="sxs-lookup"><span data-stu-id="836bb-110">Validate prerequisites</span></span>

<span data-ttu-id="836bb-111">若要部署 Skype 会议室系统 v2 使用配置管理器中，确保您满足以下先决条件和要求。</span><span class="sxs-lookup"><span data-stu-id="836bb-111">To deploy Skype Room Systems v2 with Configuration Manager, ensure that you meet the following prerequisites and requirements.</span></span>

### <a name="system-center-configuration-manager-requirements"></a><span data-ttu-id="836bb-112">System Center Configuration Manager 要求</span><span class="sxs-lookup"><span data-stu-id="836bb-112">System Center Configuration Manager requirements</span></span>

-   <span data-ttu-id="836bb-113">System Center Configuration Manager 版本必须至少 1706年或以上。</span><span class="sxs-lookup"><span data-stu-id="836bb-113">System Center Configuration Manager version must be at least 1706 or above.</span></span> <span data-ttu-id="836bb-114">我们建议使用 1710年或更高版本。</span><span class="sxs-lookup"><span data-stu-id="836bb-114">We recommend using 1710 or later.</span></span> <span data-ttu-id="836bb-115">签出[System Center Configuration Manager 中支持的 10 Windows](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client)若要了解有关配置管理器支持的 Windows 10 版本。</span><span class="sxs-lookup"><span data-stu-id="836bb-115">Check out [Support for Windows 10 in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) to learn about the Windows 10 versions that Configuration Manager supports.</span></span>

-   <span data-ttu-id="836bb-116">必须安装 Windows 评估和部署工具包 (ADK) Windows 10 的受支持的版本。</span><span class="sxs-lookup"><span data-stu-id="836bb-116">A supported version of Windows Assessment and Deployment Kit (ADK) for Windows 10 must be installed.</span></span> <span data-ttu-id="836bb-117">请参阅[Windows 10 ADK](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-adk) ，您可以使用不同版本的配置管理器中，并确保您的部署包括正确版本的版本。</span><span class="sxs-lookup"><span data-stu-id="836bb-117">See the versions of the [Windows 10 ADK](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-adk) that you can use with different versions of Configuration Manager, and ensure that your deployment includes the correct version.</span></span>

-   <span data-ttu-id="836bb-118">网站系统服务器必须已分配了分发点角色，并应[启动前执行环境 (PXE) 支持](https://docs.microsoft.com/sccm/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network)启用网络启动部署为其启用启动映像。</span><span class="sxs-lookup"><span data-stu-id="836bb-118">The site system servers must have been assigned the distribution point role, and the boot images should be enabled for [preboot execution environment (PXE) support](https://docs.microsoft.com/sccm/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network) to enable network-initiated deployments.</span></span> <span data-ttu-id="836bb-119">如果没有启用 PXE 支持，可以将[引导介质](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network)用于您的部署。</span><span class="sxs-lookup"><span data-stu-id="836bb-119">If PXE support isn’t enabled, you can use [bootable media](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) for your deployments.</span></span>

-   <span data-ttu-id="836bb-120">网络访问帐户必须被配置为支持新的计算机 （裸机） 部署方案。</span><span class="sxs-lookup"><span data-stu-id="836bb-120">A network access account must be configured to support new computer (bare metal) deployment scenarios.</span></span> <span data-ttu-id="836bb-121">若要了解更多有关配置的网络访问帐户，请参阅[管理帐户以访问 System Center Configuration Manager 中的内容](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA)。</span><span class="sxs-lookup"><span data-stu-id="836bb-121">To learn more about the configuration of a network access account, see [Manage accounts to access content in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span></span>

-   <span data-ttu-id="836bb-122">我们建议您启用[多播的支持](https://docs.microsoft.com/sccm/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network)，如果您可能要将相同的 Skype 会议室系统 v2 图像同时部署到多个单位。</span><span class="sxs-lookup"><span data-stu-id="836bb-122">We recommend that you enable [multicast support](https://docs.microsoft.com/sccm/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network), if you’re likely to deploy the same Skype Room Systems v2 image to multiple units at the same time.</span></span>

### <a name="networking-requirements"></a><span data-ttu-id="836bb-123">网络要求</span><span class="sxs-lookup"><span data-stu-id="836bb-123">Networking requirements</span></span>

-   <span data-ttu-id="836bb-124">您的网络应该有一个动态主机配置协议 (DHCP) 服务器，配置为自动的 IP 地址分发到将在其中部署 Skype 会议室系统 v2 单位子网。</span><span class="sxs-lookup"><span data-stu-id="836bb-124">Your network should have a Dynamic Host Configuration Protocol (DHCP) server, configured for automatic IP address distribution to the subnets where Skype Room Systems v2 units will be deployed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="836bb-125">DHCP 租约持续时间必须设置为超过图像部署持续时间值。</span><span class="sxs-lookup"><span data-stu-id="836bb-125">DHCP lease duration must be set to a value longer than the image deployment duration.</span></span> <span data-ttu-id="836bb-126">否则，部署可能会失败。</span><span class="sxs-lookup"><span data-stu-id="836bb-126">Otherwise, the deployment might fail.</span></span>

-   <span data-ttu-id="836bb-127">应将您的网络，包括开关和虚拟 Lan (Vlan) 配置为支持 PXE。</span><span class="sxs-lookup"><span data-stu-id="836bb-127">Your network, including switches and virtual LANs (VLANs), should be configured to support PXE.</span></span> <span data-ttu-id="836bb-128">请参阅您的网络供应商有关 IP 帮助程序和 PXE 配置的详细信息。</span><span class="sxs-lookup"><span data-stu-id="836bb-128">Refer to your network vendor for more information about IP Helper and PXE configuration.</span></span> <span data-ttu-id="836bb-129">或者，您可以使用[可启动媒体](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network)对于您的部署，如果 PXE 支持未启用。</span><span class="sxs-lookup"><span data-stu-id="836bb-129">Alternatively, you can use [bootable media](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) for your deployments, if PXE support isn’t enabled.</span></span>

    > [!NOTE]
    > <span data-ttu-id="836bb-130">为 Surface Pro 时使用以太网适配器或 Microsoft 从扩展坞，仅支持设备，从网络 （PXE 启动） 引导。</span><span class="sxs-lookup"><span data-stu-id="836bb-130">For Surface Pro devices, booting from the network (PXE boot) is only supported when you use an Ethernet adapter or docking station from Microsoft.</span></span> <span data-ttu-id="836bb-131">第三方以太网适配器不支持与 Surface Pro PXE 启动。</span><span class="sxs-lookup"><span data-stu-id="836bb-131">Third-party Ethernet adapters don’t support PXE boot with Surface Pro.</span></span> <span data-ttu-id="836bb-132">有关详细信息，请参阅[以太网适配器和表面的部署](https://docs.microsoft.com/surface/ethernet-adapters-and-surface-device-deployment)。</span><span class="sxs-lookup"><span data-stu-id="836bb-132">See [Ethernet adapters and Surface deployment](https://docs.microsoft.com/surface/ethernet-adapters-and-surface-device-deployment) for more information.</span></span>

## <a name="configure-system-center-configuration-manager-for-operating-system-deployment"></a><span data-ttu-id="836bb-133">配置操作系统部署 System Center Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="836bb-133">Configure System Center Configuration Manager for operating system deployment</span></span>

<span data-ttu-id="836bb-134">本文假定您已有的正常运行的 System Center Configuration Manager 部署，并不需要部署和配置配置管理器从零开始的所有步骤的详细信息。</span><span class="sxs-lookup"><span data-stu-id="836bb-134">This article assumes you already have a healthy System Center Configuration Manager deployment, and doesn’t detail all the steps required to deploy and configure Configuration Manager from scratch.</span></span> <span data-ttu-id="836bb-135">[文档和配置指南](https://docs.microsoft.com/sccm/)在 System Center Configuration Manager 是很好的资源;我们建议您与这些资源开始如果您尚未尚未部署配置管理器。</span><span class="sxs-lookup"><span data-stu-id="836bb-135">The [documentation and the configuration guidance](https://docs.microsoft.com/sccm/) on the System Center Configuration Manager is a great resource; we recommend you start with these resources if you haven’t yet deployed Configuration Manager.</span></span>

<span data-ttu-id="836bb-136">以下说明用于验证正确配置了操作系统部署 (OSD) 功能。</span><span class="sxs-lookup"><span data-stu-id="836bb-136">Use the following instructions to verify that the operating system deployment (OSD) features are configured properly.</span></span>

### <a name="validate-and-upgrade-configuration-manager"></a><span data-ttu-id="836bb-137">验证并升级配置管理器</span><span class="sxs-lookup"><span data-stu-id="836bb-137">Validate and upgrade Configuration Manager</span></span>

1.  <span data-ttu-id="836bb-138">在 Configuration Manager 控制台中，转到**管理** \> **更新和服务**。</span><span class="sxs-lookup"><span data-stu-id="836bb-138">In the Configuration Manager console, go to **Administration** \> **Updates and Servicing**.</span></span>

2.  <span data-ttu-id="836bb-139">检查安装的生成和适用您尚未安装程序的更新。</span><span class="sxs-lookup"><span data-stu-id="836bb-139">Check the installed build and applicable updates that haven’t been installed yet.</span></span>

3.  <span data-ttu-id="836bb-140">查看[支持 Windows 10 中 System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client);如果您需要升级部署，请选择您想要安装的更新，然后选择**下载**。</span><span class="sxs-lookup"><span data-stu-id="836bb-140">Review [Support for Windows 10 in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client); if you need to upgrade your deployment, select the update you want to install, and then select **Download**.</span></span>

4.  <span data-ttu-id="836bb-141">下载完毕后，选择更新，，然后选择**安装更新包**。</span><span class="sxs-lookup"><span data-stu-id="836bb-141">After the download is complete, select the update, and then select **Install Update Pack**.</span></span>

### <a name="configure-distribution-points-to-support-pxe-and-multicast"></a><span data-ttu-id="836bb-142">配置为支持 PXE 和多播的分发点</span><span class="sxs-lookup"><span data-stu-id="836bb-142">Configure distribution points to support PXE and multicast</span></span>

1.  <span data-ttu-id="836bb-143">在 Configuration Manager 控制台中，转到**管理** \> **分发点**。</span><span class="sxs-lookup"><span data-stu-id="836bb-143">In the Configuration Manager console, go to **Administration** \> **Distribution Points**.</span></span>

2.  <span data-ttu-id="836bb-144">选择分发点服务器，将提供 Skype 会议室系统 v2 部署中，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="836bb-144">Select the distribution point server that will serve the Skype Room Systems v2 deployment, and then select **Properties**.</span></span>

3.  <span data-ttu-id="836bb-145">选择**PXE**选项卡，并确保启用了以下设置：</span><span class="sxs-lookup"><span data-stu-id="836bb-145">Select the **PXE** tab, and ensure that the following settings are enabled:</span></span>
    -   <span data-ttu-id="836bb-146">启用 PXE 支持的客户端</span><span class="sxs-lookup"><span data-stu-id="836bb-146">Enable PXE support for clients</span></span>
    -   <span data-ttu-id="836bb-147">允许对传入 PXE 请求做出响应此分发点</span><span class="sxs-lookup"><span data-stu-id="836bb-147">Allow this distribution point to respond to incoming PXE requests</span></span>
    -   <span data-ttu-id="836bb-148">启用未知的计算机支持</span><span class="sxs-lookup"><span data-stu-id="836bb-148">Enable unknown computer support</span></span>

4.  <span data-ttu-id="836bb-149">*可选：* 若要启用多播的支持，选择**多播**选项卡，并确保启用了以下设置：</span><span class="sxs-lookup"><span data-stu-id="836bb-149">*Optional:* To enable multicast support, select the **Multicast** tab, and ensure that the following settings are enabled:</span></span>
    -   <span data-ttu-id="836bb-150">启用多播同时将数据发送到多个客户端</span><span class="sxs-lookup"><span data-stu-id="836bb-150">Enable multicast to simultaneously send data to multiple clients</span></span>
    -   <span data-ttu-id="836bb-151">配置根据您的网络团队建议的 UDP 端口范围</span><span class="sxs-lookup"><span data-stu-id="836bb-151">Configure the UDP port range as per your network team’s recommendation</span></span>

### <a name="configure-the-network-access-account"></a><span data-ttu-id="836bb-152">配置网络访问帐户</span><span class="sxs-lookup"><span data-stu-id="836bb-152">Configure the Network Access Account</span></span>

1.  <span data-ttu-id="836bb-153">在 Configuration Manager 控制台中，转到**管理** \> **站点配置** \> **网站**，然后选择网站。</span><span class="sxs-lookup"><span data-stu-id="836bb-153">In the Configuration Manager console, go to **Administration** \> **Site Configuration** \> **Sites**, and then select the site.</span></span>

2.  <span data-ttu-id="836bb-154">在**设置**组中，选择**配置网站组件** \> **软件分发**。</span><span class="sxs-lookup"><span data-stu-id="836bb-154">In the **Settings** group, select **Configure Site Components** \> **Software Distribution**.</span></span>

3.  <span data-ttu-id="836bb-155">选择**网络访问帐户**选项卡设置备份一个或多个帐户和然后选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="836bb-155">Select the **Network Access Account** tab. Set up one or more accounts, and then select **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="836bb-156">帐户无需任何特殊权限，**从网络访问此计算机**右在分发点服务器除外。</span><span class="sxs-lookup"><span data-stu-id="836bb-156">The accounts don’t need any special rights, except for the **Access this computer from the network** right on the distribution point server.</span></span> <span data-ttu-id="836bb-157">通用域用户帐户将适用。</span><span class="sxs-lookup"><span data-stu-id="836bb-157">A generic domain user account will be appropriate.</span></span> <span data-ttu-id="836bb-158">有关详细信息，请参阅[管理帐户以访问 System Center Configuration Manager 中的内容](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA)。</span><span class="sxs-lookup"><span data-stu-id="836bb-158">For more information, see [Manage accounts to access content in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span></span>

### <a name="configure-a-boot-image"></a><span data-ttu-id="836bb-159">配置启动映像</span><span class="sxs-lookup"><span data-stu-id="836bb-159">Configure a boot image</span></span>

1.  <span data-ttu-id="836bb-160">在 Configuration Manager 控制台中，转到**软件库** \> **操作系统** \> **启动映像**。</span><span class="sxs-lookup"><span data-stu-id="836bb-160">In the Configuration Manager console, go to **Software Library** \> **Operating System** \> **Boot Images**.</span></span>

2.  <span data-ttu-id="836bb-161">选择**启动映像 (x64)**，，，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="836bb-161">Select **Boot image (x64)**, and then select **Properties**.</span></span>

3.  <span data-ttu-id="836bb-162">选择**数据源**选项卡，并启用**部署从 PXE 启用分发点此启动映像**。</span><span class="sxs-lookup"><span data-stu-id="836bb-162">Select the **Data Source** tab, and enable **Deploy this boot image from the PXE-enabled distribution point**.</span></span>

4.  <span data-ttu-id="836bb-163">选择**可选组件**选项卡安装所需的组件：</span><span class="sxs-lookup"><span data-stu-id="836bb-163">Select the **Optional Components** tab to install required components:</span></span>

    1.  <span data-ttu-id="836bb-164">选择星形图标，然后搜索为**HTML (WinPE HTA)**</span><span class="sxs-lookup"><span data-stu-id="836bb-164">Select the star icon, and search for **HTML (WinPE-HTA)**</span></span>

    2.  <span data-ttu-id="836bb-165">选择**确定**将 HTML 中的应用程序支持添加到启动映像。</span><span class="sxs-lookup"><span data-stu-id="836bb-165">Select **OK** to add HTML application support in to the boot image.</span></span>

5.  <span data-ttu-id="836bb-166">*可选：* 若要自定义部署体验，请选择**自定义**选项卡。</span><span class="sxs-lookup"><span data-stu-id="836bb-166">*Optional:* To customize the deployment experience, select the **Customization** tab.</span></span>
    -   <span data-ttu-id="836bb-167">如果您想要在部署过程中有权访问命令提示符下的，启用**命令支持 （仅测试）** 。</span><span class="sxs-lookup"><span data-stu-id="836bb-167">Enable **command support (testing only)** if you want to have access to a command prompt during the deployment.</span></span> <span data-ttu-id="836bb-168">启用后，您可以通过在部署期间随时选择**F8**启动命令提示符。</span><span class="sxs-lookup"><span data-stu-id="836bb-168">When this is enabled, you can start a command prompt by selecting **F8** at any time during the deployment.</span></span>
    -   <span data-ttu-id="836bb-169">您还可以指定在部署过程中显示自定义背景图像。</span><span class="sxs-lookup"><span data-stu-id="836bb-169">You can also specify a custom background image to be displayed during the deployment.</span></span> <span data-ttu-id="836bb-170">若要设置图像，启用**指定自定义背景图像文件 (UNC 路径**，然后选择您的背景。</span><span class="sxs-lookup"><span data-stu-id="836bb-170">To set an image, enable **Specify the custom background image file (UNC path** and select your background.</span></span>

6.  <span data-ttu-id="836bb-171">当出现提示，请选择**是**和分发到分发点更新的启动映像。</span><span class="sxs-lookup"><span data-stu-id="836bb-171">When asked, select **Yes** and distribute the updated boot image to your distribution points.</span></span>

<span data-ttu-id="836bb-172">有关详细信息，请参阅[管理启动映像使用 System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-boot-images)。</span><span class="sxs-lookup"><span data-stu-id="836bb-172">For more information, see [Manage boot images with System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-boot-images).</span></span>

> [!NOTE]
> <span data-ttu-id="836bb-173">您可以创建可引导 USB 介质启动配置管理器没有 PXE 支持的环境的任务序列基于部署。</span><span class="sxs-lookup"><span data-stu-id="836bb-173">You can create a bootable USB media to initiate Configuration Manager task sequence–based deployments for environments that have no PXE support.</span></span> <span data-ttu-id="836bb-174">可引导介质只包含启动映像、 可选 prestart 命令和其所需的文件和配置管理器二进制文件以支持到 Windows PE 启动，连接到配置管理器中的部署过程的其余部分。</span><span class="sxs-lookup"><span data-stu-id="836bb-174">The bootable media contains only the boot image, optional prestart commands and their required files, and Configuration Manager binaries to support booting into Windows PE and connecting to Configuration Manager for the rest of the deployment process.</span></span> <span data-ttu-id="836bb-175">有关详细信息，请参阅[如何创建可引导介质](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia)。</span><span class="sxs-lookup"><span data-stu-id="836bb-175">For more information, see [How to Create Bootable Media](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia).</span></span>

## <a name="create-configuration-manager-packages"></a><span data-ttu-id="836bb-176">创建配置管理器包</span><span class="sxs-lookup"><span data-stu-id="836bb-176">Create Configuration Manager packages</span></span>

<span data-ttu-id="836bb-177">配置管理器需要大量的包来部署和配置的 Skype 会议室系统 v2 单位。</span><span class="sxs-lookup"><span data-stu-id="836bb-177">Configuration Manager requires a number of packages to deploy and configure the Skype Room System v2 units.</span></span>

<span data-ttu-id="836bb-178">您需要创建并配置了下列程序包，然后将它们分发到配置管理器网站系统已分配了分发点服务器角色。</span><span class="sxs-lookup"><span data-stu-id="836bb-178">You need to create and configure the following packages, and then distribute them to the Configuration Manager site systems that have been assigned the distribution point server role.</span></span>

| <span data-ttu-id="836bb-179">**程序包名称**</span><span class="sxs-lookup"><span data-stu-id="836bb-179">**Package name**</span></span>                     | <span data-ttu-id="836bb-180">**类型**</span><span class="sxs-lookup"><span data-stu-id="836bb-180">**Type**</span></span>               | <span data-ttu-id="836bb-181">**说明**</span><span class="sxs-lookup"><span data-stu-id="836bb-181">**Description**</span></span>                                                                           |
|--------------------------------------|------------------------|-------------------------------------------------------------------------------------------|
| <span data-ttu-id="836bb-182">SR v2-SR 应用程序包</span><span class="sxs-lookup"><span data-stu-id="836bb-182">SRS v2 - SRS Application Package</span></span>     | <span data-ttu-id="836bb-183">软件包</span><span class="sxs-lookup"><span data-stu-id="836bb-183">Software package</span></span>       | <span data-ttu-id="836bb-184">包 Skype 会议室系统 v2 部署工具包</span><span class="sxs-lookup"><span data-stu-id="836bb-184">Package for the Skype Room Systems v2 deployment kit</span></span>                                      |
| <span data-ttu-id="836bb-185">SR v2-Sysprep 包</span><span class="sxs-lookup"><span data-stu-id="836bb-185">SRS v2 - Sysprep Package</span></span>             | <span data-ttu-id="836bb-186">软件包</span><span class="sxs-lookup"><span data-stu-id="836bb-186">Software package</span></span>       | <span data-ttu-id="836bb-187">自定义 Unattended.xml 配置 Skype 会议室系统 v2 单位包</span><span class="sxs-lookup"><span data-stu-id="836bb-187">Package for the custom Unattended.xml to configure Skype Room Systems v2 units</span></span>            |
| <span data-ttu-id="836bb-188">SR v2-设置 SRSComputerName 包</span><span class="sxs-lookup"><span data-stu-id="836bb-188">SRS v2 - Set-SRSComputerName Package</span></span> | <span data-ttu-id="836bb-189">软件包</span><span class="sxs-lookup"><span data-stu-id="836bb-189">Software package</span></span>       | <span data-ttu-id="836bb-190">要在部署过程中指定计算机名称的 HTML 应用程序 (HTA) 包</span><span class="sxs-lookup"><span data-stu-id="836bb-190">Package for the HTML application (HTA) to assign a computer name during the deployment</span></span>    |
| <span data-ttu-id="836bb-191">SR v2-配置 SR 安装程序</span><span class="sxs-lookup"><span data-stu-id="836bb-191">SRS v2 - Configure SRS Setup</span></span>         | <span data-ttu-id="836bb-192">软件包</span><span class="sxs-lookup"><span data-stu-id="836bb-192">Software package</span></span>       | <span data-ttu-id="836bb-193">要配置的 Skype 会议室系统 v2 应用程序部署包</span><span class="sxs-lookup"><span data-stu-id="836bb-193">Package to configure deployment of the Skype Room Systems v2 app</span></span>                          |
| <span data-ttu-id="836bb-194">SR v2-操作系统更新包</span><span class="sxs-lookup"><span data-stu-id="836bb-194">SRS v2 - OS Updates Package</span></span>          | <span data-ttu-id="836bb-195">软件包</span><span class="sxs-lookup"><span data-stu-id="836bb-195">Software package</span></span>       | <span data-ttu-id="836bb-196">包来部署必需的操作系统更新</span><span class="sxs-lookup"><span data-stu-id="836bb-196">Package to deploy mandatory operating system updates</span></span>                                      |
| <span data-ttu-id="836bb-197">SR v2-根证书包</span><span class="sxs-lookup"><span data-stu-id="836bb-197">SRS v2 - Root Certificate Package</span></span>    | <span data-ttu-id="836bb-198">软件包</span><span class="sxs-lookup"><span data-stu-id="836bb-198">Software package</span></span>       | <span data-ttu-id="836bb-199">可选-包来部署 （不需要加入域的单位） 的根证书</span><span class="sxs-lookup"><span data-stu-id="836bb-199">Optional - Package to deploy the root certificate (not required for domain-joined units)</span></span>  |
| <span data-ttu-id="836bb-200">SR v2-Microsoft OMS 代理包</span><span class="sxs-lookup"><span data-stu-id="836bb-200">SRS v2 - Microsoft OMS Agent Package</span></span> | <span data-ttu-id="836bb-201">软件包</span><span class="sxs-lookup"><span data-stu-id="836bb-201">Software package</span></span>       | <span data-ttu-id="836bb-202">可选-包来部署和配置 Microsoft 操作管理套件代理</span><span class="sxs-lookup"><span data-stu-id="836bb-202">Optional - Package to deploy and configure the Microsoft Operations Management Suite agent</span></span>|
| <span data-ttu-id="836bb-203">SR v2-WinPE 背景包</span><span class="sxs-lookup"><span data-stu-id="836bb-203">SRS v2 - WinPE Background Package</span></span>    | <span data-ttu-id="836bb-204">软件包</span><span class="sxs-lookup"><span data-stu-id="836bb-204">Software package</span></span>       | <span data-ttu-id="836bb-205">自定义背景图像用于启动映像包</span><span class="sxs-lookup"><span data-stu-id="836bb-205">Package for the custom background image to use with boot images</span></span>                           |
| <span data-ttu-id="836bb-206">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="836bb-206">Windows 10 Enterprise</span></span>                | <span data-ttu-id="836bb-207">操作系统映像</span><span class="sxs-lookup"><span data-stu-id="836bb-207">Operating system image</span></span> | <span data-ttu-id="836bb-208">操作系统安装文件 (install.wim) 包</span><span class="sxs-lookup"><span data-stu-id="836bb-208">Package for the operating system installation file (install.wim)</span></span>                          |
| <span data-ttu-id="836bb-209">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="836bb-209">Surface Pro</span></span>                          | <span data-ttu-id="836bb-210">驱动程序包</span><span class="sxs-lookup"><span data-stu-id="836bb-210">Driver package</span></span>         | <span data-ttu-id="836bb-211">设备驱动程序和用于 Microsoft Surface Pro 固件软件包</span><span class="sxs-lookup"><span data-stu-id="836bb-211">Package for the device drivers and firmware for Microsoft Surface Pro</span></span>                     |
| <span data-ttu-id="836bb-212">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="836bb-212">Surface Pro 4</span></span>                        | <span data-ttu-id="836bb-213">驱动程序包</span><span class="sxs-lookup"><span data-stu-id="836bb-213">Driver package</span></span>         | <span data-ttu-id="836bb-214">设备驱动程序和 Microsoft Surface Pro 4 的固件软件包</span><span class="sxs-lookup"><span data-stu-id="836bb-214">Package for the device drivers and firmware for Microsoft Surface Pro 4</span></span>                   |

<span data-ttu-id="836bb-215">有关详细信息，请参阅[包和程序 System Center Configuration Manager 中](https://docs.microsoft.com/sccm/apps/deploy-use/packages-and-programs)。</span><span class="sxs-lookup"><span data-stu-id="836bb-215">For more information, see [Packages and programs in System Center Configuration Manager](https://docs.microsoft.com/sccm/apps/deploy-use/packages-and-programs).</span></span>

### <a name="create-folders-for-the-package-source-files"></a><span data-ttu-id="836bb-216">创建源文件的程序包的文件夹</span><span class="sxs-lookup"><span data-stu-id="836bb-216">Create folders for the package source files</span></span>

<span data-ttu-id="836bb-217">配置管理器需要程序包源文件，它们首次创建时，它们更新的时间来组织特定的文件夹结构中。</span><span class="sxs-lookup"><span data-stu-id="836bb-217">Configuration Manager requires package source files to be organized in a specific folder structure when they’re first created and when they’re updated.</span></span>

<span data-ttu-id="836bb-218">或到主机包源文件正在使用的服务器共享的 System Center Configuration Manager 管理中心网站或主站点上创建以下文件夹结构：</span><span class="sxs-lookup"><span data-stu-id="836bb-218">Create the following folder structure on the System Center Configuration Manager central administration site or primary site, or on a server share you’re using to host package source files:</span></span>

-   <span data-ttu-id="836bb-219">SR v2-Microsoft OMS 代理包</span><span class="sxs-lookup"><span data-stu-id="836bb-219">SRS v2 - Microsoft OMS Agent Package</span></span>
-   <span data-ttu-id="836bb-220">SR v2-操作系统更新包</span><span class="sxs-lookup"><span data-stu-id="836bb-220">SRS v2 - OS Updates Package</span></span>
-   <span data-ttu-id="836bb-221">SR v2-根证书包</span><span class="sxs-lookup"><span data-stu-id="836bb-221">SRS v2 - Root Certificate Package</span></span>
-   <span data-ttu-id="836bb-222">SR v2-设置 SRSComputerName 包</span><span class="sxs-lookup"><span data-stu-id="836bb-222">SRS v2 - Set-SRSComputerName Package</span></span>
-   <span data-ttu-id="836bb-223">SR v2-SR 应用程序包</span><span class="sxs-lookup"><span data-stu-id="836bb-223">SRS v2 - SRS Application Package</span></span>
-   <span data-ttu-id="836bb-224">SR v2-配置 SR 安装程序</span><span class="sxs-lookup"><span data-stu-id="836bb-224">SRS v2 - Configure SRS Setup</span></span>
-   <span data-ttu-id="836bb-225">SR v2-Sysprep 包</span><span class="sxs-lookup"><span data-stu-id="836bb-225">SRS v2 - Sysprep Package</span></span>
-   <span data-ttu-id="836bb-226">驱动程序</span><span class="sxs-lookup"><span data-stu-id="836bb-226">Drivers</span></span>
    -   <span data-ttu-id="836bb-227">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="836bb-227">Surface Pro</span></span>
    -   <span data-ttu-id="836bb-228">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="836bb-228">Surface Pro 4</span></span>
-   <span data-ttu-id="836bb-229">操作系统</span><span class="sxs-lookup"><span data-stu-id="836bb-229">Operating Systems</span></span>
    -   <span data-ttu-id="836bb-230">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="836bb-230">Windows 10 Enterprise</span></span>

> [!TIP]
> <span data-ttu-id="836bb-231">您还可以[下载](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)和使用包括包，您需要使用，这些脚本和任务序列模板，您需要导入的文件夹结构的 zip 文件。</span><span class="sxs-lookup"><span data-stu-id="836bb-231">You may also [download](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) and use the zip file that includes the folder structure for the packages, the scripts that you need to use, and the task sequence template, that you need to import.</span></span>

### <a name="create-the-microsoft-operations-management-suite-agent-package"></a><span data-ttu-id="836bb-232">创建 Microsoft 操作管理套件代理包</span><span class="sxs-lookup"><span data-stu-id="836bb-232">Create the Microsoft Operations Management Suite agent package</span></span>

1. <span data-ttu-id="836bb-233">下载操作管理套件 X-64 代理从<https://go.microsoft.com/fwlink/?LinkId=828603>。</span><span class="sxs-lookup"><span data-stu-id="836bb-233">Download the Operations Management Suite X-64 agent from <https://go.microsoft.com/fwlink/?LinkId=828603>.</span></span>

2. <span data-ttu-id="836bb-234">通过打开命令提示符窗口并在命令提示符处输入**MMASetup AMD64.exe 无**程序包解压缩到**SR v2-Microsoft OMS 代理包**文件夹中。</span><span class="sxs-lookup"><span data-stu-id="836bb-234">Extract the package into the **SRS v2 - Microsoft OMS Agent Package** folder by opening a Command Prompt window and entering **MMASetup-AMD64.exe /C:**     at the command prompt.</span></span>

3. <span data-ttu-id="836bb-235">在 Configuration Manager 控制台中，转到**软件库** \> **应用程序管理** \> **包**以及然后选择**创建新程序包**。</span><span class="sxs-lookup"><span data-stu-id="836bb-235">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4. <span data-ttu-id="836bb-236">输入以下信息以创建包：</span><span class="sxs-lookup"><span data-stu-id="836bb-236">Enter the following information to create the package:</span></span>

   - <span data-ttu-id="836bb-237">名称<strong>: SR v2-Microsoft OMS 代理包</strong></span><span class="sxs-lookup"><span data-stu-id="836bb-237">Name<strong>: SRS v2 - Microsoft OMS Agent Package</strong></span></span>

   - <span data-ttu-id="836bb-238">制造商<strong>: Microsoft Corporation</strong></span><span class="sxs-lookup"><span data-stu-id="836bb-238">Manufacturer<strong>: Microsoft Corporation</strong></span></span>

   - <span data-ttu-id="836bb-239">版本<strong>: 8.1.11081.0</strong> （输入下载的安装文件的版本）</span><span class="sxs-lookup"><span data-stu-id="836bb-239">Version<strong>: 8.1.11081.0</strong> (enter the version of the downloaded installation file)</span></span>

   - <span data-ttu-id="836bb-240">选择**此程序包包含源文件**复选框、 **SR v2-Microsoft OMS 代理包**文件夹中，输入的路径，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="836bb-240">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Microsoft OMS Agent Package** folder, and then select **Next**.</span></span>

5. <span data-ttu-id="836bb-241">选择**不创建程序**，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="836bb-241">Select **Do not create a program**, and then select **Next**.</span></span>

6. <span data-ttu-id="836bb-242">查看**确认的设置**页，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="836bb-242">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7. <span data-ttu-id="836bb-243">选择**关闭**。</span><span class="sxs-lookup"><span data-stu-id="836bb-243">Select **Close**.</span></span>

### <a name="create-the-operating-system-updates-package"></a><span data-ttu-id="836bb-244">创建操作系统更新包</span><span class="sxs-lookup"><span data-stu-id="836bb-244">Create the operating system updates package</span></span>

1. <span data-ttu-id="836bb-245">在**SR v2-操作系统更新程序包**文件夹中，创建名为**安装 SRSv2 OS Updates.ps1**新的 PowerShell 脚本。</span><span class="sxs-lookup"><span data-stu-id="836bb-245">In the **SRS v2 - OS Updates Package** folder, create a new PowerShell script named **Install-SRSv2-OS-Updates.ps1**.</span></span>

2. <span data-ttu-id="836bb-246">将以下脚本复制到**安装 SRSv2 OS Updates.ps1**脚本。</span><span class="sxs-lookup"><span data-stu-id="836bb-246">Copy the script below into the **Install-SRSv2-OS-Updates.ps1** script.</span></span> <span data-ttu-id="836bb-247">或者，您可以从[此处](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)下载该安装 SRSv2 OS Updates.ps1 脚本。</span><span class="sxs-lookup"><span data-stu-id="836bb-247">Alternatively, you can download the Install-SRSv2-OS-Updates.ps1 script from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
   ```
   # Install-SRSv2-OS-Updates.ps1
   $strPath = split-path -parent $MyInvocation.MyCommand.Definition
   $total = gci $strPath *.msu | measure | Select-Object -expand Count
   $i = 0
   gci $strPath *.msu | ForEach-Object {
     $i++
     WUSA ""$_.FullName /quiet /norestart""
     Write-Progress -activity "Applying Mandatory Updates" -status "Installing
     $_ .. $i of $total" -percentComplete (($i / $total) * 100)
     Wait-Process -name wusa
   }
   ```
3. <span data-ttu-id="836bb-248">下载到同一文件夹的必需的 Windows 更新程序包。</span><span class="sxs-lookup"><span data-stu-id="836bb-248">Download the mandatory Windows Update packages into the same folder.</span></span>
   > [!NOTE]
   > <span data-ttu-id="836bb-249">在发布本文时，仅[KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu)是必需的。</span><span class="sxs-lookup"><span data-stu-id="836bb-249">At the time this article was published, only [KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) was required.</span></span> <span data-ttu-id="836bb-250">检查[配置 Skype 会议室系统 v2 控制台](console.md)，请参阅是否需要其他任何更新。</span><span class="sxs-lookup"><span data-stu-id="836bb-250">Check [Configure a Skype Room Systems v2 console](console.md), to see whether any other updates are required.</span></span>

4. <span data-ttu-id="836bb-251">在 Configuration Manager 控制台中，转到**软件库** \> **应用程序管理** \> **包**以及然后选择**创建新程序包**。</span><span class="sxs-lookup"><span data-stu-id="836bb-251">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

5. <span data-ttu-id="836bb-252">输入以下信息以创建包：</span><span class="sxs-lookup"><span data-stu-id="836bb-252">Enter the following information to create the package:</span></span>
   -   <span data-ttu-id="836bb-253">名称： **SR v2 – 操作系统更新包**</span><span class="sxs-lookup"><span data-stu-id="836bb-253">Name: **SRS v2 – OS Updates Package**</span></span>
   -   <span data-ttu-id="836bb-254">制造商： **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="836bb-254">Manufacturer: **Microsoft Corporation**</span></span>
   -   <span data-ttu-id="836bb-255">版本： **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="836bb-255">Version: **1.0.0**</span></span>
   -   <span data-ttu-id="836bb-256">选择**此程序包包含源文件**复选框、 **SR v2-操作系统更新程序包**文件夹中，输入的路径，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="836bb-256">Select the **This package contains source files** check box, enter the path to the **SRS v2 - OS Updates Package** folder, and then select **Next**.</span></span>

6. <span data-ttu-id="836bb-257">选择**不创建程序**，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="836bb-257">Select **Do not create a program**, and then select **Next**.</span></span>

7. <span data-ttu-id="836bb-258">查看**确认的设置**页，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="836bb-258">Review the **Confirm the settings** page, and then select **Next**.</span></span>

8. <span data-ttu-id="836bb-259">选择**关闭**。</span><span class="sxs-lookup"><span data-stu-id="836bb-259">Select **Close**.</span></span>

### <a name="create-the-root-certificate-package-optional"></a><span data-ttu-id="836bb-260">创建根证书包 （可选）</span><span class="sxs-lookup"><span data-stu-id="836bb-260">Create the root certificate package (optional)</span></span>

<span data-ttu-id="836bb-261">创建此程序包分发不会加入 Active Directory 域的设备的根证书。</span><span class="sxs-lookup"><span data-stu-id="836bb-261">You create this package to distribute the root certificate for devices that won’t be joined to an Active Directory domain.</span></span> <span data-ttu-id="836bb-262">创建此包，仅当以下条件适用：</span><span class="sxs-lookup"><span data-stu-id="836bb-262">Create this package only if both the following conditions apply:</span></span>
-   <span data-ttu-id="836bb-263">您的部署包括本地 Lync 或 Skype 业务服务器。</span><span class="sxs-lookup"><span data-stu-id="836bb-263">Your deployment includes on-premises Lync or Skype for Business Server.</span></span>
-   <span data-ttu-id="836bb-264">Skype 会议室系统 v2 单位配置为用于在工作组中而不是域成员。</span><span class="sxs-lookup"><span data-stu-id="836bb-264">Skype Room Systems v2 units are configured to work in a workgroup instead of a domain member.</span></span>

1.  <span data-ttu-id="836bb-265">将根证书复制到**SR v2 – 根证书程序包**文件夹。</span><span class="sxs-lookup"><span data-stu-id="836bb-265">Copy the root certificate into the **SRS v2 – Root Certificate Package** folder.</span></span>

2.  <span data-ttu-id="836bb-266">在 Configuration Manager 控制台中，转到**软件库** \> **应用程序管理** \> **包**以及然后选择**创建新程序包**。</span><span class="sxs-lookup"><span data-stu-id="836bb-266">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

3.  <span data-ttu-id="836bb-267">输入以下信息以创建包：</span><span class="sxs-lookup"><span data-stu-id="836bb-267">Enter the following information to create the package:</span></span>
    -   <span data-ttu-id="836bb-268">名称： **SR v2 – 根证书包**</span><span class="sxs-lookup"><span data-stu-id="836bb-268">Name: **SRS v2 – Root Certificate Package**</span></span>
    -   <span data-ttu-id="836bb-269">制造商：*贵组织的名称*</span><span class="sxs-lookup"><span data-stu-id="836bb-269">Manufacturer: *Your organization’s name*</span></span>
    -   <span data-ttu-id="836bb-270">版本： **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="836bb-270">Version: **1.0.0**</span></span>
    -   <span data-ttu-id="836bb-271">选择**此程序包包含源文件**复选框、 **SR v2 – 根证书程序包**文件夹中，输入的路径，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="836bb-271">Select the **This package contains source files** check box, enter the path to the **SRS v2 – Root Certificate Package** folder, and then select **Next**.</span></span>

4.  <span data-ttu-id="836bb-272">选择**不创建程序**，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="836bb-272">Select **Do not create a program**, and then select **Next**.</span></span>

5.  <span data-ttu-id="836bb-273">查看**确认的设置**页，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="836bb-273">Review the **Confirm the settings** page, and then select **Next**.</span></span>

6.  <span data-ttu-id="836bb-274">选择**关闭**。</span><span class="sxs-lookup"><span data-stu-id="836bb-274">Select **Close**.</span></span>

### <a name="create-the-skype-room-systems-v2-deployment-kit-package"></a><span data-ttu-id="836bb-275">创建 Skype 会议室系统 v2 部署套件包</span><span class="sxs-lookup"><span data-stu-id="836bb-275">Create the Skype Room Systems v2 deployment kit package</span></span>

1.  <span data-ttu-id="836bb-276">下载最新版本的**Skype 会议室系统 v2 部署工具包**从<https://go.microsoft.com/fwlink/?linkid=851168>，并将其安装到工作站。</span><span class="sxs-lookup"><span data-stu-id="836bb-276">Download the latest version of the **Skype Room Systems v2 deployment kit** from <https://go.microsoft.com/fwlink/?linkid=851168>, and install it to a workstation.</span></span>

2.  <span data-ttu-id="836bb-277">复制从内容**c:\\Program Files (x86)\\Skype 会议室系统部署工具包** **SR v2-SR 应用程序包**文件夹。</span><span class="sxs-lookup"><span data-stu-id="836bb-277">Copy the content from **C:\\Program Files (x86)\\Skype Room System Deployment Kit** to the **SRS v2 - SRS Application Package** folder.</span></span>

3.  <span data-ttu-id="836bb-278">在 Configuration Manager 控制台中，转到**软件库** \> **应用程序管理** \> **包**以及然后选择**创建新程序包**。</span><span class="sxs-lookup"><span data-stu-id="836bb-278">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4.  <span data-ttu-id="836bb-279">输入以下信息以创建包：</span><span class="sxs-lookup"><span data-stu-id="836bb-279">Enter the following information to create the package:</span></span>
    -   <span data-ttu-id="836bb-280">名称： **SR v2 – SR 应用程序包**</span><span class="sxs-lookup"><span data-stu-id="836bb-280">Name: **SRS v2 – SRS Application Package**</span></span>
    -   <span data-ttu-id="836bb-281">制造商： **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="836bb-281">Manufacturer: **Microsoft Corporation**</span></span>
    -   <span data-ttu-id="836bb-282">版本： **3.1.104.0** （输入下载的安装文件的版本）</span><span class="sxs-lookup"><span data-stu-id="836bb-282">Version: **3.1.104.0** (enter the version of the downloaded installation file)</span></span>
    -   <span data-ttu-id="836bb-283">选择**此程序包包含源文件**复选框、 **SR v2 – SR 应用程序包**文件夹中，输入的路径，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="836bb-283">Select the **This package contains source files** check box, enter the path to the **SRS v2 – SRS Application Package** folder, and then select **Next**.</span></span>
5.  <span data-ttu-id="836bb-284">选择**不创建程序**，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="836bb-284">Select **Do not create a program**, and then select **Next**.</span></span>

6.  <span data-ttu-id="836bb-285">查看**确认的设置**页，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="836bb-285">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7.  <span data-ttu-id="836bb-286">选择**关闭**。</span><span class="sxs-lookup"><span data-stu-id="836bb-286">Select **Close**.</span></span>

### <a name="create-the-computer-name-assignment-package"></a><span data-ttu-id="836bb-287">创建计算机名称分配包</span><span class="sxs-lookup"><span data-stu-id="836bb-287">Create the computer name assignment package</span></span>

1.  <span data-ttu-id="836bb-288">在**SR v2-设置 SRSComputerName 程序包**文件夹中，创建名为**集 SRSComputerName.hta**新 HTML 应用程序。</span><span class="sxs-lookup"><span data-stu-id="836bb-288">In the **SRS v2 - Set-SRSComputerName Package** folder, create a new HTML application named **Set-SRSComputerName.hta** .</span></span>

2.  <span data-ttu-id="836bb-289">将以下脚本复制到**集 SRSComputerName.hta**文件。</span><span class="sxs-lookup"><span data-stu-id="836bb-289">Copy the following script into the **Set-SRSComputerName.hta** file.</span></span> <span data-ttu-id="836bb-290">此外，您可以从[此处](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)下载设置 SRSComputerName.hta 文件。</span><span class="sxs-lookup"><span data-stu-id="836bb-290">Alternatively, you can download the Set-SRSComputerName.hta file from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
    ```
    <!DOCTYPE HTML>
    <html>
    <head>
    <title>Set SRS Computer Name</title>
    <HTA:APPLICATION
      APPLICATIONNAME="Set SRS Computer Name"
      ID="SetSRSComputerName"
      VERSION="1.0"
      SCROLL="no"
      SINGLEINSTANCE="yes"
      WINDOWSTATE="maximize"
      MaximizeButton="no"
      MinimizeButton="no"
      SysMenu="no"
      ShowInTaskbar="no"
      Caption="no"
      />
    <style type="text/css">
    body {
        background-color: #fdfeff;
        color: darkblue;
        font-family: Calibri;
        font-size: 12pt;
        margin: 4em 3em;
    }
    </style>
    </head>
    <script language="VBScript">
    Public strNewComputerName
    Sub GenerateComputerName()
        strComputer = "."
        Set objWMIService = GetObject("winmgmts:\\" & strComputer & "\root\cimv2")
        Set colItems = objWMIService.ExecQuery("Select * from Win32_BIOS",,48)
        For Each objItem in colItems
            strSerialNumber = objItem.SerialNumber
        Next
        strNewComputerName = "SRS-"  & right(replace(strSerialNumber, "-","") ,10)
        TextArea1.innerHTML = "The serial number of the device: " & strSerialNumber
        strHTMLText = strHTMLText & "<br> Computer name to be assigned: <font color = red>" & strNewComputerName & "</font>"
        strHTMLText = strHTMLText & "<br><br> Click Accept to use this as the computer name and continue deployment, or Change to set a new name."
        strHTMLText = strHTMLText & "<p><input type=""button"" value=""Accept"" name = ""Accept_Button"" onclick=""SetComputerName"" />"
        strHTMLText = strHTMLText & " <input type=""button"" value=""Change"" name = ""Change_Button"" onclick=""ChangeComputerName"" />"
        TextArea2.innerHTML = strHTMLText
    End Sub

    Sub SetComputerName()
        dim result
        result = MsgBox("Computer Name to be assigned: " & strNewComputerName &vbcrlf & "Are you sure you want to continue?", 36)
        If (result = vbYes) then
            SET env = CreateObject("Microsoft.SMS.TSEnvironment")
            env("OSDComputerName") = strNewComputerName
            self.close
        elseif (result = vbNo) then
            Window_OnLoad
        End If
    End Sub

    Sub UpdateComputerName()
        strNewComputerName = newcomputername.value
        if len(trim(strNewComputerName)) = 0 then
            MsgBox "Computer name cannot be empty." &vbcrlf & "Update and try again.",16
            exit sub
        end if
        SetComputerName
    End Sub

    Sub ChangeComputerName()
        TextArea2.innerHTML = "<p>Type the new computer name and click Accept:  <input type=""text"" name=""newcomputername"" value =" & strNewComputerName & " />"
        TextArea2.innerHTML = TextArea2.innerHTML & "<br><input type=""button"" value=""Update"" name = ""Update_Button"" onclick=""UpdateComputerName"" />"
    End Sub

    Sub Window_OnLoad
        Set oTSProgressUI = CreateObject("Microsoft.SMS.TsProgressUI")
        oTSProgressUI.CloseProgressDialog
        GenerateComputerName
    End Sub
    </script>

    <body>
    <span id = "TextArea1"></span>
    <span id = "TextArea2">
    </span>
    </body>
    </html>

    ```
3.  <span data-ttu-id="836bb-291">在 Configuration Manager 控制台中，转到**软件库** \> **应用程序管理** \> **包**以及然后选择**创建新程序包**。</span><span class="sxs-lookup"><span data-stu-id="836bb-291">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4.  <span data-ttu-id="836bb-292">输入以下信息以创建包：</span><span class="sxs-lookup"><span data-stu-id="836bb-292">Enter the following information to create the package:</span></span>

    -   <span data-ttu-id="836bb-293">名称： **SR v2-设置 SRSComputerName 包**</span><span class="sxs-lookup"><span data-stu-id="836bb-293">Name: **SRS v2 - Set-SRSComputerName Package**</span></span>

    -   <span data-ttu-id="836bb-294">制造商： **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="836bb-294">Manufacturer: **Microsoft Corporation**</span></span>

    -   <span data-ttu-id="836bb-295">版本： **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="836bb-295">Version: **1.0.0**</span></span>

    -   <span data-ttu-id="836bb-296">选择**此程序包包含源文件**复选框、 **SR v2-设置 SRSComputerName 程序包**文件夹中，输入的路径，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="836bb-296">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Set-SRSComputerName Package** folder, and then select **Next**.</span></span>

5.  <span data-ttu-id="836bb-297">选择**不创建程序**，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="836bb-297">Select **Do not create a program**, and then select **Next**.</span></span>

6.  <span data-ttu-id="836bb-298">查看**确认的设置**页，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="836bb-298">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7.  <span data-ttu-id="836bb-299">选择**关闭**。</span><span class="sxs-lookup"><span data-stu-id="836bb-299">Select **Close**.</span></span>

### <a name="create-the-sysprep-package"></a><span data-ttu-id="836bb-300">创建 Sysprep 包</span><span class="sxs-lookup"><span data-stu-id="836bb-300">Create the Sysprep package</span></span>

1. <span data-ttu-id="836bb-301">在**SR v2 – Sysprep 程序包**文件夹中，创建名为**Unattend.xml**的新 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="836bb-301">In the **SRS v2 – Sysprep Package** folder, create a new XML file named **Unattend.xml** .</span></span>

2. <span data-ttu-id="836bb-302">将以下文本复制到**Unattend.xml**文件。</span><span class="sxs-lookup"><span data-stu-id="836bb-302">Copy the following text into the **Unattend.xml** file.</span></span> <span data-ttu-id="836bb-303">此外，您可以从[此处](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)下载 Unattend.xml 文件。</span><span class="sxs-lookup"><span data-stu-id="836bb-303">Alternatively, you can download the Unattend.xml file from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
   ```
   <?xml version="1.0" encoding="utf-8"?>
   <unattend xmlns="urn:schemas-microsoft-com:unattend">
   <settings pass="specialize">
       <component name="Microsoft-Windows-Embedded-BootExp" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="NonSxS" xmlns:wcm="https://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
           <DisableBootMenu>1</DisableBootMenu>
           <DisplayDisabled>1</DisplayDisabled>
       </component>
       <component name="Microsoft-Windows-powercpl" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="https://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
           <PreferredPlan>8c5e7fda-e8bf-4a96-9a85-a6e23a8c635c</PreferredPlan>
       </component>
   </settings>
   <settings pass="oobeSystem">
       <component name="Microsoft-Windows-Shell-Setup" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="https://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
           <OOBE>
               <HideEULAPage>true</HideEULAPage>
               <HideLocalAccountScreen>true</HideLocalAccountScreen>
               <HideOEMRegistrationScreen>true</HideOEMRegistrationScreen>
               <HideOnlineAccountScreens>true</HideOnlineAccountScreens>
               <HideWirelessSetupInOOBE>true</HideWirelessSetupInOOBE>
               <SkipMachineOOBE>true</SkipMachineOOBE>
               <SkipUserOOBE>true</SkipUserOOBE>
               <ProtectYourPC>1</ProtectYourPC>
           </OOBE>
           <AutoLogon>
               <Enabled>true</Enabled>
               <Username>Skype</Username>
               <Password>
                   <Value>UABhAHMAcwB3AG8AcgBkAA==</Value>
                   <PlainText>false</PlainText>
               </Password>
           </AutoLogon>
           <UserAccounts>
               <LocalAccounts>
                   <LocalAccount wcm:action="add">
                       <Password>
                           <Value>cwBmAGIAUABhAHMAcwB3AG8AcgBkAA==</Value>
                           <PlainText>false</PlainText>
                       </Password>
                       <Name>Admin</Name>
                       <Group>Administrators</Group>
                       <DisplayName>Administrator</DisplayName>
                       <Description>Administrator</Description>
                   </LocalAccount>
               </LocalAccounts>
           </UserAccounts>
       </component>
   </settings>
   <cpi:offlineImage cpi:source="wim:h:/install.wim#Windows 10 Enterprise" xmlns:cpi="urn:schemas-microsoft-com:cpi" />
   </unattend>
   ```
3. <span data-ttu-id="836bb-304">在 Configuration Manager 控制台中，转到**软件库** \> **应用程序管理** \> **包**以及然后选择**创建新程序包**。</span><span class="sxs-lookup"><span data-stu-id="836bb-304">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4. <span data-ttu-id="836bb-305">输入以下信息以创建包：</span><span class="sxs-lookup"><span data-stu-id="836bb-305">Enter the following information to create the package:</span></span>
   -   <span data-ttu-id="836bb-306">名称： **SR v2-Sysprep 包**</span><span class="sxs-lookup"><span data-stu-id="836bb-306">Name: **SRS v2 - Sysprep Package**</span></span>
   -   <span data-ttu-id="836bb-307">制造商： **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="836bb-307">Manufacturer: **Microsoft Corporation**</span></span>
   -   <span data-ttu-id="836bb-308">版本： **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="836bb-308">Version: **1.0.0**</span></span>
   -   <span data-ttu-id="836bb-309">选择**此程序包包含源文件**复选框、 **SR v2 – Sysprep 程序包**文件夹中，输入的路径，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="836bb-309">Select the **This package contains source files** check box, enter the path to the **SRS v2 – Sysprep Package** folder, and then select **Next**.</span></span>
5. <span data-ttu-id="836bb-310">选择**不创建程序**，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="836bb-310">Select **Do not create a program**, and then select **Next**.</span></span>

6. <span data-ttu-id="836bb-311">查看**确认的设置**页，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="836bb-311">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7. <span data-ttu-id="836bb-312">选择**关闭**。</span><span class="sxs-lookup"><span data-stu-id="836bb-312">Select **Close**.</span></span>

### <a name="create-the-windows-10-enterprise-package"></a><span data-ttu-id="836bb-313">创建 Windows 10 Enterprise 包</span><span class="sxs-lookup"><span data-stu-id="836bb-313">Create the Windows 10 Enterprise package</span></span>

1.  <span data-ttu-id="836bb-314">获取 Windows 10 Enterprise x64 媒体，并复制到**install.wim**文件**操作系统\\Windows 10 Enterprise**文件夹。</span><span class="sxs-lookup"><span data-stu-id="836bb-314">Obtain a Windows 10 Enterprise x64 media, and copy the **install.wim** file to the **Operating Systems\\Windows 10 Enterprise** folder.</span></span>

2.  <span data-ttu-id="836bb-315">在 Configuration Manager 控制台中，转到**软件库** \> **操作系统** \> **操作系统映像**和然后选择**添加操作系统映像**。</span><span class="sxs-lookup"><span data-stu-id="836bb-315">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Operating System Images**, and then select **Add Operating System Image**.</span></span>

3.  <span data-ttu-id="836bb-316">指定您刚复制的**install.wim**文件的路径，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="836bb-316">Specify the path to the **install.wim** file you just copied, and then select **Next**.</span></span>

4.  <span data-ttu-id="836bb-317">更新**版本**字段匹配的 Windows 10 Enterprise 图像，内部版本号，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="836bb-317">Update the **Version** field to match the build number of the Windows 10 Enterprise image, and then select **Next**.</span></span>

5.  <span data-ttu-id="836bb-318">查看**详细信息**页上，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="836bb-318">Review the **Details** page, and then select **Next**.</span></span>

6.  <span data-ttu-id="836bb-319">选择**关闭**。</span><span class="sxs-lookup"><span data-stu-id="836bb-319">Select **Close**.</span></span>

<span data-ttu-id="836bb-320">有关详细信息，请参阅[管理操作系统映像使用 System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-operating-system-images)。</span><span class="sxs-lookup"><span data-stu-id="836bb-320">For more information, see [Manage operating system images with System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-operating-system-images).</span></span>

### <a name="create-surface-pro-device-driver-packages"></a><span data-ttu-id="836bb-321">创建 Surface Pro 设备驱动程序包</span><span class="sxs-lookup"><span data-stu-id="836bb-321">Create Surface Pro device driver packages</span></span>

<span data-ttu-id="836bb-322">Skype 会议室系统 v2 支持 Surface Pro 和 Surface Pro 4。</span><span class="sxs-lookup"><span data-stu-id="836bb-322">Skype Room Systems v2 is supported for both Surface Pro and Surface Pro 4.</span></span> <span data-ttu-id="836bb-323">您需要创建已在您的环境中每个 Surface Pro 模型驱动程序包。</span><span class="sxs-lookup"><span data-stu-id="836bb-323">You need to create a driver package for each Surface Pro model you have in your environment.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="836bb-324">驱动程序必须与 Windows 10 Enterprise 生成和 Skype 会议室系统 v2 部署套件版本兼容。</span><span class="sxs-lookup"><span data-stu-id="836bb-324">The drivers must be compatible with the Windows 10 Enterprise build and the Skype Room Systems v2 deployment kit version.</span></span> <span data-ttu-id="836bb-325">有关详细信息，请参阅[下载最新的固件和呈现设备的驱动程序](https://docs.microsoft.com/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices)和[Configure 控制台](console.md)。</span><span class="sxs-lookup"><span data-stu-id="836bb-325">For more information, see [Download the latest firmware and drivers for Surface devices](https://docs.microsoft.com/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices) and [Configure a console](console.md).</span></span>

1.  <span data-ttu-id="836bb-326">下载最新驱动程序和固件。</span><span class="sxs-lookup"><span data-stu-id="836bb-326">Download the latest drivers and firmware.</span></span>
    -   <span data-ttu-id="836bb-327">为 Surface Pro:<https://www.microsoft.com/download/details.aspx?id=55484></span><span class="sxs-lookup"><span data-stu-id="836bb-327">For Surface Pro: <https://www.microsoft.com/download/details.aspx?id=55484></span></span>
    -   <span data-ttu-id="836bb-328">为 Surface Pro 4:<https://www.microsoft.com/download/details.aspx?id=49498></span><span class="sxs-lookup"><span data-stu-id="836bb-328">For Surface Pro 4: <https://www.microsoft.com/download/details.aspx?id=49498></span></span>

2.  <span data-ttu-id="836bb-329">提取下载的驱动程序和固件。</span><span class="sxs-lookup"><span data-stu-id="836bb-329">Extract the downloaded driver and firmware.</span></span> <span data-ttu-id="836bb-330">打开命令提示符窗口并在命令提示符处，输入以下命令之一：</span><span class="sxs-lookup"><span data-stu-id="836bb-330">Open a Command Prompt window and at the command prompt, enter one of the following commands:</span></span>
    -   `msiexec /a C:\SurfacePro_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro"`
    -   `msiexec /a C:\SurfacePro4_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro 4"`

3.  <span data-ttu-id="836bb-331">在 Configuration Manager 控制台中，转到**软件库** \> **操作系统** \> **驱动程序**，然后选择**导入驱动程序**。</span><span class="sxs-lookup"><span data-stu-id="836bb-331">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Drivers**, and then select **Import Driver**.</span></span>

4.  <span data-ttu-id="836bb-332">选择**导入以下网络路径 (UNC) 中的所有驱动程序**中，选择源文件夹 (例如，c:\\_Sources\\驱动程序\\Surface Pro)，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="836bb-332">Select **Import all drivers in the following network path (UNC)**, select the source folder (for example, C:\\_Sources\\Drivers\\Surface Pro), and then select **Next**.</span></span>

5.  <span data-ttu-id="836bb-333">在**指定的导入的驱动程序的详细信息**页上，选择所有列出驱动程序，，然后选择**启用这些驱动程序并允许进行安装的计算机**。</span><span class="sxs-lookup"><span data-stu-id="836bb-333">On the **Specify the details for the imported drivers** page, select all the listed drivers, and then select **Enable these drivers and allow computers to install them**.</span></span>

6.  <span data-ttu-id="836bb-334">选择**类别**，创建新类别相匹配的表面模型，选择**确定**，，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="836bb-334">Select **Categories**, create a new category that matches the Surface model, select **OK**, and then select **Next**.</span></span>

7.  <span data-ttu-id="836bb-335">选择**新程序包**。</span><span class="sxs-lookup"><span data-stu-id="836bb-335">Select **New Package**.</span></span>

8.  <span data-ttu-id="836bb-336">指定与 Surface Pro 模型匹配的软件包名称，请输入文件夹路径以存储驱动程序包文件中的，选择**确定**，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="836bb-336">Specify the package name that matches the Surface Pro model, enter a folder path to store the driver package files in, select **OK**, and then select **Next**.</span></span>

9.  <span data-ttu-id="836bb-337">在**启动映像**页上，确保没有启动映像选择，然后选中**下一步**。</span><span class="sxs-lookup"><span data-stu-id="836bb-337">On the **boot images** page, ensure that no boot images are selected, and then select **Next**.</span></span>

10. <span data-ttu-id="836bb-338">选择**关闭**。</span><span class="sxs-lookup"><span data-stu-id="836bb-338">Select **Close**.</span></span>

11. <span data-ttu-id="836bb-339">转到**软件库** \> **操作系统** \> **驱动程序**，选择**文件夹\>创建文件夹**，并输入一个文件夹名称相匹配的 Surface Pro 模型的您刚才导入的驱动程序。</span><span class="sxs-lookup"><span data-stu-id="836bb-339">Go to **Software Library** \> **Operating Systems** \> **Drivers**, select **Folder \> Create Folder**, and enter a folder name that matches the Surface Pro model that you just imported the drivers for.</span></span>

12. <span data-ttu-id="836bb-340">将所有已导入的驱动程序移动到新创建的文件夹，以便于导航和操作。</span><span class="sxs-lookup"><span data-stu-id="836bb-340">Move all the imported drivers to the newly created folder for easier navigation and operation.</span></span>

> [!NOTE]
> <span data-ttu-id="836bb-341">对其他 Surface Pro 模型，您可能必须重复相同的步骤。</span><span class="sxs-lookup"><span data-stu-id="836bb-341">Repeat the same steps for other Surface Pro models you might have.</span></span> <span data-ttu-id="836bb-342">有关详细信息，请参阅[管理驱动因素 System Center Configuration Manager 中](https://docs.microsoft.com/sccm/osd/get-started/manage-drivers)。</span><span class="sxs-lookup"><span data-stu-id="836bb-342">For more information, see [Manage drivers in System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-drivers).</span></span>

### <a name="create-skype-room-system-configuration-package"></a><span data-ttu-id="836bb-343">创建 Skype 会议室系统配置包</span><span class="sxs-lookup"><span data-stu-id="836bb-343">Create Skype Room System Configuration Package</span></span>

1.  <span data-ttu-id="836bb-344">在 Configuration Manager 控制台中，转到**软件库** \> **应用程序管理** \> **包**以及然后选择**创建新程序包**。</span><span class="sxs-lookup"><span data-stu-id="836bb-344">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

2.  <span data-ttu-id="836bb-345">输入以下信息以创建包：</span><span class="sxs-lookup"><span data-stu-id="836bb-345">Enter the following information to create the package:</span></span>

    -   <span data-ttu-id="836bb-346">名称： **SR v2-配置 SR 安装程序包**</span><span class="sxs-lookup"><span data-stu-id="836bb-346">Name: **SRS v2 - Configure SRS Setup Package**</span></span>

    -   <span data-ttu-id="836bb-347">制造商： **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="836bb-347">Manufacturer: **Microsoft Corporation**</span></span>

    -   <span data-ttu-id="836bb-348">版本： **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="836bb-348">Version: **1.0.0**</span></span>

    -   <span data-ttu-id="836bb-349">选择**此程序包包含源文件**复选框、 **SR v2-配置 SR 安装程序**文件夹中，输入的路径，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="836bb-349">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Configure SRS Setup** folder, and then select **Next**.</span></span>

3.  <span data-ttu-id="836bb-350">选择**不创建程序**，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="836bb-350">Select **Do not create a program**, and then select **Next**.</span></span>

4.  <span data-ttu-id="836bb-351">查看**确认的设置**页，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="836bb-351">Review the **Confirm the settings** page, and then select **Next**.</span></span>

5.  <span data-ttu-id="836bb-352">选择**关闭**。</span><span class="sxs-lookup"><span data-stu-id="836bb-352">Select **Close**.</span></span>



## <a name="distribute-configuration-manager-packages"></a><span data-ttu-id="836bb-353">分发配置管理器包</span><span class="sxs-lookup"><span data-stu-id="836bb-353">Distribute Configuration Manager packages</span></span>

<span data-ttu-id="836bb-354">必须将所有程序包都分发给已分配了分发点角色配置管理器层次结构中的服务器。</span><span class="sxs-lookup"><span data-stu-id="836bb-354">All the packages must be distributed to the servers that have been assigned the distribution point role in the Configuration Manager hierarchy.</span></span> <span data-ttu-id="836bb-355">按照以下说明启动软件包分发。</span><span class="sxs-lookup"><span data-stu-id="836bb-355">Follow the instructions below to initiate package distribution.</span></span>

1.  <span data-ttu-id="836bb-356">分发软件包。</span><span class="sxs-lookup"><span data-stu-id="836bb-356">Distribute software packages.</span></span>

    1.  <span data-ttu-id="836bb-357">在 Configuration Manager 控制台中，转到**软件库** \> **应用程序管理** \> **包**。</span><span class="sxs-lookup"><span data-stu-id="836bb-357">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**.</span></span> <span data-ttu-id="836bb-358">选择您想要分配的所有软件程序包，然后都选择**分发内容**。</span><span class="sxs-lookup"><span data-stu-id="836bb-358">Select all the software packages you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="836bb-359">查看包的列表，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="836bb-359">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="836bb-360">向列表中，添加所有分发点服务器 （或分发点组，具体取决于您的配置管理器层次结构），然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="836bb-360">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="836bb-361">选择**下一步**，，，然后选择**关闭**。</span><span class="sxs-lookup"><span data-stu-id="836bb-361">Select **Next**, and then select **Close**.</span></span>

2.  <span data-ttu-id="836bb-362">分发驱动程序包。</span><span class="sxs-lookup"><span data-stu-id="836bb-362">Distribute driver packages.</span></span>

    1.  <span data-ttu-id="836bb-363">在 Configuration Manager 控制台中，转到**软件库** \> **操作系统** \> **驱动程序包**。</span><span class="sxs-lookup"><span data-stu-id="836bb-363">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Driver Packages**.</span></span> <span data-ttu-id="836bb-364">选择您想要分配的所有驱动程序包，然后都选择**分发内容**。</span><span class="sxs-lookup"><span data-stu-id="836bb-364">Select all the driver packages you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="836bb-365">查看包的列表，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="836bb-365">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="836bb-366">向列表中，添加所有分发点服务器 （或分发点组，具体取决于您的配置管理器层次结构），然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="836bb-366">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="836bb-367">选择**下一步**，，，然后选择**关闭**。</span><span class="sxs-lookup"><span data-stu-id="836bb-367">Select **Next**, and then select **Close**.</span></span>

3.  <span data-ttu-id="836bb-368">分发操作系统包。</span><span class="sxs-lookup"><span data-stu-id="836bb-368">Distribute operating system packages.</span></span>

    1.  <span data-ttu-id="836bb-369">在 Configuration Manager 控制台中，转到**软件库** \> **操作系统** \> **操作系统映像**。</span><span class="sxs-lookup"><span data-stu-id="836bb-369">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Operating System Images**.</span></span> <span data-ttu-id="836bb-370">选择您想要分配的所有操作系统映像，然后都选择**分发内容**。</span><span class="sxs-lookup"><span data-stu-id="836bb-370">Select all the operating system images you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="836bb-371">查看包的列表，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="836bb-371">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="836bb-372">向列表中，添加所有分发点服务器 （或分发点组，具体取决于您的配置管理器层次结构），然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="836bb-372">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="836bb-373">选择**下一步**，，，然后选择**关闭**。</span><span class="sxs-lookup"><span data-stu-id="836bb-373">Select **Next**, and then select **Close**.</span></span>

> [!NOTE]
> <span data-ttu-id="836bb-374">软件包分发可能需要一些时间，具体取决于程序包大小、 配置管理器层次结构、 分发点服务器的数量和网络中可以使用的带宽。</span><span class="sxs-lookup"><span data-stu-id="836bb-374">Package distribution might take some time, depending on the package size, Configuration Manager hierarchy, number of distribution point servers, and the bandwidth available in your network.</span></span>
> 
> <span data-ttu-id="836bb-375">在开始部署 Skype 会议室系统 v2 单位之前，必须将分发所有程序包。</span><span class="sxs-lookup"><span data-stu-id="836bb-375">All the packages must be distributed before you can start deploying a Skype Room Systems v2 unit.</span></span>
> 
> <span data-ttu-id="836bb-376">您可以查看您程序包分发 Configuration Manager 控制台中的状态，转到**监控** \> **分发状态** \> **内容状态**。</span><span class="sxs-lookup"><span data-stu-id="836bb-376">You can review the status of your package distribution in the Configuration Manager console by going to **Monitoring** \> **Distribution Status** \> **Content Status**.</span></span>

## <a name="configuration-manager-task-sequences"></a><span data-ttu-id="836bb-377">配置管理器任务序列</span><span class="sxs-lookup"><span data-stu-id="836bb-377">Configuration Manager task sequences</span></span>

<span data-ttu-id="836bb-378">使用任务序列使用 System Center Configuration Manager 中自动部署到目标计算机的操作系统映像的步骤。</span><span class="sxs-lookup"><span data-stu-id="836bb-378">You use task sequences with System Center Configuration Manager to automate the steps for deploying an operating system image to a destination computer.</span></span> <span data-ttu-id="836bb-379">若要部署中自动方式的 Skype 会议室系统 v2 单元，您创建引用用于启动目标 Skype 会议室系统 v2 计算机、 Windows 10 Enterprise 操作系统映像的要进行安装，以及任何启动映像任务序列其他其他内容，例如其他应用程序或软件更新。</span><span class="sxs-lookup"><span data-stu-id="836bb-379">To deploy a Skype Room Systems v2 unit in an automated fashion, you create a task sequence that references the boot image used to start the destination Skype Room Systems v2 computer, the Windows 10 Enterprise operating system image that you want to install, and any other additional content, such as other applications or software updates.</span></span>

### <a name="import-the-sample-task-sequence"></a><span data-ttu-id="836bb-380">导入示例任务序列</span><span class="sxs-lookup"><span data-stu-id="836bb-380">Import the sample task sequence</span></span>

<span data-ttu-id="836bb-381">您可以下载轻松导入示例任务序列并自定义以符合您的需求。</span><span class="sxs-lookup"><span data-stu-id="836bb-381">You can download and easily import a sample task sequence and customize it to meet your needs.</span></span>

1.  <span data-ttu-id="836bb-382">[**下载**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)示例任务序列，并将下载的压缩文件复制到共享位置。</span><span class="sxs-lookup"><span data-stu-id="836bb-382">[**Download**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) the sample task sequence, and copy the downloaded zip file to a shared location.</span></span>
2.  <span data-ttu-id="836bb-383">在 Configuration Manager 控制台中，转到**软件库** \> **操作系统** \> **任务序列**和然后选择**导入任务序列**。</span><span class="sxs-lookup"><span data-stu-id="836bb-383">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Task Sequences**, and then select **Import Task Sequence**.</span></span>

3.  <span data-ttu-id="836bb-384">选择**浏览**，转到您在步骤 1 中使用的共享的文件夹位置，选择**Skype 会议室系统 v2 部署 (EN-US).zip**文件中，，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="836bb-384">Select **Browse**, go to the shared folder location you used in step 1, select the **Skype Room Systems v2 Deployment (EN-US).zip** file, and then select **Next**.</span></span>

4.  <span data-ttu-id="836bb-385">将**操作**设置为**新建**，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="836bb-385">Set **Action** to **Create New**, and then select **Next**.</span></span>

5.  <span data-ttu-id="836bb-386">确认设置，，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="836bb-386">Confirm the settings, and then select **Next**.</span></span>

6.  <span data-ttu-id="836bb-387">选择**关闭**。</span><span class="sxs-lookup"><span data-stu-id="836bb-387">Select **Close**.</span></span>

### <a name="validate-that-the-reference-packages-are-correctly-linked-to-each-task-sequence-step"></a><span data-ttu-id="836bb-388">验证引用包正确链接到任务序列的每个步骤。</span><span class="sxs-lookup"><span data-stu-id="836bb-388">Validate that the reference packages are correctly linked to each task sequence step.</span></span>

1. <span data-ttu-id="836bb-389">选择导入的任务序列，，，然后选择**编辑**。</span><span class="sxs-lookup"><span data-stu-id="836bb-389">Select the imported task sequence, and then select **Edit**.</span></span>

    <span data-ttu-id="836bb-390">任务序列编辑器打开并显示每个连续的步骤，您需要部署和配置 Skype 会议室系统 v2 单位。</span><span class="sxs-lookup"><span data-stu-id="836bb-390">The Task Sequence Editor opens and displays each sequential step that you need to deploy and configure a Skype Room Systems v2 unit.</span></span>

2. <span data-ttu-id="836bb-391">演练每个步骤并完成建议的更新：</span><span class="sxs-lookup"><span data-stu-id="836bb-391">Walk through each step and complete the recommended updates:</span></span>

   1. <span data-ttu-id="836bb-392">**在 Windows PE 重新启动**： 此步骤重新启动，然后启动到 Windows PXE 的计算机。</span><span class="sxs-lookup"><span data-stu-id="836bb-392">**Restart in Windows PE**: This step restarts and then boots the computer into Windows PXE.</span></span> <span data-ttu-id="836bb-393">没有更改所需的此步骤。</span><span class="sxs-lookup"><span data-stu-id="836bb-393">No changes are required for this step.</span></span>

   2. <span data-ttu-id="836bb-394">**分区磁盘 0 – UEFI**： 此步骤擦除磁盘配置并创建基于已配置的设置的分区。</span><span class="sxs-lookup"><span data-stu-id="836bb-394">**Partition Disk 0 – UEFI**: This step wipes the disk configuration and creates partitions based on the configured settings.</span></span> <span data-ttu-id="836bb-395">我们建议对此步骤不进行任何更改。</span><span class="sxs-lookup"><span data-stu-id="836bb-395">We recommend that you not make any changes to this step.</span></span>

   3. <span data-ttu-id="836bb-396">**设置 SR 计算机名称**： 本步骤包括 HTML 应用程序提供 UI 在部署过程中设置的 Skype 会议室系统 v2 单位的计算机名称。</span><span class="sxs-lookup"><span data-stu-id="836bb-396">**Set SRS Computer Name**: This step includes an HTML application to provide a UI to set a computer name for the Skype Room Systems v2 unit during the deployment.</span></span>
      -  <span data-ttu-id="836bb-397">这是一个可选步骤，但它可以仅禁用如果您想要管理计算机命名通过备用的过程。</span><span class="sxs-lookup"><span data-stu-id="836bb-397">This is an optional step, but it can only be disabled if you want to manage computer naming through an alternate process.</span></span>
      -  <span data-ttu-id="836bb-398">确认已选中**SR v2-设置 SRSComputerName**包。</span><span class="sxs-lookup"><span data-stu-id="836bb-398">Verify that the **SRS v2 - Set-SRSComputerName** package is selected.</span></span> <span data-ttu-id="836bb-399">如果没有，则浏览到包，并选择它。</span><span class="sxs-lookup"><span data-stu-id="836bb-399">If it isn’t, browse to the package and select it.</span></span>

   4. <span data-ttu-id="836bb-400">**应用的操作系统**： 此步骤指定要部署操作系统映像和要使用的无人参与的 Sysprep 应答文件。</span><span class="sxs-lookup"><span data-stu-id="836bb-400">**Apply Operating System**: This step specifies the operating system image to be deployed and the unattended Sysprep answer file to use.</span></span>
      -  <span data-ttu-id="836bb-401">验证已选择正确的 Windows 10 Enterprise 操作系统图像文件。</span><span class="sxs-lookup"><span data-stu-id="836bb-401">Verify that the correct Windows 10 Enterprise operating system image file is selected.</span></span>
      -  <span data-ttu-id="836bb-402">验证启用了**使用无人参与或为自定义安装 Sysprep 应答文件**，并选择**SR v2-Sysprep 包**。</span><span class="sxs-lookup"><span data-stu-id="836bb-402">Verify that **Use an unattended or Sysprep answer file for a custom installation** is enabled, and the **SRS v2 - Sysprep Package** is selected.</span></span> <span data-ttu-id="836bb-403">此外还应确保**文件名称**设置为**unattend.xml**。</span><span class="sxs-lookup"><span data-stu-id="836bb-403">Also ensure that **File Name** is set to **unattend.xml**.</span></span>

   5. <span data-ttu-id="836bb-404">**应用 Windows 设置**： 此步骤收集关于 Windows 安装的信息。</span><span class="sxs-lookup"><span data-stu-id="836bb-404">**Apply Windows Settings**: This step gathers information about the Windows installation.</span></span>
      -  <span data-ttu-id="836bb-405">提供许可和注册信息包括本地管理员帐户密码，产品密钥和时区 （具体取决于您的需求）。</span><span class="sxs-lookup"><span data-stu-id="836bb-405">Provide licensing and registration information including the product key, local administrator account password, and time zone (depending on your needs).</span></span>

   6. <span data-ttu-id="836bb-406">**应用网络设置**： 此步骤，可以指定工作组或 Active Directory 域名和组织单位。</span><span class="sxs-lookup"><span data-stu-id="836bb-406">**Apply Network Settings**: This step allows you to specify a workgroup or Active Directory domain name and organizational unit.</span></span>
      > [!NOTE]
      > <span data-ttu-id="836bb-407">建议的操作需要部署 Skype 会议室系统 v2 单位为 Actve Directory 域的成员，请参阅[Skype 会议室系统域加入注意事项](domain-joining-considerations.md)。</span><span class="sxs-lookup"><span data-stu-id="836bb-407">See [Skype Room System domain joining considerations](domain-joining-considerations.md) for recommended actions you need to take in deploying Skype Room Systems v2 units as members of an Actve Directory domain.</span></span>
   7. <span data-ttu-id="836bb-408">**应用驱动程序：** 使用此步骤和及其子步骤部署适用的设备驱动程序和基于 Surface Pro 模型必须的固件。</span><span class="sxs-lookup"><span data-stu-id="836bb-408">**Apply Drivers:** This step and its sub-steps are used to deploy applicable device drivers and firmware based on the Surface Pro model you have.</span></span> <span data-ttu-id="836bb-409">更新每个步骤，以指定与此部署关联的相关的驱动程序包。</span><span class="sxs-lookup"><span data-stu-id="836bb-409">Update each step to specify the relevant driver package associated with this deployment.</span></span>
      -   <span data-ttu-id="836bb-410">每个驱动因素包配置为利用 Windows Management Instrumentation (WMI) 筛选器部署相关的驱动程序的固件基于 Surface Pro 使和模型。</span><span class="sxs-lookup"><span data-stu-id="836bb-410">Each driver package is configured to leverage Windows Management Instrumentation (WMI) filters to deploy relevant drivers and firmware based on the Surface Pro make and model.</span></span>
      -   <span data-ttu-id="836bb-411">我们强烈建议您不更改这些驱动程序的配置，否则部署可能会失败。</span><span class="sxs-lookup"><span data-stu-id="836bb-411">We highly recommend that you not alter the configuration of these drivers, otherwise deployment might fail.</span></span>

   8. <span data-ttu-id="836bb-412">**设置 Windows 和配置管理器**： 此步骤部署和配置 Configuration Manager 客户端。</span><span class="sxs-lookup"><span data-stu-id="836bb-412">**Set up Windows and Configuration Manager**: This step deploys and configures the Configuration Manager client.</span></span> <span data-ttu-id="836bb-413">更新指定的内置的配置管理器客户端包此步骤。</span><span class="sxs-lookup"><span data-stu-id="836bb-413">Update this step to specify the built-in Configuration Manager Client Package.</span></span>

   9. <span data-ttu-id="836bb-414">**安装根证书**： 此步骤分发非加入域的设备的根证书，因此是可选的默认为禁用。</span><span class="sxs-lookup"><span data-stu-id="836bb-414">**Install Root Certificate**: This step distributes the root certificate for non–domain-joined devices, and therefore is optional and disabled by default.</span></span>
      -   <span data-ttu-id="836bb-415">如果您需要部署到的 Skype 会议室系统 v2 单位的根证书，则启用此步骤。</span><span class="sxs-lookup"><span data-stu-id="836bb-415">Enable this step if you need to deploy a root certificate to the Skype Room Systems v2 units.</span></span>
      -   <span data-ttu-id="836bb-416">如果需要执行此步骤，请验证选中的**SR v2 – 根证书包**和**禁用 64-bit 文件系统重定向**。</span><span class="sxs-lookup"><span data-stu-id="836bb-416">If you do need to perform this step, verify that the **SRS v2 – Root Certificate Package** and **Disable 64-bit file system redirection** are selected.</span></span>

   10. <span data-ttu-id="836bb-417">**安装和配置 OMS 代理**： 此步骤安装 Microsoft 操作管理套件代理的 64 位版本和配置要连接到您的日志分析工作区的代理。</span><span class="sxs-lookup"><span data-stu-id="836bb-417">**Install and Configure OMS Agent**: This step installs the 64-bit version of the Microsoft Operations Management Suite agent and configures the agent to connect to your Log Analytics workspace.</span></span>
       -   <span data-ttu-id="836bb-418">默认情况下禁用此步骤。</span><span class="sxs-lookup"><span data-stu-id="836bb-418">This step is disabled by default.</span></span> <span data-ttu-id="836bb-419">仅当您要使用 OMS to monitor the health 的您 Skype 会议室系统 v2 单位，则启用此步骤。</span><span class="sxs-lookup"><span data-stu-id="836bb-419">Enable this step only if you’re going to use OMS to monitor the health of your Skype Room Systems v2 units.</span></span>
       -   <span data-ttu-id="836bb-420">编辑此步骤和更新的命令行参数指定您的**工作区 ID**和**工作区键**。</span><span class="sxs-lookup"><span data-stu-id="836bb-420">Edit this step and update the command-line parameters to specify your **Workspace ID** and **Workspace Key**.</span></span>
       -   <span data-ttu-id="836bb-421">有关获取操作管理套件工作区 ID 和主关键字的详细信息，请参阅[到 Azure 中的日志分析服务的连接的 Windows 计算机](with-oms.md#configure-test-devices-for-operations-management-suite-setup)。</span><span class="sxs-lookup"><span data-stu-id="836bb-421">See [Connect Windows computers to the Log Analytics service in Azure](with-oms.md#configure-test-devices-for-operations-management-suite-setup) for more information about obtaining the Operations Management Suite Workspace ID and the primary key.</span></span>
       -   <span data-ttu-id="836bb-422">验证选中的**SR v2 – Microsoft OMS 代理包**和**禁用 64-bit 文件系统重定向**。</span><span class="sxs-lookup"><span data-stu-id="836bb-422">Verify that the **SRS v2 – Microsoft OMS Agent Package** and **Disable 64-bit file system redirection** are selected.</span></span>
       -   <span data-ttu-id="836bb-423">有关监控的 Skype 会议室系统 v2 部署运行状况的详细信息，请参阅[使用 OMS 的规划 Skype 会议室系统 v2 管理](../../plan-your-deployment/clients-and-devices/oms-management.md)和[使用 OMS 的部署 Skype 会议室系统 v2 管理](with-oms.md#configure-test-devices-for-operations-management-suite-setup)。</span><span class="sxs-lookup"><span data-stu-id="836bb-423">For more information about monitoring the health of your Skype Room Systems v2 deployment, see [Plan Skype Room Systems v2 management with OMS](../../plan-your-deployment/clients-and-devices/oms-management.md) and [Deploy Skype Room Systems v2 management with OMS](with-oms.md#configure-test-devices-for-operations-management-suite-setup).</span></span>

   11. <span data-ttu-id="836bb-424">**复制 SR v2 配置文件**： 此步骤将从 Skype 会议室系统 v2 部署工具包所需的安装和配置文件复制到本地硬盘。</span><span class="sxs-lookup"><span data-stu-id="836bb-424">**Copy SRS v2 Configuration Files**: This step copies the required setup and configuration files from the Skype Room Systems v2 deployment kit to the local hard drive.</span></span> <span data-ttu-id="836bb-425">无自定义，则需要此步骤。</span><span class="sxs-lookup"><span data-stu-id="836bb-425">No customization is required for this step.</span></span>
       -   <span data-ttu-id="836bb-426">验证选中的**SR v2 – SR 应用程序包**和**禁用 64-bit 文件系统重定向**。</span><span class="sxs-lookup"><span data-stu-id="836bb-426">Verify that the **SRS v2 – SRS Application Package** and **Disable 64-bit file system redirection** are selected.</span></span>

   12. <span data-ttu-id="836bb-427">**安装 SRSv2 操作系统更新**： 此步骤将部署与 Skype 会议室系统 v2 部署所需的任何必需的操作系统更新。</span><span class="sxs-lookup"><span data-stu-id="836bb-427">**Install-SRSv2-OS-Updates**: This step deploys any mandatory operating system updates required with the Skype Room Systems v2 deployment.</span></span> <span data-ttu-id="836bb-428">请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="836bb-428">Do the following:</span></span>
       -   <span data-ttu-id="836bb-429">检查以查看哪些更新所需的[配置 Skype 会议室系统 v2 控制台](console.md)。</span><span class="sxs-lookup"><span data-stu-id="836bb-429">Check [Configure a Skype Room Systems v2 console](console.md) to see which updates are required.</span></span>
       -   <span data-ttu-id="836bb-430">确认您**SR v2 – 操作系统更新程序包**包含所有必需的更新。</span><span class="sxs-lookup"><span data-stu-id="836bb-430">Verify that your **SRS v2 – OS Updates Package** includes all the required updates.</span></span>
       -   <span data-ttu-id="836bb-431">确认已选中**SR v2 – 操作系统更新包**。</span><span class="sxs-lookup"><span data-stu-id="836bb-431">Verify that the **SRS v2 – OS Updates Package** is selected.</span></span>
       -   <span data-ttu-id="836bb-432">验证 PowerShell 执行策略设置为**绕过**。</span><span class="sxs-lookup"><span data-stu-id="836bb-432">Verify that the PowerShell execution policy is set to **Bypass**.</span></span>

   13. <span data-ttu-id="836bb-433">**重新启动计算机**： 在安装必需的操作系统更新后，此步骤重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="836bb-433">**Restart Computer**: This step reboots the computer after the mandatory operating system updates are installed.</span></span> <span data-ttu-id="836bb-434">无自定义，则需要此步骤。</span><span class="sxs-lookup"><span data-stu-id="836bb-434">No customization is required for this step.</span></span>

   14. <span data-ttu-id="836bb-435">**配置 Windows 组件**： 此步骤配置所需的 Windows 功能。</span><span class="sxs-lookup"><span data-stu-id="836bb-435">**Configure Windows Components**: This step configures the required Windows features.</span></span> <span data-ttu-id="836bb-436">无自定义，则需要此步骤。</span><span class="sxs-lookup"><span data-stu-id="836bb-436">No customization is required for this step.</span></span>

   15. <span data-ttu-id="836bb-437">**重新启动计算机**： 配置 Windows 功能后，此步骤重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="836bb-437">**Restart Computer**: This step reboots the computer after the Windows features are configured.</span></span> <span data-ttu-id="836bb-438">无自定义，则需要此步骤。</span><span class="sxs-lookup"><span data-stu-id="836bb-438">No customization is required for this step.</span></span>

   16. <span data-ttu-id="836bb-439">**添加本地 Skype 用户**： 此步骤创建用于自动登录到 Windows 和启动 Skype 会议室系统 v2 应用程序的本地 Skype 帐户。</span><span class="sxs-lookup"><span data-stu-id="836bb-439">**Add Local Skype User**: This step creates the local Skype account used to automatically sign in to Windows and start the Skype Room Systems v2 application.</span></span> <span data-ttu-id="836bb-440">此步骤没有与其关联的任何软件程序包，它需要无自定义。</span><span class="sxs-lookup"><span data-stu-id="836bb-440">This step doesn’t have any software package associated with it, and no customization is required for it.</span></span>

   17. <span data-ttu-id="836bb-441">**设置并配置 SR 应用程序**： 此步骤配置下次启动操作系统的 Skype 会议室系统 v2 应用程序安装。</span><span class="sxs-lookup"><span data-stu-id="836bb-441">**Set up and configure SRS application**: This step configures the Skype Room Systems v2 application installation for the next boot of the operating system.</span></span>
       -   <span data-ttu-id="836bb-442">验证选中**SR v2 – 配置 SR 安装程序包**并**禁用 64-bit 文件系统重定向**。</span><span class="sxs-lookup"><span data-stu-id="836bb-442">Verify that the **SRS v2 – Configure SRS Setup Package** and **Disable 64-bit file system redirection** are selected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="836bb-443">它是非常重要的任务序列步骤必须在提供的顺序。</span><span class="sxs-lookup"><span data-stu-id="836bb-443">It is very important that the task sequence steps must be in the provided order.</span></span> <span data-ttu-id="836bb-444">修改顺序的步骤，或配置其他步骤可能会中断部署。</span><span class="sxs-lookup"><span data-stu-id="836bb-444">Modifying the order of steps, or configuring additional steps might break the deployment.</span></span>
>
> <span data-ttu-id="836bb-445">**设置并配置 SR 应用程序**步骤必须在任务序列中的最后一步，否则部署可能会失败。</span><span class="sxs-lookup"><span data-stu-id="836bb-445">**Set up and configure SRS application** step must be the last step in the task sequence, otherwise the deployment might fail.</span></span>

### <a name="create-deployment-for-the-task-sequence"></a><span data-ttu-id="836bb-446">创建部署任务序列</span><span class="sxs-lookup"><span data-stu-id="836bb-446">Create deployment for the task sequence</span></span>

1. <span data-ttu-id="836bb-447">选择任务序列，，，然后选择**部署**。</span><span class="sxs-lookup"><span data-stu-id="836bb-447">Select the task sequence, and then select **Deploy**.</span></span>

2. <span data-ttu-id="836bb-448">选择**浏览**选择部署目标集合。</span><span class="sxs-lookup"><span data-stu-id="836bb-448">Select **Browse** to select target collection for deployment.</span></span>

3. <span data-ttu-id="836bb-449">选择**所有未知的计算机**，然后选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="836bb-449">Select **All Unknown Computers** and then select **OK**.</span></span>

4. <span data-ttu-id="836bb-450">选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="836bb-450">Select **Next**.</span></span>

5. <span data-ttu-id="836bb-451">选择**用途**下拉列表上的**有空**。</span><span class="sxs-lookup"><span data-stu-id="836bb-451">Select **Available** on the **Purpose** drop down list.</span></span>

6. <span data-ttu-id="836bb-452">在**使可用于以下**列表中，选择**仅媒体和 PXE** ，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="836bb-452">Select **Only Media and PXE** in the **Make available to the following** list, and then select **Next**.</span></span>
   > [!WARNING]
   > <span data-ttu-id="836bb-453">它是非常重要的**目的**设置为**可用**。</span><span class="sxs-lookup"><span data-stu-id="836bb-453">It is very important that **Purpose** is set to **Available**.</span></span> <span data-ttu-id="836bb-454">确保**用途**是\*\*\*\* 设置为**所需**。</span><span class="sxs-lookup"><span data-stu-id="836bb-454">Make sure that the **Purpose** is **NOT** set to **Required**.</span></span> <span data-ttu-id="836bb-455">另外，请确保您选择中**对以下公开\*\*\*\*仅媒体和 PXE** 。</span><span class="sxs-lookup"><span data-stu-id="836bb-455">Also make sure that you select **Only Media and PXE** in the **Make available to the following**.</span></span>
   >
   > <span data-ttu-id="836bb-456">为其他设置这些值可能会导致获取 Skype 会议室系统部署映像时启动的所有计算机。</span><span class="sxs-lookup"><span data-stu-id="836bb-456">Setting these values to something else might cause all computers to get the Skype Room Systems deployment image when booted.</span></span>
7. <span data-ttu-id="836bb-457">不指定任何计划，并选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="836bb-457">Do not specify any schedule and select **Next**.</span></span>

8. <span data-ttu-id="836bb-458">不更改**用户体验**部分中的任何内容，并选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="836bb-458">Do not change anything within the **User Experience** section and select **Next**.</span></span>

9. <span data-ttu-id="836bb-459">不更改**通知**部分中的任何内容，并选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="836bb-459">Do not change anything within the **Alerts** section and select **Next**.</span></span>

10. <span data-ttu-id="836bb-460">不更改该**分发点**内容中的任何内容，并选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="836bb-460">Do not change anything within the **Distribution Points** section and select **Next**.</span></span>

11. <span data-ttu-id="836bb-461">确认设置，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="836bb-461">Confirm the settings and then select **Next**.</span></span>

12. <span data-ttu-id="836bb-462">选择**关闭**。</span><span class="sxs-lookup"><span data-stu-id="836bb-462">Select **Close**.</span></span>

<a name="validate-and-troubleshoot-the-solution"></a><span data-ttu-id="836bb-463">验证并排查解决方案</span><span class="sxs-lookup"><span data-stu-id="836bb-463">Validate and troubleshoot the solution</span></span>
--------------------------------------

<span data-ttu-id="836bb-464">在您完成 System Center Configuration Manager 任务序列后，您需要执行测试运行以验证任务序列可以部署和配置 Skype 会议室系统 v2 单位。</span><span class="sxs-lookup"><span data-stu-id="836bb-464">After you’ve completed the System Center Configuration Manager task sequences, you’ll need to perform a test run to validate that the task sequence can deploy and configure Skype Room Systems v2 units.</span></span>

1.  <span data-ttu-id="836bb-465">通过使用受支持的以太网适配器之一或使用曲面停靠到有线网络连接的测试设备。</span><span class="sxs-lookup"><span data-stu-id="836bb-465">Connect the test device to the wired network by using one of the supported Ethernet adapters or using the Surface dock.</span></span> <span data-ttu-id="836bb-466">如果尚未为您的环境配置 PXE 启动功能，您可用于启动映像上 USB 闪存驱动器[您先前创建](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media)从 USB 启动并连接到配置管理器。</span><span class="sxs-lookup"><span data-stu-id="836bb-466">If PXE boot functionality hasn’t been configured for your environment, you can use the boot image on the USB flash drive [that you created earlier](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media) to boot from USB and connect to Configuration Manager.</span></span>

2.  <span data-ttu-id="836bb-467">访问固件并启动 PXE 启动：</span><span class="sxs-lookup"><span data-stu-id="836bb-467">Access the firmware and initiate PXE boot:</span></span>

    1.  <span data-ttu-id="836bb-468">确保曲面设备处于关闭状态。</span><span class="sxs-lookup"><span data-stu-id="836bb-468">Ensure the Surface device is powered off.</span></span>

    2.  <span data-ttu-id="836bb-469">按住**批量向上**按钮。</span><span class="sxs-lookup"><span data-stu-id="836bb-469">Press and hold the **Volume Up** button.</span></span>

    3.  <span data-ttu-id="836bb-470">按下并释放**高级**按钮。</span><span class="sxs-lookup"><span data-stu-id="836bb-470">Press and release the **Power** button.</span></span>

    4.  <span data-ttu-id="836bb-471">设备后开始启动，释放**卷 Up**按钮。</span><span class="sxs-lookup"><span data-stu-id="836bb-471">After the device begins to boot, release the **Volume Up** button.</span></span>

    5.  <span data-ttu-id="836bb-472">选择**启动配置**。</span><span class="sxs-lookup"><span data-stu-id="836bb-472">Select **Boot configuration**.</span></span>

    6.  <span data-ttu-id="836bb-473">请执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="836bb-473">Do one of the following:</span></span>

        -   <span data-ttu-id="836bb-474">选择**PXE 启动**，并将其拖动至列表顶部。</span><span class="sxs-lookup"><span data-stu-id="836bb-474">Select **PXE boot**, and drag it to the top of the list.</span></span> <span data-ttu-id="836bb-475">此外，您可以扫过网络适配器立即启动到设备上的左侧。</span><span class="sxs-lookup"><span data-stu-id="836bb-475">Alternatively, you can swipe left on the network adapter to boot to the device immediately.</span></span> <span data-ttu-id="836bb-476">这不会影响启动顺序。</span><span class="sxs-lookup"><span data-stu-id="836bb-476">This won’t affect the boot order.</span></span>
        -   <span data-ttu-id="836bb-477">选择包含启动媒体的 USB 闪存驱动器。</span><span class="sxs-lookup"><span data-stu-id="836bb-477">Select the USB flash drive that holds the boot media.</span></span>

3.  <span data-ttu-id="836bb-478">选择**退出**，，，然后选择**立即重新启动**。</span><span class="sxs-lookup"><span data-stu-id="836bb-478">Select **Exit**, and then select **Restart Now**.</span></span>

4.  <span data-ttu-id="836bb-479">出现提示时，选择网络启动服务**Enter** 。</span><span class="sxs-lookup"><span data-stu-id="836bb-479">When prompted, select **Enter** for network boot service.</span></span>

5.  <span data-ttu-id="836bb-480">Windows PE 将加载到内存中，并将启动任务序列向导。</span><span class="sxs-lookup"><span data-stu-id="836bb-480">Windows PE will load into memory, and the Task Sequence Wizard will start.</span></span> <span data-ttu-id="836bb-481">选择**下一步**以继续。</span><span class="sxs-lookup"><span data-stu-id="836bb-481">Select **Next** to continue.</span></span>

6.  <span data-ttu-id="836bb-482">选择之前，导入任务序列，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="836bb-482">Select the task sequence that you imported earlier, and then select **Next**.</span></span>

7.  <span data-ttu-id="836bb-483">应用磁盘配置后，将提示您指定设备的计算机名称。</span><span class="sxs-lookup"><span data-stu-id="836bb-483">After the disk configuration is applied, you’ll be prompted to specify a computer name for the device.</span></span> <span data-ttu-id="836bb-484">用户界面会显示基于 Surface Pro 设备序列号的推荐的计算机名称。</span><span class="sxs-lookup"><span data-stu-id="836bb-484">The user interface will display a recommended computer name based on the serial number of the Surface Pro device.</span></span> <span data-ttu-id="836bb-485">您可以接受建议的名称，或指定一个新。</span><span class="sxs-lookup"><span data-stu-id="836bb-485">You can either accept the proposed name or specify a new one.</span></span> <span data-ttu-id="836bb-486">按照计算机名称分配屏幕上的说明。</span><span class="sxs-lookup"><span data-stu-id="836bb-486">Follow the instructions on the computer name assignment screen.</span></span> <span data-ttu-id="836bb-487">当选择**接受**时，在开始部署。</span><span class="sxs-lookup"><span data-stu-id="836bb-487">When you select **Accept**, the deployment begins.</span></span>

8.  <span data-ttu-id="836bb-488">部署过程的其余部分是自动并不要求输入任何多个用户。</span><span class="sxs-lookup"><span data-stu-id="836bb-488">The rest of the deployment process is automatic and doesn’t ask for any more user input.</span></span>

9.  <span data-ttu-id="836bb-489">部署任务序列完成配置设备后，您将看到要求您配置 Skype 会议室系统 v2 应用程序设置下配置屏幕。</span><span class="sxs-lookup"><span data-stu-id="836bb-489">After the deployment task sequence finishes configuring the device, you’ll see the following configuration screen that asks you to configure the Skype Room Systems v2 application settings.</span></span>

    ![Skype 会议室系统 v2 应用程序的初始安装屏幕](../../media/room-systems-scale-image2.png)

10.  <span data-ttu-id="836bb-491">Surface Pro 插入 Skype 会议室系统 v2 控制台中，并配置的应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="836bb-491">Plug the Surface Pro into the Skype Room Systems v2 console, and configure the application settings.</span></span>

11.  <span data-ttu-id="836bb-492">验证已部署的设备上的[Skype 会议室系统 v2 帮助](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)中列出的功能都正常工作。</span><span class="sxs-lookup"><span data-stu-id="836bb-492">Validate that the capabilities listed in [Skype Room Systems v2 help](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) are working on the deployed device.</span></span>


<span data-ttu-id="836bb-493">要解决安装失败，请检查日志在 Configuration Manager 任务序列中执行的所有步骤的**SMSTS.log**文件。</span><span class="sxs-lookup"><span data-stu-id="836bb-493">To troubleshoot a failed installation, check the **SMSTS.log** file, which logs all the steps executed in a Configuration Manager task sequence.</span></span>

<span data-ttu-id="836bb-494">SMSTS.log 文件存储在多个路径，具体取决于生成过程的阶段之一。</span><span class="sxs-lookup"><span data-stu-id="836bb-494">The SMSTS.log file is stored on one of a number of paths, depending on the stage of the build process.</span></span> <span data-ttu-id="836bb-495">检查下表标识 SMSTS.log 文件的路径。</span><span class="sxs-lookup"><span data-stu-id="836bb-495">Check the following table to identify the path to the SMSTS.log file.</span></span>


| <span data-ttu-id="836bb-496">**部署阶段**</span><span class="sxs-lookup"><span data-stu-id="836bb-496">**Deployment phase**</span></span>                                                            | <span data-ttu-id="836bb-497">**任务序列日志路径**</span><span class="sxs-lookup"><span data-stu-id="836bb-497">**Task sequence log path**</span></span>                         |
|---------------------------------------------------------------------------------|----------------------------------------------------|
| <span data-ttu-id="836bb-498">WinPE 之前 HDD 格式</span><span class="sxs-lookup"><span data-stu-id="836bb-498">WinPE, before HDD format</span></span>                                                        | <span data-ttu-id="836bb-499">X:\\Windows\\Temp\\smstslog\\smsts.log</span><span class="sxs-lookup"><span data-stu-id="836bb-499">X:\\Windows\\Temp\\smstslog\\smsts.log</span></span>             |
| <span data-ttu-id="836bb-500">WinPE 之后 HDD 格式</span><span class="sxs-lookup"><span data-stu-id="836bb-500">WinPE, after HDD format</span></span>                                                         | <span data-ttu-id="836bb-501">C:\\_SMSTaskSequence\\日志\\Smstslog\\smsts.log</span><span class="sxs-lookup"><span data-stu-id="836bb-501">C:\\_SMSTaskSequence\\Logs\\Smstslog\\smsts.log</span></span>    |
| <span data-ttu-id="836bb-502">部署之前的 Configuration Manager 代理已安装, 的操作系统</span><span class="sxs-lookup"><span data-stu-id="836bb-502">Operating system deployed, before the Configuration Manager agent was installed</span></span> | <span data-ttu-id="836bb-503">c:\\_SMSTaskSequence\\日志\\Smstslog\\smsts.log</span><span class="sxs-lookup"><span data-stu-id="836bb-503">c:\\_SMSTaskSequence\\Logs\\Smstslog\\smsts.log</span></span>    |
| <span data-ttu-id="836bb-504">操作系统和部署 Configuration Manager 代理</span><span class="sxs-lookup"><span data-stu-id="836bb-504">Operating system and the Configuration Manager agent deployed</span></span>                   | <span data-ttu-id="836bb-505">%windir%\\System32\\ccm\\日志\\Smstslog\\smsts.log</span><span class="sxs-lookup"><span data-stu-id="836bb-505">%windir%\\System32\\ccm\\logs\\Smstslog\\smsts.log</span></span> |
| <span data-ttu-id="836bb-506">完成执行任务序列</span><span class="sxs-lookup"><span data-stu-id="836bb-506">Task sequence execution complete</span></span>                                                | <span data-ttu-id="836bb-507">%windir%\\System32\\ccm\\日志\\smsts.log</span><span class="sxs-lookup"><span data-stu-id="836bb-507">%windir%\\System32\\ccm\\logs\\smsts.log</span></span>           |

> [!TIP]
> <span data-ttu-id="836bb-508">可以随时期间任务序列以打开命令控制台中，选择**F8** ，然后获取对 SMSTS.log 文件的访问。</span><span class="sxs-lookup"><span data-stu-id="836bb-508">You can select **F8** at any time during the task sequence to open a command console, and then get access to the SMSTS.log file.</span></span>

<span data-ttu-id="836bb-509">要解决 PXE 启动问题，请检查两个日志文件的配置管理器服务器上的特定于 PXE 操作：</span><span class="sxs-lookup"><span data-stu-id="836bb-509">To troubleshoot PXE boot issues, check the two log files on the Configuration Manager server that are specific to PXE actions:</span></span>

-   <span data-ttu-id="836bb-510">**Pxecontrol.log**，位于配置管理器安装日志目录</span><span class="sxs-lookup"><span data-stu-id="836bb-510">**Pxecontrol.log**, located in the Configuration Manager installation logs directory</span></span>

-   <span data-ttu-id="836bb-511">**Smspxe.log**，位于配置管理器管理点 (MP) 日志目录中</span><span class="sxs-lookup"><span data-stu-id="836bb-511">**Smspxe.log**, located in Configuration Manager Management Point (MP) logs directory</span></span>

<span data-ttu-id="836bb-512">您可以使用进一步解决配置管理器安装的日志文件的完整列表，请参阅[System Center Configuration Manager 中的日志文件](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/log-files)。</span><span class="sxs-lookup"><span data-stu-id="836bb-512">For a complete list of the log files that you can use to further troubleshoot your Configuration Manager installation, see [Log files in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/log-files).</span></span>
