---
title: 存档配置
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
  - CSH
ms.custom:
  - ms.lync.lscp.MonArchSettingMain
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 9c2fd164-a9b8-40e6-a1c4-423a7fe34aba
description: 使用存档配置来控制您的Skype for Business Server的存档选项，包括启用和禁用以下选项：
---

# <a name="archiving-configuration"></a>存档配置
 
使用存档配置来控制您的Skype for Business Server的存档选项，包括启用和禁用以下选项：
  
- 存档失败时阻止即时消息 (IM) 或会议会话
    
- 与 Exchange 2013 存储集成，适用于 2013 Exchange用户
    
- 清除存档数据
    
存档配置包括全局配置以及可选的一个或多个站点和池存档配置：
  
- **全局配置** 默认情况下，在部署的所有部署中创建Skype for Business Server配置。 您可以编辑全局配置，但无法删除此存档配置。 如果您尝试将其删除，则所有选项将重置为默认值。
    
- **站点配置 (可选)** 您可以指定一个或多个站点存档配置，您可将每个存档配置分别配置为控制特定站点的存档选项。 站点配置会覆盖全局配置，但仅限于在存档站点配置中指定的站点。 可以编辑或删除站点配置。
    
- **池配置 (可选)** 可以指定一个或多个池存档配置，以控制特定池的存档选项。 池配置会覆盖全局配置和站点配置，但仅限于在存档池配置中指定的池。 可以编辑或删除池配置。
    
> [!NOTE]
> 存档配置适用于 Skype for Business Server 上的用户;如果使用 Exchange 将存档数据存储在 Microsoft Exchange 中，则存档配置适用于在 Exchange 2013 上保留的用户，但为 Exchange 2013 上用户实现的方式略有不同。 将在下节中介绍这些差异。 
  
“存档配置”页将列出为部署配置的每个存档策略。该页还将显示策略名称、范围（全局、站点或用户）以及为每个存档配置启用的存档选项。在“存档配置”页上，您有以下选项：
- **新增功能** 可以添加以下一个或多个可选的存档配置。
    
  - 站点配置
    
  - 池配置
    
- **编辑** 您可以更改该页上列出的任何存档配置的选项。 使用此选项，可以执行以下操作：
    
  - **显示详细信息** 此选项将打开一个对话框，您可以在其中更改所选存档配置的存档选项。 一次只能显示一个存档配置的详细信息。
    
  - **全选** 此选项选择列表中的所有存档配置。
    
  - **删除** 此选项将删除所有选定的存档配置。
    
- **操作** 可以使用此选项在页面上列出的任何配置中快速启用或禁用 IM 会话或 Web 会议会话的存档，而不是编辑配置。 "操作" **下可用的** 选项取决于当前在存档配置中指定的选项。 所有选项都可用，但当前对存档配置有效的选项除外。 选项包括：
    
  - **存档 IM 会话**
    
  - **存档 IM 和 Web 会议会话**
    
  - **禁用存档**
    
- **刷新** 可以刷新" **存档配置"** 页以验证所有存档配置的选项状态。
    
有关存档特性和功能（包括 Exchange 集成）的详细信息，请参阅 Plan [for archiving in Skype for Business Server 2015](../../plan-your-deployment/archiving/archiving.md)、[Deploy archiving for Skype for Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md)和 [Manage archiving inSkype for Business Server 2015 年 10 月](../../manage/archiving/archiving.md)。

