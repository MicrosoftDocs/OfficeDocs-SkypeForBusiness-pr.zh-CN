---
title: Lync Server 2013：附录 A：使用 cmdlet 部署 Survivable 分支设备
description: Lync Server 2013：附录 A：使用 cmdlet 部署 Survivable 分支设备。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Appendix A: Using cmdlets to deploy a Survivable Branch Appliance'
ms:assetid: 796a26cf-7ec9-453b-8757-6153a6dd86c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398598(v=OCS.15)
ms:contentKeyID: 48184569
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6bf1fe5d86900ec5da95ed9020720149a5015f19
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561868"
---
# <a name="appendix-a-using-cmdlets-to-deploy-a-survivable-branch-appliance-in-lync-server-2013"></a>附录 A：使用 cmdlet 在 Lync Server 2013 中部署 Survivable 分支设备

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-07_

本主题介绍如何使用 Lync Server 命令行管理程序部署 Survivable 分支设备。 请在中央站点执行此过程。

<div>

## <a name="to-deploy-a-survivable-branch-appliance-remotely"></a>远程部署 Survivable 分支设备

1.  按照在 [Lync Server 2013 中将分支站点添加到拓扑中](lync-server-2013-add-branch-sites-to-your-topology.md) 的过程操作，以添加新的分支站点。

2.  将分支站点加入到域中。

3.  将 RTCUniversalSBATechnicians 组添加到本地 Administrators 组。

4.  重新启动服务器，并以 RTCUniversalSBATechnicians 组成员的身份登录到该服务器。

5.  在 Lync Server 命令行管理程序中，键入以下命令，将占位符替换为您的组织的正确信息：
    
        Export-CsConfiguration -FileName C:\CSConfig.zip
        Import-CsConfiguration -LocalStore -FileName C:\CSConfig.zip -Verbose
        Enable-CSReplica -Verbose
        Enable-CsComputer -Verbose
        Request-CsCertificate -New -Type default -CA <YourCA> -Verbose
        Set-CsCertificate -Type Default -Thumbprint <YourCertThumbprint>
        Start-cswindowsservice -verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

