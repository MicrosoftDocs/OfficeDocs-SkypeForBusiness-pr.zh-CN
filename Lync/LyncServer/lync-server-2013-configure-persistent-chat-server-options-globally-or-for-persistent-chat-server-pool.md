---
title: Lync Server 2013：全局或永久聊天服务器池配置持久聊天服务器选项
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Persistent Chat Server options globally or for Persistent Chat Server pool
ms:assetid: 1e8d5245-cd58-4aad-9a1c-35b24189bc40
ms:mtpsurl: https://technet.microsoft.com/library/JJ204731(v=OCS.15)
ms:contentKeyID: 48183581
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a9cadd23099dbcaee5c577705ca1c2e4bdf6c00
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520459"
---
# <a name="configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool-in-lync-server-2013"></a>在 Lync Server 2013 中全局或为持久聊天服务器池配置持久聊天服务器选项

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-06_

在 "Lync Server 2013 控制面板" 中，可以使用 **"持久聊天" 页的**"持久**聊天配置**" 部分在应用于所有持久聊天服务器池或特定持久聊天服务器池的持续性聊天设置的全局位置对其进行配置。

<div>


> [!NOTE]  
> 若要配置和使用持久聊天服务器，必须首先使用拓扑生成器将持久聊天服务器支持添加到拓扑，然后发布拓扑。 有关详细信息，请参阅部署文档中的在 <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Lync server 2013 中将持久聊天服务器添加到部署</A> 。



</div>

<div>

## <a name="to-configure-persistent-chat-options-globally"></a>全局配置持久聊天选项

1.  使用分配给 CsPersistentChatAdministrator 或 CsAdministrator 角色的用户帐户登录到您的本地部署中的任一计算机。

2.  从 " **开始** " 菜单中，选择 "Lync Server 控制面板" 或打开一个浏览器窗口，然后输入管理 URL。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。
    
    <div>
    

    > [!IMPORTANT]  
    > 您还可以使用 Windows PowerShell cmdlet。 有关详细信息，请参阅部署文档中的 <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">使用 Windows PowerShell Cmdlet 配置持久聊天服务器</A> 。

    
    </div>

3.  在左侧导航栏中，单击“持久聊天”****，然后单击“持久聊天配置”****。

4.  在 " **持久聊天配置** " 页上，单击 " **新建"，** 然后单击 " **站点配置**"。
    
    <div>
    

    > [!IMPORTANT]  
    > 如果要将配置应用于部署在站点中的所有持久聊天服务器池，请选择此选项。 如果要将配置应用于特定的持久聊天服务器池，请单击 " <STRONG>池配置</STRONG> "。

    
    </div>

5.  在 " **选择站点**" 中，选择要为持久聊天服务器站点配置配置的站点。

6.  在“新建持久聊天配置”**** 中，执行下列操作：
    
      - 在“名称”**** 中，指定新配置设置的名称。默认状态下，已存在站点名称。
    
      - 在“默认聊天历史记录”**** 中，定义首次请求时每个聊天室要处理的聊天消息的数目。默认情况下，此数目为 30。这是全局默认值，管理员可根据每个类别禁用聊天历史记录。
        
        <div>
        

        > [!IMPORTANT]  
        > 持久聊天服务器将在内存中缓存这些邮件，因此如果增加此数字，将缓存更多的邮件。 您始终可通过搜索来访问历史记录内容。 默认消息数仅确定您在连接到聊天室时首次看到的最大消息数。

        
        </div>
    
      - 在“最大文件大小(KB)”**** 中，选择每条聊天历史记录的最大文件大小。默认情况下，此数目为 20 MB (20,000 KB)。这是可上载到系统（通过系统对应的“类别”**** 设置为系统启用文件上载）中任何聊天室的文件的最大大小。
        
        <div>
        

        > [!IMPORTANT]  
        > 在服务器上强制实施此设置，因为自定义应用程序或以前的 Group Chat 客户端使用 Office 通信服务器 2007 R2 &nbsp; 组聊天服务器或 Lync server 2010，组聊天可以将文件发布到聊天室。 Lync 2013 客户端不具有文件上传/下载功能，因此，如果您拥有纯 Lync 2013 部署或 Lync 2013 客户端，则无法在持久聊天服务器聊天室中发布文件。

        
        </div>
    
      - 在“参与者更新限制”**** 中，选择参与者更新的限制。 持久聊天服务器将名单信息 (连接到聊天室) 到所有参与者，直到连接的用户数达到此号码。 默认情况下，此数目为 75。 此限制指示在给定会议室中的参与者的最大数量，超过该数量后，持续聊天服务器将停止向连接的客户端发送有关会议室中存在的人员名单更新。
    
      - （可选）在“聊天室管理 URL”**** 中，选择聊天室管理 URL。这是基于 Web 的自定义聊天室管理的 URL。如果您不需要自定义聊天室管理，并且只使用默认设置，则将此选项留空。该 URL 设置后，它将被用作内部和外部聊天室管理 URL。
        
        如果要自定义会议室创建体验并包含特定的业务工作流，则可以使用持久聊天服务器软件开发工具包 (SDK) 构建自定义聊天室管理解决方案，将其承载到某处，并将 URL 放在此处。 此 URL 将被发送给客户端，以便用户尝试查看/创建聊天室时将被指引到您的自定义聊天室管理解决方案。

