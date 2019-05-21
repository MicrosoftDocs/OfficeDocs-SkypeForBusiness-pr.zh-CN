---
title: 在 Skype for Business Server 2015 中安装规划工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b95b3301-fa1e-4b96-9af4-05b43d39db8d
description: 使用 Skype for Business Server 2015 计划工具开始设计和规划 Skype for business Server 2015 基础结构之前, 必须首先安装规划工具。 规划工具不需要部署到属于你计划安装 Skype for Business Server 2015 的域或基础结构的一部分的工作站或服务器。 规划工具附带的自述文件详细介绍了有关安装和使用该工具的重要信息。 Some of the information in the Readme file is duplicated here for clarity.
ms.openlocfilehash: 192eae34bf6cf3fa53be82d8cb4450f960c90314
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279125"
---
# <a name="install-the-planning-tool-in-skype-for-business-server-2015"></a><span data-ttu-id="30c72-106">在 Skype for Business Server 2015 中安装规划工具</span><span class="sxs-lookup"><span data-stu-id="30c72-106">Install the Planning Tool in Skype for Business Server 2015</span></span>

<span data-ttu-id="30c72-107">使用 Skype for Business Server 2015 计划工具开始设计和规划 Skype for business Server 2015 基础结构之前, 必须首先安装规划工具。</span><span class="sxs-lookup"><span data-stu-id="30c72-107">Before you begin designing and planning your Skype for Business Server 2015 infrastructure by using the Skype for Business Server 2015 Planning Tool, you must first install the Planning Tool.</span></span> <span data-ttu-id="30c72-108">规划工具不需要部署到属于你计划安装 Skype for Business Server 2015 的域或基础结构的一部分的工作站或服务器。</span><span class="sxs-lookup"><span data-stu-id="30c72-108">The Planning Tool does not need to be deployed to a workstation or server that is part of the domain or infrastructure where you plan to install Skype for Business Server 2015.</span></span> <span data-ttu-id="30c72-109">规划工具附带的自述文件详细介绍了有关安装和使用该工具的重要信息。</span><span class="sxs-lookup"><span data-stu-id="30c72-109">The Readme file that accompanies the Planning Tool details important information about installing and using the tool.</span></span> <span data-ttu-id="30c72-110">Some of the information in the Readme file is duplicated here for clarity.</span><span class="sxs-lookup"><span data-stu-id="30c72-110">Some of the information in the Readme file is duplicated here for clarity.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="30c72-111">规划工具要求在安装该工具的计算机上具有管理员权限和权限的用户进行安装。</span><span class="sxs-lookup"><span data-stu-id="30c72-111">The Planning Tool requires installation by a user with administrator rights and permissions on the computer on which the tool is to be installed.</span></span>

<span data-ttu-id="30c72-112">规划工具的安装和操作支持的操作系统包括:</span><span class="sxs-lookup"><span data-stu-id="30c72-112">The supported operating systems for installation and operation of the Planning Tool are:</span></span>

- <span data-ttu-id="30c72-113">Windows 10</span><span class="sxs-lookup"><span data-stu-id="30c72-113">Windows 10</span></span>

- <span data-ttu-id="30c72-114">Windows 8</span><span class="sxs-lookup"><span data-stu-id="30c72-114">Windows 8</span></span>

- <span data-ttu-id="30c72-115">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="30c72-115">Windows 8.1</span></span>

- <span data-ttu-id="30c72-116">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="30c72-116">Windows Server 2012</span></span>

- <span data-ttu-id="30c72-117">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="30c72-117">Windows Server 2012 R2</span></span>

- <span data-ttu-id="30c72-118">Windows 7 32 位版本</span><span class="sxs-lookup"><span data-stu-id="30c72-118">Windows 7, 32-bit edition</span></span>

- <span data-ttu-id="30c72-119">Windows 7，使用 Windows on Win32 (WOW) 的 64 位版本</span><span class="sxs-lookup"><span data-stu-id="30c72-119">Windows 7, 64-bit edition using Windows on Win32 (WOW)</span></span>

- <span data-ttu-id="30c72-120">Windows Server 2008 R2，使用 WOW</span><span class="sxs-lookup"><span data-stu-id="30c72-120">Windows Server 2008 R2, using WOW</span></span>

