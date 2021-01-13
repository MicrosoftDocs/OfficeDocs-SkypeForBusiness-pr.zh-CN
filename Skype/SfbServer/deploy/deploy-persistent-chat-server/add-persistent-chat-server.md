---
title: 将持久聊天服务器添加到 Skype for Business Server 2015 拓扑
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6b4f4d69-3c9d-4bc7-bc9b-46427a095de2
description: 摘要：阅读本主题，了解如何将持久聊天服务器添加到 Skype for Business Server 2015 拓扑。
ms.openlocfilehash: 3b0f3ca57af4b9bf53125e38e1aa3005099b5b70
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825102"
---
# <a name="add-persistent-chat-server-to-your-skype-for-business-server-2015-topology"></a>将持久聊天服务器添加到 Skype for Business Server 2015 拓扑
 
**摘要：** 阅读本主题，了解如何将持久聊天服务器添加到 Skype for Business Server 2015 拓扑。
  
在计划部署持久聊天服务器的每台服务器上安装必备软件后，可使用拓扑生成器： 
  
- 更新拓扑以包括持久聊天服务器
    
- 发布更新的拓扑
    
> [!NOTE] 
> 持久聊天在 Skype for Business Server 2015 中可用，但在 Skype for Business Server 2019 中不再受支持。 Teams 中也提供相同的功能。 有关详细信息，请参阅 [Microsoft Teams](/microsoftteams/upgrade-start-here)升级入门。 如果你需要使用持久聊天，你的选择是：将需要此功能的用户迁移到 Teams，或者继续使用 Skype for Business Server 2015。 

## <a name="update-your-topology-to-include-persistent-chat-server"></a>更新拓扑以包括持久聊天服务器

执行以下步骤以安装单个持久聊天服务器池，而无需进行灾难恢复配置。 有关为扩展持久聊天服务器池配置高可用性和灾难恢复的信息，请参阅在 [Skype for Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md)中为持久聊天服务器配置高可用性和灾难恢复。
  
若要部署多个持久聊天服务器池，请对每个池重复相同的过程。
  
1. 在运行 Skype for Business Server 或安装了 Skype for Business Server 管理工具的计算机上，使用作为本地 Users 组 (成员的帐户或具有同等用户权限的帐户登录) 。
    
    > [!NOTE]
    > 可以使用作为本地 Users 组的成员的帐户定义拓扑，但要发布拓扑， 安装 Skype for Business Server 时需要拥有的帐户必须是 **Domain Admins** 组和 **RTCUniversalServerAdmins** 组的成员，并且对要用于持久聊天服务器文件存储 (的文件存储具有完全控制权限 () 以便拓扑生成器可以配置所需的 DACLs) 或具有同等权限的帐户。
  
2. 启动拓扑生成器。
    
3. 在控制台树中，导航到 **"持久聊天** 池"节点并展开它以选择 Skype for Business Server 池，或者右键单击该节点并选择 **"新建持久聊天池"。** 您必须定义池的完全限定域名 (FQDN) ，并指示该池是单服务器池还是多服务器池部署。
    
    您可选择“多计算机池”或“单计算机池”。 如果计划在持久聊天服务器池中拥有多个前端服务器，请选择前者。 现在或稍后做出此选择，因为在创建单计算机池之后，将无法向其添加其他服务器。 如果选择多计算机池，请输入组成该池的单个前端服务器的名称。
    
    > [!IMPORTANT]
    > 如果要在 Standard Edition 服务器上安装持久聊天服务器角色，则 FQDN 需要与 Standard Edition Server 的 FQDN 相匹配。 
  
4. 定义持久 **聊天** 服务器池的简单显示名称。 自定义显示名称，尤其是在存在多个持久聊天服务器池来区分聊天室时。
    
5. 定义持久聊天服务器用于与 Skype for Business Server 前端服务器进行通信的端口。 默认端口为 5041。
    
6. 如果您的组织需要合规性支持，请选中“启用合规性”复选框。 如果选择，持久聊天服务器合规性服务将安装在与持久聊天服务器前端服务器相同的计算机上。 系统稍后会提示您SQL Server后端服务器进行持久聊天服务器合规性。
    
