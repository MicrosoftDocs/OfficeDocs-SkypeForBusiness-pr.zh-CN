---
title: 在 Skype for Business Server 2015 中使用呼叫质量仪表板
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ec62b70f-885e-4272-b9d2-a574ea434b64
description: 摘要： 了解有关如何使用调用质量面板。 通话质量仪表板是用于业务服务器 2015年的 Skype 的工具。
ms.openlocfilehash: c4d67088fc11e05d6880d80da714f3268e0e7e2d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="use-call-quality-dashboard-for-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中使用呼叫质量仪表板
 
**摘要：**了解有关如何使用调用质量面板。 通话质量仪表板是用于业务服务器 2015年的 Skype 的工具。
  
CQD 允许 IT 专业人员使用聚合数据来识别其环境中遇到媒体质量问题的重点关注区域。它允许 IT 专业人员比较不同用户组的统计信息，并识别趋势和模式。它重点关注的不是单个通话问题，而是识别适用于给定环境中许多用户的问题和解决方案。
  
## <a name="call-quality-dashboard-user-guide"></a>呼叫质量仪表板用户指南

呼叫质量仪表板 (CQD) 是一个用于根据用户体验质量 (QoE) 数据快速创建并组织报告的 Web 门户。CQD 部署 SSAS 多维数据集以将数据聚合在 QoE 指标数据库中。这样，用户能够实时创建并修改报告，以及进行调查。虽然可以使用 Excel 直接连接到多维数据集，但门户已针对涉及 QoE 数据的几个工作流进行了优化。这些数据包括：用于实现快速访问的报告数据缓存、用于信息共享和发布的报告页面深层链接、简化的报告编辑和创建以及用于报告说明的可编辑元数据。此外，CQD 还提供 Web API，允许用户以编程方式访问多维数据集数据以用于自定义仪表板。 
  
### <a name="feature-overview"></a>功能概述

用户访问呼叫质量仪表板时，他/她将看见以下内容：
  
![使用 CQD](../../media/1e061858-db6f-452b-9ae4-eab507220371.png)
  
1. "摘要窗格"是可在其中找到"报表设置"（右边） 的上下文。 
    
2. 报告可以通过单击摘要窗格中的"编辑"设置组级别的属性 （包括 y 轴高度）。
    
3. 痕迹导航可帮助用户确定其在报告集层次结构中的当前位置。 
    
4. 有子报告的报告会显示一个蓝色链接。单击链接将向下钻取到子报告。 
    
将光标移到条形图上时，趋势线将会显示详细值。 具有焦点的报表将显示操作菜单:"编辑"、"克隆"、"删除"和"下载"。 
  
### <a name="default-reports"></a>默认报告

用户首次访问呼叫质量仪表板门户时，会自动创建一组默认的报告。这些报告有时称为系统报告。用户能够任意修改或删除这些报告。通常，用户通过创建新的同级报告和子报告来扩展这些报告。 
  
在顶层，"音频流每月趋势"报表显示每月的所有音频流的趋势。 将光标移到条形图中的条形上时，将显示条形图所表示数据的更详细视图。 单击音频流每月趋势报告的标题上将导航到"托管与非托管的音频流"报表，其中报表都分为托管和非托管的调用。 管理呼叫是从公司防火墙内通过有线连接进行的呼叫。 非管理呼叫包括从公司防火墙外进行的呼叫以及通过 Wi-Fi 进行的所有呼叫。
  
其他高级别报告称为"用户报告通话质量分级直方图。" 呼叫质量评级是 Skype for Business 用户在呼叫结束时提供用来指示通话质量的数字。 评级数字范围从 1 到 5，1 表示最差，5 表示最佳。 直方图显示一个月中具有指示评级的音频通话数。 
  
通常，单击任何报告标题将导航到具有额外数据筛选器的报告。在系统报告中，每个子报告显示其父报告中的一部分数据。这提供了一个用于解决问题的概念简单的模式：通过调查有问题的数据或趋势所属的子报告来缩小问题范围。由于能够创建新的子报告，用户可以针对特定数据趋势的来源调查其自己的假设。
  
### <a name="creating-and-editing-reports"></a>创建和编辑报告

