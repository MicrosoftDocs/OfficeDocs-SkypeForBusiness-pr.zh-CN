---
title: Lync Server 2013：最佳实践分析工具概述
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Best Practices Analyzer
ms:assetid: c5fcaa05-eb1c-4092-90ad-177b127e795b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591349(v=OCS.15)
ms:contentKeyID: 48185364
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c13554027a1e75bc28943478a883b72beeec7419
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216339"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-best-practices-analyzer-in-lync-server-2013"></a>Lync Server 2013 中的最佳实践分析工具概述

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-19_

您可以使用 Lync Server 2013 和最佳实践分析程序来识别和解决 Lync Server 2013 部署中的问题。 Lync Server 2013，最佳实践分析工具会收集 Lync Server 2013 组件的配置信息。

通过适当的网络访问，最佳实践分析工具可以检查运行 Active Directory 域服务、Exchange Server 统一消息（UM）和 Lync Server 2013 的服务器。 您可以使用最佳做法分析器 Best Practices Analyzer 执行以下操作：

  - 主动执行检查，以验证是否按照建议的最佳做法设置配置。

  - 自动检测 Lync Server 2013 所需的更新。

  - 生成问题列表，例如不够理想的配置设置、不支持的选项、缺少更新或我们不建议的做法等问题。

  - 帮助您排除和修复具体问题。

最佳做法分析器提供以下功能：

  - 极低的安装先决条件。

  - 关于已报告问题的联机文档，包括疑难解答提示。

  - 可以保存供以后查看的配置信息。

  - 最先进的系统分析。

最佳实践分析工具使用一组 XML 配置文件来确定要从 Lync Server 2013 环境中收集的信息。 除了检查 Active Directory 域服务外，还检查 Windows Server 操作系统注册表以及 Windows Management Instrumentation (WMI) 中的设置等源。

最佳实践分析工具会将所收集的数据与 Lync Server 2013 部署的设置和配置的一组预定义规则进行比较。

将收集的数据与预定义规则比较后，该工具会报告问题。 对于报告的每个问题，最佳实践分析工具都提供有关在扫描的 Lync Server 2013 环境中找到的内容和建议的配置的信息。 最佳做法分析器还提供有关具体问题详细信息的链接。

<div>


> [!NOTE]  
> Lync Server 2013，最佳实践分析工具仅收集 Lync Server 2013 组件中的配置信息。 您可以使用该工具的早期版本扫描以前的环境。 有关详细信息，请参阅<A href="lync-server-2013-requirements-for-running-best-practices-analyzer.md">在 Lync Server 2013 中运行最佳实践分析工具的要求</A>。



</div>

</div>

<span> </span>

</div>

</div>

</div>

