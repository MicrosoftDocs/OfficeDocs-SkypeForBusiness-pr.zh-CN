---
title: 为 Skype for Business Server 部署呼叫质量仪表板
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 287f64f5-0f8a-455a-8979-7b34bf0217bb
description: 摘要：了解呼叫质量仪表板的部署过程。 呼叫质量仪表板是 Skype for business Server 的工具。
ms.openlocfilehash: 5879c4a99eec8471763e0fccc3a4886be660dbb6
ms.sourcegitcommit: 54cbcf917d9663e6aa9760d7399b36c00d66478c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/18/2020
ms.locfileid: "42840156"
---
# <a name="deploy-call-quality-dashboard-for-skype-for-business-server"></a>为 Skype for Business Server 部署呼叫质量仪表板
 
**摘要：** 了解通话质量仪表板的部署过程。 呼叫质量仪表板是 Skype for business Server 的工具。
  
## <a name="deployment-overview"></a>部署概述

呼叫质量仪表板（CQD）由三个主要组件组成：
  
- **存档数据库**，其中复制和存储了体验质量（QoE）数据。
    
- **多维数据集**，其中 QoE 存档数据库中的数据进行聚合以进行优化和快速访问。
    
- **门户**，用户可在其中轻松查询和可视化 QoE 数据。
    
