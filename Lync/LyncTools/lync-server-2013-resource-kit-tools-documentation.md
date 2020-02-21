---
title: Lync Server 2013 资源工具包工具文档
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 Resource Kit Tools Documentation
ms:assetid: b1c341f1-86fa-479d-ba4d-28df5a4c1622
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945604(v=OCS.15)
ms:contentKeyID: 51541429
ms.date: 02/02/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 496d1c5e420ab20787d526f1a9fa93070e9eafb1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206498"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-resource-kit-tools-documentation"></a><span data-ttu-id="8047c-102">Lync Server 2013 资源工具包工具文档</span><span class="sxs-lookup"><span data-stu-id="8047c-102">Lync Server 2013 Resource Kit Tools Documentation</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8047c-103">_**上次修改的主题：** 2014-01-09_</span><span class="sxs-lookup"><span data-stu-id="8047c-103">_**Topic Last Modified:** 2014-01-09_</span></span>

<span data-ttu-id="8047c-104">本主题介绍属于 Lync Server 2013 资源工具包的工具，其中包括每个工具的用途及其使用示例。Lync Server 2013 的资源工具包工具可帮助部署和管理 Lync Server 2013 的 IT 管理员更轻松地执行日常任务。</span><span class="sxs-lookup"><span data-stu-id="8047c-104">This topic describes the tools that are part of the Lync Server 2013 Resource Kit, including the purpose of each tool, and examples of its use.The Lync Server 2013, Resource Kit Tools help to make routine tasks easier for IT administrators who deploy and manage Lync Server 2013.</span></span> <span data-ttu-id="8047c-105">例如，可以使用**Web 会议数据**工具轻松地控制用户在联机会议期间上载的数据。</span><span class="sxs-lookup"><span data-stu-id="8047c-105">For example, the **Web Conf Data** tool can be used to easily control data that is uploaded by users during an online meeting.</span></span> <span data-ttu-id="8047c-106">**SEFAUtil**工具可用于为用户设置代理呼叫转发和应答。</span><span class="sxs-lookup"><span data-stu-id="8047c-106">The **SEFAUtil** tool can be used to set up delegate call forwarding and answering for users.</span></span> <span data-ttu-id="8047c-107">我们鼓励 IT 管理员使用这些工具更有效地管理 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="8047c-107">We encourage IT administrators to use these tools to more effectively manage Lync Server 2013.</span></span>

<div>

## <a name="installation-of-the-resource-kit-tools"></a><span data-ttu-id="8047c-108">资源工具包工具的安装</span><span class="sxs-lookup"><span data-stu-id="8047c-108">Installation of the Resource Kit Tools</span></span>

