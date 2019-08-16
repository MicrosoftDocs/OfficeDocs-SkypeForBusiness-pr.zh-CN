---
title: 使用 System Center Configuration Manager 部署 Microsoft 团队聊天室
author: lanachin
ms.author: v-lanac
ms.reviewer: Turgayo
manager: serdars
ms.date: 5/10/2018
audience: ITPro
ms.topic: quickstart
ms.service: msteams
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
ms.collection: M365-voice
description: 阅读本主题, 了解如何在大规模部署中部署 Microsoft 团队聊天室。
ms.openlocfilehash: 26bb864f1b3eea49eaf99b598af9b5794df824be
ms.sourcegitcommit: 1401ee484a2bc8e72d96649b0571bb59198f9dab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/15/2019
ms.locfileid: "36428005"
---
# <a name="deploy-microsoft-teams-rooms-by-using-system-center-configuration-manager"></a><span data-ttu-id="36241-103">使用 System Center Configuration Manager 部署 Microsoft 团队聊天室</span><span class="sxs-lookup"><span data-stu-id="36241-103">Deploy Microsoft Teams Rooms by using System Center Configuration Manager</span></span>

<span data-ttu-id="36241-104">本文提供使用 System Center Configuration Manager 创建 Microsoft 团队聊天室部署的所有必要信息。</span><span class="sxs-lookup"><span data-stu-id="36241-104">This article gives you all the necessary information to create your Microsoft Teams Rooms deployments by using System Center Configuration Manager.</span></span>

<span data-ttu-id="36241-105">利用 System Center Configuration Manager 提供的易于使用的方法, 你可以将操作系统和其他应用程序部署到多台目标设备。</span><span class="sxs-lookup"><span data-stu-id="36241-105">With the easy-to-use methods provided by System Center Configuration Manager, you can deploy the operating system and other applications to multiple target devices.</span></span>

<span data-ttu-id="36241-106">使用下面所示的方法指导你完成 Configuration Manager 配置, 并根据组织的需要自定义本指南中提供的示例程序包和脚本。</span><span class="sxs-lookup"><span data-stu-id="36241-106">Use the approach illustrated below to guide you through your Configuration Manager configuration, and customize the sample packages and scripts provided throughout this guidance as needed for your organization.</span></span>

![使用配置管理器的 Microsoft 团队会议室部署流程](../media/room-systems-scale-image1.png)

> [!IMPORTANT]
> <span data-ttu-id="36241-108">此解决方案仅通过基于 Surface Pro 的部署进行了测试。</span><span class="sxs-lookup"><span data-stu-id="36241-108">This solution has only been tested with Surface Pro–based deployments.</span></span> <span data-ttu-id="36241-109">按照制造商指南, 了解不基于 Surface Pro 的配置。</span><span class="sxs-lookup"><span data-stu-id="36241-109">Follow the manufacturer’s guidelines for configurations that aren’t based on Surface Pro.</span></span>

## <a name="validate-prerequisites"></a><span data-ttu-id="36241-110">验证先决条件</span><span class="sxs-lookup"><span data-stu-id="36241-110">Validate prerequisites</span></span>

<span data-ttu-id="36241-111">若要通过 Configuration Manager 部署 Microsoft 团队聊天室, 请确保满足以下先决条件和要求。</span><span class="sxs-lookup"><span data-stu-id="36241-111">To deploy Microsoft Teams Rooms with Configuration Manager, ensure that you meet the following prerequisites and requirements.</span></span>

### <a name="system-center-configuration-manager-requirements"></a><span data-ttu-id="36241-112">System Center Configuration Manager 要求</span><span class="sxs-lookup"><span data-stu-id="36241-112">System Center Configuration Manager requirements</span></span>

-   <span data-ttu-id="36241-113">System Center Configuration Manager 版本必须至少为1706或更高版本。</span><span class="sxs-lookup"><span data-stu-id="36241-113">System Center Configuration Manager version must be at least 1706 or above.</span></span> <span data-ttu-id="36241-114">我们建议使用1710或更高版本。</span><span class="sxs-lookup"><span data-stu-id="36241-114">We recommend using 1710 or later.</span></span> <span data-ttu-id="36241-115">查看[System Center Configuration manager 中的 windows 10 支持](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client), 了解 Configuration Manager 支持的 windows 10 版本。</span><span class="sxs-lookup"><span data-stu-id="36241-115">Check out [Support for Windows 10 in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) to learn about the Windows 10 versions that Configuration Manager supports.</span></span>

-   <span data-ttu-id="36241-116">必须安装支持的 windows 10 版本的 Windows 评估和部署工具包 (ADK)。</span><span class="sxs-lookup"><span data-stu-id="36241-116">A supported version of Windows Assessment and Deployment Kit (ADK) for Windows 10 must be installed.</span></span> <span data-ttu-id="36241-117">查看可用于不同版本的 Configuration Manager 的[Windows 10 ADK](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-adk)版本, 并确保你的部署包含正确的版本。</span><span class="sxs-lookup"><span data-stu-id="36241-117">See the versions of the [Windows 10 ADK](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-adk) that you can use with different versions of Configuration Manager, and ensure that your deployment includes the correct version.</span></span>

