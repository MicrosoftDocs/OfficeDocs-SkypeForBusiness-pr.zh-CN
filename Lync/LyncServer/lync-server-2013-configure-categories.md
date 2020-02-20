---
title: Lync Server 2013：配置类别
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure categories
ms:assetid: 4547f514-f0c0-404d-890f-092ddeeac852
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204859(v=OCS.15)
ms:contentKeyID: 48184033
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b808fff7a6356e437490a3f80a6f4f30b9a66801
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146485"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-categories-in-lync-server-2013"></a>在 Lync Server 2013 中配置类别

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-06_

在 Lync Server 2013 控制面板中，可以使用 "**持久聊天**" 页的 "**类别**" 部分配置类别。 Persistent 聊天室类别是用于组织聊天室的逻辑结构。 类别定义一组默认的访问控制列表 (ACL)，以便控制可以创建或加入聊天室的用户和用户组。 您还可以使用类别强制在组织中不同部门之间使用信息隔离墙。

聊天室类别可以包含聊天室，但不包含其他类别。 每个类别使用名称 和描述 等元数据描述其内容。 此外，类别还具有可以设置以控制其所拥有聊天室的行为的属性，例如聊天室是否允许执行邀请或文件上载操作，或者包含聊天历史记录。

<div>

## <a name="to-configure-categories-for-chat-rooms"></a>配置聊天室的类别

1.  使用分配给 CsPersistentChatAdministrator 或 CsAdministrator 角色的用户帐户登录到您的本地部署中的任一计算机。

2.  从 "**开始**" 菜单中，选择 "Lync Server 控制面板" 或打开一个浏览器窗口，然后输入管理 URL。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。
    
    <div>
    

    > [!IMPORTANT]  
    > 您还可以使用 Windows PowerShell cmdlet。 有关详细信息，请参阅部署文档中的<A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">使用 Windows PowerShell Cmdlet 配置持久聊天服务器</A>。

    
    </div>

3.  在左侧导航栏中，单击“持久聊天”****，然后单击“类别”****。
    
    对于多个持久聊天服务器池部署，请从下拉列表中选择相应的池。

4.  在“类别”**** 页上，单击“新建”**** 或“编辑”****。

5.  在 "**选择服务**" 中，选择与需要在其上创建类别的持久聊天服务器池对应的服务。 该服务是持久聊天服务器池，持久聊天（客户端）使用它来确定该类别属于哪个池。 一个类别只能属于一个持久聊天服务器池，不能移动到另一个池，也不能与另一个池共享。

6.  在“新建类别”**** 中，执行下列操作：
    
    1.  在“名称”**** 中，指定新聊天室类别的名称。
    
    2.  在“描述”**** 中，提供有关聊天室类别（例如 Contoso 聊天室类别）的详细描述。
    
    3.  若要控制是否能为属于此类别的聊天室启用邀请，请选中或清除“启用邀请”**** 复选框。 如果选中，此类别中的聊天室将可以打开或关闭邀请；如果清除，则不允许该类别中的聊天室执行邀请操作。 如果会议室有邀请，则在将新成员添加到聊天室时，他或她会在其持久聊天客户端中获取新聊天室的通知。
    
    4.  若要控制属于此类别的聊天室中的文件上载，请选中或清除“启用文件上载”**** 复选框。如果选中，该类别的聊天室可以启用或禁用文件上载；如果清除，则不允许该类别的聊天室执行文件上载操作。
        
        <div>
        

        > [!IMPORTANT]  
        > 在服务器上强制实施此设置，因为自定义应用程序或以前使用 Office 通信服务器 2007 R2&nbsp;组聊天服务器或 Lync server 2010 的组聊天客户端可以将文件发布到聊天室。 Lync 2013 客户端不具有文件上传/下载功能，因此，如果您拥有纯 Lync 2013 部署或 Lync 2013 客户端，则无法在持久聊天服务器聊天室中发布文件。

        
        </div>
    
    5.  若要控制聊天历史记录，请选中或清除 "**启用聊天历史记录**" 复选框。 如果选中，聊天室聊天内容将是持久的；否则，聊天消息将不是持久的。 如果启用了合规性，将合规保存聊天室聊天内容，但用户无法访问较早的消息。 此选项可用于为不需要持久保持聊天历史记录的实时、临时协作指派的聊天室。

7.  在“编辑类别”**** 中，执行下列操作：
    
      - 在 "**成员身份**" 中，在 "**允许的成员**" 部分，添加或删除用户和其他 Active Directory 域服务主体（用户、通讯组、组织单位等），这些域允许添加为属于该类别的聊天室的成员。 类别允许的主体可以搜索该类别中的聊天室（除非聊天室处于隐藏状态，在这种情况下只有聊天室的成员才能在目录中搜索它）。
    
      - 在 "**成员身份**" 的 "**拒绝的成员**" 部分，添加或删除与要从聊天室拒绝的成员关联的用户和其他 Active Directory 主体。
    
      - 在 "**成员资格**" 中，在 "**创建者**" 部分，添加或删除与该类别的创建者关联的用户和其他 Active Directory 主体。 创建者是有权创建聊天室并指定聊天室管理员和成员的用户。

8.  单击“提交”****。

</div>

</div>

<span> </span>

</div>

</div>

</div>

