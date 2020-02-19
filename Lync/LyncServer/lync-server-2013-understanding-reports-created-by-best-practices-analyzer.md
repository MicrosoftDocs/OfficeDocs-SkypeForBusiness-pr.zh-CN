---
title: Lync Server 2013：了解最佳实践分析程序创建的报告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Understanding reports created by Best Practices Analyzer
ms:assetid: 1386dd6c-7f3e-4da9-905b-cef1468bf14a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591344(v=OCS.15)
ms:contentKeyID: 48183471
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 376b35a250ae1be9574cfa93debe154d94ca589f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140925"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="understanding-reports-created-by-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="8b19c-102">了解 Lync Server 2013 中的最佳实践分析工具创建的报告</span><span class="sxs-lookup"><span data-stu-id="8b19c-102">Understanding reports created by Best Practices Analyzer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8b19c-103">_**上次修改的主题：** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="8b19c-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="8b19c-p101">最佳做法分析器提供多种类型的报告，旨在促进问题的分析和解决。最佳做法分析器可标识问题，如错误、警告和其他信息。</span><span class="sxs-lookup"><span data-stu-id="8b19c-p101">Best Practices Analyzer provides multiple types of reports that are organized to facilitate the analysis and resolution of issues. Best Practices Analyzer identifies issues such as errors, warnings, and other information.</span></span>

<div>

## <a name="reports"></a><span data-ttu-id="8b19c-106">报告</span><span class="sxs-lookup"><span data-stu-id="8b19c-106">Reports</span></span>

<span data-ttu-id="8b19c-107">通过查看以下每个报告可以访问扫描结果：</span><span class="sxs-lookup"><span data-stu-id="8b19c-107">You can access the results of a scan by viewing each of the following reports:</span></span>

  - <span data-ttu-id="8b19c-108">**列表报告**   列表报告按特定条件进行组织。</span><span class="sxs-lookup"><span data-stu-id="8b19c-108">**List reports**   List reports are organized by specific criteria.</span></span> <span data-ttu-id="8b19c-109">可以按类、严重性或问题来排列结果。</span><span class="sxs-lookup"><span data-stu-id="8b19c-109">You can arrange the results by class, severity, or issue.</span></span> <span data-ttu-id="8b19c-110">例如，如果按类组织结果，则与控制器相关的问题将包括在报告的“控制器”部分下。</span><span class="sxs-lookup"><span data-stu-id="8b19c-110">For example, if you organize results by class, issues related to Directors are included under the Directors section of the report.</span></span> <span data-ttu-id="8b19c-111">可以查看所有问题，或只查看信息性项目。</span><span class="sxs-lookup"><span data-stu-id="8b19c-111">You can view all of the issues, or just the informational items.</span></span> <span data-ttu-id="8b19c-112">可在列表报告中搜索特定项，如内存。</span><span class="sxs-lookup"><span data-stu-id="8b19c-112">You can search a list report for specific items, such as memory.</span></span> <span data-ttu-id="8b19c-113">还可以打印报告或导出报告。</span><span class="sxs-lookup"><span data-stu-id="8b19c-113">You can also print the report or export it.</span></span>

  - <span data-ttu-id="8b19c-114">**树报告**   树报告按用于运行扫描的规则以及运行扫描时指定的其他选项进行组织。</span><span class="sxs-lookup"><span data-stu-id="8b19c-114">**Tree reports**   Tree reports are organized by the rules that are used to run the scan and other options that you specified at the time the scan was run.</span></span> <span data-ttu-id="8b19c-115">例如，与“测试拓扑”规则相关的问题包括在报告的“测试拓扑”部分下。</span><span class="sxs-lookup"><span data-stu-id="8b19c-115">For example, issues related to the Test Topology rules are included under the Test Topology section of the report.</span></span> <span data-ttu-id="8b19c-116">可以查看所有问题的详细信息，或只查看问题的摘要。</span><span class="sxs-lookup"><span data-stu-id="8b19c-116">You can view the details of all the issues, or just a summary of the issues.</span></span> <span data-ttu-id="8b19c-117">可在目录树报告中搜索特定项，如内存。</span><span class="sxs-lookup"><span data-stu-id="8b19c-117">You can search a tree report for specific items, such as memory.</span></span> <span data-ttu-id="8b19c-118">还可以打印报告或导出报告。</span><span class="sxs-lookup"><span data-stu-id="8b19c-118">You can also print the report or export it.</span></span>

  - <span data-ttu-id="8b19c-119">\*\*\*\*   其他报告中的其他报告项包括扫描中所包含的任务的运行时日志。</span><span class="sxs-lookup"><span data-stu-id="8b19c-119">**Other reports**   Items in other reports include the run-time log of tasks that were included in the scan.</span></span> <span data-ttu-id="8b19c-120">可搜索其他报告中的项目以查找特定项（如内存）。</span><span class="sxs-lookup"><span data-stu-id="8b19c-120">You can search the items in other reports for specific items, such as memory.</span></span> <span data-ttu-id="8b19c-121">还可以打印报告或导出报告。</span><span class="sxs-lookup"><span data-stu-id="8b19c-121">You can also print the report or export it.</span></span>

