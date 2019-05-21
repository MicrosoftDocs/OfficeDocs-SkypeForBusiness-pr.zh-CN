---
title: 将持久聊天服务器添加到 Skype for business Server 2015 拓扑
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6b4f4d69-3c9d-4bc7-bc9b-46427a095de2
description: '摘要: 阅读本主题, 了解如何将持久聊天服务器添加到 Skype for business Server 2015 拓扑。'
ms.openlocfilehash: c953b93d8ea20b8878269c8be0540ba8e032ce87
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34282299"
---
# <a name="add-persistent-chat-server-to-your-skype-for-business-server-2015-topology"></a>将持久聊天服务器添加到 Skype for business Server 2015 拓扑
 
**摘要:** 阅读本主题, 了解如何将持久聊天服务器添加到 Skype for business Server 2015 拓扑。
  
在计划部署持久聊天服务器的每台服务器上安装必备软件后, 可使用拓扑生成器执行以下操作: 
  
- 更新拓扑以包含持久聊天服务器
    
- 发布更新的拓扑
    
> [!NOTE] 
> Skype for business Server 2015 中提供了持久聊天, 但 Skype for business Server 2019 不再支持此功能。 团队中提供了相同的功能。 有关详细信息, 请参阅[从 Skype For Business 迁移到 Microsoft 团队](/microsoftteams/journey-skypeforbusiness-teams)。 如果需要使用持久聊天, 您可以选择将需要此功能的用户迁移到团队, 或继续使用 Skype for Business Server 2015。 

## <a name="update-your-topology-to-include-persistent-chat-server"></a>更新拓扑以包含持久聊天服务器

若要在不使用灾难恢复配置的情况下安装单个持久聊天服务器池, 请执行以下步骤。 有关为高可用性和灾难恢复配置延长的持久聊天服务器池, 请参阅[在 Skype for Business server 2015 中配置持久聊天服务器的高可用性和灾难恢复](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md)。
  
若要部署多个持久聊天服务器池, 请为每个池重复相同的过程。
  
1. 在运行 Skype for Business 服务器或安装了 Skype for business 服务器管理工具的计算机上, 使用属于本地 Users 组的成员 (或具有等效用户权限的帐户) 登录。
    
    > [!NOTE]
    > 你可以通过使用属于本地用户组的成员的帐户定义拓扑, 但要发布安装 Skype for Business 服务器所需的拓扑, 你必须使用**域管理员**组成员的帐户和**RTCUniversalServerAdmins**组, 并且具有对持久聊天服务器文件存储区中要使用的文件存储的完全控制权限 (读取、写入和修改) (以便拓扑生成器可以配置所需的 dacl) 或帐户等效的权限。
  
2. 启动拓扑生成器。
    
3. 在控制台树中, 导航到 "**持久聊天池**" 节点并展开它以选择 Skype For business 服务器池, 或者右键单击该节点, 然后选择 "**新建持久聊天池**"。 必须定义池的完全限定的域名 (FQDN), 并指示池是单服务器池还是多服务器池部署。
    
    您可选择“**多计算机池**”或“**单计算机池**”。 如果计划在持久聊天服务器池中安装多台前端服务器, 请选择前者。 现在或稍后做出此选择，因为在创建单计算机池之后，将无法向其添加其他服务器。 如果你选择多台计算机池, 请输入组成池的单个前端服务器的名称。
    
    > [!IMPORTANT]
    > 如果在标准版服务器上安装持久聊天服务器角色, 则 FQDN 需要与标准版服务器的 FQDN 相匹配。 
  
4. 为持久聊天服务器池定义一个简单的**显示名称**。 显示名称可由自定义客户端使用, 特别是当存在多个持久聊天服务器池来区分房间时。
    
5. 定义持久聊天服务器用于与 Skype for business 服务器前端服务器通信的端口。 默认端口为 5041。
    
6. 如果您的组织需要合规性支持，请选中“**启用合规性**”复选框。 如果选择此项, 持久聊天服务器合规性服务将与持久聊天服务器前端服务器安装在同一台计算机上。 系统将提示你选择 SQL Server 后端服务器, 以便在以后持续聊天服务器合规性。
    
7. 为持久聊天服务器池分配网站相关性。 选中 "**将此池用作网站\<的 SiteName\>默认值**" 复选框, 或**将此池用作所有网站的默认值**将此持久聊天服务器池指定为当前网站或所有网站的默认池。 当使用 Skype for Business 客户端创建和管理会议室时, 聊天室创建和管理体验将使用与用户的网站关联的默认池, 以便它可以将会议室创建和管理操作路由到该池。 这仅适用于已部署多个持久聊天服务器池的情况, 并且希望使用持久聊天服务器的聊天室创建和管理功能。
    
    > [!IMPORTANT]
    > 可以使用持久聊天服务器软件开发工具包 (SDK) 自定义聊天室创建和管理功能。 
  
