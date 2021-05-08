---
title: 使用 Microsoft Teams 会议室 部署Microsoft Endpoint Configuration Manager
author: dstrome
ms.author: dstrome
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom:
- Strat_SB_Admin
- seo-marvel-apr2020
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
ms.collection:
- M365-collaboration
description: 了解如何使用 Microsoft Teams 会议室 大规模部署部署Microsoft Endpoint Configuration Manager。
no-loc:
- Microsoft
- Microsoft Corporation
- Microsoft Teams Rooms
- Microsoft Teams Room
- System Center
- Configuration Manager
- Windows
- Surface
- Surface Pro
- Windows PE
- Windows 10
- Windows 10 Enterprise
- Azure
- Azure Monitor
- Log Analytics
- Operations Management Suite
ms.openlocfilehash: 2348d0f3e9d94aed80494155fbaab8288ddd97a6
ms.sourcegitcommit: 95386369e2256ba382b4d6e34adb7473de050b26
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/29/2021
ms.locfileid: "51410108"
---
# <a name="deploy-microsoft-teams-rooms-by-using-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="2e302-103">使用 Microsoft Teams 会议室 部署Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="2e302-103">Deploy Microsoft Teams Rooms by using Microsoft Endpoint Configuration Manager</span></span>

<span data-ttu-id="2e302-104">本文提供了使用 Microsoft Endpoint Configuration Manager 创建 Microsoft Teams 会议室 部署所需的全部Microsoft Endpoint Configuration Manager。</span><span class="sxs-lookup"><span data-stu-id="2e302-104">This article gives you all the necessary information to create your Microsoft Teams Rooms deployments by using Microsoft Endpoint Configuration Manager.</span></span>

<span data-ttu-id="2e302-105">使用 Configuration Manager 提供的易用方法，可以将操作系统和其他应用程序部署到多个目标设备。</span><span class="sxs-lookup"><span data-stu-id="2e302-105">With the easy-to-use methods provided by Configuration Manager, you can deploy the operating system and other applications to multiple target devices.</span></span>

<span data-ttu-id="2e302-106">使用下面演示的方法指导完成配置管理器配置，并根据需要自定义本指南中提供的示例包和脚本。</span><span class="sxs-lookup"><span data-stu-id="2e302-106">Use the approach illustrated below to guide you through your Configuration Manager configuration, and customize the sample packages and scripts provided throughout this guidance as needed for your organization.</span></span>

![Microsoft Teams 会议室配置管理器管理部署过程](../media/room-systems-scale-image1.png)

> [!IMPORTANT]
> <span data-ttu-id="2e302-108">此解决方案仅通过基于 Surface Pro 的部署进行测试。</span><span class="sxs-lookup"><span data-stu-id="2e302-108">This solution has only been tested with Surface Pro–based deployments.</span></span> <span data-ttu-id="2e302-109">请遵循制造商针对不基于产品/服务的配置Surface Pro。</span><span class="sxs-lookup"><span data-stu-id="2e302-109">Follow the manufacturer's guidelines for configurations that aren't based on Surface Pro.</span></span>

## <a name="validate-prerequisites"></a><span data-ttu-id="2e302-110">验证先决条件</span><span class="sxs-lookup"><span data-stu-id="2e302-110">Validate prerequisites</span></span>

<span data-ttu-id="2e302-111">若要Microsoft Teams 会议室配置管理器部署资源，请确保满足以下先决条件和要求。</span><span class="sxs-lookup"><span data-stu-id="2e302-111">To deploy Microsoft Teams Rooms with Configuration Manager, ensure that you meet the following prerequisites and requirements.</span></span>

### <a name="microsoft-endpoint-configuration-manager-requirements"></a><span data-ttu-id="2e302-112">Microsoft Endpoint Configuration Manager要求</span><span class="sxs-lookup"><span data-stu-id="2e302-112">Microsoft Endpoint Configuration Manager requirements</span></span>

-   <span data-ttu-id="2e302-113">Microsoft Endpoint Configuration Manager版本必须至少为 1706 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="2e302-113">Microsoft Endpoint Configuration Manager version must be at least 1706 or above.</span></span> <span data-ttu-id="2e302-114">建议使用 1710 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="2e302-114">We recommend using 1710 or later.</span></span> <span data-ttu-id="2e302-115">请查看[配置管理器Windows 10](/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client)支持，了解配置管理器Windows 10版本。</span><span class="sxs-lookup"><span data-stu-id="2e302-115">Check out [Support for Windows 10 in Configuration Manager](/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) to learn about the Windows 10 versions that Configuration Manager supports.</span></span>

-   <span data-ttu-id="2e302-116">必须安装适用于 Windows ADK (ADK) 支持Windows 10版本。</span><span class="sxs-lookup"><span data-stu-id="2e302-116">A supported version of Windows Assessment and Deployment Kit (ADK) for Windows 10 must be installed.</span></span> <span data-ttu-id="2e302-117">请参阅适用于配置管理器Windows 10版本的[ADK](/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-adk)版本，并确保部署包含正确的版本。</span><span class="sxs-lookup"><span data-stu-id="2e302-117">See the versions of the [Windows 10 ADK](/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-adk) that you can use with different versions of Configuration Manager, and ensure that your deployment includes the correct version.</span></span>

-   <span data-ttu-id="2e302-118">必须为站点系统服务器分配分发点角色，并且应该为预启动执行环境启用启动映像 [ (PXE](/configmgr/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network)) 启用网络发起的部署。</span><span class="sxs-lookup"><span data-stu-id="2e302-118">The site system servers must have been assigned the distribution point role, and the boot images should be enabled for [preboot execution environment (PXE) support](/configmgr/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network) to enable network-initiated deployments.</span></span> <span data-ttu-id="2e302-119">如果未启用 PXE 支持，可以使用 [可启动](/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) 媒体进行部署。</span><span class="sxs-lookup"><span data-stu-id="2e302-119">If PXE support isn't enabled, you can use [bootable media](/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) for your deployments.</span></span>

