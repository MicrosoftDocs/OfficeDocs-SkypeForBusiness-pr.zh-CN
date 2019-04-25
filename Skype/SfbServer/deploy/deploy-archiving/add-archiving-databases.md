---
title: 业务服务器添加到现有部署中 Skype 的存档数据库
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3b67df85-181d-45ca-ba48-bb74a439f242
description: 摘要： 阅读本主题可了解如何向您 Skype 业务服务器部署添加存档数据库。
ms.openlocfilehash: 083b6329cdf27331ba861b96a74f94e2ae5aa912
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32229458"
---
# <a name="add-archiving-databases-to-an-existing-deployment-in-skype-for-business-server"></a>业务服务器添加到现有部署中 Skype 的存档数据库
 
**摘要：** 阅读本主题可了解如何将存档数据库添加到您 Skype 业务服务器部署。
  
必须先在拓扑中纳入存档，然后才能配置您的部署以支持存档。 本主题中的信息介绍如何使用拓扑生成器以：
  
- 向拓扑添加存档数据库。
    
- 发布更新的拓扑以向您 Skype 业务服务器部署添加存档数据库。
    
> [!NOTE]
> 如果您想要使用 Microsoft Exchange 集成来部署中存储存档数据和 Exchange 服务器上的所有用户的文件，不指定**存档 SQL Server 存储**或**使用 SQL Server 存储镜像**的信息。
  
### <a name="add-an-archiving-database-to-your-topology"></a>向拓扑添加存档数据库

1. 业务服务器运行 Skype 的计算机上或在其上 Skype 的安装了 Business Server 管理工具，使用登录本地 Users 组 （或具有同等用户权限的帐户） 的成员的帐户。
    
2. 启动拓扑生成器。
    
3. 在控制台树中，导航到您要在其中部署存档的前端池，然后单击要在其中部署存档的前端池的名称。
    
4. 在“**操作**”菜单上，单击“**编辑属性**”。 
    
5. 在“**编辑属性**”对话框中，单击“**常规**”。
    
6. 向下滚动到“**存档**”。
    
7. 选中“**存档**”复选框。
    
8. 下**存档 SQL Server 存储，请**执行下列选项之一：
    
   - 若要使用现有 SQL Server 存储，请在下拉列表框中，单击要使用的 SQL Server 存储的名称。 如果您的所有用户都驻留在 Microsoft Exchange Server 2013 或上方，您可以存档 Skype 业务通信的所有用户在 Exchange。 在这种情况下，您无需配置 SQL Server 存档存储。
    
   - 若要指定新的 SQL Server 存储，请单击**新建**，然后在**定义新的 SQL Server 存储**对话框中，执行以下：
    
   - 在**SQL Server FQDN**中，指定要在其创建新的 SQL Server 存储的服务器的 FQDN。
    
   - 单击“**默认实例**”以使用默认的实例，或者，若要指定其他实例，请单击“**命名实例**”，然后指定要使用的实例。
    
   - 如果指定的 SQL Server 实例处于镜像关系中，选择**此 SQL 实例处于镜像关系中**复选框，然后，在**镜像端口号**框中，指定的端口号。
    
9. 如果您想要使用 SQL Server 存储镜像，选择**启用 SQL Server 存储镜像**，然后执行下列操作：
    
   - 若要将现有 SQL Server 存储用于镜像，请在**存档 SQL Server 存储镜像**下拉列表框中，单击您想要用于镜像的 SQL Server 存储的名称。
    
   - 若要指定新的 SQL Server 存储用于镜像，请单击**新建**，然后在**定义新的 SQL Server 存储**对话框中，执行下列选项之一：
    
     a. 在**SQL Server FQDN**中，指定要在其创建新的 SQL Server 存储的 SQL Server 的 FQDN。
    
     b. 单击“**默认实例**”以使用默认的实例，或者，若要指定其他实例，请单击“**命名实例**”，然后指定要使用的实例。
    
     c. 如果指定的 SQL Server 实例处于镜像关系中，选择**此 SQL 实例处于镜像关系中**复选框，然后，在**镜像端口号**框中，指定的端口号。
    
   - 如果您启用 SQL Server 镜像，并且想要包括 SQL Server 镜像见证 （的第三个单独 SQL Server 实例的可以检测到主 SQL Server 实例和镜像实例的运行状况），选择**使用 SQL Server 镜像见证启用自动故障转移**复选框，，然后执行下列选项之一：
    
     a. 在**SQL Server FQDN**中，指定要在其创建新的 SQL Server 镜像见证的服务器的 FQDN。
    
     b. 单击“**默认实例**”以使用默认的实例，或者，若要指定其他实例，请单击“**命名实例**”，然后指定要用于镜像见证的实例。
    
     c. 如果指定的 SQL Server 实例处于镜像关系中，选择**此 SQL 实例处于镜像关系中**复选框，然后，在**镜像端口号**框中，指定的端口号。
    
10. 若要保存配置，请单击“**确定**”。
    
### <a name="publish-the-updated-topology-to-add-an-archiving-database-to-your-deployment"></a>发布更新的拓扑以将存档数据库添加到部署

1. 业务服务器运行 Skype 的计算机上或在其上 Skype 的安装了 Business Server 管理工具，使用登录本地 Users 组 （或具有同等用户权限的帐户） 的成员的帐户。
    
    > [!NOTE]
    > 您可以使用本地用户组的成员的帐户定义拓扑，但要发布拓扑，需要将服务器添加到拓扑，必须使用**Domain Admins**组和**RTCUniversalServer 的成员的帐户Admins**组，并使用的业务服务器文件存储的 Skype （以便拓扑生成器可以配置所需的随机访问控制列表 (Dacl)，或一个文件共享上具有完全控制权限 （读取、 写入和修改）具有同等权限的帐户。
  
2. 打开您在上一节使用拓扑生成器中创建的拓扑。
    
3. 在控制台树中，右键单击**Skype 业务服务器**，，然后单击**发布拓扑**。
    
4. 在“**发布拓扑**”页上，单击“**下一步**”。
    
5. 在“**创建数据库**”页上，确认已经选择了数据库，然后单击“**下一步**”。 
    
    > [!NOTE]
    > 如果没有创建数据库所需的相应权限，则可以取消数据库的选择，并且具有相应权限的人可以创建数据库。 可以使用拓扑生成器安装 > 仅专用 SQL Server 数据库。 与其他服务器组件并置的 SQL Server 上的数据库必须通过在该计算机上运行本地安装程序进行安装。 
  
6. 在“**发布向导完成**”页上，确认已成功发布拓扑，然后单击“**完成**”。
    
    > [!IMPORTANT]
    > 发布拓扑后，必须配置存档选项和策略，然后才能存档任何内容。 有关详细信息，请参阅[配置存档选项 Skype 业务服务器](configure-archiving-options.md)和[配置存档策略的 Skype 业务服务器](configure-archiving-policies.md)。 
  

