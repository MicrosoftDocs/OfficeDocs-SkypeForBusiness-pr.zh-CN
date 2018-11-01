---
title: Lync Server 2013：对持久聊天服务器进行故障回复
TOCTitle: 对持久聊天服务器进行故障回复
ms:assetid: 67b91de4-6ddc-43e6-9812-5e1aa84a7980
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204970(v=OCS.15)
ms:contentKeyID: 49313102
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中对持久聊天服务器进行故障回复

 

_**上一次修改主题：** 2014-02-05_

此过程概述了从 持久聊天服务器故障中恢复并从主数据中心重新建立操作需要执行的步骤。

在 持久聊天服务器故障期间，主数据中心完全中断，主数据库和镜像数据库变得不可用。主数据中心将故障转移到备份服务器。

以下过程在备份主数据中心并重新生成服务器后还原正常操作。该过程假定主数据中心已从整体中断中恢复，并已使用 拓扑生成器重新生成并重新安装 mgc 数据库和 mgccomp 数据库。

该过程还假定在故障转移期间未部署新镜像和备份服务器，并且唯一部署的服务器是 [在 Lync Server 2013 中对持久聊天服务器进行故障转移](lync-server-2013-failing-over-persistent-chat-server.md)中定义的备份服务器及其镜像服务器。

这些步骤旨在恢复配置在导致从主服务器故障转移到备份服务器的灾难发生之前的状态。

## 故障回复 持久聊天服务器

1.  使用 Lync Server 命令行管理程序中的 `Set-CsPersistentChatActiveServer` cmdlet 清除 持久聊天服务器活动服务器列表中的所有服务器。这将会阻止所有 持久聊天服务器在故障回复期间连接到 mgc 数据库和 mgccomp 数据库。
    
    > [!IMPORTANT]  
	> 辅助 持久聊天服务器后端服务器上的 SQL Server 代理应以特权帐户运行。尤其需要指出的是，该帐户必须具有以下权限：
    > <ul>
    > <li><p>对于放置备份的网络共享的读取权限。</p></li>
    > <li><p>对于备份将复制到的特定本地目录的写入权限。</p></li>
    > </ul>


2.  在备份 mgc 数据库上禁用镜像：
    
    1.  使用 SQL Server Management Studio 连接到备份 mgc 实例。
    
    2.  右键单击 mgc 数据库，指向“任务”，然后单击“镜像”。
    
    3.  单击“取消镜像”。
    
    4.  单击“确定”。
    
    5.  对 mgccomp 数据库执行相同步骤。

3.  备份 mgc 数据库，使其可以还原为新主数据库：
    
    1.  使用 SQL Server Management Studio 连接到备份 mgc 实例。
    
    2.  右键单击 mgc 数据库，指向“任务”，然后单击“备份”。随即将显示“备份数据库”对话框。
    
    3.  在“备份类型”中，选择“完全”。
    
    4.  对于“备份组件”，请单击“数据库”。
    
    5.  接受“名称”中建议的默认备份集名称，或为备份集输入不同名称。
    
    6.  *\<可选\>* 在“说明”中，输入备份集的说明。
    
    7.  从目标列表中删除默认备份位置。
    
    8.  使用您建立用于日志传送的共享位置的路径向列表中添加文件。主数据库和备份数据库均可使用此路径。
    
    9.  单击“确定”关闭对话框并开始备份过程。

4.  使用上一步中创建的备份数据库还原主数据库。
    
    1.  使用 SQL Server Management Studio 连接到主 mgc 实例。
    
    2.  右键单击 mgc 数据库，指向“任务”，指向“还原”，然后单击“数据库”。随即会显示“还原数据库”对话框。
    
    3.  选择“自设备”。
    
    4.  单击浏览按钮，将打开“指定备份”对话框。在“备份媒体”中，选择“文件”。单击“添加”，选择您在步骤 3 中创建的备份文件，然后单击“确定”。
    
    5.  在“选择用于还原的备份集”中，选择备份。
    
    6.  在“选择页”窗格中单击“选项”。
    
    7.  在“还原选项”中，选择“覆盖现有数据库”。
    
    8.  在“恢复状态”中，选择“使数据库处于可以使用的状态”。
    
    9.  单击“确定”开始还原过程。

5.  为主数据库配置 SQL Server 日志传送。按照 [在 Lync Server 2013 中为持久聊天服务器配置高可用性和灾难恢复](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)中的过程为主 mgc 数据库建立日志传送。

6.  设置 持久聊天服务器活动服务器。从 Lync Server 命令行管理程序中，使用 **Set-CsPersistentChatActiveServer** cmdlet 设置活动服务器的列表。
    
    > [!IMPORTANT]
    > 所有活动服务器必须都与新主数据库位于同一数据中心中，或位于与数据库之间存在低延迟/高带宽连接的数据中心中。


运行以下 Windows PowerShell 命令将池还原到正常状态：

    Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal

有关详细信息，请参阅 [Set-CsPersistentChatState](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsPersistentChatState) cmdlet 的帮助主题。

