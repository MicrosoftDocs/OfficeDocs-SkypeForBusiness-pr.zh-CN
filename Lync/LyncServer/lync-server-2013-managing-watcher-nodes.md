---
title: Lync Server 2013：管理观察程序节点
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing watcher nodes
ms:assetid: 66deaf49-a71f-4a6e-ada0-ea8b688ee921
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688078(v=OCS.15)
ms:contentKeyID: 49733674
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27d2afd025897df4f9b98e235d408a264d2cceb2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724002"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-watcher-nodes-in-lync-server-2013"></a>在 Lync Server 2013 中管理观察程序节点

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-20_

除了修改在观察程序节点上执行的合成事务，管理员还可以使用**CsWatcherNodeConfiguration** cmdlet 执行两个其他重要任务：启用和禁用 "观察程序" 节点，以及将观察程序节点配置为在运行其测试时使用内部 url 或外部 url。

默认情况下，观察程序节点设计为定期运行其所有启用的合成事务。 但是，有时可能需要暂停这些交易。 例如，如果观察程序节点暂时与网络断开连接，则没有理由运行合成事务。 如果没有网络连接，这些事务将保证失败。 如果要临时禁用观察程序节点，请从 Lync Server Management Shell 运行类似下面的命令：

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False

此命令将禁用观察程序节点 atl-观察程序-001.litwareinc.com 上的合成事务的执行。 若要恢复合成事务的执行，请将 Enabled 属性设置回 True （$True）：

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True

<div>


> [!NOTE]  
> Enabled 属性可用于打开或关闭观察程序节点。 如果要永久删除观察程序节点，请使用<STRONG>CsWatcherNodeConfiguration</STRONG> cmdlet：<BR>Remove-CsWatcherNodeConfiguration-Identity "atl-watcher-001.litwareinc.com"<BR>该命令将从指定的计算机中删除所有观察程序节点配置设置，这将阻止计算机自动运行合成事务。 但是，该命令不会卸载 System Center agent 文件或 Lync Server 2013 系统文件。



</div>

默认情况下，观察程序节点在进行测试时使用组织的外部 Url。 但是，观察程序节点也可以配置为使用组织的内部 Url。 这使管理员能够验证位于外围网络内的用户的 URL 访问。 若要将观察程序节点配置为使用内部 Url 而不是外部 Url，请将 UseInternalWebUrls 属性设置为 True （$True）：

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True

如果将此属性重置为默认值 False （$False），则观察程序将使用外部 Url：

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False

</div>

<span> </span>

</div>

</div>

</div>

