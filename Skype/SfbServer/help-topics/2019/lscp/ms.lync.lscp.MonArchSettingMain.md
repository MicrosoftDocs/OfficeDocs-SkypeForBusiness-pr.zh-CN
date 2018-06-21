---
title: 存档配置
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.MonArchSettingMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9c2fd164-a9b8-40e6-a1c4-423a7fe34aba
description: 使用存档配置来控制您的业务服务器部署，包括启用和禁用以下选项的 Skype 的存档选项：
ms.openlocfilehash: 3bac88f44fea669c0eb1219046067f1e348c413c
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/20/2018
ms.locfileid: "19973211"
---
# <a name="archiving-configuration"></a>存档配置
 
使用存档配置来控制您的业务服务器部署，包括启用和禁用以下选项的 Skype 的存档选项：
  
- 存档失败时阻止即时消息 (IM) 或会议会话
    
- 与 Exchange 存储中，为用户的集成驻留在 Exchange
    
- 清除存档数据
    
存档配置包括全局配置以及可选的一个或多个站点和池存档配置：
  
- **全局配置**默认情况下，所有 Skype 业务服务器部署中创建全局配置。 您可以编辑全局配置，但无法删除此存档配置。 如果您尝试将其删除，则所有选项将重置为默认值。
    
- **网站配置 （可选）** 您可以指定一个或多个站点存档配置，其中每个您可以配置为特定站点的存档选项的控件。 站点配置会覆盖全局配置，但仅限于在存档站点配置中指定的站点。 可以编辑或删除站点配置。
    
- **池配置 （可选）** 您可以指定一个或多个池存档配置，控制特定池的存档选项。 池配置会覆盖全局配置和站点配置，但仅限于在存档池配置中指定的池。 可以编辑或删除池配置。
    
> [!NOTE]
> 存档配置适用于用户的企业服务器驻留在 Skype 和，如果您使用 Exchange 存储存档数据，Microsoft Exchange 中向用户驻留在 Exchange 但略有不同的用户驻留在 Exchange 上实现。 将在下节中介绍这些差异。 
  
“**存档配置**”页将列出为部署配置的每个存档策略。该页还将显示策略名称、范围（全局、站点或用户）以及为每个存档配置启用的存档选项。在“**存档配置**”页上，您有以下选项：
- **新**您可以添加一个或多个以下可选存档配置。
    
  - 站点配置
    
  - 池配置
    
- **编辑**您可以更改的任何页面上列出在存档配置的选项。 使用此选项，可以执行以下操作：
    
  - **显示详细信息**此选项可打开一个对话框，您可以在其中更改所选的存档配置的存档选项。 您仅可以显示一次一个的存档配置的详细信息。
    
  - **选择全部**此选项可选择列表中所有存档配置。
    
  - **删除**此选项可删除所有选定的存档配置。
    
- **操作**您可以使用此选项可快速启用或禁用存档 IM 会话或 web 会议会话中列出在页上，而不是编辑配置任何配置。 可在**操作**下的选项取决于当前在存档配置中指定哪些选项。 所有选项都都可用，除当前选项生效的存档配置。 选项包括：
    
  - **存档 IM 会话**
    
  - **存档 IM 和 Web 会议会话**
    
  - **禁用存档**
    
- **刷新**您可以刷新**存档配置**页以验证所有存档配置的选项状态。
    
有关的存档功能和功能，包括 Exchange 集成的详细信息，请参阅[规划存档中的业务服务器 2015 Skype](../../../plan-your-deployment/archiving/archiving.md)、[业务服务器 2015年的 Skype 存档的部署](../../../deploy/deploy-archiving/deploy-archiving.md)，和[管理存档中的 Skype业务服务器 2015年](../../../manage/archiving/archiving.md)。

