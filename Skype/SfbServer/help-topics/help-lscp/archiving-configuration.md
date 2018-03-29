---
title: 存档配置
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.MonArchSettingMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9c2fd164-a9b8-40e6-a1c4-423a7fe34aba
description: 使用存档配置控制归档您 Skype 业务服务器部署，其中包括启用和禁用下列选项的选项：
ms.openlocfilehash: e32c42d5ef945b360ce4992ea9a33658bcc4068a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="archiving-configuration"></a>存档配置
 
使用存档配置控制归档您 Skype 业务服务器部署，其中包括启用和禁用下列选项的选项：
  
- 存档失败时阻止即时消息 (IM) 或会议会话
    
- 与 Exchange 2013 存储，用户集成驻留在 Exchange 2013
    
- 清除存档数据
    
存档配置包括全局配置以及可选的一个或多个站点和池存档配置：
  
- **全局配置**默认情况下，所有 Skype 业务服务器部署中创建全局配置。 您可以编辑全局配置，但无法删除此存档配置。 如果您尝试将其删除，则所有选项将重置为默认值。
    
- **站点配置 （可选）**您可以指定一个或多个站点存档配置，您可以配置归档选项针对特定的网站控制每个。 站点配置会覆盖全局配置，但仅限于在存档站点配置中指定的站点。 可以编辑或删除站点配置。
    
- **池配置 （可选）**您可以指定一个或多个池存档配置，控制归档选项为一个特定的池。 池配置会覆盖全局配置和站点配置，但仅限于在存档池配置中指定的池。 可以编辑或删除池配置。
    
> [!NOTE]
> 存档的配置将应用于用户的业务服务器驻留在 Skype 上和，如果使用 Exchange 将存档数据存储在 Microsoft Exchange 用户驻留在 Exchange 2013 但实现了略有不同的用户驻留在 Exchange 2013。 将在下节中介绍这些差异。 
  
“**存档配置**”页将列出为部署配置的每个存档策略。该页还将显示策略名称、范围（全局、站点或用户）以及为每个存档配置启用的存档选项。在“**存档配置**”页上，您有以下选项：
- **新**您可以添加一个或多个以下可选的存档配置的每个。
    
  - 站点配置
    
  - 池配置
    
- **编辑**您可以更改页面上列出的存档配置的任何选项。 使用此选项，可以执行以下操作：
    
  - **显示详细信息**此选项将打开一个对话框，在其中可以更改所选的存档配置存档选项。 您可以仅显示一次一个存档配置的详细信息。
    
  - **选择全部**此选项在列表中选择存档的所有配置。
    
  - **删除**此选项将删除所有选定的存档配置。
    
- **操作**此选项可以用于快速启用或禁用存档的即时消息会话或配置页面，而无需编辑配置上列出的 web 会议会话。 可在**操作**下的选项取决于当前存档配置中指定选项。 所有选项都都可用，除非当前的选项对存档配置有效。 选项如下所示：
    
  - **存档 IM 会话**
    
  - **存档 IM 和 Web 会议会话**
    
  - **禁用存档**
    
- **刷新**您可以刷新**存档配置**页后，可以验证所有的存档配置选项的状态。
    
有关存档功能和功能，其中包括交换集成详细信息请参阅[存档业务服务器 2015年的 Skype 的规划](../../plan-your-deployment/archiving/archiving.md)、[部署存档业务服务器 2015年的 Skype](../../deploy/deploy-archiving/deploy-archiving.md)，和[管理存档的 Skype 的商业服务器 2015年](../../manage/archiving/archiving.md)。

