---
title: 配置观察程序节点以参与 System Center 发现
description: 配置观察程序节点以参与 System Center 发现。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a watcher node to participate in System Center discovery
ms:assetid: 15c5dcfd-603b-47ea-af1b-8714c2ec08af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204704(v=OCS.15)
ms:contentKeyID: 48183500
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d6a42ae77e0c8bde8b8e4de4461180ad00380a5d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564358"
---
# <a name="configuring-a-watcher-node-in-lync-server-2013-to-participate-in-system-center-discovery"></a>在 Lync Server 2013 中配置观察程序节点以参与 System Center 发现

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-22_

若要确保您的观察程序节点参与到 System Center Operations Manager 的发现过程，必须在已安装 System Center Operations Manager 控制台的计算机上完成以下过程：

1.  在“管理”**** 选项卡上，单击“代理托管”****。

2.  右键单击观察程序节点计算机的名称，然后单击“属性”****。在“属性”**** 对话框的“安全性”**** 选项卡上，选择“允许此代理充当代理并发现其他计算机上的托管对象”****，然后单击“确定”****。

在将观察程序节点配置为充当代理之后，重新启动观察程序节点计算机。 重新启动计算机后，验证该计算机上的 Operations Manager 事件日志中未记录任何错误事件。 在计算机运行15分钟或更长时间后，请使用 Operations Manager 控制台验证 lync Server 计算机是否列在 **lync** 类别下。

</div>

<span> </span>

</div>

</div>

</div>

