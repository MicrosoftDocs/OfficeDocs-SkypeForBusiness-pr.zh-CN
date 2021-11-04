---
title: 配置存档的存档Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 2f534697-ac7f-45b7-8cdc-ba67f052223b
description: 摘要：阅读本主题，了解如何配置用于存档Skype for Business Server。 您最初在部署存档时设置存档配置，但您可以在部署后更改、添加和删除配置。
ms.openlocfilehash: b27a6bdd85b935b0751abf3da2bac94488234cdb
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60749511"
---
# <a name="configure-archiving-options-for-skype-for-business-server"></a>配置存档的存档Skype for Business Server
 
**摘要：** 阅读本主题，了解如何为存档配置初始Skype for Business Server。 您最初在部署存档时设置存档配置，但您可以在部署后更改、添加和删除配置。
  
若要配置初始存档配置，Skype for Business Server控制面板指定以下内容：
  
- 部署数据库时默认创建的全局Skype for Business Server
    
- 指定如何为特定站点实施存档的可选站点级别配置
    
- 指定如何为特定池实施存档的可选池级别配置
    
您需要为以下项配置选项：
  
- 启用还是禁用存档
    
- 是否存档 IM 会话
    
- 是否存档 Web 会议会话
    
- 存档不可用时是否阻止活动
    
- 是否使用Exchange集成
    
- 如何设置数据的清除和导出
    
> [!NOTE]
> 在启用存档之前，应指定所有适当的选项。 
  
有关如何实施存档配置（包括可以指定哪些选项以及存档配置的层次结构）的详细信息，请参阅 Plan [for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md)。 有关如何使用控制面板或部署后管理配置的详细信息，请参阅管理Windows PowerShell中的存档[Skype for Business Server。](../../manage/archiving/options.md)
  
## <a name="configure-global-level-archiving-options"></a>配置全局级别存档选项

向拓扑中添加存档并发布拓扑时，Skype for Business Server创建用于存档的全局配置。 默认情况下，全局配置中不启用任何存档选项。 除非您自己设置站点或池配置（这将重写全局配置），否则全局配置将控制要为整个部署启用的选项。
  
在全局级别配置存档选项：
  
1. 使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。 
    
3. 在左侧导航栏中，单击 **“监控和存档”**，然后单击 **“存档配置”**。
    
4. 在“存档配置”页上，单击“全局”，再单击“编辑”，然后单击“显示详细信息”。
    
5. 在“编辑存档设置 - 全局”的“存档设置”下拉列表中，选择下列存档选项之一：
    
   - **禁用存档**
    
   - **存档 IM 会话**
    
   - **存档 IM 和 Web 会议会话**
    
6. 此外，在 **"编辑存档设置 - 全局"** 页上，执行以下操作：
    
   - 要在存档不可用时阻止活动，请选中“存档失败时阻止即时消息(IM)或 Web 会议会话”复选框。
    
   - 若要使用Microsoft Exchange Server存储存档数据，请单击 **"Microsoft Exchange集成"** 复选框。
    
   - 若要启用数据清除，请选中“启用存档数据清除”复选框，然后执行下列操作之一：
    
   - 要指定在特定的天数之后清除，请单击“在最长期限(天)后清除导出的存档数据和存储的存档数据”，然后指定天数。
    
   - 要限制仅清除已导出的存档数据，请单击“仅清除导出的存档数据”。
    
7. 单击“提交”。
    
## <a name="configure-site-level-archiving-options"></a>配置站点级别存档选项

您可以为特定站点指定存档选项。 站点配置会覆盖全局配置，但仅适用于站点配置中指定的站点。 
  
1. 使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。 
    
3. 在左侧导航栏中，单击 **“监控和存档”**，然后单击 **“存档配置”**。
    
4. 在“存档配置”页上，单击“新建”，然后单击“站点配置”。
    
5. 在“选择站点”中，选择要为存档配置的站点。
    
6. 在“存档设置”下拉列表框的“新建存档设置”中，执行以下操作之一：
    
   - 若要只为即时消息 (IM) 会话启用存档，请单击“存档 IM 会话”。
    
   - 若要为 IM 会话和会议启用存档，请单击“存档 IM 和 Web 会议会话”。
    
   - 若要为策略禁用存档，请单击“禁用存档”。
    
7. 另请在“新建存档设置”中，执行下列操作：
    
   - 要在存档不可用时阻止活动，请选中“存档失败时阻止即时消息 (IM) 或 Web 会议会话”复选框。
    
   - 若要使用Microsoft Exchange Server存储存档数据，请单击 **"Microsoft Exchange集成"** 复选框。
    
   - 若要启用数据清除，请选中“启用存档数据清除”复选框，然后执行下列操作之一：
    
   - 要指定在特定的天数之后清除，请单击“在最长期限(天)后清除导出的存档数据和存储的存档数据”，然后指定天数。
    
   - 要限制仅清除已导出的存档数据，请单击“仅清除导出的存档数据”。
    
8. 单击“提交”。
    
## <a name="configure-pool-level-archiving-options"></a>配置池级别存档选项

您可以为特定池指定存档选项。 池配置可重写全局配置和站点配置，但它仅适用于池配置中指定的池。
  
1. 使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。 
    
3. 在左侧导航栏中，单击 **“监控和存档”**，然后单击 **“存档配置”**。
    
4. 在“存档配置”页上，单击“新建”，然后单击“池配置”。
    
5. 在“选择服务”中，选择要为存档配置的池。
    
6. 在“新建存档设置”的“存档设置”下拉列表中，选择下列存档选项之一：
    
   - **禁用存档**
    
   - **存档 IM 会话**
    
   - **存档 IM 和 Web 会议会话**
    
7. 另请在“新建存档设置”页中，执行下列操作：
    
   - 要在存档不可用时阻止活动，请选中“存档失败时阻止即时消息(IM)或 Web 会议会话”复选框。
    
   - 若要使用Microsoft Exchange Server存储存档数据，请单击 **"Microsoft Exchange集成"** 复选框。
    
   - 若要启用数据清除，请选中“启用存档数据清除”复选框，然后执行下列操作之一：
    
   - 要指定在特定的天数之后清除，请单击“在最长期限(天)后清除导出的存档数据和存储的存档数据”，然后指定天数。
    
   - 要限制仅清除已导出的存档数据，请单击“仅清除导出的存档数据”。
    
8. 单击“提交”。
    

