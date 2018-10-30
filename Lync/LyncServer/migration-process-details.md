---
title: 迁移过程 - 详细信息
TOCTitle: 迁移过程 - 详细信息
ms:assetid: ca7e352c-9bde-47d9-8273-5cf2fdfdfe7e
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205264(v=OCS.15)
ms:contentKeyID: 49314258
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 迁移过程 - 详细信息

 

_**上一次修改主题：** 2016-12-08_

使用以下先决条件和详细步骤将 Lync Server 2010 群聊或 Office Communications Server 2007 R2  群聊迁移到 Lync Server 2013持久聊天服务器。

## 迁移的先决条件

将 Lync Server 2010 群聊或 Office Communications Server 2007 R2  群聊迁移到 Lync Server 2013  持久聊天服务器之前，确保已满足以下先决条件。

1.  部署至少一个 Lync Server 2013 池。如果有多个 Lync Server 2013 池，请决定哪个 Lync Server 2013 池将成为新 Lync Server 2013  持久聊天服务器池的主池。

2.  安装 Lync Server 2013持久聊天服务器池。它将为空（没有类别、聊天室或外接程序）。在迁移旧的类别、聊天室或外接程序前，可以在 Lync Server 2013持久聊天服务器部署中创建聊天室、类别或外接程序。
    
    > [!IMPORTANT]
    > 注意这些新创建的项可能与您迁移的旧项冲突。应避免任何命名冲突；否则，在迁移旧数据时将覆盖新创建的项。


## 准备要迁移的源数据

执行以下步骤适当准备要迁移的源数据。

1.  备份Lync Server 2010 群聊或 Office Communications Server 2007 R2  群聊的源数据库。有关备份 SQL Server 的详细信息，请参阅“备份概述 (SQL Server)”，网址为 <http://go.microsoft.com/fwlink/p/?linkid=254851>。
    
    > [!IMPORTANT]
    > Active Directory 域服务 应该相同。一个迁移条件是不能迁移到不同部署中的池（具体来说，不同 Active Directory 林中的池）。


2.  检查 Lync Server 2010 群聊或 Office Communications Server 2007 R2  群聊聊天室和类别配置。对现有旧部署中的类别、聊天室或外接程序的任何更改都将通过 群聊管理工具完成。
    
    > [!TIP]
    > 对 Lync Server 2013持久聊天服务器部署中的类别、聊天室或外接程序的任何更改都通过 Lync Server 控制面板或 Windows PowerShell cmdlet 执行。
    
    按照以下步骤准备要迁移的旧系统。
    
    1.  持久聊天服务器支持单级类别，这与深层级的类别集合不同。迁移后，子类别将带有完整父类别名称的前缀。您最好简化并平整现有类别结构，以便生成的结构满足您的要求。
    
    2.  验证根类别是否存在 **管理员**。如果此级别存在管理员，则这些用户在迁移后将被添加为 **所有聊天室的管理员**。如果这不是组织的要求，则需要从根类别中删除这些管理员。
    
    3.  验证聊天室名称的长度。迁移后，由于类别结构简化，如果某个子类别下存在聊天室，这些聊天室将带有完整父类别名称的前缀。命名限制为 256 个字符，其中包括父类别名称。您必须验证聊天室名称的长度，并可在名称过长时缩短其长度。
    
    4.  在 Lync Server 2013 中，如果类别“邀请”设置为 true，则可以为该类别下聊天室的邀请选择 true 或 false。但是如果类别邀请设置为 false，则该类别下的聊天室将关闭邀请。在迁移前，如果希望聊天室存在于特定类别下，必须重置旧 Lync Server  群聊服务器版本中的邀请设置。否则，在迁移期间， Lync Server 2013 会显示警告，并将聊天室设置为默认值 false。
    
    5.  如果在聊天室中使用了文件，必须在迁移后手动将这些文件 XCOPY 到新的 持久聊天文件存储中。工具不会执行此操作。
    
    6.  如果有联盟用户和带联盟用户的聊天室，请注意 持久聊天服务器不支持联盟。带联盟用户的聊天室将被迁移，但用户自己无法访问内容，因为联盟访问不受支持。
    
    7.  标识不想迁移的聊天室，并将它们标记为禁用。
    
    8.  标识您不想迁移的聊天室内容的截至日期。例如，您可能不想迁移 2010 年 1 月 1 日以前的消息，因为这些消息可能已作废或与迁移不相关。

## 执行迁移

执行以下步骤来迁移旧 群聊服务器。

