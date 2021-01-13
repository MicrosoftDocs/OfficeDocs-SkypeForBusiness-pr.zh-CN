---
title: 存档配置
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.MonArchSettingMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9c2fd164-a9b8-40e6-a1c4-423a7fe34aba
description: 使用存档配置来控制 Skype for Business Server 部署的存档选项，包括启用和禁用以下选项：
ms.openlocfilehash: 96a01579f43833017978fc6067b5a86f9e9951aa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827002"
---
# <a name="archiving-configuration"></a>存档配置
 
使用存档配置来控制 Skype for Business Server 部署的存档选项，包括启用和禁用以下选项：
  
- 存档失败时阻止即时消息 (IM) 或会议会话
    
- 与 Exchange 2013 存储集成，适用于位于 Exchange 2013 上的用户
    
- 清除存档数据
    
存档配置包括全局配置以及可选的一个或多个站点和池存档配置：
  
- **全局配置** 默认情况下，全局配置在所有 Skype for Business Server 部署中创建。 您可以编辑全局配置，但无法删除此存档配置。 如果您尝试将其删除，则所有选项将重置为默认值。
    
- **站点配置 (可选)** 可以指定一个或多个站点存档配置，每个存档配置都可以配置为控制特定站点的存档选项。 站点配置会覆盖全局配置，但仅限于在存档站点配置中指定的站点。 可以编辑或删除站点配置。
    
- **池配置 (可选)** 可以指定一个或多个池存档配置，以控制特定池的存档选项。 池配置会覆盖全局配置和站点配置，但仅限于在存档池配置中指定的池。 可以编辑或删除池配置。
    
> [!NOTE]
> 存档配置适用于 Skype for Business Server 上用户，如果使用 Exchange 在 Microsoft Exchange 中存储存档数据，则存档配置适用于位于 Exchange 2013 上但为 Exchange 2013 上用户实现略有不同的用户。 将在下节中介绍这些差异。 
  
“存档配置”页将列出为部署配置的每个存档策略。该页还将显示策略名称、范围（全局、站点或用户）以及为每个存档配置启用的存档选项。在“存档配置”页上，您有以下选项：
- **新建** 可以添加以下一个或多个可选的存档配置。
    
  - 站点配置
    
  - 池配置
    
- **编辑** 您可以更改页面上列出的任何存档配置的选项。 使用此选项，可以执行以下操作：
    
  - **显示详细信息** 此选项将打开一个对话框，您可以在其中更改所选存档配置的存档选项。 一次只能显示一个存档配置的详细信息。
    
  - **全选** 此选项选择列表中的所有存档配置。
    
  - **删除** 此选项将删除所有选定的存档配置。
    
- **操作** 可以使用此选项在页面上列出的任何配置中快速启用或禁用 IM 会话或 Web 会议会话的存档，而不是编辑配置。 "操作" **下可用的** 选项取决于当前在存档配置中指定的选项。 除当前对存档配置生效的选项外，所有选项都可用。 选项包括：
    
  - **存档 IM 会话**
    
  - **存档 IM 和 Web 会议会话**
    
  - **禁用存档**
    
- **刷新** 可以刷新" **存档配置** "页以验证所有存档配置的选项状态。
    
有关存档特性和功能的详细信息，包括 Exchange 集成，请参阅规划 [Skype for Business Server 2015](../../plan-your-deployment/archiving/archiving.md)中的存档、 [部署 Skype for Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md)的存档以及管理 Skype for Business Server [2015](../../manage/archiving/archiving.md)中的存档。

