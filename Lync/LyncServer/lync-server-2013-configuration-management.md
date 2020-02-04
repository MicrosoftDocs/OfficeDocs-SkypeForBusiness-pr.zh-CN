---
title: Lync Server 2013：配置管理
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuration management
ms:assetid: 00ea1196-cb40-427f-99a4-5e8037cbf367
ms:mtpsurl: https://technet.microsoft.com/library/Dn720316(v=OCS.15)
ms:contentKeyID: 63969570
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6997f64695a4df606e6fbaa9767f22be04de6615
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741392"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuration-management-in-lync-server-2013"></a><span data-ttu-id="ac55b-102">Lync Server 2013 中的配置管理</span><span class="sxs-lookup"><span data-stu-id="ac55b-102">Configuration management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ac55b-103">_**主题上次修改时间：** 2015-05-15_</span><span class="sxs-lookup"><span data-stu-id="ac55b-103">_**Topic Last Modified:** 2015-05-15_</span></span>

<span data-ttu-id="ac55b-104">配置管理是记录和跟踪硬件和软件资产以及系统配置信息的过程。</span><span class="sxs-lookup"><span data-stu-id="ac55b-104">Configuration management is the process of recording and tracking hardware and software assets and system configuration information.</span></span> <span data-ttu-id="ac55b-105">它通常用于跟踪软件许可证、维护客户端计算机和服务器的标准硬件和软件内部版本，并定义新计算机的命名标准。</span><span class="sxs-lookup"><span data-stu-id="ac55b-105">It is generally used to track software licenses, maintain a standard hardware and software build for client computers and servers, and define naming standards for new computers.</span></span> <span data-ttu-id="ac55b-106">配置管理通常涵盖以下类别：</span><span class="sxs-lookup"><span data-stu-id="ac55b-106">Configuration management generally covers the following categories:</span></span>

  - <span data-ttu-id="ac55b-107">**硬件**   此类别跟踪 IT 组织拥有的设备、设备所在的设备以及使用设备的人员。</span><span class="sxs-lookup"><span data-stu-id="ac55b-107">**Hardware**   This category tracks the pieces of equipment that the IT organization owns, where equipment is located, and who uses equipment.</span></span> <span data-ttu-id="ac55b-108">此信息使组织能够规划和预算升级、维护标准硬件版本、报告 IT 资产价值以进行会计用途，并帮助防止盗窃。</span><span class="sxs-lookup"><span data-stu-id="ac55b-108">This information enables an organization to plan and budget for upgrades, maintain standard hardware builds, report on the value of IT assets for accounting purposes, and help prevent theft.</span></span>

  - <span data-ttu-id="ac55b-109">**软件**   此类别跟踪安装在每台计算机上的软件、版本号以及许可证的保留位置。</span><span class="sxs-lookup"><span data-stu-id="ac55b-109">**Software**   This category tracks software that is installed on each computer, the version numbers, and where the licenses are held.</span></span> <span data-ttu-id="ac55b-110">此信息有助于规划升级，确保软件获得许可，并检测是否存在未经授权（和未经许可）的软件。</span><span class="sxs-lookup"><span data-stu-id="ac55b-110">This information helps plan upgrades, to ensure that software is licensed, and detect the presence of unauthorized (and unlicensed) software.</span></span>

  - <span data-ttu-id="ac55b-111">**标准版本**   此类别跟踪客户端计算机和服务器的当前标准内部版本，以及客户端计算机和服务器是否满足此标准。</span><span class="sxs-lookup"><span data-stu-id="ac55b-111">**Standard Builds**   This category tracks the current standard build for the client computers and servers and whether the client computers and servers meet this standard.</span></span> <span data-ttu-id="ac55b-112">定义和强制实施标准生成有助于支持人员，因为员工只需要维护每个软件的有限数量的版本。</span><span class="sxs-lookup"><span data-stu-id="ac55b-112">Defining and enforcing standard builds helps support staff because the staff is required to maintain only a limited number of versions of each piece of software.</span></span>

  - <span data-ttu-id="ac55b-113">**累积更新和修补程序**   此类别可跟踪测试和批准使用的服务包和哪些计算机处于最新状态。</span><span class="sxs-lookup"><span data-stu-id="ac55b-113">**Cumulative Updates and Hotfixes**   This category tracks which service packs are tested and approved for use and which computers are up to date.</span></span> <span data-ttu-id="ac55b-114">此信息对于降低计算机遭到破坏的风险和检测已安装未经批准的更新的用户非常重要。</span><span class="sxs-lookup"><span data-stu-id="ac55b-114">This information is important to reduce the risk of computers being compromised and to detect users who have installed unapproved updates.</span></span>

  - <span data-ttu-id="ac55b-115">**系统配置信息**   此类别跟踪系统的功能、系统元素之间的交互以及依赖于平稳运行的系统的进程。</span><span class="sxs-lookup"><span data-stu-id="ac55b-115">**System Configuration Information**   This category tracks the function of a system, the interaction between system elements, and the processes that depend on a system that is running smoothly.</span></span> <span data-ttu-id="ac55b-116">例如，可以在一台服务器上配置第三方代理服务器。</span><span class="sxs-lookup"><span data-stu-id="ac55b-116">For example, third-party proxy server may be configured on a single server.</span></span> <span data-ttu-id="ac55b-117">应了解代理服务器对此服务器的依赖，并且如果出现故障，可能需要应急计划。</span><span class="sxs-lookup"><span data-stu-id="ac55b-117">The proxy server’s dependence on this server should be understood and contingency plans may be required if there is a failure.</span></span> <span data-ttu-id="ac55b-118">如果代理服务器可以配置为同时与另一个前端服务器通信，则依赖项和应急计划可能会发生更改。</span><span class="sxs-lookup"><span data-stu-id="ac55b-118">If the proxy server can be configured to also communicate with another front-end server, dependencies and contingency plans will probably change.</span></span>

