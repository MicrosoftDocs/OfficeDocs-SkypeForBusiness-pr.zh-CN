---
title: 部署呼叫质量仪表板Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 287f64f5-0f8a-455a-8979-7b34bf0217bb
description: 摘要：了解呼叫质量仪表板的部署过程。 通话质量仪表板是一种用于Skype for Business Server。
ms.openlocfilehash: 88f484091b68379d390b921235f78ff9a7a1dd08
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60751701"
---
# <a name="deploy-call-quality-dashboard-for-skype-for-business-server"></a>部署呼叫质量仪表板Skype for Business Server
 
**摘要：** 了解呼叫质量仪表板的部署过程。 通话质量仪表板是一种用于Skype for Business Server。
  
## <a name="deployment-overview"></a>部署概述

呼叫质量仪表板 (CQD) 由三个主要组件组成：
  
- **存档数据库**，其中将复制 (QoE) 用户体验质量。
    
- **多维数据集**，其中聚合 QoE 存档数据库中的数据，以优化快速访问。
    
- **门户**，用户可在门户中轻松查询和可视化 QoE 数据。
    
![CQD 组件。](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
QoE 存档的安装过程涉及创建 QoE 存档数据库、部署将数据从源 QoE 指标数据库移动到 QoE 存档数据库的 SQL Server 存储过程，以及设置 SQL Server 代理作业以定期执行存储过程。 
  
多维数据集部署从 QoE 存档所在的用户处获取信息，部署多维数据集，并设置定期刷新多维数据集的常规 SQL Server 代理作业。
  
门户安装会创建一个存储库数据库，用于存储 CQD 用户到每个用户的报告/查询的映射。 然后，它设置一个 IIS Web 应用程序，这是一个仪表板，用户可以在仪表板中查看一组预定义的报告，并自定义和创建自己的查询以可视化多维数据集数据。 门户安装会创建另外两个 Web 应用程序，这些应用程序公开 API，以便用户以编程方式访问存储库和多维数据集。  (仪表板内部也使用这些 API。) 
  

|**阶段**|**步骤**|**角色和组成员身份**|**文档**|
|:-----|:-----|:-----|:-----|
|安装必备硬件和软件。  <br/> |决定 CQD 配置，然后选择SQL Server安装选项。  <br/> |属于本地 Administrators 组成员的域用户。  <br/> |部署文档中的"预安装要求"部分。  <br/> |
|安装 CQD。  <br/> |在部署文档后运行 MSI。  <br/> |若要执行设置，安装帐户必须是作为本地管理员组的成员且对监控服务器上 QoE 指标数据库具有读取访问权限的域用户。  <br/> |部署文档中的"帐户和部署步骤"部分。  <br/> |
|授予用户访问权限。  <br/> |若要管理对门户的用户授权，我们建议使用 IIS 7.0 中引入的 URL 授权。 有关详细信息，请参阅了解 [IIS 7.0 URL 授权](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization)。  <br/> |属于本地 Administrators 组成员的域用户。  <br/> |部署文档中的"管理门户的用户访问"部分。  <br/> |
|可选：提供子网映射信息。  <br/> |在 QoE 存档数据库中填充网络和构建映射表。  <br/> |对 QoE 存档数据库具有写访问权限的帐户。  <br/> |用户文档中的"提供子网信息"部分。  <br/> |
   


呼叫质量仪表板的部署涉及设置基础结构和安装软件。 以下过程概述了该过程。
  
## <a name="deployment-steps"></a>部署步骤

1. 将CallQualityDashboard.msi复制到要安装 CQD 存档数据库组件的计算机 (这是已安装SQL Server的计算机) 。 
    
2. 执行 MSI (Windows将提示使用管理员权限运行，) 。 
    
3. 接受 EULA。
    
4. 选择与呼叫质量仪表板组件相关的文件将位于的目标文件夹或接受默认位置。
    
5. 选择所有功能。
    
6. 在"QoE 存档配置"页上，提供以下信息：
    
   - **QoE 指标SQL Server：SQL Server** QoE 指标 DB 所在的实例 (将成为数据源) 。
    
   - **QoE 存档SQL Server名称：** 这是只读字段，并修复为本地计算机完全限定的域名。 存档 DB 只能安装在本地计算机上。
    
   - **QoE 存档SQL Server实例：** 要SQL Server存档数据库的本地数据库实例名称。 若要使用默认实例SQL Server，请保留此字段为空。 若要使用命名SQL Server实例，请指定实例 (，例如"名称"之后 \") 。
    
   - **QoE 存档数据库：** 默认情况下，此选项设置为"新建数据库"。 由于不支持存档数据库升级，因此可以使用"使用现有数据库"选项的唯一情形是，现有存档数据库与要安装内部版本具有相同的架构。
    
   - **数据库文件目录：** 存档数据库的数据库文件 (.mdf 和 .ldf) 的位置的路径。 这应该位于推荐 (配置中的驱动器或 HDD2 上，) 操作系统分开。 请注意，由于文件名在安装中是固定的，为了避免任何潜在的冲突，建议使用没有文件的空白目录。
    
   - **使用多个分区：** 默认设置为"多个分区"，这需要商业智能Enterprise或SQL Server。 对于"Standard Edition"，选择"单分区"选项。 请注意，如果使用单个分区，则多维数据集处理性能可能会受到影响。
    
     > [!NOTE]
     > 安装程序完成后，无法更改"使用多个分区"选项的选择。 若要更改它，需要首先卸载多维数据集功能，然后使用控制面板中的"更改"选项重新安装。 
  
   - **分区文件目录：** QoE 存档数据库的分区应放置的位置的路径。 这应位于推荐 (配置驱动器中的驱动器或 HDD3 上) 操作系统驱动器和SQL日志文件驱动器。 请注意，由于文件名在安装中是固定的，为了避免任何潜在的冲突，建议使用没有文件的空白目录。
    
   - **SQL代理作业用户 - 用户名 &amp;密码**：域服务帐户名和密码 (已屏蔽) ，将用于运行 SQL Server 代理作业 (该作业将运行存储过程以将数据从 QoE 指标数据库提取到存档 DB 中，因此此帐户必须具有对 QoE 指标 DB 的读取访问权限，如"帐户"部分所述。 此帐户还需要在 QoE 存档实例SQL Server登录) 。
    
     > [!NOTE]
     > 运行该 SQL Server 实例的帐户（如 NT SERVICE\MSSQLSERVER）必须具有对上述给定目录的访问/权限，安装才能成功。 有关详细信息，请参阅[Configure File System Permissions for 数据库引擎 Access](/previous-versions/sql/sql-server-2012/jj219062(v=sql.110))
  
7. 单击下一步后，安装程序将执行先决条件检查并报告是否遇到任何问题。 当所有先决条件检查通过时，安装程序将转到"多维数据集配置"页。 
    
    > [!NOTE]
    > 如果安装程序显示一条警告消息，指出 QoE 存档 SQL Server 实例的 SQL Server 代理服务当前未运行，则安装可以继续，但安装后请确保 SQL 代理服务正在运行，并且将启动类型设置为"自动"，以便计划的作业运行。 
  
8. 在"多维数据集配置"页上，提供以下信息：
    
   - **QoE 存档SQL Server名称：** 这是只读字段，并修复为本地计算机完全限定的域名。 多维数据集只能从具有 QoE 存档数据库和注释 (安装。 多维数据集本身可以安装在远程计算机上。 请参阅下面的) 
    
   - **QoE 存档SQL Server实例：SQL Server** QoE 存档数据库所在的位置的实例名称。 若要指定默认实例SQL Server，请保留此字段为空。 若要指定SQL Server实例，请输入实例 (，例如"名称"之后 \") 。 如果选择了 QoE 存档组件进行安装，则此字段将预填充"QoE 存档配置"页上提供的值。
    
   - **多维数据集分析服务器**：SQL Server创建多维数据集的 Analysis Service 实例名称。 这可以是其他计算机，但安装用户必须是 Analysis Service 实例的目标服务器SQL Server的成员。
    
     > [!NOTE]
     >  有关配置服务器管理员Analysis Services，请参阅授予 [服务器管理员权限 (Analysis Services) ](/analysis-services/instances/grant-server-admin-rights-to-an-analysis-services-instance?viewFallbackFrom=sql-server-ver15)
  
   - **使用多个分区：** 默认设置为"多个分区"，这需要商业智能Enterprise或SQL Server。 对于"Standard Edition"，选择"单分区"选项。 请注意，如果使用"单个分区"，则多维数据集处理性能可能会受到影响。
    
     > [!NOTE]
     >  安装程序完成后，无法更改"使用多个分区"选项的选择。 若要更改它，需要首先卸载多维数据集功能，然后使用控制面板中的"更改"选项重新安装。
  
   - **多维数据集用户 - &amp; 用户名密码：** 域服务帐户名和密码 (将) 多维数据集处理的名称。 如果选择了 QoE 存档组件进行安装，则此字段将预填充在 SQL 代理作业用户的"存档配置"页上提供的值，但我们建议指定不同的域服务帐户，以便安装程序可以授予最低要求的权限。
    
9. 单击下一步时，将执行另一轮验证，并报告任何问题。 成功完成验证后，安装程序将转到"门户配置"页。 
    
10. 在"门户配置"页上，提供以下信息：
    
    - **QoE 存档SQL Server：SQL Server** QoE 存档数据库所在的位置的实例名称。 请注意，与"QoE 存档配置"页和"多维数据集配置"页不同，计算机名称不是固定的，必须提供。 如果选择了 QoE 存档组件进行安装，则此字段将预填充"QoE 存档配置"页上提供的值。
    
    - **多维数据集分析服务器**：SQL Server多维数据集所在的 Analysis Service 实例名称。 如果为安装选择了多维数据集组件，则此字段将预填充"多维数据集配置"页上提供的值。
    
    - **存储库SQL Server：SQL Server** 创建存储库数据库的实例名称。 如果 QoE 存档数据库所在的 SQL Server 实例名称已在其他组件) 的安装 (中提前提供，则此字段将预先填充 QoE 存档数据库 SQL Server 实例名称。 这可以是任何SQL Server实例。
    
    - **存储库数据库：** 默认情况下，该选项设置为"新建数据库"。 由于不支持 Repository DB 升级，因此可以使用"使用现有数据库"选项的唯一情形是，现有 Repository DB 与要安装内部版本具有相同的架构。
    
    - **IIS 应用程序池用户 - 用户名 &amp; 密码** ：IIS 应用程序池应执行的帐户。 如果选择内置系统帐户，则"用户名"和"密码"字段将灰显。 只有在从下拉框中选择"其他"时，才能启用这些字段，以便用户可以输入域服务帐户信息。
    
11. 单击下一步时，将完成最后一轮验证，以确保可以使用提供的凭据访问 SQL Server 实例，并确保 IIS 在计算机中可用。 成功完成验证后，安装程序将继续安装。 
    
安装程序完成后，很可能SQL Server代理作业正在进行中，同时执行 QoE 数据的初始负载和多维数据集处理。 根据 QoE 中数据的数量，门户尚没有可供查看的数据。 若要检查数据加载和多维数据集处理的状态，请转到  `http://<machinename>/CQD/#/Health` 。 
> [!NOTE]
> 请注意，用于检查下载多维数据集处理状态的 URL 区分大小写。 如果输入"运行状况"，URL 将不起作用。 必须在 URL 末尾输入大写 H 的"Health"。 
  
如果启用调试模式，将显示详细的日志消息。 若要启用调试模式，请转到 **%SYSTEMDRIVE%\Program Files\Skype For Business 2015 CQD\QoEDataService\web.config**，并更新以下行，以便值设置为 **True**：

```xml
<add key="QoEDataLib.DebugMode" value="True" /> 
```

主门户页面可通过 访问  `http://<machinename>/CQD` 。 
## <a name="managing-user-access-for-the-portal"></a>管理门户的用户访问

若要管理对门户的用户授权，我们建议使用 IIS 7.0 中引入的 URL 授权。 有关 IIS 安全性详细信息，请参阅 [了解 IIS 7.0 URL 授权](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization)。
  
任何网站或 Web 应用程序都继承为整个 IIS 配置的默认 URL 授权，通常为"允许所有用户"。 如果对门户的访问需要更加严格，则管理员可通过编辑"授权规则"仅向特定组用户授予访问权限。
  
![部署呼叫质量 - IIS 中的授权规则。](../../media/0da80c28-58fe-4aca-94b4-db684389468c.png)
  
> [!NOTE]
> 不要将"授权规则"图标与"授权规则"部分下的"ASP.NET"混淆，这是一种不同的授权机制。 
  
管理员应首先删除继承的"允许所有用户"规则。 这将阻止任何未经授权的用户访问门户。
  
![部署 CQD。](../../media/fa17ad19-d303-40f8-8324-d13fd67936ab.png)
  
接下来，管理员应添加新的允许规则，并授予特定用户访问门户的权限。 建议创建一个称为"CQDPortalUsers"的本地组来管理用户。
  
![部署呼叫质量仪表板。](../../media/8cfdc141-ec89-4552-921b-53196f497cbf.png)
  
配置详细信息存储在门户web.config中的位置。
  
```xml
<?xml version="1.0" encoding="UTF-8"?> <configuration> <system.webServer> <security> <authorization> <remove users="*" roles="" verbs="" /> <add accessType="Allow" roles="CQDPortalUsers" /> </authorization> </security> </system.webServer> </configuration> 
```

下一步是配置 CQD 的仪表板。 在 IIS 对用户进行身份验证后，他们必须拥有对 CQD 目录的文件权限才能访问 Web 门户内容。 可以通过 CQD 目录属性的安全选项卡更改 ACL，以添加单个用户或组;但是，建议的方法是保持文件权限不变。 相反，将 IIS 设置更改为使用 IIS 工作进程访问 CQD 目录，而不管哪个用户已经过身份验证。 
  
> [!IMPORTANT]
> 必须仅更改 CQD 应用程序的此设置，而不要更改这两个 API 应用程序的此设置：QoEDataService 和 QoERepositoryService。 
  
## <a name="configuring-file-access-for-the-cqd-dashboard"></a>Configuring File Access for the CQD (Dashboard) 

1. 打开 CQD 的配置编辑器。
    
     ![部署呼叫质量仪表板。](../../media/544056eb-3090-434e-bae6-321c984029fa.png)
  
2. 在"部分"下，**选择"system.webServer/serverRuntime"。**
    
     ![部署呼叫质量仪表板。](../../media/b0af0e56-21b0-45dd-b610-5381b39319d3.png)
  
3. 将 authenticatedUserOverride 更改为 **UseWorkerProcessUser**。
    
     ![部署呼叫质量仪表板 - 配置编辑器。](../../media/a7c127f5-9a90-4710-afba-1d1e588efb37.png)
  
4. 单击 **页面** 右侧上的"应用"。
    
## <a name="known-issues"></a>已知问题

### <a name="the-cqd-shows-no-data-after-deployment"></a>CQD 在部署后未显示任何数据

您可能会收到以下错误：

*在多维数据集上运行查询时，无法执行查询。使用查询编辑器修改查询并修复任何问题。此外，请确保多维数据集是可访问的。*

这意味着，在 CQD 中SQL Server Analysis Services必须先处理多维数据集。 可以按照以下步骤解决此问题：

1. 打开SQL Management Studio并选择 **"Analysis Services"。**

2. 展开 **QoECube** 对象，选择 **"QoE** 指标"，右键单击，然后选择"浏览 **"。** 

    如果返回空浏览器，则多维数据集尚未继续。

3. 右键单击 **"QoE 指标**"，然后选择"进程 **"。**

4. 处理完成后，再次右键单击该对象，然后选择"浏览"以确认浏览器页面现在显示数据。 


### <a name="users-have-trouble-logging-in-because-installer-fails-to-create-the-correct-settings-in-iis"></a>用户登录时遇到问题，因为安装程序在 IIS 中无法创建正确的设置

在极少数情况下，安装程序在 IIS 中无法创建正确的设置。 需要手动更改才能允许用户登录 CQD。 如果用户登录时遇到问题，请按照以下步骤操作：
  
1. 打开 IIS 管理器，然后导航到"默认网站"。
    
     ![部署呼叫质量仪表板。](../../media/dc6007aa-870b-4d70-867d-32ffd937063b.png)
  
2. 单击"身份验证"。 如果"匿名身份验证"、"ASP.NET 模拟"、"表单身份验证"和"Windows 身份验证"与下面所示的设置不匹配，请手动更改它们以匹配以下设置。 应禁用所有其他身份验证机制。
    
     ![部署呼叫质量仪表板。](../../media/5d9e38fb-8a50-41a2-a423-3ce983a83d0c.png)
  
3. 对于"Windows身份验证"，请单击设置"高级身份验证"。
    
     ![部署呼叫质量仪表板。](../../media/cad29486-df40-4cc9-82f3-bbdaca52d9ca.png)
  
4. 将"扩展保护"设置为"接受"并选中"启用内核模式身份验证"框。
    
     ![部署呼叫质量仪表板。](../../media/0ab2dda1-0001-4747-8cfc-072e9368b6cb.png)
  
5. 对"默认网站"下面的每个"CQD"、"QoEDataService"和"QoERepositoryService"条目重复上述步骤。
    
对于 HTTP 和 HTTPS 端口绑定，安装程序将在默认端口号上创建端口绑定 (端口 80（对于 HTTP）和端口 443（对于 HTTPS) ）。 如果计算机上还有一个使用这些绑定的网站，则存在冲突，并且无法预测 IIS 行为。 避免此问题的最佳方法就是确保在安装 CQD 之前没有将任何其他网站映射到端口 80 和 443。 
  
若要在 IIS 中启用 SSL/TLS 并强制用户通过安全 HTTPS（而不是 HTTP）进行连接：
  
1. 在 IIS 中配置安全套接字层，请参阅在 [IIS 7](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc771438(v=ws.10))中配置安全套接字层。 完成后，将  `http` 替换为 `https` 。
    
2. 有关在连接连接中启用 TLS SQL Server，请参阅如何使用 Microsoft 管理控制台为 SQL Server 实例启用[SSL 加密](https://support.microsoft.com/kb/316898/)。
    
## <a name="cube-sync-fails"></a>多维数据集同步失败

QoEMetrics 可能包含一些基于最终用户时钟的无效记录。 如果时间斜线大于 60 年，多维数据集导入将失败。
  
 使用下面的选择检查 Min 和 Max StartTime/EndTime。 查找和删除过去和非常远的未来记录，可以忽略这些记录，并且会中断同步过程。
  
- 选择 MIN (StartTime) FROM CqdPartitionedStreamView
    
- Select MAX (StartTime) FROM CqdPartitionedStreamView
    
- Select MIN (EndTime) FROM CqdPartitionedStreamView
    
- Select MAX (EndTime) FROM CqdPartitionedStreamView
    
## <a name="post-install-tasks"></a>安装后任务

### <a name="importing-buildings-and-networks"></a>导入大楼和网络

安装 CQD 后，执行以下配置任务：
  
1. 定义生成类型 (推荐) 
    
2. 定义生成所有权类型 (推荐) 
    
3. 定义强烈建议 (网络) 
    
4. 导入大楼 (推荐) 
    
5. 导入子网 (推荐) 
    
### <a name="define-building-types"></a>定义生成类型

建筑物类型用于描述组织中不同的建筑物定义或类型。 
  
> [!NOTE]
> 此步骤是可选的，但建议执行此步骤。 
  
示例
  
- 总部
    
- 远程Office
    
- 联合位置
    
  **示例SQL语法**
  
```SQL
INSERT INTO
[dbo].[CqdBuildingType]
([BuildingTypeId],
[BuildingTypeDesc])
VALUES
(1, 
'Headquarters')   
```

BuildingTypeId 和 BuildingTypeDesc 参数是必需的。
  
### <a name="define-building-ownership-types"></a>定义构建所有权类型

所有权类型用于区分拥有的资产和租用的资产。
  
> [!NOTE]
> 此步骤是可选的，但建议执行此步骤。 
  
示例
  
- Contoso 租用的非 RE &amp; F
    
- Contoso Leased RE &amp; F
    
- Contoso Owned
    
- 子公司租用
    
  **示例SQL语法**
  
```SQL
INSERT INTO
[dbo].[CqdBuildingOwnershipType]
([OwnershipTypeId],
[OwnershipTypeDesc]
)

VALUES
(1,
'Contoso Owned'
)
```

OwnershipTypeId 和 OwnershipTypeDesc 参数是必需的。 
  
### <a name="define-network-names"></a>定义网络名称

网络类型用于描述组织中不同类型的网络。 这样，您能够基于特定网络 (筛选出) 网络类型。
  
> [!NOTE]
> 强烈建议定义网络名称，但它是可选的。 如果您决定不定义网络名称，请确保每个 CqdNetwork 条目的 BuildingId 为 0。 
  
示例
  
- VPN
    
- 实验室
    
  **示例SQL语法**
  
```SQL
INSERT INTO [dbo].[CqdNetworkName] 
( [NetworkName]
,[NetworkType]
 ) 
VALUES
('VPN','VPN') 
```

NetworkNameID 和 NetworkName 参数是必需的，NetworkType 参数是可选的，但建议这样做。
  
### <a name="import-buildings"></a>导入大楼

通过导入大楼，你可以获取生成特定见解， (WiFi/有线等上的通话质量欠佳) 。 
  
> [!NOTE]
> 此步骤是可选的，但建议执行此步骤。 
  
在导入新建筑物之前，应该已经标识了预定义的 BuildingKey。 为此，请发出"SELECT MAX (BuildingKey) FROM CqdBuilding"SQL命令来标识当前值，并将其添加到结果中。
  
 **示例SQL语法**
  
```SQL
INSERT INTO [dbo].[CqdBuilding] 
( [BuildingKey]
,[BuildingName]
,[BuildingShortName]
,[OwnershipTypeId],
[BuildingTypeId]
)
VALUES
(2, 'Ann Arbor', 'AA', 0, 0)
```

BuildingKey、BuildingName、BuildingShortName、OwnershipTypeId、BuildingTypeId 参数是必需的，其他参数是可选的。
  
### <a name="import-subnets"></a>导入子网

通过导入大楼，你可以获取生成特定见解， (WiFi/有线等上的通话质量欠佳) 。 
  
> [!NOTE]
> 此步骤是可选的，但建议执行此步骤。
  
导入子网，然后将它们映射到上一步中导入的大楼。 如果您决定不填充 NetworkName，请确保此表中的每个条目都使用 NetworkNameID 0。 有关呼叫质量SQL语法和参数的信息，请参阅使用呼叫质量仪表板[进行](./use.md)Skype for Business Server。
  
 **示例SQL语法**
  
```SQL
INSERT INTO [dbo].[CqdNetwork] 
([Network]
,[NetworkRange]
,[NetworkNameID]
,[BuildingKey]
,[UpdatedDate]
)

VALUES
 ('172.16.254.0',32,0,1,'2015-11-11')
```

Network 和 UpdatedDate 参数是必需的，其他参数是可选的。
  
### <a name="optional-bssid"></a>可选：BSSID

填充 BSSID 信息可为你提供控制器或无线设备的其他 WiFi 流关联。 这是通过构建或子网进行筛选之外。 
  
 **示例SQL语法**
  
```SQL
INSERT INTO [dbo].[CqdBssid]
([Ap],
[Bss],
[Building],
[ess],
[phy]
)
VALUES
('AP1','00-00-00-00-00-00','Aruba AP 1','Controller1','bgn')
```

**CqdBssidTable 详细信息**

|**如 CQD 中所示**|**CQDBssid 表**|**示例输入**|
|:-----|:-----|:-----|
|Ap NName  <br/> |AP  <br/> |AP1  <br/> |
|BBssid  <br/> |BSS  <br/> |00-00-00-00-00-00-00 (必须使用分隔的 fformat)   <br/> |
|控制者  <br/> |生成  <br/> |阿鲁巴岛 AP 7  <br/> |
|设备  <br/> |ess  <br/> |Controller1  <br/> |
|无线电广播  <br/> |phy  <br/> |bgn  <br/> |
   
### <a name="processing-the-imported-data"></a>处理导入的数据

默认情况下，导入建筑物/网络数据后，它仅适用于在此时间点之后生成的记录。 
  
若要用此新数据标记所有以前的记录，您需要运行 CqdUpdateBuilding 存储过程，如下所示： 
  
为记录提供第一个记录的日期 (使用 Select MIN (StartTime) FROM CqdPartitionedStreamView SQL 命令 ) ，即明天的 EndDate，然后为后两个值选择 NULL。
  
将数据与流数据关联后，SSIS 多维数据集需要重新处理所有记录。 这同样适用于批量添加 BSSID/ISP 数据的情况。 确保选中"进程已满"。
