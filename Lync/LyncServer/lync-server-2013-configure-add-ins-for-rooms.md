---
title: Lync Server 2013：配置聊天室的外接程序
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure add-ins for rooms
ms:assetid: 4eeaf19e-8369-4f6f-af65-a283cf7daa1c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204878(v=OCS.15)
ms:contentKeyID: 48184090
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27dd6ab5cdd6ca67d94071049a9615731735d8aa
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146585"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-add-ins-for-rooms-in-lync-server-2013"></a>在 Lync Server 2013 中配置聊天室的外接程序

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-21_

在 Lync Server 2013 控制面板中，可以使用 "**持久聊天**" 页的 "**加载项**" 部分将 url 与持久聊天室相关联。 这些 Url 显示在对话可扩展性窗格中聊天室的 Lync 2013 客户端中。 管理员必须将外接程序添加到已注册的外接程序列表中，聊天室管理员/创建者必须将聊天室与注册的外接程序关联，然后用户才能在其 Lync 2013 客户端中看到此升级。

外接程序用于扩展聊天室内体验。 典型加载项可能包含指向 Silverlight 应用程序的 URL，在将股票代号发布到聊天室时，会对该 URL 进行拦截，并在 "可扩展性" 窗格中显示股票历史记录。 其他示例包括将 OneNote 2013 URL 作为外接程序嵌入聊天室，以包括一些共享上下文，如“指导思想”或“今日主题”。

<div>

## <a name="to-configure-add-ins-for-chat-rooms"></a>配置聊天室外接程序

1.  使用分配给 CsPersistentChatAdministrator 或 CsAdministrator 角色的用户帐户登录到您的本地部署中的任一计算机。

2.  从 "**开始**" 菜单中，选择 "Lync Server 控制面板" 或打开一个浏览器窗口，然后输入管理 URL。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。
    
    <div>
    

    > [!IMPORTANT]  
    > 您还可以使用 Windows PowerShell cmdlet。 有关详细信息，请参阅部署文档中的<A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">使用 Windows PowerShell Cmdlet 配置持久聊天服务器</A>。

    
    </div>

3.  在左侧导航栏中，单击“持久聊天”****，然后单击“外接程序”****。
    
    对于多个持久聊天服务器池部署，请从下拉列表中选择相应的池。

4.  在“外接程序”**** 页上，单击“新建”****。

5.  在 "**选择服务**" 中，选择与需要在其中创建外接程序的持久聊天服务器池对应的服务。 外接程序无法从一个池移到另一个池，或者在不同池之间共享。

6.  在“新建外接程序”**** 中，执行下列操作：
    
      - 在“名称”**** 中，指定新外接程序的名称。
    
      - 在“URL”**** 中，指定与外接程序关联的 URL。URL 限制为 http 和 https 协议。

7.  单击“提交”****。

</div>

<div>

## <a name="see-also"></a>另请参阅


[打开 Lync Server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)  


[使用 Windows PowerShell cmdlet 配置持久聊天服务器](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

