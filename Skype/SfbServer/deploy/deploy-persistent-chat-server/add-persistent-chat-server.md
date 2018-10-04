---
title: 向您 Skype 业务服务器 2015年拓扑添加持久聊天服务器
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6b4f4d69-3c9d-4bc7-bc9b-46427a095de2
description: 摘要： 阅读本主题可了解如何向您 Skype 业务服务器 2015年拓扑添加持久聊天服务器。
ms.openlocfilehash: ff2486db39546e88c4a75e27875a84a2c3b939ae
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25371980"
---
# <a name="add-persistent-chat-server-to-your-skype-for-business-server-2015-topology"></a>向您 Skype 业务服务器 2015年拓扑添加持久聊天服务器
 
**摘要：** 阅读本主题可了解如何向您 Skype 业务服务器 2015年拓扑添加持久聊天服务器。
  
您计划部署持久聊天服务器的每台服务器上安装必备软件后，您可以使用拓扑生成器以： 
  
- 更新拓扑以包含持久聊天服务器
    
- 发布更新的拓扑
    
> [!NOTE] 
> 持久聊天中的业务服务器 2015 Skype 可用但业务服务器 2019年不再支持在 Skype。 中团队提供了相同的功能。 有关详细信息，请参阅[从企业对 Microsoft 团队的 Skype 旅程](/microsoftteams/journey-skypeforbusiness-teams)。 如果您需要使用持久聊天，您的选择是也迁移要求给团队，此功能的用户或继续对业务服务器 2015年使用 Skype。 

## <a name="update-your-topology-to-include-persistent-chat-server"></a>更新拓扑以包含持久聊天服务器

安装无需灾难恢复配置单个持久聊天服务器池执行以下步骤。 有关配置高可用性和灾难恢复的扩展持久聊天服务器池，请参阅[配置高可用性和灾难恢复对于 Persistent Chat Server in Skype 的业务服务器 2015年](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md)。
  
若要部署多个持久聊天服务器池，请为每个池重复相同的过程。
  
1. 业务服务器运行 Skype 的计算机上或在其上 Skype 的安装了 Business Server 管理工具，使用登录本地 Users 组 （或具有同等用户权限的帐户） 的成员的帐户。
    
    > [!NOTE]
    > 您可以使用本地用户组的成员的帐户定义拓扑，但要发布拓扑，需要安装 Skype 业务服务器，必须使用**Domain Admins**组和**的成员的帐户RTCUniversalServerAdmins**组，并在您打算对于 Persistent Chat Server 文件存储 （以便该拓扑生成器可以配置所需的 Dacl），使用的文件存储上具有完全控制权限 （读取、 写入和修改） 或使用的帐户同等的权限。
  
2. 启动拓扑生成器。
    
3. 在控制台树中，导航到**持久聊天池**节点，并展开该选择 Skype 对于业务服务器池，或右键单击节点并选择**新的持久聊天池**。 您必须定义池的完全限定的域名 (FQDN)，并指示该池将是单服务器池或多服务器池部署。
    
    您可选择“**多计算机池**”或“**单计算机池**”。 如果您打算持久聊天服务器池中有多个前端服务器，请选择前者。 现在或稍后做出此选择，因为在创建单计算机池之后，将无法向其添加其他服务器。 如果选择多计算机池，输入单个前端服务器组成该池的名称。
    
    > [!IMPORTANT]
    > 如果要在 Standard Edition server 上安装持久聊天服务器角色，则 FQDN 需要与 Standard Edition server 的 FQDN 匹配。 
  
4. 定义持久聊天服务器池的一个简单的**显示名称**。 可以自定义客户端，使用的显示名称，尤其是在有多个持久聊天服务器池区分聊天室时。
    
5. 定义持久聊天服务器用于与 Skype 业务 Server 前端服务器进行通信的端口。 默认端口为 5041。
    
6. 如果您的组织需要合规性支持，请选中“**启用合规性**”复选框。 如果选择了，与持久聊天服务器前端服务器相同的计算机上安装持久聊天服务器合规性服务。 系统会提示您选择 SQL Server 后端服务器持久聊天服务器合规性更高版本。
    
7. 分配持久聊天服务器池的站点关联。 选择**默认为此池用于网站\<SiteName\>** 复选框或**使用此池作为所有站点的默认设置**将此持久聊天服务器池指定为当前网站或所有网站的默认池。 当业务客户端 Skype 用于创建和管理聊天室时，以便它可以将聊天室创建和管理操作路由到该池的聊天室创建和管理体验中使用与用户的站点关联的默认池。 这仅适用于具有多个持久聊天服务器池部署，并且想要使用的持久聊天服务器的聊天室创建和管理功能。
    
    > [!IMPORTANT]
    > 您可以自定义使用持久聊天服务器软件开发工具包 (SDK) 的聊天室创建和管理功能。 
  
