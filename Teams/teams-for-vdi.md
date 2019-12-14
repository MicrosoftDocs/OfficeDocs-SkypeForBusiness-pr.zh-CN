---
title: 适用于虚拟化桌面基础结构的 Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rafarhi, jmorrow
audience: admin
description: 了解如何在虚拟桌面基础结构（VDI）环境中运行 Microsoft 团队。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fd9440ce7c4d35af28e577c9d9e01845f298ef01
ms.sourcegitcommit: c15ab82834005b9a19247e06488f1f21161fc426
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/13/2019
ms.locfileid: "40020056"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a><span data-ttu-id="c268e-103">适用于虚拟化桌面基础结构的 Teams</span><span class="sxs-lookup"><span data-stu-id="c268e-103">Teams for Virtualized Desktop Infrastructure</span></span>

<span data-ttu-id="c268e-104">本文介绍在虚拟化环境中使用 Microsoft 团队的要求和限制。</span><span class="sxs-lookup"><span data-stu-id="c268e-104">This article describes the requirements and limitations for using Microsoft Teams in a virtualized environment.</span></span>

## <a name="what-is-vdi"></a><span data-ttu-id="c268e-105">什么是 VDI？</span><span class="sxs-lookup"><span data-stu-id="c268e-105">What is VDI?</span></span>

<span data-ttu-id="c268e-106">虚拟桌面基础结构（VDI）是在数据中心的集中式服务器上托管桌面操作系统和应用程序的虚拟化技术。</span><span class="sxs-lookup"><span data-stu-id="c268e-106">Virtual Desktop Infrastructure (VDI) is virtualization technology that hosts a desktop operating system and applications on a centralized server in a data center.</span></span> <span data-ttu-id="c268e-107">这使具有完全安全和合规的集中源的用户能够获得完全个性化的桌面体验。</span><span class="sxs-lookup"><span data-stu-id="c268e-107">This enables a fully personalized desktop experience to users with a fully secured and compliant centralized source.</span></span>
 
<span data-ttu-id="c268e-108">虚拟环境中的 Microsoft 团队支持聊天和协作，并且通过 Citrix 平台，还支持调用和会议功能。</span><span class="sxs-lookup"><span data-stu-id="c268e-108">Microsoft Teams in a virtualized environment supports chat and collaboration, and with the Citrix platform, calling and meeting functionality are also supported.</span></span>

<span data-ttu-id="c268e-109">虚拟环境中的团队支持多个配置。</span><span class="sxs-lookup"><span data-stu-id="c268e-109">Teams in a virtualized environment supports multiple configurations.</span></span> <span data-ttu-id="c268e-110">其中包括 VDI、专用、共享、持久和非持久模式。</span><span class="sxs-lookup"><span data-stu-id="c268e-110">These include VDI, dedicated, shared, persistent and non-persistent modes.</span></span> <span data-ttu-id="c268e-111">功能在连续开发中且定期添加，并且功能将在未来的几个月和几年内扩展。</span><span class="sxs-lookup"><span data-stu-id="c268e-111">Features are in continuous development and are added on a regular basis, and functionality will expand in the coming months and years.</span></span>
 
<span data-ttu-id="c268e-112">在虚拟化环境中使用团队可能与在非虚拟化环境中使用团队稍有不同。</span><span class="sxs-lookup"><span data-stu-id="c268e-112">Using Teams in a virtualized environment may be somewhat different from using Teams in a non-virtualized environment.</span></span> <span data-ttu-id="c268e-113">例如，某些高级功能在虚拟化环境中可能不可用，并且视频分辨率可能有所不同。</span><span class="sxs-lookup"><span data-stu-id="c268e-113">For example, some advanced features may not be available in a virtualized environment and video resolution may differ.</span></span> <span data-ttu-id="c268e-114">若要确保获得最佳的用户体验，请按照本文中的指南操作。</span><span class="sxs-lookup"><span data-stu-id="c268e-114">To ensure an optimal user experience, follow the guidance in this article.</span></span>

## <a name="teams-on-vdi-components"></a><span data-ttu-id="c268e-115">VDI 组件上的团队</span><span class="sxs-lookup"><span data-stu-id="c268e-115">Teams on VDI components</span></span>

<span data-ttu-id="c268e-116">在虚拟化环境中使用团队需要以下组件。</span><span class="sxs-lookup"><span data-stu-id="c268e-116">Using Teams in a virtualized environment requires the following components.</span></span>

- <span data-ttu-id="c268e-117">**虚拟化代理**：针对虚拟化提供程序的资源和连接管理器，例如 Azure</span><span class="sxs-lookup"><span data-stu-id="c268e-117">**Virtualization broker**: The resource and connection manager to the virtualization provider, such as Azure</span></span>
- <span data-ttu-id="c268e-118">**虚拟桌面**：运行 Microsoft 团队的虚拟机（VM）堆栈</span><span class="sxs-lookup"><span data-stu-id="c268e-118">**Virtual desktop**: The Virtual Machine (VM) stack that runs Microsoft Teams</span></span>
- <span data-ttu-id="c268e-119">**瘦客户端**：用户使用物理接口的终结点</span><span class="sxs-lookup"><span data-stu-id="c268e-119">**Thin client**: The endpoint that the user physically interfaces with</span></span>
- <span data-ttu-id="c268e-120">**团队桌面应用**：这是团队桌面客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="c268e-120">**Teams desktop app**: This is the Teams desktop client app</span></span>

## <a name="teams-on-vdi-requirements"></a><span data-ttu-id="c268e-121">VDI 要求的团队</span><span class="sxs-lookup"><span data-stu-id="c268e-121">Teams on VDI requirements</span></span>

### <a name="virtualization-provider-requirements"></a><span data-ttu-id="c268e-122">虚拟化提供商要求</span><span class="sxs-lookup"><span data-stu-id="c268e-122">Virtualization provider requirements</span></span>

<span data-ttu-id="c268e-123">团队桌面应用已通过主流虚拟化解决方案提供商进行验证。</span><span class="sxs-lookup"><span data-stu-id="c268e-123">The Teams desktop app was validated with leading virtualization solution providers.</span></span> <span data-ttu-id="c268e-124">有了多个市场提供商，我们建议你咨询你的虚拟化解决方案提供商以确保满足最低要求。</span><span class="sxs-lookup"><span data-stu-id="c268e-124">With multiple market providers, we recommend that you consult your virtualization solution provider to ensure minimum requirements are met.</span></span>
  
<span data-ttu-id="c268e-125">目前，带有音频/视频（AV）优化的团队在通过 Citrix 认证。</span><span class="sxs-lookup"><span data-stu-id="c268e-125">Currently, Teams on VDI with audio/video (AV) optimization is certified with Citrix.</span></span> <span data-ttu-id="c268e-126">查看本部分中的信息，确保同时满足 Citrix 和团队要求才能获得正确的功能。</span><span class="sxs-lookup"><span data-stu-id="c268e-126">Review the information in this section to ensure both Citrix and Teams requirements are met for proper functionality.</span></span>

### <a name="partners-certified-for-teams"></a><span data-ttu-id="c268e-127">合作伙伴认证的团队</span><span class="sxs-lookup"><span data-stu-id="c268e-127">Partners certified for Teams</span></span>

<span data-ttu-id="c268e-128">以下合作伙伴拥有团队的虚拟桌面基础结构解决方案。</span><span class="sxs-lookup"><span data-stu-id="c268e-128">The following partners have virtual desktop infrastructure solutions for Teams.</span></span>

|<span data-ttu-id="c268e-129">配偶</span><span class="sxs-lookup"><span data-stu-id="c268e-129">Partner</span></span>|<span data-ttu-id="c268e-130">合作伙伴解决方案</span><span class="sxs-lookup"><span data-stu-id="c268e-130">Partner solution</span></span>|
|----|---|
|![表示 Citrix 的徽标](media/citrix.png)| <span data-ttu-id="c268e-132"><a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Citrix 虚拟应用和桌面</a></span><span class="sxs-lookup"><span data-stu-id="c268e-132"><a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Citrix Virtual Apps and Desktops</a></span></span> |

### <a name="citrix-virtual-apps-and-desktops-requirements"></a><span data-ttu-id="c268e-133">Citrix 虚拟应用和桌面要求</span><span class="sxs-lookup"><span data-stu-id="c268e-133">Citrix Virtual Apps and Desktops requirements</span></span>

<span data-ttu-id="c268e-134">Citrix 虚拟应用和桌面（以前称为 XenApp 和 XenDesktop）为适用于 VDI 的团队提供 AV 优化。</span><span class="sxs-lookup"><span data-stu-id="c268e-134">Citrix Virtual Apps and Desktops (formerly known as XenApp and XenDesktop) provides AV optimization for Teams on VDI.</span></span> <span data-ttu-id="c268e-135">通过 Citrix 虚拟应用和桌面，VDI 上的团队不仅支持聊天和协作，还支持呼叫和会议功能。</span><span class="sxs-lookup"><span data-stu-id="c268e-135">With Citrix Virtual Apps and Desktops, Teams on VDI supports calling and meeting functionality in addition to chat and collaboration.</span></span>

