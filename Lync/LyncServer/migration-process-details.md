---
title: 迁移过程-详细信息
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migration process - details
ms:assetid: ca7e352c-9bde-47d9-8273-5cf2fdfdfe7e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205264(v=OCS.15)
ms:contentKeyID: 48185412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c15c5cf8a2eaa207467f53d57d82e6cf4491e13
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527199"
---
# <a name="migration-process---details"></a>迁移过程-详细信息

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-19_

使用以下先决条件和详细步骤将 Lync Server 2010、组聊天或 Office 通信服务器 2007 R2 组聊天迁移到 Lync Server 2013、持久聊天服务器。

<div>

## <a name="prerequisites-for-migration"></a>迁移的先决条件

在将 Lync Server 2010、组聊天或 Office 通信服务器 2007 R2 组聊天迁移到 Lync Server 2013、持久聊天服务器之前，请确保您已满足以下先决条件。

1.  至少部署一个 Lync Server 2013 池。 如果您有多个 Lync Server 2013 池，请确定哪个 Lync Server 2013 池将成为新 Lync Server 2013 持久聊天服务器池的主池。

2.  安装 Lync Server 2013、持久聊天服务器池。 它将为空（没有类别、聊天室或外接程序）。 在迁移旧版类别、聊天室或外接程序之前，您可以在 Lync Server 2013 的持久聊天服务器部署中创建聊天室、类别或外接程序。
    
    <div>
    

    > [!IMPORTANT]  
    > 注意这些新创建的项可能与您迁移的旧项冲突。应避免任何命名冲突；否则，在迁移旧数据时将覆盖新创建的项。

    
    </div>

</div>

<div>

## <a name="preparing-the-source-data-for-migration"></a>准备要迁移的源数据

执行以下步骤适当准备要迁移的源数据。

1.  备份任何 Lync Server 2010、组聊天或 Office 通信服务器 2007 R2 组聊天的源数据库。 有关备份 SQL Server 的详细信息，请参阅上的 "备份概述 (SQL Server) " <https://go.microsoft.com/fwlink/p/?linkid=254851> 。
    
    <div>
    

    > [!IMPORTANT]  
    > Active Directory 域服务应相同。 作为迁移的一个条件，您无法迁移到不同部署 (中的池（具体来说，在不同的 Active Directory 林中) 。

    
    </div>

2.  检查你的 Lync Server 2010、组聊天或 Office 通信服务器 2007 R2 组聊天聊天室和类别配置。 对现有旧部署中的类别、聊天室或外接程序所做的任何更改都将通过 "组聊天管理工具" 完成。
    
    <div>
    

    > [!TIP]  
    > Lync server 2013 中对类别、会议室或外接程序进行的任何更改都是由 Lync Server 控制面板或 Windows PowerShell cmdlet 执行的。

    
    </div>
    
    按照以下步骤准备要迁移的旧系统。
    
    1.  持久聊天服务器支持单个级别的类别，不同类别的深度分层集。 迁移后，子类别将带有完整父类别名称的前缀。 您最好简化并平整现有类别结构，以便生成的结构满足您的要求。
    
    2.  验证根类别是否存在**管理员**。如果此级别存在管理员，则这些用户在迁移后将被添加为**所有聊天室的管理员**。如果这不是组织的要求，则需要从根类别中删除这些管理员。
    
    3.  验证聊天室名称的长度。迁移后，由于类别结构简化，如果某个子类别下存在聊天室，这些聊天室将带有完整父类别名称的前缀。命名限制为 256 个字符，其中包括父类别名称。您必须验证聊天室名称的长度，并可在名称过长时缩短其长度。
    
    4.  在 Lync Server 2013 中，如果将 "类别 **邀请** 设置" 设置为 "true"，则可以选择 "真" 或 "假" 来邀请到该类别下的会议室。 但是如果类别邀请设置为 false，则该类别下的聊天室将关闭邀请。 在迁移之前，如果想要 (s) 在特定类别中存在，则必须重置旧版 Lync Server 组聊天服务器版本中的邀请设置。 否则，在迁移过程中，Lync Server 2013 将显示警告，并将聊天室设置为默认值 false。
    
    5.  如果在聊天室中使用了文件，则必须在迁移后将文件手动以 XCOPY 的的的新持久聊天文件存储。 工具不会执行此操作。
    
    6.  如果你有联合用户和带联合用户的聊天室，请注意持久聊天服务器不支持联合。 带联盟用户的聊天室将被迁移，但用户自己无法访问内容，因为联盟访问不受支持。
    
    7.  标识不想迁移的聊天室，并将它们标记为禁用。
    
    8.  标识您不想迁移的聊天室内容的截至日期。例如，您可能不想迁移 2010 年 1 月 1 日以前的消息，因为这些消息可能已作废或与迁移不相关。

</div>

<div>

## <a name="performing-the-migration"></a>执行迁移

