---
title: Lync Server 2013：启用或禁用 Microsoft SIP 处理语言（MSPL）服务器应用程序
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable a Microsoft SIP Processing Language (MSPL) server application
ms:assetid: b20af38d-224a-4459-991d-0b7eabb3ca7c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182573(v=OCS.15)
ms:contentKeyID: 48185145
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 12fb1160742898b65b14ea17bc10a9c6ed56c780
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736202"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application-in-lync-server-2013"></a>在 Lync Server 2013 中启用或禁用 Microsoft SIP 处理语言（MSPL）服务器应用程序

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-09-21_

可以使用 Lync Server "控制面板" 启用或禁用在 Lync Server 2013 环境中运行的 Microsoft SIP 处理语言（MSPL）服务器应用程序。 这些应用程序是仅使用脚本语言的脚本应用程序，而不是 Microsoft Lync 2013 预览版 API。

并非所有脚本都可以启用或禁用。 例如，启用了 DefaultRouting 脚本，并且不能为 DefaultRouting 更改此选项。

<div>

## <a name="to-enable-or-disable-an-mspl-server-application"></a>启用或禁用 MSPL 服务器应用程序

1.  从 RTCUniversalServerAdmins 组的成员（或具有等效用户权限）或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到你在其中部署 Lync Server 2013 的网络中的任何计算机。

2.  打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击 "**拓扑**"，然后单击 "**服务器应用程序**"。

4.  在 "**服务器应用程序**" 页面上，单击列标题以对应用程序进行排序，然后单击要修改的服务器应用程序。

5.  单击 "**操作**"。

6.  单击 "**启用应用程序**" 或 "**禁用应用程序**" （即，如果脚本支持此选项）。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中将 Microsoft SIP 处理语言（MSPL）应用程序标记为关键或非关键应用程序](lync-server-2013-mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical.md)  


[在 Lync Server 2013 中查看 Microsoft SIP 处理语言 (MSPL) 服务器应用程序](lync-server-2013-view-microsoft-sip-processing-language-mspl-server-applications.md)  


[管理 Lync Server 2013 拓扑](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

