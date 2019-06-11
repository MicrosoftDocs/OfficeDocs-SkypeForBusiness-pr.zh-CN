---
title: 验证试点池与旧池的共存情况
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Verify pilot pool coexistence with legacy pool
ms:assetid: 597d0fa6-ca04-4521-b1c2-72d7f35ecd08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204914(v=OCS.15)
ms:contentKeyID: 48184209
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f67b113a4619d90345df9858f348d663383066d7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845070"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a>验证试点池与旧池的共存情况

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-09-28_

<div>

## <a name="verify-the-pool-in-office-communications-server-2007-r2-administrative-tool"></a>验证 Office 通信服务器 2007 R2 管理工具中的池

1.  打开 Office 通信服务器 2007 R2 管理工具。

2.  展开 "**林**" 节点, 展开 "**标准版服务器**" 或 "**企业版池**" 节点, 然后展开 "池" 或 "服务器名称"。

3.  确保在池中运行 Office 通信服务器 2007 R2 服务。
    
    ![Office 通信服务器 2007 R2 管理控制台](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Office 通信服务器 2007 R2 管理控制台")  

</div>

<div>

## <a name="verify-the-pilot-pool-in-lync-server-2013-control-panel"></a>在 Lync Server 2013 控制面板中验证试点池

1.  从作为 CsAdministrator 角色成员的用户帐户登录到 Lync Server 2013 前端服务器。

2.  打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  单击 "**拓扑**"。

4.  验证你部署的服务器是否存在于你的试点池中。
    
    ![Lync Server "控制面板" 拓扑页面](images/JJ204914.a3d1ba5f-c1a7-45e8-b9a5-7cb07b01af8c(OCS.15).jpg "Lync Server \"控制面板\" 拓扑页面")  

</div>

<div>

## <a name="verify-lync-server-2013-services-have-started"></a>验证是否已启动 Lync Server 2013 服务

1.  在 Lync Server 2013 前端服务器上, 从 "**管理工具**" 组中打开 "**服务**" 小程序。

2.  验证列出的服务是否与下图中的列表相符。
    
    ![显示 Lync 服务已启动]的 "服务" 页面(images/JJ204914.fd35d54a-2ab6-4c09-b5e9-fd5bf10f6f51(OCS.15).jpg "显示 Lync 服务已启动")的 "服务" 页面  

</div>

</div>

<span> </span>

</div>

</div>

</div>

