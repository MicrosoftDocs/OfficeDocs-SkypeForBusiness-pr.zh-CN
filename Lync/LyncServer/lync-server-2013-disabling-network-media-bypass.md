---
title: Lync Server 2013：禁用网络媒体旁路
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disabling network media bypass
ms:assetid: 936d2678-d712-4589-b172-b5793013652f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688141(v=OCS.15)
ms:contentKeyID: 49733741
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29508180b54ace29e1ac913dd52d06d374068bfc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528979"
---
# <a name="disabling-network-media-bypass-in-lync-server-2013"></a>在 Lync Server 2013 中禁用网络媒体旁路

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-15_

媒体绕过设置在 Microsoft Lync Server 2013 部署中全局应用。 媒体旁路允许呼叫绕过中介服务器。 有关何时使用媒体旁路的详细信息，请参阅规划部分中的在 [Lync Server 2013 中规划媒体旁路](lync-server-2013-planning-for-media-bypass.md) 。您可以从 Lync Server 控制面板禁用媒体旁路功能。 有关启用和配置中间词旁路的详细信息，请参阅 [在 Lync Server 2013 中启用网络媒体旁路](lync-server-2013-enabling-network-media-bypass.md)

<div>

## <a name="to-disable-media-bypass"></a>禁用媒体旁路

1.  从作为 RTCUniversalServerAdmins 组成员的用户帐户 (或具有等效的用户权限) 或分配给 CsAdministrator 角色，请登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“网络配置”****，然后单击“全局”****。

4.  在“全局”**** 页上，单击“全局”**** 配置。 始终只有一种配置，并且总是名为 Global。

5.  在 " **编辑** " 菜单上，单击 " **查看详细信息**"。

6.  在 " **编辑全局设置** " 页上，清除 " **启用媒体旁路** " 复选框。

7.  单击 " **提交** " 以保存所做的更改。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中启用网络媒体旁路](lync-server-2013-enabling-network-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