7. 为持久聊天服务器池分配站点相关性。 选中 **"使用此池作为站点 \<SiteName\>** 的默认池"复选框或"使用此池作为所有站点的默认池"，以将此持久聊天服务器池指定为当前站点或所有站点的默认池。 当 Skype for Business 客户端用于创建和管理聊天室时，与用户网站关联的默认池由聊天室创建和管理体验使用，以便它可以将聊天室创建和管理操作路由到该池。 这仅适用于部署了多个持久聊天服务器池，并且希望使用持久聊天服务器的聊天室创建和管理功能的情况。
    
    > [!IMPORTANT]
    > 您可以使用持久聊天服务器软件开发工具包和 SDK)  (自定义聊天室创建和) 。 
  
8. 通过SQL **之** 一为持久聊天服务器后端 (定义聊天室内容) 存储位置：
    
   - 若要使用现有SQL Server，请在下拉列表中，单击SQL Server应用商店的名称。
    
   - 若要指定新的SQL Server数据库，请单击 **"** 新建 **"，在**"定义新的SQL存储"中，执行下列操作：
    
   - 在 **SQL Server FQDN** 中，指定要SQL Server数据库的 FQDN SQL Server数据库。
    
   - 选择“默认实例”以使用默认实例，或指定其他实例，选择“命名实例”，然后指定要使用的实例。
    
     > [!NOTE]
     > 若要详细了解如何配置备份数据库SQL Server进行灾难恢复，请参阅 [在 Skype for Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md)中为持久聊天服务器配置高可用性和灾难恢复。 
  
9. 如果启用了SQL Server，请定义合规性存储。
    
    > [!IMPORTANT]
    > 若要详细了解如何配置 SQL Server 镜像，以高可用性持久聊天服务器数据库和持久聊天服务器合规性数据库，请参阅在 [Skype for Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md)中为持久聊天服务器配置高可用性和灾难恢复。 
  
10. 定义文件存储。 文件存储是一个文件夹，其中存储了已上载到文件存储库的所有文件的副本（例如，存储已发布到聊天室的文件附件）。 对于多服务器持久聊天服务器拓扑，这必须是 UNC (通用命名) 约定;对于单服务器持久聊天服务器拓扑，它可以是本地文件路径。
    
    若要使用现有文件存储，请执行下列步骤：
    
    - 在 **文件服务器 FQDN** 中，指定要创建新文件存储计算机 FQDN。
    
    - 在“文件共享”中，指定要使用的文件存储。
    
      > [!IMPORTANT]
      > 您可以在创建文件存储之前在拓扑生成器中定义文件存储，但在发布拓扑之前，必须在定义的位置创建文件存储。 如果文件存储不存在，则发布拓扑的尝试将失败。 
  
11. 选择要用作此持久聊天服务器池的下一个跃点的前端服务器池。 这是能够将持久聊天服务器请求路由到此池的前端服务器池。
    
12. 若要保存配置，请单击“完成”。 持久聊天服务器池显示在拓扑生成器中，并附带特定的池设置。
    
    若要发布已更新的拓扑（已添加持久聊天服务器），请参阅"发布更新的拓扑"。
    
    > [!NOTE]
    > 在拓扑生成器已打开后，可以继续执行"发布更新的拓扑"中的步骤 3，以开始发布更新的拓扑。 
  
## <a name="publish-the-updated-topology"></a>发布更新的拓扑
<a name="BKMK_PublishTopology"> </a>

在拓扑生成器中更新拓扑后，必须先将拓扑发布到中央管理存储，然后才能配置和使用 Skype for Business Server。 数据的只读副本将复制到拓扑中的所有服务器，使所有服务器与拓扑和其他配置更改保持同步。
  
发布拓扑之前，请安装持久聊天服务器的数据库。 使用拓扑生成器通过选择"操作 **和安装数据库****"来安装数据库**。
  
1. 在运行 Skype for Business Server 或安装了 Skype for Business Server 管理工具的计算机上， 使用同时是 **Domain Admins** 组和 **RTCUniversalServerAdmins** 组的成员并且对文件存储具有完全控制权限的帐户登录 (读取、写入和修改要用于持久聊天服务器文件存储 (的) ，以便拓扑生成器可以配置所需的任意访问控制列表 (DACLs) ) 或具有同等用户权限的帐户。
    
2. 启动拓扑生成器。 如果 **在本地保存了本地文件，** 请选择"打开拓扑"。
    
3. 在控制台树中，右键单击 **Skype for Business Server 2015，** 然后单击"**发布拓扑"。**
    
4. 在“发布拓扑”页上，单击“下一步”。
    
5. 在“发布向导完成”页上，确认已成功发布拓扑，然后单击“完成”。
    