7.  单击“提交”****。

</div>

<div>

## <a name="to-configure-persistent-chat-options-for-a-specific-persistent-chat-server-pool"></a>为特定的持久聊天服务器池配置持久聊天选项

1.  使用分配给 CsPersistentChatAdministrator 或 CsAdministrator 角色的用户帐户登录到您的本地部署中的任一计算机。

2.  从 " **开始** " 菜单中选择 "Lync Server 控制面板"，或打开一个浏览器窗口，然后输入管理 URL。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。
    
    <div>
    

    > [!IMPORTANT]  
    > 您还可以使用 Windows PowerShell cmdlet。 有关详细信息，请参阅部署文档中的 <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">使用 Windows PowerShell Cmdlet 配置持久聊天服务器</A> 。

    
    </div>

3.  在左侧导航栏中，单击“持久聊天”****，然后单击“持久聊天配置”****。

4.  在“持久聊天配置”**** 页上，单击“新建”****，然后单击“池配置”****。

5.  在 " **选择服务**" 中，选择与要配置的持久聊天服务器池相关联的服务。

6.  在“新建持久聊天配置”**** 中，执行下列操作：
    
      - 在“名称”**** 中，指定新配置设置的名称。默认情况下，已存在站点池名称。
    
      - 在“默认聊天历史记录”**** 中，定义首次请求时每个聊天室要处理的聊天消息的数目。默认情况下，此数目为 30。这是全局默认值，管理员可根据每个类别禁用聊天历史记录。
        
        <div>
        

        > [!IMPORTANT]  
        > 持久聊天服务器将在内存中缓存这些邮件，因此如果增加此数字，将缓存更多的邮件。 您始终可通过搜索来访问历史记录内容。 默认消息数仅确定您在连接到聊天室时首次看到的最大消息数。

        
        </div>
    
      - 在“最大文件大小(KB)”**** 中，选择每条聊天历史记录的最大文件大小。默认情况下，此数目为 20 MB (20,000 KB)。这是可上载到系统（通过系统对应的“类别”**** 设置为系统启用文件上载）中任何聊天室的文件的最大大小。
        
        <div>
        

        > [!IMPORTANT]  
        > 由于自定义应用程序或以前的组聊天客户端 (Office 通信服务器 2007 R2 &nbsp; 组聊天服务器或 Lync server 2010，组聊天) 可以将文件发布到聊天室，因此在服务器上强制实施此设置。 Lync 2013 客户端不具有文件上传/下载功能，因此，如果您拥有纯 Lync 2013 部署或 Lync 2013 客户端，则无法在持久聊天服务器聊天室中发布文件。

        
        </div>
    
      - 在“参与者更新限制”**** 中，选择参与者更新的限制。 持久聊天服务器将名单信息 (连接到聊天室) 到所有参与者，直到连接的用户数达到此号码。 默认情况下，此数目为 75。 此限制指示在给定会议室中的参与者的最大数量，超过该数量后，持续聊天服务器将停止向连接的客户端发送有关会议室中存在的人员名单更新。
    
      - 在“聊天室管理 URL”**** 中，选择聊天室管理 URL。这是基于 Web 的聊天室管理部署的 URL。如果不需要自定义聊天室管理并且只想使用默认设置，请将此选项留空。
        
        如果要自定义会议室创建体验并包含特定的业务工作流，则可以使用持久聊天服务器软件开发工具包 (SDK) 构建自定义聊天室管理解决方案，将其承载到某处，并将 URL 放在此处。 此 URL 将被发送给客户端，以便用户在尝试查看/创建聊天室时将被定向到您的自定义聊天室管理解决方案。

7.  单击“提交”****。

</div>

</div>

<span> </span>

</div>

</div>

</div>

