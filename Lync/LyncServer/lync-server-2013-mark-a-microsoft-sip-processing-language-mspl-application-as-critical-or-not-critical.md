---
title: Lync Server 2013：将 Microsoft SIP 处理语言 (MSPL) 应用程序标记为关键或非关键
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mark a Microsoft SIP Processing Language (MSPL) application as critical or not critical
ms:assetid: df68fdc6-b7e6-4f07-acdc-0cd4c2c888a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182598(v=OCS.15)
ms:contentKeyID: 48185622
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 42c40b115e81736cbbf8769292ab251953d3a752
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524759"
---
# <a name="mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical-in-lync-server-2013"></a>在 Lync Server 2013 中将 Microsoft SIP 处理语言 (MSPL) 应用程序标记为关键或非关键

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-11-01_

Microsoft SIP 处理语言 (MSPL) 服务器应用程序是仅脚本的应用程序，使用的是 MSPL 脚本语言，而不是 Microsoft Lync 2010 API。 某些 MSPL 服务器应用程序被指定为关键。 如果脚本非常关键，则必须在系统启动过程中启动该脚本，才能启动 Lync Server 2013。 如果运行 Lync Server 时脚本失败，则服务器不会关闭，但会停止向脚本发送流量，并会在事件日志中写入错误。

您可以使用 Lync Server 控制面板将 Microsoft SIP 处理语言 (MSPL) 服务器应用程序标记为关键或取消标记。

并非所有脚本都支持此选项。 例如，DefaultRouting 脚本被标记为关键，不能为 DefaultRouting 更改此选项。

<div>

## <a name="to-mark-or-unmark-an-mspl-server-application-as-critical"></a>将 MSPL 服务器应用程序标记或取消标记为关键

1.  从作为 RTCUniversalServerAdmins 组成员的用户帐户 (或具有等效的用户权限) 或分配给 CsServerAdministrator 或 CsAdministrator 角色，请登录到您在其中部署了 Lync Server 2013 的网络中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“拓扑”****，然后单击“服务器应用程序”****。

4.  在“服务器应用程序”**** 页上，单击某个列标题对应用程序进行排序（如果需要），然后单击要修改的服务器应用程序。

5.  单击“操作”****。

6.  单击 " **标记为关键** " 或 " **取消选择" 作为关键** (即，如果脚本支持此选项) 。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中启用或禁用 Microsoft SIP 处理语言 (MSPL) 服务器应用程序](lync-server-2013-enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application.md)  


[在 Lync Server 2013 中查看 Microsoft SIP 处理语言 (MSPL) 服务器应用程序](lync-server-2013-view-microsoft-sip-processing-language-mspl-server-applications.md)  


[管理 Lync Server 2013 拓扑](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

