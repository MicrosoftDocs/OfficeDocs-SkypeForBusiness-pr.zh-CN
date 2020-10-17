---
title: Lync Server 2013：查看受信任的应用程序列表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View a list of trusted applications
ms:assetid: f09300b3-67cf-4e70-a51a-23d62479b913
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182604(v=OCS.15)
ms:contentKeyID: 48185844
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d44b6c4fd29109608691914784b02e2ad362b591
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506649"
---
# <a name="view-a-list-of-trusted-applications-in-lync-server-2013"></a>在 Lync Server 2013 中查看受信任的应用程序列表

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-21_

您可以使用 Lync Server 2013 控制面板查看您在 Lync Server 2013 环境中部署的受信任应用程序的列表。 受信任的应用程序是基于 Microsoft 统一通信托管 API (UCMA) 3.0 Core SDK （受 Lync Server 2013 信任）的应用程序。 以下列表概述了此信任关系：

  - 受信任的应用程序不会受到 Lync Server 身份验证的挑战。

  - Lync Server 不会限制受信任的应用程序的 SIP 事务、连接或通过 Internet 的传出语音协议 (VoIP) 呼叫。

  - 受信任应用程序可模拟任何用户，并能在不出现在名单中的情况下参加会议。

  - 受信任应用程序具有高可用性和恢复能力。

在 Lync Server 控制面板中，可以看到应用程序的名称、运行的池以及它们所使用的端口。

<div>

## <a name="to-view-a-list-of-trusted-applications"></a>查看受信任应用程序列表

1.  从分配给 CsServerAdministrator、CsAdministrator、CsHelpDesk 或 CsViewOnlyAdministrator 角色的用户帐户中，登录到内部部署中的任何计算机。 有关 Lync Server 2013 中提供的预定义管理角色的详细信息，请参阅 [在 Lync server 2013 中规划基于角色的访问控制](lync-server-2013-planning-for-role-based-access-control.md)。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“拓扑”****，然后单击“受信任应用程序”****。

4.  在“受信任应用程序”**** 页上，单击某个列标题对应用程序进行排序（如果需要）。

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

