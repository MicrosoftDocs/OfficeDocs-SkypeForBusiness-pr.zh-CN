---
title: "设置 Skype for Business 呼叫分析"
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 9/25/2017
ms.audience: Admin
ms.topic: get-started-article
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: fbf7247a-84ae-46cc-9204-2c45b1c734cd
description: "Set up and use Call Analytics to identify and troubleshoot Skype for Business and Microsoft Teams call quality problems."
---

# 设置 Skype for Business 呼叫分析

> [!重要信息]
> 本文是由机器翻译的，请参阅[免责声明](fbf7247a-84ae-46cc-9204-2c45b1c734cd.md#MT_Footer)。请在 [此处](https://support.office.com/en-us/article/fbf7247a-84ae-46cc-9204-2c45b1c734cd) 中查找本文的英文版本以便参考。
  
作为Skype for Business Online管理员，您可以使用呼叫分析Skype for Business和Microsoft Teams呼叫质量和连接问题疑难解答。您可能会发现有用设置呼叫分析中的下列功能：
  
- 设置让其他人员，例如技术支持人员代理的权限使用呼叫分析，但阻止他们访问Skype for Business管理中心中的其余部分。
    
- 上载.tsv 或.csv 数据文件，可以将构建、 站点和租户信息添加到呼叫分析。
    
> [!注释]
> 正在预览呼叫分析。文本和图像此处所述可能与您的体验。 
  
## 设置呼叫分析权限
<a name="BKMK_SetCAPerms"> </a>

作为管理员，您将获得完整访问所有的分析功能的呼叫。此外，您可以使用呼叫分析包含层 1 和 2 层权限组中的技术支持人员模型。 具有 1 层权限的用户可以访问受限的视图的呼叫分析。 具有 2 层权限的用户可以访问呼叫分析的全部功能。这两种权限级别阻止向Skype for Business管理中心中的其余部分的访问。您可以通过添加一组包含一层或权限页面的第 2 部分用户授予访问层。有关详细信息，请参阅[设置呼叫分析中的分层权限](fbf7247a-84ae-46cc-9204-2c45b1c734cd.md#BKMK_SetUpTier)。
  
第 1 层的技术支持人员代理处理基本呼叫质量问题。 第 1 层代理不调查问题会议;它们收集相关的信息，然后升级到第 2 层工程师。第 2 层代理，请参阅详细的呼叫日志隐藏的第 1 层代理的信息。下表概述了使用呼叫分析的代理到可用的信息。
  
|
|
|**活动**|**在呼叫分析的信息**|**第 1 层工程师所看到的内容**|**第 2 层工程师所看到的内容**|
|:-----|:-----|:-----|:-----|
|**呼叫** <br/> |呼叫者姓名  <br/> |仅为其代理搜索的用户的名称。  <br/> |用户的姓名。  <br/> |
||收件人姓名  <br/> |显示为内部用户或外部用户。  <br/> |收件人的姓名。  <br/> |
||呼叫方电话号码  <br/> |除最后三个数字的完整的电话号码是使用星号符号混淆。例如，15552823 ***。  <br/> |除最后三个数字的完整的电话号码是使用星号符号混淆。例如，15552823 ***。  <br/> |
||收件人电话号码  <br/> |除最后三个数字的完整的电话号码是使用星号符号混淆。例如，15552823 ***。  <br/> |除最后三个数字的完整的电话号码是使用星号符号混淆。例如，15552823 ***。  <br/> |
||**呼叫详细信息**> **高级**选项卡  <br/> |不显示的信息。  <br/> |显示，例如设备名称、 IP 地址、 子网映射和所有详细信息。  <br/> |
||**呼叫详细信息**> **高级**> **调试**选项卡  <br/> |不显示的信息。  <br/> |显示，例如 DNS 后缀和 SSID 的全部详细信息。  <br/> |
|**会议** <br/> |参与者姓名  <br/> |仅为其代理搜索的用户的名称。标识为内部用户或外部用户的其他参与者。  <br/> |显示所有姓名。  <br/> |
||参与者计数  <br/> |参与者的数量。  <br/> |参与者的数量。  <br/> |
||会话的详细信息  <br/> |显示具有例外会话详细信息。仅为其显示搜索代理的用户的名称。标识为内部用户或外部用户的其他参与者。最后三个数字的电话号码与星号符号混淆。  <br/> |显示会话详细信息。用户名和会话的详细信息显示。最后三个数字的电话号码与星号符号混淆。  <br/> |
   
 **设置呼叫分析中的分层权限**
  
1. 创建Office 365安全组层 1 和 2 层，并将所需的人员添加到每个组。您也可以重新使用现有的安全组。有关详细信息，请参阅[创建、 编辑或删除 Office 365 管理中心中的安全组](https://support.office.com/article/55c96b32-e086-4c9e-948b-a018b44510cb)。
    
2. 在Office 365 管理中心中，转到 **中心的管理员**> **Skype for Business**。
    
    > [!注释]
    > 如果您先进入旧Skype for Business管理中心中，请通过单击 **附带试用我们新的管理中心**转到最新版本。 
  
3. 在新的Skype for Business管理中心中，单击 **权限**。
    
4. 将Office 365安全组添加到 **层 1**和 **2 层**框。您可以为每个角色添加多个组。
    
     ![Screenshot shows the Permissions for Call Analytics page with the options for Tier 1 and Tier 2 permissions.](../images/ed5b6b05-b407-4363-8cf0-a6e79027f64b.png)
  
使用任一这些权限级别的用户访问通过专用 URL https://adminportal.services.skypeforbusiness.com 呼叫分析。
  
## 上载.tsv 或.csv 文件中添加构建，网站，并租户的信息
<a name="BKMK_UploadFiles"> </a>

可以上载的.csv 或.tsv 文件构建、 站点和租户信息添加到呼叫分析。 具有所有此类信息呼叫分析可以将 IP 地址映射到物理位置。您或技术支持人员代理可能查找此信息用于帮助呼叫问题中的找到趋势。例如，原因是在同一建筑时遇到的许多用户类似呼叫质量问题？
  
![Screenshot shows the Sites page with values for Number of sites and Number of subnets, and the Select file button to import site data by uploading a .tsv or a .csv file.](../images/b2f3a5cb-32b5-4f60-a9af-0691aa6ff1e8.png)
  
如果您是Skype for Business管理员，您可以使用Skype for Business Online呼叫质量仪表板中的现有数据文件。首先，从呼叫质量仪表板中下载文件，然后您将其上载到呼叫分析。若要下载的现有数据文件，请转到 **Skype for Business 管理中心**> **工具**> **Skype for Business Online 呼叫质量仪表板**> **立即上载**。在 **我的上载**列表中，单击所需的文件旁边的 **下载**。
  
如果您从头开始创建.tsv 或.csv 文件，请参阅[租户数据文件格式和建筑物数据文件结构](turning-on-and-using-call-quality-dashboard-for-microsoft-teams-and-skype-for-bu.md#BKMK_TenantDataFile)。
  
## 
<a name="MT_Footer"> </a>

> [!注释]
> **机器翻译免责声明**：本文是由无人工介入的计算机系统翻译的。Microsoft 提供机器翻译是为了帮助非英语国家/地区用户方便阅读有关 Microsoft 产品、服务和技术的内容。由于机器翻译的原因，本文可能包含词汇、语法或文法方面的错误。 
  
## 另请参阅
<a name="MT_Footer"> </a>

#### 其他资源

[使用呼叫分析来进行故障排除较差 Skype for Business 呼叫质量](use-call-analytics-to-troubleshoot-poor-skype-for-business-call-quality.md)
  
[呼叫分析和呼叫质量仪表板之间的区别是什么？](what-s-the-difference-between-call-analytics-and-call-quality-dashboard.md)

