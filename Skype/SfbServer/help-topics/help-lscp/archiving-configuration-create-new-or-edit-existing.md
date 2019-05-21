---
title: 存档配置新建或编辑现有
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.MonArchSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49096960-c442-4846-be8f-03c167acea41
description: 使用存档配置可控制用于部署的存档选项。存档配置包括全局配置以及可选的一个或多个站点和池配置：
ms.openlocfilehash: d40750069d34cb274342c1f5aab5d8191f90a334
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299874"
---
# <a name="archiving-configuration-create-new-or-edit-existing"></a>存档配置：创建新的或编辑现有的
 
使用存档配置可控制用于部署的存档选项。存档配置包括全局配置以及可选的一个或多个站点和池配置：
  
- **全局配置**默认情况下会创建全局配置。 您可以编辑全局配置，但无法删除此存档配置。 如果您尝试将其删除，则所有选项将重置为默认值。
    
- **网站配置 (可选)** 你可以指定一个或多个网站存档配置, 每个配置都可以配置用于控制特定网站的存档选项。 站点配置会覆盖全局配置，但仅限于在存档站点配置中指定的站点。 可以编辑或删除站点配置。
    
- **池配置 (可选)** 你可以指定一个或多个池存档配置, 以控制特定池的存档选项。 池配置会覆盖全局配置和站点配置，但仅限于在存档池配置中指定的池。 可以编辑或删除池配置。
    
> [!NOTE]
> 存档配置适用于驻留在 Skype for business Server 上的用户, 如果你启用 Microsoft Exchange 集成选项以使用 Exchange 2013 将存档数据存储在 Microsoft Exchange 中, 请向托管在 Exchange 2013 的用户。 但是, 对于驻留在 Exchange 2013 上的用户而言, 某些选项的实现方式稍有不同, 如下一节所述。 
  
若要配置新的或现有的存档配置的设置，请指定以下选项：
- **名称**每个存档配置都需要一个名称。 该名称由你添加或编辑的配置类型确定:
    
  - **全局配置**默认名称为全局名称。 例如，Contoso 北美机构。
    
  - **网站配置**列表包含部署中的可用网站。 单击某个站点即可将其选中。 例如，Redmond 数据中心。
    
  - **池配置**指定一个合适的名称, 该名称可以是部署中特定前端池或标准版服务器的名称。 例如，市场营销部门。
    
- **说明**这是可选操作。 使用它提供其他详细信息, 如配置的范围或使用。 例如, 与其他网站的法律部门协调。
    
- **存档设置**选项包括以下内容:
    
  - **存档 IM 会话**
    
  - **存档 IM 和 Web 会议会话**
    
  - **禁用存档**
    
- **如果存档失败, 阻止即时消息 (IM) 或 web 会议会话**失败包括以下几项:
    
  - **IM**故障可能是整个数据库或存储服务有问题。 在此情况下，将阻止为存档启用的用户使用 IM。
    
  - **会议**故障可能是不可用的文件共享或存储服务有问题。 在此情况下，池中托管的所有活动会议在发生故障时将切换到限制模式，并且不能激活新会议。
    
    IM 和会议都能在修复故障后自动恢复。
    
- **Microsoft Exchange 集成**如果你拥有托管在 Exchange 2013 上的用户, 请选择此选项。 使用此选项, 如果用户的邮箱已放置在原地保留, 则 Exchange 2013 用于存储这些用户的数据。 如果你的所有用户都托管在 Exchange 2013 中, 则无需设置单独的 SQL Server 数据库来存储存档数据。
    
- **启用清除存档数据**选择此选项可启用清除并指定清除选项, 包括以下内容:
    
  - 在您指定的特定天数之后清除
    
  - 在导出存档数据 (包括已上载到 Exchange 的数据, 如果启用 Microsoft Exchange 集成) 后清除。
    
    > [!NOTE]
    > 如果启用 Microsoft Exchange 集成, 请清除托管在 Exchange 2013 上的用户, 并将其邮箱置于就地保留状态由 Exchange 控制。 唯一的例外是存储在 Lync Server 文件共享上的会议文件。 如果您选择在已导出存档数据后清除数据，或在指定的最长天数（如果您指定了最长保留天数）后清除数据，则仅在导出文件（上载到 Exchange）后才从文件共享中清除这些文件。 
  
有关存档功能和功能 (包括 Exchange 集成) 的详细信息, 请参阅[在 skype for Business server 2015 中计划存档](../../plan-your-deployment/archiving/archiving.md)、[部署 Skype for business server 2015 存档](../../deploy/deploy-archiving/deploy-archiving.md)和[管理 skype for business 中的存档Business Server 2015](../../manage/archiving/archiving.md)。

