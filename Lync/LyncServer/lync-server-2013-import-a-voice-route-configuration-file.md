---
title: Lync Server 2013：导入语音路由配置文件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Import a voice route configuration file
ms:assetid: 4bac05e5-ed8b-4f10-96b0-b8a65ff356ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398301(v=OCS.15)
ms:contentKeyID: 48184049
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 91f0d523cad59ee965fa90bdf6907ea030cc8a3b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830029"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="import-a-voice-route-configuration-file-in-lync-server-2013"></a>在 Lync Server 2013 中导入语音路由配置文件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-11-01_

如果要在不发布的情况下保存语音路由配置, 请按照以下步骤使用 Lync Server 控制面板配置导出和导入命令来保存和检索你的语音路由配置的快照。 当您导入一个语音路由配置文件 (vcfg), 但同时在服务器上对语音路由配置进行了更改时, Lync Server 控制面板中的 "**语音路由**" 组中的页面将指示有对语音路由的未提交更改。 这些未提交的更改是两种需要调节的配置之间的差异。

如果你对组内任何页面上的设置进行了任何未提交的更改, 则所做的更改将保存在导出的语音配置文件 (vcfg) 中。 这使你可以在发布更改之前在多个会话期间进行语音路由配置更改。

<div>

## <a name="to-import-a-voice-routing-configuration"></a>导入语音路由配置

1.  以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。 有关详细信息, 请参阅[在 Lync Server 2013 中委派设置权限](lync-server-2013-delegate-setup-permissions.md)。

2.  打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“语音路由”****。

4.  在“操作”**** 菜单上，单击“导入配置”****。

5.  找到要导入的配置文件，然后单击“打开”****。

6.  单击“提交”****，然后单击“全部提交”****。
    
    <div>
    

    > [!NOTE]  
    > 任何时候导入语音配置文件，都必须运行“全部提交”<STRONG></STRONG>命令以发布配置更改。 有关详细信息, 请参阅操作文档中的<A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 中的 "发布待处理的语音路由配置更改"</A> 。

    
    </div>

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中导出语音路由配置文件](lync-server-2013-export-a-voice-route-configuration-file.md)  
[将挂起的更改发布到 Lync Server 2013 中的语音路由配置](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

