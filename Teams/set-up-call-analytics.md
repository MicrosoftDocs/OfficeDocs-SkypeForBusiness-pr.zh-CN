---
title: 设置通话分析
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: fbf7247a-84ae-46cc-9204-2c45b1c734cd
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
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
ms.openlocfilehash: ebd5ec0ea60a59e50c3ce7137f518d9a596074a5
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32204809"
---
# <a name="set-up-call-analytics"></a>设置通话分析

为工作组或业务联机管理 Skype，您可以使用调用分析解决 for Business 的 Skype 和 Microsoft 团队呼叫质量和连接问题。 您可能会发现有用设置呼叫分析中的以下功能：
  
- 设置让其他人员，如技术支持代理，请使用调用分析的权限，但禁止访问的 Microsoft 团队管理中心的其余部分。 
    
- 上载.tsv 或.csv 数据文件，可以将构建、 网站和租户信息添加到呼叫分析。
    
**调用分析现已在 Microsoft 团队管理中心**。 若要查看所有呼叫信息和用户的数据，请使用**通话记录**选项卡。您可以通过查看用户配置文件页上，通过执行下列选项之一来执行此操作：

- 搜索仪表板中的用户。
  
   ![屏幕截图的用户搜索仪表板上](media/set-up-call-analytics-image-1.png)

-  左侧导航窗格中，选择**用户**。

   ![左侧导航的屏幕截图](media/set-up-call-analytics-image-2.png)
  
## <a name="set-call-analytics-permissions"></a>设置呼叫分析的权限
<a name="BKMK_SetCAPerms"></a>

作为管理员，必须调用分析的所有功能的完全访问权限。 此外，您可以分配支持人员的 Azure Active Directory 角色。 团队 communications 支持专家角色分配用户应具有有限的呼叫分析视图。 团队 communications 支持工程师角色分配用户需要访问呼叫分析的全部功能。 这两个权限级别防止对其余的 Microsoft 团队管理中心的访问。

> [!NOTE]
> Communications 支持专家角色等同于第 1 层支持它等效于第 2 层支持 communications 支持工程师角色。

有关团队管理员角色的详细信息，请参阅[管理团队使用的 Microsoft 团队管理角色](using-admin-roles.md)。 
  
Communications 支持专家处理基本呼叫质量问题。 他们不调查与会议的问题。 相反，它们收集相关的信息，然后升级到 communications 支持工程师。 Communications 支持工程师请参阅详细的呼叫日志的已隐藏从通信支持专家的信息。 下表提供的信息概述了对通信支持专家和通信支持工程师使用调用分析时。

|**活动**|**呼叫分析中的信息**|**哪些 communications 支持专业人员可以看到**|**哪些 communications 支持工程师可以看到**|
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
||||
   
 ### <a name="set-up-permissions-by-assigning-admin-roles"></a>设置通过分配管理员角色的权限
<a name="BKMK_SetUpTier"> </a>

若要了解如何为 Azure Active Directory 中的管理角色分配，请参阅[在 Azure Active Directory 中的视图和分配角色](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-manage-roles-portal)。

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a>上载.tsv 或.csv 文件添加生成，网站和租户信息
<a name="BKMK_UploadFiles"> </a>

可以通过上载.csv 或.tsv 文件构建、 网站和租户信息添加到呼叫分析。 与所有此类信息呼叫分析可以将 IP 地址映射到物理位置。 您或帮助台代理可能会发现有用帮助呼叫问题中的专色趋势的此信息。 例如，为什么很多用户在同一构建具有类似呼叫质量问题？ 

如果您是团队和 Skype 对于业务管理员，您可以使用团队 & Skype 从现有数据文件对于业务呼叫质量仪表板。 首先，呼叫质量仪表板中下载文件，然后将其上载到呼叫分析。 

- 若要下载现有数据文件，转到**Microsoft 团队管理中心** > **呼叫质量仪表板** > **立即上载**。 在**我上载**列表中，单击所需的文件旁边的**下载**。

- 若要上载的新文件，转到**Microsoft 团队管理中心** > **位置**，然后选择**上载位置数据**或**替换位置数据**。
  
如果您正在从头创建.tsv 或.csv 文件，请参阅[租户数据文件格式和构建数据文件结构](turning-on-and-using-call-quality-dashboard.md#BKMKTenantDataFile)。
  
## <a name="related-topics"></a>相关主题
<a name="BKMK_UploadFiles"> </a>

[使用通话分析来排查通话质量不良问题](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[通话分析和通话质量仪表板](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 
