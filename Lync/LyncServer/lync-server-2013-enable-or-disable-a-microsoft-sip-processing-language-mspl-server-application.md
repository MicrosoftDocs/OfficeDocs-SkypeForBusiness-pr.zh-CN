---
title: Lync Server 2013：启用或禁用 Microsoft SIP 处理语言 (MSPL) Server 应用程序
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
ms.openlocfilehash: 98dce0363a031a2d56c7d8a7cc479452f4fb0382
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528629"
---
# <a name="enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application-in-lync-server-2013"></a>在 Lync Server 2013 中启用或禁用 Microsoft SIP 处理语言 (MSPL) 服务器应用程序

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-21_

您可以使用 Lync Server 控制面板启用或禁用在 Lync Server 2013 环境中运行的 (MSPL) 服务器应用程序的 Microsoft SIP 处理语言。 这些应用程序是仅包含脚本的应用程序，使用脚本语言而非 Microsoft Lync 2013 Preview API。

并非所有脚本都能启用或禁用。例如，DefaultRouting 脚本为启用状态，无法为 DefaultRouting 更改此选项。

<div>

## <a name="to-enable-or-disable-an-mspl-server-application"></a>启用或禁用 MSPL 服务器应用程序

1.  从作为 RTCUniversalServerAdmins 组成员的用户帐户 (或具有等效的用户权限) 或分配给 CsServerAdministrator 或 CsAdministrator 角色，请登录到您在其中部署了 Lync Server 2013 的网络中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“拓扑”****，然后单击“服务器应用程序”****。

4.  在“服务器应用程序”**** 页上，单击某个列标题对应用程序进行排序（如果需要），然后单击要修改的服务器应用程序。

5.  单击“操作”****。

6.  单击“启用应用程序”**** 或“禁用应用程序”****（前提是该脚本支持此选项）。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中将 Microsoft SIP 处理语言 (MSPL) 应用程序标记为关键或非关键](lync-server-2013-mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical.md)  


[在 Lync Server 2013 中查看 Microsoft SIP 处理语言 (MSPL) 服务器应用程序](lync-server-2013-view-microsoft-sip-processing-language-mspl-server-applications.md)  


[管理 Lync Server 2013 拓扑](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

