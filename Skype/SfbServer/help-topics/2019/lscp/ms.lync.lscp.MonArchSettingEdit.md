---
title: 存档配置创建新的或编辑现有的
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.MonArchSettingEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 49096960-c442-4846-be8f-03c167acea41
ROBOTS: NOINDEX, NOFOLLOW
description: 使用存档配置可控制部署的存档选项。 存档配置包括全局配置以及可选的一个或多个站点和池配置：
ms.openlocfilehash: 77d1be61be3a1bad063bb7f32957937f182094e4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812252"
---
# <a name="archiving-configuration-create-new-or-edit-existing"></a>存档配置：创建新的或编辑现有的
 
使用存档配置可控制部署的存档选项。 存档配置包括全局配置以及可选的一个或多个站点和池配置：
  
- **全局配置** 默认情况下将创建全局配置。 您可以编辑全局配置，但无法删除此存档配置。 如果您尝试将其删除，则所有选项将重置为默认值。
    
- **站点配置 (可选)** 可以指定一个或多个站点存档配置，每个存档配置都可以配置为控制特定站点的存档选项。 站点配置会覆盖全局配置，但仅限于在存档站点配置中指定的站点。 可以编辑或删除站点配置。
    
- **池配置 (可选)** 可以指定一个或多个池存档配置，以控制特定池的存档选项。 池配置会覆盖全局配置和站点配置，但仅限于在存档池配置中指定的池。 可以编辑或删除池配置。
    
> [!NOTE]
> 存档配置适用于 Skype for Business Server 上用户，如果启用 Microsoft Exchange 集成选项以使用 Exchange 存储 Microsoft Exchange 中的存档数据，则存档配置适用于位于 Exchange 上的用户。 但是，某些选项的实现方式对于 Exchange 上的用户略有不同，如下一节中所述。 
  
若要配置新的或现有的存档配置的设置，请指定以下选项：
- **名称** 每个存档配置都需要一个名称。 该名称由要添加或编辑的配置类型决定：
    
  - **全局配置** 默认名称为 Global。 例如，Contoso 北美机构。
    
  - **站点配置** 该列表包含部署中的可用站点。 单击某个站点将其选中。 例如，Redmond 数据中心。
    
  - **池配置** 指定适当的名称，该名称可以是部署中的特定前端池或 Standard Edition Server 的名称。 例如，市场营销部门。
    
- **说明** 这是可选的。 使用它提供其他详细信息，例如配置的范围或使用。 例如，与其他网站的法律部门协调。
    
- **存档设置** 选项包括：
    
  - **存档 IM 会话**
    
  - **存档 IM 和 Web 会议会话**
    
  - **禁用存档**
    
- **存档失败时阻止即时消息 (IM)** 或 Web 会议会话故障包括：
    
  - **IM** A failure could be a full database or problem with the storage service. 在此情况下，将阻止为存档启用的用户使用 IM。
    
  - **会议** 故障可能是文件共享不可用或存储服务出现问题。 在此情况下，池中托管的所有活动会议在发生故障时将切换到限制模式，并且不能激活新会议。
    
    IM 和会议都能在修复故障后自动恢复。
    
- **Microsoft Exchange 集成** 如果您的用户位于 Exchange 上，请选择此选项。 使用此选项，如果这些用户的邮箱已置于"保留"状态，则 Exchange 用于存储In-Place数据。 如果您的所有用户都位于 Exchange 上，则无需设置单独的存档SQL Server数据库来存储存档数据。
    
- **启用存档数据的清除** 选择此选项可启用清除并指定清除选项，其中包括：
    
  - 在您指定的特定天数之后清除
    
  - 导出存档数据后清除 (包括已上载到 Exchange 的数据（如果启用了 Microsoft Exchange 集成) ）。
    
    > [!NOTE]
    > 如果启用 Microsoft Exchange 集成，则 Exchange 上用户及其邮箱处于"保留"状态In-Place清除由 Exchange 控制。 唯一的例外是存储在 Lync Server 文件共享上的会议文件。 如果您选择在已导出存档数据后清除数据，或在指定的最长天数（如果您指定了最长保留天数）后清除数据，则仅在导出文件（上载到 Exchange）后才从文件共享中清除这些文件。 
  
有关存档特性和功能的详细信息，包括 Exchange 集成，请参阅 Plan [for archiving in Skype for Business Server，](../../../plan-your-deployment/archiving/archiving.md)Deploy archiving for Skype for Business [Server，](../../../deploy/deploy-archiving/deploy-archiving.md)and [Manage archiving in Skype for Business Server.](../../../manage/archiving/archiving.md)