<div>

## <a name="implementing-configuration-management"></a><span data-ttu-id="ac55b-119">实现配置管理</span><span class="sxs-lookup"><span data-stu-id="ac55b-119">Implementing configuration management</span></span>

<span data-ttu-id="ac55b-120">确定需要管理的项目后，通过收集数据和报告数据来实现配置管理。</span><span class="sxs-lookup"><span data-stu-id="ac55b-120">After you determine what items need managing, implement configuration management by collecting data and reporting data.</span></span> <span data-ttu-id="ac55b-121">小型组织最简单的方法是手动收集数据（客户端计算机、操作系统、已安装软件的数量和型号），并将其保存在 Office Word 或 Office Excel 文档中。</span><span class="sxs-lookup"><span data-stu-id="ac55b-121">The simplest approach for small organizations is to collect data manually (number and model of client computers, operating system, installed software) and save it in an Office Word or Office Excel document.</span></span> <span data-ttu-id="ac55b-122">对于较大、更复杂且不断变化的系统，必须自动发现资产和详细信息的收集。</span><span class="sxs-lookup"><span data-stu-id="ac55b-122">For larger, more complex, and constantly changing systems, the discovery of assets and collection of detailed information must be automated.</span></span> <span data-ttu-id="ac55b-123">确定哪些信息与你的组织相关，并将其记录在数据库中。</span><span class="sxs-lookup"><span data-stu-id="ac55b-123">Decide what information is relevant to your organization and record it in a database.</span></span>

<span data-ttu-id="ac55b-124">配置管理数据库是在以下领域支持人员和管理的有用工具：</span><span class="sxs-lookup"><span data-stu-id="ac55b-124">The configuration management database is a useful tool for support staff and management in the following areas:</span></span>

  - <span data-ttu-id="ac55b-125">**安全审核**   通过数据库，你可以确定运行 Lync Server 和客户端计算机系统的服务器，这些服务器必须已应用修补程序，或者已错过安装 service pack 或最新防病毒更新。</span><span class="sxs-lookup"><span data-stu-id="ac55b-125">**Security Audits**   The database enables you to identify servers that are running Lync Server and client computer systems that must have hotfixes applied or that have missed the installation of a service pack or the latest antivirus updates.</span></span>

  - <span data-ttu-id="ac55b-126">**软件安装**   识别客户端软件版本和跟踪它们将帮助管理员规划版本更新和新安装，还将帮助管理员提供许可文档和合规性。</span><span class="sxs-lookup"><span data-stu-id="ac55b-126">**Software Installation**   Identifying client software versions and tracking them will aid administrators in planning version updates and new installs and also by helping with licensing documentation and compliance.</span></span>

  - <span data-ttu-id="ac55b-127">**配置信息**   如果您维护的所有设置的最新列表均已更改为默认值，那么您将能够快速、高效地解决问题。</span><span class="sxs-lookup"><span data-stu-id="ac55b-127">**Configuration Information**   If you maintain an up-to-date list of all settings that were changed from their default, then you'll be able to troubleshoot issues quickly and more effectively.</span></span>

  - <span data-ttu-id="ac55b-128">**规划升级**   如果容量检查发现您的 Lync 数据库服务器上需要额外的存储空间，请务必了解每台服务器是否有内部 RAID 控制器。</span><span class="sxs-lookup"><span data-stu-id="ac55b-128">**Planning Upgrades**   If a capacity review reveals that additional storage space is required on your Lync database servers, it’s important to know whether each server has an internal RAID controller.</span></span> <span data-ttu-id="ac55b-129">如果是，则它们是同一型号？</span><span class="sxs-lookup"><span data-stu-id="ac55b-129">If they do, then are they the same model?</span></span> <span data-ttu-id="ac55b-130">是否已安装相同数量的磁盘？</span><span class="sxs-lookup"><span data-stu-id="ac55b-130">Do they have the same number of disks installed?</span></span> <span data-ttu-id="ac55b-131">配置管理数据库将指示每种情况下可以安装的磁盘类型、编号和升级路径。</span><span class="sxs-lookup"><span data-stu-id="ac55b-131">The configuration management database will indicate the type of disk that can be installed, the number, and the upgrade path in each case.</span></span>

