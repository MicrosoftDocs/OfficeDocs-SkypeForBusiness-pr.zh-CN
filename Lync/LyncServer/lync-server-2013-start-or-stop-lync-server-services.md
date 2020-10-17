---
title: Lync Server 2013：启动或停止 Lync Server 服务
description: Lync Server 2013：启动或停止 Lync Server 服务。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Start or stop Lync Server 2013 services
ms:assetid: 1c70b4ec-9de5-4f7a-a3c9-c0eb76710505
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520958(v=OCS.15)
ms:contentKeyID: 48183554
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d6e6520cbf6fda38676beab984c2d006061b019
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48541858"
---
# <a name="start-or-stop-lync-server-2013-services"></a>启动或停止 Lync Server 2013 服务

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-02-05_

您可以使用 Lync Server 控制面板启动或停止在特定计算机上运行的所有 Lync Server 2013 服务，或者启动或停止特定服务。

<div>

## <a name="to-start-or-stop-all-lync-server-services-on-a-computer"></a>启动或停止计算机上的所有 Lync Server 服务

1.  从作为 RTCUniversalServerAdmins 组成员的用户帐户 (或具有等效的用户权限) 或分配给 CsServerAdministrator 或 CsAdministrator 角色，请登录到您在其中部署了 Lync Server 2013 的网络中的任何计算机。 您可以通过运行与以下内容类似的命令来确定您是否已分配 CsServerAdministrator 或 CsAdministrator RBAC 角色：
    
        Get-CsAdminRoleAssignment -Identity "kenmyer"

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“拓扑”****，然后单击“状态”****。

4.  在“状态”**** 页上，根据需要对列表进行排序或搜索列表，以查找正在运行要启动或停止的服务的计算机，然后单击该计算机。

5.  单击“操作”****。

6.  单击“启动所有服务”**** 或“停止所有服务”****。

</div>

<div>

## <a name="to-start-or-stop-a-specific-service"></a>启动或停止特定服务

1.  使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“拓扑”****，然后单击“状态”****。

4.  在“状态”**** 页上，根据需要对列表进行排序或搜索列表，以查找正在运行要启动或停止的服务的计算机，然后单击该计算机。

5.  单击“属性”****。

6.  如有必要，对服务列表进行排序，然后单击要启动或停止的服务。

7.  单击“操作”****。

8.  单击“启动服务”**** 或“停止服务”****。

9.  单击“关闭”****。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中阻止服务的会话](lync-server-2013-prevent-sessions-for-services.md)  


[管理 Lync Server 2013 拓扑](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

