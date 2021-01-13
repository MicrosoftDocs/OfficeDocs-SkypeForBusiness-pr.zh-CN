---
title: 升级到 Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/14/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 74ce73bc-356b-4705-83b1-341ee010fd19
description: 摘要：了解如何从 Lync Server 2013 升级到 Skype for Business Server 2015。 从 Microsoft 评估中心下载 Skype for Business Server 2015 的免费试用版 https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server ：.
ms.openlocfilehash: cda83d03db697a0adf404af4f6fe6e350abf6b58
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820422"
---
# <a name="upgrade-to-skype-for-business-server-2015"></a>升级到 Skype for Business Server 2015
 
**摘要：** 了解如何从 Lync Server 2013 升级到 Skype for Business Server 2015。 从 Microsoft 评估中心下载 Skype for Business Server 2015  [的免费试用版](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)。
  
使用本文档中的过程，通过使用 Skype for Business Server 拓扑生成器和新的 In-Place 升级功能，从 Lync Server 2013 升级到 Skype for Business Server 2015。 如果要从 Lync Server 2010 或 Office Communications Server 2007 R2 升级，请参阅"规划升级到[Skype for Business Server 2015"。](../plan-your-deployment/upgrade.md)

> [!NOTE]
> 就地升级在 Skype for Business Server 2015 中可用，但在 Skype for Business Server 2019 中不再受支持。 支持并行共存，有关详细信息，请参阅迁移到[Skype for Business Server 2019。](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md)
  
## <a name="upgrade-from-lync-server-2013"></a>从 Lync Server 2013 升级

将 Lync Server 2013 升级到 Skype for Business Server 2015 涉及安装必备软件、使用 Skype for Business Server 拓扑生成器升级池中的数据库，以及在每个与池关联的服务器上使用 Skype for Business Server In-Place 升级。 若要完成升级，请执行本主题中的八个步骤。
  
### <a name="before-you-begin"></a>准备工作

- 查看 [升级到 Skype for Business Server 2015 的计划](../plan-your-deployment/upgrade.md)。
    
