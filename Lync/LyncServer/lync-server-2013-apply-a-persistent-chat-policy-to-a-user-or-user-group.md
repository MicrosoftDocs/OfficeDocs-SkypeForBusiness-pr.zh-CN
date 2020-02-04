---
title: Lync Server 2013：将持久聊天策略应用于用户或用户组
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Apply a Persistent Chat policy to a user or user group
ms:assetid: 809ef4e0-8d42-4feb-b7c0-3995f39867a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205038(v=OCS.15)
ms:contentKeyID: 48184652
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 726fe9a5fa20a52f770cd5bab475de5731562989
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737622"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="apply-a-persistent-chat-policy-to-a-user-or-user-group-in-lync-server-2013"></a>在 Lync Server 2013 中将持久聊天策略应用于用户或用户组

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-06_

如果已启用 Lync Server 2013 的用户，则可以将适当的策略应用于特定用户，以便为永久聊天服务器启用或禁用它们。

<div>


> [!NOTE]  
> 若要配置和使用持久聊天服务器，必须首先使用拓扑生成器向拓扑添加持久聊天服务器支持，然后发布拓扑。 有关详细信息，请参阅在部署文档中<A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">将持久聊天服务器添加到 Lync Server 2013</A>中的部署。<BR>若要配置持久聊天服务器配置设置，请参阅在部署文档中<A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">为 Lync server 2013 中的永久聊天服务器池配置持久聊天服务器选项</A>。



</div>

使用本主题中的过程将以前创建的持久聊天用户策略应用于一个或多个用户帐户或用户组。

<div>

## <a name="to-apply-a-persistent-chat-user-policy-to-a-user-account"></a>将持久聊天用户策略应用于用户帐户

1.  从分配给 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  从 "**开始**" 菜单中，选择 "Lync Server 控制面板" 或打开一个浏览器窗口，然后输入管理员 URL。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“**用户**”，然后搜索要配置的用户帐户。

4.  在列出搜索结果的表中，单击相应的用户帐户，再单击“**编辑**”，然后单击“**显示详细信息**”。

5.  在 "**永久聊天策略**" 下的 "**编辑 Lync Server 用户**" 中，选择要应用的持久聊天用户策略。
    
    <div>
    

    > [!NOTE]  
    > " <STRONG> &lt;自动&gt; </STRONG>设置" 应用默认有效策略。 服务器将自动应用这些设置。

    
    </div>

6.  单击“**提交**”。

</div>

</div>

<span> </span>

</div>

</div>

</div>

