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
ms.openlocfilehash: 75d51a6c20593c725863632350d90e2e58626e4d
ms.sourcegitcommit: 0f2024740e03af303efc62e7f54aa918a61ca51b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/06/2019
ms.locfileid: "39890597"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a><span data-ttu-id="03d2b-103">适用于虚拟化桌面基础结构的 Teams</span><span class="sxs-lookup"><span data-stu-id="03d2b-103">Teams for Virtualized Desktop Infrastructure</span></span>

<span data-ttu-id="03d2b-104">本文介绍在虚拟化环境中使用 Microsoft 团队的要求和限制。</span><span class="sxs-lookup"><span data-stu-id="03d2b-104">This article describes the requirements and limitations for using Microsoft Teams in a virtualized environment.</span></span>

## <a name="what-is-vdi"></a><span data-ttu-id="03d2b-105">什么是 VDI？</span><span class="sxs-lookup"><span data-stu-id="03d2b-105">What is VDI?</span></span>

<span data-ttu-id="03d2b-106">虚拟桌面基础结构（VDI）是在数据中心的集中式服务器上托管桌面操作系统和应用程序的虚拟化技术。</span><span class="sxs-lookup"><span data-stu-id="03d2b-106">Virtual Desktop Infrastructure (VDI) is virtualization technology that hosts a desktop operating system and applications on a centralized server in a data center.</span></span> <span data-ttu-id="03d2b-107">这使具有完全安全和合规的集中源的用户能够获得完全个性化的桌面体验。</span><span class="sxs-lookup"><span data-stu-id="03d2b-107">This enables a fully personalized desktop experience to users with a fully secured and compliant centralized source.</span></span>
 
<span data-ttu-id="03d2b-108">虚拟环境中的 Microsoft 团队支持聊天和协作，并且通过 Citrix 平台，还支持调用和会议功能。</span><span class="sxs-lookup"><span data-stu-id="03d2b-108">Microsoft Teams in a virtualized environment supports chat and collaboration, and with the Citrix platform, calling and meeting functionality are also supported.</span></span>

<span data-ttu-id="03d2b-109">虚拟环境中的团队支持多个配置。</span><span class="sxs-lookup"><span data-stu-id="03d2b-109">Teams in a virtualized environment supports multiple configurations.</span></span> <span data-ttu-id="03d2b-110">其中包括 VDI、专用、共享、持久和非持久模式。</span><span class="sxs-lookup"><span data-stu-id="03d2b-110">These include VDI, dedicated, shared, persistent and non-persistent modes.</span></span> <span data-ttu-id="03d2b-111">功能在连续开发中且定期添加，并且功能将在未来的几个月和几年内扩展。</span><span class="sxs-lookup"><span data-stu-id="03d2b-111">Features are in continuous development and are added on a regular basis, and functionality will expand in the coming months and years.</span></span>
 
<span data-ttu-id="03d2b-112">在虚拟化环境中使用团队可能与在非虚拟化环境中使用团队稍有不同。</span><span class="sxs-lookup"><span data-stu-id="03d2b-112">Using Teams in a virtualized environment may be somewhat different from using Teams in a non-virtualized environment.</span></span> <span data-ttu-id="03d2b-113">例如，某些高级功能在虚拟化环境中可能不可用，并且视频分辨率可能有所不同。</span><span class="sxs-lookup"><span data-stu-id="03d2b-113">For example, some advanced features may not be available in a virtualized environment and video resolution may differ.</span></span> <span data-ttu-id="03d2b-114">若要确保获得最佳的用户体验，请按照本文中的指南操作。</span><span class="sxs-lookup"><span data-stu-id="03d2b-114">To ensure an optimal user experience, follow the guidance in this article.</span></span>

## <a name="teams-on-vdi-components"></a><span data-ttu-id="03d2b-115">VDI 组件上的团队</span><span class="sxs-lookup"><span data-stu-id="03d2b-115">Teams on VDI components</span></span>

<span data-ttu-id="03d2b-116">在虚拟化环境中使用团队需要以下组件。</span><span class="sxs-lookup"><span data-stu-id="03d2b-116">Using Teams in a virtualized environment requires the following components.</span></span>

- <span data-ttu-id="03d2b-117">**虚拟化代理**：针对虚拟化提供程序的资源和连接管理器，例如 Azure</span><span class="sxs-lookup"><span data-stu-id="03d2b-117">**Virtualization broker**: The resource and connection manager to the virtualization provider, such as Azure</span></span>
- <span data-ttu-id="03d2b-118">**虚拟桌面**：运行 Microsoft 团队的虚拟机（VM）堆栈</span><span class="sxs-lookup"><span data-stu-id="03d2b-118">**Virtual desktop**: The Virtual Machine (VM) stack that runs Microsoft Teams</span></span>
- <span data-ttu-id="03d2b-119">**瘦客户端**：用户使用物理接口的终结点</span><span class="sxs-lookup"><span data-stu-id="03d2b-119">**Thin client**: The endpoint that the user physically interfaces with</span></span>
- <span data-ttu-id="03d2b-120">**团队桌面应用**：这是团队桌面客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="03d2b-120">**Teams desktop app**: This is the Teams desktop client app</span></span>

## <a name="teams-on-vdi-requirements"></a><span data-ttu-id="03d2b-121">VDI 要求的团队</span><span class="sxs-lookup"><span data-stu-id="03d2b-121">Teams on VDI requirements</span></span>

### <a name="virtualization-provider-requirements"></a><span data-ttu-id="03d2b-122">虚拟化提供商要求</span><span class="sxs-lookup"><span data-stu-id="03d2b-122">Virtualization provider requirements</span></span>

<span data-ttu-id="03d2b-123">团队桌面应用已通过主流虚拟化解决方案提供商进行验证。</span><span class="sxs-lookup"><span data-stu-id="03d2b-123">The Teams desktop app was validated with leading virtualization solution providers.</span></span> <span data-ttu-id="03d2b-124">有了多个市场提供商，我们建议你咨询你的虚拟化解决方案提供商以确保满足最低要求。</span><span class="sxs-lookup"><span data-stu-id="03d2b-124">With multiple market providers, we recommend that you consult your virtualization solution provider to ensure minimum requirements are met.</span></span>
  
<span data-ttu-id="03d2b-125">目前，带有音频/视频（AV）优化的团队在通过 Citrix 认证。</span><span class="sxs-lookup"><span data-stu-id="03d2b-125">Currently, Teams on VDI with audio/video (AV) optimization is certified with Citrix.</span></span> <span data-ttu-id="03d2b-126">查看本部分中的信息，确保同时满足 Citrix 和团队要求才能获得正确的功能。</span><span class="sxs-lookup"><span data-stu-id="03d2b-126">Review the information in this section to ensure both Citrix and Teams requirements are met for proper functionality.</span></span>

### <a name="partners-certified-for-teams"></a><span data-ttu-id="03d2b-127">合作伙伴认证的团队</span><span class="sxs-lookup"><span data-stu-id="03d2b-127">Partners certified for Teams</span></span>

<span data-ttu-id="03d2b-128">以下合作伙伴拥有团队的虚拟桌面基础结构解决方案。</span><span class="sxs-lookup"><span data-stu-id="03d2b-128">The following partners have virtual desktop infrastructure solutions for Teams.</span></span>

|<span data-ttu-id="03d2b-129">配偶</span><span class="sxs-lookup"><span data-stu-id="03d2b-129">Partner</span></span>|<span data-ttu-id="03d2b-130">合作伙伴解决方案</span><span class="sxs-lookup"><span data-stu-id="03d2b-130">Partner solution</span></span>|
|----|---|
|![表示 Citrix 的徽标](media/citrix.png)| <span data-ttu-id="03d2b-132"><a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Citrix 虚拟应用和桌面</a></span><span class="sxs-lookup"><span data-stu-id="03d2b-132"><a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Citrix Virtual Apps and Desktops</a></span></span> |

### <a name="citrix-virtual-apps-and-desktops-requirements"></a><span data-ttu-id="03d2b-133">Citrix 虚拟应用和桌面要求</span><span class="sxs-lookup"><span data-stu-id="03d2b-133">Citrix Virtual Apps and Desktops requirements</span></span>

<span data-ttu-id="03d2b-134">Citrix 虚拟应用和桌面（以前称为 XenApp 和 XenDesktop）为适用于 VDI 的团队提供 AV 优化。</span><span class="sxs-lookup"><span data-stu-id="03d2b-134">Citrix Virtual Apps and Desktops (formerly known as XenApp and XenDesktop) provides AV optimization for Teams on VDI.</span></span> <span data-ttu-id="03d2b-135">通过 Citrix 虚拟应用和桌面，VDI 上的团队不仅支持聊天和协作，还支持呼叫和会议功能。</span><span class="sxs-lookup"><span data-stu-id="03d2b-135">With Citrix Virtual Apps and Desktops, Teams on VDI supports calling and meeting functionality in addition to chat and collaboration.</span></span>

