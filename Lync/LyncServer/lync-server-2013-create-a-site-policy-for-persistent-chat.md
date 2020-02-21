---
title: Lync Server 2013：为持久聊天创建站点策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a site policy for Persistent Chat
ms:assetid: 1327ff5c-b859-4010-a240-e0b2b084b5bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204693(v=OCS.15)
ms:contentKeyID: 48183470
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e910b9266259f8a37a3e1f1576c084c3ac7e1e6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195905"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-site-policy-for-persistent-chat-in-lync-server-2013"></a>在 Lync Server 2013 中为持久聊天创建站点策略

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-06_

对于已部署的每个网站，可以创建特定于站点的持久聊天策略。

站点策略中的配置将覆盖全局策略，但是仅限于站点策略所涉及的特定站点。

<div>


> [!NOTE]  
> 若要配置和使用持久聊天服务器，必须首先使用拓扑生成器将持久聊天服务器支持添加到拓扑，然后发布拓扑。 有关详细信息，请参阅部署文档中的在<A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Lync server 2013 中将持久聊天服务器添加到部署</A>。<BR>若要配置持久聊天服务器配置设置，请参阅部署文档中的 "<A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">全局或在 Lync server 2013 中为持久聊天服务器池配置持久聊天服务器选项</A>"。



</div>

<div>

## <a name="to-create-a-persistent-chat-policy-for-a-site"></a>为网站创建持久聊天策略

1.  使用分配给 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  从 "**开始**" 菜单中，选择 "Lync Server 控制面板" 或打开一个浏览器窗口，然后输入管理 URL。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“持久聊天”****，然后单击“持久聊天策略”****。
    
    <div>
    

    > [!IMPORTANT]  
    > 您还可以使用 Windows PowerShell cmdlet。 有关详细信息，请参阅部署文档中的<A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">使用 Windows PowerShell Cmdlet 配置持久聊天服务器</A>。

    
    </div>

4.  单击“新建”****，然后单击“站点策略”****。

5.  在“选择站点”**** 中，单击要应用此策略的站点。

6.  在“新建持久聊天策略”**** 中，执行下列操作之一：
    
      - 在“名称”**** 中，指定新站点策略的名称（例如，Redmond）。
    
      - 在“说明”**** 中，提供有关该站点策略内容的详细信息（例如，Redmond 的聊天室策略）。
    
      - 若要控制未通过站点策略明确控制的所有站点的持久聊天，请选中或清除“启用持久聊天”**** 复选框。

7.  单击“提交”****。

</div>

</div>

<span> </span>

</div>

</div>

</div>

