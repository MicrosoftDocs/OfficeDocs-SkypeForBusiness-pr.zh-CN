---
title: Lync Server 2013：最佳做法分析器概述
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
ms.openlocfilehash: 53e63bf6063803364a679a3cc0724ec1cbeae1a2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755596"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-best-practices-analyzer-in-lync-server-2013"></a>Lync Server 2013 中的最佳做法分析器概述

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-09-19_

你可以使用 Lync Server 2013、最佳做法分析器识别和解决 Lync Server 2013 部署问题。 Lync Server 2013，最佳做法分析器从 Lync Server 2013 组件收集配置信息。

使用正确的网络访问，最佳做法分析器可以检查运行 Active Directory 域服务、Exchange Server 统一消息（UM）和 Lync Server 2013 的服务器。 可以使用最佳做法分析程序执行以下操作：

  - 主动执行检查，验证是否根据推荐的最佳做法设置了配置。

  - 自动检测 Lync Server 2013 所需的更新。

  - 生成问题列表，例如不推荐的配置设置、不支持的选项、缺少的更新或不推荐的做法。

  - 帮助你解决和解决特定问题。

最佳做法分析器提供以下功能：

  - 最低安装必备条件。

  - 有关报告的问题（包括疑难解答提示）的联机文档。

  - 可以保存供以后查看的配置信息。

  - 一流的系统分析。

最佳做法分析器使用一组 XML 配置文件来确定要从 Lync Server 2013 环境中收集的信息。 除了检查 Active Directory 域服务，它还检查源，例如 windows Server 操作系统注册表和 Windows Management Instrumentation （WMI）中的设置。

最佳做法分析器将收集的数据与 Lync Server 2013 部署的设置和配置的一组预定义规则进行比较。

将收集的数据与预定义的规则进行比较之后，该工具将报告问题。 对于它报告的每个问题，最佳做法分析器提供有关在扫描的 Lync Server 2013 环境中找到的内容和建议的配置的信息。 最佳做法分析器还提供有关特定问题的更多详细信息的链接。

<div>


> [!NOTE]  
> Lync Server 2013，最佳做法分析器仅收集 Lync Server 2013 组件的配置信息。 你可以使用该工具的以前版本来扫描以前的环境。 有关详细信息，请参阅<A href="lync-server-2013-requirements-for-running-best-practices-analyzer.md">在 Lync Server 2013 中运行最佳做法分析器的要求</A>。



</div>

</div>

<span> </span>

</div>

</div>

</div>

