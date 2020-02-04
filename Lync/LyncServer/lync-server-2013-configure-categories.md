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
ms.openlocfilehash: bf7b7b3ceb24e3b5bffb307cdde048e7a0cabb8c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757756"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-categories-in-lync-server-2013"></a>在 Lync Server 2013 中配置类别

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-06_

在 Lync Server 2013 控制面板中，你可以使用**持久聊天**页面的 "**类别**" 部分配置类别。 持久的聊天室类别是用于组织聊天室的逻辑结构。 类别定义一组默认的访问控制列表 (ACL)，以便控制可以创建或加入聊天室的用户和用户组。 您还可以使用类别强制在组织中不同部门之间使用信息隔离墙。

聊天室类别可以包含聊天室，但不包含其他类别。 每个类别说明了其内容及元数据，比如名称和说明。 此外，类别还具有可以设置以控制其所拥有聊天室的行为的属性，例如聊天室是否允许执行Invitations或File Uploads操作，或者包含Chat History。

<div>

## <a name="to-configure-categories-for-chat-rooms"></a>配置聊天室的类别

1.  使用分配给 CsPersistentChatAdministrator 或 CsAdministrator 角色的用户帐户登录您的本地部署中的任一计算机。

2.  从 "**开始**" 菜单中，选择 "Lync Server 控制面板" 或打开一个浏览器窗口，然后输入管理员 URL。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。
    
    <div>
    

    > [!IMPORTANT]  
    > 你还可以使用 Windows PowerShell cmdlet。 有关详细信息，请参阅在部署文档中<A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">使用 Windows PowerShell Cmdlet 配置持久聊天服务器</A>。

    
    </div>

3.  在左侧导航栏中，单击“**持久聊天**”，然后单击“**类别**”。
    
    对于多个持久聊天服务器池部署，从下拉列表中选择相应的池。

4.  在“**类别**”页上，单击“**新建**”或“**编辑**”。

5.  在 "**选择服务**" 中，选择与需要在其中创建类别的持久聊天服务器池对应的服务。 该服务是持久聊天服务器池，永久聊天（客户端）使用它标识类别所属的池。 一个类别只能属于一个持久聊天服务器池，不能移到另一个，或与另一个池共享。

6.  在“**新建类别**”中，执行下列操作：
    
    1.  在“**名称**”中，指定新聊天室类别的名称。
    
    2.  在“**描述**”中，提供有关聊天室类别（例如 Contoso 聊天室类别）的详细描述。
    
    3.  要控制是否为属于此类别的聊天室启用邀请，请选中或清除“**启用邀请**”复选框。 如果选中，则此类别的聊天室将打开或关闭邀请；如果清除，则不允许此类别的聊天室具有邀请。 如果会议室有邀请，则在将新成员添加到聊天室时，他或她将收到新聊天室在其持久聊天客户端中的通知。
    
    4.  要控制属于此类别的聊天室中的文件上载，请选中或清除“**启用文件上载**”复选框。如果选中，该类别的聊天室可以启用或禁用文件上载；如果清除，则不允许该类别的聊天室执行文件上载操作。
        
        <div>
        

        > [!IMPORTANT]  
        > 由于自定义应用程序或以前的群组聊天客户端使用 Office 通信服务器 2007 R2&nbsp;组聊天服务器或 Lync server 2010，组聊天可将文件发布到聊天室，因此在服务器上强制使用此设置。 Lync 2013 客户端没有文件上传/下载功能，因此，如果你有纯 Lync 2013 部署或 Lync 2013 客户端，则无法在持久聊天服务器聊天室中发布文件。

        
        </div>
    
    5.  若要控制聊天历史记录，请选中或清除 "**启用聊天历史记录**" 复选框。 如果选中，则聊天室聊天内容将变成持久的；否则，将不会保留聊天消息。 如果启用了合规性，则将按合规性保存聊天室聊天内容，但用户无法访问较早的消息。 此选项可用于指定为无需保留聊天历史记录的实时、临时协作的聊天室。

7.  在“**编辑类别**”中，执行下列操作：
    
      - 在 "允许的成员" 部分**中，在**"**允许的成员**" 部分中，添加或删除允许添加为属于该类别的聊天室成员的用户和其他 Active Directory 域服务主体（用户、通讯组、组织单位等）。 类别允许的主体可搜索此类别的聊天室（除非隐藏了聊天室，在这种情况下，仅聊天室的成员可在此目录中搜索聊天室）。
    
      - 在 "**拒绝成员**" 部分**中，在**"拒绝的成员" 部分中，添加或删除与从聊天室拒绝的成员关联的用户和其他 Active Directory 主体。
    
      - 在 "**成员资格**" 部分中，在 "**创建者**" 部分中，添加或删除与类别的 "创建者" 关联的用户和其他 Active Directory 主体。 创建者是有权创建聊天室并指定聊天室管理员和成员的用户。

8.  单击“**提交**”。

</div>

</div>

<span> </span>

</div>

</div>

</div>

