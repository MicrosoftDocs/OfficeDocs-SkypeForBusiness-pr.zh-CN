---
title: Skype for Business Server 2015 资源工具包工具文档
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 1/20/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b1c341f1-86fa-479d-ba4d-28df5a4c1622
description: 本主题介绍 Skype for Business Server 2015 资源工具包中的工具，包括每个工具的用途及其使用示例。 Skype for Business Server 2015 资源工具包可帮助部署和管理 Skype for Business Server 2015 的 IT 管理员更轻松地执行常规任务。 例如，Web Conf Data 工具可用于轻松控制用户在联机会议期间上载的数据。 SEFAUtil 工具可用于为用户设置代理人呼叫转发和应答。 我们鼓励 IT 管理员使用这些工具更有效地管理 Skype for Business Server 2015。
ms.openlocfilehash: bf1a1d946c998466b118e0ab2038044a48d90970
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822032"
---
# <a name="skype-for-business-server-2015-resource-kit-tools-documentation"></a><span data-ttu-id="3275a-107">Skype for Business Server 2015 资源工具包工具文档</span><span class="sxs-lookup"><span data-stu-id="3275a-107">Skype for Business Server 2015 Resource Kit Tools Documentation</span></span>

<span data-ttu-id="3275a-108">本主题介绍 Skype for Business Server 2015 资源工具包中的工具，包括每个工具的用途及其使用示例。</span><span class="sxs-lookup"><span data-stu-id="3275a-108">This topic describes the tools in the Skype for Business Server 2015 Resource Kit, including the purpose of each tool, and examples of its use.</span></span> <span data-ttu-id="3275a-109">Skype for Business Server 2015 资源工具包可帮助部署和管理 Skype for Business Server 2015 的 IT 管理员更轻松地执行常规任务。</span><span class="sxs-lookup"><span data-stu-id="3275a-109">The Skype for Business Server 2015 Resource Kit helps to make routine tasks easier for IT administrators who deploy and manage Skype for Business Server 2015.</span></span> <span data-ttu-id="3275a-110">例如 **，Web Conf Data** 工具可用于轻松控制用户在联机会议期间上载的数据。</span><span class="sxs-lookup"><span data-stu-id="3275a-110">For example, the **Web Conf Data** tool can be used to easily control data that is uploaded by users during an online meeting.</span></span> <span data-ttu-id="3275a-111">**SEFAUtil** 工具可用于为用户设置代理人呼叫转发和应答。</span><span class="sxs-lookup"><span data-stu-id="3275a-111">The **SEFAUtil** tool can be used to set up delegate call forwarding and answering for users.</span></span> <span data-ttu-id="3275a-112">我们鼓励 IT 管理员使用这些工具更有效地管理 Skype for Business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="3275a-112">We encourage IT administrators to use these tools to more effectively manage Skype for Business Server 2015.</span></span>

## <a name="installation-of-the-resource-kit-tools"></a><span data-ttu-id="3275a-113">安装资源工具包工具</span><span class="sxs-lookup"><span data-stu-id="3275a-113">Installation of the Resource Kit Tools</span></span>

