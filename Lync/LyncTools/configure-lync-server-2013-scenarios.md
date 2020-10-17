---
title: 配置 Lync Server 2013 方案
description: 配置 Lync Server 2013 方案。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Lync Server 2013 Scenarios
ms:assetid: 6705346b-1512-4af3-85e4-64dfa6ee6f80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945596(v=OCS.15)
ms:contentKeyID: 51541420
ms.date: 12/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c4a5b7bd271191067779ac358807cc54918b16bc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555458"
---
# <a name="configure-lync-server-2013-scenarios"></a><span data-ttu-id="b9e9e-103">配置 Lync Server 2013 方案</span><span class="sxs-lookup"><span data-stu-id="b9e9e-103">Configure Lync Server 2013 Scenarios</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b9e9e-104">_**上次修改的主题：** 2016-12-28_</span><span class="sxs-lookup"><span data-stu-id="b9e9e-104">_**Topic Last Modified:** 2016-12-28_</span></span>

<span data-ttu-id="b9e9e-105">若要运行 Lync Server 2013 应力 and Performance Tool (LyncPerfTool) ，必须首先为将要执行的方案配置 Lync Server 2013 拓扑。</span><span class="sxs-lookup"><span data-stu-id="b9e9e-105">To run the Lync Server 2013 Stress and Performance Tool (LyncPerfTool), the Lync Server 2013 topology must first be configured for the scenarios that will be executed.</span></span> <span data-ttu-id="b9e9e-106">如果未配置 Lync Server 2013 或配置不正确，则在大多数情况下负载模拟将会失败。</span><span class="sxs-lookup"><span data-stu-id="b9e9e-106">If Lync Server 2013 is not configured or is configured incorrectly, load simulation will fail in most cases.</span></span> <span data-ttu-id="b9e9e-107">在 Lync Server 2013 压力和性能工具中，我们提供了示例 Lync Server 命令行管理程序脚本和基本资源文件，可用作配置 Lync Server 2013 的起始点。</span><span class="sxs-lookup"><span data-stu-id="b9e9e-107">With the Lync Server 2013 Stress and Performance Tool, we have provided example Lync Server Management Shell scripts and basic resource files that can be used as a starting point for configuring Lync Server 2013.</span></span> <span data-ttu-id="b9e9e-108">本主题介绍了提供的 Windows PowerShell 示例。</span><span class="sxs-lookup"><span data-stu-id="b9e9e-108">This topic describes the Windows PowerShell examples provided.</span></span> <span data-ttu-id="b9e9e-109">请注意，本主题的目标并不是介绍如何在一般情况下配置 Lync Server 2013 的目标。</span><span class="sxs-lookup"><span data-stu-id="b9e9e-109">Note that it is not the goal of this topic to describe how to configure Lync Server 2013 in general.</span></span> <span data-ttu-id="b9e9e-110">有关在 Lync Server 2013 中使用 Windows PowerShell 的详细信息，请参阅 Lync Server 命令行管理程序文档（网址为） <https://technet.microsoft.com/library/gg398474.aspx> 。</span><span class="sxs-lookup"><span data-stu-id="b9e9e-110">For details about working with Windows PowerShell in Lync Server 2013, see the Lync Server Management Shell documentation at <https://technet.microsoft.com/library/gg398474.aspx>.</span></span>

<div>

## <a name="about-running-lync-server-management-shell-scripts"></a><span data-ttu-id="b9e9e-111">关于运行 Lync Server 命令行管理程序脚本</span><span class="sxs-lookup"><span data-stu-id="b9e9e-111">About Running Lync Server Management Shell Scripts</span></span>