<span data-ttu-id="30c72-121">此外, 规划工具需要 Microsoft .NET Framework 4.5。</span><span class="sxs-lookup"><span data-stu-id="30c72-121">Additionally, the Planning Tool requires Microsoft .NET Framework 4.5.</span></span>

<span data-ttu-id="30c72-122">满足预安装要求后, 即可安装规划工具。</span><span class="sxs-lookup"><span data-stu-id="30c72-122">After the preinstallation requirements are met, you can then install the Planning Tool.</span></span>



## <a name="to-install-the-planning-tool"></a><span data-ttu-id="30c72-123">安装规划工具</span><span class="sxs-lookup"><span data-stu-id="30c72-123">To install the Planning Tool</span></span>

1. <span data-ttu-id="30c72-124">以 Administrators 组成员的身份登录本地计算机。</span><span class="sxs-lookup"><span data-stu-id="30c72-124">Log on to the local computer as a member of the Administrators group.</span></span>

2. <span data-ttu-id="30c72-125">使用 Windows 资源管理器或命令窗口, 找到您下载规划工具安装文件的目录。</span><span class="sxs-lookup"><span data-stu-id="30c72-125">Using Windows Explorer or a command window, locate the directory where you downloaded the Planning Tool installation files.</span></span>

3. <span data-ttu-id="30c72-p103">找到 SkypeForBusinessPlanningTool.msi。在 Windows 资源管理器中双击该文件。在命令窗口中，键入文件的名称，然后按 **Enter** 运行该文件。</span><span class="sxs-lookup"><span data-stu-id="30c72-p103">Locate the SkypeForBusinessPlanningTool.msi. In Windows Explorer, double-click the file. In the command window, type the name of the file, and then press **Enter** to run the file.</span></span>

4. <span data-ttu-id="30c72-129">在“**Skype for Business Server 2015 规划工具安装向导**”的“欢迎”页上，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="30c72-129">On the Welcome page of the **Skype for Business Server 2015, Planning Tool Setup Wizard**, click **Next**.</span></span>

5. <span data-ttu-id="30c72-130">查看“**最终用户许可协议**”，如果选择接受许可协议中的使用条款，则选择“**我接受许可协议中的条款**”，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="30c72-130">Review the **End-User License Agreement**, select **I accept the terms in the License Agreement** if you choose to accept the terms of use in the license agreement, and then click **Next**.</span></span>

6. <span data-ttu-id="30c72-p104">选择安装规划工具文件的位置。默认位置是 C:\Program Files (x86)\Skype for Business Server 2015\Planning Tool。如果要更改安装位置，请单击“**更改**”。在“**更改目标文件夹**”上，浏览或键入要安装这些文件的位置，单击“**确定**”，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="30c72-p104">Choose where to install the Planning Tool files. The default location is C:\Program Files (x86)\Skype for Business Server 2015\Planning Tool. If you want to change the installation location, click **Change**. On **Change destination folder**, browse or type the location to install the files, click **OK**, and then click **Next**.</span></span>

7. <span data-ttu-id="30c72-135">安装程序现在已准备好安装规划工具。</span><span class="sxs-lookup"><span data-stu-id="30c72-135">The installer is now ready to install the Planning Tool.</span></span> <span data-ttu-id="30c72-136">单击“安装”\*\*\*\* 开始安装过程。</span><span class="sxs-lookup"><span data-stu-id="30c72-136">Click **Install** to begin the installation process.</span></span>

8. <span data-ttu-id="30c72-137">将开始安装，并将显示进度。</span><span class="sxs-lookup"><span data-stu-id="30c72-137">The installation will start, and the progress will be displayed.</span></span> <span data-ttu-id="30c72-138">成功完成安装后，单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="30c72-138">After the installation is successfully completed, click **Finish**.</span></span>

9. <span data-ttu-id="30c72-139">规划工具可供使用。</span><span class="sxs-lookup"><span data-stu-id="30c72-139">The Planning Tool is ready for use.</span></span>

## <a name="optional-software"></a><span data-ttu-id="30c72-140">可选软件</span><span class="sxs-lookup"><span data-stu-id="30c72-140">Optional Software</span></span>
<span data-ttu-id="30c72-141"><a name="Optional_Software"> </a></span><span class="sxs-lookup"><span data-stu-id="30c72-141"></span></span>

