---
title: 适用于虚拟化桌面基础结构的 Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rafarhi, jmorrow
audience: admin
description: 了解如何在 VDI 虚拟桌面基础结构和 VDI (中) Microsoft Teams。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: b7262cc77310a9ea198a51af720e6e5117a72111
ms.sourcegitcommit: 4e1f5d99c1d0612dc5b50f850280983867ff53d8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2021
ms.locfileid: "51874468"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a><span data-ttu-id="d4368-103">适用于虚拟化桌面基础结构的 Teams</span><span class="sxs-lookup"><span data-stu-id="d4368-103">Teams for Virtualized Desktop Infrastructure</span></span>

<span data-ttu-id="d4368-104">本文介绍在虚拟化环境中使用 Microsoft Teams 的要求和限制。</span><span class="sxs-lookup"><span data-stu-id="d4368-104">This article describes the requirements and limitations for using Microsoft Teams in a virtualized environment.</span></span>

## <a name="what-is-vdi"></a><span data-ttu-id="d4368-105">什么是 VDI？</span><span class="sxs-lookup"><span data-stu-id="d4368-105">What is VDI?</span></span>

<span data-ttu-id="d4368-106">虚拟桌面基础结构 (VDI) 是一种虚拟化技术，在数据中心的集中服务器上托管桌面操作系统和应用程序。</span><span class="sxs-lookup"><span data-stu-id="d4368-106">Virtual Desktop Infrastructure (VDI) is virtualization technology that hosts a desktop operating system and applications on a centralized server in a data center.</span></span> <span data-ttu-id="d4368-107">这使具有完全安全且合规的集中源的用户能够获得完全个性化的桌面体验。</span><span class="sxs-lookup"><span data-stu-id="d4368-107">This enables a fully personalized desktop experience to users with a fully secured and compliant centralized source.</span></span>

<span data-ttu-id="d4368-108">虚拟化环境中 Microsoft Teams 支持聊天和协作。</span><span class="sxs-lookup"><span data-stu-id="d4368-108">Microsoft Teams in a virtualized environment supports chat and collaboration.</span></span> <span data-ttu-id="d4368-109">此外，通过 Windows 虚拟桌面、Citrix 和 VMware 平台，也支持呼叫和会议功能。</span><span class="sxs-lookup"><span data-stu-id="d4368-109">And with the Windows Virtual Desktop, Citrix, and VMware platforms, calling and meeting functionality is also supported.</span></span>

<span data-ttu-id="d4368-110">虚拟化环境中的团队支持多个配置。</span><span class="sxs-lookup"><span data-stu-id="d4368-110">Teams in a virtualized environment supports multiple configurations.</span></span> <span data-ttu-id="d4368-111">这些模式包括 VDI、专用、共享、持久性和非持久性模式。</span><span class="sxs-lookup"><span data-stu-id="d4368-111">These include VDI, dedicated, shared, persistent, and non-persistent modes.</span></span> <span data-ttu-id="d4368-112">功能持续开发，并定期添加，功能将在几个月和数年内扩展。</span><span class="sxs-lookup"><span data-stu-id="d4368-112">Features are in continuous development and are added on a regular basis, and functionality will expand in the coming months and years.</span></span>

<span data-ttu-id="d4368-113">在虚拟化环境中使用 Teams 可能与在非虚拟化环境中使用 Teams 稍有不同。</span><span class="sxs-lookup"><span data-stu-id="d4368-113">Using Teams in a virtualized environment might be somewhat different from using Teams in a non-virtualized environment.</span></span> <span data-ttu-id="d4368-114">例如，某些高级功能在虚拟化环境中可能不可用，并且视频分辨率可能有所不同。</span><span class="sxs-lookup"><span data-stu-id="d4368-114">For example, some advanced features might not be available in a virtualized environment, and video resolution might differ.</span></span>

<span data-ttu-id="d4368-115">若要确保获得最佳用户体验，请遵循本文中的指导。</span><span class="sxs-lookup"><span data-stu-id="d4368-115">To ensure an optimal user experience, follow the guidance in this article.</span></span>

> [!Note]
> <span data-ttu-id="d4368-116">有关不同平台上的 Teams VDI 的详细信息，请参阅 [按平台的 Teams 功能](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)。</span><span class="sxs-lookup"><span data-stu-id="d4368-116">For details about Teams VDI on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span></span>

## <a name="teams-on-vdi-components"></a><span data-ttu-id="d4368-117">VDI 组件上的 Teams</span><span class="sxs-lookup"><span data-stu-id="d4368-117">Teams on VDI components</span></span>

<span data-ttu-id="d4368-118">在虚拟化环境中使用 Teams 需要以下组件。</span><span class="sxs-lookup"><span data-stu-id="d4368-118">Using Teams in a virtualized environment requires the following components.</span></span>

- <span data-ttu-id="d4368-119">**虚拟化代理**：虚拟化提供程序（例如 Azure）的资源和连接管理器</span><span class="sxs-lookup"><span data-stu-id="d4368-119">**Virtualization broker**: The resource and connection manager to the virtualization provider, such as Azure</span></span>
- <span data-ttu-id="d4368-120">**虚拟桌面**：运行 Microsoft Teams (VM) 堆栈</span><span class="sxs-lookup"><span data-stu-id="d4368-120">**Virtual desktop**: The Virtual Machine (VM) stack that runs Microsoft Teams</span></span>
- <span data-ttu-id="d4368-121">**精简客户端**：用户实际交互的终结点</span><span class="sxs-lookup"><span data-stu-id="d4368-121">**Thin client**: The endpoint that the user physically interfaces with</span></span>
- <span data-ttu-id="d4368-122">**Teams 桌面应用**：Teams 桌面客户端应用</span><span class="sxs-lookup"><span data-stu-id="d4368-122">**Teams desktop app**: The Teams desktop client app</span></span>

## <a name="teams-on-vdi-requirements"></a><span data-ttu-id="d4368-123">Teams on VDI 要求</span><span class="sxs-lookup"><span data-stu-id="d4368-123">Teams on VDI requirements</span></span>

### <a name="virtualization-provider-requirements"></a><span data-ttu-id="d4368-124">虚拟化提供商要求</span><span class="sxs-lookup"><span data-stu-id="d4368-124">Virtualization provider requirements</span></span>

<span data-ttu-id="d4368-125">Teams 桌面应用已使用领先的虚拟化解决方案提供商进行验证。</span><span class="sxs-lookup"><span data-stu-id="d4368-125">The Teams desktop app was validated with leading virtualization solution providers.</span></span> <span data-ttu-id="d4368-126">对于多个市场提供商，建议咨询虚拟化解决方案提供商，确保满足最低要求。</span><span class="sxs-lookup"><span data-stu-id="d4368-126">With multiple market providers, we recommend that you consult your virtualization solution provider to ensure that you meet the minimum requirements.</span></span>
  
<span data-ttu-id="d4368-127">目前，通过 Windows 虚拟桌面、Citrix 和 VMware (VDI 上的 Teams) AV) 优化。</span><span class="sxs-lookup"><span data-stu-id="d4368-127">Currently, Teams on VDI with audio/video (AV) optimization is certified with Windows Virtual Desktop, Citrix, and VMware.</span></span> <span data-ttu-id="d4368-128">查看本部分的信息，确保满足正确功能的所有要求。</span><span class="sxs-lookup"><span data-stu-id="d4368-128">Review the information in this section to ensure that you meet all requirements for proper functionality.</span></span>

### <a name="platforms-certified-for-teams"></a><span data-ttu-id="d4368-129">通过 Teams 认证的平台</span><span class="sxs-lookup"><span data-stu-id="d4368-129">Platforms certified for Teams</span></span>

<span data-ttu-id="d4368-130">以下平台具有适用于 Teams 的虚拟桌面基础结构解决方案。</span><span class="sxs-lookup"><span data-stu-id="d4368-130">The following platforms have virtual desktop infrastructure solutions for Teams.</span></span>

|<span data-ttu-id="d4368-131">平台</span><span class="sxs-lookup"><span data-stu-id="d4368-131">Platform</span></span>|<span data-ttu-id="d4368-132">解决方案</span><span class="sxs-lookup"><span data-stu-id="d4368-132">Solution</span></span>|
|----|---|
|![表示 Microsoft 的徽标](media/microsoft-logo.png)| <span data-ttu-id="d4368-134"><a href="/azure/virtual-desktop/teams-on-wvd" target="_blank">Windows 虚拟桌面</a></span><span class="sxs-lookup"><span data-stu-id="d4368-134"><a href="/azure/virtual-desktop/teams-on-wvd" target="_blank">Windows Virtual Desktop</a></span></span> |
|![表示 Citrix 的徽标](media/citrix-logo.png)| <span data-ttu-id="d4368-136"><a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Citrix 虚拟应用和桌面</a></span><span class="sxs-lookup"><span data-stu-id="d4368-136"><a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Citrix Virtual Apps and Desktops</a></span></span> |
|![表示 VMware 的徽标](media/vmware-logo.png)| <span data-ttu-id="d4368-138"><a href="https://www.vmware.com/products/horizon.html" target="_blank">VMware Horizon</a></span><span class="sxs-lookup"><span data-stu-id="d4368-138"><a href="https://www.vmware.com/products/horizon.html" target="_blank">VMware Horizon</a></span></span> |

### <a name="windows-virtual-desktop"></a><span data-ttu-id="d4368-139">Windows 虚拟桌面</span><span class="sxs-lookup"><span data-stu-id="d4368-139">Windows Virtual Desktop</span></span>

<span data-ttu-id="d4368-140">Windows 虚拟桌面为 VDI 上的 Teams 提供 AV 优化。</span><span class="sxs-lookup"><span data-stu-id="d4368-140">Windows Virtual Desktop provides AV optimization for Teams on VDI.</span></span> <span data-ttu-id="d4368-141">若要了解更多内容以及要求和安装，请参阅在[Windows 虚拟桌面上使用 Teams。](/azure/virtual-desktop/teams-on-wvd)</span><span class="sxs-lookup"><span data-stu-id="d4368-141">To learn more and requirements and installation, see [Use Teams on Windows Virtual Desktop](/azure/virtual-desktop/teams-on-wvd).</span></span>

### <a name="citrix-virtual-apps-and-desktops-requirements"></a><span data-ttu-id="d4368-142">Citrix 虚拟应用和桌面要求</span><span class="sxs-lookup"><span data-stu-id="d4368-142">Citrix Virtual Apps and Desktops requirements</span></span>

