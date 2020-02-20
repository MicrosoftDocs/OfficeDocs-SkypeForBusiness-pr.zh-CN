---
title: Lync Server 2013：对持久聊天服务器进行故障回复
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing back Persistent Chat Server
ms:assetid: 67b91de4-6ddc-43e6-9812-5e1aa84a7980
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204970(v=OCS.15)
ms:contentKeyID: 48184396
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6847f4002204c270b5978df2cab2851eeb912b20
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151322"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="failing-back-persistent-chat-server-in-lync-server-2013"></a>在 Lync Server 2013 中对持久聊天服务器进行故障回复

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-02-05_

此过程概述了从持久聊天服务器故障中恢复所需的步骤，以及从主数据中心重新建立操作所需的步骤。

在持久聊天服务器出现故障的过程中，主数据中心受到完全中断，主数据库和镜像数据库将变得不可用。 主数据中心将故障转移到备份服务器。

以下过程在备份主数据中心并重新生成服务器后还原正常操作。 此过程假定主数据中心已从总中断恢复，并且已使用拓扑生成器重新生成并重新安装 mgc 数据库和 mgccomp 数据库。

此过程还假定在故障转移期间没有部署新的镜像服务器和备份服务器，并且部署的唯一服务器是备份服务器及其镜像服务器，如在[Lync server 2013 中通过持久聊天服务器进行故障转移](lync-server-2013-failing-over-persistent-chat-server.md)时进行了定义。

这些步骤旨在恢复配置在导致从主服务器故障转移到备份服务器的灾难发生之前的状态。

<div>

## <a name="to-fail-back-persistent-chat-server"></a>对持久聊天服务器进行故障回复

1.  使用 Lync Server 命令行管理程序中的`Set-CsPersistentChatActiveServer` Cmdlet 从持久聊天服务器活动服务器列表中清除所有服务器。 这将阻止所有持久聊天服务器在故障回复期间连接到 mgc 数据库和 mgccomp 数据库。
    
    <div>
    

    > [!IMPORTANT]  
    > 辅助持久聊天服务器后端服务器上的 SQL Server 代理应在特权帐户下运行。 尤其需要指出的是，该帐户必须具有以下权限： 
    > <UL>
    > <LI>
    > <P>对于放置备份的网络共享的读取权限。</P>
    > <LI>
    > <P>对于备份将复制到的特定本地目录的写入权限。</P></LI></UL>

    
    </div>

2.  在备份 mgc 数据库上禁用镜像：
    
    1.  使用 SQL Server Management Studio 连接到备份 mgc 实例。
    
    2.  右键单击 mgc 数据库，指向“任务”****，然后单击“镜像”****。
    
    3.  单击“取消镜像”****。
    
    4.  单击“确定”****。
    
    5.  对 mgccomp 数据库执行相同步骤。

3.  备份 mgc 数据库，使其可以还原为新主数据库：
    
    1.  使用 SQL Server Management Studio 连接到备份 mgc 实例。
    
    2.  右键单击 mgc 数据库，指向“任务”****，然后单击“备份”****。随即将显示“备份数据库”**** 对话框。
    
    3.  在“备份类型”**** 中，选择“完全”****。
    
    4.  对于“备份组件”****，请单击“数据库”****。
    
    5.  接受“名称”**** 中建议的默认备份集名称，或为备份集输入不同名称。
    
    6.  * \<可选\> *在 "**说明**" 中，输入备份集的说明。
    
    7.  从目标列表中删除默认备份位置。
    
    8.  使用您建立用于日志传送的共享位置的路径向列表中添加文件。主数据库和备份数据库均可使用此路径。
    
    9.  单击“确定”**** 关闭对话框并开始备份过程。

4.  使用上一步中创建的备份数据库还原主数据库。
    
    1.  使用 SQL Server Management Studio 连接到主 mgc 实例。
    
    2.  右键单击 mgc 数据库，指向“任务”****，指向“还原”****，然后单击“数据库”****。随即会显示“还原数据库”**** 对话框。
    
    3.  选择“自设备”****。
    
    4.  单击浏览按钮，将打开“指定备份”**** 对话框。在“备份媒体”**** 中，选择“文件”****。单击“添加”****，选择您在步骤 3 中创建的备份文件，然后单击“确定”****。
    
    5.  在“选择用于还原的备份集”**** 中，选择备份。
    
    6.  在“选择页”**** 窗格中单击“选项”****。
    
    7.  在“还原选项”**** 中，选择“覆盖现有数据库”****。
    
    8.  在“恢复状态”**** 中，选择“使数据库处于可以使用的状态”****。
    
    9.  单击“确定”**** 开始还原过程。

5.  为主数据库配置 SQL Server 日志传送。 按照在[Lync server 2013 中配置持久聊天服务器以实现高可用性和灾难恢复](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)过程中的过程，为主 mgc 数据库建立日志传送。

6.  设置持久聊天服务器活动服务器。 在 Lync Server 命令行管理程序中，使用**set-cspersistentchatactiveserver** cmdlet 设置活动服务器的列表。
    
    <div>
    

    > [!IMPORTANT]  
    > 所有活动服务器都必须与新主数据库位于同一数据中心中，或位于与数据库之间存在低延迟/高带宽连接的数据中心中。

    
    </div>

将池还原到正常状态将运行以下 Windows PowerShell 命令：

    Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal

有关详细信息，请参阅[CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/Set-CsPersistentChatState) cmdlet 的帮助主题。

</div>

</div>

<span> </span>

</div>

</div>

</div>

