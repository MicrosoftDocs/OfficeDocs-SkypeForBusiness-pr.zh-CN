---
title: Lync Server 2013：配置聊天室外接程序
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure add-ins for rooms
ms:assetid: 4eeaf19e-8369-4f6f-af65-a283cf7daa1c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204878(v=OCS.15)
ms:contentKeyID: 48184090
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0eb6525f67f22e09c4bf7ea40f575b3981e9a55c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837441"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-add-ins-for-rooms-in-lync-server-2013"></a>在 Lync Server 2013 中配置聊天室外接程序

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-02-21_

在 Lync Server 2013 "控制面板" 中, 可以使用**持久聊天**页面的**加载项**部分将 url 与持久聊天室相关联。 这些 Url 将出现在 "对话扩展性" 窗格的聊天室中的 Lync 2013 客户端中。 管理员必须将加载项添加到已注册外接程序的列表, 并且聊天室管理器/创建者必须将聊天室与其中一个已注册外接程序相关联, 然后用户才能在其 Lync 2013 客户端中看到此升级。

外接程序用于扩展聊天室内体验。 典型外接程序可能包含指向 Silverlight 应用程序的 URL, 该应用程序在将股票行情滚动到聊天室时进行截获, 并在 "扩展性" 窗格中显示股票历史记录。 其他示例包括将 OneNote 2013 URL 作为外接程序嵌入聊天室，以包括一些共享上下文，如“指导思想”或“今日主题”。

<div>

## <a name="to-configure-add-ins-for-chat-rooms"></a>配置聊天室外接程序

1.  使用分配给 CsPersistentChatAdministrator 或 CsAdministrator 角色的用户帐户登录您的本地部署中的任一计算机。

2.  从 "**开始**" 菜单中, 选择 "Lync Server 控制面板" 或打开一个浏览器窗口, 然后输入管理员 URL。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。
    
    <div>
    

    > [!IMPORTANT]  
    > 你还可以使用 Windows PowerShell cmdlet。 有关详细信息, 请参阅在部署文档中<A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">使用 Windows PowerShell Cmdlet 配置持久聊天服务器</A>。

    
    </div>

3.  在左侧导航栏中，单击“**持久聊天**”，然后单击“**外接程序**”。
    
    对于多个持久聊天服务器池部署, 从下拉列表中选择相应的池。

4.  在“**外接程序**”页上，单击“**新建**”。

5.  在 "**选择服务**" 中, 选择与需要在其中创建外接程序的持久聊天服务器池对应的服务。 外接程序无法从一个池移到另一个池，或者在不同池之间共享。

6.  在“**新建外接程序**”中，执行下列操作：
    
      - 在“**名称**”中，指定新外接程序的名称。
    
      - 在“**URL**”中，指定与外接程序关联的 URL。URL 将限制为 http 和 https 协议。

7.  单击“**提交**”。

</div>

<div>

## <a name="see-also"></a>另请参阅


[打开 Lync Server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)  


[使用 Windows PowerShell Cmdlet 配置持久聊天服务器](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