<span data-ttu-id="30c72-142">Skype for Business Server 2015 规划工具旨在导出到 Microsoft Excel 和 Microsoft Visio。</span><span class="sxs-lookup"><span data-stu-id="30c72-142">The Skype for Business Server 2015 Planning Tool is designed to export to Microsoft Excel and Microsoft Visio.</span></span> <span data-ttu-id="30c72-143">虽然这些应用程序不是规划工具运行所必需的, 但它们确实为设计的部署和文档增加了重要价值。</span><span class="sxs-lookup"><span data-stu-id="30c72-143">While these applications are not required for the operation of the Planning Tool, they do add significant value to the deployment and documentation of your design.</span></span>

### <a name="microsoft-excel"></a><span data-ttu-id="30c72-144">Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="30c72-144">Microsoft Excel</span></span>

<span data-ttu-id="30c72-145">将设计导出到 Microsoft Excel 时会创建一个报告，该报告在电子表格中显示 7 个选项卡：</span><span class="sxs-lookup"><span data-stu-id="30c72-145">Exporting your design to Microsoft Excel creates a report that displays seven tabs in the spreadsheet:</span></span>

- <span data-ttu-id="30c72-146">摘要-显示有关网站配置的信息, 包括用户计数、容量设置和服务器配置文件信息。</span><span class="sxs-lookup"><span data-stu-id="30c72-146">Summary - Displays information on site configuration, including user count, capacity settings, and server profile information.</span></span>

- <span data-ttu-id="30c72-147">硬件配置文件-显示针对拓扑中指定的服务器的推荐硬件配置 (包括 CPU、内存、磁盘和网络接口) 的报告。</span><span class="sxs-lookup"><span data-stu-id="30c72-147">Hardware Profile - Displays a report on the recommended hardware configurations for servers that are specified in the topology, including CPU, memory, disk, and network interface.</span></span> <span data-ttu-id="30c72-148">还包括服务器组件的数量和推荐规格。</span><span class="sxs-lookup"><span data-stu-id="30c72-148">The quantity and recommended specifications for the server components are also included.</span></span> <span data-ttu-id="30c72-149">此外，还按站点定义了每台服务器，以按站点提供服务器要求的完整描述。</span><span class="sxs-lookup"><span data-stu-id="30c72-149">In addition, each server is defined by site to provide a complete representation of server requirements by site.</span></span>

- <span data-ttu-id="30c72-150">端口要求-显示已启用的所有端口以及与域名系统负载平衡 (DNS LB) 和硬件负载平衡器 (HLB) 的关联的报告。</span><span class="sxs-lookup"><span data-stu-id="30c72-150">Ports Requirements - Displays a report of all ports that are enabled, and the association to Domain Name System load balancing (DNS LB) and hardware load balancers (HLB).</span></span> <span data-ttu-id="30c72-151">应使用此报告规划防火墙以及 DNS LB 和 HLB 配置。</span><span class="sxs-lookup"><span data-stu-id="30c72-151">You should use this report to plan your firewall and DNS LB and HLB configurations.</span></span>

- <span data-ttu-id="30c72-152">摘要报告-显示设置边缘服务器网络所需设置的一般摘要。</span><span class="sxs-lookup"><span data-stu-id="30c72-152">Summary Report - Displays the general summary of the settings that are required to set up your Edge Server network.</span></span>

- <span data-ttu-id="30c72-153">证书报告-显示用于获取运行边缘服务器所需证书的主题名称和主题备用名称。</span><span class="sxs-lookup"><span data-stu-id="30c72-153">Certificates Report - Displays the subject name and subject alternate names that are required for the certificates needed to get the Edge Servers running.</span></span>

- <span data-ttu-id="30c72-154">防火墙报告-显示外部接口和内部接口的源和目标端口以及 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="30c72-154">Firewall Report - Displays the source and destination ports and IP addresses for both External and Internal interfaces.</span></span>

- <span data-ttu-id="30c72-155">DNS 报告-显示你创建的每个 DNS 条目所需的完全限定的域名 (FQDN) 和 IP/VIP 地址。</span><span class="sxs-lookup"><span data-stu-id="30c72-155">DNS Report - Displays the fully qualified domain name (FQDN) and IP/VIP addresses required for each DNS entry that you create.</span></span>

