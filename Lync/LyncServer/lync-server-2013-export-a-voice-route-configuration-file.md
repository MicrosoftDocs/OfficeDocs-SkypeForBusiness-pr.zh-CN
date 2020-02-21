---
title: Lync Server 2013：导出语音路由配置文件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Export a voice route configuration file
ms:assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398081(v=OCS.15)
ms:contentKeyID: 48183248
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b1549cabf8163275c202075dcfc7ef081b38d20
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202378"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="export-a-voice-route-configuration-file-in-lync-server-2013"></a>在 Lync Server 2013 中导出语音路由配置文件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-11-01_

如果要在不发布的情况下保存语音路由配置，请按照以下步骤使用 Lync Server 控制面板的 "导出" 和 "导入" 命令来保存和检索语音路由配置的快照。 当您导入语音路由配置文件（. vcfg），但同时在服务器上对语音路由配置进行了更改时，在 Lync Server 控制面板中的 "**语音路由**" 组中的页面将指示对语音路由有未提交的更改。 这些未提交的更改是两种需要调节的配置之间的差异。

如果对组中任何页面上的设置进行了任何未提交的更改，则所做的更改会保存在导出的语音配置文件（vcfg）中。 这使您可以在发布更改之前在多个会话期间进行语音路由配置更改。

<div>

## <a name="to-export-a-voice-routing-configuration"></a>导出语音路由配置

1.  以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。 有关详细信息，请参阅[Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“语音路由”****。

4.  在“操作”**** 菜单上，单击“导出配置”****。

5.  指定位置和文件名，然后单击“保存”****。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中导入语音路由配置文件](lync-server-2013-import-a-voice-route-configuration-file.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

