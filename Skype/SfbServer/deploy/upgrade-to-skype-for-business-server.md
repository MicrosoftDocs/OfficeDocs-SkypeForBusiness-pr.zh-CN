---
title: 升级到 Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 7/14/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 74ce73bc-356b-4705-83b1-341ee010fd19
description: '摘要： 了解如何从 Lync Server 2013 升级到 Skype 的业务服务器 2015年。 有关从 Microsoft 评估中心的业务服务器 2015年下载免费试用版的 Skype: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server。'
ms.openlocfilehash: f3c451e0c1590daab2c6576964c1e1ce5ec3c4ec
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="upgrade-to-skype-for-business-server-2015"></a>升级到 Skype for Business Server 2015
 
**摘要：**了解如何从 Lync Server 2013 升级到 Skype 的业务服务器 2015年。 有关从[Microsoft 评估中心](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)业务服务器 2015年下载 Skype 的免费试用版。
  
本文档中使用过程从升级 Lync Server 2013 到 Skype 的业务服务器 2015年通过 Skype 业务服务器拓扑生成器和新在就地升级功能。 如果您想要从 Lync Server 2010 或办公室通信服务器 2007 R2 升级，请参阅[计划升级到业务服务器 2015年的 Skype](../plan-your-deployment/upgrade.md)。
  
## <a name="upgrade-from-lync-server-2013"></a>从 Lync Server 2013 升级

升级到 Skype 的 Lync Server 2013，业务服务器 2015年涉及安装必备软件，使用 Skype 业务服务器拓扑生成器要升级的数据库中该池，并使用 Skype 业务服务器的就地升级每个服务器与池相关联。 要完成升级，请执行此主题中的八个步骤。
  
### <a name="before-you-begin"></a>开始之前

- 查看[计划升级到业务服务器 2015年的 Skype](../plan-your-deployment/upgrade.md)。
    
