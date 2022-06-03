---
title: 升级到 2015 Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/14/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 74ce73bc-356b-4705-83b1-341ee010fd19
description: 摘要：了解如何从 Lync Server 2013 升级到 2015 Skype for Business Server。
ms.openlocfilehash: 30cd73e8c21c9ee60521e1c2bddf8bddf4d23b6f
ms.sourcegitcommit: e99471689ff60f9ab1095bc075f8b4c5569c9634
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/02/2022
ms.locfileid: "65860563"
---
# <a name="upgrade-to-skype-for-business-server-2015"></a>升级到 2015 Skype for Business Server
 
**总结：** 了解如何从 Lync Server 2013 升级到 2015 Skype for Business Server。 
  
使用本文档中的过程，使用Skype for Business Server拓扑生成器和新的In-Place升级功能从 Lync Server 2013 升级到 2015 Skype for Business Server。 如果要从 Lync Server 2010 或 Office Communications Server 2007 R2 升级，请参阅[计划升级到 2015 Skype for Business Server](../plan-your-deployment/upgrade.md)。

> [!NOTE]
> 就地升级在 2015 Skype for Business Server提供，但在 2019 Skype for Business Server不再受支持。 支持并行共存，有关详细信息，请参阅[迁移到 Skype for Business Server 2019](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md)。
  
## <a name="upgrade-from-lync-server-2013"></a>从 Lync Server 2013 升级

将 Lync Server 2013 升级到 Skype for Business Server 2015 涉及安装必备软件、使用Skype for Business Server拓扑生成器升级池中的数据库，以及对与之关联的每个服务器使用Skype for Business Server In-Place升级池。 若要完成升级，请完成本主题中的八个步骤。
  
### <a name="before-you-begin"></a>准备工作

- 查看[要升级到 2015 Skype for Business Server的计划](../plan-your-deployment/upgrade.md)。
    
