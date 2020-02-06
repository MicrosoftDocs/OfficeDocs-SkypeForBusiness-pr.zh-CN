---
title: 存档配置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.MonArchSettingMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 9c2fd164-a9b8-40e6-a1c4-423a7fe34aba
ROBOTS: NOINDEX, NOFOLLOW
description: 使用存档配置控制 Skype for Business Server 部署的存档选项，包括启用和禁用以下选项：
ms.openlocfilehash: 35ef51f9e67b42624dbf106037ae6a57343c21c1
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41795011"
---
# <a name="archiving-configuration"></a>存档配置
 
使用存档配置控制 Skype for Business Server 部署的存档选项，包括启用和禁用以下选项：
  
- 存档失败时阻止即时消息 (IM) 或会议会话
    
- 与 Exchange 存储集成，适用于托管的用户
    
- 清除存档数据
    
存档配置包括全局配置以及可选的一个或多个站点和池存档配置：
  
- **全局配置**默认情况下，全局配置在所有 Skype for Business 服务器部署中创建。 您可以编辑全局配置，但无法删除此存档配置。 如果您尝试将其删除，则所有选项将重置为默认值。
    
- **网站配置（可选）** 你可以指定一个或多个网站存档配置，每个配置都可以配置用于控制特定网站的存档选项。 站点配置会覆盖全局配置，但仅限于在存档站点配置中指定的站点。 可以编辑或删除站点配置。
    
- **池配置（可选）** 你可以指定一个或多个池存档配置，以控制特定池的存档选项。 池配置会覆盖全局配置和站点配置，但仅限于在存档池配置中指定的池。 可以编辑或删除池配置。
    
> [!NOTE]
> 存档配置适用于驻留在 Skype for business 服务器上的用户，并且，如果你使用 Exchange 将存档数据存储在 Microsoft Exchange 中，则对于驻留在 exchange 上的用户来说，其实现方式稍有不同。 将在下节中介绍这些差异。 
  
“**存档配置**”页将列出为部署配置的每个存档策略。该页还将显示策略名称、范围（全局、站点或用户）以及为每个存档配置启用的存档选项。在“**存档配置**”页上，您有以下选项：
- **新**你可以添加以下每个可选存档配置中的一个或多个配置。
    
  - 站点配置
    
  - 池配置
    
- **编辑**你可以更改页面上列出的任何存档配置的选项。 使用此选项，您可以执行以下操作：
    
  - **显示详细信息**此选项将打开一个对话框，您可以在其中更改所选存档配置的存档选项。 一次只能显示一个存档配置的详细信息。
    
  - **全选**此选项选择列表中的所有存档配置。
    
  - **Delete**此选项将删除所有选定的存档配置。
    
- **操作**你可以使用此选项快速启用或禁用页面上列出的任何配置中的 IM 会话或 web 会议会话的存档，而不是编辑配置。 "**操作**" 下的可用选项取决于存档配置中当前指定的选项。 除了当前对存档配置有效的选项之外，所有选项均可用。 选项包括以下内容：
    
  - **存档 IM 会话**
    
  - **存档 IM 和 Web 会议会话**
    
  - **禁用存档**
    
- **刷新**你可以刷新 "**存档配置**" 页，以验证所有存档配置的选项的状态。
    
有关存档功能和功能（包括 Exchange 集成）的详细信息，请参阅[在 skype for Business 服务器中规划存档](../../../plan-your-deployment/archiving/archiving.md)、[部署 Skype for business 服务器存档](../../../deploy/deploy-archiving/deploy-archiving.md)和[管理 skype for business 服务器中的存档](../../../manage/archiving/archiving.md)。

