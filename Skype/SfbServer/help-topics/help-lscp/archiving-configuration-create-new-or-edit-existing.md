---
title: 存档配置创建新的或编辑现有的
ms.reviewer: ''
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
ms.openlocfilehash: 2167b0ccc65a9bfc6ae731add156fa0b0925eaf2
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32234843"
---
# <a name="archiving-configuration-create-new-or-edit-existing"></a>存档配置：创建新的或编辑现有的
 
使用存档配置可控制用于部署的存档选项。存档配置包括全局配置以及可选的一个或多个站点和池配置：
  
- **全局配置**默认情况下创建的全局配置。 您可以编辑全局配置，但无法删除此存档配置。 如果您尝试将其删除，则所有选项将重置为默认值。
    
- **网站配置 （可选）** 您可以指定一个或多个站点存档配置，其中每个您可以配置为特定站点的存档选项的控件。 站点配置会覆盖全局配置，但仅限于在存档站点配置中指定的站点。 可以编辑或删除站点配置。
    
- **池配置 （可选）** 您可以指定一个或多个池存档配置，来控制特定池的存档选项。 池配置会覆盖全局配置和站点配置，但仅限于在存档池配置中指定的池。 可以编辑或删除池配置。
    
> [!NOTE]
> 存档配置适用于用户的企业服务器驻留在 Skype 上，如果您启用 Microsoft Exchange 集成选项以使用 Exchange 2013 存储存档数据在 Microsoft Exchange、 用户驻留在 Exchange 2013。 但是，某些选项实现略有不同的用户驻留在 Exchange 2013 一节中所述。 
  
若要配置新的或现有的存档配置的设置，请指定以下选项：
- **名称**每个存档配置需要的名称。 名称取决于要添加或编辑的配置的类型：
    
  - **全局配置**默认名称为 Global。 例如，Contoso 北美机构。
    
  - **网站配置**该列表包含在部署中可用的站点。 单击某个站点即可将其选中。 例如，Redmond 数据中心。
    
  - **池配置**指定合适的名称，可以是一个特定的前端池或 Standard Edition Server 部署中的名称。 例如，市场营销部门。
    
- **说明**这是可选的。 使用它来提供其他详细信息，例如使用配置的范围。 例如，法律部门的其他网站与协调一致。
    
- **存档设置**选项包括：
    
  - **存档 IM 会话**
    
  - **存档 IM 和 Web 会议会话**
    
  - **禁用存档**
    
- **阻止即时消息 (IM) 或 web 会议会话存档失败时**故障包括以下方面：
    
  - **IM**失败可能是完整数据库备份或问题的存储服务。 在此情况下，将阻止为存档启用的用户使用 IM。
    
  - **会议**失败可能是不可用的文件共享或存储服务有问题。 在此情况下，池中托管的所有活动会议在发生故障时将切换到限制模式，并且不能激活新会议。
    
    IM 和会议都能在修复故障后自动恢复。
    
- **Microsoft Exchange 集成**如果有用户驻留在 Exchange 2013，请选择此选项。 使用此选项，Exchange 2013 用于存储数据的用户，如果其邮箱已被置于就地保留。 如果您的所有用户都驻留在 Exchange 2013 中，您不需要单独的 SQL Server 数据库来存储存档数据设置。
    
- **启用清除存档数据功能**选择此选项可启用清除功能并指定清除选项，包括以下各项：
    
  - 在您指定的特定天数之后清除
    
  - 之后的存档数据清除已导出 （如果启用 Microsoft Exchange 集成，其中包括已上载到 Exchange 的数据）。
    
    > [!NOTE]
    > 如果您启用 Microsoft Exchange 集成，请清除用户驻留在 Exchange 2013 和 exchange 控制其邮箱置于就地保留。 对于会议文件，存储在 Lync Server 文件共享中是唯一的例外。 如果您选择在已导出存档数据后清除数据，或在指定的最长天数（如果您指定了最长保留天数）后清除数据，则仅在导出文件（上载到 Exchange）后才从文件共享中清除这些文件。 
  
有关的存档功能和功能，包括 Exchange 集成的详细信息，请参阅[规划存档中的业务服务器 2015 Skype](../../plan-your-deployment/archiving/archiving.md)、[业务服务器 2015年的 Skype 存档的部署](../../deploy/deploy-archiving/deploy-archiving.md)，和[管理存档中的 Skype业务服务器 2015年](../../manage/archiving/archiving.md)。