<span data-ttu-id="3275a-114">若要安装 Skype for Business Server 2015 资源工具包，请 [OCSReskit.msi](https://www.microsoft.com/download/details.aspx?id=52631) 下载中心下载。</span><span class="sxs-lookup"><span data-stu-id="3275a-114">To install the Skype for Business Server 2015 Resource Kit, download [OCSReskit.msi](https://www.microsoft.com/download/details.aspx?id=52631) from the Download Center.</span></span>

<span data-ttu-id="3275a-115">运行 **OCSResKit.msi** 以执行简单的安装。</span><span class="sxs-lookup"><span data-stu-id="3275a-115">Run **OCSResKit.msi** to do a simple installation.</span></span> <span data-ttu-id="3275a-116">.msi 将安装以下路径中的所有工具 **：%Program Files%\Skype for Business Server 2015\ResKit。**</span><span class="sxs-lookup"><span data-stu-id="3275a-116">The .msi installs all the tools in the following path: **%Program Files%\Skype for Business Server 2015\ResKit**.</span></span> <span data-ttu-id="3275a-117">自包含可执行文件的工具在此文件夹中。</span><span class="sxs-lookup"><span data-stu-id="3275a-117">Tools that are self-contained executables are in this folder.</span></span> <span data-ttu-id="3275a-118">也具有支持文件的工具在其自己的子文件夹内。</span><span class="sxs-lookup"><span data-stu-id="3275a-118">Tools that also have supporting files are in their own subfolders.</span></span>

## <a name="supported-environments"></a><span data-ttu-id="3275a-119">支持的环境</span><span class="sxs-lookup"><span data-stu-id="3275a-119">Supported Environments</span></span>

<span data-ttu-id="3275a-120">Skype for Business Server 2015 资源工具包应安装在符合 Skype for Business Server 2015（通常用于运行 Skype for Business Server 2015）所需的规范的服务器上。</span><span class="sxs-lookup"><span data-stu-id="3275a-120">The Skype for Business Server 2015 Resource Kit should be installed on a server that meets the specifications required for Skype for Business Server 2015, usually one being used to run Skype for Business Server 2015.</span></span>

## <a name="resource-kit-tools-overview"></a><span data-ttu-id="3275a-121">资源工具包工具概述</span><span class="sxs-lookup"><span data-stu-id="3275a-121">Resource Kit Tools Overview</span></span>

<span data-ttu-id="3275a-122">以下是 Skype for Business Server 2015 资源工具包中提供的工具列表。</span><span class="sxs-lookup"><span data-stu-id="3275a-122">The following is a list of the tools that are provided in the Skype for Business Server 2015 Resource Kit.</span></span> <span data-ttu-id="3275a-123">以下各节介绍了每个工具的说明，包括要求和示例用法。</span><span class="sxs-lookup"><span data-stu-id="3275a-123">A description of each tool, including the requirements and example usage is covered in the following sections.</span></span>

- [<span data-ttu-id="3275a-124">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="3275a-124">ABSConfig</span></span>](resource-kit-tools.md#ABSConfig)

- [<span data-ttu-id="3275a-125">带宽策略服务监视器</span><span class="sxs-lookup"><span data-stu-id="3275a-125">Bandwidth Policy Service Monitor</span></span>](resource-kit-tools.md#bpsm)

- [<span data-ttu-id="3275a-126">带宽使用率分析器</span><span class="sxs-lookup"><span data-stu-id="3275a-126">Bandwidth Utilization Analyzer</span></span>](resource-kit-tools.md#bua)

- [<span data-ttu-id="3275a-127">呼叫 Parkometer</span><span class="sxs-lookup"><span data-stu-id="3275a-127">Call Parkometer</span></span>](resource-kit-tools.md#callpark)

- [<span data-ttu-id="3275a-128">DBAnalyze</span><span class="sxs-lookup"><span data-stu-id="3275a-128">DBAnalyze</span></span>](resource-kit-tools.md#dba)

- [<span data-ttu-id="3275a-129">导入存储服务数据</span><span class="sxs-lookup"><span data-stu-id="3275a-129">Import Storage Service Data</span></span>](resource-kit-tools.md#Issd)

- [<span data-ttu-id="3275a-130">LCSSync</span><span class="sxs-lookup"><span data-stu-id="3275a-130">LCSSync</span></span>](resource-kit-tools.md#LCSSync)

- [<span data-ttu-id="3275a-131">查找用户控制台</span><span class="sxs-lookup"><span data-stu-id="3275a-131">Lookup User Console</span></span>](resource-kit-tools.md#LUC)

- [<span data-ttu-id="3275a-132">MsTurnPing</span><span class="sxs-lookup"><span data-stu-id="3275a-132">MsTurnPing</span></span>](resource-kit-tools.md#MsTurnPing)

- [<span data-ttu-id="3275a-133">网络配置查看器</span><span class="sxs-lookup"><span data-stu-id="3275a-133">Network Configuration Viewer</span></span>](resource-kit-tools.md#NCV)

- [<span data-ttu-id="3275a-134">响应组代理实时</span><span class="sxs-lookup"><span data-stu-id="3275a-134">Response Group Agent Live</span></span>](resource-kit-tools.md#RGAL)

- [<span data-ttu-id="3275a-135">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="3275a-135">SEFAUtil</span></span>](resource-kit-tools.md#SEFAUtil)

- [<span data-ttu-id="3275a-136">SYSPrep.ps1</span><span class="sxs-lookup"><span data-stu-id="3275a-136">SYSPrep.ps1</span></span>](resource-kit-tools.md#SYSPrep)

- [<span data-ttu-id="3275a-137">未分配号码通知迁移</span><span class="sxs-lookup"><span data-stu-id="3275a-137">Unassigned Number Announcements Migration</span></span>](resource-kit-tools.md#UNAM)

- [<span data-ttu-id="3275a-138">Web Conf 数据</span><span class="sxs-lookup"><span data-stu-id="3275a-138">Web Conf Data</span></span>](resource-kit-tools.md#WebConfData)

## <a name="absconfig"></a><span data-ttu-id="3275a-139">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="3275a-139">ABSConfig</span></span>
<span data-ttu-id="3275a-140"><a name="ABSConfig"> </a></span><span class="sxs-lookup"><span data-stu-id="3275a-140"><a name="ABSConfig"> </a></span></span>

<span data-ttu-id="3275a-141">"通讯簿服务配置" (ABSConfig) 是一种管理工具，可帮助管理员在 Skype for Business Server 2015 中自定义通讯簿服务配置。</span><span class="sxs-lookup"><span data-stu-id="3275a-141">The Address Book Service Configuration tool (ABSConfig) is an administrative tool that helps administrators customize Address Book Service configuration in Skype for Business Server 2015.</span></span> <span data-ttu-id="3275a-142">此工具还使 Skype for Business Server 2015 管理员能够还原默认通讯簿服务设置。</span><span class="sxs-lookup"><span data-stu-id="3275a-142">This tool also enables Skype for Business Server 2015 administrators to restore the default Address Book Service settings.</span></span>

### <a name="description"></a><span data-ttu-id="3275a-143">说明</span><span class="sxs-lookup"><span data-stu-id="3275a-143">Description</span></span>

<span data-ttu-id="3275a-144">ABSConfig 是一个图形用户界面应用程序，使管理员能够配置与通讯簿服务相关的 Active Directory 域服务属性。</span><span class="sxs-lookup"><span data-stu-id="3275a-144">ABSConfig is a graphical user interface application that enables administrators to configure Active Directory Domain Services attributes that are related to Address Book Service.</span></span>

<span data-ttu-id="3275a-145">该工具的主要方案如下：</span><span class="sxs-lookup"><span data-stu-id="3275a-145">The primary scenarios for the tool are the following:</span></span>

- <span data-ttu-id="3275a-146">使管理员能够将 Active Directory 域服务中的属性映射到 Skype for Business Server 2015 的属性。</span><span class="sxs-lookup"><span data-stu-id="3275a-146">To enable administrators to map attributes in Active Directory Domain Services to the attributes for Skype for Business Server 2015.</span></span>

- <span data-ttu-id="3275a-147">使管理员能够指定要包含在通讯簿服务文件中或要排除的 Active Directory 域服务属性。</span><span class="sxs-lookup"><span data-stu-id="3275a-147">To enable administrators to specify the Active Directory Domain Services attribute to be included or excluded in the Address Book Service files.</span></span>

- <span data-ttu-id="3275a-148">使管理员能够还原默认的通讯簿服务设置。</span><span class="sxs-lookup"><span data-stu-id="3275a-148">To enable administrators to restore default Address Book Service settings.</span></span>

<span data-ttu-id="3275a-149">ABSConfig 工具可通过使用文件启动ABSConfig.exe文件。</span><span class="sxs-lookup"><span data-stu-id="3275a-149">The ABSConfig tool can be started by using the ABSConfig.exe file.</span></span> <span data-ttu-id="3275a-150">该工具将打开到" **配置属性"** 选项卡。此表具有将 Active Directory 域服务属性映射到 Skype for Business Server 2015 的属性字段以及根据特定属性筛选器指定在通讯簿服务文件中包括或排除哪些用户的选项。</span><span class="sxs-lookup"><span data-stu-id="3275a-150">The tool opens to the **Configure Attributes** tab. This table has options to map Active Directory Domain Services attributes to the attribute fields for Skype for Business Server 2015 and to specify which users to include or exclude in Address Book Service files based on specific attribute filters.</span></span> <span data-ttu-id="3275a-151">它还具有自定义要包含在通讯簿文件中的电话号码值的选项。</span><span class="sxs-lookup"><span data-stu-id="3275a-151">It also has options to customize which value of the phone number to be included in the Address Book file.</span></span> <span data-ttu-id="3275a-152">通过 **"还原默认值** "选项，管理员可以将通讯簿服务设置还原为默认值。</span><span class="sxs-lookup"><span data-stu-id="3275a-152">The **Restore Defaults** option enables administrators to restore Address Book Service settings to default values.</span></span>

> [!NOTE]
> <span data-ttu-id="3275a-153">将 AD 属性重新映射到不同的 OC 字段名称仅适用于通讯簿文件下载，并且不受通讯簿 Web 查询支持。</span><span class="sxs-lookup"><span data-stu-id="3275a-153">Re-mapping of AD attributes to different OC Field Names will only work for Address Book File Download, and is not supported by Address Book Web Query.</span></span>

### <a name="output"></a><span data-ttu-id="3275a-154">输出</span><span class="sxs-lookup"><span data-stu-id="3275a-154">Output</span></span>

<span data-ttu-id="3275a-155">ABSConfig 将通讯簿服务配置存储在数据库中。</span><span class="sxs-lookup"><span data-stu-id="3275a-155">ABSConfig stores the Address Book Service configuration in the database.</span></span>

```console
Path: %ProgramFiles%\Skype for Business Server 2015\Reskit
```

### <a name="purpose"></a><span data-ttu-id="3275a-156">用途</span><span class="sxs-lookup"><span data-stu-id="3275a-156">Purpose</span></span>

<span data-ttu-id="3275a-157">ABSConfig 提供了一种快速而轻松地自定义 Skype for Business Server 2015 通讯簿服务的方法。</span><span class="sxs-lookup"><span data-stu-id="3275a-157">ABSConfig provides a quick and easy way to customize Skype for Business Server 2015 Address Book Service.</span></span>

### <a name="requirements"></a><span data-ttu-id="3275a-158">要求</span><span class="sxs-lookup"><span data-stu-id="3275a-158">Requirements</span></span>

#### <a name="computer"></a><span data-ttu-id="3275a-159">计算机</span><span class="sxs-lookup"><span data-stu-id="3275a-159">Computer</span></span>

<span data-ttu-id="3275a-160">ABSConfig 只能从安装了 Skype for Business Server 2015 的已加入域的计算机运行。</span><span class="sxs-lookup"><span data-stu-id="3275a-160">ABSConfig can be run only from a domain-joined computer that has Skype for Business Server 2015 installed.</span></span> <span data-ttu-id="3275a-161">对于 Skype for Business Server 2015 Enterprise Edition，此工具可在安装期间启用了通讯簿服务的任何前端服务器上运行。</span><span class="sxs-lookup"><span data-stu-id="3275a-161">In the case of Skype for Business Server 2015, Enterprise Edition, this tool can be run on any Front End servers that have the Address Book Service enabled during setup.</span></span>

#### <a name="network"></a><span data-ttu-id="3275a-162">Network</span><span class="sxs-lookup"><span data-stu-id="3275a-162">Network</span></span>

<span data-ttu-id="3275a-163">计算机应能够连接到前端池和后端数据库。</span><span class="sxs-lookup"><span data-stu-id="3275a-163">The computer should be able to connect to the Front End pool and back-end database.</span></span>

#### <a name="software"></a><span data-ttu-id="3275a-164">软件</span><span class="sxs-lookup"><span data-stu-id="3275a-164">Software</span></span>

<span data-ttu-id="3275a-165">在运行 ABSConfig 工具之前，必须安装以下软件组件：</span><span class="sxs-lookup"><span data-stu-id="3275a-165">The following software components must be installed before running the ABSConfig tool:</span></span>

- <span data-ttu-id="3275a-166">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="3275a-166">Skype for Business Server 2015</span></span>

#### <a name="users"></a><span data-ttu-id="3275a-167">用户</span><span class="sxs-lookup"><span data-stu-id="3275a-167">Users</span></span>

<span data-ttu-id="3275a-168">具有更新 Skype for Business Server 2015 部署所需的权限的管理员。</span><span class="sxs-lookup"><span data-stu-id="3275a-168">Administrators who have the permissions required to update the Skype for Business Server 2015 deployment.</span></span>

### <a name="examples"></a><span data-ttu-id="3275a-169">示例</span><span class="sxs-lookup"><span data-stu-id="3275a-169">Examples</span></span>

<span data-ttu-id="3275a-170">ABSConfig 可通过在命令 **提示符ABSConfig.exe** 命令提示符下键入命令命令。</span><span class="sxs-lookup"><span data-stu-id="3275a-170">ABSConfig can be started by typing **ABSConfig.exe** at a command prompt.</span></span> <span data-ttu-id="3275a-171">下面是 ABSConfig 工具用户界面。</span><span class="sxs-lookup"><span data-stu-id="3275a-171">Shown below is the ABSConfig tool user interface.</span></span>

![ABSConfig.exe工具。](../media/Reskit_2012_Tools_Documentation_ABSConfig.JPG)

### <a name="summary"></a><span data-ttu-id="3275a-173">摘要</span><span class="sxs-lookup"><span data-stu-id="3275a-173">Summary</span></span>

<span data-ttu-id="3275a-174">ABSConfig 工具为管理员提供了一个快速且易于使用的工具来自定义 Skype for Business Server 2015 通讯簿服务。</span><span class="sxs-lookup"><span data-stu-id="3275a-174">The ABSConfig tool provides administrators a quick and easy to use tool to customize Skype for Business Server 2015 Address Book Service.</span></span>

## <a name="bandwidth-policy-service-monitor"></a><span data-ttu-id="3275a-175">带宽策略服务监视器</span><span class="sxs-lookup"><span data-stu-id="3275a-175">Bandwidth Policy Service Monitor</span></span>
<span data-ttu-id="3275a-176"><a name="bpsm"> </a></span><span class="sxs-lookup"><span data-stu-id="3275a-176"><a name="bpsm"> </a></span></span>

<span data-ttu-id="3275a-177">带宽策略服务监视器工具旨在允许管理员查看以下列表：</span><span class="sxs-lookup"><span data-stu-id="3275a-177">The Bandwidth Policy Service Monitor tool is intended to allow administrators to view a list of the following:</span></span>

1. <span data-ttu-id="3275a-178">拓扑中配置的所有 Skype for Business Server 2015 带宽 (身份验证) 核心策略服务</span><span class="sxs-lookup"><span data-stu-id="3275a-178">All the configured Skype for Business Server 2015 Bandwidth Policy services (Authentication and Core) in the topology</span></span>

2. <span data-ttu-id="3275a-179">每个服务与其他带宽策略服务和边缘服务器的连接</span><span class="sxs-lookup"><span data-stu-id="3275a-179">The connections that each service makes to other Bandwidth Policy services and to the Edge servers</span></span>

3. <span data-ttu-id="3275a-180">网络配置文档中配置的所有链接以及每个带宽策略服务报告的实际带宽使用量</span><span class="sxs-lookup"><span data-stu-id="3275a-180">All the links that are configured in the Network configuration document and real-time bandwidth usage as reported by each of the Bandwidth Policy services</span></span>

### <a name="description"></a><span data-ttu-id="3275a-181">说明</span><span class="sxs-lookup"><span data-stu-id="3275a-181">Description</span></span>

<span data-ttu-id="3275a-182">带宽策略服务监视器工具作为基于 GUI 的应用程序实现。</span><span class="sxs-lookup"><span data-stu-id="3275a-182">The Bandwidth Policy Service Monitor tool is implemented as a GUI-based application.</span></span> <span data-ttu-id="3275a-183">管理员通过运行 PDPMonUI.exe 来启动PDPMonUI.exe。</span><span class="sxs-lookup"><span data-stu-id="3275a-183">Administrators start the tool by running PDPMonUI.exe.</span></span>

<span data-ttu-id="3275a-184">当该工具启动时，它会尝试发现拓扑中的带宽策略服务列表。</span><span class="sxs-lookup"><span data-stu-id="3275a-184">When the tool starts, it attempts to discover the list of Bandwidth Policy services in the topology.</span></span> <span data-ttu-id="3275a-185">初始更新完成后，窗口左侧的窗格将填充一个服务列表，这些服务按它们所属的群集进行分组。</span><span class="sxs-lookup"><span data-stu-id="3275a-185">After the initial update is done, the pane to the left of the window is populated with a list of services that are grouped by the clusters that they belong to.</span></span>

<span data-ttu-id="3275a-186">当管理员选择特定带宽策略服务时，右侧窗格将显示有关该特定服务的信息。</span><span class="sxs-lookup"><span data-stu-id="3275a-186">When administrators select a particular Bandwidth Policy Service, the pane on the right displays the information about that particular service.</span></span> <span data-ttu-id="3275a-187">该窗格还有两个显示信息的主要选项卡。</span><span class="sxs-lookup"><span data-stu-id="3275a-187">That pane also has two main tabs that display information.</span></span>

#### <a name="machine-info-tab"></a><span data-ttu-id="3275a-188">计算机信息选项卡</span><span class="sxs-lookup"><span data-stu-id="3275a-188">Machine Info Tab</span></span>

<span data-ttu-id="3275a-189">" **计算机信息** "选项卡显示所选带宽策略服务的详细信息，以及所选带宽策略服务与其他服务建立的所有连接的列表和状态。</span><span class="sxs-lookup"><span data-stu-id="3275a-189">The **Machine Info** tab shows the details of the Bandwidth Policy Service that is selected and the list and state of all the connections that are made by the selected Bandwidth Policy Service to other services.</span></span>

#### <a name="topology-info-tab"></a><span data-ttu-id="3275a-190">拓扑信息选项卡</span><span class="sxs-lookup"><span data-stu-id="3275a-190">Topology Info Tab</span></span>

<span data-ttu-id="3275a-191">" **拓扑信息** "选项卡显示了在网络配置设置中配置的所有链接的列表。</span><span class="sxs-lookup"><span data-stu-id="3275a-191">The **Topology Info** tab shows a list of all the links that are configured in the Network configuration settings.</span></span> <span data-ttu-id="3275a-192">对于每个链接，将显示音频和视频带宽容量。</span><span class="sxs-lookup"><span data-stu-id="3275a-192">For each link, the audio and video bandwidth capacity is displayed.</span></span> <span data-ttu-id="3275a-193">此外，当前利用的带宽以 Kbps 为单位和容量百分比显示。</span><span class="sxs-lookup"><span data-stu-id="3275a-193">Additionally, the currently utilized bandwidth is displayed, both in Kbps and as a percentage of the capacity.</span></span> <span data-ttu-id="3275a-194">该工具使用颜色编码突出显示利用率接近容量的链接，这允许管理员快速隔离此类链接。</span><span class="sxs-lookup"><span data-stu-id="3275a-194">The tool uses color-coding to highlight links that have utilization that is close to the capacity—this allows administrators to quickly isolate such links.</span></span>

> [!NOTE]
>  <span data-ttu-id="3275a-195">如果带宽策略服务监视器工具连接到任何配置的带宽策略服务时遇到故障，将不会填充计算机信息和拓扑 **信息** 选项卡中的信息。 </span><span class="sxs-lookup"><span data-stu-id="3275a-195">If the Bandwidth Policy Service Monitor tool experiences failure when it connects to any of the configured Bandwidth Policy services, the information in the **Machine Info** and the **Topology Info** tabs won't be populated.</span></span> <span data-ttu-id="3275a-196">但是，该工具可能最初连接，但随后会失去与服务的连接。</span><span class="sxs-lookup"><span data-stu-id="3275a-196">However, it is possible that the tool might connect initially but subsequently lose its connection to the service.</span></span> <span data-ttu-id="3275a-197">在这种情况下，管理员可能会看到过时的信息。</span><span class="sxs-lookup"><span data-stu-id="3275a-197">In such cases, administrators might see outdated information.</span></span> <span data-ttu-id="3275a-198">每个选项卡 **上都有** "上次更新时间"时间戳，管理员可以查看上次为特定带宽策略服务更新数据的时间。</span><span class="sxs-lookup"><span data-stu-id="3275a-198">There is a **Last Updated** time stamp on each of the tabs that can allow administrators to see when the data was last updated for a particular Bandwidth Policy Service.</span></span>

### <a name="output"></a><span data-ttu-id="3275a-199">输出</span><span class="sxs-lookup"><span data-stu-id="3275a-199">Output</span></span>

<span data-ttu-id="3275a-200">没有命令行输出;程序输出包含在主图形用户界面中 (GUI) 。</span><span class="sxs-lookup"><span data-stu-id="3275a-200">There is no command-line output; the program output is contained within the main graphical user interface (GUI).</span></span>

### <a name="purpose"></a><span data-ttu-id="3275a-201">用途</span><span class="sxs-lookup"><span data-stu-id="3275a-201">Purpose</span></span>

<span data-ttu-id="3275a-202">带宽策略服务监视器工具的目的是允许管理员查看拓扑中定义的每个带宽策略服务的状态。</span><span class="sxs-lookup"><span data-stu-id="3275a-202">The purpose of the Bandwidth Policy Service Monitor tool is to allow administrators visibility into the state of each of the Bandwidth Policy services that are defined in the topology.</span></span> <span data-ttu-id="3275a-203">此外，管理员可以查看网络配置文档中定义的所有链接实时带宽使用情况。</span><span class="sxs-lookup"><span data-stu-id="3275a-203">In addition, administrators can see real-time bandwidth usage for all the links that are defined in the Network configuration document.</span></span>

### <a name="requirements"></a><span data-ttu-id="3275a-204">要求</span><span class="sxs-lookup"><span data-stu-id="3275a-204">Requirements</span></span>

<span data-ttu-id="3275a-205">带宽策略服务监视器工具需要在属于 Skype for Business Server 拓扑的一部分的计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="3275a-205">The Bandwidth Policy Service Monitor tool needs to be run on a computer that is part of the Skype for Business Server topology.</span></span>

### <a name="summary"></a><span data-ttu-id="3275a-206">摘要</span><span class="sxs-lookup"><span data-stu-id="3275a-206">Summary</span></span>

<span data-ttu-id="3275a-207">带宽策略服务监视器工具对于管理员来说可能是一项有价值的资源，以便管理员可以检查拓扑中所有带宽策略服务的状态，更重要的是，他们可以获取在网络配置设置中定义的链接实时带宽利用率。</span><span class="sxs-lookup"><span data-stu-id="3275a-207">The Bandwidth Policy Service Monitor tool can be a valuable resource to administrators so they can inspect the state of all the Bandwidth Policy services in the topology—and more importantly—they can obtain real-time bandwidth utilization for the links that are defined in the Network configuration settings.</span></span>

## <a name="bandwidth-utilization-analyzer"></a><span data-ttu-id="3275a-208">带宽使用率分析器</span><span class="sxs-lookup"><span data-stu-id="3275a-208">Bandwidth Utilization Analyzer</span></span>
<span data-ttu-id="3275a-209"><a name="bua"> </a></span><span class="sxs-lookup"><span data-stu-id="3275a-209"><a name="bua"> </a></span></span>

<span data-ttu-id="3275a-210">带宽利用率分析器是一种工具，可创建有关企业网络中跨 WAN 链路的 UC 终结点的各种带宽消耗视图的报告。</span><span class="sxs-lookup"><span data-stu-id="3275a-210">Bandwidth Utilization Analyzer is a tool that creates reports about various views of bandwidth consumption by the UC endpoints across WAN links in the enterprise network.</span></span> <span data-ttu-id="3275a-211">这些报告可用于了解当前带宽消耗模式，并有助于进行带宽容量规划。</span><span class="sxs-lookup"><span data-stu-id="3275a-211">These reports can be used to understand the current bandwidth consumption pattern and to aid in bandwidth capacity planning.</span></span>

### <a name="description"></a><span data-ttu-id="3275a-212">说明</span><span class="sxs-lookup"><span data-stu-id="3275a-212">Description</span></span>

<span data-ttu-id="3275a-213">带宽利用率分析器作为基于 GUI 的应用程序实现。</span><span class="sxs-lookup"><span data-stu-id="3275a-213">Bandwidth Utilization Analyzer is implemented as a GUI-based application.</span></span> <span data-ttu-id="3275a-214">此工具专门为整个网络的音频使用率生成报告，并帮助进行容量规划。</span><span class="sxs-lookup"><span data-stu-id="3275a-214">This tool generates reports specifically for audio utilization across the network and helps with capacity planning.</span></span> <span data-ttu-id="3275a-215">它还对分配给各种链接的带宽容量进行访问。</span><span class="sxs-lookup"><span data-stu-id="3275a-215">It also iterates on the bandwidth capacity that is assigned to various links.</span></span>

### <a name="output"></a><span data-ttu-id="3275a-216">输出</span><span class="sxs-lookup"><span data-stu-id="3275a-216">Output</span></span>

<span data-ttu-id="3275a-217">带宽利用率分析器为系统中配置的所有 WAN 链路提供带宽容量和音频利用率的图形。</span><span class="sxs-lookup"><span data-stu-id="3275a-217">Bandwidth Utilization Analyzer provides graphic al plots of bandwidth capacity and utilization for audio for all the WAN links that are configured in the system.</span></span>

### <a name="purpose"></a><span data-ttu-id="3275a-218">用途</span><span class="sxs-lookup"><span data-stu-id="3275a-218">Purpose</span></span>

<span data-ttu-id="3275a-219">在任何语音和视频部署中，监视并了解企业网络中媒体流量的带宽使用率趋势至关重要。</span><span class="sxs-lookup"><span data-stu-id="3275a-219">In any voice and video deployment, it's critical to monitor and understand the trend of bandwidth utilization of media traffic across the enterprise network.</span></span> <span data-ttu-id="3275a-220">带宽利用率分析器工具使管理员可以实现此目的。</span><span class="sxs-lookup"><span data-stu-id="3275a-220">The Bandwidth Utilization Analyzer tool allows an administrator to achieve just that.</span></span> <span data-ttu-id="3275a-221">此工具执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="3275a-221">This tool does the following:</span></span>

- <span data-ttu-id="3275a-222">生成特定报告以用于整个网络的音频使用率</span><span class="sxs-lookup"><span data-stu-id="3275a-222">Generates specific reports for audio utilization across the network</span></span>

- <span data-ttu-id="3275a-223">有助于对分配给各种链路的带宽容量进行更有效的容量规划和迭代</span><span class="sxs-lookup"><span data-stu-id="3275a-223">Helps with more effective capacity planning and iteration on the bandwidth capacity that is assigned to various links</span></span>

<span data-ttu-id="3275a-224">带宽利用率分析器可以生成带宽容量和使用率报告的图形绘图;它们如下所示：</span><span class="sxs-lookup"><span data-stu-id="3275a-224">Bandwidth Utilization Analyzer can generate graphical plots of bandwidth capacity and utilization reports; they are as follows:</span></span>

- <span data-ttu-id="3275a-225">企业网络内的所有 WAN 链路</span><span class="sxs-lookup"><span data-stu-id="3275a-225">All the WAN links in the enterprise network</span></span>

- <span data-ttu-id="3275a-226">按所选的 WAN 链接进行筛选</span><span class="sxs-lookup"><span data-stu-id="3275a-226">Filtered by selected WAN links that have been chosen</span></span>

- <span data-ttu-id="3275a-227">按超过链接容量的 WAN 链接进行筛选</span><span class="sxs-lookup"><span data-stu-id="3275a-227">Filtered by WAN links that have exceeded link capacity</span></span>

- <span data-ttu-id="3275a-228">按未充分利用预配带宽的 WAN 链路进行筛选</span><span class="sxs-lookup"><span data-stu-id="3275a-228">Filtered by WAN links that have been under-utilizing the provisioned bandwidth</span></span>

- <span data-ttu-id="3275a-229">按已到达关键级别的 WAN 链路进行筛选 (带宽使用率大于 WAN 链路带宽容量的 90) </span><span class="sxs-lookup"><span data-stu-id="3275a-229">Filter by WAN links that have been reaching critical levels (a bandwidth utilization that is greater than 90% of bandwidth capacity of the WAN link)</span></span>

- <span data-ttu-id="3275a-230">按 WAN 链接类型（网络站点链接、区域间链接和站点内的链接）进行筛选</span><span class="sxs-lookup"><span data-stu-id="3275a-230">Filtered by WAN link type—network-site links, interregional links, and links within a site</span></span>

- <span data-ttu-id="3275a-231">按网络区域筛选</span><span class="sxs-lookup"><span data-stu-id="3275a-231">Filtered by network region</span></span>

#### <a name="applications"></a><span data-ttu-id="3275a-232">应用程序</span><span class="sxs-lookup"><span data-stu-id="3275a-232">Applications</span></span>

<span data-ttu-id="3275a-233">带宽使用率分析器具有以下两个应用程序 (工具) ：</span><span class="sxs-lookup"><span data-stu-id="3275a-233">Bandwidth Utilization Analyzer has the following two applications (tools):</span></span>

- <span data-ttu-id="3275a-234">**WanLinkLogCollector.exe** 利用此工具，用户可以输入所需信息。</span><span class="sxs-lookup"><span data-stu-id="3275a-234">**WanLinkLogCollector.exe** This tool enables its user to input the required information.</span></span>

- <span data-ttu-id="3275a-235">**BandwidthUtilizationAnalyzer.xlsm** Microsoft Excel 电子表格软件报告由用户自动WanLinkLogCollector.exe。</span><span class="sxs-lookup"><span data-stu-id="3275a-235">**BandwidthUtilizationAnalyzer.xlsm** A Microsoft Excel spreadsheet software report is automatically launched by WanLinkLogCollector.exe.</span></span> <span data-ttu-id="3275a-236">此应用程序允许用户将筛选器应用于报告，如本文稍后部分所示。</span><span class="sxs-lookup"><span data-stu-id="3275a-236">This application allows the user to apply filters to the report as shown later in this article.</span></span>

#### <a name="phases-of-using-bandwidth-utilization-analyzer"></a><span data-ttu-id="3275a-237">使用带宽使用率分析器阶段</span><span class="sxs-lookup"><span data-stu-id="3275a-237">Phases of Using Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="3275a-238">使用带宽使用率分析器有两个阶段：</span><span class="sxs-lookup"><span data-stu-id="3275a-238">There are two phases when using Bandwidth Utilization Analyzer:</span></span>

- <span data-ttu-id="3275a-239">收集日志，使用日志WanLinkLogCollector.exe</span><span class="sxs-lookup"><span data-stu-id="3275a-239">Collect logs, which is performed by using WanLinkLogCollector.exe</span></span>

- <span data-ttu-id="3275a-240">自定义报告，使用 BandwidthUtilizationAnalyzer.xlsm 执行</span><span class="sxs-lookup"><span data-stu-id="3275a-240">Customize reports, which is performed by using BandwidthUtilizationAnalyzer.xlsm</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="3275a-241">我们强烈建议BandwidthUtilizationAnalyzer.xls最终用户不要手动启动。</span><span class="sxs-lookup"><span data-stu-id="3275a-241">We strongly recommend that BandwidthUtilizationAnalyzer.xlsm not be manually launched by end users.</span></span>

#### <a name="starting-bandwidth-utilization-analyzer"></a><span data-ttu-id="3275a-242">启动带宽利用率分析器</span><span class="sxs-lookup"><span data-stu-id="3275a-242">Starting Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="3275a-243">在WanLinkLogCollector.exe提示符或 Windows 资源管理器启动命令。</span><span class="sxs-lookup"><span data-stu-id="3275a-243">Start WanLinkLogCollector.exe at the command prompt or by using Windows Explorer.</span></span>

 <span data-ttu-id="3275a-244">**使用WanLinkLogCollector.exe**</span><span class="sxs-lookup"><span data-stu-id="3275a-244">**Using WanLinkLogCollector.exe**</span></span>

<span data-ttu-id="3275a-245">使用应用程序有三WanLinkLogCollector.exe：</span><span class="sxs-lookup"><span data-stu-id="3275a-245">There are three steps to using WanLinkLogCollector.exe:</span></span>

1. <span data-ttu-id="3275a-246">**记录日程表** 提供需要生成报告的日程表</span><span class="sxs-lookup"><span data-stu-id="3275a-246">**Log the timeline** Provide the timeline that the report needs to be generated for</span></span>

2. <span data-ttu-id="3275a-247">**指定文件目录** 提供文件位置信息</span><span class="sxs-lookup"><span data-stu-id="3275a-247">**Specify the file directories** Provide file location information</span></span>

3. <span data-ttu-id="3275a-248">**收集日志并启动报告查看器** 执行命令以生成报告</span><span class="sxs-lookup"><span data-stu-id="3275a-248">**Collect the logs and launch the report viewer** Execute the command to generate the report</span></span>

#### <a name="step-1---log-the-timeline"></a><span data-ttu-id="3275a-249">步骤 1 - 记录日程表</span><span class="sxs-lookup"><span data-stu-id="3275a-249">Step 1 - Log the timeline</span></span>

<span data-ttu-id="3275a-250">通过记录时间线，工具用户可以指定以下内容，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="3275a-250">Logging the timeline allows the tool user to specify the following as shown in the figure below.</span></span>

1. <span data-ttu-id="3275a-251">**开始日期** 这是要生成报告的日程表的开始日期;例如，2010 年 8 月 1 日。</span><span class="sxs-lookup"><span data-stu-id="3275a-251">**Start date** This is the start date of the timeline that the report is to be generated for; for example, August 1, 2010.</span></span>

2. <span data-ttu-id="3275a-252">**结束日期** 这是要生成报告的日程表的结束日期;例如，2010 年 9 月 30 日。</span><span class="sxs-lookup"><span data-stu-id="3275a-252">**End date** This is the end date of the timeline that the report is to be generated for; for example, September 30, 2010.</span></span>

     ![带宽利用率 A 中的开始日期和结束日期](../media/Reskit_2012_Tools_Documentation_Image4.jpg)

#### <a name="step-2---specify-the-file-directories"></a><span data-ttu-id="3275a-254">步骤 2 - 指定文件目录</span><span class="sxs-lookup"><span data-stu-id="3275a-254">Step 2 - Specify the file directories</span></span>

<span data-ttu-id="3275a-255">用户可以按如下所示指定以下文件目录。</span><span class="sxs-lookup"><span data-stu-id="3275a-255">The following file directories can be specified by the user as shown.</span></span>

- <span data-ttu-id="3275a-256">**服务器日志文件位置** 存储带宽策略服务器日志的文件夹位置。</span><span class="sxs-lookup"><span data-stu-id="3275a-256">**Server log files location** The folder location where Bandwidth policy server logs are stored.</span></span> <span data-ttu-id="3275a-257">这通常位于<\<fileserver\> \\ \> FE \AppServerFiles\PDP 中。</span><span class="sxs-lookup"><span data-stu-id="3275a-257">This is typically in \<fileserver\>\\<choice of FE\>\AppServerFiles\PDP.</span></span>

- <span data-ttu-id="3275a-258">**临时文件存储位置** 生成报告时存储中间文件的临时文件位置。</span><span class="sxs-lookup"><span data-stu-id="3275a-258">**Temporary file storage location** The temporary file location where intermediate files are stored while the report is being generated.</span></span>

    ![带宽利用率 Anal 中的文件目录](../media/Reskit_2012_Tools_Documentation_Image5.jpg)

    > [!NOTE]
    > <span data-ttu-id="3275a-260">确保向工具用户提供了对服务器日志和临时文件存储文件夹的足够文件访问权限。</span><span class="sxs-lookup"><span data-stu-id="3275a-260">Ensure that sufficient file access to the server logs and the temporary file store folder is provided to the tool user.</span></span>

#### <a name="step-3---collect-the-logs-and-start-the-report-viewer"></a><span data-ttu-id="3275a-261">步骤 3 - 收集日志并启动报告查看器</span><span class="sxs-lookup"><span data-stu-id="3275a-261">Step 3 - Collect the logs and start the report viewer</span></span>

<span data-ttu-id="3275a-262">若要收集日志并启动报告查看器 **，请单击"** 执行"，如下所示。</span><span class="sxs-lookup"><span data-stu-id="3275a-262">To collect the logs and start the report viewer, click **Execute** as shown below.</span></span> <span data-ttu-id="3275a-263">此步骤将收集所需数据。</span><span class="sxs-lookup"><span data-stu-id="3275a-263">This step collects the required data.</span></span>

![在带宽利用率中定期收集数据](../media/Reskit_2012_Tools_Documentation_Image6.jpg)

<span data-ttu-id="3275a-265">输入验证成功后，将显示如下所示的消息。</span><span class="sxs-lookup"><span data-stu-id="3275a-265">When the input validation is successful, the message shown below is displayed.</span></span>

![记录带宽 Utili 中收集的通知](../media/Reskit_2012_Tools_Documentation_Image7.jpg)

<span data-ttu-id="3275a-267">单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="3275a-267">Click **OK**.</span></span> <span data-ttu-id="3275a-268">BandwidthUtilizationAnalyzer.xlsm 自动启动。</span><span class="sxs-lookup"><span data-stu-id="3275a-268">BandwidthUtilizationAnalyzer.xlsm is automatically started.</span></span> <span data-ttu-id="3275a-269">按照消息框中的说明操作。</span><span class="sxs-lookup"><span data-stu-id="3275a-269">Follow the instructions in the message box.</span></span> <span data-ttu-id="3275a-270">有关详细信息，请参阅下一 **BandwidthUtilizationAnalyzer.xls中的** "使用 m"。</span><span class="sxs-lookup"><span data-stu-id="3275a-270">For details, see **Using BandwidthUtilizationAnalyzer.xlsm** in the next section.</span></span>


### <a name="using-bandwidthutilizationanalyzerxlsm"></a><span data-ttu-id="3275a-271">使用 BandwidthUtilizationAnalyzer.xlsm</span><span class="sxs-lookup"><span data-stu-id="3275a-271">Using BandwidthUtilizationAnalyzer.xlsm</span></span>

1. <span data-ttu-id="3275a-272">当BandwidthUtilizationAnalyzer.xlsm 时，请单击 **"刷新** "，如下所示。</span><span class="sxs-lookup"><span data-stu-id="3275a-272">When BandwidthUtilizationAnalyzer.xlsm is automatically started, click **Refresh** as shown below.</span></span>

     ![BandwidthUtilizationAnalyzer.xlsm](../media/Reskit_2012_Tools_Documentation_Image8.jpg)

2. <span data-ttu-id="3275a-274">打开文件文件夹后，consolidated.csv消息框中指定的位置选择一个文件夹，如下所示。</span><span class="sxs-lookup"><span data-stu-id="3275a-274">When a file folder is opened, select consolidated.csv from the location that is specified in the message box as shown below.</span></span> <span data-ttu-id="3275a-275">它还将显示位置为 **C：\Temp。**</span><span class="sxs-lookup"><span data-stu-id="3275a-275">It also shows the location as **C:\Temp**.</span></span>

     ![在 BandwidthUtilizationAnalyzer 中打开文件夹。](../media/Reskit_2012_Tools_Documentation_Image9.jpg)

3. <span data-ttu-id="3275a-277">单击 **“导入”**。</span><span class="sxs-lookup"><span data-stu-id="3275a-277">Click **Import**.</span></span>

4. <span data-ttu-id="3275a-278">图形绘图自动生成。</span><span class="sxs-lookup"><span data-stu-id="3275a-278">The graphical plot is automatically generated.</span></span> <span data-ttu-id="3275a-279">当在后台工作的指针消失时，它可用。</span><span class="sxs-lookup"><span data-stu-id="3275a-279">It is available when the working-in-the-background pointer disappears.</span></span>

     ![在报表视图中应用筛选器。](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

#### <a name="applying-filters-to-the-report-view"></a><span data-ttu-id="3275a-281">将筛选器应用于报表视图</span><span class="sxs-lookup"><span data-stu-id="3275a-281">Applying Filters to the Report View</span></span>

<span data-ttu-id="3275a-282">可应用于筛选器的筛选器报表视图如下所示：</span><span class="sxs-lookup"><span data-stu-id="3275a-282">The filters that can be applied to the report view as shown below are described as follows:</span></span>

![在报表视图中应用筛选器。](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

1. <span data-ttu-id="3275a-284">**名称** 按 WAN 链接 (筛选器位于图形视图右侧) 。前缀表示以下链接类型;查看垂直 (蓝色) 框：</span><span class="sxs-lookup"><span data-stu-id="3275a-284">**Name** Filter by WAN links (the filter is on the right side of the graph).The prefix denotes the following link types; see the vertical (blue) box:</span></span>

   - <span data-ttu-id="3275a-285">**S 网站** 从网络站点到网络区域之间的 WAN 链路</span><span class="sxs-lookup"><span data-stu-id="3275a-285">**S Site** The WAN link from a network site to a network region</span></span>

   - <span data-ttu-id="3275a-286">**IS 站点间** 两个网络站点之间的 WAN 链路</span><span class="sxs-lookup"><span data-stu-id="3275a-286">**IS Inter-Site** The WAN link between two network sites</span></span>

   - <span data-ttu-id="3275a-287">**R 区域间** 两个网络区域之间的 WAN 链路</span><span class="sxs-lookup"><span data-stu-id="3275a-287">**R Inter-Region** The WAN link between two network region</span></span>

2. <span data-ttu-id="3275a-288">**超出限制** 按带宽利用率大于带宽容量的 WAN 链路进行筛选</span><span class="sxs-lookup"><span data-stu-id="3275a-288">**Exceeded limit** Filter by WAN links whose bandwidth utilization is more than the bandwidth capacity</span></span>

3. <span data-ttu-id="3275a-289">**关键级别** 按带宽利用率达到 90% 或大于带宽容量的 WAN 链路进行筛选</span><span class="sxs-lookup"><span data-stu-id="3275a-289">**Critical levels** Filter by WAN links whose bandwidth utilization has reached 90% or more than the bandwidth capacity</span></span>

4. <span data-ttu-id="3275a-290">**利用不足** 按带宽利用率低于带宽容量的 25% 的 WAN 链路进行筛选</span><span class="sxs-lookup"><span data-stu-id="3275a-290">**Under-utilized** Filter by WAN links whose bandwidth utilization has been less than 25% of the bandwidth capacity</span></span>

5. <span data-ttu-id="3275a-291">**链接类型** 按以下 WAN 链接类型进行筛选：</span><span class="sxs-lookup"><span data-stu-id="3275a-291">**Link type** Filter by the following WAN links types:</span></span>

   - <span data-ttu-id="3275a-292">**网络站点** 类型</span><span class="sxs-lookup"><span data-stu-id="3275a-292">**Network site** type</span></span>

   - <span data-ttu-id="3275a-293">**站点间** 类型</span><span class="sxs-lookup"><span data-stu-id="3275a-293">**Inter-site** type</span></span>

   - <span data-ttu-id="3275a-294">**区域间链接** 类型</span><span class="sxs-lookup"><span data-stu-id="3275a-294">**Inter-Region link** type</span></span>

6. <span data-ttu-id="3275a-295">**区域** 按网络区域筛选</span><span class="sxs-lookup"><span data-stu-id="3275a-295">**Region** Filter by network region</span></span>

<span data-ttu-id="3275a-296">下图显示了上述筛选器。</span><span class="sxs-lookup"><span data-stu-id="3275a-296">The following figures show the previously described filters.</span></span>

<span data-ttu-id="3275a-297">按 **名称筛选**。</span><span class="sxs-lookup"><span data-stu-id="3275a-297">Filter by **Name**.</span></span> <span data-ttu-id="3275a-298">选择需要在图形中显示的链接列表。</span><span class="sxs-lookup"><span data-stu-id="3275a-298">Select the list of links that need to be displayed in the graph.</span></span>

![在 BandwidthUtilizationAnalyzer 中按名称筛选。](../media/Reskit_2012_Tools_Documentation_Image12.jpg)

<span data-ttu-id="3275a-300">按 **超出限制筛选**。</span><span class="sxs-lookup"><span data-stu-id="3275a-300">Filter by **Exceeded limit**.</span></span> <span data-ttu-id="3275a-301">选择 **True** 以强制执行筛选器。</span><span class="sxs-lookup"><span data-stu-id="3275a-301">Select **True** to enforce the filter.</span></span>

![按超出限制进行筛选。](../media/Reskit_2012_Tools_Documentation_Image13.jpg)

<span data-ttu-id="3275a-303">按 **关键级别筛选**。</span><span class="sxs-lookup"><span data-stu-id="3275a-303">Filter by **Critical levels**.</span></span> <span data-ttu-id="3275a-304">选择 **True** 以强制执行筛选器。</span><span class="sxs-lookup"><span data-stu-id="3275a-304">Select **True** to enforce the filter.</span></span>

![按关键级别筛选。](../media/Reskit_2012_Tools_Documentation_Image14.jpg)

<span data-ttu-id="3275a-306">按 **"利用不足"进行筛选**。</span><span class="sxs-lookup"><span data-stu-id="3275a-306">Filter by **Under utilized**.</span></span> <span data-ttu-id="3275a-307">选择 **True** 以强制执行筛选器。</span><span class="sxs-lookup"><span data-stu-id="3275a-307">Select **True** to enforce the filter.</span></span>

![按"利用不足"进行筛选。](../media/Reskit_2012_Tools_Documentation_Image15.jpg)

<span data-ttu-id="3275a-309">按链接 **类型筛选**。</span><span class="sxs-lookup"><span data-stu-id="3275a-309">Filter by **Link Type**.</span></span> <span data-ttu-id="3275a-310">选择需要显示的一个或多个类型。</span><span class="sxs-lookup"><span data-stu-id="3275a-310">Select the type or types that need to be displayed.</span></span>

![按链接类型筛选。](../media/Reskit_2012_Tools_Documentation_Image16.jpg)

<span data-ttu-id="3275a-312">按区域 **筛选**。</span><span class="sxs-lookup"><span data-stu-id="3275a-312">Filter by **Region**.</span></span> <span data-ttu-id="3275a-313">选择需要显示其链接的区域列表。</span><span class="sxs-lookup"><span data-stu-id="3275a-313">Select a list of regions whose links need to be displayed.</span></span>

![按区域筛选。](../media/Reskit_2012_Tools_Documentation_Image17.jpg)

### <a name="requirements"></a><span data-ttu-id="3275a-315">要求</span><span class="sxs-lookup"><span data-stu-id="3275a-315">Requirements</span></span>

- <span data-ttu-id="3275a-316">.NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="3275a-316">The .NET Framework 3.5</span></span>

- <span data-ttu-id="3275a-317">Microsoft Excel 2010 或 Excel 2007</span><span class="sxs-lookup"><span data-stu-id="3275a-317">Microsoft Excel 2010 or Excel 2007</span></span>

### <a name="summary"></a><span data-ttu-id="3275a-318">摘要</span><span class="sxs-lookup"><span data-stu-id="3275a-318">Summary</span></span>

<span data-ttu-id="3275a-319">带宽利用率分析器用于绘制网络中 UC 流量的音频带宽利用率。</span><span class="sxs-lookup"><span data-stu-id="3275a-319">Bandwidth Utilization Analyzer is used to plot the audio bandwidth utilization for UC traffic across the network.</span></span> <span data-ttu-id="3275a-320">此工具还可用于报告网络上视频带宽的使用情况。</span><span class="sxs-lookup"><span data-stu-id="3275a-320">This tool can be used to report the utilization of video bandwidth on the network as well.</span></span>

## <a name="call-parkometer"></a><span data-ttu-id="3275a-321">呼叫 Parkometer</span><span class="sxs-lookup"><span data-stu-id="3275a-321">Call Parkometer</span></span>
<span data-ttu-id="3275a-322"><a name="callpark"> </a></span><span class="sxs-lookup"><span data-stu-id="3275a-322"><a name="callpark"> </a></span></span>

<span data-ttu-id="3275a-323">呼叫 Parkometer 是一个命令行应用程序，可轻松访问呼叫 Park 通道数据库。</span><span class="sxs-lookup"><span data-stu-id="3275a-323">Call Parkometer is a command-line application that provides easy access to the Call Park orbit database.</span></span>

### <a name="description"></a><span data-ttu-id="3275a-324">说明</span><span class="sxs-lookup"><span data-stu-id="3275a-324">Description</span></span>

<span data-ttu-id="3275a-325">呼叫 Parkometer 是跟踪当前已呼叫的一种工具。</span><span class="sxs-lookup"><span data-stu-id="3275a-325">Call Parkometer is a tool to track currently parked calls.</span></span> <span data-ttu-id="3275a-326">它还收集有关通道和呼叫 (CPS) 使用情况的统计信息。</span><span class="sxs-lookup"><span data-stu-id="3275a-326">It also collects statistics about orbits and Call Park Server (CPS) usage.</span></span> <span data-ttu-id="3275a-327">此命令行工具提供从本地或远程连接的计算机对 CPS 通道SQL Server数据库的读写访问权限。</span><span class="sxs-lookup"><span data-stu-id="3275a-327">This command-line tool provides both read and write-access to the CPS orbit SQL Server database from a local or remotely connected computer.</span></span>

<span data-ttu-id="3275a-328">所有选项都是互斥的。</span><span class="sxs-lookup"><span data-stu-id="3275a-328">All options are mutually exclusive.</span></span> <span data-ttu-id="3275a-329">命令行语法如下所示：</span><span class="sxs-lookup"><span data-stu-id="3275a-329">Command-line syntax is as follows:</span></span>

- <span data-ttu-id="3275a-330">**-o** 参数 - 列出为此池配置的所有通道范围。</span><span class="sxs-lookup"><span data-stu-id="3275a-330">**-o** parameter—lists all orbit ranges configured for this pool.</span></span>

- <span data-ttu-id="3275a-331">**-n** 参数- 列出此池中当前使用的所有通道。</span><span class="sxs-lookup"><span data-stu-id="3275a-331">**-n** parameter—lists all currently used orbits in this pool.</span></span> <span data-ttu-id="3275a-332">显示的信息如下所示：</span><span class="sxs-lookup"><span data-stu-id="3275a-332">The information displayed is as follows:</span></span>

  - <span data-ttu-id="3275a-333">SIP 统一资源 (URI) 的 URI。</span><span class="sxs-lookup"><span data-stu-id="3275a-333">SIP Uniform Resource Identifier (URI) of the parkee and parker.</span></span>

  - <span data-ttu-id="3275a-334">呼叫所位于的 CPS 的主机名。</span><span class="sxs-lookup"><span data-stu-id="3275a-334">Host name of the CPS where the call is parked.</span></span>

  - <span data-ttu-id="3275a-335">呼叫被叫到的时间戳。</span><span class="sxs-lookup"><span data-stu-id="3275a-335">Time stamp of when the call was parked.</span></span>

- <span data-ttu-id="3275a-336">**-f** 参数 - 列出池中当前可用通道的数量。</span><span class="sxs-lookup"><span data-stu-id="3275a-336">**-f** parameter—lists the number of currently free orbits in the pool.</span></span>

- <span data-ttu-id="3275a-337">**-r \<n\>** parameter - 列出 \<n\> 最后一次被叫的呼叫。</span><span class="sxs-lookup"><span data-stu-id="3275a-337">**-r \<n\>** parameter—lists the \<n\> last parked calls.</span></span> <span data-ttu-id="3275a-338">显示的信息如下所示：</span><span class="sxs-lookup"><span data-stu-id="3275a-338">The information displayed is as follows:</span></span>

  - <span data-ttu-id="3275a-339">被方 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="3275a-339">Parkee SIP URI.</span></span>

  - <span data-ttu-id="3275a-340">小马 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="3275a-340">Parker SIP URI.</span></span>

  - <span data-ttu-id="3275a-341">呼叫已托管的 CPS 的主机名。</span><span class="sxs-lookup"><span data-stu-id="3275a-341">Host name of the CPS where the call was parked.</span></span>

  - <span data-ttu-id="3275a-342">检索或删除呼叫的时间戳。</span><span class="sxs-lookup"><span data-stu-id="3275a-342">Time stamp of when the call was retrieved or dropped.</span></span>

- <span data-ttu-id="3275a-343">**-t \<n\>** 参数 - 测试在数据库中保留通道以显示分配的通道号码的随机性。</span><span class="sxs-lookup"><span data-stu-id="3275a-343">**-t\<n\>** parameter - tests reserving an orbit in the database to show the randomness of the assigned orbit numbers.</span></span>

### <a name="output"></a><span data-ttu-id="3275a-344">输出</span><span class="sxs-lookup"><span data-stu-id="3275a-344">Output</span></span>

<span data-ttu-id="3275a-345">根据在命令提示符下指定的输入参数，呼叫呼叫时间表将显示以下输出：</span><span class="sxs-lookup"><span data-stu-id="3275a-345">Depending on the input parameters that are specified at a command prompt, Call Parkometer displays the following output:</span></span>

- <span data-ttu-id="3275a-346">为此池配置的所有通道范围</span><span class="sxs-lookup"><span data-stu-id="3275a-346">All orbit ranges that are configured for this pool</span></span>

- <span data-ttu-id="3275a-347">当前已呼叫的已呼叫</span><span class="sxs-lookup"><span data-stu-id="3275a-347">Currently parked calls</span></span>

- <span data-ttu-id="3275a-348">通道中 (可用) 数量</span><span class="sxs-lookup"><span data-stu-id="3275a-348">Number of free (available) orbits</span></span>

- <span data-ttu-id="3275a-349">最近接听的呼叫</span><span class="sxs-lookup"><span data-stu-id="3275a-349">Recently parked calls</span></span>

- <span data-ttu-id="3275a-350">用于测试统一和随机通道值的保留通道</span><span class="sxs-lookup"><span data-stu-id="3275a-350">Reserved orbits for testing uniform and random orbit values</span></span>

### <a name="purpose"></a><span data-ttu-id="3275a-351">用途</span><span class="sxs-lookup"><span data-stu-id="3275a-351">Purpose</span></span>

<span data-ttu-id="3275a-352">CPS 工具的用途是提供对 CPS 数据库的命令行访问。</span><span class="sxs-lookup"><span data-stu-id="3275a-352">The purpose of the CPS tool is to provide command-line access to the CPS database.</span></span> <span data-ttu-id="3275a-353">管理员可以查看 CPS 使用情况并确定分配给池的通道数。</span><span class="sxs-lookup"><span data-stu-id="3275a-353">The administrator can view the CPS usage and determine the number of orbits assigned to a pool.</span></span>

### <a name="requirements"></a><span data-ttu-id="3275a-354">要求</span><span class="sxs-lookup"><span data-stu-id="3275a-354">Requirements</span></span>

<span data-ttu-id="3275a-355">如果在运行 CPS 的同一计算机上运行此工具，则没有任何要求。</span><span class="sxs-lookup"><span data-stu-id="3275a-355">There are no requirements if this tool is run on the same computer that is running CPS.</span></span> <span data-ttu-id="3275a-356">如果此工具在远程计算机上运行，则必须SQL Server Skype for Business Server 2015 使用的远程数据库以允许远程访问。</span><span class="sxs-lookup"><span data-stu-id="3275a-356">If this tool is run on a remote computer, the SQL Server database used by Skype for Business Server 2015 must be configured to allow remote access.</span></span> <span data-ttu-id="3275a-357">必须使用数据库连接字符串配置呼叫SQL Server以连接到池的呼叫SQL Server。</span><span class="sxs-lookup"><span data-stu-id="3275a-357">Call Parkometer must be configured with a SQL Server database connection string to connect to the pool's SQL Server.</span></span> <span data-ttu-id="3275a-358">此SQL Server数据库连接字符串在配置文件中定义 **，parkometer.exe.config。** 它必须放置在用户所在的parkometer.exe目录中。</span><span class="sxs-lookup"><span data-stu-id="3275a-358">This SQL Server database connection string is defined in the configuration file, **parkometer.exe.config**. It must be placed in the same directory where parkometer.exe is located.</span></span> <span data-ttu-id="3275a-359">以下 XML 文件是示例parkometer.exe.config。必须配置的参数包括用户名 (例如，mydomain\Administrator) 、密码 (（例如，mypassword) ）和主机名 (例如，myserver) 。</span><span class="sxs-lookup"><span data-stu-id="3275a-359">The following XML file is an example of a parkometer.exe.config. The parameters that must be configured are user name (for example, mydomain\Administrator), password (for example, mypassword), and host name (for example, myserver).</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <appSettings>
   <add key="SQL" value="server=myserver\RTC;
database=cpsdyn;
User Id=mydomain\Administrator;
Password=mypassword.;
Integrated Security=false;"/>
  </appSettings>
</configuration>
```

### <a name="examples"></a><span data-ttu-id="3275a-360">示例</span><span class="sxs-lookup"><span data-stu-id="3275a-360">Examples</span></span>

<span data-ttu-id="3275a-361">已部署的通道范围：-o 参数列出为此池配置的所有通道范围，如下所示</span><span class="sxs-lookup"><span data-stu-id="3275a-361">Deployed orbit ranges: the -o parameter lists all orbit ranges that are configured for this pool as shown</span></span>

![呼叫 Parkometer 中的通道范围。](../media/Reskit_2012_Tools_Documentation_Image18.jpg)

<span data-ttu-id="3275a-363">Currently parked calls： the -n parameter lists all currently used orbits on this pool as shown</span><span class="sxs-lookup"><span data-stu-id="3275a-363">Currently parked calls: the -n parameter lists all currently used orbits on this pool as shown</span></span>

![呼叫 Parkometer 中当前已呼叫的呼叫。](../media/Reskit_2012_Tools_Documentation_Image19.jpg)

<span data-ttu-id="3275a-365">可用通道数：-f 参数列出池中当前可用通道的数量，如下所示</span><span class="sxs-lookup"><span data-stu-id="3275a-365">Number of free orbits: the -f parameter lists the number of currently free orbits in the pool as shown</span></span>

![呼叫 Parkometer 中的免费通道。](../media/Reskit_2012_Tools_Documentation_Image20.jpg)

<span data-ttu-id="3275a-367">最近已停呼叫：-r \<n\> 参数列出最后 \<n\> 一个已停呼叫，如下所示</span><span class="sxs-lookup"><span data-stu-id="3275a-367">Recently parked calls: the -r \<n\> parameter lists the \<n\> last parked calls as shown</span></span>

![呼叫 Parkometer 中的最近呼叫。](../media/Reskit_2012_Tools_Documentation_Image21.jpg)

<span data-ttu-id="3275a-369">测试通道保留：-t 参数测试在数据库中保留通道 \<n\> ，如下所示</span><span class="sxs-lookup"><span data-stu-id="3275a-369">Test orbit reservation: the -t \<n\> parameter tests reserving an orbit in the database as shown</span></span>

![在呼叫 Parkometer 中测试通道保留。](../media/Reskit_2012_Tools_Documentation_Image22.jpg)

### <a name="summary"></a><span data-ttu-id="3275a-371">摘要</span><span class="sxs-lookup"><span data-stu-id="3275a-371">Summary</span></span>

<span data-ttu-id="3275a-372">呼叫 Parkometer 是一个命令行工具，可提供有关呼叫管理服务器的详细信息。</span><span class="sxs-lookup"><span data-stu-id="3275a-372">Call Parkometer is a command-line tool that provides detailed information about the Call Park Server.</span></span>

## <a name="dbanalyze"></a><span data-ttu-id="3275a-373">DBAnalyze</span><span class="sxs-lookup"><span data-stu-id="3275a-373">DBAnalyze</span></span>
<span data-ttu-id="3275a-374"><a name="dba"> </a></span><span class="sxs-lookup"><span data-stu-id="3275a-374"><a name="dba"> </a></span></span>

### <a name="description"></a><span data-ttu-id="3275a-375">说明</span><span class="sxs-lookup"><span data-stu-id="3275a-375">Description</span></span>

<span data-ttu-id="3275a-376">DBAnalyze 是一个命令行工具，可帮助管理员收集有关 Skype for Business Server 2015 数据库的分析报告。</span><span class="sxs-lookup"><span data-stu-id="3275a-376">DBAnalyze is a command-line tool that helps administrators to gather analysis reports about the Skype for Business Server 2015 databases.</span></span> <span data-ttu-id="3275a-377">DBAnalyze 具有以下模式：诊断、用户数据、会议、MCUs 和磁盘碎片：</span><span class="sxs-lookup"><span data-stu-id="3275a-377">DBAnalyze has the following modes: diagnostic, user data, conference, MCUs, and disk fragmentation:</span></span>

- <span data-ttu-id="3275a-378">**诊断模式** 创建一个报告，其中包含有关表 (记录数的信息， 碎片、数据大小和索引大小) 、数据和 日志文件 大小、上次备份时间、运行 Microsoft Office Communications Server 的服务器之间的联系人分布、平均权限数、联系人、容器、订阅、出版物、每个用户的终结点、任何未正确存储的用户、无法路由的用户、每个用户组织的平均会议数、计划的会议、活动会议以及数据库版本。</span><span class="sxs-lookup"><span data-stu-id="3275a-378">**Diagnostic mode** Creates a report that includes information about tables (number of records, fragmentation, data size, and index size), data and log file sizes, the last back-up time, contact distribution among servers that are running Microsoft Office Communications Server, the average number of permissions, contacts, containers, subscriptions, publications, endpoints per user, any improperly homed users, users that can't be routed, the average number of conferences organized per user, scheduled conferences, active conferences, and the database version.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3275a-379">运行诊断模式可能会影响服务器性能。</span><span class="sxs-lookup"><span data-stu-id="3275a-379">Running diagnostic mode can affect server performance.</span></span>

- <span data-ttu-id="3275a-380">**用户数据模式** 报告指定用户或联系人和权限列表中具有该用户的用户的联系人、容器、订阅、发布、权限和联系人组数据。</span><span class="sxs-lookup"><span data-stu-id="3275a-380">**User data mode** Reports contact, container, subscription, publication, permission, and contact-group data for a specified user or for users who have that user in their contact and permission lists.</span></span> <span data-ttu-id="3275a-381">此模式还会报告用户组织或受邀参加的会议的摘要数据。</span><span class="sxs-lookup"><span data-stu-id="3275a-381">This mode also reports summary data for conferences that a user organizes or is invited to.</span></span>

- <span data-ttu-id="3275a-382">**会议模式** 报告特定会议的详细数据，包括会议的所有计划时详细信息、被邀请者列表、允许参加会议的媒体类型列表、活动 MCUs (多点控制单元) 、活动参与者列表以及每个参与者的信号状态。</span><span class="sxs-lookup"><span data-stu-id="3275a-382">**Conference mode** Reports detailed data for a specific conference, including all schedule-time details for the conference, the invitee list, the list of media types allowed for the conference, active MCUs (multipoint control units), the active participant list, and each participant's signaling state.</span></span>

- <span data-ttu-id="3275a-383">**解码会议 ID** 解码公用电话交换网 (PSTN) **/pstnid** 开关指定的会议 ID，但不连接到后端获取详细信息。</span><span class="sxs-lookup"><span data-stu-id="3275a-383">**Decode Meeting ID** Decodes a public switched telephone network (PSTN) meeting ID that is specified by the **/pstnid** switch but does not connect to the back end for detailed information.</span></span>

- <span data-ttu-id="3275a-384">**解析会议** 解码 **/pstnid** 开关指定的 PSTN 会议 ID，并显示有关 ID 指示的会议的信息。</span><span class="sxs-lookup"><span data-stu-id="3275a-384">**Resolve conference** Decodes a PSTN meeting ID that is specified by the **/pstnid** switch and displays information about the conference indicated by the ID.</span></span>

- <span data-ttu-id="3275a-385">**MCUs 模式** 报告池中每个 MCU 的 ID、媒体类型、URL、检测信号状态、会议负载和参与者负载。</span><span class="sxs-lookup"><span data-stu-id="3275a-385">**MCUs mode** Reports the ID, media type, URL, heartbeat status, conference load, and participant load for each MCU in the pool.</span></span>

- <span data-ttu-id="3275a-386">**磁盘碎片模式** 显示所有磁盘的碎片状态。</span><span class="sxs-lookup"><span data-stu-id="3275a-386">**Disk fragmentation mode** Displays the fragmentation status of all disks.</span></span>

<span data-ttu-id="3275a-387">此工具可用于诊断各种问题或帮助管理员进行容量规划。</span><span class="sxs-lookup"><span data-stu-id="3275a-387">This tool can be used to diagnose various problems or to assist administrators with capacity planning.</span></span> <span data-ttu-id="3275a-388">例如，如果服务器 A 上的大多数用户选择服务器 B 上作为联系人的用户，管理员可以将服务器 A 上的用户移动到服务器 B 以减少跨服务器通信。</span><span class="sxs-lookup"><span data-stu-id="3275a-388">For example, if most of the users homed on server A choose users homed on server B as their contacts, the administrator can move the users on server A to server B to reduce cross-server traffic.</span></span>

### <a name="output"></a><span data-ttu-id="3275a-389">输出</span><span class="sxs-lookup"><span data-stu-id="3275a-389">Output</span></span>

<span data-ttu-id="3275a-390">此工具输出有关 Skype for Business Server 2015 数据库的预定义报告。</span><span class="sxs-lookup"><span data-stu-id="3275a-390">This tool outputs predefined reports about the Skype for Business Server 2015 database.</span></span> <span data-ttu-id="3275a-391">**路径**： %ProgramFiles%\Skype for Business Server 2015\Reskit</span><span class="sxs-lookup"><span data-stu-id="3275a-391">**Path**: %ProgramFiles%\Skype for Business Server 2015\Reskit</span></span>

### <a name="purpose"></a><span data-ttu-id="3275a-392">用途</span><span class="sxs-lookup"><span data-stu-id="3275a-392">Purpose</span></span>

<span data-ttu-id="3275a-393">若要安装Dbanalyze.exe，请将其复制到本地文件夹，然后运行该工具。</span><span class="sxs-lookup"><span data-stu-id="3275a-393">To install Dbanalyze.exe, copy it to a local folder and then run the tool.</span></span> <span data-ttu-id="3275a-394">若要使用该工具，请从命令行运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="3275a-394">To use the tool, run the following command from the command line.</span></span> <span data-ttu-id="3275a-395">`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]` 命令行选项的说明如下所示。</span><span class="sxs-lookup"><span data-stu-id="3275a-395">`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]` The descriptions for the command-line options are shown below.</span></span>

![用于命令的命令行Dbanalyze.exe。](../media/Reskit_2012_Tools_Documentation_Image35.JPG)

### <a name="requirements"></a><span data-ttu-id="3275a-397">要求</span><span class="sxs-lookup"><span data-stu-id="3275a-397">Requirements</span></span>

 <span data-ttu-id="3275a-398">**计算机** DBAnalyze 只能从安装了 Skype for Business Server 2015 的已加入域的计算机运行。</span><span class="sxs-lookup"><span data-stu-id="3275a-398">**Computer** DBAnalyze can be run only from a domain-joined computer that has Skype for Business Server 2015 installed.</span></span>

 <span data-ttu-id="3275a-399">**网络** 计算机应能够连接到后端数据库。</span><span class="sxs-lookup"><span data-stu-id="3275a-399">**Network** The computer should be able to connect to the back-end database.</span></span>

 <span data-ttu-id="3275a-400">**软件** 运行 DBAnalyze 之前，必须安装 Skype for Business Server 2015 软件组件。</span><span class="sxs-lookup"><span data-stu-id="3275a-400">**Software** Skype for Business Server 2015 software components must be installed before running DBAnalyze.</span></span>

 <span data-ttu-id="3275a-401">**用户** 下表显示了具有访问 Skype for Business Server 2015 数据库的必要权限的管理员。</span><span class="sxs-lookup"><span data-stu-id="3275a-401">**Users** The table below shows the administrators who have the necessary permissions to access Skype for Business Server 2015 databases.</span></span>

![权限表Dbanalyze.exe。](../media/Reskit_2012_Tools_Documentation_Image36.JPG)

> [!NOTE]
> <span data-ttu-id="3275a-403">**/report：disk** 模式需要本地管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="3275a-403">A local administrator account is required for **/report:disk** mode.</span></span>

### <a name="examples"></a><span data-ttu-id="3275a-404">示例</span><span class="sxs-lookup"><span data-stu-id="3275a-404">Examples</span></span>

<span data-ttu-id="3275a-405">下面是有效命令Dbanalyze.exe示例：</span><span class="sxs-lookup"><span data-stu-id="3275a-405">The following are examples of valid Dbanalyze.exe commands:</span></span>

```console
dbanalyze.exe /report:diag
dbanalyze.exe /report:user /user:usera@domainb.com
dbanalyze.exe /report:conf /user:bob@example.com /conf:1W9J71SKSX2X
dbanalyze.exe /report:resolve /pstnid:12345
dbanalyze.exe /report:mcus
dbanalyze.exe /report:disk
```

### <a name="summary"></a><span data-ttu-id="3275a-406">摘要</span><span class="sxs-lookup"><span data-stu-id="3275a-406">Summary</span></span>

<span data-ttu-id="3275a-407">DBAnalyzer 为管理员提供了快速而轻松地分析 Skype for Business Server 2015 数据库。</span><span class="sxs-lookup"><span data-stu-id="3275a-407">DBAnalyzer provides administrators a quick and easy to analyze Skype for Business Server 2015 databases.</span></span>

## <a name="import-storage-service-data"></a><span data-ttu-id="3275a-408">导入存储服务数据</span><span class="sxs-lookup"><span data-stu-id="3275a-408">Import Storage Service Data</span></span>
<span data-ttu-id="3275a-409"><a name="Issd"> </a></span><span class="sxs-lookup"><span data-stu-id="3275a-409"><a name="Issd"> </a></span></span>

<span data-ttu-id="3275a-410">ImportStorageServiceData 资源工具包工具允许将从存储服务 (LYSS) 刷新的队列和终结点数据重新导入存储服务。</span><span class="sxs-lookup"><span data-stu-id="3275a-410">The ImportStorageServiceData resource kit tool allows for re-importing Queue and Endpoint data that was flushed out of the Storage Service (LYSS) back into the Storage Service.</span></span>

### <a name="description"></a><span data-ttu-id="3275a-411">说明</span><span class="sxs-lookup"><span data-stu-id="3275a-411">Description</span></span>

<span data-ttu-id="3275a-412">从存储服务中刷新的数据可能是自动 (，) 队列项目状态或数据库大小进行定期刷新。</span><span class="sxs-lookup"><span data-stu-id="3275a-412">The data flushed out of the Storage Service could have been automatic (periodic) based on Queue Item status or database size.</span></span> <span data-ttu-id="3275a-413">这可能是由于手动调用池故障转移 cmdlet 或 StorageServiceFullFlush cmdlet (池故障转移 cmdlet 调用了) 。</span><span class="sxs-lookup"><span data-stu-id="3275a-413">It could have happened due to the manual invocation of the pool failover cmdlet, or the StorageServiceFullFlush cmdlet (which the pool failover cmdlet invokes).</span></span> <span data-ttu-id="3275a-414">请注意，如果前端的任何存储服务 (LYSS ) 数据库大小高于正常级别，则理想情况下不应重新导入数据，因为这样做可能会导致更多数据导出回。此外，应首先解决可能导致存储服务队列增长的错误的任何问题 (例如 Exchange 终结点错误、网络问题或其他) 。</span><span class="sxs-lookup"><span data-stu-id="3275a-414">Note that data should ideally not be re-imported if any of the Storage Service (LYSS ) database size on the front ends is above the normal level, because doing so will likely just cause more data to be exported back out. Furthermore, any problems which could have contributed to errors that caused the Storage Service Queue to grow should first be resolved (for example Exchange endpoint errors, network issues, or other problems).</span></span>

 <span data-ttu-id="3275a-415">**方案 1：** 在池故障转移期间，可能会从每个前端的存储服务中刷新文件。</span><span class="sxs-lookup"><span data-stu-id="3275a-415">**Scenario 1:** during pool failover, files may be flushed out from storage service for each front end.</span></span> <span data-ttu-id="3275a-416">故障转移完成后，应运行该工具以重新导入数据。</span><span class="sxs-lookup"><span data-stu-id="3275a-416">After failover is completed, the tool should be run to re-import the data.</span></span>

 <span data-ttu-id="3275a-417">方案 **2：** 每天自动刷新数据或响应超过特定大小阈值的存储服务数据库 (例如 60%、80%、90% ) 。</span><span class="sxs-lookup"><span data-stu-id="3275a-417">**Scenario 2:** data is being flushed automatically each day or in response to Storage Service database exceeding certain size thresholds ( for example 60%, 80%, 90% full ).</span></span> <span data-ttu-id="3275a-418">此自动刷新的数据应由管理员定期重新导入。</span><span class="sxs-lookup"><span data-stu-id="3275a-418">This automatically flushed data should be re-imported routinely by the administrator.</span></span> <span data-ttu-id="3275a-419">在以上情况下，如果未部署监控 SCOM 包，则存在与从存储服务刷新数据相关的 Skype for Business Server 存储服务事件。</span><span class="sxs-lookup"><span data-stu-id="3275a-419">In the above situation, if the monitoring SCOM pack is not deployed, there are events for Skype for Business Server Storage Service relating to data being flushed from the Storage Service.</span></span> <span data-ttu-id="3275a-420">32075 (完全刷新操作的事件 ID 已启动) ，32076 (完全刷新已完成) ，32082 (维护级别刷新开始) ，32083 (维护级别刷新完成) ，32089 (刷新由于填充数据库) 而发生。</span><span class="sxs-lookup"><span data-stu-id="3275a-420">Event IDs of 32075 (full flush operation is started), 32076 (full flush has completed), 32082 (maintenance level flush started), 32083 (maintenance level flush complete), 32089 (flush occurred due to filling up of database).</span></span> <span data-ttu-id="3275a-421">请注意，这些事件 ID 对应于 RTM 版本。</span><span class="sxs-lookup"><span data-stu-id="3275a-421">Note these event Ids correspond to the RTM release.</span></span> <span data-ttu-id="3275a-422">当管理员看到这些事件时，这意味着有一些文件已刷新。应定期使用此工具重新导入此数据，例如每周导入一次。</span><span class="sxs-lookup"><span data-stu-id="3275a-422">When an administrator sees these events, it means that there are files that have been flushed out. This data should routinely be imported back using this tool, for example once per week.</span></span>

<span data-ttu-id="3275a-423">对于联机服务版本，如果部署了 Skype for Business Server 的运行状况监控 SCOM 包，则可能会引发新的警报，要求管理员将刷新的数据重新导入到存储服务。</span><span class="sxs-lookup"><span data-stu-id="3275a-423">For the Online Service release, if health monitoring SCOM pack for Skype for Business Server is deployed, there are new alerts which may be raised which ask the administrator to re-import the flushed data back into Storage Service.</span></span> <span data-ttu-id="3275a-424">前端服务器上事件日志中将存在触发警报的相应事件。</span><span class="sxs-lookup"><span data-stu-id="3275a-424">There will be a corresponding event in the event log on the Front End server which triggered the alert.</span></span> <span data-ttu-id="3275a-425">该事件将说明刷新的数据文件所在的父路径，以及满足警报条件的文件数。</span><span class="sxs-lookup"><span data-stu-id="3275a-425">The event will give a description of the Parent path under which the flushed data files are located, as well as how many files there are which meet the alert criteria.</span></span> <span data-ttu-id="3275a-426">警报条件是，特定父路径下存在至少 ( Y 天的文件，其中 X 和 Y 在 StorageService 中预设，但可以通过更改 APPCONFIG 文件覆盖。) 下面显示了两个可触发运行状况警报的事件示例，区别在于其父路径不同。</span><span class="sxs-lookup"><span data-stu-id="3275a-426">The alert criteria is that there are X or more files under the particular parent path which are at least Y days old ( where X and Y are preset within the StorageService but can be overridden by changing the APPCONFIG file.)Two examples of events which can trigger the health alert are shown below, with the difference being their parent path.</span></span> <span data-ttu-id="3275a-427">一种可能位于 Web 服务文件共享下，另一种可能性是每个前端的本地应用程序数据目录。</span><span class="sxs-lookup"><span data-stu-id="3275a-427">One possibility is under Web service file share, while the other possibility is the local Application Data directory of each front end.</span></span> <span data-ttu-id="3275a-428"> (例如 c：\ProgramData\Microsoft\Skype for Business Server 2015\StorageService ) 。</span><span class="sxs-lookup"><span data-stu-id="3275a-428">( for example c:\ProgramData\Microsoft\Skype for Business Server 2015\StorageService ).</span></span> <span data-ttu-id="3275a-429">然后，管理员将运行此 reskit 工具。</span><span class="sxs-lookup"><span data-stu-id="3275a-429">The administrator will then run this reskit tool.</span></span>

<span data-ttu-id="3275a-430">如果运行此工具的前端不拥有数据，则此工具将增加它所运行的前端以及其他前端上的 CPU 和 IO 负载。</span><span class="sxs-lookup"><span data-stu-id="3275a-430">This tool will increase CPU and IO load on the front end it is running on, as well as other front ends, in the situation that the data is not owned by the front end that the tool is executed on.</span></span> <span data-ttu-id="3275a-431">建议在前端不负载过重的 CPU 和 IO 负载（例如高峰时段之外）时运行此工具。</span><span class="sxs-lookup"><span data-stu-id="3275a-431">We recommend runng this tool when front ends are not under heavy CPU and IO load, for example outside of peak hours.</span></span> <span data-ttu-id="3275a-432">其次，此工具可以 2 到 3 分钟导入一个数据文件。</span><span class="sxs-lookup"><span data-stu-id="3275a-432">Secondly, this tool can 2 to 3 minutes to import one data file.</span></span> <span data-ttu-id="3275a-433">在估计工具将运行的时间时，请记住这一点。</span><span class="sxs-lookup"><span data-stu-id="3275a-433">Keep this in mind when estimating how long tool will be running.</span></span> <span data-ttu-id="3275a-434">默认情况下，日志文件生成的详细内容将显示在文件存储中。</span><span class="sxs-lookup"><span data-stu-id="3275a-434">The verbose log file generated by the tool will by default appear on the File Store.</span></span> <span data-ttu-id="3275a-435">如果未报告任何错误，请将其删除，因为日志文件数十 MB 或更多。</span><span class="sxs-lookup"><span data-stu-id="3275a-435">Delete it if there are no errors reported, because the log file can be tens of MB or more.</span></span>

![示例存储服务器事件日志事件。](../media/Reskit_2012_Tools_Documentation_Image1.jpg)

### <a name="requirements"></a><span data-ttu-id="3275a-437">要求</span><span class="sxs-lookup"><span data-stu-id="3275a-437">Requirements</span></span>

<span data-ttu-id="3275a-438">安装 Skype for Business Server 2015 资源工具包工具。</span><span class="sxs-lookup"><span data-stu-id="3275a-438">Install the Skype for Business Server 2015 Resource Kit tools.</span></span> <span data-ttu-id="3275a-439">该工具在安装了 Skype for Business Server 和 Skype for Business Server 命令行管理程序的已加入域的计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="3275a-439">The tool runs on domain-joined machines where Skype for Business Server and Skype for Business Server Management Shell are installed.</span></span> <span data-ttu-id="3275a-440">该工具使用命令行管理程序中的 cmdlet 标识池中的所有前端服务器。</span><span class="sxs-lookup"><span data-stu-id="3275a-440">The tool uses a cmdlet from the management shell to identify all the Front End servers in the pool.</span></span> <span data-ttu-id="3275a-441">其次，必须从池中安装了 **RtcLocal** 数据库的计算机执行该工具。</span><span class="sxs-lookup"><span data-stu-id="3275a-441">Secondly, the tool must be executed from a machine in the pool which has the **RtcLocal** database installed.</span></span> <span data-ttu-id="3275a-442">该工具使用该数据库检索池的 WEBSERVICE 文件共享的位置。</span><span class="sxs-lookup"><span data-stu-id="3275a-442">This database is used by the tool to retrieve the location of the WEBSERVICE file share for the pool.</span></span> <span data-ttu-id="3275a-443">此外，在使用该工具之前，每台前端服务器必须先在每个前端服务器上以及从其中执行该工具的计算机上使用 **Enable-PSRemoting** 启用 Windows PowerShell 远程处理。</span><span class="sxs-lookup"><span data-stu-id="3275a-443">Additionally, before using the tool, each Front End server must first enable Windows PowerShell Remoting using **Enable-PSRemoting** on each Front End server, as well as the machine that the tool is executed from.</span></span> <span data-ttu-id="3275a-444">否则，此工具Windows PowerShell远程命令将失败。</span><span class="sxs-lookup"><span data-stu-id="3275a-444">Otherwise, remote Windows PowerShell commands from this tool will fail.</span></span> <span data-ttu-id="3275a-445">Windows PowerShell后，可以在池中的所有前端服务器上关闭远程。</span><span class="sxs-lookup"><span data-stu-id="3275a-445">Windows PowerShell Remoting can be turned off on all Front End servers in the pool after it is finished.</span></span> <span data-ttu-id="3275a-446">最后，调用该工具的帐户或凭据必须具有对正在执行此工具的池的 webservice 文件共享的读/写权限。</span><span class="sxs-lookup"><span data-stu-id="3275a-446">Finally, the account or credential invoking the tool must have read/write permission to the webservice file share for the pool they are executing this tool on.</span></span> <span data-ttu-id="3275a-447">否则，该工具将失败，出现 IO 权限错误。</span><span class="sxs-lookup"><span data-stu-id="3275a-447">Otherwise the tool will fail with IO Permission errors.</span></span>

> [!NOTE]
> <span data-ttu-id="3275a-448">在Windows Server 2012，Windows PowerShell默认启用远程，但在 Windows Server 2008 操作系统上不启用远程。</span><span class="sxs-lookup"><span data-stu-id="3275a-448">On Windows Server 2012, Windows PowerShell Remoting is enabled by default, but not on the Windows Server 2008 operating system.</span></span>

### <a name="examples"></a><span data-ttu-id="3275a-449">示例</span><span class="sxs-lookup"><span data-stu-id="3275a-449">Examples</span></span>

```console
>  C:\StorageService>ImportStorageServiceData.exe
Description:
This tool will re-import Storage Service (LYSS) flushed queue data back in.  For a pool: you are required to run this tool on a machine inside the pool which has the Lync Server Management Shell installed.  Additionally, all front end machines need to have Windows Powershell Remoting enabled before executing this tool by executing Enable-PSRemoting.  Also, please ensure that all Storage Service instance DB Size are at the 'Normal' level (verify this by viewing Eventlog events). Otherwise re-importing may cause data to be flushed out again if any Storage Service instance DB size level goes above 'Normal'.
Usage: Default behavior is to Import data from web service file share as well as any files on all Front End machines in pool.
Additional Options:
-Verbose                    : Turn verbose output on.

-StorageServiceHostName     : Host Name of Storage Service WCF endpoint.  ( Default=localhost netnamedpipe binding. )

-FileSharePath              : Import only all data from just under the UNC path specified.

ActivityID: cc3b62ff-bb66-4e61-a6e2-96cb3626315c. <-- Use this to correlate with StorageService trace logs if troubleshooting.
Type Server name (TCP binding) or press <enter> for localhost (NamePipe binding):
Using NetNamedPipeBinding...
OnTopologyChanged Event received
Web Service File Share: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService

Front Ends:
server.vdomain.com
server2.vdomain.com
server1.vdomain.com
server3.vdomain.com
Looking under directory: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService for exported data.
# Files found: 8
Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
0120910\SERVER.vdomain.com\944f5724c65c5f93900dc1c8c898b102__0.xml
Items deserialized: 20

All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER.vdomain.com\944f5724c65c5f93900dc1c8c898b102__0.xml

All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER.vdomain.com\944f5724c65c5f93900dc1c8c898b102__0.xml

Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER.vdomain.com\944f5724c65c5f93900dc1c8c898b102__0.xml: succeeded: 20, failed: 0

Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\17d5435ae40259f7bbdf1866776386e4__0.xml
Items deserialized: 20

[cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server1.vdomain.com, queueItems=20

All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\17d5435ae40259f7bbdf1866776386e4__0.xml

All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\17d5435ae40259f7bbdf1866776386e4__0.xml

Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
SERVER1.vdomain.com\17d5435ae40259f7bbdf1866776386e4__0.xml: succeeded: 20, failed: 0

Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\904f6c9b8ac951ae8b3c86684d3832e4__0.xml

Items deserialized: 20
[cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server1.vdomain.com, queueItems=20

All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\904f6c9b8ac951ae8b3c86684d
3832e4__0.xml

All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\904f6c9b8ac951ae8b3c
86684d3832e4__0.xml

Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
SERVER1.vdomain.com\904f6c9b8ac951ae8b3c86684d3832e4__0.xml: succeeded: 20, failed: 0

Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
0120910\SERVER2.vdomain.com\69844a271e6c5633a1f2b46a42287dd6__0.xml

Items deserialized: 20

[cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server2.vdom
ain.com, queueItems=20

All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
\co1-WebServices-1\StorageService\DataExport\20120910\SERVER2.vdomain.com\69844a271e6c5633a1f2b46a42
287dd6__0.xml

All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER2.vdomain.com\69844a271e6c5633a1f2
b46a42287dd6__0.xml

Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
SERVER2.vdomain.com\69844a271e6c5633a1f2b46a42287dd6__0.xml: succeeded: 20, failed: 0

Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
0120910\SERVER3.vdomain.com\3313935458e35b9b9759e08a15d251e6__0.xml

Items deserialized: 20

[cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server3.vdom
ain.com, queueItems=1

All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\3313935458e35b9b9759e08a15
d251e6__0.xml

All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\3313935458e35b9b9759
e08a15d251e6__0.xml

Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
SERVER3.vdomain.com\3313935458e35b9b9759e08a15d251e6__0.xml: succeeded: 20, failed: 0

Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
0120910\SERVER3.vdomain.com\4501e04eae4856059346949ff817c220__0.xml
Items deserialized: 20
[cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server3.vdom
ain.com, queueItems=1
All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\4501e04eae4856059346949ff8
17c220__0.xml
All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\4501e04eae4856059346
949ff817c220__0.xml

Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
SERVER3.vdomain.com\4501e04eae4856059346949ff817c220__0.xml: succeeded: 20, failed: 0
Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
0120910\SERVER3.vdomain.com\5ad77443ad955a22a876749be66d5317__0.xml

Items deserialized: 20
[cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server3.vdom
ain.com, queueItems=20
All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\5ad77443ad955a22a876749be6
6d5317__0.xml
All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\5ad77443ad955a22a876
749be66d5317__0.xml
Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
SERVER3.vdomain.com\5ad77443ad955a22a876749be66d5317__0.xml: succeeded: 20, failed: 0
Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
0120910\SERVER3.vdomain.com\a11e27ae439a582288d4657eda86b565__0.xml
Items deserialized: 20
[cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server3.vdom
ain.com, queueItems=20
All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\a11e27ae439a582288d4657eda
86b565__0.xml
All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\a11e27ae439a582288d4
657eda86b565__0.xml
Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
SERVER3.vdomain.com\a11e27ae439a582288d4657eda86b565__0.xml: succeeded: 20, failed: 0
All files have been imported into Storage Service for path: \\dc.vdomain.com\OcsFileStore\co1-WebSer
vices-1\StorageService
Importing files for: server.vdomain.com
No files founds.
Importing files for: server2.vdomain.com
No files founds.
Importing files for: server1.vdomain.com
No files founds.
Importing files for: server3.vdomain.com
No files founds.
Writing log: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\ImportStorageServiceData
Log20120910_1609SS
Tool has finished execution.
>  C:\StorageService>
```

## <a name="lcssync"></a><span data-ttu-id="3275a-450">LCSSync</span><span class="sxs-lookup"><span data-stu-id="3275a-450">LCSSync</span></span>
<span data-ttu-id="3275a-451"><a name="LCSSync"> </a></span><span class="sxs-lookup"><span data-stu-id="3275a-451"><a name="LCSSync"> </a></span></span>

<span data-ttu-id="3275a-452">LCSSync 工具有助于在多林环境中部署 Skype for Business Server 2015 通信软件。</span><span class="sxs-lookup"><span data-stu-id="3275a-452">The LCSSync tool helps to deploy Skype for Business Server 2015 communications software in a multi-forest environment.</span></span> <span data-ttu-id="3275a-453">此工具用于将不同用户林中的用户和组作为 Active Directory 域服务联系人对象同步到安装了 Skype for Business Server 2015 的中央林。</span><span class="sxs-lookup"><span data-stu-id="3275a-453">This tool is used to synchronize users and groups from different user forests as an Active Directory Domain Services contact object to a central forest where Skype for Business Server 2015 is installed.</span></span>

### <a name="description"></a><span data-ttu-id="3275a-454">说明</span><span class="sxs-lookup"><span data-stu-id="3275a-454">Description</span></span>

 <span data-ttu-id="3275a-455">LCSSync 使用中央林中同步的 Active Directory 域服务联系对象为用户启用 Skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="3275a-455">LCSSync uses the synchronized Active Directory Domain Services contact objects in the central forest to enable users for Skype for Business Server.</span></span> <span data-ttu-id="3275a-456">若要提供单一登录，主用户帐户必须映射到 Skype for Business Server 2015 中央林中的 Active Directory 域服务联系人对象。</span><span class="sxs-lookup"><span data-stu-id="3275a-456">To provide single sign-in, the primary user account must be mapped to the Active Directory Domain Services contact object in the central forest for Skype for Business Server 2015.</span></span> <span data-ttu-id="3275a-457">此工具可帮助执行该映射。</span><span class="sxs-lookup"><span data-stu-id="3275a-457">This tool helps perform that mapping.</span></span> <span data-ttu-id="3275a-458">此工具提供在 Microsoft Identity Integration Server 中创建管理代理的模板。</span><span class="sxs-lookup"><span data-stu-id="3275a-458">This tool provides templates for creating Management Agents in the Microsoft Identity Integration Server.</span></span>

### <a name="summary"></a><span data-ttu-id="3275a-459">摘要</span><span class="sxs-lookup"><span data-stu-id="3275a-459">Summary</span></span>

<span data-ttu-id="3275a-460">LCSSync 工具有助于在多林环境中部署 Skype for Business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="3275a-460">The LCSSync tool helps to deploy Skype for Business Server 2015 in a multi-forest environment.</span></span>

## <a name="lookup-user-console"></a><span data-ttu-id="3275a-461">查找用户控制台</span><span class="sxs-lookup"><span data-stu-id="3275a-461">Lookup User Console</span></span>
<span data-ttu-id="3275a-462"><a name="LUC"> </a></span><span class="sxs-lookup"><span data-stu-id="3275a-462"><a name="LUC"> </a></span></span>

<span data-ttu-id="3275a-463">LookupUserConsole 工具显示有关特定用户的内部 Skype for Business Server 路由信息。</span><span class="sxs-lookup"><span data-stu-id="3275a-463">The LookupUserConsole tool displays internal Skype for Business Server routing information about specific users.</span></span> <span data-ttu-id="3275a-464">此信息对于 Microsoft 支持人员诊断部署和路由问题可能很有用。</span><span class="sxs-lookup"><span data-stu-id="3275a-464">This information may be useful to Microsoft support personal in diagnosing deployment and routing problems.</span></span>

### <a name="description"></a><span data-ttu-id="3275a-465">说明</span><span class="sxs-lookup"><span data-stu-id="3275a-465">Description</span></span>

 <span data-ttu-id="3275a-466">执行LookupUserConsole.exe将打开接受 SIP 地址的命令提示符，并尝试显示与 SIP 地址相关的内部 Skype for Business Server 路由信息。</span><span class="sxs-lookup"><span data-stu-id="3275a-466">Executing LookupUserConsole.exe will open a command prompt that accepts SIP addresses and attempts to display internal Skype for Business Server routing information relating them.</span></span> <span data-ttu-id="3275a-467">键入 **exit** 以退出 LookupUserConsole 工具。</span><span class="sxs-lookup"><span data-stu-id="3275a-467">Type **exit** to quit the LookupUserConsole tool.</span></span>

### <a name="requirements"></a><span data-ttu-id="3275a-468">要求</span><span class="sxs-lookup"><span data-stu-id="3275a-468">Requirements</span></span>

<span data-ttu-id="3275a-469">安装 Skype for Business Server 2015 资源工具包。</span><span class="sxs-lookup"><span data-stu-id="3275a-469">Install the Skype for Business Server 2015 Resource Kit.</span></span> <span data-ttu-id="3275a-470">该工具在安装了 Skype for Business Server 的已加入域的计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="3275a-470">The tool runs on domain-joined machines where Skype for Business Server is installed.</span></span>

### <a name="examples"></a><span data-ttu-id="3275a-471">示例</span><span class="sxs-lookup"><span data-stu-id="3275a-471">Examples</span></span>

<span data-ttu-id="3275a-472">C：\Program Files\Skype for Business Server 2015\ResKit \>LookupUserConsole.exe</span><span class="sxs-lookup"><span data-stu-id="3275a-472">C:\Program Files\Skype for Business Server 2015\ResKit\>LookupUserConsole.exe</span></span>

```console
> sip:john.doe@vdomain.com

  Execution time (ms):                            171.094
  Exeuction result:                               Success
  SIP URI:                                        sip:john.doe@vdomain.com
  User info:
    SID:                                          S-1-5-21-2831376166-29632525...    Display name:                                     John Doe
    Grouping ID:                                  00000000-0000-0000-0000-...
    Line URI:                                     <null>
    Policy assignment:                            TenantId={00000000--0000-000....
    SIP enabled:                                  True
    UC enabled:                                   False
    Tenant ID:                                    00000000-0000-0000-0000-...  Cluster info:
    Active cluster:                               pool0.vdomain.com
    Backup registrar cluster:                     <null>
    Deployment location:                          <null>
    Home Front-End FQDN:                          SERVER.vdomain.com
    Primary Registrar cluster:                    pool0.vdomain.com
    Remote Director external SIP FQDN:            <null>
    Remote Director internal SIP FQDN:            <null>
    Remote Director Web FQDN:                     <null>
    Routing group ID:                             4501e04e-ae48-5605-9346...
    Service tag ID:                               1266953005
    User Front-End resolved:                      True
    User in local forest:                         True
    User in remote forest:                        False
    User in split domain:                         False
    User-Services cluster:                        pool0.vdomain.com

> sip:nouser@vdomain.com

  Execution time (ms):                            948.7574
  Exeuction result:                               UserDoesNotExist

> exit
```

## <a name="msturnping"></a><span data-ttu-id="3275a-473">MsTurnPing</span><span class="sxs-lookup"><span data-stu-id="3275a-473">MsTurnPing</span></span>
<span data-ttu-id="3275a-474"><a name="MsTurnPing"> </a></span><span class="sxs-lookup"><span data-stu-id="3275a-474"><a name="MsTurnPing"> </a></span></span>

<span data-ttu-id="3275a-475">MSTurnPing 工具允许 Skype for Business Server 2015 通信软件的管理员检查运行音频/视频边缘和音频/视频身份验证服务的服务器以及拓扑中运行带宽策略服务的服务器的状态。</span><span class="sxs-lookup"><span data-stu-id="3275a-475">The MSTurnPing tool allows an administrator of Skype for Business Server 2015 communications software to check the status of the servers running the Audio/Video Edge and Audio/Video Authentication services as well as the servers that are running Bandwidth Policy Services in the topology.</span></span>

### <a name="description"></a><span data-ttu-id="3275a-476">说明</span><span class="sxs-lookup"><span data-stu-id="3275a-476">Description</span></span>

<span data-ttu-id="3275a-477">MSTurnPing 工具允许 Skype for Business Server 2015 通信软件的管理员检查运行音频/视频边缘和音频/视频身份验证服务的服务器以及拓扑中运行带宽策略服务的服务器的状态。</span><span class="sxs-lookup"><span data-stu-id="3275a-477">The MSTurnPing tool allows an administrator of Skype for Business Server 2015 communications software to check the status of the servers running the Audio/Video Edge and Audio/Video Authentication services as well as the servers that are running Bandwidth Policy Services in the topology.</span></span>

<span data-ttu-id="3275a-478">该工具允许管理员执行以下测试：</span><span class="sxs-lookup"><span data-stu-id="3275a-478">The tool allows the administrator to perform the following tests:</span></span>

1. <span data-ttu-id="3275a-479">A/V 边缘服务器测试：该工具通过执行以下操作对拓扑中所有 A/V 边缘服务器执行测试：</span><span class="sxs-lookup"><span data-stu-id="3275a-479">A/V Edge Server test: The tool performs tests against all A/V Edge Servers in the topology by doing the following:</span></span>

   - <span data-ttu-id="3275a-480">验证 Skype for Business Server 音频/视频身份验证服务是否已启动，并可以发出正确的凭据。</span><span class="sxs-lookup"><span data-stu-id="3275a-480">Verifying that the Skype for Business Server Audio/Video Authentication service is started and can issue proper credentials.</span></span>

   - <span data-ttu-id="3275a-481">验证 Skype for Business Server 音频/视频边缘服务是否已启动，并可以成功分配外部边缘上的资源。</span><span class="sxs-lookup"><span data-stu-id="3275a-481">Verifying that the Skype for Business Server Audio/Video Edge service is started and can allocate the resources on the external edge successfully.</span></span>

2. <span data-ttu-id="3275a-482">带宽策略服务测试：该工具通过执行以下操作，对在拓扑中运行带宽策略服务的所有服务器执行测试：</span><span class="sxs-lookup"><span data-stu-id="3275a-482">Bandwidth Policy Service test: The tool performs tests against all the servers that are running the Bandwidth Policy Services in the topology by doing the following:</span></span>

   - <span data-ttu-id="3275a-483">验证 Skype for Business Server 带宽策略服务 (身份验证) 并可以发出正确的凭据。</span><span class="sxs-lookup"><span data-stu-id="3275a-483">Verifying that the Skype for Business Server Bandwidth Policy Service (Authentication) is started and can issue proper credentials.</span></span>

   - <span data-ttu-id="3275a-484">验证 Skype for Business Server 带宽策略服务 (核心) 并可以成功执行带宽检查。</span><span class="sxs-lookup"><span data-stu-id="3275a-484">Verifying that the Skype for Business Server Bandwidth Policy Service (Core) is started and can perform the bandwidth check successfully.</span></span>

<span data-ttu-id="3275a-485">必须从属于拓扑并安装了本地存储的计算机运行此工具。</span><span class="sxs-lookup"><span data-stu-id="3275a-485">This tool must be run from a computer that is part of the topology and has the local store installed.</span></span>

### <a name="output"></a><span data-ttu-id="3275a-486">输出</span><span class="sxs-lookup"><span data-stu-id="3275a-486">Output</span></span>

<span data-ttu-id="3275a-487">该工具输出每个操作的结果。</span><span class="sxs-lookup"><span data-stu-id="3275a-487">The tool outputs the results of each of the operations.</span></span>

- <span data-ttu-id="3275a-488">如果 **执行了 AudioVideoEdgeServer** 测试，该工具的输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="3275a-488">If the **AudioVideoEdgeServer** test is performed, the tool outputs are the following:</span></span>

  - <span data-ttu-id="3275a-489">在拓扑中提供 Skype for Business Server 2015 音频/视频身份验证服务的计算机的测试结果</span><span class="sxs-lookup"><span data-stu-id="3275a-489">The test results of the computers that provide the Skype for Business Server 2015 Audio/Video Authentication service in the topology</span></span>

  - <span data-ttu-id="3275a-490">在拓扑中提供 Skype for Business Server 2015 音频/视频边缘服务的计算机的测试结果</span><span class="sxs-lookup"><span data-stu-id="3275a-490">The test results of the computers that provide the Skype for Business Server 2015 Audio/Video Edge service in the topology</span></span>

- <span data-ttu-id="3275a-491">如果 **执行 BandwidthPolicyServer** 测试，则该工具输出如下：</span><span class="sxs-lookup"><span data-stu-id="3275a-491">If the **BandwidthPolicyServer** test is performed, the tool outputs are the following:</span></span>

  - <span data-ttu-id="3275a-492">在拓扑中提供 Skype for Business Server 2015 带宽策略服务 (身份验证) 测试结果</span><span class="sxs-lookup"><span data-stu-id="3275a-492">The test results of the computers that provide the Skype for Business Server 2015 Bandwidth Policy Service (Authentication) in the topology</span></span>

  - <span data-ttu-id="3275a-493">在拓扑中提供 Skype for Business Server 2015 带宽策略服务 (核心) 测试结果</span><span class="sxs-lookup"><span data-stu-id="3275a-493">The test results of the computers that provide the Skype for Business Server 2015 Bandwidth Policy Service (Core) in the topology</span></span>

### <a name="requirements"></a><span data-ttu-id="3275a-494">要求</span><span class="sxs-lookup"><span data-stu-id="3275a-494">Requirements</span></span>

- <span data-ttu-id="3275a-495">必须从拓扑中具有本地存储的计算机运行此工具。</span><span class="sxs-lookup"><span data-stu-id="3275a-495">This tool must be run from a computer that is in the topology and that has the local store.</span></span>

- <span data-ttu-id="3275a-496">该工具必须以有权访问本地存储的管理员角色运行。</span><span class="sxs-lookup"><span data-stu-id="3275a-496">The tool must be run as an administrator who has access to the local store.</span></span>

### <a name="examples"></a><span data-ttu-id="3275a-497">示例</span><span class="sxs-lookup"><span data-stu-id="3275a-497">Examples</span></span>

<span data-ttu-id="3275a-498">下面是工具输入的示例。</span><span class="sxs-lookup"><span data-stu-id="3275a-498">The following is an example of the tool input.</span></span>

```console
MsTurnPing -ServerRole AudioVideoEdgeServer

MsTurnPing -ServerRole BandwidthPolicyServer
```

### <a name="summary"></a><span data-ttu-id="3275a-499">摘要</span><span class="sxs-lookup"><span data-stu-id="3275a-499">Summary</span></span>

<span data-ttu-id="3275a-500">对于要检查运行音频/视频和带宽策略服务的服务器状态的 Skype for Business Server 2015 管理员来说，此工具可能是一项有价值的资源。</span><span class="sxs-lookup"><span data-stu-id="3275a-500">This tool can be a valuable resource to Skype for Business Server 2015 administrators who want to check the status of the servers that are running audio/video and bandwidth policy services.</span></span>

## <a name="network-configuration-viewer"></a><span data-ttu-id="3275a-501">网络配置查看器</span><span class="sxs-lookup"><span data-stu-id="3275a-501">Network Configuration Viewer</span></span>
<span data-ttu-id="3275a-502"><a name="NCV"> </a></span><span class="sxs-lookup"><span data-stu-id="3275a-502"><a name="NCV"> </a></span></span>

<span data-ttu-id="3275a-503">Skype for Business Server 2015 通信软件管理员可以使用网络配置查看器查看企业的呼叫允许控制 (CAC) 网络拓扑，该拓扑已预配为允许实时通信会话，例如基于指定带宽容量的语音或视频呼叫。</span><span class="sxs-lookup"><span data-stu-id="3275a-503">Network Configuration Viewer can be used by Skype for Business Server 2015 communications software administrators to view call admission control (CAC) network topology for an enterprise that is provisioned to allow real-time communication sessions, such as voice or video calls based on specified bandwidth capacity.</span></span> <span data-ttu-id="3275a-504">Skype for Business Server 2015 管理员定义 CAC 策略，这些策略由随 Skype for Business Server 2015 一起安装的带宽策略服务强制执行。</span><span class="sxs-lookup"><span data-stu-id="3275a-504">Skype for Business Server 2015 administrators define CAC policies, which are enforced by the Bandwidth Policy services that are installed with Skype for Business Server 2015.</span></span>

### <a name="description"></a><span data-ttu-id="3275a-505">说明</span><span class="sxs-lookup"><span data-stu-id="3275a-505">Description</span></span>

<span data-ttu-id="3275a-506">网络配置查看器 (NetworkConfigurationViewer.exe) 允许管理员执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="3275a-506">Network Configuration Viewer (NetworkConfigurationViewer.exe) allows administrators to perform the following tasks:</span></span>

- <span data-ttu-id="3275a-507">以图形格式从 Skype for Business Server 2015 部署加载和查看 CAC 网络拓扑。</span><span class="sxs-lookup"><span data-stu-id="3275a-507">Load and view CAC network topology from a Skype for Business Server 2015 deployment in a graphical format.</span></span>

- <span data-ttu-id="3275a-508">以图形格式从带宽策略服务器服务器日志文件和查看 CAC 网络拓扑。</span><span class="sxs-lookup"><span data-stu-id="3275a-508">Load and view CAC network topology from a Bandwidth Policy Server log file in a graphical format.</span></span>

- <span data-ttu-id="3275a-509">以 XML 格式在磁盘上保存和存储 CAC 网络拓扑。</span><span class="sxs-lookup"><span data-stu-id="3275a-509">Save and store CAC network topology in an XML format on the disk.</span></span>

- <span data-ttu-id="3275a-510">以 JPG 或 BMP 格式保存和存储 CAC 网络拓扑图。</span><span class="sxs-lookup"><span data-stu-id="3275a-510">Save and store CAC network topology diagram in JPG or BMP format.</span></span>

- <span data-ttu-id="3275a-511">查看 CAC 网络拓扑配置数据。</span><span class="sxs-lookup"><span data-stu-id="3275a-511">View CAC network topology configuration data.</span></span>

- <span data-ttu-id="3275a-512">以树视图样式查看 CAC 网络拓扑。</span><span class="sxs-lookup"><span data-stu-id="3275a-512">View CAC network topology in a tree-view style.</span></span>

- <span data-ttu-id="3275a-513">定义 CAC 网络拓扑链接的自定义连接器 (例如，站点到区域、区域到区域以及站点到站点链接) 。</span><span class="sxs-lookup"><span data-stu-id="3275a-513">Define custom connectors for CAC network topology links (for example, site-to-region, region-to-region, and site-to-site links).</span></span>

- <span data-ttu-id="3275a-514">查看 CAC 网络拓扑站点信息、区域信息以及已预配的带宽策略和网络链接。</span><span class="sxs-lookup"><span data-stu-id="3275a-514">View CAC network topology site information, region Information, and provisioned bandwidth policies and network links.</span></span>

### <a name="purpose"></a><span data-ttu-id="3275a-515">用途</span><span class="sxs-lookup"><span data-stu-id="3275a-515">Purpose</span></span>

<span data-ttu-id="3275a-516">在图形界面中查看企业 CAC 网络拓扑链接。</span><span class="sxs-lookup"><span data-stu-id="3275a-516">View enterprise CAC network topology links in a graphical interface.</span></span>

### <a name="examples"></a><span data-ttu-id="3275a-517">示例</span><span class="sxs-lookup"><span data-stu-id="3275a-517">Examples</span></span>

 <span data-ttu-id="3275a-518">以图形格式从 **Skype for Business Server 2015** 部署加载和查看 CAC 网络拓扑：Skype for Business Server 2015 管理员可以使用"下载网络配置"选项在任何 Skype for Business Server  2015 计算机上加载和查看 CAC 网络拓扑配置，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="3275a-518">**Load and view CAC network topology from a Skype for Business Server 2015 deployment in a graphical format**: Skype for Business Server 2015 administrators can load and view CAC network topology configuration on any Skype for Business Server 2015 computer by using the **Download Network Configuration** option as shown in the figure below.</span></span> <span data-ttu-id="3275a-519">在未连接到 Skype for Business Server 2015 配置存储的计算机上部署该工具时，将无法下载或查看此类配置。</span><span class="sxs-lookup"><span data-stu-id="3275a-519">The tool will fail to download or view such a configuration when deployed on a computer that does not have connectivity to the Skype for Business Server 2015 configuration store.</span></span>

![下载网络配置。](../media/Reskit_2012_Tools_Documentation_Image23.jpg)

 <span data-ttu-id="3275a-521">**以图形格式从带宽策略服务器日志文件和查看 CAC 网络拓扑：** Skype for Business Server 2015 带宽策略服务器将 CAC 网络拓扑保存为 Skype for Business Server 2015 文件共享位置下的日志记录机制的一部分。</span><span class="sxs-lookup"><span data-stu-id="3275a-521">**Load and View CAC network topology from a Bandwidth Policy server log file in a graphical format:** Skype for Business Server 2015 Bandwidth Policy servers save the CAC network topology as a part of the logging mechanism under the Skype for Business Server 2015 file share location.</span></span> <span data-ttu-id="3275a-522">Skype for Business Server 2015 管理员可以使用"开放网络配置"选项以图形格式查看此类文件，如下所示。</span><span class="sxs-lookup"><span data-stu-id="3275a-522">Skype for Business Server 2015 administrators can view such a file in a graphical format by using the **Open Network Configuration** option as shown below.</span></span>

![打开带宽策略服务器日志文件。](../media/Reskit_2012_Tools_Documentation_Image24.jpg)

<span data-ttu-id="3275a-524">以 XML 格式在磁盘上保存和存储 CAC 网络拓扑：Skype for Business Server 2015 管理员可以使用"保存网络配置副本"选项以 XML 格式保存 CAC 网络拓扑配置文件，如下所示。</span><span class="sxs-lookup"><span data-stu-id="3275a-524">Save and store CAC network topology in an XML format on the disk: Skype for Business Server 2015 administrators can save the CAC network topology configuration file in an XML format by using the **Save a copy of Network Configuration** option as shown below.</span></span> <span data-ttu-id="3275a-525">然后，保存的配置文件可以脱机用于图形查看目的。</span><span class="sxs-lookup"><span data-stu-id="3275a-525">The saved configuration file can then be used offline for graphical viewing purposes.</span></span>

![将网络配置另存为 XML 文件。](../media/Reskit_2012_Tools_Documentation_Image25.jpg)

<span data-ttu-id="3275a-527">以 JPG 或 BMP 格式保存和存储 CAC 网络拓扑图：Skype for Business Server 2015 管理员可以使用"保存网络配置"图表作为图片选项以图形格式保存 CAC 网络拓扑配置 ( JPG 和 BMP 文件格式) ，如下所示。</span><span class="sxs-lookup"><span data-stu-id="3275a-527">Save and Store CAC network topology diagram in JPG or BMP format: Skype for Business Server 2015 administrators can save the CAC network topology configuration in a graphical format (JPG and BMP file formats) by using the **Save Network Configuration diagram as picture** option as shown below.</span></span>

![将网络配置保存为图片。](../media/Reskit_2012_Tools_Documentation_Image26.jpg)

 <span data-ttu-id="3275a-529"><strong>查看 CAC 网络拓扑配置数据：</strong>Skype for Business Server 2015 管理员可以使用如下所示的"查看网络配置"数据选项，以文本格式查看相关的网络配置数据，如网络区域、网络站点、带宽配置文件和站点子网 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="3275a-529"><strong>View CAC network topology configuration data:</strong>Skype for Business Server 2015 administrators can view related network configuration data such as network regions, network sites, bandwidth profiles, and site subnet IP addresses in a textual format by using the View Network Configuration data option as shown below.</span></span>

![查看网络配置数据。](../media/Reskit_2012_Tools_Documentation_Image27.jpg)

 <span data-ttu-id="3275a-531">**以树视图样式查看 CAC 网络拓扑：** Skype for Business Server 2015 管理员可以使用工具窗口左侧的控制面板以图形树视图样式查看相关的网络配置数据，如下所示。</span><span class="sxs-lookup"><span data-stu-id="3275a-531">**View CAC network topology in a tree-view style:** Skype for Business Server 2015 administrators can view related network configuration data in a graphical tree view style by using the control panel on the left side of the tool window as shown below.</span></span>

![在树视图中查看网络配置数据。](../media/Reskit_2012_Tools_Documentation_Image28.jpg)

 <span data-ttu-id="3275a-533">**定义 CAC** 网络拓扑链接的自定义 (，如站点到区域、区域到区域以及站点到站点链接) ：Skype for Business Server 2015 管理员可以使用如下所示的"设置"选项为 CAC 网络配置 WAN 链接定义自定义图形连接器。</span><span class="sxs-lookup"><span data-stu-id="3275a-533">**Define custom connectors for CAC network topology links (such as site-to-region, region-to-region, and site-to-site links):** Skype for Business Server 2015 administrators can define custom graphical connectors for CAC network configuration WAN links by using the Settings option as shown below.</span></span> <span data-ttu-id="3275a-534">这有助于区分在网络配置中预配的各种类型的网络链接。</span><span class="sxs-lookup"><span data-stu-id="3275a-534">This helps differentiate between various types of network links that are provisioned in the network configuration.</span></span>

![工具](../media/Reskit_2012_Tools_Documentation_Image29.jpg)

 <span data-ttu-id="3275a-536">**查看 CAC 网络拓扑站点信息、区域信息和已设置带宽策略：** Skype for Business Server 2015 管理员可以使用如下所示的选项查看相关的 CAC 网络区域信息、站点信息和 CAC 带宽设置信息。</span><span class="sxs-lookup"><span data-stu-id="3275a-536">**View CAC network topology site information, region information, and provisioned bandwidth policies:** Skype for Business Server 2015 administrators can view related CAC network region information, site information, and CAC bandwidth provisioning information by using options shown below.</span></span> <span data-ttu-id="3275a-537"> (例如， **单击网络区域** 或网络站点对象中的"信息"。) </span><span class="sxs-lookup"><span data-stu-id="3275a-537">(For example, click **Info** in a network region or network site object.)</span></span>

![为网络定义自定义连接器。](../media/Reskit_2012_Tools_Documentation_Image30.jpg)

### <a name="summary"></a><span data-ttu-id="3275a-539">摘要</span><span class="sxs-lookup"><span data-stu-id="3275a-539">Summary</span></span>

<span data-ttu-id="3275a-540">对于希望以图形格式查看部署的 CAC 网络拓扑的 Skype for Business Server 2015 管理员来说，此工具可能是一项有价值的资源。</span><span class="sxs-lookup"><span data-stu-id="3275a-540">This tool can be a valuable resource to Skype for Business Server 2015 administrators who would like to view CAC network topology for their deployment in a graphical format.</span></span>

## <a name="response-group-agent-live"></a><span data-ttu-id="3275a-541">响应组代理实时</span><span class="sxs-lookup"><span data-stu-id="3275a-541">Response Group Agent Live</span></span>
<span data-ttu-id="3275a-542"><a name="RGAL"> </a></span><span class="sxs-lookup"><span data-stu-id="3275a-542"><a name="RGAL"> </a></span></span>

<span data-ttu-id="3275a-543">响应组应用程序使代理能够使用其内置 Web 服务访问有用的实时信息。</span><span class="sxs-lookup"><span data-stu-id="3275a-543">The Response Group application gives agents the ability to access useful real-time information using its built-in Web service.</span></span> <span data-ttu-id="3275a-544">遗憾的是，此数据的图形视图在应用程序外部不可用。</span><span class="sxs-lookup"><span data-stu-id="3275a-544">Unfortunately, no graphical view of this data is available outside the application.</span></span> <span data-ttu-id="3275a-545">响应组代理实时资源工具包工具通过提供一种简单、图形的方式访问此信息，从而解决了此问题，通过实时 Skype for Business 通信软件信息（如存在其他代理）进行增强。</span><span class="sxs-lookup"><span data-stu-id="3275a-545">The Response Group Agent Live Resource Kit tool solves this issue by providing a simple and graphical way to access this information, enhanced with real-time Skype for Business communications software information such as the presence of other agents.</span></span>

### <a name="description"></a><span data-ttu-id="3275a-546">说明</span><span class="sxs-lookup"><span data-stu-id="3275a-546">Description</span></span>

<span data-ttu-id="3275a-547">响应组代理实时是一个 Windows 应用程序，提供登录和注销功能以及一些实时信息 (例如组成员身份和当前呼叫数) 响应组代理。</span><span class="sxs-lookup"><span data-stu-id="3275a-547">Response Group Agent Live is a Windows application that provides sign-in and sign-out functionality and some real-time information (such as group membership and current number of calls) to Response Group agents.</span></span> <span data-ttu-id="3275a-548">它旨在成为可从 Skype for Business 访问的 (组页面的增强版本。</span><span class="sxs-lookup"><span data-stu-id="3275a-548">It is meant to be an enhanced version of the Agent Groups page (accessible from Skype for Business.</span></span>

### <a name="purpose"></a><span data-ttu-id="3275a-549">用途</span><span class="sxs-lookup"><span data-stu-id="3275a-549">Purpose</span></span>

<span data-ttu-id="3275a-550">响应组应用程序将传入呼叫排入队列，然后将这些呼叫路由到代理组。</span><span class="sxs-lookup"><span data-stu-id="3275a-550">The Response Group application queues incoming calls, and then routes them to agent groups.</span></span> <span data-ttu-id="3275a-551">为了做出有关哪些呼叫服务的明智决定，代理可以访问有关其代理组实时信息，例如哪些其他代理可用以及每个队列中等待的呼叫数。</span><span class="sxs-lookup"><span data-stu-id="3275a-551">To make informed decisions about which calls to service, agents can access real-time information about their agent groups, such as what other agents are available and how many calls are waiting in each queue.</span></span> <span data-ttu-id="3275a-552">此信息最初只能通过响应组服务访问，由响应组代理 Live 以直观方式提供。</span><span class="sxs-lookup"><span data-stu-id="3275a-552">This information, initially accessible only through the Response Group service, is made available in an intuitive way by Response Group Agent Live.</span></span>

#### <a name="features"></a><span data-ttu-id="3275a-553">功能</span><span class="sxs-lookup"><span data-stu-id="3275a-553">Features</span></span>

<span data-ttu-id="3275a-554">响应组代理实时工具基于响应组服务和 Skype for Business Server 2015 SDK 构建。</span><span class="sxs-lookup"><span data-stu-id="3275a-554">The Response Group Agent Live tool is built on the Response Group service and the Skype for Business Server 2015 SDK.</span></span> <span data-ttu-id="3275a-555">它向响应组代理提供响应组服务 (的信息和功能，例如组成员身份、其他代理的存在以及呼叫等待) 。</span><span class="sxs-lookup"><span data-stu-id="3275a-555">It provides Response Group agents the information and capabilities that are available from the Response Group service (such as group membership, presence of other agents, and number of waiting calls).</span></span>

<span data-ttu-id="3275a-556">下图说明了响应组代理 Live 的主接口。</span><span class="sxs-lookup"><span data-stu-id="3275a-556">The figure below illustrates the main interface of Response Group Agent Live.</span></span>

![响应组代理实时工具。](../media/Reskit_2012_Tools_Documentation_Image37.JPG)

<span data-ttu-id="3275a-558">响应组代理实时中的代理可以使用以下三个主要功能：</span><span class="sxs-lookup"><span data-stu-id="3275a-558">The following three main features are available for agents in Response Group Agent Live:</span></span>

- <span data-ttu-id="3275a-559">**登录/注销：** (与可从 Skype for Business Server 2015) 访问的"代理组"页面相反，响应组代理实时仅允许代理一次登录或注销所有代理组。</span><span class="sxs-lookup"><span data-stu-id="3275a-559">**Sign-in/out:** Contrary to the Agent Groups page (accessible from Skype for Business Server 2015), Response Group Agent Live allows only agents to sign-in or out of all agent groups at once.</span></span> <span data-ttu-id="3275a-560">此应用程序为代理提供三种快速登录或注销方法：</span><span class="sxs-lookup"><span data-stu-id="3275a-560">This application provides three quick ways for agents to sign in or out:</span></span>

  - <span data-ttu-id="3275a-561">单击应用程序中的 (和) 登录/注销按钮。</span><span class="sxs-lookup"><span data-stu-id="3275a-561">Click the Sign-in/out (green and red) buttons within the application.</span></span>

  - <span data-ttu-id="3275a-562">右键单击系统托盘图标，然后选择登录或注销。</span><span class="sxs-lookup"><span data-stu-id="3275a-562">Right-click the system tray icon, and select sign in or sign out.</span></span>

  - <span data-ttu-id="3275a-563">使用可配置的键盘快捷方式。</span><span class="sxs-lookup"><span data-stu-id="3275a-563">Using configurable keyboard shortcuts.</span></span>

- <span data-ttu-id="3275a-564">**组成员身份：** 选择代理组后，响应组代理实时将在右窗格中显示此组中代理的列表。</span><span class="sxs-lookup"><span data-stu-id="3275a-564">**Group membership:** When an agent group is selected, Response Group Agent Live displays the list of agents in this group in the right pane.</span></span> <span data-ttu-id="3275a-565">如果 Skype for Business Server 2015 与此应用程序在同一计算机上运行，状态信息和联系人卡片将显示在响应组代理 Live 中。</span><span class="sxs-lookup"><span data-stu-id="3275a-565">If Skype for Business Server 2015 is running on the same computer as this application, presence information and the contact card are displayed in the Response Group Agent Live.</span></span> <span data-ttu-id="3275a-566">代理可以直接从该发送 IM 或呼叫其他代理。</span><span class="sxs-lookup"><span data-stu-id="3275a-566">Agents can send an IM or call other agents directly from there.</span></span>

- <span data-ttu-id="3275a-567">**实时统计信息：** 响应组代理实时功能提供所有代理组实时统计信息。</span><span class="sxs-lookup"><span data-stu-id="3275a-567">**Real-time statistics:** Response Group Agent Live provides real-time statistics for all agent groups.</span></span> <span data-ttu-id="3275a-568">更新频率为一分钟。</span><span class="sxs-lookup"><span data-stu-id="3275a-568">The update frequency is one minute.</span></span> <span data-ttu-id="3275a-569">响应组应答呼叫时，在组名称旁边添加一个可视指示器，其中显示当前排队的呼叫数。</span><span class="sxs-lookup"><span data-stu-id="3275a-569">When a call is answered by a Response Group, a visual indicator is added next to the group name with the current number of queued calls.</span></span> <span data-ttu-id="3275a-570">将指针停留在组上还会显示最长等待时间。</span><span class="sxs-lookup"><span data-stu-id="3275a-570">Pausing the pointer over a group also displays the longest waiting time.</span></span>

### <a name="requirements"></a><span data-ttu-id="3275a-571">要求</span><span class="sxs-lookup"><span data-stu-id="3275a-571">Requirements</span></span>

<span data-ttu-id="3275a-572">响应组代理 Live 需要 .NET Framework 4.0。</span><span class="sxs-lookup"><span data-stu-id="3275a-572">Response Group Agent Live requires the .NET Framework 4.0.</span></span> <span data-ttu-id="3275a-573">此外，若要利用状态和联系人卡片功能，必须在本地安装 Skype for Business (并运行) 。</span><span class="sxs-lookup"><span data-stu-id="3275a-573">In addition, to take advantage of the presence and contact card features, Skype for Business must be installed locally (and be running).</span></span>

#### <a name="configuration"></a><span data-ttu-id="3275a-574">配置</span><span class="sxs-lookup"><span data-stu-id="3275a-574">Configuration</span></span>

<span data-ttu-id="3275a-575">通过使用应用程序中的"选项"对话框，可以将响应组代理实时自定义为单个首选项。</span><span class="sxs-lookup"><span data-stu-id="3275a-575">Response Group Agent Live can be customized to individual preferences by using the Options dialog box in the application.</span></span> <span data-ttu-id="3275a-576">此外，管理员还可以定义默认主机地址，方法为直接编辑默认主机RGAgentLive.exe.config属性。</span><span class="sxs-lookup"><span data-stu-id="3275a-576">In addition, the administrator can define the default host address by editing directly the defaultHostAddress property of the RGAgentLive.exe.config file.</span></span>

<span data-ttu-id="3275a-577">下图说明了代理可用于配置主机地址和快捷键的"选项"对话框。</span><span class="sxs-lookup"><span data-stu-id="3275a-577">The figure below illustrates the Options dialog box that agents can use to configure the host address and shortcut keys.</span></span> <span data-ttu-id="3275a-578">通过单击主界面右上方的"选项"按钮可以访问此对话框。</span><span class="sxs-lookup"><span data-stu-id="3275a-578">This dialog is accessed by clicking the Options button on the top right of the main interface.</span></span>

!["响应组代理实时选项"对话框。](../media/Reskit_2012_Tools_Documentation_Image38.JPG)

<span data-ttu-id="3275a-580">可以在响应组代理实时配置中自定义以下三个不同的设置：</span><span class="sxs-lookup"><span data-stu-id="3275a-580">The following three different settings can be customized in the Response Group Agent Live configuration:</span></span>

- <span data-ttu-id="3275a-581">主机地址：这通常是属于代理主池的 Web 池 FQDN。</span><span class="sxs-lookup"><span data-stu-id="3275a-581">Host address: This is typically the web pool FQDN belonging to the agent's home pool.</span></span> <span data-ttu-id="3275a-582">确切的响应组服务地址会在后台自动派生自此信息 (主机地址后追加正确的) 。</span><span class="sxs-lookup"><span data-stu-id="3275a-582">The exact Response Group service address is automatically derived in the background from this information (by appending the right path after the host).</span></span>

- <span data-ttu-id="3275a-583">快捷方式：可以自定义登录/注销的确切快捷方式。</span><span class="sxs-lookup"><span data-stu-id="3275a-583">Shortcuts: The exact shortcuts to sign-in/out can be customized.</span></span> <span data-ttu-id="3275a-584">唯一的限制是，这两个快捷方式都必须包含"Windows 徽标" (以及至少另一个键) 。</span><span class="sxs-lookup"><span data-stu-id="3275a-584">The only limitation is that both shortcuts must contain the "Windows Logo" key (in addition to at least another key).</span></span>

- <span data-ttu-id="3275a-585">从 Windows 开始：可以将应用程序配置为自动启动 Windows。</span><span class="sxs-lookup"><span data-stu-id="3275a-585">Start with Windows: The application can be configured to start automatically with Windows.</span></span>

### <a name="examples"></a><span data-ttu-id="3275a-586">示例</span><span class="sxs-lookup"><span data-stu-id="3275a-586">Examples</span></span>

<span data-ttu-id="3275a-587">下图说明如何通过右键单击右窗格中的联系人来呼叫其他代理或向其他代理发送 IM。</span><span class="sxs-lookup"><span data-stu-id="3275a-587">The figure below illustrates how to call or send an IM to another agent by right-clicking the contact in the right pane.</span></span>

![发出呼叫或发送 IM。](../media/Reskit_2012_Tools_Documentation_Image39.JPG)

<span data-ttu-id="3275a-589">下图说明了响应组代理 Live 如何显示队列中的当前呼叫数以及所有这些传入呼叫中的最长等待时间。</span><span class="sxs-lookup"><span data-stu-id="3275a-589">The figure below illustrates how Response Group Agent Live displays the current number of calls in the queue and the longest waiting time among all these incoming calls.</span></span>

![查看队列信息。](../media/Reskit_2012_Tools_Documentation_Image40.JPG)

### <a name="summary"></a><span data-ttu-id="3275a-591">摘要</span><span class="sxs-lookup"><span data-stu-id="3275a-591">Summary</span></span>

<span data-ttu-id="3275a-592">快速登录和注销、组成员身份和基本实时统计信息是有趣的响应组代理功能，仅在应用程序外部从响应组服务提供。</span><span class="sxs-lookup"><span data-stu-id="3275a-592">Fast sign-in and sign-out, group membership, and basic real-time statistics are interesting Response Group agent features that are only available outside the application from the Response Group service.</span></span> <span data-ttu-id="3275a-593">通过响应组代理实时资源工具包工具，Skype for Business Server 2015 管理员可以为代理提供 Windows 应用程序，以便他们以更快、图形的方式执行任务。</span><span class="sxs-lookup"><span data-stu-id="3275a-593">With the Response Group Agent Live Resource Kit tool, Skype for Business Server 2015 administrators can provide their agents with a Windows application that allows them to perform tasks in a faster and graphical way.</span></span>

## <a name="sefautil"></a><span data-ttu-id="3275a-594">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="3275a-594">SEFAUtil</span></span>
<span data-ttu-id="3275a-595"><a name="SEFAUtil"> </a></span><span class="sxs-lookup"><span data-stu-id="3275a-595"><a name="SEFAUtil"> </a></span></span>

<span data-ttu-id="3275a-596">SEFAUtil (辅助扩展功能激活) 是一个命令行工具，使 Skype for Business Server 2015 通信软件管理员和技术支持代理能够代表 Skype for Business Server 2015 用户配置代理人响铃、呼叫转发、同时响铃、团队呼叫设置和组内呼叫接听。</span><span class="sxs-lookup"><span data-stu-id="3275a-596">SEFAUtil (secondary extension feature activation) is a command-line tool that enables Skype for Business Server 2015 communications software administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Skype for Business Server 2015 user.</span></span> <span data-ttu-id="3275a-597">该工具还允许管理员查询为特定用户发布的呼叫路由设置。SEFAUtil 工具允许管理员代表用户启用/禁用/修改呼叫转发或同时响铃。</span><span class="sxs-lookup"><span data-stu-id="3275a-597">The tool also allows administrators to query the call-routing settings that are published for a particular user.The SEFAUtil tool allows the administrator to enable/disable/modify call forwarding or simultaneously ringing on behalf of the user.</span></span> <span data-ttu-id="3275a-598">管理员可以以 SIP URI (的形式指定目标) 或使用用户已发布的目标。</span><span class="sxs-lookup"><span data-stu-id="3275a-598">The administrator can specify the target (in the form of a SIP URI) or use a target that has already been published by the user.</span></span> <span data-ttu-id="3275a-599">此工具还允许管理员代表用户添加或删除代理人或团队呼叫组的成员。此工具基于 Microsoft 统一通信托管 API (UCMA) 3.0 构建，要求管理员在 SEFAUtil 的中央管理存储中创建受信任的应用程序。</span><span class="sxs-lookup"><span data-stu-id="3275a-599">This tool also allows administrators to add or remove delegates or team-call group members on behalf of the user.This tool is built on Microsoft Unified Communications Managed API (UCMA) 3.0 and requires that administrators create a trusted application in the Central Management store for SEFAUtil.</span></span>

<span data-ttu-id="3275a-600">SEFAUtil (辅助扩展功能激活) 使 Skype for Business Server 2015 管理员和技术支持代理可以代表 Skype for Business Server 2015 用户配置代理人响铃、呼叫转发、同时响铃、团队呼叫设置和组内呼叫接听。</span><span class="sxs-lookup"><span data-stu-id="3275a-600">SEFAUtil (secondary extension feature activation) enables Skype for Business Server 2015 administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Skype for Business Server 2015 user.</span></span> <span data-ttu-id="3275a-601">此工具还允许管理员查询为特定用户发布的呼叫路由设置。</span><span class="sxs-lookup"><span data-stu-id="3275a-601">This tool also allows administrators to query the call-routing settings that are published for a particular user.</span></span>

### <a name="description"></a><span data-ttu-id="3275a-602">说明</span><span class="sxs-lookup"><span data-stu-id="3275a-602">Description</span></span>

<span data-ttu-id="3275a-603">当前版本的 SEFAUtil 只是一个命令行工具;没有支持的图形用户界面。</span><span class="sxs-lookup"><span data-stu-id="3275a-603">The current version of SEFAUtil is only a command-line tool; there is no supporting graphical user interface.</span></span> <span data-ttu-id="3275a-604">此工具基于 Microsoft 统一通信托管 API (UCMA) 3.0。</span><span class="sxs-lookup"><span data-stu-id="3275a-604">This tool is based on Microsoft Unified Communications Managed API (UCMA) 3.0.</span></span> <span data-ttu-id="3275a-605">此工具中的功能允许管理员和技术支持代理执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="3275a-605">The features in this tool allow administrators and helpdesk agents to do the following:</span></span>

- <span data-ttu-id="3275a-606">查看用户呼叫的所有呼叫路由 (包括呼叫转发、委派、同时响铃、团队呼叫和组内呼叫) </span><span class="sxs-lookup"><span data-stu-id="3275a-606">View all call routing settings for a user (includes call-forwarding, delegation, simultaneous ringing, team-call and group call pickup)</span></span>

- <span data-ttu-id="3275a-607">启用/禁用/修改呼叫 (包括目标计时器和无应答计时器) </span><span class="sxs-lookup"><span data-stu-id="3275a-607">Enable/disable/modify call-forwarding setting (includes destination and no-answer timer)</span></span>

- <span data-ttu-id="3275a-608">启用/禁用/修改呼叫转发即时配置</span><span class="sxs-lookup"><span data-stu-id="3275a-608">Enable/disable/modify call-forwarding immediate configurations</span></span>

- <span data-ttu-id="3275a-609">启用/禁用/修改委派设置</span><span class="sxs-lookup"><span data-stu-id="3275a-609">Enable/disable/modify delegation settings</span></span>

- <span data-ttu-id="3275a-610">启用/禁用/修改团队呼叫组设置</span><span class="sxs-lookup"><span data-stu-id="3275a-610">Enable/disable/modify team-call group settings</span></span>

    > [!NOTE]
    > <span data-ttu-id="3275a-611">Skype for Business Server 2015 SEFAUtil 工具中的新增功能</span><span class="sxs-lookup"><span data-stu-id="3275a-611">New in Skype for Business Server 2015 SEFAUtil tool</span></span>

- <span data-ttu-id="3275a-612">启用/禁用/修改同时响铃设置 (目标) </span><span class="sxs-lookup"><span data-stu-id="3275a-612">Enable/disable/modify simultaneous ringing settings (includes destination)</span></span>

    > [!NOTE]
    > <span data-ttu-id="3275a-613">Skype for Business Server 2015 SEFAUtil 工具中的新增功能</span><span class="sxs-lookup"><span data-stu-id="3275a-613">New in Skype for Business Server 2015 SEFAUtil tool</span></span>

- <span data-ttu-id="3275a-614">启用/禁用/修改组内呼叫接听设置</span><span class="sxs-lookup"><span data-stu-id="3275a-614">Enable/disable/modify group call pickup settings</span></span>

    > [!CAUTION]
    > <span data-ttu-id="3275a-615">Skype for Business Server 2015 SEFAUtil 工具中的新增功能</span><span class="sxs-lookup"><span data-stu-id="3275a-615">New in Skype for Business Server 2015 SEFAUtil tool</span></span>

<span data-ttu-id="3275a-616">此工具具有以下限制：</span><span class="sxs-lookup"><span data-stu-id="3275a-616">This tool has the following limitations:</span></span>

- <span data-ttu-id="3275a-617">仅支持位于 Skype for Business Server 池中的用户</span><span class="sxs-lookup"><span data-stu-id="3275a-617">Supported only for users homed in a Skype for Business Server pool</span></span>

- <span data-ttu-id="3275a-618">不支持批量编辑多个用户的呼叫路由设置</span><span class="sxs-lookup"><span data-stu-id="3275a-618">Bulk-edit of call routing settings for several users is not supported</span></span>

### <a name="output"></a><span data-ttu-id="3275a-619">输出</span><span class="sxs-lookup"><span data-stu-id="3275a-619">Output</span></span>

<span data-ttu-id="3275a-620">此工具的当前版本仅在命令提示符窗口中提供输出。</span><span class="sxs-lookup"><span data-stu-id="3275a-620">The current version of this tool provides output only in the Command Prompt window.</span></span> <span data-ttu-id="3275a-621">有关详细信息，请参阅本文档稍后的"示例"部分。</span><span class="sxs-lookup"><span data-stu-id="3275a-621">For details, see the Examples section later in this document.</span></span>

### <a name="purpose"></a><span data-ttu-id="3275a-622">用途</span><span class="sxs-lookup"><span data-stu-id="3275a-622">Purpose</span></span>

<span data-ttu-id="3275a-623">以下是可能使用此工具的一些关键方案：</span><span class="sxs-lookup"><span data-stu-id="3275a-623">Following are some of the key scenarios where this tool may be used:</span></span>

- <span data-ttu-id="3275a-624">Bob 是一名主管，已移至 Skype for Business Server 电话服务。</span><span class="sxs-lookup"><span data-stu-id="3275a-624">Bob is an executive and has been moved to Skype for Business Server telephony.</span></span> <span data-ttu-id="3275a-625">他对现有 PBX 系统具有委派。</span><span class="sxs-lookup"><span data-stu-id="3275a-625">He has delegation on his existing PBX system.</span></span> <span data-ttu-id="3275a-626">作为移动到 Skype for Business Server 2015 的一部分，管理员能够配置 Bob 的路由以反映其预先存在的委派配置。</span><span class="sxs-lookup"><span data-stu-id="3275a-626">As part of the move to Skype for Business Server 2015, the administrator is able to configure Bob's routing to reflect his pre-existing delegation configuration.</span></span>

- <span data-ttu-id="3275a-627">Alice 正在出差，意识到她需要她的一位客户拨打重要电话。</span><span class="sxs-lookup"><span data-stu-id="3275a-627">Alice is travelling and realizes that she is expecting an important call from one of her customers.</span></span> <span data-ttu-id="3275a-628">但是，她位于酒店中，无法访问计算机。</span><span class="sxs-lookup"><span data-stu-id="3275a-628">However, she is in a hotel and has no access to a computer.</span></span> <span data-ttu-id="3275a-629">她呼叫支持人员，并请求他们将拨打她的工作电话号码的所有呼叫转发到其移动电话号码。</span><span class="sxs-lookup"><span data-stu-id="3275a-629">She calls the helpdesk and requests that they forward to her mobile number all the calls made to her work number.</span></span> <span data-ttu-id="3275a-630">支持人员可以代表她执行配置。</span><span class="sxs-lookup"><span data-stu-id="3275a-630">The helpdesk personnel are able to do the configuration on her behalf.</span></span>

- <span data-ttu-id="3275a-631">Joe 每次工作时，拨打工作号码的呼叫都会发至其移动语音邮件;但是，在大多数其他位置，情况似乎可以正常运行。</span><span class="sxs-lookup"><span data-stu-id="3275a-631">Joe's calls to his work number are going to his mobile voicemail whenever he is at work; however, things appear to be working correctly in most other locations.</span></span> <span data-ttu-id="3275a-632">技术支持人员可以查看 Joe 的路由配置，并发现 Joe 已配置了同时响铃到其移动电话。</span><span class="sxs-lookup"><span data-stu-id="3275a-632">The helpdesk technician is able to view Joe's routing configuration and discovers that Joe has simultaneous ringing configured to his mobile phone.</span></span> <span data-ttu-id="3275a-633">技术人员询问 Joe 办公室的移动覆盖情况，并可以确定同时响铃规则是导致呼叫在网络覆盖较差时转到 Joe 的移动语音邮件的原因。</span><span class="sxs-lookup"><span data-stu-id="3275a-633">The technician asks Joe about the mobile coverage at his office and is able to determine that the simultaneous ringing rule is what is causing the calls to go to Joe's mobile voicemail when his network coverage is poor.</span></span>

- <span data-ttu-id="3275a-634">Mike 是 Contoso 的新员工，他加入了一个新团队，其中所有成员都配置为团队呼叫，启用 Skype for Business Server 2015 后，管理员能够设置其团队呼叫组设置以包括所有新的团队成员，此外，管理员将 Mike 添加为团队中每个成员的团队呼叫组成员。</span><span class="sxs-lookup"><span data-stu-id="3275a-634">Mike is a new employee at Contoso and he's joining a new team on which all members are configured for team-call, when being enabled for Skype for Business Server 2015, the administrator is able to set his team-call group settings to include all his new team members, additionally, the administrator adds Mike as a team-call group member for each of the members in his team.</span></span>

- <span data-ttu-id="3275a-635">Contoso 人力资源部门的客户服务做法是自第一次呼叫以来，为所有呼叫者提供个人服务。</span><span class="sxs-lookup"><span data-stu-id="3275a-635">A customer service practice in the human resources department at Contoso is to provide personal service for all callers since the first call.</span></span> <span data-ttu-id="3275a-636">鉴于部门的所有成员彼此非常接近，让所有电话通过团队呼叫同时响铃会对团队造成很大干扰。</span><span class="sxs-lookup"><span data-stu-id="3275a-636">Given that all members of the department sit very close to each other, having all phones ringing at the same time with team-call is very disruptive for the team.</span></span> <span data-ttu-id="3275a-637">为了提供最佳服务而不会干扰团队成员，Skype for Business Server 2015 管理员利用组内呼叫接听功能。</span><span class="sxs-lookup"><span data-stu-id="3275a-637">To provide the best service without disrupting the team members, the Skype for Business Server 2015 administrator takes advantage of the Group Call Pickup capability.</span></span> <span data-ttu-id="3275a-638">管理员将所有部门成员添加到分拣组，并与部门沟通分拣组号码。</span><span class="sxs-lookup"><span data-stu-id="3275a-638">The administrator adds all department members to a pickup group and communicates to the department the pickup group number.</span></span> <span data-ttu-id="3275a-639">当 Samantha 不在桌面上时，Joe 注意到她的电话在响铃，然后继续从自己的桌面接听电话。</span><span class="sxs-lookup"><span data-stu-id="3275a-639">When Samantha is absent from her desk, Joe notices her phone ringing and he proceeds to answer the call from his desk.</span></span>

### <a name="requirements"></a><span data-ttu-id="3275a-640">要求</span><span class="sxs-lookup"><span data-stu-id="3275a-640">Requirements</span></span>

<span data-ttu-id="3275a-641">SEFAUtil 工具只能在属于受信任应用程序池的一部分的计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="3275a-641">The SEFAUtil tool can be run only on a computer that is a part of a Trusted Application Pool.</span></span> <span data-ttu-id="3275a-642">UCMA 3.0 必须安装在该计算机上。</span><span class="sxs-lookup"><span data-stu-id="3275a-642">UCMA 3.0 must be installed on that computer.</span></span> <span data-ttu-id="3275a-643">若要运行该工具，必须在该池中创建具有 SEFAUtil 应用程序 ID 的新受信任应用程序。</span><span class="sxs-lookup"><span data-stu-id="3275a-643">To run the tool, a new Trusted Application with the SEFAUtil application ID must be created on that pool.</span></span>

### <a name="creating-a-new-trusted-application-for-the-sefautil-tool"></a><span data-ttu-id="3275a-644">为 SEFAUtil 工具创建新的受信任应用程序</span><span class="sxs-lookup"><span data-stu-id="3275a-644">Creating a new Trusted Application for the SEFAUtil tool</span></span>

1. <span data-ttu-id="3275a-645">SEFAUTil 工具只能在属于受信任应用程序一部分的计算机上应用程序池。</span><span class="sxs-lookup"><span data-stu-id="3275a-645">The SEFAUTil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="3275a-646">如果需要，可以使用以下 cmdlet 通过 Skype for Business Server 命令行应用程序池将池添加为新的受信任池：</span><span class="sxs-lookup"><span data-stu-id="3275a-646">If needed, adding a pool as a new trusted application pool can be done via the Skype for Business Server Management Shell with the following cmdlet:</span></span>

   ```powershell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```

    > [!NOTE]
    > <span data-ttu-id="3275a-647">必须在将用于运行 SEFAUtil 工具的任何计算机上安装 UCMA 3.0。</span><span class="sxs-lookup"><span data-stu-id="3275a-647">UCMA 3.0 must be installed on any computer that will be used to run the SEFAUtil tool.</span></span>

2. <span data-ttu-id="3275a-648">需要在 SEFAUtil 工具的拓扑中定义受信任应用程序。</span><span class="sxs-lookup"><span data-stu-id="3275a-648">A trusted application needs to be defined in the topology for the SEFAUtil tool.</span></span> <span data-ttu-id="3275a-649">若要将 SEFAUtil 定义为新的受信任应用程序，请使用 Skype for Business Server 命令行管理程序并执行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="3275a-649">To define SEFAUtil as a new trusted application, use the Skype for Business Server Management Shell and execute the following cmdlet:</span></span>

   ```powershell
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN> -Port 7489
   ```

    > [!NOTE]
    > <span data-ttu-id="3275a-650">如果需要，可以使用其他端口。</span><span class="sxs-lookup"><span data-stu-id="3275a-650">A different port can be used if needed.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="3275a-651">池 FQDN：将承载 SEFAUtil 应用程序的服务器或池的 FQDN (通常是 Skype for Business 前端服务器>池) 。</span><span class="sxs-lookup"><span data-stu-id="3275a-651">Pool FQDN: The FQDN of the server or pool that will host the SEFAUtil application (usually a Skype for Business Front End server     > or pool).</span></span>
    > <span data-ttu-id="3275a-652">池注册器 FQDN：与此域关联的 Skype for Business 前端服务器或池的 FQDN 应用程序池。</span><span class="sxs-lookup"><span data-stu-id="3275a-652">Pool Registrar FQDN: The FQDN of the Skype for Business Front End server or pool associated with this application pool.</span></span>
    > <span data-ttu-id="3275a-653">池站点：此池所位于的站点的站点 ID。</span><span class="sxs-lookup"><span data-stu-id="3275a-653">Pool Site: The Site ID of the site on which this pool is homed.</span></span>

3. <span data-ttu-id="3275a-654">需要启用拓扑更改。</span><span class="sxs-lookup"><span data-stu-id="3275a-654">The topology changes need to be enabled.</span></span> <span data-ttu-id="3275a-655">可以通过执行以下 cmdlet 通过 Skype for Business Server 命令行管理程序启用拓扑更改：</span><span class="sxs-lookup"><span data-stu-id="3275a-655">Enabling the topology changes can be done via the Skype for Business Server Management Shell by executing the following cmdlet:</span></span>

   ```powershell
   Enable-CsToplogy
   ```

4. <span data-ttu-id="3275a-656">如果需要，在将用于运行 SEFAUtil 工具的服务器中安装 Skype for Business Server 2015 资源工具包工具 (服务器必须是受信任服务器的一应用程序池) 。</span><span class="sxs-lookup"><span data-stu-id="3275a-656">If needed, install the Skype for Business Server 2015 Resource Kit Tools in the server that will be used to run the SEFAUtil tool (the server must be part of a trusted application pool).</span></span>

5. <span data-ttu-id="3275a-657">验证 SEFAUtil 是否正常运行。</span><span class="sxs-lookup"><span data-stu-id="3275a-657">Verify the SEFAUtil is running correctly.</span></span> <span data-ttu-id="3275a-658">为此，请通过具有管理员权限的 Windows 命令提示符运行该工具，以显示部署中用户的呼叫转发设置。</span><span class="sxs-lookup"><span data-stu-id="3275a-658">To do this, run the tool from a windows command prompt with administrator privileges to display the call forwarding settings of a user in the deployment.</span></span> <span data-ttu-id="3275a-659">默认情况下，该工具位于："...\Program Files\Skype for Business Server 2015\Reskit"中。</span><span class="sxs-lookup"><span data-stu-id="3275a-659">By default the tool will be located in: "…\Program Files\Skype for Business Server 2015\Reskit".</span></span> <span data-ttu-id="3275a-660">若要显示用户的呼叫转发设置，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="3275a-660">To display the call forwarding settings of a user, use the following command:</span></span>

   ```console
   SEFAUtil.exe <user SIP address> /server:<Skype for Business Server/Pool FQDN>
   ```

    <span data-ttu-id="3275a-661">应显示用户的呼叫转发设置。</span><span class="sxs-lookup"><span data-stu-id="3275a-661">The call forwarding settings of the user should be displayed.</span></span>

#### <a name="group-call-pickup"></a><span data-ttu-id="3275a-662">群组代接</span><span class="sxs-lookup"><span data-stu-id="3275a-662">Group Call Pickup</span></span>

<span data-ttu-id="3275a-663">组内呼叫分拣需要在 Skype for Business Server 2015 中进行其他配置，以完全启用该功能。</span><span class="sxs-lookup"><span data-stu-id="3275a-663">Group Call Pickup requires additional configuration in Skype for Business Server 2015 for the capability to be fully enabled.</span></span> <span data-ttu-id="3275a-664">在将分拣组分配给用户之前，请参阅组内呼叫分拣产品文档，以参阅此功能的规划和部署步骤。</span><span class="sxs-lookup"><span data-stu-id="3275a-664">Before assigning pickup groups to users, refer to the Group Call Pickup product documentation for the planning and deployment steps of this capability.</span></span>

### <a name="examples"></a><span data-ttu-id="3275a-665">示例</span><span class="sxs-lookup"><span data-stu-id="3275a-665">Examples</span></span>

#### <a name="display-current-call-handling-settings"></a><span data-ttu-id="3275a-666">显示当前呼叫处理设置</span><span class="sxs-lookup"><span data-stu-id="3275a-666">Display Current Call Handling Settings</span></span>

<span data-ttu-id="3275a-667">以下命令显示用户的呼叫处理。</span><span class="sxs-lookup"><span data-stu-id="3275a-667">The following command displays the call handling for the user.</span></span>  `SEFAUtil.exe /server:SfBS2015server.contoso.com katarina@contoso.com`

> [!NOTE]
> <span data-ttu-id="3275a-668">此示例使用 **/server** 开关指定要连接到的 Skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="3275a-668">This example uses the **/server** switch to specify the Skype for Business Server to connect to.</span></span>

 <span data-ttu-id="3275a-669">"输出"</span><span class="sxs-lookup"><span data-stu-id="3275a-669">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:20
Call Forward No Answer to: voicemail
```

#### <a name="set-the-call-forwardno-answer-destination"></a><span data-ttu-id="3275a-670">设置呼叫转发/无应答目标</span><span class="sxs-lookup"><span data-stu-id="3275a-670">Set the Call Forward/No Answer Destination</span></span>

<span data-ttu-id="3275a-671">本示例设置呼叫前向/无应答目标以及响铃延迟。</span><span class="sxs-lookup"><span data-stu-id="3275a-671">This example sets the call forward/no answer destination and the ring delay.</span></span> <span data-ttu-id="3275a-672">此处未提供 /server 开关;SEFAUtil 尝试自动发现 Skype for Business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="3275a-672">Here, the /server switch is not provided; SEFAUtil attempts to autodiscover the Skype for Business Server 2015.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablefwdnoanswer /callanswerwaittime:30 /setfwddestination:+14255550126@contoso.com;user=phone
```

 <span data-ttu-id="3275a-673">"输出"</span><span class="sxs-lookup"><span data-stu-id="3275a-673">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="enable-call-forwarding-immediately"></a><span data-ttu-id="3275a-674">立即启用呼叫转发</span><span class="sxs-lookup"><span data-stu-id="3275a-674">Enable Call Forwarding Immediately</span></span>

<span data-ttu-id="3275a-675">此示例立即启用呼叫转发给其他用户。</span><span class="sxs-lookup"><span data-stu-id="3275a-675">This example immediately enables call-forwarding to another user.</span></span>

```console
SEFAUtil.exe sip:katarina@contoso.com /enablefwdimmediate /setfwddestination:anders@contoso.com
```

 <span data-ttu-id="3275a-676">"输出"</span><span class="sxs-lookup"><span data-stu-id="3275a-676">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
Forward immediate to: sip:anders@contoso.com
```

#### <a name="disable-call-forwarding-immediately"></a><span data-ttu-id="3275a-677">立即禁用呼叫转发</span><span class="sxs-lookup"><span data-stu-id="3275a-677">Disable Call Forwarding Immediately</span></span>

<span data-ttu-id="3275a-678">此示例立即禁用呼叫转发。</span><span class="sxs-lookup"><span data-stu-id="3275a-678">This example immediately disables call forwarding.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com katarina@contoso.com /disablefwdimmediate
```

 <span data-ttu-id="3275a-679">"输出"</span><span class="sxs-lookup"><span data-stu-id="3275a-679">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-user-as-a-delegate-and-set-up-simultaneous-ringing-of-delegates"></a><span data-ttu-id="3275a-680">将用户添加为代理人并设置代理人的同时响铃</span><span class="sxs-lookup"><span data-stu-id="3275a-680">Add a User as a Delegate and Set Up Simultaneous Ringing of Delegates</span></span>

<span data-ttu-id="3275a-681">本示例将用户添加为代理人，并设置代理人同时响铃。</span><span class="sxs-lookup"><span data-stu-id="3275a-681">This example adds a user as a delegate and sets up simultaneous ringing of delegates.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /adddelegate:joe@contoso.com /simulringdelegates
```

 <span data-ttu-id="3275a-682">"输出"</span><span class="sxs-lookup"><span data-stu-id="3275a-682">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simultaneously Ringing Delegates: sip:joe@contoso.com
```

#### <a name="change-simultaneous-ringing-rule-of-delegates"></a><span data-ttu-id="3275a-683">更改代理人同时响铃规则</span><span class="sxs-lookup"><span data-stu-id="3275a-683">Change Simultaneous Ringing Rule of Delegates</span></span>

<span data-ttu-id="3275a-684">本示例将上一示例中设置的同时响铃规则更改为延迟响铃规则。</span><span class="sxs-lookup"><span data-stu-id="3275a-684">This example changes the simultaneous ringing rule that was set in the previous example to the delayed ringing rule.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /delayringdelegates:10
```

 <span data-ttu-id="3275a-685">"输出"</span><span class="sxs-lookup"><span data-stu-id="3275a-685">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
Delay Ringing Delegates (delay:10 seconds): sip:joe@contoso.com
```

#### <a name="remove-the-delegate"></a><span data-ttu-id="3275a-686">删除代理</span><span class="sxs-lookup"><span data-stu-id="3275a-686">Remove the Delegate</span></span>

<span data-ttu-id="3275a-687">本示例删除委托。</span><span class="sxs-lookup"><span data-stu-id="3275a-687">This example removes the delegate.</span></span>

> [!NOTE]
> <span data-ttu-id="3275a-688">删除最后一个委派时，将自动禁用委派响铃。</span><span class="sxs-lookup"><span data-stu-id="3275a-688">When the last delegate is removed, delegate ringing is automatically disabled.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removedelegate:joe@contoso.com
```

 <span data-ttu-id="3275a-689">"输出"</span><span class="sxs-lookup"><span data-stu-id="3275a-689">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-delegate-and-set-up-the-call-forward-to-delegates-rule"></a><span data-ttu-id="3275a-690">添加代理并设置Call-Forward委派规则</span><span class="sxs-lookup"><span data-stu-id="3275a-690">Add a Delegate and Set Up the Call-Forward to Delegates Rule</span></span>

<span data-ttu-id="3275a-691">本示例添加一个代理，并设置呼叫转发给代理人规则。</span><span class="sxs-lookup"><span data-stu-id="3275a-691">This example adds a delegate and sets up the call-forward to delegates rule.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /adddelegate:anders@contoso.com /fwdtodelegates
```

 <span data-ttu-id="3275a-692">"输出"</span><span class="sxs-lookup"><span data-stu-id="3275a-692">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Forwarding calls to Delegates: sip:anders@contoso.com
```

#### <a name="enable-simultaneous-ringing-and-set-a-destination-number"></a><span data-ttu-id="3275a-693">启用同时响铃并设置目标号码</span><span class="sxs-lookup"><span data-stu-id="3275a-693">Enable Simultaneous Ringing and Set a Destination Number</span></span>

<span data-ttu-id="3275a-694">本示例启用同时响铃并设置同时响铃目标号码。</span><span class="sxs-lookup"><span data-stu-id="3275a-694">This example enables simultaneous ringing and sets a simultaneous ringing destination number.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /setsimulringdestination:+14255550126 /enablesimulring
```

> [!NOTE]
> <span data-ttu-id="3275a-695">若要更改已启用同时响铃的用户的同时响铃目标号码，请保持使用 /enablesimulring 开关的命令，否则不会更改目标号码。</span><span class="sxs-lookup"><span data-stu-id="3275a-695">To change the simultaneous ringing destination number of a user that has already simultaneous ringing enabled, keep the command with the /enablesimulring switch, otherwise the destination number will not be changed.</span></span>

 <span data-ttu-id="3275a-696">"输出"</span><span class="sxs-lookup"><span data-stu-id="3275a-696">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: True
Simul_Ringing to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="disable-simultaneous-ringing"></a><span data-ttu-id="3275a-697">禁用同时响铃</span><span class="sxs-lookup"><span data-stu-id="3275a-697">Disable Simultaneous Ringing</span></span>

<span data-ttu-id="3275a-698">本示例禁用同时响铃。</span><span class="sxs-lookup"><span data-stu-id="3275a-698">This example disables simultaneous ringing.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablesimulring
```

 <span data-ttu-id="3275a-699">"输出"</span><span class="sxs-lookup"><span data-stu-id="3275a-699">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-team-member-for-team-call-and-set-up-simultaneous-ringing-to-the-team-call-members-group"></a><span data-ttu-id="3275a-700">将团队成员添加到Team-Call设置同时响铃到Team-Call成员组</span><span class="sxs-lookup"><span data-stu-id="3275a-700">Add a Team Member for Team-Call and Set up Simultaneous Ringing to the Team-Call Members Group</span></span>

<span data-ttu-id="3275a-701">本示例向用户的团队呼叫组添加团队成员，并启用团队呼叫组同时响铃。</span><span class="sxs-lookup"><span data-stu-id="3275a-701">This example adds a team member to the team-call group of a user and enables simultaneous ringing to the team-call group.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam
```

> [!NOTE]
> <span data-ttu-id="3275a-702">向用户的团队呼叫组添加成员将自动切换用户的同时响铃设置，以模拟其团队呼叫组。</span><span class="sxs-lookup"><span data-stu-id="3275a-702">Adding a member to the team-call group of a user will automatically switch the simultaneous ringing settigs of the users to simulring his team-call group.</span></span>

 <span data-ttu-id="3275a-703">"输出"</span><span class="sxs-lookup"><span data-stu-id="3275a-703">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Team ringing enabled. Team: sip:anders@contoso.com
```

#### <a name="remove-a-member-from-the-team-call-group"></a><span data-ttu-id="3275a-704">从组中删除Team-Call成员</span><span class="sxs-lookup"><span data-stu-id="3275a-704">Remove a Member from the Team-Call Group</span></span>

<span data-ttu-id="3275a-705">此示例将删除用户团队呼叫组的团队成员。</span><span class="sxs-lookup"><span data-stu-id="3275a-705">This example removes a team member of the team-call group of a user.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removeteammember:anders@contoso.com
```

> [!NOTE]
> <span data-ttu-id="3275a-706">如果要删除的成员是团队呼叫组的唯一成员，将自动禁用同时响铃到团队呼叫组。</span><span class="sxs-lookup"><span data-stu-id="3275a-706">If the member being removed is the only member of the team-call group, simultaneously ringing to the team-call group will be automatically disabled.</span></span>

 <span data-ttu-id="3275a-707">"输出"</span><span class="sxs-lookup"><span data-stu-id="3275a-707">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="set-the-delayed-ring-to-the-team-call-group"></a><span data-ttu-id="3275a-708">将延迟响铃设置为Team-Call组</span><span class="sxs-lookup"><span data-stu-id="3275a-708">Set the Delayed Ring to the Team-Call Group</span></span>

<span data-ttu-id="3275a-709">此示例将延迟响铃更改为团队呼叫组时间设置。</span><span class="sxs-lookup"><span data-stu-id="3275a-709">This example changes the delayed ring to the team-call group time setting.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /delayringteam:5
```

 <span data-ttu-id="3275a-710">"输出"</span><span class="sxs-lookup"><span data-stu-id="3275a-710">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Delay Ringing Team (delay:5 seconds). Team: sip:anders@contoso.com
```

#### <a name="enable-team-call"></a><span data-ttu-id="3275a-711">启用Team-Call</span><span class="sxs-lookup"><span data-stu-id="3275a-711">Enable Team-Call</span></span>

<span data-ttu-id="3275a-712">本示例为给定用户启用团队呼叫。</span><span class="sxs-lookup"><span data-stu-id="3275a-712">This example enables team-call for a given user.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /simulringteam
```

> [!NOTE]
> <span data-ttu-id="3275a-713">如果用户的团队呼叫组没有成员，将不会启用团队呼叫。</span><span class="sxs-lookup"><span data-stu-id="3275a-713">If the team-call group of the user has no members, team-call won't be enabled.</span></span>

 <span data-ttu-id="3275a-714">"输出"</span><span class="sxs-lookup"><span data-stu-id="3275a-714">**Output**</span></span>

#### <a name="disable-team-call"></a><span data-ttu-id="3275a-715">禁用Team-Call</span><span class="sxs-lookup"><span data-stu-id="3275a-715">Disable Team-Call</span></span>

<span data-ttu-id="3275a-716">本示例为给定用户禁用团队呼叫。</span><span class="sxs-lookup"><span data-stu-id="3275a-716">This example disables team-call for a given user.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disableteamcall
```

 <span data-ttu-id="3275a-717">"输出"</span><span class="sxs-lookup"><span data-stu-id="3275a-717">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="enable-group-call-pickup-and-assign-a-pickup-group-to-a-user"></a><span data-ttu-id="3275a-718">启用组内呼叫接听并将分拣组分配给用户</span><span class="sxs-lookup"><span data-stu-id="3275a-718">Enable Group Call Pickup and Assign a Pickup Group to a User</span></span>

<span data-ttu-id="3275a-719">本示例为用户分配一个分拣组，并启用组内呼叫分拣。</span><span class="sxs-lookup"><span data-stu-id="3275a-719">This example assigns a pickup group to a user and enables Group Call Pickup.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablegrouppickup:199
```

 <span data-ttu-id="3275a-720">"输出"</span><span class="sxs-lookup"><span data-stu-id="3275a-720">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Group Pickup Orbit: sip:199;phone-context=user-default@contoso.com;user=phone
```

#### <a name="disable-group-call-pickup"></a><span data-ttu-id="3275a-721">禁用组内呼叫接听</span><span class="sxs-lookup"><span data-stu-id="3275a-721">Disable Group Call Pickup</span></span>

<span data-ttu-id="3275a-722">本示例为给定用户禁用组内呼叫接听。</span><span class="sxs-lookup"><span data-stu-id="3275a-722">This example disables Group Call Pickup for a given user.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablegrouppickup
```

> [!NOTE]
> <span data-ttu-id="3275a-723">为用户禁用组内呼叫接听时，不会保留分配给该用户的组号码。</span><span class="sxs-lookup"><span data-stu-id="3275a-723">When you disable Group Call Pickup for a user, the group number that was assigned to the user is not retained.</span></span> <span data-ttu-id="3275a-724">如果随后希望为该用户重新启用组内呼叫接听，则必须使用 /enablegrouppickup 开关再次分配组号码。</span><span class="sxs-lookup"><span data-stu-id="3275a-724">If you subsequently want to re-enable Group Call Pickup for that user, you must assign the group number again with the /enablegrouppickup switch.</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
```

## <a name="sysprepps1"></a><span data-ttu-id="3275a-725">SYSPrep.ps1</span><span class="sxs-lookup"><span data-stu-id="3275a-725">SYSPrep.ps1</span></span>
<span data-ttu-id="3275a-726"><a name="SYSPrep"> </a></span><span class="sxs-lookup"><span data-stu-id="3275a-726"><a name="SYSPrep"> </a></span></span>

### <a name="description"></a><span data-ttu-id="3275a-727">说明</span><span class="sxs-lookup"><span data-stu-id="3275a-727">Description</span></span>

<span data-ttu-id="3275a-728">SYSPrep.ps1一Windows PowerShell脚本，它将在 Windows Server 2008 操作系统计算机上安装以下 Skype for Business Server 2015 必备组件。</span><span class="sxs-lookup"><span data-stu-id="3275a-728">SYSPrep.ps1 is a Windows PowerShell script that will install the following Skype for Business Server 2015 prerequisites on your Windows Server 2008 operating system machine.</span></span>

- <span data-ttu-id="3275a-729">Microsoft .Net Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="3275a-729">Microsoft .Net Framework 4.5</span></span>

- <span data-ttu-id="3275a-730">Microsoft SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="3275a-730">Microsoft SQL Server Express</span></span>

- <span data-ttu-id="3275a-731">Windows Powershell 版本 3.0</span><span class="sxs-lookup"><span data-stu-id="3275a-731">Windows Powershell version 3.0</span></span>

- <span data-ttu-id="3275a-732">Visual C++ 2010 可再发行组件</span><span class="sxs-lookup"><span data-stu-id="3275a-732">Visual C++ 2010 Redistributable</span></span>

- <span data-ttu-id="3275a-733">Internet Information Server 更新</span><span class="sxs-lookup"><span data-stu-id="3275a-733">Internet Information Server Updates</span></span>

- <span data-ttu-id="3275a-734">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="3275a-734">Windows Identity Foundation</span></span>

- <span data-ttu-id="3275a-735">Skype for Business Server 2015 核心文件</span><span class="sxs-lookup"><span data-stu-id="3275a-735">Skype for Business Server 2015 Core files</span></span>

  <span data-ttu-id="3275a-736">虽然脚本名称类似于 Microsoft Windows 操作系统的系统准备工具，但二者有所不同。</span><span class="sxs-lookup"><span data-stu-id="3275a-736">While the script name is similar to the System Preparation Tool for the Microsoft Windows operating systems, they are different.</span></span> <span data-ttu-id="3275a-737">此脚本将仅安装 Skype for Business Server 2015 所需的必备组件。</span><span class="sxs-lookup"><span data-stu-id="3275a-737">This script will only install the required prerequisites for Skype for Business Server 2015.</span></span> <span data-ttu-id="3275a-738">安装这些必备组件后，可以使用 Windows SYSPrep 工具创建服务器映像。</span><span class="sxs-lookup"><span data-stu-id="3275a-738">Once those prerequisites are installed, the Windows SYSPrep tool can then be used to create an image of the server.</span></span>

### <a name="requirements"></a><span data-ttu-id="3275a-739">要求</span><span class="sxs-lookup"><span data-stu-id="3275a-739">Requirements</span></span>

<span data-ttu-id="3275a-740">在运行 SYSPrep.ps1 脚本之前，必须将必备文件复制到 Windows Server 2008 操作系统计算机上本地文件夹中 (例如 **D：\Setup) 。**</span><span class="sxs-lookup"><span data-stu-id="3275a-740">Prior to running the SYSPrep.ps1 script, you must copy the prerequisite files to a local folder on the Windows Server 2008 operating system machine (for example **D:\Setup)**.</span></span> <span data-ttu-id="3275a-741">此文件夹还必须包含 Skype for Business Server 2015 文件的副本，特别是 **Setup.exe。**</span><span class="sxs-lookup"><span data-stu-id="3275a-741">This folder must also include a copy of the Skype for Business Server 2015 files, specifically **Setup.exe.**</span></span> <span data-ttu-id="3275a-742">可以从以下位置下载必备文件：</span><span class="sxs-lookup"><span data-stu-id="3275a-742">The prerequisite files can be downloaded from the following locations:</span></span>


| <span data-ttu-id="3275a-743">**先决条件**</span><span class="sxs-lookup"><span data-stu-id="3275a-743">**Prerequisite**</span></span>                                | <span data-ttu-id="3275a-744">**位置**</span><span class="sxs-lookup"><span data-stu-id="3275a-744">**Location**</span></span>                                                            |
|:------------------------------------------------|:------------------------------------------------------------------------|
| <span data-ttu-id="3275a-745">Microsoft .Net Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="3275a-745">Microsoft .Net Framework 4.5</span></span>  <br/>             | <https://go.microsoft.com/?linkid=9816306>  <br/>                       |
| <span data-ttu-id="3275a-746">Microsoft SQL Server Express 2008 R2</span><span class="sxs-lookup"><span data-stu-id="3275a-746">Microsoft SQL Server Express 2008 R2</span></span>  <br/>     | <https://www.microsoft.com/download/details.aspx?id=23650>  <br/> |
| <span data-ttu-id="3275a-747">Windows Powershell 版本 3.0</span><span class="sxs-lookup"><span data-stu-id="3275a-747">Windows Powershell version 3.0</span></span>  <br/>           | <https://www.microsoft.com/download/details.aspx?id=34595>  <br/> |
| <span data-ttu-id="3275a-748">Visual C++ 2010 可再发行组件</span><span class="sxs-lookup"><span data-stu-id="3275a-748">Visual C++ 2010 Redistributable</span></span>  <br/>          | <https://www.microsoft.com/download/details.aspx?id=5555>  <br/>  |
| <span data-ttu-id="3275a-749">Internet Information Server 更新</span><span class="sxs-lookup"><span data-stu-id="3275a-749">Internet Information Server Updates</span></span>  <br/>      | <https://www.microsoft.com/download/details.aspx?id=34869>  <br/> |
| <span data-ttu-id="3275a-750">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="3275a-750">Windows Identity Foundation</span></span>  <br/>              | <https://www.microsoft.com/download/details.aspx?id=17331>  <br/> |
| <span data-ttu-id="3275a-751">Skype for Business Server 2015 Setup.exe</span><span class="sxs-lookup"><span data-stu-id="3275a-751">Skype for Business Server 2015 Setup.exe</span></span>  <br/> | <span data-ttu-id="3275a-752">从 Skype for Business Server 2015 媒体复制</span><span class="sxs-lookup"><span data-stu-id="3275a-752">Copy from Skype for Business Server 2015 media</span></span>  <br/>                   |

### <a name="parameter"></a><span data-ttu-id="3275a-753">参数</span><span class="sxs-lookup"><span data-stu-id="3275a-753">Parameter</span></span>

<span data-ttu-id="3275a-754">**-SetupFolder** 参数将必备文件的目录位置作为参数</span><span class="sxs-lookup"><span data-stu-id="3275a-754">The **-SetupFolder** parameter takes as an argument the directory location of the prerequisite files</span></span>

### <a name="examples"></a><span data-ttu-id="3275a-755">示例</span><span class="sxs-lookup"><span data-stu-id="3275a-755">Examples</span></span>

<span data-ttu-id="3275a-756">若要运行 SYSPrep.ps1 脚本并安装 Skype for Business Server 2015 必备组件，请从提升的命令提示符运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="3275a-756">To run the SYSPrep.ps1 script and install the Skype for Business Server 2015 prerequisites, run the following command from an elevated command prompt:</span></span>

```console
./SysPrep.PS1 -SetupFolder D:\Setup
```

## <a name="unassigned-number-announcements-migration"></a><span data-ttu-id="3275a-757">未分配号码通知迁移</span><span class="sxs-lookup"><span data-stu-id="3275a-757">Unassigned Number Announcements Migration</span></span>
<span data-ttu-id="3275a-758"><a name="UNAM"> </a></span><span class="sxs-lookup"><span data-stu-id="3275a-758"><a name="UNAM"> </a></span></span>

<span data-ttu-id="3275a-759">未分配号码通知迁移工具使 Skype for Business Server 2015 管理员能够将通知应用程序服务未分配号码配置从源 Skype for Business Server 或池移动到目标 Skype for Business Server 或池。</span><span class="sxs-lookup"><span data-stu-id="3275a-759">The Unassigned Number Announcements Migration tool enables a Skype for Business Server 2015 administrator to move the unassigned numbers configuration that is serviced by the announcement application from a source Skype for Business Server or Pool to a destination Skype for Business Server or Pool.</span></span>

### <a name="description"></a><span data-ttu-id="3275a-760">说明</span><span class="sxs-lookup"><span data-stu-id="3275a-760">Description</span></span>

<span data-ttu-id="3275a-761">未分配号码通知迁移工具是一个 Windows PowerShell 脚本，用于将源服务器或池的公告应用程序所服务的未分配号码配置移动到其他服务器或池。</span><span class="sxs-lookup"><span data-stu-id="3275a-761">The Unassigned Number Announcements Migration tool is a Windows PowerShell script that moves the unassigned numbers configuration serviced by the announcement application of a source server or pool to a different server or pool.</span></span>

<span data-ttu-id="3275a-762">执行时，未分配号码通知迁移脚本将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="3275a-762">When executed, the Unassigned Number Announcements Migration script will perform the following operations:</span></span>

1. <span data-ttu-id="3275a-763">将源服务器或池中托管通知应用程序的未分配号码通知使用的所有音频文件移动到目标服务器或池的文件存储。</span><span class="sxs-lookup"><span data-stu-id="3275a-763">Move all the audio files used by the unassigned number announcements of the announcement application hosted in the source server or pool to the file store of the destination server or pool.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3275a-764">将音频文件复制到目标池后，将从源池中删除它们。</span><span class="sxs-lookup"><span data-stu-id="3275a-764">The audio files are removed from the source pool once they're copied to the destination pool.</span></span>

2. <span data-ttu-id="3275a-765">将为源服务器或池中承载的公告应用程序配置的所有未分配号码通知移动到目标服务器或池。</span><span class="sxs-lookup"><span data-stu-id="3275a-765">Move all unassigned number announcements configured for the announcement application hosted in the source server or pool to the destination server or pool.</span></span>

3. <span data-ttu-id="3275a-766">将源服务器或池中托管通知应用程序服务的所有未分配号码范围重新分配给目标服务器或池。</span><span class="sxs-lookup"><span data-stu-id="3275a-766">Reassign all the unassigned number ranges that are serviced by the announcement application hosted in the source server or pool to the destination server or pool.</span></span>

<span data-ttu-id="3275a-767">成功运行脚本后，由源服务器或池中承载的公告应用程序服务的所有未分配号码范围现在都由目标服务器或池使用相同的配置提供服务。</span><span class="sxs-lookup"><span data-stu-id="3275a-767">After successfully running the script, all the unassigned number ranges that were serviced by the announcement application hosted in the source server or pool will now be serviced with the same configuration by the destination server or pool.</span></span>

### <a name="output"></a><span data-ttu-id="3275a-768">输出</span><span class="sxs-lookup"><span data-stu-id="3275a-768">Output</span></span>

<span data-ttu-id="3275a-769">**Move-CsAnnouncementConfiguration** 脚本指示在 Skype for Business Server 命令行管理程序窗口中执行迁移操作的成功或失败。</span><span class="sxs-lookup"><span data-stu-id="3275a-769">The **Move-CsAnnouncementConfiguration** script indicates in the Skype for Business Server Management Shell window from where it's executed the success or failure of the migration operation.</span></span>

<span data-ttu-id="3275a-770">如果操作执行因任何错误而中断，则成功移动到目标位置的未分配号码范围将保留在目标中，并且其余要迁移的未分配号码范围将保留在源中以及操作表单中。</span><span class="sxs-lookup"><span data-stu-id="3275a-770">If the execution of the operation is interrupted by any error, the unassigned number ranges that were successfully moved to the destination will remain in the destination in an operational form and the rest of the unassigned number ranges to be migrated will remain in the source as well in an operational form.</span></span> <span data-ttu-id="3275a-771">若要完全迁移其余配置，请解决错误后重新运行脚本。</span><span class="sxs-lookup"><span data-stu-id="3275a-771">To fully migrate the rest of the configuration, rerun the script after addressing the error.</span></span>

### <a name="purpose"></a><span data-ttu-id="3275a-772">用途</span><span class="sxs-lookup"><span data-stu-id="3275a-772">Purpose</span></span>

<span data-ttu-id="3275a-773">未分配号码通知迁移脚本可用于以下三种方案：</span><span class="sxs-lookup"><span data-stu-id="3275a-773">The Unassigned Number Announcements Migration script can be used in the following three scenarios:</span></span>

- <span data-ttu-id="3275a-774">**将配置设置迁移到新版本的 Skype for Business Server：** Contoso 正在迁移到 Skype for Business Server 2015，作为迁移过程的一部分，Skype for Business Server 管理员希望将通知应用程序服务未分配号码配置从 Lync Server 2013 部署移动到新的 Skype for Business Server 2015 部署。</span><span class="sxs-lookup"><span data-stu-id="3275a-774">**Migrating configuration settings to a new version of Skype for Business Server:** Contoso is in the process of migrating to Skype for Business Server 2015 and as part of the migration process the Skype for Business Server administrator would like to move the unassigned numbers configuration serviced by the announcement application from the Lync Server 2013 deployment to the new Skype for Business Server 2015 deployment.</span></span> <span data-ttu-id="3275a-775">若要移动配置设置，Skype for Business Server 管理员使用未分配号码通知迁移工具。</span><span class="sxs-lookup"><span data-stu-id="3275a-775">To move the configuration settings, the Skype for Business Server administrator uses the Unassigned Number Announcements Migration tool.</span></span>

- <span data-ttu-id="3275a-776">**将部署从 Skype for Business Server 2015 回滚到 Lync Server 2013：** 由于意外因素，Contoso 必须回滚到新 Skype for Business Server 2015 部署的迁移。</span><span class="sxs-lookup"><span data-stu-id="3275a-776">**Rolling back a deployment from Skype for Business Server 2015 to Lync Server 2013:** Due unexpected factors, Contoso has to roll back the migration to the new Skype for Business Server 2015 deployment.</span></span> <span data-ttu-id="3275a-777">为了最大限度地减少服务中断，Skype for Business Server 管理员使用未分配号码通知迁移工具将配置从 Skype for Business Server 2015 部署回滚到 Lync Server 2013 部署。</span><span class="sxs-lookup"><span data-stu-id="3275a-777">To minimize disruptions to the service, the Skype for Business Server administrator uses the Unassigned Number Announcements Migration tool to roll back the configuration from the Skype for Business Server 2015 deployment to the Lync Server 2013 deployment.</span></span>

- <span data-ttu-id="3275a-778">**在部署之间移动数据：** Contoso 正在将一个池的所有服务器替换为较新的服务器。</span><span class="sxs-lookup"><span data-stu-id="3275a-778">**Moving data between deployments:** Contoso is in the process of replacing all the servers of one pool with newer servers.</span></span> <span data-ttu-id="3275a-779">其策略是部署新的 Skype for Business Server 2015 池，将旧池的所有数据移动到新池，然后弃用旧池。</span><span class="sxs-lookup"><span data-stu-id="3275a-779">Their strategy is to deploy a new Skype for Business Server 2015 pool, move all the data from the old to the new pool, and then deprecate the old pool.</span></span> <span data-ttu-id="3275a-780">部署新池后，使用未分配号码通知迁移工具将配置从旧池移动到新池。</span><span class="sxs-lookup"><span data-stu-id="3275a-780">Once the new pool is deployed, the Unassigned Number Announcements Migration tool is used to move the configuration from the old pool to the new one.</span></span>

#### <a name="requirements"></a><span data-ttu-id="3275a-781">要求</span><span class="sxs-lookup"><span data-stu-id="3275a-781">Requirements</span></span>

<span data-ttu-id="3275a-782">以下是成功运行该工具所需的主要要求：</span><span class="sxs-lookup"><span data-stu-id="3275a-782">The following are the main requirements needed to successfully run the tool:</span></span>

1. <span data-ttu-id="3275a-783">该脚本必须从安装了 Skype for Business Server 命令行管理程序 的计算机运行。</span><span class="sxs-lookup"><span data-stu-id="3275a-783">The script must be run from a computer that has Skype for Business Server Management Shell installed.</span></span>

2. <span data-ttu-id="3275a-784">通知应用程序必须成功部署在源和目标 Skype for Business 服务器或池中。</span><span class="sxs-lookup"><span data-stu-id="3275a-784">The announcement application has to be successfully deployed in the source and destination Skype for Business Servers or Pools.</span></span>

#### <a name="move-csannouncementconfiguration-script"></a><span data-ttu-id="3275a-785">Move-CsAnnouncementConfiguration脚本</span><span class="sxs-lookup"><span data-stu-id="3275a-785">Move-CsAnnouncementConfiguration script</span></span>

<span data-ttu-id="3275a-786">the Move-CsAnnouncementConfiguration script requires the two parameters that are described in the table below.</span><span class="sxs-lookup"><span data-stu-id="3275a-786">The Move-CsAnnouncementConfiguration script requires the two parameters that are described in the table below.</span></span>

![Move-CsAnnouncementConfiguration参数。](../media/Reskit_2012_Tools_Documentation_Image41.JPG)

### <a name="examples"></a><span data-ttu-id="3275a-788">示例</span><span class="sxs-lookup"><span data-stu-id="3275a-788">Examples</span></span>

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2013-pool-to-a-skype-for-business-server-2015-pool"></a><span data-ttu-id="3275a-789">将未分配号码通知配置从 Lync Server 2013 池移动到 Skype for Business Server 2015 池</span><span class="sxs-lookup"><span data-stu-id="3275a-789">Moving the Unassigned Number Announcements Configuration from a Lync Server 2013 Pool to a Skype for Business Server 2015 Pool</span></span>

<span data-ttu-id="3275a-790">此示例将未分配号码通知从源池 (Lync Server 2013) 移动到目标池 (Skype for Business Server 2015) 。</span><span class="sxs-lookup"><span data-stu-id="3275a-790">This example moves the unassigned number announcements from the source pool (Lync Server 2013) to the destination pool (Skype for Business Server 2015).</span></span>

```powershell
Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination SfBS2015Pool.contoso.com
```

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-skype-for-business-server-2015-pool-to-a-lync-server-2013-pool"></a><span data-ttu-id="3275a-791">将未分配号码通知配置从 Skype for Business Server 2015 池移动到 Lync Server 2013 池</span><span class="sxs-lookup"><span data-stu-id="3275a-791">Moving the Unassigned Number Announcements Configuration from a Skype for Business Server 2015 Pool to a Lync Server 2013 Pool</span></span>

<span data-ttu-id="3275a-792">此示例将未分配号码通知从源池 (Skype for Business Server 2015) 移动到目标池 (Lync Server 2013) 。</span><span class="sxs-lookup"><span data-stu-id="3275a-792">This example moves the unassigned number announcements from the source pool (Skype for Business Server 2015) to the destination pool (Lync Server 2013).</span></span>

```powershell
Move-CsAnnouncementConfiguration.ps1 -Source SfBS2015Pool.contoso.com -Destination LS2013Pool.contoso.com
```

## <a name="web-conf-data"></a><span data-ttu-id="3275a-793">Web Conf 数据</span><span class="sxs-lookup"><span data-stu-id="3275a-793">Web Conf Data</span></span>
<span data-ttu-id="3275a-794"><a name="WebConfData"> </a></span><span class="sxs-lookup"><span data-stu-id="3275a-794"><a name="WebConfData"> </a></span></span>

<span data-ttu-id="3275a-795">Web Conf Data Tool 允许 Skype for Business Server 2015 通信软件的管理员对与组织者的 Web 会议关联的数据进行更多控制。</span><span class="sxs-lookup"><span data-stu-id="3275a-795">The Web Conf Data Tool allows an administrator of Skype for Business Server 2015 communications software to have more control over the data associated with an organizer's Web conferences.</span></span> <span data-ttu-id="3275a-796">方案包括基于时间戳条件删除特定用户的会议数据的能力。</span><span class="sxs-lookup"><span data-stu-id="3275a-796">Scenarios include the ability to delete a specific user's meeting data based on a time stamp criteria.</span></span>

### <a name="description"></a><span data-ttu-id="3275a-797">说明</span><span class="sxs-lookup"><span data-stu-id="3275a-797">Description</span></span>

<span data-ttu-id="3275a-798">此工具允许管理员执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="3275a-798">This tool allows the administrator to perform the following operations:</span></span>

1. <span data-ttu-id="3275a-799">查找与单个用户关联的所有 Web 会议数据。</span><span class="sxs-lookup"><span data-stu-id="3275a-799">Find all Web conferencing data associated with a single user.</span></span>

2. <span data-ttu-id="3275a-800">删除与单个用户关联的所有 Web 会议数据。</span><span class="sxs-lookup"><span data-stu-id="3275a-800">Delete all Web conferencing data associated with a single user.</span></span>

3. <span data-ttu-id="3275a-801">删除与某个用户关联的所有超过特定日期的 Web 会议数据。</span><span class="sxs-lookup"><span data-stu-id="3275a-801">Delete all Web conferencing data associated with a single user that is older than a certain date.</span></span>

4. <span data-ttu-id="3275a-802">将单个用户从一个池移动到另一个池时，移动与该用户关联的所有 Web 会议数据。</span><span class="sxs-lookup"><span data-stu-id="3275a-802">Move all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3275a-803">Lync Server 2010 的资源工具包工具支持在将单个用户从一个池移动到另一个池时移动与该用户关联的所有 Web 会议数据。</span><span class="sxs-lookup"><span data-stu-id="3275a-803">The Resource Kit Tools for Lync Server 2010 supported moving all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span> <span data-ttu-id="3275a-804">此工具现在弃用此功能，而支持 **MoveConferenceData** 参数。</span><span class="sxs-lookup"><span data-stu-id="3275a-804">That functionality is now deprecated from this tool in favor of the **MoveConferenceData** parameter.</span></span> <span data-ttu-id="3275a-805">有关此参数的详细信息，请参阅 [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser.md?view=skype-ps) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3275a-805">For details about this parameter, see the [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser.md?view=skype-ps) cmdlet.</span></span>

<span data-ttu-id="3275a-806">该工具仅删除非活动会议的会议数据。</span><span class="sxs-lookup"><span data-stu-id="3275a-806">The tool deletes meeting data only for meetings that are inactive.</span></span> <span data-ttu-id="3275a-807">无法 (活动会议或) 中的会议。</span><span class="sxs-lookup"><span data-stu-id="3275a-807">Active meetings (or meetings in sessions) cannot be deleted.</span></span>

<span data-ttu-id="3275a-808">必须从与目标用户位于同一池中的计算机运行此工具。</span><span class="sxs-lookup"><span data-stu-id="3275a-808">This tool must be run from a computer that is in the same pool as the target user.</span></span> <span data-ttu-id="3275a-809">此工具管理其会议内容数据的用户必须托管在同一个用户池中。</span><span class="sxs-lookup"><span data-stu-id="3275a-809">The user whose meeting content data is being managed by this tool must be homed in the same user pool.</span></span>

### <a name="output"></a><span data-ttu-id="3275a-810">输出</span><span class="sxs-lookup"><span data-stu-id="3275a-810">Output</span></span>

<span data-ttu-id="3275a-811">此工具输出每个操作的结果：</span><span class="sxs-lookup"><span data-stu-id="3275a-811">This tool outputs the results of each of the operations:</span></span>

- <span data-ttu-id="3275a-812">如果执行查询，该工具将输出将该用户作为组织者的所有非活动会议数据文件夹的列表。</span><span class="sxs-lookup"><span data-stu-id="3275a-812">If a query is performed, the tool outputs the list of all inactive meeting data folders that have that user as an organizer.</span></span>

- <span data-ttu-id="3275a-813">如果执行删除操作，该工具将输出其数据将被删除的所有会议数据文件夹的列表。</span><span class="sxs-lookup"><span data-stu-id="3275a-813">If a delete is performed, the tool outputs the list of all meeting data folders whose data will be deleted.</span></span>

### <a name="requirements"></a><span data-ttu-id="3275a-814">要求</span><span class="sxs-lookup"><span data-stu-id="3275a-814">Requirements</span></span>

<span data-ttu-id="3275a-815">该工具需要在组织者当前所位于的同一池中运行。</span><span class="sxs-lookup"><span data-stu-id="3275a-815">The tool needs to be run in the same pool where the organizer is currently homed.</span></span>

<span data-ttu-id="3275a-816">该工具必须使用具有内容文件存储访问权限的管理员权限运行。</span><span class="sxs-lookup"><span data-stu-id="3275a-816">The tool must be run using administrator privileges with access to the Content File Store.</span></span>

### <a name="examples"></a><span data-ttu-id="3275a-817">示例</span><span class="sxs-lookup"><span data-stu-id="3275a-817">Examples</span></span>

<span data-ttu-id="3275a-818">下表介绍参数，其中一些参数在示例中使用。</span><span class="sxs-lookup"><span data-stu-id="3275a-818">The following table describes the parameters, some of which are used in the examples.</span></span>

![Web Conf Data Tool 参数。](../media/Reskit_2012_Tools_Documentation_Image51.JPG)

```console
WebConfDataTool.exe /User:user0@contoso.com /Action:query ""/ExpirationDate:08/09/2010 12:00:00""
```

<span data-ttu-id="3275a-820">前面的示例演示查询命令如何工作。</span><span class="sxs-lookup"><span data-stu-id="3275a-820">The preceding example shows how a query command would work.</span></span> <span data-ttu-id="3275a-821">此类命令的输出将是受此工具影响的所有会议内容文件夹的列表。</span><span class="sxs-lookup"><span data-stu-id="3275a-821">The output of such a command would be a list of all meeting content folders that would be affected by this tool.</span></span>

```console
WebConfDataTool.exe /User:user0@contoso.com /Action:delete
```

<span data-ttu-id="3275a-822">前面的示例是删除命令。</span><span class="sxs-lookup"><span data-stu-id="3275a-822">The preceding is an example of a delete command.</span></span> <span data-ttu-id="3275a-823">删除命令将从该用户中删除所有非活动会议文件夹。</span><span class="sxs-lookup"><span data-stu-id="3275a-823">The delete command will remove all inactive meeting folders from this user.</span></span>

### <a name="summary"></a><span data-ttu-id="3275a-824">摘要</span><span class="sxs-lookup"><span data-stu-id="3275a-824">Summary</span></span>

<span data-ttu-id="3275a-825">此工具对于需要更精确地控制会议数据的管理员来说，可能是一项有价值的资源。</span><span class="sxs-lookup"><span data-stu-id="3275a-825">This tool can be a valuable resource to administrators who need more precise control over conference meeting data.</span></span>


