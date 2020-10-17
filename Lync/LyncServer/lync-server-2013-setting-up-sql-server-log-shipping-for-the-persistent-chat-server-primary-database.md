---
title: Lync Server 2013：为持久聊天服务器主数据库设置 SQL Server 日志传送
description: Lync Server 2013：为持久聊天服务器主数据库设置 SQL Server 日志传送。
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
ms.openlocfilehash: 72b7e68bd0cb7b9f544b86a15204d3e832692ec1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554258"
---
# <a name="setting-up-sql-server-log-shipping-in-lync-server-2013-for-the-persistent-chat-server-primary-database"></a>在 Lync Server 2013 中为持久聊天服务器主数据库设置 SQL Server 日志传送

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-11-12_

使用 SQL Server Management Studio 连接到持久聊天服务器辅助日志传送数据库实例，并确保 SQL Server 代理正在运行。

若要使用连接到持久聊天主数据库实例的 SQL Server Management Studio，请执行以下步骤：

1.  请确保 SQL Server 代理正在运行。

2.  右键单击 mgc 数据库，然后单击“属性”****。

3.  在“选择页”**** 下，单击“事务日志传送”****。

4.  选中“将此数据库启用为日志传送配置中的主数据库”**** 复选框。

5.  在“事务日志备份”**** 下，单击“备份设置”****。

6.  在“备份文件夹的网络路径”**** 框中，键入您为事务日志备份文件夹创建的共享的网络路径。

7.  如果备份文件夹位于主服务器上，则在 "如果备份文件夹位于主服务器上" 中键入备份文件夹的本地路径 **，请键入文件夹的本地路径 (例如： c： \\ backup) ** 框。  (如果备份文件夹不在主服务器上，则可以将此框保留为空。 ) 
    
    <div>
    

    > [!IMPORTANT]  
    > 如果主服务器上的 SQL Server 服务帐户在本地系统帐户下运行，则必须在主服务器上创建备份文件夹，并指定该文件夹的本地路径。

    
    </div>

8.  配置“删除文件，如果其保留时间超过”**** 和“在以下时间内没有执行备份时报警”**** 参数。

9.  查看“备份作业”**** 下的“计划”**** 框中所列的备份计划。 若要自定义安装计划，请单击 " **计划**"，然后根据需要调整 SQL Server 代理计划。

10. 在“压缩”**** 下，选择“使用默认服务器设置”****，然后单击“确定”****。

11. 在“辅助服务器实例和数据库”**** 下，单击“添加”****。

12. 单击 " **连接** "，然后连接到已配置为辅助服务器的 SQL Server 实例。

13. 在“辅助数据库”**** 框中，从列表中选择“mgc”**** 数据库。

14. 在 " **初始化辅助数据库** " 选项卡上，依次选择 " **是"、"生成主数据库的完整备份并将其还原到辅助数据库中" (并创建辅助数据库（如果) 中不存在） **。

15. 在“复制文件”**** 选项卡上的“复制文件的目标文件夹”**** 框中，键入应将事务日志备份复制到的文件夹的路径。此文件夹通常位于辅助服务器上。

16. 注意“复制作业”**** 下的“计划”**** 框中列出的复制计划。 若要自定义安装计划，请单击 " **计划**"，然后根据需要调整 SQL Server 代理计划。 此计划应与备份计划大致相同。

17. 在“还原”**** 选项卡上的“还原备份时的数据库状态”**** 下，选择“无恢复模式”**** 选项。

18. 在“延迟还原备份操作至少:”**** 下，选择“0 分钟”****。

19. 在“在以下时间内没有执行还原时报警”**** 下选择报警阈值。

20. 查看“还原作业”**** 下的“计划”**** 框中列出的还原计划。 若要自定义安装计划，请单击 " **计划**"，根据需要调整 SQL Server 代理计划，然后单击 **"确定"**。 此计划应与备份计划大致相同。

21. 在“数据库属性”**** 对话框中，单击“确定”**** 开始配置过程。

</div>

<span> </span>

</div>

</div>

</div>

