---
title: 配置 Lync Server 2013 方案
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
ms.openlocfilehash: 789c3ee8c18b5fb0e92ef9a520152644bebbdde1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730713"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-lync-server-2013-scenarios"></a>配置 Lync Server 2013 方案

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2016-12-28_

若要运行 Lync Server 2013 应力和性能工具（LyncPerfTool），必须首先为将要执行的方案配置 Lync Server 2013 拓扑。 如果未配置 Lync Server 2013 或配置不正确，则在大多数情况下，负载模拟将失败。 使用 Lync Server 2013 应力和性能工具，我们提供了示例 Lync Server Management Shell 脚本和基本资源文件，可用作配置 Lync Server 2013 的起始点。 本主题介绍所提供的 Windows PowerShell 示例。 请注意，本主题的目标不是介绍如何在一般情况下配置 Lync Server 2013 的目标。 有关在 Lync Server 2013 中使用 Windows PowerShell 的详细信息，请参阅 Lync Server Management Shell 文档<https://technet.microsoft.com/en-us/library/gg398474.aspx>。

<div>

## <a name="about-running-lync-server-management-shell-scripts"></a>关于运行 Lync Server 命令行管理程序脚本

我们提供了可用于准备运行负载模拟的 Lync Server Management Shell 脚本示例。 由于脚本适用于负载模拟，因此它们很简单且许可，因此可能不适合生产。 所有脚本都是示例，在某些情况下，必须对其进行修改以反映你的拓扑。 至少，我们认为需要修改响应组服务（RGS）方案，以指定分配给代理组的代理。 但是，你可以选择不模拟此加载。

<div>


> [!WARNING]  
> 请注意查看和理解所提供的示例。 脚本将覆盖拓扑中的任何现有设置。



</div>

<div>


> [!NOTE]  
> 有关使用 Windows PowerShell 和 Lync Server 命令行管理程序的详细信息，请参阅 Lync Server 2013 中的<A href="https://go.microsoft.com/fwlink/?linkid=203150">https://go.microsoft.com/fwlink/?LinkId=203150</A>Windows powershell 博客。



</div>

</div>

<div>

## <a name="stress-and-performance-tool-client-version-monikers"></a>压力和性能工具客户端版本名字对象

如果您已更改默认值的设置，您可能需要配置客户端版本检查策略。 有关详细信息，请参阅 "配置支持的客户<https://technet.microsoft.com/en-us/library/gg412832(v=ocs.15).aspx>端版本"。 在与 Lync Server 2013 通信时，Lync Server 2013 应力和性能工具默认使用以下用户代理版本：

  - LSPT/15.0.0.0 （Lync Server 2013 应力和性能工具）

  - OCPHONE/.0.522

这些适用于 LyncPerfTool 中的移动（UCWA）客户端：

  - Ucwa Perf 工具/Web 会议

  - Ucwa Perf 工具/移动版

</div>

</div>

<span> </span>

</div>

</div>

</div>

