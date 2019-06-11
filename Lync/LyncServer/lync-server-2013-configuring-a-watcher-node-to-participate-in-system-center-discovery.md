---
title: 配置观察程序节点以参与 System Center 发现
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring a watcher node to participate in System Center discovery
ms:assetid: 15c5dcfd-603b-47ea-af1b-8714c2ec08af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204704(v=OCS.15)
ms:contentKeyID: 48183500
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 66be6bd0336471626f2ca4e41a89c3a45b073f05
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837296"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-in-lync-server-2013-to-participate-in-system-center-discovery"></a>在 Lync Server 2013 中配置观察程序节点以参与 System Center 发现

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-22_

若要确保你的观察程序节点参与 System Center Operations Manager 的发现过程, 必须在已安装 System Center Operations Manager 控制台的计算机上完成以下过程:

1.  在 "**管理**" 选项卡上, 单击 "**代理托管**"。

2.  右键单击观察程序节点计算机的名称, 然后单击 "**属性**"。 在 "**属性**" 对话框中的 "**安全**" 选项卡上, 选择 "**允许此代理充当代理并发现其他计算机上的托管对象**", 然后单击 **"确定"**。

将观察程序节点配置为用作代理后, 重新启动观察程序节点计算机。 重新启动计算机后, 请验证该计算机上的 Operations Manager 事件日志中未记录任何错误事件。 当计算机运行15分钟或更长时间后, 请使用 Operations Manager 控制台验证 lync 服务器计算机是否在**lync**类别下列出。

</div>

<span> </span>

</div>

</div>

</div>

