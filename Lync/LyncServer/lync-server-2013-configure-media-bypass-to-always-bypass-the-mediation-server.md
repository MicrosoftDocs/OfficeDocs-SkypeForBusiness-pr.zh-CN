---
title: Lync Server 2013：配置媒体旁路以始终绕过中介服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure media bypass to always bypass the Mediation Server
ms:assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425846(v=OCS.15)
ms:contentKeyID: 48183819
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ae9bfa8be276cccc6f31def6fb7014e417841d8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190555"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-media-bypass-in-lync-server-2013-to-always-bypass-the-mediation-server"></a>在 Lync Server 2013 中配置媒体旁路以始终绕过中介服务器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-25_

<div>


> [!NOTE]  
> 本主题假定，对于希望媒体绕过中介服务器的特定站点或特定服务，已为连接到对等方（Internet 电话服务提供商 (ITSP) 的公用电话交换网 (PSTN) 网关、IP-PBX 或会话边界控制器）的所有中继连接配置媒体旁路。<BR>如果启用了呼叫允许控制，则无法将媒体配置为始终绕过中介服务器。 这些设置不兼容，因此在 Lync Server 控制面板用户界面中的设置不兼容，因此是相互排斥的设置。



</div>

除了为与中介服务器的对等方相关联的各个中继连接启用媒体旁路功能外，还必须配置全局媒体旁路设置。 如果您使用本主题中的步骤来配置媒体绕过的全局设置，则假设您在 Lync 终结点和任何对等方之间具有很好的连接，在中继连接上配置了媒体旁路。

如果在 Lync Server 终结点和所有对等方之间没有足够的连接，且其各自的中继连接已启用媒体旁路，则必须将全局媒体旁路设置配置为使用网站和区域信息采用媒体旁路。 这可以在媒体绕过中介服务器时，提供更为细化的控制。 为此，请按照 "[在 Lync server 2013 中配置媒体旁路全局设置" 中的步骤操作，以使用站点和区域信息](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md)，并改为[在 lync Server 2013 中将子网与网络站点关联](lync-server-2013-associate-a-subnet-with-a-network-site.md)。

<div>

## <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a>在全局范围启用媒体旁路以始终绕过中介服务器

1.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

2.  在左侧导航栏中，单击“网络配置”****。

3.  双击列表中的“全局”**** 配置。

4.  在“编辑全局设置”**** 页上，选中“启用媒体旁路”**** 复选框。

5.  单击“始终绕过”****。

6.  单击“提交”****。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中配置媒体旁路](lync-server-2013-configure-media-bypass.md)  
[Lync Server 2013 中的全局媒体旁路选项](lync-server-2013-global-media-bypass-options.md)  
[Lync Server 2013 中的媒体旁路和中介服务器](lync-server-2013-media-bypass-and-mediation-server.md)  


[在 Lync Server 2013 中规划媒体旁路](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

