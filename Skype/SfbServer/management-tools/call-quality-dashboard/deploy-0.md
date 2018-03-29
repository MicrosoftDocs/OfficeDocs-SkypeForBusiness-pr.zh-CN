---
title: Skype 通话质量仪表板部署业务服务器 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 287f64f5-0f8a-455a-8979-7b34bf0217bb
description: 摘要： 了解调用质量仪表板的部署过程。 通话质量仪表板是用于业务服务器 2015年的 Skype 的工具。
ms.openlocfilehash: ff8f9bae2c292720bb3fd9943bc541a8eeb6759c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-call-quality-dashboard-for-skype-for-business-server-2015"></a>Skype 通话质量仪表板部署业务服务器 2015
 
**摘要：**了解调用质量仪表板部署过程。 通话质量仪表板是用于业务服务器 2015年的 Skype 的工具。
  
## <a name="deployment-overview"></a>部署概述

通话质量仪表板 (CQD) 由三个主要组件组成：
  
- **存档数据库**，在其中体验质量 (QoE) 并将数据复制存储。
    
- **多维数据集**，其中 QoE 存档数据库中的数据进行聚合的优化和快速存取。
    
- **门户网站**，在其中用户可以方便地查询和可视化 QoE 数据。
    
![CQD 组件](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
QoE 归档文件的安装过程包括创建 QoE 存档数据库、 部署会将数据从移动源 QoE 指标数据库到 QoE 存档数据库中，SQL Server 存储过程设置 SQL Server 代理作业来执行存储以固定间隔的过程。 
  
多维数据集部署 QoE 存档所在、 部署多维数据集，以及将会定期刷新多维数据集的常规 SQL Server 代理作业设置为在用户获取信息。
  
门户安装创建存储库数据库，用于存储到每个用户的报告查询的 CQD 用户的映射。 然后设置 IIS web 应用程序即仪表板用户查看一组预定义的报告，以及自定义和创建自己的查询可视化数据的多维数据集。 门户安装创建两个其他 web 应用程序公开 Api，可用于以编程方式访问存储库和多维数据集的用户。 （这些 Api 使用内部的仪表板）。
  

|**阶段**|**步骤**|**角色和组成员资格**|**文档**|
|:-----|:-----|:-----|:-----|
|安装系统必备组件的硬件和软件。  <br/> |决定的 CQD 配置，并选择要从中执行安装 SQL Server。  <br/> |属于本地 Administrators 组成员的域用户。  <br/> |部署文档中的"预安装要求"部分。  <br/> |
|安装 CQD。  <br/> |运行 MSI 下部署文档。  <br/> |若要执行安装程序，安装的帐户必须是本地管理员组成员的域用户和监视服务器上有读取访问权限 QoE 指标数据库。  <br/> |部署文档中的"帐户和部署步骤"部分。  <br/> |
|授予用户访问权。  <br/> |用于管理门户的用户身份验证，我们建议使用 URL 授权，IIS 7.0 中引入了。 有关详细信息，请参阅[了解 IIS 7.0 的 URL 授权](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization)。  <br/> |属于本地 Administrators 组成员的域用户。  <br/> |管理门户中部署文档部分的用户访问。  <br/> |
|可选： 提供子网的映射信息。  <br/> |填充网络和构建映射 QoE 存档数据库中的表。  <br/> |有到 QoE 存档数据库的写访问权限的帐户。  <br/> |"提供子网信息"一节中的用户文档。  <br/> |
   
## 

设置基础结构和安装软件，涉及到的呼叫质量仪表板部署。 下面的过程概述了该进程。
  
### <a name="deployment-steps"></a>部署步骤

1. 将 CallQualityDashboard.msi 复制到 CQD 的存档数据库组件的安装位置的计算机 （这是已安装的 SQL Server 的计算机）。 
    
2. 执行 MSI （Windows 会提示使用管理员权限运行，这样做）。 
    
3. 接受最终用户许可协议。
    
4. 选择目标文件夹位置与调用质量仪表板组件相关的文件将位于或接受默认位置。
    
5. 选择所有的功能。
    
6. 在 QoE 存档配置页上，提供了以下信息：
    
   - **QoE 标准 SQL Server:**QoE 指标数据库所在的 SQL Server 实例名称 （这将是数据源）。
    
   - **QoE 存档 SQL Server 名称：**这是只读字段并固定到本地计算机的完全合格的域名称。 只能在本地计算机上可以安装存档数据库。
    
   - **QoE 存档的 SQL Server 实例：**为存档数据库旨在创建一个本地 SQL Server 实例名称。 若要使用默认的 SQL Server 实例，请将此字段留空。 若要使用 SQL Server 的命名的实例，请指定实例名称 (例如后的名称"\")。
    
   - **QoE 存档数据库：**默认情况下，此选项设置为"创建新数据库"。 由于不支持存档数据库升级，可以在其下使用了"使用现有数据库"选项的唯一事物是现有的存档数据库是否具有相同的架构生成安装。
    
   - **数据库文件目录：**存档数据库的数据库文件 （.mdf 和.ldf） 应放置的位置的路径。 这应该是在一个驱动器上 (推荐使用的硬件配置中的 HDD2) 独立于操作系统。 请注意，因为文件的名称安装在固定的以避免任何潜在的冲突，建议空白目录与文件不能使用。
    
   - **使用多个分区：**默认设置为"多个分区"，这需要商业智能版或企业版的 SQL Server。 标准版中，请选择"单个分区"选项。 请注意，是否使用单个分区，则多维数据集的处理性能可能会受到影响。
    
    > [!NOTE]
    > 完成安装程序后，使用多个分区选项对所选内容不能更改。 要更改它，该多维数据集功能必须是第一个卸载并重新安装使用控制面板中的"更改"选项。 
  
   - **分区文件目录：**QoE 存档数据库的分区的放置位置的路径。 这应该是在一个驱动器上 (推荐使用的硬件配置中的 HDD3) 独立于操作系统驱动器和 SQL 数据库日志文件驱动器。 请注意，因为文件的名称安装在固定的以避免任何潜在的冲突，建议空白目录与文件不能使用。
    
   - **SQL 代理作业用户用户名&amp;密码：**域服务帐户名和密码 （遮蔽） 将用来运行"QoE 存档数据"（它将运行该存储的过程获取数据从 QoE 指标数据库到存档数据库，因此，该帐户必须具有读取访问权限 QoE 指标数据库，SQL Server 代理作业的步骤 如在帐户部分所示。 此帐户还需要有一个登录 QoE 存档的 SQL Server 实例中）。
    
    > [!NOTE]
    > 如 NT SERVICE\MSSQLSERVER 下运行 SQL Server 实例的帐户必须具有访问/安装成功上面给出的目录的权限。 有关详细信息，请参阅[配置文件系统数据库引擎访问权限](https://msdn.microsoft.com/en-us/library/jj219062%28v=sql.110%29.aspx)
  
7. 在单击下一步，安装程序将执行系统必备检查和报告，如果遇到任何问题。 当所有系统必备检查处理过程中，安装程序将转到多维数据集配置页。 
    
    > [!NOTE]
    > 如果安装程序显示 QoE 存档的 SQL Server 实例的 SQL Server 代理服务当前未运行一条警告消息，可以继续安装，但安装后，请确保 SQL 代理服务正在运行，并将启动类型设置为自动运行计划的作业。 
  
8. 在多维数据集配置页上，提供了以下信息：
    
   - **QoE 存档 SQL Server 名称：**这是只读字段并固定到本地计算机的完全合格的域名称。 多维数据集可以安装仅从机器具有 QoE 存档数据库 （请注意。 多维数据集本身可能安装在远程计算机上。 请参见下文）
    
   - **QoE 存档的 SQL Server 实例：**QoE 存档数据库所在的 SQL Server 实例名称。 若要指定默认的 SQL Server 实例，请将此字段留空。 若要指定命名的 SQL Server 实例，输入实例名称 (例如后的名称"\")。 如果选择 QoE 档案组件的安装，此字段将预先填充 QoE 存档配置页面上提供的值。
    
   - **多维数据集的分析服务器：**创建多维数据集所在的 SQL Server 分析服务实例名称。 这可以是另一台计算机，但执行安装的用户必须是服务器管理员的目标 SQL Server 分析服务实例的成员。
    
    > [!NOTE]
    >  有关配置 Analysis Services 服务器管理员权限的详细信息，请参阅[授予服务器管理员权限 (Analysis Services)](https://msdn.microsoft.com/en-us/library/ms174561.aspx)
  
   - **使用多个分区：**默认设置为"多个分区"，这需要商业智能版或企业版的 SQL Server。 标准版中，请选择"单个分区"选项。 请注意，是否使用单个分区，则多维数据集的处理性能可能会受到影响。
    
    > [!NOTE]
    >  完成安装程序后，使用多个分区选项对所选内容不能更改。 要更改它，该多维数据集功能必须是第一个卸载并重新安装使用控制面板中的"更改"选项。
  
   - **多维数据集的用户的用户名&amp;密码：**域服务帐户名和密码 （遮蔽） 将触发处理多维数据集。 如果选择 QoE 档案组件的安装，此字段将 SQL 代理作业用户提供存档配置页上的值预先填充但建议，以便安装程序可以授予指定一个不同的域服务帐户对其最低所需的权限。
    
9. 当单击下一步，将执行另一轮验证，将报告任何问题。 在成功完成验证，安装程序将进入门户配置页。 
    
10. 在入口配置页上，提供了以下信息：
    
    - **QoE 存档的 SQL Server:**QoE 存档数据库所在的 SQL Server 实例名称。 注意，与 QoE 存档配置页和多维数据集配置页，不同的计算机名称不固定的必须提供。 如果选择 QoE 档案组件的安装，此字段将预先填充 QoE 存档配置页面上提供的值。
    
    - **多维数据集的分析服务器：**SQL Server 分析服务实例名称设置为该多维数据集所在的位置。 如果安装选择多维数据集的组件，此字段将预先填充多维数据集配置页面上提供的值。
    
    - **存储库 SQL Server:**创建存储库数据库所在的 SQL Server 实例名称。 如果前面的设置 （在其他组件） 提供了 QoE 存档数据库所在的 SQL Server 实例名称，此字段将预先填充 QoE 存档数据库的 SQL Server 实例名称。 这可以是任何 SQL Server 实例。
    
    - **存储库数据库：**默认情况下该选项设置为"创建新数据库"。 由于不支持存储库数据库升级，在"使用现有数据库"选项可以使用机制的唯一情况是如果现有存储库数据库具有相同的架构生成安装。
    
    - **IIS 应用程序池用户的用户名&amp;密码：**下应执行 IIS 应用程序池帐户。 如果选择了内置的系统帐户，用户名称和密码字段将灰显。 如果"其他"选择从下拉框中，以便用户可以输入域服务帐户信息，仅将启用这些字段。
    
11. 当单击下一步，将进行验证的最终轮以确保 SQL Server 实例都可以访问使用提供的凭据，并且 IIS 的计算机上可用。 在成功完成验证，安装程序将继续安装。 
    
完成安装程序后，很可能 SQL Server 代理作业将在进行中，执行初始加载 QoE 数据和多维数据集处理。 根据中 QoE 数据量，门户将没有数据可供查看尚未。 要检查的数据负载和多维数据集处理的状态，请转到`http://<machinename>/CQD/#/Health`。 
> [!NOTE]
> 请注意，检查下载多维数据集处理的状态的 URL 区分大小写。 如果您输入的 URL 不起健康。 您必须输入 '健康' 结尾的 URL 以大写 h。 
  
如果启用了调试模式将显示详细的日志消息。 要启用调试模式，转到**为企业 2015 CQD\QoEDataService\web.config Files\Skype %SYSTEMDRIVE%\Program**，并更新下面的行，因此值设置为**True**:

```
<add key="QoEDataLib.DebugMode" value="True" /> 
```

门户的主页是通过可访问`http://<machinename>/CQD`。 
## <a name="managing-user-access-for-the-portal"></a>管理门户的用户访问

用于管理门户的用户身份验证，我们建议使用 URL 授权，IIS 7.0 中引入了。 有关 IIS 安全性的详细信息，请参阅[了解 IIS 7.0 的 URL 授权](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization)。
  
任何 web 站点或 web 应用程序继承的默认 URL 授权配置整个 iis，这通常是"允许所有用户"。 如果需要更具限制性访问门户，然后管理员可以授予访问只有特定的用户组通过编辑"授权规则"。
  
![部署呼叫质量 - IIS 中的授权规则](../../media/0da80c28-58fe-4aca-94b4-db684389468c.png)
  
> [!NOTE]
> 授权规则图标是不会混淆与 ASP.NET 部分，是一种不同的授权机制下".NET 授权"。 
  
管理员应该首先删除继承"允许所有用户"规则。 这可以防止任何未经授权的用户访问门户网站。
  
![部署 CQD](../../media/fa17ad19-d303-40f8-8324-d13fd67936ab.png)
  
下一步，管理员应添加新的允许规则并授予特定用户访问门户网站的权限。 建议创建一个名为"CQDPortalUsers"的本地组来管理用户。
  
![部署呼叫质量仪表板](../../media/8cfdc141-ec89-4552-921b-53196f497cbf.png)
  
配置详细信息都存储在 web.config 位于门户的物理目录。
  
```
<?xml version="1.0" encoding="UTF-8"?> <configuration> <system.webServer> <security> <authorization> <remove users="*" roles="" verbs="" /> <add accessType="Allow" roles="CQDPortalUsers" /> </authorization> </security> </system.webServer> </configuration> 
```

下一步是配置的 CQD 的仪表板。 用户在通过 IIS 进行身份验证后，他们将不得不具有 CQD 目录的文件权限，才能访问 web 入口网站的内容。 可以更改通过 CQD 目录属性的安全选项卡上的 Acl 添加个别用户或组;但是建议的方法是保持不变的文件权限。 相反，更改 IIS 设置以使用 IIS 工作进程访问的 CQD 目录，无论该用户进行身份验证。 
  
> [!IMPORTANT]
> 很重要的只需更改此设置的 CQD 的应用程序，而不是针对两个 API 应用程序： QoEDataService 和 QoERepositoryService。 
  
### <a name="configuring-file-access-for-the-cqd-dashboard"></a>配置文件访问的 CQD （仪表板）

1. 打开 CQD 的配置编辑器。
    
     ![部署呼叫质量仪表板](../../media/544056eb-3090-434e-bae6-321c984029fa.png)
  
2. 在部分，选择**system.webServer/serverRuntime**。
    
     ![部署呼叫质量仪表板](../../media/b0af0e56-21b0-45dd-b610-5381b39319d3.png)
  
3. 将 authenticatedUserOverride 更改为**UseWorkerProcessUser**。
    
     ![部署呼叫质量仪表板 - 配置编辑器](../../media/a7c127f5-9a90-4710-afba-1d1e588efb37.png)
  
4. 单击右侧的页上的**应用**。
    
## <a name="known-issues"></a>已知的问题

在极少数情况下，安装程序无法在 IIS 中创建了正确的设置。 允许用户登录到 CQD 需要手动更改。 如果用户在登录时遇到问题，请按照下列步骤操作：
  
1. 打开启动 IIS 管理器中，然后定位到默认的 Web 站点。
    
     ![部署呼叫质量仪表板](../../media/dc6007aa-870b-4d70-867d-32ffd937063b.png)
  
2. 单击"身份验证"。 如果"匿名身份验证"、"ASP.NET 模拟"、"表单身份验证"和"Windows 身份验证"与以下所示的设置不匹配，手动进行更改以匹配下面的设置。 应禁用所有其他身份验证机制。
    
     ![部署呼叫质量仪表板](../../media/5d9e38fb-8a50-41a2-a423-3ce983a83d0c.png)
  
3. 有关"Windows 身份验证"，请单击高级设置在右侧。
    
     ![部署呼叫质量仪表板](../../media/cad29486-df40-4cc9-82f3-bbdaca52d9ca.png)
  
4. 将"扩展保护"设置为接受，请选中"启用内核模式身份验证"框。
    
     ![部署呼叫质量仪表板](../../media/0ab2dda1-0001-4747-8cfc-072e9368b6cb.png)
  
5. 重复上述步骤为每个"CQD"、"QoEDataService"和"QoERepositoryService"项下"默认 Web 站点"。
    
HTTP 和 HTTPS 端口绑定安装程序将在默认端口号 （端口 80 (http） 和 HTTPS 端口 443 上创建端口绑定。 如果使用这些绑定的计算机上没有另一个网站，将有冲突和无法预测的 IIS 行为。 若要避免此问题的最佳方法是请确保没有其他网站都映射到端口 80 和 443 安装 CQD 之前。 
  
若要启用 SSL/TLS 在 IIS 中，强迫用户通过安全的 HTTPS，而不是 HTTP 连接：
  
1. 在 IIS 中配置安全套接字层，请参见[IIS 7 中配置安全套接字层](https://technet.microsoft.com/en-us/library/cc771438%28v=ws.10%29.aspx)。 完成后，替换`http`与`https`。
    
2. 在 SQL Server 连接启用 TLS 的说明，请参阅[如何启用 SSL 加密技术，通过使用 Microsoft 管理控制台的 SQL Server 的实例](https://support.microsoft.com/en-us/kb/316898/)。
    
### <a name="cube-sync-fails"></a>多维数据集同步失败

QoEMetrics 可能包含一些无效的记录基于最终用户时钟。 如果时间偏差大于 60 年，多维数据集导入将失败。
  
 检查最小和最大值开始时间/结束时间使用下面的选定内容。 寻找和删除记录得过去和很远的将来可以忽略它们，它们会分解同步进程。
  
- 选择 MIN(StartTime) 从 CqdPartitionedStreamView
    
- 选择 MAX(StartTime) 从 CqdPartitionedStreamView
    
- 选择 MIN(EndTime) 从 CqdPartitionedStreamView
    
- 选择 MAX(EndTime) 从 CqdPartitionedStreamView
    
## <a name="post-install-tasks"></a>安装后任务

### <a name="importing-buildings-and-networks"></a>导入建筑物和网络

后安装 CQD，请执行以下配置任务：
  
1. 定义生成类型 （推荐）
    
2. 定义构建所有权类型 （推荐）
    
3. 定义网络类型 （强烈推荐）
    
4. 导入建筑物 （推荐）
    
5. 导入子网 （推荐）
    
### <a name="define-building-types"></a>定义生成类型

建筑类型用于描述不同建筑物定义或您的组织的类型。 
  
> [!NOTE]
> 此步骤是可选的但建议这样做。 
  
示例
  
- 总部
    
- 远程办公室
    
- 合资的位置
    
 **SQL 语法示例**
  
```
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

所有权类型用于区分拥有的与租赁的资产。
  
> [!NOTE]
> 此步骤是可选的但建议这样做。 
  
示例
  
- Contoso 租借非-RE&amp;F
    
- Contoso 租用 RE&amp;F
    
- Contoso 拥有
    
- 租用的子公司
    
 **SQL 语法示例**
  
```
INSERT INTO
[dbo].[CqdBuildingOwnershipType]
([OwnershipTypeId],
[OwnershipTypeDesc],
)

VALUES
(1,
'Contoso Owned',
)
```

OwnershipTypeId 和 OwnershipTypeDesc 参数是必需的。 
  
### <a name="define-network-names"></a>定义网络名称

网络类型用来描述不同类型的组织中的网络。 这使您能够筛选 （或筛选出） 特定网络类型。
  
> [!NOTE]
> 强烈建议来定义网络名称，但它是可选的。 如果您决定定义网络名称，请确保每个 CqdNetwork 条目具有 0 BuildingId。 
  
示例
  
- VPN
    
- 实验室
    
 **SQL 语法示例**
  
```
INSERT INTO [dbo].[CqdNetworkName] 
( [NetworkName]
,[NetworkType]
 ) 
VALUES
('VPN','VPN') 
```

NetworkNameID 和 NetworkName 参数需要，NetworkType 参数是可选的但建议。
  
### <a name="import-buildings"></a>导入建筑物

导入建筑物可以获取生成特定的见解 （每个构建 WiFi/有线等差调用。） 的能力。 
  
> [!NOTE]
> 此步骤是可选的但建议这样做。 
  
在导入之前新构建您应该已经标识预定义的 BuildingKey。 为此，发出"从 CqdBuilding 中选择 MAX(BuildingKey)"SQL 命令，若要确定当前值并添加到结果 1。
  
 **SQL 语法示例**
  
```
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

BuildingKey、 BuildingName、 BuildingShortName、 OwnershipTypeId，BuildingTypeId 参数是必需的其他参数是可选的。
  
### <a name="import-subnets"></a>导入子网

导入建筑物可以获取生成特定的见解 （每个构建 WiFi/有线等差调用。） 的能力。 
  
> [!NOTE]
> 此步骤是可选的但建议这样做。 
  
导入子网，然后将它们映射到的最后一步导入建筑物。 如果您决定不填充 NetworkName，请确保在此表中的每个条目使用 0 NetworkNameID。
  
 **SQL 语法示例**
  
```
INSERT INTO [dbo].[CqdNetwork] 
([Network]
,[NetworkNameID]
,[BuildingKey]
,[UpdatedDate]
)

VALUES
 ('172.16.254.0',0,1,'2015-11-11')
```

网络上，并且 UpdatedDate 参数是必需的其他参数是可选的。
  
### <a name="optional-bssid"></a>可选： BSSID

填充 BSSID 信息为您提供了额外的 WiFi 流关联的控制器或无线电。 这是加上建筑物或子网的筛选。 
  
 **SQL 语法示例**
  
```
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

**CqdBssidTable 的详细信息**

|**CQD 所示**|**CQDBssid 表**|**示例输入**|
|:-----|:-----|:-----|
|Ap NName  <br/> |接入点  <br/> |AP1  <br/> |
|BBssid  <br/> |BSS  <br/> |00-00-00-00-00-00 （必须使用分隔符的 fformat）  <br/> |
|控制器  <br/> |大楼  <br/> |阿鲁巴岛 AP 7  <br/> |
|设备  <br/> |ess  <br/> |Controller1  <br/> |
|无线电  <br/> |phy  <br/> |bgn  <br/> |
   
### <a name="processing-the-imported-data"></a>处理导入的数据

默认情况下，导入构建/网络数据后它将仅适用于生成后的时间点的记录。 
  
标记此新数据与所有以前的记录，您将需要运行 CqdUpdateBuilding 存储过程，如下所示： 
  
为它提供您的第一个记录的日期 （标识使用来自 CqdPartitionedStreamView SQL 选择 MIN(StartTime) 命令），明天，然后最后两个值为空的结束日期。
  
流数据与关联数据后，SSIS 多维数据集必须重新处理的所有记录。 这同样适用时批量添加 BSSID/ISP 数据。 确保选中"全过程"的了。
  

