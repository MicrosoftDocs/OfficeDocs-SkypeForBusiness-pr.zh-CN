---
title: 将存档数据库添加到现有部署Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: quickstart
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 3b67df85-181d-45ca-ba48-bb74a439f242
description: 摘要：阅读本主题，了解如何将存档数据库添加到您的Skype for Business Server部署。
ms.openlocfilehash: 3bc4e14998e45803518436bb180906e9c79e14f4
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "62401576"
---
# <a name="add-archiving-databases-to-an-existing-deployment-in-skype-for-business-server"></a>将存档数据库添加到现有部署Skype for Business Server
 
**摘要：** 阅读本主题，了解如何将存档数据库添加到您的Skype for Business Server部署。
  
必须先在拓扑中纳入存档，然后才能配置您的部署以支持存档。 本主题中的信息说明如何使用拓扑生成器：
  
- 向拓扑中添加存档数据库。
    
- 发布更新的拓扑以将存档数据库添加到您的Skype for Business Server部署。
    
> [!NOTE]
> 如果要使用 Microsoft Exchange 集成在 Exchange 服务器上为部署中的所有用户存储存档数据和文件，请不要指定存档 **SQL Server** 存储或使用 **SQL Server Store** 镜像信息。
  
### <a name="add-an-archiving-database-to-your-topology"></a>向拓扑中添加存档数据库

1. 在运行 Skype for Business Server 或安装了 Skype for Business Server 管理工具的计算机上，使用作为本地 Users 组 (成员的帐户或具有同等用户权限) 的帐户登录。
    
2. 启动拓扑生成器。
    
3. 在控制台树中，导航到要部署存档的前端池，然后单击要部署存档的前端池的名称。
    
4. 在“操作”菜单上，单击“编辑属性”。 
    
5. 在“编辑属性”对话框中，单击“常规”。
    
6. 向下滚动到“存档”。
    
7. 选中“存档”复选框。
    
8. 在 **"SQL Server存储"下，** 执行下列操作之一：
    
   - 若要使用现有 SQL Server 存储，请在下拉列表框中，单击要使用的 SQL Server 存储的名称。 如果您的所有用户都位于 Microsoft Exchange Server 2013 或Microsoft Exchange Server，您可以在 Skype for Business 中为所有用户存档Exchange。 在这种情况下，无需配置存档SQL Server存档。
    
   - 若要指定新的SQL Server应用商店，请单击"新建"**，然后在**"定义新的SQL Server应用商店"对话框中，执行以下操作：
    
   - 在 **SQL Server FQDN** 中，指定要创建新的数据库存储SQL Server FQDN。
    
   - 单击“默认实例”以使用默认的实例，或者，若要指定其他实例，请单击“命名实例”，然后指定要使用的实例。
    
   - 如果指定的SQL Server实例位于镜像关系中，请选中"此 **SQL** 实例位于镜像关系中"复选框，然后在"镜像端口号"中指定端口号。
    
9. 如果要使用存储镜像SQL Server，请选择"启用SQL Server **存储镜像**"，然后执行以下操作：
    
   - 若要将现有 SQL Server 存储用于镜像，请在"存档 **SQL Server** 存储镜像"下拉列表框中，单击要用于镜像的 SQL Server 存储的名称。
    
   - 若要指定新的SQL Server存储进行镜像，请单击"新建"，然后在"定义新的 SQL Server **存储**"对话框中，执行下列操作之一：
    
     a. 在 **SQL Server FQDN** 中，指定要SQL Server存储的 FQDN。SQL Server FQDN。
    
     b. 单击“默认实例”以使用默认的实例，或者，若要指定其他实例，请单击“命名实例”，然后指定要使用的实例。
    
     c. 如果指定的SQL Server实例位于镜像关系中，请选中"此 **SQL** 实例位于镜像关系中"复选框，然后在"镜像端口号"中指定端口号。
    
   - 如果启用 SQL Server 镜像，并且希望包括一个 SQL Server 镜像见证 (第三个单独的 SQL Server 实例，该实例可以检测主 SQL Server 和镜像实例) 的运行状况，请选择"使用 **SQL Server** 镜像见证启用自动故障转移" 复选框，然后执行下列操作之一：
    
     a. 在 **SQL Server FQDN** 中，指定要创建新数据库的服务器的 FQDN SQL Server见证。
    
     b. 单击“默认实例”以使用默认的实例，或者，若要指定其他实例，请单击“命名实例”，然后指定要用于镜像见证的实例。
    
     c. 如果指定的SQL Server实例位于镜像关系中，请选中"此 **SQL** 实例位于镜像关系中"复选框，然后在"镜像端口号"中指定端口号。
    
10. 若要保存配置，请单击“确定”。
    
### <a name="publish-the-updated-topology-to-add-an-archiving-database-to-your-deployment"></a>发布更新的拓扑以向部署中添加存档数据库

1. 在运行 Skype for Business Server 或安装了 Skype for Business Server 管理工具的计算机上，使用作为本地 Users 组 (成员的帐户或具有同等用户权限) 的帐户登录。
    
    > [!NOTE]
    > 您可以使用作为本地 Users 组的成员的帐户来定义拓扑，但若要发布拓扑（向拓扑中添加服务器是必需的）必须使用 Domain **Admins** 组和 **RTCUniversalServerAdmins** 组的成员且具有完全控制权限的帐户 (读取、 在用于 Skype for Business Server 文件存储 (的文件共享上写入和修改) ，以便拓扑生成器可以配置所需的任意访问控制列表 (DACLs) 或具有同等权限的帐户。
  
2. 使用拓扑生成器打开在上一部分中创建的拓扑。
    
3. 在控制台树中，**右键单击**"Skype for Business Server"，然后单击"发布 **拓扑"**。
    
4. 在“发布拓扑”页上，单击“下一步”。
    
5. 在“创建数据库”页上，确认已经选择了数据库，然后单击“下一步”。 
    
    > [!NOTE]
    > 如果没有创建数据库所需的相应权限，则可以取消数据库的选择，并且具有相应权限的人可以创建数据库。 >拓扑生成器SQL专用服务器中的数据库。 与其他服务器组件并置的 SQL Server 上的数据库必须通过在该计算机上运行本地安装程序进行安装。 
  
6. 在 **“发布向导完成”** 页上，确认已成功发布拓扑，然后单击 **“完成”**。
    
    > [!IMPORTANT]
    > 发布拓扑后，必须配置存档选项和策略，然后才能存档任何内容。 有关详细信息，请参阅 Configure [archiving options for Skype for Business Server](configure-archiving-options.md)和 [Configure archiving policies for Skype for Business Server](configure-archiving-policies.md)。 
  