- 查看[业务服务器 2015年的 Skype 的服务器要求](../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。
    
- [安装系统必备组件的业务服务器 2015 Skype](install/install-prerequisites.md) 。
    
- [安装 Skype 业务服务器 2015年](install/install.md)。
    
### <a name="step-1-install-administrator-tools-and-download-topology"></a>第 1 步：安装管理员工具并下载拓扑

1. 连接到不具有 Lync OCSCore 或安装任何其他 Lync 组件拓扑中的计算机。
    
2. 从 Skype 业务服务器 2015年安装媒体，从**OCS_Volume\Setup\AMD64**上运行**Setup.exe** 。 
    
3. 单击“**安装**”。 
    
4. 接受许可协议。
    
5. 在部署向导中，单击“**安装管理员工具**”，按照步骤进行安装。
    
     ![已调出“安装管理员工具”链接的“部署向导”屏幕截图。](../media/5bbac2d6-a5b3-42b4-a243-7bcf2b04477a.png)
  
6. 从 Windows 启动屏幕，打开业务服务器拓扑生成器 Skype。
    
7. 单击“**从现有部署下载拓扑**”，然后单击“**下一步**”。
    
8. 输入拓扑名称，然后单击“**保存**”。
    
9. 转到保存拓扑的位置，创建一个拓扑副本。
    
### <a name="step-2-upgrade-and-publish-topology-using-topology-builder"></a>第 2 步：使用拓扑生成器升级和发布拓扑

在开始升级过程之前，必须为您计划升级池运行所有服务。 这是为了保证拓扑更改复制到池中服务器的本地数据库。
  
> [!IMPORTANT]
>  在升级之前保存拓扑文件副本。 升级后，您将不能降级拓扑。 > 如果您的服务数据库，如持久聊天服务是持久聊天数据库所在的服务器上跳过此步骤，因为是在同一服务器上，请转到步骤 4。 停止服务后，请在每台服务器上运行就地升级安装以升级本地数据库。
  
> [!NOTE]
> 如果拓扑有镜像的后端数据库，那么在使用拓扑生成器**发布拓扑时**，您会看到主数据库和镜像数据库同时出现。发布拓扑时，请确保所有数据库都在主数据库上运行，同时只选择主数据库，而不是镜像数据库，否则，在发布拓扑后，您会看到警告。
  
选择以下选项来升级和业务服务器 2015年拓扑生成器使用 Skype 发布一个新拓扑结构之一。 在完成这些步骤并发布更新后的拓扑之后，转到本主题中的第 3 步。
  
#### <a name="option-1-upgrade-an-isolated-front-end-pool-and-associated-archiving-and-monitoring-stores"></a>选项 1：升级隔离的前端池和关联的存档与监控存储

如果您升级的池依赖于存档和监控存储，则在使用以下步骤时，存档和监控存储也会随之升级。
  
1. 拓扑生成器中右键单击 Lync Server 2013 池、 选择**升级到业务服务器 2015年的 Skype**，并执行的步骤。 
    
     ![包含升级选项的 Lync Server 2013 右键单击菜单屏幕截图。](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
2. 拓扑生成器中单击**操作** > **发布拓扑**或**操作** > **拓扑** > **发布**。 
    
     ![拓扑生成器中带“发布拓扑”选项的“操作”菜单屏幕截图。](../media/d6712634-9205-401f-a0b0-3ea096ca51bf.png)
  
3. 在发布期间，选择在存档和监控存储上安装数据库。
    
#### <a name="option-2-upgrade-front-end-pool-without-upgrading-archiving-and-monitoring-stores"></a>无需升级归档和监控存储选项 2： 升级前端池

如果您使用以下 步骤，选定池的存档和监控将被禁用。在升级之后，该池将不会有存档和监控存储。
  
1. 拓扑生成器中选择您想要升级的 Lync Server 2013 池。
    
2. 移除依赖项 Lync 2013 存档服务器和监视存储。 
    
   - 转到**操作** > **编辑属性**。
    
   - 清除“**存档**”复选框。
    
     ![“编辑属性”对话框上的“存档”复选框的屏幕截图。](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - 清除“**监控**”复选框。
    
     ![显示“监控”复选框的“编辑属性”对话框的屏幕截图。](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. 用鼠标右键单击 Lync Server 2013 池、 选择**升级到业务服务器 2015年的 Skype**，并按照步骤。 
    
     ![包含升级选项的 Lync Server 2013 右键单击菜单屏幕截图。](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. 拓扑生成器中单击**操作** > **发布拓扑**或**操作** > **拓扑** > **发布**。 
    
#### <a name="option-3-upgrade-front-end-pool-and-associated-it-to-new-skype-for-business-server-2015-archiving-and-monitoring-stores"></a>选项 3： 升级前端池和它与新 Skype 业务服务器 2015年归档和监视存储

如果使用以下步骤，存档和监控将在先前的存储中停止，并在您创建的新存储中启动。 
  
1. 拓扑生成器中选择您想要升级的 Lync Server 2013 池。 
    
2. 移除依赖项 Lync 2013 存档服务器和监视存储。 
    
   - 转到**操作** > **编辑属性**。
    
   - 清除“**存档**”复选框。
    
     ![“编辑属性”对话框上的“存档”复选框的屏幕截图。](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - 清除“**监控**”复选框。
    
     ![显示“监控”复选框的“编辑属性”对话框的屏幕截图。](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. 用鼠标右键单击 Lync Server 2013 池、 选择**升级到业务服务器 2015年的 Skype**，并按照步骤。 
    
     ![包含升级选项的 Lync Server 2013 右键单击菜单屏幕截图。](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. 为存档创建新的 SQL 存储。 
    
   - 选择池和**操作** > **编辑属性**。 
    
   -  选中“**存档**”复选框。
    
   - 单击“**新建**”。
    
     ![显示“存档”部分下的“新建”按钮的“编辑属性”对话框的屏幕截图。](../media/3a4a18e7-8251-4736-837c-2b486f64f896.png)
  
5. 为监控创建新的 SQL 存储。 
    
   - 选择池和**操作** > **编辑属性**。 
    
   -  选中“**监控**”复选框。
    
   - 单击“**新建**”。
    
     ![显示“监控”部分下的“新建”按钮的“编辑属性”对话框的屏幕截图。](../media/729c72a7-0068-4e0d-99dc-e480a6bfbf1d.png)
  
6. 拓扑生成器中单击**操作** > **发布拓扑**或**操作** > **拓扑** > **发布**。 
    
7. 在发布期间，选择在新的存档和监控存储上安装数据库。
    
### <a name="step-3-wait-for-replication"></a>第 3 步：等待复制

留些时间耐心等候复制，以便将更新后的拓扑发布到环境中的所有服务器。
  
### <a name="step-4-stop-all-services-in-pool-to-be-upgraded"></a>第 4 步：停用池中所有需要升级的服务

每个服务器上的服务于您要升级，请运行以下 cmdlet PowerShell 的池：
  
```
Disable-CsComputer -Scorch
```

我们建议使用禁用 CsComputer，因为您可能需要在原位升级过程中重新启动服务器。 如果您使用 Stop-CsWindowsService，一些服务可能会在重启后自动重新启动。 这可能导致就地升级失败。
  
### <a name="step-5-upgrade-front-end-pools-and-non-front-end-pool-servers"></a>第 5 步：升级前端池和非前端池服务器

> [!NOTE]
>  请升级安装所有新的 Skype 所需业务服务器 2015年必备的软件包括之前： > 至少 32 GB 的可用空间在尝试升级之前。 此外，还要确保驱动器是一个固定的本地驱动器，不连接 USB 或火线，用 NTFS 文件系统格式化、 没有压缩，并且不包含页文件。 > PowerShell 版本 6.2.9200.0 或更高版本。 > 最新 Lync Server 2013安装的累积更新。 > 安装 SQL Server 2012 SP1。 > 以下 KB （自动安装如果使用的 Microsoft 更新） 的安装： > Windows Server 2008 R2-[KB2533623](https://support.microsoft.com/kb/2533623)> Windows Server 2012-[KB2858668](https://support.microsoft.com/kb/2858668)> 窗口Server 2012 R2-[KB2982006](https://support.microsoft.com/kb/2982006)
  
使用适当升级每个服务器上更新的前端池、 边缘池、 中介服务器和持久聊天池。
  
1. 在每个服务器上，运行**Setup.exe** **OCS_Volume\Setup\amd64**从 Skype 业务服务器 2015年安装媒体。
    
2. 接受许可协议，并在适当升级为按照提示进行操作。
    
3. 在前端池和非-前端池中的每台服务器上的每台服务器重复上述步骤。
    
> [!NOTE]
> 系统可能会在就地升级期间提示您重启服务器。 这很正常。 重新启动后，在适当升级将继续从离开的位置。 
  
成功完成就地升级时，您将看到以下消息。
  
![显示就地升级成功完成的屏幕截图。](../media/2f52cb50-9bb4-4714-a982-9c7a0865f78a.png)
  
### <a name="step-6-restart-services-on-all-upgraded-servers"></a>第 6 步：在所有升级后的服务器上重启服务

> [!NOTE]
> 然后重新启动服务，请确保 %ProgramData%\WindowsFabric 在所有前端服务器上不存在。 如果存在，请在启动服务之前将其删除。 
  
- 升级前端池中所有服务器之后，重新启动服务，通过使用以下 PowerShell 命令： 
    
  ```
  Start-CsPool
  ```

    > [!NOTE]
    > 如果在开始运行就地升级之前已存在需要处理的系统重启，则就地升级不会在安装结束时要求您重新启动。在您尝试使用 Start-CSPool cmdlet 启动服务时，这会导致第一台前端服务器出现一些程序集异常。要解决这些错误，请重新启动池中的所有服务器并再次运行该 cmdlet。 
  
- 在非前端池服务器上，使用以下命令重启服务：
    
  ```
  Start-CsWindowsService
  ```

单击就地升级页面上的“**确定**”之后，您将看到提示您完成此步骤的以下信息。
  
![显示就地升级成功完成后的后续步骤的屏幕截图。](../media/6a7236b6-9ef9-4df3-8682-b0e4021810f9.png)
  
### <a name="step-7-verify-skype-for-business-functionality-works"></a>第 7 步： 验证 Skype 业务功能可以正常运行

若要确保升级成功，已升级的池，测试 Skype 的业务，以确保功能达到预期效果。 
  
### <a name="step-8-upgrade-secondary-pools"></a>第 8 步：升级辅助池

重复本主题中的步骤，升级您的环境中的其他任何池。
  
## <a name="troubleshoot-issues-with-the-in-place-upgrade"></a>对就地升级问题进行故障诊断

如果就地升级失败，您可能会看到如下图所示的消息。 
  
![显示由于未安装所需的累积更新而导致就地升级失败的屏幕截图。](../media/f84db06b-0841-45a9-870d-7ba4b5a463d5.png)
  
查看页面底部帮您进行疑难解答的完整消息。单击“**查看日志**”获得更多详细信息。
  
如果在就地升级失败上**验证升级准备情况**或 * * 安装缺少的系统必备组件 * *，请确保服务器有所有最新 Windows 服务器、 Lync 服务器和 SQL Server 更新应用，并且所有所需的软件和角色安装。 现在需要的列表，请参阅[安装系统必备组件的业务服务器 2015 Skype](install/install-prerequisites.md)和[业务服务器 2015年的 Skype 的服务器要求](../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。
  
## <a name="see-also"></a>另请参阅

#### 

[计划升级到 Skype 的业务服务器 2015](../plan-your-deployment/upgrade.md)
  
[业务服务器 2015 Skype 的的服务要求](../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[为业务服务器 2015年安装 Skype 的先决条件](install/install-prerequisites.md)
  
[为业务服务器 2015年安装 Skype](install/install.md)

