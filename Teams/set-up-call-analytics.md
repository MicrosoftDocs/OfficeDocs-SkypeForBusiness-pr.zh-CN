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
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
description: 设置和使用呼叫分析来识别 Skype for Business 和 Microsoft 团队通话质量问题，并对其进行故障排除。
ms.openlocfilehash: fe46ee580554969d26395b26117649ab8ada2ea0
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41838052"
---
# <a name="set-up-call-analytics"></a>设置通话分析

作为团队或 Skype for Business Online 管理员，您可以使用呼叫分析对 Skype for Business 和 Microsoft 团队通话质量和连接问题进行故障排除。 你可能会发现在调用分析中设置以下功能非常有用：
  
- 设置允许其他人员（如帮助台代理）使用呼叫分析的权限，但阻止他们访问 Microsoft 团队管理中心的其余部分。 
    
- 通过上载 tsv 或 .csv 数据文件，将生成、网站和租户信息添加到调用分析。
    
**"呼叫分析" 现在可在 Microsoft 团队管理中心中使用**。 若要查看用户的所有呼叫信息和数据，请使用 "**通话记录**" 选项卡。你可以通过执行下列操作之一，通过查看用户的配置文件页面来执行此操作：

- 从仪表板中搜索用户。
  
   ![仪表板上的用户搜索的屏幕截图](media/set-up-call-analytics-image-1.png)

-  在左侧导航中选择 "**用户**"。

   ![左侧导航的屏幕截图](media/set-up-call-analytics-image-2.png)
  
## <a name="set-call-analytics-permissions"></a>设置呼叫分析权限
<a name="BKMK_SetCAPerms"></a>

作为管理员，你拥有对呼叫分析的所有功能的完全访问权限。 此外，你可以将 Azure Active Directory 角色分配给支持人员。 将团队通信支持专家角色分配给应具有有限视图的调用分析的用户。 将团队通信支持工程师角色分配给需要访问调用分析的完整功能的用户。 这两个权限级别阻止访问 Microsoft 团队管理中心的其余部分。

> [!NOTE]
> 通信支持专家角色等效于第1层支持，而通信支持工程师角色等效于第2层支持。

有关团队管理员角色的详细信息，请参阅[使用 Microsoft 团队管理员角色管理团队](using-admin-roles.md)。 
  
通信支持专家处理基本的通话质量问题。 他们不会调查会议问题。 而是收集相关信息，然后升级到通信支持工程师。 通信支持工程师查看有关通信支持专家隐藏的详细通话记录中的信息。 下表简要介绍了在使用呼叫分析时，通信支持专家和通信支持工程师可使用的信息。

|**活动**|**通话分析中的信息**|**通信支持专家可以看到的内容**|**通信支持工程师看到的内容**|
|:-----|:-----|:-----|:-----|
|**呼叫** <br/> |呼叫者姓名  <br/> |仅限代理搜索的用户的名称。  <br/> |用户名。  <br/> |
||收件人姓名  <br/> |显示为内部用户或外部用户。  <br/> |收件人姓名。  <br/> |
||呼叫方电话号码  <br/> |除最后三位数字之外的整个电话号码都被用星号符号混淆。 例如，15552823 * * *。  <br/> |除最后三位数字之外的整个电话号码都被用星号符号混淆。 例如，15552823 * * *。  <br/> |
||收件人电话号码  <br/> |除最后三位数字之外的整个电话号码都被用星号符号混淆。 例如，15552823 * * *。  <br/> |除最后三位数字之外的整个电话号码都被用星号符号混淆。 例如，15552823 * * *。  <br/> |
||**"呼叫详细信息** > "**高级**选项卡 <br/> |未显示信息。  <br/> |显示所有详细信息，如设备名称、IP 地址、子网映射等。  <br/> |
||**"呼叫详细信息** > "**高级** > "**调试**" 选项卡 <br/> |未显示信息。  <br/> |显示所有详细信息，如 DNS 后缀和 SSID。  <br/> |
|**会议** <br/> |参与者姓名  <br/> |仅限代理搜索的用户的名称。 标识为内部用户或外部用户的其他参与者。  <br/> |显示所有名称。  <br/> |
||参与者计数  <br/> |参与者的数量。  <br/> |参与者的数量。  <br/> |
||会话详细信息  <br/> |与异常一起显示的会话详细信息。 仅显示对其进行代理搜索的用户的名称。 标识为内部用户或外部用户的其他参与者。 用星号符号进行混淆的电话号码的最后三位数字。  <br/> |显示的会话详细信息。 显示的用户名和会话详细信息。 用星号符号进行混淆的电话号码的最后三位数字。  <br/> |
||||
   
 ### <a name="set-up-permissions-by-assigning-admin-roles"></a>通过分配管理员角色设置权限
<a name="BKMK_SetUpTier"> </a>

若要了解如何在 Azure Active Directory 中分配管理角色，请参阅[在 Azure Active directory 中查看和分配角色](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-manage-roles-portal)。

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a>上载 tsv 或 .csv 文件以添加建筑物、网站和租户信息
<a name="BKMK_UploadFiles"> </a>

你可以通过上载 .csv 或 tsv 文件，将生成、网站和租户信息添加到调用分析。 有了所有这些信息，呼叫分析可以将 IP 地址映射到物理位置。 您或帮助台工程师可能会发现此信息有助于发现通话问题的趋势。 例如，为什么同一建筑物中的许多用户有类似的通话质量问题？ 

如果你是团队和 Skype for business 管理员，则可以使用来自 & Skype for business 通话质量仪表板的团队中的现有数据文件。 首先，从 "呼叫质量" 仪表板下载文件，然后将其上传到 "调用分析"。 

- 若要下载现有数据文件，请转到**Microsoft 团队管理中心** > **呼叫质量仪表板** > "**立即上载**"。 在 "**我的上载**" 列表中，单击所需文件旁边的 "**下载**"。

- 若要上传新文件，请转到 " **Microsoft 团队管理中心** > "**位置**，然后选择 "**上载位置数据**" 或 "**替换位置数据**"。
  
如果要从头开始创建 tsv 或 .csv 文件，请参阅[租户数据文件格式和生成数据文件结构](turning-on-and-using-call-quality-dashboard.md#BKMKTenantDataFile)。
  
## <a name="related-topics"></a>相关主题
<a name="BKMK_UploadFiles"> </a>

[使用通话分析来排查通话质量不良问题](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[通话分析和通话质量仪表板](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 