-   <span data-ttu-id="36241-118">必须为站点系统服务器分配分发点角色, 并且应为[预启动执行环境 (PXE) 支持](https://docs.microsoft.com/sccm/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network)启用启动映像以启用网络启动的部署。</span><span class="sxs-lookup"><span data-stu-id="36241-118">The site system servers must have been assigned the distribution point role, and the boot images should be enabled for [preboot execution environment (PXE) support](https://docs.microsoft.com/sccm/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network) to enable network-initiated deployments.</span></span> <span data-ttu-id="36241-119">如果未启用 PXE 支持, 你可以将[可启动媒体](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network)用于你的部署。</span><span class="sxs-lookup"><span data-stu-id="36241-119">If PXE support isn’t enabled, you can use [bootable media](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) for your deployments.</span></span>

-   <span data-ttu-id="36241-120">必须将网络访问帐户配置为支持新计算机 (裸机) 部署方案。</span><span class="sxs-lookup"><span data-stu-id="36241-120">A network access account must be configured to support new computer (bare metal) deployment scenarios.</span></span> <span data-ttu-id="36241-121">若要了解有关网络访问帐户配置的详细信息, 请参阅[管理 System Center Configuration Manager 中的 "管理帐户以访问内容](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA)"。</span><span class="sxs-lookup"><span data-stu-id="36241-121">To learn more about the configuration of a network access account, see [Manage accounts to access content in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span></span>

-   <span data-ttu-id="36241-122">如果你可能同时将同一 Microsoft 团队会议室图像部署到多个单元, 我们建议你启用[多路广播支持](https://docs.microsoft.com/sccm/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network)。</span><span class="sxs-lookup"><span data-stu-id="36241-122">We recommend that you enable [multicast support](https://docs.microsoft.com/sccm/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network), if you’re likely to deploy the same Microsoft Teams Rooms image to multiple units at the same time.</span></span>

### <a name="networking-requirements"></a><span data-ttu-id="36241-123">网络要求</span><span class="sxs-lookup"><span data-stu-id="36241-123">Networking requirements</span></span>

-   <span data-ttu-id="36241-124">您的网络应该具有动态主机配置协议 (DHCP) 服务器, 该服务器已配置为将部署 Microsoft 团队聊天室单元的子网自动分配 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="36241-124">Your network should have a Dynamic Host Configuration Protocol (DHCP) server, configured for automatic IP address distribution to the subnets where Microsoft Teams Rooms units will be deployed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="36241-125">DHCP 租用期必须设置为比映像部署持续时间更长的值。</span><span class="sxs-lookup"><span data-stu-id="36241-125">DHCP lease duration must be set to a value longer than the image deployment duration.</span></span> <span data-ttu-id="36241-126">否则, 部署可能失败。</span><span class="sxs-lookup"><span data-stu-id="36241-126">Otherwise, the deployment might fail.</span></span>

-   <span data-ttu-id="36241-127">您的网络 (包括交换机和虚拟 Lan (Vlan)) 应配置为支持 PXE。</span><span class="sxs-lookup"><span data-stu-id="36241-127">Your network, including switches and virtual LANs (VLANs), should be configured to support PXE.</span></span> <span data-ttu-id="36241-128">有关 IP 帮助程序和 PXE 配置的详细信息, 请参阅您的网络供应商。</span><span class="sxs-lookup"><span data-stu-id="36241-128">Refer to your network vendor for more information about IP Helper and PXE configuration.</span></span> <span data-ttu-id="36241-129">或者, 如果未启用 PXE 支持, 你可以将[可启动媒体](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network)用于部署。</span><span class="sxs-lookup"><span data-stu-id="36241-129">Alternatively, you can use [bootable media](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) for your deployments, if PXE support isn’t enabled.</span></span>

    > [!NOTE]
    > <span data-ttu-id="36241-130">对于 Surface Pro 设备, 仅在使用以太网适配器或来自 Microsoft 的插接站时, 才支持从网络启动 (PXE 启动)。</span><span class="sxs-lookup"><span data-stu-id="36241-130">For Surface Pro devices, booting from the network (PXE boot) is only supported when you use an Ethernet adapter or docking station from Microsoft.</span></span> <span data-ttu-id="36241-131">第三方以太网适配器不支持与 Surface Pro 进行 PXE 启动。</span><span class="sxs-lookup"><span data-stu-id="36241-131">Third-party Ethernet adapters don’t support PXE boot with Surface Pro.</span></span> <span data-ttu-id="36241-132">有关详细信息, 请参阅[以太网适配器和 Surface 部署](https://docs.microsoft.com/surface/ethernet-adapters-and-surface-device-deployment)。</span><span class="sxs-lookup"><span data-stu-id="36241-132">See [Ethernet adapters and Surface deployment](https://docs.microsoft.com/surface/ethernet-adapters-and-surface-device-deployment) for more information.</span></span>

## <a name="configure-system-center-configuration-manager-for-operating-system-deployment"></a><span data-ttu-id="36241-133">为操作系统部署配置 System Center Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="36241-133">Configure System Center Configuration Manager for operating system deployment</span></span>

<span data-ttu-id="36241-134">本文假定你已具有正常的 System Center Configuration Manager 部署, 并且不详细介绍了从头开始部署和配置 Configuration Manager 所需的所有步骤。</span><span class="sxs-lookup"><span data-stu-id="36241-134">This article assumes you already have a healthy System Center Configuration Manager deployment, and doesn’t detail all the steps required to deploy and configure Configuration Manager from scratch.</span></span> <span data-ttu-id="36241-135">System Center Configuration Manager 上的[文档和配置指南](https://docs.microsoft.com/sccm/)是一个很好的资源;如果尚未部署配置管理器, 建议您从这些资源开始。</span><span class="sxs-lookup"><span data-stu-id="36241-135">The [documentation and the configuration guidance](https://docs.microsoft.com/sccm/) on the System Center Configuration Manager is a great resource; we recommend you start with these resources if you haven’t yet deployed Configuration Manager.</span></span>

<span data-ttu-id="36241-136">按照以下说明验证是否正确配置了操作系统部署 (OSD) 功能。</span><span class="sxs-lookup"><span data-stu-id="36241-136">Use the following instructions to verify that the operating system deployment (OSD) features are configured properly.</span></span>

### <a name="validate-and-upgrade-configuration-manager"></a><span data-ttu-id="36241-137">验证和升级 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="36241-137">Validate and upgrade Configuration Manager</span></span>

1.  <span data-ttu-id="36241-138">在 Configuration Manager 控制台中, 转到 "**管理** \> **更新和服务**"。</span><span class="sxs-lookup"><span data-stu-id="36241-138">In the Configuration Manager console, go to **Administration** \> **Updates and Servicing**.</span></span>

2.  <span data-ttu-id="36241-139">检查已安装的内部版本和适用的更新 (尚未安装)。</span><span class="sxs-lookup"><span data-stu-id="36241-139">Check the installed build and applicable updates that haven’t been installed yet.</span></span>

3.  <span data-ttu-id="36241-140">查看[System Center Configuration Manager 中对 Windows 10 的支持](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client);如果需要升级你的部署, 请选择要安装的更新, 然后选择 "**下载**"。</span><span class="sxs-lookup"><span data-stu-id="36241-140">Review [Support for Windows 10 in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client); if you need to upgrade your deployment, select the update you want to install, and then select **Download**.</span></span>

4.  <span data-ttu-id="36241-141">下载完成后, 选择更新, 然后选择 "**安装更新包**"。</span><span class="sxs-lookup"><span data-stu-id="36241-141">After the download is complete, select the update, and then select **Install Update Pack**.</span></span>

### <a name="configure-distribution-points-to-support-pxe-and-multicast"></a><span data-ttu-id="36241-142">配置分发点以支持 PXE 和多播</span><span class="sxs-lookup"><span data-stu-id="36241-142">Configure distribution points to support PXE and multicast</span></span>

1.  <span data-ttu-id="36241-143">在 Configuration Manager 控制台中, 转到 "**管理** \> **分发点**"。</span><span class="sxs-lookup"><span data-stu-id="36241-143">In the Configuration Manager console, go to **Administration** \> **Distribution Points**.</span></span>

2.  <span data-ttu-id="36241-144">选择将为 Microsoft 团队聊天室部署提供服务的分发点服务器, 然后选择 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="36241-144">Select the distribution point server that will serve the Microsoft Teams Rooms deployment, and then select **Properties**.</span></span>

3.  <span data-ttu-id="36241-145">选择 " **PXE** " 选项卡, 确保启用以下设置:</span><span class="sxs-lookup"><span data-stu-id="36241-145">Select the **PXE** tab, and ensure that the following settings are enabled:</span></span>
    -   <span data-ttu-id="36241-146">为客户端启用 PXE 支持</span><span class="sxs-lookup"><span data-stu-id="36241-146">Enable PXE support for clients</span></span>
    -   <span data-ttu-id="36241-147">允许此分发点响应传入的 PXE 请求</span><span class="sxs-lookup"><span data-stu-id="36241-147">Allow this distribution point to respond to incoming PXE requests</span></span>
    -   <span data-ttu-id="36241-148">启用未知计算机支持</span><span class="sxs-lookup"><span data-stu-id="36241-148">Enable unknown computer support</span></span>

4.  <span data-ttu-id="36241-149">*可选:* 若要启用多址广播支持, 请选择 "**多播**" 选项卡, 并确保启用以下设置:</span><span class="sxs-lookup"><span data-stu-id="36241-149">*Optional:* To enable multicast support, select the **Multicast** tab, and ensure that the following settings are enabled:</span></span>
    -   <span data-ttu-id="36241-150">启用多播以同时向多个客户端发送数据</span><span class="sxs-lookup"><span data-stu-id="36241-150">Enable multicast to simultaneously send data to multiple clients</span></span>
    -   <span data-ttu-id="36241-151">根据网络团队的建议配置 UDP 端口范围</span><span class="sxs-lookup"><span data-stu-id="36241-151">Configure the UDP port range as per your network team’s recommendation</span></span>

### <a name="configure-the-network-access-account"></a><span data-ttu-id="36241-152">配置网络访问帐户</span><span class="sxs-lookup"><span data-stu-id="36241-152">Configure the Network Access Account</span></span>

1.  <span data-ttu-id="36241-153">在 Configuration Manager 控制台中, 转到 "**管理** \> **网站配置** \> **网站**", 然后选择网站。</span><span class="sxs-lookup"><span data-stu-id="36241-153">In the Configuration Manager console, go to **Administration** \> **Site Configuration** \> **Sites**, and then select the site.</span></span>

2.  <span data-ttu-id="36241-154">在 "**设置**" 组中, 选择 "**配置网站组件** \> **软件分发**"。</span><span class="sxs-lookup"><span data-stu-id="36241-154">In the **Settings** group, select **Configure Site Components** \> **Software Distribution**.</span></span>

3.  <span data-ttu-id="36241-155">选择 "**网络访问帐户**" 选项卡。设置一个或多个帐户, 然后选择 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="36241-155">Select the **Network Access Account** tab. Set up one or more accounts, and then select **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="36241-156">帐户不需要任何特殊权利, 除非分发点服务器上的 "**从网络访问此计算机**" 权利除外。</span><span class="sxs-lookup"><span data-stu-id="36241-156">The accounts don’t need any special rights, except for the **Access this computer from the network** right on the distribution point server.</span></span> <span data-ttu-id="36241-157">常规域用户帐户将非常合适。</span><span class="sxs-lookup"><span data-stu-id="36241-157">A generic domain user account will be appropriate.</span></span> <span data-ttu-id="36241-158">有关详细信息, 请参阅[在 System Center Configuration Manager 中管理用于访问内容的帐户](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA)。</span><span class="sxs-lookup"><span data-stu-id="36241-158">For more information, see [Manage accounts to access content in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span></span>

### <a name="configure-a-boot-image"></a><span data-ttu-id="36241-159">配置启动映像</span><span class="sxs-lookup"><span data-stu-id="36241-159">Configure a boot image</span></span>

1.  <span data-ttu-id="36241-160">在 Configuration Manager 控制台中, 转到 "**软件库** \> **操作系统** \> **启动" 图像**。</span><span class="sxs-lookup"><span data-stu-id="36241-160">In the Configuration Manager console, go to **Software Library** \> **Operating System** \> **Boot Images**.</span></span>

2.  <span data-ttu-id="36241-161">选择 "**启动映像 (x64)**", 然后选择 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="36241-161">Select **Boot image (x64)**, and then select **Properties**.</span></span>

3.  <span data-ttu-id="36241-162">选择 "**数据源**" 选项卡, 然后**从启用 PXE 的分发点启用 "从启用 PXE 的分发点部署此启动映像"**。</span><span class="sxs-lookup"><span data-stu-id="36241-162">Select the **Data Source** tab, and enable **Deploy this boot image from the PXE-enabled distribution point**.</span></span>

4.  <span data-ttu-id="36241-163">选择 "**可选组件**" 选项卡以安装所需组件:</span><span class="sxs-lookup"><span data-stu-id="36241-163">Select the **Optional Components** tab to install required components:</span></span>

    1.  <span data-ttu-id="36241-164">选择星号图标, 然后搜索**HTML (WinPE-HTA)**</span><span class="sxs-lookup"><span data-stu-id="36241-164">Select the star icon, and search for **HTML (WinPE-HTA)**</span></span>

    2.  <span data-ttu-id="36241-165">选择 **"确定"** 将 HTML 应用程序支持添加到启动映像。</span><span class="sxs-lookup"><span data-stu-id="36241-165">Select **OK** to add HTML application support in to the boot image.</span></span>

5.  <span data-ttu-id="36241-166">*可选:* 若要自定义部署体验, 请选择 "**自定义**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="36241-166">*Optional:* To customize the deployment experience, select the **Customization** tab.</span></span>
    -   <span data-ttu-id="36241-167">如果希望在部署期间有权访问命令提示符, 请启用**命令支持 (仅限测试)** 。</span><span class="sxs-lookup"><span data-stu-id="36241-167">Enable **command support (testing only)** if you want to have access to a command prompt during the deployment.</span></span> <span data-ttu-id="36241-168">如果启用了此功能, 你可以在部署期间随时选择**F8**来启动命令提示符。</span><span class="sxs-lookup"><span data-stu-id="36241-168">When this is enabled, you can start a command prompt by selecting **F8** at any time during the deployment.</span></span>
    -   <span data-ttu-id="36241-169">你还可以指定要在部署期间显示的自定义背景图像。</span><span class="sxs-lookup"><span data-stu-id="36241-169">You can also specify a custom background image to be displayed during the deployment.</span></span> <span data-ttu-id="36241-170">若要设置图像, 请启用 "**指定自定义背景图像文件 (UNC 路径"** 和 "选择你的背景"。</span><span class="sxs-lookup"><span data-stu-id="36241-170">To set an image, enable **Specify the custom background image file (UNC path** and select your background.</span></span>

6.  <span data-ttu-id="36241-171">当系统询问时, 选择 **"是"** , 然后将更新后的启动映像分发到分发点。</span><span class="sxs-lookup"><span data-stu-id="36241-171">When asked, select **Yes** and distribute the updated boot image to your distribution points.</span></span>

<span data-ttu-id="36241-172">有关详细信息, 请参阅[通过 System Center Configuration Manager 管理启动映像](https://docs.microsoft.com/sccm/osd/get-started/manage-boot-images)。</span><span class="sxs-lookup"><span data-stu-id="36241-172">For more information, see [Manage boot images with System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-boot-images).</span></span>

> [!NOTE]
> <span data-ttu-id="36241-173">你可以创建可启动 USB 媒体, 以针对没有 PXE 支持的环境启动基于配置管理器任务序列的部署。</span><span class="sxs-lookup"><span data-stu-id="36241-173">You can create a bootable USB media to initiate Configuration Manager task sequence–based deployments for environments that have no PXE support.</span></span> <span data-ttu-id="36241-174">可启动媒体仅包含启动映像、可选预启动命令及其所需的文件, 以及配置管理器二进制文件以支持启动到 Windows PE 并连接到配置管理器以执行其余的部署过程。</span><span class="sxs-lookup"><span data-stu-id="36241-174">The bootable media contains only the boot image, optional prestart commands and their required files, and Configuration Manager binaries to support booting into Windows PE and connecting to Configuration Manager for the rest of the deployment process.</span></span> <span data-ttu-id="36241-175">有关详细信息, 请参阅[如何创建可启动媒体](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia)。</span><span class="sxs-lookup"><span data-stu-id="36241-175">For more information, see [How to Create Bootable Media](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia).</span></span>

## <a name="create-configuration-manager-packages"></a><span data-ttu-id="36241-176">创建 Configuration Manager 程序包</span><span class="sxs-lookup"><span data-stu-id="36241-176">Create Configuration Manager packages</span></span>

> [!IMPORTANT]
> <span data-ttu-id="36241-177">每个 SRS 安装程序版本所需的操作系统版本随每个 MSI 版本更改。</span><span class="sxs-lookup"><span data-stu-id="36241-177">The required operating system version for each SRS installer version changes with every MSI release.</span></span> <span data-ttu-id="36241-178">若要确定给定 MSI 的最佳操作系统版本, 请运行一次控制台安装脚本。</span><span class="sxs-lookup"><span data-stu-id="36241-178">To determine the best operating system version for a given MSI, run the console setup script once.</span></span> <span data-ttu-id="36241-179">若要了解详细信息, 请参阅[使用 System Center Configuration Manager 部署 Microsoft 团队聊天室](room-systems-scale.md)。</span><span class="sxs-lookup"><span data-stu-id="36241-179">To learn more, see [Deploy Microsoft Teams Rooms by using System Center Configuration Manager](room-systems-scale.md).</span></span>

<span data-ttu-id="36241-180">配置管理器需要多个程序包来部署和配置 Microsoft 团队聊天室单元。</span><span class="sxs-lookup"><span data-stu-id="36241-180">Configuration Manager requires a number of packages to deploy and configure the Microsoft Teams Rooms units.</span></span>

<span data-ttu-id="36241-181">您需要创建和配置以下程序包, 然后将它们分发到分配有分发点服务器角色的 Configuration Manager 站点系统。</span><span class="sxs-lookup"><span data-stu-id="36241-181">You need to create and configure the following packages, and then distribute them to the Configuration Manager site systems that have been assigned the distribution point server role.</span></span>

| <span data-ttu-id="36241-182">**程序包名称**</span><span class="sxs-lookup"><span data-stu-id="36241-182">**Package name**</span></span>                     | <span data-ttu-id="36241-183">**类型**</span><span class="sxs-lookup"><span data-stu-id="36241-183">**Type**</span></span>               | <span data-ttu-id="36241-184">**说明**</span><span class="sxs-lookup"><span data-stu-id="36241-184">**Description**</span></span>                                                                           |
|--------------------------------------|------------------------|-------------------------------------------------------------------------------------------|
| <span data-ttu-id="36241-185">SRS v2-SRS 应用程序包</span><span class="sxs-lookup"><span data-stu-id="36241-185">SRS v2 - SRS Application Package</span></span>     | <span data-ttu-id="36241-186">软件包</span><span class="sxs-lookup"><span data-stu-id="36241-186">Software package</span></span>       | <span data-ttu-id="36241-187">Microsoft 团队聊天室部署工具包的程序包</span><span class="sxs-lookup"><span data-stu-id="36241-187">Package for the Microsoft Teams Rooms deployment kit</span></span>                                      |
| <span data-ttu-id="36241-188">SRS v2-Sysprep 程序包</span><span class="sxs-lookup"><span data-stu-id="36241-188">SRS v2 - Sysprep Package</span></span>             | <span data-ttu-id="36241-189">软件包</span><span class="sxs-lookup"><span data-stu-id="36241-189">Software package</span></span>       | <span data-ttu-id="36241-190">用于配置 Microsoft 团队聊天室单元的自定义无人参与的程序包</span><span class="sxs-lookup"><span data-stu-id="36241-190">Package for the custom Unattended.xml to configure Microsoft Teams Rooms units</span></span>            |
| <span data-ttu-id="36241-191">SRS v2-Set-SRSComputerName 程序包</span><span class="sxs-lookup"><span data-stu-id="36241-191">SRS v2 - Set-SRSComputerName Package</span></span> | <span data-ttu-id="36241-192">软件包</span><span class="sxs-lookup"><span data-stu-id="36241-192">Software package</span></span>       | <span data-ttu-id="36241-193">用于 HTML 应用程序 (HTA) 的程序包在部署期间分配计算机名称</span><span class="sxs-lookup"><span data-stu-id="36241-193">Package for the HTML application (HTA) to assign a computer name during the deployment</span></span>    |
| <span data-ttu-id="36241-194">SRS v2-配置 SRS 设置</span><span class="sxs-lookup"><span data-stu-id="36241-194">SRS v2 - Configure SRS Setup</span></span>         | <span data-ttu-id="36241-195">软件包</span><span class="sxs-lookup"><span data-stu-id="36241-195">Software package</span></span>       | <span data-ttu-id="36241-196">用于配置 Microsoft 团队聊天室应用的部署的程序包</span><span class="sxs-lookup"><span data-stu-id="36241-196">Package to configure deployment of the Microsoft Teams Rooms app</span></span>                          |
| <span data-ttu-id="36241-197">SRS v2-OS 更新程序包</span><span class="sxs-lookup"><span data-stu-id="36241-197">SRS v2 - OS Updates Package</span></span>          | <span data-ttu-id="36241-198">软件包</span><span class="sxs-lookup"><span data-stu-id="36241-198">Software package</span></span>       | <span data-ttu-id="36241-199">用于部署强制操作系统更新的程序包</span><span class="sxs-lookup"><span data-stu-id="36241-199">Package to deploy mandatory operating system updates</span></span>                                      |
| <span data-ttu-id="36241-200">SRS v2-根证书程序包</span><span class="sxs-lookup"><span data-stu-id="36241-200">SRS v2 - Root Certificate Package</span></span>    | <span data-ttu-id="36241-201">软件包</span><span class="sxs-lookup"><span data-stu-id="36241-201">Software package</span></span>       | <span data-ttu-id="36241-202">可选-用于部署根证书的程序包 (对于域加入的设备不需要)</span><span class="sxs-lookup"><span data-stu-id="36241-202">Optional - Package to deploy the root certificate (not required for domain-joined units)</span></span>  |
| <span data-ttu-id="36241-203">SRS v2-Microsoft Monitoring Agent 程序包</span><span class="sxs-lookup"><span data-stu-id="36241-203">SRS v2 - Microsoft Monitoring Agent Package</span></span> | <span data-ttu-id="36241-204">软件包</span><span class="sxs-lookup"><span data-stu-id="36241-204">Software package</span></span>       | <span data-ttu-id="36241-205">可选-用于部署和配置 Microsoft Operations Management Suite 代理的程序包</span><span class="sxs-lookup"><span data-stu-id="36241-205">Optional - Package to deploy and configure the Microsoft Operations Management Suite agent</span></span>|
| <span data-ttu-id="36241-206">SRS v2-WinPE 后台程序包</span><span class="sxs-lookup"><span data-stu-id="36241-206">SRS v2 - WinPE Background Package</span></span>    | <span data-ttu-id="36241-207">软件包</span><span class="sxs-lookup"><span data-stu-id="36241-207">Software package</span></span>       | <span data-ttu-id="36241-208">用于与启动映像一起使用的自定义背景图像的程序包</span><span class="sxs-lookup"><span data-stu-id="36241-208">Package for the custom background image to use with boot images</span></span>                           |
| <span data-ttu-id="36241-209">Windows 10 企业版</span><span class="sxs-lookup"><span data-stu-id="36241-209">Windows 10 Enterprise</span></span>                | <span data-ttu-id="36241-210">操作系统映像</span><span class="sxs-lookup"><span data-stu-id="36241-210">Operating system image</span></span> | <span data-ttu-id="36241-211">操作系统安装文件 (安装 .wim) 的程序包</span><span class="sxs-lookup"><span data-stu-id="36241-211">Package for the operating system installation file (install.wim)</span></span>                          |
| <span data-ttu-id="36241-212">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="36241-212">Surface Pro</span></span>                          | <span data-ttu-id="36241-213">驱动程序包</span><span class="sxs-lookup"><span data-stu-id="36241-213">Driver package</span></span>         | <span data-ttu-id="36241-214">适用于 Microsoft Surface Pro 的设备驱动程序和固件的程序包</span><span class="sxs-lookup"><span data-stu-id="36241-214">Package for the device drivers and firmware for Microsoft Surface Pro</span></span>                     |
| <span data-ttu-id="36241-215">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="36241-215">Surface Pro 4</span></span>                        | <span data-ttu-id="36241-216">驱动程序包</span><span class="sxs-lookup"><span data-stu-id="36241-216">Driver package</span></span>         | <span data-ttu-id="36241-217">适用于 Microsoft Surface Pro 4 的设备驱动程序和固件的程序包</span><span class="sxs-lookup"><span data-stu-id="36241-217">Package for the device drivers and firmware for Microsoft Surface Pro 4</span></span>                   |

<span data-ttu-id="36241-218">有关详细信息, 请参阅[System Center Configuration Manager 中的程序包和程序](https://docs.microsoft.com/sccm/apps/deploy-use/packages-and-programs)。</span><span class="sxs-lookup"><span data-stu-id="36241-218">For more information, see [Packages and programs in System Center Configuration Manager](https://docs.microsoft.com/sccm/apps/deploy-use/packages-and-programs).</span></span>

### <a name="create-folders-for-the-package-source-files"></a><span data-ttu-id="36241-219">为程序包源文件创建文件夹</span><span class="sxs-lookup"><span data-stu-id="36241-219">Create folders for the package source files</span></span>

<span data-ttu-id="36241-220">配置管理器要求程序包源文件在首次创建时和更新时组织在特定文件夹结构中。</span><span class="sxs-lookup"><span data-stu-id="36241-220">Configuration Manager requires package source files to be organized in a specific folder structure when they’re first created and when they’re updated.</span></span>

<span data-ttu-id="36241-221">在 System Center Configuration Manager 管理中心网站或主网站上创建以下文件夹结构, 或者在用于托管程序包源文件的服务器共享上创建以下文件夹结构:</span><span class="sxs-lookup"><span data-stu-id="36241-221">Create the following folder structure on the System Center Configuration Manager central administration site or primary site, or on a server share you’re using to host package source files:</span></span>

-   <span data-ttu-id="36241-222">SRS v2-Microsoft Monitoring Agent 程序包</span><span class="sxs-lookup"><span data-stu-id="36241-222">SRS v2 - Microsoft Monitoring Agent Package</span></span>
-   <span data-ttu-id="36241-223">SRS v2-OS 更新程序包</span><span class="sxs-lookup"><span data-stu-id="36241-223">SRS v2 - OS Updates Package</span></span>
-   <span data-ttu-id="36241-224">SRS v2-根证书程序包</span><span class="sxs-lookup"><span data-stu-id="36241-224">SRS v2 - Root Certificate Package</span></span>
-   <span data-ttu-id="36241-225">SRS v2-Set-SRSComputerName 程序包</span><span class="sxs-lookup"><span data-stu-id="36241-225">SRS v2 - Set-SRSComputerName Package</span></span>
-   <span data-ttu-id="36241-226">SRS v2-SRS 应用程序包</span><span class="sxs-lookup"><span data-stu-id="36241-226">SRS v2 - SRS Application Package</span></span>
-   <span data-ttu-id="36241-227">SRS v2-配置 SRS 设置</span><span class="sxs-lookup"><span data-stu-id="36241-227">SRS v2 - Configure SRS Setup</span></span>
-   <span data-ttu-id="36241-228">SRS v2-Sysprep 程序包</span><span class="sxs-lookup"><span data-stu-id="36241-228">SRS v2 - Sysprep Package</span></span>
-   <span data-ttu-id="36241-229">设备</span><span class="sxs-lookup"><span data-stu-id="36241-229">Drivers</span></span>
    -   <span data-ttu-id="36241-230">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="36241-230">Surface Pro</span></span>
    -   <span data-ttu-id="36241-231">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="36241-231">Surface Pro 4</span></span>
-   <span data-ttu-id="36241-232">操作系统</span><span class="sxs-lookup"><span data-stu-id="36241-232">Operating Systems</span></span>
    -   <span data-ttu-id="36241-233">Windows 10 企业版</span><span class="sxs-lookup"><span data-stu-id="36241-233">Windows 10 Enterprise</span></span>

> [!TIP]
> <span data-ttu-id="36241-234">你还可以[下载](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)和使用 zip 文件, 该文件包含要导入的程序包的文件夹结构、你需要使用的脚本和任务序列模板。</span><span class="sxs-lookup"><span data-stu-id="36241-234">You may also [download](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) and use the zip file that includes the folder structure for the packages, the scripts that you need to use, and the task sequence template, that you need to import.</span></span>

### <a name="create-the-monitoring-agent-package"></a><span data-ttu-id="36241-235">创建监视 agent 程序包</span><span class="sxs-lookup"><span data-stu-id="36241-235">Create the Monitoring agent package</span></span>

1. <span data-ttu-id="36241-236">从<https://go.microsoft.com/fwlink/?LinkId=828603>下载监视代理。</span><span class="sxs-lookup"><span data-stu-id="36241-236">Download the Monitoring agent from <https://go.microsoft.com/fwlink/?LinkId=828603>.</span></span>

2. <span data-ttu-id="36241-237">通过打开命令提示符窗口并在命令提示符处输入**MMASetup-AMD64/c:** 将程序包解压缩到 " **SRS V2-Microsoft Monitoring Agent" 程序包**文件夹中。</span><span class="sxs-lookup"><span data-stu-id="36241-237">Extract the package into the **SRS v2 - Microsoft Monitoring Agent Package** folder by opening a Command Prompt window and entering **MMASetup-AMD64.exe /C:**     at the command prompt.</span></span>

3. <span data-ttu-id="36241-238">在 Configuration Manager 控制台中, 转到 "**软件库** \> **应用程序管理** \> **程序包**", 然后选择 "**创建程序包**"。</span><span class="sxs-lookup"><span data-stu-id="36241-238">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4. <span data-ttu-id="36241-239">输入以下信息以创建程序包:</span><span class="sxs-lookup"><span data-stu-id="36241-239">Enter the following information to create the package:</span></span>

   - <span data-ttu-id="36241-240">名称<strong>: SRS v2-Microsoft Monitoring Agent 程序包</strong></span><span class="sxs-lookup"><span data-stu-id="36241-240">Name<strong>: SRS v2 - Microsoft Monitoring Agent Package</strong></span></span>

   - <span data-ttu-id="36241-241">制造商<strong>: Microsoft Corporation</strong></span><span class="sxs-lookup"><span data-stu-id="36241-241">Manufacturer<strong>: Microsoft Corporation</strong></span></span>

   - <span data-ttu-id="36241-242">版本<strong>: 8.1.11081.0</strong> (输入下载的安装文件的版本)</span><span class="sxs-lookup"><span data-stu-id="36241-242">Version<strong>: 8.1.11081.0</strong> (enter the version of the downloaded installation file)</span></span>

   - <span data-ttu-id="36241-243">选中 "**此程序包包含源文件**" 复选框, 输入 SRS v2 的路径 **-Microsoft Monitoring Agent 程序包**文件夹, 然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="36241-243">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Microsoft Monitoring Agent Package** folder, and then select **Next**.</span></span>

5. <span data-ttu-id="36241-244">选择 "**不创建程序**", 然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="36241-244">Select **Do not create a program**, and then select **Next**.</span></span>

6. <span data-ttu-id="36241-245">查看**确认设置**页面, 然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="36241-245">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7. <span data-ttu-id="36241-246">选择 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="36241-246">Select **Close**.</span></span>

### <a name="create-the-operating-system-updates-package"></a><span data-ttu-id="36241-247">创建操作系统更新程序包</span><span class="sxs-lookup"><span data-stu-id="36241-247">Create the operating system updates package</span></span>

1. <span data-ttu-id="36241-248">在 " **SRS v2-OS 更新" 程序包**文件夹中, 创建一个名为**Install-SRSv2-OS-Updates**的新 PowerShell 脚本。</span><span class="sxs-lookup"><span data-stu-id="36241-248">In the **SRS v2 - OS Updates Package** folder, create a new PowerShell script named **Install-SRSv2-OS-Updates.ps1**.</span></span>

2. <span data-ttu-id="36241-249">将下面的脚本复制到**Install-SRSv2-OS-Updates**脚本中。</span><span class="sxs-lookup"><span data-stu-id="36241-249">Copy the script below into the **Install-SRSv2-OS-Updates.ps1** script.</span></span> <span data-ttu-id="36241-250">或者, 你也可以从[此处](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)下载 Install-SRSv2-OS-Updates 脚本。</span><span class="sxs-lookup"><span data-stu-id="36241-250">Alternatively, you can download the Install-SRSv2-OS-Updates.ps1 script from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
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
3. <span data-ttu-id="36241-251">将强制性的 Windows 更新包下载到同一文件夹中。</span><span class="sxs-lookup"><span data-stu-id="36241-251">Download the mandatory Windows Update packages into the same folder.</span></span>
   > [!NOTE]
   > <span data-ttu-id="36241-252">发布本文时, 只需[KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) 。</span><span class="sxs-lookup"><span data-stu-id="36241-252">At the time this article was published, only [KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) was required.</span></span> <span data-ttu-id="36241-253">选中 "[配置 Microsoft 团队聊天室" 控制台](console.md), 查看是否需要任何其他更新。</span><span class="sxs-lookup"><span data-stu-id="36241-253">Check [Configure a Microsoft Teams Rooms console](console.md), to see whether any other updates are required.</span></span>

4. <span data-ttu-id="36241-254">在 Configuration Manager 控制台中, 转到 "**软件库** \> **应用程序管理** \> **程序包**", 然后选择 "**创建程序包**"。</span><span class="sxs-lookup"><span data-stu-id="36241-254">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

5. <span data-ttu-id="36241-255">输入以下信息以创建程序包:</span><span class="sxs-lookup"><span data-stu-id="36241-255">Enter the following information to create the package:</span></span>
   -   <span data-ttu-id="36241-256">名称: **SRS v2-OS 更新程序包**</span><span class="sxs-lookup"><span data-stu-id="36241-256">Name: **SRS v2 – OS Updates Package**</span></span>
   -   <span data-ttu-id="36241-257">制造商: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="36241-257">Manufacturer: **Microsoft Corporation**</span></span>
   -   <span data-ttu-id="36241-258">版本: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="36241-258">Version: **1.0.0**</span></span>
   -   <span data-ttu-id="36241-259">选中 "**此程序包包含源文件**" 复选框, 输入**SRS V2-OS 更新程序包**文件夹的路径, 然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="36241-259">Select the **This package contains source files** check box, enter the path to the **SRS v2 - OS Updates Package** folder, and then select **Next**.</span></span>

6. <span data-ttu-id="36241-260">选择 "**不创建程序**", 然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="36241-260">Select **Do not create a program**, and then select **Next**.</span></span>

7. <span data-ttu-id="36241-261">查看**确认设置**页面, 然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="36241-261">Review the **Confirm the settings** page, and then select **Next**.</span></span>

8. <span data-ttu-id="36241-262">选择 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="36241-262">Select **Close**.</span></span>

### <a name="create-the-root-certificate-package-optional"></a><span data-ttu-id="36241-263">创建根证书程序包 (可选)</span><span class="sxs-lookup"><span data-stu-id="36241-263">Create the root certificate package (optional)</span></span>

<span data-ttu-id="36241-264">创建此程序包以分配不会加入 Active Directory 域的设备的根证书。</span><span class="sxs-lookup"><span data-stu-id="36241-264">You create this package to distribute the root certificate for devices that won’t be joined to an Active Directory domain.</span></span> <span data-ttu-id="36241-265">仅当满足下列两个条件时才创建此程序包:</span><span class="sxs-lookup"><span data-stu-id="36241-265">Create this package only if both the following conditions apply:</span></span>
-   <span data-ttu-id="36241-266">你的部署包括本地 Lync 或 Skype for business 服务器。</span><span class="sxs-lookup"><span data-stu-id="36241-266">Your deployment includes on-premises Lync or Skype for Business Server.</span></span>
-   <span data-ttu-id="36241-267">Microsoft 团队房间单元配置为在工作组中工作, 而不是域成员。</span><span class="sxs-lookup"><span data-stu-id="36241-267">Microsoft Teams Rooms units are configured to work in a workgroup instead of a domain member.</span></span>

1.  <span data-ttu-id="36241-268">将根证书复制到 " **SRS v2-根证书包**" 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="36241-268">Copy the root certificate into the **SRS v2 – Root Certificate Package** folder.</span></span>

2.  <span data-ttu-id="36241-269">在 Configuration Manager 控制台中, 转到 "**软件库** \> **应用程序管理** \> **程序包**", 然后选择 "**创建程序包**"。</span><span class="sxs-lookup"><span data-stu-id="36241-269">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

3.  <span data-ttu-id="36241-270">输入以下信息以创建程序包:</span><span class="sxs-lookup"><span data-stu-id="36241-270">Enter the following information to create the package:</span></span>
    -   <span data-ttu-id="36241-271">名称: **SRS v2-根证书程序包**</span><span class="sxs-lookup"><span data-stu-id="36241-271">Name: **SRS v2 – Root Certificate Package**</span></span>
    -   <span data-ttu-id="36241-272">制造商:*你的组织的名称*</span><span class="sxs-lookup"><span data-stu-id="36241-272">Manufacturer: *Your organization’s name*</span></span>
    -   <span data-ttu-id="36241-273">版本: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="36241-273">Version: **1.0.0**</span></span>
    -   <span data-ttu-id="36241-274">选中 "**此程序包包含源文件**" 复选框, 输入 " **SRS V2-根证书程序包**" 文件夹的路径, 然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="36241-274">Select the **This package contains source files** check box, enter the path to the **SRS v2 – Root Certificate Package** folder, and then select **Next**.</span></span>

4.  <span data-ttu-id="36241-275">选择 "**不创建程序**", 然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="36241-275">Select **Do not create a program**, and then select **Next**.</span></span>

5.  <span data-ttu-id="36241-276">查看**确认设置**页面, 然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="36241-276">Review the **Confirm the settings** page, and then select **Next**.</span></span>

6.  <span data-ttu-id="36241-277">选择 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="36241-277">Select **Close**.</span></span>

### <a name="create-the-microsoft-teams-rooms-deployment-kit-package"></a><span data-ttu-id="36241-278">创建 Microsoft 团队聊天室部署套件程序包</span><span class="sxs-lookup"><span data-stu-id="36241-278">Create the Microsoft Teams Rooms deployment kit package</span></span>

1.  <span data-ttu-id="36241-279">从<https://go.microsoft.com/fwlink/?linkid=851168>下载最新版本的**Microsoft 团队会议室部署工具包**, 并将其安装到工作站。</span><span class="sxs-lookup"><span data-stu-id="36241-279">Download the latest version of the **Microsoft Teams Rooms deployment kit** from <https://go.microsoft.com/fwlink/?linkid=851168>, and install it to a workstation.</span></span>

2.  <span data-ttu-id="36241-280">将内容从**C:\\Program Files (x86)\\Skype 会议室系统部署工具包**复制到**srs v2-srs 应用程序包**文件夹。</span><span class="sxs-lookup"><span data-stu-id="36241-280">Copy the content from **C:\\Program Files (x86)\\Skype Room System Deployment Kit** to the **SRS v2 - SRS Application Package** folder.</span></span>

3.  <span data-ttu-id="36241-281">在 Configuration Manager 控制台中, 转到 "**软件库** \> **应用程序管理** \> **程序包**", 然后选择 "**创建程序包**"。</span><span class="sxs-lookup"><span data-stu-id="36241-281">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4.  <span data-ttu-id="36241-282">输入以下信息以创建程序包:</span><span class="sxs-lookup"><span data-stu-id="36241-282">Enter the following information to create the package:</span></span>
    -   <span data-ttu-id="36241-283">名称: **srs v2 – Srs 应用程序包**</span><span class="sxs-lookup"><span data-stu-id="36241-283">Name: **SRS v2 – SRS Application Package**</span></span>
    -   <span data-ttu-id="36241-284">制造商: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="36241-284">Manufacturer: **Microsoft Corporation**</span></span>
    -   <span data-ttu-id="36241-285">版本: **3.1.104.0** (输入下载的安装文件的版本)</span><span class="sxs-lookup"><span data-stu-id="36241-285">Version: **3.1.104.0** (enter the version of the downloaded installation file)</span></span>
    -   <span data-ttu-id="36241-286">选中 "**此程序包包含源文件**" 复选框, 输入**SRS V2-srs 应用程序包**文件夹的路径, 然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="36241-286">Select the **This package contains source files** check box, enter the path to the **SRS v2 – SRS Application Package** folder, and then select **Next**.</span></span>
5.  <span data-ttu-id="36241-287">选择 "**不创建程序**", 然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="36241-287">Select **Do not create a program**, and then select **Next**.</span></span>

6.  <span data-ttu-id="36241-288">查看**确认设置**页面, 然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="36241-288">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7.  <span data-ttu-id="36241-289">选择 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="36241-289">Select **Close**.</span></span>

### <a name="create-the-computer-name-assignment-package"></a><span data-ttu-id="36241-290">创建计算机名称分配包</span><span class="sxs-lookup"><span data-stu-id="36241-290">Create the computer name assignment package</span></span>

1.  <span data-ttu-id="36241-291">在 " **SRS V2 SRSComputerName 包**" 文件夹中, 创建名为**SET-SRSCOMPUTERNAME**的新 HTML 应用程序。</span><span class="sxs-lookup"><span data-stu-id="36241-291">In the **SRS v2 - Set-SRSComputerName Package** folder, create a new HTML application named **Set-SRSComputerName.hta** .</span></span>

2.  <span data-ttu-id="36241-292">将以下脚本复制到**Set-SRSComputerName**文件中。</span><span class="sxs-lookup"><span data-stu-id="36241-292">Copy the following script into the **Set-SRSComputerName.hta** file.</span></span> <span data-ttu-id="36241-293">或者, 您可以从[此处](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)下载 Set-SRSComputerName 文件。</span><span class="sxs-lookup"><span data-stu-id="36241-293">Alternatively, you can download the Set-SRSComputerName.hta file from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
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
3.  <span data-ttu-id="36241-294">在 Configuration Manager 控制台中, 转到 "**软件库** \> **应用程序管理** \> **程序包**", 然后选择 "**创建程序包**"。</span><span class="sxs-lookup"><span data-stu-id="36241-294">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4.  <span data-ttu-id="36241-295">输入以下信息以创建程序包:</span><span class="sxs-lookup"><span data-stu-id="36241-295">Enter the following information to create the package:</span></span>

    -   <span data-ttu-id="36241-296">名称: **SRS v2-Set-SRSComputerName 程序包**</span><span class="sxs-lookup"><span data-stu-id="36241-296">Name: **SRS v2 - Set-SRSComputerName Package**</span></span>

    -   <span data-ttu-id="36241-297">制造商: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="36241-297">Manufacturer: **Microsoft Corporation**</span></span>

    -   <span data-ttu-id="36241-298">版本: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="36241-298">Version: **1.0.0**</span></span>

    -   <span data-ttu-id="36241-299">选中 "**此程序包包含源文件**" 复选框, 输入**SRS v2 SRSComputerName 程序包**文件夹的路径, 然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="36241-299">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Set-SRSComputerName Package** folder, and then select **Next**.</span></span>

5.  <span data-ttu-id="36241-300">选择 "**不创建程序**", 然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="36241-300">Select **Do not create a program**, and then select **Next**.</span></span>

6.  <span data-ttu-id="36241-301">查看**确认设置**页面, 然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="36241-301">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7.  <span data-ttu-id="36241-302">选择 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="36241-302">Select **Close**.</span></span>

### <a name="create-the-sysprep-package"></a><span data-ttu-id="36241-303">创建 Sysprep 程序包</span><span class="sxs-lookup"><span data-stu-id="36241-303">Create the Sysprep package</span></span>

1. <span data-ttu-id="36241-304">在**SRS v2-Sysprep 程序包**文件夹中, 创建名为**UNATTEND.XML**的新 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="36241-304">In the **SRS v2 – Sysprep Package** folder, create a new XML file named **Unattend.xml** .</span></span>

2. <span data-ttu-id="36241-305">将以下文本复制到**unattend.xml**文件中。</span><span class="sxs-lookup"><span data-stu-id="36241-305">Copy the following text into the **Unattend.xml** file.</span></span> <span data-ttu-id="36241-306">或者, 您可以从[此处](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)下载 unattend.xml 文件。</span><span class="sxs-lookup"><span data-stu-id="36241-306">Alternatively, you can download the Unattend.xml file from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
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
3. <span data-ttu-id="36241-307">在 Configuration Manager 控制台中, 转到 "**软件库** \> **应用程序管理** \> **程序包**", 然后选择 "**创建程序包**"。</span><span class="sxs-lookup"><span data-stu-id="36241-307">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4. <span data-ttu-id="36241-308">输入以下信息以创建程序包:</span><span class="sxs-lookup"><span data-stu-id="36241-308">Enter the following information to create the package:</span></span>
   -   <span data-ttu-id="36241-309">名称: **SRS v2-Sysprep 程序包**</span><span class="sxs-lookup"><span data-stu-id="36241-309">Name: **SRS v2 - Sysprep Package**</span></span>
   -   <span data-ttu-id="36241-310">制造商: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="36241-310">Manufacturer: **Microsoft Corporation**</span></span>
   -   <span data-ttu-id="36241-311">版本: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="36241-311">Version: **1.0.0**</span></span>
   -   <span data-ttu-id="36241-312">选中 "**此程序包包含源文件**" 复选框, 输入 SRS v2 的路径 **-"Sysprep 程序包**" 文件夹, 然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="36241-312">Select the **This package contains source files** check box, enter the path to the **SRS v2 – Sysprep Package** folder, and then select **Next**.</span></span>
5. <span data-ttu-id="36241-313">选择 "**不创建程序**", 然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="36241-313">Select **Do not create a program**, and then select **Next**.</span></span>

6. <span data-ttu-id="36241-314">查看**确认设置**页面, 然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="36241-314">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7. <span data-ttu-id="36241-315">选择 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="36241-315">Select **Close**.</span></span>

### <a name="create-the-windows-10-enterprise-package"></a><span data-ttu-id="36241-316">创建 Windows 10 企业版程序包</span><span class="sxs-lookup"><span data-stu-id="36241-316">Create the Windows 10 Enterprise package</span></span>

1.  <span data-ttu-id="36241-317">获取 Windows 10 企业版 x64 媒体, 并将**install**文件复制到**操作系统\\Windows 10 企业版**文件夹。</span><span class="sxs-lookup"><span data-stu-id="36241-317">Obtain a Windows 10 Enterprise x64 media, and copy the **install.wim** file to the **Operating Systems\\Windows 10 Enterprise** folder.</span></span>

2.  <span data-ttu-id="36241-318">在 Configuration Manager 控制台中, 转到 "**软件库** \> **操作系统** \> "**操作系统映像**, 然后选择 "**添加操作系统映像**"。</span><span class="sxs-lookup"><span data-stu-id="36241-318">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Operating System Images**, and then select **Add Operating System Image**.</span></span>

3.  <span data-ttu-id="36241-319">指定刚复制的**install**文件的路径, 然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="36241-319">Specify the path to the **install.wim** file you just copied, and then select **Next**.</span></span>

4.  <span data-ttu-id="36241-320">将 "**版本**" 字段更新为与 Windows 10 企业版映像的内部版本号相匹配, 然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="36241-320">Update the **Version** field to match the build number of the Windows 10 Enterprise image, and then select **Next**.</span></span>

5.  <span data-ttu-id="36241-321">查看 "**详细信息**" 页面, 然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="36241-321">Review the **Details** page, and then select **Next**.</span></span>

6.  <span data-ttu-id="36241-322">选择 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="36241-322">Select **Close**.</span></span>

<span data-ttu-id="36241-323">有关详细信息, 请参阅[用 System Center Configuration Manager 管理操作系统映像](https://docs.microsoft.com/sccm/osd/get-started/manage-operating-system-images)。</span><span class="sxs-lookup"><span data-stu-id="36241-323">For more information, see [Manage operating system images with System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-operating-system-images).</span></span>

### <a name="create-surface-pro-device-driver-packages"></a><span data-ttu-id="36241-324">创建 Surface Pro 设备驱动程序包</span><span class="sxs-lookup"><span data-stu-id="36241-324">Create Surface Pro device driver packages</span></span>

<span data-ttu-id="36241-325">Surface Pro 和 Surface Pro 4 均支持 Microsoft 球队会议室。</span><span class="sxs-lookup"><span data-stu-id="36241-325">Microsoft Teams Rooms is supported for both Surface Pro and Surface Pro 4.</span></span> <span data-ttu-id="36241-326">您需要为环境中的每个 Surface Pro 模型创建一个驱动程序包。</span><span class="sxs-lookup"><span data-stu-id="36241-326">You need to create a driver package for each Surface Pro model you have in your environment.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="36241-327">驱动程序必须与 Windows 10 企业版内部版本和 Microsoft 团队聊天室部署工具包版本兼容。</span><span class="sxs-lookup"><span data-stu-id="36241-327">The drivers must be compatible with the Windows 10 Enterprise build and the Microsoft Teams Rooms deployment kit version.</span></span> <span data-ttu-id="36241-328">有关详细信息, 请参阅[下载 Surface 设备的最新固件和驱动程序](https://docs.microsoft.com/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices)和[配置控制台](console.md)。</span><span class="sxs-lookup"><span data-stu-id="36241-328">For more information, see [Download the latest firmware and drivers for Surface devices](https://docs.microsoft.com/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices) and [Configure a console](console.md).</span></span>

1.  <span data-ttu-id="36241-329">下载最新的驱动程序和固件。</span><span class="sxs-lookup"><span data-stu-id="36241-329">Download the latest drivers and firmware.</span></span>
    -   <span data-ttu-id="36241-330">对于 Surface Pro:<https://www.microsoft.com/download/details.aspx?id=55484></span><span class="sxs-lookup"><span data-stu-id="36241-330">For Surface Pro: <https://www.microsoft.com/download/details.aspx?id=55484></span></span>
    -   <span data-ttu-id="36241-331">对于 Surface Pro 4:<https://www.microsoft.com/download/details.aspx?id=49498></span><span class="sxs-lookup"><span data-stu-id="36241-331">For Surface Pro 4: <https://www.microsoft.com/download/details.aspx?id=49498></span></span>

2.  <span data-ttu-id="36241-332">提取已下载的驱动程序和固件。</span><span class="sxs-lookup"><span data-stu-id="36241-332">Extract the downloaded driver and firmware.</span></span> <span data-ttu-id="36241-333">打开命令提示符窗口, 在命令提示符处输入以下命令之一:</span><span class="sxs-lookup"><span data-stu-id="36241-333">Open a Command Prompt window and at the command prompt, enter one of the following commands:</span></span>
    -   `msiexec /a C:\SurfacePro_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro"`
    -   `msiexec /a C:\SurfacePro4_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro 4"`

3.  <span data-ttu-id="36241-334">在 Configuration Manager 控制台中, 转到 "**软件库** \> **操作系统** \> **驱动程序**", 然后选择 "**导入驱动程序**"。</span><span class="sxs-lookup"><span data-stu-id="36241-334">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Drivers**, and then select **Import Driver**.</span></span>

4.  <span data-ttu-id="36241-335">选择 **"导入以下网络路径 (UNC) 中的所有驱动程序**", 选择源文件夹 (例如,\\C\\:\\_Sources 驱动程序 Surface Pro), 然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="36241-335">Select **Import all drivers in the following network path (UNC)**, select the source folder (for example, C:\\_Sources\\Drivers\\Surface Pro), and then select **Next**.</span></span>

5.  <span data-ttu-id="36241-336">在 "**指定导入的驱动程序的详细信息**" 页面上, 选择列出的所有驱动程序, 然后选择 "**启用这些驱动程序并允许计算机安装它们**"。</span><span class="sxs-lookup"><span data-stu-id="36241-336">On the **Specify the details for the imported drivers** page, select all the listed drivers, and then select **Enable these drivers and allow computers to install them**.</span></span>

6.  <span data-ttu-id="36241-337">选择 "**类别**", 创建与曲面模型相匹配的新类别, 选择 **"确定**", 然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="36241-337">Select **Categories**, create a new category that matches the Surface model, select **OK**, and then select **Next**.</span></span>

7.  <span data-ttu-id="36241-338">选择 "**新建程序包**"。</span><span class="sxs-lookup"><span data-stu-id="36241-338">Select **New Package**.</span></span>

8.  <span data-ttu-id="36241-339">指定与 Surface Pro 模型相匹配的程序包名称, 输入用于存储驱动程序包文件的文件夹路径, 选择 **"确定**", 然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="36241-339">Specify the package name that matches the Surface Pro model, enter a folder path to store the driver package files in, select **OK**, and then select **Next**.</span></span>

9.  <span data-ttu-id="36241-340">在 "**启动映像**" 页面上, 确保未选中任何启动映像, 然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="36241-340">On the **boot images** page, ensure that no boot images are selected, and then select **Next**.</span></span>

10. <span data-ttu-id="36241-341">选择 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="36241-341">Select **Close**.</span></span>

11. <span data-ttu-id="36241-342">转到 "**软件库** \> **操作系统** \> **驱动程序**", 选择 "**文件夹\>创建文件夹**", 然后输入与您刚为其导入驱动程序的 Surface Pro 模型相匹配的文件夹名称。</span><span class="sxs-lookup"><span data-stu-id="36241-342">Go to **Software Library** \> **Operating Systems** \> **Drivers**, select **Folder \> Create Folder**, and enter a folder name that matches the Surface Pro model that you just imported the drivers for.</span></span>

12. <span data-ttu-id="36241-343">将所有导入的驱动程序移动到新创建的文件夹, 以便更轻松地进行导航和操作。</span><span class="sxs-lookup"><span data-stu-id="36241-343">Move all the imported drivers to the newly created folder for easier navigation and operation.</span></span>

> [!NOTE]
> <span data-ttu-id="36241-344">对您可能拥有的其他 Surface Pro 模型重复相同步骤。</span><span class="sxs-lookup"><span data-stu-id="36241-344">Repeat the same steps for other Surface Pro models you might have.</span></span> <span data-ttu-id="36241-345">有关详细信息, 请参阅[管理 System Center Configuration Manager 中的驱动程序](https://docs.microsoft.com/sccm/osd/get-started/manage-drivers)。</span><span class="sxs-lookup"><span data-stu-id="36241-345">For more information, see [Manage drivers in System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-drivers).</span></span>

### <a name="create-microsoft-teams-rooms-configuration-package"></a><span data-ttu-id="36241-346">创建 Microsoft 团队聊天室配置包</span><span class="sxs-lookup"><span data-stu-id="36241-346">Create Microsoft Teams Rooms Configuration Package</span></span>

1.  <span data-ttu-id="36241-347">在 Configuration Manager 控制台中, 转到 "**软件库** \> **应用程序管理** \> **程序包**", 然后选择 "**创建程序包**"。</span><span class="sxs-lookup"><span data-stu-id="36241-347">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

2.  <span data-ttu-id="36241-348">输入以下信息以创建程序包:</span><span class="sxs-lookup"><span data-stu-id="36241-348">Enter the following information to create the package:</span></span>

    -   <span data-ttu-id="36241-349">名称: **SRS v2-配置 SRS 安装程序包**</span><span class="sxs-lookup"><span data-stu-id="36241-349">Name: **SRS v2 - Configure SRS Setup Package**</span></span>

    -   <span data-ttu-id="36241-350">制造商: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="36241-350">Manufacturer: **Microsoft Corporation**</span></span>

    -   <span data-ttu-id="36241-351">版本: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="36241-351">Version: **1.0.0**</span></span>

    -   <span data-ttu-id="36241-352">选中 "**此程序包包含源文件**" 复选框, 输入 SRS v2 的路径 **-"配置 srs 设置**" 文件夹, 然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="36241-352">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Configure SRS Setup** folder, and then select **Next**.</span></span>

3.  <span data-ttu-id="36241-353">选择 "**不创建程序**", 然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="36241-353">Select **Do not create a program**, and then select **Next**.</span></span>

4.  <span data-ttu-id="36241-354">查看**确认设置**页面, 然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="36241-354">Review the **Confirm the settings** page, and then select **Next**.</span></span>

5.  <span data-ttu-id="36241-355">选择 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="36241-355">Select **Close**.</span></span>



## <a name="distribute-configuration-manager-packages"></a><span data-ttu-id="36241-356">分发 Configuration Manager 程序包</span><span class="sxs-lookup"><span data-stu-id="36241-356">Distribute Configuration Manager packages</span></span>

<span data-ttu-id="36241-357">必须将所有程序包分发到在 Configuration Manager 层次结构中分配有分发点角色的服务器。</span><span class="sxs-lookup"><span data-stu-id="36241-357">All the packages must be distributed to the servers that have been assigned the distribution point role in the Configuration Manager hierarchy.</span></span> <span data-ttu-id="36241-358">按照以下说明启动软件包分发。</span><span class="sxs-lookup"><span data-stu-id="36241-358">Follow the instructions below to initiate package distribution.</span></span>

1.  <span data-ttu-id="36241-359">分发软件包。</span><span class="sxs-lookup"><span data-stu-id="36241-359">Distribute software packages.</span></span>

    1.  <span data-ttu-id="36241-360">在 Configuration Manager 控制台中, 转到 "**软件库** \> **应用程序管理** \> "**程序包**。</span><span class="sxs-lookup"><span data-stu-id="36241-360">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**.</span></span> <span data-ttu-id="36241-361">选择要分发的所有软件包, 然后选择 "**分发内容**"。</span><span class="sxs-lookup"><span data-stu-id="36241-361">Select all the software packages you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="36241-362">查看程序包列表, 然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="36241-362">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="36241-363">将所有分发点服务器 (或分发点组, 具体取决于您的 Configuration Manager 层次结构) 添加到列表, 然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="36241-363">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="36241-364">选择 "**下一步**", 然后选择 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="36241-364">Select **Next**, and then select **Close**.</span></span>

2.  <span data-ttu-id="36241-365">分发驱动程序包。</span><span class="sxs-lookup"><span data-stu-id="36241-365">Distribute driver packages.</span></span>

    1.  <span data-ttu-id="36241-366">在 Configuration Manager 控制台中, 转到**软件库** \> **操作系统** \> **驱动程序包**。</span><span class="sxs-lookup"><span data-stu-id="36241-366">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Driver Packages**.</span></span> <span data-ttu-id="36241-367">选择要分发的所有驱动程序包, 然后选择 "**分发内容**"。</span><span class="sxs-lookup"><span data-stu-id="36241-367">Select all the driver packages you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="36241-368">查看程序包列表, 然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="36241-368">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="36241-369">将所有分发点服务器 (或分发点组, 具体取决于您的 Configuration Manager 层次结构) 添加到列表, 然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="36241-369">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="36241-370">选择 "**下一步**", 然后选择 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="36241-370">Select **Next**, and then select **Close**.</span></span>

3.  <span data-ttu-id="36241-371">分发操作系统程序包。</span><span class="sxs-lookup"><span data-stu-id="36241-371">Distribute operating system packages.</span></span>

    1.  <span data-ttu-id="36241-372">在 Configuration Manager 控制台中, 转到**软件库** \> **操作系统** \>的操作系统**映像**。</span><span class="sxs-lookup"><span data-stu-id="36241-372">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Operating System Images**.</span></span> <span data-ttu-id="36241-373">选择要分发的所有操作系统映像, 然后选择 "**分发内容**"。</span><span class="sxs-lookup"><span data-stu-id="36241-373">Select all the operating system images you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="36241-374">查看程序包列表, 然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="36241-374">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="36241-375">将所有分发点服务器 (或分发点组, 具体取决于您的 Configuration Manager 层次结构) 添加到列表, 然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="36241-375">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="36241-376">选择 "**下一步**", 然后选择 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="36241-376">Select **Next**, and then select **Close**.</span></span>

> [!NOTE]
> <span data-ttu-id="36241-377">程序包分发可能需要一些时间, 具体取决于程序包大小、Configuration Manager 层次结构、分发点服务器数以及网络中可用的带宽。</span><span class="sxs-lookup"><span data-stu-id="36241-377">Package distribution might take some time, depending on the package size, Configuration Manager hierarchy, number of distribution point servers, and the bandwidth available in your network.</span></span>
> 
> <span data-ttu-id="36241-378">必须先分发所有程序包, 然后才能开始部署 Microsoft 团队聊天室单元。</span><span class="sxs-lookup"><span data-stu-id="36241-378">All the packages must be distributed before you can start deploying a Microsoft Teams Rooms unit.</span></span>
> 
> <span data-ttu-id="36241-379">你可以通过转到**监视** \> **分发状态** \> **内容状态**来查看 Configuration Manager 控制台中程序包分发的状态。</span><span class="sxs-lookup"><span data-stu-id="36241-379">You can review the status of your package distribution in the Configuration Manager console by going to **Monitoring** \> **Distribution Status** \> **Content Status**.</span></span>

## <a name="configuration-manager-task-sequences"></a><span data-ttu-id="36241-380">配置管理器任务序列</span><span class="sxs-lookup"><span data-stu-id="36241-380">Configuration Manager task sequences</span></span>

<span data-ttu-id="36241-381">将任务序列与 System Center Configuration Manager 配合使用, 以自动执行将操作系统映像部署到目标计算机的步骤。</span><span class="sxs-lookup"><span data-stu-id="36241-381">You use task sequences with System Center Configuration Manager to automate the steps for deploying an operating system image to a destination computer.</span></span> <span data-ttu-id="36241-382">若要以自动方式部署 Microsoft 团队会议室, 请创建一个任务序列, 该序列引用用于启动目标 Microsoft 团队聊天室计算机的启动映像、要安装的 Windows 10 企业操作系统映像以及任何其他其他内容, 如其他应用程序或软件更新。</span><span class="sxs-lookup"><span data-stu-id="36241-382">To deploy a Microsoft Teams Rooms unit in an automated fashion, you create a task sequence that references the boot image used to start the destination Microsoft Teams Rooms computer, the Windows 10 Enterprise operating system image that you want to install, and any other additional content, such as other applications or software updates.</span></span>

### <a name="import-the-sample-task-sequence"></a><span data-ttu-id="36241-383">导入示例任务序列</span><span class="sxs-lookup"><span data-stu-id="36241-383">Import the sample task sequence</span></span>

<span data-ttu-id="36241-384">你可以下载并轻松导入示例任务序列, 并对其进行自定义以满足你的需求。</span><span class="sxs-lookup"><span data-stu-id="36241-384">You can download and easily import a sample task sequence and customize it to meet your needs.</span></span>

1.  <span data-ttu-id="36241-385">[**下载**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)示例任务序列, 并将下载的 zip 文件复制到共享位置。</span><span class="sxs-lookup"><span data-stu-id="36241-385">[**Download**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) the sample task sequence, and copy the downloaded zip file to a shared location.</span></span>
2.  <span data-ttu-id="36241-386">在 Configuration Manager 控制台中, 转到 "**软件库** \> **操作系统** \> "**任务序列**, 然后选择 "**导入任务序列**"。</span><span class="sxs-lookup"><span data-stu-id="36241-386">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Task Sequences**, and then select **Import Task Sequence**.</span></span>

3.  <span data-ttu-id="36241-387">选择 "**浏览**", 转到步骤1中使用的共享文件夹位置, 选择 " **Microsoft 团队聊天室部署 (en-us) .zip** " 文件, 然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="36241-387">Select **Browse**, go to the shared folder location you used in step 1, select the **Microsoft Teams Rooms Deployment (EN-US).zip** file, and then select **Next**.</span></span>

4.  <span data-ttu-id="36241-388">将**操作**设置为 "**新建**", 然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="36241-388">Set **Action** to **Create New**, and then select **Next**.</span></span>

5.  <span data-ttu-id="36241-389">确认设置, 然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="36241-389">Confirm the settings, and then select **Next**.</span></span>

6.  <span data-ttu-id="36241-390">选择 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="36241-390">Select **Close**.</span></span>

### <a name="validate-that-the-reference-packages-are-correctly-linked-to-each-task-sequence-step"></a><span data-ttu-id="36241-391">验证引用程序包是否正确链接到每个任务序列步骤。</span><span class="sxs-lookup"><span data-stu-id="36241-391">Validate that the reference packages are correctly linked to each task sequence step.</span></span>

1. <span data-ttu-id="36241-392">选择导入的任务序列, 然后选择 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="36241-392">Select the imported task sequence, and then select **Edit**.</span></span>

    <span data-ttu-id="36241-393">任务序列编辑器随即打开, 并显示部署和配置 Microsoft 团队聊天室单元所需的每个连续步骤。</span><span class="sxs-lookup"><span data-stu-id="36241-393">The Task Sequence Editor opens and displays each sequential step that you need to deploy and configure a Microsoft Teams Rooms unit.</span></span>

2. <span data-ttu-id="36241-394">演练每个步骤并完成推荐的更新:</span><span class="sxs-lookup"><span data-stu-id="36241-394">Walk through each step and complete the recommended updates:</span></span>

   1. <span data-ttu-id="36241-395">**在 WINDOWS PE 中重启**: 此步骤将重新启动, 然后将计算机启动到 Windows PXE。</span><span class="sxs-lookup"><span data-stu-id="36241-395">**Restart in Windows PE**: This step restarts and then boots the computer into Windows PXE.</span></span> <span data-ttu-id="36241-396">此步骤不需要任何更改。</span><span class="sxs-lookup"><span data-stu-id="36241-396">No changes are required for this step.</span></span>

   2. <span data-ttu-id="36241-397">**分区磁盘 0-UEFI**: 此步骤将擦除磁盘配置, 并基于已配置的设置创建分区。</span><span class="sxs-lookup"><span data-stu-id="36241-397">**Partition Disk 0 – UEFI**: This step wipes the disk configuration and creates partitions based on the configured settings.</span></span> <span data-ttu-id="36241-398">我们建议您不要对此步骤进行任何更改。</span><span class="sxs-lookup"><span data-stu-id="36241-398">We recommend that you not make any changes to this step.</span></span>

   3. <span data-ttu-id="36241-399">**设置 SRS 计算机名**: 此步骤包括一个 HTML 应用程序, 用于在部署期间提供用于为 Microsoft 团队聊天室单元设置计算机名称的 UI。</span><span class="sxs-lookup"><span data-stu-id="36241-399">**Set SRS Computer Name**: This step includes an HTML application to provide a UI to set a computer name for the Microsoft Teams Rooms unit during the deployment.</span></span>
      -  <span data-ttu-id="36241-400">这是一个可选步骤, 但仅当你希望通过备用进程管理计算机命名时, 才可以禁用它。</span><span class="sxs-lookup"><span data-stu-id="36241-400">This is an optional step, but it can only be disabled if you want to manage computer naming through an alternate process.</span></span>
      -  <span data-ttu-id="36241-401">验证是否已选中 " **SRS v2-SRSComputerName** " 程序包。</span><span class="sxs-lookup"><span data-stu-id="36241-401">Verify that the **SRS v2 - Set-SRSComputerName** package is selected.</span></span> <span data-ttu-id="36241-402">如果不是, 请浏览到程序包并将其选中。</span><span class="sxs-lookup"><span data-stu-id="36241-402">If it isn’t, browse to the package and select it.</span></span>

   4. <span data-ttu-id="36241-403">**应用操作系统**: 此步骤指定要部署的操作系统映像和要使用的无人参与 Sysprep 应答文件。</span><span class="sxs-lookup"><span data-stu-id="36241-403">**Apply Operating System**: This step specifies the operating system image to be deployed and the unattended Sysprep answer file to use.</span></span>
      -  <span data-ttu-id="36241-404">验证是否选择了正确的 Windows 10 企业操作系统映像文件。</span><span class="sxs-lookup"><span data-stu-id="36241-404">Verify that the correct Windows 10 Enterprise operating system image file is selected.</span></span>
      -  <span data-ttu-id="36241-405">验证是否已启用 "**为自定义安装使用无人参与或 Sysprep 应答文件**", 并选中 " **SRS V2-sysprep 程序包**"。</span><span class="sxs-lookup"><span data-stu-id="36241-405">Verify that **Use an unattended or Sysprep answer file for a custom installation** is enabled, and the **SRS v2 - Sysprep Package** is selected.</span></span> <span data-ttu-id="36241-406">此外, 请\*\*\*\* 确保文件名设置为**unattend.xml**。</span><span class="sxs-lookup"><span data-stu-id="36241-406">Also ensure that **File Name** is set to **unattend.xml**.</span></span>

   5. <span data-ttu-id="36241-407">**应用 Windows 设置**: 此步骤收集有关 Windows 安装的信息。</span><span class="sxs-lookup"><span data-stu-id="36241-407">**Apply Windows Settings**: This step gathers information about the Windows installation.</span></span>
      -  <span data-ttu-id="36241-408">提供授权和注册信息, 包括产品密钥、本地管理员帐户密码和时区 (取决于你的需要)。</span><span class="sxs-lookup"><span data-stu-id="36241-408">Provide licensing and registration information including the product key, local administrator account password, and time zone (depending on your needs).</span></span>

   6. <span data-ttu-id="36241-409">**应用网络设置**: 此步骤允许你指定工作组或 Active Directory 域名和组织单位。</span><span class="sxs-lookup"><span data-stu-id="36241-409">**Apply Network Settings**: This step allows you to specify a workgroup or Active Directory domain name and organizational unit.</span></span>
      > [!NOTE]
      > <span data-ttu-id="36241-410">请参阅[Skype 会议室系统域加入](domain-joining-considerations.md)有关建议操作的注意事项, 在部署 Microsoft 团队聊天室单元作为 Actve Directory 域的成员时需要执行此操作。</span><span class="sxs-lookup"><span data-stu-id="36241-410">See [Skype Room System domain joining considerations](domain-joining-considerations.md) for recommended actions you need to take in deploying Microsoft Teams Rooms units as members of an Actve Directory domain.</span></span>
   7. <span data-ttu-id="36241-411">**应用驱动程序:** 此步骤及其子步骤用于基于你所拥有的 Surface Pro 模型部署适用的设备驱动程序和固件。</span><span class="sxs-lookup"><span data-stu-id="36241-411">**Apply Drivers:** This step and its sub-steps are used to deploy applicable device drivers and firmware based on the Surface Pro model you have.</span></span> <span data-ttu-id="36241-412">更新每个步骤以指定与此部署关联的相关驱动程序包。</span><span class="sxs-lookup"><span data-stu-id="36241-412">Update each step to specify the relevant driver package associated with this deployment.</span></span>
      -   <span data-ttu-id="36241-413">每个驱动程序包都配置为利用 Windows Management Instrumentation (WMI) 筛选器, 根据 Surface Pro 和 model 部署相关的驱动程序和固件。</span><span class="sxs-lookup"><span data-stu-id="36241-413">Each driver package is configured to leverage Windows Management Instrumentation (WMI) filters to deploy relevant drivers and firmware based on the Surface Pro make and model.</span></span>
      -   <span data-ttu-id="36241-414">我们强烈建议您不要更改这些驱动程序的配置, 否则部署可能会失败。</span><span class="sxs-lookup"><span data-stu-id="36241-414">We highly recommend that you not alter the configuration of these drivers, otherwise deployment might fail.</span></span>

   8. <span data-ttu-id="36241-415">**设置 Windows 和配置管理器**: 此步骤可部署和配置 Configuration Manager 客户端。</span><span class="sxs-lookup"><span data-stu-id="36241-415">**Set up Windows and Configuration Manager**: This step deploys and configures the Configuration Manager client.</span></span> <span data-ttu-id="36241-416">更新此步骤以指定内置的 Configuration Manager 客户端包。</span><span class="sxs-lookup"><span data-stu-id="36241-416">Update this step to specify the built-in Configuration Manager Client Package.</span></span>

   9. <span data-ttu-id="36241-417">**安装根证书**: 此步骤为非域加入的设备分发根证书, 因此默认情况下为可选和禁用。</span><span class="sxs-lookup"><span data-stu-id="36241-417">**Install Root Certificate**: This step distributes the root certificate for non–domain-joined devices, and therefore is optional and disabled by default.</span></span>
      -   <span data-ttu-id="36241-418">如果需要将根证书部署到 Microsoft 团队聊天室单元, 请启用此步骤。</span><span class="sxs-lookup"><span data-stu-id="36241-418">Enable this step if you need to deploy a root certificate to the Microsoft Teams Rooms units.</span></span>
      -   <span data-ttu-id="36241-419">如果确实需要执行此步骤, 请验证**SRS v2 –根证书程序包**和 "**禁用64位文件系统重定向**" 是否已选中。</span><span class="sxs-lookup"><span data-stu-id="36241-419">If you do need to perform this step, verify that the **SRS v2 – Root Certificate Package** and **Disable 64-bit file system redirection** are selected.</span></span>

   10. <span data-ttu-id="36241-420">**安装和配置监视代理**: 此步骤安装64位版本的 Microsoft Azure 监视器代理并将代理配置为连接到 Log Analytics 工作区。</span><span class="sxs-lookup"><span data-stu-id="36241-420">**Install and Configure Monitoring Agent**: This step installs the 64-bit version of the Microsoft Azure Monitor agent and configures the agent to connect to your Log Analytics workspace.</span></span>
       -   <span data-ttu-id="36241-421">此步骤默认情况下处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="36241-421">This step is disabled by default.</span></span> <span data-ttu-id="36241-422">只有当你要使用监视 Agent 监视 Microsoft 团队会议室的运行状况时, 才启用此步骤。</span><span class="sxs-lookup"><span data-stu-id="36241-422">Enable this step only if you’re going to use the Monitoring Agent to monitor the health of your Microsoft Teams Rooms units.</span></span>
       -   <span data-ttu-id="36241-423">编辑此步骤并更新命令行参数以指定你的**工作区 ID**和**工作区密钥**。</span><span class="sxs-lookup"><span data-stu-id="36241-423">Edit this step and update the command-line parameters to specify your **Workspace ID** and **Workspace Key**.</span></span>
       -   <span data-ttu-id="36241-424">有关获取 Operations Management Suite 工作区 ID 和主键的详细信息, 请参阅[配置 Azure 监视的测试设备](azure-monitor-deploy.md#configure-test-devices-for-azure-monitoring)。</span><span class="sxs-lookup"><span data-stu-id="36241-424">See [Configure test devices for Azure Monitoring](azure-monitor-deploy.md#configure-test-devices-for-azure-monitoring) for more information about obtaining the Operations Management Suite Workspace ID and the primary key.</span></span>
       -   <span data-ttu-id="36241-425">验证**SRS v2-Microsoft Monitoring Agent 程序包**和 "**禁用64位文件系统重定向**" 是否已选中。</span><span class="sxs-lookup"><span data-stu-id="36241-425">Verify that the **SRS v2 – Microsoft Monitoring Agent Package** and **Disable 64-bit file system redirection** are selected.</span></span>
       -   <span data-ttu-id="36241-426">有关监视 Microsoft 团队聊天室部署的运行状况的详细信息, 请参阅[通过 Azure 监视器规划 Microsoft 团队会议室管理](azure-monitor-plan.md)、[通过 Azure 监视器部署 microsoft 团队聊天室管理](azure-monitor-deploy.md)和[管理 Microsoft带有 Azure 监视器的团队聊天室设备](azure-monitor-manage.md)。</span><span class="sxs-lookup"><span data-stu-id="36241-426">For more information about monitoring the health of your Microsoft Teams Rooms deployment, see [Plan Microsoft Teams Rooms management with Azure Monitor](azure-monitor-plan.md), [Deploy Microsoft Teams Rooms management with Azure Monitor](azure-monitor-deploy.md) and [Manage Microsoft Teams Rooms devices with Azure Monitor](azure-monitor-manage.md).</span></span>

   11. <span data-ttu-id="36241-427">**复制 SRS V2 配置文件**: 此步骤将所需的设置和配置文件从 Microsoft 团队聊天室部署工具包复制到本地硬盘。</span><span class="sxs-lookup"><span data-stu-id="36241-427">**Copy SRS v2 Configuration Files**: This step copies the required setup and configuration files from the Microsoft Teams Rooms deployment kit to the local hard drive.</span></span> <span data-ttu-id="36241-428">此步骤不需要自定义。</span><span class="sxs-lookup"><span data-stu-id="36241-428">No customization is required for this step.</span></span>
       -   <span data-ttu-id="36241-429">验证**srs v2 – Srs 应用程序包**和 "**禁用64位文件系统重定向**" 是否已选中。</span><span class="sxs-lookup"><span data-stu-id="36241-429">Verify that the **SRS v2 – SRS Application Package** and **Disable 64-bit file system redirection** are selected.</span></span>

   12. <span data-ttu-id="36241-430">**安装-SRSv2-OS-更新**: 此步骤将部署 Microsoft 团队聊天室部署所需的任何必需的操作系统更新。</span><span class="sxs-lookup"><span data-stu-id="36241-430">**Install-SRSv2-OS-Updates**: This step deploys any mandatory operating system updates required with the Microsoft Teams Rooms deployment.</span></span> <span data-ttu-id="36241-431">请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="36241-431">Do the following:</span></span>
       -   <span data-ttu-id="36241-432">选中 "[配置 Microsoft 团队聊天室" 控制台](console.md)以查看需要哪些更新。</span><span class="sxs-lookup"><span data-stu-id="36241-432">Check [Configure a Microsoft Teams Rooms console](console.md) to see which updates are required.</span></span>
       -   <span data-ttu-id="36241-433">验证**SRS v2-OS 更新程序包**中是否包含所有必需的更新。</span><span class="sxs-lookup"><span data-stu-id="36241-433">Verify that your **SRS v2 – OS Updates Package** includes all the required updates.</span></span>
       -   <span data-ttu-id="36241-434">验证 " **SRS v2-OS 更新" 程序包**是否已选中。</span><span class="sxs-lookup"><span data-stu-id="36241-434">Verify that the **SRS v2 – OS Updates Package** is selected.</span></span>
       -   <span data-ttu-id="36241-435">验证是否已将 PowerShell 执行策略设置为 "**回避**"。</span><span class="sxs-lookup"><span data-stu-id="36241-435">Verify that the PowerShell execution policy is set to **Bypass**.</span></span>

   13. <span data-ttu-id="36241-436">**重新启动计算机**: 此步骤会在安装必需的操作系统更新后重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="36241-436">**Restart Computer**: This step reboots the computer after the mandatory operating system updates are installed.</span></span> <span data-ttu-id="36241-437">此步骤不需要自定义。</span><span class="sxs-lookup"><span data-stu-id="36241-437">No customization is required for this step.</span></span>

   14. <span data-ttu-id="36241-438">**配置 Windows 组件**: 此步骤配置所需的 Windows 功能。</span><span class="sxs-lookup"><span data-stu-id="36241-438">**Configure Windows Components**: This step configures the required Windows features.</span></span> <span data-ttu-id="36241-439">此步骤不需要自定义。</span><span class="sxs-lookup"><span data-stu-id="36241-439">No customization is required for this step.</span></span>

   15. <span data-ttu-id="36241-440">**重新启动计算机**: 此步骤将在配置 Windows 功能后重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="36241-440">**Restart Computer**: This step reboots the computer after the Windows features are configured.</span></span> <span data-ttu-id="36241-441">此步骤不需要自定义。</span><span class="sxs-lookup"><span data-stu-id="36241-441">No customization is required for this step.</span></span>

   16. <span data-ttu-id="36241-442">**添加本地 Skype 用户**: 此步骤创建用于自动登录 Windows 和启动 Microsoft 球队聊天室应用程序的本地 skype 帐户。</span><span class="sxs-lookup"><span data-stu-id="36241-442">**Add Local Skype User**: This step creates the local Skype account used to automatically sign in to Windows and start the Microsoft Teams Rooms application.</span></span> <span data-ttu-id="36241-443">此步骤没有与之关联的任何软件包, 并且不需要进行自定义。</span><span class="sxs-lookup"><span data-stu-id="36241-443">This step doesn’t have any software package associated with it, and no customization is required for it.</span></span>

   17. <span data-ttu-id="36241-444">**设置和配置 SRS 应用程序**: 此步骤为操作系统的下一次启动配置 Microsoft 团队聊天室应用程序安装。</span><span class="sxs-lookup"><span data-stu-id="36241-444">**Set up and configure SRS application**: This step configures the Microsoft Teams Rooms application installation for the next boot of the operating system.</span></span>
       -   <span data-ttu-id="36241-445">验证**srs v2-"配置 Srs 安装程序包**" 和 "**禁用64位文件系统重定向**" 是否已选中。</span><span class="sxs-lookup"><span data-stu-id="36241-445">Verify that the **SRS v2 – Configure SRS Setup Package** and **Disable 64-bit file system redirection** are selected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="36241-446">任务序列步骤必须按所提供的顺序排列, 这一点非常重要。</span><span class="sxs-lookup"><span data-stu-id="36241-446">It is very important that the task sequence steps must be in the provided order.</span></span> <span data-ttu-id="36241-447">修改步骤顺序或配置其他步骤可能会中断部署。</span><span class="sxs-lookup"><span data-stu-id="36241-447">Modifying the order of steps, or configuring additional steps might break the deployment.</span></span>
>
> <span data-ttu-id="36241-448">**设置和配置 SRS 应用程序**步骤必须是任务序列中的最后一步, 否则部署可能失败。</span><span class="sxs-lookup"><span data-stu-id="36241-448">**Set up and configure SRS application** step must be the last step in the task sequence, otherwise the deployment might fail.</span></span>

### <a name="create-deployment-for-the-task-sequence"></a><span data-ttu-id="36241-449">为任务序列创建部署</span><span class="sxs-lookup"><span data-stu-id="36241-449">Create deployment for the task sequence</span></span>

1. <span data-ttu-id="36241-450">选择任务序列, 然后选择 "**部署**"。</span><span class="sxs-lookup"><span data-stu-id="36241-450">Select the task sequence, and then select **Deploy**.</span></span>

2. <span data-ttu-id="36241-451">选择 "**浏览**", 选择要部署的目标集合。</span><span class="sxs-lookup"><span data-stu-id="36241-451">Select **Browse** to select target collection for deployment.</span></span>

3. <span data-ttu-id="36241-452">选择 "**所有未知计算机**", 然后选择 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="36241-452">Select **All Unknown Computers** and then select **OK**.</span></span>

4. <span data-ttu-id="36241-453">选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="36241-453">Select **Next**.</span></span>

5. <span data-ttu-id="36241-454">在 "**用途**" 下拉列表中选择 "**可用**"。</span><span class="sxs-lookup"><span data-stu-id="36241-454">Select **Available** on the **Purpose** drop down list.</span></span>

6. <span data-ttu-id="36241-455">仅在 "**可用于以下**列表" 列表中选择 "**媒体和 PXE** ", 然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="36241-455">Select **Only Media and PXE** in the **Make available to the following** list, and then select **Next**.</span></span>
   > [!WARNING]
   > <span data-ttu-id="36241-456">将 "**用途**" 设置为 "**可用**" 非常重要。</span><span class="sxs-lookup"><span data-stu-id="36241-456">It is very important that **Purpose** is set to **Available**.</span></span> <span data-ttu-id="36241-457">请确保 "**用途**"**未**设置为 "**必需**"。</span><span class="sxs-lookup"><span data-stu-id="36241-457">Make sure that the **Purpose** is **NOT** set to **Required**.</span></span> <span data-ttu-id="36241-458">此外, 请确保仅选择 "在**以下情况下可用**的**媒体和 PXE** "。</span><span class="sxs-lookup"><span data-stu-id="36241-458">Also make sure that you select **Only Media and PXE** in the **Make available to the following**.</span></span>
   >
   > <span data-ttu-id="36241-459">将这些值设置为其他值可能会导致所有计算机在引导时获得 Microsoft 团队会议室部署映像。</span><span class="sxs-lookup"><span data-stu-id="36241-459">Setting these values to something else might cause all computers to get the Microsoft Teams Rooms deployment image when booted.</span></span>
7. <span data-ttu-id="36241-460">不要指定任何计划, 然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="36241-460">Do not specify any schedule and select **Next**.</span></span>

8. <span data-ttu-id="36241-461">不要更改 "**用户体验**" 部分中的任何内容, 然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="36241-461">Do not change anything within the **User Experience** section and select **Next**.</span></span>

9. <span data-ttu-id="36241-462">不要更改 "**通知**" 部分中的任何内容, 然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="36241-462">Do not change anything within the **Alerts** section and select **Next**.</span></span>

10. <span data-ttu-id="36241-463">不要更改 "**分发点**" 部分中的任何内容, 然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="36241-463">Do not change anything within the **Distribution Points** section and select **Next**.</span></span>

11. <span data-ttu-id="36241-464">确认设置, 然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="36241-464">Confirm the settings and then select **Next**.</span></span>

12. <span data-ttu-id="36241-465">选择 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="36241-465">Select **Close**.</span></span>

<a name="validate-and-troubleshoot-the-solution"></a><span data-ttu-id="36241-466">验证和解决解决方案</span><span class="sxs-lookup"><span data-stu-id="36241-466">Validate and troubleshoot the solution</span></span>
--------------------------------------

<span data-ttu-id="36241-467">完成 System Center Configuration Manager 任务序列后, 你需要执行测试运行以验证任务序列是否可以部署和配置 Microsoft 团队会议室单元。</span><span class="sxs-lookup"><span data-stu-id="36241-467">After you’ve completed the System Center Configuration Manager task sequences, you’ll need to perform a test run to validate that the task sequence can deploy and configure Microsoft Teams Rooms units.</span></span>

1.  <span data-ttu-id="36241-468">使用受支持的以太网适配器之一或使用 Surface dock 将测试设备连接到有线网络。</span><span class="sxs-lookup"><span data-stu-id="36241-468">Connect the test device to the wired network by using one of the supported Ethernet adapters or using the Surface dock.</span></span> <span data-ttu-id="36241-469">如果尚未针对你的环境配置 PXE 启动功能, 你可以使用[之前创建](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media)的 usb 闪存驱动器上的启动映像从 usb 启动并连接到 Configuration Manager。</span><span class="sxs-lookup"><span data-stu-id="36241-469">If PXE boot functionality hasn’t been configured for your environment, you can use the boot image on the USB flash drive [that you created earlier](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media) to boot from USB and connect to Configuration Manager.</span></span>

2.  <span data-ttu-id="36241-470">访问固件并启动 PXE 启动:</span><span class="sxs-lookup"><span data-stu-id="36241-470">Access the firmware and initiate PXE boot:</span></span>

    1.  <span data-ttu-id="36241-471">确保已关闭 Surface 设备电源。</span><span class="sxs-lookup"><span data-stu-id="36241-471">Ensure the Surface device is powered off.</span></span>

    2.  <span data-ttu-id="36241-472">按住**音量**按钮。</span><span class="sxs-lookup"><span data-stu-id="36241-472">Press and hold the **Volume Up** button.</span></span>

    3.  <span data-ttu-id="36241-473">按下并释放 "**电源**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="36241-473">Press and release the **Power** button.</span></span>

    4.  <span data-ttu-id="36241-474">在设备开始启动后, 释放 "**音量**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="36241-474">After the device begins to boot, release the **Volume Up** button.</span></span>

    5.  <span data-ttu-id="36241-475">选择 "**启动配置**"。</span><span class="sxs-lookup"><span data-stu-id="36241-475">Select **Boot configuration**.</span></span>

    6.  <span data-ttu-id="36241-476">请执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="36241-476">Do one of the following:</span></span>

        -   <span data-ttu-id="36241-477">选择 " **PXE 启动**", 然后将其拖动到列表顶部。</span><span class="sxs-lookup"><span data-stu-id="36241-477">Select **PXE boot**, and drag it to the top of the list.</span></span> <span data-ttu-id="36241-478">或者, 你可以在网络适配器上向左轻扫以立即启动到设备。</span><span class="sxs-lookup"><span data-stu-id="36241-478">Alternatively, you can swipe left on the network adapter to boot to the device immediately.</span></span> <span data-ttu-id="36241-479">这不会影响启动顺序。</span><span class="sxs-lookup"><span data-stu-id="36241-479">This won’t affect the boot order.</span></span>
        -   <span data-ttu-id="36241-480">选择包含启动媒体的 u 盘。</span><span class="sxs-lookup"><span data-stu-id="36241-480">Select the USB flash drive that holds the boot media.</span></span>

3.  <span data-ttu-id="36241-481">选择 "**退出**", 然后选择 "**立即重启**"。</span><span class="sxs-lookup"><span data-stu-id="36241-481">Select **Exit**, and then select **Restart Now**.</span></span>

4.  <span data-ttu-id="36241-482">出现提示时, 选择 "**输入**网络启动服务"。</span><span class="sxs-lookup"><span data-stu-id="36241-482">When prompted, select **Enter** for network boot service.</span></span>

5.  <span data-ttu-id="36241-483">Windows PE 将加载到内存中, 任务序列向导将启动。</span><span class="sxs-lookup"><span data-stu-id="36241-483">Windows PE will load into memory, and the Task Sequence Wizard will start.</span></span> <span data-ttu-id="36241-484">选择 "**下一步**" 继续。</span><span class="sxs-lookup"><span data-stu-id="36241-484">Select **Next** to continue.</span></span>

6.  <span data-ttu-id="36241-485">选择之前导入的任务序列, 然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="36241-485">Select the task sequence that you imported earlier, and then select **Next**.</span></span>

7.  <span data-ttu-id="36241-486">在应用磁盘配置后, 系统将提示你为设备指定计算机名称。</span><span class="sxs-lookup"><span data-stu-id="36241-486">After the disk configuration is applied, you’ll be prompted to specify a computer name for the device.</span></span> <span data-ttu-id="36241-487">用户界面将根据 Surface Pro 设备的序列号显示推荐的计算机名称。</span><span class="sxs-lookup"><span data-stu-id="36241-487">The user interface will display a recommended computer name based on the serial number of the Surface Pro device.</span></span> <span data-ttu-id="36241-488">你可以接受建议的名称, 也可以指定一个新名称。</span><span class="sxs-lookup"><span data-stu-id="36241-488">You can either accept the proposed name or specify a new one.</span></span> <span data-ttu-id="36241-489">按照 "计算机名称分配" 屏幕上的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="36241-489">Follow the instructions on the computer name assignment screen.</span></span> <span data-ttu-id="36241-490">选择 "**接受**" 时, 将开始部署。</span><span class="sxs-lookup"><span data-stu-id="36241-490">When you select **Accept**, the deployment begins.</span></span>

8.  <span data-ttu-id="36241-491">部署过程的其余部分是自动完成的, 不会询问更多用户输入。</span><span class="sxs-lookup"><span data-stu-id="36241-491">The rest of the deployment process is automatic and doesn’t ask for any more user input.</span></span>

9.  <span data-ttu-id="36241-492">部署任务序列完成配置设备后, 你将看到以下配置屏幕, 该屏幕要求你配置 Microsoft 团队聊天室应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="36241-492">After the deployment task sequence finishes configuring the device, you’ll see the following configuration screen that asks you to configure the Microsoft Teams Rooms application settings.</span></span>

    ![Microsoft 团队聊天室应用程序的初始设置屏幕](../media/room-systems-scale-image2.png)

10.  <span data-ttu-id="36241-494">将 Surface Pro 插入 Microsoft 团队聊天室控制台, 然后配置应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="36241-494">Plug the Surface Pro into the Microsoft Teams Rooms console, and configure the application settings.</span></span>

11.  <span data-ttu-id="36241-495">验证[Microsoft 团队聊天室](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)中列出的功能是否帮助正在使用部署的设备。</span><span class="sxs-lookup"><span data-stu-id="36241-495">Validate that the capabilities listed in [Microsoft Teams Rooms help](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) are working on the deployed device.</span></span>


<span data-ttu-id="36241-496">若要解决安装失败的问题, 请检查**SMSTS**文件, 该文件将记录配置管理器任务序列中执行的所有步骤。</span><span class="sxs-lookup"><span data-stu-id="36241-496">To troubleshoot a failed installation, check the **SMSTS.log** file, which logs all the steps executed in a Configuration Manager task sequence.</span></span>

<span data-ttu-id="36241-497">SMSTS 文件存储在多条路径中, 具体取决于生成过程的阶段。</span><span class="sxs-lookup"><span data-stu-id="36241-497">The SMSTS.log file is stored on one of a number of paths, depending on the stage of the build process.</span></span> <span data-ttu-id="36241-498">检查下表以标识 SMSTS 文件的路径。</span><span class="sxs-lookup"><span data-stu-id="36241-498">Check the following table to identify the path to the SMSTS.log file.</span></span>


| <span data-ttu-id="36241-499">**部署阶段**</span><span class="sxs-lookup"><span data-stu-id="36241-499">**Deployment phase**</span></span>                                                            | <span data-ttu-id="36241-500">**任务序列日志路径**</span><span class="sxs-lookup"><span data-stu-id="36241-500">**Task sequence log path**</span></span>                         |
|---------------------------------------------------------------------------------|----------------------------------------------------|
| <span data-ttu-id="36241-501">在 HDD 格式之前的 WinPE</span><span class="sxs-lookup"><span data-stu-id="36241-501">WinPE, before HDD format</span></span>                                                        | <span data-ttu-id="36241-502">X:\\Windows\\Temp\\smstslog\\smsts</span><span class="sxs-lookup"><span data-stu-id="36241-502">X:\\Windows\\Temp\\smstslog\\smsts.log</span></span>             |
| <span data-ttu-id="36241-503">在 HDD 格式后进行 WinPE</span><span class="sxs-lookup"><span data-stu-id="36241-503">WinPE, after HDD format</span></span>                                                         | <span data-ttu-id="36241-504">C:\\_SMSTaskSequence\\log\\Smstslog\\smsts</span><span class="sxs-lookup"><span data-stu-id="36241-504">C:\\_SMSTaskSequence\\Logs\\Smstslog\\smsts.log</span></span>    |
| <span data-ttu-id="36241-505">在安装 Configuration Manager 代理之前已部署操作系统</span><span class="sxs-lookup"><span data-stu-id="36241-505">Operating system deployed, before the Configuration Manager agent was installed</span></span> | <span data-ttu-id="36241-506">c:\\_SMSTaskSequence\\log\\Smstslog\\smsts</span><span class="sxs-lookup"><span data-stu-id="36241-506">c:\\_SMSTaskSequence\\Logs\\Smstslog\\smsts.log</span></span>    |
| <span data-ttu-id="36241-507">操作系统和配置管理器代理已部署</span><span class="sxs-lookup"><span data-stu-id="36241-507">Operating system and the Configuration Manager agent deployed</span></span>                   | <span data-ttu-id="36241-508">% windir%\\System32\\ccm\\log\\Smstslog\\smsts</span><span class="sxs-lookup"><span data-stu-id="36241-508">%windir%\\System32\\ccm\\logs\\Smstslog\\smsts.log</span></span> |
| <span data-ttu-id="36241-509">任务序列执行完成</span><span class="sxs-lookup"><span data-stu-id="36241-509">Task sequence execution complete</span></span>                                                | <span data-ttu-id="36241-510">% windir%\\System32\\ccm\\\\smsts 日志</span><span class="sxs-lookup"><span data-stu-id="36241-510">%windir%\\System32\\ccm\\logs\\smsts.log</span></span>           |

> [!TIP]
> <span data-ttu-id="36241-511">你可以在任务序列期间随时选择**F8**以打开命令控制台, 然后获取对 SMSTS 文件的访问权限。</span><span class="sxs-lookup"><span data-stu-id="36241-511">You can select **F8** at any time during the task sequence to open a command console, and then get access to the SMSTS.log file.</span></span>

<span data-ttu-id="36241-512">若要解决 PXE 启动问题, 请检查 Configuration Manager 服务器上特定于 PXE 操作的两个日志文件:</span><span class="sxs-lookup"><span data-stu-id="36241-512">To troubleshoot PXE boot issues, check the two log files on the Configuration Manager server that are specific to PXE actions:</span></span>

-   <span data-ttu-id="36241-513">**Pxecontrol**, 位于 Configuration Manager 安装日志目录中</span><span class="sxs-lookup"><span data-stu-id="36241-513">**Pxecontrol.log**, located in the Configuration Manager installation logs directory</span></span>

-   <span data-ttu-id="36241-514">**Smspxe**, 位于 Configuration Manager 管理点 (MP) 日志目录中</span><span class="sxs-lookup"><span data-stu-id="36241-514">**Smspxe.log**, located in Configuration Manager Management Point (MP) logs directory</span></span>

<span data-ttu-id="36241-515">有关可用于进一步排除 Configuration Manager 安装故障的日志文件的完整列表, 请参阅[System Center Configuration Manager 中的日志记录文件](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/log-files)。</span><span class="sxs-lookup"><span data-stu-id="36241-515">For a complete list of the log files that you can use to further troubleshoot your Configuration Manager installation, see [Log files in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/log-files).</span></span>