### <a name="microsoft-visio"></a><span data-ttu-id="30c72-156">Microsoft Visio</span><span class="sxs-lookup"><span data-stu-id="30c72-156">Microsoft Visio</span></span>

<span data-ttu-id="30c72-p110">将设计导出到 Microsoft Visio 会创建在配置的拓扑和基础结构的文档中使用的图。您可以编辑和重新排列导入的图以满足文档需求。典型的 Visio 图包括：</span><span class="sxs-lookup"><span data-stu-id="30c72-p110">Exporting your design to Microsoft Visio creates a diagram for use in your documentation purposes of your configured topology and infrastructure. The imported diagram can be edited and rearranged to meet your documentation needs. The typical Visio diagram will include:</span></span>

> [!NOTE]
> <span data-ttu-id="30c72-160">如果你的设计足够大, 需要超过三个前端服务器, 将为前端池、前端服务器、运行 SQL Server 的计算机、IP 地址和 Fqdn 创建一个额外页面。</span><span class="sxs-lookup"><span data-stu-id="30c72-160">If your design is large enough to require more than three Front End Servers, an additional page will be created for the Front End pool, Front End Servers, the computer running SQL Server, IP addresses, and FQDNs.</span></span>

- <span data-ttu-id="30c72-161">已配置 Skype for business Server 2015 网站的全局拓扑图。</span><span class="sxs-lookup"><span data-stu-id="30c72-161">Global Topology - Diagram of configured Skype for Business Server 2015 sites.</span></span>

- <span data-ttu-id="30c72-162">"网站名称" 选项卡-显示 "边缘服务器"、"防火墙"、"公共交换电话网络" (PSTN) 和内部服务器部署的站点配置拓扑。</span><span class="sxs-lookup"><span data-stu-id="30c72-162">Site Name tab - Displays the site configuration topology with Edge Server, firewall, public switched telephone network (PSTN) with gateways, and the internal server deployment.</span></span> <span data-ttu-id="30c72-163">内部部署包括配置的服务器和池, 包括前端池、基于 SQL Server 的服务器、Active Directory 域服务、控制器、Exchange 统一消息 (UM) 服务器、Exchange 邮箱服务器、Office Web Apps 服务器中介服务器和持久聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="30c72-163">Internal deployment consists of configured servers and pools, including the Front End pools, SQL Server-based servers, Active Directory Domain Services, Directors, Exchange Unified Messaging (UM) servers, Exchange Mailbox Servers, Office Web Apps Servers, Mediation Servers, and Persistent Chat Servers.</span></span>

- <span data-ttu-id="30c72-164">边缘网络图-详细介绍边缘服务器配置以及关联的 IP 地址和 Fqdn 的图表。</span><span class="sxs-lookup"><span data-stu-id="30c72-164">Edge Network Diagram - Diagram detailing the Edge Server configuration with associated IP addresses and FQDNs.</span></span> <span data-ttu-id="30c72-165">还包括 DNS 负载平衡和硬件负载平衡器。</span><span class="sxs-lookup"><span data-stu-id="30c72-165">DNS load balancing and hardware load balancers are also included.</span></span> <span data-ttu-id="30c72-166">此外, 将显示 Director 和前端服务器或前端池, 其中关联的 DNS LB 或 HLB 以及分配的 IP 地址 (计划工具支持 IPv4 和 IPv6 地址) 和 FQDN。</span><span class="sxs-lookup"><span data-stu-id="30c72-166">Additionally, Directors and the Front End Server or Front End pool are displayed, with associated DNS LB or HLB and the assigned IP address (the Planning Tool supports both IPv4 and IPv6 addresses) and FQDN.</span></span>

## <a name="see-also"></a><span data-ttu-id="30c72-167">另请参阅</span><span class="sxs-lookup"><span data-stu-id="30c72-167">See also</span></span>
<span data-ttu-id="30c72-168"><a name="Optional_Software"> </a></span><span class="sxs-lookup"><span data-stu-id="30c72-168"></span></span>

[<span data-ttu-id="30c72-169">Installing the Planning Tool</span><span class="sxs-lookup"><span data-stu-id="30c72-169">Installing the Planning Tool</span></span>](https://technet.microsoft.com/library/ebdc9e26-4b22-4b02-85b9-7462bcfe7c93.aspx)