当在报表的操作菜单，单击"编辑"，用户将看到报告编辑器。 每个报告都可以通过对多维数据集进行查询得到。 报告是其查询返回的数据的可视化形式。 报告编辑器是用于编辑这些查询的用户界面，并包含报告的显示选项。 用户打开报告编辑器时，他/她将看见以下内容：
  
![使用 CQD](../../media/e8969625-e6f9-4d67-873f-93e78dd12b35.png)
  
1. 左侧窗格中选择了维度、度量和筛选器。 悬停在某个现有值将显示一个"x"按钮，允许值中删除。 单击标题旁的"加号"按钮将会打开添加新的维度、 度量值或筛选器对话框。 
    
2. 顶部显示了图表自定义选项。
    
3. 报告编辑器中提供了报告预览。 
    
4. 可使用底部的编辑框创建详细报告说明。 
    
### <a name="sparklines-in-tables"></a>表中的迷你图

将 StartDate.Month 添加为一个维度，且数据以表格形式呈现为趋势时，可以在表格单元格内显示条形图和迷你图。将鼠标指针移到条形图和迷你图上将显示单个月的值。 
  
![使用 CQD](../../media/fe6b18d7-b8cf-472a-9c93-0f7703f5a700.png)
  
为了显示条形图和迷你图，必须检查报告编辑器顶部的"显示迷你图"复选框。 这将选中“趋势”选项，并将“月份”下移为最后一个维度，这也可以通过单击“月份”并使用向上和向下箭头上移或下移 StartDate.Month 来完成。 
  
### <a name="settings"></a>设置

设置菜单位于仪表板的右上角，其包含了有用页面（比如“系统运行状况”和“关于”页面）的链接。
  
![使用 CQD](../../media/0e9ae123-e231-4fea-94e1-5788e8f3e1d3.png)
  
显示说明和时间戳将由单个用户，且这些设置只会影响个人的仪表板的版本，不修改报表设置或其他用户看到。 清除缓存会导致所有查询从多维数据集重新加载其数据，而恢复默认设置将删除用户创建或修改的所有报告，并重新创建系统报告集 - 用户首次登录时看到的内容。
  
用户仪表板链接显示用户可以在其中查看 CQD 的其他用户并浏览其报告的页面。 共享报告集时，只需复制 URL 栏中的链接并与另一个 CQD 用户共享该链接即可。 此链接将是相同的一个用户将看到在用户仪表板的链接页面中用户的用户名下。
  
### <a name="supplying-subnet-information"></a>提供子网信息

如果在存档数据库中输入了特定于站点的信息以提供子网到大楼的映射信息（例如，按大楼的有线/无线呼叫质量），则可以显示其他分析内容。 
  
至少，需要填写以下表格才能创建这些报告：
  
- CqdBuilding
    
- CqdNetwork
    
可在 CqdBuildingType 和 CqdBuildingOwnershipType 表中提供其他信息以进行进一步的筛选和向下钻取。 
  
这些表的架构采用如下定义：
  
**CqdBuilding**

|**列**|**数据类型**|**允许空值？**|**详细信息**|
|:-----|:-----|:-----|:-----|
|BuildingKey  <br/> |int  <br/> |否  <br/> |CqdBuilding 表的主键。  <br/> |
|BuildingName  <br/> |varchar(80)  <br/> |否  <br/> |大楼名称。  <br/> |
|BuildingShortName  <br/> |varchar(10)  <br/> |否  <br/> |大楼名称的简短版本。  <br/> |
|OwnershipTypeId  <br/> |int  <br/> |否  <br/> |外键，应与 CqdBuildingOwners 表中的其中一个条目匹配。  <br/> |
|BuildingTypeId  <br/> |int  <br/> |否  <br/> |外键，应与 CqdBuildingType 表中的其中一个条目匹配。  <br/> |
|纬度  <br/> |float  <br/> |是  <br/> |大楼的纬度。  <br/> |
|经度  <br/> |float  <br/> |是  <br/> |大楼的经度。  <br/> |
|CityName  <br/> |varchar(30)  <br/> |是  <br/> |大楼所在的城市名称。  <br/> |
|邮政编码  <br/> |varchar(25)  <br/> |是  <br/> |大楼所在的邮编。  <br/> |
|CountryShortCode  <br/> |varchar(2)  <br/> |是  <br/> |大楼所在的国家/地区的 ISO 3166-1 alpha-2 代码。  <br/> |
|StateProvinceCode  <br/> |varchar(3)  <br/> |是  <br/> |大楼所在的省/市/自治区的 3 字母缩写。  <br/> |
|InsideCorp  <br/> |bit  <br/> |是  <br/> |指明大楼是否是企业网络一部分的 bit（位）。  <br/> |
|BuildingOfficeType  <br/> |nvarchar(150)  <br/> |是  <br/> |大楼办公室类型的说明。  <br/> |
|区域  <br/> |varchar(25)  <br/> |是  <br/> |大楼所在的地区。  <br/> |
   