<span data-ttu-id="b9e9e-112">我们提供了示例 Lync Server 命令行管理程序脚本，可用于准备运行负载模拟。</span><span class="sxs-lookup"><span data-stu-id="b9e9e-112">We have provided example Lync Server Management Shell scripts that may be used in preparation for running load simulation.</span></span> <span data-ttu-id="b9e9e-113">由于脚本适用于负载模拟，因此它们简单易用，因此可能不适合生产。</span><span class="sxs-lookup"><span data-stu-id="b9e9e-113">Because the scripts are intended for load simulation, they are simple and permissive, and therefore may not be appropriate for production.</span></span> <span data-ttu-id="b9e9e-114">所有脚本都是示例，在某些情况下，必须对其进行修改，以反映您的拓扑。</span><span class="sxs-lookup"><span data-stu-id="b9e9e-114">All scripts are examples and must be reviewed, and, in some cases, modified to reflect your topology.</span></span> <span data-ttu-id="b9e9e-115">我们预计响应组服务 (RGS) 方案需要进行修改，以指定分配给代理组的代理。</span><span class="sxs-lookup"><span data-stu-id="b9e9e-115">At a minimum, we expect that the Response Group Service (RGS) scenario would need to be modified to specify the agents that are assigned to the agent groups.</span></span> <span data-ttu-id="b9e9e-116">不过，您可以选择不模拟此负载。</span><span class="sxs-lookup"><span data-stu-id="b9e9e-116">However, you have the option to not simulate this load.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="b9e9e-117">请注意查看和理解提供的示例。</span><span class="sxs-lookup"><span data-stu-id="b9e9e-117">Take care in reviewing and understanding the examples provided.</span></span> <span data-ttu-id="b9e9e-118">脚本将覆盖拓扑中的任何现有设置。</span><span class="sxs-lookup"><span data-stu-id="b9e9e-118">Scripts will overwrite any existing settings in the topology.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="b9e9e-119">有关使用 Windows PowerShell 和 Lync Server 命令行管理程序的详细信息，请参阅位于的 Lync Server 2013 Windows PowerShell 博客 <A href="https://go.microsoft.com/fwlink/?linkid=203150">https://go.microsoft.com/fwlink/?LinkId=203150</A> 。</span><span class="sxs-lookup"><span data-stu-id="b9e9e-119">For details about using Windows PowerShell and the Lync Server Management Shell, see the Lync Server 2013 Windows PowerShell Blog at <A href="https://go.microsoft.com/fwlink/?linkid=203150">https://go.microsoft.com/fwlink/?LinkId=203150</A>.</span></span>



</div>

</div>

<div>

## <a name="stress-and-performance-tool-client-version-monikers"></a><span data-ttu-id="b9e9e-120">压力和性能工具客户端版本名字对象</span><span class="sxs-lookup"><span data-stu-id="b9e9e-120">Stress and Performance Tool Client Version Monikers</span></span>

<span data-ttu-id="b9e9e-121">如果您已经更改了默认值的设置，您可能需要配置客户端版本检查策略。</span><span class="sxs-lookup"><span data-stu-id="b9e9e-121">You may need to configure the Client Version Check policy if you have changed the settings from the default values.</span></span> <span data-ttu-id="b9e9e-122">有关详细信息，请参阅中的 "配置支持的客户端版本" <https://technet.microsoft.com/library/gg412832(v=ocs.15).aspx> 。</span><span class="sxs-lookup"><span data-stu-id="b9e9e-122">For details, see “Configuring supported client versions” at <https://technet.microsoft.com/library/gg412832(v=ocs.15).aspx>.</span></span> <span data-ttu-id="b9e9e-123">在与 Lync Server 2013 通信时，Lync Server 2013 的压力和性能工具默认使用以下用户代理版本：</span><span class="sxs-lookup"><span data-stu-id="b9e9e-123">The Lync Server 2013 Stress and Performance Tool uses the following User Agent Versions by default when communicating with Lync Server 2013:</span></span>

  - <span data-ttu-id="b9e9e-124">LSPT/15.0.0.0 (Lync Server 2013 压力和性能工具) </span><span class="sxs-lookup"><span data-stu-id="b9e9e-124">LSPT/15.0.0.0 (Lync Server 2013 Stress and Performance Tool)</span></span>

  - <span data-ttu-id="b9e9e-125">OCPHONE/.0.522</span><span class="sxs-lookup"><span data-stu-id="b9e9e-125">OCPHONE/.0.522</span></span>

<span data-ttu-id="b9e9e-126">这些功能适用于 LyncPerfTool 中的移动 (UCWA) 客户端：</span><span class="sxs-lookup"><span data-stu-id="b9e9e-126">These are for the Mobility (UCWA) client in LyncPerfTool:</span></span>

  - <span data-ttu-id="b9e9e-127">Ucwa Perf 工具/Web 会议</span><span class="sxs-lookup"><span data-stu-id="b9e9e-127">Ucwa Perf Tool/Web Conference</span></span>

  - <span data-ttu-id="b9e9e-128">Ucwa Perf 工具/移动</span><span class="sxs-lookup"><span data-stu-id="b9e9e-128">Ucwa Perf Tool/Mobile</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

