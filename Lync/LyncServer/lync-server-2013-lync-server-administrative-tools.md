---
title: Lync Server 2013： Lync Server 管理工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server administrative tools
ms:assetid: 9b006f93-4f3d-461d-89b8-e80a34fdb3c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195756(v=OCS.15)
ms:contentKeyID: 48184972
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 85ba9b1d9848fa51d798dd93b9cbc53daf69a6b7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150423"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-administrative-tools"></a><span data-ttu-id="032ad-102">Lync Server 2013 管理工具</span><span class="sxs-lookup"><span data-stu-id="032ad-102">Lync Server 2013 administrative tools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="032ad-103">_**上次修改的主题：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="032ad-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="032ad-104">本主题介绍了 Lync Server 2013 的管理工具。</span><span class="sxs-lookup"><span data-stu-id="032ad-104">This topic describes the administrative tools for Lync Server 2013.</span></span>

<span data-ttu-id="032ad-105">默认情况下，在每台 Lync Server 服务器上安装管理工具。</span><span class="sxs-lookup"><span data-stu-id="032ad-105">The administrative tools are installed by default on each Lync Server server.</span></span> <span data-ttu-id="032ad-106">此外，您可在其他计算机（如专用管理控制台）上安装这些管理工具。</span><span class="sxs-lookup"><span data-stu-id="032ad-106">Additionally, you can install the administrative tools on other computers, such as dedicated administrative consoles.</span></span> <span data-ttu-id="032ad-107">有关安装管理工具的过程，请参阅[Install Lync Server 2013 管理工具](lync-server-2013-install-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="032ad-107">For procedures to install the administrative tools, see [Install Lync Server 2013 administrative tools](lync-server-2013-install-lync-server-administrative-tools.md).</span></span> <span data-ttu-id="032ad-108">有关打开用于执行管理任务的工具的过程，请参阅[Open Lync Server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="032ad-108">For procedures to open the tools to perform management tasks, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

<span data-ttu-id="032ad-109">在安装或使用 Lync Server 管理工具之前，请确保查看基础结构、操作系统、软件和管理员权限要求。</span><span class="sxs-lookup"><span data-stu-id="032ad-109">Ensure that you review infrastructure, operating system, software, and administrator rights requirements before you install or use the Lync Server administrative tools.</span></span> <span data-ttu-id="032ad-110">有关基础结构要求的详细信息，请参阅[Lync Server 2013 中的管理工具基础结构要求](lync-server-2013-administrative-tools-infrastructure-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="032ad-110">For details about infrastructure requirements, see [Administrative tools infrastructure requirements in Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md).</span></span> <span data-ttu-id="032ad-111">有关操作系统和软件要求的详细信息，以安装 Lync Server 管理工具，请参阅 lync server [2013 中的服务器和工具操作系统支持](lync-server-2013-server-and-tools-operating-system-support.md)、 [lync server 2013 的其他软件要求](lync-server-2013-additional-software-requirements.md)以及[Lync server 2013 中的其他服务器支持和要求](lync-server-2013-additional-server-support-and-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="032ad-111">For details about operating system and software requirements to install the Lync Server administrative tools, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md), [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md), and [Additional server support and requirements in Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md).</span></span> <span data-ttu-id="032ad-112">安装和使用这些工具所需的用户权利和权限在[设置和管理 Lync Server 2013 所需的管理员权限和权限](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)中进行了说明。</span><span class="sxs-lookup"><span data-stu-id="032ad-112">The user rights and permissions required to install and use the tools are described in [Administrator rights and permissions required for setup and administration of Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md).</span></span>

<span data-ttu-id="032ad-113">管理工具由以下几种工具组成：</span><span class="sxs-lookup"><span data-stu-id="032ad-113">The administrative tools consist of the following:</span></span>

  - <span data-ttu-id="032ad-114">**Lync server 部署向导**   用于部署 Lync server 并安装所有管理工具。</span><span class="sxs-lookup"><span data-stu-id="032ad-114">**Lync Server Deployment Wizard**   Use to deploy Lync Server and to install all administrative tools.</span></span>

  - <span data-ttu-id="032ad-115">**Lync Server 拓扑生成器**   用于定义部署中的组件。</span><span class="sxs-lookup"><span data-stu-id="032ad-115">**Lync Server Topology Builder**   Use to define components in your deployment.</span></span>

  - <span data-ttu-id="032ad-116">**Lync Server 控制面板**   用于通过使用基于 web 的界面对部署进行日常管理。</span><span class="sxs-lookup"><span data-stu-id="032ad-116">**Lync Server Control Panel**   Use for ongoing management of your deployment by using a web-based interface.</span></span>

  - <span data-ttu-id="032ad-117">**Lync Server Management Shell**   使用命令行对部署进行日常管理。</span><span class="sxs-lookup"><span data-stu-id="032ad-117">**Lync Server Management Shell**   Use for ongoing management of your deployment by using the command line.</span></span>

  - <span data-ttu-id="032ad-118">**Lync Server 日志记录工具**   用于解决部署中的问题。</span><span class="sxs-lookup"><span data-stu-id="032ad-118">**Lync Server Logging tool**   Use to troubleshoot problems in your deployment.</span></span>

  - <span data-ttu-id="032ad-119">**集中日志记录服务**   收集日志和跟踪来自一台计算机、池、站点或全局的文件。</span><span class="sxs-lookup"><span data-stu-id="032ad-119">**Centralized Logging Service**   Collect logs and trace files from one computer, pool, site or global.</span></span> <span data-ttu-id="032ad-120">选择并定义包含提供程序、标志和跟踪级别的方案。</span><span class="sxs-lookup"><span data-stu-id="032ad-120">Select and define scenarios that contain providers, flags and trace levels.</span></span> <span data-ttu-id="032ad-121">收集、聚合和显示类似于任何基于文本的工具或 Snooper.exe 的工具的日志记录。</span><span class="sxs-lookup"><span data-stu-id="032ad-121">Logging is collected, aggregated and displayed with tools such as any text-based tool or Snooper.exe.</span></span>

<span data-ttu-id="032ad-122">您可以通过主要使用拓扑生成器和 Lync Server 控制面板来管理您的部署。</span><span class="sxs-lookup"><span data-stu-id="032ad-122">You can manage your deployment by primarily using Topology Builder and Lync Server Control Panel.</span></span>

<div>

## <a name="deployment-wizard"></a><span data-ttu-id="032ad-123">部署向导</span><span class="sxs-lookup"><span data-stu-id="032ad-123">Deployment Wizard</span></span>

<span data-ttu-id="032ad-124">必须使用安装媒体上包含的 Lync Server 部署向导将所有管理工具安装到尚未安装 Lync Server 的计算机上。</span><span class="sxs-lookup"><span data-stu-id="032ad-124">You must use the Lync Server Deployment Wizard included on the installation media to install all administrative tools onto a computer on which you have not already installed Lync Server.</span></span> <span data-ttu-id="032ad-125">在管理工具安装过程中，会将 Lync Server 部署向导与其他工具一起安装在本地，以便以后可以使用它为其他组件安装文件，或删除您不希望的组件的文件计算机.</span><span class="sxs-lookup"><span data-stu-id="032ad-125">During the administrative tools installation process, the Lync Server Deployment Wizard is installed locally along with the other tools so that you can later use it to install files for additional components or remove files for components that you do not want on the computer.</span></span>

<span data-ttu-id="032ad-126">有关如何在 Lync Server 安装介质中首次运行 Lync Server 部署向导的详细信息，请参阅[Install Lync server 2013 管理工具](lync-server-2013-install-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="032ad-126">For details about how to run the Lync Server Deployment Wizard for the first time from the Lync Server installation media, see [Install Lync Server 2013 administrative tools](lync-server-2013-install-lync-server-administrative-tools.md).</span></span>

</div>

<div>

## <a name="topology-builder"></a><span data-ttu-id="032ad-127">拓扑生成器</span><span class="sxs-lookup"><span data-stu-id="032ad-127">Topology Builder</span></span>

<span data-ttu-id="032ad-128">有关您可以使用拓扑生成器执行的部署任务的详细信息，请参阅部署文档中的每个服务器角色。</span><span class="sxs-lookup"><span data-stu-id="032ad-128">For details about deployment tasks that you can you perform by using Topology Builder, see the Deployment documentation for each server role.</span></span>

</div>

<div>

## <a name="lync-server-control-panel"></a><span data-ttu-id="032ad-129">Lync 服务器控制面板</span><span class="sxs-lookup"><span data-stu-id="032ad-129">Lync Server Control Panel</span></span>

<span data-ttu-id="032ad-130">您可以使用 Lync Server 2013 控制面板执行管理和维护 Lync Server 2013 所需的大部分管理任务。</span><span class="sxs-lookup"><span data-stu-id="032ad-130">You can use Lync Server 2013 Control Panel to perform most of the administrative tasks required to manage and maintain Lync Server 2013.</span></span> <span data-ttu-id="032ad-131">Lync Server 控制面板为您提供了图形用户界面（GUI），用于管理运行 Lync Server 的服务器的配置，以及组织中的用户、客户端和设备。</span><span class="sxs-lookup"><span data-stu-id="032ad-131">Lync Server Control Panel provides you with a graphical user interface (GUI) to manage the configuration of the servers running Lync Server, in addition to the users, clients, and devices in your organization.</span></span> <span data-ttu-id="032ad-132">Lync Server 命令行管理程序使用 Lync Server 控制面板作为执行 Lync Server 配置的基础机制。</span><span class="sxs-lookup"><span data-stu-id="032ad-132">Lync Server Management Shell uses Lync Server Control Panel as the underlying mechanism to perform Lync Server configuration.</span></span>

<span data-ttu-id="032ad-133">Lync Server 控制面板将自动安装在每个 Lync Server 前端服务器或 Standard Edition server 上。</span><span class="sxs-lookup"><span data-stu-id="032ad-133">Lync Server Control Panel is automatically installed on every Lync Server Front End Server or Standard Edition server.</span></span> <span data-ttu-id="032ad-134">在此版本中，您可以远程管理边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="032ad-134">In this release, you administer Edge Servers remotely.</span></span> <span data-ttu-id="032ad-135">您还可以在另一台计算机上安装 Lync Server 控制面板，例如，要从中集中管理 Lync Server 的管理控制台。</span><span class="sxs-lookup"><span data-stu-id="032ad-135">You can also install Lync Server Control Panel on another computer, such as a management console from which you want to centrally manage Lync Server.</span></span> <span data-ttu-id="032ad-136">有关详细信息，请参阅[Install Lync Server 2013 管理工具](lync-server-2013-install-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="032ad-136">For details, see [Install Lync Server 2013 administrative tools](lync-server-2013-install-lync-server-administrative-tools.md).</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="032ad-137">若要使用 Lync Server 控制面板配置设置，必须使用分配给 CsAdministrator 角色的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="032ad-137">To configure settings using Lync Server Control Panel, you must be logged in using an account that is assigned to the CsAdministrator role.</span></span> <span data-ttu-id="032ad-138">有关 Lync Server 2013 中提供的预定义管理角色的详细信息，请参阅<A href="lync-server-2013-planning-for-role-based-access-control.md">在 Lync server 2013 中规划基于角色的访问控制</A>。</span><span class="sxs-lookup"><span data-stu-id="032ad-138">For details about the predefined administrative roles available in Lync Server 2013, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="032ad-139">若要使用 Lync Server 控制面板配置设置，还必须使用最小屏幕分辨率为 1024 x 768 的计算机。</span><span class="sxs-lookup"><span data-stu-id="032ad-139">To configure settings using Lync Server Control Panel, you must also use a computer with a minimum screen resolution of 1024 x 768.</span></span></P></LI></UL>



</div>

</div>

<div>

## <a name="lync-server-management-shell"></a><span data-ttu-id="032ad-140">Lync Server 命令行管理程序</span><span class="sxs-lookup"><span data-stu-id="032ad-140">Lync Server Management Shell</span></span>

<span data-ttu-id="032ad-141">在 Lync Server 中，Lync Server 命令行管理程序提供了一种新的管理和管理方法。</span><span class="sxs-lookup"><span data-stu-id="032ad-141">In Lync Server, the Lync Server Management Shell provides a new method for administration and management.</span></span> <span data-ttu-id="032ad-142">Lync Server 命令行管理程序是一种功能强大的管理界面，内置于 Windows PowerShell 命令行界面中，其中包含一组专用于 Lync Server 的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="032ad-142">Lync Server Management Shell is a powerful management interface, built on the Windows PowerShell command-line interface, that includes a comprehensive set of cmdlets that are specific to Lync Server.</span></span> <span data-ttu-id="032ad-143">借助 Lync Server 命令行管理程序，您可以获得一组丰富的配置和自动化控件。</span><span class="sxs-lookup"><span data-stu-id="032ad-143">With Lync Server Management Shell, you gain a rich set of configuration and automation controls.</span></span> <span data-ttu-id="032ad-144">拓扑生成器和 Lync Server 控制面板都实现这些 cmdlet 的子集，以支持 Lync Server 的管理。</span><span class="sxs-lookup"><span data-stu-id="032ad-144">Topology Builder and Lync Server Control Panel both implement subsets of these cmdlets to support management of Lync Server.</span></span> <span data-ttu-id="032ad-145">Lync Server 命令行管理程序包含所有 Lync Server 管理任务的 cmdlet，您可以单独使用这些 cmdlet 来管理您的部署。</span><span class="sxs-lookup"><span data-stu-id="032ad-145">The Lync Server Management Shell includes cmdlets for all Lync Server administration tasks, and you can use the cmdlets individually to manage your deployment.</span></span> <span data-ttu-id="032ad-146">有关详细信息，请参阅[Lync Server 2013](lync-server-2013-lync-server-management-shell.md)命令行管理程序文档或每个 cmdlet 的命令行帮助。</span><span class="sxs-lookup"><span data-stu-id="032ad-146">For details, see [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) documentation or the command-line help for each cmdlet.</span></span>

</div>

<div>

## <a name="logging-tool"></a><span data-ttu-id="032ad-147">日志记录工具</span><span class="sxs-lookup"><span data-stu-id="032ad-147">Logging Tool</span></span>

<span data-ttu-id="032ad-148">Lync Server 日志记录工具可通过在产品运行时捕获产品中的日志记录和跟踪信息来简化故障排除。</span><span class="sxs-lookup"><span data-stu-id="032ad-148">The Lync Server Logging Tool facilitates troubleshooting by capturing logging and tracing information from the product while the product is running.</span></span> <span data-ttu-id="032ad-149">您可以使用该工具在任何 Lync Server 服务器角色上运行调试会话。</span><span class="sxs-lookup"><span data-stu-id="032ad-149">You can use the tool to run debug sessions on any Lync Server server role.</span></span> <span data-ttu-id="032ad-150">有关日志记录工具的详细信息，请参阅 TechNet Library 上的 Lync Server 2010 日志记录工具[https://go.microsoft.com/fwlink/p/?linkId=199265](https://go.microsoft.com/fwlink/p/?linkid=199265)文档。</span><span class="sxs-lookup"><span data-stu-id="032ad-150">For details about the Logging Tool, see the Lync Server 2010 Logging Tool documentation on the TechNet Library at [https://go.microsoft.com/fwlink/p/?linkId=199265](https://go.microsoft.com/fwlink/p/?linkid=199265).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="032ad-151">在所有情况下，建议通过 Lync Server 日志记录工具的所有日志记录收集的集中日志记录服务。</span><span class="sxs-lookup"><span data-stu-id="032ad-151">The Centralized Logging Service is recommended for all logging collection over the Lync Server Logging Tool in all circumstances.</span></span> <span data-ttu-id="032ad-152">Lync Server 日志记录工具仍可正常运行，但如果集中日志记录服务已在运行，它将干扰或呈现为大部分的无效。</span><span class="sxs-lookup"><span data-stu-id="032ad-152">The Lync Server Logging Tool will still work, but it will interfere or be rendered mostly ineffective if the Centralized Logging Service is already running.</span></span> <span data-ttu-id="032ad-153">应仅使用集中式日志记录服务或 Lync Server 日志记录工具，但决不会同时使用这两个工具。</span><span class="sxs-lookup"><span data-stu-id="032ad-153">You should use only the Centralized Logging Service or the Lync Server Logging Tool, but never both concurrently.</span></span> <span data-ttu-id="032ad-154">有关集中日志记录服务以及应以独占方式使用它的原因的详细信息，请参阅<A href="lync-server-2013-using-the-centralized-logging-service.md">使用 Lync Server 2013 中的集中日志记录服务</A>。</span><span class="sxs-lookup"><span data-stu-id="032ad-154">For more information on the Centralized Logging Service and why you should use it exclusively, see <A href="lync-server-2013-using-the-centralized-logging-service.md">Using the Centralized Logging Service in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="032ad-155">本部分内容</span><span class="sxs-lookup"><span data-stu-id="032ad-155">In This Section</span></span>

  - [<span data-ttu-id="032ad-156">Lync Server 2013 中的管理工具基础结构要求</span><span class="sxs-lookup"><span data-stu-id="032ad-156">Administrative tools infrastructure requirements in Lync Server 2013</span></span>](lync-server-2013-administrative-tools-infrastructure-requirements.md)

  - [<span data-ttu-id="032ad-157">Lync Server 2013 中的服务器和工具操作系统支持</span><span class="sxs-lookup"><span data-stu-id="032ad-157">Server and tools operating system support in Lync Server 2013</span></span>](lync-server-2013-server-and-tools-operating-system-support.md)

  - [<span data-ttu-id="032ad-158">Lync Server 2013 中的管理工具软件要求</span><span class="sxs-lookup"><span data-stu-id="032ad-158">Administrative tools software requirements in Lync Server 2013</span></span>](lync-server-2013-administrative-tools-software-requirements.md)

  - [<span data-ttu-id="032ad-159">安装和管理 Lync Server 2013 所需的管理员权利和权限</span><span class="sxs-lookup"><span data-stu-id="032ad-159">Administrator rights and permissions required for setup and administration of Lync Server 2013</span></span>](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)

  - [<span data-ttu-id="032ad-160">在 Lync Server 2013 中发布拓扑的要求</span><span class="sxs-lookup"><span data-stu-id="032ad-160">Requirements to publish a topology in Lync Server 2013</span></span>](lync-server-2013-requirements-to-publish-a-topology.md)

  - [<span data-ttu-id="032ad-161">安装 Lync Server 2013 管理工具</span><span class="sxs-lookup"><span data-stu-id="032ad-161">Install Lync Server 2013 administrative tools</span></span>](lync-server-2013-install-lync-server-administrative-tools.md)

  - [<span data-ttu-id="032ad-162">打开 Lync Server 2013 管理工具</span><span class="sxs-lookup"><span data-stu-id="032ad-162">Open Lync Server 2013 administrative tools</span></span>](lync-server-2013-open-lync-server-administrative-tools.md)

  - [<span data-ttu-id="032ad-163">Lync Server 2013 控制面板疑难解答</span><span class="sxs-lookup"><span data-stu-id="032ad-163">Troubleshooting Lync Server 2013 Control Panel</span></span>](lync-server-2013-troubleshooting-lync-server-2013-control-panel.md)

  - [<span data-ttu-id="032ad-164">在 Lync Server 2013 中使用集中日志记录服务</span><span class="sxs-lookup"><span data-stu-id="032ad-164">Using the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-using-the-centralized-logging-service.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="032ad-165">另请参阅</span><span class="sxs-lookup"><span data-stu-id="032ad-165">See Also</span></span>


[<span data-ttu-id="032ad-166">Lync Server 2013 命令行管理程序</span><span class="sxs-lookup"><span data-stu-id="032ad-166">Lync Server 2013 Management Shell</span></span>](lync-server-2013-lync-server-management-shell.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

