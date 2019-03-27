---
title: 为 Skype for Business Server 2015 中的持久聊天服务器配置高可用性和灾难恢复
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5fb5b189-56c1-49cf-92c8-e4fd6e2fdd5c
description: 摘要： 阅读本主题可了解如何为业务服务器 2015年对于 Persistent Chat Server in Skype 配置高可用性和灾难恢复。
ms.openlocfilehash: 7bc1ae0b71df3916c36acfdc7fabce91caa297e8
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899276"
---
# <a name="configure-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a>为 Skype for Business Server 2015 中的持久聊天服务器配置高可用性和灾难恢复
 
**摘要：** 阅读本主题可了解如何为业务服务器 2015年对于 Persistent Chat Server in Skype 配置高可用性和灾难恢复。
  
Skype 业务服务器支持的后端服务器，包括数据库镜像高可用性的多个的模式。 有关详细信息，请参阅[Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。
  
> [!NOTE]
> 与持久聊天服务器不支持 AlwaysOn 可用性组。 

> [!NOTE] 
> 持久聊天中的业务服务器 2015 Skype 可用但业务服务器 2019年不再支持在 Skype。 中团队提供了相同的功能。 有关详细信息，请参阅[从企业对 Microsoft 团队的 Skype 旅程](/microsoftteams/journey-skypeforbusiness-teams)。 如果您需要使用持久聊天，您的选择是也迁移要求给团队，此功能的用户或继续对业务服务器 2015年使用 Skype。
  
配置持久聊天的高可用性和灾难恢复部署之前，请确保您熟悉中[规划高可用性和灾难恢复 for Persistent Chat Server 中的业务服务器 2015 Skype](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md)的概念。 这些主题中所述的持久聊天服务器的灾难恢复解决方案是基于拉伸的持久聊天服务器池。 规划内容介绍资源需求，以及启用持久聊天服务器，包括使用 SQL Server 镜像的高可用性和 SQL Server 日志传送的高可用性和灾难恢复的扩展的池拓扑灾难恢复。
  
## <a name="use-topology-builder-to-configure-high-availability-and-disaster-recovery"></a>使用拓扑生成器配置高可用性和灾难恢复

在拓扑生成器中，执行以下步骤以为持久聊天服务器配置高可用性和灾难恢复。
  
1. 添加镜像数据库和日志传送辅助数据库 SQL Server 存储。
    
2. 编辑持久聊天服务器服务属性实现：
    
    a. 为主数据库启用镜像。
    
    b. 添加主镜像 SQL Server 存储。
    
    c. 启用 SQL Server 日志传送数据库。
    
    d. 添加 SQL Server 日志传送辅助 SQL Server 存储。
    
    e。 添加辅助数据库的 SQL Server 存储镜像。
    
    f。 发布拓扑。
    
## <a name="set-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database"></a>为持久聊天服务器主数据库设置 SQL Server 日志传送

使用 SQL Server Management Studio，连接到持久聊天服务器辅助日志传送数据库实例，并确保 SQL Server 代理正在运行。 然后连接到的持久聊天主数据库实例并执行以下步骤：
  
1. 右键单击 mgc 数据库，然后单击“**属性**”。
    
2. 在“**选择页**”下，单击“**事务日志传送**”。
    
3. 选中“**将此数据库启用为日志传送配置中的主数据库**”复选框。
    
4. 在“**事务日志备份**”下，单击“**备份设置**”。
    
5. 在“**备份文件夹的网络路径**”框中，键入您为事务日志备份文件夹创建的共享的网络路径。
    
6. 如果备份文件夹位于主服务器上，请在“**如果备份文件夹位于主服务器上，则键入该文件夹的本地路径(示例: c:\backup)**”框中键入该备份文件夹的本地路径。（如果备份文件夹不在主服务器上，则可将此框留空。）
    
    > [!IMPORTANT]
    > 如果本地系统帐户下运行您的主服务器上的 SQL Server 服务帐户，您必须在主服务器上创建备份文件夹，并指定该文件夹的本地路径。 
  
7. 配置“**删除文件，如果其保留时间超过**”和“**在以下时间内没有执行备份时报警**”参数。
    
8. 查看“**备份作业**”下的“**计划**”框中所列的备份计划。 若要自定义安装的计划，单击**计划**，并调整所需的 SQL Server 代理计划。
    
9. 在“**压缩**”下，选择“**使用默认服务器设置**”，然后单击“**确定**”。
    
10. 在“**辅助服务器实例和数据库**”下，单击“**添加**”。
    
11. 单击**连接**并连接到 SQL Server 的已配置为辅助服务器实例。
    
12. 在“**辅助数据库**”框中，从列表中选择“**mgc**”数据库。
    
13. 在**初始化辅助数据库**选项卡中，选择选项**是，生成主数据库的完整备份和还原到辅助数据库 （以及创建辅助数据库不存在时）**。
    
14. **复制文件**选项卡中，在**复制的文件的目标文件夹**框中，键入应该将事务日志备份复制到其中的文件夹的路径。 此文件夹通常位于辅助服务器。
    
15. 复制计划**复制作业**下的**日程表**框中列出的注释。 若要自定义安装的计划，单击**计划**，并调整所需的 SQL Server 代理计划。 此计划应该大约是相同的备份的计划。
    
16. 在**还原**选项卡上，在**数据库状态还原备份时**，下选择**无恢复模式**选项。
    
17. 在**延迟还原备份至少：**，选择**0 分钟**。
    
18. 选择下**警报内没有执行还原时**报警阈值。
    
19. 查看下**还原作业**的**日程表**框中列出的还原计划。 若要自定义安装的计划，单击**计划**、 调整 SQL Server 代理计划，根据需要单击**确定**。 此计划应该大约是相同的备份的计划。
    
20. 在**数据库属性**对话框中，单击**确定**以开始配置过程。
    
## <a name="set-up-sql-server-log-shipping-between-the-primary-mirror-and-the-secondary-database"></a>设置 SQL Server 日志传送主镜像和辅助数据库之间

执行以下步骤以便日志传送能够继续如果主持久聊天数据库故障转移到其镜像数据库。
  
1. 手动故障转移到镜像主持久聊天数据库。 这是通过使用 Skype 业务 Server 命令行管理程序和**Invoke-csdatabasefailover** cmdlet。
    
2. 使用 SQL Server Management Studio，连接到主 Persistent Chat Server 镜像实例。
    
3. 确保 SQL Server 代理正在运行。
    
4. 右键单击 mgc 数据库，然后单击“**属性**”。
    
5. 在“**选择页**”下，单击“**事务日志传送**”。
    
6. 选中“**将此数据库启用为日志传送配置中的主数据库**”复选框。
    
7. 在“**事务日志备份**”下，单击“**备份设置**”。
    
8. 在**备份文件夹的网络路径**框中，键入您为事务日志备份文件夹创建的共享的网络路径。
    
9. 如果备份文件夹位于主服务器上，请在**如果备份文件夹所在的主服务器上，键入文件夹的本地路径**框中键入指向备份文件夹的本地路径。 （如果备份文件夹不是主服务器上，您可以将此框保留为空。）
    
    > [!IMPORTANT]
    > 如果本地系统帐户下运行您的主服务器上的 SQL Server 服务帐户，您必须在主服务器上创建备份文件夹，并指定该文件夹的本地路径。 
  
10. 配置“**删除文件，如果其保留时间超过**”和“**在以下时间内没有执行备份时报警**”参数。
    
11. 查看“**备份作业**”下的“**计划**”框中所列的备份计划。 若要自定义安装的计划，请单击**计划**，并调整 SQL Server 代理计划，根据需要。
    
    > [!IMPORTANT]
    > 使用相同的设置用于主数据库。 
  
12. 在**压缩**下选择**使用默认服务器设置**并单击**确定**。
    
13. 在“**辅助服务器实例和数据库**”下，单击“**添加**”。
    
14. 单击**连接**，并连接到 SQL Server 的已配置为辅助服务器实例。
    
15. 在“**辅助数据库**”框中，从列表中选择“**mgc**”数据库。
    
16. 在**初始化辅助数据库**选项卡中，选择**否，辅助数据库已初始化**的选项。
    
17. 在**将文件复制**选项卡上的在**复制的文件的目标文件夹**中，键入到事务日志备份文件夹的路径应复制，单击**确定**。 此文件夹通常位于辅助服务器。
    
18. 打开**脚本配置**下拉列表，并选择**配置脚本保存到新的查询窗口**。
    
19. 在新的查询窗口中，在**数据库属性**，单击**确定**开始配置过程。
    
20. 选择并运行第一个查询的一半 （参见第 18 步） 安装到行:- \* \* \* \* \* \* End: Script to be run at Primary: \* \* \* \* \* \*。
    
    > [!IMPORTANT]
    > 手动运行此脚本是必需的因为 SQL Server Management Studio 中不支持 SQL Server 日志传送配置中的多个主数据库。 
  
21. 选择**取消**以关闭日志文件传送配置面板并建立正确地实现 （出现时故障转移） 主和镜像数据库的日志文件传送工作安装程序。
    
22. 手动故障回复到主主持久聊天数据库。 这是通过使用 Skype 业务 Server Management Shell，并使用**Invoke-csdatabasefailover** cmdlet。
    