<span data-ttu-id="d4368-143">Citrix 虚拟应用和桌面 (以前称为 XenApp 和 XenDesktop) 为 VDI 上的 Teams 提供 AV 优化。</span><span class="sxs-lookup"><span data-stu-id="d4368-143">Citrix Virtual Apps and Desktops (formerly known as XenApp and XenDesktop) provides AV optimization for Teams on VDI.</span></span> <span data-ttu-id="d4368-144">借助 Citrix 虚拟应用和桌面，VDI 上的 Teams 除了支持聊天和协作外，还支持呼叫和会议功能。</span><span class="sxs-lookup"><span data-stu-id="d4368-144">With Citrix Virtual Apps and Desktops, Teams on VDI supports calling and meeting functionality in addition to chat and collaboration.</span></span>

<span data-ttu-id="d4368-145">可以在 Citrix 下载站点 下载最新版本的 Citrix 虚拟应用 [和桌面](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/)。</span><span class="sxs-lookup"><span data-stu-id="d4368-145">You can download the latest version of Citrix Virtual Apps and Desktops at [the Citrix downloads site](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/).</span></span> <span data-ttu-id="d4368-146"> (需要先登录。) 默认情况下，所需的组件将捆绑到 [Citrix 工作区应用 (CWA) ](https://www.citrix.com/downloads/workspace-app/) 和虚拟交付代理 (VDA) 中。</span><span class="sxs-lookup"><span data-stu-id="d4368-146">(You'll need to sign in first.) The necessary components are bundled into the [Citrix Workspace app (CWA)](https://www.citrix.com/downloads/workspace-app/) and Virtual Delivery Agent (VDA) by default.</span></span> <span data-ttu-id="d4368-147">无需在 CWA 或 VDA 上安装任何其他组件或插件。</span><span class="sxs-lookup"><span data-stu-id="d4368-147">You don't need to install any additional components or plugins on CWA or the VDA.</span></span>

<span data-ttu-id="d4368-148">有关最新的服务器和客户端要求，请参阅 [此 Citrix 网站](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html)。</span><span class="sxs-lookup"><span data-stu-id="d4368-148">For the latest server and client requirements, see [this Citrix website](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html).</span></span>

### <a name="vmware-horizon-workspace-and-desktop-requirements"></a><span data-ttu-id="d4368-149">VMware Horizon Workspace 和桌面要求</span><span class="sxs-lookup"><span data-stu-id="d4368-149">VMware Horizon Workspace and Desktop requirements</span></span>

<span data-ttu-id="d4368-150">VMware Horizon 是一个新式平台，用于跨混合云安全交付虚拟桌面和应用。</span><span class="sxs-lookup"><span data-stu-id="d4368-150">VMware Horizon is a modern platform for secure delivery of virtual desktops and apps across the hybrid cloud.</span></span> <span data-ttu-id="d4368-151">为了提供出色的最终用户体验，VMware Horizon 为 Teams 提供媒体优化。</span><span class="sxs-lookup"><span data-stu-id="d4368-151">To offer a great end-user experience, VMware Horizon provides media optimization for Teams.</span></span> <span data-ttu-id="d4368-152">此优化可跨虚拟桌面和应用提高整体工作效率，并增强使用 Teams 进行呼叫和开会的用户体验。</span><span class="sxs-lookup"><span data-stu-id="d4368-152">This optimization improves overall productivity across virtual desktops and apps, and enhances user experience when calling and meeting using Teams.</span></span>

<span data-ttu-id="d4368-153">可以从 VMware 下载页下载最新版本的 [VMware](https://my.vmware.com/web/vmware/downloads/#all_products) Horizon。</span><span class="sxs-lookup"><span data-stu-id="d4368-153">You can download the latest version of VMware Horizon from the [VMware Downloads](https://my.vmware.com/web/vmware/downloads/#all_products) page.</span></span> <span data-ttu-id="d4368-154">默认情况下，所需的媒体优化组件是 Horizon Agent 和 Horizon 客户端的一部分，无需安装任何其他插件来使用 Teams 的优化功能。</span><span class="sxs-lookup"><span data-stu-id="d4368-154">The required media optimization components are part of the Horizon Agent and Horizon Client by default and there's no need to install any additional plug-in to use the optimization feature for Teams.</span></span>

<span data-ttu-id="d4368-155">若要获取有关如何为 Teams 配置媒体优化的最新要求和说明，请参阅 [此 VMware 网站](https://docs.vmware.com/en/VMware-Horizon/2006/horizon-remote-desktop-features/GUID-F68FA7BB-B08F-4EFF-9BB1-1F9FC71F8214.html)。</span><span class="sxs-lookup"><span data-stu-id="d4368-155">To get the latest requirements and instructions on how to configure media optimization for Teams, see [this VMware website](https://docs.vmware.com/en/VMware-Horizon/2006/horizon-remote-desktop-features/GUID-F68FA7BB-B08F-4EFF-9BB1-1F9FC71F8214.html).</span></span>

## <a name="install-or-update-the-teams-desktop-app-on-vdi"></a><span data-ttu-id="d4368-156">在 VDI 上安装或更新 Teams 桌面应用</span><span class="sxs-lookup"><span data-stu-id="d4368-156">Install or update the Teams desktop app on VDI</span></span>

<span data-ttu-id="d4368-157">可以使用每台计算机安装或每用户安装使用 MSI 包部署适用于 VDI 的 Teams 桌面应用。</span><span class="sxs-lookup"><span data-stu-id="d4368-157">You can deploy the Teams desktop app for VDI using a per-machine installation or per-user installation using the MSI package.</span></span> <span data-ttu-id="d4368-158">决定使用哪种方法取决于是使用持久性设置还是非持久性设置，以及组织的关联功能需求。</span><span class="sxs-lookup"><span data-stu-id="d4368-158">Deciding on which approach to use depends on whether you use a persistent or non-persistent setup and the associated functionality needs of your organization.</span></span>

<span data-ttu-id="d4368-159">对于专用的持久性设置，任一方法都正常工作。</span><span class="sxs-lookup"><span data-stu-id="d4368-159">For a dedicated persistent setup, either approach would work.</span></span> <span data-ttu-id="d4368-160">但是，对于非永久性设置，Teams 要求每台计算机安装一次，以便高效工作。</span><span class="sxs-lookup"><span data-stu-id="d4368-160">However, for a non-persistent setup, Teams requires a per-machine installation in order to work efficiently.</span></span> <span data-ttu-id="d4368-161">请参阅 [非永久性设置](#non-persistent-setup) 部分。</span><span class="sxs-lookup"><span data-stu-id="d4368-161">See the [Non-persistent setup](#non-persistent-setup) section.</span></span>

<span data-ttu-id="d4368-162">使用每台计算机安装时，将禁用自动更新。</span><span class="sxs-lookup"><span data-stu-id="d4368-162">With per-machine installation, automatic updates is disabled.</span></span> <span data-ttu-id="d4368-163">这意味着要更新 Teams 应用，必须卸载当前版本以更新到较新版本。</span><span class="sxs-lookup"><span data-stu-id="d4368-163">This means that to update the Teams app, you must uninstall the current version to update to a newer version.</span></span> <span data-ttu-id="d4368-164">通过按用户安装，将启用自动更新。</span><span class="sxs-lookup"><span data-stu-id="d4368-164">With per-user installation, automatic updates is enabled.</span></span> <span data-ttu-id="d4368-165">对于大多数 VDI 部署，建议使用每台计算机安装部署 Teams。</span><span class="sxs-lookup"><span data-stu-id="d4368-165">For most VDI deployments, we recommend you deploy Teams using per-machine installation.</span></span>

<span data-ttu-id="d4368-166">若要更新到最新的 Teams 版本，请从卸载过程开始，然后是最新的 Teams 版本部署。</span><span class="sxs-lookup"><span data-stu-id="d4368-166">To update to the latest Teams version, start with the uninstall procedure followed by latest Teams version deployment.</span></span>

<span data-ttu-id="d4368-167">若要使 VDI 环境中 Teams AV 优化正常工作，精简客户端终结点必须能够访问 Internet。</span><span class="sxs-lookup"><span data-stu-id="d4368-167">For Teams AV optimization in VDI environments to work properly, the thin client endpoint must have access to the internet.</span></span> <span data-ttu-id="d4368-168">如果精简客户端终结点上未提供 Internet 访问，优化启动不会成功。</span><span class="sxs-lookup"><span data-stu-id="d4368-168">If internet access isn't available at the thin client endpoint, optimization startup won't be successful.</span></span> <span data-ttu-id="d4368-169">这意味着用户位于未优化的媒体状态。</span><span class="sxs-lookup"><span data-stu-id="d4368-169">This means that the user is in a non-optimized media state.</span></span>

#### <a name="dedicated-persistent-setup"></a><span data-ttu-id="d4368-170">专用持久设置</span><span class="sxs-lookup"><span data-stu-id="d4368-170">Dedicated persistent setup</span></span>

<span data-ttu-id="d4368-171">在专用的永久性设置中，用户注销后，会保留用户的本地操作系统更改。</span><span class="sxs-lookup"><span data-stu-id="d4368-171">In a dedicated persistent setup, users' local operating system changes are retained after users log off.</span></span> <span data-ttu-id="d4368-172">对于永久性安装，Teams 支持按用户和按计算机安装。</span><span class="sxs-lookup"><span data-stu-id="d4368-172">For persistent setup, Teams supports both per-user and per-machine installation.</span></span>

<span data-ttu-id="d4368-173">下面是建议的最低 VM 配置。</span><span class="sxs-lookup"><span data-stu-id="d4368-173">The following is the recommended minimum VM configuration.</span></span>

|<span data-ttu-id="d4368-174">参数</span><span class="sxs-lookup"><span data-stu-id="d4368-174">Parameter</span></span>  |<span data-ttu-id="d4368-175">工作站操作系统</span><span class="sxs-lookup"><span data-stu-id="d4368-175">Workstation operating system</span></span>  |<span data-ttu-id="d4368-176">服务器操作系统</span><span class="sxs-lookup"><span data-stu-id="d4368-176">Server operating system</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="d4368-177">vCPU</span><span class="sxs-lookup"><span data-stu-id="d4368-177">vCPU</span></span>   |    <span data-ttu-id="d4368-178">2 个核心</span><span class="sxs-lookup"><span data-stu-id="d4368-178">2 cores</span></span>     |  <span data-ttu-id="d4368-179">4、6 或 8</span><span class="sxs-lookup"><span data-stu-id="d4368-179">4,6, or 8</span></span><br><span data-ttu-id="d4368-180">必须了解 NUMA (配置) 基础的非统一内存访问，并相应地配置 VM。</span><span class="sxs-lookup"><span data-stu-id="d4368-180">It's important to understand the underlying non-uniform memory access (NUMA) configuration and configure your VMs accordingly.</span></span>     |
|<span data-ttu-id="d4368-181">RAM</span><span class="sxs-lookup"><span data-stu-id="d4368-181">RAM</span></span>     |   <span data-ttu-id="d4368-182">4 GB</span><span class="sxs-lookup"><span data-stu-id="d4368-182">4 GB</span></span>      | <span data-ttu-id="d4368-183">每个用户 512 到 1024 MB</span><span class="sxs-lookup"><span data-stu-id="d4368-183">512 to 1024 MB per user</span></span>        |
|<span data-ttu-id="d4368-184">存储空间</span><span class="sxs-lookup"><span data-stu-id="d4368-184">Storage</span></span>    | <span data-ttu-id="d4368-185">8 GB</span><span class="sxs-lookup"><span data-stu-id="d4368-185">8 GB</span></span>        | <span data-ttu-id="d4368-186">40 到 60 GB</span><span class="sxs-lookup"><span data-stu-id="d4368-186">40 to 60 GB</span></span>        |

#### <a name="non-persistent-setup"></a><span data-ttu-id="d4368-187">非永久性设置</span><span class="sxs-lookup"><span data-stu-id="d4368-187">Non-persistent setup</span></span>

<span data-ttu-id="d4368-188">在非永久性设置中，用户注销后不会保留用户的本地操作系统更改。</span><span class="sxs-lookup"><span data-stu-id="d4368-188">In a non-persistent setup, users' local operating system changes are not retained after users log off.</span></span> <span data-ttu-id="d4368-189">此类设置通常共享多用户会话。</span><span class="sxs-lookup"><span data-stu-id="d4368-189">Such setups are commonly shared multi-user sessions.</span></span> <span data-ttu-id="d4368-190">VM 配置因用户数和可用物理盒资源而异。</span><span class="sxs-lookup"><span data-stu-id="d4368-190">VM configuration varies based on the number of users and available physical box resources.</span></span>

<span data-ttu-id="d4368-191">对于非永久性设置，Teams 桌面应用必须安装在每台计算机的黄金映像中。</span><span class="sxs-lookup"><span data-stu-id="d4368-191">For a non-persistent setup, the Teams desktop app must be installed per-machine to the golden image.</span></span> <span data-ttu-id="d4368-192"> (有关详细信息，请参阅在 [VDI](#install-or-update-the-teams-desktop-app-on-vdi) 上安装或更新 Teams 桌面应用部分。) 这可确保在用户会话期间高效启动 Teams 应用。</span><span class="sxs-lookup"><span data-stu-id="d4368-192">(To learn more, see the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.) This ensures an efficient launch of the Teams app during a user session.</span></span>

<span data-ttu-id="d4368-193">在非持久性设置中使用 Teams 还需要配置文件缓存管理器，以高效同步 Teams 运行时数据。</span><span class="sxs-lookup"><span data-stu-id="d4368-193">Using Teams in a non-persistent setup also requires a profile-caching manager, for efficient Teams runtime data synchronization.</span></span> <span data-ttu-id="d4368-194">高效的数据同步可确保在用户的会话 (缓存用户的数据、配置文件) 设置等用户特定信息。</span><span class="sxs-lookup"><span data-stu-id="d4368-194">Efficient data synchronization ensures that the appropriate user-specific information (such as a user's data, profile, or settings) is cached during the user's session.</span></span> <span data-ttu-id="d4368-195">确保同步这两个文件夹中的数据：</span><span class="sxs-lookup"><span data-stu-id="d4368-195">Make sure data in these two folders are synched:</span></span><br>
- <span data-ttu-id="d4368-196">C：\Users\username\AppData\Local\Microsoft\IdentityCache (%localAppdata%\Microsoft\IdentityCache) </span><span class="sxs-lookup"><span data-stu-id="d4368-196">C:\Users\username\AppData\Local\Microsoft\IdentityCache (%localAppdata%\Microsoft\IdentityCache)</span></span>
- <span data-ttu-id="d4368-197">C：\Users\username\AppData\Roaming\Microsoft\Teams (%appdata%\Microsoft\Teams) </span><span class="sxs-lookup"><span data-stu-id="d4368-197">C:\Users\username\AppData\Roaming\Microsoft\Teams (%appdata%\Microsoft\Teams)</span></span>

> [!NOTE]
> <span data-ttu-id="d4368-198">漫游文件夹 (，或者，如果使用文件夹重定向，则需要缓存管理器) 以确保 Teams 应用具有运行应用程序所需的运行时数据和文件。</span><span class="sxs-lookup"><span data-stu-id="d4368-198">A roaming folder (or, if you are using folder redirection, a caching manager) is required to ensure that the Teams app has the runtime data and files required to run the application.</span></span> <span data-ttu-id="d4368-199">这是缓解网络延迟问题或网络故障所必需的，否则会导致应用程序错误，并且由于数据和文件不可用导致体验变慢。</span><span class="sxs-lookup"><span data-stu-id="d4368-199">This is necessary to mitigate network latency issues or network glitches, which would otherwise cause application errors and a slow experience due to unavailable data and files.</span></span>

<span data-ttu-id="d4368-200">有各种可用的缓存管理器解决方案。</span><span class="sxs-lookup"><span data-stu-id="d4368-200">There are a variety of caching manager solutions available.</span></span> <span data-ttu-id="d4368-201">例如 [，FSLogix](/fslogix/overview)。</span><span class="sxs-lookup"><span data-stu-id="d4368-201">For example, [FSLogix](/fslogix/overview).</span></span> <span data-ttu-id="d4368-202">有关特定配置说明，请参阅缓存管理器提供程序。</span><span class="sxs-lookup"><span data-stu-id="d4368-202">Consult your caching manager provider for specific configuration instructions.</span></span>

##### <a name="teams-cached-content-exclusion-list-for-non-persistent-setup"></a><span data-ttu-id="d4368-203">用于非持久设置的 Teams 缓存内容排除列表</span><span class="sxs-lookup"><span data-stu-id="d4368-203">Teams cached content exclusion list for non-persistent setup</span></span>

<span data-ttu-id="d4368-204">从 Teams 缓存文件夹 %appdata%/Microsoft/Teams 中排除以下内容。</span><span class="sxs-lookup"><span data-stu-id="d4368-204">Exclude the following from the Teams caching folder, %appdata%/Microsoft/Teams.</span></span> <span data-ttu-id="d4368-205">排除这些项有助于减小用户缓存大小，以进一步优化非持久性设置。</span><span class="sxs-lookup"><span data-stu-id="d4368-205">Excluding these items helps reduce the user caching size to further optimize your non-persistent setup.</span></span>

- <span data-ttu-id="d4368-206">.txt 文件</span><span class="sxs-lookup"><span data-stu-id="d4368-206">.txt files</span></span>
- <span data-ttu-id="d4368-207">Media-stack 文件夹</span><span class="sxs-lookup"><span data-stu-id="d4368-207">Media-stack folder</span></span>
- <span data-ttu-id="d4368-208">meeting-addin\Cache (%appdata%\Microsoft\Teams\meeting-addin\Cache) </span><span class="sxs-lookup"><span data-stu-id="d4368-208">meeting-addin\Cache (%appdata%\Microsoft\Teams\meeting-addin\Cache)</span></span>

### <a name="microsoft-365-apps-for-enterprise-considerations"></a><span data-ttu-id="d4368-209">适用于企业的 Microsoft 365 应用注意事项</span><span class="sxs-lookup"><span data-stu-id="d4368-209">Microsoft 365 Apps for enterprise considerations</span></span>

<span data-ttu-id="d4368-210">使用适用于企业的 Microsoft 365 应用在 VDI 上部署 Teams 时，请考虑以下事项。</span><span class="sxs-lookup"><span data-stu-id="d4368-210">Consider the following when you deploy Teams with Microsoft 365 Apps for enterprise on VDI.</span></span>

#### <a name="new-deployments-of-teams-through-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="d4368-211">通过适用于企业的 Microsoft 365 应用部署 Teams 的新部署</span><span class="sxs-lookup"><span data-stu-id="d4368-211">New deployments of Teams through Microsoft 365 Apps for enterprise</span></span>

<span data-ttu-id="d4368-212">通过 Microsoft 365 企业版应用部署 Teams 之前，必须先卸载任何预先存在的 Teams 应用（如果它们是使用每台计算机安装部署的）。</span><span class="sxs-lookup"><span data-stu-id="d4368-212">Before you deploy Teams through Microsoft 365 Apps for enterprise, you must first uninstall any pre-existing Teams apps if they were deployed using per-machine installation.</span></span>

<span data-ttu-id="d4368-213">通过 Microsoft 365 企业版应用安装的 Teams 是按用户安装的。</span><span class="sxs-lookup"><span data-stu-id="d4368-213">Teams through Microsoft 365 Apps for enterprise is installed per-user.</span></span> <span data-ttu-id="d4368-214">有关详细信息，请参阅在 VDI 上安装或更新 [Teams 桌面应用](#install-or-update-the-teams-desktop-app-on-vdi) 部分。</span><span class="sxs-lookup"><span data-stu-id="d4368-214">To learn more, see the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.</span></span>

#### <a name="teams-deployments-through-microsoft-365-apps-for-enterprise-updates"></a><span data-ttu-id="d4368-215">通过适用于企业更新的 Microsoft 365 应用部署 Teams</span><span class="sxs-lookup"><span data-stu-id="d4368-215">Teams deployments through Microsoft 365 Apps for enterprise updates</span></span>

<span data-ttu-id="d4368-216">Teams 也会添加到 Microsoft 365 企业版应用的现有安装中。</span><span class="sxs-lookup"><span data-stu-id="d4368-216">Teams is also being added to existing installations of Microsoft 365 Apps for enterprise.</span></span> <span data-ttu-id="d4368-217">由于 Microsoft 365 企业版应用仅按用户安装 Teams，请参阅在 [VDI](#install-or-update-the-teams-desktop-app-on-vdi) 上安装或更新 Teams 桌面应用部分。</span><span class="sxs-lookup"><span data-stu-id="d4368-217">Since Microsoft 365 Apps for enterprise installs Teams per-user only, see the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.</span></span>

#### <a name="using-teams-with-per-machine-installation-and-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="d4368-218">将 Teams 与每台计算机安装和适用于企业的 Microsoft 365 应用一同使用</span><span class="sxs-lookup"><span data-stu-id="d4368-218">Using Teams with per-machine installation and Microsoft 365 Apps for enterprise</span></span>

<span data-ttu-id="d4368-219">Microsoft 365 企业版应用不支持每台计算机安装 Teams。</span><span class="sxs-lookup"><span data-stu-id="d4368-219">Microsoft 365 Apps for enterprise doesn't support per-machine installations of Teams.</span></span> <span data-ttu-id="d4368-220">若要使用每台计算机安装，必须从 Microsoft 365 企业版应用中排除 Teams。</span><span class="sxs-lookup"><span data-stu-id="d4368-220">To use per-machine installation, you must exclude Teams from Microsoft 365 Apps for enterprise.</span></span> <span data-ttu-id="d4368-221">请参阅 [将 Teams 桌面应用部署到 VM](#deploy-the-teams-desktop-app-to-the-vm) 和 [如何通过适用于企业的 Microsoft 365](#how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise) 应用排除 Teams 部署部分。</span><span class="sxs-lookup"><span data-stu-id="d4368-221">See the [Deploy the Teams desktop app to the VM](#deploy-the-teams-desktop-app-to-the-vm) and [How to exclude Teams deployment through Microsoft 365 Apps for enterprise](#how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise) sections.</span></span>

#### <a name="how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="d4368-222">如何通过适用于企业的 Microsoft 365 应用排除 Teams 部署</span><span class="sxs-lookup"><span data-stu-id="d4368-222">How to exclude Teams deployment through Microsoft 365 Apps for enterprise</span></span>

<span data-ttu-id="d4368-223">若要详细了解 Teams 和 Microsoft 365 企业版应用，请参阅如何从适用于企业的 [Microsoft 365](/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-office-365-proplus) 应用的新安装中排除 Teams 和使用组策略来控制 Teams 的 [安装](/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams)。</span><span class="sxs-lookup"><span data-stu-id="d4368-223">To learn more about Teams and Microsoft 365 Apps for enterprise, see [How to exclude Teams from new installations of Microsoft 365 Apps for enterprise](/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-office-365-proplus) and [Use Group Policy to control the installation of Teams](/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams).</span></span>

### <a name="deploy-the-teams-desktop-app-to-the-vm"></a><span data-ttu-id="d4368-224">将 Teams 桌面应用部署到 VM</span><span class="sxs-lookup"><span data-stu-id="d4368-224">Deploy the Teams desktop app to the VM</span></span>

1. <span data-ttu-id="d4368-225">使用以下链接之一下载与 VDI VM 操作系统匹配的 Teams MSI 包：</span><span class="sxs-lookup"><span data-stu-id="d4368-225">Download the Teams MSI package that matches your VDI VM operating system using one of the following links:</span></span>

    - [<span data-ttu-id="d4368-226">32 位版本</span><span class="sxs-lookup"><span data-stu-id="d4368-226">32-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)
    - [<span data-ttu-id="d4368-227">64 位版本</span><span class="sxs-lookup"><span data-stu-id="d4368-227">64-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)

    > [!NOTE]
    > <span data-ttu-id="d4368-228">对于政府云，请参阅 [使用 Microsoft 终结点配置管理器安装 Microsoft Teams，](msi-deployment.md) 了解 MSI 文件的下载链接。</span><span class="sxs-lookup"><span data-stu-id="d4368-228">For government clouds, see [Install Microsoft Teams using Microsoft Endpoint Configuration Manager](msi-deployment.md) for the download links to the MSI files.</span></span>

    <span data-ttu-id="d4368-229">所需的 Teams 桌面应用最低版本是版本 1.3.00.4461。</span><span class="sxs-lookup"><span data-stu-id="d4368-229">The minimum version of the Teams desktop app that's required is version 1.3.00.4461.</span></span> <span data-ttu-id="d4368-230"> (版本不支持 PSTN 保留。) </span><span class="sxs-lookup"><span data-stu-id="d4368-230">(PSTN hold isn't supported in earlier versions.)</span></span>

2. <span data-ttu-id="d4368-231">运行以下命令之一，将 MSI 安装到 VDI VM：</span><span class="sxs-lookup"><span data-stu-id="d4368-231">Install the MSI to the VDI VM by running one of the following commands:</span></span>

    - <span data-ttu-id="d4368-232">按用户安装 (默认) </span><span class="sxs-lookup"><span data-stu-id="d4368-232">Per-user installation (default)</span></span>
  
        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSERS=1
        ```

        <span data-ttu-id="d4368-233">此过程是默认安装，用于将 Teams 安装到 %AppData% 用户文件夹。</span><span class="sxs-lookup"><span data-stu-id="d4368-233">This process is the default installation, which installs Teams to the %AppData% user folder.</span></span> <span data-ttu-id="d4368-234">此时，黄金映像设置已完成。</span><span class="sxs-lookup"><span data-stu-id="d4368-234">At this point, the golden image setup is complete.</span></span> <span data-ttu-id="d4368-235">Teams 无法正常使用非永久性安装上的按用户安装。</span><span class="sxs-lookup"><span data-stu-id="d4368-235">Teams won't work properly with per-user installation on a non-persistent setup.</span></span>

    - <span data-ttu-id="d4368-236">每台计算机安装</span><span class="sxs-lookup"><span data-stu-id="d4368-236">Per-machine installation</span></span>

        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1 ALLUSERS=1
        ```

        <span data-ttu-id="d4368-237">此过程将 Teams 安装到 64 位操作系统上的 program Files (x86) 文件夹，以及 32 位操作系统上的 Program Files 文件夹。</span><span class="sxs-lookup"><span data-stu-id="d4368-237">This process installs Teams to the Program Files (x86) folder on a 64-bit operating system and to the Program Files folder on a 32-bit operating system.</span></span> <span data-ttu-id="d4368-238">此时，黄金映像设置已完成。</span><span class="sxs-lookup"><span data-stu-id="d4368-238">At this point, the golden image setup is complete.</span></span> <span data-ttu-id="d4368-239">非永久性设置需要每台计算机安装 Teams。</span><span class="sxs-lookup"><span data-stu-id="d4368-239">Installing Teams per-machine is required for non-persistent setups.</span></span>

        <span data-ttu-id="d4368-240">下一个交互式登录会话将启动 Teams 并请求凭据。</span><span class="sxs-lookup"><span data-stu-id="d4368-240">The next interactive logon session starts Teams and asks for credentials.</span></span>

        > [!NOTE]
        > <span data-ttu-id="d4368-241">这些示例还使用 **ALLUSERS=1** 参数。</span><span class="sxs-lookup"><span data-stu-id="d4368-241">These examples also use the **ALLUSERS=1** parameter.</span></span> <span data-ttu-id="d4368-242">设置此参数时，Teams Machine-Wide 安装程序会显示在"控制面板"中的"程序和功能"中，以及"应用"&"Windows 设置"中针对计算机的所有用户显示的功能。</span><span class="sxs-lookup"><span data-stu-id="d4368-242">When you set this parameter, Teams Machine-Wide Installer appears in Programs and Features in Control Panel and in Apps & features in Windows Settings for all users of the computer.</span></span> <span data-ttu-id="d4368-243">然后，所有用户都可以卸载 Teams（如果他们具有管理员凭据）。</span><span class="sxs-lookup"><span data-stu-id="d4368-243">All users can then uninstall Teams if they have admin credentials.</span></span>
        <span data-ttu-id="d4368-244">必须了解 **ALLUSERS=1** 和 **ALLUSER=1 的区别**。</span><span class="sxs-lookup"><span data-stu-id="d4368-244">It's important to understand the difference between **ALLUSERS=1** and **ALLUSER=1**.</span></span> <span data-ttu-id="d4368-245">**ALLUSERS=1** 参数可用于非 VDI 和 VDI 环境，而 **ALLUSER=1** 参数仅在 VDI 环境中用于指定每台计算机安装。</span><span class="sxs-lookup"><span data-stu-id="d4368-245">The **ALLUSERS=1** parameter can be used in non-VDI and VDI environments, while the **ALLUSER=1** parameter is used only in VDI environments to specify a per-machine installation.</span></span>

3. <span data-ttu-id="d4368-246">从 VDI VM 卸载 MSI。</span><span class="sxs-lookup"><span data-stu-id="d4368-246">Uninstall the MSI from the VDI VM.</span></span> <span data-ttu-id="d4368-247">有两种方法可以卸载 Teams。</span><span class="sxs-lookup"><span data-stu-id="d4368-247">There are two ways to uninstall Teams.</span></span>

    - <span data-ttu-id="d4368-248">PowerShell 脚本：可以使用此 [PowerShell 脚本](scripts/powershell-script-deployment-cleanup.md) 卸载 Teams 并删除用户的 Teams 文件夹。</span><span class="sxs-lookup"><span data-stu-id="d4368-248">PowerShell script: You can use [this PowerShell script](scripts/powershell-script-deployment-cleanup.md) to uninstall Teams and remove the Teams folder for a user.</span></span> <span data-ttu-id="d4368-249">为计算机上安装 Teams 的每个用户配置文件运行脚本。</span><span class="sxs-lookup"><span data-stu-id="d4368-249">Run the script for each user profile in which Teams was installed on the computer.</span></span>
    - <span data-ttu-id="d4368-250">命令行：运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="d4368-250">Command line: Run the following command.</span></span>
  
      ```console
      msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>
      ```

      <span data-ttu-id="d4368-251">此过程从"程序文件" (x86) 或"程序文件"文件夹中卸载 Teams，具体取决于操作系统环境。</span><span class="sxs-lookup"><span data-stu-id="d4368-251">This process uninstalls Teams from the Program Files (x86) folder or Program Files folder, depending on the operating system environment.</span></span>

## <a name="teams-on-vdi-performance-considerations"></a><span data-ttu-id="d4368-252">Teams on VDI 性能注意事项</span><span class="sxs-lookup"><span data-stu-id="d4368-252">Teams on VDI performance considerations</span></span>

<span data-ttu-id="d4368-253">有各种虚拟化设置配置，每个配置都有不同的优化重点。</span><span class="sxs-lookup"><span data-stu-id="d4368-253">There are a variety of virtualized setup configurations, each with a different focus for optimization.</span></span> <span data-ttu-id="d4368-254">例如，配置可能侧重于用户密度。</span><span class="sxs-lookup"><span data-stu-id="d4368-254">For example, a configuration might focus on user density.</span></span> <span data-ttu-id="d4368-255">规划时，请考虑以下事项，以帮助根据组织的工作负荷需求优化设置。</span><span class="sxs-lookup"><span data-stu-id="d4368-255">When planning, consider the following to help optimize your setup based on your organization's workload needs.</span></span>

- <span data-ttu-id="d4368-256">最低要求：某些工作负荷可能需要使用高于最低要求的资源进行设置。</span><span class="sxs-lookup"><span data-stu-id="d4368-256">Minimum requirement: Some workloads might require a setup using resources that are above the minimum requirements.</span></span> <span data-ttu-id="d4368-257">例如，对于使用需要更多计算资源的应用程序的开发人员的工作负荷。</span><span class="sxs-lookup"><span data-stu-id="d4368-257">For example, workloads for developers who use applications that demand more computing resources.</span></span>
- <span data-ttu-id="d4368-258">依赖项：其中包括对基础结构、工作负荷的依赖关系，以及 Teams 桌面应用外部的其他环境注意事项。</span><span class="sxs-lookup"><span data-stu-id="d4368-258">Dependencies: These include dependencies on infrastructure, workload, and other environmental considerations outside the Teams desktop app.</span></span>
- <span data-ttu-id="d4368-259">VDI 上的已禁用功能：Teams 禁用 VDI 的 GPU 密集型功能，这有助于改善暂时性 CPU 利用率。</span><span class="sxs-lookup"><span data-stu-id="d4368-259">Disabled features on VDI: Teams disables GPU-intensive features for VDI, which can help improve transient CPU utilization.</span></span> <span data-ttu-id="d4368-260">禁用了以下功能：</span><span class="sxs-lookup"><span data-stu-id="d4368-260">The following features are disabled:</span></span>
    - <span data-ttu-id="d4368-261">Teams CSS 动画</span><span class="sxs-lookup"><span data-stu-id="d4368-261">Teams CSS animation</span></span>
    - <span data-ttu-id="d4368-262">Giphy 自动启动</span><span class="sxs-lookup"><span data-stu-id="d4368-262">Giphy auto-start</span></span>

## <a name="teams-on-vdi-with-calling-and-meetings"></a><span data-ttu-id="d4368-263">VDI 上的 Teams 与通话和会议</span><span class="sxs-lookup"><span data-stu-id="d4368-263">Teams on VDI with calling and meetings</span></span>

<span data-ttu-id="d4368-264">除了聊天和协作外，支持虚拟化提供商平台的 VDI 上的 Teams 还支持通话和会议。</span><span class="sxs-lookup"><span data-stu-id="d4368-264">In addition to chat and collaboration, Teams on VDI with calling and meetings is available with supported virtualization provider platforms.</span></span> <span data-ttu-id="d4368-265">支持的功能基于 WebRTC 媒体堆栈和虚拟化提供程序实现。</span><span class="sxs-lookup"><span data-stu-id="d4368-265">Supported features are based on the WebRTC media stack and virtualization provider implementation.</span></span> <span data-ttu-id="d4368-266">下图提供了体系结构的概述。</span><span class="sxs-lookup"><span data-stu-id="d4368-266">The following diagram provides an overview of the architecture.</span></span>

![显示 Teams on VDI 体系结构的示意图](media/teams-on-vdi-architecture.png)

> [!IMPORTANT]
> <span data-ttu-id="d4368-268">如果当前运行 Teams 时未在 VDI 中执行 AV 优化，并且使用尚不支持用于优化的功能 (如在应用共享) 时授予和控制，必须设置虚拟化提供程序策略以关闭 Teams 重定向。</span><span class="sxs-lookup"><span data-stu-id="d4368-268">If you currently run Teams without AV optimization in VDI and you use features that are not supported yet for optimization (such as Give and take control when app sharing), you have to set virtualization provider policies to turn off Teams redirection.</span></span> <span data-ttu-id="d4368-269">这意味着 Teams 媒体会话不会优化。</span><span class="sxs-lookup"><span data-stu-id="d4368-269">This means that Teams media sessions won't be optimized.</span></span> <span data-ttu-id="d4368-270">若要了解如何设置策略以关闭 Teams 重定向，请联系虚拟化提供商。</span><span class="sxs-lookup"><span data-stu-id="d4368-270">For steps on how to set policies to turn off Teams redirection, contact your virtualization provider.</span></span>

### <a name="network-requirements"></a><span data-ttu-id="d4368-271">网络要求</span><span class="sxs-lookup"><span data-stu-id="d4368-271">Network requirements</span></span>

<span data-ttu-id="d4368-272">建议评估环境，确定可能影响整体云语音和视频部署的任何风险和要求。</span><span class="sxs-lookup"><span data-stu-id="d4368-272">We recommend that you evaluate your environment to identify any risks and requirements that can influence your overall cloud voice and video deployment.</span></span> <span data-ttu-id="d4368-273">使用 [Skype for Business 网络评估工具](https://www.microsoft.com/download/details.aspx?id=53885) 测试你的网络是否适用于 Teams。</span><span class="sxs-lookup"><span data-stu-id="d4368-273">Use the [Skype for Business Network Assessment Tool](https://www.microsoft.com/download/details.aspx?id=53885) to test whether your network is ready for Teams.</span></span>

<span data-ttu-id="d4368-274">若要详细了解如何为 Teams 准备网络，请参阅为 [Teams 准备组织的网络](prepare-network.md)。</span><span class="sxs-lookup"><span data-stu-id="d4368-274">To learn more about how to prepare your network for Teams, see [Prepare your organization's network for Teams](prepare-network.md).</span></span>

### <a name="migrate-from-skype-for-business-on-vdi-to-teams-on-vdi"></a><span data-ttu-id="d4368-275">从 VDI 上的 Skype for Business 迁移到 VDI 上的 Teams</span><span class="sxs-lookup"><span data-stu-id="d4368-275">Migrate from Skype for Business on VDI to Teams on VDI</span></span>

<span data-ttu-id="d4368-276">如果要从 VDI 上的 Skype for Business 迁移到 VDI 上的 Teams，则除了两个应用程序之间的差异外，也实现 VDI 时存在一些差异。</span><span class="sxs-lookup"><span data-stu-id="d4368-276">If you're migrating from Skype for Business on VDI to Teams on VDI, besides the differences between the two applications, there are some differences when VDI is also implemented.</span></span> <span data-ttu-id="d4368-277">Skype for Business VDI 中的 Teams VDI 目前不支持的一些功能如下所示：</span><span class="sxs-lookup"><span data-stu-id="d4368-277">Some capabilities that aren't currently supported in Teams VDI that are in Skype for Business VDI are as follows:</span></span>

- <span data-ttu-id="d4368-278">在 VDI 中禁用某些 AV 功能的按平台策略</span><span class="sxs-lookup"><span data-stu-id="d4368-278">Per-platform policy to disable some AV features in VDI</span></span>
- <span data-ttu-id="d4368-279">在应用共享时授予并控制</span><span class="sxs-lookup"><span data-stu-id="d4368-279">Give and take control when app sharing</span></span>
- <span data-ttu-id="d4368-280">无音频聊天中的屏幕共享</span><span class="sxs-lookup"><span data-stu-id="d4368-280">Screen share from chat without audio</span></span>
- <span data-ttu-id="d4368-281">同时发送和接收视频和屏幕共享</span><span class="sxs-lookup"><span data-stu-id="d4368-281">Simultaneous video and screen sharing send and receive</span></span>

### <a name="teams-on-chrome-browser-versus-teams-desktop-app-for-vdi"></a><span data-ttu-id="d4368-282">Chrome 浏览器上的 Teams 与适用于 VDI 的 Teams 桌面应用</span><span class="sxs-lookup"><span data-stu-id="d4368-282">Teams on Chrome browser versus Teams desktop app for VDI</span></span>

<span data-ttu-id="d4368-283">Chrome 浏览器上的 Teams 不提供用于 VDI 的 Teams 桌面应用与 AV 优化的替换项。</span><span class="sxs-lookup"><span data-stu-id="d4368-283">Teams on Chrome browser doesn't provide a replacement for the Teams desktop app for VDI with AV optimization.</span></span> <span data-ttu-id="d4368-284">聊天和协作体验如期工作。</span><span class="sxs-lookup"><span data-stu-id="d4368-284">The chat and collaboration experience works as expected.</span></span> <span data-ttu-id="d4368-285">当需要媒体时，某些体验可能无法满足用户在 Chrome 浏览器上的期望：</span><span class="sxs-lookup"><span data-stu-id="d4368-285">When media is needed, there are some experiences that might not meet user expectations on the Chrome browser:</span></span>

- <span data-ttu-id="d4368-286">音频和视频流式处理体验可能并非最佳。</span><span class="sxs-lookup"><span data-stu-id="d4368-286">The audio and video streaming experience might not be optimal.</span></span> <span data-ttu-id="d4368-287">用户可能会遇到延迟或质量降低的情况。</span><span class="sxs-lookup"><span data-stu-id="d4368-287">Users might experiences delays or reduced quality.</span></span>
- <span data-ttu-id="d4368-288">设备设置在浏览器设置中不可用。</span><span class="sxs-lookup"><span data-stu-id="d4368-288">Device settings aren't available in browser settings.</span></span>
- <span data-ttu-id="d4368-289">设备管理通过浏览器进行处理，需要在浏览器网站设置中设置多个设置。</span><span class="sxs-lookup"><span data-stu-id="d4368-289">Device management is handled through the browser and requires multiple settings in browser site settings.</span></span>
- <span data-ttu-id="d4368-290">可能需要在 Windows 设备管理中设置设备设置。</span><span class="sxs-lookup"><span data-stu-id="d4368-290">Device settings might also need to be set in Windows device management.</span></span>

## <a name="teams-on-vdi-with-chat-and-collaboration"></a><span data-ttu-id="d4368-291">通过聊天和协作在 VDI 上的 Teams</span><span class="sxs-lookup"><span data-stu-id="d4368-291">Teams on VDI with chat and collaboration</span></span>

<span data-ttu-id="d4368-292">如果你的组织只想使用 Teams 中的聊天和协作功能，你可以设置用户级策略以关闭 Teams 中的呼叫和会议功能。</span><span class="sxs-lookup"><span data-stu-id="d4368-292">If your organization wants to only use chat and collaboration features in Teams, you can set user-level policies to turn off calling and meeting functionality in Teams.</span></span> 

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a><span data-ttu-id="d4368-293">设置策略以关闭呼叫和会议功能</span><span class="sxs-lookup"><span data-stu-id="d4368-293">Set policies to turn off calling and meeting functionality</span></span>

<span data-ttu-id="d4368-294">可以使用 Microsoft Teams 管理中心或 PowerShell 设置策略。</span><span class="sxs-lookup"><span data-stu-id="d4368-294">You can set policies by using the Microsoft Teams admin center or PowerShell.</span></span> <span data-ttu-id="d4368-295">传播策略更改 (可能需要) 几个小时。</span><span class="sxs-lookup"><span data-stu-id="d4368-295">It might take some time (a few hours) for the policy changes to propagate.</span></span> <span data-ttu-id="d4368-296">如果未立即看到给定帐户的更改，请在几小时后重试。</span><span class="sxs-lookup"><span data-stu-id="d4368-296">If you don't see changes for a given account immediately, try again in a few hours.</span></span>

<span data-ttu-id="d4368-297">[**调用策略**](teams-calling-policy.md)：Teams 包括内置的 DisallowCalling 调用策略，其中所有调用功能都已关闭。</span><span class="sxs-lookup"><span data-stu-id="d4368-297">[**Calling polices**](teams-calling-policy.md): Teams includes the built-in DisallowCalling calling policy, in which all calling features are turned off.</span></span> <span data-ttu-id="d4368-298">将 DisallowCalling 策略分配给组织中在虚拟化环境中使用 Teams 的所有用户。</span><span class="sxs-lookup"><span data-stu-id="d4368-298">Assign the DisallowCalling policy to all users in your organization who use Teams in a virtualized environment.</span></span>

<span data-ttu-id="d4368-299">[**会议策略**](meeting-policies-in-teams.md)：Teams 包括内置的 AllOff 会议策略，其中所有会议功能都已关闭。</span><span class="sxs-lookup"><span data-stu-id="d4368-299">[**Meeting policies**](meeting-policies-in-teams.md): Teams includes the built-in AllOff meeting policy, in which all meeting features are turned off.</span></span> <span data-ttu-id="d4368-300">将 AllOff 策略分配给组织中在虚拟化环境中使用 Teams 的所有用户。</span><span class="sxs-lookup"><span data-stu-id="d4368-300">Assign the AllOff policy to all users in your organization who use Teams in a virtualized environment.</span></span>

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a><span data-ttu-id="d4368-301">使用 Microsoft Teams 管理中心分配策略</span><span class="sxs-lookup"><span data-stu-id="d4368-301">Assign policies using the Microsoft Teams admin center</span></span>

<span data-ttu-id="d4368-302">将 DisallowCalling 调用策略和 AllOff 会议策略分配给用户：</span><span class="sxs-lookup"><span data-stu-id="d4368-302">To assign the DisallowCalling calling policy and the AllOff meeting policy to a user:</span></span>

1. <span data-ttu-id="d4368-303">在 Microsoft Teams 管理中心的左侧导航栏中，转到"用户 **"。**</span><span class="sxs-lookup"><span data-stu-id="d4368-303">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="d4368-304">单击用户名的左侧以选择用户，然后单击“编辑设置”。</span><span class="sxs-lookup"><span data-stu-id="d4368-304">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="d4368-305">执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d4368-305">Do the following:</span></span>
    1.  <span data-ttu-id="d4368-306">在 **"调用策略"** 下，**单击"禁止""缩放"。**</span><span class="sxs-lookup"><span data-stu-id="d4368-306">Under **Calling policy**, click **DisallowCalling**.</span></span>
    2.  <span data-ttu-id="d4368-307">在"**会议策略"** 下，单击 **"AllOff"。**</span><span class="sxs-lookup"><span data-stu-id="d4368-307">Under **Meeting policy**, click **AllOff**.</span></span>
4. <span data-ttu-id="d4368-308">单击“**应用**”。</span><span class="sxs-lookup"><span data-stu-id="d4368-308">Click **Apply**.</span></span>

<span data-ttu-id="d4368-309">若要一次向多个用户分配策略，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d4368-309">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="d4368-310">在 Microsoft Teams 管理中心的左侧导航栏中，转到“**用户**”，然后搜索用户或筛选视图，以显示所需的用户。</span><span class="sxs-lookup"><span data-stu-id="d4368-310">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="d4368-311">在 **&#x2713;**（复选标记）列，选择用户。</span><span class="sxs-lookup"><span data-stu-id="d4368-311">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="d4368-312">若要选择所有用户，请单击表格顶部的 &#x2713;（复选标记）。</span><span class="sxs-lookup"><span data-stu-id="d4368-312">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="d4368-313">单击“**编辑设置**”，执行所需的更改，然后单击“**应用**”。</span><span class="sxs-lookup"><span data-stu-id="d4368-313">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>

<span data-ttu-id="d4368-314">或者，也可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d4368-314">Or, you can also do the following:</span></span>

1. <span data-ttu-id="d4368-315">在 Microsoft Teams 管理中心的左侧导航栏中，转到要分配的策略。</span><span class="sxs-lookup"><span data-stu-id="d4368-315">In the left navigation of the Microsoft Teams admin center, go to the policy you want to assign.</span></span> <span data-ttu-id="d4368-316">例如：</span><span class="sxs-lookup"><span data-stu-id="d4368-316">For example:</span></span>
    - <span data-ttu-id="d4368-317">转到 **"语音**  >  **呼叫策略"，** 然后单击"**取消允许""呼叫"。**</span><span class="sxs-lookup"><span data-stu-id="d4368-317">Go to **Voice** > **Calling policies**, and then click **DisallowCalling**.</span></span>
    - <span data-ttu-id="d4368-318">转到"**会议**  >  **会议策略"，** 然后单击 **"AllOff"。**</span><span class="sxs-lookup"><span data-stu-id="d4368-318">Go to **Meetings** > **Meeting policies**, and then click **AllOff**.</span></span>
2. <span data-ttu-id="d4368-319">选择“管理用户”。</span><span class="sxs-lookup"><span data-stu-id="d4368-319">Select **Manage users**.</span></span>
3. <span data-ttu-id="d4368-320">在“管理用户”窗格中，按显示名称或用户名搜索用户，选择用户名，然后单击“添加”。</span><span class="sxs-lookup"><span data-stu-id="d4368-320">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="d4368-321">对想要添加的每一个用户重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="d4368-321">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="d4368-322">添加完用户后，单击"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="d4368-322">When you're finished adding users, click **Save**.</span></span>

#### <a name="assign-policies-using-powershell"></a><span data-ttu-id="d4368-323">使用 PowerShell 分配策略</span><span class="sxs-lookup"><span data-stu-id="d4368-323">Assign policies using PowerShell</span></span>

<span data-ttu-id="d4368-324">以下示例演示如何使用 [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) 将 DisallowCalling 调用策略分配给用户。</span><span class="sxs-lookup"><span data-stu-id="d4368-324">The following example shows how to use the [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) to assign the DisallowCalling calling policy to a user.</span></span>

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

<span data-ttu-id="d4368-325">若要详细了解使用 PowerShell 管理调用策略，请参阅[Set-CsTeamsCallingPolicy。](/powershell/module/skype/set-csteamscallingpolicy)</span><span class="sxs-lookup"><span data-stu-id="d4368-325">To learn more about using PowerShell to manage calling policies, see [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy).</span></span>

<span data-ttu-id="d4368-326">以下示例演示如何使用 [Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) 将 AllOff 会议策略分配给用户。</span><span class="sxs-lookup"><span data-stu-id="d4368-326">The following example shows how to use the [Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) to assign the AllOff meeting policy to a user.</span></span>

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

<span data-ttu-id="d4368-327">若要详细了解使用 PowerShell 管理会议策略，请参阅[Set-CsTeamsMeetingPolicy。](/powershell/module/skype/set-csteamsmeetingpolicy)</span><span class="sxs-lookup"><span data-stu-id="d4368-327">To learn more about using PowerShell to manage meeting policies, see [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy).</span></span>

## <a name="migrate-teams-on-vdi-with-chat-and-collaboration-to-optimize-teams-with-calling-and-meetings"></a><span data-ttu-id="d4368-328">通过聊天和协作迁移 VDI 上的 Teams，以通过通话和会议优化 Teams</span><span class="sxs-lookup"><span data-stu-id="d4368-328">Migrate Teams on VDI with chat and collaboration to optimize Teams with calling and meetings</span></span>

<span data-ttu-id="d4368-329">如果 VDI 上的 Teams 具有聊天和协作的现有实现，其中你已设置用户级策略以关闭呼叫和会议功能，并且你将迁移到具有 AV 优化的 Teams，则必须设置策略，为 VDI 用户启用这些 Teams 的呼叫和会议功能。</span><span class="sxs-lookup"><span data-stu-id="d4368-329">If you have an existing implementation of Teams on VDI with chat and collaboration in which you had set user-level policies to turn off calling and meeting functionality, and you're migrating to Teams with AV optimization, you must set policies to turn on calling and meeting functionality for those Teams on VDI users.</span></span>

### <a name="set-policies-to-turn-on-calling-and-meeting-functionality"></a><span data-ttu-id="d4368-330">设置策略以打开呼叫和会议功能</span><span class="sxs-lookup"><span data-stu-id="d4368-330">Set policies to turn on calling and meeting functionality</span></span>

<span data-ttu-id="d4368-331">可以使用 Microsoft Teams 管理中心或 PowerShell 设置呼叫和会议策略并将其分配给用户。</span><span class="sxs-lookup"><span data-stu-id="d4368-331">You can use the Microsoft Teams admin center or PowerShell to set and assign calling and meeting policies to your users.</span></span> <span data-ttu-id="d4368-332">传播策略更改 (可能需要) 几个小时。</span><span class="sxs-lookup"><span data-stu-id="d4368-332">It can take some time (a few hours) for policy changes to propagate.</span></span> <span data-ttu-id="d4368-333">如果未立即看到给定帐户的更改，请在几小时后重试。</span><span class="sxs-lookup"><span data-stu-id="d4368-333">If you don't see changes for a given account immediately, try again after a few hours.</span></span>

<span data-ttu-id="d4368-334">[**调用策略**](teams-calling-policy.md)：Teams 中的调用策略控制哪些呼叫功能可供用户使用。</span><span class="sxs-lookup"><span data-stu-id="d4368-334">[**Calling polices**](teams-calling-policy.md): Calling policies in Teams control which calling features are available to users.</span></span> <span data-ttu-id="d4368-335">Teams 包括内置的 AllowCalling 呼叫策略，其中所有通话功能都开启。</span><span class="sxs-lookup"><span data-stu-id="d4368-335">Teams includes the built-in AllowCalling calling policy, in which all calling features are turned on.</span></span> <span data-ttu-id="d4368-336">若要启用所有调用功能，请分配 AllowCalling 策略。</span><span class="sxs-lookup"><span data-stu-id="d4368-336">To turn on all calling features, assign the AllowCalling policy.</span></span> <span data-ttu-id="d4368-337">或者，创建自定义呼叫策略以打开你需要的呼叫功能并将其分配给用户。</span><span class="sxs-lookup"><span data-stu-id="d4368-337">Or, create a custom calling policy to turn on the calling features that you want and assign it to users.</span></span> 

<span data-ttu-id="d4368-338">[**会议策略**](meeting-policies-in-teams.md)：Teams 中的会议策略控制用户可以创建的会议类型以及组织中用户安排的会议参与者可用的功能。</span><span class="sxs-lookup"><span data-stu-id="d4368-338">[**Meeting policies**](meeting-policies-in-teams.md): Meeting policies in Teams control the types of meetings that users can create and the features that are available to meeting participants that are scheduled by users in your organization.</span></span> <span data-ttu-id="d4368-339">Teams 包括内置的 AllOn 会议策略，其中所有会议功能都开启。</span><span class="sxs-lookup"><span data-stu-id="d4368-339">Teams includes the built-in AllOn meeting policy, in which all meeting features are turned on.</span></span> <span data-ttu-id="d4368-340">若要启用所有会议功能，请分配 AllOn 策略。</span><span class="sxs-lookup"><span data-stu-id="d4368-340">To turn on all meeting features, assign the AllOn policy.</span></span> <span data-ttu-id="d4368-341">或者，创建自定义会议策略以打开你需要的会议功能并为其分配用户。</span><span class="sxs-lookup"><span data-stu-id="d4368-341">Or, create a custom meeting policy to turn on the meeting features that you want and assign it users.</span></span>

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a><span data-ttu-id="d4368-342">使用 Microsoft Teams 管理中心分配策略</span><span class="sxs-lookup"><span data-stu-id="d4368-342">Assign policies using the Microsoft Teams admin center</span></span>

<span data-ttu-id="d4368-343">若要向用户分配 AllowCalling 调用策略和 AllOn 会议策略，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d4368-343">To assign the AllowCalling calling policy and the AllOn meeting policy to a user:</span></span>

1. <span data-ttu-id="d4368-344">在 Microsoft Teams 管理中心的左侧导航栏中，转到"用户 **"。**</span><span class="sxs-lookup"><span data-stu-id="d4368-344">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="d4368-345">单击用户名的左侧以选择用户，然后单击“编辑设置”。</span><span class="sxs-lookup"><span data-stu-id="d4368-345">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="d4368-346">执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d4368-346">Do the following:</span></span>
    1.  <span data-ttu-id="d4368-347">在 **"调用策略"** 下，单击 **"AllowCalling"。**</span><span class="sxs-lookup"><span data-stu-id="d4368-347">Under **Calling policy**, click **AllowCalling**.</span></span>
    2.  <span data-ttu-id="d4368-348">在"**会议策略"** 下，单击 **"AllOn"。**</span><span class="sxs-lookup"><span data-stu-id="d4368-348">Under **Meeting policy**, click **AllOn**.</span></span>
4. <span data-ttu-id="d4368-349">单击“**应用**”。</span><span class="sxs-lookup"><span data-stu-id="d4368-349">Click **Apply**.</span></span>

<span data-ttu-id="d4368-350">若要一次向多个用户分配策略，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d4368-350">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="d4368-351">在 Microsoft Teams 管理中心的左侧导航栏中，转到“**用户**”，然后搜索用户或筛选视图，以显示所需的用户。</span><span class="sxs-lookup"><span data-stu-id="d4368-351">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="d4368-352">在 **&#x2713;**（复选标记）列，选择用户。</span><span class="sxs-lookup"><span data-stu-id="d4368-352">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="d4368-353">若要选择所有用户， **请单击&#x2713;(** 表) "复选框。</span><span class="sxs-lookup"><span data-stu-id="d4368-353">To select all users, click the **&#x2713;** (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="d4368-354">单击“**编辑设置**”，执行所需的更改，然后单击“**应用**”。</span><span class="sxs-lookup"><span data-stu-id="d4368-354">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>

<span data-ttu-id="d4368-355">或者，也可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d4368-355">Or, you can also do the following:</span></span>

1. <span data-ttu-id="d4368-356">在 Microsoft Teams 管理中心的左侧导航栏中，转到要分配的策略。</span><span class="sxs-lookup"><span data-stu-id="d4368-356">In the left navigation of the Microsoft Teams admin center, go to the policy you want to assign.</span></span> <span data-ttu-id="d4368-357">例如：</span><span class="sxs-lookup"><span data-stu-id="d4368-357">For example:</span></span>
    - <span data-ttu-id="d4368-358">转到"**语音**  >  **呼叫策略"，** 然后单击 **"AllowCalling"。**</span><span class="sxs-lookup"><span data-stu-id="d4368-358">Go to **Voice** > **Calling policies**, and then click **AllowCalling**.</span></span>
    - <span data-ttu-id="d4368-359">转到"**会议**  >  **会议策略"，** 然后单击 **"AllOn"。**</span><span class="sxs-lookup"><span data-stu-id="d4368-359">Go to **Meetings** > **Meeting policies**, and then click **AllOn**.</span></span>
2. <span data-ttu-id="d4368-360">选择“管理用户”。</span><span class="sxs-lookup"><span data-stu-id="d4368-360">Select **Manage users**.</span></span>
3. <span data-ttu-id="d4368-361">在“管理用户”窗格中，按显示名称或用户名搜索用户，选择用户名，然后单击“添加”。</span><span class="sxs-lookup"><span data-stu-id="d4368-361">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="d4368-362">对想要添加的每一个用户重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="d4368-362">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="d4368-363">添加完用户后，单击"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="d4368-363">When you're finished adding users, click **Save**.</span></span>

#### <a name="assign-policies-using-powershell"></a><span data-ttu-id="d4368-364">使用 PowerShell 分配策略</span><span class="sxs-lookup"><span data-stu-id="d4368-364">Assign policies using PowerShell</span></span>

<span data-ttu-id="d4368-365">以下示例演示如何使用 [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) 将 AllowCalling 调用策略分配给用户。</span><span class="sxs-lookup"><span data-stu-id="d4368-365">The following example shows how to use the [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) to assign the AllowCalling calling policy to a user.</span></span>

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName AllowCalling -Identity "user email id"
```

<span data-ttu-id="d4368-366">若要详细了解使用 PowerShell 管理调用策略，请参阅[Set-CsTeamsCallingPolicy。](/powershell/module/skype/set-csteamscallingpolicy)</span><span class="sxs-lookup"><span data-stu-id="d4368-366">To learn more about using PowerShell to manage calling policies, see [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy).</span></span>

<span data-ttu-id="d4368-367">以下示例演示如何使用 [Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) 将 AllOn 会议策略分配给用户。</span><span class="sxs-lookup"><span data-stu-id="d4368-367">The following example shows how to use the [Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) to assign the AllOn meeting policy to a user.</span></span>

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOn -Identity "user email id"
```

<span data-ttu-id="d4368-368">若要详细了解使用 PowerShell 管理会议策略，请参阅[Set-CsTeamsMeetingPolicy。](/powershell/module/skype/set-csteamsmeetingpolicy)</span><span class="sxs-lookup"><span data-stu-id="d4368-368">To learn more about using PowerShell to manage meeting policies, see [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy).</span></span>

## <a name="control-fallback-mode-in-teams"></a><span data-ttu-id="d4368-369">在 Teams 中控制回退模式</span><span class="sxs-lookup"><span data-stu-id="d4368-369">Control fallback mode in Teams</span></span>

<span data-ttu-id="d4368-370">当用户从不受支持的终结点进行连接时，用户会进入回退模式，其中 AV 未优化。</span><span class="sxs-lookup"><span data-stu-id="d4368-370">When users connect from an unsupported endpoint, the users are in fallback mode, in which AV isn't optimized.</span></span> <span data-ttu-id="d4368-371">可以通过设置以下注册表 DWORD 值之一来禁用或启用回退模式：</span><span class="sxs-lookup"><span data-stu-id="d4368-371">You can disable or enable fallback mode by setting one of the following registry DWORD values:</span></span>

- <span data-ttu-id="d4368-372">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Teams\DisableFallback</span><span class="sxs-lookup"><span data-stu-id="d4368-372">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Teams\DisableFallback</span></span>
- <span data-ttu-id="d4368-373">HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\Teams\DisableFallback</span><span class="sxs-lookup"><span data-stu-id="d4368-373">HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\Teams\DisableFallback</span></span>

<span data-ttu-id="d4368-374">若要禁用回退模式，将值设置为 **1。**</span><span class="sxs-lookup"><span data-stu-id="d4368-374">To disable fallback mode, set the value to **1**.</span></span> <span data-ttu-id="d4368-375">若要仅启用音频，将值设置为 **2。**</span><span class="sxs-lookup"><span data-stu-id="d4368-375">To enable audio only, set the value to **2**.</span></span> <span data-ttu-id="d4368-376">如果该值不存在或设置为 **0** (零) ，则启用回退模式。</span><span class="sxs-lookup"><span data-stu-id="d4368-376">If the value isn't present or is set to **0** (zero), fallback mode is enabled.</span></span>

<span data-ttu-id="d4368-377">此功能在 Teams 版本 1.3.00.13565 及更高版本中可用。</span><span class="sxs-lookup"><span data-stu-id="d4368-377">This feature is available in Teams version 1.3.00.13565 and later.</span></span>

## <a name="known-issues-and-limitations"></a><span data-ttu-id="d4368-378">已知问题和限制</span><span class="sxs-lookup"><span data-stu-id="d4368-378">Known issues and limitations</span></span>

### <a name="client-deployment-installation-and-setup"></a><span data-ttu-id="d4368-379">客户端部署、安装和设置</span><span class="sxs-lookup"><span data-stu-id="d4368-379">Client deployment, installation, and setup</span></span>

- <span data-ttu-id="d4368-380">通过每台计算机安装，VDI 上的 Teams 不会以非 VDI Teams 客户端的方式自动更新。</span><span class="sxs-lookup"><span data-stu-id="d4368-380">With per-machine installation, Teams on VDI isn't automatically updated in the way that non-VDI Teams clients are.</span></span> <span data-ttu-id="d4368-381">必须安装新的 MSI 来更新 VM 映像，如在 VDI 上安装或更新 [Teams 桌面应用](#install-or-update-the-teams-desktop-app-on-vdi) 部分中所述。</span><span class="sxs-lookup"><span data-stu-id="d4368-381">You have to update the VM image by installing a new MSI as described in the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.</span></span> <span data-ttu-id="d4368-382">必须卸载当前版本，以更新到较新版本。</span><span class="sxs-lookup"><span data-stu-id="d4368-382">You must uninstall the current version to update to a newer version.</span></span>
- <span data-ttu-id="d4368-383">在 Citrix 环境中，如果用户在 Teams 运行时从虚拟机断开连接，则 Teams 更新可能会导致用户在重新连接时为 AV 保持未优化状态。</span><span class="sxs-lookup"><span data-stu-id="d4368-383">In Citrix environments, if the user disconnects from the Virtual Machine while Teams is running, Teams updates can result in the user to be in a non-optimized state for AV when they reconnect.</span></span> <span data-ttu-id="d4368-384">建议用户在从 Citrix 虚拟机断开连接之前退出 Teams，以避免这种情况。</span><span class="sxs-lookup"><span data-stu-id="d4368-384">We recommend that users quit Teams before they disconnect from Citrix Virtual Machine to avoid this scenario.</span></span>
- <span data-ttu-id="d4368-385">应按用户或每台计算机部署团队。</span><span class="sxs-lookup"><span data-stu-id="d4368-385">Teams should be deployed either per user or per machine.</span></span> <span data-ttu-id="d4368-386">不支持针对每个用户和每台计算机的并发部署 Teams。</span><span class="sxs-lookup"><span data-stu-id="d4368-386">Deployment of Teams for concurrent per user and per machine is not supported.</span></span> <span data-ttu-id="d4368-387">若要从每台计算机或每个用户迁移到其中一种模式，请按照卸载过程操作并重新部署到任一模式。</span><span class="sxs-lookup"><span data-stu-id="d4368-387">To migrate from either per machine or per user to one of these modes, follow the uninstall procedure and redeploy to either mode.</span></span>
- <span data-ttu-id="d4368-388">Windows 虚拟桌面和 VMware 目前不支持基于 MacOS 和 Linux 的客户端。</span><span class="sxs-lookup"><span data-stu-id="d4368-388">Windows Virtual Desktop and VMware don't support MacOS and Linux-based clients at this time.</span></span>

### <a name="calling-and-meetings"></a><span data-ttu-id="d4368-389">呼叫和会议</span><span class="sxs-lookup"><span data-stu-id="d4368-389">Calling and meetings</span></span>

<span data-ttu-id="d4368-390">不支持以下呼叫和会议功能：</span><span class="sxs-lookup"><span data-stu-id="d4368-390">The following calling and meeting features are not supported:</span></span>

- <span data-ttu-id="d4368-391">任何多窗口功能（如新会议体验）或新会议体验附带的任何功能</span><span class="sxs-lookup"><span data-stu-id="d4368-391">Any multi-window functionality like the new meeting experiences or any functionality that comes with the new meeting experience</span></span>
- <span data-ttu-id="d4368-392">增强型紧急服务</span><span class="sxs-lookup"><span data-stu-id="d4368-392">Enhanced emergency services</span></span>
- <span data-ttu-id="d4368-393">Teams 应用和设备之间的 HID 按钮和 LED 控件</span><span class="sxs-lookup"><span data-stu-id="d4368-393">HID buttons and LED controls between the Teams app and devices</span></span>
- <span data-ttu-id="d4368-394">背景模糊和效果</span><span class="sxs-lookup"><span data-stu-id="d4368-394">Background blur and effects</span></span>
- <span data-ttu-id="d4368-395">广播和实时事件制作者和演示者角色</span><span class="sxs-lookup"><span data-stu-id="d4368-395">Broadcast and live event producer and presenter roles</span></span>
- <span data-ttu-id="d4368-396">Location-Based LBR (路由) </span><span class="sxs-lookup"><span data-stu-id="d4368-396">Location-Based Routing (LBR)</span></span>
- <span data-ttu-id="d4368-397">呼叫寄存</span><span class="sxs-lookup"><span data-stu-id="d4368-397">Call park</span></span>
- <span data-ttu-id="d4368-398">呼叫队列</span><span class="sxs-lookup"><span data-stu-id="d4368-398">Call queue</span></span>
- <span data-ttu-id="d4368-399">共享系统音频/计算机声音</span><span class="sxs-lookup"><span data-stu-id="d4368-399">Shared system audio/computer sound</span></span>
- <span data-ttu-id="d4368-400">直接路由的媒体旁路</span><span class="sxs-lookup"><span data-stu-id="d4368-400">Media bypass for Direct Routing</span></span>
- <span data-ttu-id="d4368-401">缩放控件</span><span class="sxs-lookup"><span data-stu-id="d4368-401">Zoom control</span></span> 

> [!NOTE]
> <span data-ttu-id="d4368-402">我们正在努力添加当前仅在非 VDI 环境中可用的呼叫和会议功能。</span><span class="sxs-lookup"><span data-stu-id="d4368-402">We're working on adding calling and meeting features that are currently only available in non-VDI environments.</span></span> <span data-ttu-id="d4368-403">这些可能包括对质量的更多管理员控制、其他屏幕共享方案和最近添加到 Teams 的高级功能。</span><span class="sxs-lookup"><span data-stu-id="d4368-403">These might include more admin control over quality, additional screen sharing scenarios, and advanced features recently added to Teams.</span></span> <span data-ttu-id="d4368-404">请联系 Teams 代表，详细了解即将推出的功能。</span><span class="sxs-lookup"><span data-stu-id="d4368-404">Contact your Teams representative to learn more about upcoming features.</span></span>

<span data-ttu-id="d4368-405">以下是呼叫和会议的已知问题和限制：</span><span class="sxs-lookup"><span data-stu-id="d4368-405">The following are known issues and limitations for calling and meetings:</span></span>

- <span data-ttu-id="d4368-406">Skype for Business 的互操作性仅限于音频通话;没有视频形式。</span><span class="sxs-lookup"><span data-stu-id="d4368-406">Interoperability with Skype for Business is limited to audio calls; there is no video modality.</span></span>
- <span data-ttu-id="d4368-407">会议或群组通话仅支持单个传入视频流。</span><span class="sxs-lookup"><span data-stu-id="d4368-407">Only a single incoming video stream is supported in meetings or group calls.</span></span> <span data-ttu-id="d4368-408">当多人发送视频时，在任何给定时间只显示主要发言人的视频。</span><span class="sxs-lookup"><span data-stu-id="d4368-408">When multiple people send video, only the dominant speaker's video is shown at any given time.</span></span>
- <span data-ttu-id="d4368-409">传入和传出视频流分辨率限制为 720p 分辨率。</span><span class="sxs-lookup"><span data-stu-id="d4368-409">Incoming and outgoing video stream resolution is limited to 720p resolution.</span></span> <span data-ttu-id="d4368-410">这是 WebRTC 限制。</span><span class="sxs-lookup"><span data-stu-id="d4368-410">This is a WebRTC limitation.</span></span>
- <span data-ttu-id="d4368-411">仅支持来自传入相机或屏幕共享流的一个视频流。</span><span class="sxs-lookup"><span data-stu-id="d4368-411">Only one video stream from an incoming camera or screen share stream is supported.</span></span> <span data-ttu-id="d4368-412">当存在传入的屏幕共享时，将显示该屏幕共享，而不是主扬声器的视频。</span><span class="sxs-lookup"><span data-stu-id="d4368-412">When there's an incoming screen share, that screen share is shown, instead of the video of the dominant speaker.</span></span>
- <span data-ttu-id="d4368-413">如果设备断开连接，然后重新连接，Teams 不会切换为使用用户选择的最后一个音频设备。</span><span class="sxs-lookup"><span data-stu-id="d4368-413">Teams doesn't switch to use the last audio device that a user selected, if the device is disconnected, and then reconnected.</span></span>
- <span data-ttu-id="d4368-414">传出屏幕共享：</span><span class="sxs-lookup"><span data-stu-id="d4368-414">Outgoing screen sharing:</span></span>
    - <span data-ttu-id="d4368-415">不支持应用程序共享。</span><span class="sxs-lookup"><span data-stu-id="d4368-415">Application sharing is not supported.</span></span>
- <span data-ttu-id="d4368-416">授予控制权并控制：</span><span class="sxs-lookup"><span data-stu-id="d4368-416">Give control and take control:</span></span>
    - <span data-ttu-id="d4368-417">在屏幕共享或应用程序共享会话期间不受支持。</span><span class="sxs-lookup"><span data-stu-id="d4368-417">Not supported during a screen sharing or application sharing session.</span></span>
    - <span data-ttu-id="d4368-418">在 PowerPoint 共享会话期间受支持。</span><span class="sxs-lookup"><span data-stu-id="d4368-418">Supported during a PowerPoint sharing session.</span></span>
- <span data-ttu-id="d4368-419">仅 Citrix 限制</span><span class="sxs-lookup"><span data-stu-id="d4368-419">Citrix-only limitations</span></span>
    - <span data-ttu-id="d4368-420">在多监视器设置中共享屏幕时，仅共享主监视器。</span><span class="sxs-lookup"><span data-stu-id="d4368-420">When screen sharing in a multi-monitor setup, only the main monitor is shared.</span></span>
    - <span data-ttu-id="d4368-421">不支持在 CWA 上高 DPI 缩放。</span><span class="sxs-lookup"><span data-stu-id="d4368-421">High DPI scaling on CWA is not supported.</span></span>

<span data-ttu-id="d4368-422">有关与 VDI 不相关的 Teams 已知问题，请参阅[在组织中支持 Teams。](/MicrosoftTeams/troubleshoot/teams-welcome)</span><span class="sxs-lookup"><span data-stu-id="d4368-422">For Teams known issues that aren't related to VDI, see [Support Teams in your organization](/MicrosoftTeams/troubleshoot/teams-welcome).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="d4368-423">疑难解答</span><span class="sxs-lookup"><span data-stu-id="d4368-423">Troubleshooting</span></span>

### <a name="troubleshoot-citrix-components"></a><span data-ttu-id="d4368-424">Citrix 组件故障排除</span><span class="sxs-lookup"><span data-stu-id="d4368-424">Troubleshoot Citrix components</span></span>

#### <a name="teams-crashes-or-the-teams-sign-in-screen-is-blank"></a><span data-ttu-id="d4368-425">Teams 崩溃或 Teams 登录屏幕为空</span><span class="sxs-lookup"><span data-stu-id="d4368-425">Teams crashes or the Teams sign in screen is blank</span></span>

<span data-ttu-id="d4368-426">这是 Citrix VDA 版本 1906 和 1909 的已知问题。</span><span class="sxs-lookup"><span data-stu-id="d4368-426">This is a known issue with Citrix VDA versions 1906 and 1909.</span></span> <span data-ttu-id="d4368-427">若要解决此问题，请添加以下注册表 DWORD 值，将其设置为 204 (十六进制) 。</span><span class="sxs-lookup"><span data-stu-id="d4368-427">To work around this issue, add the following registry DWORD value, and set it to 204 (hexadecimal).</span></span>

<span data-ttu-id="d4368-428">HKEY_LOCAL_MACHINE\SOFTWARE\Citrix\CtxHook\AppInit_Dlls\SfrHook\Teams.exe</span><span class="sxs-lookup"><span data-stu-id="d4368-428">HKEY_LOCAL_MACHINE\SOFTWARE\Citrix\CtxHook\AppInit_Dlls\SfrHook\Teams.exe</span></span>

<span data-ttu-id="d4368-429">然后重启 VDA。</span><span class="sxs-lookup"><span data-stu-id="d4368-429">Then, restart VDA.</span></span> <span data-ttu-id="d4368-430">有关详细信息，请参阅此 Citrix 支持文章 [Teams 的 HDX 优化故障排除](https://support.citrix.com/article/CTX253754)。</span><span class="sxs-lookup"><span data-stu-id="d4368-430">To learn more, see this Citrix support article, [Troubleshooting HDX optimization for Teams](https://support.citrix.com/article/CTX253754).</span></span>

## <a name="related-topics"></a><span data-ttu-id="d4368-431">相关主题</span><span class="sxs-lookup"><span data-stu-id="d4368-431">Related topics</span></span>

- [<span data-ttu-id="d4368-432">使用 MSI 安装 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d4368-432">Install Microsoft Teams using MSI</span></span>](msi-deployment.md)
- [<span data-ttu-id="d4368-433">Teams PowerShell 概览</span><span class="sxs-lookup"><span data-stu-id="d4368-433">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="d4368-434">在 Windows 虚拟桌面上使用 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d4368-434">Use Microsoft Teams on Windows Virtual desktop</span></span>](/azure/virtual-desktop/teams-on-wvd)
