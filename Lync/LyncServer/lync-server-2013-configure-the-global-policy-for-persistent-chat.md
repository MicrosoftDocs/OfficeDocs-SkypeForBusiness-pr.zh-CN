---
title: Lync Server 2013：配置持久聊天的全局策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure the global policy for Persistent Chat
ms:assetid: 6176eb5c-19de-4c07-bcc0-2e38f8965966
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204951(v=OCS.15)
ms:contentKeyID: 48184323
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 236023756f8d2c917812d38f5a03da8dd4c40b5b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837315"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-global-policy-for-persistent-chat-in-lync-server-2013"></a>在 Lync Server 2013 中配置持久聊天的全局策略

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-06_

你可以单独使用默认全局策略来为你的部署中的所有用户启用持久聊天设置。 你还可以为网站和用户指定其他策略, 以控制特定用户和网站是否启用或禁用持久聊天。

您不能删除全局策略。 如果您尝试删除它, 则配置将重置为默认值。

<div>


> [!NOTE]  
> 若要配置和使用持久聊天服务器, 必须首先使用拓扑生成器向拓扑添加持久聊天服务器支持, 然后发布拓扑。 有关详细信息, 请参阅在部署文档中<A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">将持久聊天服务器添加到 Lync Server 2013</A>中的部署。<BR>若要配置持久聊天服务器配置设置, 请参阅在部署文档中<A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">为 Lync server 2013 中的永久聊天服务器池配置持久聊天服务器选项</A>。



</div>

<div>

## <a name="to-configure-the-global-policy-for-persistent-chat"></a>配置永久聊天的全局策略

1.  从分配给 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  从 "**开始**" 菜单中, 选择 "Lync Server 控制面板" 或打开一个浏览器窗口, 然后输入管理员 URL。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息, 请参阅在操作文档中[打开 Lync Server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。
    
    <div>
    

    > [!IMPORTANT]  
    > 你还可以使用 Windows PowerShell cmdlet。 有关详细信息, 请参阅<A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">使用 Windows PowerShell cmdlet 在部署文档中配置持久聊天服务器</A>。

    
    </div>

3.  在 Lync Server "控制面板" 中, 单击 "**持久聊天**", 然后单击 "**持久聊天策略**"。

4.  单击策略列表中的“**全局**”，再单击“**编辑**”，然后单击“**显示详细信息**”。

5.  在“**编辑持久聊天策略 - 全局**”中，执行下列操作：
    
      - 在“**名称**”中，如果不想使用全局策略的默认名称 Global，可以为其指定新名称。
    
      - 在 "**说明**" 中, 提供有关用户策略的详细信息 (例如, CentralSiteName 的全局策略)。
    
      - 若要为未通过网站策略或用户策略明确控制的所有网站和用户控制持久聊天, 请选中或清除 "**启用持久聊天**" 复选框。

6.  单击“**提交**”。

</div>

</div>

<span> </span>

</div>

</div>

</div>