**CqdNetwork**

|**列**|**数据类型**|**允许空值？**|**详细信息**|
|:-----|:-----|:-----|:-----|
|网络  <br/> |varchar(25)  <br/> |否  <br/> |子网地址。  <br/> |
|NetworkRange  <br/> |tinyint  <br/> |是  <br/> |子网掩码。  <br/> |
|NetworkNameID  <br/> |int  <br/> |是  <br/> |可选地映射到 CqdNetworkName 表中的一行。  <br/> |
|BuildingKey  <br/> |int  <br/> |是  <br/> |外键，应与 CqdBuilding 表中的其中一个条目匹配。  <br/> |
|UpdatedDate  <br/> |datetime  <br/> |否  <br/> |条目最后更新的日期时间。  <br/> |
   
默认情况下此下一个表有一个条目 (0，未知)。
  
**CqdBuildingType**

|**列**|**数据类型**|**允许空值？**|**详细信息**|
|:-----|:-----|:-----|:-----|
|BuildingTypeId  <br/> |int  <br/> |否  <br/> |CqdBuildingType 表的主键。  <br/> |
|BuildingTypeDesc  <br/> |char(18)  <br/> |否  <br/> |大楼类型说明。  <br/> |
   
默认情况下此下一步的表中有一个条目 (0，'未知'，0，则为 null)。
  
**CqdBuildingOwnershipType**

|**列**|**数据类型**|**允许空值？**|**详细信息**|
|:-----|:-----|:-----|:-----|
|OwnershipTypeId  <br/> |int  <br/> |否  <br/> |CqdBuildingOwnershipType 表的主键。  <br/> |
|OwnershipTypeDesc  <br/> |varchar(25)  <br/> |否  <br/> |所有权类型说明。  <br/> |
|LeaseInd  <br/> |tinyint  <br/> |是  <br/> |引用 CqdBuildingOwnershipType 表中其他行的索引，用于确定租用的大楼。  <br/> |
|所有者  <br/> |varchar(50)  <br/> |是  <br/> |大楼所有者。  <br/> |
   
默认情况下此下一步的表中有一个条目 (0，'未知'，0，则为 null)。
  
**CqdBssid**

|**列**|**数据类型**|**允许空值？**|**详细信息**|
|:-----|:-----|:-----|:-----|
|bss  <br/> |nvarchar(50)  <br/> |否  <br/> |CqdBssid 表的主键。是 WiFi 接入点的 BSSID。  <br/> |
|ess  <br/> |nvarchar(50)  <br/> |是  <br/> |WiFi 接入点控制器信息。  <br/> |
|phy  <br/> |nvarchar(50)  <br/> |是  <br/> |Phy 信息。  <br/> |
|ap  <br/> |nvarchar(50)  <br/> |是  <br/> |WiFi 接入点名称。  <br/> |
|大楼  <br/> |nvarchar(500)  <br/> |是  <br/> |WiFi 接入点所在大楼名称。  <br/> |
   
## <a name="cqd-streams"></a>CQD 流

CQD 流将为良好、较差或未分类。CQM 1.5 现在使用以下 CQD 定义： 
  
- 较差流是超过阈值的较差呼叫指标的任意组合。
    
- 差一个流中调用时，调用这两种流是标记很差。 在会议中，每个参与者被视为唯一的呼叫，并报告上独立于所有其他人。
    