<span data-ttu-id="8047c-109">若要安装 Lync Server 2013、资源工具包工具，请下载**ocsreskit.msi**。</span><span class="sxs-lookup"><span data-stu-id="8047c-109">To install the Lync Server 2013, Resource Kit Tools, download **OCSReskit.msi**.</span></span> <span data-ttu-id="8047c-110">您可以从下载中心下载资源工具包工具安装程序[https://go.microsoft.com/fwlink/p/?LinkID=330429](https://go.microsoft.com/fwlink/p/?linkid=330429)。</span><span class="sxs-lookup"><span data-stu-id="8047c-110">You can download the Resource Kit Tools installer from the Download Center at [https://go.microsoft.com/fwlink/p/?LinkID=330429](https://go.microsoft.com/fwlink/p/?linkid=330429).</span></span>

<span data-ttu-id="8047c-111">运行**ocsreskit.msi**以执行简单安装。</span><span class="sxs-lookup"><span data-stu-id="8047c-111">Run **OCSResKit.msi** to do a simple installation.</span></span> <span data-ttu-id="8047c-112">.Msi 在以下路径中安装所有工具： **% Program Files%\\Microsoft Lync Server 2013\\\reskit**。</span><span class="sxs-lookup"><span data-stu-id="8047c-112">The .msi installs all the tools in the following path: **%Program Files%\\Microsoft Lync Server 2013\\ResKit**.</span></span> <span data-ttu-id="8047c-113">包含自包含可执行文件的工具位于此文件夹中。</span><span class="sxs-lookup"><span data-stu-id="8047c-113">Tools that are self-contained executables are in this folder.</span></span> <span data-ttu-id="8047c-114">还包含文件的工具位于自己的子文件夹中。</span><span class="sxs-lookup"><span data-stu-id="8047c-114">Tools that also have files are in their own subfolders.</span></span>

</div>

<div>

## <a name="supported-environments"></a><span data-ttu-id="8047c-115">支持的环境</span><span class="sxs-lookup"><span data-stu-id="8047c-115">Supported Environments</span></span>

<span data-ttu-id="8047c-116">为了获得最佳性能，Lync Server 2013，资源工具包工具应安装在相同的环境中，并且具有与 Lync Server 2013 所需的相同规范。</span><span class="sxs-lookup"><span data-stu-id="8047c-116">For optimal performance, the Lync Server 2013, Resource Kit Tools should be installed in the same environment and with the same specifications that are required for Lync Server 2013.</span></span>

</div>

<div>

## <a name="resource-kit-tools-overview"></a><span data-ttu-id="8047c-117">资源工具包工具概述</span><span class="sxs-lookup"><span data-stu-id="8047c-117">Resource Kit Tools Overview</span></span>

<span data-ttu-id="8047c-118">以下列表介绍了 Lync Server 2013 资源工具包中提供的工具。</span><span class="sxs-lookup"><span data-stu-id="8047c-118">The following list describes the tools that are provided in the Lync Server 2013 Resource Kit.</span></span> <span data-ttu-id="8047c-119">下一节中介绍了每个工具的说明，包括要求和示例用法。</span><span class="sxs-lookup"><span data-stu-id="8047c-119">A description of each tool, including the requirements and example usage is covered in the following section.</span></span>

  - <span data-ttu-id="8047c-120">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="8047c-120">ABSConfig</span></span>

  - <span data-ttu-id="8047c-121">带宽策略服务监视器</span><span class="sxs-lookup"><span data-stu-id="8047c-121">Bandwidth Policy Service Monitor</span></span>

  - <span data-ttu-id="8047c-122">带宽利用率分析器</span><span class="sxs-lookup"><span data-stu-id="8047c-122">Bandwidth Utilization Analyzer</span></span>

  - <span data-ttu-id="8047c-123">调用寄存时间记录器</span><span class="sxs-lookup"><span data-stu-id="8047c-123">Call Parkometer</span></span>

  - <span data-ttu-id="8047c-124">CleanupStorageServiceData</span><span class="sxs-lookup"><span data-stu-id="8047c-124">CleanupStorageServiceData</span></span>

  - <span data-ttu-id="8047c-125">DBAnalyze</span><span class="sxs-lookup"><span data-stu-id="8047c-125">DBAnalyze</span></span>

  - <span data-ttu-id="8047c-126">ImportStorageServiceData</span><span class="sxs-lookup"><span data-stu-id="8047c-126">ImportStorageServiceData</span></span>

  - <span data-ttu-id="8047c-127">LCSSync</span><span class="sxs-lookup"><span data-stu-id="8047c-127">LCSSync</span></span>

  - <span data-ttu-id="8047c-128">LookupUserConsole</span><span class="sxs-lookup"><span data-stu-id="8047c-128">LookupUserConsole</span></span>

  - <span data-ttu-id="8047c-129">MsTurnPing</span><span class="sxs-lookup"><span data-stu-id="8047c-129">MsTurnPing</span></span>

  - <span data-ttu-id="8047c-130">网络配置查看器</span><span class="sxs-lookup"><span data-stu-id="8047c-130">Network Configuration Viewer</span></span>

  - <span data-ttu-id="8047c-131">响应组代理实时</span><span class="sxs-lookup"><span data-stu-id="8047c-131">Response Group Agent Live</span></span>

  - <span data-ttu-id="8047c-132">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="8047c-132">SEFAUtil</span></span>

  - <span data-ttu-id="8047c-133">SYSPrep. ps1</span><span class="sxs-lookup"><span data-stu-id="8047c-133">SYSPrep.ps1</span></span>

  - <span data-ttu-id="8047c-134">未分配号码通知迁移</span><span class="sxs-lookup"><span data-stu-id="8047c-134">Unassigned Number Announcements Migration</span></span>

  - <span data-ttu-id="8047c-135">Web 会议数据</span><span class="sxs-lookup"><span data-stu-id="8047c-135">Web Conf Data</span></span>

</div>

<div>

## <a name="absconfig"></a><span data-ttu-id="8047c-136">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="8047c-136">ABSConfig</span></span>

<span data-ttu-id="8047c-137">通讯簿服务配置工具（ABSConfig）是一种管理工具，可帮助管理员在 Lync Server 2013 中自定义通讯簿服务配置。</span><span class="sxs-lookup"><span data-stu-id="8047c-137">The Address Book Service Configuration tool (ABSConfig) is an administrative tool that helps administrators customize Address Book Service configuration in Lync Server 2013.</span></span> <span data-ttu-id="8047c-138">此工具还使 Lync Server 2013 管理员能够还原默认通讯簿服务设置。</span><span class="sxs-lookup"><span data-stu-id="8047c-138">This tool also enables Lync Server 2013 administrators to restore the default Address Book Service settings.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="8047c-139">说明</span><span class="sxs-lookup"><span data-stu-id="8047c-139">Description</span></span>

<span data-ttu-id="8047c-140">ABSConfig 是一个图形用户界面应用程序，使管理员能够配置与通讯簿服务相关的 Active Directory 域服务属性。</span><span class="sxs-lookup"><span data-stu-id="8047c-140">ABSConfig is a graphical user interface application that enables administrators to configure Active Directory Domain Services attributes that are related to Address Book Service.</span></span>

<span data-ttu-id="8047c-141">该工具的主要方案如下所示：</span><span class="sxs-lookup"><span data-stu-id="8047c-141">The primary scenarios for the tool are the following:</span></span>

  - <span data-ttu-id="8047c-142">使管理员能够将 Active Directory 域服务中的属性映射到 Lync Server 2013 的属性。</span><span class="sxs-lookup"><span data-stu-id="8047c-142">To enable administrators to map attributes in Active Directory Domain Services to the attributes for Lync Server 2013.</span></span>

  - <span data-ttu-id="8047c-143">使管理员能够指定要在通讯簿服务文件中包含或排除的 Active Directory 域服务属性。</span><span class="sxs-lookup"><span data-stu-id="8047c-143">To enable administrators to specify the Active Directory Domain Services attribute to be included or excluded in the Address Book Service files.</span></span>

  - <span data-ttu-id="8047c-144">使管理员能够还原默认通讯簿服务设置。</span><span class="sxs-lookup"><span data-stu-id="8047c-144">To enable administrators to restore default Address Book Service settings.</span></span>

<span data-ttu-id="8047c-145">可以使用 absConfig 文件启动 ABSConfig 工具。</span><span class="sxs-lookup"><span data-stu-id="8047c-145">The ABSConfig tool can be started by using the absConfig.exe file.</span></span> <span data-ttu-id="8047c-146">该工具将打开 "**配置属性**" 选项卡。此表中的选项可用于将 Active Directory 域服务属性映射到 Lync Server 2013 的属性字段，并指定哪些用户在通讯簿服务文件中根据特定的属性筛选器包含或排除。</span><span class="sxs-lookup"><span data-stu-id="8047c-146">The tool opens to the **Configure Attributes** tab. This table has options to map Active Directory Domain Services attributes to the attribute fields for Lync Server 2013 and to specify which users to include or exclude in Address Book Service files based on specific attribute filters.</span></span> <span data-ttu-id="8047c-147">它还具有自定义要在通讯簿文件中包含的电话号码的值的选项。</span><span class="sxs-lookup"><span data-stu-id="8047c-147">It also has options to customize which value of the phone number to be included in the Address Book file.</span></span> <span data-ttu-id="8047c-148">"**还原默认**值" 选项使管理员能够将通讯簿服务设置还原为默认值。</span><span class="sxs-lookup"><span data-stu-id="8047c-148">The **Restore Defaults** option enables administrators to restore Address Book Service settings to default values.</span></span>

</div>

<div>

## <a name="changes-from-lync-server-2010"></a><span data-ttu-id="8047c-149">来自 Lync Server 2010 的更改</span><span class="sxs-lookup"><span data-stu-id="8047c-149">Changes from Lync Server 2010</span></span>

<span data-ttu-id="8047c-150">在 Lync Server 2013 ABS 配置工具中，可以通过取消选中属性的 "启用" 复选框来删除属性（行）。</span><span class="sxs-lookup"><span data-stu-id="8047c-150">In Lync Server 2013 ABS Configuration tool, attributes (rows) may be removed by unchecking the “enable” checkbox for the attribute.</span></span> <span data-ttu-id="8047c-151">这与删除 Lync Server 2010 中的行的效果相同。</span><span class="sxs-lookup"><span data-stu-id="8047c-151">This has the same effect as deleting the row in Lync Server 2010.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8047c-152">"启用" 复选框位于最右侧的列中;您可能需要向右滚动才能看到列</span><span class="sxs-lookup"><span data-stu-id="8047c-152">The enable checkbox is in the far right column; you may need to scroll right to see the column</span></span>



</div>

</div>

<div>

## <a name="output"></a><span data-ttu-id="8047c-153">Output</span><span class="sxs-lookup"><span data-stu-id="8047c-153">Output</span></span>

<span data-ttu-id="8047c-154">ABSConfig 将通讯簿服务配置存储在数据库中。</span><span class="sxs-lookup"><span data-stu-id="8047c-154">ABSConfig stores the Address Book Service configuration in the database.</span></span>

    Path: %ProgramFiles%\Microsoft Lync Server 2013\Reskit

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="8047c-155">用途</span><span class="sxs-lookup"><span data-stu-id="8047c-155">Purpose</span></span>

<span data-ttu-id="8047c-156">ABSConfig 提供了一种快速、简便的方法来自定义 Lync Server 2013 通讯簿服务。</span><span class="sxs-lookup"><span data-stu-id="8047c-156">ABSConfig provides a quick and easy way to customize Lync Server 2013 Address Book Service.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="8047c-157">Requirements</span><span class="sxs-lookup"><span data-stu-id="8047c-157">Requirements</span></span>

<div>

## <a name="computer"></a><span data-ttu-id="8047c-158">计算机</span><span class="sxs-lookup"><span data-stu-id="8047c-158">Computer</span></span>

<span data-ttu-id="8047c-159">只能从安装了 Lync Server 2013 的加入域的计算机运行 ABSConfig。</span><span class="sxs-lookup"><span data-stu-id="8047c-159">ABSConfig can be run only from a domain-joined computer that has Lync Server 2013 installed.</span></span> <span data-ttu-id="8047c-160">在 Lync Server 2013 （Enterprise Edition）的情况下，可以在安装过程中启用了通讯簿服务的任何前端服务器上运行此工具。</span><span class="sxs-lookup"><span data-stu-id="8047c-160">In the case of Lync Server 2013, Enterprise Edition, this tool can be run on any Front End servers that have the Address Book Service enabled during setup.</span></span>

</div>

<div>

## <a name="network"></a><span data-ttu-id="8047c-161">网络</span><span class="sxs-lookup"><span data-stu-id="8047c-161">Network</span></span>

<span data-ttu-id="8047c-162">计算机应能够连接到前端池和后端数据库。</span><span class="sxs-lookup"><span data-stu-id="8047c-162">The computer should be able to connect to the Front End pool and back-end database.</span></span>

</div>

<div>

## <a name="software"></a><span data-ttu-id="8047c-163">软件</span><span class="sxs-lookup"><span data-stu-id="8047c-163">Software</span></span>

<span data-ttu-id="8047c-164">在运行 ABSConfig 工具之前，必须安装以下软件组件：</span><span class="sxs-lookup"><span data-stu-id="8047c-164">The following software components must be installed before running the ABSConfig tool:</span></span>

  - <span data-ttu-id="8047c-165">Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8047c-165">Microsoft Lync Server 2013</span></span>

</div>

<div>

## <a name="users"></a><span data-ttu-id="8047c-166">用户</span><span class="sxs-lookup"><span data-stu-id="8047c-166">Users</span></span>

<span data-ttu-id="8047c-167">拥有更新 Lync Server 2013 部署所需权限的管理员。</span><span class="sxs-lookup"><span data-stu-id="8047c-167">Administrators who have the permissions required to update the Lync Server 2013 deployment.</span></span>

</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="8047c-168">示例</span><span class="sxs-lookup"><span data-stu-id="8047c-168">Examples</span></span>

<span data-ttu-id="8047c-169">可以通过在命令提示符处键入**ABSConfig**来启动 ABSConfig。</span><span class="sxs-lookup"><span data-stu-id="8047c-169">ABSConfig can be started by typing **ABSConfig.exe** at a command prompt.</span></span> <span data-ttu-id="8047c-170">下面显示的是 ABSConfig 工具用户界面。</span><span class="sxs-lookup"><span data-stu-id="8047c-170">Shown below is the ABSConfig tool user interface.</span></span>

<span data-ttu-id="8047c-171">![ABSConfig 工具。](images/JJ945604.6fb63a70-7b63-4b8b-b7d1-82fe9aa2028f(OCS.15).jpg "ABSConfig 工具。")</span><span class="sxs-lookup"><span data-stu-id="8047c-171">![The ABSConfig.exe tool.](images/JJ945604.6fb63a70-7b63-4b8b-b7d1-82fe9aa2028f(OCS.15).jpg "The ABSConfig.exe tool.")</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="8047c-172">总结</span><span class="sxs-lookup"><span data-stu-id="8047c-172">Summary</span></span>

<span data-ttu-id="8047c-173">ABSConfig 工具为管理员提供了一个快速且易于使用的工具，可用于自定义 Lync Server 2013 通讯簿服务。</span><span class="sxs-lookup"><span data-stu-id="8047c-173">The ABSConfig tool provides administrators a quick and easy to use tool to customize Lync Server 2013 Address Book Service.</span></span>

</div>

</div>

<div>

## <a name="bandwidth-policy-service-monitor"></a><span data-ttu-id="8047c-174">带宽策略服务监视器</span><span class="sxs-lookup"><span data-stu-id="8047c-174">Bandwidth Policy Service Monitor</span></span>

<span data-ttu-id="8047c-175">带宽策略服务监视器工具旨在允许管理员查看以下项的列表：</span><span class="sxs-lookup"><span data-stu-id="8047c-175">The Bandwidth Policy Service Monitor tool is intended to allow administrators to view a list of the following:</span></span>

1.  <span data-ttu-id="8047c-176">拓扑中所有已配置的 Lync Server 2013 带宽策略服务（身份验证和核心）</span><span class="sxs-lookup"><span data-stu-id="8047c-176">All the configured Lync Server 2013 Bandwidth Policy services (Authentication and Core) in the topology</span></span>

2.  <span data-ttu-id="8047c-177">每个服务对其他带宽策略服务和边缘服务器所做的连接</span><span class="sxs-lookup"><span data-stu-id="8047c-177">The connections that each service makes to other Bandwidth Policy services and to the Edge servers</span></span>

3.  <span data-ttu-id="8047c-178">在网络配置文档中配置的所有链接，以及每个带宽策略服务报告的实时带宽使用率</span><span class="sxs-lookup"><span data-stu-id="8047c-178">All the links that are configured in the Network configuration document and real-time bandwidth usage as reported by each of the Bandwidth Policy services</span></span>

<div>

## <a name="description"></a><span data-ttu-id="8047c-179">说明</span><span class="sxs-lookup"><span data-stu-id="8047c-179">Description</span></span>

<span data-ttu-id="8047c-180">带宽策略服务监视器工具以基于 GUI 的应用程序的形式实现。</span><span class="sxs-lookup"><span data-stu-id="8047c-180">The Bandwidth Policy Service Monitor tool is implemented as a GUI-based application.</span></span> <span data-ttu-id="8047c-181">管理员通过运行 PDPMonUI 启动该工具。</span><span class="sxs-lookup"><span data-stu-id="8047c-181">Administrators start the tool by running PDPMonUI.exe.</span></span>

<span data-ttu-id="8047c-182">当工具启动时，它将尝试发现拓扑中的带宽策略服务列表。</span><span class="sxs-lookup"><span data-stu-id="8047c-182">When the tool starts, it attempts to discover the list of Bandwidth Policy services in the topology.</span></span> <span data-ttu-id="8047c-183">完成初始更新后，窗口左侧的窗格将使用由其所属群集分组的服务列表进行填充。</span><span class="sxs-lookup"><span data-stu-id="8047c-183">After the initial update is done, the pane to the left of the window is populated with a list of services that are grouped by the clusters that they belong to.</span></span>

<span data-ttu-id="8047c-184">当管理员选择特定的带宽策略服务时，右侧窗格将显示有关该特定服务的信息。</span><span class="sxs-lookup"><span data-stu-id="8047c-184">When administrators select a particular Bandwidth Policy Service, the pane on the right displays the information about that particular service.</span></span> <span data-ttu-id="8047c-185">该窗格还包含两个显示信息的主选项卡。</span><span class="sxs-lookup"><span data-stu-id="8047c-185">That pane also has two main tabs that display information.</span></span>

<div>

## <a name="machine-info-tab"></a><span data-ttu-id="8047c-186">计算机信息选项卡</span><span class="sxs-lookup"><span data-stu-id="8047c-186">Machine Info Tab</span></span>

<span data-ttu-id="8047c-187">"**计算机信息**" 选项卡显示已选择的带宽策略服务的详细信息，以及由选定带宽策略服务对其他服务所做的所有连接的列表和状态。</span><span class="sxs-lookup"><span data-stu-id="8047c-187">The **Machine Info** tab shows the details of the Bandwidth Policy Service that is selected and the list and state of all the connections that are made by the selected Bandwidth Policy Service to other services.</span></span>

</div>

<div>

## <a name="topology-info-tab"></a><span data-ttu-id="8047c-188">拓扑信息选项卡</span><span class="sxs-lookup"><span data-stu-id="8047c-188">Topology Info Tab</span></span>

<span data-ttu-id="8047c-189">"**拓扑信息**" 选项卡显示在网络配置设置中配置的所有链接的列表。</span><span class="sxs-lookup"><span data-stu-id="8047c-189">The **Topology Info** tab shows a list of all the links that are configured in the Network configuration settings.</span></span> <span data-ttu-id="8047c-190">对于每个链接，都会显示音频和视频带宽容量。</span><span class="sxs-lookup"><span data-stu-id="8047c-190">For each link, the audio and video bandwidth capacity is displayed.</span></span> <span data-ttu-id="8047c-191">此外，当前使用的带宽以 Kbps 和容量百分比的形式显示。</span><span class="sxs-lookup"><span data-stu-id="8047c-191">Additionally, the currently utilized bandwidth is displayed, both in Kbps and as a percentage of the capacity.</span></span> <span data-ttu-id="8047c-192">该工具使用颜色编码突出显示具有接近容量的使用率的链接，这使管理员能够快速隔离此类链接。</span><span class="sxs-lookup"><span data-stu-id="8047c-192">The tool uses color-coding to highlight links that have utilization that is close to the capacity—this allows administrators to quickly isolate such links.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8047c-193">如果带宽策略服务监视器工具在连接到任何已配置的带宽策略服务时遇到故障，则不会填充<STRONG>计算机信息</STRONG>和<STRONG>拓扑信息</STRONG>选项卡中的信息。</span><span class="sxs-lookup"><span data-stu-id="8047c-193">If the Bandwidth Policy Service Monitor tool experiences failure when it connects to any of the configured Bandwidth Policy services, the information in the <STRONG>Machine Info</STRONG> and the <STRONG>Topology Info</STRONG> tabs won’t be populated.</span></span> <span data-ttu-id="8047c-194">但是，该工具可能会在最初连接但随后失去与该服务的连接。</span><span class="sxs-lookup"><span data-stu-id="8047c-194">However, it is possible that the tool might connect initially but subsequently lose its connection to the service.</span></span> <span data-ttu-id="8047c-195">在这种情况下，管理员可能会看到过时的信息。</span><span class="sxs-lookup"><span data-stu-id="8047c-195">In such cases, administrators might see outdated information.</span></span> <span data-ttu-id="8047c-196">每个选项卡上都有<STRONG>最后更新</STRONG>的时间戳，这些选项卡可允许管理员查看特定带宽策略服务的上次更新数据的时间。</span><span class="sxs-lookup"><span data-stu-id="8047c-196">There is a <STRONG>Last Updated</STRONG> time stamp on each of the tabs that can allow administrators to see when the data was last updated for a particular Bandwidth Policy Service.</span></span>



</div>

</div>

</div>

<div>

## <a name="output"></a><span data-ttu-id="8047c-197">Output</span><span class="sxs-lookup"><span data-stu-id="8047c-197">Output</span></span>

<span data-ttu-id="8047c-198">没有命令行输出;程序输出包含在主图形用户界面（GUI）中。</span><span class="sxs-lookup"><span data-stu-id="8047c-198">There is no command-line output; the program output is contained within the main graphical user interface (GUI).</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="8047c-199">用途</span><span class="sxs-lookup"><span data-stu-id="8047c-199">Purpose</span></span>

<span data-ttu-id="8047c-200">带宽策略服务监视器工具旨在使管理员能够查看拓扑中定义的每个带宽策略服务的状态。</span><span class="sxs-lookup"><span data-stu-id="8047c-200">The purpose of the Bandwidth Policy Service Monitor tool is to allow administrators visibility into the state of each of the Bandwidth Policy services that are defined in the topology.</span></span> <span data-ttu-id="8047c-201">此外，管理员可以查看网络配置文档中定义的所有链接的实时带宽使用率。</span><span class="sxs-lookup"><span data-stu-id="8047c-201">In addition, administrators can see real-time bandwidth usage for all the links that are defined in the Network configuration document.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="8047c-202">Requirements</span><span class="sxs-lookup"><span data-stu-id="8047c-202">Requirements</span></span>

<span data-ttu-id="8047c-203">带宽策略服务监视器工具需要在作为 Lync Server 拓扑的一部分的计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="8047c-203">The Bandwidth Policy Service Monitor tool needs to be run on a computer that is part of the Lync Server topology.</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="8047c-204">总结</span><span class="sxs-lookup"><span data-stu-id="8047c-204">Summary</span></span>

<span data-ttu-id="8047c-205">带宽策略服务监视器工具对于管理员来说是一项宝贵的资源，这样他们就可以检查拓扑中所有带宽策略服务的状态—更重要的是，它们可以获取链接的实时带宽利用率，在网络配置设置中定义。</span><span class="sxs-lookup"><span data-stu-id="8047c-205">The Bandwidth Policy Service Monitor tool can be a valuable resource to administrators so they can inspect the state of all the Bandwidth Policy services in the topology—and more importantly—they can obtain real-time bandwidth utilization for the links that are defined in the Network configuration settings.</span></span>

</div>

</div>

<div>

## <a name="bandwidth-utilization-analyzer"></a><span data-ttu-id="8047c-206">带宽利用率分析器</span><span class="sxs-lookup"><span data-stu-id="8047c-206">Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="8047c-207">带宽利用率分析器是一种工具，该工具通过企业网络中的多个 WAN 链接的 UC 终结点创建有关带宽消耗的各种视图的报告。</span><span class="sxs-lookup"><span data-stu-id="8047c-207">Bandwidth Utilization Analyzer is a tool that creates reports about various views of bandwidth consumption by the UC endpoints across WAN links in the enterprise network.</span></span> <span data-ttu-id="8047c-208">这些报告可用于了解当前带宽消耗模式，并可帮助进行带宽容量规划。</span><span class="sxs-lookup"><span data-stu-id="8047c-208">These reports can be used to understand the current bandwidth consumption pattern and to aid in bandwidth capacity planning.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="8047c-209">说明</span><span class="sxs-lookup"><span data-stu-id="8047c-209">Description</span></span>

<span data-ttu-id="8047c-210">带宽利用率分析器是作为基于 GUI 的应用程序实现的。</span><span class="sxs-lookup"><span data-stu-id="8047c-210">Bandwidth Utilization Analyzer is implemented as a GUI-based application.</span></span> <span data-ttu-id="8047c-211">此工具专门针对网络中的音频利用率生成报告，并帮助进行容量规划。</span><span class="sxs-lookup"><span data-stu-id="8047c-211">This tool generates reports specifically for audio utilization across the network and helps with capacity planning.</span></span> <span data-ttu-id="8047c-212">它还会对分配给各个链路的带宽容量进行迭代。</span><span class="sxs-lookup"><span data-stu-id="8047c-212">It also iterates on the bandwidth capacity that is assigned to various links.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="8047c-213">Output</span><span class="sxs-lookup"><span data-stu-id="8047c-213">Output</span></span>

<span data-ttu-id="8047c-214">带宽利用率分析器为系统中配置的所有 WAN 链路提供了图形 al 的带宽容量和使用情况的视频。</span><span class="sxs-lookup"><span data-stu-id="8047c-214">Bandwidth Utilization Analyzer provides graphic al plots of bandwidth capacity and utilization for audio for all the WAN links that are configured in the system.</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="8047c-215">用途</span><span class="sxs-lookup"><span data-stu-id="8047c-215">Purpose</span></span>

<span data-ttu-id="8047c-216">在任何语音和视频部署中，监视和理解整个企业网络中媒体流量的带宽利用率趋势非常关键。</span><span class="sxs-lookup"><span data-stu-id="8047c-216">In any voice and video deployment, it’s critical to monitor and understand the trend of bandwidth utilization of media traffic across the enterprise network.</span></span> <span data-ttu-id="8047c-217">利用带宽利用率分析器工具，管理员即可实现这一点。</span><span class="sxs-lookup"><span data-stu-id="8047c-217">The Bandwidth Utilization Analyzer tool allows an administrator to achieve just that.</span></span> <span data-ttu-id="8047c-218">此工具执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="8047c-218">This tool does the following:</span></span>

  - <span data-ttu-id="8047c-219">为整个网络中的音频利用率生成特定报告</span><span class="sxs-lookup"><span data-stu-id="8047c-219">Generates specific reports for audio utilization across the network</span></span>

  - <span data-ttu-id="8047c-220">有助于在分配给各个链路的带宽容量中进行更有效的容量规划和迭代</span><span class="sxs-lookup"><span data-stu-id="8047c-220">Helps with more effective capacity planning and iteration on the bandwidth capacity that is assigned to various links</span></span>

<span data-ttu-id="8047c-221">带宽利用率分析器可生成带宽容量和使用率报告的图形化绘图;它们如下所示：</span><span class="sxs-lookup"><span data-stu-id="8047c-221">Bandwidth Utilization Analyzer can generate graphical plots of bandwidth capacity and utilization reports; they are as follows:</span></span>

  - <span data-ttu-id="8047c-222">企业网络中的所有 WAN 链路</span><span class="sxs-lookup"><span data-stu-id="8047c-222">All the WAN links in the enterprise network</span></span>

  - <span data-ttu-id="8047c-223">通过选定的已选择的 WAN 链接进行筛选</span><span class="sxs-lookup"><span data-stu-id="8047c-223">Filtered by selected WAN links that have been chosen</span></span>

  - <span data-ttu-id="8047c-224">通过已超出链接容量的 WAN 链路进行筛选</span><span class="sxs-lookup"><span data-stu-id="8047c-224">Filtered by WAN links that have exceeded link capacity</span></span>

  - <span data-ttu-id="8047c-225">通过已在使用预配带宽的 WAN 链接进行筛选</span><span class="sxs-lookup"><span data-stu-id="8047c-225">Filtered by WAN links that have been under-utilizing the provisioned bandwidth</span></span>

  - <span data-ttu-id="8047c-226">按已达到关键级别的 WAN 链路进行筛选（WAN 链路带宽使用率大于90% 的带宽使用率）</span><span class="sxs-lookup"><span data-stu-id="8047c-226">Filter by WAN links that have been reaching critical levels (a bandwidth utilization that is greater than 90% of bandwidth capacity of the WAN link)</span></span>

  - <span data-ttu-id="8047c-227">按 WAN 链接类型（网络站点链接、区域间链接和站点内的链接）进行筛选</span><span class="sxs-lookup"><span data-stu-id="8047c-227">Filtered by WAN link type—network-site links, interregional links, and links within a site</span></span>

  - <span data-ttu-id="8047c-228">按网络区域筛选</span><span class="sxs-lookup"><span data-stu-id="8047c-228">Filtered by network region</span></span>

<div>

## <a name="applications"></a><span data-ttu-id="8047c-229">应用程序</span><span class="sxs-lookup"><span data-stu-id="8047c-229">Applications</span></span>

<span data-ttu-id="8047c-230">带宽使用率分析器包含以下两个应用程序（工具）：</span><span class="sxs-lookup"><span data-stu-id="8047c-230">Bandwidth Utilization Analyzer has the following two applications (tools):</span></span>

  - <span data-ttu-id="8047c-231">**Wanlinklogcollector.exe**   此工具使其用户能够输入所需的信息。</span><span class="sxs-lookup"><span data-stu-id="8047c-231">**WanLinkLogCollector.exe**   This tool enables its user to input the required information.</span></span>

  - <span data-ttu-id="8047c-232">**Bandwidthutilizationanalyzer.xlsm xlsm**  Microsoft Excel 电子表格软件报告由 wanlinklogcollector.exe 自动启动。</span><span class="sxs-lookup"><span data-stu-id="8047c-232">**BandwidthUtilizationAnalyzer.xlsm**  A Microsoft Excel spreadsheet software report is automatically launched by WanLinkLogCollector.exe.</span></span> <span data-ttu-id="8047c-233">此应用程序允许用户将筛选器应用于报表，如本文后面所示。</span><span class="sxs-lookup"><span data-stu-id="8047c-233">This application allows the user to apply filters to the report as shown later in this article.</span></span>

</div>

<div>

## <a name="phases-of-using-bandwidth-utilization-analyzer"></a><span data-ttu-id="8047c-234">使用带宽使用率分析器的各个阶段</span><span class="sxs-lookup"><span data-stu-id="8047c-234">Phases of Using Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="8047c-235">使用带宽使用率分析器时有两个阶段：</span><span class="sxs-lookup"><span data-stu-id="8047c-235">There are two phases when using Bandwidth Utilization Analyzer:</span></span>

  - <span data-ttu-id="8047c-236">收集使用 Wanlinklogcollector.exe 执行的日志</span><span class="sxs-lookup"><span data-stu-id="8047c-236">Collect logs, which is performed by using WanLinkLogCollector.exe</span></span>

  - <span data-ttu-id="8047c-237">自定义报表，通过使用 Bandwidthutilizationanalyzer.xlsm 执行。 xlsm</span><span class="sxs-lookup"><span data-stu-id="8047c-237">Customize reports, which is performed by using BandwidthUtilizationAnalyzer.xlsm</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="8047c-238">强烈建议最终用户手动启动 xlsm Bandwidthutilizationanalyzer.xlsm。</span><span class="sxs-lookup"><span data-stu-id="8047c-238">We strongly recommend that BandwidthUtilizationAnalyzer.xlsm not be manually launched by end users.</span></span>



</div>

</div>

<div>

## <a name="starting-bandwidth-utilization-analyzer"></a><span data-ttu-id="8047c-239">启动带宽使用率分析器</span><span class="sxs-lookup"><span data-stu-id="8047c-239">Starting Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="8047c-240">在命令提示符处或使用 Windows 资源管理器启动 Wanlinklogcollector.exe。</span><span class="sxs-lookup"><span data-stu-id="8047c-240">Start WanLinkLogCollector.exe at the command prompt or by using Windows Explorer.</span></span>

<span data-ttu-id="8047c-241">**使用 Wanlinklogcollector.exe**</span><span class="sxs-lookup"><span data-stu-id="8047c-241">**Using WanLinkLogCollector.exe**</span></span>

<span data-ttu-id="8047c-242">使用 Wanlinklogcollector.exe 有三个步骤：</span><span class="sxs-lookup"><span data-stu-id="8047c-242">There are three steps to using WanLinkLogCollector.exe:</span></span>

1.  <span data-ttu-id="8047c-243">**日志时间线**   提供需要生成报告的时间线</span><span class="sxs-lookup"><span data-stu-id="8047c-243">**Log the timeline**   Provide the timeline that the report needs to be generated for</span></span>

2.  <span data-ttu-id="8047c-244">**指定文件目录**   提供文件位置信息</span><span class="sxs-lookup"><span data-stu-id="8047c-244">**Specify the file directories**   Provide file location information</span></span>

3.  <span data-ttu-id="8047c-245">**收集日志并启动报告查看器**  执行命令以生成报告</span><span class="sxs-lookup"><span data-stu-id="8047c-245">**Collect the logs and launch the report viewer**  Execute the command to generate the report</span></span>

<div>

## <a name="step-1---log-the-timeline"></a><span data-ttu-id="8047c-246">步骤 1-记录日程表</span><span class="sxs-lookup"><span data-stu-id="8047c-246">Step 1 - Log the timeline</span></span>

<span data-ttu-id="8047c-247">记录日程表时，工具用户可以按下图所示指定以下各项。</span><span class="sxs-lookup"><span data-stu-id="8047c-247">Logging the timeline allows the tool user to specify the following as shown in the figure below.</span></span>

1.  <span data-ttu-id="8047c-248">**开始日期**这是要为其生成报告的时间线的开始日期;例如，2010年8月1日。</span><span class="sxs-lookup"><span data-stu-id="8047c-248">**Start date** This is the start date of the timeline that the report is to be generated for; for example, August 1, 2010.</span></span>

2.  <span data-ttu-id="8047c-249">**结束日期**这是要为其生成报告的时间线的结束日期;例如，2010年9月30日。</span><span class="sxs-lookup"><span data-stu-id="8047c-249">**End date** This is the end date of the timeline that the report is to be generated for; for example, September 30, 2010.</span></span>
    
    <span data-ttu-id="8047c-250">![带宽利用率中的开始和结束日期](images/JJ945604.2c597cfc-3372-4d41-816b-26202f607ad8(OCS.15).jpg "带宽利用率中的开始和结束日期")</span><span class="sxs-lookup"><span data-stu-id="8047c-250">![Start and End dates in the Bandwidth Utilization A](images/JJ945604.2c597cfc-3372-4d41-816b-26202f607ad8(OCS.15).jpg "Start and End dates in the Bandwidth Utilization A")</span></span>  

</div>

<div>

## <a name="step-2---specify-the-file-directories"></a><span data-ttu-id="8047c-251">步骤 2-指定文件目录</span><span class="sxs-lookup"><span data-stu-id="8047c-251">Step 2 - Specify the file directories</span></span>

<span data-ttu-id="8047c-252">用户可以按如下所示指定文件目录。</span><span class="sxs-lookup"><span data-stu-id="8047c-252">The following file directories can be specified by the user as shown.</span></span>

  - <span data-ttu-id="8047c-253">**服务器日志文件位置**存储带宽策略服务器日志的文件夹位置。</span><span class="sxs-lookup"><span data-stu-id="8047c-253">**Server log files location** The folder location where Bandwidth policy server logs are stored.</span></span> <span data-ttu-id="8047c-254">这通常是在\<\\AppServerFiles\>\\\<\>\\PDP 的登录选择中。</span><span class="sxs-lookup"><span data-stu-id="8047c-254">This is typically in \<fileserver\>\\\<choice of FE\>\\AppServerFiles\\PDP.</span></span>

  - <span data-ttu-id="8047c-255">**临时文件存储位置**生成报告时存储中间文件的临时文件位置。</span><span class="sxs-lookup"><span data-stu-id="8047c-255">**Temporary file storage location** The temporary file location where intermediate files are stored while the report is being generated.</span></span>

<span data-ttu-id="8047c-256">![带宽利用率用量中的文件目录](images/JJ945604.d66daeac-1669-45e3-932d-3f6782840c2a(OCS.15).jpg "带宽利用率用量中的文件目录")</span><span class="sxs-lookup"><span data-stu-id="8047c-256">![File directories in the Bandwidth Utilization Anal](images/JJ945604.d66daeac-1669-45e3-932d-3f6782840c2a(OCS.15).jpg "File directories in the Bandwidth Utilization Anal")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8047c-257">确保向工具用户提供了对服务器日志和临时文件存储文件夹的足够文件访问权限。</span><span class="sxs-lookup"><span data-stu-id="8047c-257">Ensure that sufficient file access to the server logs and the temporary file store folder is provided to the tool user.</span></span>



</div>

</div>

<div>

## <a name="step-3---collect-the-logs-and-start-the-report-viewer"></a><span data-ttu-id="8047c-258">步骤 3-收集日志并启动报告查看器</span><span class="sxs-lookup"><span data-stu-id="8047c-258">Step 3 - Collect the logs and start the report viewer</span></span>

<span data-ttu-id="8047c-259">若要收集日志并启动报告查看器，请单击 "**执行**"，如下所示。</span><span class="sxs-lookup"><span data-stu-id="8047c-259">To collect the logs and start the report viewer, click **Execute** as shown below.</span></span> <span data-ttu-id="8047c-260">此步骤将收集所需的数据。</span><span class="sxs-lookup"><span data-stu-id="8047c-260">This step collects the required data.</span></span>

<span data-ttu-id="8047c-261">![在带宽利用率用量中收集数据](images/JJ945604.0019cb2c-7c01-4dc9-ac90-ac47c47d1bfd(OCS.15).jpg "在带宽利用率用量中收集数据")</span><span class="sxs-lookup"><span data-stu-id="8047c-261">![Collecting data in the Bandwidth Utilization Analy](images/JJ945604.0019cb2c-7c01-4dc9-ac90-ac47c47d1bfd(OCS.15).jpg "Collecting data in the Bandwidth Utilization Analy")</span></span>

<span data-ttu-id="8047c-262">输入验证成功后，将显示下面显示的消息。</span><span class="sxs-lookup"><span data-stu-id="8047c-262">When the input validation is successful, the message shown below is displayed.</span></span>

<span data-ttu-id="8047c-263">![在带宽 Utili 中记录收集的通知](images/JJ945604.eda91da8-3285-4eab-8ccb-c6d89c8cc221(OCS.15).jpg "在带宽 Utili 中记录收集的通知")</span><span class="sxs-lookup"><span data-stu-id="8047c-263">![Logs collected notification in the Bandwidth Utili](images/JJ945604.eda91da8-3285-4eab-8ccb-c6d89c8cc221(OCS.15).jpg "Logs collected notification in the Bandwidth Utili")</span></span>

<span data-ttu-id="8047c-264">单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="8047c-264">Click **OK**.</span></span> <span data-ttu-id="8047c-265">Bandwidthutilizationanalyzer.xlsm 将自动启动。</span><span class="sxs-lookup"><span data-stu-id="8047c-265">BandwidthUtilizationAnalyzer.xlsm is automatically started.</span></span> <span data-ttu-id="8047c-266">按照消息框中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="8047c-266">Follow the instructions in the message box.</span></span> <span data-ttu-id="8047c-267">有关详细信息，请参阅下一节中的**Using bandwidthutilizationanalyzer.xlsm. xlsm** 。</span><span class="sxs-lookup"><span data-stu-id="8047c-267">For details, see **Using BandwidthUtilizationAnalyzer.xlsm** in the next section.</span></span>

</div>

<div>


<span data-ttu-id="8047c-268">**使用 Bandwidthutilizationanalyzer.xlsm。 xlsm**</span><span class="sxs-lookup"><span data-stu-id="8047c-268">**Using BandwidthUtilizationAnalyzer.xlsm**</span></span>

1.  <span data-ttu-id="8047c-269">如果 xlsm 自动启动，请单击 "**刷新**"，如下所示。</span><span class="sxs-lookup"><span data-stu-id="8047c-269">When BandwidthUtilizationAnalyzer.xlsm is automatically started, click **Refresh** as shown below.</span></span>
    
    <span data-ttu-id="8047c-270">![Bandwidthutilizationanalyzer.xlsm。 xlsm](images/JJ945604.c4e675b9-1671-400e-a712-6db82d731b39(OCS.15).jpg "Bandwidthutilizationanalyzer.xlsm。 xlsm")</span><span class="sxs-lookup"><span data-stu-id="8047c-270">![BandwidthUtilizationAnalyzer.xlsm](images/JJ945604.c4e675b9-1671-400e-a712-6db82d731b39(OCS.15).jpg "BandwidthUtilizationAnalyzer.xlsm")</span></span>

2.  <span data-ttu-id="8047c-271">打开文件文件夹后，从消息框中指定的位置选择 "合并" .csv，如下所示。</span><span class="sxs-lookup"><span data-stu-id="8047c-271">When a file folder is opened, select consolidated.csv from the location that is specified in the message box as shown below.</span></span> <span data-ttu-id="8047c-272">它还将位置显示为**C：\\Temp**。</span><span class="sxs-lookup"><span data-stu-id="8047c-272">It also shows the location as **C:\\Temp**.</span></span>
    
    <span data-ttu-id="8047c-273">![打开 Bandwidthutilizationanalyzer.xlsm 中的文件夹。](images/JJ945604.601cc572-cee9-45fb-9ed1-c4b96a2fa21e(OCS.15).jpg "打开 Bandwidthutilizationanalyzer.xlsm 中的文件夹。")</span><span class="sxs-lookup"><span data-stu-id="8047c-273">![Opening a folder in BandwidthUtilizationAnalyzer.](images/JJ945604.601cc572-cee9-45fb-9ed1-c4b96a2fa21e(OCS.15).jpg "Opening a folder in BandwidthUtilizationAnalyzer.")</span></span>

3.  <span data-ttu-id="8047c-274">单击“导入”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8047c-274">Click **Import**.</span></span>

4.  <span data-ttu-id="8047c-275">图形绘图将自动生成。</span><span class="sxs-lookup"><span data-stu-id="8047c-275">The graphical plot is automatically generated.</span></span> <span data-ttu-id="8047c-276">它在后台工作指针消失时可用。</span><span class="sxs-lookup"><span data-stu-id="8047c-276">It is available when the working-in-the-background pointer disappears.</span></span>
    
    <span data-ttu-id="8047c-277">![在报告视图中应用筛选器。](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "在报告视图中应用筛选器。")</span><span class="sxs-lookup"><span data-stu-id="8047c-277">![Applying filters in Report View.](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "Applying filters in Report View.")</span></span>

</div>

<div>

## <a name="applying-filters-to-the-report-view"></a><span data-ttu-id="8047c-278">将筛选器应用于报告视图</span><span class="sxs-lookup"><span data-stu-id="8047c-278">Applying Filters to the Report View</span></span>

<span data-ttu-id="8047c-279">可应用于报告视图的筛选器如下所示：</span><span class="sxs-lookup"><span data-stu-id="8047c-279">The filters that can be applied to the report view as shown below are described as follows:</span></span>

<span data-ttu-id="8047c-280">![在报告视图中应用筛选器。](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "在报告视图中应用筛选器。")</span><span class="sxs-lookup"><span data-stu-id="8047c-280">![Applying filters in Report View.](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "Applying filters in Report View.")</span></span>

1.  <span data-ttu-id="8047c-281">**名称**按 WAN 链接筛选（筛选器位于图形右侧）。前缀表示以下链接类型;请参阅垂直（蓝色）框：</span><span class="sxs-lookup"><span data-stu-id="8047c-281">**Name** Filter by WAN links (the filter is on the right side of the graph).The prefix denotes the following link types; see the vertical (blue) box:</span></span>
    
      - <span data-ttu-id="8047c-282">**S 网站**从网络站点到网络区域的 WAN 链接</span><span class="sxs-lookup"><span data-stu-id="8047c-282">**S Site** The WAN link from a network site to a network region</span></span>
    
      - <span data-ttu-id="8047c-283">**是站点间**两个网络站点之间的 WAN 链路</span><span class="sxs-lookup"><span data-stu-id="8047c-283">**IS Inter-Site** The WAN link between two network sites</span></span>
    
      - <span data-ttu-id="8047c-284">**R 区域间**两个网络区域之间的 WAN 链路</span><span class="sxs-lookup"><span data-stu-id="8047c-284">**R Inter-Region** The WAN link between two network region</span></span>

2.  <span data-ttu-id="8047c-285">**超出限制**按带宽利用率大于带宽容量的 WAN 链路进行筛选</span><span class="sxs-lookup"><span data-stu-id="8047c-285">**Exceeded limit** Filter by WAN links whose bandwidth utilization is more than the bandwidth capacity</span></span>

3.  <span data-ttu-id="8047c-286">**关键级别**按带宽利用率达到90% 或大于带宽容量的 WAN 链路进行筛选</span><span class="sxs-lookup"><span data-stu-id="8047c-286">**Critical levels** Filter by WAN links whose bandwidth utilization has reached 90% or more than the bandwidth capacity</span></span>

4.  <span data-ttu-id="8047c-287">未**充分利用**按 WAN 链路进行筛选，其带宽使用率已少于带宽容量的25%</span><span class="sxs-lookup"><span data-stu-id="8047c-287">**Under-utilized** Filter by WAN links whose bandwidth utilization has been less than 25% of the bandwidth capacity</span></span>

5.  <span data-ttu-id="8047c-288">**链接类型**按以下 WAN 链接类型进行筛选：</span><span class="sxs-lookup"><span data-stu-id="8047c-288">**Link type** Filter by the following WAN links types:</span></span>
    
      - <span data-ttu-id="8047c-289">**网络站点**类型</span><span class="sxs-lookup"><span data-stu-id="8047c-289">**Network site** type</span></span>
    
      - <span data-ttu-id="8047c-290">**站点间**类型</span><span class="sxs-lookup"><span data-stu-id="8047c-290">**Inter-site** type</span></span>
    
      - <span data-ttu-id="8047c-291">**区域间链接**类型</span><span class="sxs-lookup"><span data-stu-id="8047c-291">**Inter-Region link** type</span></span>

6.  <span data-ttu-id="8047c-292">**区域**按网络区域筛选</span><span class="sxs-lookup"><span data-stu-id="8047c-292">**Region** Filter by network region</span></span>

<span data-ttu-id="8047c-293">下图显示了前面介绍的筛选器。</span><span class="sxs-lookup"><span data-stu-id="8047c-293">The following figures show the previously described filters.</span></span>

<span data-ttu-id="8047c-294">按**名称**筛选。</span><span class="sxs-lookup"><span data-stu-id="8047c-294">Filter by **Name**.</span></span> <span data-ttu-id="8047c-295">选择需要在图形中显示的链接的列表。</span><span class="sxs-lookup"><span data-stu-id="8047c-295">Select the list of links that need to be displayed in the graph.</span></span>

<span data-ttu-id="8047c-296">![按名称在 Bandwidthutilizationanalyzer.xlsm 中进行筛选。](images/JJ945604.002b7c8e-f0da-48ce-9e1a-5c34d2cab063(OCS.15).jpg "按名称在 Bandwidthutilizationanalyzer.xlsm 中进行筛选。")</span><span class="sxs-lookup"><span data-stu-id="8047c-296">![Filtering by Name in BandwidthUtilizationAnalyzer.](images/JJ945604.002b7c8e-f0da-48ce-9e1a-5c34d2cab063(OCS.15).jpg "Filtering by Name in BandwidthUtilizationAnalyzer.")</span></span>

<span data-ttu-id="8047c-297">按**超出限制**进行筛选。</span><span class="sxs-lookup"><span data-stu-id="8047c-297">Filter by **Exceeded limit**.</span></span> <span data-ttu-id="8047c-298">选择 " **True** " 以强制执行筛选器。</span><span class="sxs-lookup"><span data-stu-id="8047c-298">Select **True** to enforce the filter.</span></span>

<span data-ttu-id="8047c-299">![按超出限制进行筛选。](images/JJ945604.5946c95e-76ce-46ca-8f3e-a79be1e5c527(OCS.15).jpg "按超出限制进行筛选。")</span><span class="sxs-lookup"><span data-stu-id="8047c-299">![Filtering by Exceeded Limit.](images/JJ945604.5946c95e-76ce-46ca-8f3e-a79be1e5c527(OCS.15).jpg "Filtering by Exceeded Limit.")</span></span>

<span data-ttu-id="8047c-300">按**临界级别**进行筛选。</span><span class="sxs-lookup"><span data-stu-id="8047c-300">Filter by **Critical levels**.</span></span> <span data-ttu-id="8047c-301">选择 " **True** " 以强制执行筛选器。</span><span class="sxs-lookup"><span data-stu-id="8047c-301">Select **True** to enforce the filter.</span></span>

<span data-ttu-id="8047c-302">![按关键级别进行筛选。](images/JJ945604.60771a52-d8ba-4cb9-a02d-d6c888cb5505(OCS.15).jpg "按关键级别进行筛选。")</span><span class="sxs-lookup"><span data-stu-id="8047c-302">![Filtering by Critical Levels.](images/JJ945604.60771a52-d8ba-4cb9-a02d-d6c888cb5505(OCS.15).jpg "Filtering by Critical Levels.")</span></span>

<span data-ttu-id="8047c-303">按**使用**情况筛选。</span><span class="sxs-lookup"><span data-stu-id="8047c-303">Filter by **Under utilized**.</span></span> <span data-ttu-id="8047c-304">选择 " **True** " 以强制执行筛选器。</span><span class="sxs-lookup"><span data-stu-id="8047c-304">Select **True** to enforce the filter.</span></span>

<span data-ttu-id="8047c-305">![按使用情况进行筛选。](images/JJ945604.95a2bf01-5aba-4927-af47-1ad3c459d791(OCS.15).jpg "按使用情况进行筛选。")</span><span class="sxs-lookup"><span data-stu-id="8047c-305">![Filtering by Under Utilized.](images/JJ945604.95a2bf01-5aba-4927-af47-1ad3c459d791(OCS.15).jpg "Filtering by Under Utilized.")</span></span>

<span data-ttu-id="8047c-306">按**链接类型**筛选。</span><span class="sxs-lookup"><span data-stu-id="8047c-306">Filter by **Link Type**.</span></span> <span data-ttu-id="8047c-307">选择需要显示的一个或一种类型。</span><span class="sxs-lookup"><span data-stu-id="8047c-307">Select the type or types that need to be displayed.</span></span>

<span data-ttu-id="8047c-308">![按链接类型筛选。](images/JJ945604.08757949-06bd-4cf3-809f-d81fd23a6639(OCS.15).jpg "按链接类型筛选。")</span><span class="sxs-lookup"><span data-stu-id="8047c-308">![Filtering by Link Type.](images/JJ945604.08757949-06bd-4cf3-809f-d81fd23a6639(OCS.15).jpg "Filtering by Link Type.")</span></span>

<span data-ttu-id="8047c-309">按**区域**筛选。</span><span class="sxs-lookup"><span data-stu-id="8047c-309">Filter by **Region**.</span></span> <span data-ttu-id="8047c-310">选择需要显示其链接的区域列表。</span><span class="sxs-lookup"><span data-stu-id="8047c-310">Select a list of regions whose links need to be displayed.</span></span>

<span data-ttu-id="8047c-311">![按区域筛选。](images/JJ945604.5de4cec4-6c09-48bb-98c7-b56f7bdb3d5a(OCS.15).jpg "按区域筛选。")</span><span class="sxs-lookup"><span data-stu-id="8047c-311">![Filtering by Region.](images/JJ945604.5de4cec4-6c09-48bb-98c7-b56f7bdb3d5a(OCS.15).jpg "Filtering by Region.")</span></span>

</div>

</div>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="8047c-312">Requirements</span><span class="sxs-lookup"><span data-stu-id="8047c-312">Requirements</span></span>

  - <span data-ttu-id="8047c-313">.NET Framework 3。5</span><span class="sxs-lookup"><span data-stu-id="8047c-313">The .NET Framework 3.5</span></span>

  - <span data-ttu-id="8047c-314">Microsoft Excel 2010 或 Excel 2007</span><span class="sxs-lookup"><span data-stu-id="8047c-314">Microsoft Excel 2010 or Excel 2007</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="8047c-315">总结</span><span class="sxs-lookup"><span data-stu-id="8047c-315">Summary</span></span>

<span data-ttu-id="8047c-316">带宽利用率分析器用于绘制网络中 UC 流量的音频带宽使用率。</span><span class="sxs-lookup"><span data-stu-id="8047c-316">Bandwidth Utilization Analyzer is used to plot the audio bandwidth utilization for UC traffic across the network.</span></span> <span data-ttu-id="8047c-317">此工具还可用于报告网络上的视频带宽使用率。</span><span class="sxs-lookup"><span data-stu-id="8047c-317">This tool can be used to report the utilization of video bandwidth on the network as well.</span></span>

</div>

</div>

<div>

## <a name="call-parkometer"></a><span data-ttu-id="8047c-318">调用寄存时间记录器</span><span class="sxs-lookup"><span data-stu-id="8047c-318">Call Parkometer</span></span>

<span data-ttu-id="8047c-319">调用寄存时间记录器是一个命令行应用程序，可提供对呼叫寄存轨道数据库的轻松访问。</span><span class="sxs-lookup"><span data-stu-id="8047c-319">Call Parkometer is a command-line application that provides easy access to the Call Park orbit database.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="8047c-320">说明</span><span class="sxs-lookup"><span data-stu-id="8047c-320">Description</span></span>

<span data-ttu-id="8047c-321">呼叫寄存时间记录器是一种跟踪当前寄存的呼叫的工具。</span><span class="sxs-lookup"><span data-stu-id="8047c-321">Call Parkometer is a tool to track currently parked calls.</span></span> <span data-ttu-id="8047c-322">它还收集有关轨道式和呼叫寄存服务器（CPS）使用情况的统计信息。</span><span class="sxs-lookup"><span data-stu-id="8047c-322">It also collects statistics about orbits and Call Park Server (CPS) usage.</span></span> <span data-ttu-id="8047c-323">此命令行工具提供对来自本地或远程连接的计算机上的 CPS 轨道 SQL Server 数据库的读写访问权限。</span><span class="sxs-lookup"><span data-stu-id="8047c-323">This command-line tool provides both read and write-access to the CPS orbit SQL Server database from a local or remotely connected computer.</span></span>

<span data-ttu-id="8047c-324">所有选项都是相互排斥的。</span><span class="sxs-lookup"><span data-stu-id="8047c-324">All options are mutually exclusive.</span></span> <span data-ttu-id="8047c-325">命令行语法如下所示：</span><span class="sxs-lookup"><span data-stu-id="8047c-325">Command-line syntax is as follows:</span></span>

  - <span data-ttu-id="8047c-326">**– o**参数-列出为此池配置的所有轨道范围。</span><span class="sxs-lookup"><span data-stu-id="8047c-326">**–o** parameter—lists all orbit ranges configured for this pool.</span></span>

  - <span data-ttu-id="8047c-327">**– n**参数—列出此池中当前使用的所有轨道。</span><span class="sxs-lookup"><span data-stu-id="8047c-327">**–n** parameter—lists all currently used orbits in this pool.</span></span> <span data-ttu-id="8047c-328">显示的信息如下所示：</span><span class="sxs-lookup"><span data-stu-id="8047c-328">The information displayed is as follows:</span></span>
    
      - <span data-ttu-id="8047c-329">Parkee 和 parker 的 SIP 统一资源标识符（URI）。</span><span class="sxs-lookup"><span data-stu-id="8047c-329">SIP Uniform Resource Identifier (URI) of the parkee and parker.</span></span>
    
      - <span data-ttu-id="8047c-330">寄存呼叫的 CPS 的主机名。</span><span class="sxs-lookup"><span data-stu-id="8047c-330">Host name of the CPS where the call is parked.</span></span>
    
      - <span data-ttu-id="8047c-331">寄存呼叫时的时间戳。</span><span class="sxs-lookup"><span data-stu-id="8047c-331">Time stamp of when the call was parked.</span></span>

  - <span data-ttu-id="8047c-332">**– f**参数-列出池中当前可用的轨道的数目。</span><span class="sxs-lookup"><span data-stu-id="8047c-332">**–f** parameter—lists the number of currently free orbits in the pool.</span></span>

  - <span data-ttu-id="8047c-333">\*\*– r \<n\> \*\*参数—列出\<n\>个最近寄存的呼叫。</span><span class="sxs-lookup"><span data-stu-id="8047c-333">**–r \<n\>** parameter—lists the \<n\> last parked calls.</span></span> <span data-ttu-id="8047c-334">显示的信息如下所示：</span><span class="sxs-lookup"><span data-stu-id="8047c-334">The information displayed is as follows:</span></span>
    
      - <span data-ttu-id="8047c-335">Parkee SIP URI。</span><span class="sxs-lookup"><span data-stu-id="8047c-335">Parkee SIP URI.</span></span>
    
      - <span data-ttu-id="8047c-336">Parker SIP URI。</span><span class="sxs-lookup"><span data-stu-id="8047c-336">Parker SIP URI.</span></span>
    
      - <span data-ttu-id="8047c-337">寄存呼叫的 CPS 的主机名。</span><span class="sxs-lookup"><span data-stu-id="8047c-337">Host name of the CPS where the call was parked.</span></span>
    
      - <span data-ttu-id="8047c-338">检索或丢弃呼叫时的时间戳。</span><span class="sxs-lookup"><span data-stu-id="8047c-338">Time stamp of when the call was retrieved or dropped.</span></span>

  - <span data-ttu-id="8047c-339">\*\*-t\<n\> \*\*参数-测试在数据库中保留一种轨道，以显示分配的轨道编号的随机性。</span><span class="sxs-lookup"><span data-stu-id="8047c-339">**-t\<n\>** parameter - tests reserving an orbit in the database to show the randomness of the assigned orbit numbers.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="8047c-340">Output</span><span class="sxs-lookup"><span data-stu-id="8047c-340">Output</span></span>

<span data-ttu-id="8047c-341">根据在命令提示符处指定的输入参数，调用寄存时间记录器显示以下输出：</span><span class="sxs-lookup"><span data-stu-id="8047c-341">Depending on the input parameters that are specified at a command prompt, Call Parkometer displays the following output:</span></span>

  - <span data-ttu-id="8047c-342">为此池配置的所有轨道范围</span><span class="sxs-lookup"><span data-stu-id="8047c-342">All orbit ranges that are configured for this pool</span></span>

  - <span data-ttu-id="8047c-343">当前寄存的呼叫</span><span class="sxs-lookup"><span data-stu-id="8047c-343">Currently parked calls</span></span>

  - <span data-ttu-id="8047c-344">空闲（可用）轨道式的数目</span><span class="sxs-lookup"><span data-stu-id="8047c-344">Number of free (available) orbits</span></span>

  - <span data-ttu-id="8047c-345">最近寄存的呼叫</span><span class="sxs-lookup"><span data-stu-id="8047c-345">Recently parked calls</span></span>

  - <span data-ttu-id="8047c-346">用于测试统一和随机轨道值的保留轨道</span><span class="sxs-lookup"><span data-stu-id="8047c-346">Reserved orbits for testing uniform and random orbit values</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="8047c-347">用途</span><span class="sxs-lookup"><span data-stu-id="8047c-347">Purpose</span></span>

<span data-ttu-id="8047c-348">CPS 工具的目的是提供对 CPS 数据库的命令行访问。</span><span class="sxs-lookup"><span data-stu-id="8047c-348">The purpose of the CPS tool is to provide command-line access to the CPS database.</span></span> <span data-ttu-id="8047c-349">管理员可以查看 CPS 使用情况，并确定分配给池的轨道式的数目。</span><span class="sxs-lookup"><span data-stu-id="8047c-349">The administrator can view the CPS usage and determine the number of orbits assigned to a pool.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="8047c-350">Requirements</span><span class="sxs-lookup"><span data-stu-id="8047c-350">Requirements</span></span>

<span data-ttu-id="8047c-351">如果在运行 CPS 的同一台计算机上运行此工具，则没有任何要求。</span><span class="sxs-lookup"><span data-stu-id="8047c-351">There are no requirements if this tool is run on the same computer that is running CPS.</span></span> <span data-ttu-id="8047c-352">如果此工具在远程计算机上运行，则必须将 Lync Server 2013 使用的 SQL Server 数据库配置为允许远程访问。</span><span class="sxs-lookup"><span data-stu-id="8047c-352">If this tool is run on a remote computer, the SQL Server database used by Lync Server 2013 must be configured to allow remote access.</span></span> <span data-ttu-id="8047c-353">必须使用 SQL Server 数据库连接字符串配置调用寄存时间记录器以连接到池的 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="8047c-353">Call Parkometer must be configured with a SQL Server database connection string to connect to the pool’s SQL Server.</span></span> <span data-ttu-id="8047c-354">此 SQL Server 数据库连接字符串是在配置文件**寄存时间记录器**中定义的。它必须放在寄存时间记录器所在的同一目录中。</span><span class="sxs-lookup"><span data-stu-id="8047c-354">This SQL Server database connection string is defined in the configuration file, **parkometer.exe.config**. It must be placed in the same directory where parkometer.exe is located.</span></span> <span data-ttu-id="8047c-355">下面的 XML 文件是一个寄存时间记录器的示例。必须配置的参数为用户名（例如，mydomain\\管理员）、密码（例如，mypassword）以及主机名称（例如，myserver）。</span><span class="sxs-lookup"><span data-stu-id="8047c-355">The following XML file is an example of a parkometer.exe.config. The parameters that must be configured are user name (for example, mydomain\\Administrator), password (for example, mypassword), and host name (for example, myserver).</span></span>

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

</div>

<div>

## <a name="examples"></a><span data-ttu-id="8047c-356">示例</span><span class="sxs-lookup"><span data-stu-id="8047c-356">Examples</span></span>

<span data-ttu-id="8047c-357">已部署的轨道范围：– o 参数列出为此池配置的所有轨道范围，如图所示</span><span class="sxs-lookup"><span data-stu-id="8047c-357">Deployed orbit ranges: the –o parameter lists all orbit ranges that are configured for this pool as shown</span></span>

<span data-ttu-id="8047c-358">![呼叫寄存时间记录器中的轨道范围。](images/JJ945604.9ede64cb-29d9-4782-a34b-b76c42fbdcad(OCS.15).jpg "呼叫寄存时间记录器中的轨道范围。")</span><span class="sxs-lookup"><span data-stu-id="8047c-358">![Orbit ranges in Call Parkometer.](images/JJ945604.9ede64cb-29d9-4782-a34b-b76c42fbdcad(OCS.15).jpg "Orbit ranges in Call Parkometer.")</span></span>

<span data-ttu-id="8047c-359">当前寄存的呼叫：– n 参数列出此池中当前使用的所有轨道，如下所示</span><span class="sxs-lookup"><span data-stu-id="8047c-359">Currently parked calls: the –n parameter lists all currently used orbits on this pool as shown</span></span>

<span data-ttu-id="8047c-360">![呼叫寄存时间记录器中当前寄存的呼叫。](images/JJ945604.07a7eec4-7999-4c92-93f0-95525b244b4c(OCS.15).jpg "呼叫寄存时间记录器中当前寄存的呼叫。")</span><span class="sxs-lookup"><span data-stu-id="8047c-360">![Currently-parked calls in Call Parkometer.](images/JJ945604.07a7eec4-7999-4c92-93f0-95525b244b4c(OCS.15).jpg "Currently-parked calls in Call Parkometer.")</span></span>

<span data-ttu-id="8047c-361">自由轨道式的数目：– f 参数列出了池中当前可用的轨道式的数目，如图所示</span><span class="sxs-lookup"><span data-stu-id="8047c-361">Number of free orbits: the –f parameter lists the number of currently free orbits in the pool as shown</span></span>

<span data-ttu-id="8047c-362">![调用寄存时间记录器中的自由轨道式。](images/JJ945604.ecc1d621-0ca0-4ecf-a579-08b41c6f08ed(OCS.15).jpg "调用寄存时间记录器中的自由轨道式。")</span><span class="sxs-lookup"><span data-stu-id="8047c-362">![Free orbits in Call Parkometer.](images/JJ945604.ecc1d621-0ca0-4ecf-a579-08b41c6f08ed(OCS.15).jpg "Free orbits in Call Parkometer.")</span></span>

<span data-ttu-id="8047c-363">最近寄存的呼叫：– r \<n\>参数列出 n \<\>个最近寄存的呼叫，如下所示</span><span class="sxs-lookup"><span data-stu-id="8047c-363">Recently parked calls: the –r \<n\> parameter lists the \<n\> last parked calls as shown</span></span>

<span data-ttu-id="8047c-364">![呼叫寄存时间记录器中最近寄存的呼叫。](images/JJ945604.1c5eb27d-faa1-491b-b4aa-b484255c3353(OCS.15).jpg "呼叫寄存时间记录器中最近寄存的呼叫。")</span><span class="sxs-lookup"><span data-stu-id="8047c-364">![Recently-parked calls in Call Parkometer.](images/JJ945604.1c5eb27d-faa1-491b-b4aa-b484255c3353(OCS.15).jpg "Recently-parked calls in Call Parkometer.")</span></span>

<span data-ttu-id="8047c-365">测试轨道保留：– t \<n\>参数测试在数据库中保留一个轨道，如下所示</span><span class="sxs-lookup"><span data-stu-id="8047c-365">Test orbit reservation: the –t \<n\> parameter tests reserving an orbit in the database as shown</span></span>

<span data-ttu-id="8047c-366">![在呼叫寄存时间记录器中测试轨道保留。](images/JJ945604.84c9b69e-7af0-4224-8711-a43a28f08691(OCS.15).jpg "在呼叫寄存时间记录器中测试轨道保留。")</span><span class="sxs-lookup"><span data-stu-id="8047c-366">![Test orbit reservations in Call Parkometer.](images/JJ945604.84c9b69e-7af0-4224-8711-a43a28f08691(OCS.15).jpg "Test orbit reservations in Call Parkometer.")</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="8047c-367">总结</span><span class="sxs-lookup"><span data-stu-id="8047c-367">Summary</span></span>

<span data-ttu-id="8047c-368">呼叫寄存时间记录器是一个命令行工具，提供有关呼叫寄存服务器的详细信息。</span><span class="sxs-lookup"><span data-stu-id="8047c-368">Call Parkometer is a command-line tool that provides detailed information about the Call Park Server.</span></span>

</div>

</div>

<div>

## <a name="cleanupstorageservicedata"></a><span data-ttu-id="8047c-369">CleanupStorageServiceData</span><span class="sxs-lookup"><span data-stu-id="8047c-369">CleanupStorageServiceData</span></span>

<span data-ttu-id="8047c-370">CleanupStorageServiceData 资源工具包工具允许从 Lync Server Storage Service （LYSS）使用的数据库中删除孤立的数据。</span><span class="sxs-lookup"><span data-stu-id="8047c-370">The CleanupStorageServiceData resource kit tool allows for deleting of orphaned data from the database used by the Lync Server Storage Service (LYSS).</span></span> <span data-ttu-id="8047c-371">存储服务的一个功能是在 Lync Server 和不同的后端数据存储终结点（如 SQL Server 和 Exchange）之间缓冲通信。</span><span class="sxs-lookup"><span data-stu-id="8047c-371">One function of the storage service is to buffer communication between Lync Server and various back-end data storage endpoints, like SQL Server and Exchange.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="8047c-372">说明</span><span class="sxs-lookup"><span data-stu-id="8047c-372">Description</span></span>

<span data-ttu-id="8047c-373">为了支持高可用性，LYSS 在池中临时接收并保存多个前端服务器上的数据副本，并在将数据传递到其最终长期存储位置后将其删除。</span><span class="sxs-lookup"><span data-stu-id="8047c-373">To support high availability, LYSS accepts and saves copies of the data on multiple front end servers in the pool temporarily, and removes that data once it has been delivered to its final long-term storage location.</span></span> <span data-ttu-id="8047c-374">在某些情况下，如果服务器可能崩溃或遇到处理问题，并且某些数据可能无法正确清理，则在其他正常操作过程中可能会发生异常情况。</span><span class="sxs-lookup"><span data-stu-id="8047c-374">There are unusual situations which may occur during otherwise normal operation, when a server might crash or experience a processing issue, and some data might not get cleaned up properly.</span></span> <span data-ttu-id="8047c-375">此数据是无害的，但它会占用有限的处理资源。</span><span class="sxs-lookup"><span data-stu-id="8047c-375">This data is harmless, but it does consume limited processing resources.</span></span> <span data-ttu-id="8047c-376">大部分正常的必要数据维护都是自动进行的，但是此工具允许在无法进行自动删除时对此类孤立数据进行安全标识和删除。</span><span class="sxs-lookup"><span data-stu-id="8047c-376">Much of the normal required data maintenance is automated, but this tool allows for the safe identification and removal of such orphaned data when automated removal is not possible.</span></span> <span data-ttu-id="8047c-377">当出现运行状况监视 System Center Operations Manager （SCOM）警报时，将提示管理员从池中的本地 LYSS 数据库中删除不需要的数据时，将显示此工具的使用情况。</span><span class="sxs-lookup"><span data-stu-id="8047c-377">Usage of this tool is indicated when a health monitoring System Center Operations Manager (SCOM) alert is raised which asks the administrator to remove the unneeded data from the local LYSS databases in the pool.</span></span> <span data-ttu-id="8047c-378">在触发警报的前端上的事件日志中将会有相应的事件。</span><span class="sxs-lookup"><span data-stu-id="8047c-378">There will be a corresponding event in the event log on the front end which triggered the alert.</span></span> <span data-ttu-id="8047c-379">事件详细信息将包含前端上包含的孤立数据量的相关信息，并在该数据超过某些预确定阈值时引发。</span><span class="sxs-lookup"><span data-stu-id="8047c-379">The event details will contain information about the amount of orphaned data contained on the front end, and is raised when that data exceeds certain pre-determine thresholds</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="8047c-380">Requirements</span><span class="sxs-lookup"><span data-stu-id="8047c-380">Requirements</span></span>

<span data-ttu-id="8047c-381">安装 Lync Server 2013 （资源工具包工具）。</span><span class="sxs-lookup"><span data-stu-id="8047c-381">Install the Lync Server 2013, Resource Kit Tools.</span></span> <span data-ttu-id="8047c-382">该工具在安装了 Lync Server 和 Lync Server 2013 命令行管理程序的加入域的计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="8047c-382">The tool runs on domain-joined machines where Lync Server and Lync Server 2013 Management Shell are installed.</span></span> <span data-ttu-id="8047c-383">该工具使用命令行管理程序中的 cmdlet 来标识池中的所有前端服务器。</span><span class="sxs-lookup"><span data-stu-id="8047c-383">The tool uses a cmdlet from the management shell to identify all Front End servers in the pool.</span></span> <span data-ttu-id="8047c-384">其次，该工具必须从安装了**RtcLocal**数据库的池中的计算机执行。</span><span class="sxs-lookup"><span data-stu-id="8047c-384">Secondly, the tool must be executed from a machine in the pool which has the **RtcLocal** database installed.</span></span> <span data-ttu-id="8047c-385">CleanupStorageServiceData 工具使用此数据库来获取与 Lync Server 路由服务通信所需的连接详细信息。最后，调用该工具的帐户或凭据必须具有对要向其写入输出日志的文件共享的读/写权限。此外，此工具依赖于池处于稳定状态。</span><span class="sxs-lookup"><span data-stu-id="8047c-385">This database is used by the CleanupStorageServiceData tool to get the connection details needed to communicate with the Lync Server Routing Service.Finally, the account or credential invoking the tool must have read/write permission to the file share to which they want to write the output log.Also, this tool depends on the pool being in a stable state.</span></span> <span data-ttu-id="8047c-386">实际上，这意味着每台前端服务器都应正常运行，SQL Server LYNCLOCAL 实例和 LYSS 数据库必须能够连接到，并且每个路由组必须具有一套完整的1个主前端服务器和2个辅助前端 servers.</span><span class="sxs-lookup"><span data-stu-id="8047c-386">In essence this means that every Front End server is expected to be up and running, the SQL Server LYNCLOCAL instance and LYSS database must be able to be connected to, and each routing group must have a complete set of 1 primary Front End servers and 2 secondary Front End servers.</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="8047c-387">示例</span><span class="sxs-lookup"><span data-stu-id="8047c-387">Examples</span></span>

<span data-ttu-id="8047c-388">C：\\Program Files\\Microsoft Lync Server 2013\\\reskit\\StorageService\> ImportStorageServiceData</span><span class="sxs-lookup"><span data-stu-id="8047c-388">C:\\Program Files\\Microsoft Lync Server 2013\\ResKit\\StorageService\> ImportStorageServiceData.exe</span></span>

    Description:
    This tool will remove orphaned data from the Storage Service database
    for a pool. You are required to run this tool on a machine inside the
    pool which has the Lync Server Management Shell installed and has RtcLocal database installed.
    Usage: Default behavior is to clean up orphaned data from the all the 
           Storage Service databases in the current pool.
    Additional Options:
    -Verbose    : Turn verbose output on.
    -LogPath    : The UNC path to which to write the log.
    ------------------------------------------------------------------------------
    Please wait while we initialize...
    Found 4 front end servers
    Replica Instances for LYSS Service
    Address: server2.vdomain.com - Primaries: 7 Secondaries: 14
    Address: server.vdomain.com - Primaries: 7 Secondaries: 14
    Address: server1.vdomain.com - Primaries: 7 Secondaries: 14
    Address: server3.vdomain.com - Primaries: 7 Secondaries: 14
    Primary Total Count = 28, Secondary Total Count = 56
    Finding and removing orphaned data for 28 routing groups
    Removing 1 stale groups from FE server.vdomain.com
    No stale routing groups detected on FE server2.vdomain.com
    No stale routing groups detected on FE server1.vdomain.com
    No stale routing groups detected on FE server3.vdomain.com
    Searching for stale queue items
    Removed 20 stale queue items for routing group 17D5435AE40259F7BBDF1866776386E4
    No stale queue items found for routing group 1975349662315F90B119DACB4F2AE3AD
    No stale queue items found for routing group 1A23E3D58BDB5A458A0B73F34AB7ACBE
    No stale queue items found for routing group 1AC91E3A1029535A80123121989CEADC
    No stale queue items found for routing group 3313935458E35B9B9759E08A15D251E6
    No stale queue items found for routing group 39BB0035B06B5427873FC6099720462A
    No stale queue items found for routing group 40721948E7B55CE893A53E911F76D185
    No stale queue items found for routing group 4501E04EAE4856059346949FF817C220
    No stale queue items found for routing group 4D833C98801F546F8E45E417EE028E2E
    No stale queue items found for routing group 5AD77443AD955A22A876749BE66D5317
    No stale queue items found for routing group 69844A271E6C5633A1F2B46A42287DD6
    No stale queue items found for routing group 69DA3BE407A95C7284EB4B1337718C93
    No stale queue items found for routing group 8437358AB34A5CC8967D5EF39494AB8D
    No stale queue items found for routing group 8ED455B1789655359816E1C5BF4C430F
    No stale queue items found for routing group 904F6C9B8AC951AE8B3C86684D3832E4
    No stale queue items found for routing group 90AAB3AE9A1950E0ADE7809A27021D63
    No stale queue items found for routing group 944F5724C65C5F93900DC1C8C898B102
    No stale queue items found for routing group 9E8A2630250C51769E39F63F0FB552BA
    No stale queue items found for routing group A11E27AE439A582288D4657EDA86B565
    No stale queue items found for routing group A9B10C76E764556FAEA3E47301EDF518
    No stale queue items found for routing group AEA2699E74ED59848ACEA7896699430D
    No stale queue items found for routing group B269961603E75065AFDA4F4F006DA5E4
    No stale queue items found for routing group BB873D9A3DA959DAB2FD743E5AA619F7
    No stale queue items found for routing group BCC6A48FBA2454B79B9EDB276657A404
    No stale queue items found for routing group C8EF4805722B5F6C876EBC0440B420FD
    No stale queue items found for routing group CA38EBDAC4845489ACE208C2240E4056
    No stale queue items found for routing group F5921887DB025C5F908CE42DB7F1AEE8
    No stale queue items found for routing group F9E606A825395422B3BF7A01ECBB7B1F
    Writing log: M:\Dev\Server\ResKit\StorageService\CleanupStorageServiceData.Log_20121009_151040
    Tool has finished execution.  Errors encountered: 0
    C:\Program Files\Microsoft Lync Server 2013\ResKit\StorageService>

</div>

</div>

<div>

## <a name="dbanalyze"></a><span data-ttu-id="8047c-389">DBAnalyze</span><span class="sxs-lookup"><span data-stu-id="8047c-389">DBAnalyze</span></span>

<div>

## <a name="description"></a><span data-ttu-id="8047c-390">说明</span><span class="sxs-lookup"><span data-stu-id="8047c-390">Description</span></span>

<span data-ttu-id="8047c-391">DBAnalyze 是一个命令行工具，可帮助管理员收集有关 Lync Server 2013 数据库的分析报告。</span><span class="sxs-lookup"><span data-stu-id="8047c-391">DBAnalyze is a command-line tool that helps administrators to gather analysis reports about the Lync Server 2013 databases.</span></span> <span data-ttu-id="8047c-392">DBAnalyze 具有以下模式：诊断、用户数据、会议、Mcu 和磁盘碎片：</span><span class="sxs-lookup"><span data-stu-id="8047c-392">DBAnalyze has the following modes: diagnostic, user data, conference, MCUs, and disk fragmentation:</span></span>

  - <span data-ttu-id="8047c-393">**诊断模式**   创建一个报表，其中包含有关表的信息（记录数、碎片、数据大小和索引大小、数据和日志文件大小、最近的备份时间、在运行 Microsoft Office 通信服务器的服务器之间的联系人分布、平均权限数、联系人、容器、订阅、发布、每个用户的终结点、任何不正确的托管用户、无法路由的用户、计划的平均会议数会议、活动会议和数据库版本。</span><span class="sxs-lookup"><span data-stu-id="8047c-393">**Diagnostic mode**   Creates a report that includes information about tables (number of records, fragmentation, data size, and index size), data and log file sizes, the last back-up time, contact distribution among servers that are running Microsoft Office Communications Server, the average number of permissions, contacts, containers, subscriptions, publications, endpoints per user, any improperly homed users, users that can’t be routed, the average number of conferences organized per user, scheduled conferences, active conferences, and the database version.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8047c-394">运行诊断模式可能会影响服务器性能。</span><span class="sxs-lookup"><span data-stu-id="8047c-394">Running diagnostic mode can affect server performance.</span></span>

    
    </div>

  - <span data-ttu-id="8047c-395">**用户数据模式**  报告指定用户或其联系人和权限列表中具有该用户的用户的联系人、容器、订阅、发布、权限和联系人组数据。</span><span class="sxs-lookup"><span data-stu-id="8047c-395">**User data mode**  Reports contact, container, subscription, publication, permission, and contact-group data for a specified user or for users who have that user in their contact and permission lists.</span></span> <span data-ttu-id="8047c-396">此模式还报告用户组织或受邀的会议的摘要数据。</span><span class="sxs-lookup"><span data-stu-id="8047c-396">This mode also reports summary data for conferences that a user organizes or is invited to.</span></span>

  - <span data-ttu-id="8047c-397">**会议模式**   报告特定会议的详细数据，包括会议的所有计划时间详细信息、被邀请者列表、会议允许的媒体类型列表、活动 mcu （multipoint 控制单位）、活动参与者列表和每个参与者的信号状态。</span><span class="sxs-lookup"><span data-stu-id="8047c-397">**Conference mode**   Reports detailed data for a specific conference, including all schedule-time details for the conference, the invitee list, the list of media types allowed for the conference, active MCUs (multipoint control units), the active participant list, and each participant’s signaling state.</span></span>

  - <span data-ttu-id="8047c-398">**解码会议 id**  解码由 **/pstnid**开关指定的公用电话交换网（PSTN）会议 ID，但不连接到后端以了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="8047c-398">**Decode Meeting ID**  Decodes a public switched telephone network (PSTN) meeting ID that is specified by the **/pstnid** switch but does not connect to the back end for detailed information.</span></span>

  - <span data-ttu-id="8047c-399">**解析会议**   解码由 **/pstnid**开关指定的 PSTN 会议 ID，并显示由 ID 指示的会议的相关信息。</span><span class="sxs-lookup"><span data-stu-id="8047c-399">**Resolve conference**   Decodes a PSTN meeting ID that is specified by the **/pstnid** switch and displays information about the conference indicated by the ID.</span></span>

  - <span data-ttu-id="8047c-400">**Mcu 模式**  报告池中每个 MCU 的 ID、媒体类型、URL、检测信号状态、会议负载和参与者负载。</span><span class="sxs-lookup"><span data-stu-id="8047c-400">**MCUs mode**  Reports the ID, media type, URL, heartbeat status, conference load, and participant load for each MCU in the pool.</span></span>

  - <span data-ttu-id="8047c-401">**磁盘碎片模式**  显示所有磁盘的碎片状态。</span><span class="sxs-lookup"><span data-stu-id="8047c-401">**Disk fragmentation mode**  Displays the fragmentation status of all disks.</span></span>

<span data-ttu-id="8047c-402">此工具可用于诊断各种问题或帮助管理员进行容量规划。</span><span class="sxs-lookup"><span data-stu-id="8047c-402">This tool can be used to diagnose various problems or to assist administrators with capacity planning.</span></span> <span data-ttu-id="8047c-403">例如，如果驻留在服务器上的大多数用户都选择用户驻留在服务器 B 上作为其联系人，则管理员可以将服务器 A 上的用户移动到服务器 B 以减少跨服务器流量。</span><span class="sxs-lookup"><span data-stu-id="8047c-403">For example, if most of the users homed on server A choose users homed on server B as their contacts, the administrator can move the users on server A to server B to reduce cross-server traffic.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="8047c-404">Output</span><span class="sxs-lookup"><span data-stu-id="8047c-404">Output</span></span>

<span data-ttu-id="8047c-405">此工具输出有关 Lync Server 2013 数据库的预定义报告。</span><span class="sxs-lookup"><span data-stu-id="8047c-405">This tool outputs predefined reports about the Lync Server 2013 database.</span></span> <span data-ttu-id="8047c-406">**路径：** % ProgramFiles%\\Microsoft Lync Server 2013\\\reskit</span><span class="sxs-lookup"><span data-stu-id="8047c-406">**Path:** %ProgramFiles%\\Microsoft Lync Server 2013\\Reskit</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="8047c-407">用途</span><span class="sxs-lookup"><span data-stu-id="8047c-407">Purpose</span></span>

<span data-ttu-id="8047c-408">若要安装 Dbanalyze，请将其复制到本地文件夹，然后运行该工具。</span><span class="sxs-lookup"><span data-stu-id="8047c-408">To install Dbanalyze.exe, copy it to a local folder and then run the tool.</span></span> <span data-ttu-id="8047c-409">若要使用此工具，请从命令行运行以下命令。`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]`</span><span class="sxs-lookup"><span data-stu-id="8047c-409">To use the tool, run the following command from the command line.`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]`</span></span> <span data-ttu-id="8047c-410">下面显示了有关命令行选项的说明。</span><span class="sxs-lookup"><span data-stu-id="8047c-410">The descriptions for the command-line options are shown below.</span></span>

<span data-ttu-id="8047c-411">![Dbanalyze 的命令行选项。](images/JJ945604.22bf3432-af6d-495b-8f48-d94c5d259523(OCS.15).jpg "Dbanalyze 的命令行选项。")</span><span class="sxs-lookup"><span data-stu-id="8047c-411">![Command line options for Dbanalyze.exe.](images/JJ945604.22bf3432-af6d-495b-8f48-d94c5d259523(OCS.15).jpg "Command line options for Dbanalyze.exe.")</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="8047c-412">Requirements</span><span class="sxs-lookup"><span data-stu-id="8047c-412">Requirements</span></span>

<span data-ttu-id="8047c-413">**计算机**只能从安装了 Lync Server 2013 的加入域的计算机运行 DBAnalyze。</span><span class="sxs-lookup"><span data-stu-id="8047c-413">**Computer** DBAnalyze can be run only from a domain-joined computer that has Lync Server 2013 installed.</span></span>

<span data-ttu-id="8047c-414">**网络**计算机应能够连接到后端数据库。</span><span class="sxs-lookup"><span data-stu-id="8047c-414">**Network** The computer should be able to connect to the back-end database.</span></span>

<span data-ttu-id="8047c-415">**软件**在运行 DBAnalyze 之前，必须安装 Lync Server 2013 软件组件。</span><span class="sxs-lookup"><span data-stu-id="8047c-415">**Software** Lync Server 2013 software components must be installed before running DBAnalyze.</span></span>

<span data-ttu-id="8047c-416">**用户**下表显示了具有访问 Lync Server 2013 数据库所需的权限的管理员。</span><span class="sxs-lookup"><span data-stu-id="8047c-416">**Users**The table below shows the administrators who have the necessary permissions to access Lync Server 2013 databases.</span></span>

<span data-ttu-id="8047c-417">![Dbanalyze 的权限表。](images/JJ945604.b8931e9e-834e-4dec-8a84-2fc47d1613e9(OCS.15).jpg "Dbanalyze 的权限表。")</span><span class="sxs-lookup"><span data-stu-id="8047c-417">![Permissions table for Dbanalyze.exe.](images/JJ945604.b8931e9e-834e-4dec-8a84-2fc47d1613e9(OCS.15).jpg "Permissions table for Dbanalyze.exe.")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8047c-418"><STRONG>/Report：磁盘</STRONG>模式需要本地管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="8047c-418">A local administrator account is required for <STRONG>/report:disk</STRONG> mode.</span></span>



</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="8047c-419">示例</span><span class="sxs-lookup"><span data-stu-id="8047c-419">Examples</span></span>

<span data-ttu-id="8047c-420">以下是有效 Dbanalyze 命令的示例：</span><span class="sxs-lookup"><span data-stu-id="8047c-420">The following are examples of valid Dbanalyze.exe commands:</span></span>

    dbanalyze.exe /report:diag
    dbanalyze.exe /report:user /user:usera@domainb.com
    dbanalyze.exe /report:conf /user:bob@example.com /conf:1W9J71SKSX2X
    dbanalyze.exe /report:resolve /pstnid:12345
    dbanalyze.exe /report:mcus
    dbanalyze.exe /report:disk

</div>

<div>

## <a name="summary"></a><span data-ttu-id="8047c-421">总结</span><span class="sxs-lookup"><span data-stu-id="8047c-421">Summary</span></span>

<span data-ttu-id="8047c-422">DBAnalyzer 为管理员提供了快速而轻松地分析 Lync Server 2013 数据库的情况。</span><span class="sxs-lookup"><span data-stu-id="8047c-422">DBAnalyzer provides administrators a quick and easy to analyze Lync Server 2013 databases.</span></span>

</div>

</div>

<div>

## <a name="importstorageservicedata"></a><span data-ttu-id="8047c-423">ImportStorageServiceData</span><span class="sxs-lookup"><span data-stu-id="8047c-423">ImportStorageServiceData</span></span>

<span data-ttu-id="8047c-424">ImportStorageServiceData 资源工具包工具允许将在存储服务（LYSS）上刷新的队列和终结点数据重新导入到存储服务中。</span><span class="sxs-lookup"><span data-stu-id="8047c-424">The ImportStorageServiceData resource kit tool allows for re-importing Queue and Endpoint data that was flushed out of the Storage Service (LYSS) back into the Storage Service.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="8047c-425">说明</span><span class="sxs-lookup"><span data-stu-id="8047c-425">Description</span></span>

<span data-ttu-id="8047c-426">从存储服务中刷新的数据可能已基于队列项目状态或数据库大小自动（定期）。</span><span class="sxs-lookup"><span data-stu-id="8047c-426">The data flushed out of the Storage Service could have been automatic (periodic) based on Queue Item status or database size.</span></span> <span data-ttu-id="8047c-427">由于手动调用池故障转移 cmdlet 或 StorageServiceFullFlush cmdlet （池故障转移 cmdlet 调用），可能会发生此问题。</span><span class="sxs-lookup"><span data-stu-id="8047c-427">It could have happened due to the manual invocation of the pool failover cmdlet, or the StorageServiceFullFlush cmdlet (which the pool failover cmdlet invokes).</span></span> <span data-ttu-id="8047c-428">请注意，如果前端上的任何存储服务（LYSS）数据库大小高于正常级别，则不应重新导入数据，因为这样做可能只会导致更多数据被导出回来。此外，应首先解决导致存储服务队列增长的错误可能会导致出现的任何问题（例如 Exchange 终结点错误、网络问题或其他问题）。</span><span class="sxs-lookup"><span data-stu-id="8047c-428">Note that data should ideally not be re-imported if any of the Storage Service (LYSS ) database size on the front ends is above the normal level, because doing so will likely just cause more data to be exported back out. Furthermore, any problems which could have contributed to errors that caused the Storage Service Queue to grow should first be resolved (for example Exchange endpoint errors, network issues, or other problems).</span></span>

<span data-ttu-id="8047c-429">**方案1：** 在池故障转移过程中，可能会从每个前端的存储服务中刷新文件。</span><span class="sxs-lookup"><span data-stu-id="8047c-429">**Scenario 1:** during pool failover, files may be flushed out from storage service for each front end.</span></span> <span data-ttu-id="8047c-430">故障转移完成后，应运行该工具以重新导入数据。</span><span class="sxs-lookup"><span data-stu-id="8047c-430">After failover is completed, the tool should be run to re-import the data.</span></span>

<span data-ttu-id="8047c-431">**方案2：** 每日自动刷新数据或响应超过特定大小阈值的 Storage Service 数据库（例如，60%、80%、90% 已满）。</span><span class="sxs-lookup"><span data-stu-id="8047c-431">**Scenario 2:** data is being flushed automatically each day or in response to Storage Service database exceeding certain size thresholds ( for example 60%, 80%, 90% full ).</span></span> <span data-ttu-id="8047c-432">此自动刷新的数据应由管理员定期重新导入。</span><span class="sxs-lookup"><span data-stu-id="8047c-432">This automatically flushed data should be re-imported routinely by the administrator.</span></span> <span data-ttu-id="8047c-433">在上述情况下，如果未部署监控 SCOM 包，则会出现与从存储服务刷新的数据相关的 Lync Server Storage Service 的事件。</span><span class="sxs-lookup"><span data-stu-id="8047c-433">In the above situation, if the monitoring SCOM pack is not deployed, there are events for Lync Server Storage Service relating to data being flushed from the Storage Service.</span></span> <span data-ttu-id="8047c-434">事件 Id 为32075（已启动完全刷新操作）、32076（已完成完全刷新）、32082（维护级别刷新已启动）、32083（维护级别刷新完成）、32089（因填充数据库而发生刷新）。</span><span class="sxs-lookup"><span data-stu-id="8047c-434">Event IDs of 32075 (full flush operation is started), 32076 (full flush has completed), 32082 (maintenance level flush started), 32083 (maintenance level flush complete), 32089 (flush occurred due to filling up of database).</span></span> <span data-ttu-id="8047c-435">注意，这些事件 Id 对应于 RTM 版本。</span><span class="sxs-lookup"><span data-stu-id="8047c-435">Note these event Ids correspond to the RTM release.</span></span> <span data-ttu-id="8047c-436">当管理员看到这些事件时，意味着已清除的文件。应使用此工具定期导入此数据，例如每周一次。</span><span class="sxs-lookup"><span data-stu-id="8047c-436">When an administrator sees these events, it means that there are files that have been flushed out. This data should routinely be imported back using this tool, for example once per week.</span></span>

<span data-ttu-id="8047c-437">对于在线服务版本，如果部署了 Lync Server 的运行状况监视 SCOM 包，则可能会引发新警报，要求管理员将刷新后的数据重新导入存储服务。</span><span class="sxs-lookup"><span data-stu-id="8047c-437">For the Online Service release, if health monitoring SCOM pack for Lync Server is deployed, there are new alerts which may be raised which ask the administrator to re-import the flushed data back into Storage Service.</span></span> <span data-ttu-id="8047c-438">在触发警报的前端服务器上的事件日志中将会有相应的事件。</span><span class="sxs-lookup"><span data-stu-id="8047c-438">There will be a corresponding event in the event log on the Front End server which triggered the alert.</span></span> <span data-ttu-id="8047c-439">该事件将提供刷新数据文件所在的父路径的说明，以及有多少个文件符合警报条件。</span><span class="sxs-lookup"><span data-stu-id="8047c-439">The event will give a description of the Parent path under which the flushed data files are located, as well as how many files there are which meet the alert criteria.</span></span> <span data-ttu-id="8047c-440">警报条件是特定父路径下的 X 或更多文件，这些文件至少为 Y 天旧（其中 X 和 Y 是在 StorageService 中预设的，但可以通过更改 APPCONFIG 文件进行重写。）下面显示了可以触发运行状况警报的事件的两个示例，区别在于它们的父路径。</span><span class="sxs-lookup"><span data-stu-id="8047c-440">The alert criteria is that there are X or more files under the particular parent path which are at least Y days old ( where X and Y are preset within the StorageService but can be overridden by changing the APPCONFIG file.)Two examples of events which can trigger the health alert are shown below, with the difference being their parent path.</span></span> <span data-ttu-id="8047c-441">有一种可能的情况是 Web 服务文件共享，而另一个可能的是每个前端的本地应用程序数据目录。</span><span class="sxs-lookup"><span data-stu-id="8047c-441">One possibility is under Web service file share, while the other possibility is the local Application Data directory of each front end.</span></span> <span data-ttu-id="8047c-442">（例如，c：\\ProgramData\\Microsoft\\Lync Server\\StorageService）。</span><span class="sxs-lookup"><span data-stu-id="8047c-442">( for example c:\\ProgramData\\Microsoft\\Lync Server\\StorageService ).</span></span> <span data-ttu-id="8047c-443">然后，管理员将运行此 \reskit 工具。</span><span class="sxs-lookup"><span data-stu-id="8047c-443">The administrator will then run this reskit tool.</span></span>

<span data-ttu-id="8047c-444">此工具会在其运行的前端上增加 CPU 和 IO 负载，以及其他前端，在数据不是在其上执行该工具的前端所拥有的情况下。</span><span class="sxs-lookup"><span data-stu-id="8047c-444">This tool will increase CPU and IO load on the front end it is running on, as well as other front ends, in the situation that the data is not owned by the front end that the tool is executed on.</span></span> <span data-ttu-id="8047c-445">我们建议在前端不低于 CPU 和 IO 负载（例如在高峰时段之外）时 runng 此工具。</span><span class="sxs-lookup"><span data-stu-id="8047c-445">We recommend runng this tool when front ends are not under heavy CPU and IO load, for example outside of peak hours.</span></span> <span data-ttu-id="8047c-446">其次，此工具可以2至3分钟导入一个数据文件。</span><span class="sxs-lookup"><span data-stu-id="8047c-446">Secondly, this tool can 2 to 3 minutes to import one data file.</span></span> <span data-ttu-id="8047c-447">在估计工具的运行时间时，请记住这一点。默认情况下，该工具生成的详细日志文件将显示在文件存储上。</span><span class="sxs-lookup"><span data-stu-id="8047c-447">Keep this in mind when estimating how long tool will be running.The verbose log file generated by the tool will by default appear on the File Store.</span></span> <span data-ttu-id="8047c-448">如果没有报告错误，则将其删除，因为日志文件可能是数十 MB 或更多。</span><span class="sxs-lookup"><span data-stu-id="8047c-448">Delete it if there are no errors reported, because the log file can be tens of MB or more.</span></span>

<span data-ttu-id="8047c-449">![示例存储服务器事件日志事件。](images/JJ945604.3a903ef7-ea8a-4606-8229-a3e32f13af3a(OCS.15).jpg "示例存储服务器事件日志事件。")</span><span class="sxs-lookup"><span data-stu-id="8047c-449">![Sample Storage Server event log events.](images/JJ945604.3a903ef7-ea8a-4606-8229-a3e32f13af3a(OCS.15).jpg "Sample Storage Server event log events.")</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="8047c-450">Requirements</span><span class="sxs-lookup"><span data-stu-id="8047c-450">Requirements</span></span>

<span data-ttu-id="8047c-451">安装 Lync Server 2013 （资源工具包工具）。</span><span class="sxs-lookup"><span data-stu-id="8047c-451">Install the Lync Server 2013, Resource Kit Tools.</span></span> <span data-ttu-id="8047c-452">该工具在安装了 Lync Server 和 Lync Server 命令行管理程序的加入域的计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="8047c-452">The tool runs on domain-joined machines where Lync Server and Lync Server Management Shell are installed.</span></span> <span data-ttu-id="8047c-453">该工具使用命令行管理程序中的 cmdlet 来标识池中的所有前端服务器。</span><span class="sxs-lookup"><span data-stu-id="8047c-453">The tool uses a cmdlet from the management shell to identify all the Front End servers in the pool.</span></span> <span data-ttu-id="8047c-454">其次，该工具必须从安装了**RtcLocal**数据库的池中的计算机执行。</span><span class="sxs-lookup"><span data-stu-id="8047c-454">Secondly, the tool must be executed from a machine in the pool which has the **RtcLocal** database installed.</span></span> <span data-ttu-id="8047c-455">工具使用此数据库检索池的 WEBSERVICE 文件共享的位置。此外，在使用此工具之前，每台前端服务器必须首先在每台前端服务器上使用**enable-psremoting**启用 Windows PowerShell 远程，以及执行该工具的计算机。</span><span class="sxs-lookup"><span data-stu-id="8047c-455">This database is used by the tool to retrieve the location of the WEBSERVICE file share for the pool.Additionally, before using the tool, each Front End server must first enable Windows PowerShell Remoting using **Enable-PSRemoting** on each Front End server, as well as the machine that the tool is executed from.</span></span> <span data-ttu-id="8047c-456">否则，此工具的远程 Windows PowerShell 命令将失败。</span><span class="sxs-lookup"><span data-stu-id="8047c-456">Otherwise, remote Windows PowerShell commands from this tool will fail.</span></span> <span data-ttu-id="8047c-457">完成后，可以在池中的所有前端服务器上关闭 Windows PowerShell 远程处理。</span><span class="sxs-lookup"><span data-stu-id="8047c-457">Windows PowerShell Remoting can be turned off on all Front End servers in the pool after it is finished.</span></span> <span data-ttu-id="8047c-458">最后，调用该工具的帐户或凭据必须具有对要在其上执行此工具的池的 webservice 文件共享的读/写权限。</span><span class="sxs-lookup"><span data-stu-id="8047c-458">Finally, the account or credential invoking the tool must have read/write permission to the webservice file share for the pool they are executing this tool on.</span></span> <span data-ttu-id="8047c-459">否则，该工具将因 IO 权限错误而失败。</span><span class="sxs-lookup"><span data-stu-id="8047c-459">Otherwise the tool will fail with IO Permission errors.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8047c-460">在 Windows Server 2012 中，Windows PowerShell 远程处理在默认情况下处于启用状态，而不是在 Windows Server 2008 操作系统上启用。</span><span class="sxs-lookup"><span data-stu-id="8047c-460">On Windows Server 2012, Windows PowerShell Remoting is enabled by default, but not on the Windows Server 2008 operating system.</span></span>



</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="8047c-461">示例</span><span class="sxs-lookup"><span data-stu-id="8047c-461">Examples</span></span>

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

</div>

</div>

<div>

## <a name="lcssync"></a><span data-ttu-id="8047c-462">LCSSync</span><span class="sxs-lookup"><span data-stu-id="8047c-462">LCSSync</span></span>

<span data-ttu-id="8047c-463">LCSSync 工具可帮助在多林环境中部署 Lync Server 2013 通信软件。</span><span class="sxs-lookup"><span data-stu-id="8047c-463">The LCSSync tool helps to deploy Lync Server 2013 communications software in a multi-forest environment.</span></span> <span data-ttu-id="8047c-464">此工具用于将不同用户林的用户和组作为 Active Directory 域服务联系人对象同步到安装了 Lync Server 2013 的中央林。</span><span class="sxs-lookup"><span data-stu-id="8047c-464">This tool is used to synchronize users and groups from different user forests as an Active Directory Domain Services contact object to a central forest where Lync Server 2013 is installed.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="8047c-465">说明</span><span class="sxs-lookup"><span data-stu-id="8047c-465">Description</span></span>

<span data-ttu-id="8047c-466">LCSSync 使用中央林中的同步 Active Directory 域服务联系人对象为用户启用 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="8047c-466">LCSSync uses the synchronized Active Directory Domain Services contact objects in the central forest to enable users for Lync Server.</span></span> <span data-ttu-id="8047c-467">若要提供单一登录，必须将主用户帐户映射到适用于 Lync Server 2013 的中央林中的 Active Directory 域服务联系人对象。</span><span class="sxs-lookup"><span data-stu-id="8047c-467">To provide single sign-in, the primary user account must be mapped to the Active Directory Domain Services contact object in the central forest for Lync Server 2013.</span></span> <span data-ttu-id="8047c-468">此工具可帮助执行该映射。</span><span class="sxs-lookup"><span data-stu-id="8047c-468">This tool helps perform that mapping.</span></span> <span data-ttu-id="8047c-469">此工具提供用于在 Microsoft Identity Integration Server 中创建管理代理的模板。</span><span class="sxs-lookup"><span data-stu-id="8047c-469">This tool provides templates for creating Management Agents in the Microsoft Identity Integration Server.</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="8047c-470">总结</span><span class="sxs-lookup"><span data-stu-id="8047c-470">Summary</span></span>

<span data-ttu-id="8047c-471">LCSSync 工具可帮助在多林环境中部署 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="8047c-471">The LCSSync tool helps to deploy Lync Server in a multi-forest environment.</span></span>

</div>

</div>

<div>

## <a name="lookupuserconsole"></a><span data-ttu-id="8047c-472">LookupUserConsole</span><span class="sxs-lookup"><span data-stu-id="8047c-472">LookupUserConsole</span></span>

<span data-ttu-id="8047c-473">LookupUserConsole 工具显示有关特定用户的内部 Lync Server 路由信息。</span><span class="sxs-lookup"><span data-stu-id="8047c-473">The LookupUserConsole tool displays internal Lync Server routing information about specific users.</span></span> <span data-ttu-id="8047c-474">此信息可能对 Microsoft 支持个人在诊断部署和路由问题方面有用。</span><span class="sxs-lookup"><span data-stu-id="8047c-474">This information may be useful to Microsoft support personal in diagnosing deployment and routing problems.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="8047c-475">说明</span><span class="sxs-lookup"><span data-stu-id="8047c-475">Description</span></span>

<span data-ttu-id="8047c-476">执行 LookupUserConsole 将打开一个命令提示符，该命令提示符接受 SIP 地址，并尝试显示与它们相关的内部 Lync Server 路由信息。</span><span class="sxs-lookup"><span data-stu-id="8047c-476">Executing LookupUserConsole.exe will open a command prompt that accepts SIP addresses and attempts to display internal Lync Server routing information relating them.</span></span> <span data-ttu-id="8047c-477">键入**exit**退出 LookupUserConsole 工具。</span><span class="sxs-lookup"><span data-stu-id="8047c-477">Type **exit** to quit the LookupUserConsole tool.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="8047c-478">Requirements</span><span class="sxs-lookup"><span data-stu-id="8047c-478">Requirements</span></span>

<span data-ttu-id="8047c-479">安装 Lync Server 2013 （资源工具包工具）。</span><span class="sxs-lookup"><span data-stu-id="8047c-479">Install the Lync Server 2013, Resource Kit Tools.</span></span> <span data-ttu-id="8047c-480">该工具在安装了 Lync Server 的加入域的计算机上运行</span><span class="sxs-lookup"><span data-stu-id="8047c-480">The tool runs on domain-joined machines where Lync Server is installed</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="8047c-481">示例</span><span class="sxs-lookup"><span data-stu-id="8047c-481">Examples</span></span>

<span data-ttu-id="8047c-482">C：\\程序文件\\Microsoft Lync Server 2013\\\reskit\>LookupUserConsole</span><span class="sxs-lookup"><span data-stu-id="8047c-482">C:\\Program Files\\Microsoft Lync Server 2013\\ResKit\>LookupUserConsole.exe</span></span>

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

</div>

</div>

<div>

## <a name="msturnping"></a><span data-ttu-id="8047c-483">MsTurnPing</span><span class="sxs-lookup"><span data-stu-id="8047c-483">MsTurnPing</span></span>

<span data-ttu-id="8047c-484">MSTurnPing 工具允许 Microsoft Lync Server 2013 通信软件的管理员检查运行 "音频/视频边缘" 和 "音频/视频身份验证服务" 的服务器的状态，以及在拓扑中运行带宽策略服务的服务器的状态。</span><span class="sxs-lookup"><span data-stu-id="8047c-484">The MSTurnPing tool allows an administrator of Microsoft Lync Server 2013 communications software to check the status of the servers running the Audio/Video Edge and Audio/Video Authentication services as well as the servers that are running Bandwidth Policy Services in the topology.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="8047c-485">说明</span><span class="sxs-lookup"><span data-stu-id="8047c-485">Description</span></span>

<span data-ttu-id="8047c-486">MSTurnPing 工具允许 Lync Server 2013 通信软件的管理员检查运行 "音频/视频边缘" 和 "音频/视频身份验证服务" 的服务器的状态，以及在拓扑中运行带宽策略服务的服务器的状态。</span><span class="sxs-lookup"><span data-stu-id="8047c-486">The MSTurnPing tool allows an administrator of Lync Server 2013 communications software to check the status of the servers running the Audio/Video Edge and Audio/Video Authentication services as well as the servers that are running Bandwidth Policy Services in the topology.</span></span>

<span data-ttu-id="8047c-487">此工具允许管理员执行以下测试：</span><span class="sxs-lookup"><span data-stu-id="8047c-487">The tool allows the administrator to perform the following tests:</span></span>

1.  <span data-ttu-id="8047c-488">A/V 边缘服务器测试：该工具通过执行以下操作，对拓扑中的所有 A/V 边缘服务器执行测试：</span><span class="sxs-lookup"><span data-stu-id="8047c-488">A/V Edge Server test: The tool performs tests against all A/V Edge Servers in the topology by doing the following:</span></span>
    
      - <span data-ttu-id="8047c-489">验证 Lync Server 音频/视频身份验证服务是否已启动，并可颁发正确的凭据。</span><span class="sxs-lookup"><span data-stu-id="8047c-489">Verifying that the Lync Server Audio/Video Authentication service is started and can issue proper credentials.</span></span>
    
      - <span data-ttu-id="8047c-490">验证 Lync Server 音频/视频边缘服务是否已启动，并可以成功地在外部边缘上分配资源。</span><span class="sxs-lookup"><span data-stu-id="8047c-490">Verifying that the Lync Server Audio/Video Edge service is started and can allocate the resources on the external edge successfully.</span></span>

2.  <span data-ttu-id="8047c-491">带宽策略服务测试：该工具通过执行以下操作，对运行此拓扑中的带宽策略服务的所有服务器执行测试：</span><span class="sxs-lookup"><span data-stu-id="8047c-491">Bandwidth Policy Service test: The tool performs tests against all the servers that are running the Bandwidth Policy Services in the topology by doing the following:</span></span>
    
      - <span data-ttu-id="8047c-492">验证 Lync Server 带宽策略服务（身份验证）是否已启动，并可颁发正确的凭据。</span><span class="sxs-lookup"><span data-stu-id="8047c-492">Verifying that the Lync Server Bandwidth Policy Service (Authentication) is started and can issue proper credentials.</span></span>
    
      - <span data-ttu-id="8047c-493">验证 Lync Server 带宽策略服务（Core）是否已启动并可以成功执行带宽检查。</span><span class="sxs-lookup"><span data-stu-id="8047c-493">Verifying that the Lync Server Bandwidth Policy Service (Core) is started and can perform the bandwidth check successfully.</span></span>

<span data-ttu-id="8047c-494">必须从作为拓扑一部分的计算机运行此工具，并安装本地存储。</span><span class="sxs-lookup"><span data-stu-id="8047c-494">This tool must be run from a computer that is part of the topology and has the local store installed.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="8047c-495">Output</span><span class="sxs-lookup"><span data-stu-id="8047c-495">Output</span></span>

<span data-ttu-id="8047c-496">该工具将输出每个操作的结果。</span><span class="sxs-lookup"><span data-stu-id="8047c-496">The tool outputs the results of each of the operations.</span></span>

  - <span data-ttu-id="8047c-497">如果执行了**AudioVideoEdgeServer**测试，则工具输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="8047c-497">If the **AudioVideoEdgeServer** test is performed, the tool outputs are the following:</span></span>
    
      - <span data-ttu-id="8047c-498">在拓扑中提供 Lync Server 音频/视频身份验证服务的计算机的测试结果</span><span class="sxs-lookup"><span data-stu-id="8047c-498">The test results of the computers that provide the Lync Server Audio/Video Authentication service in the topology</span></span>
    
      - <span data-ttu-id="8047c-499">在拓扑中提供 Lync Server 音频/视频边缘服务的计算机的测试结果</span><span class="sxs-lookup"><span data-stu-id="8047c-499">The test results of the computers that provide the Lync Server Audio/Video Edge service in the topology</span></span>

  - <span data-ttu-id="8047c-500">如果执行了**BandwidthPolicyServer**测试，则工具输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="8047c-500">If the **BandwidthPolicyServer** test is performed, the tool outputs are the following:</span></span>
    
      - <span data-ttu-id="8047c-501">在拓扑中提供 Lync Server 带宽策略服务（身份验证）的计算机的测试结果</span><span class="sxs-lookup"><span data-stu-id="8047c-501">The test results of the computers that provide the Lync Server Bandwidth Policy Service (Authentication) in the topology</span></span>
    
      - <span data-ttu-id="8047c-502">在拓扑中提供 Lync Server 带宽策略服务（核心）的计算机的测试结果</span><span class="sxs-lookup"><span data-stu-id="8047c-502">The test results of the computers that provide the Lync Server Bandwidth Policy Service (Core) in the topology</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="8047c-503">Requirements</span><span class="sxs-lookup"><span data-stu-id="8047c-503">Requirements</span></span>

  - <span data-ttu-id="8047c-504">此工具必须从拓扑中的计算机运行，且具有本地存储。</span><span class="sxs-lookup"><span data-stu-id="8047c-504">This tool must be run from a computer that is in the topology and that has the local store.</span></span>

  - <span data-ttu-id="8047c-505">该工具必须以具有本地存储访问权限的管理员身份运行。</span><span class="sxs-lookup"><span data-stu-id="8047c-505">The tool must be run as an administrator who has access to the local store.</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="8047c-506">示例</span><span class="sxs-lookup"><span data-stu-id="8047c-506">Examples</span></span>

<span data-ttu-id="8047c-507">以下是工具输入的一个示例。</span><span class="sxs-lookup"><span data-stu-id="8047c-507">The following is an example of the tool input.</span></span>

    MsTurnPing -ServerRole AudioVideoEdgeServer
    
    MsTurnPing -ServerRole BandwidthPolicyServer

</div>

<div>

## <a name="summary"></a><span data-ttu-id="8047c-508">总结</span><span class="sxs-lookup"><span data-stu-id="8047c-508">Summary</span></span>

<span data-ttu-id="8047c-509">对于要检查运行音频/视频和带宽策略服务的服务器的状态的 Lync Server 2013 管理员，此工具可能是一种有用的资源。</span><span class="sxs-lookup"><span data-stu-id="8047c-509">This tool can be a valuable resource to Lync Server 2013 administrators who want to check the status of the servers that are running audio/video and bandwidth policy services.</span></span>

</div>

</div>

<div>

## <a name="network-configuration-viewer"></a><span data-ttu-id="8047c-510">网络配置查看器</span><span class="sxs-lookup"><span data-stu-id="8047c-510">Network Configuration Viewer</span></span>

<span data-ttu-id="8047c-511">Microsoft Lync Server 2013 通信软件管理员可使用网络配置查看器查看已预配的企业的呼叫允许控制（CAC）网络拓扑，以允许实时通信会话（如语音或基于指定带宽容量的视频呼叫。</span><span class="sxs-lookup"><span data-stu-id="8047c-511">Network Configuration Viewer can be used by Microsoft Lync Server 2013 communications software administrators to view call admission control (CAC) network topology for an enterprise that is provisioned to allow real-time communication sessions, such as voice or video calls based on specified bandwidth capacity.</span></span> <span data-ttu-id="8047c-512">Lync Server 2013 管理员定义 CAC 策略，这些策略由随 Lync Server 2013 一起安装的带宽策略服务强制实施。</span><span class="sxs-lookup"><span data-stu-id="8047c-512">Lync Server 2013 administrators define CAC policies, which are enforced by the Bandwidth Policy services that are installed with Lync Server 2013.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="8047c-513">说明</span><span class="sxs-lookup"><span data-stu-id="8047c-513">Description</span></span>

<span data-ttu-id="8047c-514">网络配置查看器（NetworkConfigurationViewer）允许管理员执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="8047c-514">Network Configuration Viewer (NetworkConfigurationViewer.exe) allows administrators to perform the following tasks:</span></span>

  - <span data-ttu-id="8047c-515">以图形格式从 Lync Server 2013 部署中加载和查看 CAC 网络拓扑。</span><span class="sxs-lookup"><span data-stu-id="8047c-515">Load and view CAC network topology from a Lync Server 2013 deployment in a graphical format.</span></span>

  - <span data-ttu-id="8047c-516">以图形格式从带宽策略服务器日志文件中加载和查看 CAC 网络拓扑。</span><span class="sxs-lookup"><span data-stu-id="8047c-516">Load and view CAC network topology from a Bandwidth Policy Server log file in a graphical format.</span></span>

  - <span data-ttu-id="8047c-517">以 XML 格式在磁盘上保存和存储 CAC 网络拓扑。</span><span class="sxs-lookup"><span data-stu-id="8047c-517">Save and store CAC network topology in an XML format on the disk.</span></span>

  - <span data-ttu-id="8047c-518">以 JPG 或 BMP 格式保存和存储 CAC 网络拓扑图。</span><span class="sxs-lookup"><span data-stu-id="8047c-518">Save and store CAC network topology diagram in JPG or BMP format.</span></span>

  - <span data-ttu-id="8047c-519">查看 CAC 网络拓扑配置数据。</span><span class="sxs-lookup"><span data-stu-id="8047c-519">View CAC network topology configuration data.</span></span>

  - <span data-ttu-id="8047c-520">在树视图样式中查看 CAC 网络拓扑。</span><span class="sxs-lookup"><span data-stu-id="8047c-520">View CAC network topology in a tree-view style.</span></span>

  - <span data-ttu-id="8047c-521">为 CAC 网络拓扑链接（例如，站点到区域、区域到区域和站点到站点链接）定义自定义连接器。</span><span class="sxs-lookup"><span data-stu-id="8047c-521">Define custom connectors for CAC network topology links (for example, site-to-region, region-to-region, and site-to-site links).</span></span>

  - <span data-ttu-id="8047c-522">查看 CAC 网络拓扑网站信息、区域信息，以及预配的带宽策略和网络链接。</span><span class="sxs-lookup"><span data-stu-id="8047c-522">View CAC network topology site information, region Information, and provisioned bandwidth policies and network links.</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="8047c-523">用途</span><span class="sxs-lookup"><span data-stu-id="8047c-523">Purpose</span></span>

<span data-ttu-id="8047c-524">在图形界面中查看企业 CAC 网络拓扑链接。</span><span class="sxs-lookup"><span data-stu-id="8047c-524">View enterprise CAC network topology links in a graphical interface.</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="8047c-525">示例</span><span class="sxs-lookup"><span data-stu-id="8047c-525">Examples</span></span>

<span data-ttu-id="8047c-526">**以图形格式从 Lync Server 2013 部署加载和查看 CAC 网络拓扑：** Lync Server 2013 管理员可以使用 "**下载网络配置**" 选项在任何 Lync server 2013 计算机上加载并查看 CAC 网络拓扑配置，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="8047c-526">**Load and view CAC network topology from a Lync Server 2013 deployment in a graphical format:** Lync Server 2013 administrators can load and view CAC network topology configuration on any Lync Server 2013 computer by using the **Download Network Configuration** option as shown in the figure below.</span></span> <span data-ttu-id="8047c-527">在没有连接到 Lync 配置存储的计算机上部署时，该工具将无法下载或查看此类配置。</span><span class="sxs-lookup"><span data-stu-id="8047c-527">The tool will fail to download or view such a configuration when deployed on a computer that does not have connectivity to the Lync configuration store.</span></span>

<span data-ttu-id="8047c-528">![下载网络配置。](images/JJ945604.8d126d3f-2545-4f13-a244-974f09614982(OCS.15).jpg "下载网络配置。")</span><span class="sxs-lookup"><span data-stu-id="8047c-528">![Downloading the network configuration.](images/JJ945604.8d126d3f-2545-4f13-a244-974f09614982(OCS.15).jpg "Downloading the network configuration.")</span></span>

<span data-ttu-id="8047c-529">**以图形格式从带宽策略服务器日志文件中加载和查看 CAC 网络拓扑：** Lync Server 2013 带宽策略服务器将 CAC 网络拓扑保存为 Lync Server 2013 文件共享位置下的日志记录机制的一部分。</span><span class="sxs-lookup"><span data-stu-id="8047c-529">**Load and View CAC network topology from a Bandwidth Policy server log file in a graphical format:** Lync Server 2013 Bandwidth Policy servers save the CAC network topology as a part of the logging mechanism under the Lync Server 2013 file share location.</span></span> <span data-ttu-id="8047c-530">Lync Server 管理员可以使用 "**打开网络配置**" 选项以图形格式查看此类文件，如下所示。</span><span class="sxs-lookup"><span data-stu-id="8047c-530">Lync Server administrators can view such a file in a graphical format by using the **Open Network Configuration** option as shown below.</span></span>

<span data-ttu-id="8047c-531">![打开带宽策略服务器日志文件。](images/JJ945604.3e503e92-aacb-4921-a8d2-23f860fe2df6(OCS.15).jpg "打开带宽策略服务器日志文件。")</span><span class="sxs-lookup"><span data-stu-id="8047c-531">![Opening a Bandwidth Policy Server log file.](images/JJ945604.3e503e92-aacb-4921-a8d2-23f860fe2df6(OCS.15).jpg "Opening a Bandwidth Policy Server log file.")</span></span>

<span data-ttu-id="8047c-532">在磁盘上以 XML 格式保存和存储 CAC 网络拓扑： Lync Server 2013 管理员可以使用 "**保存网络配置**" 选项的副本以 xml 格式保存 cac 网络拓扑配置文件，如下所示。</span><span class="sxs-lookup"><span data-stu-id="8047c-532">Save and store CAC network topology in an XML format on the disk: Lync Server 2013 administrators can save the CAC network topology configuration file in an XML format by using the **Save a copy of Network Configuration** option as shown below.</span></span> <span data-ttu-id="8047c-533">然后，可以将已保存的配置文件脱机用于图形化查看目的。</span><span class="sxs-lookup"><span data-stu-id="8047c-533">The saved configuration file can then be used offline for graphical viewing purposes.</span></span>

<span data-ttu-id="8047c-534">![将网络配置另存为 XML 文件。](images/JJ945604.6eeef3b0-78b5-4ee6-8d94-1a4ddf3d8676(OCS.15).jpg "将网络配置另存为 XML 文件。")</span><span class="sxs-lookup"><span data-stu-id="8047c-534">![Saving the network configuration as an XML file.](images/JJ945604.6eeef3b0-78b5-4ee6-8d94-1a4ddf3d8676(OCS.15).jpg "Saving the network configuration as an XML file.")</span></span>

<span data-ttu-id="8047c-535">以 JPG 或 BMP 格式保存和存储 CAC 网络拓扑图： Lync Server 2013 管理员可以使用 "**将网络配置图表另存为图片**" 选项以图形格式（JPG 和 BMP 文件格式）保存 cac 网络拓扑配置，如下所示。</span><span class="sxs-lookup"><span data-stu-id="8047c-535">Save and Store CAC network topology diagram in JPG or BMP format: Lync Server 2013 administrators can save the CAC network topology configuration in a graphical format (JPG and BMP file formats) by using the **Save Network Configuration diagram as picture** option as shown below.</span></span>

<span data-ttu-id="8047c-536">![将网络配置另存为图片。](images/JJ945604.145a6fb9-58b1-46b1-bbd5-a661ceba07b4(OCS.15).jpg "将网络配置另存为图片。")</span><span class="sxs-lookup"><span data-stu-id="8047c-536">![Saving the network configuration as a picture.](images/JJ945604.145a6fb9-58b1-46b1-bbd5-a661ceba07b4(OCS.15).jpg "Saving the network configuration as a picture.")</span></span>

<span data-ttu-id="8047c-537">**查看 CAC 网络拓扑配置数据：** Lync Server 2013 管理员可以使用如下所示的 "查看网络配置数据" 选项，以文本格式查看相关网络配置数据，例如网络区域、网络站点、带宽配置文件和站点子网 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="8047c-537">**View CAC network topology configuration data:** Lync Server 2013 administrators can view related network configuration data such as network regions, network sites, bandwidth profiles, and site subnet IP addresses in a textual format by using the View Network Configuration data option as shown below.</span></span>

<span data-ttu-id="8047c-538">![查看网络配置数据。](images/JJ945604.b72a4c21-a042-4d91-bf96-fcb396af0679(OCS.15).jpg "查看网络配置数据。")</span><span class="sxs-lookup"><span data-stu-id="8047c-538">![Viewing network configuration data.](images/JJ945604.b72a4c21-a042-4d91-bf96-fcb396af0679(OCS.15).jpg "Viewing network configuration data.")</span></span>

<span data-ttu-id="8047c-539">**在树视图样式中查看 CAC 网络拓扑：** Lync Server 2013 管理员可以使用工具窗口左侧的 "控制面板" 中的 "控制" 面板查看图形树视图样式中的相关网络配置数据，如下所示。</span><span class="sxs-lookup"><span data-stu-id="8047c-539">**View CAC network topology in a tree-view style:** Lync Server 2013 administrators can view related network configuration data in a graphical tree view style by using the control panel on the left side of the tool window as shown below.</span></span>

<span data-ttu-id="8047c-540">![在树视图中查看网络配置数据。](images/JJ945604.4d924ac9-fd96-430f-b211-ee35b7ef9a23(OCS.15).jpg "在树视图中查看网络配置数据。")</span><span class="sxs-lookup"><span data-stu-id="8047c-540">![Viewing network configuration data in a tree-view.](images/JJ945604.4d924ac9-fd96-430f-b211-ee35b7ef9a23(OCS.15).jpg "Viewing network configuration data in a tree-view.")</span></span>

<span data-ttu-id="8047c-541">**为 CAC 网络拓扑链接定义自定义连接器（如站点到区域、区域到区域和站点到站点链接）：** Lync Server 2013 管理员可使用如下所示的 "设置" 选项定义自定义的 CAC 网络配置 WAN 链接的图形连接器。</span><span class="sxs-lookup"><span data-stu-id="8047c-541">**Define custom connectors for CAC network topology links (such as site-to-region, region-to-region, and site-to-site links):** Lync Server 2013 administrators can define custom graphical connectors for CAC network configuration WAN links by using the Settings option as shown below.</span></span> <span data-ttu-id="8047c-542">这有助于区分在网络配置中预配的各种类型的网络链接。</span><span class="sxs-lookup"><span data-stu-id="8047c-542">This helps differentiate between various types of network links that are provisioned in the network configuration.</span></span>

<span data-ttu-id="8047c-543">![为 CAC 网络拓扑定义自定义连接器](images/JJ945604.b20bea67-c8e1-453e-b1dd-e2aa17b62566(OCS.15).jpg "为 CAC 网络拓扑定义自定义连接器")</span><span class="sxs-lookup"><span data-stu-id="8047c-543">![Define custom connectors for CAC network topology](images/JJ945604.b20bea67-c8e1-453e-b1dd-e2aa17b62566(OCS.15).jpg "Define custom connectors for CAC network topology")</span></span>

<span data-ttu-id="8047c-544">**查看 CAC 网络拓扑网站信息、区域信息和预配的带宽策略：** Lync Server 2013 管理员可以通过使用下面所示的选项查看相关的 CAC 网络区域信息、网站信息和 CAC 带宽设置信息。</span><span class="sxs-lookup"><span data-stu-id="8047c-544">**View CAC network topology site information, region information, and provisioned bandwidth policies:** Lync Server 2013 administrators can view related CAC network region information, site information, and CAC bandwidth provisioning information by using options shown below.</span></span> <span data-ttu-id="8047c-545">（例如，单击 "网络区域" 或 "网络站点" 对象中的 "**信息**"。）</span><span class="sxs-lookup"><span data-stu-id="8047c-545">(For example, click **Info** in a network region or network site object.)</span></span>

<span data-ttu-id="8047c-546">![为你的网络定义自定义连接器。](images/JJ945604.26262c75-4342-41c3-bc98-1793aa6a7713(OCS.15).jpg "为你的网络定义自定义连接器。")</span><span class="sxs-lookup"><span data-stu-id="8047c-546">![Defining custom connectors for your network.](images/JJ945604.26262c75-4342-41c3-bc98-1793aa6a7713(OCS.15).jpg "Defining custom connectors for your network.")</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="8047c-547">总结</span><span class="sxs-lookup"><span data-stu-id="8047c-547">Summary</span></span>

<span data-ttu-id="8047c-548">对于希望以图形格式查看其部署的 CAC 网络拓扑的 Lync Server 2013 管理员，此工具可能是一种宝贵的资源。</span><span class="sxs-lookup"><span data-stu-id="8047c-548">This tool can be a valuable resource to Lync Server 2013 administrators who would like to view CAC network topology for their deployment in a graphical format.</span></span>

</div>

</div>

<div>

## <a name="response-group-agent-live"></a><span data-ttu-id="8047c-549">响应组代理实时</span><span class="sxs-lookup"><span data-stu-id="8047c-549">Response Group Agent Live</span></span>

<span data-ttu-id="8047c-550">响应组应用程序使代理能够使用其内置 Web 服务访问有用的实时信息。</span><span class="sxs-lookup"><span data-stu-id="8047c-550">The Response Group application gives agents the ability to access useful real-time information using its built-in Web service.</span></span> <span data-ttu-id="8047c-551">遗憾的是，在应用程序外，此数据的图形视图不可用。</span><span class="sxs-lookup"><span data-stu-id="8047c-551">Unfortunately, no graphical view of this data is available outside the application.</span></span> <span data-ttu-id="8047c-552">响应组代理实时资源工具包工具解决了此问题，方法是提供一种简单且图形化的方式来访问此信息，并使用实时 Microsoft Lync 2013 通信软件信息（如其他代理的状态）进行了改进。</span><span class="sxs-lookup"><span data-stu-id="8047c-552">The Response Group Agent Live Resource Kit tool solves this issue by providing a simple and graphical way to access this information, enhanced with real-time Microsoft Lync 2013 communications software information such as the presence of other agents.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="8047c-553">说明</span><span class="sxs-lookup"><span data-stu-id="8047c-553">Description</span></span>

<span data-ttu-id="8047c-554">响应组代理 Live 是一种 Windows 应用程序，它向响应组代理提供登录和注销功能以及一些实时信息（如组成员身份和当前呼叫数）。</span><span class="sxs-lookup"><span data-stu-id="8047c-554">Response Group Agent Live is a Windows application that provides sign-in and sign-out functionality and some real-time information (such as group membership and current number of calls) to Response Group agents.</span></span> <span data-ttu-id="8047c-555">它应是 "代理组" 页面的增强版本（可从 Lync 2013 访问）。</span><span class="sxs-lookup"><span data-stu-id="8047c-555">It is meant to be an enhanced version of the Agent Groups page (accessible from Lync 2013.</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="8047c-556">用途</span><span class="sxs-lookup"><span data-stu-id="8047c-556">Purpose</span></span>

<span data-ttu-id="8047c-557">响应组应用程序对传入呼叫进行排队，然后将其路由到代理组。</span><span class="sxs-lookup"><span data-stu-id="8047c-557">The Response Group application queues incoming calls, and then routes them to agent groups.</span></span> <span data-ttu-id="8047c-558">为了对要服务的呼叫做出有根据的决定，代理可以访问有关其代理组的实时信息，例如，哪些其他代理可用以及每个队列中等待的呼叫数。</span><span class="sxs-lookup"><span data-stu-id="8047c-558">To make informed decisions about which calls to service, agents can access real-time information about their agent groups, such as what other agents are available and how many calls are waiting in each queue.</span></span> <span data-ttu-id="8047c-559">最初仅可通过响应组服务访问的此信息将以直观方式由响应组代理实时提供。</span><span class="sxs-lookup"><span data-stu-id="8047c-559">This information, initially accessible only through the Response Group service, is made available in an intuitive way by Response Group Agent Live.</span></span>

<div>

## <a name="features"></a><span data-ttu-id="8047c-560">功能</span><span class="sxs-lookup"><span data-stu-id="8047c-560">Features</span></span>

<span data-ttu-id="8047c-561">响应组代理 Live 工具建立在响应组服务和 Microsoft Lync 2013 SDK 之上。</span><span class="sxs-lookup"><span data-stu-id="8047c-561">The Response Group Agent Live tool is built on the Response Group service and the Microsoft Lync 2013 SDK.</span></span> <span data-ttu-id="8047c-562">它提供响应组代理响应组服务提供的信息和功能（如组成员身份、其他代理的状态以及等待呼叫数）。</span><span class="sxs-lookup"><span data-stu-id="8047c-562">It provides Response Group agents the information and capabilities that are available from the Response Group service (such as group membership, presence of other agents, and number of waiting calls).</span></span>

<span data-ttu-id="8047c-563">下图展示了响应组代理的主接口。</span><span class="sxs-lookup"><span data-stu-id="8047c-563">The figure below illustrates the main interface of Response Group Agent Live.</span></span>

<span data-ttu-id="8047c-564">![响应组代理 Live 工具。](images/JJ945604.63cb0374-a6ef-4a59-b60e-bec86a880d09(OCS.15).jpg "响应组代理 Live 工具。")</span><span class="sxs-lookup"><span data-stu-id="8047c-564">![The Response Group Agent Live tool.](images/JJ945604.63cb0374-a6ef-4a59-b60e-bec86a880d09(OCS.15).jpg "The Response Group Agent Live tool.")</span></span>

<span data-ttu-id="8047c-565">以下三个主要功能可用于响应组代理 Live 中的代理：</span><span class="sxs-lookup"><span data-stu-id="8047c-565">The following three main features are available for agents in Response Group Agent Live:</span></span>

  - <span data-ttu-id="8047c-566">**登录/注销：** 与 "代理组" 页相反（可从 Lync 2013 访问），响应组代理 Live 仅允许代理同时登录或注销所有代理组。</span><span class="sxs-lookup"><span data-stu-id="8047c-566">**Sign-in/out:** Contrary to the Agent Groups page (accessible from Lync 2013), Response Group Agent Live allows only agents to sign-in or out of all agent groups at once.</span></span> <span data-ttu-id="8047c-567">此应用程序提供了三种快速代理登录或注销的方法：</span><span class="sxs-lookup"><span data-stu-id="8047c-567">This application provides three quick ways for agents to sign in or out:</span></span>
    
      - <span data-ttu-id="8047c-568">单击应用程序中的 "登录/注销" （绿色和红色）按钮。</span><span class="sxs-lookup"><span data-stu-id="8047c-568">Click the Sign-in/out (green and red) buttons within the application.</span></span>
    
      - <span data-ttu-id="8047c-569">右键单击 "系统" 任务栏图标，并选择 "登录" 或 "注销"。</span><span class="sxs-lookup"><span data-stu-id="8047c-569">Right-click the system tray icon, and select sign in or sign out.</span></span>
    
      - <span data-ttu-id="8047c-570">使用可配置的键盘快捷方式。</span><span class="sxs-lookup"><span data-stu-id="8047c-570">Using configurable keyboard shortcuts.</span></span>

  - <span data-ttu-id="8047c-571">**组成员身份：** 如果选择了代理组，响应组代理 Live 将在右侧窗格中显示此组中的代理列表。</span><span class="sxs-lookup"><span data-stu-id="8047c-571">**Group membership:** When an agent group is selected, Response Group Agent Live displays the list of agents in this group in the right pane.</span></span> <span data-ttu-id="8047c-572">如果 Lync 2013 在此应用程序所在的同一台计算机上运行，状态信息和联系人卡片将显示在响应组代理 Live 中。</span><span class="sxs-lookup"><span data-stu-id="8047c-572">If Lync 2013 is running on the same computer as this application, presence information and the contact card are displayed in the Response Group Agent Live.</span></span> <span data-ttu-id="8047c-573">代理可以直接从那里发送即时消息或呼叫其他代理。</span><span class="sxs-lookup"><span data-stu-id="8047c-573">Agents can send an IM or call other agents directly from there.</span></span>

  - <span data-ttu-id="8047c-574">**实时统计信息：** 响应组代理 Live 提供所有代理组的实时统计信息。</span><span class="sxs-lookup"><span data-stu-id="8047c-574">**Real-time statistics:** Response Group Agent Live provides real-time statistics for all agent groups.</span></span> <span data-ttu-id="8047c-575">更新频率为一分钟。</span><span class="sxs-lookup"><span data-stu-id="8047c-575">The update frequency is one minute.</span></span> <span data-ttu-id="8047c-576">当响应组接听呼叫时，将在组名称旁边添加当前已排队呼叫的可视指示器。</span><span class="sxs-lookup"><span data-stu-id="8047c-576">When a call is answered by a Response Group, a visual indicator is added next to the group name with the current number of queued calls.</span></span> <span data-ttu-id="8047c-577">将指针暂停在某个组上还会显示最长等待时间。</span><span class="sxs-lookup"><span data-stu-id="8047c-577">Pausing the pointer over a group also displays the longest waiting time.</span></span>

</div>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="8047c-578">Requirements</span><span class="sxs-lookup"><span data-stu-id="8047c-578">Requirements</span></span>

<span data-ttu-id="8047c-579">响应组代理 Live 需要 .NET Framework 4.0。</span><span class="sxs-lookup"><span data-stu-id="8047c-579">Response Group Agent Live requires the .NET Framework 4.0.</span></span> <span data-ttu-id="8047c-580">此外，若要利用状态和联系人卡片功能，必须在本地安装 Lync 2013 （并运行）。</span><span class="sxs-lookup"><span data-stu-id="8047c-580">In addition, to take advantage of the presence and contact card features, Lync 2013 must be installed locally (and be running).</span></span>

<div>

## <a name="configuration"></a><span data-ttu-id="8047c-581">配置</span><span class="sxs-lookup"><span data-stu-id="8047c-581">Configuration</span></span>

<span data-ttu-id="8047c-582">通过使用应用程序中的 "选项" 对话框，可以将响应组代理 Live 自定义为单个首选项。</span><span class="sxs-lookup"><span data-stu-id="8047c-582">Response Group Agent Live can be customized to individual preferences by using the Options dialog box in the application.</span></span> <span data-ttu-id="8047c-583">此外，管理员还可以通过直接编辑 RGAgentLive 文件的 defaultHostAddress 属性来定义默认的主机地址。</span><span class="sxs-lookup"><span data-stu-id="8047c-583">In addition, the administrator can define the default host address by editing directly the defaultHostAddress property of the RGAgentLive.exe.config file.</span></span>

<span data-ttu-id="8047c-584">下图说明了代理可用于配置主机地址和快捷键的 "选项" 对话框。</span><span class="sxs-lookup"><span data-stu-id="8047c-584">The figure below illustrates the Options dialog box that agents can use to configure the host address and shortcut keys.</span></span> <span data-ttu-id="8047c-585">通过单击主界面右上方的 "选项" 按钮可访问此对话框。</span><span class="sxs-lookup"><span data-stu-id="8047c-585">This dialog is accessed by clicking the Options button on the top right of the main interface.</span></span>

<span data-ttu-id="8047c-586">!["响应组代理实时选项" 对话框。](images/JJ945604.3cc15e29-8699-45ab-90c3-e1565fa6ebf6(OCS.15).jpg ""响应组代理实时选项" 对话框。")</span><span class="sxs-lookup"><span data-stu-id="8047c-586">![The Response Group Agent Live Options dialog box.](images/JJ945604.3cc15e29-8699-45ab-90c3-e1565fa6ebf6(OCS.15).jpg "The Response Group Agent Live Options dialog box.")</span></span>

<span data-ttu-id="8047c-587">可以在响应组代理 Live 配置中自定义以下三种不同的设置：</span><span class="sxs-lookup"><span data-stu-id="8047c-587">The following three different settings can be customized in the Response Group Agent Live configuration:</span></span>

  - <span data-ttu-id="8047c-588">主机地址：这通常是属于代理主池的 web 池 FQDN。</span><span class="sxs-lookup"><span data-stu-id="8047c-588">Host address: This is typically the web pool FQDN belonging to the agent’s home pool.</span></span> <span data-ttu-id="8047c-589">确切的响应组服务地址将自动从此信息的后台派生（通过在主机后面追加正确的路径）。</span><span class="sxs-lookup"><span data-stu-id="8047c-589">The exact Response Group service address is automatically derived in the background from this information (by appending the right path after the host).</span></span>

  - <span data-ttu-id="8047c-590">快捷方式：可以自定义登录/注销的确切快捷方式。</span><span class="sxs-lookup"><span data-stu-id="8047c-590">Shortcuts: The exact shortcuts to sign-in/out can be customized.</span></span> <span data-ttu-id="8047c-591">唯一的限制是，这两个快捷方式都必须包含 "Windows 徽标" 键（除了至少一个密钥）。</span><span class="sxs-lookup"><span data-stu-id="8047c-591">The only limitation is that both shortcuts must contain the “Windows Logo” key (in addition to at least another key).</span></span>

  - <span data-ttu-id="8047c-592">从 Windows 开始：可以将应用程序配置为在 Windows 中自动启动。</span><span class="sxs-lookup"><span data-stu-id="8047c-592">Start with Windows: The application can be configured to start automatically with Windows.</span></span>

</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="8047c-593">示例</span><span class="sxs-lookup"><span data-stu-id="8047c-593">Examples</span></span>

<span data-ttu-id="8047c-594">下图说明了如何通过右键单击右侧窗格中的联系人呼叫或发送 IM 到另一个代理。</span><span class="sxs-lookup"><span data-stu-id="8047c-594">The figure below illustrates how to call or send an IM to another agent by right-clicking the contact in the right pane.</span></span>

<span data-ttu-id="8047c-595">![发出呼叫或发送即时消息。](images/JJ945604.009cebe0-5a93-4745-89c3-8a16c7c13009(OCS.15).jpg "发出呼叫或发送即时消息。")</span><span class="sxs-lookup"><span data-stu-id="8047c-595">![Making a call or sending an IM.](images/JJ945604.009cebe0-5a93-4745-89c3-8a16c7c13009(OCS.15).jpg "Making a call or sending an IM.")</span></span>

<span data-ttu-id="8047c-596">下图说明了响应组代理实时如何显示队列中的当前呼叫数以及所有这些传入呼叫中的最长等待时间。</span><span class="sxs-lookup"><span data-stu-id="8047c-596">The figure below illustrates how Response Group Agent Live displays the current number of calls in the queue and the longest waiting time among all these incoming calls.</span></span>

<span data-ttu-id="8047c-597">![查看队列信息。](images/JJ945604.131d7f79-b7ed-41f5-a9da-ffc556e31037(OCS.15).jpg "查看队列信息。")</span><span class="sxs-lookup"><span data-stu-id="8047c-597">![Viewing queue information.](images/JJ945604.131d7f79-b7ed-41f5-a9da-ffc556e31037(OCS.15).jpg "Viewing queue information.")</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="8047c-598">总结</span><span class="sxs-lookup"><span data-stu-id="8047c-598">Summary</span></span>

<span data-ttu-id="8047c-599">快速登录和注销、组成员身份和基本实时统计信息是仅在来自响应组服务的应用程序外部可用的响应组代理功能。</span><span class="sxs-lookup"><span data-stu-id="8047c-599">Fast sign-in and sign-out, group membership, and basic real-time statistics are interesting Response Group agent features that are only available outside the application from the Response Group service.</span></span> <span data-ttu-id="8047c-600">通过 "响应组代理实时资源工具包" 工具，Lync 管理员可以向其代理提供 Windows 应用程序，使其能够以更快速的图形方式执行任务。</span><span class="sxs-lookup"><span data-stu-id="8047c-600">With the Response Group Agent Live Resource Kit tool, Lync administrators can provide their agents with a Windows application that allows them to perform tasks in a faster and graphical way.</span></span>

</div>

</div>

<div>

## <a name="sefautil"></a><span data-ttu-id="8047c-601">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="8047c-601">SEFAUtil</span></span>

<span data-ttu-id="8047c-602">SEFAUtil （辅助扩展功能激活）是一种命令行工具，可让 Microsoft Lync Server 2013 通信软件管理员和支持人员代理配置代理响铃、呼叫转接、同时响铃、团队呼叫代表 Lync Server 2013 用户的设置和组呼叫应答。</span><span class="sxs-lookup"><span data-stu-id="8047c-602">SEFAUtil (secondary extension feature activation) is a command-line tool that enables Microsoft Lync Server 2013 communications software administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Lync Server 2013 user.</span></span> <span data-ttu-id="8047c-603">该工具还允许管理员查询为特定用户发布的呼叫路由设置。使用 SEFAUtil 工具，管理员可以代表用户启用/禁用/修改呼叫转接或同时响铃。</span><span class="sxs-lookup"><span data-stu-id="8047c-603">The tool also allows administrators to query the call-routing settings that are published for a particular user.The SEFAUtil tool allows the administrator to enable/disable/modify call forwarding or simultaneously ringing on behalf of the user.</span></span> <span data-ttu-id="8047c-604">管理员可以指定目标（采用 SIP URI 的形式），也可以使用用户已发布的目标。</span><span class="sxs-lookup"><span data-stu-id="8047c-604">The administrator can specify the target (in the form of a SIP URI) or use a target that has already been published by the user.</span></span> <span data-ttu-id="8047c-605">此工具还允许管理员代表用户添加或删除代理人或团队呼叫组成员。此工具建立在 Microsoft 统一通信托管 API （UCMA）3.0 的基础上，并要求管理员在中央管理存储中为 SEFAUtil 创建受信任的应用程序</span><span class="sxs-lookup"><span data-stu-id="8047c-605">This tool also allows administrators to add or remove delegates or team-call group members on behalf of the user.This tool is built on Microsoft Unified Communications Managed API (UCMA) 3.0 and requires that administrators create a trusted application in the Central Management store for SEFAUtil</span></span>

<span data-ttu-id="8047c-606">SEFAUtil （辅助扩展功能激活）使 Lync Server 2013 管理员和支持人员代理能够代表 Lync Server 2013 用户配置代理响铃、呼叫转接、同时响铃、团队呼叫设置和组呼叫应答.</span><span class="sxs-lookup"><span data-stu-id="8047c-606">SEFAUtil (secondary extension feature activation) enables Lync Server 2013 administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Lync Server 2013 user.</span></span> <span data-ttu-id="8047c-607">此工具还允许管理员查询为特定用户发布的呼叫路由设置。</span><span class="sxs-lookup"><span data-stu-id="8047c-607">This tool also allows administrators to query the call-routing settings that are published for a particular user.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="8047c-608">说明</span><span class="sxs-lookup"><span data-stu-id="8047c-608">Description</span></span>

<span data-ttu-id="8047c-609">SEFAUtil 的当前版本只是一个命令行工具;不支持图形用户界面。</span><span class="sxs-lookup"><span data-stu-id="8047c-609">The current version of SEFAUtil is only a command-line tool; there is no supporting graphical user interface.</span></span> <span data-ttu-id="8047c-610">此工具基于 Microsoft 统一通信托管 API （UCMA）3.0。</span><span class="sxs-lookup"><span data-stu-id="8047c-610">This tool is based on Microsoft Unified Communications Managed API (UCMA) 3.0.</span></span> <span data-ttu-id="8047c-611">此工具中的功能允许管理员和支持人员代理执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="8047c-611">The features in this tool allow administrators and helpdesk agents to do the following:</span></span>

  - <span data-ttu-id="8047c-612">查看用户的所有呼叫路由设置（包括呼叫转接、委派、同时响铃、团队呼叫和组呼叫装货）</span><span class="sxs-lookup"><span data-stu-id="8047c-612">View all call routing settings for a user (includes call-forwarding, delegation, simultaneous ringing, team-call and group call pickup)</span></span>

  - <span data-ttu-id="8047c-613">启用/禁用/修改呼叫转接设置（包括目标和无应答计时器）</span><span class="sxs-lookup"><span data-stu-id="8047c-613">Enable/disable/modify call-forwarding setting (includes destination and no-answer timer)</span></span>

  - <span data-ttu-id="8047c-614">启用/禁用/修改呼叫转接即时配置</span><span class="sxs-lookup"><span data-stu-id="8047c-614">Enable/disable/modify call-forwarding immediate configurations</span></span>

  - <span data-ttu-id="8047c-615">启用/禁用/修改委派设置</span><span class="sxs-lookup"><span data-stu-id="8047c-615">Enable/disable/modify delegation settings</span></span>

  - <span data-ttu-id="8047c-616">启用/禁用/修改团队呼叫组设置</span><span class="sxs-lookup"><span data-stu-id="8047c-616">Enable/disable/modify team-call group settings</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8047c-617">Lync Server 2013 SEFAUtil 工具中的新增工具</span><span class="sxs-lookup"><span data-stu-id="8047c-617">New in Lync Server 2013 SEFAUtil tool</span></span>

    
    </div>

  - <span data-ttu-id="8047c-618">启用/禁用/修改同时响铃设置（包括目标）</span><span class="sxs-lookup"><span data-stu-id="8047c-618">Enable/disable/modify simultaneous ringing settings (includes destination)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8047c-619">Lync Server 2013 SEFAUtil 工具中的新增工具</span><span class="sxs-lookup"><span data-stu-id="8047c-619">New in Lync Server 2013 SEFAUtil tool</span></span>

    
    </div>

  - <span data-ttu-id="8047c-620">启用/禁用/修改组呼叫装货设置</span><span class="sxs-lookup"><span data-stu-id="8047c-620">Enable/disable/modify group call pickup settings</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="8047c-621">Lync Server 2013 SEFAUtil 工具中的新增工具</span><span class="sxs-lookup"><span data-stu-id="8047c-621">New in Lync Server 2013 SEFAUtil tool</span></span>

    
    </div>

<span data-ttu-id="8047c-622">此工具具有以下限制：</span><span class="sxs-lookup"><span data-stu-id="8047c-622">This tool has the following limitations:</span></span>

  - <span data-ttu-id="8047c-623">仅对驻留在 Lync Server 池中的用户受支持</span><span class="sxs-lookup"><span data-stu-id="8047c-623">Supported only for users homed in a Lync Server pool</span></span>

  - <span data-ttu-id="8047c-624">不支持批量编辑多个用户的呼叫路由设置</span><span class="sxs-lookup"><span data-stu-id="8047c-624">Bulk-edit of call routing settings for several users is not supported</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="8047c-625">Output</span><span class="sxs-lookup"><span data-stu-id="8047c-625">Output</span></span>

<span data-ttu-id="8047c-626">此工具的当前版本仅在命令提示符窗口中提供输出。</span><span class="sxs-lookup"><span data-stu-id="8047c-626">The current version of this tool provides output only in the Command Prompt window.</span></span> <span data-ttu-id="8047c-627">有关详细信息，请参阅本文档后面的示例部分。</span><span class="sxs-lookup"><span data-stu-id="8047c-627">For details, see the Examples section later in this document.</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="8047c-628">用途</span><span class="sxs-lookup"><span data-stu-id="8047c-628">Purpose</span></span>

<span data-ttu-id="8047c-629">以下是可能使用此工具的一些关键方案：</span><span class="sxs-lookup"><span data-stu-id="8047c-629">Following are some of the key scenarios where this tool may be used:</span></span>

  - <span data-ttu-id="8047c-630">小明是一名行政人员，已移至 Lync Server 电话服务。</span><span class="sxs-lookup"><span data-stu-id="8047c-630">Bob is an executive and has been moved to Lync Server telephony.</span></span> <span data-ttu-id="8047c-631">他在其现有的 PBX 系统上拥有委派。</span><span class="sxs-lookup"><span data-stu-id="8047c-631">He has delegation on his existing PBX system.</span></span> <span data-ttu-id="8047c-632">作为移动到 Lync 的一部分，管理员可以配置王俊元的路由，以反映其预先存在的委派配置。</span><span class="sxs-lookup"><span data-stu-id="8047c-632">As part of the move to Lync, the administrator is able to configure Bob’s routing to reflect his pre-existing delegation configuration.</span></span>

  - <span data-ttu-id="8047c-633">Alice 正在出差，认识到她需要来自一个客户的重要呼叫。</span><span class="sxs-lookup"><span data-stu-id="8047c-633">Alice is travelling and realizes that she is expecting an important call from one of her customers.</span></span> <span data-ttu-id="8047c-634">但是，她在宾馆中，没有对计算机的访问权限。</span><span class="sxs-lookup"><span data-stu-id="8047c-634">However, she is in a hotel and has no access to a computer.</span></span> <span data-ttu-id="8047c-635">她呼叫帮助台并请求将其转接至移动电话号码对她的工作电话号码的所有呼叫。</span><span class="sxs-lookup"><span data-stu-id="8047c-635">She calls the helpdesk and requests that they forward to her mobile number all the calls made to her work number.</span></span> <span data-ttu-id="8047c-636">帮助台人员可以代表她进行配置。</span><span class="sxs-lookup"><span data-stu-id="8047c-636">The helpdesk personnel are able to do the configuration on her behalf.</span></span>

  - <span data-ttu-id="8047c-637">当用户在工作时，Joe 对他的工作电话号码的呼叫将进入移动电话语音邮件;但是，在大多数其他位置看似乎工作正常。</span><span class="sxs-lookup"><span data-stu-id="8047c-637">Joe’s calls to his work number are going to his mobile voicemail whenever he is at work; however, things appear to be working correctly in most other locations.</span></span> <span data-ttu-id="8047c-638">帮助台技术人员可以查看 Joe 的路由配置，并发现 Joe 已将呼叫配置为移动电话。</span><span class="sxs-lookup"><span data-stu-id="8047c-638">The helpdesk technician is able to view Joe’s routing configuration and discovers that Joe has simultaneous ringing configured to his mobile phone.</span></span> <span data-ttu-id="8047c-639">技术人员在他的办公室中向 Joe 提问，并能够确定同时响铃的规则是，当网络覆盖范围较差时，会导致呼叫进入 Joe 的移动语音邮件。</span><span class="sxs-lookup"><span data-stu-id="8047c-639">The technician asks Joe about the mobile coverage at his office and is able to determine that the simultaneous ringing rule is what is causing the calls to go to Joe’s mobile voicemail when his network coverage is poor.</span></span>

  - <span data-ttu-id="8047c-640">Mike 是 Contoso 的新员工，他加入了一个新团队，在该团队中为团队呼叫配置所有成员后，在为 Microsoft Lync 启用时，管理员可以将他的团队呼叫组设置设置为包含所有新团队成员，此外，管理员将 Mike 添加为团队中每个成员的团队呼叫组成员。</span><span class="sxs-lookup"><span data-stu-id="8047c-640">Mike is a new employee at Contoso and he’s joining a new team on which all members are configured for team-call, when being enabled for Microsoft Lync, the administrator is able to set his team-call group settings to include all his new team members, additionally, the administrator adds Mike as a team-call group member for each of the members in his team.</span></span>

  - <span data-ttu-id="8047c-641">Contoso 中的人力资源部门的客户服务实践是在第一次呼叫后为所有呼叫者提供个人服务。</span><span class="sxs-lookup"><span data-stu-id="8047c-641">A customer service practice in the human resources department at Contoso is to provide personal service for all callers since the first call.</span></span> <span data-ttu-id="8047c-642">如果部门的所有成员都非常接近，团队呼叫将同时拨打所有电话，同时对团队造成中断。</span><span class="sxs-lookup"><span data-stu-id="8047c-642">Given that all members of the department sit very close to each other, having all phones ringing at the same time with team-call is very disruptive for the team.</span></span> <span data-ttu-id="8047c-643">若要在不中断团队成员的情况下提供最佳服务，Lync 管理员可以利用组呼叫应答功能。</span><span class="sxs-lookup"><span data-stu-id="8047c-643">To provide the best service without disrupting the team members, the Lync administrator takes advantage of the Group Call Pickup capability.</span></span> <span data-ttu-id="8047c-644">管理员将所有部门成员添加到一个装货组，并向该部门传达装货组编号。</span><span class="sxs-lookup"><span data-stu-id="8047c-644">The administrator adds all department members to a pickup group and communicates to the department the pickup group number.</span></span> <span data-ttu-id="8047c-645">当她的办公桌中缺少 Samantha 时，Joe 会通知她的电话响铃，他将继续应答来自他的办公桌的呼叫。</span><span class="sxs-lookup"><span data-stu-id="8047c-645">When Samantha is absent from her desk, Joe notices her phone ringing and he proceeds to answer the call from his desk.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="8047c-646">Requirements</span><span class="sxs-lookup"><span data-stu-id="8047c-646">Requirements</span></span>

<span data-ttu-id="8047c-647">SEFAUtil 工具只能在属于受信任应用程序池一部分的计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="8047c-647">The SEFAUtil tool can be run only on a computer that is a part of a Trusted Application Pool.</span></span> <span data-ttu-id="8047c-648">UCMA 3.0 必须安装在该计算机上。</span><span class="sxs-lookup"><span data-stu-id="8047c-648">UCMA 3.0 must be installed on that computer.</span></span> <span data-ttu-id="8047c-649">若要运行该工具，必须在该池上创建一个具有 SEFAUtil 应用程序 ID 的新受信任应用程序。</span><span class="sxs-lookup"><span data-stu-id="8047c-649">To run the tool, a new Trusted Application with the SEFAUtil application ID must be created on that pool.</span></span>

<span data-ttu-id="8047c-650">**为 SEFAUtil 工具创建新的受信任应用程序**</span><span class="sxs-lookup"><span data-stu-id="8047c-650">**Creating a new Trusted Application for the SEFAUtil tool**</span></span>

1.  <span data-ttu-id="8047c-651">SEFAUTil 工具只能在属于受信任应用程序池一部分的计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="8047c-651">The SEFAUTil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="8047c-652">如果需要，可以通过 Lync Server 命令行管理程序将池添加为新的受信任应用程序池，其中包含以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="8047c-652">If needed, adding a pool as a new trusted application pool can be done via the Lync Server Management Shell with the following cmdlet:</span></span>
    
        New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8047c-653">UCMA 3.0 必须安装在将用于运行 SEFAUtil 工具的任何计算机上。</span><span class="sxs-lookup"><span data-stu-id="8047c-653">UCMA 3.0 must be installed on any computer that will be used to run the SEFAUtil tool.</span></span>

    
    </div>

2.  <span data-ttu-id="8047c-654">需要在 SEFAUtil 工具的拓扑中定义受信任的应用程序。</span><span class="sxs-lookup"><span data-stu-id="8047c-654">A trusted application needs to be defined in the topology for the SEFAUtil tool.</span></span> <span data-ttu-id="8047c-655">若要将 SEFAUtil 定义为新的受信任应用程序，请使用 Lync Server 命令行管理程序，并执行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="8047c-655">To define SEFAUtil as a new trusted application, use the Lync Server Management Shell and execute the following cmdlet:</span></span>
    
        New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8047c-656">如果需要，可以使用其他端口。</span><span class="sxs-lookup"><span data-stu-id="8047c-656">A different port can be used if needed.</span></span>

    
    </div>

3.  <span data-ttu-id="8047c-657">需要启用拓扑更改。</span><span class="sxs-lookup"><span data-stu-id="8047c-657">The topology changes need to be enabled.</span></span> <span data-ttu-id="8047c-658">通过执行以下 cmdlet，可以通过 Lync Server 命令行管理程序来启用拓扑更改：</span><span class="sxs-lookup"><span data-stu-id="8047c-658">Enabling the topology changes can be done via the Lync Server Management Shell by executing the following cmdlet:</span></span>
    
        Enable-CsToplogy

4.  <span data-ttu-id="8047c-659">如果需要，请在将用于运行 SEFAUtil 工具的服务器中安装 Lync Server 2013 资源工具包工具（该服务器必须是受信任的应用程序池的一部分）。</span><span class="sxs-lookup"><span data-stu-id="8047c-659">If needed, install the Lync Server 2013 Resource Kit Tools in the server that will be used to run the SEFAUtil tool (the server must be part of a trusted application pool).</span></span>

5.  <span data-ttu-id="8047c-660">验证 SEFAUtil 是否正常运行。</span><span class="sxs-lookup"><span data-stu-id="8047c-660">Verify the SEFAUtil is running correctly.</span></span> <span data-ttu-id="8047c-661">为此，请从具有管理员权限的 windows 命令提示符处运行该工具，以在部署中显示用户的呼叫转接设置。</span><span class="sxs-lookup"><span data-stu-id="8047c-661">To do this, run the tool from a windows command prompt with administrator privileges to display the call forwarding settings of a user in the deployment.</span></span> <span data-ttu-id="8047c-662">默认情况下，该工具将位于： ".。。\\Program Files\\Microsoft Lync Server 2013\\\reskit "。</span><span class="sxs-lookup"><span data-stu-id="8047c-662">By default the tool will be located in: “…\\Program Files\\Microsoft Lync Server 2013\\Reskit”.</span></span> <span data-ttu-id="8047c-663">若要显示用户的呼叫转接设置，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="8047c-663">To display the call forwarding settings of a user, use the following command:</span></span>
    
        SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
    
    <span data-ttu-id="8047c-664">应显示用户的呼叫转接设置。</span><span class="sxs-lookup"><span data-stu-id="8047c-664">The call forwarding settings of the user should be displayed.</span></span>

<div>

## <a name="group-call-pickup"></a><span data-ttu-id="8047c-665">组间电话提货</span><span class="sxs-lookup"><span data-stu-id="8047c-665">Group Call Pickup</span></span>

<span data-ttu-id="8047c-666">组内呼叫应答需要在 Lync Server 中进行其他配置，才能完全启用此功能。</span><span class="sxs-lookup"><span data-stu-id="8047c-666">Group Call Pickup requires additional configuration in Lync Server for the capability to be fully enabled.</span></span> <span data-ttu-id="8047c-667">在向用户分配分拣组之前，请参阅组的 "呼叫装货产品文档"，了解此功能的规划和部署步骤。</span><span class="sxs-lookup"><span data-stu-id="8047c-667">Before assigning pickup groups to users, refer to the Group Call Pickup product documentation for the planning and deployment steps of this capability.</span></span>

</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="8047c-668">示例</span><span class="sxs-lookup"><span data-stu-id="8047c-668">Examples</span></span>

<div>

## <a name="display-current-call-handling-settings"></a><span data-ttu-id="8047c-669">显示当前呼叫处理设置</span><span class="sxs-lookup"><span data-stu-id="8047c-669">Display Current Call Handling Settings</span></span>

<span data-ttu-id="8047c-670">以下命令将显示用户的呼叫处理。</span><span class="sxs-lookup"><span data-stu-id="8047c-670">The following command displays the call handling for the user.</span></span> `SEFAUtil.exe /server:lyncserver.contoso.com katarina@contoso.com`

<div>


> [!NOTE]  
> <span data-ttu-id="8047c-671">此示例使用<STRONG>/server</STRONG>开关指定要连接到的 Lync server。</span><span class="sxs-lookup"><span data-stu-id="8047c-671">This example uses the <STRONG>/server</STRONG> switch to specify the Lync Server to connect to.</span></span>



</div>

<span data-ttu-id="8047c-672">"输出"</span><span class="sxs-lookup"><span data-stu-id="8047c-672">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:20
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="set-the-call-forwardno-answer-destination"></a><span data-ttu-id="8047c-673">设置呼叫转接/无应答目的地</span><span class="sxs-lookup"><span data-stu-id="8047c-673">Set the Call Forward/No Answer Destination</span></span>

<span data-ttu-id="8047c-674">本示例设置呼叫转接/无应答目的地和环延迟。</span><span class="sxs-lookup"><span data-stu-id="8047c-674">This example sets the call forward/no answer destination and the ring delay.</span></span> <span data-ttu-id="8047c-675">这里不提供/server 开关;SEFAUtil 尝试自动发现 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="8047c-675">Here, the /server switch is not provided; SEFAUtil attempts to autodiscover the Lync Server.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /enablefwdnoanswer /callanswerwaittime:30 /setfwddestination:+1425555 0126@contoso.com;user=phone

<span data-ttu-id="8047c-676">"输出"</span><span class="sxs-lookup"><span data-stu-id="8047c-676">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: sip:+14255550126@contoso.com;user=phone

</div>

<div>

## <a name="enable-call-forwarding-immediately"></a><span data-ttu-id="8047c-677">立即启用呼叫转接</span><span class="sxs-lookup"><span data-stu-id="8047c-677">Enable Call Forwarding Immediately</span></span>

<span data-ttu-id="8047c-678">此示例立即启用到另一个用户的呼叫转接。</span><span class="sxs-lookup"><span data-stu-id="8047c-678">This example immediately enables call-forwarding to another user.</span></span>

    SEFAUtil.exe sip:katarina@contoso.com /enablefwdimmediate /setfwddestination:anders@contoso.com

<span data-ttu-id="8047c-679">"输出"</span><span class="sxs-lookup"><span data-stu-id="8047c-679">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    Forward immediate to: sip:anders@contoso.com

</div>

<div>

## <a name="disable-call-forwarding-immediately"></a><span data-ttu-id="8047c-680">立即禁用呼叫转接</span><span class="sxs-lookup"><span data-stu-id="8047c-680">Disable Call Forwarding Immediately</span></span>

<span data-ttu-id="8047c-681">本示例将立即禁用呼叫转接。</span><span class="sxs-lookup"><span data-stu-id="8047c-681">This example immediately disables call forwarding.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com katarina@contoso.com  /disablefwdimmediate

<span data-ttu-id="8047c-682">"输出"</span><span class="sxs-lookup"><span data-stu-id="8047c-682">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-user-as-a-delegate-and-set-up-simultaneous-ringing-of-delegates"></a><span data-ttu-id="8047c-683">将用户添加为代理人并设置代理人的同时响铃</span><span class="sxs-lookup"><span data-stu-id="8047c-683">Add a User as a Delegate and Set Up Simultaneous Ringing of Delegates</span></span>

<span data-ttu-id="8047c-684">本示例将用户添加为代理人并设置代理人的同时响铃。</span><span class="sxs-lookup"><span data-stu-id="8047c-684">This example adds a user as a delegate and sets up simultaneous ringing of delegates.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /adddelegate:joe@contoso.com /simulringdelegates

<span data-ttu-id="8047c-685">"输出"</span><span class="sxs-lookup"><span data-stu-id="8047c-685">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simultaneously Ringing Delegates: sip:joe@contoso.com

</div>

<div>

## <a name="change-simultaneous-ringing-rule-of-delegates"></a><span data-ttu-id="8047c-686">更改代理人的同时响铃规则</span><span class="sxs-lookup"><span data-stu-id="8047c-686">Change Simultaneous Ringing Rule of Delegates</span></span>

<span data-ttu-id="8047c-687">本示例将上一示例中设置的同时响铃规则更改为延迟的震铃规则。</span><span class="sxs-lookup"><span data-stu-id="8047c-687">This example changes the simultaneous ringing rule that was set in the previous example to the delayed ringing rule.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /delayringdelegates:10

<span data-ttu-id="8047c-688">"输出"</span><span class="sxs-lookup"><span data-stu-id="8047c-688">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    Delay Ringing Delegates (delay:10 seconds): sip:joe@contoso.com

</div>

<div>

## <a name="remove-the-delegate"></a><span data-ttu-id="8047c-689">删除委派</span><span class="sxs-lookup"><span data-stu-id="8047c-689">Remove the Delegate</span></span>

<span data-ttu-id="8047c-690">本示例删除代理。</span><span class="sxs-lookup"><span data-stu-id="8047c-690">This example removes the delegate.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8047c-691">删除最后一个委派时，将自动禁用委派震铃。</span><span class="sxs-lookup"><span data-stu-id="8047c-691">When the last delegate is removed, delegate ringing is automatically disabled.</span></span>



</div>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /removedelegate:joe@contoso.com

<span data-ttu-id="8047c-692">"输出"</span><span class="sxs-lookup"><span data-stu-id="8047c-692">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-delegate-and-set-up-the-call-forward-to-delegates-rule"></a><span data-ttu-id="8047c-693">添加代理并设置呼叫转发到代理人规则</span><span class="sxs-lookup"><span data-stu-id="8047c-693">Add a Delegate and Set Up the Call-Forward to Delegates Rule</span></span>

<span data-ttu-id="8047c-694">本示例添加一个代理人并设置 "呼叫前转到代理人" 规则。</span><span class="sxs-lookup"><span data-stu-id="8047c-694">This example adds a delegate and sets up the call-forward to delegates rule.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /adddelegate:anders@contoso.com /fwdtodelegates

<span data-ttu-id="8047c-695">"输出"</span><span class="sxs-lookup"><span data-stu-id="8047c-695">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Forwarding calls to Delegates: sip:anders@contoso.com

</div>

<div>

## <a name="enable-simultaneous-ringing-and-set-a-destination-number"></a><span data-ttu-id="8047c-696">启用同时响铃并设置目标号码</span><span class="sxs-lookup"><span data-stu-id="8047c-696">Enable Simultaneous Ringing and Set a Destination Number</span></span>

<span data-ttu-id="8047c-697">本示例启用同时响铃并设置同时响铃的目标号码。</span><span class="sxs-lookup"><span data-stu-id="8047c-697">This example enables simultaneous ringing and sets a simultaneous ringing destination number.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /setsimulringdestination:+14255550126 /enablesimulring

<div>


> [!NOTE]  
> <span data-ttu-id="8047c-698">若要更改已启用同时响铃的用户的同时响铃的目标号码，请使用/enablesimulring 开关保留该命令，否则将不会更改目标号码。</span><span class="sxs-lookup"><span data-stu-id="8047c-698">To change the simultaneous ringing destination number of a user that has already simultaneous ringing enabled, keep the command with the /enablesimulring switch, otherwise the destination number will not be changed.</span></span>



</div>

<span data-ttu-id="8047c-699">"输出"</span><span class="sxs-lookup"><span data-stu-id="8047c-699">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: True
    Simul_Ringing to: sip:+14255550126@contoso.com;user=phone

</div>

<div>

## <a name="disable-simultaneous-ringing"></a><span data-ttu-id="8047c-700">禁用同时响铃</span><span class="sxs-lookup"><span data-stu-id="8047c-700">Disable Simultaneous Ringing</span></span>

<span data-ttu-id="8047c-701">本示例禁用同时响铃。</span><span class="sxs-lookup"><span data-stu-id="8047c-701">This example disables simultaneous ringing.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disablesimulring

<span data-ttu-id="8047c-702">"输出"</span><span class="sxs-lookup"><span data-stu-id="8047c-702">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-team-member-for-team-call-and-set-up-simultaneous-ringing-to-the-team-call-members-group"></a><span data-ttu-id="8047c-703">为团队呼叫添加团队成员，并将同时响铃设置为 "团队呼叫成员" 组</span><span class="sxs-lookup"><span data-stu-id="8047c-703">Add a Team Member for Team-Call and Set up Simultaneous Ringing to the Team-Call Members Group</span></span>

<span data-ttu-id="8047c-704">此示例向用户的团队呼叫组添加团队成员，并允许同时响铃到团队呼叫组。</span><span class="sxs-lookup"><span data-stu-id="8047c-704">This example adds a team member to the team-call group of a user and enables simultaneous ringing to the team-call group.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam

<div>


> [!NOTE]  
> <span data-ttu-id="8047c-705">将成员添加到用户的团队呼叫组将自动切换用户的同时响铃响铃，以同时他的团队呼叫组。</span><span class="sxs-lookup"><span data-stu-id="8047c-705">Adding a member to the team-call group of a user will automatically switch the simultaneous ringing settigs of the users to simulring his team-call group.</span></span>



</div>

<span data-ttu-id="8047c-706">"输出"</span><span class="sxs-lookup"><span data-stu-id="8047c-706">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Team ringing enabled. Team: sip:anders@contoso.com

</div>

<div>

## <a name="remove-a-member-from-the-team-call-group"></a><span data-ttu-id="8047c-707">从团队呼叫组中删除成员</span><span class="sxs-lookup"><span data-stu-id="8047c-707">Remove a Member from the Team-Call Group</span></span>

<span data-ttu-id="8047c-708">本示例将删除用户的团队呼叫组的团队成员。</span><span class="sxs-lookup"><span data-stu-id="8047c-708">This example removes a team member of the team-call group of a user.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /removeteammember:anders@contoso.com

<div>


> [!NOTE]  
> <span data-ttu-id="8047c-709">如果要删除的成员是团队呼叫组的唯一成员，同时响铃到团队呼叫组将自动禁用。</span><span class="sxs-lookup"><span data-stu-id="8047c-709">If the member being removed is the only member of the team-call group, simultaneously ringing to the team-call group will be automatically disabled.</span></span>



</div>

<span data-ttu-id="8047c-710">"输出"</span><span class="sxs-lookup"><span data-stu-id="8047c-710">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="set-the-delayed-ring-to-the-team-call-group"></a><span data-ttu-id="8047c-711">将延迟环设置为团队呼叫组</span><span class="sxs-lookup"><span data-stu-id="8047c-711">Set the Delayed Ring to the Team-Call Group</span></span>

<span data-ttu-id="8047c-712">本示例将延迟的环更改为 "团队呼叫组时间" 设置。</span><span class="sxs-lookup"><span data-stu-id="8047c-712">This example changes the delayed ring to the team-call group time setting.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /delayringteam:5

<span data-ttu-id="8047c-713">"输出"</span><span class="sxs-lookup"><span data-stu-id="8047c-713">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Delay Ringing Team (delay:5 seconds). Team: sip:anders@contoso.com

</div>

<div>

## <a name="enable-team-call"></a><span data-ttu-id="8047c-714">启用团队呼叫</span><span class="sxs-lookup"><span data-stu-id="8047c-714">Enable Team-Call</span></span>

<span data-ttu-id="8047c-715">此示例为给定用户启用团队呼叫。</span><span class="sxs-lookup"><span data-stu-id="8047c-715">This example enables team-call for a given user.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /simulringteam

<div>


> [!NOTE]  
> <span data-ttu-id="8047c-716">如果用户的团队呼叫组没有成员，则不会启用团队呼叫。</span><span class="sxs-lookup"><span data-stu-id="8047c-716">If the team-call group of the user has no members, team-call won’t be enabled.</span></span>



</div>

<span data-ttu-id="8047c-717">"输出"</span><span class="sxs-lookup"><span data-stu-id="8047c-717">**Output**</span></span>

</div>

<div>

## <a name="disable-team-call"></a><span data-ttu-id="8047c-718">禁用团队呼叫</span><span class="sxs-lookup"><span data-stu-id="8047c-718">Disable Team-Call</span></span>

<span data-ttu-id="8047c-719">本示例为给定用户禁用团队呼叫。</span><span class="sxs-lookup"><span data-stu-id="8047c-719">This example disables team-call for a given user.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disableteamcall

<span data-ttu-id="8047c-720">"输出"</span><span class="sxs-lookup"><span data-stu-id="8047c-720">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="enable-group-call-pickup-and-assign-a-pickup-group-to-a-user"></a><span data-ttu-id="8047c-721">启用组呼叫应答并将分拣组分配给用户</span><span class="sxs-lookup"><span data-stu-id="8047c-721">Enable Group Call Pickup and Assign a Pickup Group to a User</span></span>

<span data-ttu-id="8047c-722">本示例将一个分拣组分配给一个用户，并启用组呼叫应答。</span><span class="sxs-lookup"><span data-stu-id="8047c-722">This example assigns a pickup group to a user and enables Group Call Pickup.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /enablegrouppickup:199

<span data-ttu-id="8047c-723">"输出"</span><span class="sxs-lookup"><span data-stu-id="8047c-723">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Group Pickup Orbit: sip:199;phone-context=user-default@ contoso.com;user=phone

</div>

<div>

## <a name="disable-group-call-pickup"></a><span data-ttu-id="8047c-724">禁用组呼叫应答</span><span class="sxs-lookup"><span data-stu-id="8047c-724">Disable Group Call Pickup</span></span>

<span data-ttu-id="8047c-725">本示例为给定用户禁用组呼叫应答。</span><span class="sxs-lookup"><span data-stu-id="8047c-725">This example disables Group Call Pickup for a given user.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disablegrouppickup

<div>


> [!NOTE]  
> <span data-ttu-id="8047c-726">当您为用户禁用组呼叫应答时，分配给该用户的组号码将不会保留。</span><span class="sxs-lookup"><span data-stu-id="8047c-726">When you disable Group Call Pickup for a user, the group number that was assigned to the user is not retained.</span></span> <span data-ttu-id="8047c-727">如果您随后要为该用户重新启用组呼叫应答，则必须使用/enablegrouppickup 开关再次分配该组编号。</span><span class="sxs-lookup"><span data-stu-id="8047c-727">If you subsequently want to re-enable Group Call Pickup for that user, you must assign the group number again with the /enablegrouppickup switch.</span></span>



</div>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True

</div>

</div>

</div>

<div>

## <a name="sysprepps1"></a><span data-ttu-id="8047c-728">SYSPrep. ps1</span><span class="sxs-lookup"><span data-stu-id="8047c-728">SYSPrep.ps1</span></span>

<div>

## <a name="description"></a><span data-ttu-id="8047c-729">说明</span><span class="sxs-lookup"><span data-stu-id="8047c-729">Description</span></span>

<span data-ttu-id="8047c-730">Sysprep.inf 是一个 Windows PowerShell 脚本，它将在 Windows Server 2008 操作系统计算机上安装以下 Lync Server 2013 必备组件。</span><span class="sxs-lookup"><span data-stu-id="8047c-730">SYSPrep.ps1 is a Windows PowerShell script that will install the following Lync Server 2013 prerequisites on your Windows Server 2008 operating system machine.</span></span>

  - <span data-ttu-id="8047c-731">Microsoft .Net Framework 4。5</span><span class="sxs-lookup"><span data-stu-id="8047c-731">Microsoft .Net Framework 4.5</span></span>

  - <span data-ttu-id="8047c-732">Microsoft SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="8047c-732">Microsoft SQL Server Express</span></span>

  - <span data-ttu-id="8047c-733">Windows Powershell 版本3。0</span><span class="sxs-lookup"><span data-stu-id="8047c-733">Windows Powershell version 3.0</span></span>

  - <span data-ttu-id="8047c-734">Visual c + + 2010 可再发行组件</span><span class="sxs-lookup"><span data-stu-id="8047c-734">Visual C++ 2010 Redistributable</span></span>

  - <span data-ttu-id="8047c-735">Internet information Server 更新</span><span class="sxs-lookup"><span data-stu-id="8047c-735">Internet Information Server Updates</span></span>

  - <span data-ttu-id="8047c-736">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="8047c-736">Windows Identity Foundation</span></span>

  - <span data-ttu-id="8047c-737">Lync Server 2013 核心文件</span><span class="sxs-lookup"><span data-stu-id="8047c-737">Lync Server 2013 Core files</span></span>

<span data-ttu-id="8047c-738">尽管脚本名称类似于 Microsoft Windows 操作系统的系统准备工具，但它们是不同的。</span><span class="sxs-lookup"><span data-stu-id="8047c-738">While the script name is similar to the System Preparation Tool for the Microsoft Windows operating systems, they are different.</span></span> <span data-ttu-id="8047c-739">此脚本将仅安装 Lync Server 2013 所需的必备组件。</span><span class="sxs-lookup"><span data-stu-id="8047c-739">This script will only install the required prerequisites for Lync Server 2013.</span></span> <span data-ttu-id="8047c-740">安装这些必备组件后，即可使用 Windows SYSPrep 工具创建服务器的映像。</span><span class="sxs-lookup"><span data-stu-id="8047c-740">Once those prerequisites are installed, the Windows SYSPrep tool can then be used to create an image of the server.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="8047c-741">Requirements</span><span class="sxs-lookup"><span data-stu-id="8047c-741">Requirements</span></span>

<span data-ttu-id="8047c-742">在运行 Sysprep.inf. ps1 脚本之前，必须将必备文件复制到 Windows Server 2008 操作系统计算机上的本地文件夹（例如**D：\\Setup）**。</span><span class="sxs-lookup"><span data-stu-id="8047c-742">Prior to running the SYSPrep.ps1 script, you must copy the prerequisite files to a local folder on the Windows Server 2008 operating system machine (for example **D:\\Setup)**.</span></span> <span data-ttu-id="8047c-743">此文件夹还必须包含 Lync Server 2013 文件（特别是 setup.exe）的副本 **。**</span><span class="sxs-lookup"><span data-stu-id="8047c-743">This folder must also include a copy of the Lync Server 2013 files, specifically **Setup.exe.**</span></span> <span data-ttu-id="8047c-744">可以从以下位置下载必备文件：</span><span class="sxs-lookup"><span data-stu-id="8047c-744">The prerequisite files can be downloaded from the following locations:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8047c-745">先决条件</span><span class="sxs-lookup"><span data-stu-id="8047c-745">Prerequisite</span></span></th>
<th><span data-ttu-id="8047c-746">位置</span><span class="sxs-lookup"><span data-stu-id="8047c-746">Location</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8047c-747">Microsoft .Net Framework 4。5</span><span class="sxs-lookup"><span data-stu-id="8047c-747">Microsoft .Net Framework 4.5</span></span></p></td>
<td><p>https://go.microsoft.com/?linkid=9816306</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8047c-748">Microsoft SQL Server Express 2008 R2</span><span class="sxs-lookup"><span data-stu-id="8047c-748">Microsoft SQL Server Express 2008 R2</span></span></p></td>
<td><p>https://www.microsoft.com/download/details.aspx?id=23650</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8047c-749">Windows Powershell 版本3。0</span><span class="sxs-lookup"><span data-stu-id="8047c-749">Windows Powershell version 3.0</span></span></p></td>
<td><p>https://www.microsoft.com/download/details.aspx?id=34595</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8047c-750">Visual c + + 2010 可再发行组件</span><span class="sxs-lookup"><span data-stu-id="8047c-750">Visual C++ 2010 Redistributable</span></span></p></td>
<td><p>https://www.microsoft.com/download/details.aspx?id=5555</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8047c-751">Internet information Server 更新</span><span class="sxs-lookup"><span data-stu-id="8047c-751">Internet Information Server Updates</span></span></p></td>
<td><p>https://www.microsoft.com/download/details.aspx?id=34869</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8047c-752">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="8047c-752">Windows Identity Foundation</span></span></p></td>
<td><p>https://www.microsoft.com/download/details.aspx?id=17331</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8047c-753">Lync Server 2013 Setup.exe</span><span class="sxs-lookup"><span data-stu-id="8047c-753">Lync Server 2013 Setup.exe</span></span></p></td>
<td><p><span data-ttu-id="8047c-754">从 Lync Server 2013 媒体复制</span><span class="sxs-lookup"><span data-stu-id="8047c-754">Copy from Lync Server 2013 media</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="parameter"></a><span data-ttu-id="8047c-755">参数</span><span class="sxs-lookup"><span data-stu-id="8047c-755">Parameter</span></span>

<span data-ttu-id="8047c-756">**– SetupFolder**参数采用参数作为参数必备文件的目录位置</span><span class="sxs-lookup"><span data-stu-id="8047c-756">The **–SetupFolder** parameter takes as an argument the directory location of the prerequisite files</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="8047c-757">示例</span><span class="sxs-lookup"><span data-stu-id="8047c-757">Examples</span></span>

<span data-ttu-id="8047c-758">若要运行 Sysprep.inf 脚本并安装 Lync Server 2013 必备组件，请从提升的命令提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="8047c-758">To run the SYSPrep.ps1 script and install the Lync Server 2013 prerequisites, run the following command from an elevated command prompt:</span></span>

    ./SysPrep.PS1 -SetupFolder D:\Setup

</div>

</div>

<div>

## <a name="unassigned-number-announcements-migration"></a><span data-ttu-id="8047c-759">未分配号码通知迁移</span><span class="sxs-lookup"><span data-stu-id="8047c-759">Unassigned Number Announcements Migration</span></span>

<span data-ttu-id="8047c-760">"未分配号码" 通知迁移工具使 Lync 管理员能够将由通知应用程序提供服务的未分配号码配置从源 Lync 服务器或池移动到目标 Lync Server 或池。</span><span class="sxs-lookup"><span data-stu-id="8047c-760">The Unassigned Number Announcements Migration tool enables a Lync administrator to move the unassigned numbers configuration that is serviced by the announcement application from a source Lync Server or Pool to a destination Lync Server or Pool.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="8047c-761">说明</span><span class="sxs-lookup"><span data-stu-id="8047c-761">Description</span></span>

<span data-ttu-id="8047c-762">未分配号码通知迁移工具是一个 Windows PowerShell 脚本，它将源服务器或池的通知应用程序提供服务的未分配号码配置移动到不同的服务器或池。</span><span class="sxs-lookup"><span data-stu-id="8047c-762">The Unassigned Number Announcements Migration tool is a Windows PowerShell script that moves the unassigned numbers configuration serviced by the announcement application of a source server or pool to a different server or pool.</span></span>

<span data-ttu-id="8047c-763">执行时，"未分配号码" 通知迁移脚本将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="8047c-763">When executed, the Unassigned Number Announcements Migration script will perform the following operations:</span></span>

1.  <span data-ttu-id="8047c-764">将源服务器或池中承载的通知应用程序的未分配号码通知所使用的所有音频文件移动到目标服务器或池的文件存储区。</span><span class="sxs-lookup"><span data-stu-id="8047c-764">Move all the audio files used by the unassigned number announcements of the announcement application hosted in the source server or pool to the file store of the destination server or pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8047c-765">在将音频文件复制到目标池后，会从源池中将其删除。</span><span class="sxs-lookup"><span data-stu-id="8047c-765">the audio files are removed from the source pool once they’re copied to the destination pool.</span></span>

    
    </div>

2.  <span data-ttu-id="8047c-766">将为源服务器或池中承载的通知应用程序配置的所有未分配号码通知移动到目标服务器或池。</span><span class="sxs-lookup"><span data-stu-id="8047c-766">Move all unassigned number announcements configured for the announcement application hosted in the source server or pool to the destination server or pool.</span></span>

3.  <span data-ttu-id="8047c-767">将由源服务器或池中承载的通知应用程序提供服务的所有未分配号码范围重新分配给目标服务器或池。</span><span class="sxs-lookup"><span data-stu-id="8047c-767">Reassign all the unassigned number ranges that are serviced by the announcement application hosted in the source server or pool to the destination server or pool.</span></span>

<span data-ttu-id="8047c-768">在成功运行脚本后，源服务器或池中承载的通知应用程序所提供的所有未分配号码范围将通过目标服务器或池的相同配置进行服务。</span><span class="sxs-lookup"><span data-stu-id="8047c-768">After successfully running the script, all the unassigned number ranges that were serviced by the announcement application hosted in the source server or pool will now be serviced with the same configuration by the destination server or pool.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="8047c-769">Output</span><span class="sxs-lookup"><span data-stu-id="8047c-769">Output</span></span>

<span data-ttu-id="8047c-770">**Move-csannouncementconfiguration**脚本在 Lync 命令行管理程序窗口中指示其执行迁移操作成功或失败的位置。</span><span class="sxs-lookup"><span data-stu-id="8047c-770">The **Move-CsAnnouncementConfiguration** script indicates in the Lync Management Shell window from where it’s executed the success or failure of the migration operation.</span></span>

<span data-ttu-id="8047c-771">如果在发生任何错误时中断操作的执行，则已成功移动到目标的未分配号码范围将保留在操作表单的目标中，并且要迁移的未分配号码范围的剩余部分将保留在源和操作表单中的源。</span><span class="sxs-lookup"><span data-stu-id="8047c-771">If the execution of the operation is interrupted by any error, the unassigned number ranges that were successfully moved to the destination will remain in the destination in an operational form and the rest of the unassigned number ranges to be migrated will remain in the source as well in an operational form.</span></span> <span data-ttu-id="8047c-772">若要完全迁移配置的其余部分，请在解决错误后重新运行脚本。</span><span class="sxs-lookup"><span data-stu-id="8047c-772">To fully migrate the rest of the configuration, rerun the script after addressing the error.</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="8047c-773">用途</span><span class="sxs-lookup"><span data-stu-id="8047c-773">Purpose</span></span>

<span data-ttu-id="8047c-774">未分配号码通知迁移脚本可用于以下三种方案：</span><span class="sxs-lookup"><span data-stu-id="8047c-774">The Unassigned Number Announcements Migration script can be used in the following three scenarios:</span></span>

  - <span data-ttu-id="8047c-775">**将配置设置迁移到新版本的 Lync Server：** Contoso 正处于迁移到 Lync Server 2013 的过程中，作为迁移过程的一部分，Lync Server 管理员希望将通知应用程序提供的未分配号码配置从 Lync Server 2010 部署移动到新的 Lync Server 2013 部署。</span><span class="sxs-lookup"><span data-stu-id="8047c-775">**Migrating configuration settings to a new version of Lync Server:** Contoso is in the process of migrating to Lync Server 2013 and as part of the migration process the Lync Server administrator would like to move the unassigned numbers configuration serviced by the announcement application from the Lync Server 2010 deployment to the new Lync Server 2013 deployment.</span></span> <span data-ttu-id="8047c-776">为了移动配置设置，Lync Server 管理员使用 "未分配号码" 通知迁移工具。</span><span class="sxs-lookup"><span data-stu-id="8047c-776">To move the configuration settings, the Lync Server administrator uses the Unassigned Number Announcements Migration tool.</span></span>

  - <span data-ttu-id="8047c-777">**将部署从 Lync server 2013 回滚到 Lync server 2010：** 由于意外因素，Contoso 必须将迁移回滚到新的 Lync Server 2013 部署。</span><span class="sxs-lookup"><span data-stu-id="8047c-777">**Rolling back a deployment from Lync Server 2013 to Lync Server 2010:** Due unexpected factors, Contoso has to roll back the migration to the new Lync Server 2013 deployment.</span></span> <span data-ttu-id="8047c-778">为了最大限度地减少对服务的中断，Lync Server 管理员使用 "未分配号码" 通知迁移工具将配置从 Lync Server 2013 部署回滚到 Lync Server 2010 部署。</span><span class="sxs-lookup"><span data-stu-id="8047c-778">To minimize disruptions to the service, the Lync Server administrator uses the Unassigned Number Announcements Migration tool to roll back the configuration from the Lync Server 2013 deployment to the Lync Server 2010 deployment.</span></span>

  - <span data-ttu-id="8047c-779">**在 Lync 部署之间移动数据：** Contoso 正处于将一个池的所有服务器替换为较新服务器的过程。</span><span class="sxs-lookup"><span data-stu-id="8047c-779">**Moving data between Lync deployments:** Contoso is in the process of replacing all the servers of one pool with newer servers.</span></span> <span data-ttu-id="8047c-780">他们的策略是部署新的 Lync Server 2013 池，将所有数据从旧池移动到新池，然后弃用旧池。</span><span class="sxs-lookup"><span data-stu-id="8047c-780">Their strategy is to deploy a new Lync Server 2013 pool, move all the data from the old to the new pool, and then deprecate the old pool.</span></span> <span data-ttu-id="8047c-781">部署新池后，将使用 "未分配号码通知" 迁移工具将配置从旧池移动到新池。</span><span class="sxs-lookup"><span data-stu-id="8047c-781">Once the new pool is deployed, the Unassigned Number Announcements Migration tool is used to move the configuration from the old pool to the new one.</span></span>

<div>

## <a name="requirements"></a><span data-ttu-id="8047c-782">Requirements</span><span class="sxs-lookup"><span data-stu-id="8047c-782">Requirements</span></span>

<span data-ttu-id="8047c-783">若要成功运行此工具，需要满足以下主要要求：</span><span class="sxs-lookup"><span data-stu-id="8047c-783">The following are the main requirements needed to successfully run the tool:</span></span>

1.  <span data-ttu-id="8047c-784">必须在安装了 Lync Server 2013 命令行管理程序的计算机上运行该脚本。</span><span class="sxs-lookup"><span data-stu-id="8047c-784">The script must be run from a computer that has Lync Server 2013 Management Shell installed.</span></span>

2.  <span data-ttu-id="8047c-785">必须在源和目标 Lync 服务器或池中成功部署通知应用程序。</span><span class="sxs-lookup"><span data-stu-id="8047c-785">The announcement application has to be successfully deployed in the source and destination Lync Servers or Pools.</span></span>

<div>

## <a name="move-csannouncementconfiguration-script"></a><span data-ttu-id="8047c-786">Move-csannouncementconfiguration 脚本</span><span class="sxs-lookup"><span data-stu-id="8047c-786">Move-CsAnnouncementConfiguration script</span></span>

<span data-ttu-id="8047c-787">Move-csannouncementconfiguration 脚本需要下表中所述的两个参数。</span><span class="sxs-lookup"><span data-stu-id="8047c-787">The Move-CsAnnouncementConfiguration script requires the two parameters that are described in the table below.</span></span>

<span data-ttu-id="8047c-788">![Move-csannouncementconfiguration 参数。](images/JJ945604.7ab66ad3-d0db-4d77-8b93-ebccf0cb0663(OCS.15).jpg "Move-csannouncementconfiguration 参数。")</span><span class="sxs-lookup"><span data-stu-id="8047c-788">![Move-CsAnnouncementConfiguration parameters.](images/JJ945604.7ab66ad3-d0db-4d77-8b93-ebccf0cb0663(OCS.15).jpg "Move-CsAnnouncementConfiguration parameters.")</span></span>

</div>

</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="8047c-789">示例</span><span class="sxs-lookup"><span data-stu-id="8047c-789">Examples</span></span>

<div>

## <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2010-pool-to-a-lync-server-2013-pool"></a><span data-ttu-id="8047c-790">将未分配的号码通知配置从 Lync Server 2010 池移动到 Lync Server 2013 池</span><span class="sxs-lookup"><span data-stu-id="8047c-790">Moving the Unassigned Number Announcements Configuration from a Lync Server 2010 Pool to a Lync Server 2013 Pool</span></span>

<span data-ttu-id="8047c-791">本示例将源池（Lync Server 2010）中未分配的号码宣告移动到目标池（Lync Server 2013）。</span><span class="sxs-lookup"><span data-stu-id="8047c-791">This example moves the unassigned number announcements from the source pool (Lync Server 2010) to the destination pool (Lync Server 2013).</span></span>

    Move-CsAnnouncementConfiguration.ps1 -Source LS2010Pool.contoso.com -Destination LS2013Pool.contoso.com

</div>

<div>

## <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2013-pool-to-a-lync-server-2010-pool"></a><span data-ttu-id="8047c-792">将未分配的号码通知配置从 Lync Server 2013 池移动到 Lync Server 2010 池</span><span class="sxs-lookup"><span data-stu-id="8047c-792">Moving the Unassigned Number Announcements Configuration from a Lync Server 2013 Pool to a Lync Server 2010 Pool</span></span>

<span data-ttu-id="8047c-793">本示例将源池（Lync Server 2013）中未分配的号码宣告移动到目标池（Lync Server 2010）。</span><span class="sxs-lookup"><span data-stu-id="8047c-793">This example moves the unassigned number announcements from the source pool (Lync Server 2013) to the destination pool (Lync Server 2010).</span></span>

    Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination LS2010Pool.contoso.com

</div>

</div>

</div>

<div>

## <a name="web-conf-data"></a><span data-ttu-id="8047c-794">Web 会议数据</span><span class="sxs-lookup"><span data-stu-id="8047c-794">Web Conf Data</span></span>

<span data-ttu-id="8047c-795">通过 Web 会议数据工具，Lync Server 2013 通信软件的管理员可以更好地控制与组织者的 Web 会议关联的数据。</span><span class="sxs-lookup"><span data-stu-id="8047c-795">The Web Conf Data Tool allows an administrator of Lync Server 2013 communications software to have more control over the data associated with an organizer’s Web conferences.</span></span> <span data-ttu-id="8047c-796">方案包括基于时间戳条件删除特定用户的会议数据的功能。</span><span class="sxs-lookup"><span data-stu-id="8047c-796">Scenarios include the ability to delete a specific user’s meeting data based on a time stamp criteria.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="8047c-797">说明</span><span class="sxs-lookup"><span data-stu-id="8047c-797">Description</span></span>

<span data-ttu-id="8047c-798">此工具允许管理员执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="8047c-798">This tool allows the administrator to perform the following operations:</span></span>

1.  <span data-ttu-id="8047c-799">查找与单个用户相关联的所有 Web 会议数据。</span><span class="sxs-lookup"><span data-stu-id="8047c-799">Find all Web conferencing data associated with a single user.</span></span>

2.  <span data-ttu-id="8047c-800">删除与单个用户相关联的所有 Web 会议数据。</span><span class="sxs-lookup"><span data-stu-id="8047c-800">Delete all Web conferencing data associated with a single user.</span></span>

3.  <span data-ttu-id="8047c-801">删除与某一日期之前的单个用户相关联的所有 Web 会议数据。</span><span class="sxs-lookup"><span data-stu-id="8047c-801">Delete all Web conferencing data associated with a single user that is older than a certain date.</span></span>

4.  <span data-ttu-id="8047c-802">当用户从一个池移动到另一个池时，移动与单个用户相关联的所有 Web 会议数据。</span><span class="sxs-lookup"><span data-stu-id="8047c-802">Move all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8047c-803">当用户从一个池移动到另一个池时，支持 Lync Server 2010 的资源工具包工具移动与单个用户相关联的所有 Web 会议数据。</span><span class="sxs-lookup"><span data-stu-id="8047c-803">The Resource Kit Tools for Lync Server 2010 supported moving all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span> <span data-ttu-id="8047c-804">现在，此工具中的功能已被弃用，取而代之的是<STRONG>MoveConferenceData</STRONG>参数。</span><span class="sxs-lookup"><span data-stu-id="8047c-804">That functionality is now deprecated from this tool in favor of the <STRONG>MoveConferenceData</STRONG> parameter.</span></span> <span data-ttu-id="8047c-805">有关此参数的详细信息，请参阅<A href="https://technet.microsoft.com/library/gg398528(v=ocs.15)">get-csuser</A> cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8047c-805">For details about this parameter, see the <A href="https://technet.microsoft.com/library/gg398528(v=ocs.15)">Move-CsUser</A> cmdlet.</span></span>



</div>

<span data-ttu-id="8047c-806">该工具仅删除处于非活动状态的会议的会议数据。</span><span class="sxs-lookup"><span data-stu-id="8047c-806">The tool deletes meeting data only for meetings that are inactive.</span></span> <span data-ttu-id="8047c-807">无法删除活动会议（或会话中的会议）。</span><span class="sxs-lookup"><span data-stu-id="8047c-807">Active meetings (or meetings in sessions) cannot be deleted.</span></span>

<span data-ttu-id="8047c-808">必须从与目标用户位于同一池中的计算机运行此工具。</span><span class="sxs-lookup"><span data-stu-id="8047c-808">This tool must be run from a computer that is in the same pool as the target user.</span></span> <span data-ttu-id="8047c-809">此工具管理其会议内容数据的用户必须驻留在相同的用户池中。</span><span class="sxs-lookup"><span data-stu-id="8047c-809">The user whose meeting content data is being managed by this tool must be homed in the same user pool.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="8047c-810">Output</span><span class="sxs-lookup"><span data-stu-id="8047c-810">Output</span></span>

<span data-ttu-id="8047c-811">此工具将输出每个操作的结果：</span><span class="sxs-lookup"><span data-stu-id="8047c-811">This tool outputs the results of each of the operations:</span></span>

  - <span data-ttu-id="8047c-812">如果执行了查询，该工具会将具有该用户的所有非活动会议数据文件夹的列表输出为组织者。</span><span class="sxs-lookup"><span data-stu-id="8047c-812">If a query is performed, the tool outputs the list of all inactive meeting data folders that have that user as an organizer.</span></span>

  - <span data-ttu-id="8047c-813">如果执行删除，该工具将输出其数据将被删除的所有会议数据文件夹的列表。</span><span class="sxs-lookup"><span data-stu-id="8047c-813">If a delete is performed, the tool outputs the list of all meeting data folders whose data will be deleted.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="8047c-814">Requirements</span><span class="sxs-lookup"><span data-stu-id="8047c-814">Requirements</span></span>

<span data-ttu-id="8047c-815">该工具需要在组织者当前托管的同一个池中运行。</span><span class="sxs-lookup"><span data-stu-id="8047c-815">The tool needs to be run in the same pool where the organizer is currently homed.</span></span>

<span data-ttu-id="8047c-816">必须使用具有对内容文件存储的访问权限的管理员权限运行该工具。</span><span class="sxs-lookup"><span data-stu-id="8047c-816">The tool must be run using administrator privileges with access to the Content File Store.</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="8047c-817">示例</span><span class="sxs-lookup"><span data-stu-id="8047c-817">Examples</span></span>

<span data-ttu-id="8047c-818">下表介绍了这些参数，其中一些参数在示例中使用。</span><span class="sxs-lookup"><span data-stu-id="8047c-818">The following table describes the parameters, some of which are used in the examples.</span></span>

<span data-ttu-id="8047c-819">![Web 会议数据工具参数。](images/JJ945604.a733c1c6-5dfc-4874-a74f-bfdee81c1401(OCS.15).jpg "Web 会议数据工具参数。")</span><span class="sxs-lookup"><span data-stu-id="8047c-819">![Web Conf Data Tool parameters.](images/JJ945604.a733c1c6-5dfc-4874-a74f-bfdee81c1401(OCS.15).jpg "Web Conf Data Tool parameters.")</span></span>

    WebConfDataTool.exe /User:user0@contoso.com /Action:query ""/ExpirationDate:08/09/2010 12:00:00""

<span data-ttu-id="8047c-820">上面的示例展示了查询命令的工作原理。</span><span class="sxs-lookup"><span data-stu-id="8047c-820">The preceding example shows how a query command would work.</span></span> <span data-ttu-id="8047c-821">此类命令的输出将是受此工具影响的所有会议内容文件夹的列表。</span><span class="sxs-lookup"><span data-stu-id="8047c-821">The output of such a command would be a list of all meeting content folders that would be affected by this tool.</span></span>

    WebConfDataTool.exe /User:user0@contoso.com /Action:delete

<span data-ttu-id="8047c-822">上一个示例是 "删除" 命令。</span><span class="sxs-lookup"><span data-stu-id="8047c-822">The preceding is an example of a delete command.</span></span> <span data-ttu-id="8047c-823">"删除" 命令将删除此用户的所有非活动会议文件夹。</span><span class="sxs-lookup"><span data-stu-id="8047c-823">The delete command will remove all inactive meeting folders from this user.</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="8047c-824">总结</span><span class="sxs-lookup"><span data-stu-id="8047c-824">Summary</span></span>

<span data-ttu-id="8047c-825">对于需要更精确控制会议会议数据的管理员来说，此工具可能是一项宝贵的资源。</span><span class="sxs-lookup"><span data-stu-id="8047c-825">This tool can be a valuable resource to administrators who need more precise control over conference meeting data.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>