执行以下步骤以迁移旧版组聊天服务器。

1.  关闭 Lync Server 2010、组聊天、Office 通信服务器 2007 R2 组聊天或 Lync Server 2013、持久聊天服务器服务。 必须停止所有服务，以便有足够的停机时间一次完成此操作。 如上文所述，请务必备份当前的组聊天数据库。

2.  以持久聊天管理员 RBAC 角色的成员身份运行 Windows PowerShell **export-cspersistentchatdata** Cmdlet (CsPersistentChatAdministrator) 。 有关导出/导入 cmdlet 的详细信息，请参阅 [在 Lync server 2013 中使用 Windows PowerShell cmdlet 对持久聊天服务器配置进行故障排除](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md)。
    
    检查导出的内容。

3.  准备好导入之前，请关闭 Lync Server 2013、持久聊天服务器服务。 需要停止所有服务，以便有足够的停机时间一次完成此操作。

4.  如果您在迁移之前在 Lync Server 2013 部署中创建了任何类别、聊天室或外接程序，请执行持久聊天数据库的备份。 导出/导入过程将能够将旧数据合并到 Lync Server 2013 部署中，但您需要备份数据库，以防无意中覆盖了内容 (例如，如果仍存在命名冲突) 。

5.  运行 Windows PowerShell **export-cspersistentchatdata** cmdlet (导入工具) ，使用 **WhatIf** 命令将持久聊天服务器池的后端服务器填充到迁移的数据。 过程中会进行一些转换以适应简化的管理模型。 修复出现的任何错误或警告。

6.  将持久聊天服务器 Windows PowerShell **export-cspersistentchatdata** Cmdlet 作为持久聊天管理员 RBAC 角色的成员运行， (CsPersistentChatAdministrator) 。 有关导出/导入 cmdlet 的详细信息，请参阅 [在 Lync server 2013 中使用 Windows PowerShell cmdlet 对持久聊天服务器配置进行故障排除](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md)。

7.  您必须将所有已上载的文件 (整个文件夹中) 到新的 Lync Server 2013、持久聊天文件存储。
    
    <div>
    

    > [!IMPORTANT]  
    > Lync 2013 (客户端) 不支持在聊天室中上载或查看文件。 您仍可以使用旧客户端在聊天室中发布和查看文件。

    
    </div>

8.  将 Lync Server 2010、Group Chat 或 Office 通信服务器 2007 R2 组聊天查找服务器 URI 移植到 Lync Server 2013、持久聊天服务器联系人对象。 如果你的 Lync 2010 组聊天或 Office Communicator 2007 R2 组聊天客户端需要连接到最新 Lync 2013、持久聊天 (客户端) 在不进行任何客户端配置更改的情况下进行迁移，则需要执行以下步骤：
    
      - 删除 ocschat@ 的 " \<domainName\> Com 查找" 服务器用户帐户。 这用于指向 Lync Server 2010 中的 "组聊天" 中的查找服务。 可以在以后卸载池并删除受信任条目。
    
      - 通过运行 Windows PowerShell cmdlet **CsPersistentChatEndpoint**持久聊天服务器 contact 对象) ，使用相同的 SIP URI 创建旧终结 (点，以便在重新启动该服务时，旧客户端将有效工作。
    
    必需的迁移过程此时完成。 Lync 2010 Group Chat (客户端) 或 Office Communicator 2007 R2 组聊天 (客户端) 现在可以透明地连接到新的持久聊天服务器池。
    
    按照 Lync Server 2010、组聊天或 Office 通信服务器 2007 R2 组聊天的这些额外的解除授权步骤进行操作。

9.  通过打开新持久聊天服务器池中的所有计算机来启动持久聊天服务器服务。

10. 使用 Lync Server 控制面板和 Windows PowerShell cmdlet 验证数据是否已成功迁移。

11. 从组聊天服务器池中的计算机卸载 Lync 2010 组聊天或 Office Communicator 2007 R2 组聊天。

12. 使用 Windows PowerShell cmdlet 删除受信任的应用程序和受信任的应用程序池。 此命令将从中央管理存储和关联的受信任的服务条目中删除这些项目， (TSEs) 从 Active Directory 中删除。 或者，此步骤可通过使用拓扑生成器 (受信任的应用程序/池具有一个专用节点，也) 。

13. 你现在可以开始通过新客户端启用持久聊天服务器功能。 有关启用持久聊天服务器的详细信息，请参阅 [在 Lync server 2013 中部署持久聊天服务器](lync-server-2013-deploying-persistent-chat-server.md)。
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server 2013 支持多个持久聊天服务器池。 但是，我们支持将 Lync 2010 组聊天或 Office 通信服务器 2007 R2 &nbsp; 组聊天池迁移到单个 Lync server 2013、持久聊天服务器池。 您可以在部署中添加其他新的持久聊天服务器池以满足法规需求 (例如，将数据保留在给定的地理位置) 中。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