![CQD 组件](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
QoE 存档的设置过程包括创建 QoE 存档数据库、部署 SQL Server 存储过程，将源 QoE 指标数据库中的数据移动到 QoE 存档数据库中，并设置 SQL Server 代理作业以执行存储的过程以固定时间间隔。 
  
多维数据集部署从用户处获取 QoE 存档所在的信息，部署多维数据集，并设置将定期刷新多维数据集的常规 SQL Server 代理作业。
  
"门户安装" 创建存储 CQD 用户与每个用户的报表/查询的映射的存储库数据库。 然后，它将设置一个 IIS web 应用程序，该应用程序是用户可以在其中查看预定义报告集的仪表板，也可以自定义和创建自己的查询以可视化多维数据集中的数据。 门户安装创建了另外两个 web 应用程序，这些应用程序公开 Api，以便用户以编程方式访问存储库和多维数据集。 （这些 Api 也由仪表板在内部使用。）
  

|**阶段**|**步骤**|**角色和组成员身份**|**文档**|
|:-----|:-----|:-----|:-----|
|安装必备硬件和软件。  <br/> |确定 CQD 配置，并选择要从中执行安装的 SQL Server。  <br/> |属于本地 Administrators 组成员的域用户。  <br/> |部署文档中的 "预安装要求" 部分。  <br/> |
|安装 CQD。  <br/> |运行部署文档后的 MSI。  <br/> |若要执行设置，安装帐户必须是本地 administrators 组成员的域用户，并且对监控服务器上的 QoE 指标数据库具有读取权限。  <br/> |部署文档中的 "帐户和部署步骤" 部分。  <br/> |
|授予用户访问权限。  <br/> |若要管理对门户的用户授权，我们建议使用在 IIS 7.0 中引入的 URL 授权。 有关详细信息，请参阅[了解 IIS 7.0 URL 授权](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization)。  <br/> |属于本地 Administrators 组成员的域用户。  <br/> |在部署文档中管理 "门户" 部分的 "用户访问"。  <br/> |
|可选：提供子网映射信息。  <br/> |在 QoE 存档数据库中填充网络和构建映射表。  <br/> |具有对 QoE 存档数据库的写入权限的帐户。  <br/> |User 文档中的 "提供子网信息" 部分。  <br/> |
   


呼叫质量仪表板的部署包括设置基础结构和安装软件。 下面的过程概述了此过程。
  
## <a name="deployment-steps"></a>部署步骤

1. 将 CallQualityDashboard 复制到要安装 CQD 的存档数据库组件的计算机（这是安装了 SQL Server 的计算机）。 
    
2. 执行 MSI （Windows 将提示以管理员权限运行，请执行此操作）。 
    
3. 接受 EULA。
    
4. 选择与 "通话质量" 仪表板组件相关的文件将位于的目标文件夹，或接受默认位置。
    
5. 选择 "所有功能"。
    
6. 在 "QoE 存档配置" 页上，提供以下信息：
    
   - **QoE 指标 SQL Server：** 用于 QoE 指标 DB 所在位置的 SQL Server 实例名称（这将是数据源）。
    
   - **QoE 存档 SQL Server 名称：** 这是只读字段，并固定到本地计算机的完全限定域名。 只能在本地计算机上安装存档数据库。
    
   - **QoE 存档 SQL Server 实例：** 要在其中创建存档数据库的本地 SQL Server 实例名称。 若要使用默认的 SQL Server 实例，请将此字段留空。 若要使用命名的 SQL Server 实例，请指定实例名称（例如，在 ""\"之后的名称）。
    
   - **QoE 存档数据库：** 默认情况下，此选项设置为 "新建数据库"。 由于不支持存档数据库升级，如果现有存档数据库的架构与要安装的版本相同，则唯一可以使用 "使用现有数据库" 选项的情况。
    
   - **数据库文件目录：** 应在何处放置存档数据库的数据库文件（.mdf 和 .ldf）的路径。 这应该是独立于操作系统的驱动器上（推荐的硬件配置中的 HDD2）。 请注意，由于文件名在安装中是固定的，因此为避免任何潜在的冲突，建议使用不包含任何文件的空白目录。
    
   - **使用多个分区：** 默认值设置为 "多个分区"，这需要 SQL Server 的商业智能版或 Enterprise edition。 对于 Standard edition，请选择 "单个分区" 选项。 请注意，如果使用单个分区，则多维数据集处理性能可能会受到影响。
    
     > [!NOTE]
     > 在安装程序完成后，不能更改 "使用多个分区的选择" 选项。 为了进行更改，需要先卸载多维数据集功能，然后使用控制面板中的 "更改" 选项重新安装。 
  
   - **分区文件目录：** 应在何处放置 QoE 存档数据库的分区的路径。 这应该是与 OS 驱动器和 SQL 数据库日志文件驱动器不同的驱动器（建议的硬件配置中的 HDD3）。 请注意，由于文件名在安装中是固定的，因此为避免任何潜在的冲突，建议使用不包含任何文件的空白目录。
    
   - **SQL 代理作业用户用户名&amp;密码：** 将用于运行 SQL Server 代理作业的 "QoE 存档数据" 步骤（将运行存储过程以将数据从 QoE 指标数据库提取到存档数据库中）的域服务帐户名称和密码（掩码）。因此，此帐户必须具有对 QoE 指标 DB 的读取访问权限，如 "帐户" 部分中所示。 此帐户还需要在 QoE 存档 SQL Server 实例中有一个登录名。
    
     > [!NOTE]
     > 运行 SQL Server 实例所依据的帐户（如 NT SERVICE\MSSQLSERVER）必须具有上述目录的访问权限，才能成功安装。 有关详细信息，请参阅[配置文件系统权限以进行数据库引擎访问](https://msdn.microsoft.com/library/jj219062%28v=sql.110%29.aspx)
  
7. 单击 "下一步" 后，安装程序将执行先决条件检查，并在遇到任何问题时报告。 当所有的先决条件检查都通过后，安装程序将转到 "多维数据集配置" 页。 
    
    > [!NOTE]
    > 如果安装程序显示一条警告消息，指出 QoE 存档 SQL Server 实例的 SQL Server 代理服务当前未运行，则可以继续安装，但安装后请确保 SQL 代理服务正在运行，并将启动类型设置为"自动"，以便运行计划的作业。 
  
8. 在 "多维数据集配置" 页上，提供以下信息：
    
   - **QoE 存档 SQL Server 名称：** 这是只读字段，并固定到本地计算机的完全限定域名。 只能从具有 QoE 存档数据库（注释）的计算机安装多维数据集。 多维数据集本身可以安装在远程计算机上。 见下文）
    
   - **QoE 存档 SQL Server 实例：** QoE 存档数据库所在位置的 SQL Server 实例名称。 若要指定默认的 SQL Server 实例，请将此字段留空。 若要指定命名的 SQL Server 实例，请输入实例名称（例如，在 ""\"之后的名称）。 如果为安装选择了 QoE 存档组件，则此字段将预先填充在 QoE 存档配置页上提供的值。
    
   - **多维数据集分析服务器：** 要在其中创建多维数据集的 SQL Server Analysis Service 实例名称。 这可以是不同的计算机，但安装用户必须是目标 SQL Server Analysis Service 实例的服务器管理员的成员。
    
     > [!NOTE]
     >  有关配置 Analysis Services 服务器管理员权限的详细信息，请参阅[授予服务器管理员权限（Analysis Services）](https://msdn.microsoft.com/library/ms174561.aspx)
  
   - **使用多个分区：** 默认值设置为 "多个分区"，这需要 SQL Server 的商业智能版或 Enterprise edition。 对于 Standard edition，请选择 "单个分区" 选项。 请注意，如果使用单个分区，则多维数据集处理性能可能会受到影响。
    
     > [!NOTE]
     >  在安装程序完成后，不能更改 "使用多个分区的选择" 选项。 为了进行更改，需要先卸载多维数据集功能，然后使用控制面板中的 "更改" 选项重新安装。
  
   - **多维数据集用户用户名&amp;密码：** 将触发多维数据集处理的域服务帐户的名称和密码（掩码）。 如果为安装选择了 "QoE 存档" 组件，则此字段将预先填充为 SQL 代理作业用户的 "存档配置" 页上提供的值，但我们建议指定一个不同的域服务帐户，以便安装程序可以授予对其所需的最低权限。
    
9. 单击 "下一步" 时，将执行另一轮验证，并将报告任何问题。 成功完成验证后，安装程序将转到 "门户配置" 页。 
    
10. 在 "门户配置" 页上，提供以下信息：
    
    - **QoE 存档 SQL Server：** QoE 存档数据库所在位置的 SQL Server 实例名称。 请注意，与 QoE 存档配置页和多维数据集配置页不同，计算机名称不是固定的，必须提供。 如果为安装选择了 QoE 存档组件，则此字段将预先填充在 QoE 存档配置页上提供的值。
    
    - **多维数据集分析服务器：** 多维数据集所在位置的 SQL Server Analysis Service 实例名称。 如果为安装选择了多维数据集组件，则此字段将预先填充 "多维数据集配置" 页上提供的值。
    
    - **存储库 SQL Server：** 要在其中创建存储库数据库的 SQL Server 实例名称。 如果 QoE 存档数据库所在的 SQL Server 实例名称在安装程序的早期（在其他组件中）中已提供，则将使用 QoE 存档数据库 SQL Server 实例名称预填充此字段。 它可以是任何 SQL Server 实例。
    
    - **存储库数据库：** 默认情况下，此选项设置为 "新建数据库"。 由于不支持存储库数据库升级，如果现有存储库数据库的架构与要安装的版本相同，则唯一可以使用 "使用现有数据库" 选项的情况。
    
    - **IIS 应用程序池用户用户名&amp;密码：** IIS 应用程序池应在其下执行的帐户。 如果选择了内置系统帐户，则 "用户名" 和 "密码" 字段将灰显。 仅当从下拉框中选择了 "其他" 时，才会启用这些字段，以便用户可以输入域服务帐户信息。
    
11. 单击 "下一步" 时，将执行最后一轮验证，以确保 SQL Server 实例可使用提供的凭据访问，并且该 IIS 在计算机上可用。 成功完成验证后，安装程序将继续进行设置。 
    
安装程序完成后，最有可能的原因是 SQL Server 代理作业正在进行，并执行 QoE 数据的初始加载和多维数据集处理。 根据 QoE 中的数据量，门户将不包含可供查看的数据。 若要检查数据加载和多维数据集处理的状态，请转`http://<machinename>/CQD/#/Health`到。 
> [!NOTE]
> 请注意，用于检查下载多维数据集的状态的 URL 是区分大小写的。 如果输入 "运行状况"，则 URL 将不起作用。 必须在具有大写 H 的 URL 末尾处输入 "Health"。 
  
如果启用了调试模式，则将显示详细的日志消息。 若要启用调试模式，请转到 **%SYSTEMDRIVE%\Program Files\Skype For Business 2015 CQD\QoEDataService\web.config**，并更新以下行，以便将该值设置为**True**：

```xml
<add key="QoEDataLib.DebugMode" value="True" /> 
```

可通过`http://<machinename>/CQD`访问主门户页面。 
## <a name="managing-user-access-for-the-portal"></a>管理门户的用户访问权限

若要管理对门户的用户授权，我们建议使用在 IIS 7.0 中引入的 URL 授权。 有关 IIS 安全性的详细信息，请参阅[了解 iis 7.0 URL 授权](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization)。
  
任何网站或 web 应用程序都会继承为整个 IIS （通常为 "允许所有用户"）配置的默认 URL 授权。 如果对门户的访问需要更具限制性，则管理员可以通过编辑 "授权规则" 仅授予特定用户组的访问权限。
  
![部署呼叫质量-IIS 中的授权规则](../../media/0da80c28-58fe-4aca-94b4-db684389468c.png)
  
> [!NOTE]
> "授权规则" 图标不会与 "ASP.NET" 部分下的 ".NET 授权" 相混淆，后者是一种不同的授权机制。 
  
管理员应首先删除继承的 "允许所有用户" 规则。 这将阻止任何未授权的用户访问门户。
  
![部署 CQD](../../media/fa17ad19-d303-40f8-8324-d13fd67936ab.png)
  
接下来，管理员应添加新的允许规则，并向特定用户授予访问门户的权限。 建议创建一个名为 "CQDPortalUsers" 的本地组来管理用户。
  
![部署呼叫质量仪表板](../../media/8cfdc141-ec89-4552-921b-53196f497cbf.png)
  
配置详细信息存储在位于门户的物理目录中的 web.config 中。
  
```xml
<?xml version="1.0" encoding="UTF-8"?> <configuration> <system.webServer> <security> <authorization> <remove users="*" roles="" verbs="" /> <add accessType="Allow" roles="CQDPortalUsers" /> </authorization> </security> </system.webServer> </configuration> 
```

下一步是配置 CQD 的仪表板。 通过 IIS 对用户进行身份验证后，他们必须具有对 CQD 目录的文件权限，才能访问 web 门户内容。 可以通过 CQD 目录属性的 "安全" 选项卡更改 Acl，以添加单个用户或组;但是，建议的方法是使文件权限保持不变。 相反，请将 IIS 设置更改为使用 IIS 工作进程访问 CQD 目录，而不管对哪个用户进行身份验证。 
  
> [!IMPORTANT]
> 一定要只更改 CQD 应用程序的此设置，而不是对这两个 API 应用程序： QoEDataService 和 QoERepositoryService。 
  
## <a name="configuring-file-access-for-the-cqd-dashboard"></a>为 CQD 配置文件访问（仪表板）

1. 打开 CQD 的配置编辑器。
    
     ![部署呼叫质量仪表板](../../media/544056eb-3090-434e-bae6-321c984029fa.png)
  
2. 在 "部分" 中，选择 " **system.webserver/microsoft.sharepoint.client.serverruntime.dll**"。
    
     ![部署呼叫质量仪表板](../../media/b0af0e56-21b0-45dd-b610-5381b39319d3.png)
  
3. 将 authenticatedUserOverride 更改为**UseWorkerProcessUser**。
    
     ![部署呼叫质量仪表板-配置编辑器](../../media/a7c127f5-9a90-4710-afba-1d1e588efb37.png)
  
4. 在页面右侧，单击 "**应用**"。
    
## <a name="known-issues"></a>已知问题

### <a name="the-cqd-shows-no-data-after-deployment"></a>CQD 在部署后不显示数据

您可能会收到以下错误消息：

*在多维数据集中运行查询时，无法执行查询。使用查询编辑器修改查询并修复任何问题。此外，请确保多维数据集可供访问。*

这意味着在 CQD 中使用多维数据集之前，必须在 SQL Server Analysis Services 中对其进行处理。 若要解决此问题，可以执行以下步骤：

1. 打开 SQL Management Studio 并选择 " **Analysis Services**"。

2. 展开**QoECube**对象，选择 " **QoE 指标**"，单击鼠标右键，然后选择 "**浏览**"。 

    如果这将返回空浏览器，则该多维数据集尚未继续。

3. 右键单击 " **QoE 公制**angain"，然后选择 "**处理**"。

4. 处理完成后，再次右键单击对象，然后选择 "**浏览**" 以确认浏览器页现在显示数据。 


### <a name="users-have-trouble-logging-in-because-installer-fails-to-create-the-correct-settings-in-iis"></a>用户在登录时遇到问题，因为安装程序无法在 IIS 中创建正确设置

在极少数情况下，安装程序无法在 IIS 中创建正确的设置。 若要允许用户登录到 CQD，需要进行手动更改。 如果用户登录时遇到问题，请按照以下步骤操作：
  
1. 打开 IIS 管理器，导航到 "默认网站"。
    
     ![部署呼叫质量仪表板](../../media/dc6007aa-870b-4d70-867d-32ffd937063b.png)
  
2. 单击 "身份验证"。 如果 "匿名身份验证"、"ASP.NET 模拟"、"表单身份验证" 和 "Windows 身份验证" 与下面显示的设置不匹配，请手动将其更改为与下面的设置相匹配。 应禁用所有其他身份验证机制。
    
     ![部署呼叫质量仪表板](../../media/5d9e38fb-8a50-41a2-a423-3ce983a83d0c.png)
  
3. 对于 "Windows 身份验证"，单击右侧的 "高级设置"。
    
     ![部署呼叫质量仪表板](../../media/cad29486-df40-4cc9-82f3-bbdaca52d9ca.png)
  
4. 设置 "扩展保护" 以接受并选中 "启用内核模式身份验证" 框。
    
     ![部署呼叫质量仪表板](../../media/0ab2dda1-0001-4747-8cfc-072e9368b6cb.png)
  
5. 对以下每个 "CQD"、"QoEDataService" 和 "QoERepositoryService" 条目重复上述步骤 "Default Web Site"。
    
对于 HTTP 和 HTTPS 端口绑定，安装程序将在默认端口号（端口 80 for HTTP，端口443用于 HTTPS）上创建端口绑定。 如果计算机上存在使用这些绑定的另一个网站，将存在冲突，无法预测 IIS 行为。 避免此问题的最好方法是，在安装 CQD 之前，确保没有其他网站映射到端口80和443。 
  
在 IIS 中启用 SSL/TLS，并强制用户通过安全 HTTPS （而不是 HTTP）进行连接：
  
1. 在 IIS 中配置安全套接字层，请参阅[在 iis 7 中配置安全套接字层](https://technet.microsoft.com/library/cc771438%28v=ws.10%29.aspx)。 完成后，将`http`替换`https`为。
    
2. 有关在 SQL Server 连接中启用 TLS 的说明，请参阅[如何使用 Microsoft 管理控制台为 SQL server 实例启用 SSL 加密](https://support.microsoft.com/kb/316898/)。
    
## <a name="cube-sync-fails"></a>多维数据集同步失败

QoEMetrics 可能包含基于最终用户时钟的一些无效记录。 如果时间偏差大于 60 yrs，多维数据集导入将失败。
  
 使用下面的选择检查 Min 和 Max StartTime/EndTime。 查找和删除在过去和远较远的将来记录，可以忽略它们，它们将分解同步过程。
  
- 从 CqdPartitionedStreamView 中选择最小值（StartTime）
    
- 从 CqdPartitionedStreamView 中选择 "最大值（StartTime）"
    
- 从 CqdPartitionedStreamView 中选择最小值（EndTime）
    
- 选择 CqdPartitionedStreamView 中的 MAX （EndTime）
    
## <a name="post-install-tasks"></a>安装后任务

### <a name="importing-buildings-and-networks"></a>导入建筑物和网络

安装 CQD 后，请执行以下配置任务：
  
1. 定义生成类型（推荐）
    
2. 定义建筑物所有权类型（推荐）
    
3. 定义网络类型（强烈推荐）
    
4. 导入建筑物（推荐）
    
5. 导入子网（推荐）
    
### <a name="define-building-types"></a>定义建筑物类型

生成类型用于描述组织中的不同建筑物定义或类型。 
  
> [!NOTE]
> 此步骤是可选的，但建议这样做。 
  
示例
  
- 总部
    
- 远程办公室
    
- 联合-冒险位置
    
  **示例 SQL 语法**
  
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
  
### <a name="define-building-ownership-types"></a>定义建筑物所有权类型

所有权类型用于区分拥有的与租用的资产。
  
> [!NOTE]
> 此步骤是可选的，但建议这样做。 
  
示例
  
- Contoso 租赁非 RE&amp;F
    
- Contoso 租赁 RE&amp;F
    
- Contoso 拥有
    
- 子公司租赁
    
  **示例 SQL 语法**
  
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

网络类型用于描述组织内的不同类型的网络。 这使您能够筛选（或筛选出）特定的网络类型。
  
> [!NOTE]
> 强烈建议定义网络名称，但这是可选的。 如果决定不定义网络名称，请确保每个 CqdNetwork 条目的 BuildingId 为0。 
  
示例
  
- VPN
    
- 实验
    
  **示例 SQL 语法**
  
```SQL
INSERT INTO [dbo].[CqdNetworkName] 
( [NetworkName]
,[NetworkType]
 ) 
VALUES
('VPN','VPN') 
```

NetworkNameID 和 NetworkName 参数是必需的，网络参数是可选的，但建议使用。
  
### <a name="import-buildings"></a>导入建筑物

通过导入建筑物，您可以获取建筑物特定的见解（每个建筑物的对 WiFi/有线等较差的呼叫）。 
  
> [!NOTE]
> 此步骤是可选的，但建议这样做。 
  
在导入新建筑物之前，您应该已经确定了预定义的 BuildingKey。 若要执行此操作，请发出 "SELECT MAX （BuildingKey） FROM CqdBuilding" SQL 命令以确定当前值，并将1添加到结果中。
  
 **示例 SQL 语法**
  
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

通过导入建筑物，您可以获取建筑物特定的见解（每个建筑物的对 WiFi/有线等较差的呼叫）。 
  
> [!NOTE]
> 此步骤是可选的，但建议这样做。
  
导入子网并将其映射到上一步骤中导入的建筑物。 如果决定不填充 NetworkName，请确保此表中的每个条目都使用 NetworkNameID 0。 有关呼叫质量仪表板的 SQL 语法和参数的详细信息，请参阅[Use Call Quality 仪表板 For Skype For Business Server](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/use)。
  
 **示例 SQL 语法**
  
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

网络和 UpdatedDate 参数是必需的，其他参数是可选的。
  
### <a name="optional-bssid"></a>可选： BSSID

填充 BSSID 信息可为您提供由控制器或收音机的额外 WiFi 流关联。 这是通过建筑物或子网进行筛选的补充。 
  
 **示例 SQL 语法**
  
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
|Ap NName  <br/> |帐款  <br/> |AP1  <br/> |
|BBssid  <br/> |面临  <br/> |00-00-00-00-00-00 （必须使用带分隔符的 fformat）  <br/> |
|控制器  <br/> |幢  <br/> |Aruba 接入点7  <br/> |
|Device  <br/> |自助  <br/> |Controller1  <br/> |
|无线电台  <br/> |物理  <br/> |bgn  <br/> |
   
### <a name="processing-the-imported-data"></a>处理导入的数据

默认情况下，在您导入生成/网络数据之后，它将仅应用于在该时间点后生成的记录。 
  
若要使用此新数据标记所有以前的记录，您将需要运行 CqdUpdateBuilding 存储过程，如下所示： 
  
为其指定第一条记录（使用 Select MIN （StartTime） FROM CqdPartitionedStreamView SQL 命令）的日期、明天的结束日期、最后两个值为 NULL。
  
数据与 stream 数据相关联后，SSIS 多维数据集需要重新处理所有记录。 批量添加 BSSID/ISP 数据时也适用。 确保选中 "进程已满"。
  