1.  关闭 Lync Server 2010 群聊、 Office Communications Server 2007 R2  群聊或 Lync Server 2013持久聊天服务器服务。必须停止所有服务，以便有足够的停机时间一次完成此操作。如前文所述，确保备份当前的 群聊数据库。

2.  以 持久聊天管理员 RBAC 角色 (CsPersistentChatAdministrator) 成员的身份运行 Windows PowerShell**Export-CsPersistentChatData** cmdlet。有关导出/导入 cmdlet 的详细信息，请参阅 [在 Lync Server 2013 中使用 Windows PowerShell Cmdlet 排查持久聊天服务器配置故障](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md)。
    
    检查导出的内容。

3.  在准备导入前，关闭 Lync Server 2013持久聊天服务器服务。需要停止所有服务，以便有足够的停机时间一次完成此操作。

4.  如果在迁移前在 Lync Server 2013 部署中创建了任何类别、聊天室或外接程序，请执行 持久聊天数据库的备份。导出/导入过程能将旧数据合并到 Lync Server 2013 部署中，但您会希望备份数据库，以防内容被不小心覆盖（例如，如果仍存在命名冲突）。

5.  运行 Windows PowerShell**Import-CsPersistentChatData** cmdlet（导入工具），使用 **WhatIf** 命令用迁移的数据填充 持久聊天服务器池的 后端服务器。过程中会进行一些转换以适应简化的管理模型。修复出现的任何错误或警告。

6.  以 持久聊天管理员 RBAC 角色 (CsPersistentChatAdministrator) 成员的身份运行 持久聊天服务器Windows PowerShell**Import-CsPersistentChatData** cmdlet。有关导出/导入 cmdlet 的详细信息，请参阅 [在 Lync Server 2013 中使用 Windows PowerShell Cmdlet 排查持久聊天服务器配置故障](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md)。

7.  必须将所有上传的文件（整个文件夹）XCOPY 到新的 Lync Server 2013持久聊天文件存储中。
    
    > [!IMPORTANT]
    > Lync 2013（客户端）不支持在聊天室中上传或查看文件。您仍可以使用旧客户端在聊天室中发布和查看文件。


8.  将 Lync Server 2010 群聊或 Office Communications Server 2007 R2  群聊查找服务器 URI 移植到 Lync Server 2013持久聊天服务器 联系人对象。如果在迁移后需要在不更改任何客户端配置的情况下将 Lync 2010 群聊或 Office Communicator 2007 R2  群聊客户端连接到最新的 Lync 2013持久聊天（客户端），则需要执行以下步骤：
    
      - 删除 ocschat@*\<domainName\>*.com 查找服务器用户帐户。其用于指向 Lync Server 2010 群聊中的查找服务。可以在以后卸载池并删除受信任条目。
    
      - 以相同的 SIP URI 运行 Windows PowerShell cmdlet **New-CsPersistentChatEndpoint** 创建旧终结点（ 持久聊天服务器联系人对象），以便服务重新启动后旧客户端有效工作。
    
    必需的迁移过程此时完成。Lync 2010 群聊（客户端）或 Office Communicator 2007 R2群聊（客户端）现在可以透明连接到新的 持久聊天服务器池。
    
    对 Lync Server 2010 群聊或 Office Communications Server 2007 R2群聊执行以下附加停用步骤。

9.  打开新 持久聊天服务器池中的所有计算机来启动 持久聊天服务器服务。

10. 使用 Lync Server 控制面板和 Windows PowerShell cmdlet 验证该数据是否已成功迁移。

11. 从 群聊服务器池的计算机中卸载 Lync 2010 群聊或 Office Communicator 2007 R2群聊。

12. 使用 Windows PowerShell cmdlet 删除受信任的应用程序和受信任的应用程序池。这将从 中央管理存储中删除这些项目并从 Active Directory 中删除相关的受信任服务条目 (TSE)。也可以使用 拓扑生成器（受信任应用程序/池也有专用节点）执行此步骤。

13. 您现在可以开始通过新客户端启用 持久聊天服务器功能。有关启用 持久聊天服务器的详细信息，请参阅 [在 Lync Server 2013 中部署持久聊天服务器](lync-server-2013-deploying-persistent-chat-server.md)。
    
    > [!IMPORTANT]
    > Lync Server 2013 支持多个 持久聊天服务器池。但是，我们支持将一个 Lync 2010 群聊或 Office Communications Server 2007 R2  群聊池迁移到单个 Lync Server 2013持久聊天服务器池。您可以在部署中添加其他新 持久聊天服务器池以满足法规需求（例如，将数据保存在给定的地域内）。