- 查看 [Skype for Business Server 2015 的服务器要求](../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。
    
- [安装 Skype for Business Server 2015 的先决条件](install/install-prerequisites.md) 。
    
- [安装 Skype for Business Server 2015](install/install.md) 。
    
### <a name="step-1-install-administrator-tools-and-download-topology"></a>步骤 1：安装管理员工具和下载拓扑

1. 连接到拓扑中未安装 Lync OCSCore 或其他任何 Lync 组件的计算机。
    
2. 从 Skype for Business Server 2015 安装媒体中，Setup.exe **OCS_Volume\Setup\AMD64 运行**。  
    
3. 单击“**安装**”。 
    
4. 接受许可协议。
    
5. 在部署向导中， **单击"安装管理员工具**"，然后按照安装步骤操作。
    
     ![部署向导的屏幕截图，其中链接指向已调用的安装管理员工具。](../media/5bbac2d6-a5b3-42b4-a243-7bcf2b04477a.png)
  
6. 在 Windows"开始"屏幕中，打开 Skype for Business Server 拓扑生成器。
    
7. 单击 **"从现有部署下载拓扑"，** 然后单击"下 **一步"。**
    
8. 输入拓扑的名称，然后单击"保存 **"。**
    
9. 转到保存拓扑的位置，并复制拓扑。
    
### <a name="step-2-upgrade-and-publish-topology-using-topology-builder"></a>步骤 2：使用拓扑生成器升级和发布拓扑

在开始升级过程之前，必须为计划升级的池运行所有服务。 因此，拓扑更改将复制到池中服务器的本地数据库。
  
> [!IMPORTANT]
>  在升级之前保存拓扑文件的副本。 升级后，将无法降级拓扑。> 如果服务与数据库位于同一台服务器上，如持久聊天服务与持久聊天数据库位于同一台服务器上，请跳过此步骤，然后转到步骤 4。 停止服务后，在每个In-Place运行升级安装程序以升级本地数据库。
  
> [!NOTE]
> 如果拓扑具有镜像的后端数据库，则当您使用拓扑生成器发布拓扑时，将会同时显示主体数据库和镜像数据库。  请确保所有数据库都运行在主体上，并且仅在发布拓扑时选择主体，而不是镜像，否则在发布拓扑后将看到一条警告。
  
选择以下选项之一，使用 Skype for Business Server 2015 拓扑生成器升级并发布新拓扑。 完成这些步骤并发布更新的拓扑后，请移至本主题中的步骤 3。
  
#### <a name="option-1-upgrade-an-isolated-front-end-pool-and-associated-archiving-and-monitoring-stores"></a>选项 1：升级独立的前端池和关联的存档和监控存储

如果要升级的池具有存档和监控存储依赖项，则当您使用以下步骤时，还将升级存档和监控存储。
  
1. 在拓扑生成器中，右键单击 Lync Server 2013 池，选择"升级到 **Skype for Business Server 2015"，** 然后按照步骤操作。 
    
     ![包含 Lync Server 2013 升级选项的右键单击菜单的屏幕截图。](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
2. 在拓扑生成器中，单击 **"操作**  >  **发布拓扑**"或"**操作**  >  **拓扑**  >  **发布"。** 
    
     !["操作"菜单在拓扑生成器中具有"发布拓扑"选项的屏幕截图。](../media/d6712634-9205-401f-a0b0-3ea096ca51bf.png)
  
3. 在发布过程中，选择在存档和监控存储中安装数据库。
    
#### <a name="option-2-upgrade-front-end-pool-without-upgrading-archiving-and-monitoring-stores"></a>选项 2：在不升级存档和监控存储的情况下升级前端池

如果使用以下步骤，将禁用所选池的存档和监控。 升级后，池将没有存档和监控存储。
  
1. 在拓扑生成器中，选择要升级的 Lync Server 2013 池。
    
2. 删除对 Lync Server 2013 存档和监控存储的依赖关系。 
    
   - 转到 **"操作**  >  **编辑"属性**。
    
   - 清除 **"存档"** 复选框。
    
     !["编辑属性"对话框中"存档"复选框的屏幕截图。](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - 清除 **"监控"** 复选框。
    
     ![显示"监视"复选框的"编辑属性"对话框的屏幕截图。](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. 右键单击 Lync Server 2013 池，选择"升级到 **Skype for Business Server 2015"，** 然后按照步骤操作。 
    
     ![包含 Lync Server 2013 升级选项的右键单击菜单的屏幕截图。](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. 在拓扑生成器中，单击 **"操作**  >  **发布拓扑**"或"**操作**  >  **拓扑**  >  **发布"。** 
    
#### <a name="option-3-upgrade-front-end-pool-and-associated-it-to-new-skype-for-business-server-2015-archiving-and-monitoring-stores"></a>选项 3：升级前端池，并关联到新的 Skype for Business Server 2015 存档和监控存储

如果使用以下步骤，存档和监控将在上一个存储中停止，并开始在已创建的新存储中启动。 
  
1. 在拓扑生成器中，选择要升级的 Lync Server 2013 池。 
    
2. 删除对 Lync Server 2013 存档和监控存储的依赖关系。 
    
   - 转到 **"操作**  >  **编辑"属性**。
    
   - 清除 **"存档"** 复选框。
    
     !["编辑属性"对话框中"存档"复选框的屏幕截图。](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - 清除 **"监控"** 复选框。
    
     ![显示"监视"复选框的"编辑属性"对话框的屏幕截图。](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. 右键单击 Lync Server 2013 池，选择"升级到 **Skype for Business Server 2015"，** 然后按照步骤操作。 
    
     ![包含 Lync Server 2013 升级选项的右键单击菜单的屏幕截图。](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. 创建新的存档SQL存档存储。 
    
   - 选择池和 **操作**  >  **编辑属性**。 
    
   -  选中“存档”复选框。
    
   - 单击"新建"。
    
     !["编辑属性"对话框的屏幕截图，该对话框显示"存档"部分下的"新建"按钮。](../media/3a4a18e7-8251-4736-837c-2b486f64f896.png)
  
5. 创建新的监控SQL存储。 
    
   - 选择池和 **操作**  >  **编辑属性**。 
    
   -  选中 **"监控"** 复选框。
    
   - 单击"新建"。
    
     !["编辑属性"对话框的屏幕截图，该对话框显示"监视"部分下的"新建"按钮。](../media/729c72a7-0068-4e0d-99dc-e480a6bfbf1d.png)
  
6. 在拓扑生成器中，单击 **"操作**  >  **发布拓扑**"或"**操作**  >  **拓扑**  >  **发布"。** 
    
7. 在发布过程中，选择在新的存档和监控存储中安装数据库。
    
### <a name="step-3-wait-for-replication"></a>步骤 3：等待复制

为复制提供一些时间，以将更新的拓扑发布到环境中的所有服务器。
  
### <a name="step-4-stop-all-services-in-pool-to-be-upgraded"></a>步骤 4：停止池中要升级的所有服务

在维护要升级的池的每个服务器上，在 PowerShell 中运行以下 cmdlet：
  
```powershell
Disable-CsComputer -Scorch
```

我们建议使用Disable-CsComputer，因为您可能需要在升级过程中重新启动In-Place服务器。 如果使用 Stop-CsWindowsService，则某些服务可能在重启后自动重新启动。 这可能会导致升级In-Place失败。
  
### <a name="step-5-upgrade-front-end-pools-and-non-front-end-pool-servers"></a>步骤 5：升级前端池和非前端池服务器

> [!NOTE]
>  在升级之前，请安装 Skype for Business Server 2015 所需的所有新必备组件，其中包括：>尝试升级之前至少 32GB 的可用空间。 此外，请确保驱动器是固定的本地驱动器，未通过 USB 或 Firewire 连接， 使用 NTFS 文件系统格式化，不压缩，并且不包含页面文件。> PowerShell 版本 6.2.9200.0 或更高版本。>安装了最新的 Lync Server 2013 累积更新。> SQL Server 2012 SP1 已安装。>如果使用 Microsoft Update，则会自动安装以下 KB 的 () ：> Windows Server 2008 R2 -[KB2533623](https://support.microsoft.com/kb/2533623)> Windows Server 2012 -[KB2858668](https://support.microsoft.com/kb/2858668)> Windows Server 2012 R2 -[KB2982006](https://support.microsoft.com/kb/2982006)
  
使用In-Place升级来更新前端池、边缘池、中介服务器和持久聊天池。
  
1. 在每台服务器上 **，Setup.exe** Skype for Business Server 2015 安装 **OCS_Volume\Setup\amd64** 运行安装程序。
    
2. 接受许可协议并按照提示执行 In-Place 升级。
    
3. 对前端池中的每台服务器和非前端池服务器重复这些步骤。
    
> [!NOTE]
> 在升级过程中，系统可能会提示In-Place服务器。 没关系。 重新启动后，In-Place升级将继续从它离开的地方开始。 
  
成功完成In-Place升级后，将看到以下消息。
  
![显示就地升级成功完成的屏幕截图。](../media/2f52cb50-9bb4-4714-a982-9c7a0865f78a.png)
  
### <a name="step-6-restart-services-on-all-upgraded-servers"></a>步骤 6：在所有升级的服务器上重新启动服务

> [!NOTE]
> 重新启动服务之前，请确保 %ProgramData%\WindowsFabric 在所有前端服务器上不存在。 如果存在，在启动服务之前将其删除。 
  
- 升级前端池中的所有服务器后，使用下面的 PowerShell 命令重新启动服务： 
    
  ```powershell
  Start-CsPool
  ```

    > [!NOTE]
    > 如果在开始运行 In-Place 升级之前已经需要挂起的系统重新启动，In-Place升级不会要求您在安装结束时重新启动。 当您尝试使用 Start-CSPool cmdlet 启动服务时，将导致针对第一台前端服务器引发一些程序集异常。 若要解决这些错误，请重新启动池中的所有服务器，然后再次运行 cmdlet。 
  
- 在非前端池服务器上，通过以下命令重新启动服务：
    
  ```powershell
  Start-CsWindowsService
  ```

单击 **"升级** In-Place"页上的"确定"后，你将看到以下完成此步骤的提醒。
  
![显示就地升级成功完成后接下来的步骤的屏幕截图。](../media/6a7236b6-9ef9-4df3-8682-b0e4021810f9.png)
  
### <a name="step-7-verify-skype-for-business-functionality-works"></a>步骤 7：验证 Skype for Business 功能是否正常工作

若要确保升级成功，请对已升级的池测试 Skype for Business 以确保功能正常工作。 
  
### <a name="step-8-upgrade-secondary-pools"></a>步骤 8：升级辅助池

重复本主题中的步骤，升级环境中具有的其他任何池。
  
## <a name="troubleshoot-issues-with-the-in-place-upgrade"></a>解决升级In-Place问题

如果In-Place升级失败，您可能会看到一条类似于下图中内容的消息。 
  
![显示由于未安装所需的累积更新而就地升级失败的屏幕截图。](../media/f84db06b-0841-45a9-870d-7ba4b5a463d5.png)
  
查看页面底部的完整消息，以帮助你解决问题。 单击 **"查看日志** "可获取更多详细信息。
  
如果 In-Place 升级在验证升级准备情况或 **安装** 缺少的先决条件时失败，请确保服务器应用了所有最新的 Windows Server、Lync Server 和 SQL Server 更新，并且已安装所有必需的软件和角色。 有关所需内容的列表，请参阅 [Skype for Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md) 的服务器要求和 Skype for Business Server [2015 的安装必备组件](install/install-prerequisites.md)。
  
## <a name="see-also"></a>另请参阅

[计划升级到 Skype for Business Server 2015](../plan-your-deployment/upgrade.md)
  
[Skype for Business Server 2015 的服务器要求](../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[安装 Skype for Business Server 2015 的先决条件](install/install-prerequisites.md)
  
[安装 Skype for Business Server 2015](install/install.md)