</div>

<div>

## <a name="issues"></a><span data-ttu-id="8b19c-122">问题</span><span class="sxs-lookup"><span data-stu-id="8b19c-122">Issues</span></span>

<span data-ttu-id="8b19c-123">最佳做法分析器生成的报告指示在扫描环境期间标识的特定问题，包括以下类型的问题：</span><span class="sxs-lookup"><span data-stu-id="8b19c-123">The reports generated by Best Practices Analyzer indicate specific issues that are identified during the scan of your environment, including following types of issues:</span></span>

  - <span data-ttu-id="8b19c-124">**错误**   需要您在环境中进行更改的关键问题。</span><span class="sxs-lookup"><span data-stu-id="8b19c-124">**Errors**   Critical issues that require you to make a change in your environment.</span></span> <span data-ttu-id="8b19c-125">例如，如果未安装 Lync Server 2013 核心组件，则会记录错误。</span><span class="sxs-lookup"><span data-stu-id="8b19c-125">For example, if Lync Server 2013 Core Components are not installed, an error is logged.</span></span>

    <span data-ttu-id="8b19c-p106">分类为错误的问题在报告中用红色的 X 符号来标识。错误显示在“列表报告”\*\*\*\* 视图的“所有问题”\*\*\*\* 选项卡以及“目录树报告”\*\*\*\* 视图的“详细视图”\*\*\*\* 选项卡和“摘要视图”\*\*\*\* 选项卡上。如果不想在报告中查看特定错误，可以指定不在报告中为该错误的单个实例或所有实例显示该错误。然后，除非您更改设置并指定在报告中显示该错误，否则该错误将只在“其他报告”\*\*\*\* 视图的“已隐藏项”\*\*\*\* 选项卡中显示。</span><span class="sxs-lookup"><span data-stu-id="8b19c-p106">Issues that are classified as errors are identified in the report by a red X symbol. Errors are displayed on the **All Issues** tab of the **List Reports** view, and on the **Detailed View** tab and the **Summary View** tab of the **Tree Reports** view. If you do not want to see a specific error in a report, you can specify that the error not be shown for a single instance or for all instances of that error in the report. The error is then displayed only on the **Hidden Items** tab of the **Other Reports** view, unless you change the setting and specify that the error be displayed in the report.</span></span>

  - <span data-ttu-id="8b19c-130">\*\*\*\*   与最佳实践实现不一致的警告问题。</span><span class="sxs-lookup"><span data-stu-id="8b19c-130">**Warnings**   Issues that are not consistent with the implementation of a best practice.</span></span> <span data-ttu-id="8b19c-131">这可能表示环境中需要或不需要更改。</span><span class="sxs-lookup"><span data-stu-id="8b19c-131">This may or may not indicate the need for a change in your environment.</span></span> <span data-ttu-id="8b19c-132">该问题可能是无需更改的特定设置的已知问题。</span><span class="sxs-lookup"><span data-stu-id="8b19c-132">The issue could be a known issue with a specific setting that you do not need to change.</span></span> <span data-ttu-id="8b19c-133">例如，未在服务器中启动的服务记录为警告。</span><span class="sxs-lookup"><span data-stu-id="8b19c-133">For example, services that are not started on a server are logged as warnings.</span></span>

    <span data-ttu-id="8b19c-p108">分类为警告的问题在报告中用三角形的黄色警告符号来标识。警告显示在“列表报告”\*\*\*\* 视图的“所有问题”\*\*\*\* 选项卡以及“目录树报告”\*\*\*\* 视图的“详细视图”\*\*\*\* 选项卡和“摘要视图”\*\*\*\* 选项卡上。如果不想在报告中查看特定错误，可以指定不在报告中为该错误的单个实例或所有实例显示该错误。然后，除非您更改设置并指定在报告中显示警告，否则该警告将只在“其他报告”\*\*\*\* 视图的“已隐藏项”\*\*\*\* 选项卡中显示。</span><span class="sxs-lookup"><span data-stu-id="8b19c-p108">Issues that are classified as warnings are identified in the report by a triangular yellow warning symbol. Warnings are displayed on the **All Issues** tab of the **List Reports** view, as well as on the **Detailed View** tab and the **Summary View** tab of the **Tree Reports** view. If you do not want to see a specific error in a report, you can specify that the error not be shown for a single instance or for all instances of that error in the report. The warning is then displayed only on the **Hidden Items** tab of the **Other Reports** view, unless you change the setting and specify that the warning be displayed in the report.</span></span>

  - <span data-ttu-id="8b19c-138">**信息**   包括未分类为错误或警告的所有问题。</span><span class="sxs-lookup"><span data-stu-id="8b19c-138">**Information**   Includes all issues that are not classified as errors or warnings.</span></span> <span data-ttu-id="8b19c-139">例如，Active Directory 域服务中的 Lync Server 2013 Standard Edition server 对象的数量被分类为信息问题。</span><span class="sxs-lookup"><span data-stu-id="8b19c-139">For example, the number of Lync Server 2013 Standard Edition server objects in Active Directory Domain Services is classified as an information issue.</span></span>

    <span data-ttu-id="8b19c-140">信息问题显示在“列表报告”\*\*\*\* 视图的“所有问题”\*\*\*\* 选项卡和“目录树报告”\*\*\*\* 视图的“详细视图”\*\*\*\* 选项卡上。</span><span class="sxs-lookup"><span data-stu-id="8b19c-140">Information issues are displayed on the **All Issues** tab of the **List Reports** view, and on the **Detailed View** tab of the **Tree Reports** view.</span></span>

