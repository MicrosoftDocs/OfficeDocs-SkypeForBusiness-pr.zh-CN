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
description: 摘要： 了解如何管理业务服务器 2015年持久聊天服务器的高可用性和灾难恢复 Skype。
ms.openlocfilehash: 8bc80ff6a38238b81b658a7f4d9620dc3a56b9be
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="manage-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中管理持久聊天服务器的高可用性和灾难恢复
 
**摘要：**了解如何管理业务服务器 2015年持久聊天服务器的高可用性和灾难恢复 Skype。
  
本主题介绍如何进行故障转移和故障恢复持久聊天服务器。 在阅读本主题之前, 请务必阅读中对 Skype 的持久聊天服务器[实现高可用性和业务服务器 2015年的 Skype 的持久聊天服务器的灾难恢复计划](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md)和[配置高可用性和灾难恢复商业服务器 2015年](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)。
  
## <a name="fail-over-persistent-chat-server"></a>持久的聊天服务器故障转移

持久的聊天服务器的故障切换可主要是一个手动过程。
  
故障转移过程是基于假设从属数据中心都已启动并正在运行，但主要的持久聊天数据库所在的持久聊天服务器服务完全不可用，包括下列：
  
- 持续聊天服务器的主数据库和镜像数据库持久性的聊天服务器都已关闭。
    
- Skype 的业务服务器前端服务器已关闭。
    
该过程主要包含两个基本步骤：
  
- 恢复主持久聊天数据库 (mgc)。
    
- 建立新的主数据库的镜像。
    
持续聊天的法规遵从性数据库 (mgccomp) 不被故障切换。 此数据库的内容具有临时性并将在合规性适配器处理数据时被清除。 它是您的责任，作为持久聊天管理员，来正确管理适配器输出，以避免数据丢失。
  
对持久聊天服务器进行故障转移：
  
1. 删除日志传送从持久聊天服务器备份日志传送的数据库。
    
  - 使用 SQL Server 管理 Studio，连接到数据库实例的持久聊天服务器备份 mgc 数据库所在的位置。
    
  - 打开主数据库的查询窗口。
    
  - 使用以下命令取消日志传送：
    
  ```
  exec sp_delete_log_shipping_secondary_database mgc
  ```

2. 从备份共享将任何未复制的备份文件复制到备份服务器的复制目标文件夹。
    
