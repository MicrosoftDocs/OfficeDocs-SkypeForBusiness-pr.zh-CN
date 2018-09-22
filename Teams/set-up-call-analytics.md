---
title: 设置呼叫分析
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: ''
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
search.appverid: MET150
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: 设置和使用调用分析确定并解决 Skype 的业务和 Microsoft 团队呼叫质量问题。
ms.openlocfilehash: de2484dac64623ed3f37c544877d48187f5ca5f9
ms.sourcegitcommit: 63a560c05b4fa3bda3abc31ef5dffe60e61e4d67
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/21/2018
ms.locfileid: "24961001"
---
# <a name="set-up-call-analytics"></a>设置呼叫分析

为业务联机管理 Skype，您可以使用调用分析解决 for Business 的 Skype 和 Microsoft 团队呼叫质量和连接问题。 您可能会发现有用设置呼叫分析中的以下功能：
  
- 设置让其他人员，如技术支持代理，请使用调用分析的权限，但禁止访问业务管理中心的 Skype 的其余部分。 
    
- 上载.tsv 或.csv 数据文件，可以将构建、 网站和租户信息添加到呼叫分析。
    
**呼叫分析现已推出中的 Microsoft 团队和 Skype 的业务 Admin Center。** 若要查看的所有呼叫信息和用户的数据，请使用**通话记录**选项卡。您可以通过仪表板用户可以搜索用户的配置文件页上查找或**用户**的左侧导航中查找用户执行此操作。

> [!IMPORTANT]
> 帮助台代理权限和网络拓扑上载中将提供新的管理门户在几个月。 同时，您可以继续使用https://adminportal.services.skypeforbusiness.com1 层和第 2 层帮助台访问。
  
## <a name="set-call-analytics-permissions"></a>设置呼叫分析的权限
<a name="BKMK_SetCAPerms"></a>

