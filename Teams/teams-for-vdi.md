---
title: 适用于虚拟化桌面基础结构的 Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rafarhi, jmorrow
audience: admin
description: 了解如何在 VDI Microsoft Teams虚拟桌面基础结构 (运行) 应用程序。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: a24de985b601b1d84250863e06fed90a77699483
ms.sourcegitcommit: 592e5a0638c7739dfaa3565b67d4edc621eebc9f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/26/2021
ms.locfileid: "52656075"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a><span data-ttu-id="81f56-103">适用于虚拟化桌面基础结构的 Teams</span><span class="sxs-lookup"><span data-stu-id="81f56-103">Teams for Virtualized Desktop Infrastructure</span></span>

<span data-ttu-id="81f56-104">本文介绍在虚拟化环境中使用Microsoft Teams的要求和限制。</span><span class="sxs-lookup"><span data-stu-id="81f56-104">This article describes the requirements and limitations for using Microsoft Teams in a virtualized environment.</span></span>

## <a name="what-is-vdi"></a><span data-ttu-id="81f56-105">什么是 VDI？</span><span class="sxs-lookup"><span data-stu-id="81f56-105">What is VDI?</span></span>

<span data-ttu-id="81f56-106">虚拟桌面基础结构 (VDI) 是一种虚拟化技术，在数据中心的集中服务器上托管桌面操作系统和应用程序。</span><span class="sxs-lookup"><span data-stu-id="81f56-106">Virtual Desktop Infrastructure (VDI) is virtualization technology that hosts a desktop operating system and applications on a centralized server in a data center.</span></span> <span data-ttu-id="81f56-107">这使具有完全安全且合规的集中源的用户能够获得完全个性化的桌面体验。</span><span class="sxs-lookup"><span data-stu-id="81f56-107">This enables a fully personalized desktop experience to users with a fully secured and compliant centralized source.</span></span>

<span data-ttu-id="81f56-108">Microsoft Teams环境中进行聊天和协作。</span><span class="sxs-lookup"><span data-stu-id="81f56-108">Microsoft Teams in a virtualized environment supports chat and collaboration.</span></span> <span data-ttu-id="81f56-109">此外，Windows虚拟桌面、Citrix 和 VMware 平台，也支持呼叫和会议功能。</span><span class="sxs-lookup"><span data-stu-id="81f56-109">And with the Windows Virtual Desktop, Citrix, and VMware platforms, calling and meeting functionality is also supported.</span></span>

<span data-ttu-id="81f56-110">Teams环境中配置支持多个配置。</span><span class="sxs-lookup"><span data-stu-id="81f56-110">Teams in a virtualized environment supports multiple configurations.</span></span> <span data-ttu-id="81f56-111">这些模式包括 VDI、专用、共享、持久性和非持久性模式。</span><span class="sxs-lookup"><span data-stu-id="81f56-111">These include VDI, dedicated, shared, persistent, and non-persistent modes.</span></span> <span data-ttu-id="81f56-112">功能持续开发，并定期添加，功能将在几个月和数年内扩展。</span><span class="sxs-lookup"><span data-stu-id="81f56-112">Features are in continuous development and are added on a regular basis, and functionality will expand in the coming months and years.</span></span>

<span data-ttu-id="81f56-113">在Teams环境中使用资源可能稍有不同，Teams虚拟化环境中使用资源。</span><span class="sxs-lookup"><span data-stu-id="81f56-113">Using Teams in a virtualized environment might be somewhat different from using Teams in a non-virtualized environment.</span></span> <span data-ttu-id="81f56-114">例如，某些高级功能在虚拟化环境中可能不可用，并且视频分辨率可能有所不同。</span><span class="sxs-lookup"><span data-stu-id="81f56-114">For example, some advanced features might not be available in a virtualized environment, and video resolution might differ.</span></span>

<span data-ttu-id="81f56-115">若要确保获得最佳用户体验，请遵循本文中的指导。</span><span class="sxs-lookup"><span data-stu-id="81f56-115">To ensure an optimal user experience, follow the guidance in this article.</span></span>

> [!Note]
> <span data-ttu-id="81f56-116">有关在不同平台上Teams VDI 的详细信息，请参阅Teams[平台提供的功能](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)。</span><span class="sxs-lookup"><span data-stu-id="81f56-116">For details about Teams VDI on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span></span>

## <a name="teams-on-vdi-components"></a><span data-ttu-id="81f56-117">Teams VDI 组件</span><span class="sxs-lookup"><span data-stu-id="81f56-117">Teams on VDI components</span></span>

<span data-ttu-id="81f56-118">在Teams环境中使用云解决方案需要以下组件。</span><span class="sxs-lookup"><span data-stu-id="81f56-118">Using Teams in a virtualized environment requires the following components.</span></span>

- <span data-ttu-id="81f56-119">**虚拟化代理**：虚拟化提供程序（例如 Azure）的资源和连接管理器</span><span class="sxs-lookup"><span data-stu-id="81f56-119">**Virtualization broker**: The resource and connection manager to the virtualization provider, such as Azure</span></span>
- <span data-ttu-id="81f56-120">**虚拟桌面**：虚拟机 (VM) 运行 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="81f56-120">**Virtual desktop**: The Virtual Machine (VM) stack that runs Microsoft Teams</span></span>
- <span data-ttu-id="81f56-121">**精简客户端**：用户实际交互的终结点</span><span class="sxs-lookup"><span data-stu-id="81f56-121">**Thin client**: The endpoint that the user physically interfaces with</span></span>
- <span data-ttu-id="81f56-122">**Teams桌面应用**：Teams桌面客户端应用</span><span class="sxs-lookup"><span data-stu-id="81f56-122">**Teams desktop app**: The Teams desktop client app</span></span>

## <a name="teams-on-vdi-requirements"></a><span data-ttu-id="81f56-123">Teams VDI 要求</span><span class="sxs-lookup"><span data-stu-id="81f56-123">Teams on VDI requirements</span></span>

### <a name="virtualization-provider-requirements"></a><span data-ttu-id="81f56-124">虚拟化提供商要求</span><span class="sxs-lookup"><span data-stu-id="81f56-124">Virtualization provider requirements</span></span>

<span data-ttu-id="81f56-125">桌面Teams已使用领先的虚拟化解决方案提供商进行验证。</span><span class="sxs-lookup"><span data-stu-id="81f56-125">The Teams desktop app was validated with leading virtualization solution providers.</span></span> <span data-ttu-id="81f56-126">对于多个市场提供商，建议咨询虚拟化解决方案提供商，确保满足最低要求。</span><span class="sxs-lookup"><span data-stu-id="81f56-126">With multiple market providers, we recommend that you consult your virtualization solution provider to ensure that you meet the minimum requirements.</span></span>
  
<span data-ttu-id="81f56-127">目前，Teams虚拟桌面、Citrix 和 VMware (Windows VDI) VDI 上的音频/视频) 优化。</span><span class="sxs-lookup"><span data-stu-id="81f56-127">Currently, Teams on VDI with audio/video (AV) optimization is certified with Windows Virtual Desktop, Citrix, and VMware.</span></span> <span data-ttu-id="81f56-128">查看本部分的信息，确保满足正确功能的所有要求。</span><span class="sxs-lookup"><span data-stu-id="81f56-128">Review the information in this section to ensure that you meet all requirements for proper functionality.</span></span>

### <a name="platforms-certified-for-teams"></a><span data-ttu-id="81f56-129">经认证的平台Teams</span><span class="sxs-lookup"><span data-stu-id="81f56-129">Platforms certified for Teams</span></span>

<span data-ttu-id="81f56-130">以下平台提供适用于 Teams 的虚拟桌面基础结构Teams。</span><span class="sxs-lookup"><span data-stu-id="81f56-130">The following platforms have virtual desktop infrastructure solutions for Teams.</span></span>

|<span data-ttu-id="81f56-131">平台</span><span class="sxs-lookup"><span data-stu-id="81f56-131">Platform</span></span>|<span data-ttu-id="81f56-132">解决方案</span><span class="sxs-lookup"><span data-stu-id="81f56-132">Solution</span></span>|
|----|---|
|![表示 Microsoft 的徽标](media/microsoft-logo.png)| <span data-ttu-id="81f56-134"><a href="/azure/virtual-desktop/teams-on-wvd" target="_blank">Windows虚拟桌面</a></span><span class="sxs-lookup"><span data-stu-id="81f56-134"><a href="/azure/virtual-desktop/teams-on-wvd" target="_blank">Windows Virtual Desktop</a></span></span> |
|![表示 Citrix 的徽标](media/citrix-logo.png)| <span data-ttu-id="81f56-136"><a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Citrix 虚拟应用和桌面</a></span><span class="sxs-lookup"><span data-stu-id="81f56-136"><a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Citrix Virtual Apps and Desktops</a></span></span> |
|![表示 VMware 的徽标](media/vmware-logo.png)| <span data-ttu-id="81f56-138"><a href="https://www.vmware.com/products/horizon.html" target="_blank">VMware Horizon</a></span><span class="sxs-lookup"><span data-stu-id="81f56-138"><a href="https://www.vmware.com/products/horizon.html" target="_blank">VMware Horizon</a></span></span> |

### <a name="windows-virtual-desktop"></a><span data-ttu-id="81f56-139">Windows虚拟桌面</span><span class="sxs-lookup"><span data-stu-id="81f56-139">Windows Virtual Desktop</span></span>

<span data-ttu-id="81f56-140">Windows虚拟桌面为 VDI 上的Teams AV 优化。</span><span class="sxs-lookup"><span data-stu-id="81f56-140">Windows Virtual Desktop provides AV optimization for Teams on VDI.</span></span> <span data-ttu-id="81f56-141">若要了解更多内容以及要求和安装，请参阅[在虚拟Teams Windows应用](/azure/virtual-desktop/teams-on-wvd)。</span><span class="sxs-lookup"><span data-stu-id="81f56-141">To learn more and requirements and installation, see [Use Teams on Windows Virtual Desktop](/azure/virtual-desktop/teams-on-wvd).</span></span>

### <a name="citrix-virtual-apps-and-desktops-requirements"></a><span data-ttu-id="81f56-142">Citrix 虚拟应用和桌面要求</span><span class="sxs-lookup"><span data-stu-id="81f56-142">Citrix Virtual Apps and Desktops requirements</span></span>