<span data-ttu-id="8b19c-141">Lync Server 2013，最佳实践分析工具不会对环境进行更改以解决问题。</span><span class="sxs-lookup"><span data-stu-id="8b19c-141">The Lync Server 2013, Best Practices Analyzer does not make changes to your environment to resolve issues.</span></span> <span data-ttu-id="8b19c-142">扫描仅检测潜在问题，并提供包含有关如何解决每个问题的信息的报告。</span><span class="sxs-lookup"><span data-stu-id="8b19c-142">The scan only detects potential issues and provides reports that contain information about how to resolve each issue.</span></span>

<span data-ttu-id="8b19c-p111">如果单击某个问题，则会显示特定问题的解释和一些选项。然后，您可以执行以下任何操作：</span><span class="sxs-lookup"><span data-stu-id="8b19c-p111">If you click an issue, an explanation and some options are displayed for specific issues. Then, you can do any of the following:</span></span>

  - <span data-ttu-id="8b19c-145">查找有关问题的更详细信息以及如何解决问题。</span><span class="sxs-lookup"><span data-stu-id="8b19c-145">Find more detailed information about the issue, and how to resolve it.</span></span>

  - <span data-ttu-id="8b19c-146">停止在报告中显示问题：</span><span class="sxs-lookup"><span data-stu-id="8b19c-146">Stop showing issues in reports:</span></span>

      - <span data-ttu-id="8b19c-147">停止为选定实例显示问题。</span><span class="sxs-lookup"><span data-stu-id="8b19c-147">Stop showing issues for the selected instance.</span></span>

      - <span data-ttu-id="8b19c-148">停止为该问题的所有实例显示问题。</span><span class="sxs-lookup"><span data-stu-id="8b19c-148">Stop showing issues for all instances of that issue.</span></span>

    <span data-ttu-id="8b19c-p112">若要查看已在报告中停止显示的问题，请转到“其他报告”\*\*\*\* 视图的“已隐藏项”\*\*\*\* 选项卡。在此，可以指定在报告中重新开始显示问题。</span><span class="sxs-lookup"><span data-stu-id="8b19c-p112">To see the issues you have stopped showing in reports, go to the **Hidden Items** tab of the **Other Reports** view. From there, you can specify to start showing issues in reports again.</span></span>

<span data-ttu-id="8b19c-151">有关解决特定问题的详细信息，请参阅[在 Lync Server 2013 中分析和解决最佳实践分析工具识别的问题](lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md)。</span><span class="sxs-lookup"><span data-stu-id="8b19c-151">For details about resolving specific issues, see [Analyzing and resolving issues identified by Best Practices Analyzer in Lync Server 2013](lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>
