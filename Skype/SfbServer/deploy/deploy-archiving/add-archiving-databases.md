---
title: 在 Skype for Business Server 2015 中将存档数据库添加到现有部署
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3b67df85-181d-45ca-ba48-bb74a439f242
description: 摘要： 阅读本主题，了解如何添加到您的业务服务器 2015年部署 Skype 的存档数据库。
ms.openlocfilehash: 09185eed2a8bd0cc9b2a03fc6361abeadbd01829
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="add-archiving-databases-to-an-existing-deployment-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中将存档数据库添加到现有部署
 
**摘要：**阅读本主题，了解如何添加到您的业务服务器 2015年部署 Skype 的存档数据库。
  
必须先在拓扑中纳入存档，然后才能配置您的部署以支持存档。 本主题中的信息介绍如何使用到拓扑生成器：
  
- 向拓扑添加存档数据库。
    
- 发布更新拓扑结构中，将添加到您的业务服务器 2015年部署 Skype 存档数据库。
    
> [!NOTE]
> 如果您想要使用 Microsoft Exchange 集成在您的部署中存储存档数据和所有用户的 Exchange 服务器上的文件，则不需要指定**存档的 SQL Server 存储**或**使用 SQL Server 存储镜像**信息。
  
### <a name="add-an-archiving-database-to-your-topology"></a>向拓扑添加存档数据库

1. 运行 Skype 业务服务器的计算机上或在其上 Skype 的安装业务服务器管理工具，使用登录的帐户是本地用户组 （或具有相当的用户权限的帐户） 的成员。
    
2. 启动拓扑生成器。
    
3. 在控制台树中，导航到您要在其中部署存档的前端池，然后单击要在其中部署存档的前端池的名称。
    
4. 在“**操作**”菜单上，单击“**编辑属性**”。 
    
5. 在“**编辑属性**”对话框中，单击“**常规**”。
    
6. 向下滚动到“**存档**”。
    
7. 选中“**存档**”复选框。
    
8. **存档的 SQL Server 存储区**下, 执行以下任一操作：
    
   - 若要使用现有 SQL Server 存储，请在下拉列表框中，单击要使用的 SQL Server 存储的名称。 如果 Microsoft Exchange Server 2013年或以上托管您的所有用户，您可以存档 Skype 业务交流所有用户在 Exchange。 在这种情况下，您不需要配置 SQL Server 存档存储。
    
   - 若要指定新的 SQL Server 存储，单击**新建**，然后在**定义新建 SQL Server 存储**对话框中，执行下列：
    
   - 在**SQL Server FQDN**，指定您要在其创建新的 SQL Server 存储的服务器的 FQDN。
    
   - 单击“**默认实例**”以使用默认的实例，或者，若要指定其他实例，请单击“**命名实例**”，然后指定要使用的实例。
    
   - 如果指定的 SQL Server 实例处于镜像关系，选择**此 SQL 实例处于镜像关系**复选框，然后在**镜像端口编号**，指定的端口号。
    
9. 如果您想要使用 SQL Server 存储镜像，选择**启用 SQL Server 存储镜像**，然后请执行下列操作：
    
   - 要用于现有的 SQL Server 存储镜像中**存档的 SQL Server 存储镜像**下拉列表框中，单击想要使用镜像的 SQL Server 存储的名称。
    
   - 若要指定新的 SQL Server 存储镜像，单击**新建**，然后在**定义新建 SQL Server 存储**对话框中，执行以下任一项：
    
    a. 在**SQL Server FQDN**，指定您要在其创建新的 SQL Server 存储 SQL Server 的 FQDN。
    
    b. 单击“**默认实例**”以使用默认的实例，或者，若要指定其他实例，请单击“**命名实例**”，然后指定要使用的实例。
    
    c. 如果指定的 SQL Server 实例处于镜像关系，选择**此 SQL 实例处于镜像关系**复选框，然后在**镜像端口编号**，指定的端口号。
    
   - 如果启用 SQL Server 镜像并希望包含镜像见证 （的第三个独立 SQL Server 实例可以检测到主 SQL Server 实例和镜像实例的运行状况） 的 SQL Server 时，选择以启用自动**使用 SQL Server 镜像见证故障切换**复选框，然后再执行下列操作之一：
    
    a. 在**SQL Server FQDN**，指定您要在其创建镜像见证新的 SQL Server 的服务器的 FQDN。
    
    b. 单击“**默认实例**”以使用默认的实例，或者，若要指定其他实例，请单击“**命名实例**”，然后指定要用于镜像见证的实例。
    
    c. 如果指定的 SQL Server 实例处于镜像关系，选择**此 SQL 实例处于镜像关系**复选框，然后在**镜像端口编号**，指定的端口号。
    
10. 若要保存配置，请单击“**确定**”。
    
### <a name="publish-the-updated-topology-to-add-an-archiving-database-to-your-deployment"></a>发布更新的拓扑以将存档数据库添加到部署

1. 运行 Skype 业务服务器的计算机上或在其上 Skype 的安装业务服务器管理工具，使用登录的帐户是本地用户组 （或具有相当的用户权限的帐户） 的成员。
    
    > [!NOTE]
    > 您可以通过使用本地用户组的成员帐户定义拓扑，但若要发布一个拓扑结构，需要将服务器添加到拓扑结构中，则必须使用的帐户是**域管理员**组和**RTCUniversalServer 的成员管理员**组中，并且使用的业务服务器文件存储的 Skype （这样拓扑生成器可以配置所需的自由访问控制列表 (Dacl)，或一个文件共享具有完全控制权限 （读取、 写入和修改）具有同等权限的帐户。
  
2. 打开您在上一节使用拓扑生成器中创建的拓扑。
    
3. 在控制台树中， **Skype 业务服务器**，右键单击，然后单击**发布拓扑**。
    
4. 在“**发布拓扑**”页上，单击“**下一步**”。
    
5. 在“**创建数据库**”页上，确认已经选择了数据库，然后单击“**下一步**”。 
    
    > [!NOTE]
    > 如果没有创建数据库所需的相应权限，则可以取消数据库的选择，并且具有相应权限的人可以创建数据库。 > 可以通过使用拓扑生成器安装只有在专用的 SQL 服务器上的数据库。 与其他服务器组件并置的 SQL Server 上的数据库必须通过在该计算机上运行本地安装程序进行安装。 
  
6. 在“**发布向导完成**”页上，确认已成功发布拓扑，然后单击“**完成**”。
    
    > [!IMPORTANT]
    > 发布拓扑后，必须配置存档选项和策略，然后才能存档任何内容。 有关详细信息，请参阅[配置归档业务服务器 2015年的 Skype 的选项](configure-archiving-options.md)和[配置归档业务服务器 2015年的 Skype 的策略](configure-archiving-policies.md)。 
  

