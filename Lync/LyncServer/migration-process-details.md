---
title: 迁移过程 - 详细信息
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migration process - details
ms:assetid: ca7e352c-9bde-47d9-8273-5cf2fdfdfe7e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205264(v=OCS.15)
ms:contentKeyID: 48185412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 39560d69842c104c7db956418dabac9aa6d29d7c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845192"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-process---details"></a>迁移过程 - 详细信息

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-19_

使用以下先决条件和详细步骤将 Lync Server 2010、群组聊天或 Office 通信服务器 2007 R2 组聊天迁移到 Lync Server 2013、持久聊天服务器。

<div>

## <a name="prerequisites-for-migration"></a>迁移的先决条件

在将 Lync Server 2010、群组聊天或 Office 通信服务器 2007 R2 组聊天迁移到 Lync Server 2013、持久聊天服务器之前, 请确保您已满足以下先决条件。

1.  至少部署一个 Lync Server 2013 池。 如果你有多个 Lync Server 2013 池, 请确定哪个 Lync Server 2013 池将成为新 Lync Server 2013 持久聊天服务器池的主池。

2.  安装 Lync Server 2013 持久聊天服务器池。 它将为空 (无类别、会议室或外接程序)。 在迁移旧版类别、会议室或外接程序之前, 可以在 Lync Server 2013 的持久聊天服务器部署中创建会议室、类别或加载项。
    
    <div>
    

    > [!IMPORTANT]  
    > 请注意, 这些新创建的项目可能会与你迁移的旧版项目发生冲突。 避免任何命名冲突;否则, 在迁移旧数据时, 它们将被覆盖。

    
    </div>

</div>

<div>

## <a name="preparing-the-source-data-for-migration"></a>为迁移准备源数据

执行以下步骤来正确准备要迁移的源数据。

1.  备份 Lync Server 2010、群组聊天或 Office 通信服务器 2007 R2 群组聊天的源数据库。 有关备份 SQL Server 的详细信息, 请参阅 "备份概述 (SQL Server)" <http://go.microsoft.com/fwlink/p/?linkid=254851>。
    
    <div>
    

    > [!IMPORTANT]  
    > Active Directory 域服务应该是相同的。 作为迁移的一个条件, 你无法迁移到其他部署 (尤其是在其他 Active Directory 林) 中的池。

    
    </div>

2.  检查 Lync Server 2010、群组聊天或 Office 通信服务器 2007 R2 组聊天聊天室和类别配置。 在现有旧版部署中对类别、会议室或外接程序所做的任何更改都将由群组聊天管理员工具完成。
    
    <div>
    

    > [!TIP]  
    > Lync server 2013 中的类别、会议室或加载项的任何更改都是由 Lync Server 控制面板或 Windows PowerShell cmdlet 执行的, 持久聊天服务器部署。

    
    </div>
    
    请按照以下步骤准备旧版系统进行迁移。
    
    1.  持久性聊天服务器支持单个级别的类别, 不同类别的深度分层集。 迁移后, 子类别将以完整的父类别名称作为前缀。 你可能希望简化和平展你的现有类别结构, 以便生成的结构满足你的要求。
    
    2.  验证根类别的**经理**。 如果此级别上存在任何经理, 则将在迁移后将这些用户添加为**所有会议室的管理员**。 如果这不是您的组织的要求, 您需要从根类别中删除这些经理。
    
    3.  验证房间名称的长度。 迁移后, 由于 "简化类别" 结构, 如果子类别中存在会议室, 则它们的前缀为完整的父类别名称。 命名限制为256个字符, 包括父类别名称。 必须验证房间名称的长度, 如果这些名称太长, 可能会缩短长度。
    
    4.  在 Lync Server 2013 中, 如果 "类别**邀请**设置" 设置为 "true", 则可以选择 "真" 或 "假", 以在该类别下对聊天室的邀请进行选择。 但是, 如果 "类别邀请" 设置设置为 "false", 则该类别下的会议室将会关闭邀请。 在迁移之前, 如果您希望在特定类别下存在会议室, 您必须在旧式 Lync 服务器组聊天服务器版本中重置邀请设置。 否则, 在迁移期间, Lync Server 2013 将显示警告, 并将聊天室设置为默认值 false。
    
    5.  如果你在聊天室中使用了文件, 则必须在迁移后手动将文件保存到新的持久聊天文件存储。 这些工具不会执行此操作。
    
    6.  如果您有联盟用户和带联盟用户的聊天室, 请注意持久聊天服务器不支持联盟。 将迁移带联盟用户的聊天室;但是, 用户本身将无法访问内容, 因为不支持联盟访问。
    
    7.  标识不想迁移的聊天室, 并将其标记为 "已禁用"。
    
    8.  标识要迁移聊天室内容的截止日期。 例如, 你可能不希望迁移早于2010年1月1日的消息, 因为这些消息可能已过时或与迁移无关。

</div>

<div>

