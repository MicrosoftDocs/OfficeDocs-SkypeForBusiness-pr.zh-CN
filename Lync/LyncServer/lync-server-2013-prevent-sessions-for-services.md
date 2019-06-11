---
title: 'Lync Server 2013: 阻止服务会话'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Prevent sessions for services
ms:assetid: 977dcc5c-2aac-48ef-86a1-a8d47b4d9e74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182553(v=OCS.15)
ms:contentKeyID: 48184866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d8d22b74168c784d6a5e19c3ffc32b9e275040b0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823551"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prevent-sessions-for-services-in-lync-server-2013"></a>在 Lync Server 2013 中阻止服务的会话

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-11-01_

可以使用 Lync Server 控制面板阻止在特定计算机上运行的所有 Lync Server 2013 服务的新会话或阻止特定 Lync Server 2013 服务的新会话。

<div>

## <a name="to-prevent-new-sessions-for-all-lync-server-services-on-a-computer"></a>阻止计算机上所有 Lync Server 服务的新会话

1.  从 RTCUniversalServerAdmins 组的成员 (或具有等效用户权限) 或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户, 登录到你在其中部署 Lync Server 2013 的网络中的任何计算机。

2.  打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中, 单击 "**拓扑**", 然后单击 "**状态**"。

4.  在 "**状态**" 页面上, 根据需要对列表进行排序或搜索以查找运行要阻止新会话的服务的计算机, 然后单击该计算机。

5.  单击 "**操作**"。

6.  单击 "**阻止所有服务的新会话**"。

</div>

<div>

## <a name="to-prevent-new-sessions-for-a-specific-service"></a>阻止特定服务的新会话

1.  从 RTCUniversalServerAdmins 组的成员 (或具有等效用户权限) 或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户, 登录到你在其中部署 Lync Server 2013 的网络中的任何计算机。

2.  打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中, 单击 "**拓扑**", 然后单击 "**状态**"。

4.  在 "**状态**" 页面上, 根据需要对列表进行排序或搜索以查找运行要启动或停止的服务的计算机, 然后单击它。

5.  单击 "**属性**"。

6.  对服务列表进行排序 (如有必要), 然后单击要阻止新会话的服务。

7.  单击 "**操作**"。

8.  单击 "**阻止新的服务会话**"。

9.  单击“关闭”****。

</div>

<div>

## <a name="see-also"></a>另请参阅


[管理 Lync Server 2013 拓扑](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