- 未分类流是没有质量指标（即综合事务、短时间通话）的流。
    
- 有效流 = 非移动客户端
    
- 分类器不能修改
    
**较差的调用定义分类器**

|**跃点计数**|**阈值**|
|:-----|:-----|
|DDegradationAvg  <br/> |大于 1.0（-1 网络 MOS）  <br/> |
|往返  <br/> |大于 500   <br/> |
|PacketLossRate  <br/> |大于 .1 (10%)   <br/> |
|JitterInterArrival  <br/> |大于 30   <br/> |
|RRatioConcealedSamplesAvg  <br/> |大于 .07   <br/> |
   
JPDR 定义 = 较差呼叫定义减去 RatioConcealedSamplesAvg  
  
## <a name="where-is-callercallee"></a>呼叫方/被呼叫方在哪里？

CQD 不使用调用方/被调用方的域。 因为有调用方和被调用方之间的中间步骤，这些已被更名为"第一"和"第二"。
  
 
            如果流中涉及服务器，则**第一个**将始终是服务器端点（例如 AV MCU；中介服务器）。
  
 **第二个**将始终是客户端端点，除非是服务器-服务器流。
  
**第一和第二个分类的示例**

|**终结点 1 UAType**|**终结点 2 UUAType**|**第一个**|**第二个**|
|:-----|:-----|:-----|:-----|
|2 (AVMCU)   <br/> |4 (Skype for Business)   <br/> |端点 1  <br/> |端点 2  <br/> |
|2 (AVMCU)   <br/> |1 (mMediationServer)   <br/> |端点 2  <br/> |端点 1  <br/> |
|4 (Skype for Business)   <br/> |4 (Skype for Business)   <br/> |MediaLine 中的呼叫方   <br/> |MMediaLine 中的被呼叫方  <br/> |
   
如果两个端点是相同类型，CQD 将“呼叫方”条目设为“第一个”，而“被呼叫方”则为“第二个”。 [此博客](https://blogs.technet.com/b/jenstr/archive/2015/05/22/call-quality-dashboard-tips-and-tricks.aspx)的详细信息，请参阅。
  
## <a name="accounting-for-vpn"></a>VPN 考虑事项

如果 VPN 解决方案已知准确地设置 VPN 标志，就可以了。 否则，请使用下列方法之一：
  
- 创建名为 VPN 的网络类型（首选），然后将 VPN 子网与此新 VPN 网络类型关联。
    
- 创建名为 VPN 的大楼，然后将 VPN 子网与此大楼关联。 
    
## <a name="query-fundamentals"></a>查询基础知识

格式正确的查询包含以下三个参数： 
  
- 度量
    
- 维度
    
- 筛选器
    
例如，“按子网[维度]显示大楼 6 [筛选器]的较差流[度量]”是一个格式正确的查询。
  
## <a name="what-does-union-do"></a>“联合”起什么作用？

通过“联合”可以使用“与”运算符筛选条件。在一些方案中，你需要将多个筛选条件组合在一起来获得类似“或”的结果。
  
例如，当你需要从大楼获取所有流时，“联合”将提供合并数据集的独特视图。要使用“联合”，请在你要联合的两个筛选条件上的“联合”字段中插入普通文本。 
  
## <a name="default-report-breakdown"></a>默认报告细分

如果在内部管理无线，你可以在管理存储桶中重新创建“无线”报告。 
  
![CQD 报告细分](../../media/658b8568-0d68-4f5f-83e8-5abc63a85c1d.png)
  
## <a name="operational-processes"></a>可选过程

首先查看并更正管理流。此区域中的质量应该完全在你的控制范围内，因此最容易修复。 
  
### <a name="managed-streams"></a>管理流 

按以下顺序查看并更正管理流： 
  
1. 服务器-服务器  
    
2.   服务器-有线-内部
    
3. 有线-有线-内部  
    
### <a name="unmanaged-streams"></a>非管理流

按以下顺序查看并更正非管理流： 
  
1. 服务器-WiFi-内部
    
2. 服务器-有线-外部
    
3. 服务器-WiFi-外部
    
4. 有线-外部-直接
    
5. 有线-外部-中继
    
6. 其他非管理
    

