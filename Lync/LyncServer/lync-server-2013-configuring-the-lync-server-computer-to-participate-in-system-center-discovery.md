---
title: 将 Lync Server 计算机配置为参与 System Center 发现
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the Lync Server computer to participate in System Center discovery
ms:assetid: 2f9c9cb0-3120-4571-9cd2-657c2123fe21
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204776(v=OCS.15)
ms:contentKeyID: 48183731
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5f5c313bab7c307a0dbc1a8e78269a94663d9c67
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191885"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-the-lync-server-2013-computer-to-participate-in-system-center-discovery"></a>将 Lync Server 2013 计算机配置为参与 System Center 发现

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-20_

若要确保新的 Lync Server 代理参与了 System Center Operations Manager 的发现过程，必须在安装了 System Center Operations Manager 控制台的每台计算机上完成以下过程：

1.  在“管理”**** 选项卡上，单击“代理托管”****。

2.  右键单击计算机的名称，然后单击“属性”****。在“属性”**** 对话框中的“安全性”**** 选项卡上，选择“允许此代理充当代理并发现其他计算机上的托管对象”****，然后单击“确定”****。

完成步骤 2 后，重新启动健康代理服务。（重新启动该服务将“强制”发现新计算机。如果您没有重新启动该服务，则 System Center Operations Manager 可能需要长达 4 小时的时间才能发现新计算机。）在重新启动该服务后，验证该计算机上的 Operations Manager 事件日志中是否记录了任何错误事件。

</div>

<span> </span>

</div>

</div>

</div>

