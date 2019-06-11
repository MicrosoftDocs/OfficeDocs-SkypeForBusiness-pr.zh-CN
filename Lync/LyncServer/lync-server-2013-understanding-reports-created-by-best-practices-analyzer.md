---
title: 'Lync Server 2013: 了解最佳做法分析器创建的报告'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Understanding reports created by Best Practices Analyzer
ms:assetid: 1386dd6c-7f3e-4da9-905b-cef1468bf14a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591344(v=OCS.15)
ms:contentKeyID: 48183471
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0903c3bafc4017d5455c188c66de3e1f2cf0b178
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845523"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-reports-created-by-best-practices-analyzer-in-lync-server-2013"></a>了解 Lync Server 2013 中由最佳做法分析器创建的报告

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-10_

最佳做法分析器提供组织的多种类型的报表, 以方便分析和解决问题。 最佳做法分析器识别错误、警告和其他信息等问题。

<div>

## <a name="reports"></a>报告会

你可以通过查看以下每个报表来访问扫描结果:

  - **列表报告**   列表报告按特定条件进行组织。 你可以按类、严重性或问题排列结果。 例如, 如果按类组织结果, 则报表的 "董事" 部分下将包含与主管相关的问题。 你可以查看所有问题, 或仅查看信息性项目。 您可以搜索特定项目 (如内存) 的列表报告。 您也可以打印报表或将其导出。

  - **树报表**   树报表按用于运行扫描的规则和运行扫描时指定的其他选项进行组织。 例如, 与测试拓扑规则相关的问题包含在报告的 "测试拓扑" 部分中。 你可以查看所有问题的详细信息, 或只查看问题摘要。 你可以搜索特定项目 (如内存) 的树报表。 您也可以打印报表或将其导出。

  - ****   其他报表中的其他报表项包括扫描中包含的任务的运行时日志。 可以在其他报表中搜索特定项目 (如内存) 中的项目。 您也可以打印报表或将其导出。

</div>

<div>

## <a name="issues"></a>故障

最佳做法分析器生成的报告指示在扫描环境期间确定的特定问题, 包括以下类型的问题:

  - **错误**   需要您在环境中进行更改的关键问题。 例如, 如果未安装 Lync Server 2013 核心组件, 则会记录错误。
    
    在报表中, 使用红色 X 符号标识被归为错误的问题。 错误将显示在 "**列表报告**" 视图的 "**所有问题**" 选项卡上, 以及 "**详细视图**" 选项卡和 "**树报表**" 视图的 "**摘要视图**" 选项卡上。 如果您不想在报表中看到特定错误, 则可以指定不会为单个实例或报表中该错误的所有实例显示错误。 然后, 该错误仅显示在 "**其他报表**" 视图的 "**隐藏项目**" 选项卡上, 除非您更改设置并指定该错误显示在报表中。

  - ****   与最佳做法实现不一致的警告问题。 这可能会也可能不表示你的环境需要更改。 问题可能是你不需要更改的特定设置的已知问题。 例如, 未在服务器上启动的服务将记录为警告。
    
    在报表中, 使用三角黄色警告符号确定归类为警告的问题。 警告显示在 "**列表报告**" 视图的 "**所有问题**" 选项卡上, 以及 "**详细视图**" 选项卡和 "**树报表**" 视图的 "**摘要视图**" 选项卡上。 如果您不想在报表中看到特定错误, 则可以指定不会为单个实例或报表中该错误的所有实例显示错误。 警告仅显示在 "**其他报表**" 视图的 "**隐藏的项目**" 选项卡上, 除非您更改设置并指定在报表中显示警告。

  - **信息**   包括未分类为错误或警告的所有问题。 例如, Active Directory 域服务中 Lync Server 2013 标准版服务器对象的数量被分类为信息问题。
    
    信息问题显示在 "**列表报告**" 视图的 "**所有问题**" 选项卡上, 以及 "**树报表**" 视图的 "**详细视图**" 选项卡上。

Lync Server 2013, 最佳做法分析器不会对你的环境进行更改来解决问题。 扫描仅检测潜在问题, 并提供报告, 其中包含有关如何解决每个问题的信息。

如果单击某个问题, 将显示特定问题的说明和某些选项。 然后, 您可以执行以下任一操作:

  - 查找有关该问题的更多详细信息, 以及如何解决该问题。

  - 停止在报表中显示问题:
    
      - 停止显示所选实例的问题。
    
      - 停止显示该问题的所有实例的相关问题。
    
    若要查看已停止显示在报表中的问题, 请转到 "**其他报表**" 视图的 "**隐藏项目**" 选项卡。 在此处, 你可以指定再次开始显示报表中的问题。

有关解决特定问题的详细信息, 请参阅[分析和解决 Lync Server 2013 中由最佳做法分析器标识的问题](lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