3. 按顺序将任何未应用的事务日志备份应用到辅助数据库。 有关详细信息，请参阅[如何： 在应用事务日志备份 (事务处理 SQL)](https://go.microsoft.com/fwlink/p/?linkid=247428)。
    
4. 使备份 mgc 数据库联机。使用在步骤 1b 中打开的查询窗口，执行下列操作：
    
  - 如果包含以下项，将断开与 mgc 数据库的所有连接：
    
  - **exec sp_who2**，用于识别与 mgc 数据库的连接。
    
  - **kill \<spid\>**来结束这些连接。
    
  - 使数据库联机：
    
  - **通过恢复还原数据库 mgc**。
    
5. 在业务服务器管理外壳的 Skype，使用命令**集 CsPersistentChatState-标识"服务： atl-cs-001.litwareinc.com"-PoolState FailedOver**故障转移到 mgc 备份数据库。 确保用您的“持久聊天”池的完全限定的域名替换 atl-cs-001.litwareinc.com。
    
    mgc 备份数据库现在充当主数据库。
    
6. 在业务服务器管理外壳的 Skype，使用**安装 CsMirrorDatabase** cmdlet 建立高可用性镜像正在充当主数据库的备份数据库。 使用备份数据库实例作为主数据库并使用备份镜像数据库实例作为镜像实例。 此镜像与最初在安装期间为主数据库配置的镜像不同。
    
7. 设置活动持久聊天服务器的服务器。 从业务服务器管理外壳的 Skype，使用**一组 CsPersistentChatActiveServer** cmdlet 设置活动服务器的列表。
    
    > [!IMPORTANT]
    > 所有活动服务器必须都与新主数据库位于同一数据中心中，或位于与数据库之间存在低延迟/高带宽连接的数据中心中。 
  
    在这种情况下，从持久聊天服务器的主数据库故障转移到持久聊天服务器备份数据库已成功完成。
    
## <a name="fail-back-persistent-chat-server"></a>故障恢复持久聊天服务器

此步骤概述从持久聊天服务器故障时，恢复和重建从主数据中心的操作所必需的步骤。
  
持久的聊天服务器发生故障，在主数据中心发生完全停电，并且主和镜像数据库变得不可用。 主数据中心将故障转移到备份服务器。
  
以下过程在备份主数据中心并重新生成服务器后还原正常操作。 此过程假定主数据中心已经从总的停机中恢复并且，mgc 数据库和 mgccomp 数据库已重新构建和重新安装通过使用拓扑生成器。
  
该过程还假定在故障转移期间未部署新镜像和备份服务器，并且唯一部署的服务器是故障转移持久聊天服务器中之前定义的备份服务器及其镜像服务器。
  
这些步骤旨在恢复配置在导致从主服务器故障转移到备份服务器的灾难发生之前的状态。
  
1. 通过**设置 CsPersistentChatActiveServer** cmdlet 从 Skype 业务服务器管理外壳程序清除持久聊天活动服务器列表中的所有服务器。 这将停止所有持久聊天服务器回切期间对 mgc 数据库和 mgccomp 数据库连接。
    
    > [!IMPORTANT]
    > 辅助数据库上的 SQL Server 代理持久聊天服务器后端服务器应特权帐户下运行。 尤其需要指出的是，该帐户必须具有以下权限： 
  
   - 对于放置备份的网络共享的读取权限。
    
   - 对于备份将复制到的特定本地目录的写入权限。
    
2. 在备份 mgc 数据库上禁用镜像：
    
   - 使用 SQL Server 管理 Studio，连接到备份 mgc 实例。
    
   - 右键单击 mgc 数据库，指向“**任务**”，然后单击“**镜像**”。
    
   - 单击“**取消镜像**”。
    
   - 单击“**确定**”。
    
   - 对 mgccomp 数据库执行相同步骤。
    
3. 备份 mgc 数据库，使其可以还原为新主数据库：
    
   - 使用 SQL Server 管理 Studio，连接到备份 mgc 实例。
    
   - 右键单击 mgc 数据库，指向“**任务**”，然后单击“**备份**”。随即将显示“**备份数据库**”对话框。
    
   - 在“**备份类型**”中，选择“**完全**”。
    
   - 对于“**备份组件**”，请单击“**数据库**”。
    
   - 接受“**名称**”中建议的默认备份集名称，或为备份集输入不同名称。
    
   -  *\<可选\>* 在**说明**中，输入备份集的描述。
    
   - 从目标列表中删除默认备份位置。
    
   - 使用您建立用于日志传送的共享位置的路径向列表中添加文件。主数据库和备份数据库均可使用此路径。
    
   - 单击“**确定**”关闭对话框并开始备份过程。
    
4. 使用上一步中创建的备份数据库还原主数据库。
    
   - 使用 SQL Server 管理 Studio，连接到主 mgc 实例。
    
   - 右键单击 mgc 数据库，指向“**任务**”，指向“**还原**”，然后单击“**数据库**”。随即会显示“**还原数据库**”对话框。
    
   - 选择“**自设备**”。
    
   - 单击浏览按钮，将打开“**指定备份**”对话框。在“**备份媒体**”中，选择“**文件**”。单击“**添加**”，选择您在步骤 3 中创建的备份文件，然后单击“**确定**”。
    
   - 在“**选择用于还原的备份集**”中，选择备份。
    
   - 在“**选择页**”窗格中单击“**选项**”。
    
   - 在“**还原选项**”中，选择“**覆盖现有数据库**”。
    
   - 在“**恢复状态**”中，选择“**使数据库处于可以使用的状态**”。
    
   - 单击“**确定**”开始还原过程。
    
5. 主数据库配置 SQL Server 日志传送。 请按照中的过程[配置高可用性和灾难恢复业务服务器 2015年的 Skype 的持久聊天服务器](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)来建立主 mgc 数据库的日志传送。
    
6. 设置活动持久聊天服务器的服务器。 从业务服务器管理外壳的 Skype，使用**一组 CsPersistentChatActiveServer** cmdlet 设置活动服务器的列表。
    
    > [!IMPORTANT]
    > 所有活动服务器必须都与新主数据库位于同一数据中心中，或位于与数据库之间存在低延迟/高带宽连接的数据中心中。 
  
若要恢复到正常状态运行下的 Windows PowerShell 命令的池：
  
```
Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal
```

有关详细信息，请参阅[设置 CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/set-cspersistentchatstate?view=skype-ps) cmdlet 的帮助主题。
  