8. 通过执行以下某项操作来定义**SQL 存储用于持久聊天服务器后端 （其中存储聊天室内容）** ：
    
   - 若要使用现有的 SQL Server 存储，请在下拉列表中，单击您想要使用的 SQL Server 存储的名称。
    
   - 若要指定新的 SQL Server 数据库，请单击**新建**，在**定义新的 SQL 存储**，请执行以下：
    
   - 在**SQL Server FQDN**中，指定要在其创建新的 SQL Server 数据库的 SQL Server 的 FQDN。
    
   - 选择“**默认实例**”以使用默认实例，或指定其他实例，选择“**命名实例**”，然后指定要使用的实例。
    
     > [!NOTE]
     > 有关如何配置 SQL Server 备份数据库的灾难恢复的详细信息，请参阅[配置高可用性和灾难恢复对于 Persistent Chat Server in Skype 的业务服务器 2015年](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md)。 
  
9. 如果启用合规性，请定义 SQL Server 合规性存储。
    
    > [!IMPORTANT]
    > 有关如何配置 SQL Server 镜像的高可用性对于 Persistent Chat Server 数据库和持久聊天服务器合规性数据库的详细信息，请参阅[配置高可用性和灾难恢复 for Persistent Chat Server in Skype为业务服务器 2015年](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md)。 
  
10. 定义文件存储。 文件存储是一个文件夹，其中存储了已上载到文件存储库的所有文件的副本（例如，存储已发布到聊天室的文件附件）。 对于多服务器持久聊天服务器拓扑，这必须是通用命名约定 (UNC) 路径;对于单服务器持久聊天服务器拓扑，它可以是本地文件路径。
    
    若要使用现有文件存储，请执行下列步骤：
    
    - 在“**文件服务器 FQDN**”中，指定要在其上创建新的文件存储的计算机的 FQDN。
    
    - 在“**文件共享**”中，指定要使用的文件存储。
    
      > [!IMPORTANT]
      > 您可以在之前您创建的文件存储，但您必须中定义的位置定义发布拓扑之前创建的文件存储在拓扑生成器中定义的文件存储。 如果文件存储不存在，则发布拓扑的尝试将失败。 
  
11. 选择要为此持久聊天服务器池用作下一个跃点的前端服务器池。 这是将能够将持久聊天服务器请求路由到此池中的前端服务器池。
    
12. 若要保存配置，请单击“**完成**”。 持久聊天服务器池出现在拓扑生成器附带有特定的池设置。
    
    若要发布更新后已向其添加持久聊天服务器的拓扑，请参阅 Publish 更新的拓扑。
    
    > [!NOTE]
    > 使用拓扑生成器中已打开，您可以继续执行步骤 3 中发布更新的拓扑以开始发布更新后的拓扑。 
  
## <a name="publish-the-updated-topology"></a>发布更新的拓扑
<a name="BKMK_PublishTopology"> </a>

更新之后您在拓扑生成器中的拓扑，您必须将发布拓扑中央管理存储之前，您可以配置和使用 Business Server Skype。 数据的只读副本将复制到拓扑中的所有服务器，使所有服务器与拓扑和其他配置更改保持同步。
  
发布拓扑之前，对于 Persistent Chat Server 安装数据库。 使用拓扑生成器来安装数据库选择**操作**和**安装数据库**。
  
1. 业务服务器运行 Skype 的计算机上或在其上 Skype 的安装了 Business Server 管理工具，使用登录**以 Domain Admins**组和**RTCUniversalServerAdmins**组的成员的帐户且具有完全控制权限 （读取、 写入和修改） 上的文件存储用于对于 Persistent Chat Server 文件存储 （以便该拓扑生成器可以配置所需的随机访问控制列表 (Dacl)），或使用具有等效用户的帐户权限。
    
2. 启动拓扑生成器。 选择“**从本地文件打开拓扑**”（如果在本地保存它）。
    
3. 在控制台树中，右键单击**业务服务器 2015年的 Skype**，，然后单击**发布拓扑**。
    
4. 在“**发布拓扑**”页上，单击“**下一步**”。
    
5. 在“**发布向导完成**”页上，确认已成功发布拓扑，然后单击“**完成**”。
    

