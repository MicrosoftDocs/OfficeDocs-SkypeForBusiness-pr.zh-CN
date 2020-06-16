---
title: 阻止服务的会话
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Prevent sessions for services
ms:assetid: 4b541c72-cdc1-4f86-a5a8-c43c24f41d8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688049(v=OCS.15)
ms:contentKeyID: 49733642
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f85595acd38e69af9fb8108cab44f4839904799a
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756551"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="prevent-sessions-for-services"></a>阻止服务的会话

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-04_

您可以使用 Microsoft Lync Server 2010 控制面板阻止在特定计算机上运行的所有 Lync Server 2010 服务的新会话或阻止特定 Lync Server 2010 服务的新会话。

<div>

## <a name="to-prevent-new-sessions-for-all-lync-server-services-on-a-computer"></a>阻止计算机上所有 Lync Server 服务的新会话

1.  从作为 RTCUniversalServerAdmins 组成员的用户帐户（或具有等效的用户权限）或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户，登录到您在其中部署了 Lync Server 2013 的网络中的任何计算机。

2.  打开“Lync Server 控制面板”。

3.  在左侧导航栏中，单击“拓扑”****，然后单击“状态”****。

4.  在“状态”**** 页上，根据需要对列表进行排序或搜索，以查找正在运行要对其阻止新会话的服务的计算机，然后单击该计算机。

5.  单击“操作”****。

6.  单击“阻止所有服务的新会话”****。

</div>

<div>

## <a name="to-prevent-new-sessions-for-a-specific-service"></a>阻止特定服务的新会话

1.  从作为 RTCUniversalServerAdmins 组成员的用户帐户（或具有等效的用户权限）或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户，登录到您在其中部署了 Lync Server 2013 的网络中的任何计算机。

2.  打开“Lync Server 控制面板”。

3.  在左侧导航栏中，单击“拓扑”****，然后单击“状态”****。

4.  在“状态”**** 页上，根据需要对列表进行排序或搜索列表，以查找正在运行要启动或停止的服务的计算机，然后单击该计算机。

5.  单击“属性”****。

6.  如有必要，对服务列表进行排序，然后单击要对其阻止新会话的服务。

7.  单击“操作”****。

8.  单击“阻止服务的新会话”****。

9.  单击“关闭”****。

</div>

</div>

<span> </span>

</div>

</div>

</div>