<span data-ttu-id="c268e-136">你可以在[此处](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/)下载 Citrix 虚拟应用和桌面的最新版本。</span><span class="sxs-lookup"><span data-stu-id="c268e-136">You can download the latest version of Citrix Virtual Apps and Desktops [here](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/).</span></span> <span data-ttu-id="c268e-137">（您需要首先登录。）默认情况下，必要的组件捆绑到[Citrix 工作区应用（CWA）](https://www.citrix.com/downloads/workspace-app/)和虚拟交付代理（VDA）中。</span><span class="sxs-lookup"><span data-stu-id="c268e-137">(You'll need to sign in first.) The necessary components are bundled into the [Citrix Workspace app (CWA)](https://www.citrix.com/downloads/workspace-app/) and Virtual Delivery Agent (VDA) by default.</span></span> <span data-ttu-id="c268e-138">无需在 CWA 或 VDA 上安装任何其他组件或插件。</span><span class="sxs-lookup"><span data-stu-id="c268e-138">You don't need to install any additional components or plugins on CWA or the VDA.</span></span>

<span data-ttu-id="c268e-139">有关最新的服务器和客户端要求，请参阅[此 Citrix 网站](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html)。</span><span class="sxs-lookup"><span data-stu-id="c268e-139">For the latest server and client requirements, see [this Citrix website](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html).</span></span>

## <a name="install-or-update-the-teams-desktop-app-on-vdi"></a><span data-ttu-id="c268e-140">在 VDI 上安装或更新团队桌面应用</span><span class="sxs-lookup"><span data-stu-id="c268e-140">Install or update the Teams desktop app on VDI</span></span>

<span data-ttu-id="c268e-141">你可以使用 MSI 程序包使用每台计算机安装或每用户安装来部署适用于 VDI 的团队桌面应用。</span><span class="sxs-lookup"><span data-stu-id="c268e-141">You can deploy the Teams desktop app for VDI using a per-machine installation or per-user installation using the MSI package.</span></span> <span data-ttu-id="c268e-142">决定使用哪种方法取决于您使用的是持久设置还是非持久设置以及您的组织的相关功能需求。</span><span class="sxs-lookup"><span data-stu-id="c268e-142">Deciding on which approach to use depends on whether you use a persistent or non-persistent setup and the associated functionality needs of your organization.</span></span>
<span data-ttu-id="c268e-143">对于专用的永久设置，这两种方法都适用。</span><span class="sxs-lookup"><span data-stu-id="c268e-143">For a dedicated persistent setup, either approach would work.</span></span>  <span data-ttu-id="c268e-144">但是，对于非持久设置，团队需要每计算机安装才能高效工作。</span><span class="sxs-lookup"><span data-stu-id="c268e-144">However, for a non-persistent setup, per-machine installation is required for Teams to work efficiently.</span></span> <span data-ttu-id="c268e-145">请参阅[非持久设置](#non-persistent-setup)部分。</span><span class="sxs-lookup"><span data-stu-id="c268e-145">See the [Non-persistent setup](#non-persistent-setup) section.</span></span>

<span data-ttu-id="c268e-146">对于每台计算机安装，自动更新已禁用。</span><span class="sxs-lookup"><span data-stu-id="c268e-146">With per-machine installation, automatic updates is disabled.</span></span> <span data-ttu-id="c268e-147">这意味着，若要更新团队应用，必须卸载当前版本才能更新到较新的版本。</span><span class="sxs-lookup"><span data-stu-id="c268e-147">This means that to update the Teams app, you must uninstall the current version to update to a newer version.</span></span> <span data-ttu-id="c268e-148">对于每用户安装，自动更新已启用。</span><span class="sxs-lookup"><span data-stu-id="c268e-148">With per-user installation, automatic updates is enabled.</span></span> <span data-ttu-id="c268e-149">对于大多数 VDI 部署，建议使用每台计算机安装部署团队。</span><span class="sxs-lookup"><span data-stu-id="c268e-149">For most VDI deployments, we recommend you deploy Teams using per-machine installation.</span></span>

<span data-ttu-id="c268e-150">若要更新到最新的团队版本，请从卸载过程开始，后跟最新的团队版本部署。</span><span class="sxs-lookup"><span data-stu-id="c268e-150">To update to the latest Teams version, start with the uninstall procedure followed by latest Teams version deployment.</span></span>

<span data-ttu-id="c268e-151">为了使 VDI 环境中的团队防病毒优化正常工作，瘦客户端终结点必须有权访问 internet。</span><span class="sxs-lookup"><span data-stu-id="c268e-151">For Teams AV optimization in VDI environments to work properly, the thin client endpoint must have access to the internet.</span></span> <span data-ttu-id="c268e-152">如果在瘦客户端终结点上无法访问 internet，优化启动将不会成功。</span><span class="sxs-lookup"><span data-stu-id="c268e-152">If internet access isn't available at the thin client endpoint, optimization startup won't be successful.</span></span> <span data-ttu-id="c268e-153">这意味着用户处于非优化的媒体状态。</span><span class="sxs-lookup"><span data-stu-id="c268e-153">This means that the user is in a non-optimized media state.</span></span>

#### <a name="dedicated-persistent-setup"></a><span data-ttu-id="c268e-154">专用永久设置</span><span class="sxs-lookup"><span data-stu-id="c268e-154">Dedicated persistent setup</span></span>

<span data-ttu-id="c268e-155">在专用的永久设置中，用户注销后，将保留用户的本地操作系统更改。</span><span class="sxs-lookup"><span data-stu-id="c268e-155">In a dedicated persistent setup, users' local operating system changes are retained after users log off.</span></span>  <span data-ttu-id="c268e-156">对于永久设置，团队同时支持每用户和每计算机安装。</span><span class="sxs-lookup"><span data-stu-id="c268e-156">For persistent setup, Teams support both per-user and per-machine installation.</span></span>

<span data-ttu-id="c268e-157">以下是推荐的最低 VM 配置。</span><span class="sxs-lookup"><span data-stu-id="c268e-157">The following is the recommended minimum VM configuration.</span></span>

|<span data-ttu-id="c268e-158">参数</span><span class="sxs-lookup"><span data-stu-id="c268e-158">Parameter</span></span>  |<span data-ttu-id="c268e-159">工作站操作系统</span><span class="sxs-lookup"><span data-stu-id="c268e-159">Workstation operating system</span></span>  |<span data-ttu-id="c268e-160">服务器操作系统</span><span class="sxs-lookup"><span data-stu-id="c268e-160">Server operation system</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="c268e-161">vCPU</span><span class="sxs-lookup"><span data-stu-id="c268e-161">vCPU</span></span>   |    <span data-ttu-id="c268e-162">2核</span><span class="sxs-lookup"><span data-stu-id="c268e-162">2 cores</span></span>     |  <span data-ttu-id="c268e-163">4、6或8</span><span class="sxs-lookup"><span data-stu-id="c268e-163">4,6, or 8</span></span><br><span data-ttu-id="c268e-164">了解基础非统一内存访问（NUMA）配置和相应配置 Vm 非常重要。</span><span class="sxs-lookup"><span data-stu-id="c268e-164">It's important to understand the underlying non-uniform memory access (NUMA) configuration and configure your VMs accordingly.</span></span>     |
|<span data-ttu-id="c268e-165">RAM</span><span class="sxs-lookup"><span data-stu-id="c268e-165">RAM</span></span>     |   <span data-ttu-id="c268e-166">4 GB</span><span class="sxs-lookup"><span data-stu-id="c268e-166">4 GB</span></span>      | <span data-ttu-id="c268e-167">每个用户512到 1024 MB</span><span class="sxs-lookup"><span data-stu-id="c268e-167">512 to 1024 MB per user</span></span>        |
|<span data-ttu-id="c268e-168">存储空间</span><span class="sxs-lookup"><span data-stu-id="c268e-168">Storage</span></span>    | <span data-ttu-id="c268e-169">8 GB</span><span class="sxs-lookup"><span data-stu-id="c268e-169">8 GB</span></span>        | <span data-ttu-id="c268e-170">40到 60 GB</span><span class="sxs-lookup"><span data-stu-id="c268e-170">40 to 60 GB</span></span>        |

#### <a name="non-persistent-setup"></a><span data-ttu-id="c268e-171">非持久设置</span><span class="sxs-lookup"><span data-stu-id="c268e-171">Non-persistent setup</span></span>

<span data-ttu-id="c268e-172">在非持久设置中，用户注销后将不保留用户的本地操作系统更改。</span><span class="sxs-lookup"><span data-stu-id="c268e-172">In a non-persistent setup, users' local operating system changes are not retained after users log off.</span></span> <span data-ttu-id="c268e-173">此类设置通常共享多用户会话。</span><span class="sxs-lookup"><span data-stu-id="c268e-173">Such setups are commonly shared multi-user sessions.</span></span> <span data-ttu-id="c268e-174">VM 配置根据用户数量和可用的物理箱资源而有所不同。</span><span class="sxs-lookup"><span data-stu-id="c268e-174">VM configuration varies based on the number of users and available physical box resources.</span></span>

<span data-ttu-id="c268e-175">对于非持久设置，必须将团队桌面应用安装到黄金图像的每台计算机上。</span><span class="sxs-lookup"><span data-stu-id="c268e-175">For a non-persistent setup, the Teams desktop app must be installed per-machine to the golden image.</span></span> <span data-ttu-id="c268e-176">（若要了解详细信息，请参阅在[VDI 部分安装或更新团队桌面应用](#install-or-update-the-teams-desktop-app-on-vdi)）。</span><span class="sxs-lookup"><span data-stu-id="c268e-176">(To learn more, see the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section).</span></span> <span data-ttu-id="c268e-177">这可确保在用户会话期间有效地启动团队应用。</span><span class="sxs-lookup"><span data-stu-id="c268e-177">This ensures an efficient launch of the Teams app during a user session.</span></span> <span data-ttu-id="c268e-178">将团队与非持久性设置配合使用时，还需要配置文件缓存管理器才能高效团队运行时数据同步。这可确保在用户会话期间缓存相应的特定于用户的信息（例如，用户数据、配置文件和设置）。</span><span class="sxs-lookup"><span data-stu-id="c268e-178">Using Teams with a non-persistent setup also requires a profile caching manager for efficient Teams runtime data sync. This ensures that the appropriate user-specific information (for example, user data, profile, and settings) are cached during the user session.</span></span>  <span data-ttu-id="c268e-179">有多种可用的缓存管理器解决方案。</span><span class="sxs-lookup"><span data-stu-id="c268e-179">There are variety of caching manager solutions available.</span></span> <span data-ttu-id="c268e-180">例如， [FSLogix](https://docs.microsoft.com/fslogix/overview)。</span><span class="sxs-lookup"><span data-stu-id="c268e-180">For example, [FSLogix](https://docs.microsoft.com/fslogix/overview).</span></span> <span data-ttu-id="c268e-181">有关特定配置说明，请咨询您的缓存管理器提供程序。</span><span class="sxs-lookup"><span data-stu-id="c268e-181">Consult your caching manager provider for specific configuration instructions.</span></span>

##### <a name="teams-cached-content-exclusion-list-for-non-persistent-setup"></a><span data-ttu-id="c268e-182">用于非持久设置的工作组缓存的内容排除列表</span><span class="sxs-lookup"><span data-stu-id="c268e-182">Teams cached content exclusion list for non-persistent setup</span></span>

<span data-ttu-id="c268e-183">从 "团队缓存" 文件夹（% appdata%/Microsoft/Teams.）中排除以下项</span><span class="sxs-lookup"><span data-stu-id="c268e-183">Exclude the following from the Teams caching folder, %appdata%/Microsoft/Teams.</span></span>  <span data-ttu-id="c268e-184">排除这些帮助将减少用户缓存大小，以进一步优化非持久设置。</span><span class="sxs-lookup"><span data-stu-id="c268e-184">Excluding these help reduce the user caching size to further optimize your non-persistent setup.</span></span>

- <span data-ttu-id="c268e-185">.txt 文件</span><span class="sxs-lookup"><span data-stu-id="c268e-185">.txt files</span></span>
- <span data-ttu-id="c268e-186">媒体堆叠文件夹</span><span class="sxs-lookup"><span data-stu-id="c268e-186">Media-stack folder</span></span>

### <a name="office-365-proplus-considerations"></a><span data-ttu-id="c268e-187">Office 365 专业增强版注意事项</span><span class="sxs-lookup"><span data-stu-id="c268e-187">Office 365 ProPlus considerations</span></span>

<span data-ttu-id="c268e-188">在 VDI 上部署具有 Office 365 专业增强版的团队时，请考虑以下事项。</span><span class="sxs-lookup"><span data-stu-id="c268e-188">Consider the following when you deploy Teams with Office 365 ProPlus on VDI.</span></span>

#### <a name="new-deployments-of-teams-through-office-365-proplus"></a><span data-ttu-id="c268e-189">通过 Office 365 专业增强版的新部署团队</span><span class="sxs-lookup"><span data-stu-id="c268e-189">New deployments of Teams through Office 365 ProPlus</span></span>

<span data-ttu-id="c268e-190">在通过 Office 365 专业增强版部署团队之前，必须先卸载任何预先存在的团队应用（如果它们是使用按计算机安装部署的）。</span><span class="sxs-lookup"><span data-stu-id="c268e-190">Before you deploy Teams through Office 365 ProPlus, you must first uninstall any pre-existing Teams apps if they were deployed using per-machine installation.</span></span>

<span data-ttu-id="c268e-191">通过 Office 365 专业增强版的团队将针对每个用户进行安装。</span><span class="sxs-lookup"><span data-stu-id="c268e-191">Teams through Office 365 ProPlus is installed per-user.</span></span> <span data-ttu-id="c268e-192">若要了解详细信息，请参阅[在 VDI 部分安装或更新团队桌面应用](#install-or-update-the-teams-desktop-app-on-vdi)。</span><span class="sxs-lookup"><span data-stu-id="c268e-192">To learn more, see the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.</span></span>

#### <a name="teams-deployments-through-office-365-proplus-updates"></a><span data-ttu-id="c268e-193">通过 Office 365 专业增强版更新的团队部署</span><span class="sxs-lookup"><span data-stu-id="c268e-193">Teams deployments through Office 365 ProPlus updates</span></span>

<span data-ttu-id="c268e-194">团队也将添加到 Office 365 专业增强版的现有安装。</span><span class="sxs-lookup"><span data-stu-id="c268e-194">Teams is also being added to existing installations of Office 365 ProPlus.</span></span> <span data-ttu-id="c268e-195">由于 Office 365 专业增强版仅为每位用户安装团队，请参阅在[VDI 部分安装或更新团队桌面应用](#install-or-update-the-teams-desktop-app-on-vdi)。</span><span class="sxs-lookup"><span data-stu-id="c268e-195">Since Office 365 ProPlus installs Teams per-user only, see the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.</span></span>

#### <a name="using-teams-with-per-machine-installation-and-office-365-proplus"></a><span data-ttu-id="c268e-196">对每台计算机安装使用团队和 Office 365 专业增强版</span><span class="sxs-lookup"><span data-stu-id="c268e-196">Using Teams with per-machine installation and Office 365 ProPlus</span></span>

<span data-ttu-id="c268e-197">Office 365 专业增强版不支持团队的每计算机安装。</span><span class="sxs-lookup"><span data-stu-id="c268e-197">Office 365 ProPlus doesn't support per-machine installations of Teams.</span></span> <span data-ttu-id="c268e-198">若要使用每台计算机安装，必须从 Office 365 专业增强版中排除团队。</span><span class="sxs-lookup"><span data-stu-id="c268e-198">To use per-machine installation, you must exclude Teams from Office 365 ProPlus.</span></span> <span data-ttu-id="c268e-199">请参阅将[团队桌面应用部署到 VM](#deploy-the-teams-desktop-app-to-the-vm)和[如何通过 Office 365 专业增强版部分排除团队部署](#how-to-exclude-teams-deployment-through-office-365-proplus)。</span><span class="sxs-lookup"><span data-stu-id="c268e-199">See the [Deploy the Teams desktop app to the VM](#deploy-the-teams-desktop-app-to-the-vm) and [How to exclude Teams deployment through Office 365 ProPlus](#how-to-exclude-teams-deployment-through-office-365-proplus) sections.</span></span>

#### <a name="how-to-exclude-teams-deployment-through-office-365-proplus"></a><span data-ttu-id="c268e-200">如何通过 Office 365 专业增强版排除团队部署</span><span class="sxs-lookup"><span data-stu-id="c268e-200">How to exclude Teams deployment through Office 365 ProPlus</span></span>

<span data-ttu-id="c268e-201">若要了解有关团队和 Office 365 专业增强版的详细信息，请参阅[如何从 Office 365 专业增强版的新安装中排除团队](https://docs.microsoft.com/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-office-365-proplus)，并[使用组策略来控制团队的安装](https://docs.microsoft.com/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams)。</span><span class="sxs-lookup"><span data-stu-id="c268e-201">To learn more about Teams and Office 365 ProPlus, see [How to exclude Teams from new installations of Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-office-365-proplus) and [Use Group Policy to control the installation of Teams](https://docs.microsoft.com/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams).</span></span>

### <a name="deploy-the-teams-desktop-app-to-the-vm"></a><span data-ttu-id="c268e-202">将团队桌面应用部署到 VM</span><span class="sxs-lookup"><span data-stu-id="c268e-202">Deploy the Teams desktop app to the VM</span></span>

1. <span data-ttu-id="c268e-203">使用以下链接之一下载与你的 VDI VM 操作系统匹配的团队 MSI 程序包。</span><span class="sxs-lookup"><span data-stu-id="c268e-203">Download the Teams MSI package that matches your VDI VM operating system using one of the following links.</span></span>

    - [<span data-ttu-id="c268e-204">32位版本</span><span class="sxs-lookup"><span data-stu-id="c268e-204">32-bit version</span></span>](https://statics.teams.microsoft.com/production-windows/1.2.00.32462/Teams_windows.msi)
    - [<span data-ttu-id="c268e-205">64位版本</span><span class="sxs-lookup"><span data-stu-id="c268e-205">64-bit version</span></span>](https://statics.teams.microsoft.com/production-windows-x64/1.2.00.32462/Teams_windows_x64.msi)

    <span data-ttu-id="c268e-206">所需的团队桌面应用的最低版本是1.2.00.31357 版本。</span><span class="sxs-lookup"><span data-stu-id="c268e-206">The minimum version of the Teams desktop app that's required is version 1.2.00.31357.</span></span> <span data-ttu-id="c268e-207">（在早期版本中不支持 PSTN 保留）</span><span class="sxs-lookup"><span data-stu-id="c268e-207">(PSTN hold is not supported in earlier versions)</span></span>

2. <span data-ttu-id="c268e-208">通过运行以下命令之一将 MSI 安装到 VDI VM：</span><span class="sxs-lookup"><span data-stu-id="c268e-208">Install the MSI to the VDI VM by running one of the following commands:</span></span>

    - <span data-ttu-id="c268e-209">每用户安装（默认）</span><span class="sxs-lookup"><span data-stu-id="c268e-209">Per-user installation  (default)</span></span>
  
        ```
        msiexec /i <path_to_msi> /l*v <install_logfile_name>
        ```
    
        <span data-ttu-id="c268e-210">这是默认安装，可将团队安装到% AppData% 用户文件夹。</span><span class="sxs-lookup"><span data-stu-id="c268e-210">This is the default installation, which installs Teams to the %AppData% user folder.</span></span> <span data-ttu-id="c268e-211">此时，将完成黄金图像设置。</span><span class="sxs-lookup"><span data-stu-id="c268e-211">At this point, the golden image setup is complete.</span></span> <span data-ttu-id="c268e-212">在非持久设置中，团队将不会在每用户安装中正常工作。</span><span class="sxs-lookup"><span data-stu-id="c268e-212">Teams will not work properly with per-user installation on a non-persistent setup.</span></span>
    
    - <span data-ttu-id="c268e-213">每计算机安装</span><span class="sxs-lookup"><span data-stu-id="c268e-213">Per-machine installation</span></span>

        ```
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1
        ```

        <span data-ttu-id="c268e-214">这会将团队安装到64位操作系统上的 "程序文件（x86）" 文件夹和32位操作系统上的 "程序文件" 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="c268e-214">This installs Teams to the Program Files (x86) folder on a 64-bit operating system and to the Program Files folder on a 32-bit operating system.</span></span> <span data-ttu-id="c268e-215">此时，将完成黄金图像设置。</span><span class="sxs-lookup"><span data-stu-id="c268e-215">At this point, the golden image setup is complete.</span></span> <span data-ttu-id="c268e-216">对于非持久设置，需要针对每台计算机安装团队。</span><span class="sxs-lookup"><span data-stu-id="c268e-216">Installing Teams per-machine is required for non-persistent setups.</span></span>
 
        <span data-ttu-id="c268e-217">下一个交互式登录会话将启动团队并要求提供凭据。</span><span class="sxs-lookup"><span data-stu-id="c268e-217">The next interactive logon session starts Teams and asks for credentials.</span></span>

3. <span data-ttu-id="c268e-218">从 VDI VM 卸载 MSI</span><span class="sxs-lookup"><span data-stu-id="c268e-218">Uninstall the MSI from the VDI VM</span></span> 

    <span data-ttu-id="c268e-219">可通过两种方式卸载团队。</span><span class="sxs-lookup"><span data-stu-id="c268e-219">There are two ways to uninstall Teams.</span></span>  
  
    - <span data-ttu-id="c268e-220">PowerShell 脚本（推荐）：你可以使用此[PowerShell 脚本](scripts/powershell-script-teams-deployment-clean-up.md)清理目标计算机或用户的团队。</span><span class="sxs-lookup"><span data-stu-id="c268e-220">PowerShell script (recommended): You can use this [PowerShell script](scripts/powershell-script-teams-deployment-clean-up.md) to clean up Teams from target machines or users.</span></span> <span data-ttu-id="c268e-221">应针对目标计算机上的每个用户执行该应用。</span><span class="sxs-lookup"><span data-stu-id="c268e-221">It should be executed for every user on a targeted machine.</span></span> 
    
    - <span data-ttu-id="c268e-222">命令行：此方法删除团队，但阻止团队重新安装。</span><span class="sxs-lookup"><span data-stu-id="c268e-222">Command line: This approach removes Teams, yet prevents re-installation of Teams.</span></span>  
    <span data-ttu-id="c268e-223">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="c268e-223">Run the following command:</span></span>
  
      ```
      msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>
      ```
      <span data-ttu-id="c268e-224">这将从 "程序文件（x86）" 文件夹或 "程序文件" 文件夹中卸载团队，具体取决于操作系统环境。</span><span class="sxs-lookup"><span data-stu-id="c268e-224">This uninstalls Teams from the Program Files (x86) folder or Program Files folder, depending on the operating system environment.</span></span>

## <a name="teams-on-vdi-performance-considerations"></a><span data-ttu-id="c268e-225">VDI 性能注意事项的团队</span><span class="sxs-lookup"><span data-stu-id="c268e-225">Teams on VDI performance considerations</span></span>

<span data-ttu-id="c268e-226">有多种虚拟化设置配置，每个配置都具有不同的优化焦点。</span><span class="sxs-lookup"><span data-stu-id="c268e-226">There are variety of virtualized setup configurations, each with a different focus for optimization.</span></span> <span data-ttu-id="c268e-227">例如，用户密度。</span><span class="sxs-lookup"><span data-stu-id="c268e-227">For example, user density.</span></span> <span data-ttu-id="c268e-228">规划时，请考虑以下事项，以帮助根据组织的工作负载需求优化设置：</span><span class="sxs-lookup"><span data-stu-id="c268e-228">When planning, consider the following to help optimize your setup based on the workload needs of your organization:</span></span>

- <span data-ttu-id="c268e-229">最低要求：某些工作负荷可能需要使用高于最低要求的资源进行设置。</span><span class="sxs-lookup"><span data-stu-id="c268e-229">Minimum requirement: Some workloads may require a setup using resources that are above the minimum requirements.</span></span> <span data-ttu-id="c268e-230">例如，使用需要更多计算资源的应用程序的开发人员的工作负荷。</span><span class="sxs-lookup"><span data-stu-id="c268e-230">For example, workloads for developers who use applications that demand more computing resources.</span></span>
- <span data-ttu-id="c268e-231">依赖关系：包括有关基础架构、工作量以及团队桌面应用之外的其他环境注意事项的依赖关系。</span><span class="sxs-lookup"><span data-stu-id="c268e-231">Dependencies: These include dependencies on infrastructure, workload, and other environmental considerations outside the Teams desktop app.</span></span>
- <span data-ttu-id="c268e-232">VDI 上已禁用的功能：团队禁用适用于 VDI 的 GPU 密集型功能，这有助于提高暂时 CPU 的利用率。</span><span class="sxs-lookup"><span data-stu-id="c268e-232">Disabled features on VDI: Teams disables GPU-intensive features for VDI, which can help improve transient CPU utilization.</span></span> <span data-ttu-id="c268e-233">已禁用以下功能：</span><span class="sxs-lookup"><span data-stu-id="c268e-233">The following features are disabled:</span></span>
    - <span data-ttu-id="c268e-234">团队 CSS 动画</span><span class="sxs-lookup"><span data-stu-id="c268e-234">Teams CSS animation</span></span>
    - <span data-ttu-id="c268e-235">Giphy 自动启动</span><span class="sxs-lookup"><span data-stu-id="c268e-235">Giphy auto-start</span></span>

## <a name="teams-on-vdi-with-calling-and-meetings"></a><span data-ttu-id="c268e-236">VDI 上的团队与呼叫和会议</span><span class="sxs-lookup"><span data-stu-id="c268e-236">Teams on VDI with calling and meetings</span></span>

<span data-ttu-id="c268e-237">除了聊天和协作，使用基于 Citrix 的平台提供与呼叫和会议支持的 VDI 团队。</span><span class="sxs-lookup"><span data-stu-id="c268e-237">In addition to chat and collaboration, Teams on VDI with calling and meeting support is available with Citrix-based platforms.</span></span> <span data-ttu-id="c268e-238">支持的功能基于 WebRTC 媒体堆栈和特定于 Citrix 的实现。</span><span class="sxs-lookup"><span data-stu-id="c268e-238">Supported features are based on the WebRTC media stack and Citrix-specific implementation.</span></span> <span data-ttu-id="c268e-239">下图概括介绍了体系结构。</span><span class="sxs-lookup"><span data-stu-id="c268e-239">The following diagram provides an overview of the architecture.</span></span>

![显示 VDI 体系结构上的团队的图表](media/teams-on-vdi-architecture.png)

<span data-ttu-id="c268e-241">不支持以下呼叫和会议功能：</span><span class="sxs-lookup"><span data-stu-id="c268e-241">These calling and meeting features are not supported:</span></span>

- <span data-ttu-id="c268e-242">增强的紧急服务</span><span class="sxs-lookup"><span data-stu-id="c268e-242">Enhanced emergency services</span></span>
- <span data-ttu-id="c268e-243">团队应用和设备之间的 HID 按钮和 LED 控件</span><span class="sxs-lookup"><span data-stu-id="c268e-243">HID buttons and LED controls between the Teams app and devices</span></span>
- <span data-ttu-id="c268e-244">背景模糊和效果</span><span class="sxs-lookup"><span data-stu-id="c268e-244">Background blur and effects</span></span>
- <span data-ttu-id="c268e-245">广播/实时事件</span><span class="sxs-lookup"><span data-stu-id="c268e-245">Broadcast/live events</span></span>
- <span data-ttu-id="c268e-246">基于位置的路由（LBR）</span><span class="sxs-lookup"><span data-stu-id="c268e-246">Location-Based Routing (LBR)</span></span>
- <span data-ttu-id="c268e-247">呼叫寄存</span><span class="sxs-lookup"><span data-stu-id="c268e-247">Call park</span></span>
- <span data-ttu-id="c268e-248">通话队列</span><span class="sxs-lookup"><span data-stu-id="c268e-248">Call queue</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c268e-249">如果当前在 VDI 中运行团队没有 AV 优化，并且你使用尚不支持的功能（例如，在应用共享时授予和控制），则必须设置 Citrix 策略以关闭团队重定向。</span><span class="sxs-lookup"><span data-stu-id="c268e-249">If you currently run Teams without AV optimization in VDI and you use features that are not supported yet for optimization (such as Give and take control when app sharing), you have to set Citrix policies to turn off Teams redirection.</span></span> <span data-ttu-id="c268e-250">这意味着不会优化团队媒体会话。</span><span class="sxs-lookup"><span data-stu-id="c268e-250">This means that Teams media sessions won’t be optimized.</span></span> <span data-ttu-id="c268e-251">有关如何设置策略以关闭团队重定向的步骤，请参阅此[Citrix 网站](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/policies/reference/ica-policy-settings/multimedia-policy-settings.html)。</span><span class="sxs-lookup"><span data-stu-id="c268e-251">For steps on how to set policies to turn off Teams redirection, see this [Citrix website](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/policies/reference/ica-policy-settings/multimedia-policy-settings.html).</span></span>

<span data-ttu-id="c268e-252">我们正在努力添加目前仅在非 VDI 环境中可用的呼叫和会议功能。</span><span class="sxs-lookup"><span data-stu-id="c268e-252">We're working on adding calling and meeting features that are currently only available in non-VDI environments.</span></span> <span data-ttu-id="c268e-253">这些功能可能包括对质量、其他屏幕共享方案以及最近添加到团队的高级功能的更多管理控制。</span><span class="sxs-lookup"><span data-stu-id="c268e-253">These may include more admin control over quality, additional screen sharing scenarios, and advanced features recently added to Teams.</span></span> <span data-ttu-id="c268e-254">联系你的团队代表了解有关即将推出的功能的详细信息。</span><span class="sxs-lookup"><span data-stu-id="c268e-254">Contact your Teams representative to learn more about upcoming features.</span></span>

### <a name="network-requirements"></a><span data-ttu-id="c268e-255">网络要求</span><span class="sxs-lookup"><span data-stu-id="c268e-255">Network requirements</span></span>

<span data-ttu-id="c268e-256">我们建议你对环境进行评估，以确定任何风险和要求，这些风险和要求会影响你的整体云语音和视频部署。</span><span class="sxs-lookup"><span data-stu-id="c268e-256">We recommend that you evaluate your environment to identify any risks and requirements that can influence your overall cloud voice and video deployment.</span></span> <span data-ttu-id="c268e-257">使用[Skype For Business 网络评估工具](https://www.microsoft.com/download/details.aspx?id=53885)测试您的网络是否已准备好使用团队。</span><span class="sxs-lookup"><span data-stu-id="c268e-257">Use the [Skype for Business Network Assessment Tool](https://www.microsoft.com/download/details.aspx?id=53885) to test whether your network is ready for Teams.</span></span>

<span data-ttu-id="c268e-258">若要了解有关如何为团队准备网络的详细信息，请参阅[为团队准备组织的网络](prepare-network.md)。</span><span class="sxs-lookup"><span data-stu-id="c268e-258">To learn more about how to prepare your network for Teams, see [Prepare your organization's network for  Teams](prepare-network.md).</span></span>

### <a name="migrate-from-skype-for-business-on-vdi-to-teams-on-vdi"></a><span data-ttu-id="c268e-259">在 vdi 上从 Skype for Business 迁移到 VDI 上的团队</span><span class="sxs-lookup"><span data-stu-id="c268e-259">Migrate from Skype for Business on VDI to Teams on VDI</span></span>

<span data-ttu-id="c268e-260">如果你要从 VDI 的 Skype for Business 迁移到 VDI 上的团队，除了两个应用程序之间的区别之外，还有一些差异。</span><span class="sxs-lookup"><span data-stu-id="c268e-260">If you're migrating from Skype for Business on VDI to Teams on VDI, besides the differences between the two applications, there are some differences when VDI is also implemented.</span></span> <span data-ttu-id="c268e-261">Skype for Business VDI 中的团队 VDI 目前不支持的某些功能如下所示：</span><span class="sxs-lookup"><span data-stu-id="c268e-261">Some capabilities that aren’t currently supported in Teams VDI that are in Skype for Business VDI are as follows:</span></span>

- <span data-ttu-id="c268e-262">利用限制媒体比特率的策略控制 VDI 呼叫体验</span><span class="sxs-lookup"><span data-stu-id="c268e-262">Control of VDI calling experiences with policies for limiting media bitrate</span></span>
- <span data-ttu-id="c268e-263">用于禁用 VDI 中的某些 AV 功能的每个平台策略</span><span class="sxs-lookup"><span data-stu-id="c268e-263">Per-platform policy to disable some AV features in VDI</span></span>
- <span data-ttu-id="c268e-264">在应用共享时提供和获取控制权</span><span class="sxs-lookup"><span data-stu-id="c268e-264">Give and take control when app sharing</span></span>
- <span data-ttu-id="c268e-265">不带音频聊天的屏幕共享</span><span class="sxs-lookup"><span data-stu-id="c268e-265">Screen share from chat without audio</span></span>
- <span data-ttu-id="c268e-266">同时视频和屏幕共享发送和接收</span><span class="sxs-lookup"><span data-stu-id="c268e-266">Simultaneous video and screen sharing send and receive</span></span>

### <a name="teams-on-chrome-browser-versus-teams-desktop-app-for-vdi"></a><span data-ttu-id="c268e-267">Chrome 浏览器上的团队与 VDI 的团队桌面应用</span><span class="sxs-lookup"><span data-stu-id="c268e-267">Teams on Chrome browser versus Teams desktop app for VDI</span></span>

<span data-ttu-id="c268e-268">Chrome 浏览器上的团队不会通过 AV 优化提供适用于 VDI 的团队桌面应用的替代项。</span><span class="sxs-lookup"><span data-stu-id="c268e-268">Teams on Chrome browser doesn't provide a replacement for the Teams desktop app for VDI with AV optimization.</span></span> <span data-ttu-id="c268e-269">聊天和协作体验按预期工作。</span><span class="sxs-lookup"><span data-stu-id="c268e-269">The chat and collaboration experience works as expected.</span></span> <span data-ttu-id="c268e-270">需要媒体时，有一些体验可能无法在 Chrome 浏览器中满足用户的预期。</span><span class="sxs-lookup"><span data-stu-id="c268e-270">When media is needed, there are some experiences that may not meet user expectations on the Chrome browser.</span></span>

- <span data-ttu-id="c268e-271">音频和视频流体验可能不是最佳的。</span><span class="sxs-lookup"><span data-stu-id="c268e-271">The audio and video streaming experience may not be optimal.</span></span> <span data-ttu-id="c268e-272">用户可能会遇到延迟或降低质量。</span><span class="sxs-lookup"><span data-stu-id="c268e-272">Users may experiences delays or reduced quality.</span></span>
- <span data-ttu-id="c268e-273">"设备设置" 在浏览器设置中不可用。</span><span class="sxs-lookup"><span data-stu-id="c268e-273">Device settings aren't available in browser settings.</span></span>
- <span data-ttu-id="c268e-274">设备管理通过浏览器进行处理，并在浏览器网站设置中需要多个设置。</span><span class="sxs-lookup"><span data-stu-id="c268e-274">Device management is handled through the browser and requires multiple settings in browser site settings.</span></span>
- <span data-ttu-id="c268e-275">可能还需要在 Windows 设备管理中设置设备设置。</span><span class="sxs-lookup"><span data-stu-id="c268e-275">Device settings may also need to be set in Windows device management.</span></span>

## <a name="teams-on-vdi-with-chat-and-collaboration"></a><span data-ttu-id="c268e-276">具有聊天和协作功能的 VDI 团队</span><span class="sxs-lookup"><span data-stu-id="c268e-276">Teams on VDI with chat and collaboration</span></span>

<span data-ttu-id="c268e-277">如果你的组织希望仅使用团队中的聊天和协作功能，你可以设置用户级策略以关闭团队中的呼叫和会议功能。</span><span class="sxs-lookup"><span data-stu-id="c268e-277">If your organization wants to only use chat and collaboration features in Teams, you can set user-level policies to turn off calling and meeting functionality in Teams.</span></span> <span data-ttu-id="c268e-278">此功能级别不需要 Citrix 虚拟应用和桌面。</span><span class="sxs-lookup"><span data-stu-id="c268e-278">This feature level doesn't require Citrix Virtual Apps and Desktops.</span></span>

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a><span data-ttu-id="c268e-279">设置用于关闭呼叫和会议功能的策略</span><span class="sxs-lookup"><span data-stu-id="c268e-279">Set policies to turn off calling and meeting functionality</span></span>

<span data-ttu-id="c268e-280">你可以使用 Microsoft 团队管理中心或 PowerShell 设置策略。</span><span class="sxs-lookup"><span data-stu-id="c268e-280">You can set policies by using the Microsoft Teams admin center or PowerShell.</span></span> <span data-ttu-id="c268e-281">需要花费一些时间（几个小时）才能传播策略更改。</span><span class="sxs-lookup"><span data-stu-id="c268e-281">It can take some time (a few hours) for the policy changes to propagate.</span></span> <span data-ttu-id="c268e-282">如果你没有立即看到给定帐户的更改，请在几个小时后重试。</span><span class="sxs-lookup"><span data-stu-id="c268e-282">If you don’t see changes for a given account immediately, try again in a few hours.</span></span>

<span data-ttu-id="c268e-283">[**通话策略**](teams-calling-policy.md)：团队包括内置的 DisallowCalling 呼叫策略，其中所有的通话功能均处于关闭状态。</span><span class="sxs-lookup"><span data-stu-id="c268e-283">[**Calling polices**](teams-calling-policy.md): Teams includes the built-in DisallowCalling calling policy, in which all calling features are turned off.</span></span> <span data-ttu-id="c268e-284">将 DisallowCalling 策略分配给组织中使用虚拟环境中的团队的所有用户。</span><span class="sxs-lookup"><span data-stu-id="c268e-284">Assign the DisallowCalling policy to all users in your organization who use Teams in a virtualized environment.</span></span>

<span data-ttu-id="c268e-285">[**会议策略**](meeting-policies-in-teams.md)：团队包括内置的 AllOff 会议策略，其中所有会议功能均处于关闭状态。</span><span class="sxs-lookup"><span data-stu-id="c268e-285">[**Meeting policies**](meeting-policies-in-teams.md): Teams includes the built-in AllOff meeting policy, in which all meeting features are turned off.</span></span> <span data-ttu-id="c268e-286">将 AllOff 策略分配给组织中使用虚拟环境中的团队的所有用户。</span><span class="sxs-lookup"><span data-stu-id="c268e-286">Assign the AllOff policy to all users in your organization who use Teams in a virtualized environment.</span></span>

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a><span data-ttu-id="c268e-287">使用 Microsoft 团队管理中心分配策略</span><span class="sxs-lookup"><span data-stu-id="c268e-287">Assign policies using the Microsoft Teams admin center</span></span>

<span data-ttu-id="c268e-288">要将 DisallowCalling 呼叫策略和 AllOff 会议策略分配给用户，请按照下列步骤操作：</span><span class="sxs-lookup"><span data-stu-id="c268e-288">To assign the DisallowCalling calling policy and the AllOff meeting policy to users, follow these steps:</span></span>

1. <span data-ttu-id="c268e-289">在 Microsoft 团队管理中心的左侧导航中，转到 "**用户**"。</span><span class="sxs-lookup"><span data-stu-id="c268e-289">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="c268e-290">通过单击用户名左侧的用户选择用户，然后单击 "**编辑设置**"。</span><span class="sxs-lookup"><span data-stu-id="c268e-290">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="c268e-291">请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="c268e-291">Do the following:</span></span>
    1.  <span data-ttu-id="c268e-292">在 "**呼叫策略**" 下，单击 " **DisallowCalling**"。</span><span class="sxs-lookup"><span data-stu-id="c268e-292">Under **Calling policy**, click **DisallowCalling**.</span></span>
    2.  <span data-ttu-id="c268e-293">在 "**会议策略**" 下，单击 " **AllOff**"。</span><span class="sxs-lookup"><span data-stu-id="c268e-293">Under **Meeting policy**, click **AllOff**.</span></span>
4. <span data-ttu-id="c268e-294">单击“**应用**”。</span><span class="sxs-lookup"><span data-stu-id="c268e-294">Click **Apply**.</span></span>

<span data-ttu-id="c268e-295">若要一次为多个用户分配策略，请参阅[批量编辑团队用户设置](edit-user-settings-in-bulk.md)。</span><span class="sxs-lookup"><span data-stu-id="c268e-295">To assign a policy to multiple users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="c268e-296">或者，您也可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c268e-296">Or, you can also do the following:</span></span>

1. <span data-ttu-id="c268e-297">在 Microsoft 团队管理中心的左侧导航中，转到要分配的策略。</span><span class="sxs-lookup"><span data-stu-id="c268e-297">In the left navigation of the Microsoft Teams admin center, go to the policy you want to assign.</span></span> <span data-ttu-id="c268e-298">例如：</span><span class="sxs-lookup"><span data-stu-id="c268e-298">For example:</span></span>
    - <span data-ttu-id="c268e-299">转到 "**语音** > **呼叫策略**"，然后单击 " **DisallowCalling**"。</span><span class="sxs-lookup"><span data-stu-id="c268e-299">Go to **Voice** > **Calling policies**, and then click **DisallowCalling**.</span></span>
    - <span data-ttu-id="c268e-300">转到 "**会议** > **会议策略**"，然后单击 " **AllOff**"。</span><span class="sxs-lookup"><span data-stu-id="c268e-300">Go to **Meetings** > **Meeting policies**, and then click **AllOff**.</span></span>
3. <span data-ttu-id="c268e-301">选择 "**管理用户**"。</span><span class="sxs-lookup"><span data-stu-id="c268e-301">Select **Manage users**.</span></span>
4. <span data-ttu-id="c268e-302">在 "**管理用户**" 窗格中，按 "显示名称" 或 "按用户名搜索用户"，选择名称，然后单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="c268e-302">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="c268e-303">对要添加的每个用户重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="c268e-303">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="c268e-304">添加完用户后，单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="c268e-304">When you're finished adding users, click **Save**.</span></span>

#### <a name="assign-policies-using-powershell"></a><span data-ttu-id="c268e-305">使用 PowerShell 分配策略</span><span class="sxs-lookup"><span data-stu-id="c268e-305">Assign policies using PowerShell</span></span>

<span data-ttu-id="c268e-306">以下示例显示了如何使用[Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy)向用户分配 DisallowCalling 调用策略。</span><span class="sxs-lookup"><span data-stu-id="c268e-306">The following example shows how to use the [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) to assign the DisallowCalling calling policy to a user.</span></span>

```
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity “user email id”
```

<span data-ttu-id="c268e-307">若要了解有关使用 PowerShell 管理通话策略的详细信息，请参阅[设置 CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="c268e-307">To learn more about using PowerShell to manage calling policies, see [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).</span></span>

<span data-ttu-id="c268e-308">以下示例显示了如何使用[Grant-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy)将 AllOff 会议策略分配给用户。</span><span class="sxs-lookup"><span data-stu-id="c268e-308">The following example shows how to use the [Grant-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) to assign the AllOff meeting policy to a user.</span></span>

```
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity “user email id”
```

<span data-ttu-id="c268e-309">若要了解有关使用 PowerShell 管理会议策略的详细信息，请参阅[设置 CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="c268e-309">To learn more about using PowerShell to manage meeting policies, see [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).</span></span>

## <a name="migrate-teams-on-vdi-with-chat-and-collaboration-to-citrix-with-calling-and-meetings"></a><span data-ttu-id="c268e-310">通过通话和会议将团队与聊天和协作迁移到 Citrix</span><span class="sxs-lookup"><span data-stu-id="c268e-310">Migrate Teams on VDI with chat and collaboration to Citrix with calling and meetings</span></span>

<span data-ttu-id="c268e-311">如果您在 VDI 上有一个现有团队的实现，其中你已设置了用户级策略以关闭呼叫和会议功能，并且你要使用 AV 优化功能迁移到 Citrix，则必须设置策略以启用呼叫和适用于 VDI 用户的团队的会议功能。</span><span class="sxs-lookup"><span data-stu-id="c268e-311">If you have an existing implementation of Teams on VDI with chat and collaboration in which you had set user-level policies to turn off calling and meeting functionality, and you're migrating to Citrix with AV optimization, you must set policies to turn on calling and meeting functionality for those Teams on VDI users.</span></span>

### <a name="set-policies-to-turn-on-calling-and-meeting-functionality"></a><span data-ttu-id="c268e-312">设置启用呼叫和会议功能的策略</span><span class="sxs-lookup"><span data-stu-id="c268e-312">Set policies to turn on calling and meeting functionality</span></span>

<span data-ttu-id="c268e-313">你可以使用 Microsoft 团队管理中心或 PowerShell 为你的用户设置和分配呼叫和会议策略。</span><span class="sxs-lookup"><span data-stu-id="c268e-313">You can use the Microsoft Teams admin center or PowerShell to set and assign calling and meeting policies to your users.</span></span> <span data-ttu-id="c268e-314">需要花费一些时间（几个小时）才能传播策略更改。</span><span class="sxs-lookup"><span data-stu-id="c268e-314">It can take some time (a few hours) for policy changes to propagate.</span></span> <span data-ttu-id="c268e-315">如果你没有立即看到给定帐户的更改，请过几个小时后重试。</span><span class="sxs-lookup"><span data-stu-id="c268e-315">If you don’t see changes for a given account immediately, try again after a few hours.</span></span>

<span data-ttu-id="c268e-316">[**通话策略**](teams-calling-policy.md)：在团队中调用策略控制用户可以使用哪些通话功能。</span><span class="sxs-lookup"><span data-stu-id="c268e-316">[**Calling polices**](teams-calling-policy.md): Calling policies in Teams control which calling features are available to users.</span></span> <span data-ttu-id="c268e-317">团队包括内置的 AllowCalling 呼叫策略，其中所有的通话功能均处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="c268e-317">Teams includes the built-in AllowCalling calling policy, in which all calling features are turned on.</span></span> <span data-ttu-id="c268e-318">若要打开所有通话功能，请分配 AllowCalling 策略。</span><span class="sxs-lookup"><span data-stu-id="c268e-318">To turn on all calling features, assign the AllowCalling policy.</span></span> <span data-ttu-id="c268e-319">或者，创建自定义呼叫策略以打开所需的通话功能，并将其分配给用户。</span><span class="sxs-lookup"><span data-stu-id="c268e-319">Or, create a custom calling policy to turn on the calling features that you want and assign it to users.</span></span> 

<span data-ttu-id="c268e-320">[**会议策略**](meeting-policies-in-teams.md)：团队中的会议策略控制用户可以创建的会议类型，以及由组织中的用户安排的可供会议参与者使用的功能。</span><span class="sxs-lookup"><span data-stu-id="c268e-320">[**Meeting policies**](meeting-policies-in-teams.md): Meeting policies in Teams control the types of meetings that users can create and the features that are available to meeting participants that are scheduled by users in your organization.</span></span> <span data-ttu-id="c268e-321">团队包括内置的 AllOn 会议策略，其中所有会议功能均处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="c268e-321">Teams includes the built-in AllOn meeting policy, in which all meeting features are turned on.</span></span> <span data-ttu-id="c268e-322">若要打开所有会议功能，请分配 AllOn 策略。</span><span class="sxs-lookup"><span data-stu-id="c268e-322">To turn on all meeting features, assign the AllOn policy.</span></span> <span data-ttu-id="c268e-323">或者，创建自定义会议策略以打开所需的会议功能，并向其分配用户。</span><span class="sxs-lookup"><span data-stu-id="c268e-323">Or, create a custom meeting policy to turn on the meeting features that you want and assign it users.</span></span>

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a><span data-ttu-id="c268e-324">使用 Microsoft 团队管理中心分配策略</span><span class="sxs-lookup"><span data-stu-id="c268e-324">Assign policies using the Microsoft Teams admin center</span></span>

<span data-ttu-id="c268e-325">要将 AllowCalling 呼叫策略和 AllOn 会议策略分配给用户，请按照下列步骤操作：</span><span class="sxs-lookup"><span data-stu-id="c268e-325">To assign the AllowCalling calling policy and the AllOn meeting policy to users, follow these steps:</span></span>

1. <span data-ttu-id="c268e-326">在 Microsoft 团队管理中心的左侧导航中，转到 "**用户**"。</span><span class="sxs-lookup"><span data-stu-id="c268e-326">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="c268e-327">通过单击用户名左侧的用户选择用户，然后单击 "**编辑设置**"。</span><span class="sxs-lookup"><span data-stu-id="c268e-327">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="c268e-328">请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="c268e-328">Do the following:</span></span>
    1.  <span data-ttu-id="c268e-329">在 "**呼叫策略**" 下，单击 " **AllowCalling**"。</span><span class="sxs-lookup"><span data-stu-id="c268e-329">Under **Calling policy**, click **AllowCalling**.</span></span>
    2.  <span data-ttu-id="c268e-330">在 "**会议策略**" 下，单击 " **AllOn**"。</span><span class="sxs-lookup"><span data-stu-id="c268e-330">Under **Meeting policy**, click **AllOn**.</span></span>
4. <span data-ttu-id="c268e-331">单击“**应用**”。</span><span class="sxs-lookup"><span data-stu-id="c268e-331">Click **Apply**.</span></span>

<span data-ttu-id="c268e-332">若要一次为多个用户分配策略，请参阅[批量编辑团队用户设置](edit-user-settings-in-bulk.md)。</span><span class="sxs-lookup"><span data-stu-id="c268e-332">To assign a policy to multiple users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="c268e-333">或者，您也可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c268e-333">Or, you can also do the following:</span></span>

1. <span data-ttu-id="c268e-334">在 Microsoft 团队管理中心的左侧导航中，转到要分配的策略。</span><span class="sxs-lookup"><span data-stu-id="c268e-334">In the left navigation of the Microsoft Teams admin center, go to the policy you want to assign.</span></span> <span data-ttu-id="c268e-335">例如：</span><span class="sxs-lookup"><span data-stu-id="c268e-335">For example:</span></span>
    - <span data-ttu-id="c268e-336">转到 "**语音** > **呼叫策略**"，然后单击 " **AllowCalling**"。</span><span class="sxs-lookup"><span data-stu-id="c268e-336">Go to **Voice** > **Calling policies**, and then click **AllowCalling**.</span></span>
    - <span data-ttu-id="c268e-337">转到 "**会议** > **会议策略**"，然后单击 " **AllOn**"。</span><span class="sxs-lookup"><span data-stu-id="c268e-337">Go to **Meetings** > **Meeting policies**, and then click **AllOn**.</span></span>
3. <span data-ttu-id="c268e-338">选择 "**管理用户**"。</span><span class="sxs-lookup"><span data-stu-id="c268e-338">Select **Manage users**.</span></span>
4. <span data-ttu-id="c268e-339">在 "**管理用户**" 窗格中，按 "显示名称" 或 "按用户名搜索用户"，选择名称，然后单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="c268e-339">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="c268e-340">对要添加的每个用户重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="c268e-340">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="c268e-341">添加完用户后，单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="c268e-341">When you're finished adding users, click **Save**.</span></span>

#### <a name="assign-policies-using-powershell"></a><span data-ttu-id="c268e-342">使用 PowerShell 分配策略</span><span class="sxs-lookup"><span data-stu-id="c268e-342">Assign policies using PowerShell</span></span>

<span data-ttu-id="c268e-343">以下示例显示了如何使用[Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy)向用户分配 AllowCalling 调用策略。</span><span class="sxs-lookup"><span data-stu-id="c268e-343">The following example shows how to use the [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) to assign the AllowCalling calling policy to a user.</span></span>

```
Grant-CsTeamsCallingPolicy -PolicyName AllowCalling -Identity “user email id”
```

<span data-ttu-id="c268e-344">若要了解有关使用 PowerShell 管理通话策略的详细信息，请参阅[设置 CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="c268e-344">To learn more about using PowerShell to manage calling policies, see [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).</span></span>

<span data-ttu-id="c268e-345">以下示例显示了如何使用[Grant-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy)将 AllOn 会议策略分配给用户。</span><span class="sxs-lookup"><span data-stu-id="c268e-345">The following example shows how to use the [Grant-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) to assign the AllOn meeting policy to a user.</span></span>

```
Grant-CsTeamsMeetingPolicy -PolicyName AllOn -Identity “user email id”
```

<span data-ttu-id="c268e-346">若要了解有关使用 PowerShell 管理会议策略的详细信息，请参阅[设置 CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="c268e-346">To learn more about using PowerShell to manage meeting policies, see [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).</span></span>

## <a name="known-issues-and-limitations"></a><span data-ttu-id="c268e-347">已知问题和限制</span><span class="sxs-lookup"><span data-stu-id="c268e-347">Known issues and limitations</span></span>

### <a name="client-deployment-installation-and-setup"></a><span data-ttu-id="c268e-348">客户端部署、安装和设置</span><span class="sxs-lookup"><span data-stu-id="c268e-348">Client deployment, installation, and setup</span></span>

- <span data-ttu-id="c268e-349">对于每台计算机安装，不会以非 VDI 团队客户端的方式自动更新 VDI 上的团队。</span><span class="sxs-lookup"><span data-stu-id="c268e-349">With per-machine installation, Teams on VDI isn't automatically updated in the way that non-VDI Teams clients are.</span></span> <span data-ttu-id="c268e-350">你必须按照在[VDI 部分安装或更新团队桌面应用](#install-or-update-the-teams-desktop-app-on-vdi)中所述，通过安装新 MSI 来更新 VM 映像。</span><span class="sxs-lookup"><span data-stu-id="c268e-350">You have to update the VM image by installing a new MSI as described in the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.</span></span> <span data-ttu-id="c268e-351">必须卸载当前版本才能更新到较新版本。</span><span class="sxs-lookup"><span data-stu-id="c268e-351">You must uninstall the current version to update to a newer version.</span></span>
- <span data-ttu-id="c268e-352">应按每个用户或每台计算机来部署团队。</span><span class="sxs-lookup"><span data-stu-id="c268e-352">Teams should be deployed either per user or per machine.</span></span> <span data-ttu-id="c268e-353">不支持针对每个用户和每台计算机并行部署团队。</span><span class="sxs-lookup"><span data-stu-id="c268e-353">Deployment of Teams for concurrent per user and per machine is not supported.</span></span>  <span data-ttu-id="c268e-354">若要从每台计算机或每用户迁移到这些模式之一，请按照卸载过程进行，然后重新部署到任一模式。</span><span class="sxs-lookup"><span data-stu-id="c268e-354">To migrate from either per machine or per user to one of these modes, follow the uninstall procedure and redeploy to either mode.</span></span>
- <span data-ttu-id="c268e-355">Citrix 目前不支持基于 MacOs 和 Linux 的客户端。</span><span class="sxs-lookup"><span data-stu-id="c268e-355">MacOs and Linux-based clients are not supported by Citrix at this time.</span></span>
- <span data-ttu-id="c268e-356">Citrix 不支持使用终结点上定义的显式 HTTP 代理。</span><span class="sxs-lookup"><span data-stu-id="c268e-356">Citrix doesn't support the use of explicit HTTP proxies defined on an endpoint.</span></span> 

### <a name="calling-and-meetings"></a><span data-ttu-id="c268e-357">通话和会议</span><span class="sxs-lookup"><span data-stu-id="c268e-357">Calling and meetings</span></span>

- <span data-ttu-id="c268e-358">与 Skype for business 的互操作性仅限于音频通话，无视频模态。</span><span class="sxs-lookup"><span data-stu-id="c268e-358">Interoperability with Skype for Business is limited to audio calls, no video modality.</span></span>
- <span data-ttu-id="c268e-359">目前不支持双音频多频率（DTMF）与电话系统交互。</span><span class="sxs-lookup"><span data-stu-id="c268e-359">Dual Tone Multi Frequency (DTMF) interaction with telephony systems  is currently not supported.</span></span>
- <span data-ttu-id="c268e-360">以匿名用户身份加入团队会议并非 AV 优化。</span><span class="sxs-lookup"><span data-stu-id="c268e-360">Joining Teams meetings as an anonymous user isn't AV-optimized.</span></span> <span data-ttu-id="c268e-361">用户可以加入会议并具有非优化的体验。</span><span class="sxs-lookup"><span data-stu-id="c268e-361">The user can join the meeting and have a non-optimized experience.</span></span>
- <span data-ttu-id="c268e-362">会议或群组通话仅支持单个传入视频流。</span><span class="sxs-lookup"><span data-stu-id="c268e-362">Only a single incoming video stream is supported in meetings or group calls.</span></span> <span data-ttu-id="c268e-363">当多人发送视频时，在任何给定时间仅显示主要演讲者的视频。</span><span class="sxs-lookup"><span data-stu-id="c268e-363">When multiple people send video, only the dominant speaker's video is shown at any given time.</span></span>  
- <span data-ttu-id="c268e-364">传入和传出视频流分辨率仅限于720p 分辨率。</span><span class="sxs-lookup"><span data-stu-id="c268e-364">Incoming and outgoing video stream resolution is limited to 720p resolution.</span></span> <span data-ttu-id="c268e-365">这是一个 WebRTC 限制。</span><span class="sxs-lookup"><span data-stu-id="c268e-365">This is a WebRTC limitation.</span></span>
- <span data-ttu-id="c268e-366">仅支持来自传入相机或屏幕共享流的一个视频流。</span><span class="sxs-lookup"><span data-stu-id="c268e-366">Only one video stream from an incoming camera or screen share stream is supported.</span></span> <span data-ttu-id="c268e-367">当存在传入屏幕共享时，将显示该屏幕共享，而不是主扬声器的视频。</span><span class="sxs-lookup"><span data-stu-id="c268e-367">When there's an incoming screen share, that screen share is shown it instead of the video of the dominant speaker.</span></span>
- <span data-ttu-id="c268e-368">出站屏幕共享：</span><span class="sxs-lookup"><span data-stu-id="c268e-368">Outgoing screen sharing:</span></span>
    - <span data-ttu-id="c268e-369">不支持应用程序共享。</span><span class="sxs-lookup"><span data-stu-id="c268e-369">Application sharing is not supported.</span></span>
- <span data-ttu-id="c268e-370">授予控制权并获得控制权：</span><span class="sxs-lookup"><span data-stu-id="c268e-370">Give control and take control:</span></span>  
    - <span data-ttu-id="c268e-371">在屏幕共享或应用程序共享会话期间不受支持。</span><span class="sxs-lookup"><span data-stu-id="c268e-371">Not supported during a screen sharing or application sharing session.</span></span>
    - <span data-ttu-id="c268e-372">在 PowerPoint 共享会话期间受支持。</span><span class="sxs-lookup"><span data-stu-id="c268e-372">Supported during a PowerPoint sharing session.</span></span>  
- <span data-ttu-id="c268e-373">不支持 CWA 上的高 DPI 缩放。</span><span class="sxs-lookup"><span data-stu-id="c268e-373">High DPI scaling on CWA is not supported.</span></span>

<span data-ttu-id="c268e-374">对于不与 VDI 无关的团队已知问题，请参阅[团队的已知问题](Known-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="c268e-374">For Teams known issues that aren’t related to VDI, see [Known issues for Teams](Known-issues.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="c268e-375">疑难解答</span><span class="sxs-lookup"><span data-stu-id="c268e-375">Troubleshooting</span></span>

#### <a name="troubleshoot-citrix-components"></a><span data-ttu-id="c268e-376">Citrix 组件疑难解答</span><span class="sxs-lookup"><span data-stu-id="c268e-376">Troubleshoot Citrix components</span></span>

<span data-ttu-id="c268e-377">有关如何解决 VDA 和 CWA 问题的信息，请参阅[此 Citrix 网站](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html)。</span><span class="sxs-lookup"><span data-stu-id="c268e-377">For information on how to troubleshoot VDA and CWA issues, see [this Citrix website](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html).</span></span>

## <a name="related-topics"></a><span data-ttu-id="c268e-378">相关主题</span><span class="sxs-lookup"><span data-stu-id="c268e-378">Related topics</span></span>

- [<span data-ttu-id="c268e-379">使用 MSI 安装 Microsoft 团队</span><span class="sxs-lookup"><span data-stu-id="c268e-379">Install Microsoft Teams using MSI</span></span>](msi-deployment.md)
- [<span data-ttu-id="c268e-380">Teams PowerShell 概览</span><span class="sxs-lookup"><span data-stu-id="c268e-380">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
