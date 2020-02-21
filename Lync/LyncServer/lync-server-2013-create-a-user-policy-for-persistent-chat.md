---
title: Lync Server 2013：为持久聊天创建用户策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a user policy for Persistent Chat
ms:assetid: aa3774af-d442-4206-8a68-2fbb9102e9d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205170(v=OCS.15)
ms:contentKeyID: 48185103
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 40e992bbbd5d2559619e2ebe5a0d67c83102e546
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195875"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-user-policy-for-persistent-chat-in-lync-server-2013"></a>在 Lync Server 2013 中为持久聊天创建用户策略

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-06_

在 Lync Server 控制面板中，可以定义可分配给**用户**中用户的用户策略。

用户策略将覆盖全局策略和站点策略，但仅适用于分配了该用户策略的特定用户。

<div>


> [!NOTE]  
> 若要配置和使用持久聊天服务器，必须首先使用拓扑生成器将持久聊天服务器支持添加到拓扑，然后发布拓扑。 有关详细信息，请参阅部署文档中的在<A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Lync server 2013 中将持久聊天服务器添加到部署</A>。<BR>若要配置持久聊天服务器配置设置，请参阅部署文档中的 "<A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">全局或在 Lync server 2013 中为持久聊天服务器池配置持久聊天服务器选项</A>"。



</div>

<div>

## <a name="to-create-a-user-policy-for-persistent-chat"></a>为持久聊天创建用户策略

1.  使用分配给 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  从 "**开始**" 菜单中，选择 "Lync Server 控制面板" 或打开一个浏览器窗口，然后输入管理 URL。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。
    
    <div>
    

    > [!IMPORTANT]  
    > 您还可以使用 Windows PowerShell cmdlet。 请参阅部署文档中的<A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">使用 Windows PowerShell Cmdlet 配置持久聊天服务器</A>。

    
    </div>

3.  在左侧导航栏中，单击“持久聊天”****，然后单击“持久聊天策略”****。

4.  单击“新建”****，然后单击“用户策略”****。

5.  在“新建持久聊天策略”**** 中，执行下列操作之一：
    
      - 在“名称”**** 中，指定新用户策略的名称。
    
      - 在 "**说明**" 中，提供有关用户策略的详细信息（例如，针对特定用户的持久聊天策略）的详细信息。
    
      - 若要控制未通过用户策略明确控制的所有用户的持久聊天，请选中或清除 "**启用持久聊天**" 复选框。

6.  单击“提交”****。

</div>

</div>

<span> </span>

</div>

</div>

</div>

