---
title: Lync Server 2013：为持久聊天服务器主数据库设置 SQL Server 日志传送
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up SQL Server Log Shipping for the Persistent Chat Server primary database
ms:assetid: 088ea1c2-d592-4a11-b3b8-f1e2f8beae93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204653(v=OCS.15)
ms:contentKeyID: 48183337
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae44d410ef165cdd4f77b877afcfb9349dd0ec00
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764568"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-sql-server-log-shipping-in-lync-server-2013-for-the-persistent-chat-server-primary-database"></a>在 Lync Server 2013 中为持久聊天服务器主数据库设置 SQL Server 日志传送

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-11-12_

使用 SQL Server Management Studio，连接到持久聊天服务器辅助日志传送数据库实例，并确保 SQL Server 代理正在运行。

使用连接到持久聊天主数据库实例的 SQL Server Management Studio，请执行以下步骤：

1.  请确保 SQL Server 代理正在运行。

2.  右键单击 mgc 数据库，然后单击“**属性**”。

3.  在“**选择页**”下，单击“**事务日志传送**”。

4.  选中“**将此数据库启用为日志传送配置中的主数据库**”复选框。

5.  在“**事务日志备份**”下，单击“**备份设置**”。

6.  在“**备份文件夹的网络路径**”框中，键入您为事务日志备份文件夹创建的共享的网络路径。

7.  如果备份文件夹位于主服务器上，请在 "如果备份文件夹位于主服务器上" 中键入备份文件夹的本地路径 **，请键入文件夹的本地路径（例如： c：\\backup）** 框。 （如果备份文件夹不在主服务器上，你可以将此框留空。）
    
    <div>
    

    > [!IMPORTANT]  
    > 如果主服务器上的 SQL Server 服务帐户在本地系统帐户下运行，则必须在主服务器上创建备份文件夹，并指定该文件夹的本地路径。

    
    </div>

8.  配置“**删除文件，如果其保留时间超过**”和“**在以下时间内没有执行备份时报警**”参数。

9.  查看“**备份作业**”下的“**计划**”框中所列的备份计划。 若要自定义安装的计划，请单击 "**计划**"，然后根据需要调整 SQL Server 代理计划。

10. 在“**压缩**”下，选择“**使用默认服务器设置**”，然后单击“**确定**”。

11. 在“**辅助服务器实例和数据库**”下，单击“**添加**”。

12. 单击 "**连接**" 并连接到已配置为辅助服务器的 SQL Server 实例。

13. 在“**辅助数据库**”框中，从列表中选择“**mgc**”数据库。

14. 在 "**初始化辅助数据库**" 选项卡上，选择 **"是，生成主数据库的完整备份"，然后将其还原到辅助数据库（如果不存在，则创建辅助数据库）**。

15. 在 "**复制文件**" 选项卡上的 "**复制的文件的目标文件夹**" 框中，键入应将事务日志备份复制到其中的文件夹的路径。 此文件夹通常位于辅助服务器上。

16. 请注意 "**复制作业**" 下的 "**日程安排**" 框中列出的复制计划。 若要自定义安装的计划，请单击 "**计划**"，然后根据需要调整 SQL Server 代理计划。 此计划应该与备份计划大致相同。

17. 在 "**还原**" 选项卡上的 "**还原备份时数据库状态**" 下，选择 "**无恢复模式**" 选项。

18. 在 "**延迟还原备份至少：**" 下，选择 " **0 分钟**"。

19. **如果未在内进行还原**，请在 "警报" 下选择警报阈值。

20. 查看 "**还原作业**" 下的 "**日程安排**" 框中列出的还原计划。 若要自定义安装的计划，请单击 "**计划**"，根据需要调整 SQL Server 代理计划，然后单击 **"确定"**。 此计划应该与备份计划大致相同。

21. 在 "**数据库属性**" 对话框中，单击 **"确定"** 开始配置过程。

</div>

<span> </span>

</div>

</div>

</div>