8. 通过执行下列操作之一, 定义**持久聊天服务器后端的 SQL 应用商店 (存储聊天室内容)** :
    
   - 若要使用现有的 SQL Server 应用商店, 请在下拉列表中单击要使用的 SQL Server 应用商店的名称。
    
   - 若要指定新的 SQL Server 数据库, 请单击 "**新建**", 然后在 "**定义新的 SQL 存储**" 中, 执行下列操作:
    
   - 在**SQL SERVER FQDN**中, 指定要在其上创建新的 sql server 数据库的 sql SERVER 的 FQDN。
    
   - 选择“**默认实例**”以使用默认实例，或指定其他实例，选择“**命名实例**”，然后指定要使用的实例。
    
     > [!NOTE]
     > 有关如何为灾难恢复配置 SQL Server 备份数据库的详细信息, 请参阅[在 Skype for Business server 2015 中配置持久聊天服务器的高可用性和灾难恢复](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md)。 
  
9. 如果已启用合规性, 请定义 SQL Server 合规性存储。
    
    > [!IMPORTANT]
    > 有关如何将 SQL Server 镜像配置为持久聊天服务器数据库和持久聊天服务器合规性数据库的高可用性的详细信息, 请参阅[在 Skype 中配置持久聊天服务器的高可用性和灾难恢复适用于 Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md)。 
  
10. 定义文件存储。 文件存储是一个文件夹，其中存储了已上载到文件存储库的所有文件的副本（例如，存储已发布到聊天室的文件附件）。 在多服务器持久聊天服务器拓扑的情况下, 这必须是通用命名约定 (UNC) 路径;对于单服务器持久聊天服务器拓扑, 它可以是本地文件路径。
    
    若要使用现有文件存储，请执行下列步骤：
    
    - 在“**文件服务器 FQDN**”中，指定要在其上创建新的文件存储的计算机的 FQDN。
    
    - 在“**文件共享**”中，指定要使用的文件存储。
    
      > [!IMPORTANT]
      > 你可以在创建文件存储之前在拓扑生成器中定义文件存储, 但你必须在发布拓扑之前在定义的位置创建文件存储。 如果文件存储不存在，则发布拓扑的尝试将失败。 
  
11. 选择要用作此持久聊天服务器池的下一跃点的前端服务器池。 这是可以将持久聊天服务器请求路由到此池的前端服务器池。
    
12. 若要保存配置，请单击“**完成**”。 持久聊天服务器池显示在拓扑生成器中, 附带你的特定池设置。
    
    若要发布已添加持久聊天服务器的已更新拓扑, 请参阅发布更新后的拓扑。
    
    > [!NOTE]
    > 拓扑生成器已打开, 你可以继续在发布更新拓扑中的步骤3以开始发布更新的拓扑。 
  
## <a name="publish-the-updated-topology"></a>发布更新的拓扑
<a name="BKMK_PublishTopology"> </a>

在拓扑生成器中更新拓扑后, 必须先将拓扑发布到中央管理存储, 然后才能配置和使用 Skype for Business 服务器。 数据的只读副本将复制到拓扑中的所有服务器，使所有服务器与拓扑和其他配置更改保持同步。
  
在发布拓扑之前, 请安装持久聊天服务器的数据库。 使用拓扑生成器, 通过选择 "**操作**" 并**安装数据库**来安装数据库。
  
1. 在运行 Skype for Business 服务器或安装了 Skype for business Server 管理工具的计算机上, 使用**域管理员**组和**RTCUniversalServerAdmins**组的成员帐户登录。并且具有对永久聊天服务器文件存储使用的文件存储区的完全控制权限 (读取、写入和修改) (以便拓扑生成器可以配置所需的随机访问控制列表 (Dacl)) 或具有等效用户的帐户使用权.
    
2. 启动拓扑生成器。 选择“**从本地文件打开拓扑**”（如果在本地保存它）。
    
3. 在控制台树中, 右键单击 " **Skype For Business Server 2015**", 然后单击 "**发布拓扑**"。
    
4. 在“**发布拓扑**”页上，单击“**下一步**”。
    
5. 在“**发布向导完成**”页上，确认已成功发布拓扑，然后单击“**完成**”。
    

