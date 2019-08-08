---
title: 将存档数据库添加到 Skype for Business 服务器中的现有部署
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3b67df85-181d-45ca-ba48-bb74a439f242
description: '摘要: 阅读本主题, 了解如何将存档数据库添加到 Skype for Business 服务器部署。'
ms.openlocfilehash: b7d429206e003042922b9b9cae6de420fdf517bb
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234373"
---
# <a name="add-archiving-databases-to-an-existing-deployment-in-skype-for-business-server"></a>将存档数据库添加到 Skype for Business 服务器中的现有部署
 
**摘要:** 阅读本主题, 了解如何将存档数据库添加到 Skype for Business 服务器部署。
  
必须先在拓扑中纳入存档，然后才能配置您的部署以支持存档。 本主题中的信息介绍了如何使用拓扑生成器执行以下操作:
  
- 向拓扑添加存档数据库。
    
- 发布更新后的拓扑, 将存档数据库添加到 Skype for Business 服务器部署。
    
> [!NOTE]
> 如果你想要使用 Microsoft Exchange 集成在 Exchange server 上为你的部署中的所有用户存储存档数据和文件, 请不要指定**存档 SQL server 存储**或**使用 Sql Server 应用商店镜像**信息。
  
### <a name="add-an-archiving-database-to-your-topology"></a>向拓扑添加存档数据库

1. 在运行 Skype for Business 服务器或安装了 Skype for business 服务器管理工具的计算机上, 使用属于本地 Users 组的成员的帐户 (或具有等效用户权限的帐户) 登录。
    
2. 启动拓扑生成器。
    
3. 在控制台树中，导航到您要在其中部署存档的前端池，然后单击要在其中部署存档的前端池的名称。
    
4. 在“**操作**”菜单上，单击“**编辑属性**”。 
    
5. 在“**编辑属性**”对话框中，单击“**常规**”。
    
6. 向下滚动到“**存档**”。
    
7. 选中“**存档**”复选框。
    
8. 在 "**存档 SQL Server 应用商店" 下,** 执行下列操作之一:
    
   - 若要使用现有 SQL Server 存储，请在下拉列表框中，单击要使用的 SQL Server 存储的名称。 如果你的所有用户都托管在 Microsoft Exchange Server 2013 或更高版本上, 你可以将 Exchange 中的所有用户的 Skype for Business 通信存档。 在这种情况下, 你无需配置 SQL Server 存档存储。
    
   - 若要指定新的 SQL Server 应用商店, 请单击 "**新建**", 然后在 "**定义新的 SQL server 存储**" 对话框中, 执行下列操作:
    
   - 在**SQL SERVER FQDN**中, 指定要在其上创建新的 SQL Server 应用商店的服务器的 FQDN。
    
   - 单击“**默认实例**”以使用默认的实例，或者，若要指定其他实例，请单击“**命名实例**”，然后指定要使用的实例。
    
   - 如果指定的 SQL Server 实例位于镜像关系中, 请选中 "**此 sql 实例处于镜像关系中**" 复选框, 然后在 "**镜像端口号**" 中指定端口号。
    
9. 如果要使用 SQL Server 应用商店镜像, 请选择 "**启用 Sql Server 应用商店镜像**", 然后执行下列操作:
    
   - 若要使用现有的 SQL Server 应用商店进行镜像, 请在 "**存档 Sql server 存储镜像**" 下拉列表框中, 单击要用于镜像的 SQL server 应用商店的名称。
    
   - 若要为镜像指定新的 SQL Server 存储, 请单击 "**新建**", 然后在 "**定义新的 SQL server 存储**" 对话框中, 执行下列操作之一:
    
     a. 在**SQL SERVER FQDN**中, 指定要在其上创建新的 sql server 应用商店的 sql SERVER 的 FQDN。
    
     b. 单击“**默认实例**”以使用默认的实例，或者，若要指定其他实例，请单击“**命名实例**”，然后指定要使用的实例。
    
     c. 如果指定的 SQL Server 实例位于镜像关系中, 请选中 "**此 sql 实例处于镜像关系中**" 复选框, 然后在 "**镜像端口号**" 中指定端口号。
    
   - 如果启用 SQL Server 镜像, 并且希望包括 SQL Server 镜像见证 (第三个单独的 SQL Server 实例, 可检测主 SQL Server 和镜像实例的运行状况), 请选择 "**使用 SQL Server 镜像见证" 以启用自动"故障转移**" 复选框, 然后执行下列操作之一:
    
     a. 在**SQL SERVER FQDN**中, 指定要在其上创建新的 SQL Server 镜像见证的服务器的 FQDN。
    
     b. 单击“**默认实例**”以使用默认的实例，或者，若要指定其他实例，请单击“**命名实例**”，然后指定要用于镜像见证的实例。
    
     c. 如果指定的 SQL Server 实例位于镜像关系中, 请选中 "**此 sql 实例处于镜像关系中**" 复选框, 然后在 "**镜像端口号**" 中指定端口号。
    
10. 若要保存配置，请单击“**确定**”。
    
### <a name="publish-the-updated-topology-to-add-an-archiving-database-to-your-deployment"></a>发布更新的拓扑以将存档数据库添加到部署

1. 在运行 Skype for Business 服务器或安装了 Skype for business 服务器管理工具的计算机上, 使用属于本地 Users 组的成员 (或具有等效用户权限的帐户) 登录。
    
    > [!NOTE]
    > 你可以通过使用属于本地用户组的成员的帐户定义拓扑, 但要发布将服务器添加到拓扑所需的拓扑, 你必须使用**域管理员**组和 RTCUniversalServer 的成员帐户。 **管理员**组, 并且具有对 Skype for Business Server 文件存储所使用的文件共享的完全控制权限 (读取、写入和修改) (以便拓扑生成器可以配置所需的随机访问控制列表 (dacl) 或具有同等权利的帐户。
  
2. 使用拓扑生成器打开在上一节中创建的拓扑。
    
3. 在控制台树中, 右键单击 " **Skype For Business 服务器**", 然后单击 "**发布拓扑**"。
    
4. 在“**发布拓扑**”页上，单击“**下一步**”。
    
5. 在“**创建数据库**”页上，确认已经选择了数据库，然后单击“**下一步**”。 
    
    > [!NOTE]
    > 如果没有创建数据库所需的相应权限，则可以取消数据库的选择，并且具有相应权限的人可以创建数据库。 > 只有专用 SQL Server 上的数据库才能使用拓扑生成器进行安装。 与其他服务器组件并置的 SQL Server 上的数据库必须通过在该计算机上运行本地安装程序进行安装。 
  
6. 在“**发布向导完成**”页上，确认已成功发布拓扑，然后单击“**完成**”。
    
    > [!IMPORTANT]
    > 发布拓扑后，必须配置存档选项和策略，然后才能存档任何内容。 有关详细信息, 请参阅[配置 skype for Business 服务器的存档选项](configure-archiving-options.md)和[配置 Skype for business 服务器的存档策略](configure-archiving-policies.md)。 
  