<span data-ttu-id="81f56-143">Citrix 虚拟应用和桌面 (以前称为 XenApp 和 XenDesktop) 为 VDI 上的 Teams提供 AV 优化。</span><span class="sxs-lookup"><span data-stu-id="81f56-143">Citrix Virtual Apps and Desktops (formerly known as XenApp and XenDesktop) provides AV optimization for Teams on VDI.</span></span> <span data-ttu-id="81f56-144">借助 Citrix 虚拟应用和桌面，Teams VDI 上的应用程序除了支持聊天和协作外，还支持呼叫和会议功能。</span><span class="sxs-lookup"><span data-stu-id="81f56-144">With Citrix Virtual Apps and Desktops, Teams on VDI supports calling and meeting functionality in addition to chat and collaboration.</span></span>

<span data-ttu-id="81f56-145">可以在 Citrix 下载站点 下载最新版本的 Citrix 虚拟应用 [和桌面](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/)。</span><span class="sxs-lookup"><span data-stu-id="81f56-145">You can download the latest version of Citrix Virtual Apps and Desktops at [the Citrix downloads site](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/).</span></span> <span data-ttu-id="81f56-146"> (需要先登录。) 默认情况下，所需的组件将捆绑到 [Citrix 工作区应用 (CWA) ](https://www.citrix.com/downloads/workspace-app/) 和虚拟交付代理 (VDA) 中。</span><span class="sxs-lookup"><span data-stu-id="81f56-146">(You'll need to sign in first.) The necessary components are bundled into the [Citrix Workspace app (CWA)](https://www.citrix.com/downloads/workspace-app/) and Virtual Delivery Agent (VDA) by default.</span></span> <span data-ttu-id="81f56-147">无需在 CWA 或 VDA 上安装任何其他组件或插件。</span><span class="sxs-lookup"><span data-stu-id="81f56-147">You don't need to install any additional components or plugins on CWA or the VDA.</span></span>

<span data-ttu-id="81f56-148">有关最新的服务器和客户端要求，请参阅 [此 Citrix 网站](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html)。</span><span class="sxs-lookup"><span data-stu-id="81f56-148">For the latest server and client requirements, see [this Citrix website](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html).</span></span>

### <a name="vmware-horizon-workspace-and-desktop-requirements"></a><span data-ttu-id="81f56-149">VMware Horizon Workspace 和桌面要求</span><span class="sxs-lookup"><span data-stu-id="81f56-149">VMware Horizon Workspace and Desktop requirements</span></span>

<span data-ttu-id="81f56-150">VMware Horizon 是一个新式平台，用于跨混合云安全交付虚拟桌面和应用。</span><span class="sxs-lookup"><span data-stu-id="81f56-150">VMware Horizon is a modern platform for secure delivery of virtual desktops and apps across the hybrid cloud.</span></span> <span data-ttu-id="81f56-151">为了提供出色的最终用户体验，VMware Horizon 为 Teams。</span><span class="sxs-lookup"><span data-stu-id="81f56-151">To offer a great end-user experience, VMware Horizon provides media optimization for Teams.</span></span> <span data-ttu-id="81f56-152">此优化可跨虚拟桌面和应用提高整体工作效率，并增强使用虚拟桌面和 Teams 进行呼叫和会议时Teams。</span><span class="sxs-lookup"><span data-stu-id="81f56-152">This optimization improves overall productivity across virtual desktops and apps, and enhances user experience when calling and meeting using Teams.</span></span>

<span data-ttu-id="81f56-153">可以从 VMware 下载页下载最新版本的 [VMware](https://my.vmware.com/web/vmware/downloads/#all_products) Horizon。</span><span class="sxs-lookup"><span data-stu-id="81f56-153">You can download the latest version of VMware Horizon from the [VMware Downloads](https://my.vmware.com/web/vmware/downloads/#all_products) page.</span></span> <span data-ttu-id="81f56-154">默认情况下，所需的媒体优化组件是 Horizon Agent 和 Horizon 客户端的一部分，无需安装任何其他插件来使用适用于 Teams。</span><span class="sxs-lookup"><span data-stu-id="81f56-154">The required media optimization components are part of the Horizon Agent and Horizon Client by default and there's no need to install any additional plug-in to use the optimization feature for Teams.</span></span>

<span data-ttu-id="81f56-155">若要获取最新要求以及如何为用户配置媒体优化Teams，请参阅[此 VMware 网站](https://docs.vmware.com/en/VMware-Horizon/2006/horizon-remote-desktop-features/GUID-F68FA7BB-B08F-4EFF-9BB1-1F9FC71F8214.html)。</span><span class="sxs-lookup"><span data-stu-id="81f56-155">To get the latest requirements and instructions on how to configure media optimization for Teams, see [this VMware website](https://docs.vmware.com/en/VMware-Horizon/2006/horizon-remote-desktop-features/GUID-F68FA7BB-B08F-4EFF-9BB1-1F9FC71F8214.html).</span></span>

## <a name="install-or-update-the-teams-desktop-app-on-vdi"></a><span data-ttu-id="81f56-156">在 VDI Teams或更新桌面应用</span><span class="sxs-lookup"><span data-stu-id="81f56-156">Install or update the Teams desktop app on VDI</span></span>

<span data-ttu-id="81f56-157">可以使用每Teams安装或每用户安装，使用 MSI 包部署适用于 VDI 的桌面应用。</span><span class="sxs-lookup"><span data-stu-id="81f56-157">You can deploy the Teams desktop app for VDI using a per-machine installation or per-user installation using the MSI package.</span></span> <span data-ttu-id="81f56-158">决定使用哪种方法取决于是使用持久性设置还是非持久性设置，以及组织的关联功能需求。</span><span class="sxs-lookup"><span data-stu-id="81f56-158">Deciding on which approach to use depends on whether you use a persistent or non-persistent setup and the associated functionality needs of your organization.</span></span>

<span data-ttu-id="81f56-159">对于专用的持久性设置，任一方法都正常工作。</span><span class="sxs-lookup"><span data-stu-id="81f56-159">For a dedicated persistent setup, either approach would work.</span></span> <span data-ttu-id="81f56-160">但是，对于非永久性设置，Teams每台计算机安装才能高效工作。</span><span class="sxs-lookup"><span data-stu-id="81f56-160">However, for a non-persistent setup, Teams requires a per-machine installation in order to work efficiently.</span></span> <span data-ttu-id="81f56-161">请参阅 [非永久性设置](#non-persistent-setup) 部分。</span><span class="sxs-lookup"><span data-stu-id="81f56-161">See the [Non-persistent setup](#non-persistent-setup) section.</span></span>

<span data-ttu-id="81f56-162">使用每台计算机安装时，将禁用自动更新。</span><span class="sxs-lookup"><span data-stu-id="81f56-162">With per-machine installation, automatic updates is disabled.</span></span> <span data-ttu-id="81f56-163">这意味着，若要更新 Teams应用，必须卸载当前版本以更新到较新版本。</span><span class="sxs-lookup"><span data-stu-id="81f56-163">This means that to update the Teams app, you must uninstall the current version to update to a newer version.</span></span> <span data-ttu-id="81f56-164">通过按用户安装，将启用自动更新。</span><span class="sxs-lookup"><span data-stu-id="81f56-164">With per-user installation, automatic updates is enabled.</span></span> <span data-ttu-id="81f56-165">对于大多数 VDI 部署，我们建议使用Teams安装来部署 VDI。</span><span class="sxs-lookup"><span data-stu-id="81f56-165">For most VDI deployments, we recommend you deploy Teams using per-machine installation.</span></span>

<span data-ttu-id="81f56-166">若要更新到最新版本Teams，请从卸载过程开始，然后是最新的 Teams 版本部署。</span><span class="sxs-lookup"><span data-stu-id="81f56-166">To update to the latest Teams version, start with the uninstall procedure followed by latest Teams version deployment.</span></span>

<span data-ttu-id="81f56-167">若要Teams VDI 环境中进行 AV 优化，精简客户端终结点必须能够访问 Internet。</span><span class="sxs-lookup"><span data-stu-id="81f56-167">For Teams AV optimization in VDI environments to work properly, the thin client endpoint must have access to the internet.</span></span> <span data-ttu-id="81f56-168">如果精简客户端终结点上未提供 Internet 访问，优化启动不会成功。</span><span class="sxs-lookup"><span data-stu-id="81f56-168">If internet access isn't available at the thin client endpoint, optimization startup won't be successful.</span></span> <span data-ttu-id="81f56-169">这意味着用户位于未优化的媒体状态。</span><span class="sxs-lookup"><span data-stu-id="81f56-169">This means that the user is in a non-optimized media state.</span></span>

#### <a name="dedicated-persistent-setup"></a><span data-ttu-id="81f56-170">专用持久设置</span><span class="sxs-lookup"><span data-stu-id="81f56-170">Dedicated persistent setup</span></span>

<span data-ttu-id="81f56-171">在专用的永久性设置中，用户注销后，会保留用户的本地操作系统更改。</span><span class="sxs-lookup"><span data-stu-id="81f56-171">In a dedicated persistent setup, users' local operating system changes are retained after users log off.</span></span> <span data-ttu-id="81f56-172">对于永久性安装，Teams支持每用户和每台计算机安装。</span><span class="sxs-lookup"><span data-stu-id="81f56-172">For persistent setup, Teams supports both per-user and per-machine installation.</span></span>

<span data-ttu-id="81f56-173">下面是建议的最低 VM 配置。</span><span class="sxs-lookup"><span data-stu-id="81f56-173">The following is the recommended minimum VM configuration.</span></span>

|<span data-ttu-id="81f56-174">参数</span><span class="sxs-lookup"><span data-stu-id="81f56-174">Parameter</span></span>  |<span data-ttu-id="81f56-175">工作站操作系统</span><span class="sxs-lookup"><span data-stu-id="81f56-175">Workstation operating system</span></span>  |<span data-ttu-id="81f56-176">服务器操作系统</span><span class="sxs-lookup"><span data-stu-id="81f56-176">Server operating system</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="81f56-177">vCPU</span><span class="sxs-lookup"><span data-stu-id="81f56-177">vCPU</span></span>   |    <span data-ttu-id="81f56-178">2 个核心</span><span class="sxs-lookup"><span data-stu-id="81f56-178">2 cores</span></span>     |  <span data-ttu-id="81f56-179">4、6 或 8</span><span class="sxs-lookup"><span data-stu-id="81f56-179">4,6, or 8</span></span><br><span data-ttu-id="81f56-180">必须了解 NUMA (配置) 基础的非统一内存访问，并相应地配置 VM。</span><span class="sxs-lookup"><span data-stu-id="81f56-180">It's important to understand the underlying non-uniform memory access (NUMA) configuration and configure your VMs accordingly.</span></span>     |
|<span data-ttu-id="81f56-181">RAM</span><span class="sxs-lookup"><span data-stu-id="81f56-181">RAM</span></span>     |   <span data-ttu-id="81f56-182">4 GB</span><span class="sxs-lookup"><span data-stu-id="81f56-182">4 GB</span></span>      | <span data-ttu-id="81f56-183">每个用户 512 到 1024 MB</span><span class="sxs-lookup"><span data-stu-id="81f56-183">512 to 1024 MB per user</span></span>        |
|<span data-ttu-id="81f56-184">存储空间</span><span class="sxs-lookup"><span data-stu-id="81f56-184">Storage</span></span>    | <span data-ttu-id="81f56-185">8 GB</span><span class="sxs-lookup"><span data-stu-id="81f56-185">8 GB</span></span>        | <span data-ttu-id="81f56-186">40 到 60 GB</span><span class="sxs-lookup"><span data-stu-id="81f56-186">40 to 60 GB</span></span>        |

#### <a name="non-persistent-setup"></a><span data-ttu-id="81f56-187">非永久性设置</span><span class="sxs-lookup"><span data-stu-id="81f56-187">Non-persistent setup</span></span>

<span data-ttu-id="81f56-188">在非永久性设置中，用户注销后不会保留用户的本地操作系统更改。</span><span class="sxs-lookup"><span data-stu-id="81f56-188">In a non-persistent setup, users' local operating system changes are not retained after users log off.</span></span> <span data-ttu-id="81f56-189">此类设置通常共享多用户会话。</span><span class="sxs-lookup"><span data-stu-id="81f56-189">Such setups are commonly shared multi-user sessions.</span></span> <span data-ttu-id="81f56-190">VM 配置因用户数和可用物理盒资源而异。</span><span class="sxs-lookup"><span data-stu-id="81f56-190">VM configuration varies based on the number of users and available physical box resources.</span></span>

<span data-ttu-id="81f56-191">对于非永久性设置，Teams桌面应用必须按计算机安装到黄金映像。</span><span class="sxs-lookup"><span data-stu-id="81f56-191">For a non-persistent setup, the Teams desktop app must be installed per-machine to the golden image.</span></span> <span data-ttu-id="81f56-192"> (有关详细信息，请参阅在[VDI 上](#install-or-update-the-teams-desktop-app-on-vdi)安装或更新 Teams 桌面应用部分。) 这可确保在用户会话期间有效启动 Teams 应用。</span><span class="sxs-lookup"><span data-stu-id="81f56-192">(To learn more, see the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.) This ensures an efficient launch of the Teams app during a user session.</span></span>

<span data-ttu-id="81f56-193">在Teams设置中使用缓存管理器还需要配置文件缓存管理器，Teams运行时数据同步。</span><span class="sxs-lookup"><span data-stu-id="81f56-193">Using Teams in a non-persistent setup also requires a profile-caching manager, for efficient Teams runtime data synchronization.</span></span> <span data-ttu-id="81f56-194">高效的数据同步可确保在用户的会话 (缓存用户的数据、配置文件) 设置等用户特定信息。</span><span class="sxs-lookup"><span data-stu-id="81f56-194">Efficient data synchronization ensures that the appropriate user-specific information (such as a user's data, profile, or settings) is cached during the user's session.</span></span> <span data-ttu-id="81f56-195">确保同步这两个文件夹中的数据：</span><span class="sxs-lookup"><span data-stu-id="81f56-195">Make sure data in these two folders are synched:</span></span><br>
- <span data-ttu-id="81f56-196">C：\Users\username\AppData\Local\Microsoft\IdentityCache (%localAppdata%\Microsoft\IdentityCache) </span><span class="sxs-lookup"><span data-stu-id="81f56-196">C:\Users\username\AppData\Local\Microsoft\IdentityCache (%localAppdata%\Microsoft\IdentityCache)</span></span>
- <span data-ttu-id="81f56-197">C：\Users\username\AppData\Roaming\Microsoft\Teams (%appdata%\Microsoft\Teams) </span><span class="sxs-lookup"><span data-stu-id="81f56-197">C:\Users\username\AppData\Roaming\Microsoft\Teams (%appdata%\Microsoft\Teams)</span></span>

> [!NOTE]
> <span data-ttu-id="81f56-198">漫游文件夹 (，或者，如果使用文件夹重定向，则要求缓存管理器) 以确保 Teams 应用具有运行应用程序所需的运行时数据和文件。</span><span class="sxs-lookup"><span data-stu-id="81f56-198">A roaming folder (or, if you are using folder redirection, a caching manager) is required to ensure that the Teams app has the runtime data and files required to run the application.</span></span> <span data-ttu-id="81f56-199">这是缓解网络延迟问题或网络故障所必需的，否则会导致应用程序错误，并且由于数据和文件不可用导致体验变慢。</span><span class="sxs-lookup"><span data-stu-id="81f56-199">This is necessary to mitigate network latency issues or network glitches, which would otherwise cause application errors and a slow experience due to unavailable data and files.</span></span>

<span data-ttu-id="81f56-200">有各种可用的缓存管理器解决方案。</span><span class="sxs-lookup"><span data-stu-id="81f56-200">There are a variety of caching manager solutions available.</span></span> <span data-ttu-id="81f56-201">例如 [，FSLogix](/fslogix/overview)。</span><span class="sxs-lookup"><span data-stu-id="81f56-201">For example, [FSLogix](/fslogix/overview).</span></span> <span data-ttu-id="81f56-202">有关特定配置说明，请参阅缓存管理器提供程序。</span><span class="sxs-lookup"><span data-stu-id="81f56-202">Consult your caching manager provider for specific configuration instructions.</span></span>

##### <a name="teams-cached-content-exclusion-list-for-non-persistent-setup"></a><span data-ttu-id="81f56-203">Teams持久性设置的缓存内容排除列表</span><span class="sxs-lookup"><span data-stu-id="81f56-203">Teams cached content exclusion list for non-persistent setup</span></span>

<span data-ttu-id="81f56-204">从缓存文件夹 %appdata%/Microsoft/Teams 中排除Teams。</span><span class="sxs-lookup"><span data-stu-id="81f56-204">Exclude the following from the Teams caching folder, %appdata%/Microsoft/Teams.</span></span> <span data-ttu-id="81f56-205">排除这些项有助于减小用户缓存大小，以进一步优化非持久性设置。</span><span class="sxs-lookup"><span data-stu-id="81f56-205">Excluding these items helps reduce the user caching size to further optimize your non-persistent setup.</span></span>

- <span data-ttu-id="81f56-206">.txt文件</span><span class="sxs-lookup"><span data-stu-id="81f56-206">.txt files</span></span>
- <span data-ttu-id="81f56-207">Media-stack 文件夹</span><span class="sxs-lookup"><span data-stu-id="81f56-207">Media-stack folder</span></span>
- <span data-ttu-id="81f56-208">meeting-addin\Cache (%appdata%\Microsoft\Teams\meeting-addin\Cache) </span><span class="sxs-lookup"><span data-stu-id="81f56-208">meeting-addin\Cache (%appdata%\Microsoft\Teams\meeting-addin\Cache)</span></span>

### <a name="microsoft-365-apps-for-enterprise-considerations"></a><span data-ttu-id="81f56-209">Microsoft 365 企业应用版注意事项</span><span class="sxs-lookup"><span data-stu-id="81f56-209">Microsoft 365 Apps for enterprise considerations</span></span>

<span data-ttu-id="81f56-210">在 VDI 上通过 Teams 部署Microsoft 365 企业应用版时，请考虑以下事项。</span><span class="sxs-lookup"><span data-stu-id="81f56-210">Consider the following when you deploy Teams with Microsoft 365 Apps for enterprise on VDI.</span></span>

#### <a name="new-deployments-of-teams-through-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="81f56-211">通过 Teams 部署Microsoft 365 企业应用版</span><span class="sxs-lookup"><span data-stu-id="81f56-211">New deployments of Teams through Microsoft 365 Apps for enterprise</span></span>

<span data-ttu-id="81f56-212">在通过 Teams 部署Microsoft 365 企业应用版，必须先卸载任何预先存在的 Teams 应用（如果它们是使用每台计算机安装部署的）。</span><span class="sxs-lookup"><span data-stu-id="81f56-212">Before you deploy Teams through Microsoft 365 Apps for enterprise, you must first uninstall any pre-existing Teams apps if they were deployed using per-machine installation.</span></span>

<span data-ttu-id="81f56-213">Teams Microsoft 365 企业应用版每个用户安装一次。</span><span class="sxs-lookup"><span data-stu-id="81f56-213">Teams through Microsoft 365 Apps for enterprise is installed per-user.</span></span> <span data-ttu-id="81f56-214">有关详细信息，请参阅在[VDI Teams或更新桌面](#install-or-update-the-teams-desktop-app-on-vdi)应用部分。</span><span class="sxs-lookup"><span data-stu-id="81f56-214">To learn more, see the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.</span></span>

#### <a name="teams-deployments-through-microsoft-365-apps-for-enterprise-updates"></a><span data-ttu-id="81f56-215">Teams更新Microsoft 365 企业应用版部署</span><span class="sxs-lookup"><span data-stu-id="81f56-215">Teams deployments through Microsoft 365 Apps for enterprise updates</span></span>

<span data-ttu-id="81f56-216">Teams添加到现有安装中的 Microsoft 365 企业应用版。</span><span class="sxs-lookup"><span data-stu-id="81f56-216">Teams is also being added to existing installations of Microsoft 365 Apps for enterprise.</span></span> <span data-ttu-id="81f56-217">由于Microsoft 365 企业应用版仅Teams用户安装，请参阅在[VDI Teams桌面应用](#install-or-update-the-teams-desktop-app-on-vdi)部分。</span><span class="sxs-lookup"><span data-stu-id="81f56-217">Since Microsoft 365 Apps for enterprise installs Teams per-user only, see the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.</span></span>

#### <a name="using-teams-with-per-machine-installation-and-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="81f56-218">将Teams与每台计算机的安装和Microsoft 365 企业应用版</span><span class="sxs-lookup"><span data-stu-id="81f56-218">Using Teams with per-machine installation and Microsoft 365 Apps for enterprise</span></span>

<span data-ttu-id="81f56-219">Microsoft 365 企业应用版不支持每台计算机安装 Teams。</span><span class="sxs-lookup"><span data-stu-id="81f56-219">Microsoft 365 Apps for enterprise doesn't support per-machine installations of Teams.</span></span> <span data-ttu-id="81f56-220">若要使用每台计算机安装，必须从Teams排除Microsoft 365 企业应用版。</span><span class="sxs-lookup"><span data-stu-id="81f56-220">To use per-machine installation, you must exclude Teams from Microsoft 365 Apps for enterprise.</span></span> <span data-ttu-id="81f56-221">请参阅[将 Teams 桌面应用部署到 VM](#deploy-the-teams-desktop-app-to-the-vm)和如何Teams[部署Microsoft 365 企业应用版](#how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise)部分。</span><span class="sxs-lookup"><span data-stu-id="81f56-221">See the [Deploy the Teams desktop app to the VM](#deploy-the-teams-desktop-app-to-the-vm) and [How to exclude Teams deployment through Microsoft 365 Apps for enterprise](#how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise) sections.</span></span>

#### <a name="how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="81f56-222">如何排除Teams部署Microsoft 365 企业应用版</span><span class="sxs-lookup"><span data-stu-id="81f56-222">How to exclude Teams deployment through Microsoft 365 Apps for enterprise</span></span>

<span data-ttu-id="81f56-223">若要详细了解 Teams 和 Microsoft 365 企业应用版，请参阅如何从 Microsoft 365 企业应用版 的新安装中排除 Teams[和使用组](/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-office-365-proplus)策略来控制[Teams。](/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams)</span><span class="sxs-lookup"><span data-stu-id="81f56-223">To learn more about Teams and Microsoft 365 Apps for enterprise, see [How to exclude Teams from new installations of Microsoft 365 Apps for enterprise](/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-office-365-proplus) and [Use Group Policy to control the installation of Teams](/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams).</span></span>

### <a name="deploy-the-teams-desktop-app-to-the-vm"></a><span data-ttu-id="81f56-224">将Teams桌面应用部署到 VM</span><span class="sxs-lookup"><span data-stu-id="81f56-224">Deploy the Teams desktop app to the VM</span></span>

1. <span data-ttu-id="81f56-225">使用Teams之一下载与 VDI VM 操作系统匹配的 MSI 包：</span><span class="sxs-lookup"><span data-stu-id="81f56-225">Download the Teams MSI package that matches your VDI VM operating system using one of the following links:</span></span>

    - [<span data-ttu-id="81f56-226">32 位版本</span><span class="sxs-lookup"><span data-stu-id="81f56-226">32-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)
    - [<span data-ttu-id="81f56-227">64 位版本</span><span class="sxs-lookup"><span data-stu-id="81f56-227">64-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)

    > [!NOTE]
    > <span data-ttu-id="81f56-228">对于政府云，请参阅使用[Microsoft Teams 安装](msi-deployment.md)Microsoft Endpoint Configuration Manager，了解 MSI 文件的下载链接。</span><span class="sxs-lookup"><span data-stu-id="81f56-228">For government clouds, see [Install Microsoft Teams using Microsoft Endpoint Configuration Manager](msi-deployment.md) for the download links to the MSI files.</span></span>

    <span data-ttu-id="81f56-229">所需的桌面应用Teams版本为 1.3.00.4461。</span><span class="sxs-lookup"><span data-stu-id="81f56-229">The minimum version of the Teams desktop app that's required is version 1.3.00.4461.</span></span> <span data-ttu-id="81f56-230"> (版本不支持 PSTN 保留。) </span><span class="sxs-lookup"><span data-stu-id="81f56-230">(PSTN hold isn't supported in earlier versions.)</span></span>

2. <span data-ttu-id="81f56-231">运行以下命令之一，将 MSI 安装到 VDI VM：</span><span class="sxs-lookup"><span data-stu-id="81f56-231">Install the MSI to the VDI VM by running one of the following commands:</span></span>

    - <span data-ttu-id="81f56-232">按用户安装 (默认) </span><span class="sxs-lookup"><span data-stu-id="81f56-232">Per-user installation (default)</span></span>
  
        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSERS=1
        ```

        <span data-ttu-id="81f56-233">此过程是默认安装，它Teams %AppData% 用户文件夹。</span><span class="sxs-lookup"><span data-stu-id="81f56-233">This process is the default installation, which installs Teams to the %AppData% user folder.</span></span> <span data-ttu-id="81f56-234">此时，黄金映像设置已完成。</span><span class="sxs-lookup"><span data-stu-id="81f56-234">At this point, the golden image setup is complete.</span></span> <span data-ttu-id="81f56-235">Teams在非永久性设置上无法正常执行按用户安装。</span><span class="sxs-lookup"><span data-stu-id="81f56-235">Teams won't work properly with per-user installation on a non-persistent setup.</span></span>

    - <span data-ttu-id="81f56-236">每台计算机安装</span><span class="sxs-lookup"><span data-stu-id="81f56-236">Per-machine installation</span></span>

        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1 ALLUSERS=1
        ```

        <span data-ttu-id="81f56-237">此过程Teams 64 位操作系统上的 Program Files (x86) 文件夹和 32 位操作系统上的 Program Files 文件夹。</span><span class="sxs-lookup"><span data-stu-id="81f56-237">This process installs Teams to the Program Files (x86) folder on a 64-bit operating system and to the Program Files folder on a 32-bit operating system.</span></span> <span data-ttu-id="81f56-238">此时，黄金映像设置已完成。</span><span class="sxs-lookup"><span data-stu-id="81f56-238">At this point, the golden image setup is complete.</span></span> <span data-ttu-id="81f56-239">非Teams需要每台计算机安装一个服务。</span><span class="sxs-lookup"><span data-stu-id="81f56-239">Installing Teams per-machine is required for non-persistent setups.</span></span>

        <span data-ttu-id="81f56-240">下一个交互式登录会话Teams请求凭据。</span><span class="sxs-lookup"><span data-stu-id="81f56-240">The next interactive logon session starts Teams and asks for credentials.</span></span>

        > [!NOTE]
        > <span data-ttu-id="81f56-241">这些示例还使用 **ALLUSERS=1** 参数。</span><span class="sxs-lookup"><span data-stu-id="81f56-241">These examples also use the **ALLUSERS=1** parameter.</span></span> <span data-ttu-id="81f56-242">设置此参数时，Teams Machine-Wide安装程序会显示在"控制面板"中的"程序和功能"中，&"应用"Windows 设置的"功能"中。</span><span class="sxs-lookup"><span data-stu-id="81f56-242">When you set this parameter, Teams Machine-Wide Installer appears in Programs and Features in Control Panel and in Apps & features in Windows Settings for all users of the computer.</span></span> <span data-ttu-id="81f56-243">然后，所有用户都可以卸载Teams管理员凭据。</span><span class="sxs-lookup"><span data-stu-id="81f56-243">All users can then uninstall Teams if they have admin credentials.</span></span>
        <span data-ttu-id="81f56-244">必须了解 **ALLUSERS=1** 和 **ALLUSER=1 的区别**。</span><span class="sxs-lookup"><span data-stu-id="81f56-244">It's important to understand the difference between **ALLUSERS=1** and **ALLUSER=1**.</span></span> <span data-ttu-id="81f56-245">**ALLUSERS=1** 参数可用于非 VDI 和 VDI 环境，而 **ALLUSER=1** 参数仅在 VDI 环境中用于指定每台计算机安装。</span><span class="sxs-lookup"><span data-stu-id="81f56-245">The **ALLUSERS=1** parameter can be used in non-VDI and VDI environments, while the **ALLUSER=1** parameter is used only in VDI environments to specify a per-machine installation.</span></span>

3. <span data-ttu-id="81f56-246">从 VDI VM 卸载 MSI。</span><span class="sxs-lookup"><span data-stu-id="81f56-246">Uninstall the MSI from the VDI VM.</span></span> <span data-ttu-id="81f56-247">有两种方法可以卸载Teams。</span><span class="sxs-lookup"><span data-stu-id="81f56-247">There are two ways to uninstall Teams.</span></span>

    - <span data-ttu-id="81f56-248">PowerShell 脚本：可以使用此[PowerShell](scripts/powershell-script-deployment-cleanup.md)脚本卸载Teams并Teams用户的文件夹。</span><span class="sxs-lookup"><span data-stu-id="81f56-248">PowerShell script: You can use [this PowerShell script](scripts/powershell-script-deployment-cleanup.md) to uninstall Teams and remove the Teams folder for a user.</span></span> <span data-ttu-id="81f56-249">针对计算机上安装了 Teams的每个用户配置文件运行脚本。</span><span class="sxs-lookup"><span data-stu-id="81f56-249">Run the script for each user profile in which Teams was installed on the computer.</span></span>
    - <span data-ttu-id="81f56-250">命令行：运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="81f56-250">Command line: Run the following command.</span></span>
  
      ```console
      msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>
      ```

      <span data-ttu-id="81f56-251">此过程会卸载Teams文件" (x86) 文件夹或"程序文件"文件夹中，具体取决于操作系统环境。</span><span class="sxs-lookup"><span data-stu-id="81f56-251">This process uninstalls Teams from the Program Files (x86) folder or Program Files folder, depending on the operating system environment.</span></span>

## <a name="teams-on-vdi-performance-considerations"></a><span data-ttu-id="81f56-252">Teams VDI 性能注意事项</span><span class="sxs-lookup"><span data-stu-id="81f56-252">Teams on VDI performance considerations</span></span>

<span data-ttu-id="81f56-253">有各种虚拟化设置配置，每个配置都有不同的优化重点。</span><span class="sxs-lookup"><span data-stu-id="81f56-253">There are a variety of virtualized setup configurations, each with a different focus for optimization.</span></span> <span data-ttu-id="81f56-254">例如，配置可能侧重于用户密度。</span><span class="sxs-lookup"><span data-stu-id="81f56-254">For example, a configuration might focus on user density.</span></span> <span data-ttu-id="81f56-255">规划时，请考虑以下事项，以帮助根据组织的工作负荷需求优化设置。</span><span class="sxs-lookup"><span data-stu-id="81f56-255">When planning, consider the following to help optimize your setup based on your organization's workload needs.</span></span>

- <span data-ttu-id="81f56-256">最低要求：某些工作负荷可能需要使用高于最低要求的资源进行设置。</span><span class="sxs-lookup"><span data-stu-id="81f56-256">Minimum requirement: Some workloads might require a setup using resources that are above the minimum requirements.</span></span> <span data-ttu-id="81f56-257">例如，对于使用需要更多计算资源的应用程序的开发人员的工作负荷。</span><span class="sxs-lookup"><span data-stu-id="81f56-257">For example, workloads for developers who use applications that demand more computing resources.</span></span>
- <span data-ttu-id="81f56-258">依赖项：这些依赖项包括对基础结构、工作负荷的依赖，以及桌面应用Teams环境注意事项。</span><span class="sxs-lookup"><span data-stu-id="81f56-258">Dependencies: These include dependencies on infrastructure, workload, and other environmental considerations outside the Teams desktop app.</span></span>
- <span data-ttu-id="81f56-259">VDI 上的已禁用功能：Teams禁用 VDI 的 GPU 密集型功能，这有助于改善暂时性 CPU 利用率。</span><span class="sxs-lookup"><span data-stu-id="81f56-259">Disabled features on VDI: Teams disables GPU-intensive features for VDI, which can help improve transient CPU utilization.</span></span> <span data-ttu-id="81f56-260">禁用了以下功能：</span><span class="sxs-lookup"><span data-stu-id="81f56-260">The following features are disabled:</span></span>
    - <span data-ttu-id="81f56-261">TeamsCSS 动画</span><span class="sxs-lookup"><span data-stu-id="81f56-261">Teams CSS animation</span></span>
    - <span data-ttu-id="81f56-262">Giphy 自动启动</span><span class="sxs-lookup"><span data-stu-id="81f56-262">Giphy auto-start</span></span>

## <a name="teams-on-vdi-with-calling-and-meetings"></a><span data-ttu-id="81f56-263">Teams呼叫和会议在 VDI 上进行通话</span><span class="sxs-lookup"><span data-stu-id="81f56-263">Teams on VDI with calling and meetings</span></span>

<span data-ttu-id="81f56-264">除了聊天和协作，Teams虚拟化提供商平台提供 VDI 上的呼叫和会议功能。</span><span class="sxs-lookup"><span data-stu-id="81f56-264">In addition to chat and collaboration, Teams on VDI with calling and meetings is available with supported virtualization provider platforms.</span></span> <span data-ttu-id="81f56-265">支持的功能基于 WebRTC 媒体堆栈和虚拟化提供程序实现。</span><span class="sxs-lookup"><span data-stu-id="81f56-265">Supported features are based on the WebRTC media stack and virtualization provider implementation.</span></span> <span data-ttu-id="81f56-266">下图提供了体系结构的概述。</span><span class="sxs-lookup"><span data-stu-id="81f56-266">The following diagram provides an overview of the architecture.</span></span>

![显示 VDI 体系结构Teams的图表](media/teams-on-vdi-architecture.png)

> [!IMPORTANT]
> <span data-ttu-id="81f56-268">如果当前运行 Teams 而不在 VDI 中执行 AV 优化，并且使用尚不支持用于优化的功能 (例如，在应用共享) 时授予并控制，必须设置虚拟化提供程序策略以关闭 Teams 重定向。</span><span class="sxs-lookup"><span data-stu-id="81f56-268">If you currently run Teams without AV optimization in VDI and you use features that are not supported yet for optimization (such as Give and take control when app sharing), you have to set virtualization provider policies to turn off Teams redirection.</span></span> <span data-ttu-id="81f56-269">这意味着Teams不会优化媒体会话。</span><span class="sxs-lookup"><span data-stu-id="81f56-269">This means that Teams media sessions won't be optimized.</span></span> <span data-ttu-id="81f56-270">若要了解如何设置策略以关闭重定向Teams，请与虚拟化提供商联系。</span><span class="sxs-lookup"><span data-stu-id="81f56-270">For steps on how to set policies to turn off Teams redirection, contact your virtualization provider.</span></span>

### <a name="network-requirements"></a><span data-ttu-id="81f56-271">网络要求</span><span class="sxs-lookup"><span data-stu-id="81f56-271">Network requirements</span></span>

<span data-ttu-id="81f56-272">建议评估环境，确定可能影响整体云语音和视频部署的任何风险和要求。</span><span class="sxs-lookup"><span data-stu-id="81f56-272">We recommend that you evaluate your environment to identify any risks and requirements that can influence your overall cloud voice and video deployment.</span></span> <span data-ttu-id="81f56-273">使用[Skype for Business评估工具](https://www.microsoft.com/download/details.aspx?id=53885)测试网络是否已准备好Teams。</span><span class="sxs-lookup"><span data-stu-id="81f56-273">Use the [Skype for Business Network Assessment Tool](https://www.microsoft.com/download/details.aspx?id=53885) to test whether your network is ready for Teams.</span></span>

<span data-ttu-id="81f56-274">若要详细了解如何准备网络Teams，请参阅[准备](prepare-network.md)组织的网络以Teams。</span><span class="sxs-lookup"><span data-stu-id="81f56-274">To learn more about how to prepare your network for Teams, see [Prepare your organization's network for Teams](prepare-network.md).</span></span>

### <a name="migrate-from-skype-for-business-on-vdi-to-teams-on-vdi"></a><span data-ttu-id="81f56-275">从 VDI Skype for Business迁移到 VDI Teams VDI 上的客户端</span><span class="sxs-lookup"><span data-stu-id="81f56-275">Migrate from Skype for Business on VDI to Teams on VDI</span></span>

<span data-ttu-id="81f56-276">如果要从 VDI 上的 Skype for Business 迁移到 VDI 上的 Teams，则除了这两个应用程序之间的差异外，也实现 VDI 时存在一些差异。</span><span class="sxs-lookup"><span data-stu-id="81f56-276">If you're migrating from Skype for Business on VDI to Teams on VDI, besides the differences between the two applications, there are some differences when VDI is also implemented.</span></span> <span data-ttu-id="81f56-277">VDI 中的 Teams VDI 目前不支持Skype for Business如下：</span><span class="sxs-lookup"><span data-stu-id="81f56-277">Some capabilities that aren't currently supported in Teams VDI that are in Skype for Business VDI are as follows:</span></span>

- <span data-ttu-id="81f56-278">在 VDI 中禁用某些 AV 功能的按平台策略</span><span class="sxs-lookup"><span data-stu-id="81f56-278">Per-platform policy to disable some AV features in VDI</span></span>
- <span data-ttu-id="81f56-279">在应用共享时授予并控制</span><span class="sxs-lookup"><span data-stu-id="81f56-279">Give and take control when app sharing</span></span>
- <span data-ttu-id="81f56-280">无音频聊天中的屏幕共享</span><span class="sxs-lookup"><span data-stu-id="81f56-280">Screen share from chat without audio</span></span>
- <span data-ttu-id="81f56-281">同时发送和接收视频和屏幕共享</span><span class="sxs-lookup"><span data-stu-id="81f56-281">Simultaneous video and screen sharing send and receive</span></span>

### <a name="teams-on-chrome-browser-versus-teams-desktop-app-for-vdi"></a><span data-ttu-id="81f56-282">Teams Chrome 浏览器与适用于 VDI Teams桌面应用</span><span class="sxs-lookup"><span data-stu-id="81f56-282">Teams on Chrome browser versus Teams desktop app for VDI</span></span>

<span data-ttu-id="81f56-283">Teams Chrome 浏览器上的应用无法通过 AV 优化Teams VDI 桌面应用。</span><span class="sxs-lookup"><span data-stu-id="81f56-283">Teams on Chrome browser doesn't provide a replacement for the Teams desktop app for VDI with AV optimization.</span></span> <span data-ttu-id="81f56-284">聊天和协作体验如期工作。</span><span class="sxs-lookup"><span data-stu-id="81f56-284">The chat and collaboration experience works as expected.</span></span> <span data-ttu-id="81f56-285">当需要媒体时，某些体验可能无法满足用户在 Chrome 浏览器上的期望：</span><span class="sxs-lookup"><span data-stu-id="81f56-285">When media is needed, there are some experiences that might not meet user expectations on the Chrome browser:</span></span>

- <span data-ttu-id="81f56-286">音频和视频流式处理体验可能并非最佳。</span><span class="sxs-lookup"><span data-stu-id="81f56-286">The audio and video streaming experience might not be optimal.</span></span> <span data-ttu-id="81f56-287">用户可能会遇到延迟或质量降低的情况。</span><span class="sxs-lookup"><span data-stu-id="81f56-287">Users might experiences delays or reduced quality.</span></span>
- <span data-ttu-id="81f56-288">设备设置在浏览器设置中不可用。</span><span class="sxs-lookup"><span data-stu-id="81f56-288">Device settings aren't available in browser settings.</span></span>
- <span data-ttu-id="81f56-289">设备管理通过浏览器进行处理，需要在浏览器网站设置中设置多个设置。</span><span class="sxs-lookup"><span data-stu-id="81f56-289">Device management is handled through the browser and requires multiple settings in browser site settings.</span></span>
- <span data-ttu-id="81f56-290">设备设置可能还需要在设备管理Windows设置。</span><span class="sxs-lookup"><span data-stu-id="81f56-290">Device settings might also need to be set in Windows device management.</span></span>

## <a name="teams-on-vdi-with-chat-and-collaboration"></a><span data-ttu-id="81f56-291">Teams聊天和协作在 VDI 上聊天</span><span class="sxs-lookup"><span data-stu-id="81f56-291">Teams on VDI with chat and collaboration</span></span>

<span data-ttu-id="81f56-292">如果你的组织只想在 Teams 使用聊天和协作功能，你可以设置用户级策略以在 Teams 中关闭呼叫和Teams。</span><span class="sxs-lookup"><span data-stu-id="81f56-292">If your organization wants to only use chat and collaboration features in Teams, you can set user-level policies to turn off calling and meeting functionality in Teams.</span></span> 

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a><span data-ttu-id="81f56-293">设置策略以关闭呼叫和会议功能</span><span class="sxs-lookup"><span data-stu-id="81f56-293">Set policies to turn off calling and meeting functionality</span></span>

<span data-ttu-id="81f56-294">可以使用管理中心或 PowerShell Microsoft Teams策略。</span><span class="sxs-lookup"><span data-stu-id="81f56-294">You can set policies by using the Microsoft Teams admin center or PowerShell.</span></span> <span data-ttu-id="81f56-295">传播策略更改 (可能需要) 几个小时。</span><span class="sxs-lookup"><span data-stu-id="81f56-295">It might take some time (a few hours) for the policy changes to propagate.</span></span> <span data-ttu-id="81f56-296">如果未立即看到给定帐户的更改，请在几小时后重试。</span><span class="sxs-lookup"><span data-stu-id="81f56-296">If you don't see changes for a given account immediately, try again in a few hours.</span></span>

<span data-ttu-id="81f56-297">[**调用策略**](teams-calling-policy.md)：Teams包括内置的 DisallowCalling 调用策略，其中所有调用功能都已关闭。</span><span class="sxs-lookup"><span data-stu-id="81f56-297">[**Calling polices**](teams-calling-policy.md): Teams includes the built-in DisallowCalling calling policy, in which all calling features are turned off.</span></span> <span data-ttu-id="81f56-298">将 DisallowCalling 策略分配给组织中在虚拟化环境中Teams的所有用户。</span><span class="sxs-lookup"><span data-stu-id="81f56-298">Assign the DisallowCalling policy to all users in your organization who use Teams in a virtualized environment.</span></span>

<span data-ttu-id="81f56-299">[**会议策略**](meeting-policies-in-teams.md)：Teams包括内置的 AllOff 会议策略，其中所有会议功能都已关闭。</span><span class="sxs-lookup"><span data-stu-id="81f56-299">[**Meeting policies**](meeting-policies-in-teams.md): Teams includes the built-in AllOff meeting policy, in which all meeting features are turned off.</span></span> <span data-ttu-id="81f56-300">将 AllOff 策略分配给组织中在虚拟化环境中Teams用户。</span><span class="sxs-lookup"><span data-stu-id="81f56-300">Assign the AllOff policy to all users in your organization who use Teams in a virtualized environment.</span></span>

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a><span data-ttu-id="81f56-301">使用管理中心Microsoft Teams策略</span><span class="sxs-lookup"><span data-stu-id="81f56-301">Assign policies using the Microsoft Teams admin center</span></span>

<span data-ttu-id="81f56-302">将 DisallowCalling 调用策略和 AllOff 会议策略分配给用户：</span><span class="sxs-lookup"><span data-stu-id="81f56-302">To assign the DisallowCalling calling policy and the AllOff meeting policy to a user:</span></span>

1. <span data-ttu-id="81f56-303">在管理中心左侧导航Microsoft Teams，转到"用户 **"。**</span><span class="sxs-lookup"><span data-stu-id="81f56-303">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="81f56-304">单击用户名的左侧以选择用户，然后单击“编辑设置”。</span><span class="sxs-lookup"><span data-stu-id="81f56-304">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="81f56-305">执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="81f56-305">Do the following:</span></span>
    1.  <span data-ttu-id="81f56-306">在 **"调用策略"** 下，**单击"禁止""缩放"。**</span><span class="sxs-lookup"><span data-stu-id="81f56-306">Under **Calling policy**, click **DisallowCalling**.</span></span>
    2.  <span data-ttu-id="81f56-307">在"**会议策略"** 下，单击 **"AllOff"。**</span><span class="sxs-lookup"><span data-stu-id="81f56-307">Under **Meeting policy**, click **AllOff**.</span></span>
4. <span data-ttu-id="81f56-308">单击“**应用**”。</span><span class="sxs-lookup"><span data-stu-id="81f56-308">Click **Apply**.</span></span>

<span data-ttu-id="81f56-309">若要一次向多个用户分配策略，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="81f56-309">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="81f56-310">在 Microsoft Teams 管理中心的左侧导航栏中，转到“**用户**”，然后搜索用户或筛选视图，以显示所需的用户。</span><span class="sxs-lookup"><span data-stu-id="81f56-310">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="81f56-311">在 **&#x2713;**（复选标记）列，选择用户。</span><span class="sxs-lookup"><span data-stu-id="81f56-311">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="81f56-312">若要选择所有用户，请单击表格顶部的 &#x2713;（复选标记）。</span><span class="sxs-lookup"><span data-stu-id="81f56-312">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="81f56-313">单击“**编辑设置**”，执行所需的更改，然后单击“**应用**”。</span><span class="sxs-lookup"><span data-stu-id="81f56-313">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>

<span data-ttu-id="81f56-314">或者，也可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="81f56-314">Or, you can also do the following:</span></span>

1. <span data-ttu-id="81f56-315">在管理中心Microsoft Teams导航中，转到要分配的策略。</span><span class="sxs-lookup"><span data-stu-id="81f56-315">In the left navigation of the Microsoft Teams admin center, go to the policy you want to assign.</span></span> <span data-ttu-id="81f56-316">例如：</span><span class="sxs-lookup"><span data-stu-id="81f56-316">For example:</span></span>
    - <span data-ttu-id="81f56-317">转到 **"语音**  >  **呼叫策略"，** 然后单击"**取消允许""呼叫"。**</span><span class="sxs-lookup"><span data-stu-id="81f56-317">Go to **Voice** > **Calling policies**, and then click **DisallowCalling**.</span></span>
    - <span data-ttu-id="81f56-318">转到"**会议**  >  **会议策略"，** 然后单击 **"AllOff"。**</span><span class="sxs-lookup"><span data-stu-id="81f56-318">Go to **Meetings** > **Meeting policies**, and then click **AllOff**.</span></span>
2. <span data-ttu-id="81f56-319">选择“管理用户”。</span><span class="sxs-lookup"><span data-stu-id="81f56-319">Select **Manage users**.</span></span>
3. <span data-ttu-id="81f56-320">在“管理用户”窗格中，按显示名称或用户名搜索用户，选择用户名，然后单击“添加”。</span><span class="sxs-lookup"><span data-stu-id="81f56-320">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="81f56-321">对想要添加的每一个用户重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="81f56-321">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="81f56-322">添加完用户后，单击"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="81f56-322">When you're finished adding users, click **Save**.</span></span>

#### <a name="assign-policies-using-powershell"></a><span data-ttu-id="81f56-323">使用 PowerShell 分配策略</span><span class="sxs-lookup"><span data-stu-id="81f56-323">Assign policies using PowerShell</span></span>

<span data-ttu-id="81f56-324">以下示例演示如何使用 [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) 将 DisallowCalling 调用策略分配给用户。</span><span class="sxs-lookup"><span data-stu-id="81f56-324">The following example shows how to use the [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) to assign the DisallowCalling calling policy to a user.</span></span>

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

<span data-ttu-id="81f56-325">若要详细了解使用 PowerShell 管理调用策略，请参阅[Set-CsTeamsCallingPolicy。](/powershell/module/skype/set-csteamscallingpolicy)</span><span class="sxs-lookup"><span data-stu-id="81f56-325">To learn more about using PowerShell to manage calling policies, see [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy).</span></span>

<span data-ttu-id="81f56-326">以下示例演示如何使用 [Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) 将 AllOff 会议策略分配给用户。</span><span class="sxs-lookup"><span data-stu-id="81f56-326">The following example shows how to use the [Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) to assign the AllOff meeting policy to a user.</span></span>

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

<span data-ttu-id="81f56-327">若要详细了解使用 PowerShell 管理会议策略，请参阅[Set-CsTeamsMeetingPolicy。](/powershell/module/skype/set-csteamsmeetingpolicy)</span><span class="sxs-lookup"><span data-stu-id="81f56-327">To learn more about using PowerShell to manage meeting policies, see [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy).</span></span>

## <a name="migrate-teams-on-vdi-with-chat-and-collaboration-to-optimize-teams-with-calling-and-meetings"></a><span data-ttu-id="81f56-328">通过Teams和协作在 VDI 上迁移 Teams，以优化呼叫和会议功能</span><span class="sxs-lookup"><span data-stu-id="81f56-328">Migrate Teams on VDI with chat and collaboration to optimize Teams with calling and meetings</span></span>

<span data-ttu-id="81f56-329">如果 VDI 上的 Teams 与聊天和协作的现有实现已设置用户级策略以关闭呼叫和会议功能，并且要迁移到具有 AV 优化的 Teams，则必须设置策略，为 VDI 用户启用这些 Teams 的呼叫和会议功能。</span><span class="sxs-lookup"><span data-stu-id="81f56-329">If you have an existing implementation of Teams on VDI with chat and collaboration in which you had set user-level policies to turn off calling and meeting functionality, and you're migrating to Teams with AV optimization, you must set policies to turn on calling and meeting functionality for those Teams on VDI users.</span></span>

### <a name="set-policies-to-turn-on-calling-and-meeting-functionality"></a><span data-ttu-id="81f56-330">设置策略以打开呼叫和会议功能</span><span class="sxs-lookup"><span data-stu-id="81f56-330">Set policies to turn on calling and meeting functionality</span></span>

<span data-ttu-id="81f56-331">可以使用 Microsoft Teams 管理中心或 PowerShell 来设置呼叫和会议策略并将其分配给用户。</span><span class="sxs-lookup"><span data-stu-id="81f56-331">You can use the Microsoft Teams admin center or PowerShell to set and assign calling and meeting policies to your users.</span></span> <span data-ttu-id="81f56-332">传播策略更改 (可能需要) 几个小时。</span><span class="sxs-lookup"><span data-stu-id="81f56-332">It can take some time (a few hours) for policy changes to propagate.</span></span> <span data-ttu-id="81f56-333">如果未立即看到给定帐户的更改，请在几小时后重试。</span><span class="sxs-lookup"><span data-stu-id="81f56-333">If you don't see changes for a given account immediately, try again after a few hours.</span></span>

<span data-ttu-id="81f56-334">[**调用策略**](teams-calling-policy.md)：调用策略Teams控制哪些调用功能可供用户使用。</span><span class="sxs-lookup"><span data-stu-id="81f56-334">[**Calling polices**](teams-calling-policy.md): Calling policies in Teams control which calling features are available to users.</span></span> <span data-ttu-id="81f56-335">Teams包括内置的 AllowCalling 调用策略，其中所有调用功能都打开。</span><span class="sxs-lookup"><span data-stu-id="81f56-335">Teams includes the built-in AllowCalling calling policy, in which all calling features are turned on.</span></span> <span data-ttu-id="81f56-336">若要启用所有调用功能，请分配 AllowCalling 策略。</span><span class="sxs-lookup"><span data-stu-id="81f56-336">To turn on all calling features, assign the AllowCalling policy.</span></span> <span data-ttu-id="81f56-337">或者，创建自定义呼叫策略以打开你需要的呼叫功能并将其分配给用户。</span><span class="sxs-lookup"><span data-stu-id="81f56-337">Or, create a custom calling policy to turn on the calling features that you want and assign it to users.</span></span> 

<span data-ttu-id="81f56-338">[**会议策略**](meeting-policies-in-teams.md)：会议Teams控制用户可以创建的会议类型，以及组织中用户安排的会议参与者可用的功能。</span><span class="sxs-lookup"><span data-stu-id="81f56-338">[**Meeting policies**](meeting-policies-in-teams.md): Meeting policies in Teams control the types of meetings that users can create and the features that are available to meeting participants that are scheduled by users in your organization.</span></span> <span data-ttu-id="81f56-339">Teams包括内置的 AllOn 会议策略，其中所有会议功能都打开。</span><span class="sxs-lookup"><span data-stu-id="81f56-339">Teams includes the built-in AllOn meeting policy, in which all meeting features are turned on.</span></span> <span data-ttu-id="81f56-340">若要启用所有会议功能，请分配 AllOn 策略。</span><span class="sxs-lookup"><span data-stu-id="81f56-340">To turn on all meeting features, assign the AllOn policy.</span></span> <span data-ttu-id="81f56-341">或者，创建自定义会议策略以打开你需要的会议功能并为其分配用户。</span><span class="sxs-lookup"><span data-stu-id="81f56-341">Or, create a custom meeting policy to turn on the meeting features that you want and assign it users.</span></span>

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a><span data-ttu-id="81f56-342">使用管理中心Microsoft Teams策略</span><span class="sxs-lookup"><span data-stu-id="81f56-342">Assign policies using the Microsoft Teams admin center</span></span>

<span data-ttu-id="81f56-343">若要向用户分配 AllowCalling 调用策略和 AllOn 会议策略，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="81f56-343">To assign the AllowCalling calling policy and the AllOn meeting policy to a user:</span></span>

1. <span data-ttu-id="81f56-344">在管理中心左侧导航Microsoft Teams，转到"用户 **"。**</span><span class="sxs-lookup"><span data-stu-id="81f56-344">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="81f56-345">单击用户名的左侧以选择用户，然后单击“编辑设置”。</span><span class="sxs-lookup"><span data-stu-id="81f56-345">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="81f56-346">执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="81f56-346">Do the following:</span></span>
    1.  <span data-ttu-id="81f56-347">在 **"调用策略"** 下，单击 **"AllowCalling"。**</span><span class="sxs-lookup"><span data-stu-id="81f56-347">Under **Calling policy**, click **AllowCalling**.</span></span>
    2.  <span data-ttu-id="81f56-348">在"**会议策略"** 下，单击 **"AllOn"。**</span><span class="sxs-lookup"><span data-stu-id="81f56-348">Under **Meeting policy**, click **AllOn**.</span></span>
4. <span data-ttu-id="81f56-349">单击“**应用**”。</span><span class="sxs-lookup"><span data-stu-id="81f56-349">Click **Apply**.</span></span>

<span data-ttu-id="81f56-350">若要一次向多个用户分配策略，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="81f56-350">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="81f56-351">在 Microsoft Teams 管理中心的左侧导航栏中，转到“**用户**”，然后搜索用户或筛选视图，以显示所需的用户。</span><span class="sxs-lookup"><span data-stu-id="81f56-351">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="81f56-352">在 **&#x2713;**（复选标记）列，选择用户。</span><span class="sxs-lookup"><span data-stu-id="81f56-352">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="81f56-353">若要选择所有用户， **请单击&#x2713;(** 表) "复选框。</span><span class="sxs-lookup"><span data-stu-id="81f56-353">To select all users, click the **&#x2713;** (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="81f56-354">单击“**编辑设置**”，执行所需的更改，然后单击“**应用**”。</span><span class="sxs-lookup"><span data-stu-id="81f56-354">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>

<span data-ttu-id="81f56-355">或者，也可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="81f56-355">Or, you can also do the following:</span></span>

1. <span data-ttu-id="81f56-356">在管理中心Microsoft Teams导航中，转到要分配的策略。</span><span class="sxs-lookup"><span data-stu-id="81f56-356">In the left navigation of the Microsoft Teams admin center, go to the policy you want to assign.</span></span> <span data-ttu-id="81f56-357">例如：</span><span class="sxs-lookup"><span data-stu-id="81f56-357">For example:</span></span>
    - <span data-ttu-id="81f56-358">转到"**语音**  >  **呼叫策略"，** 然后单击 **"AllowCalling"。**</span><span class="sxs-lookup"><span data-stu-id="81f56-358">Go to **Voice** > **Calling policies**, and then click **AllowCalling**.</span></span>
    - <span data-ttu-id="81f56-359">转到"**会议**  >  **会议策略"，** 然后单击 **"AllOn"。**</span><span class="sxs-lookup"><span data-stu-id="81f56-359">Go to **Meetings** > **Meeting policies**, and then click **AllOn**.</span></span>
2. <span data-ttu-id="81f56-360">选择“管理用户”。</span><span class="sxs-lookup"><span data-stu-id="81f56-360">Select **Manage users**.</span></span>
3. <span data-ttu-id="81f56-361">在“管理用户”窗格中，按显示名称或用户名搜索用户，选择用户名，然后单击“添加”。</span><span class="sxs-lookup"><span data-stu-id="81f56-361">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="81f56-362">对想要添加的每一个用户重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="81f56-362">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="81f56-363">添加完用户后，单击"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="81f56-363">When you're finished adding users, click **Save**.</span></span>

#### <a name="assign-policies-using-powershell"></a><span data-ttu-id="81f56-364">使用 PowerShell 分配策略</span><span class="sxs-lookup"><span data-stu-id="81f56-364">Assign policies using PowerShell</span></span>

<span data-ttu-id="81f56-365">以下示例演示如何使用 [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) 将 AllowCalling 调用策略分配给用户。</span><span class="sxs-lookup"><span data-stu-id="81f56-365">The following example shows how to use the [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) to assign the AllowCalling calling policy to a user.</span></span>

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName AllowCalling -Identity "user email id"
```

<span data-ttu-id="81f56-366">若要详细了解使用 PowerShell 管理调用策略，请参阅[Set-CsTeamsCallingPolicy。](/powershell/module/skype/set-csteamscallingpolicy)</span><span class="sxs-lookup"><span data-stu-id="81f56-366">To learn more about using PowerShell to manage calling policies, see [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy).</span></span>

<span data-ttu-id="81f56-367">以下示例演示如何使用 [Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) 将 AllOn 会议策略分配给用户。</span><span class="sxs-lookup"><span data-stu-id="81f56-367">The following example shows how to use the [Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) to assign the AllOn meeting policy to a user.</span></span>

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOn -Identity "user email id"
```

<span data-ttu-id="81f56-368">若要详细了解使用 PowerShell 管理会议策略，请参阅[Set-CsTeamsMeetingPolicy。](/powershell/module/skype/set-csteamsmeetingpolicy)</span><span class="sxs-lookup"><span data-stu-id="81f56-368">To learn more about using PowerShell to manage meeting policies, see [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy).</span></span>

## <a name="control-fallback-mode-in-teams"></a><span data-ttu-id="81f56-369">在控件中控制回退Teams</span><span class="sxs-lookup"><span data-stu-id="81f56-369">Control fallback mode in Teams</span></span>

<span data-ttu-id="81f56-370">当用户从不受支持的终结点进行连接时，用户会进入回退模式，其中 AV 未优化。</span><span class="sxs-lookup"><span data-stu-id="81f56-370">When users connect from an unsupported endpoint, the users are in fallback mode, in which AV isn't optimized.</span></span> <span data-ttu-id="81f56-371">可以通过设置以下注册表 DWORD 值之一来禁用或启用回退模式：</span><span class="sxs-lookup"><span data-stu-id="81f56-371">You can disable or enable fallback mode by setting one of the following registry DWORD values:</span></span>

- <span data-ttu-id="81f56-372">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Teams\DisableFallback</span><span class="sxs-lookup"><span data-stu-id="81f56-372">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Teams\DisableFallback</span></span>
- <span data-ttu-id="81f56-373">HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\Teams\DisableFallback</span><span class="sxs-lookup"><span data-stu-id="81f56-373">HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\Teams\DisableFallback</span></span>

<span data-ttu-id="81f56-374">若要禁用回退模式，将值设置为 **1。**</span><span class="sxs-lookup"><span data-stu-id="81f56-374">To disable fallback mode, set the value to **1**.</span></span> <span data-ttu-id="81f56-375">若要仅启用音频，将值设置为 **2。**</span><span class="sxs-lookup"><span data-stu-id="81f56-375">To enable audio only, set the value to **2**.</span></span> <span data-ttu-id="81f56-376">如果该值不存在或设置为 **0** (零) ，则启用回退模式。</span><span class="sxs-lookup"><span data-stu-id="81f56-376">If the value isn't present or is set to **0** (zero), fallback mode is enabled.</span></span>

<span data-ttu-id="81f56-377">此功能在 Teams 1.3.00.13565 及更高版本中可用。</span><span class="sxs-lookup"><span data-stu-id="81f56-377">This feature is available in Teams version 1.3.00.13565 and later.</span></span>

## <a name="known-issues-and-limitations"></a><span data-ttu-id="81f56-378">已知问题和限制</span><span class="sxs-lookup"><span data-stu-id="81f56-378">Known issues and limitations</span></span>

### <a name="client-deployment-installation-and-setup"></a><span data-ttu-id="81f56-379">客户端部署、安装和设置</span><span class="sxs-lookup"><span data-stu-id="81f56-379">Client deployment, installation, and setup</span></span>

- <span data-ttu-id="81f56-380">通过每台计算机安装，Teams VDI 上的配置不会以非 VDI 客户端Teams的方式自动更新。</span><span class="sxs-lookup"><span data-stu-id="81f56-380">With per-machine installation, Teams on VDI isn't automatically updated in the way that non-VDI Teams clients are.</span></span> <span data-ttu-id="81f56-381">必须安装新的 MSI 来更新 VM 映像，如在 VDI 上安装或Teams[桌面应用](#install-or-update-the-teams-desktop-app-on-vdi)部分中所述。</span><span class="sxs-lookup"><span data-stu-id="81f56-381">You have to update the VM image by installing a new MSI as described in the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.</span></span> <span data-ttu-id="81f56-382">必须卸载当前版本，以更新到较新版本。</span><span class="sxs-lookup"><span data-stu-id="81f56-382">You must uninstall the current version to update to a newer version.</span></span>
- <span data-ttu-id="81f56-383">在 Citrix 环境中，如果用户在运行 Teams 时与虚拟机断开连接，Teams 更新可能会导致用户在重新连接时为 AV 保持未优化状态。</span><span class="sxs-lookup"><span data-stu-id="81f56-383">In Citrix environments, if the user disconnects from the Virtual Machine while Teams is running, Teams updates can result in the user to be in a non-optimized state for AV when they reconnect.</span></span> <span data-ttu-id="81f56-384">建议用户在从 Citrix 虚拟机Teams之前退出配置，以避免这种情况。</span><span class="sxs-lookup"><span data-stu-id="81f56-384">We recommend that users quit Teams before they disconnect from Citrix Virtual Machine to avoid this scenario.</span></span>
- <span data-ttu-id="81f56-385">Teams用户或每台计算机部署资源。</span><span class="sxs-lookup"><span data-stu-id="81f56-385">Teams should be deployed either per user or per machine.</span></span> <span data-ttu-id="81f56-386">不支持Teams每个用户和每台计算机的并发数进行部署。</span><span class="sxs-lookup"><span data-stu-id="81f56-386">Deployment of Teams for concurrent per user and per machine is not supported.</span></span> <span data-ttu-id="81f56-387">若要从每台计算机或每个用户迁移到其中一种模式，请按照卸载过程操作并重新部署到任一模式。</span><span class="sxs-lookup"><span data-stu-id="81f56-387">To migrate from either per machine or per user to one of these modes, follow the uninstall procedure and redeploy to either mode.</span></span>
- <span data-ttu-id="81f56-388">Windows虚拟桌面目前不支持基于 macOS 和 Linux 的客户端。</span><span class="sxs-lookup"><span data-stu-id="81f56-388">Windows Virtual Desktop doesn't support macOS and Linux-based clients at this time.</span></span>

### <a name="calling-and-meetings"></a><span data-ttu-id="81f56-389">呼叫和会议</span><span class="sxs-lookup"><span data-stu-id="81f56-389">Calling and meetings</span></span>

<span data-ttu-id="81f56-390">不支持以下呼叫和会议功能：</span><span class="sxs-lookup"><span data-stu-id="81f56-390">The following calling and meeting features are not supported:</span></span>

- <span data-ttu-id="81f56-391">任何多窗口功能（如新会议体验）或新会议体验附带的任何功能</span><span class="sxs-lookup"><span data-stu-id="81f56-391">Any multi-window functionality like the new meeting experiences or any functionality that comes with the new meeting experience</span></span>
- <span data-ttu-id="81f56-392">增强型紧急服务</span><span class="sxs-lookup"><span data-stu-id="81f56-392">Enhanced emergency services</span></span>
- <span data-ttu-id="81f56-393">应用和设备之间的 HID 按钮Teams LED 控件</span><span class="sxs-lookup"><span data-stu-id="81f56-393">HID buttons and LED controls between the Teams app and devices</span></span>
- <span data-ttu-id="81f56-394">背景模糊和效果</span><span class="sxs-lookup"><span data-stu-id="81f56-394">Background blur and effects</span></span>
- <span data-ttu-id="81f56-395">广播和实时事件制作者和演示者角色</span><span class="sxs-lookup"><span data-stu-id="81f56-395">Broadcast and live event producer and presenter roles</span></span>
- <span data-ttu-id="81f56-396">Location-Based LBR (路由) </span><span class="sxs-lookup"><span data-stu-id="81f56-396">Location-Based Routing (LBR)</span></span>
- <span data-ttu-id="81f56-397">呼叫寄存</span><span class="sxs-lookup"><span data-stu-id="81f56-397">Call park</span></span>
- <span data-ttu-id="81f56-398">共享系统音频/计算机声音</span><span class="sxs-lookup"><span data-stu-id="81f56-398">Shared system audio/computer sound</span></span>
- <span data-ttu-id="81f56-399">直接路由的媒体旁路</span><span class="sxs-lookup"><span data-stu-id="81f56-399">Media bypass for Direct Routing</span></span>
- <span data-ttu-id="81f56-400">缩放控件</span><span class="sxs-lookup"><span data-stu-id="81f56-400">Zoom control</span></span> 

> [!NOTE]
> <span data-ttu-id="81f56-401">我们正在努力添加当前仅在非 VDI 环境中可用的呼叫和会议功能。</span><span class="sxs-lookup"><span data-stu-id="81f56-401">We're working on adding calling and meeting features that are currently only available in non-VDI environments.</span></span> <span data-ttu-id="81f56-402">这些可能包括对质量的更多管理员控制、其他屏幕共享方案和最近添加到 Teams。</span><span class="sxs-lookup"><span data-stu-id="81f56-402">These might include more admin control over quality, additional screen sharing scenarios, and advanced features recently added to Teams.</span></span> <span data-ttu-id="81f56-403">请联系Teams代表，详细了解即将推出的功能。</span><span class="sxs-lookup"><span data-stu-id="81f56-403">Contact your Teams representative to learn more about upcoming features.</span></span>

<span data-ttu-id="81f56-404">以下是呼叫和会议的已知问题和限制：</span><span class="sxs-lookup"><span data-stu-id="81f56-404">The following are known issues and limitations for calling and meetings:</span></span>

- <span data-ttu-id="81f56-405">与音频Skype for Business仅限音频呼叫;没有视频形式。</span><span class="sxs-lookup"><span data-stu-id="81f56-405">Interoperability with Skype for Business is limited to audio calls; there is no video modality.</span></span>
- <span data-ttu-id="81f56-406">传入和传出视频流分辨率限制为 720p 分辨率。</span><span class="sxs-lookup"><span data-stu-id="81f56-406">Incoming and outgoing video stream resolution is limited to 720p resolution.</span></span>
- <span data-ttu-id="81f56-407">仅支持来自传入相机或屏幕共享流的一个视频流。</span><span class="sxs-lookup"><span data-stu-id="81f56-407">Only one video stream from an incoming camera or screen share stream is supported.</span></span> <span data-ttu-id="81f56-408">当存在传入的屏幕共享时，将显示该屏幕共享，而不是主扬声器的视频。</span><span class="sxs-lookup"><span data-stu-id="81f56-408">When there's an incoming screen share, that screen share is shown, instead of the video of the dominant speaker.</span></span>
- <span data-ttu-id="81f56-409">Teams用户选择的最后一个音频设备（如果设备已断开连接，然后重新连接）不切换到使用。</span><span class="sxs-lookup"><span data-stu-id="81f56-409">Teams doesn't switch to use the last audio device that a user selected, if the device is disconnected, and then reconnected.</span></span>
- <span data-ttu-id="81f56-410">传出屏幕共享：</span><span class="sxs-lookup"><span data-stu-id="81f56-410">Outgoing screen sharing:</span></span>
    - <span data-ttu-id="81f56-411">不支持应用程序共享。</span><span class="sxs-lookup"><span data-stu-id="81f56-411">Application sharing is not supported.</span></span>
- <span data-ttu-id="81f56-412">授予控制权并控制：</span><span class="sxs-lookup"><span data-stu-id="81f56-412">Give control and take control:</span></span>
    - <span data-ttu-id="81f56-413">在屏幕共享或应用程序共享会话期间不受支持。</span><span class="sxs-lookup"><span data-stu-id="81f56-413">Not supported during a screen sharing or application sharing session.</span></span>
    - <span data-ttu-id="81f56-414">在共享会话PowerPoint支持。</span><span class="sxs-lookup"><span data-stu-id="81f56-414">Supported during a PowerPoint sharing session.</span></span>
- <span data-ttu-id="81f56-415">仅 Citrix 限制</span><span class="sxs-lookup"><span data-stu-id="81f56-415">Citrix-only limitations</span></span>
    - <span data-ttu-id="81f56-416">在多监视器设置中共享屏幕时，仅共享主监视器。</span><span class="sxs-lookup"><span data-stu-id="81f56-416">When screen sharing in a multi-monitor setup, only the main monitor is shared.</span></span>
    - <span data-ttu-id="81f56-417">不支持在 CWA 上高 DPI 缩放。</span><span class="sxs-lookup"><span data-stu-id="81f56-417">High DPI scaling on CWA is not supported.</span></span>

<span data-ttu-id="81f56-418">有关Teams VDI 的已知问题，请参阅[在Teams支持。](/MicrosoftTeams/troubleshoot/teams-welcome)</span><span class="sxs-lookup"><span data-stu-id="81f56-418">For Teams known issues that aren't related to VDI, see [Support Teams in your organization](/MicrosoftTeams/troubleshoot/teams-welcome).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="81f56-419">疑难解答</span><span class="sxs-lookup"><span data-stu-id="81f56-419">Troubleshooting</span></span>

### <a name="troubleshoot-citrix-components"></a><span data-ttu-id="81f56-420">Citrix 组件故障排除</span><span class="sxs-lookup"><span data-stu-id="81f56-420">Troubleshoot Citrix components</span></span>

#### <a name="teams-crashes-or-the-teams-sign-in-screen-is-blank"></a><span data-ttu-id="81f56-421">Teams崩溃或Teams登录屏幕为空</span><span class="sxs-lookup"><span data-stu-id="81f56-421">Teams crashes or the Teams sign in screen is blank</span></span>

<span data-ttu-id="81f56-422">这是 Citrix VDA 版本 1906 和 1909 的已知问题。</span><span class="sxs-lookup"><span data-stu-id="81f56-422">This is a known issue with Citrix VDA versions 1906 and 1909.</span></span> <span data-ttu-id="81f56-423">若要解决此问题，请添加以下注册表 DWORD 值，将其设置为 204 (十六进制) 。</span><span class="sxs-lookup"><span data-stu-id="81f56-423">To work around this issue, add the following registry DWORD value, and set it to 204 (hexadecimal).</span></span>

<span data-ttu-id="81f56-424">HKEY_LOCAL_MACHINE\SOFTWARE\Citrix\CtxHook\AppInit_Dlls\SfrHook\Teams.exe</span><span class="sxs-lookup"><span data-stu-id="81f56-424">HKEY_LOCAL_MACHINE\SOFTWARE\Citrix\CtxHook\AppInit_Dlls\SfrHook\Teams.exe</span></span>

<span data-ttu-id="81f56-425">然后重启 VDA。</span><span class="sxs-lookup"><span data-stu-id="81f56-425">Then, restart VDA.</span></span> <span data-ttu-id="81f56-426">若要了解有关详细信息，请参阅此 Citrix 支持文章排查针对 Teams[的 HDX 优化](https://support.citrix.com/article/CTX253754)问题。</span><span class="sxs-lookup"><span data-stu-id="81f56-426">To learn more, see this Citrix support article, [Troubleshooting HDX optimization for Teams](https://support.citrix.com/article/CTX253754).</span></span>

## <a name="related-topics"></a><span data-ttu-id="81f56-427">相关主题</span><span class="sxs-lookup"><span data-stu-id="81f56-427">Related topics</span></span>

- [<span data-ttu-id="81f56-428">使用 MSI Microsoft Teams安装</span><span class="sxs-lookup"><span data-stu-id="81f56-428">Install Microsoft Teams using MSI</span></span>](msi-deployment.md)
- [<span data-ttu-id="81f56-429">Teams PowerShell 概览</span><span class="sxs-lookup"><span data-stu-id="81f56-429">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="81f56-430">在 Microsoft Teams 虚拟Windows上使用</span><span class="sxs-lookup"><span data-stu-id="81f56-430">Use Microsoft Teams on Windows Virtual desktop</span></span>](/azure/virtual-desktop/teams-on-wvd)