作为管理员，您获取的呼叫分析的所有功能的完全访问权限。 此外，您可以使用帮助台模型中包括层 1 和 2 层权限组的呼叫的分析。 具有 1 层权限的用户可以访问仅有限的呼叫分析视图。 第 2 层权限的用户可以访问呼叫分析的全部功能。 这两个权限级别防止对其余的 Microsoft 团队和 Skype 业务管理中心的访问。 您可以通过添加包含到 Tier 1 或权限页上的第 2 层一部分用户组授予对层的访问。 有关详细信息，请参阅[设置呼叫分析中的分层权限](set-up-call-analytics.md#BKMK_SetUpTier)。
  
第 1 层帮助台代理处理基本呼叫质量问题。 第 1 层代理不调查问题与会议;它们收集相关的信息，然后升级到第 2 层代理。 第 2 层代理，请参阅详细的呼叫日志的从 1 层代理处于隐藏状态的信息。 下表概述了至代理使用调用分析的可用信息。


|**活动**|**呼叫分析中的信息**|**第 1 层代理所看到的内容**|**第 2 层代理所看到的内容**|
|:-----|:-----|:-----|:-----|
|**呼叫** <br/> |呼叫者姓名  <br/> |仅为其代理搜索的用户的名称。  <br/> |用户名。  <br/> |
||收件人的姓名  <br/> |显示为内部用户或外部用户。  <br/> |收件人姓名。  <br/> |
||呼叫方电话号码  <br/> |除最后三个数字的完整的电话号码是模糊处理星号符号。 例如，15552823 ***。  <br/> |除最后三个数字的完整的电话号码是模糊处理星号符号。 例如，15552823 ***。  <br/> |
||收件人的电话号码  <br/> |除最后三个数字的完整的电话号码是模糊处理星号符号。 例如，15552823 ***。  <br/> |除最后三个数字的完整的电话号码是模糊处理星号符号。 例如，15552823 ***。  <br/> |
||**呼叫详细信息** > **高级**选项卡 <br/> |不显示的信息。  <br/> |所示，如设备名称、 IP 地址、 子网映射和更多的所有详细信息。  <br/> |
||**呼叫详细信息** > **高级** > **调试**选项卡 <br/> |不显示的信息。  <br/> |所示，如 DNS 后缀和 SSID 的所有详细信息。  <br/> |
|**会议** <br/> |参与者姓名  <br/> |仅为其代理搜索的用户的名称。 标识为内部用户或外部用户的其他参与者。  <br/> |显示所有名称。  <br/> |
||参与者计数  <br/> |参与者数目。  <br/> |参与者数目。  <br/> |
||会话详细信息  <br/> |显示例外的会话详细信息。 仅为其显示搜索的代理的用户的名称。 标识为内部用户或外部用户的其他参与者。 最后三个星号符号模糊处理的电话号码的数字。  <br/> |显示的会话详细信息。 用户的用户名和显示的会话详细信息。 最后三个星号符号模糊处理的电话号码的数字。  <br/> |
   
 **设置呼叫分析中的分层权限**
 <a name="BKMK_SetUpTier"> </a>

![sfb-徽标-30x30.png](media/sfb-logo-30x30.png) **使用的 Microsoft 团队和 Skype 的业务管理中心**
  
1. 第 1 层和第 2 层中创建 Office 365 安全组，并将所需的人员添加到每个组。 您还可以重用现有的安全组。 有关详细信息，请参阅[在 Office 365 管理中心中创建、编辑或删除安全组](https://support.office.com/article/55c96b32-e086-4c9e-948b-a018b44510cb)。
    
2. 在 Office 365 管理中心，转到**管理中心** > **for Business 的 Skype**。

    > [!NOTE]
    > 如果您使用的**Microsoft 团队和 Skype 的业务管理中心**，在左侧导航窗格中，单击**旧门户**。
  
3. 选择**工具** > **商业调用分析 （预览） 的 Skype** > **设置**，然后单击**权限**。
    
4. 将 Office 365 安全组添加到**Tier 1**和**2 层**框中。 您可以将多个组添加到每个角色。
    
     ![屏幕快照显示了调用分析页层 1 和 2 层权限的选项的权限。](media/setup-call-analytics-image1.png)
  
 具有这些权限级别之一的用户获取对呼叫的分析通过专用 URL *https://adminportal.services.skypeforbusiness.com*。
  
## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a>上载.tsv 或.csv 文件添加生成，网站和租户信息
<a name="BKMK_UploadFiles"> </a>

可以通过上载.csv 或.tsv 文件构建、 网站和租户信息添加到呼叫分析。 与所有此类信息呼叫分析可以将 IP 地址映射到物理位置。 您或帮助台代理可能会发现有用帮助呼叫问题中的专色趋势的此信息。 例如，为什么很多用户在同一构建具有类似呼叫质量问题？ 
  
![屏幕快照显示了网站页的网站数量和子网，数值和选择文件按钮上载.tsv 或.csv 文件导入网站数据。](media/b2f3a5cb-32b5-4f60-a9af-0691aa6ff1e8.png)
  
如果您的业务管理 Skype，您可以使用 Skype 从现有数据文件对于业务联机呼叫质量的仪表板。 首先，呼叫质量仪表板中下载文件，然后将其上载到呼叫分析。 若要下载现有数据文件，请转到**业务管理中心的 Skype** > **工具** > **业务联机呼叫质量仪表板的 Skype** > **立即上载**。 在**我上载**列表中，单击所需的文件旁边的**下载**。
  
如果您正在从头创建.tsv 或.csv 文件，请参阅[租户数据文件格式和构建数据文件结构](turning-on-and-using-call-quality-dashboard.md#BKMKTenantDataFile)。
  
## <a name="related-topics"></a>相关主题
<a name="BKMK_UploadFiles"> </a>

[使用通话分析解决通话质量不佳的问题](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[呼叫分析和呼叫质量仪表板](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 
