---
title: 创建新模板或编辑现有的存档配置
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.MonArchSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49096960-c442-4846-be8f-03c167acea41
description: 使用存档配置可控制用于部署的存档选项。存档配置包括全局配置以及可选的一个或多个站点和池配置：
ms.openlocfilehash: 49227ded326c893d42852796e9c783a2dc4096cd
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="archiving-configuration-create-new-or-edit-existing"></a>存档配置：创建新的或编辑现有的
 
使用存档配置可控制用于部署的存档选项。存档配置包括全局配置以及可选的一个或多个站点和池配置：
  
- **全局配置**默认情况下创建全局配置。 您可以编辑全局配置，但无法删除此存档配置。 如果您尝试将其删除，则所有选项将重置为默认值。
    
- **站点配置 （可选）**您可以指定一个或多个站点存档配置，您可以配置归档选项针对特定的网站控制每个。 站点配置会覆盖全局配置，但仅限于在存档站点配置中指定的站点。 可以编辑或删除站点配置。
    
- **池配置 （可选）**您可以指定一个或多个池存档配置，控制归档选项为一个特定的池。 池配置会覆盖全局配置和站点配置，但仅限于在存档池配置中指定的池。 可以编辑或删除池配置。
    
> [!NOTE]
> 存档的配置将应用于用户业务服务器驻留在 Skype 上，如果启用 Microsoft Exchange 集成选项，使用 Exchange 2013 存档数据存储在 Microsoft Exchange 用户驻留在 Exchange 2013。 但是，某些选项将实现略有不同的用户驻留在 Exchange 2013 下一节中所述。 
  
若要配置新的或现有的存档配置的设置，请指定以下选项：
- **名称**每个存档配置需要一个名称。 名称取决于您在添加或编辑的配置的类型：
    
  - **全局配置**默认名称是全局。 例如，Contoso 北美机构。
    
  - **站点配置**该列表包含在部署中的可用站点。 单击某个站点将其选中。 例如，Redmond 数据中心。
    
  - **池配置**指定适当的名称，它可以是一个特定的前端池或标准版服务器部署中的名称。 例如，市场营销部门。
    
- **说明**这是可选的。 使用它来提供更多详细信息，如使用配置的范围。 例如，协调与其他站点的法律部门。
    
- **存档设置**选项如下所示：
    
  - **存档 IM 会话**
    
  - **存档 IM 和 Web 会议会话**
    
  - **禁用存档**
    
- **阻止即时消息 (IM) 或 web 会议会话如果存档失败则**以下故障：
    
  - **即时消息**故障可能是一个完整的数据库或存储服务问题。 在此情况下，将阻止为存档启用的用户使用 IM。
    
  - **会议**故障可能是不可用的文件共享或存储服务有问题。 在此情况下，池中托管的所有活动会议在发生故障时将切换到限制模式，并且不能激活新会议。
    
    IM 和会议都能在修复故障后自动恢复。
    
- **Microsoft Exchange 集成**如果必须驻留在 Exchange 2013 的用户，请选择此选项。 使用此选项，Exchange 2013 用于存储数据的用户，如果他们的邮箱已经置于适当地存放。 如果您的所有用户都驻留在 Exchange 2013，您不需要设置单独的 SQL Server 数据库，用于存储存档数据。
    
- **启用存档数据的清除**选择此选项可启用清除，并指定清除选项，包括下列：
    
  - 在您指定的特定天数之后清除
    
  - 清除存档数据后已导出 （如果启用 Microsoft Exchange 集成，其中包括已上载到交换的数据）。
    
    > [!NOTE]
    > 如果您启用 Microsoft Exchange 集成，清除用户驻留在 Exchange 2013，并通过交换控制放置适当地存放在其邮箱。 唯一的例外是存储 Lync Server 文件共享上的会议文件。 如果您选择在已导出存档数据后清除数据，或在指定的最长天数（如果您指定了最长保留天数）后清除数据，则仅在导出文件（上载到 Exchange）后才从文件共享中清除这些文件。 
  
有关存档功能和功能，其中包括交换集成详细信息请参阅[存档业务服务器 2015年的 Skype 的规划](../../plan-your-deployment/archiving/archiving.md)、[部署存档业务服务器 2015年的 Skype](../../deploy/deploy-archiving/deploy-archiving.md)，和[管理存档的 Skype 的商业服务器 2015年](../../manage/archiving/archiving.md)。

