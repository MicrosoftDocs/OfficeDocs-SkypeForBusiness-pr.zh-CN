---
title: 在 Skype for Business Server 2015 中管理持久聊天服务器的高可用性和灾难恢复
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4346e70b-ac48-4ab9-853e-3cdd6dcfe678
description: 摘要： 了解如何管理持久聊天服务器高可用性和灾难恢复 Skype 中的业务服务器 2015年。
ms.openlocfilehash: 477897362a01ae3ac6097c50eaed8f9ece31f49d
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25371632"
---
# <a name="manage-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中管理持久聊天服务器的高可用性和灾难恢复
 
**摘要：** 了解如何管理持久聊天服务器高可用性和灾难恢复 Skype 中的业务服务器 2015年。
  
本主题介绍如何进行故障转移和故障后 Persistent Chat Server。 之前阅读本主题，请务必阅读 Persistent Chat Server in 的 Skype[规划高可用性和灾难恢复 for Persistent Chat Server 中的业务服务器 2015 Skype](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md)和[配置高可用性和灾难恢复业务服务器 2015年](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)。

> [!NOTE]
> 持久聊天中的业务服务器 2015 Skype 可用但业务服务器 2019年不再支持在 Skype。 中团队提供了相同的功能。 有关详细信息，请参阅[从企业对 Microsoft 团队的 Skype 旅程](/microsoftteams/journey-skypeforbusiness-teams)。 如果您需要使用持久聊天，您的选择是也迁移要求给团队，此功能的用户或继续对业务服务器 2015年使用 Skype。 
  
## <a name="fail-over-persistent-chat-server"></a>持久聊天服务器故障转移

持久聊天服务器的故障转移被旨在作为主要一个手动过程。
  
故障转移过程已根据假设辅助数据中心已启动并正在运行，但完全不可用，包括以下主要的持久聊天数据库所在的持久聊天服务器服务：
  
- 持久聊天服务器主数据库和持久聊天服务器镜像数据库不可用。
    
- Skype 业务 Server 前端服务器已关闭。
    
该过程主要包含两个基本步骤：
  
- 恢复主持久聊天数据库 (mgc)。
    
- 建立新的主数据库的镜像。
    
持久聊天合规性数据库 (mgccomp) 不故障转移。 此数据库的内容具有临时性并将在合规性适配器处理数据时被清除。 您有责任，作为持久聊天管理员，以正确管理适配器输出，以避免数据丢失。
  
对持久聊天服务器进行故障转移：
  
1. 取消日志传送从持久聊天服务器备份日志传送数据库。
    
   - 使用 SQL Server Management Studio，连接到 Persistent Chat Server 备份 mgc 数据库所在的数据库实例。
    
   - 打开主数据库的查询窗口。
    
   - 使用以下命令取消日志传送：
    
   ```
   exec sp_delete_log_shipping_secondary_database mgc
   ```

2. 从备份共享将任何未复制的备份文件复制到备份服务器的复制目标文件夹。
    
