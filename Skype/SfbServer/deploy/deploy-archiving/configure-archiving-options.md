---
title: 配置 Skype 业务服务器的存档的选项
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2f534697-ac7f-45b7-8cdc-ba67f052223b
description: 摘要： 阅读本主题可了解如何配置初始的 Skype 业务服务器的存档选项。 您最初设置存档配置，当您部署存档，但您可以更改、 添加和删除部署后的配置。
ms.openlocfilehash: 80501c01c4e05e0578685b42f8fb83b7faed6c59
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30896293"
---
# <a name="configure-archiving-options-for-skype-for-business-server"></a>配置 Skype 业务服务器的存档的选项
 
**摘要：** 阅读本主题可了解如何配置初始的 Skype 业务服务器的存档选项。 您最初设置存档配置，当您部署存档，但您可以更改、 添加和删除部署后的配置。
  
若要配置初始存档配置，您使用业务 Server Control Panel 的 Skype 指定以下：
  
- 为业务 Server 部署 Skype 时默认创建的全局级配置
    
- 指定如何为特定站点实施存档的可选站点级别配置
    
- 指定如何实现存档的特定池的可选池级配置
    
您需要为以下内容配置选项：
  
- 启用还是禁用存档
    
- 是否存档 IM 会话
    
- 是否存档 Web 会议会话
    
- 是否在存档不可用时阻止活动
    
- 是否使用 Exchange 集成
    
- 如何设置数据的清除和导出
    
> [!NOTE]
> 在启用存档之前，应指定所有适当选项。 
  
有关操作的详细信息实现存档配置，包括您可以指定的选项和层次结构的存档配置，请参阅[Plan for Business Server 的 Skype 的存档](../../plan-your-deployment/archiving/archiving.md)。 有关如何管理的详细信息后部署通过使用控制面板，或使用 Windows PowerShell 配置，请参阅[管理 Skype 业务服务器中的存档选项](../../manage/archiving/options.md)。
  
## <a name="configure-global-level-archiving-options"></a>配置全局级别存档选项

当您向拓扑添加存档并发布拓扑时，业务服务器 Skype 创建存档的全局配置。 默认情况下，不会在全局配置中启用任何存档选项。 除非您自己设置站点或池配置（这将重写全局配置），否则全局配置将控制要为整个部署启用的选项。
  
在全局级别配置存档选项：
  
1. 使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。 
    
3. 在左侧导航栏中，单击“监控和存档”****，然后单击“存档配置”****。
    
4. 在“**存档配置**”页上，单击“**全局**”，再单击“**编辑**”，然后单击“**显示详细信息**”。
    
5. 在“**编辑存档设置 - 全局**”的“**存档设置**”下拉列表中，选择下列存档选项之一：
    
   - **禁用存档**
    
   - **存档 IM 会话**
    
   - **存档 IM 和 Web 会议会话**
    
6. 此外在**编辑存档设置-全局**页上，执行以下操作：
    
   - 要在存档不可用时阻止活动，请选中“**存档失败时阻止即时消息 (IM) 或 Web 会议会话**”复选框。
    
   - 若要使用 Microsoft Exchange Server 存储存档数据，请单击**Microsoft Exchange 集成**复选框。
    
   - 若要启用数据清除，请选中“**启用存档数据清除**”复选框，然后执行下列操作之一：
    
   - 要指定在特定的天数之后清除，请单击“**在最长期限（天）后清除导出的存档数据和存储的存档数据**”，然后指定天数。
    
   - 要限制仅清除已导出的存档数据，请单击“**仅清除导出的存档数据**”。
    
7. 单击“**提交**”。
    
## <a name="configure-site-level-archiving-options"></a>配置站点级别存档选项

您可以为特定站点指定存档选项。 站点配置可覆盖全局配置，但它仅适用于站点配置中指定的站点。 
  
1. 使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。 
    
3. 在左侧导航栏中，单击“监控和存档”****，然后单击“存档配置”****。
    
4. 在“**存档配置**”页上，单击“**新建**”，然后单击“**站点配置**”。
    
5. 在“**选择站点**”中，选择要为存档配置的站点。
    
6. 在“**新建存档设置**”的“**存档设置**”下拉列表框中，执行下列操作之一：
    
   - 若要只为即时消息 (IM) 会话启用存档，请单击“**存档 IM 会话**”。
    
   - 若要为 IM 会话和会议启用存档，请单击“**存档 IM 和 Web 会议会话**”。
    
   - 若要为策略禁用存档，请单击“**禁用存档**”。
    
7. 另请在“**新建存档设置**”中，执行下列操作：
    
   - 要在存档不可用时阻止活动，请选中“**存档失败时阻止即时消息 (IM) 或 Web 会议会话**”复选框。
    
   - 若要使用 Microsoft Exchange Server 存储存档数据，请单击**Microsoft Exchange 集成**复选框。
    
   - 若要启用数据清除，请选中“**启用存档数据清除**”复选框，然后执行下列操作之一：
    
   - 要指定在特定的天数之后清除，请单击“**在最长期限（天）后清除导出的存档数据和存储的存档数据**”，然后指定天数。
    
   - 要限制仅清除已导出的存档数据，请单击“**仅清除导出的存档数据**”。
    
8. 单击“**提交**”。
    
## <a name="configure-pool-level-archiving-options"></a>配置池级别存档选项

您可以为特定池指定存档选项。池配置可覆盖全局配置和站点配置，但它仅适用于池配置中指定的池。
  
1. 使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。 
    
3. 在左侧导航栏中，单击“监控和存档”****，然后单击“存档配置”****。
    
4. 在“**存档配置**”页上，单击“**新建**”，然后单击“**池配置**”。
    
5. 在“**选择服务**”中，选择要为存档配置的池。
    
6. 在“**新建存档设置**”的“**存档设置**”下拉列表中，选择下列存档选项之一：
    
   - **禁用存档**
    
   - **存档 IM 会话**
    
   - **存档 IM 和 Web 会议会话**
    
7. 另请在“**新建存档设置**”页中，执行下列操作：
    
   - 要在存档不可用时阻止活动，请选中“**存档失败时阻止即时消息 (IM) 或 Web 会议会话**”复选框。
    
   - 若要使用 Microsoft Exchange Server 存储存档数据，请单击**Microsoft Exchange 集成**复选框。
    
   - 若要启用数据清除，请选中“**启用存档数据清除**”复选框，然后执行下列操作之一：
    
   - 要指定在特定的天数之后清除，请单击“**在最长期限（天）后清除导出的存档数据和存储的存档数据**”，然后指定天数。
    
   - 要限制仅清除已导出的存档数据，请单击“**仅清除导出的存档数据**”。
    
8. 单击“**提交**”。
    