## <a name="performing-the-migration"></a>执行迁移

执行以下步骤迁移旧式群组聊天服务器。

1.  关闭 Lync Server 2010、群组聊天、Office 通信服务器 2007 R2 群组聊天或 Lync Server 2013、持久聊天服务器服务。 必须停止所有服务, 因此计划在有足够的停机时间时执行此操作。 如前面所述, 请确保备份当前的群组聊天数据库。

2.  以永久聊天管理员 RBAC 角色 (CsPersistentChatAdministrator) 的成员身份运行 Windows PowerShell **Export CsPersistentChatData** cmdlet。 有关导出/导入 cmdlet 的详细信息, 请参阅[在 Lync server 2013 中使用 Windows PowerShell cmdlet 对持久聊天服务器配置进行故障排除](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md)。
    
    检查导出的内容。

3.  准备导入之前, 请关闭 Lync Server 2013、持久聊天服务器服务。 需要停止所有服务, 因此计划在有足够的停机时间时执行此操作。

4.  如果在迁移之前在 Lync Server 2013 部署中创建了任何类别、会议室或加载项, 请执行持久聊天数据库的备份。 导出/导入过程能够将旧数据合并到 Lync Server 2013 部署中, 但你需要备份数据库以防意外覆盖内容 (例如, 如果命名冲突仍然存在)。

5.  运行 Windows PowerShell **Import-CsPersistentChatData** cmdlet (导入工具), 使用**WhatIf**命令, 使用迁移的数据填充持久聊天服务器池的后端服务器。 过程中会发生某些转换, 以适应简化的管理模型。 修复出现的任何错误或警告。

6.  以持久聊天管理员 RBAC 角色 (CsPersistentChatAdministrator) 的成员身份运行持久聊天服务器 Windows PowerShell **CsPersistentChatData** cmdlet。 有关导出/导入 cmdlet 的详细信息, 请参阅[在 Lync server 2013 中使用 Windows PowerShell cmdlet 对持久聊天服务器配置进行故障排除](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md)。

7.  必须将所有上载的文件 (整个文件夹) XCOPY 为新的 Lync Server 2013、持久聊天文件存储。
    
    <div>
    

    > [!IMPORTANT]  
    > Lync 2013 (客户端) 不支持上载或查看聊天室中的文件。 您仍然可以使用旧客户端来发布和查看聊天室中的文件。

    
    </div>

8.  将 Lync Server 2010、群组聊天或 Office 通信服务器 2007 R2 群组聊天查找服务器 URI 移植到 Lync Server 2013、持久聊天服务器联系人对象。 如果您的 Lync 2010 群组聊天或 Office Communicator 2007 R2 组聊天客户端需要连接到最新的 Lync 2013、持久聊天 (客户端), 而无需任何客户端配置更改, 则需要执行以下步骤:
    
      - 删除 ocschat @\<DomainName\>查找服务器用户帐户。 这用于指向 Lync Server 2010 中的查找服务, 群组聊天。 你可以在以后卸载该池并删除受信任的条目。
    
      - 通过运行具有相同 SIP URI 的 Windows PowerShell cmdlet **CsPersistentChatEndpoint**创建旧版终结点 (持久聊天服务器联系人对象), 以便在重新启动服务时, 旧客户端将有效工作。
    
    强制执行的迁移过程已完成。 Lync 2010 群组聊天 (客户端) 或 Office Communicator 2007 R2 组聊天 (客户) 现在可以透明地连接到新的持久聊天服务器池。
    
    对于 Lync Server 2010、群组聊天或 Office 通信服务器 2007 R2 群组聊天, 请按照以下附加解除授权步骤操作。

9.  通过打开新的持久聊天服务器池中的所有计算机启动持久聊天服务器服务。

10. 使用 Lync Server "控制面板" 和 "Windows PowerShell" cmdlet 验证数据是否已成功迁移。

11. 从群组聊天服务器池中的计算机卸载 Lync 2010 组聊天或 Office Communicator 2007 R2 组聊天。

12. 使用 Windows PowerShell cmdlet 删除受信任的应用程序和受信任的应用程序池。 这将从 Active Directory 中的中央管理存储和关联的受信任服务条目 (TSEs) 中删除这些项目。 或者, 此步骤通过使用拓扑生成器 (受信任的应用程序/池也有一个专用节点) 工作。

13. 现在, 您可以通过新客户端开始启用持久聊天服务器功能。 有关启用持久聊天服务器的详细信息, 请参阅[在 Lync server 2013 中部署持久聊天服务器](lync-server-2013-deploying-persistent-chat-server.md)。
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server 2013 支持多个持久聊天服务器池。 但是, 我们支持将 Lync 2010 组聊天或 Office 通信服务器 2007 R2&nbsp;组聊天池迁移到单个 Lync server 2013、持久聊天服务器池。 你可以在你的部署中添加其他新持久聊天服务器池以满足管理法规需求 (例如, 在给定地理区域内保留数据)。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