3. 按顺序将任何未应用的事务日志备份应用到辅助数据库。 有关详细信息，请参阅[How to： 应用事务日志备份 (TRANSACT-SQL)](https://go.microsoft.com/fwlink/p/?linkid=247428)。
    
4. 使备份 mgc 数据库联机。使用在步骤 1b 中打开的查询窗口，执行下列操作：
    
   - 如果包含以下项，将断开与 mgc 数据库的所有连接：
    
   - **exec sp_who2**，用于识别与 mgc 数据库的连接。
    
   - **kill \<spid\>** 结束这些连接。
    
   - 使数据库联机：
    
   - **通过恢复还原数据库 mgc**。
    
5. 在业务 Server Management Shell 的 Skype，使用命令**Set-cspersistentchatstate-Identity"service: atl-cs-001.litwareinc.com"-PoolState FailedOver**故障转移到 mgc 备份数据库。 确保用您的“持久聊天”池的完全限定的域名替换 atl-cs-001.litwareinc.com。
    
    mgc 备份数据库现在充当主数据库。
    
6. 在业务 Server Management Shell 的 Skype，使用**Install-csmirrordatabase** cmdlet 建立备份数据库现在充当主数据库的高可用性镜像。 使用备份数据库实例作为主数据库并使用备份镜像数据库实例作为镜像实例。 此镜像与最初在安装期间为主数据库配置的镜像不同。
    
7. 设置持久聊天服务器的活动服务器。 从业务 Server Management Shell 的 Skype，使用**Set-cspersistentchatactiveserver** cmdlet 可设置活动服务器的列表。
    
    > [!IMPORTANT]
    > 所有活动服务器必须都与新主数据库位于同一数据中心中，或位于与数据库之间存在低延迟/高带宽连接的数据中心中。 
  
    此时，从持久聊天服务器主数据库到持久聊天服务器备份数据库的故障转移即成功完成。
    
## <a name="fail-back-persistent-chat-server"></a>失败返回持久聊天服务器

此过程概述了从 Persistent Chat Server 故障中恢复并重新建立从主数据中心的操作所必需的步骤。
  
持久聊天服务器失败期间的主数据中心会受到影响完成中断和主和镜像数据库不可用。 主数据中心将故障转移到备份服务器。
  
以下过程在备份主数据中心并重新生成服务器后还原正常操作。 此过程假定主数据中心已经从总故障中恢复并 mgc 数据库和 mgccomp 数据库具有已重新构建和重新安装使用拓扑生成器。
  
该过程还假定在故障转移期间未部署新镜像和备份服务器，并且唯一部署的服务器是故障转移持久聊天服务器中之前定义的备份服务器及其镜像服务器。
  
这些步骤旨在恢复配置在导致从主服务器故障转移到备份服务器的灾难发生之前的状态。
  
1. 使用适用于业务 Server 命令行管理程序从 Skype **Set-cspersistentchatactiveserver** cmdlet 清除所有服务器从持久聊天活动服务器列表。 这将停止所有持久聊天服务器故障回复期间与 mgc 数据库和 mgccomp 数据库连接。
    
    > [!IMPORTANT]
    > 第二上的 SQL Server 代理持久聊天服务器后端服务器应特权帐户下运行。 尤其需要指出的是，该帐户必须具有以下权限： 
  
   - 对于放置备份的网络共享的读取权限。
    
   - 对于备份将复制到的特定本地目录的写入权限。
    
2. 在备份 mgc 数据库上禁用镜像：
    
   - 使用 SQL Server Management Studio，连接到备份 mgc 实例。
    
   - 右键单击 mgc 数据库，指向“**任务**”，然后单击“**镜像**”。
    
   - 单击“**取消镜像**”。
    
   - 单击“**确定**”。
    
   - 对 mgccomp 数据库执行相同步骤。
    
3. 备份 mgc 数据库，使其可以还原为新主数据库：
    
   - 使用 SQL Server Management Studio，连接到备份 mgc 实例。
    
   - 右键单击 mgc 数据库，指向“**任务**”，然后单击“**备份**”。随即将显示“**备份数据库**”对话框。
    
   - 在“**备份类型**”中，选择“**完全**”。
    
   - 对于“**备份组件**”，请单击“**数据库**”。
    
   - 接受“**名称**”中建议的默认备份集名称，或为备份集输入不同名称。
    
   -  *\<可选\>* 在**说明**框中，输入备份集的说明。
    
   - 从目标列表中删除默认备份位置。
    
   - 使用您建立用于日志传送的共享位置的路径向列表中添加文件。主数据库和备份数据库均可使用此路径。
    
   - 单击“**确定**”关闭对话框并开始备份过程。
    
4. 使用上一步中创建的备份数据库还原主数据库。
    
   - 使用 SQL Server Management Studio，连接到主 mgc 实例。
    
   - 右键单击 mgc 数据库，指向“**任务**”，指向“**还原**”，然后单击“**数据库**”。随即会显示“**还原数据库**”对话框。
    
   - 选择“**自设备**”。
    
   - 单击浏览按钮，将打开“**指定备份**”对话框。在“**备份媒体**”中，选择“**文件**”。单击“**添加**”，选择您在步骤 3 中创建的备份文件，然后单击“**确定**”。
    
   - 在“**选择用于还原的备份集**”中，选择备份。
    
   - 在“**选择页**”窗格中单击“**选项**”。
    
   - 在“**还原选项**”中，选择“**覆盖现有数据库**”。
    
   - 在“**恢复状态**”中，选择“**使数据库处于可以使用的状态**”。
    
   - 单击“**确定**”开始还原过程。
    
5. 配置主数据库的 SQL Server 日志传送。 按照中的过程[配置高可用性和灾难恢复 for Persistent Chat Server 中的业务服务器 2015 Skype](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)建立主 mgc 数据库的日志传送。
    
6. 设置持久聊天服务器的活动服务器。 从业务 Server Management Shell 的 Skype，使用**Set-cspersistentchatactiveserver** cmdlet 可设置活动服务器的列表。
    
    > [!IMPORTANT]
    > 所有活动服务器必须都与新主数据库位于同一数据中心中，或位于与数据库之间存在低延迟/高带宽连接的数据中心中。 
  
若要还原到其正常的池状态，请运行以下 Windows PowerShell 命令：
  
```
Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal
```

有关详细信息，请参阅[Set-cspersistentchatstate](https://docs.microsoft.com/powershell/module/skype/set-cspersistentchatstate?view=skype-ps) cmdlet 的帮助主题。
  

