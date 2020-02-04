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
ms.openlocfilehash: 4feb77aa99e1fe3018a469e61e9688a87cf81760
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726382"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-site-policy-for-persistent-chat-in-lync-server-2013"></a>在 Lync Server 2013 中为持久聊天创建站点策略

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-06_

对于已部署的每个网站，你可以创建特定于站点的持久聊天策略。

站点策略中的配置将覆盖全局策略，但是仅限于站点策略所涉及的特定站点。

<div>


> [!NOTE]  
> 若要配置和使用持久聊天服务器，必须首先使用拓扑生成器向拓扑添加持久聊天服务器支持，然后发布拓扑。 有关详细信息，请参阅在部署文档中<A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">将持久聊天服务器添加到 Lync Server 2013</A>中的部署。<BR>若要配置持久聊天服务器配置设置，请参阅在部署文档中<A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">为 Lync server 2013 中的永久聊天服务器池配置持久聊天服务器选项</A>。



</div>

<div>

## <a name="to-create-a-persistent-chat-policy-for-a-site"></a>为网站创建持久聊天策略

1.  从分配给 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  从 "**开始**" 菜单中，选择 "Lync Server 控制面板" 或打开一个浏览器窗口，然后输入管理员 URL。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“**持久聊天**”，然后单击“**持久聊天策略**”。
    
    <div>
    

    > [!IMPORTANT]  
    > 你还可以使用 Windows PowerShell cmdlet。 有关详细信息，请参阅在部署文档中<A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">使用 Windows PowerShell Cmdlet 配置持久聊天服务器</A>。

    
    </div>

4.  单击“**新建**”，然后单击“**站点策略**”。

5.  在“**选择站点**”中，单击要应用此策略的站点。

6.  在“**新建持久聊天策略**”中，执行下列操作之一：
    
      - 在“**名称**”中，指定新站点策略的名称（例如，Redmond）。
    
      - 在“**说明**”中，提供有关该站点策略内容的详细信息（例如，Redmond 的聊天室策略）。
    
      - 若要控制未通过站点策略明确控制的所有站点的持久聊天，请选中或清除“**启用持久聊天**”复选框。

7.  单击“**提交**”。

</div>

</div>

<span> </span>

</div>

</div>

</div>