</div>

<div>

## <a name="tools-used-for-configuration-management"></a><span data-ttu-id="ac55b-132">用于配置管理的工具</span><span class="sxs-lookup"><span data-stu-id="ac55b-132">Tools used for configuration management</span></span>

<span data-ttu-id="ac55b-133">有许多工具可用于发现、审核和报告资源。</span><span class="sxs-lookup"><span data-stu-id="ac55b-133">There are many tools to discover, audit, and report assets.</span></span> <span data-ttu-id="ac55b-134">本部分将讨论其中的一些工具。</span><span class="sxs-lookup"><span data-stu-id="ac55b-134">Some of these tools are discussed in this section.</span></span>

  - <span data-ttu-id="ac55b-135">**自动脚本**   你可以编写简单的脚本来报告诸如操作系统、service pack 级别和软件是否存在于特定计算机集的项目。</span><span class="sxs-lookup"><span data-stu-id="ac55b-135">**Automated Scripts**   You can write simple scripts to report items such as the operating system, service pack level, and whether software exists on a specific set of computers.</span></span> <span data-ttu-id="ac55b-136">你可以将这些脚本编写为组织的确切要求。</span><span class="sxs-lookup"><span data-stu-id="ac55b-136">You can write these scripts to an organization’s exact requirements.</span></span> <span data-ttu-id="ac55b-137">但是，所需数量的脚本及其复杂性可能会使脚本的创建和维护成本高昂。</span><span class="sxs-lookup"><span data-stu-id="ac55b-137">However, the required number of scripts and their complexity can make scripts expensive to create and maintain.</span></span>

  - <span data-ttu-id="ac55b-138">**自动化工具**   根据您的企业规模和组织需求，您可能需要考虑使用自动工具。</span><span class="sxs-lookup"><span data-stu-id="ac55b-138">**Automated Tools**   Depending on the size of your business and your organizational needs, you may want to consider using automated tools.</span></span> <span data-ttu-id="ac55b-139">诸如 Microsoft 终结点配置管理器之类的工具合并标准报表模板（如 service pack 级别），并允许你创建自定义报表（例如，自定义应用程序）。</span><span class="sxs-lookup"><span data-stu-id="ac55b-139">Tools such as Microsoft Endpoint Configuration Manager incorporate standard report templates (such as service pack level) and also enable you to create customized reports, for example, for a custom application.</span></span> <span data-ttu-id="ac55b-140">Microsoft 终结点配置管理器还可以用于报告硬件和软件配置。</span><span class="sxs-lookup"><span data-stu-id="ac55b-140">The Microsoft Endpoint Configuration Manager can also be used to report on hardware and software configurations.</span></span>

</div>

<div>

## <a name="relationship-with-change-management"></a><span data-ttu-id="ac55b-141">与更改管理的关系</span><span class="sxs-lookup"><span data-stu-id="ac55b-141">Relationship with change management</span></span>

<span data-ttu-id="ac55b-142">配置管理与变更管理紧密相关。</span><span class="sxs-lookup"><span data-stu-id="ac55b-142">Configuration management is closely related to change management.</span></span> <span data-ttu-id="ac55b-143">配置管理确定需要更改，并确定和记录更改已发生。</span><span class="sxs-lookup"><span data-stu-id="ac55b-143">Configuration management identifies the need for change and identifies and records that a change has occurred.</span></span> <span data-ttu-id="ac55b-144">例如，配置管理数据库可用于标识需要修补程序的服务器。</span><span class="sxs-lookup"><span data-stu-id="ac55b-144">For example, the configuration management database can be used to identify servers that require a hotfix.</span></span> <span data-ttu-id="ac55b-145">然后，更改管理定义应用修补程序的过程。</span><span class="sxs-lookup"><span data-stu-id="ac55b-145">Change management then defines the process for applying the hotfix.</span></span>

<span data-ttu-id="ac55b-146">相反，如果新的累积更新已推出，则更改管理过程应将此信息提供给配置管理系统。</span><span class="sxs-lookup"><span data-stu-id="ac55b-146">Conversely, if a new cumulative update is rolled out, the change management process should supply this information to the configuration management system.</span></span> <span data-ttu-id="ac55b-147">配置管理工具可能需要配置为识别新软件，以便他们能够发现和跟踪软件的部署位置和时间。</span><span class="sxs-lookup"><span data-stu-id="ac55b-147">The configuration management tools will probably need to be configured to identify the new software so that they can discover and track where and when the software is deployed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