- 查看 [Skype for Business Server 2015 的服务器要求](../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。
    
- [安装 2015 Skype for Business Server先决条件](install/install-prerequisites.md)。
    
- [安装Skype for Business Server 2015](install/install.md)。
    
### <a name="step-1-install-administrator-tools-and-download-topology"></a>步骤 1：安装管理员工具并下载拓扑

1. 连接到未安装 Lync OCSCore 或任何其他 Lync 组件的拓扑中的计算机。
    
2. 从 Skype for Business Server 2015 安装介质中，从 **OCS_Volume\Setup\AMD64 运行Setup.exe**。**** 
    
3. 单击“**安装**”。 
    
4. 接受许可协议。
    
5. 在部署向导中，单击 **“安装管理员工具**”，然后按照步骤进行安装。
    
     ![“部署向导”的屏幕截图，其中包含“安装管理员工具”的链接。](../media/5bbac2d6-a5b3-42b4-a243-7bcf2b04477a.png)
  
6. 从Windows "开始"屏幕打开Skype for Business Server拓扑生成器。
    
7. 单击 **现有部署中的“下载拓扑**”，然后单击 **“下一步**”。
    
8. 输入拓扑的名称，然后单击 **“保存**”。
    
9. 转到保存拓扑的位置，并创建拓扑的副本。
    
### <a name="step-2-upgrade-and-publish-topology-using-topology-builder"></a>步骤 2：使用拓扑生成器升级和发布拓扑

在开始升级过程之前，必须为计划升级的池运行所有服务。 因此，拓扑更改将复制到池中服务器的本地数据库。
  
> [!IMPORTANT]
>  升级前保存拓扑文件的副本。 升级后，将无法降级拓扑。>如果服务与数据库位于同一服务器上，例如持久聊天服务与持久聊天数据库位于同一服务器上，请跳过此步骤，然后转到步骤 4。 停止服务后，在每个服务器上运行In-Place升级设置以升级本地数据库。
  
> [!NOTE]
> 如果拓扑具有镜像的后端数据库，则使用拓扑生成器 **发布拓扑时** ，将同时显示主体数据库和镜像数据库。 请确保所有数据库都在主体上运行，并且在发布拓扑时仅选择主体而不是镜像，否则发布拓扑后会看到警告。
  
选择以下选项之一，使用 Skype for Business Server 2015 拓扑生成器升级和发布新拓扑。 完成步骤并发布更新后的拓扑后，请转到本主题中的步骤 3。
  
#### <a name="option-1-upgrade-an-isolated-front-end-pool-and-associated-archiving-and-monitoring-stores"></a>选项 1：升级隔离的前端池和关联的存档和监视存储

如果要升级的池具有存档和监视存储依赖项，则使用以下步骤时，也会升级存档和监视存储。
  
1. 在拓扑生成器中，右键单击 Lync Server 2013 池，选择 **“升级到 2015 Skype for Business Server**”，然后按照步骤操作。 
    
     ![右键单击菜单的屏幕截图，其中包含 Lync Server 2013 的升级选项。](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
2. 在拓扑生成器中，单击 **“操作** > **发布拓扑** ”或 **“操作** > **拓扑** > **发布**”。 
    
     ![拓扑生成器中具有“发布拓扑”选项的“操作”菜单的屏幕截图。](../media/d6712634-9205-401f-a0b0-3ea096ca51bf.png)
  
3. 在发布期间，选择在存档和监视存储上安装数据库。
    
#### <a name="option-2-upgrade-front-end-pool-without-upgrading-archiving-and-monitoring-stores"></a>选项 2：升级前端池而不升级存档和监视存储

如果使用以下步骤，则禁用所选池的存档和监视。 升级后，池将没有存档和监视存储。
  
1. 在拓扑生成器中，选择要升级的 Lync Server 2013 池。
    
2. 删除 Lync Server 2013 存档和监视存储的依赖项。 
    
   - 转到 **“操作** > **编辑”属性**。
    
   - 清除 **存档** 复选框。
    
     ![“编辑属性”对话框上的“存档”复选框的屏幕截图。](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - 清除“ **监视”** 复选框。
    
     ![显示“监视”复选框的“编辑属性”对话框的屏幕截图。](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. 右键单击 Lync Server 2013 池，选择 **“升级到 2015 Skype for Business Server**”，然后按照步骤操作。 
    
     ![右键单击菜单的屏幕截图，其中包含 Lync Server 2013 的升级选项。](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. 在拓扑生成器中，单击 **“操作** > **发布拓扑** ”或 **“操作** > **拓扑** > **发布**”。 
    
#### <a name="option-3-upgrade-front-end-pool-and-associated-it-to-new-skype-for-business-server-2015-archiving-and-monitoring-stores"></a>选项 3：升级前端池并将其关联到新的 Skype for Business Server 2015 存档和监视存储

如果使用以下步骤，存档和监视将停止在上一个存储中，并从你创建的新存储开始。 
  
1. 在拓扑生成器中，选择要升级的 Lync Server 2013 池。 
    
2. 删除 Lync Server 2013 存档和监视存储的依赖项。 
    
   - 转到 **“操作** > **编辑”属性**。
    
   - 清除 **存档** 复选框。
    
     ![“编辑属性”对话框上的“存档”复选框的屏幕截图。](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - 清除“ **监视”** 复选框。
    
     ![显示“监视”复选框的“编辑属性”对话框的屏幕截图。](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. 右键单击 Lync Server 2013 池，选择 **“升级到 2015 Skype for Business Server**”，然后按照步骤操作。 
    
     ![右键单击菜单的屏幕截图，其中包含 Lync Server 2013 的升级选项。](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. 为存档创建新的SQL存储。 
    
   - 选择池和 **操作** > **编辑属性**。 
    
   -  选中“存档”复选框。
    
   - 单击"新建"。
    
     ![“编辑属性”对话框的屏幕截图，其中显示了“存档”部分下的“新建”按钮。](../media/3a4a18e7-8251-4736-837c-2b486f64f896.png)
  
5. 创建用于监视的新SQL存储。 
    
   - 选择池和 **操作** > **编辑属性**。 
    
   -  选中 **“监视”** 复选框。
    
   - 单击"新建"。
    
     ![“编辑属性”对话框的屏幕截图，其中显示了“监视”部分下的“新建”按钮。](../media/729c72a7-0068-4e0d-99dc-e480a6bfbf1d.png)
  
6. 在拓扑生成器中，单击 **“操作** > **发布拓扑** ”或 **“操作** > **拓扑** > **发布**”。 
    
7. 在发布期间，选择在新的存档和监视存储上安装数据库。
    
### <a name="step-3-wait-for-replication"></a>步骤 3：等待复制

给复制一些时间，将更新后的拓扑发布到环境中的所有服务器。
  
### <a name="step-4-stop-all-services-in-pool-to-be-upgraded"></a>步骤 4：停止池中要升级的所有服务

在为要升级的池提供服务的每个服务器上，在 PowerShell 中运行以下 cmdlet：
  
```powershell
Disable-CsComputer -Scorch
```

建议使用Disable-CsComputer，因为可能需要在In-Place升级过程中重新启动服务器。 如果使用 Stop-CsWindowsService，某些服务可能会在重新启动后自动重启。 这可能会导致In-Place升级失败。
  
### <a name="step-5-upgrade-front-end-pools-and-non-front-end-pool-servers"></a>步骤 5：升级前端池和非前端池服务器

> [!NOTE]
>  升级前，请安装 2015 Skype for Business Server所需的所有新先决条件，其中包括：>尝试升级前至少 32GB 的可用空间。 此外，请确保驱动器是固定的本地驱动器，未由 USB 或 Firewire 连接， 使用 NTFS 文件系统设置格式，未压缩，且不包含页面文件.> PowerShell 版本 6.2.9200.0 或更高版本。>已安装的最新 Lync Server 2013 累积更新。已安装> SQL Server 2012 SP1。>使用 Microsoft Update) 自动安装以下 KB 安装 (：> Windows服务器 2008 R2 -[KB2533623](https://support.microsoft.com/kb/2533623)> Windows Server 2012 -[KB2858668](https://support.microsoft.com/kb/2858668)> Windows Server 2012 R2 -[KB2982006](https://support.microsoft.com/kb/2982006)
  
在每个服务器上使用In-Place升级来更新前端池、边缘池、中介服务器和持久聊天池。
  
1. 在每台服务器上，在 **Skype for Business Server** 2015 安装介质上从 **OCS_Volume\Setup\amd64** 运行Setup.exe。
    
2. 接受许可协议，并按照In-Place升级的提示操作。
    
3. 对前端池和每个非前端池服务器上的每个服务器重复这些步骤。
    
> [!NOTE]
> 可能会提示你在In-Place升级期间重新启动服务器。 没关系。 重新启动后，In-Place升级将继续从它离开的位置开始。 
  
成功完成In-Place升级后，会看到以下消息。
  
![显示已成功完成就地升级的屏幕截图。](../media/2f52cb50-9bb4-4714-a982-9c7a0865f78a.png)
  
### <a name="step-6-restart-services-on-all-upgraded-servers"></a>步骤 6：在所有升级的服务器上重启服务

> [!NOTE]
> 在重启服务之前，请确保 %ProgramData%\WindowsFabric 在所有前端服务器上不存在。 如果存在，请在启动服务之前将其删除。 
  
- 升级前端池中的所有服务器后，请使用以下 PowerShell 命令重启服务： 
    
  ```powershell
  Start-CsPool
  ```

    > [!NOTE]
    > 如果在开始运行In-Place升级之前已经需要挂起系统重启，则In-Place升级不会要求你在安装结束时重新启动。 这将导致在尝试使用 Start-CSPool cmdlet 启动服务时，针对第一个前端服务器引发一些程序集异常。 若要解决这些错误，请重启池中的所有服务器，然后再次运行 cmdlet。 
  
- 在非前端池服务器上，使用以下命令重启服务：
    
  ```powershell
  Start-CsWindowsService
  ```

单击“In-Place升级”页上的“ **确定** ”后，将看到以下提醒以完成此步骤。
  
![屏幕截图显示就地升级成功完成后的后续步骤。](../media/6a7236b6-9ef9-4df3-8682-b0e4021810f9.png)
  
### <a name="step-7-verify-skype-for-business-functionality-works"></a>步骤 7：验证Skype for Business功能是否有效

为了确保升级成功，对于已升级的池，请测试Skype for Business以确保功能按预期工作。 
  
### <a name="step-8-upgrade-secondary-pools"></a>步骤 8：升级辅助池

重复本主题中的步骤，升级环境中的任何其他池。
  
## <a name="troubleshoot-issues-with-the-in-place-upgrade"></a>排查In-Place升级问题

如果In-Place升级失败，可能会看到类似于下图中的消息。 
  
![屏幕截图显示，由于未安装所需的累积更新，就地升级失败。](../media/f84db06b-0841-45a9-870d-7ba4b5a463d5.png)
  
查看页面底部的完整消息，帮助你解决问题。 单击 **“查看日志** ”以获取更多详细信息。
  
如果In-Place升级在 **验证升级就绪性** 或 **安装缺少先决条件** 时失败，请确保服务器已应用所有最新的Windows服务器、Lync Server 和SQL Server更新，并安装所有必需的软件和角色。 有关所需内容的列表，请参阅 [Skype for Business Server 2015 的服务器要求](../plan-your-deployment/requirements-for-your-environment/server-requirements.md)和 [2015 Skype for Business Server安装先决条件](install/install-prerequisites.md)。
  
## <a name="see-also"></a>另请参阅

[计划升级到 2015 Skype for Business Server](../plan-your-deployment/upgrade.md)
  
[Skype for Business Server 2015 的服务器要求](../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[安装 Skype for Business Server 2015 的先决条件](install/install-prerequisites.md)
  
[安装Skype for Business Server 2015](install/install.md)
