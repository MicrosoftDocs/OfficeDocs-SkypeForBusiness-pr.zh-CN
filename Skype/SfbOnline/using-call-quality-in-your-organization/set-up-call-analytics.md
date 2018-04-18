---
title: Skype 业务调用分析设置
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: ''
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: 设置和使用调用分析来识别和解决 Skype 的通话质量问题，业务和 Microsoft 小组。
ms.openlocfilehash: 6e4566198e140c94da40f4db1a890eb4190d5da3
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="set-up-skype-for-business-call-analytics"></a>Skype 业务调用分析设置

Skype 的在线业务的管理，您可以使用调用分析来解决 Skype 业务以及 Microsoft 小组呼叫质量和连接问题。 您可能会发现有用设置调用分析中的以下功能：
  
- 设置权限让其他人员，如帮助台代理，请使用调用的分析，但阻止其访问业务管理中心的 Skype 的其余部分。 
    
- 通过上传数据的文件.tsv 或.csv 文件，可以将建筑物、 站点和组织信息添加到调用分析。
    
> [!NOTE]
> 调用分析目前在预览中。 文本和此处所述的图像可能会不匹配您的体验。 
  
## <a name="set-call-analytics-permissions"></a>设置调用分析权限
<a name="BKMK_SetCAPerms"></a>

作为管理员，您获得的调用分析的所有功能的完全访问权限。 此外，可以使用中包括的权限组，第 1 层和 2 层的调用分析帮助台模型。 使用第 1 层的权限的用户可以访问只片面调用分析。 使用第 2 层的权限的用户可以访问调用分析的全部功能。 这两种权限级别对业务管理中心的 Skype 的其余部分阻止访问。 您可以通过添加包含到第 1 层或 2 层部分中的权限页面的用户的组授予访问层。 有关详细信息，请参阅[设置分层调用分析中的权限](set-up-call-analytics.md#BKMK_SetUpTier)。
  
第 1 层支持人员代理处理呼叫质量的基本问题。 第 1 层工程师不调查问题的会议;它们收集相关的信息，然后就汇报给第 2 层工程师。 第 2 层工程师请参阅详细的电话记录中的信息隐藏的第 1 层工程师。 下表概述了为代理使用调用分析可用的信息。


|**活动**|**在调用分析信息**|**第 1 层工程师所看到的内容**|**第 2 层工程师所看到的内容**|
|:-----|:-----|:-----|:-----|
|**呼叫** <br/> |呼叫者姓名  <br/> |只为其代理搜索的用户的名称。  <br/> |用户的姓名。  <br/> |
||收件人姓名  <br/> |显示为内部用户或外部用户。  <br/> |收件人的姓名。  <br/> |
||呼叫方电话号码  <br/> |使用星号符号对，除了后三位的完整的电话号码进行模糊处理。 例如，15552823 ***。  <br/> |使用星号符号对，除了后三位的完整的电话号码进行模糊处理。 例如，15552823 ***。  <br/> |
||收件人电话号码  <br/> |使用星号符号对，除了后三位的完整的电话号码进行模糊处理。 例如，15552823 ***。  <br/> |使用星号符号对，除了后三位的完整的电话号码进行模糊处理。 例如，15552823 ***。  <br/> |
||**呼叫的详细记录** > **高级**选项卡 <br/> |不显示信息。  <br/> |所示，如设备名称、 IP 地址、 子网映射和所有详细信息。  <br/> |
||**呼叫的详细记录** > **高级** > **调试**选项卡 <br/> |不显示信息。  <br/> |所示，如 DNS 后缀和 SSID 的所有详细信息。  <br/> |
|**会议** <br/> |参与者名称  <br/> |只为其代理搜索的用户的名称。 标识为内部用户或外部用户的其他参与者。  <br/> |所示的所有名称。  <br/> |
||参与者计数  <br/> |参与者的数量。  <br/> |参与者的数量。  <br/> |
||会话详细信息  <br/> |会话详细信息显示有例外。 只为其代理搜索的用户的显示名称。 标识为内部用户或外部用户的其他参与者。 最后三位数字电话号码替换为星号符号进行模糊处理。  <br/> |会话详细信息显示。 用户名和会话详细信息显示。 最后三位数字电话号码替换为星号符号进行模糊处理。  <br/> |
   
 **设置调用分析中的分层权限**
 <a name="BKMK_SetUpTier"> </a>
  
1. 第 1 层和 2 层，为创建 Office 365 安全组，并向每个组中添加所需的人员。 您还可以重用现有的安全组。 有关详细信息，请参阅[在 Office 365 管理中心中创建、编辑或删除安全组](https://support.office.com/article/55c96b32-e086-4c9e-948b-a018b44510cb)。
    
2. 在 Office 365 管理中心，转到**管理中心** > **业务的 Skype**。
    
    > [!NOTE]
    > 如果您居住在旧 Skype 的业务管理中心，请通过单击**来尝试我们的新管理中心**转到新版本。 
  
3. 在业务管理中心新 Skype，单击**权限**。
    
4. 将 Office 365 安全组添加到**第 1 层**和**2 层**框。 您可以为每个角色添加多个组。
    
     ![屏幕抓图显示了使用第 1 层和 2 层权限选项调用分析页面的权限。](../images/ed5b6b05-b407-4363-8cf0-a6e79027f64b.png)
  
 与这些权限级别的用户到达通过专用的 URL 调用分析*https://adminportal.services.skypeforbusiness.com*。
  
## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a>传.tsv 或.csv 文件添加构建，站点，和租户信息
<a name="BKMK_UploadFiles"> </a>

可以通过上传的.tsv 或.csv 文件构建、 站点和组织信息添加到调用分析。 与所有此类信息调用分析可以将 IP 地址映射到物理位置。 您或技术支持工程师可能会发现此信息有助于发现在呼叫问题的趋势。 例如，为什么很多用户在同一建筑内有类似呼叫质量问题？ 
  
![屏幕抓图显示了具有多站点和子网的数量值网站页和选择文件按钮来上载.tsv 或.csv 文件导入网站数据。](../images/b2f3a5cb-32b5-4f60-a9af-0691aa6ff1e8.png)
  
如果 Skype 业务管理员，您可以使用现有数据文件从 Skype 业务在线呼叫质量仪表板 首先，从呼叫质量面板，下载该文件，然后您将其上载到调用分析。 要下载一个现有的数据文件，请转至**业务管理中心的 Skype** > **工具** > **Skype 业务在线呼叫质量仪表板** > **立即上载**。 在**我上载**列表中，单击所需的文件旁边的**下载**。
  
如果您正在从头创建.tsv 或.csv 文件，请参阅[租户的数据文件格式和生成的数据文件结构](turning-on-and-using-call-quality-dashboard.md#BKMKTenantDataFile)。
  
## <a name="related-topics"></a>相关主题
<a name="BKMK_UploadFiles"> </a>

[使用通话分析解决 Skype for Business 通话质量不佳的问题](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[通话分析与通话质量仪表板之间有何区别？](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 