-   <span data-ttu-id="2e302-120">必须将网络访问帐户配置为支持新计算机 (裸机) 方案。</span><span class="sxs-lookup"><span data-stu-id="2e302-120">A network access account must be configured to support new computer (bare metal) deployment scenarios.</span></span> <span data-ttu-id="2e302-121">若要详细了解网络访问帐户的配置，请参阅配置管理器 [中使用的帐户](/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA)。</span><span class="sxs-lookup"><span data-stu-id="2e302-121">To learn more about the configuration of a network access account, see [Accounts used in Configuration Manager](/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span></span>

-   <span data-ttu-id="2e302-122">如果可能会同时[将同一映像](/configmgr/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network)部署到多个Microsoft Teams 会议室，建议启用多播支持。</span><span class="sxs-lookup"><span data-stu-id="2e302-122">We recommend that you enable [multicast support](/configmgr/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network), if you're likely to deploy the same Microsoft Teams Rooms image to multiple units at the same time.</span></span>

### <a name="networking-requirements"></a><span data-ttu-id="2e302-123">网络要求</span><span class="sxs-lookup"><span data-stu-id="2e302-123">Networking requirements</span></span>

-   <span data-ttu-id="2e302-124">网络应具有一个动态主机配置协议 (DHCP) 服务器，该服务器配置为自动将 IP 地址分发到Microsoft Teams 会议室单元的子网。</span><span class="sxs-lookup"><span data-stu-id="2e302-124">Your network should have a Dynamic Host Configuration Protocol (DHCP) server, configured for automatic IP address distribution to the subnets where Microsoft Teams Rooms units will be deployed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2e302-125">DHCP 租约持续时间必须设置为大于映像部署持续时间的值。</span><span class="sxs-lookup"><span data-stu-id="2e302-125">DHCP lease duration must be set to a value longer than the image deployment duration.</span></span> <span data-ttu-id="2e302-126">否则，部署可能会失败。</span><span class="sxs-lookup"><span data-stu-id="2e302-126">Otherwise, the deployment might fail.</span></span>

-   <span data-ttu-id="2e302-127">网络（包括交换机和虚拟 (VLAN) ）应配置为支持 PXE。</span><span class="sxs-lookup"><span data-stu-id="2e302-127">Your network, including switches and virtual LANs (VLANs), should be configured to support PXE.</span></span> <span data-ttu-id="2e302-128">有关 IP 帮助程序与 PXE 配置的信息，请参阅网络供应商。</span><span class="sxs-lookup"><span data-stu-id="2e302-128">Refer to your network vendor for more information about IP Helper and PXE configuration.</span></span> <span data-ttu-id="2e302-129">或者，如果 [PXE](/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) 支持未启用，可以使用可启动媒体进行部署。</span><span class="sxs-lookup"><span data-stu-id="2e302-129">Alternatively, you can use [bootable media](/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) for your deployments, if PXE support isn't enabled.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2e302-130">对于Surface Pro，只有在使用 Microsoft 的以太网适配器或扩展坞 (PXE) 时，才支持从网络启动。</span><span class="sxs-lookup"><span data-stu-id="2e302-130">For Surface Pro devices, booting from the network (PXE boot) is only supported when you use an Ethernet adapter or docking station from Microsoft.</span></span> <span data-ttu-id="2e302-131">第三方以太网适配器不支持使用 PXE Surface Pro。</span><span class="sxs-lookup"><span data-stu-id="2e302-131">Third-party Ethernet adapters don't support PXE boot with Surface Pro.</span></span> <span data-ttu-id="2e302-132">有关详细信息 [，请参阅以太网适配器和 Surface](/surface/ethernet-adapters-and-surface-device-deployment) 部署。</span><span class="sxs-lookup"><span data-stu-id="2e302-132">See [Ethernet adapters and Surface deployment](/surface/ethernet-adapters-and-surface-device-deployment) for more information.</span></span>

## <a name="configure-microsoft-endpoint-configuration-manager-for-operating-system-deployment"></a><span data-ttu-id="2e302-133">为Microsoft Endpoint Configuration Manager配置配置</span><span class="sxs-lookup"><span data-stu-id="2e302-133">Configure Microsoft Endpoint Configuration Manager for operating system deployment</span></span>

<span data-ttu-id="2e302-134">本文假定你已拥有正常的 Configuration Manager 部署，并且未详细说明从头开始部署和配置配置管理器所需的所有步骤。</span><span class="sxs-lookup"><span data-stu-id="2e302-134">This article assumes you already have a healthy Configuration Manager deployment, and doesn't detail all the steps required to deploy and configure Configuration Manager from scratch.</span></span> <span data-ttu-id="2e302-135">有关[开发环境的文档](/configmgr/)和Microsoft Endpoint Configuration Manager是一个很好的资源;如果尚未部署配置管理器，建议从这些资源着手。</span><span class="sxs-lookup"><span data-stu-id="2e302-135">The [documentation and the configuration guidance](/configmgr/) on the Microsoft Endpoint Configuration Manager is a great resource; we recommend you start with these resources if you haven't yet deployed Configuration Manager.</span></span>

<span data-ttu-id="2e302-136">使用以下说明验证 OSD (配置) 操作系统部署。</span><span class="sxs-lookup"><span data-stu-id="2e302-136">Use the following instructions to verify that the operating system deployment (OSD) features are configured properly.</span></span>

### <a name="validate-and-upgrade-configuration-manager"></a><span data-ttu-id="2e302-137">验证和升级配置管理器</span><span class="sxs-lookup"><span data-stu-id="2e302-137">Validate and upgrade Configuration Manager</span></span>

1.  <span data-ttu-id="2e302-138">在配置管理器控制台中，转到 **"管理更新** \> **"和"服务"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-138">In the Configuration Manager console, go to **Administration** \> **Updates and Servicing**.</span></span>

2.  <span data-ttu-id="2e302-139">检查已安装的生成和尚未安装的适用更新。</span><span class="sxs-lookup"><span data-stu-id="2e302-139">Check the installed build and applicable updates that haven't been installed yet.</span></span>

3.  <span data-ttu-id="2e302-140">查看 [配置管理器Windows 10支持;](/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client)如果需要升级部署，请选择要安装的更新，然后选择"下载 **"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-140">Review [Support for Windows 10 in Configuration Manager](/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client); if you need to upgrade your deployment, select the update you want to install, and then select **Download**.</span></span>

4.  <span data-ttu-id="2e302-141">下载完成后，选择更新，然后选择"**安装更新包"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-141">After the download is complete, select the update, and then select **Install Update Pack**.</span></span>

### <a name="configure-distribution-points-to-support-pxe-and-multicast"></a><span data-ttu-id="2e302-142">配置分发点以支持 PXE 和多播</span><span class="sxs-lookup"><span data-stu-id="2e302-142">Configure distribution points to support PXE and multicast</span></span>

1.  <span data-ttu-id="2e302-143">在配置管理器控制台中，转到 **"管理** \> **分发点"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-143">In the Configuration Manager console, go to **Administration** \> **Distribution Points**.</span></span>

2.  <span data-ttu-id="2e302-144">选择用于部署部署的分发点Microsoft Teams 会议室，然后选择"属性 **"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-144">Select the distribution point server that will serve the Microsoft Teams Rooms deployment, and then select **Properties**.</span></span>

3.  <span data-ttu-id="2e302-145">选择 **"PXE"** 选项卡，并确保已启用以下设置：</span><span class="sxs-lookup"><span data-stu-id="2e302-145">Select the **PXE** tab, and ensure that the following settings are enabled:</span></span>
    -   <span data-ttu-id="2e302-146">为客户端启用 PXE 支持</span><span class="sxs-lookup"><span data-stu-id="2e302-146">Enable PXE support for clients</span></span>
    -   <span data-ttu-id="2e302-147">允许此分发点响应传入的 PXE 请求</span><span class="sxs-lookup"><span data-stu-id="2e302-147">Allow this distribution point to respond to incoming PXE requests</span></span>
    -   <span data-ttu-id="2e302-148">启用未知的计算机支持</span><span class="sxs-lookup"><span data-stu-id="2e302-148">Enable unknown computer support</span></span>

4.  <span data-ttu-id="2e302-149">*可选：* 若要启用多播支持，请选择" **多** 播"选项卡，并确保启用以下设置：</span><span class="sxs-lookup"><span data-stu-id="2e302-149">*Optional:* To enable multicast support, select the **Multicast** tab, and ensure that the following settings are enabled:</span></span>
    -   <span data-ttu-id="2e302-150">启用多播以同时将数据发送到多个客户端</span><span class="sxs-lookup"><span data-stu-id="2e302-150">Enable multicast to simultaneously send data to multiple clients</span></span>
    -   <span data-ttu-id="2e302-151">根据网络团队的建议配置 UDP 端口范围</span><span class="sxs-lookup"><span data-stu-id="2e302-151">Configure the UDP port range as per your network team's recommendation</span></span>

### <a name="configure-the-network-access-account"></a><span data-ttu-id="2e302-152">配置网络访问帐户</span><span class="sxs-lookup"><span data-stu-id="2e302-152">Configure the Network Access Account</span></span>

1.  <span data-ttu-id="2e302-153">在配置管理器控制台中，转到" **管理** \> **站点配置** \> **站点**"，然后选择站点。</span><span class="sxs-lookup"><span data-stu-id="2e302-153">In the Configuration Manager console, go to **Administration** \> **Site Configuration** \> **Sites**, and then select the site.</span></span>

2.  <span data-ttu-id="2e302-154">在 **"设置"** 组中，选择 **"配置站点组件** \> **软件分发"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-154">In the **Settings** group, select **Configure Site Components** \> **Software Distribution**.</span></span>

3.  <span data-ttu-id="2e302-155">选择"**网络访问帐户"** 选项卡。设置一个或多个帐户，然后选择"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-155">Select the **Network Access Account** tab. Set up one or more accounts, and then select **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="2e302-156">帐户不需要任何特殊权限，但从分发点服务器上网络访问此计算机除外。</span><span class="sxs-lookup"><span data-stu-id="2e302-156">The accounts don't need any special rights, except for the **Access this computer from the network** right on the distribution point server.</span></span> <span data-ttu-id="2e302-157">通用域用户帐户将适用。</span><span class="sxs-lookup"><span data-stu-id="2e302-157">A generic domain user account will be appropriate.</span></span> <span data-ttu-id="2e302-158">有关详细信息，请参阅 [配置管理器 中使用的帐户](/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA)。</span><span class="sxs-lookup"><span data-stu-id="2e302-158">For more information, see [Accounts used in Configuration Manager](/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span></span>

### <a name="configure-a-boot-image"></a><span data-ttu-id="2e302-159">配置启动映像</span><span class="sxs-lookup"><span data-stu-id="2e302-159">Configure a boot image</span></span>

1.  <span data-ttu-id="2e302-160">在配置管理器控制台中，转到 **"软件库** \> **操作系统** \> **启动映像"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-160">In the Configuration Manager console, go to **Software Library** \> **Operating System** \> **Boot Images**.</span></span>

2.  <span data-ttu-id="2e302-161">选择 **"启动映像 (x64) "，** 然后选择"属性 **"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-161">Select **Boot image (x64)**, and then select **Properties**.</span></span>

3.  <span data-ttu-id="2e302-162">选择"**数据源"** 选项卡，然后从已启用 PXE 的分发点启用"部署 **此启动映像"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-162">Select the **Data Source** tab, and enable **Deploy this boot image from the PXE-enabled distribution point**.</span></span>

4.  <span data-ttu-id="2e302-163">选择" **可选组件"** 选项卡以安装所需的组件：</span><span class="sxs-lookup"><span data-stu-id="2e302-163">Select the **Optional Components** tab to install required components:</span></span>

    1.  <span data-ttu-id="2e302-164">选择星形图标，然后搜索 **WINPE-HTA (HTML)**</span><span class="sxs-lookup"><span data-stu-id="2e302-164">Select the star icon, and search for **HTML (WinPE-HTA)**</span></span>

    2.  <span data-ttu-id="2e302-165">选择 **"** 确定"，将 HTML 应用程序支持添加到启动映像。</span><span class="sxs-lookup"><span data-stu-id="2e302-165">Select **OK** to add HTML application support in to the boot image.</span></span>

5.  <span data-ttu-id="2e302-166">*可选：* 若要自定义部署体验，请选择"自定义 **"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="2e302-166">*Optional:* To customize the deployment experience, select the **Customization** tab.</span></span>
    -   <span data-ttu-id="2e302-167">若要 **在 (访问命令) ，** 才启用命令支持以测试。</span><span class="sxs-lookup"><span data-stu-id="2e302-167">Enable **command support (testing only)** if you want to have access to a command prompt during the deployment.</span></span> <span data-ttu-id="2e302-168">启用此功能后，可以在部署过程中随时通过选择 **F8** 来启动命令提示符。</span><span class="sxs-lookup"><span data-stu-id="2e302-168">When this is enabled, you can start a command prompt by selecting **F8** at any time during the deployment.</span></span>
    -   <span data-ttu-id="2e302-169">还可以指定在部署期间显示的自定义背景映像。</span><span class="sxs-lookup"><span data-stu-id="2e302-169">You can also specify a custom background image to be displayed during the deployment.</span></span> <span data-ttu-id="2e302-170">若要设置图像，请启用 **"在 UNC 路径 (自定义背景图像文件并选择** 背景。</span><span class="sxs-lookup"><span data-stu-id="2e302-170">To set an image, enable **Specify the custom background image file (UNC path** and select your background.</span></span>

6.  <span data-ttu-id="2e302-171">当系统询问时 **，选择** "是"，并将更新的启动映像分发到分发点。</span><span class="sxs-lookup"><span data-stu-id="2e302-171">When asked, select **Yes** and distribute the updated boot image to your distribution points.</span></span>

<span data-ttu-id="2e302-172">有关详细信息，请参阅使用 [Configuration Manager 管理启动映像](/configmgr/osd/get-started/manage-boot-images)。</span><span class="sxs-lookup"><span data-stu-id="2e302-172">For more information, see [Manage boot images with Configuration Manager](/configmgr/osd/get-started/manage-boot-images).</span></span>

> [!NOTE]
> <span data-ttu-id="2e302-173">可以创建可启动的 USB 媒体，为没有 PXE 支持的环境启动基于配置管理器任务序列的部署。</span><span class="sxs-lookup"><span data-stu-id="2e302-173">You can create a bootable USB media to initiate Configuration Manager task sequence–based deployments for environments that have no PXE support.</span></span> <span data-ttu-id="2e302-174">可启动媒体仅包含启动映像、可选预启动命令及其所需文件，以及 Configuration Manager 二进制文件，用于支持启动到 Windows PE 并连接到 Configuration Manager 以完成部署过程的其余部分。</span><span class="sxs-lookup"><span data-stu-id="2e302-174">The bootable media contains only the boot image, optional prestart commands and their required files, and Configuration Manager binaries to support booting into Windows PE and connecting to Configuration Manager for the rest of the deployment process.</span></span> <span data-ttu-id="2e302-175">有关详细信息，请参阅 [创建可启动媒体](/configmgr/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia)。</span><span class="sxs-lookup"><span data-stu-id="2e302-175">For more information, see [Create bootable media](/configmgr/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia).</span></span>

## <a name="create-configuration-manager-packages"></a><span data-ttu-id="2e302-176">创建配置管理器包</span><span class="sxs-lookup"><span data-stu-id="2e302-176">Create Configuration Manager packages</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2e302-177">每个 SRS 安装程序版本所需的操作系统版本随每个 MSI 版本而更改。</span><span class="sxs-lookup"><span data-stu-id="2e302-177">The required operating system version for each SRS installer version changes with every MSI release.</span></span> <span data-ttu-id="2e302-178">若要确定给定 MSI 的最佳操作系统版本，请运行控制台设置脚本一次。</span><span class="sxs-lookup"><span data-stu-id="2e302-178">To determine the best operating system version for a given MSI, run the console setup script once.</span></span> <span data-ttu-id="2e302-179">有关详细信息，请参阅使用 Microsoft Teams 会议室[部署Microsoft Endpoint Configuration Manager。](rooms-scale.md)</span><span class="sxs-lookup"><span data-stu-id="2e302-179">To learn more, see [Deploy Microsoft Teams Rooms by using Microsoft Endpoint Configuration Manager](rooms-scale.md).</span></span>

<span data-ttu-id="2e302-180">配置管理器需要多个包来部署和配置Microsoft Teams 会议室单元。</span><span class="sxs-lookup"><span data-stu-id="2e302-180">Configuration Manager requires a number of packages to deploy and configure the Microsoft Teams Rooms units.</span></span>

<span data-ttu-id="2e302-181">需要创建并配置以下包，并将其分发到已分配有分发点服务器角色的 Configuration Manager 站点系统。</span><span class="sxs-lookup"><span data-stu-id="2e302-181">You need to create and configure the following packages, and then distribute them to the Configuration Manager site systems that have been assigned the distribution point server role.</span></span>

| <span data-ttu-id="2e302-182">**包名称**</span><span class="sxs-lookup"><span data-stu-id="2e302-182">**Package name**</span></span>                     | <span data-ttu-id="2e302-183">**类型**</span><span class="sxs-lookup"><span data-stu-id="2e302-183">**Type**</span></span>               | <span data-ttu-id="2e302-184">**说明**</span><span class="sxs-lookup"><span data-stu-id="2e302-184">**Description**</span></span>                                                                           |
|--------------------------------------|------------------------|-------------------------------------------------------------------------------------------|
| <span data-ttu-id="2e302-185">SRS v2 - SRS 应用程序包</span><span class="sxs-lookup"><span data-stu-id="2e302-185">SRS v2 - SRS Application Package</span></span>     | <span data-ttu-id="2e302-186">软件包</span><span class="sxs-lookup"><span data-stu-id="2e302-186">Software package</span></span>       | <span data-ttu-id="2e302-187">部署工具包Microsoft Teams 会议室包</span><span class="sxs-lookup"><span data-stu-id="2e302-187">Package for the Microsoft Teams Rooms deployment kit</span></span>                                      |
| <span data-ttu-id="2e302-188">SRS v2 - Sysprep 包</span><span class="sxs-lookup"><span data-stu-id="2e302-188">SRS v2 - Sysprep Package</span></span>             | <span data-ttu-id="2e302-189">软件包</span><span class="sxs-lookup"><span data-stu-id="2e302-189">Software package</span></span>       | <span data-ttu-id="2e302-190">用于配置每个Unattended.xml的自定义Microsoft Teams 会议室包</span><span class="sxs-lookup"><span data-stu-id="2e302-190">Package for the custom Unattended.xml to configure Microsoft Teams Rooms units</span></span>            |
| <span data-ttu-id="2e302-191">SRS v2 - Set-SRSComputerName 包</span><span class="sxs-lookup"><span data-stu-id="2e302-191">SRS v2 - Set-SRSComputerName Package</span></span> | <span data-ttu-id="2e302-192">软件包</span><span class="sxs-lookup"><span data-stu-id="2e302-192">Software package</span></span>       | <span data-ttu-id="2e302-193">HTML 应用程序的包 (HTA) ，以在部署期间分配计算机名称</span><span class="sxs-lookup"><span data-stu-id="2e302-193">Package for the HTML application (HTA) to assign a computer name during the deployment</span></span>    |
| <span data-ttu-id="2e302-194">SRS v2 - 配置 SRS 设置</span><span class="sxs-lookup"><span data-stu-id="2e302-194">SRS v2 - Configure SRS Setup</span></span>         | <span data-ttu-id="2e302-195">软件包</span><span class="sxs-lookup"><span data-stu-id="2e302-195">Software package</span></span>       | <span data-ttu-id="2e302-196">用于配置应用部署Microsoft Teams 会议室包</span><span class="sxs-lookup"><span data-stu-id="2e302-196">Package to configure deployment of the Microsoft Teams Rooms app</span></span>                          |
| <span data-ttu-id="2e302-197">SRS v2 - OS 更新包</span><span class="sxs-lookup"><span data-stu-id="2e302-197">SRS v2 - OS Updates Package</span></span>          | <span data-ttu-id="2e302-198">软件包</span><span class="sxs-lookup"><span data-stu-id="2e302-198">Software package</span></span>       | <span data-ttu-id="2e302-199">部署强制操作系统更新的包</span><span class="sxs-lookup"><span data-stu-id="2e302-199">Package to deploy mandatory operating system updates</span></span>                                      |
| <span data-ttu-id="2e302-200">SRS v2 - 根证书包</span><span class="sxs-lookup"><span data-stu-id="2e302-200">SRS v2 - Root Certificate Package</span></span>    | <span data-ttu-id="2e302-201">软件包</span><span class="sxs-lookup"><span data-stu-id="2e302-201">Software package</span></span>       | <span data-ttu-id="2e302-202">可选 - 用于部署根证书的包 (已加入域的单元不需要) </span><span class="sxs-lookup"><span data-stu-id="2e302-202">Optional - Package to deploy the root certificate (not required for domain-joined units)</span></span>  |
| <span data-ttu-id="2e302-203">SRS v2 - Microsoft Monitoring Agent 包</span><span class="sxs-lookup"><span data-stu-id="2e302-203">SRS v2 - Microsoft Monitoring Agent Package</span></span> | <span data-ttu-id="2e302-204">软件包</span><span class="sxs-lookup"><span data-stu-id="2e302-204">Software package</span></span>       | <span data-ttu-id="2e302-205">可选 - 用于部署和配置 Microsoft Operations Management Suite 代理的包</span><span class="sxs-lookup"><span data-stu-id="2e302-205">Optional - Package to deploy and configure the Microsoft Operations Management Suite agent</span></span>|
| <span data-ttu-id="2e302-206">SRS v2 - WinPE 后台包</span><span class="sxs-lookup"><span data-stu-id="2e302-206">SRS v2 - WinPE Background Package</span></span>    | <span data-ttu-id="2e302-207">软件包</span><span class="sxs-lookup"><span data-stu-id="2e302-207">Software package</span></span>       | <span data-ttu-id="2e302-208">要用于启动映像的自定义背景映像的包</span><span class="sxs-lookup"><span data-stu-id="2e302-208">Package for the custom background image to use with boot images</span></span>                           |
| <span data-ttu-id="2e302-209">Windows 10 企业版</span><span class="sxs-lookup"><span data-stu-id="2e302-209">Windows 10 Enterprise</span></span>                | <span data-ttu-id="2e302-210">操作系统映像</span><span class="sxs-lookup"><span data-stu-id="2e302-210">Operating system image</span></span> | <span data-ttu-id="2e302-211">install.wim (操作系统安装文件的) </span><span class="sxs-lookup"><span data-stu-id="2e302-211">Package for the operating system installation file (install.wim)</span></span>                          |
| <span data-ttu-id="2e302-212">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="2e302-212">Surface Pro</span></span>                          | <span data-ttu-id="2e302-213">驱动程序包</span><span class="sxs-lookup"><span data-stu-id="2e302-213">Driver package</span></span>         | <span data-ttu-id="2e302-214">适用于 Microsoft Surface Pro 的设备驱动程序和固件Surface Pro</span><span class="sxs-lookup"><span data-stu-id="2e302-214">Package for the device drivers and firmware for Microsoft Surface Pro</span></span>                     |
| <span data-ttu-id="2e302-215">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="2e302-215">Surface Pro 4</span></span>                        | <span data-ttu-id="2e302-216">驱动程序包</span><span class="sxs-lookup"><span data-stu-id="2e302-216">Driver package</span></span>         | <span data-ttu-id="2e302-217">适用于 Microsoft Surface Pro 4 的设备驱动程序和固件Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="2e302-217">Package for the device drivers and firmware for Microsoft Surface Pro 4</span></span>                   |

<span data-ttu-id="2e302-218">有关详细信息，请参阅 Configuration [Manager 中的包和程序](/configmgr/apps/deploy-use/packages-and-programs)。</span><span class="sxs-lookup"><span data-stu-id="2e302-218">For more information, see [Packages and programs in Configuration Manager](/configmgr/apps/deploy-use/packages-and-programs).</span></span>

### <a name="create-folders-for-the-package-source-files"></a><span data-ttu-id="2e302-219">为包源文件创建文件夹</span><span class="sxs-lookup"><span data-stu-id="2e302-219">Create folders for the package source files</span></span>

<span data-ttu-id="2e302-220">配置管理器要求包源文件在首次创建和更新时按特定文件夹结构进行组织。</span><span class="sxs-lookup"><span data-stu-id="2e302-220">Configuration Manager requires package source files to be organized in a specific folder structure when they're first created and when they're updated.</span></span>

<span data-ttu-id="2e302-221">在管理中心站点或主Microsoft Endpoint Configuration Manager或用于托管包源文件的服务器共享上创建以下文件夹结构：</span><span class="sxs-lookup"><span data-stu-id="2e302-221">Create the following folder structure on the Microsoft Endpoint Configuration Manager central administration site or primary site, or on a server share you're using to host package source files:</span></span>

-   <span data-ttu-id="2e302-222">SRS v2 - Microsoft Monitoring Agent 包</span><span class="sxs-lookup"><span data-stu-id="2e302-222">SRS v2 - Microsoft Monitoring Agent Package</span></span>
-   <span data-ttu-id="2e302-223">SRS v2 - OS 更新包</span><span class="sxs-lookup"><span data-stu-id="2e302-223">SRS v2 - OS Updates Package</span></span>
-   <span data-ttu-id="2e302-224">SRS v2 - 根证书包</span><span class="sxs-lookup"><span data-stu-id="2e302-224">SRS v2 - Root Certificate Package</span></span>
-   <span data-ttu-id="2e302-225">SRS v2 - Set-SRSComputerName 包</span><span class="sxs-lookup"><span data-stu-id="2e302-225">SRS v2 - Set-SRSComputerName Package</span></span>
-   <span data-ttu-id="2e302-226">SRS v2 - SRS 应用程序包</span><span class="sxs-lookup"><span data-stu-id="2e302-226">SRS v2 - SRS Application Package</span></span>
-   <span data-ttu-id="2e302-227">SRS v2 - 配置 SRS 设置</span><span class="sxs-lookup"><span data-stu-id="2e302-227">SRS v2 - Configure SRS Setup</span></span>
-   <span data-ttu-id="2e302-228">SRS v2 - Sysprep 包</span><span class="sxs-lookup"><span data-stu-id="2e302-228">SRS v2 - Sysprep Package</span></span>
-   <span data-ttu-id="2e302-229">驱动程序</span><span class="sxs-lookup"><span data-stu-id="2e302-229">Drivers</span></span>
    -   <span data-ttu-id="2e302-230">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="2e302-230">Surface Pro</span></span>
    -   <span data-ttu-id="2e302-231">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="2e302-231">Surface Pro 4</span></span>
-   <span data-ttu-id="2e302-232">操作系统</span><span class="sxs-lookup"><span data-stu-id="2e302-232">Operating Systems</span></span>
    -   <span data-ttu-id="2e302-233">Windows 10 企业版</span><span class="sxs-lookup"><span data-stu-id="2e302-233">Windows 10 Enterprise</span></span>

> [!TIP]
> <span data-ttu-id="2e302-234">还可以下载 [并使用](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) zip 文件，其中包含包的文件夹结构、需要使用的脚本以及需要导入的任务序列模板。</span><span class="sxs-lookup"><span data-stu-id="2e302-234">You may also [download](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) and use the zip file that includes the folder structure for the packages, the scripts that you need to use, and the task sequence template, that you need to import.</span></span>

### <a name="create-the-monitoring-agent-package"></a><span data-ttu-id="2e302-235">创建监视代理包</span><span class="sxs-lookup"><span data-stu-id="2e302-235">Create the Monitoring agent package</span></span>

1. <span data-ttu-id="2e302-236">从 下载监视代理 <https://go.microsoft.com/fwlink/?LinkId=828603> 。</span><span class="sxs-lookup"><span data-stu-id="2e302-236">Download the Monitoring agent from <https://go.microsoft.com/fwlink/?LinkId=828603>.</span></span>

2. <span data-ttu-id="2e302-237">打开命令提示符窗口，在命令提示符下输入MMASetup-AMD64.exe **/C：** ，将包提取到 **SRS v2 -** Microsoft Monitoring Agent Package 文件夹。</span><span class="sxs-lookup"><span data-stu-id="2e302-237">Extract the package into the **SRS v2 - Microsoft Monitoring Agent Package** folder by opening a Command Prompt window and entering **MMASetup-AMD64.exe /C:**     at the command prompt.</span></span>

3. <span data-ttu-id="2e302-238">在配置管理器控制台中，转到 **"软件库** \> **应用程序管理** \> **包"，** 然后选择"**创建包"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-238">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4. <span data-ttu-id="2e302-239">输入以下信息以创建包：</span><span class="sxs-lookup"><span data-stu-id="2e302-239">Enter the following information to create the package:</span></span>

   - <span data-ttu-id="2e302-240">名称<strong>：SRS v2 - Microsoft Monitoring Agent包</strong></span><span class="sxs-lookup"><span data-stu-id="2e302-240">Name<strong>: SRS v2 - Microsoft Monitoring Agent Package</strong></span></span>

   - <span data-ttu-id="2e302-241">制造商<strong>：Microsoft Corporation</strong></span><span class="sxs-lookup"><span data-stu-id="2e302-241">Manufacturer<strong>: Microsoft Corporation</strong></span></span>

   - <span data-ttu-id="2e302-242">版本<strong>：8.1.11081.0</strong> (输入下载的安装文件版本) </span><span class="sxs-lookup"><span data-stu-id="2e302-242">Version<strong>: 8.1.11081.0</strong> (enter the version of the downloaded installation file)</span></span>

   - <span data-ttu-id="2e302-243">选中"**此包包含源文件"复选框**，输入 **SRS v2 -** Microsoft Monitoring Agent包文件夹的路径，然后选择"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-243">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Microsoft Monitoring Agent Package** folder, and then select **Next**.</span></span>

5. <span data-ttu-id="2e302-244">选择 **"不创建程序"，** 然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-244">Select **Do not create a program**, and then select **Next**.</span></span>

6. <span data-ttu-id="2e302-245">查看"**确认设置"页**，然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-245">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7. <span data-ttu-id="2e302-246">选择"**关闭"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-246">Select **Close**.</span></span>

### <a name="create-the-operating-system-updates-package"></a><span data-ttu-id="2e302-247">创建操作系统更新包</span><span class="sxs-lookup"><span data-stu-id="2e302-247">Create the operating system updates package</span></span>

1. <span data-ttu-id="2e302-248">在 **"SRS v2 - OS 更新包** "文件夹中，创建名为Install-SRSv2-OS-Updates.ps1 **的新 PowerShell 脚本**。</span><span class="sxs-lookup"><span data-stu-id="2e302-248">In the **SRS v2 - OS Updates Package** folder, create a new PowerShell script named **Install-SRSv2-OS-Updates.ps1**.</span></span>

2. <span data-ttu-id="2e302-249">将以下脚本复制到 **Install-SRSv2-OS-Updates.ps1** 脚本。</span><span class="sxs-lookup"><span data-stu-id="2e302-249">Copy the script below into the **Install-SRSv2-OS-Updates.ps1** script.</span></span> <span data-ttu-id="2e302-250">或者，可以从此处下载[Install-SRSv2-OS-Updates.ps1脚本。](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="2e302-250">Alternatively, you can download the Install-SRSv2-OS-Updates.ps1 script from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
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
3. <span data-ttu-id="2e302-251">将更新包Windows同一文件夹中。</span><span class="sxs-lookup"><span data-stu-id="2e302-251">Download the mandatory Windows Update packages into the same folder.</span></span>
   > [!NOTE]
   > <span data-ttu-id="2e302-252">在本文发布时，只需要[KB4056892。](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu)</span><span class="sxs-lookup"><span data-stu-id="2e302-252">At the time this article was published, only [KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) was required.</span></span> <span data-ttu-id="2e302-253">选中["Microsoft Teams 会议室](console.md)主机"，查看是否需要任何其他更新。</span><span class="sxs-lookup"><span data-stu-id="2e302-253">Check [Configure a Microsoft Teams Rooms console](console.md), to see whether any other updates are required.</span></span>

4. <span data-ttu-id="2e302-254">在配置管理器控制台中，转到 **"软件库** \> **应用程序管理** \> **包"，** 然后选择"**创建包"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-254">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

5. <span data-ttu-id="2e302-255">输入以下信息以创建包：</span><span class="sxs-lookup"><span data-stu-id="2e302-255">Enter the following information to create the package:</span></span>
   -   <span data-ttu-id="2e302-256">名称 **：SRS v2 – OS 更新包**</span><span class="sxs-lookup"><span data-stu-id="2e302-256">Name: **SRS v2 – OS Updates Package**</span></span>
   -   <span data-ttu-id="2e302-257">制造商 **：Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="2e302-257">Manufacturer: **Microsoft Corporation**</span></span>
   -   <span data-ttu-id="2e302-258">版本 **：1.0.0**</span><span class="sxs-lookup"><span data-stu-id="2e302-258">Version: **1.0.0**</span></span>
   -   <span data-ttu-id="2e302-259">选中"**此包包含源文件"复选框**，输入 **SRS v2 - OS 更新包** 文件夹的路径，然后选择"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-259">Select the **This package contains source files** check box, enter the path to the **SRS v2 - OS Updates Package** folder, and then select **Next**.</span></span>

6. <span data-ttu-id="2e302-260">选择 **"不创建程序"，** 然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-260">Select **Do not create a program**, and then select **Next**.</span></span>

7. <span data-ttu-id="2e302-261">查看"**确认设置"页**，然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-261">Review the **Confirm the settings** page, and then select **Next**.</span></span>

8. <span data-ttu-id="2e302-262">选择"**关闭"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-262">Select **Close**.</span></span>

### <a name="create-the-root-certificate-package-optional"></a><span data-ttu-id="2e302-263">创建根证书包 (可选) </span><span class="sxs-lookup"><span data-stu-id="2e302-263">Create the root certificate package (optional)</span></span>

<span data-ttu-id="2e302-264">创建此包，为不会加入 Active Directory 域的设备分发根证书。</span><span class="sxs-lookup"><span data-stu-id="2e302-264">You create this package to distribute the root certificate for devices that won't be joined to an Active Directory domain.</span></span> <span data-ttu-id="2e302-265">仅在以下两个条件都适用时创建此包：</span><span class="sxs-lookup"><span data-stu-id="2e302-265">Create this package only if both the following conditions apply:</span></span>
-   <span data-ttu-id="2e302-266">您的部署包括本地 Lync 或 Skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="2e302-266">Your deployment includes on-premises Lync or Skype for Business Server.</span></span>
-   <span data-ttu-id="2e302-267">Microsoft Teams 会议室单位配置为在工作组中工作，而不是在域成员中工作。</span><span class="sxs-lookup"><span data-stu-id="2e302-267">Microsoft Teams Rooms units are configured to work in a workgroup instead of a domain member.</span></span>

1.  <span data-ttu-id="2e302-268">将根证书复制到 **"SRS v2 – 根证书包"** 文件夹。</span><span class="sxs-lookup"><span data-stu-id="2e302-268">Copy the root certificate into the **SRS v2 – Root Certificate Package** folder.</span></span>

2.  <span data-ttu-id="2e302-269">在配置管理器控制台中，转到 **"软件库** \> **应用程序管理** \> **包"，** 然后选择"**创建包"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-269">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

3.  <span data-ttu-id="2e302-270">输入以下信息以创建包：</span><span class="sxs-lookup"><span data-stu-id="2e302-270">Enter the following information to create the package:</span></span>
    -   <span data-ttu-id="2e302-271">名称 **：SRS v2 – 根证书包**</span><span class="sxs-lookup"><span data-stu-id="2e302-271">Name: **SRS v2 – Root Certificate Package**</span></span>
    -   <span data-ttu-id="2e302-272">制造商 *：组织的名称*</span><span class="sxs-lookup"><span data-stu-id="2e302-272">Manufacturer: *Your organization's name*</span></span>
    -   <span data-ttu-id="2e302-273">版本 **：1.0.0**</span><span class="sxs-lookup"><span data-stu-id="2e302-273">Version: **1.0.0**</span></span>
    -   <span data-ttu-id="2e302-274">选中"**此包包含源文件"复选框**，输入 **SRS v2 –** 根证书包文件夹的路径，然后选择"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-274">Select the **This package contains source files** check box, enter the path to the **SRS v2 – Root Certificate Package** folder, and then select **Next**.</span></span>

4.  <span data-ttu-id="2e302-275">选择 **"不创建程序"，** 然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-275">Select **Do not create a program**, and then select **Next**.</span></span>

5.  <span data-ttu-id="2e302-276">查看"**确认设置"页**，然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-276">Review the **Confirm the settings** page, and then select **Next**.</span></span>

6.  <span data-ttu-id="2e302-277">选择"**关闭"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-277">Select **Close**.</span></span>

### <a name="create-the-microsoft-teams-rooms-deployment-kit-package"></a><span data-ttu-id="2e302-278">创建 Microsoft Teams 会议室 部署工具包包</span><span class="sxs-lookup"><span data-stu-id="2e302-278">Create the Microsoft Teams Rooms deployment kit package</span></span>

1.  <span data-ttu-id="2e302-279">从 下载最新版本的 **Microsoft Teams 会议室** 工具包 <https://go.microsoft.com/fwlink/?linkid=851168> ，并安装到工作站。</span><span class="sxs-lookup"><span data-stu-id="2e302-279">Download the latest version of the **Microsoft Teams Rooms deployment kit** from <https://go.microsoft.com/fwlink/?linkid=851168>, and install it to a workstation.</span></span>

2.  <span data-ttu-id="2e302-280">将内容从 **C： program \\ Files (x86) Skype \\ Room System Deployment Kit 复制到** **SRS v2 - SRS 应用程序包** 文件夹。</span><span class="sxs-lookup"><span data-stu-id="2e302-280">Copy the content from **C:\\Program Files (x86)\\Skype Room System Deployment Kit** to the **SRS v2 - SRS Application Package** folder.</span></span>

3.  <span data-ttu-id="2e302-281">在配置管理器控制台中，转到 **"软件库** \> **应用程序管理** \> **包"，** 然后选择"**创建包"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-281">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4.  <span data-ttu-id="2e302-282">输入以下信息以创建包：</span><span class="sxs-lookup"><span data-stu-id="2e302-282">Enter the following information to create the package:</span></span>
    -   <span data-ttu-id="2e302-283">名称 **：SRS v2 – SRS 应用程序包**</span><span class="sxs-lookup"><span data-stu-id="2e302-283">Name: **SRS v2 – SRS Application Package**</span></span>
    -   <span data-ttu-id="2e302-284">制造商 **：Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="2e302-284">Manufacturer: **Microsoft Corporation**</span></span>
    -   <span data-ttu-id="2e302-285">版本 **：3.1.104.0** (输入下载的安装文件版本) </span><span class="sxs-lookup"><span data-stu-id="2e302-285">Version: **3.1.104.0** (enter the version of the downloaded installation file)</span></span>
    -   <span data-ttu-id="2e302-286">选中"**此包包含源文件"复选框**，输入 **SRS v2 – SRS** 应用程序包文件夹的路径，然后选择"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-286">Select the **This package contains source files** check box, enter the path to the **SRS v2 – SRS Application Package** folder, and then select **Next**.</span></span>
5.  <span data-ttu-id="2e302-287">选择 **"不创建程序"，** 然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-287">Select **Do not create a program**, and then select **Next**.</span></span>

6.  <span data-ttu-id="2e302-288">查看"**确认设置"页**，然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-288">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7.  <span data-ttu-id="2e302-289">选择"**关闭"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-289">Select **Close**.</span></span>

### <a name="create-the-computer-name-assignment-package"></a><span data-ttu-id="2e302-290">创建计算机名称分配包</span><span class="sxs-lookup"><span data-stu-id="2e302-290">Create the computer name assignment package</span></span>

1.  <span data-ttu-id="2e302-291">在 **"SRS v2 - Set-SRSComputerName 包** "文件夹中，创建名为 **Set-SRSComputerName.hta 的新** HTML 应用程序。</span><span class="sxs-lookup"><span data-stu-id="2e302-291">In the **SRS v2 - Set-SRSComputerName Package** folder, create a new HTML application named **Set-SRSComputerName.hta** .</span></span>

2.  <span data-ttu-id="2e302-292">将以下脚本复制到 **Set-SRSComputerName.hta** 文件中。</span><span class="sxs-lookup"><span data-stu-id="2e302-292">Copy the following script into the **Set-SRSComputerName.hta** file.</span></span> <span data-ttu-id="2e302-293">或者，可以从此处下载 Set-SRSComputerName.hta [文件](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)。</span><span class="sxs-lookup"><span data-stu-id="2e302-293">Alternatively, you can download the Set-SRSComputerName.hta file from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
    ```HTML
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
3.  <span data-ttu-id="2e302-294">在配置管理器控制台中，转到 **"软件库** \> **应用程序管理** \> **包"，** 然后选择"**创建包"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-294">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4.  <span data-ttu-id="2e302-295">输入以下信息以创建包：</span><span class="sxs-lookup"><span data-stu-id="2e302-295">Enter the following information to create the package:</span></span>

    -   <span data-ttu-id="2e302-296">名称 **：SRS v2 - Set-SRSComputerName包**</span><span class="sxs-lookup"><span data-stu-id="2e302-296">Name: **SRS v2 - Set-SRSComputerName Package**</span></span>

    -   <span data-ttu-id="2e302-297">制造商 **：Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="2e302-297">Manufacturer: **Microsoft Corporation**</span></span>

    -   <span data-ttu-id="2e302-298">版本 **：1.0.0**</span><span class="sxs-lookup"><span data-stu-id="2e302-298">Version: **1.0.0**</span></span>

    -   <span data-ttu-id="2e302-299">选中"**此包包含源文件"复选框**，输入 **SRS v2 - Set-SRSComputerName包文件夹** 的路径，然后选择"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-299">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Set-SRSComputerName Package** folder, and then select **Next**.</span></span>

5.  <span data-ttu-id="2e302-300">选择 **"不创建程序"，** 然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-300">Select **Do not create a program**, and then select **Next**.</span></span>

6.  <span data-ttu-id="2e302-301">查看"**确认设置"页**，然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-301">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7.  <span data-ttu-id="2e302-302">选择"**关闭"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-302">Select **Close**.</span></span>

### <a name="create-the-sysprep-package"></a><span data-ttu-id="2e302-303">创建 Sysprep 包</span><span class="sxs-lookup"><span data-stu-id="2e302-303">Create the Sysprep package</span></span>

1. <span data-ttu-id="2e302-304">在 **"SRS v2 – Sysprep 包** "文件夹中，创建名为Unattend.xml **的新 XML 文件** 。</span><span class="sxs-lookup"><span data-stu-id="2e302-304">In the **SRS v2 – Sysprep Package** folder, create a new XML file named **Unattend.xml** .</span></span>

2. <span data-ttu-id="2e302-305">将以下文本复制到 **Unattend.xml** 文件中。</span><span class="sxs-lookup"><span data-stu-id="2e302-305">Copy the following text into the **Unattend.xml** file.</span></span> <span data-ttu-id="2e302-306">或者，可以从此处下载[Unattend.xml文件。](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="2e302-306">Alternatively, you can download the Unattend.xml file from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
   ```XML
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
3. <span data-ttu-id="2e302-307">在配置管理器控制台中，转到 **"软件库** \> **应用程序管理** \> **包"，** 然后选择"**创建包"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-307">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4. <span data-ttu-id="2e302-308">输入以下信息以创建包：</span><span class="sxs-lookup"><span data-stu-id="2e302-308">Enter the following information to create the package:</span></span>
   -   <span data-ttu-id="2e302-309">名称 **：SRS v2 - Sysprep 包**</span><span class="sxs-lookup"><span data-stu-id="2e302-309">Name: **SRS v2 - Sysprep Package**</span></span>
   -   <span data-ttu-id="2e302-310">制造商 **：Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="2e302-310">Manufacturer: **Microsoft Corporation**</span></span>
   -   <span data-ttu-id="2e302-311">版本 **：1.0.0**</span><span class="sxs-lookup"><span data-stu-id="2e302-311">Version: **1.0.0**</span></span>
   -   <span data-ttu-id="2e302-312">选中"**此包包含源文件"复选框**，输入 **SRS v2 – Sysprep 包** 文件夹的路径，然后选择"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-312">Select the **This package contains source files** check box, enter the path to the **SRS v2 – Sysprep Package** folder, and then select **Next**.</span></span>
5. <span data-ttu-id="2e302-313">选择 **"不创建程序"，** 然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-313">Select **Do not create a program**, and then select **Next**.</span></span>

6. <span data-ttu-id="2e302-314">查看"**确认设置"页**，然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-314">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7. <span data-ttu-id="2e302-315">选择"**关闭"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-315">Select **Close**.</span></span>

### <a name="create-the-windows-10-enterprise-package"></a><span data-ttu-id="2e302-316">创建Windows 10 企业版包</span><span class="sxs-lookup"><span data-stu-id="2e302-316">Create the Windows 10 Enterprise package</span></span>

1.  <span data-ttu-id="2e302-317">获取Windows 10 企业版 x64 媒体，将 **install.wim** 文件复制到 **操作系统 \\** Windows 10 企业版文件夹。</span><span class="sxs-lookup"><span data-stu-id="2e302-317">Obtain a Windows 10 Enterprise x64 media, and copy the **install.wim** file to the **Operating Systems\\Windows 10 Enterprise** folder.</span></span>

2.  <span data-ttu-id="2e302-318">在 Configuration Manager 控制台中，转到 **"软件库** \> **操作系统** \> **映像**"，然后选择"**添加操作系统映像"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-318">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Operating System Images**, and then select **Add Operating System Image**.</span></span>

3.  <span data-ttu-id="2e302-319">指定刚复制的 **install.wim** 文件的路径，然后选择"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-319">Specify the path to the **install.wim** file you just copied, and then select **Next**.</span></span>

4.  <span data-ttu-id="2e302-320">更新 **"版本**"字段以匹配映像Windows 10 企业版版本号，然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-320">Update the **Version** field to match the build number of the Windows 10 Enterprise image, and then select **Next**.</span></span>

5.  <span data-ttu-id="2e302-321">查看"**详细信息"** 页，然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-321">Review the **Details** page, and then select **Next**.</span></span>

6.  <span data-ttu-id="2e302-322">选择"**关闭"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-322">Select **Close**.</span></span>

<span data-ttu-id="2e302-323">有关详细信息，请参阅使用 [Configuration Manager 管理 OS 映像](/configmgr/osd/get-started/manage-operating-system-images)。</span><span class="sxs-lookup"><span data-stu-id="2e302-323">For more information, see [Manage OS images with Configuration Manager](/configmgr/osd/get-started/manage-operating-system-images).</span></span>

### <a name="create-surface-pro-device-driver-packages"></a><span data-ttu-id="2e302-324">创建Surface Pro驱动程序包</span><span class="sxs-lookup"><span data-stu-id="2e302-324">Create Surface Pro device driver packages</span></span>

<span data-ttu-id="2e302-325">Microsoft Teams 会议室和 Surface Pro 都Surface Pro 4。</span><span class="sxs-lookup"><span data-stu-id="2e302-325">Microsoft Teams Rooms is supported for both Surface Pro and Surface Pro 4.</span></span> <span data-ttu-id="2e302-326">需要为环境中具有的每个Surface Pro模型创建驱动程序包。</span><span class="sxs-lookup"><span data-stu-id="2e302-326">You need to create a driver package for each Surface Pro model you have in your environment.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2e302-327">驱动程序必须与内部版本Windows 10 企业版部署工具包Microsoft Teams 会议室兼容。</span><span class="sxs-lookup"><span data-stu-id="2e302-327">The drivers must be compatible with the Windows 10 Enterprise build and the Microsoft Teams Rooms deployment kit version.</span></span> <span data-ttu-id="2e302-328">有关详细信息，请参阅下载 [Surface 设备](/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices) 的最新固件和驱动程序和 [配置主机](console.md)。</span><span class="sxs-lookup"><span data-stu-id="2e302-328">For more information, see [Download the latest firmware and drivers for Surface devices](/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices) and [Configure a console](console.md).</span></span>

1.  <span data-ttu-id="2e302-329">下载最新的驱动程序和固件。</span><span class="sxs-lookup"><span data-stu-id="2e302-329">Download the latest drivers and firmware.</span></span>
    -   <span data-ttu-id="2e302-330">对于Surface Pro：<https://www.microsoft.com/download/details.aspx?id=55484></span><span class="sxs-lookup"><span data-stu-id="2e302-330">For Surface Pro: <https://www.microsoft.com/download/details.aspx?id=55484></span></span>
    -   <span data-ttu-id="2e302-331">对于Surface Pro 4：<https://www.microsoft.com/download/details.aspx?id=49498></span><span class="sxs-lookup"><span data-stu-id="2e302-331">For Surface Pro 4: <https://www.microsoft.com/download/details.aspx?id=49498></span></span>

2.  <span data-ttu-id="2e302-332">提取下载的驱动程序和固件。</span><span class="sxs-lookup"><span data-stu-id="2e302-332">Extract the downloaded driver and firmware.</span></span> <span data-ttu-id="2e302-333">打开命令提示符窗口，在命令提示符下输入以下命令之一：</span><span class="sxs-lookup"><span data-stu-id="2e302-333">Open a Command Prompt window and at the command prompt, enter one of the following commands:</span></span>
    -   `msiexec /a C:\SurfacePro_Win10.msi /passive TARGETDIR="C:\_Sources\Drivers\Surface Pro"`
    -   `msiexec /a C:\SurfacePro4_Win10.msi /passive TARGETDIR="C:\_Sources\Drivers\Surface Pro 4"`

3.  <span data-ttu-id="2e302-334">在 Configuration Manager 控制台中，转到 **"软件库** \> **操作系统** \> **驱动程序**"，然后选择"**导入驱动程序"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-334">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Drivers**, and then select **Import Driver**.</span></span>

4.  <span data-ttu-id="2e302-335">选择 **"导入以下网络** 路径 (UNC) 的所有驱动程序"，选择源文件夹 (例如 C： _Sources 驱动程序Surface Pro) ，然后选择"下一 \\ \\ \\ 步"。 </span><span class="sxs-lookup"><span data-stu-id="2e302-335">Select **Import all drivers in the following network path (UNC)**, select the source folder (for example, C:\\_Sources\\Drivers\\Surface Pro), and then select **Next**.</span></span>

5.  <span data-ttu-id="2e302-336">在 **"指定导入的驱动程序** 的详细信息"页上，选择列出的所有驱动程序，然后选择"启用这些驱动程序并允许计算机 **安装它们"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-336">On the **Specify the details for the imported drivers** page, select all the listed drivers, and then select **Enable these drivers and allow computers to install them**.</span></span>

6.  <span data-ttu-id="2e302-337">选择 **"** 类别"，创建与 Surface 模型匹配的新类别，选择"**确定**"，然后选择"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-337">Select **Categories**, create a new category that matches the Surface model, select **OK**, and then select **Next**.</span></span>

7.  <span data-ttu-id="2e302-338">选择 **"新建包"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-338">Select **New Package**.</span></span>

8.  <span data-ttu-id="2e302-339">指定与模型匹配的包Surface Pro，输入用于存储驱动程序包文件的文件夹路径，选择"确定"，然后选择"下一步 **"。** </span><span class="sxs-lookup"><span data-stu-id="2e302-339">Specify the package name that matches the Surface Pro model, enter a folder path to store the driver package files in, select **OK**, and then select **Next**.</span></span>

9.  <span data-ttu-id="2e302-340">在"**启动映像"** 页上，确保未选择任何启动映像，然后选择"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-340">On the **boot images** page, ensure that no boot images are selected, and then select **Next**.</span></span>

10. <span data-ttu-id="2e302-341">选择"**关闭"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-341">Select **Close**.</span></span>

11. <span data-ttu-id="2e302-342">转到 **"软件库** 操作系统驱动程序"，选择"文件夹创建文件夹"，并输入与刚导入驱动程序Surface Pro \>  \> 模型相匹配的文件夹名称。 **\>**</span><span class="sxs-lookup"><span data-stu-id="2e302-342">Go to **Software Library** \> **Operating Systems** \> **Drivers**, select **Folder \> Create Folder**, and enter a folder name that matches the Surface Pro model that you just imported the drivers for.</span></span>

12. <span data-ttu-id="2e302-343">将导入的所有驱动程序移到新创建的文件夹，以便更轻松地导航和操作。</span><span class="sxs-lookup"><span data-stu-id="2e302-343">Move all the imported drivers to the newly created folder for easier navigation and operation.</span></span>

> [!NOTE]
> <span data-ttu-id="2e302-344">对可能拥有的其他Surface Pro重复相同的步骤。</span><span class="sxs-lookup"><span data-stu-id="2e302-344">Repeat the same steps for other Surface Pro models you might have.</span></span> <span data-ttu-id="2e302-345">有关详细信息，请参阅在 [Configuration Manager 中管理驱动程序](/configmgr/osd/get-started/manage-drivers)。</span><span class="sxs-lookup"><span data-stu-id="2e302-345">For more information, see [Manage drivers in Configuration Manager](/configmgr/osd/get-started/manage-drivers).</span></span>

### <a name="create-microsoft-teams-rooms-configuration-package"></a><span data-ttu-id="2e302-346">创建Microsoft Teams 会议室配置包</span><span class="sxs-lookup"><span data-stu-id="2e302-346">Create Microsoft Teams Rooms Configuration Package</span></span>

1.  <span data-ttu-id="2e302-347">在配置管理器控制台中，转到 **"软件库** \> **应用程序管理** \> **包"，** 然后选择"**创建包"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-347">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

2.  <span data-ttu-id="2e302-348">输入以下信息以创建包：</span><span class="sxs-lookup"><span data-stu-id="2e302-348">Enter the following information to create the package:</span></span>

    -   <span data-ttu-id="2e302-349">名称 **：SRS v2 - 配置 SRS 安装包**</span><span class="sxs-lookup"><span data-stu-id="2e302-349">Name: **SRS v2 - Configure SRS Setup Package**</span></span>

    -   <span data-ttu-id="2e302-350">制造商 **：Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="2e302-350">Manufacturer: **Microsoft Corporation**</span></span>

    -   <span data-ttu-id="2e302-351">版本 **：1.0.0**</span><span class="sxs-lookup"><span data-stu-id="2e302-351">Version: **1.0.0**</span></span>

    -   <span data-ttu-id="2e302-352">选中"**此包包含源文件"复选框**，输入 **SRS v2 - 配置 SRS 安装程序** 文件夹的路径，然后选择"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-352">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Configure SRS Setup** folder, and then select **Next**.</span></span>

3.  <span data-ttu-id="2e302-353">选择 **"不创建程序"，** 然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-353">Select **Do not create a program**, and then select **Next**.</span></span>

4.  <span data-ttu-id="2e302-354">查看"**确认设置"页**，然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-354">Review the **Confirm the settings** page, and then select **Next**.</span></span>

5.  <span data-ttu-id="2e302-355">选择"**关闭"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-355">Select **Close**.</span></span>



## <a name="distribute-configuration-manager-packages"></a><span data-ttu-id="2e302-356">分发配置管理器包</span><span class="sxs-lookup"><span data-stu-id="2e302-356">Distribute Configuration Manager packages</span></span>

<span data-ttu-id="2e302-357">所有包必须分发到在配置管理器层次结构中分配了分发点角色的服务器。</span><span class="sxs-lookup"><span data-stu-id="2e302-357">All the packages must be distributed to the servers that have been assigned the distribution point role in the Configuration Manager hierarchy.</span></span> <span data-ttu-id="2e302-358">按照以下说明启动包分发。</span><span class="sxs-lookup"><span data-stu-id="2e302-358">Follow the instructions below to initiate package distribution.</span></span>

1.  <span data-ttu-id="2e302-359">分发软件包。</span><span class="sxs-lookup"><span data-stu-id="2e302-359">Distribute software packages.</span></span>

    1.  <span data-ttu-id="2e302-360">在配置管理器控制台中，转到 **"软件库** \> **应用程序管理** \> **包"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-360">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**.</span></span> <span data-ttu-id="2e302-361">选择要分发的所有软件包，然后选择"分发 **内容"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-361">Select all the software packages you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="2e302-362">查看程序包列表，然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-362">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="2e302-363">根据配置管理器层次结构， (组或分发点组添加所有分发点) 服务器，然后选择"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-363">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="2e302-364">选择 **"下一** 步"，然后选择"关闭 **"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-364">Select **Next**, and then select **Close**.</span></span>

2.  <span data-ttu-id="2e302-365">分发驱动程序包。</span><span class="sxs-lookup"><span data-stu-id="2e302-365">Distribute driver packages.</span></span>

    1.  <span data-ttu-id="2e302-366">在 Configuration Manager 控制台中，转到 **"软件库** \> **操作系统驱动程序** \> **包"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-366">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Driver Packages**.</span></span> <span data-ttu-id="2e302-367">选择要分发的所有驱动程序包，然后选择"分发 **内容"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-367">Select all the driver packages you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="2e302-368">查看程序包列表，然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-368">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="2e302-369">根据配置管理器层次结构， (组或分发点组添加所有分发点) 服务器，然后选择"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-369">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="2e302-370">选择 **"下一** 步"，然后选择"关闭 **"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-370">Select **Next**, and then select **Close**.</span></span>

3.  <span data-ttu-id="2e302-371">分发操作系统包。</span><span class="sxs-lookup"><span data-stu-id="2e302-371">Distribute operating system packages.</span></span>

    1.  <span data-ttu-id="2e302-372">在 Configuration Manager 控制台中，转到 **"软件库** \> **操作系统** \> **映像"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-372">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Operating System Images**.</span></span> <span data-ttu-id="2e302-373">选择要分发的所有操作系统映像，然后选择"分发 **内容"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-373">Select all the operating system images you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="2e302-374">查看程序包列表，然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-374">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="2e302-375">根据配置管理器层次结构， (组或分发点组添加所有分发点) 服务器，然后选择"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-375">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="2e302-376">选择 **"下一** 步"，然后选择"关闭 **"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-376">Select **Next**, and then select **Close**.</span></span>

> [!NOTE]
> <span data-ttu-id="2e302-377">包分发可能需要一些时间，具体取决于包大小、配置管理器层次结构、分发点服务器数以及网络中可用的带宽。</span><span class="sxs-lookup"><span data-stu-id="2e302-377">Package distribution might take some time, depending on the package size, Configuration Manager hierarchy, number of distribution point servers, and the bandwidth available in your network.</span></span>
> 
> <span data-ttu-id="2e302-378">必须先分发所有包，然后才能开始部署Microsoft Teams 会议室单元。</span><span class="sxs-lookup"><span data-stu-id="2e302-378">All the packages must be distributed before you can start deploying a Microsoft Teams Rooms unit.</span></span>
> 
> <span data-ttu-id="2e302-379">可以通过访问"监视分发状态内容状态"，在配置管理器控制台中 \> **查看包** \> **分发的状态**。</span><span class="sxs-lookup"><span data-stu-id="2e302-379">You can review the status of your package distribution in the Configuration Manager console by going to **Monitoring** \> **Distribution Status** \> **Content Status**.</span></span>

## <a name="configuration-manager-task-sequences"></a><span data-ttu-id="2e302-380">Configuration Manager 任务序列</span><span class="sxs-lookup"><span data-stu-id="2e302-380">Configuration Manager task sequences</span></span>

<span data-ttu-id="2e302-381">将任务序列与 Configuration Manager 一起用于自动执行将操作系统映像部署到目标计算机的步骤。</span><span class="sxs-lookup"><span data-stu-id="2e302-381">You use task sequences with Configuration Manager to automate the steps for deploying an operating system image to a destination computer.</span></span> <span data-ttu-id="2e302-382">若要以自动化方式部署 Microsoft Teams 会议室 单元，请创建一个任务序列，该序列引用用于启动目标 Microsoft Teams 会议室 计算机的启动映像、要安装的 Windows 10 企业版 操作系统映像，以及任何其他内容，例如其他应用程序或软件更新。</span><span class="sxs-lookup"><span data-stu-id="2e302-382">To deploy a Microsoft Teams Rooms unit in an automated fashion, you create a task sequence that references the boot image used to start the destination Microsoft Teams Rooms computer, the Windows 10 Enterprise operating system image that you want to install, and any other additional content, such as other applications or software updates.</span></span>

### <a name="import-the-sample-task-sequence"></a><span data-ttu-id="2e302-383">导入示例任务序列</span><span class="sxs-lookup"><span data-stu-id="2e302-383">Import the sample task sequence</span></span>

<span data-ttu-id="2e302-384">可以下载并轻松导入示例任务序列，并对其进行自定义以满足需求。</span><span class="sxs-lookup"><span data-stu-id="2e302-384">You can download and easily import a sample task sequence and customize it to meet your needs.</span></span>

1.  <span data-ttu-id="2e302-385">[**下载**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) 示例任务序列，将下载的 zip 文件复制到共享位置。</span><span class="sxs-lookup"><span data-stu-id="2e302-385">[**Download**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) the sample task sequence, and copy the downloaded zip file to a shared location.</span></span>
2.  <span data-ttu-id="2e302-386">在 Configuration Manager 控制台中，转到 **"软件库** \> **操作系统任务** \> **序列"，** 然后选择"**导入任务序列"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-386">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Task Sequences**, and then select **Import Task Sequence**.</span></span>

3.  <span data-ttu-id="2e302-387">选择 **"浏览**"，转到步骤 1 中使用的共享文件夹位置，选择"Microsoft Teams 会议室 **部署" (") .zip"** 文件，然后选择"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-387">Select **Browse**, go to the shared folder location you used in step 1, select the **Microsoft Teams Rooms Deployment (EN-US).zip** file, and then select **Next**.</span></span>

4.  <span data-ttu-id="2e302-388">将 **"操作**"**设置为"新建**"，然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-388">Set **Action** to **Create New**, and then select **Next**.</span></span>

5.  <span data-ttu-id="2e302-389">确认设置，然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-389">Confirm the settings, and then select **Next**.</span></span>

6.  <span data-ttu-id="2e302-390">选择"**关闭"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-390">Select **Close**.</span></span>

### <a name="validate-that-the-reference-packages-are-correctly-linked-to-each-task-sequence-step"></a><span data-ttu-id="2e302-391">验证引用包是否正确链接到每个任务序列步骤。</span><span class="sxs-lookup"><span data-stu-id="2e302-391">Validate that the reference packages are correctly linked to each task sequence step.</span></span>

1. <span data-ttu-id="2e302-392">选择导入的任务序列，然后选择"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-392">Select the imported task sequence, and then select **Edit**.</span></span>

    <span data-ttu-id="2e302-393">任务序列编辑器将打开并显示部署和配置任务单元所需的每个Microsoft Teams 会议室步骤。</span><span class="sxs-lookup"><span data-stu-id="2e302-393">The Task Sequence Editor opens and displays each sequential step that you need to deploy and configure a Microsoft Teams Rooms unit.</span></span>

2. <span data-ttu-id="2e302-394">完成每个步骤并完成建议的更新：</span><span class="sxs-lookup"><span data-stu-id="2e302-394">Walk through each step and complete the recommended updates:</span></span>

   1. <span data-ttu-id="2e302-395">**在 PE Windows重启**：此步骤重启，然后将计算机启动到 Windows PXE。</span><span class="sxs-lookup"><span data-stu-id="2e302-395">**Restart in Windows PE**: This step restarts and then boots the computer into Windows PXE.</span></span> <span data-ttu-id="2e302-396">此步骤不需要任何更改。</span><span class="sxs-lookup"><span data-stu-id="2e302-396">No changes are required for this step.</span></span>

   2. <span data-ttu-id="2e302-397">**分区磁盘 0 – UEFI：** 此步骤将擦除磁盘配置，并基于配置的设置创建分区。</span><span class="sxs-lookup"><span data-stu-id="2e302-397">**Partition Disk 0 – UEFI**: This step wipes the disk configuration and creates partitions based on the configured settings.</span></span> <span data-ttu-id="2e302-398">建议不要对此步骤做出任何更改。</span><span class="sxs-lookup"><span data-stu-id="2e302-398">We recommend that you not make any changes to this step.</span></span>

   3. <span data-ttu-id="2e302-399">**设置 SRS 计算机名称**：此步骤包括一个 HTML 应用程序，用于提供一个 UI，用于设置部署期间Microsoft Teams 会议室单元的计算机名称。</span><span class="sxs-lookup"><span data-stu-id="2e302-399">**Set SRS Computer Name**: This step includes an HTML application to provide a UI to set a computer name for the Microsoft Teams Rooms unit during the deployment.</span></span>
      -  <span data-ttu-id="2e302-400">这是一个可选步骤，但只有当你想要通过备用进程管理计算机命名时，才能禁用此步骤。</span><span class="sxs-lookup"><span data-stu-id="2e302-400">This is an optional step, but it can only be disabled if you want to manage computer naming through an alternate process.</span></span>
      -  <span data-ttu-id="2e302-401">验证是否 **选择了"SRS v2 - Set-SRSComputerName"** 包。</span><span class="sxs-lookup"><span data-stu-id="2e302-401">Verify that the **SRS v2 - Set-SRSComputerName** package is selected.</span></span> <span data-ttu-id="2e302-402">如果不是，请浏览到程序包并选择它。</span><span class="sxs-lookup"><span data-stu-id="2e302-402">If it isn't, browse to the package and select it.</span></span>

   4. <span data-ttu-id="2e302-403">**应用操作系统**：此步骤指定要部署的操作系统映像和要使用无人参与的 Sysprep 应答文件。</span><span class="sxs-lookup"><span data-stu-id="2e302-403">**Apply Operating System**: This step specifies the operating system image to be deployed and the unattended Sysprep answer file to use.</span></span>
      -  <span data-ttu-id="2e302-404">验证是否选择了Windows 10 企业版映像文件。</span><span class="sxs-lookup"><span data-stu-id="2e302-404">Verify that the correct Windows 10 Enterprise operating system image file is selected.</span></span>
      -  <span data-ttu-id="2e302-405">验证是否已启用对自定义安装使用无人参与或 **Sysprep** 应答文件，并选择了 **"SRS v2 - Sysprep 包** "。</span><span class="sxs-lookup"><span data-stu-id="2e302-405">Verify that **Use an unattended or Sysprep answer file for a custom installation** is enabled, and the **SRS v2 - Sysprep Package** is selected.</span></span> <span data-ttu-id="2e302-406">另请确保 **将"文件名**"设置为 **unattend.xml。**</span><span class="sxs-lookup"><span data-stu-id="2e302-406">Also ensure that **File Name** is set to **unattend.xml**.</span></span>

   5. <span data-ttu-id="2e302-407">**应用Windows 设置：** 此步骤收集有关安装Windows的信息。</span><span class="sxs-lookup"><span data-stu-id="2e302-407">**Apply Windows Settings**: This step gathers information about the Windows installation.</span></span>
      -  <span data-ttu-id="2e302-408">提供许可和注册信息，包括产品密钥、本地管理员帐户密码和时区 (，具体取决于) 。</span><span class="sxs-lookup"><span data-stu-id="2e302-408">Provide licensing and registration information including the product key, local administrator account password, and time zone (depending on your needs).</span></span>

   6. <span data-ttu-id="2e302-409">**应用网络设置：** 此步骤允许指定工作组或 Active Directory 域名和组织单位。</span><span class="sxs-lookup"><span data-stu-id="2e302-409">**Apply Network Settings**: This step allows you to specify a workgroup or Active Directory domain name and organizational unit.</span></span>
      > [!NOTE]
      > <span data-ttu-id="2e302-410">请参阅[Skype Room System](domain-joining-considerations.md)域加入注意事项，了解在将 Microsoft Teams 会议室 作为 Actve Directory 域的成员部署时需要执行的建议操作。</span><span class="sxs-lookup"><span data-stu-id="2e302-410">See [Skype Room System domain joining considerations](domain-joining-considerations.md) for recommended actions you need to take in deploying Microsoft Teams Rooms units as members of an Actve Directory domain.</span></span>
   7. <span data-ttu-id="2e302-411">**应用驱动程序：** 此步骤及其子步骤用于根据你拥有的设备Surface Pro部署适用的设备驱动程序和固件。</span><span class="sxs-lookup"><span data-stu-id="2e302-411">**Apply Drivers:** This step and its sub-steps are used to deploy applicable device drivers and firmware based on the Surface Pro model you have.</span></span> <span data-ttu-id="2e302-412">更新每个步骤，指定与此部署关联的相关驱动程序包。</span><span class="sxs-lookup"><span data-stu-id="2e302-412">Update each step to specify the relevant driver package associated with this deployment.</span></span>
      -   <span data-ttu-id="2e302-413">每个驱动程序包配置为利用 Windows Management Instrumentation (WMI) 筛选器，根据制造和Surface Pro部署相关的驱动程序和固件。</span><span class="sxs-lookup"><span data-stu-id="2e302-413">Each driver package is configured to leverage Windows Management Instrumentation (WMI) filters to deploy relevant drivers and firmware based on the Surface Pro make and model.</span></span>
      -   <span data-ttu-id="2e302-414">强烈建议不要更改这些驱动程序的配置，否则部署可能会失败。</span><span class="sxs-lookup"><span data-stu-id="2e302-414">We highly recommend that you not alter the configuration of these drivers, otherwise deployment might fail.</span></span>

   8. <span data-ttu-id="2e302-415">**设置Windows和配置管理器**：此步骤部署并配置 Configuration Manager 客户端。</span><span class="sxs-lookup"><span data-stu-id="2e302-415">**Set up Windows and Configuration Manager**: This step deploys and configures the Configuration Manager client.</span></span> <span data-ttu-id="2e302-416">更新此步骤以指定内置的 Configuration Manager 客户端包。</span><span class="sxs-lookup"><span data-stu-id="2e302-416">Update this step to specify the built-in Configuration Manager Client Package.</span></span>

   9. <span data-ttu-id="2e302-417">**安装根证书**：此步骤为未加入域的设备分发根证书，因此是可选的，默认情况下处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="2e302-417">**Install Root Certificate**: This step distributes the root certificate for non–domain-joined devices, and therefore is optional and disabled by default.</span></span>
      -   <span data-ttu-id="2e302-418">如果需要将根证书部署到每个单元，Microsoft Teams 会议室此步骤。</span><span class="sxs-lookup"><span data-stu-id="2e302-418">Enable this step if you need to deploy a root certificate to the Microsoft Teams Rooms units.</span></span>
      -   <span data-ttu-id="2e302-419">如果需要执行此步骤，请验证是否选择了 **"SRS v2 –** 根证书包"和"禁用 **64** 位文件系统重定向"。</span><span class="sxs-lookup"><span data-stu-id="2e302-419">If you do need to perform this step, verify that the **SRS v2 – Root Certificate Package** and **Disable 64-bit file system redirection** are selected.</span></span>

   10. <span data-ttu-id="2e302-420">**安装和配置监视代理**：此步骤安装 64 位版本的 Microsoft Azure Monitor 代理，并配置代理以连接到 Log Analytics 工作区。</span><span class="sxs-lookup"><span data-stu-id="2e302-420">**Install and Configure Monitoring Agent**: This step installs the 64-bit version of the Microsoft Azure Monitor agent and configures the agent to connect to your Log Analytics workspace.</span></span>
       -   <span data-ttu-id="2e302-421">默认情况下，此步骤处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="2e302-421">This step is disabled by default.</span></span> <span data-ttu-id="2e302-422">只有在要使用监视代理监视每个单元的运行状况时，才Microsoft Teams 会议室此步骤。</span><span class="sxs-lookup"><span data-stu-id="2e302-422">Enable this step only if you're going to use the Monitoring Agent to monitor the health of your Microsoft Teams Rooms units.</span></span>
       -   <span data-ttu-id="2e302-423">编辑此步骤并更新命令行参数，以指定 **工作区 ID** 和 **工作区密钥**。</span><span class="sxs-lookup"><span data-stu-id="2e302-423">Edit this step and update the command-line parameters to specify your **Workspace ID** and **Workspace Key**.</span></span>
       -   <span data-ttu-id="2e302-424">有关 [获取](azure-monitor-deploy.md#configure-test-devices-for-azure-monitoring) Operations Management Suite 工作区 ID 和主密钥的信息，请参阅为 Azure 监视配置测试设备。</span><span class="sxs-lookup"><span data-stu-id="2e302-424">See [Configure test devices for Azure Monitoring](azure-monitor-deploy.md#configure-test-devices-for-azure-monitoring) for more information about obtaining the Operations Management Suite Workspace ID and the primary key.</span></span>
       -   <span data-ttu-id="2e302-425">验证是否 **选择了"SRS v2 – Microsoft Monitoring Agent包**"和"禁用 **64 位文件系统重定向**"。</span><span class="sxs-lookup"><span data-stu-id="2e302-425">Verify that the **SRS v2 – Microsoft Monitoring Agent Package** and **Disable 64-bit file system redirection** are selected.</span></span>
       -   <span data-ttu-id="2e302-426">有关监视 Microsoft Teams 会议室 部署的运行状况详细信息，请参阅使用[Azure Monitor](azure-monitor-plan.md)规划 Microsoft Teams 会议室 管理、使用 Azure [Monitor](azure-monitor-deploy.md)部署 Microsoft Teams 会议室 管理以及使用[Azure Monitor](azure-monitor-manage.md)管理 Microsoft Teams 会议室 设备。</span><span class="sxs-lookup"><span data-stu-id="2e302-426">For more information about monitoring the health of your Microsoft Teams Rooms deployment, see [Plan Microsoft Teams Rooms management with Azure Monitor](azure-monitor-plan.md), [Deploy Microsoft Teams Rooms management with Azure Monitor](azure-monitor-deploy.md) and [Manage Microsoft Teams Rooms devices with Azure Monitor](azure-monitor-manage.md).</span></span>

   11. <span data-ttu-id="2e302-427">**复制 SRS v2 配置文件**：此步骤将所需的安装和配置文件从 Microsoft Teams 会议室 部署工具包复制到本地硬盘驱动器。</span><span class="sxs-lookup"><span data-stu-id="2e302-427">**Copy SRS v2 Configuration Files**: This step copies the required setup and configuration files from the Microsoft Teams Rooms deployment kit to the local hard drive.</span></span> <span data-ttu-id="2e302-428">此步骤不需要自定义。</span><span class="sxs-lookup"><span data-stu-id="2e302-428">No customization is required for this step.</span></span>
       -   <span data-ttu-id="2e302-429">验证是否 **选择了"SRS v2 – SRS** 应用程序包"和"禁用 **64 位文件系统重定向** "。</span><span class="sxs-lookup"><span data-stu-id="2e302-429">Verify that the **SRS v2 – SRS Application Package** and **Disable 64-bit file system redirection** are selected.</span></span>

   12. <span data-ttu-id="2e302-430">**Install-SRSv2-OS-Updates：** 此步骤部署任何必需的操作系统更新，Microsoft Teams 会议室部署。</span><span class="sxs-lookup"><span data-stu-id="2e302-430">**Install-SRSv2-OS-Updates**: This step deploys any mandatory operating system updates required with the Microsoft Teams Rooms deployment.</span></span> <span data-ttu-id="2e302-431">执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="2e302-431">Do the following:</span></span>
       -   <span data-ttu-id="2e302-432">选中["配置Microsoft Teams 会议室](console.md)主机以查看需要哪些更新。</span><span class="sxs-lookup"><span data-stu-id="2e302-432">Check [Configure a Microsoft Teams Rooms console](console.md) to see which updates are required.</span></span>
       -   <span data-ttu-id="2e302-433">验证 **SRS v2 – OS 更新包** 是否包含所有必需的更新。</span><span class="sxs-lookup"><span data-stu-id="2e302-433">Verify that your **SRS v2 – OS Updates Package** includes all the required updates.</span></span>
       -   <span data-ttu-id="2e302-434">验证是否选择了 **"SRS v2 – OS 更新包** "。</span><span class="sxs-lookup"><span data-stu-id="2e302-434">Verify that the **SRS v2 – OS Updates Package** is selected.</span></span>
       -   <span data-ttu-id="2e302-435">验证 PowerShell 执行策略是否设置为"绕过 **"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-435">Verify that the PowerShell execution policy is set to **Bypass**.</span></span>

   13. <span data-ttu-id="2e302-436">**重新启动计算机**：此步骤在安装必需的操作系统更新后重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="2e302-436">**Restart Computer**: This step reboots the computer after the mandatory operating system updates are installed.</span></span> <span data-ttu-id="2e302-437">此步骤不需要自定义。</span><span class="sxs-lookup"><span data-stu-id="2e302-437">No customization is required for this step.</span></span>

   14. <span data-ttu-id="2e302-438">**配置Windows组件**：此步骤配置所需的Windows功能。</span><span class="sxs-lookup"><span data-stu-id="2e302-438">**Configure Windows Components**: This step configures the required Windows features.</span></span> <span data-ttu-id="2e302-439">此步骤不需要自定义。</span><span class="sxs-lookup"><span data-stu-id="2e302-439">No customization is required for this step.</span></span>

   15. <span data-ttu-id="2e302-440">**重新启动计算机**：此步骤在配置Windows后重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="2e302-440">**Restart Computer**: This step reboots the computer after the Windows features are configured.</span></span> <span data-ttu-id="2e302-441">此步骤不需要自定义。</span><span class="sxs-lookup"><span data-stu-id="2e302-441">No customization is required for this step.</span></span>

   16. <span data-ttu-id="2e302-442">**添加Skype** 用户：此步骤创建用于自动登录到 Skype 的本地 Windows，并启动 Microsoft Teams 会议室 应用程序。</span><span class="sxs-lookup"><span data-stu-id="2e302-442">**Add Local Skype User**: This step creates the local Skype account used to automatically sign in to Windows and start the Microsoft Teams Rooms application.</span></span> <span data-ttu-id="2e302-443">此步骤没有任何关联的软件包，并且不需要任何自定义。</span><span class="sxs-lookup"><span data-stu-id="2e302-443">This step doesn't have any software package associated with it, and no customization is required for it.</span></span>

   17. <span data-ttu-id="2e302-444">**设置和配置 SRS 应用程序**：此步骤Microsoft Teams 会议室操作系统下次启动时配置应用程序安装。</span><span class="sxs-lookup"><span data-stu-id="2e302-444">**Set up and configure SRS application**: This step configures the Microsoft Teams Rooms application installation for the next boot of the operating system.</span></span>
       -   <span data-ttu-id="2e302-445">验证是否 **选择了"SRS v2 – 配置 SRS** 安装包"和"禁用 **64 位文件系统** 重定向"。</span><span class="sxs-lookup"><span data-stu-id="2e302-445">Verify that the **SRS v2 – Configure SRS Setup Package** and **Disable 64-bit file system redirection** are selected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2e302-446">任务序列步骤必须按提供的顺序进行，这一点非常重要。</span><span class="sxs-lookup"><span data-stu-id="2e302-446">It is very important that the task sequence steps must be in the provided order.</span></span> <span data-ttu-id="2e302-447">修改步骤顺序或配置其他步骤可能会中断部署。</span><span class="sxs-lookup"><span data-stu-id="2e302-447">Modifying the order of steps, or configuring additional steps might break the deployment.</span></span>
>
> <span data-ttu-id="2e302-448">**设置和配置 SRS 应用程序** 步骤必须是任务序列中的最后一步，否则部署可能会失败。</span><span class="sxs-lookup"><span data-stu-id="2e302-448">**Set up and configure SRS application** step must be the last step in the task sequence, otherwise the deployment might fail.</span></span>

### <a name="create-deployment-for-the-task-sequence"></a><span data-ttu-id="2e302-449">为任务序列创建部署</span><span class="sxs-lookup"><span data-stu-id="2e302-449">Create deployment for the task sequence</span></span>

1. <span data-ttu-id="2e302-450">选择任务序列，然后选择"部署 **"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-450">Select the task sequence, and then select **Deploy**.</span></span>

2. <span data-ttu-id="2e302-451">选择 **"浏览** "以选择要部署的目标集合。</span><span class="sxs-lookup"><span data-stu-id="2e302-451">Select **Browse** to select target collection for deployment.</span></span>

3. <span data-ttu-id="2e302-452">选择 **"所有未知计算机**"，然后选择"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-452">Select **All Unknown Computers** and then select **OK**.</span></span>

4. <span data-ttu-id="2e302-453">选择"下 **一步"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-453">Select **Next**.</span></span>

5. <span data-ttu-id="2e302-454">在 **"用途** " **下拉列表** 中选择"可用"。</span><span class="sxs-lookup"><span data-stu-id="2e302-454">Select **Available** on the **Purpose** drop down list.</span></span>

6. <span data-ttu-id="2e302-455">在 **"使以下列表可用**"**中选择"仅** 媒体和 PXE"，然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-455">Select **Only Media and PXE** in the **Make available to the following** list, and then select **Next**.</span></span>
   > [!WARNING]
   > <span data-ttu-id="2e302-456">将" **用途"设置为** "可用 **"非常重要**。</span><span class="sxs-lookup"><span data-stu-id="2e302-456">It is very important that **Purpose** is set to **Available**.</span></span> <span data-ttu-id="2e302-457">确保"用途 **"\*\*\*\*未设置为**"必需 **"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-457">Make sure that the **Purpose** is **NOT** set to **Required**.</span></span> <span data-ttu-id="2e302-458">另请确保在"使以下项可用"中选择"**仅媒体和** **PXE"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-458">Also make sure that you select **Only Media and PXE** in the **Make available to the following**.</span></span>
   >
   > <span data-ttu-id="2e302-459">将这些值设置为其他值可能会导致所有计算机在Microsoft Teams 会议室部署映像。</span><span class="sxs-lookup"><span data-stu-id="2e302-459">Setting these values to something else might cause all computers to get the Microsoft Teams Rooms deployment image when booted.</span></span>
7. <span data-ttu-id="2e302-460">不要指定任何计划，然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-460">Do not specify any schedule and select **Next**.</span></span>

8. <span data-ttu-id="2e302-461">请勿更改"用户体验"部分 **内的内容**，然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-461">Do not change anything within the **User Experience** section and select **Next**.</span></span>

9. <span data-ttu-id="2e302-462">请勿更改"警报"部分 **内** 的内容，然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-462">Do not change anything within the **Alerts** section and select **Next**.</span></span>

10. <span data-ttu-id="2e302-463">请勿更改"分发点"部分 **内的内容，** 然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-463">Do not change anything within the **Distribution Points** section and select **Next**.</span></span>

11. <span data-ttu-id="2e302-464">确认设置，然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-464">Confirm the settings and then select **Next**.</span></span>

12. <span data-ttu-id="2e302-465">选择"**关闭"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-465">Select **Close**.</span></span>

<a name="validate-and-troubleshoot-the-solution"></a><span data-ttu-id="2e302-466">验证和排查解决方案问题</span><span class="sxs-lookup"><span data-stu-id="2e302-466">Validate and troubleshoot the solution</span></span>
--------------------------------------

<span data-ttu-id="2e302-467">完成任务序列Microsoft Endpoint Configuration Manager，需要执行测试运行来验证任务序列是否可部署和配置Microsoft Teams 会议室单位。</span><span class="sxs-lookup"><span data-stu-id="2e302-467">After you've completed the Microsoft Endpoint Configuration Manager task sequences, you'll need to perform a test run to validate that the task sequence can deploy and configure Microsoft Teams Rooms units.</span></span>

1.  <span data-ttu-id="2e302-468">连接支持以太网适配器之一或 Surface 扩展坞将测试设备连接到有线网络。</span><span class="sxs-lookup"><span data-stu-id="2e302-468">Connect the test device to the wired network by using one of the supported Ethernet adapters or using the Surface dock.</span></span> <span data-ttu-id="2e302-469">如果尚未为环境配置 PXE 启动功能，可以使用之前创建的 U 盘上的启动映像从 USB 启动[](/configmgr/osd/deploy-use/create-bootable-media)并连接到 Configuration Manager。</span><span class="sxs-lookup"><span data-stu-id="2e302-469">If PXE boot functionality hasn't been configured for your environment, you can use the boot image on the USB flash drive [that you created earlier](/configmgr/osd/deploy-use/create-bootable-media) to boot from USB and connect to Configuration Manager.</span></span>

2.  <span data-ttu-id="2e302-470">访问固件并启动 PXE 启动：</span><span class="sxs-lookup"><span data-stu-id="2e302-470">Access the firmware and initiate PXE boot:</span></span>

    1.  <span data-ttu-id="2e302-471">确保 Surface 设备已关闭电源。</span><span class="sxs-lookup"><span data-stu-id="2e302-471">Ensure the Surface device is powered off.</span></span>

    2.  <span data-ttu-id="2e302-472">长按" **调高音量"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="2e302-472">Press and hold the **Volume Up** button.</span></span>

    3.  <span data-ttu-id="2e302-473">按下并松开 **"电源"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="2e302-473">Press and release the **Power** button.</span></span>

    4.  <span data-ttu-id="2e302-474">设备开始启动后，释放 **"调高音量"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="2e302-474">After the device begins to boot, release the **Volume Up** button.</span></span>

    5.  <span data-ttu-id="2e302-475">选择 **"启动配置"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-475">Select **Boot configuration**.</span></span>

    6.  <span data-ttu-id="2e302-476">执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="2e302-476">Do one of the following:</span></span>

        -   <span data-ttu-id="2e302-477">选择 **"PXE 启动**"，并将其拖动到列表顶部。</span><span class="sxs-lookup"><span data-stu-id="2e302-477">Select **PXE boot**, and drag it to the top of the list.</span></span> <span data-ttu-id="2e302-478">或者，可以在网络适配器上向左轻扫以立即启动到设备。</span><span class="sxs-lookup"><span data-stu-id="2e302-478">Alternatively, you can swipe left on the network adapter to boot to the device immediately.</span></span> <span data-ttu-id="2e302-479">这不会影响启动顺序。</span><span class="sxs-lookup"><span data-stu-id="2e302-479">This won't affect the boot order.</span></span>
        -   <span data-ttu-id="2e302-480">选择保存启动媒体的 U 盘。</span><span class="sxs-lookup"><span data-stu-id="2e302-480">Select the USB flash drive that holds the boot media.</span></span>

3.  <span data-ttu-id="2e302-481">选择 **"退出**"，然后选择"**立即重启"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-481">Select **Exit**, and then select **Restart Now**.</span></span>

4.  <span data-ttu-id="2e302-482">系统提示时，为 **网络启动** 服务选择 Enter。</span><span class="sxs-lookup"><span data-stu-id="2e302-482">When prompted, select **Enter** for network boot service.</span></span>

5.  <span data-ttu-id="2e302-483">WindowsPE 将加载到内存中，任务序列向导将启动。</span><span class="sxs-lookup"><span data-stu-id="2e302-483">Windows PE will load into memory, and the Task Sequence Wizard will start.</span></span> <span data-ttu-id="2e302-484">选择 **"下一** 步"继续。</span><span class="sxs-lookup"><span data-stu-id="2e302-484">Select **Next** to continue.</span></span>

6.  <span data-ttu-id="2e302-485">选择之前导入的任务序列，然后选择"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="2e302-485">Select the task sequence that you imported earlier, and then select **Next**.</span></span>

7.  <span data-ttu-id="2e302-486">应用磁盘配置后，系统会提示你指定设备的计算机名称。</span><span class="sxs-lookup"><span data-stu-id="2e302-486">After the disk configuration is applied, you'll be prompted to specify a computer name for the device.</span></span> <span data-ttu-id="2e302-487">用户界面将基于设备序列号显示Surface Pro名称。</span><span class="sxs-lookup"><span data-stu-id="2e302-487">The user interface will display a recommended computer name based on the serial number of the Surface Pro device.</span></span> <span data-ttu-id="2e302-488">可以接受建议的名称或指定新名称。</span><span class="sxs-lookup"><span data-stu-id="2e302-488">You can either accept the proposed name or specify a new one.</span></span> <span data-ttu-id="2e302-489">按照计算机名称分配屏幕上的说明操作。</span><span class="sxs-lookup"><span data-stu-id="2e302-489">Follow the instructions on the computer name assignment screen.</span></span> <span data-ttu-id="2e302-490">选择" **接受"** 时，部署将开始。</span><span class="sxs-lookup"><span data-stu-id="2e302-490">When you select **Accept**, the deployment begins.</span></span>

8.  <span data-ttu-id="2e302-491">部署过程的其余部分是自动的，不需要任何其他用户输入。</span><span class="sxs-lookup"><span data-stu-id="2e302-491">The rest of the deployment process is automatic and doesn't ask for any more user input.</span></span>

9.  <span data-ttu-id="2e302-492">部署任务序列完成设备配置后，会看到以下配置屏幕，要求配置Microsoft Teams 会议室设置。</span><span class="sxs-lookup"><span data-stu-id="2e302-492">After the deployment task sequence finishes configuring the device, you'll see the following configuration screen that asks you to configure the Microsoft Teams Rooms application settings.</span></span>

    ![应用程序的初始Microsoft Teams 会议室屏幕](../media/room-systems-scale-image2.png)

10.  <span data-ttu-id="2e302-494">将Surface Pro插入 Microsoft Teams 会议室 控制台，并配置应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="2e302-494">Plug the Surface Pro into the Microsoft Teams Rooms console, and configure the application settings.</span></span>

11.  <span data-ttu-id="2e302-495">验证帮助中列出的Microsoft Teams 会议室[在](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)已部署设备上是否正常工作。</span><span class="sxs-lookup"><span data-stu-id="2e302-495">Validate that the capabilities listed in [Microsoft Teams Rooms help](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) are working on the deployed device.</span></span>


<span data-ttu-id="2e302-496">若要排查安装失败的问题，请检查 **SMSTS.log** 文件，该文件记录在 Configuration Manager 任务序列中执行的所有步骤。</span><span class="sxs-lookup"><span data-stu-id="2e302-496">To troubleshoot a failed installation, check the **SMSTS.log** file, which logs all the steps executed in a Configuration Manager task sequence.</span></span>

<span data-ttu-id="2e302-497">SMSTS.日志文件存储在多个路径之一上，具体取决于生成过程的阶段。</span><span class="sxs-lookup"><span data-stu-id="2e302-497">The SMSTS.log file is stored on one of a number of paths, depending on the stage of the build process.</span></span> <span data-ttu-id="2e302-498">查看下表，确定 SMSTS.日志文件。</span><span class="sxs-lookup"><span data-stu-id="2e302-498">Check the following table to identify the path to the SMSTS.log file.</span></span>


| <span data-ttu-id="2e302-499">**部署阶段**</span><span class="sxs-lookup"><span data-stu-id="2e302-499">**Deployment phase**</span></span>                                                            | <span data-ttu-id="2e302-500">**任务序列日志路径**</span><span class="sxs-lookup"><span data-stu-id="2e302-500">**Task sequence log path**</span></span>                         |
|---------------------------------------------------------------------------------|----------------------------------------------------|
| <span data-ttu-id="2e302-501">WinPE，HDD 格式之前</span><span class="sxs-lookup"><span data-stu-id="2e302-501">WinPE, before HDD format</span></span>                                                        | <span data-ttu-id="2e302-502">\\X：Windows Temp \\ \\ smstslog \\ smsts.log</span><span class="sxs-lookup"><span data-stu-id="2e302-502">X:\\Windows\\Temp\\smstslog\\smsts.log</span></span>             |
| <span data-ttu-id="2e302-503">WinPE，HDD 格式之后</span><span class="sxs-lookup"><span data-stu-id="2e302-503">WinPE, after HDD format</span></span>                                                         | <span data-ttu-id="2e302-504">\\C：_SMSTaskSequence Logs \\ \\ Smstslog \\ smsts.log</span><span class="sxs-lookup"><span data-stu-id="2e302-504">C:\\_SMSTaskSequence\\Logs\\Smstslog\\smsts.log</span></span>    |
| <span data-ttu-id="2e302-505">在安装 Configuration Manager 代理之前部署的操作系统</span><span class="sxs-lookup"><span data-stu-id="2e302-505">Operating system deployed, before the Configuration Manager agent was installed</span></span> | <span data-ttu-id="2e302-506">\\c：_SMSTaskSequence Logs \\ \\ Smstslog \\ smsts.log</span><span class="sxs-lookup"><span data-stu-id="2e302-506">c:\\_SMSTaskSequence\\Logs\\Smstslog\\smsts.log</span></span>    |
| <span data-ttu-id="2e302-507">已部署操作系统和 Configuration Manager 代理</span><span class="sxs-lookup"><span data-stu-id="2e302-507">Operating system and the Configuration Manager agent deployed</span></span>                   | <span data-ttu-id="2e302-508">%windir% \\ System32 \\ ccm \\ logs \\ Smstslog \\ smsts.log</span><span class="sxs-lookup"><span data-stu-id="2e302-508">%windir%\\System32\\ccm\\logs\\Smstslog\\smsts.log</span></span> |
| <span data-ttu-id="2e302-509">任务序列执行完成</span><span class="sxs-lookup"><span data-stu-id="2e302-509">Task sequence execution complete</span></span>                                                | <span data-ttu-id="2e302-510">%windir% \\ System32 \\ ccm \\ 日志 \\ smsts.log</span><span class="sxs-lookup"><span data-stu-id="2e302-510">%windir%\\System32\\ccm\\logs\\smsts.log</span></span>           |

> [!TIP]
> <span data-ttu-id="2e302-511">在任务序列中，你随时可以选择 **F8** 以打开命令控制台，然后访问 SMSTS.日志文件。</span><span class="sxs-lookup"><span data-stu-id="2e302-511">You can select **F8** at any time during the task sequence to open a command console, and then get access to the SMSTS.log file.</span></span>

<span data-ttu-id="2e302-512">若要排查 PXE 启动问题，请检查 Configuration Manager 服务器上特定于 PXE 操作的两个日志文件：</span><span class="sxs-lookup"><span data-stu-id="2e302-512">To troubleshoot PXE boot issues, check the two log files on the Configuration Manager server that are specific to PXE actions:</span></span>

-   <span data-ttu-id="2e302-513">**Pxecontrol.log，** 位于 Configuration Manager 安装日志目录中</span><span class="sxs-lookup"><span data-stu-id="2e302-513">**Pxecontrol.log**, located in the Configuration Manager installation logs directory</span></span>

-   <span data-ttu-id="2e302-514">**Smspxe.log，** 位于配置管理器管理点 (MP) 目录中</span><span class="sxs-lookup"><span data-stu-id="2e302-514">**Smspxe.log**, located in Configuration Manager Management Point (MP) logs directory</span></span>

<span data-ttu-id="2e302-515">有关可用于进一步排查配置管理器安装问题的完整日志文件列表，请参阅Microsoft Endpoint Configuration Manager[日志文件参考](/configmgr/core/plan-design/hierarchy/log-files)。</span><span class="sxs-lookup"><span data-stu-id="2e302-515">For a complete list of the log files that you can use to further troubleshoot your Configuration Manager installation, see the Microsoft Endpoint Configuration Manager [Log file reference](/configmgr/core/plan-design/hierarchy/log-files).</span></span>