<span data-ttu-id="03d2b-136">你可以在[此处](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/)下载 Citrix 虚拟应用和桌面的最新版本。</span><span class="sxs-lookup"><span data-stu-id="03d2b-136">You can download the latest version of Citrix Virtual Apps and Desktops [here](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/).</span></span> <span data-ttu-id="03d2b-137">（您需要首先登录。）默认情况下，必要的组件捆绑到[Citrix 工作区应用（CWA）](https://www.citrix.com/downloads/workspace-app/)和虚拟交付代理（VDA）中。</span><span class="sxs-lookup"><span data-stu-id="03d2b-137">(You'll need to sign in first.) The necessary components are bundled into the [Citrix Workspace app (CWA)](https://www.citrix.com/downloads/workspace-app/) and Virtual Delivery Agent (VDA) by default.</span></span> <span data-ttu-id="03d2b-138">无需在 CWA 或 VDA 上安装任何其他组件或插件。</span><span class="sxs-lookup"><span data-stu-id="03d2b-138">You don't need to install any additional components or plugins on CWA or the VDA.</span></span>

<span data-ttu-id="03d2b-139">有关最新的服务器和客户端要求，请参阅[此 Citrix 网站](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html)。</span><span class="sxs-lookup"><span data-stu-id="03d2b-139">For the latest server and client requirements, see [this Citrix website](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html).</span></span>

## <a name="install-the-teams-desktop-app-on-vdi"></a><span data-ttu-id="03d2b-140">在 VDI 上安装团队桌面应用</span><span class="sxs-lookup"><span data-stu-id="03d2b-140">Install the Teams desktop app on VDI</span></span>

<span data-ttu-id="03d2b-141">你可以使用 MSI 程序包使用每台计算机安装或每用户安装来部署适用于 VDI 的团队桌面应用。</span><span class="sxs-lookup"><span data-stu-id="03d2b-141">You can deploy the Teams desktop app for VDI using a per-machine installation or per-user installation using the MSI package.</span></span> <span data-ttu-id="03d2b-142">决定使用哪种方法取决于您使用的是持久设置还是非持久设置以及您的组织的相关功能需求。</span><span class="sxs-lookup"><span data-stu-id="03d2b-142">Deciding on which approach to use depends on whether you use a persistent or non-persistent setup and the associated functionality needs of your organization.</span></span>
<span data-ttu-id="03d2b-143">对于专用的永久设置，这两种方法都适用。</span><span class="sxs-lookup"><span data-stu-id="03d2b-143">For a dedicated persistent setup, either approach would work.</span></span>  <span data-ttu-id="03d2b-144">但是，对于非持久设置，团队需要每计算机安装才能高效工作。</span><span class="sxs-lookup"><span data-stu-id="03d2b-144">However, for a non-persistent setup, per-machine installation is required for Teams to work efficiently.</span></span> <span data-ttu-id="03d2b-145">请参阅[非持久设置](#non-persistent-setup)部分。</span><span class="sxs-lookup"><span data-stu-id="03d2b-145">See the [Non-persistent setup](#non-persistent-setup) section.</span></span>

<span data-ttu-id="03d2b-146">对于每台计算机安装，自动更新已禁用。</span><span class="sxs-lookup"><span data-stu-id="03d2b-146">With per-machine installation, automatic updates is disabled.</span></span> <span data-ttu-id="03d2b-147">这意味着，若要更新团队应用，必须卸载当前版本才能更新到较新的版本。</span><span class="sxs-lookup"><span data-stu-id="03d2b-147">This means that to update the Teams app, you must uninstall the current version to update to a newer version.</span></span> <span data-ttu-id="03d2b-148">对于每用户安装，自动更新已启用。</span><span class="sxs-lookup"><span data-stu-id="03d2b-148">With per-user installation, automatic updates is enabled.</span></span> <span data-ttu-id="03d2b-149">对于大多数 VDI 部署，建议使用每台计算机安装部署团队。</span><span class="sxs-lookup"><span data-stu-id="03d2b-149">For most VDI deployments, we recommend you deploy Teams using per-machine installation.</span></span>

<span data-ttu-id="03d2b-150">为了使 VDI 环境中的团队防病毒优化正常工作，瘦客户端终结点必须有权访问 internet。</span><span class="sxs-lookup"><span data-stu-id="03d2b-150">For Teams AV optimization in VDI environments to work properly, the thin client endpoint must have access to the internet.</span></span> <span data-ttu-id="03d2b-151">如果在瘦客户端终结点上无法访问 internet，优化启动将不会成功。</span><span class="sxs-lookup"><span data-stu-id="03d2b-151">If internet access isn't available at the thin client endpoint, optimization startup won't be successful.</span></span> <span data-ttu-id="03d2b-152">这意味着用户处于非优化的媒体状态。</span><span class="sxs-lookup"><span data-stu-id="03d2b-152">This means that the user is in a non-optimized media state.</span></span>

#### <a name="dedicated-persistent-setup"></a><span data-ttu-id="03d2b-153">专用永久设置</span><span class="sxs-lookup"><span data-stu-id="03d2b-153">Dedicated persistent setup</span></span>

<span data-ttu-id="03d2b-154">在专用的永久设置中，用户注销后，将保留用户的本地操作系统更改。</span><span class="sxs-lookup"><span data-stu-id="03d2b-154">In a dedicated persistent setup, users' local operating system changes are retained after users log off.</span></span>  <span data-ttu-id="03d2b-155">对于永久设置，团队同时支持每用户和每计算机安装。</span><span class="sxs-lookup"><span data-stu-id="03d2b-155">For persistent setup, Teams support both per-user and per-machine installation.</span></span>

<span data-ttu-id="03d2b-156">以下是推荐的最低 VM 配置。</span><span class="sxs-lookup"><span data-stu-id="03d2b-156">The following is the recommended minimum VM configuration.</span></span>

|<span data-ttu-id="03d2b-157">参数</span><span class="sxs-lookup"><span data-stu-id="03d2b-157">Parameter</span></span>  |<span data-ttu-id="03d2b-158">工作站操作系统</span><span class="sxs-lookup"><span data-stu-id="03d2b-158">Workstation operating system</span></span>  |<span data-ttu-id="03d2b-159">服务器操作系统</span><span class="sxs-lookup"><span data-stu-id="03d2b-159">Server operation system</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="03d2b-160">vCPU</span><span class="sxs-lookup"><span data-stu-id="03d2b-160">vCPU</span></span>   |    <span data-ttu-id="03d2b-161">2核</span><span class="sxs-lookup"><span data-stu-id="03d2b-161">2 cores</span></span>     |  <span data-ttu-id="03d2b-162">4、6或8</span><span class="sxs-lookup"><span data-stu-id="03d2b-162">4,6, or 8</span></span><br><span data-ttu-id="03d2b-163">了解基础非统一内存访问（NUMA）配置和相应配置 Vm 非常重要。</span><span class="sxs-lookup"><span data-stu-id="03d2b-163">It's important to understand the underlying non-uniform memory access (NUMA) configuration and configure your VMs accordingly.</span></span>     |
|<span data-ttu-id="03d2b-164">RAM</span><span class="sxs-lookup"><span data-stu-id="03d2b-164">RAM</span></span>     |   <span data-ttu-id="03d2b-165">4 GB</span><span class="sxs-lookup"><span data-stu-id="03d2b-165">4 GB</span></span>      | <span data-ttu-id="03d2b-166">每个用户512到 1024 MB</span><span class="sxs-lookup"><span data-stu-id="03d2b-166">512 to 1024 MB per user</span></span>        |
|<span data-ttu-id="03d2b-167">存储空间</span><span class="sxs-lookup"><span data-stu-id="03d2b-167">Storage</span></span>    | <span data-ttu-id="03d2b-168">8 GB</span><span class="sxs-lookup"><span data-stu-id="03d2b-168">8 GB</span></span>        | <span data-ttu-id="03d2b-169">40到 60 GB</span><span class="sxs-lookup"><span data-stu-id="03d2b-169">40 to 60 GB</span></span>        |

#### <a name="non-persistent-setup"></a><span data-ttu-id="03d2b-170">非持久设置</span><span class="sxs-lookup"><span data-stu-id="03d2b-170">Non-persistent setup</span></span>

<span data-ttu-id="03d2b-171">在非持久设置中，用户注销后将不保留用户的本地操作系统更改。</span><span class="sxs-lookup"><span data-stu-id="03d2b-171">In a non-persistent setup, users' local operating system changes are not retained after users log off.</span></span> <span data-ttu-id="03d2b-172">此类设置通常共享多用户会话。</span><span class="sxs-lookup"><span data-stu-id="03d2b-172">Such setups are commonly shared multi-user sessions.</span></span> <span data-ttu-id="03d2b-173">VM 配置根据用户数量和可用的物理箱资源而有所不同。</span><span class="sxs-lookup"><span data-stu-id="03d2b-173">VM configuration varies based on the number of users and available physical box resources.</span></span>

<span data-ttu-id="03d2b-174">对于非持久设置，必须将团队桌面应用安装到黄金图像的每台计算机上。</span><span class="sxs-lookup"><span data-stu-id="03d2b-174">For a non-persistent setup, the Teams desktop app must be installed per-machine to the golden image.</span></span> <span data-ttu-id="03d2b-175">（若要了解详细信息，请参阅在[VDI 部分安装 "团队桌面应用](#install-the-teams-desktop-app-on-vdi)" 部分）。</span><span class="sxs-lookup"><span data-stu-id="03d2b-175">(To learn more, see the [Install the Teams desktop app on VDI](#install-the-teams-desktop-app-on-vdi) section).</span></span> <span data-ttu-id="03d2b-176">这可确保在用户会话期间有效地启动团队应用。</span><span class="sxs-lookup"><span data-stu-id="03d2b-176">This ensures an efficient launch of the Teams app during a user session.</span></span> <span data-ttu-id="03d2b-177">将团队与非持久性设置配合使用时，还需要配置文件缓存管理器才能高效团队运行时数据同步。这可确保在用户会话期间缓存相应的特定于用户的信息（例如，用户数据、配置文件和设置）。</span><span class="sxs-lookup"><span data-stu-id="03d2b-177">Using Teams with a non-persistent setup also requires a profile caching manager for efficient Teams runtime data sync. This ensures that the appropriate user-specific information (for example, user data, profile, and settings) are cached during the user session.</span></span>  <span data-ttu-id="03d2b-178">有多种可用的缓存管理器解决方案。</span><span class="sxs-lookup"><span data-stu-id="03d2b-178">There are variety of caching manager solutions available.</span></span> <span data-ttu-id="03d2b-179">例如， [FSLogix](https://docs.microsoft.com/fslogix/overview)。</span><span class="sxs-lookup"><span data-stu-id="03d2b-179">For example, [FSLogix](https://docs.microsoft.com/fslogix/overview).</span></span> <span data-ttu-id="03d2b-180">有关特定配置说明，请咨询您的缓存管理器提供程序。</span><span class="sxs-lookup"><span data-stu-id="03d2b-180">Consult your caching manager provider for specific configuration instructions.</span></span>

##### <a name="teams-cached-content-exclusion-list-for-non-persistent-setup"></a><span data-ttu-id="03d2b-181">用于非持久设置的工作组缓存的内容排除列表</span><span class="sxs-lookup"><span data-stu-id="03d2b-181">Teams cached content exclusion list for non-persistent setup</span></span>

<span data-ttu-id="03d2b-182">从 "团队缓存" 文件夹（% appdata%/Microsoft/Teams.）中排除以下项</span><span class="sxs-lookup"><span data-stu-id="03d2b-182">Exclude the following from the Teams caching folder, %appdata%/Microsoft/Teams.</span></span>  <span data-ttu-id="03d2b-183">排除这些帮助将减少用户缓存大小，以进一步优化非持久设置。</span><span class="sxs-lookup"><span data-stu-id="03d2b-183">Excluding these help reduce the user caching size to further optimize your non-persistent setup.</span></span>

- <span data-ttu-id="03d2b-184">.txt 文件</span><span class="sxs-lookup"><span data-stu-id="03d2b-184">.txt files</span></span>
- <span data-ttu-id="03d2b-185">媒体堆叠文件夹</span><span class="sxs-lookup"><span data-stu-id="03d2b-185">Media-stack folder</span></span>

### <a name="office-365-proplus-considerations"></a><span data-ttu-id="03d2b-186">Office 365 专业增强版注意事项</span><span class="sxs-lookup"><span data-stu-id="03d2b-186">Office 365 ProPlus considerations</span></span>

<span data-ttu-id="03d2b-187">在 VDI 上部署具有 Office 365 专业增强版的团队时，请考虑以下事项。</span><span class="sxs-lookup"><span data-stu-id="03d2b-187">Consider the following when you deploy Teams with Office 365 ProPlus on VDI.</span></span>

#### <a name="new-deployments-of-teams-through-office-365-proplus"></a><span data-ttu-id="03d2b-188">通过 Office 365 专业增强版的新部署团队</span><span class="sxs-lookup"><span data-stu-id="03d2b-188">New deployments of Teams through Office 365 ProPlus</span></span>

<span data-ttu-id="03d2b-189">在通过 Office 365 专业增强版部署团队之前，必须先卸载任何预先存在的团队应用（如果它们是使用按计算机安装部署的）。</span><span class="sxs-lookup"><span data-stu-id="03d2b-189">Before you deploy Teams through Office 365 ProPlus, you must first uninstall any pre-existing Teams apps if they were deployed using per-machine installation.</span></span>

<span data-ttu-id="03d2b-190">通过 Office 365 专业增强版的团队将针对每个用户进行安装。</span><span class="sxs-lookup"><span data-stu-id="03d2b-190">Teams through Office 365 ProPlus is installed per-user.</span></span> <span data-ttu-id="03d2b-191">若要了解详细信息，请参阅[在 VDI 部分安装团队桌面应用](#install-the-teams-desktop-app-on-vdi)。</span><span class="sxs-lookup"><span data-stu-id="03d2b-191">To learn more, see the [Install the Teams desktop app on VDI](#install-the-teams-desktop-app-on-vdi) section.</span></span>

#### <a name="teams-deployments-through-office-365-proplus-updates"></a><span data-ttu-id="03d2b-192">通过 Office 365 专业增强版更新的团队部署</span><span class="sxs-lookup"><span data-stu-id="03d2b-192">Teams deployments through Office 365 ProPlus updates</span></span>

<span data-ttu-id="03d2b-193">团队也将添加到 Office 365 专业增强版的现有安装。</span><span class="sxs-lookup"><span data-stu-id="03d2b-193">Teams is also being added to existing installations of Office 365 ProPlus.</span></span> <span data-ttu-id="03d2b-194">由于 Office 365 专业增强版仅为每位用户安装团队，请参阅在[VDI 部分安装团队桌面应用](#install-the-teams-desktop-app-on-vdi)。</span><span class="sxs-lookup"><span data-stu-id="03d2b-194">Since Office 365 ProPlus installs Teams per-user only, see the [Install the Teams desktop app on VDI](#install-the-teams-desktop-app-on-vdi) section.</span></span>

#### <a name="using-teams-with-per-machine-installation-and-office-365-proplus"></a><span data-ttu-id="03d2b-195">对每台计算机安装使用团队和 Office 365 专业增强版</span><span class="sxs-lookup"><span data-stu-id="03d2b-195">Using Teams with per-machine installation and Office 365 ProPlus</span></span>

<span data-ttu-id="03d2b-196">Office 365 专业增强版不支持团队的每计算机安装。</span><span class="sxs-lookup"><span data-stu-id="03d2b-196">Office 365 ProPlus doesn't support per-machine installations of Teams.</span></span> <span data-ttu-id="03d2b-197">若要使用每台计算机安装，必须从 Office 365 专业增强版中排除团队。</span><span class="sxs-lookup"><span data-stu-id="03d2b-197">To use per-machine installation, you must exclude Teams from Office 365 ProPlus.</span></span> <span data-ttu-id="03d2b-198">请参阅将[团队桌面应用部署到 VM](#deploy-the-teams-desktop-app-to-the-vm)和[如何通过 Office 365 专业增强版部分排除团队部署](#how-to-exclude-teams-deployment-through-office-365-proplus)。</span><span class="sxs-lookup"><span data-stu-id="03d2b-198">See the [Deploy the Teams desktop app to the VM](#deploy-the-teams-desktop-app-to-the-vm) and [How to exclude Teams deployment through Office 365 ProPlus](#how-to-exclude-teams-deployment-through-office-365-proplus) sections.</span></span>

#### <a name="how-to-exclude-teams-deployment-through-office-365-proplus"></a><span data-ttu-id="03d2b-199">如何通过 Office 365 专业增强版排除团队部署</span><span class="sxs-lookup"><span data-stu-id="03d2b-199">How to exclude Teams deployment through Office 365 ProPlus</span></span>

<span data-ttu-id="03d2b-200">若要了解有关团队和 Office 365 专业增强版的详细信息，请参阅[如何从 Office 365 专业增强版的新安装中排除团队](https://docs.microsoft.com/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-office-365-proplus)，并[使用组策略来控制团队的安装](https://docs.microsoft.com/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams)。</span><span class="sxs-lookup"><span data-stu-id="03d2b-200">To learn more about Teams and Office 365 ProPlus, see [How to exclude Teams from new installations of Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-office-365-proplus) and [Use Group Policy to control the installation of Teams](https://docs.microsoft.com/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams).</span></span>

### <a name="deploy-the-teams-desktop-app-to-the-vm"></a><span data-ttu-id="03d2b-201">将团队桌面应用部署到 VM</span><span class="sxs-lookup"><span data-stu-id="03d2b-201">Deploy the Teams desktop app to the VM</span></span>

1. <span data-ttu-id="03d2b-202">使用以下链接之一下载与你的 VDI VM 操作系统匹配的团队 MSI 程序包。</span><span class="sxs-lookup"><span data-stu-id="03d2b-202">Download the Teams MSI package that matches your VDI VM operating system using one of the following links.</span></span>

    - [<span data-ttu-id="03d2b-203">32位版本</span><span class="sxs-lookup"><span data-stu-id="03d2b-203">32-bit version</span></span>](https://statics.teams.microsoft.com/production-windows/1.2.00.32462/Teams_windows.msi)
    - [<span data-ttu-id="03d2b-204">64位版本</span><span class="sxs-lookup"><span data-stu-id="03d2b-204">64-bit version</span></span>](https://statics.teams.microsoft.com/production-windows-x64/1.2.00.32462/Teams_windows_x64.msi)

    <span data-ttu-id="03d2b-205">所需的团队桌面应用的最低版本是1.2.00.31357 版本。</span><span class="sxs-lookup"><span data-stu-id="03d2b-205">The minimum version of the Teams desktop app that's required is version 1.2.00.31357.</span></span>

2. <span data-ttu-id="03d2b-206">通过运行以下命令之一将 MSI 安装到 VDI VM：</span><span class="sxs-lookup"><span data-stu-id="03d2b-206">Install the MSI to the VDI VM by running one of the following commands:</span></span>

    - <span data-ttu-id="03d2b-207">每用户安装（默认）</span><span class="sxs-lookup"><span data-stu-id="03d2b-207">Per-user installation  (default)</span></span>
  
        ```
        msiexec /i <path_to_msi> /l*v <install_logfile_name>
        ```
    
        <span data-ttu-id="03d2b-208">这是默认安装，可将团队安装到% AppData% 用户文件夹。</span><span class="sxs-lookup"><span data-stu-id="03d2b-208">This is the default installation, which installs Teams to the %AppData% user folder.</span></span> <span data-ttu-id="03d2b-209">此时，将完成黄金图像设置。</span><span class="sxs-lookup"><span data-stu-id="03d2b-209">At this point, the golden image setup is complete.</span></span> <span data-ttu-id="03d2b-210">在非持久设置中，团队将不会在每用户安装中正常工作。</span><span class="sxs-lookup"><span data-stu-id="03d2b-210">Teams will not work properly with per-user installation on a non-persistent setup.</span></span>
    
    - <span data-ttu-id="03d2b-211">每计算机安装</span><span class="sxs-lookup"><span data-stu-id="03d2b-211">Per-machine installation</span></span>

        ```
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1
        ```

        <span data-ttu-id="03d2b-212">这会将团队安装到64位操作系统上的 "程序文件（x86）" 文件夹和32位操作系统上的 "程序文件" 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="03d2b-212">This installs Teams to the Program Files (x86) folder on a 64-bit operating system and to the Program Files folder on a 32-bit operating system.</span></span> <span data-ttu-id="03d2b-213">此时，将完成黄金图像设置。</span><span class="sxs-lookup"><span data-stu-id="03d2b-213">At this point, the golden image setup is complete.</span></span> <span data-ttu-id="03d2b-214">对于非持久设置，需要针对每台计算机安装团队。</span><span class="sxs-lookup"><span data-stu-id="03d2b-214">Installing Teams per-machine is required for non-persistent setups.</span></span>
 
        <span data-ttu-id="03d2b-215">下一个交互式登录会话将启动团队并要求提供凭据。</span><span class="sxs-lookup"><span data-stu-id="03d2b-215">The next interactive logon session starts Teams and asks for credentials.</span></span>

3. <span data-ttu-id="03d2b-216">从 VDI VM 卸载 MSI</span><span class="sxs-lookup"><span data-stu-id="03d2b-216">Uninstall the MSI from the VDI VM</span></span> 

    <span data-ttu-id="03d2b-217">可通过两种方式卸载团队。</span><span class="sxs-lookup"><span data-stu-id="03d2b-217">There are two ways to uninstall Teams.</span></span>  
  
    - <span data-ttu-id="03d2b-218">PowerShell 脚本（推荐）：你可以使用此[PowerShell 脚本](scripts/powershell-script-teams-deployment-clean-up.md)清理目标计算机或用户的团队。</span><span class="sxs-lookup"><span data-stu-id="03d2b-218">PowerShell script (recommended): You can use this [PowerShell script](scripts/powershell-script-teams-deployment-clean-up.md) to clean up Teams from target machines or users.</span></span> <span data-ttu-id="03d2b-219">应针对目标计算机上的每个用户执行该应用。</span><span class="sxs-lookup"><span data-stu-id="03d2b-219">It should be executed for every user on a targeted machine.</span></span> 
    
    - <span data-ttu-id="03d2b-220">命令行：此方法删除团队，但阻止团队重新安装。</span><span class="sxs-lookup"><span data-stu-id="03d2b-220">Command line: This approach removes Teams, yet prevents re-installation of Teams.</span></span>  
    <span data-ttu-id="03d2b-221">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="03d2b-221">Run the following command:</span></span>
  
      ```
      msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>
      ```
      <span data-ttu-id="03d2b-222">这将从 "程序文件（x86）" 文件夹或 "程序文件" 文件夹中卸载团队，具体取决于操作系统环境。</span><span class="sxs-lookup"><span data-stu-id="03d2b-222">This uninstalls Teams from the Program Files (x86) folder or Program Files folder, depending on the operating system environment.</span></span>

## <a name="teams-on-vdi-performance-considerations"></a><span data-ttu-id="03d2b-223">VDI 性能注意事项的团队</span><span class="sxs-lookup"><span data-stu-id="03d2b-223">Teams on VDI performance considerations</span></span>

<span data-ttu-id="03d2b-224">有多种虚拟化设置配置，每个配置都具有不同的优化焦点。</span><span class="sxs-lookup"><span data-stu-id="03d2b-224">There are variety of virtualized setup configurations, each with a different focus for optimization.</span></span> <span data-ttu-id="03d2b-225">例如，用户密度。</span><span class="sxs-lookup"><span data-stu-id="03d2b-225">For example, user density.</span></span> <span data-ttu-id="03d2b-226">规划时，请考虑以下事项，以帮助根据组织的工作负载需求优化设置：</span><span class="sxs-lookup"><span data-stu-id="03d2b-226">When planning, consider the following to help optimize your setup based on the workload needs of your organization:</span></span>

- <span data-ttu-id="03d2b-227">最低要求：某些工作负荷可能需要使用高于最低要求的资源进行设置。</span><span class="sxs-lookup"><span data-stu-id="03d2b-227">Minimum requirement: Some workloads may require a setup using resources that are above the minimum requirements.</span></span> <span data-ttu-id="03d2b-228">例如，使用需要更多计算资源的应用程序的开发人员的工作负荷。</span><span class="sxs-lookup"><span data-stu-id="03d2b-228">For example, workloads for developers who use applications that demand more computing resources.</span></span>
- <span data-ttu-id="03d2b-229">依赖关系：包括有关基础架构、工作量以及团队桌面应用之外的其他环境注意事项的依赖关系。</span><span class="sxs-lookup"><span data-stu-id="03d2b-229">Dependencies: These include dependencies on infrastructure, workload, and other environmental considerations outside the Teams desktop app.</span></span>
- <span data-ttu-id="03d2b-230">VDI 上已禁用的功能：团队禁用适用于 VDI 的 GPU 密集型功能，这有助于提高暂时 CPU 的利用率。</span><span class="sxs-lookup"><span data-stu-id="03d2b-230">Disabled features on VDI: Teams disables GPU-intensive features for VDI, which can help improve transient CPU utilization.</span></span> <span data-ttu-id="03d2b-231">已禁用以下功能：</span><span class="sxs-lookup"><span data-stu-id="03d2b-231">The following features are disabled:</span></span>
    - <span data-ttu-id="03d2b-232">团队 CSS 动画</span><span class="sxs-lookup"><span data-stu-id="03d2b-232">Teams CSS animation</span></span>
    - <span data-ttu-id="03d2b-233">Giphy 自动启动</span><span class="sxs-lookup"><span data-stu-id="03d2b-233">Giphy auto-start</span></span>

## <a name="teams-on-vdi-with-calling-and-meetings"></a><span data-ttu-id="03d2b-234">VDI 上的团队与呼叫和会议</span><span class="sxs-lookup"><span data-stu-id="03d2b-234">Teams on VDI with calling and meetings</span></span>

<span data-ttu-id="03d2b-235">除了聊天和协作，使用基于 Citrix 的平台提供与呼叫和会议支持的 VDI 团队。</span><span class="sxs-lookup"><span data-stu-id="03d2b-235">In addition to chat and collaboration, Teams on VDI with calling and meeting support is available with Citrix-based platforms.</span></span> <span data-ttu-id="03d2b-236">支持的功能基于 WebRTC 媒体堆栈和特定于 Citrix 的实现。</span><span class="sxs-lookup"><span data-stu-id="03d2b-236">Supported features are based on the WebRTC media stack and Citrix-specific implementation.</span></span> <span data-ttu-id="03d2b-237">下图概括介绍了体系结构。</span><span class="sxs-lookup"><span data-stu-id="03d2b-237">The following diagram provides an overview of the architecture.</span></span>

![显示 VDI 体系结构上的团队的图表](media/teams-on-vdi-architecture.png)

<span data-ttu-id="03d2b-239">不支持以下呼叫和会议功能：</span><span class="sxs-lookup"><span data-stu-id="03d2b-239">These calling and meeting features are not supported:</span></span>

- <span data-ttu-id="03d2b-240">增强的紧急服务</span><span class="sxs-lookup"><span data-stu-id="03d2b-240">Enhanced emergency services</span></span>
- <span data-ttu-id="03d2b-241">团队应用和设备之间的 HID 按钮和 LED 控件</span><span class="sxs-lookup"><span data-stu-id="03d2b-241">HID buttons and LED controls between the Teams app and devices</span></span>
- <span data-ttu-id="03d2b-242">背景模糊和效果</span><span class="sxs-lookup"><span data-stu-id="03d2b-242">Background blur and effects</span></span>
- <span data-ttu-id="03d2b-243">广播/实时事件</span><span class="sxs-lookup"><span data-stu-id="03d2b-243">Broadcast/live events</span></span>
- <span data-ttu-id="03d2b-244">基于位置的路由（LBR）</span><span class="sxs-lookup"><span data-stu-id="03d2b-244">Location-Based Routing (LBR)</span></span>
- <span data-ttu-id="03d2b-245">呼叫寄存</span><span class="sxs-lookup"><span data-stu-id="03d2b-245">Call park</span></span>
- <span data-ttu-id="03d2b-246">通话队列</span><span class="sxs-lookup"><span data-stu-id="03d2b-246">Call queue</span></span>

> [!IMPORTANT]
> <span data-ttu-id="03d2b-247">如果当前在 VDI 中运行团队没有 AV 优化，并且你使用尚不支持的功能（例如，在应用共享时授予和控制），则必须设置 Citrix 策略以关闭团队重定向。</span><span class="sxs-lookup"><span data-stu-id="03d2b-247">If you currently run Teams without AV optimization in VDI and you use features that are not supported yet for optimization (such as Give and take control when app sharing), you have to set Citrix policies to turn off Teams redirection.</span></span> <span data-ttu-id="03d2b-248">这意味着不会优化团队媒体会话。</span><span class="sxs-lookup"><span data-stu-id="03d2b-248">This means that Teams media sessions won’t be optimized.</span></span> <span data-ttu-id="03d2b-249">有关如何设置策略以关闭团队重定向的步骤，请参阅此[Citrix 网站](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/policies/reference/ica-policy-settings/multimedia-policy-settings.html)。</span><span class="sxs-lookup"><span data-stu-id="03d2b-249">For steps on how to set policies to turn off Teams redirection, see this [Citrix website](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/policies/reference/ica-policy-settings/multimedia-policy-settings.html).</span></span>

<span data-ttu-id="03d2b-250">我们正在努力添加目前仅在非 VDI 环境中可用的呼叫和会议功能。</span><span class="sxs-lookup"><span data-stu-id="03d2b-250">We're working on adding calling and meeting features that are currently only available in non-VDI environments.</span></span> <span data-ttu-id="03d2b-251">这些功能可能包括对质量、其他屏幕共享方案以及最近添加到团队的高级功能的更多管理控制。</span><span class="sxs-lookup"><span data-stu-id="03d2b-251">These may include more admin control over quality, additional screen sharing scenarios, and advanced features recently added to Teams.</span></span> <span data-ttu-id="03d2b-252">联系你的团队代表了解有关即将推出的功能的详细信息。</span><span class="sxs-lookup"><span data-stu-id="03d2b-252">Contact your Teams representative to learn more about upcoming features.</span></span>

### <a name="network-requirements"></a><span data-ttu-id="03d2b-253">网络要求</span><span class="sxs-lookup"><span data-stu-id="03d2b-253">Network requirements</span></span>

<span data-ttu-id="03d2b-254">我们建议你对环境进行评估，以确定任何风险和要求，这些风险和要求会影响你的整体云语音和视频部署。</span><span class="sxs-lookup"><span data-stu-id="03d2b-254">We recommend that you evaluate your environment to identify any risks and requirements that can influence your overall cloud voice and video deployment.</span></span> <span data-ttu-id="03d2b-255">使用[Skype For Business 网络评估工具](https://www.microsoft.com/download/details.aspx?id=53885)测试您的网络是否已准备好使用团队。</span><span class="sxs-lookup"><span data-stu-id="03d2b-255">Use the [Skype for Business Network Assessment Tool](https://www.microsoft.com/download/details.aspx?id=53885) to test whether your network is ready for Teams.</span></span>

<span data-ttu-id="03d2b-256">若要了解有关如何为团队准备网络的详细信息，请参阅[为团队准备组织的网络](prepare-network.md)。</span><span class="sxs-lookup"><span data-stu-id="03d2b-256">To learn more about how to prepare your network for Teams, see [Prepare your organization's network for  Teams](prepare-network.md).</span></span>

### <a name="migrate-from-skype-for-business-on-vdi-to-teams-on-vdi"></a><span data-ttu-id="03d2b-257">在 vdi 上从 Skype for Business 迁移到 VDI 上的团队</span><span class="sxs-lookup"><span data-stu-id="03d2b-257">Migrate from Skype for Business on VDI to Teams on VDI</span></span>

<span data-ttu-id="03d2b-258">如果你要从 VDI 的 Skype for Business 迁移到 VDI 上的团队，除了两个应用程序之间的区别之外，还有一些差异。</span><span class="sxs-lookup"><span data-stu-id="03d2b-258">If you're migrating from Skype for Business on VDI to Teams on VDI, besides the differences between the two applications, there are some differences when VDI is also implemented.</span></span> <span data-ttu-id="03d2b-259">Skype for Business VDI 中的团队 VDI 目前不支持的某些功能如下所示：</span><span class="sxs-lookup"><span data-stu-id="03d2b-259">Some capabilities that aren’t currently supported in Teams VDI that are in Skype for Business VDI are as follows:</span></span>

- <span data-ttu-id="03d2b-260">利用限制媒体比特率的策略控制 VDI 呼叫体验</span><span class="sxs-lookup"><span data-stu-id="03d2b-260">Control of VDI calling experiences with policies for limiting media bitrate</span></span>
- <span data-ttu-id="03d2b-261">用于禁用 VDI 中的某些 AV 功能的每个平台策略</span><span class="sxs-lookup"><span data-stu-id="03d2b-261">Per-platform policy to disable some AV features in VDI</span></span>
- <span data-ttu-id="03d2b-262">在应用共享时提供和获取控制权</span><span class="sxs-lookup"><span data-stu-id="03d2b-262">Give and take control when app sharing</span></span>
- <span data-ttu-id="03d2b-263">不带音频聊天的屏幕共享</span><span class="sxs-lookup"><span data-stu-id="03d2b-263">Screen share from chat without audio</span></span>
- <span data-ttu-id="03d2b-264">同时视频和屏幕共享发送和接收</span><span class="sxs-lookup"><span data-stu-id="03d2b-264">Simultaneous video and screen sharing send and receive</span></span>

### <a name="teams-on-chrome-browser-versus-teams-desktop-app-for-vdi"></a><span data-ttu-id="03d2b-265">Chrome 浏览器上的团队与 VDI 的团队桌面应用</span><span class="sxs-lookup"><span data-stu-id="03d2b-265">Teams on Chrome browser versus Teams desktop app for VDI</span></span>

<span data-ttu-id="03d2b-266">Chrome 浏览器上的团队不会通过 AV 优化提供适用于 VDI 的团队桌面应用的替代项。</span><span class="sxs-lookup"><span data-stu-id="03d2b-266">Teams on Chrome browser doesn't provide a replacement for the Teams desktop app for VDI with AV optimization.</span></span> <span data-ttu-id="03d2b-267">聊天和协作体验按预期工作。</span><span class="sxs-lookup"><span data-stu-id="03d2b-267">The chat and collaboration experience works as expected.</span></span> <span data-ttu-id="03d2b-268">需要媒体时，有一些体验可能无法在 Chrome 浏览器中满足用户的预期。</span><span class="sxs-lookup"><span data-stu-id="03d2b-268">When media is needed, there are some experiences that may not meet user expectations on the Chrome browser.</span></span>

- <span data-ttu-id="03d2b-269">音频和视频流体验可能不是最佳的。</span><span class="sxs-lookup"><span data-stu-id="03d2b-269">The audio and video streaming experience may not be optimal.</span></span> <span data-ttu-id="03d2b-270">用户可能会遇到延迟或降低质量。</span><span class="sxs-lookup"><span data-stu-id="03d2b-270">Users may experiences delays or reduced quality.</span></span>
- <span data-ttu-id="03d2b-271">"设备设置" 在浏览器设置中不可用。</span><span class="sxs-lookup"><span data-stu-id="03d2b-271">Device settings aren't available in browser settings.</span></span>
- <span data-ttu-id="03d2b-272">设备管理通过浏览器进行处理，并在浏览器网站设置中需要多个设置。</span><span class="sxs-lookup"><span data-stu-id="03d2b-272">Device management is handled through the browser and requires multiple settings in browser site settings.</span></span>
- <span data-ttu-id="03d2b-273">可能还需要在 Windows 设备管理中设置设备设置。</span><span class="sxs-lookup"><span data-stu-id="03d2b-273">Device settings may also need to be set in Windows device management.</span></span>

## <a name="teams-on-vdi-with-chat-and-collaboration"></a><span data-ttu-id="03d2b-274">具有聊天和协作功能的 VDI 团队</span><span class="sxs-lookup"><span data-stu-id="03d2b-274">Teams on VDI with chat and collaboration</span></span>

<span data-ttu-id="03d2b-275">如果你的组织希望仅使用团队中的聊天和协作功能，你可以设置用户级策略以关闭团队中的呼叫和会议功能。</span><span class="sxs-lookup"><span data-stu-id="03d2b-275">If your organization wants to only use chat and collaboration features in Teams, you can set user-level policies to turn off calling and meeting functionality in Teams.</span></span> <span data-ttu-id="03d2b-276">此功能级别不需要 Citrix 虚拟应用和桌面。</span><span class="sxs-lookup"><span data-stu-id="03d2b-276">This feature level doesn't require Citrix Virtual Apps and Desktops.</span></span>

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a><span data-ttu-id="03d2b-277">设置用于关闭呼叫和会议功能的策略</span><span class="sxs-lookup"><span data-stu-id="03d2b-277">Set policies to turn off calling and meeting functionality</span></span>

<span data-ttu-id="03d2b-278">你可以使用 Microsoft 团队管理中心或 PowerShell 设置策略。</span><span class="sxs-lookup"><span data-stu-id="03d2b-278">You can set policies by using the Microsoft Teams admin center or PowerShell.</span></span> <span data-ttu-id="03d2b-279">需要花费一些时间（几个小时）才能传播策略更改。</span><span class="sxs-lookup"><span data-stu-id="03d2b-279">It can take some time (a few hours) for the policy changes to propagate.</span></span> <span data-ttu-id="03d2b-280">如果你没有立即看到给定帐户的更改，请在几个小时后重试。</span><span class="sxs-lookup"><span data-stu-id="03d2b-280">If you don’t see changes for a given account immediately, try again in a few hours.</span></span>

<span data-ttu-id="03d2b-281">[**通话策略**](teams-calling-policy.md)：团队包括内置的 DisallowCalling 呼叫策略，其中所有的通话功能均处于关闭状态。</span><span class="sxs-lookup"><span data-stu-id="03d2b-281">[**Calling polices**](teams-calling-policy.md): Teams includes the built-in DisallowCalling calling policy, in which all calling features are turned off.</span></span> <span data-ttu-id="03d2b-282">将 DisallowCalling 策略分配给组织中使用虚拟环境中的团队的所有用户。</span><span class="sxs-lookup"><span data-stu-id="03d2b-282">Assign the DisallowCalling policy to all users in your organization who use Teams in a virtualized environment.</span></span>

<span data-ttu-id="03d2b-283">[**会议策略**](meeting-policies-in-teams.md)：团队包括内置的 AllOff 会议策略，其中所有会议功能均处于关闭状态。</span><span class="sxs-lookup"><span data-stu-id="03d2b-283">[**Meeting policies**](meeting-policies-in-teams.md): Teams includes the built-in AllOff meeting policy, in which all meeting features are turned off.</span></span> <span data-ttu-id="03d2b-284">将 AllOff 策略分配给组织中使用虚拟环境中的团队的所有用户。</span><span class="sxs-lookup"><span data-stu-id="03d2b-284">Assign the AllOff policy to all users in your organization who use Teams in a virtualized environment.</span></span>

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a><span data-ttu-id="03d2b-285">使用 Microsoft 团队管理中心分配策略</span><span class="sxs-lookup"><span data-stu-id="03d2b-285">Assign policies using the Microsoft Teams admin center</span></span>

<span data-ttu-id="03d2b-286">要将 DisallowCalling 呼叫策略和 AllOff 会议策略分配给用户，请按照下列步骤操作：</span><span class="sxs-lookup"><span data-stu-id="03d2b-286">To assign the DisallowCalling calling policy and the AllOff meeting policy to users, follow these steps:</span></span>

1. <span data-ttu-id="03d2b-287">在 Microsoft 团队管理中心的左侧导航中，转到 "**用户**"。</span><span class="sxs-lookup"><span data-stu-id="03d2b-287">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="03d2b-288">通过单击用户名左侧的用户选择用户，然后单击 "**编辑设置**"。</span><span class="sxs-lookup"><span data-stu-id="03d2b-288">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="03d2b-289">请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="03d2b-289">Do the following:</span></span>
    1.  <span data-ttu-id="03d2b-290">在 "**呼叫策略**" 下，单击 " **DisallowCalling**"。</span><span class="sxs-lookup"><span data-stu-id="03d2b-290">Under **Calling policy**, click **DisallowCalling**.</span></span>
    2.  <span data-ttu-id="03d2b-291">在 "**会议策略**" 下，单击 " **AllOff**"。</span><span class="sxs-lookup"><span data-stu-id="03d2b-291">Under **Meeting policy**, click **AllOff**.</span></span>
4. <span data-ttu-id="03d2b-292">单击“**应用**”。</span><span class="sxs-lookup"><span data-stu-id="03d2b-292">Click **Apply**.</span></span>

<span data-ttu-id="03d2b-293">若要一次为多个用户分配策略，请参阅[批量编辑团队用户设置](edit-user-settings-in-bulk.md)。</span><span class="sxs-lookup"><span data-stu-id="03d2b-293">To assign a policy to multiple users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="03d2b-294">或者，您也可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="03d2b-294">Or, you can also do the following:</span></span>

1. <span data-ttu-id="03d2b-295">在 Microsoft 团队管理中心的左侧导航中，转到要分配的策略。</span><span class="sxs-lookup"><span data-stu-id="03d2b-295">In the left navigation of the Microsoft Teams admin center, go to the policy you want to assign.</span></span> <span data-ttu-id="03d2b-296">例如：</span><span class="sxs-lookup"><span data-stu-id="03d2b-296">For example:</span></span>
    - <span data-ttu-id="03d2b-297">转到 "**语音** > **呼叫策略**"，然后单击 " **DisallowCalling**"。</span><span class="sxs-lookup"><span data-stu-id="03d2b-297">Go to **Voice** > **Calling policies**, and then click **DisallowCalling**.</span></span>
    - <span data-ttu-id="03d2b-298">转到 "**会议** > **会议策略**"，然后单击 " **AllOff**"。</span><span class="sxs-lookup"><span data-stu-id="03d2b-298">Go to **Meetings** > **Meeting policies**, and then click **AllOff**.</span></span>
3. <span data-ttu-id="03d2b-299">选择 "**管理用户**"。</span><span class="sxs-lookup"><span data-stu-id="03d2b-299">Select **Manage users**.</span></span>
4. <span data-ttu-id="03d2b-300">在 "**管理用户**" 窗格中，按 "显示名称" 或 "按用户名搜索用户"，选择名称，然后单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="03d2b-300">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="03d2b-301">对要添加的每个用户重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="03d2b-301">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="03d2b-302">添加完用户后，单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="03d2b-302">When you're finished adding users, click **Save**.</span></span>

#### <a name="assign-policies-using-powershell"></a><span data-ttu-id="03d2b-303">使用 PowerShell 分配策略</span><span class="sxs-lookup"><span data-stu-id="03d2b-303">Assign policies using PowerShell</span></span>

<span data-ttu-id="03d2b-304">以下示例显示了如何使用[Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy)向用户分配 DisallowCalling 调用策略。</span><span class="sxs-lookup"><span data-stu-id="03d2b-304">The following example shows how to use the [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) to assign the DisallowCalling calling policy to a user.</span></span>

```
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity “user email id”
```

<span data-ttu-id="03d2b-305">若要了解有关使用 PowerShell 管理通话策略的详细信息，请参阅[设置 CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="03d2b-305">To learn more about using PowerShell to manage calling policies, see [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).</span></span>

<span data-ttu-id="03d2b-306">以下示例显示了如何使用[Grant-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy)将 AllOff 会议策略分配给用户。</span><span class="sxs-lookup"><span data-stu-id="03d2b-306">The following example shows how to use the [Grant-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) to assign the AllOff meeting policy to a user.</span></span>

```
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity “user email id”
```

<span data-ttu-id="03d2b-307">若要了解有关使用 PowerShell 管理会议策略的详细信息，请参阅[设置 CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="03d2b-307">To learn more about using PowerShell to manage meeting policies, see [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).</span></span>

## <a name="migrate-teams-on-vdi-with-chat-and-collaboration-to-citrix-with-calling-and-meetings"></a><span data-ttu-id="03d2b-308">通过通话和会议将团队与聊天和协作迁移到 Citrix</span><span class="sxs-lookup"><span data-stu-id="03d2b-308">Migrate Teams on VDI with chat and collaboration to Citrix with calling and meetings</span></span>

<span data-ttu-id="03d2b-309">如果您在 VDI 上有一个现有团队的实现，其中你已设置了用户级策略以关闭呼叫和会议功能，并且你要使用 AV 优化功能迁移到 Citrix，则必须设置策略以启用呼叫和适用于 VDI 用户的团队的会议功能。</span><span class="sxs-lookup"><span data-stu-id="03d2b-309">If you have an existing implementation of Teams on VDI with chat and collaboration in which you had set user-level policies to turn off calling and meeting functionality, and you're migrating to Citrix with AV optimization, you must set policies to turn on calling and meeting functionality for those Teams on VDI users.</span></span>

### <a name="set-policies-to-turn-on-calling-and-meeting-functionality"></a><span data-ttu-id="03d2b-310">设置启用呼叫和会议功能的策略</span><span class="sxs-lookup"><span data-stu-id="03d2b-310">Set policies to turn on calling and meeting functionality</span></span>

<span data-ttu-id="03d2b-311">你可以使用 Microsoft 团队管理中心或 PowerShell 为你的用户设置和分配呼叫和会议策略。</span><span class="sxs-lookup"><span data-stu-id="03d2b-311">You can use the Microsoft Teams admin center or PowerShell to set and assign calling and meeting policies to your users.</span></span> <span data-ttu-id="03d2b-312">需要花费一些时间（几个小时）才能传播策略更改。</span><span class="sxs-lookup"><span data-stu-id="03d2b-312">It can take some time (a few hours) for policy changes to propagate.</span></span> <span data-ttu-id="03d2b-313">如果你没有立即看到给定帐户的更改，请过几个小时后重试。</span><span class="sxs-lookup"><span data-stu-id="03d2b-313">If you don’t see changes for a given account immediately, try again after a few hours.</span></span>

<span data-ttu-id="03d2b-314">[**通话策略**](teams-calling-policy.md)：在团队中调用策略控制用户可以使用哪些通话功能。</span><span class="sxs-lookup"><span data-stu-id="03d2b-314">[**Calling polices**](teams-calling-policy.md): Calling policies in Teams control which calling features are available to users.</span></span> <span data-ttu-id="03d2b-315">团队包括内置的 AllowCalling 呼叫策略，其中所有的通话功能均处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="03d2b-315">Teams includes the built-in AllowCalling calling policy, in which all calling features are turned on.</span></span> <span data-ttu-id="03d2b-316">若要打开所有通话功能，请分配 AllowCalling 策略。</span><span class="sxs-lookup"><span data-stu-id="03d2b-316">To turn on all calling features, assign the AllowCalling policy.</span></span> <span data-ttu-id="03d2b-317">或者，创建自定义呼叫策略以打开所需的通话功能，并将其分配给用户。</span><span class="sxs-lookup"><span data-stu-id="03d2b-317">Or, create a custom calling policy to turn on the calling features that you want and assign it to users.</span></span> 

<span data-ttu-id="03d2b-318">[**会议策略**](meeting-policies-in-teams.md)：团队中的会议策略控制用户可以创建的会议类型，以及由组织中的用户安排的可供会议参与者使用的功能。</span><span class="sxs-lookup"><span data-stu-id="03d2b-318">[**Meeting policies**](meeting-policies-in-teams.md): Meeting policies in Teams control the types of meetings that users can create and the features that are available to meeting participants that are scheduled by users in your organization.</span></span> <span data-ttu-id="03d2b-319">团队包括内置的 AllOn 会议策略，其中所有会议功能均处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="03d2b-319">Teams includes the built-in AllOn meeting policy, in which all meeting features are turned on.</span></span> <span data-ttu-id="03d2b-320">若要打开所有会议功能，请分配 AllOn 策略。</span><span class="sxs-lookup"><span data-stu-id="03d2b-320">To turn on all meeting features, assign the AllOn policy.</span></span> <span data-ttu-id="03d2b-321">或者，创建自定义会议策略以打开所需的会议功能，并向其分配用户。</span><span class="sxs-lookup"><span data-stu-id="03d2b-321">Or, create a custom meeting policy to turn on the meeting features that you want and assign it users.</span></span>

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a><span data-ttu-id="03d2b-322">使用 Microsoft 团队管理中心分配策略</span><span class="sxs-lookup"><span data-stu-id="03d2b-322">Assign policies using the Microsoft Teams admin center</span></span>

<span data-ttu-id="03d2b-323">要将 AllowCalling 呼叫策略和 AllOn 会议策略分配给用户，请按照下列步骤操作：</span><span class="sxs-lookup"><span data-stu-id="03d2b-323">To assign the AllowCalling calling policy and the AllOn meeting policy to users, follow these steps:</span></span>

1. <span data-ttu-id="03d2b-324">在 Microsoft 团队管理中心的左侧导航中，转到 "**用户**"。</span><span class="sxs-lookup"><span data-stu-id="03d2b-324">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="03d2b-325">通过单击用户名左侧的用户选择用户，然后单击 "**编辑设置**"。</span><span class="sxs-lookup"><span data-stu-id="03d2b-325">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="03d2b-326">请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="03d2b-326">Do the following:</span></span>
    1.  <span data-ttu-id="03d2b-327">在 "**呼叫策略**" 下，单击 " **AllowCalling**"。</span><span class="sxs-lookup"><span data-stu-id="03d2b-327">Under **Calling policy**, click **AllowCalling**.</span></span>
    2.  <span data-ttu-id="03d2b-328">在 "**会议策略**" 下，单击 " **AllOn**"。</span><span class="sxs-lookup"><span data-stu-id="03d2b-328">Under **Meeting policy**, click **AllOn**.</span></span>
4. <span data-ttu-id="03d2b-329">单击“**应用**”。</span><span class="sxs-lookup"><span data-stu-id="03d2b-329">Click **Apply**.</span></span>

<span data-ttu-id="03d2b-330">若要一次为多个用户分配策略，请参阅[批量编辑团队用户设置](edit-user-settings-in-bulk.md)。</span><span class="sxs-lookup"><span data-stu-id="03d2b-330">To assign a policy to multiple users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="03d2b-331">或者，您也可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="03d2b-331">Or, you can also do the following:</span></span>

1. <span data-ttu-id="03d2b-332">在 Microsoft 团队管理中心的左侧导航中，转到要分配的策略。</span><span class="sxs-lookup"><span data-stu-id="03d2b-332">In the left navigation of the Microsoft Teams admin center, go to the policy you want to assign.</span></span> <span data-ttu-id="03d2b-333">例如：</span><span class="sxs-lookup"><span data-stu-id="03d2b-333">For example:</span></span>
    - <span data-ttu-id="03d2b-334">转到 "**语音** > **呼叫策略**"，然后单击 " **AllowCalling**"。</span><span class="sxs-lookup"><span data-stu-id="03d2b-334">Go to **Voice** > **Calling policies**, and then click **AllowCalling**.</span></span>
    - <span data-ttu-id="03d2b-335">转到 "**会议** > **会议策略**"，然后单击 " **AllOn**"。</span><span class="sxs-lookup"><span data-stu-id="03d2b-335">Go to **Meetings** > **Meeting policies**, and then click **AllOn**.</span></span>
3. <span data-ttu-id="03d2b-336">选择 "**管理用户**"。</span><span class="sxs-lookup"><span data-stu-id="03d2b-336">Select **Manage users**.</span></span>
4. <span data-ttu-id="03d2b-337">在 "**管理用户**" 窗格中，按 "显示名称" 或 "按用户名搜索用户"，选择名称，然后单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="03d2b-337">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="03d2b-338">对要添加的每个用户重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="03d2b-338">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="03d2b-339">添加完用户后，单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="03d2b-339">When you're finished adding users, click **Save**.</span></span>

#### <a name="assign-policies-using-powershell"></a><span data-ttu-id="03d2b-340">使用 PowerShell 分配策略</span><span class="sxs-lookup"><span data-stu-id="03d2b-340">Assign policies using PowerShell</span></span>

<span data-ttu-id="03d2b-341">以下示例显示了如何使用[Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy)向用户分配 AllowCalling 调用策略。</span><span class="sxs-lookup"><span data-stu-id="03d2b-341">The following example shows how to use the [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) to assign the AllowCalling calling policy to a user.</span></span>

```
Grant-CsTeamsCallingPolicy -PolicyName AllowCalling -Identity “user email id”
```

<span data-ttu-id="03d2b-342">若要了解有关使用 PowerShell 管理通话策略的详细信息，请参阅[设置 CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="03d2b-342">To learn more about using PowerShell to manage calling policies, see [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).</span></span>

<span data-ttu-id="03d2b-343">以下示例显示了如何使用[Grant-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy)将 AllOn 会议策略分配给用户。</span><span class="sxs-lookup"><span data-stu-id="03d2b-343">The following example shows how to use the [Grant-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) to assign the AllOn meeting policy to a user.</span></span>

```
Grant-CsTeamsMeetingPolicy -PolicyName AllOn -Identity “user email id”
```

<span data-ttu-id="03d2b-344">若要了解有关使用 PowerShell 管理会议策略的详细信息，请参阅[设置 CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="03d2b-344">To learn more about using PowerShell to manage meeting policies, see [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).</span></span>

## <a name="known-issues-and-limitations"></a><span data-ttu-id="03d2b-345">已知问题和限制</span><span class="sxs-lookup"><span data-stu-id="03d2b-345">Known issues and limitations</span></span>

### <a name="client-deployment-installation-and-setup"></a><span data-ttu-id="03d2b-346">客户端部署、安装和设置</span><span class="sxs-lookup"><span data-stu-id="03d2b-346">Client deployment, installation, and setup</span></span>

- <span data-ttu-id="03d2b-347">对于每台计算机安装，不会以非 VDI 团队客户端的方式自动更新 VDI 上的团队。</span><span class="sxs-lookup"><span data-stu-id="03d2b-347">With per-machine installation, Teams on VDI isn't automatically updated in the way that non-VDI Teams clients are.</span></span> <span data-ttu-id="03d2b-348">你必须按照 "在[VDI 中安装团队桌面应用](#install-the-teams-desktop-app-on-vdi)" 部分中所述，通过安装新 MSI 来更新 VM 映像。</span><span class="sxs-lookup"><span data-stu-id="03d2b-348">You have to update the VM image by installing a new MSI as described in the [Install the Teams desktop app on VDI](#install-the-teams-desktop-app-on-vdi) section.</span></span> <span data-ttu-id="03d2b-349">必须卸载当前版本才能更新到较新版本。</span><span class="sxs-lookup"><span data-stu-id="03d2b-349">You must uninstall the current version to update to a newer version.</span></span>
- <span data-ttu-id="03d2b-350">Citrix 目前不支持基于 MacOs 和 Linux 的客户端。</span><span class="sxs-lookup"><span data-stu-id="03d2b-350">MacOs and Linux-based clients are not supported by Citrix at this time.</span></span>
- <span data-ttu-id="03d2b-351">Citrix 不支持使用终结点上定义的显式 HTTP 代理。</span><span class="sxs-lookup"><span data-stu-id="03d2b-351">Citrix doesn't support the use of explicit HTTP proxies defined on an endpoint.</span></span> 

### <a name="calling-and-meetings"></a><span data-ttu-id="03d2b-352">通话和会议</span><span class="sxs-lookup"><span data-stu-id="03d2b-352">Calling and meetings</span></span>

- <span data-ttu-id="03d2b-353">与 Skype for business 的互操作性仅限于音频通话，无视频模态。</span><span class="sxs-lookup"><span data-stu-id="03d2b-353">Interoperability with Skype for Business is limited to audio calls, no video modality.</span></span>
- <span data-ttu-id="03d2b-354">目前不支持双音频多频率（DTMF）与电话系统交互。</span><span class="sxs-lookup"><span data-stu-id="03d2b-354">Dual Tone Multi Frequency (DTMF) interaction with telephony systems  is currently not supported.</span></span>
- <span data-ttu-id="03d2b-355">以匿名用户身份加入团队会议并非 AV 优化。</span><span class="sxs-lookup"><span data-stu-id="03d2b-355">Joining Teams meetings as an anonymous user isn't AV-optimized.</span></span> <span data-ttu-id="03d2b-356">用户可以加入会议并具有非优化的体验。</span><span class="sxs-lookup"><span data-stu-id="03d2b-356">The user can join the meeting and have a non-optimized experience.</span></span>
- <span data-ttu-id="03d2b-357">会议或群组通话仅支持单个传入视频流。</span><span class="sxs-lookup"><span data-stu-id="03d2b-357">Only a single incoming video stream is supported in meetings or group calls.</span></span> <span data-ttu-id="03d2b-358">当多人发送视频时，在任何给定时间仅显示主要演讲者的视频。</span><span class="sxs-lookup"><span data-stu-id="03d2b-358">When multiple people send video, only the dominant speaker's video is shown at any given time.</span></span>  
- <span data-ttu-id="03d2b-359">传入和传出视频流分辨率仅限于720p 分辨率。</span><span class="sxs-lookup"><span data-stu-id="03d2b-359">Incoming and outgoing video stream resolution is limited to 720p resolution.</span></span> <span data-ttu-id="03d2b-360">这是一个 WebRTC 限制。</span><span class="sxs-lookup"><span data-stu-id="03d2b-360">This is a WebRTC limitation.</span></span>
- <span data-ttu-id="03d2b-361">仅支持来自传入相机或屏幕共享流的一个视频流。</span><span class="sxs-lookup"><span data-stu-id="03d2b-361">Only one video stream from an incoming camera or screen share stream is supported.</span></span> <span data-ttu-id="03d2b-362">当存在传入屏幕共享时，将显示该屏幕共享，而不是主扬声器的视频。</span><span class="sxs-lookup"><span data-stu-id="03d2b-362">When there's an incoming screen share, that screen share is shown it instead of the video of the dominant speaker.</span></span>
- <span data-ttu-id="03d2b-363">出站屏幕共享：</span><span class="sxs-lookup"><span data-stu-id="03d2b-363">Outgoing screen sharing:</span></span>
    - <span data-ttu-id="03d2b-364">不支持应用程序共享。</span><span class="sxs-lookup"><span data-stu-id="03d2b-364">Application sharing is not supported.</span></span>
- <span data-ttu-id="03d2b-365">授予控制权并获得控制权：</span><span class="sxs-lookup"><span data-stu-id="03d2b-365">Give control and take control:</span></span>  
    - <span data-ttu-id="03d2b-366">在屏幕共享或应用程序共享会话期间不受支持。</span><span class="sxs-lookup"><span data-stu-id="03d2b-366">Not supported during a screen sharing or application sharing session.</span></span>
    - <span data-ttu-id="03d2b-367">在 PowerPoint 共享会话期间受支持。</span><span class="sxs-lookup"><span data-stu-id="03d2b-367">Supported during a PowerPoint sharing session.</span></span>  
- <span data-ttu-id="03d2b-368">不支持 CWA 上的高 DPI 缩放。</span><span class="sxs-lookup"><span data-stu-id="03d2b-368">High DPI scaling on CWA is not supported.</span></span>

<span data-ttu-id="03d2b-369">对于不与 VDI 无关的团队已知问题，请参阅[团队的已知问题](Known-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="03d2b-369">For Teams known issues that aren’t related to VDI, see [Known issues for Teams](Known-issues.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="03d2b-370">疑难解答</span><span class="sxs-lookup"><span data-stu-id="03d2b-370">Troubleshooting</span></span>

#### <a name="troubleshoot-citrix-components"></a><span data-ttu-id="03d2b-371">Citrix 组件疑难解答</span><span class="sxs-lookup"><span data-stu-id="03d2b-371">Troubleshoot Citrix components</span></span>

<span data-ttu-id="03d2b-372">有关如何解决 VDA 和 CWA 问题的信息，请参阅[此 Citrix 网站](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html)。</span><span class="sxs-lookup"><span data-stu-id="03d2b-372">For information on how to troubleshoot VDA and CWA issues, see [this Citrix website](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html).</span></span>

## <a name="related-topics"></a><span data-ttu-id="03d2b-373">相关主题</span><span class="sxs-lookup"><span data-stu-id="03d2b-373">Related topics</span></span>

- [<span data-ttu-id="03d2b-374">使用 MSI 安装 Microsoft 团队</span><span class="sxs-lookup"><span data-stu-id="03d2b-374">Install Microsoft Teams using MSI</span></span>](msi-deployment.md)
- [<span data-ttu-id="03d2b-375">Teams PowerShell 概览</span><span class="sxs-lookup"><span data-stu-id="03d2b-375">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
