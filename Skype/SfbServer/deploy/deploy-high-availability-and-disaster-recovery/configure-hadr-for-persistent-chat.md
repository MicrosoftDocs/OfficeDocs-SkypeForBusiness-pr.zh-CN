---
title: 为 Skype for Business Server 2015 中的持久聊天服务器配置高可用性和灾难恢复
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5fb5b189-56c1-49cf-92c8-e4fd6e2fdd5c
description: '摘要: 阅读本主题, 了解如何在 Skype for business Server 2015 中配置持久聊天服务器的高可用性和灾难恢复。'
ms.openlocfilehash: cfc2843ceb3afba4813cc729856dcd35a4a6439e
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240113"
---
# <a name="configure-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a>为 Skype for Business Server 2015 中的持久聊天服务器配置高可用性和灾难恢复
 
**摘要:** 阅读本主题, 了解如何在 Skype for business Server 2015 中配置持久聊天服务器的高可用性和灾难恢复。
  
Skype for Business 服务器支持对后端服务器的多个高可用性模式, 包括数据库镜像。 有关详细信息，请参阅[Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。
  
> [!NOTE]
> 永久聊天服务器不支持 AlwaysOn 可用性组。 
  
在为高可用性和灾难恢复配置持久聊天部署之前, 请确保熟悉适用于[Skype for Business server 2015 中持久聊天服务器的高可用性和灾难恢复](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md)的概念。 这些主题中所述的持久聊天服务器的灾难恢复解决方案是基于持续持续的持久聊天服务器池构建的。 规划内容介绍资源要求和延长的池拓扑, 该拓扑支持持久聊天服务器的高可用性和灾难恢复, 包括使用 SQL Server 镜像实现高可用性和 SQL Server 日志传送灾难恢复。
  
## <a name="use-topology-builder-to-configure-high-availability-and-disaster-recovery"></a>使用拓扑生成器配置高可用性和灾难恢复

在拓扑生成器中，执行以下步骤以为持久聊天服务器配置高可用性和灾难恢复。
  
1. 添加镜像数据库和日志传送辅助数据库 SQL Server 存储。
    
2. 将持久聊天服务器服务属性编辑为:
    
    a. 为主数据库启用镜像。
    
    b. 添加主镜像 SQL Server 应用商店。
    
    c. 启用 SQL Server 日志传送数据库。
    
    d. 添加 SQL Server 日志传送辅助 SQL Server 应用商店。
    
    e.i. 为辅助数据库添加 SQL Server 应用商店镜像。
    
    f. 发布拓扑。
    
## <a name="set-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database"></a>为持久聊天服务器主数据库设置 SQL Server 日志传送

使用 SQL Server Management Studio, 连接到持久聊天服务器辅助日志传送数据库实例, 并确保 SQL Server 代理正在运行。 然后, 连接到持久聊天主数据库实例并执行以下步骤:
  
1. 右键单击 mgc 数据库，然后单击“**属性**”。
    
2. 在“**选择页**”下，单击“**事务日志传送**”。
    
3. 选中“**将此数据库启用为日志传送配置中的主数据库**”复选框。
    
4. 在“**事务日志备份**”下，单击“**备份设置**”。
    
5. 在“**备份文件夹的网络路径**”框中，键入您为事务日志备份文件夹创建的共享的网络路径。
    
6. 如果备份文件夹位于主服务器上，请在“**如果备份文件夹位于主服务器上，则键入该文件夹的本地路径(示例: c:\backup)**”框中键入该备份文件夹的本地路径。（如果备份文件夹不在主服务器上，则可将此框留空。）
    
    > [!IMPORTANT]
    > 如果主服务器上的 SQL Server 服务帐户在本地系统帐户下运行, 则必须在主服务器上创建备份文件夹, 并指定该文件夹的本地路径。 
  
7. 配置“**删除文件，如果其保留时间超过**”和“**在以下时间内没有执行备份时报警**”参数。
    
8. 查看“**备份作业**”下的“**计划**”框中所列的备份计划。 若要自定义安装的计划, 请单击 "**计划**", 然后根据需要调整 SQL Server 代理计划。
    
9. 在“**压缩**”下，选择“**使用默认服务器设置**”，然后单击“**确定**”。
    
10. 在“**辅助服务器实例和数据库**”下，单击“**添加**”。
    
11. 单击 "**连接**" 并连接到已配置为辅助服务器的 SQL Server 实例。
    
12. 在“**辅助数据库**”框中，从列表中选择“**mgc**”数据库。
    
13. 在 "**初始化辅助数据库**" 选项卡上, 选择 **"是, 生成主数据库的完整备份", 然后将其还原到辅助数据库 (如果不存在, 则创建辅助数据库)**。
    
14. 在 "**复制文件**" 选项卡上的 "**复制的文件的目标文件夹**" 框中, 键入应将事务日志备份复制到其中的文件夹的路径。 此文件夹通常位于辅助服务器上。
    
15. 请注意 "**复制作业**" 下的 "**日程安排**" 框中列出的复制计划。 若要自定义安装的计划, 请单击 "**计划**", 然后根据需要调整 SQL Server 代理计划。 此计划应该与备份计划大致相同。
    
16. 在 "**还原**" 选项卡上的 "**还原备份时数据库状态**" 下, 选择 "**无恢复模式**" 选项。
    
17. 在 "**延迟还原备份至少:**" 下, 选择 " **0 分钟**"。
    
18. **如果未在内进行还原**, 请在 "警报" 下选择警报阈值。
    
19. 查看 "**还原作业**" 下的 "**日程安排**" 框中列出的还原计划。 若要自定义安装的计划, 请单击 "**计划**", 根据需要调整 SQL Server 代理计划, 然后单击 **"确定"**。 此计划应该与备份计划大致相同。
    
20. 在 "**数据库属性**" 对话框中, 单击 **"确定"** 开始配置过程。
    
## <a name="set-up-sql-server-log-shipping-between-the-primary-mirror-and-the-secondary-database"></a>在主镜像和辅助数据库之间设置 SQL Server 日志传送

如果主持久聊天数据库故障转移到其镜像数据库, 请执行以下步骤, 以使日志传送继续进行。
  
1. 将主持久聊天数据库手动故障转移到镜像。 这可通过使用 Skype for Business 服务器命令行管理程序和**CsDatabaseFailover** cmdlet 完成。
    
2. 使用 SQL Server Management Studio 连接到主持久聊天服务器镜像实例。
    
3. 请确保 SQL Server 代理正在运行。
    
4. 右键单击 mgc 数据库，然后单击“**属性**”。
    
5. 在“**选择页**”下，单击“**事务日志传送**”。
    
6. 选中“**将此数据库启用为日志传送配置中的主数据库**”复选框。
    
7. 在“**事务日志备份**”下，单击“**备份设置**”。
    
8. 在 "**备份文件夹的网络路径**" 框中, 键入为 "事务日志备份" 文件夹创建的共享的网络路径。
    
9. 如果备份文件夹位于主服务器上, 请在 "**如果备份文件夹位于主服务器上**" 中键入备份文件夹的本地路径, 请在 "文件夹" 框中键入本地路径。 (如果备份文件夹不在主服务器上, 你可以将此框留空。)
    
    > [!IMPORTANT]
    > 如果主服务器上的 SQL Server 服务帐户在本地系统帐户下运行, 则必须在主服务器上创建备份文件夹, 并指定该文件夹的本地路径。 
  
10. 配置“**删除文件，如果其保留时间超过**”和“**在以下时间内没有执行备份时报警**”参数。
    
11. 查看“**备份作业**”下的“**计划**”框中所列的备份计划。 若要自定义安装的计划, 请单击 "**计划**", 然后根据需要调整 SQL Server 代理计划。
    
    > [!IMPORTANT]
    > 使用您用于主数据库的相同设置。 
  
12. 在 "**压缩**" 下, 选择 "**使用默认服务器设置**", 然后单击 **"确定"**。
    
13. 在“**辅助服务器实例和数据库**”下，单击“**添加**”。
    
14. 单击 "**连接**", 并连接到已配置为辅助服务器的 SQL Server 实例。
    
15. 在“**辅助数据库**”框中，从列表中选择“**mgc**”数据库。
    
16. 在 "**初始化辅助数据库**" 选项卡上, 选择 "**否, 辅助数据库已初始化**"。
    
17. 在 "**复制**文件" 选项卡上, 在 "**复制的文件的目标文件夹**" 中, 键入应将事务日志备份复制到其中的文件夹的路径, 然后单击 **"确定"**。 此文件夹通常位于辅助服务器上。
    
18. 打开 "**脚本配置**" 下拉列表, 然后选择 "**对新查询进行脚本配置" 窗口**。
    
19. 在 "新建查询" 窗口的 "**数据库属性**" 中, 单击 **"确定"** 开始配置过程。
    
20. 选择并运行查询的第一半 (请参阅步骤 18 \* \* \* \* \* \* ) 至行:--结束: 要在主要\* \* \* \* \* \*位置运行的脚本:。
    
    > [!IMPORTANT]
    > 必须手动运行此脚本, 因为 SQL Server Management Studio 不支持 SQL Server 日志传送配置中的多个主数据库。 
  
21. 选择 "**取消**" 以关闭日志文件传输配置面板, 并建立可正确为主数据库和镜像数据库 (如果故障转移) 实现日志文件传送的工作设置。
    
22. 将主持久聊天数据库手动故障恢复到主数据库。 这是通过使用 Skype for Business 服务器命令行管理程序和**CsDatabaseFailover** cmdlet 完成的。
    

