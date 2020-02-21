---
title: Lync Server 2013：配置持久聊天的全局策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the global policy for Persistent Chat
ms:assetid: 6176eb5c-19de-4c07-bcc0-2e38f8965966
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204951(v=OCS.15)
ms:contentKeyID: 48184323
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9c4596749e1c4bf4c9f4002b33234c83afa1fd5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199705"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-the-global-policy-for-persistent-chat-in-lync-server-2013"></a>在 Lync Server 2013 中配置持久聊天的全局策略

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-06_

您可以使用默认全局策略来为部署中的所有用户启用持久聊天设置。 您还可以为网站和用户指定其他策略，以控制是否为特定用户和网站启用或禁用持久聊天。

无法删除全局策略。 如果试图删除全局策略，配置将重置为默认值。

<div>


> [!NOTE]  
> 若要配置和使用持久聊天服务器，必须首先使用拓扑生成器将持久聊天服务器支持添加到拓扑，然后发布拓扑。 有关详细信息，请参阅部署文档中的在<A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Lync server 2013 中将持久聊天服务器添加到部署</A>。<BR>若要配置持久聊天服务器配置设置，请参阅部署文档中的 "<A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">全局或在 Lync server 2013 中为持久聊天服务器池配置持久聊天服务器选项</A>"。



</div>

<div>

## <a name="to-configure-the-global-policy-for-persistent-chat"></a>配置持久聊天的全局策略

1.  使用分配给 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  从 "**开始**" 菜单中，选择 "Lync Server 控制面板" 或打开一个浏览器窗口，然后输入管理 URL。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅操作文档中的[Open Lync Server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。
    
    <div>
    

    > [!IMPORTANT]  
    > 您还可以使用 Windows PowerShell cmdlet。 有关详细信息，请参阅部署文档中的<A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">使用 Windows PowerShell Cmdlet 配置持久聊天服务器</A>。

    
    </div>

3.  在 "Lync Server 控制面板" 中，单击 "**持久聊天**"，然后单击 "**持久聊天策略**"。

4.  单击策略列表中的“全局”****，再单击“编辑”****，然后单击“显示详细信息”****。

5.  在“编辑持久聊天策略 - 全局”**** 中，执行下列操作：
    
      - 在“名称”**** 中，如果不想使用全局策略的默认名称 Global，可以为其指定新名称。
    
      - 在 "**说明**" 中，提供有关用户策略的详细信息（例如，CentralSiteName 的全局策略）的详细信息。
    
      - 若要控制未通过站点策略或用户策略明确控制的所有站点和用户的持久聊天，请选中或清除 "**启用持久聊天**" 复选框。

6.  单击“提交”****。

</div>

</div>

<span> </span>

</div>

</div>

</div>

