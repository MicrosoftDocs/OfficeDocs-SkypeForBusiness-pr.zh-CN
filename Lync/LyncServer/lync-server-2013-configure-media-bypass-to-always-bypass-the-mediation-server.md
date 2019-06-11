---
title: 'Lync Server 2013: 配置 "绕过媒体" 以始终绕过中介服务器'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure media bypass to always bypass the Mediation Server
ms:assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425846(v=OCS.15)
ms:contentKeyID: 48183819
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7aca094110036692c5ac5327b166a3f81e4b769f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837349"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-media-bypass-in-lync-server-2013-to-always-bypass-the-mediation-server"></a>Configure media bypass in Lync Server 2013 to always bypass the Mediation Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-02-25_

<div>


> [!NOTE]  
> 本主题假定你已针对特定的情况, 在 Internet 电话服务提供商 (ITSP) 处为对等 (公共交换电话网络 (PSTN) 网关、IP PBX 或会话边界控制器 (SBC) 的任何主干连接配置了媒体旁路您希望媒体绕过中介服务器的网站或服务。<BR>您不能将媒体配置为始终绕过中介服务器, 同时启用呼叫许可控制。 这些设置不兼容, 因此在 Lync Server 控制面板用户界面中是相互排斥的设置。



</div>

除了为与中介服务器相关联的对等的单个干线连接启用媒体旁路外, 还必须为媒体旁路配置全局设置。 如果你使用本主题中的步骤来配置媒体绕过的全局设置, 则假设你在 Lync 终结点和任何对等方之间具有良好的连接, 你可以在中继连接上配置了媒体旁路。

如果您在 Lync 服务器终结点和所有对等的中介服务器之间没有良好的连接, 并且其各自的干线连接已启用媒体绕过, 则必须将全局媒体绕过设置配置为使用网站和区域信息采用媒体旁路。 这允许在确定媒体绕过中介服务器时提供更多控制。 若要执行此操作, 请使用在 lync server [2013 中配置媒体绕过全局设置中的步骤, 以使用网站和区域信息](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md), 并[将子网与 lync server 2013 中的网络网站相关联](lync-server-2013-associate-a-subnet-with-a-network-site.md)。

<div>

## <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a>在全局范围启用媒体旁路以始终绕过中介服务器

1.  打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

2.  在左侧导航栏中，单击“网络配置”****。

3.  双击列表中的“全局”**** 配置。

4.  在“编辑全局设置”**** 页上，选中“启用媒体旁路”**** 复选框。

5.  单击“始终绕过”****。

6.  单击“**提交**”。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中配置媒体绕过](lync-server-2013-configure-media-bypass.md)  
[Lync Server 2013 中的全局媒体绕过选项](lync-server-2013-global-media-bypass-options.md)  
[Lync Server 2013 中的媒体绕过和中介服务器](lync-server-2013-media-bypass-and-mediation-server.md)  


[在 Lync Server 2013 中规划媒体旁路](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

