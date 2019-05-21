---
title: 配置 Skype for Business 服务器的存档策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8e48087-d4f0-4fe1-9e7e-f2b3e07f815f
description: '摘要: 阅读本主题, 了解如何为 Skype for business Server 用户配置初始存档策略。'
ms.openlocfilehash: 9d4fc7bd27440688f981ac9d05b1e47750ad7867
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286558"
---
# <a name="configure-archiving-policies-for-skype-for-business-server"></a>配置 Skype for Business 服务器的存档策略
 
**摘要:** 阅读本主题, 了解如何为 Skype for Business Server 用户配置初始存档策略。
  
在 Skype for Business Server 中, 你可以使用策略为托管在 Skype for business 服务器上的用户启用和禁用内部通信和外部通信的存档。 这包括以下内容：
  
- 部署 Skype for Business 服务器时默认创建的全局策略
    
- 指定如何为特定站点实施存档的可选站点级别策略
    
- 指定如何为特定用户实施存档的可选用户级策略
    
您最初在部署存档时设置存档策略，但您可以在部署后更改、添加和删除策略。 在 "Skype for Business 服务器控制面板" 中, 可以使用 "**存档和监视**" 组的 "**存档策略**" 页面管理全局、网站和用户级别的策略。
  
> [!NOTE]
> 为了控制存档的实施，您必须指定选项，如是否存档 IM 或会议、关键模式的使用，以及清除选项。 默认情况下，在全局存档配置或任何站点或池存档配置中不会启用任何选项。 您应先指定所有适当的选项，然后再针对内部或外部通信启用存档。 有关详细信息, 请参阅[配置 Skype for Business 服务器的存档选项](configure-archiving-options.md)。 
  
> [!NOTE]
> 如果为你的部署启用 Microsoft Exchange 集成, 则 Exchange 就地保留策略控制是否为托管于 Exchange 的用户启用存档, 并将其邮箱置于原地保留。 
  
有关存档策略的工作原理的详细信息, 包括全局、网站和用户策略的层次结构, 请参阅[Skype For Business 服务器中的存档计划](../../plan-your-deployment/archiving/archiving.md)。 有关如何在部署后管理策略的详细信息, 请参阅[管理 Skype For Business 服务器中的存档策略](../../manage/archiving/policies.md)。
  
## <a name="global-policy"></a>全局策略

当您部署前端服务器时, Skype for Business 服务器将为存档创建全局策略。 默认情况下，将在全局策略中禁用存档。 全局策略控制是否为整个部署启用存档以进行内部和外部通信, 除非你设置网站或用户策略 (这将覆盖全局策略), 或者你对部分或全部使用 Microsoft Exchange 集成您的用户。 如果您使用 Microsoft Exchange 集成, 则全局策略不会应用于托管在 Exchange 上的任何用户, 并将邮箱置于原地保留状态。
  
### <a name="configure-the-global-policy-for-archiving-for-skype-for-business-server-archiving-databases"></a>为 Skype for business Server 存档数据库配置全局策略以存档

1. 使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 打开一个浏览器窗口, 然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。 
    
3. 在左侧导航栏中，单击“监控和存档”****，然后单击“存档策略”****。
    
4. 在“**存档策略**”页上，单击“**全局**”，再单击“**编辑**”，然后单击“**显示详细信息**”。
    
5. 在“**编辑存档策略 - 全局**”中，执行下列操作：
    
   - 在“**名称**”中，如果不想使用全局策略的默认名称 Global，可以为其指定新名称。 
    
   - 在 "**说明**" 中, 提供有关策略的内容 (例如, *divisionName*的全局策略) 的信息。
    
   - 要控制未通过特定站点策略或用户策略控制的所有站点和用户的内部通信存档，请选中或清除“**存档内部通信**”复选框。
    
   - 要控制未通过特定站点策略或用户策略控制的所有站点和用户的外部通信存档，请选中或清除“**存档外部通信**”复选框。
    
6. 单击“**提交**”。
    
## <a name="site-policies"></a>站点策略

您可通过为特定站点中的每个站点创建存档策略来启用或禁用这些站点的存档。 站点策略将覆盖全局策略，但用户策略将覆盖站点策略。 仅当你不使用 Microsoft Exchange 集成时, 或者, 如果你使用的是 Microsoft Exchange 集成, 但某些用户没有托管在 Exchange 上, 并且其邮箱放置在原地保留中, 则仅适用于存档策略。
  
### <a name="create-an-archiving-policy-for-a-site"></a>创建站点的存档策略

1. 使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 打开一个浏览器窗口, 然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。
    
3. 在左侧导航栏中，单击“监控和存档”****，然后单击“存档策略”****。
    
    有关存档策略的工作原理的详细信息, 包括全局、网站和用户策略的层次结构, 请参阅[Skype For Business 服务器中的存档计划](../../plan-your-deployment/archiving/archiving.md)。
    
4. 单击“**新建**”，然后单击“**站点策略**”。
    
5. 在“**选择站点**”中，单击要应用此策略的站点。
    
6. 在“**新建存档策略**”中，执行下列操作：
    
   - 在“**名称**”中，指定站点策略的名称。 
    
   - 在“**说明**”中，提供有关该站点策略内容的信息（例如，Redmond 的站点策略）。
    
   - 若要控制指定站点的内部通信存档，请选中或清除“**存档内部通信**”复选框。
    
   - 若要控制指定站点的外部通信存档，请选中或清除“**存档外部通信**”复选框。
    
7. 单击“**提交**”。
    
## <a name="user-policies"></a>用户策略

通过为用户创建和配置存档策略、然后将该策略应用于特定用户或用户组，可为特定用户启用或禁用存档。 用户策略会覆盖任何全局策略或站点策略。 仅当你不使用 Microsoft Exchange 集成时, 或者, 如果你使用的是 Microsoft Exchange 集成, 但某些用户没有托管在 Exchange 上, 并且其邮箱放置在原地保留中, 则仅适用于存档策略。
  
### <a name="configure-an-archiving-policy-for-users-homed-on-skype-for-business-server"></a>为驻留在 Skype for business 服务器上的用户配置存档策略

1. 使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 打开一个浏览器窗口, 然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。 
    
3. 在左侧导航栏中，单击“监控和存档”****，然后单击“存档策略”****。
    
4. 单击“**新建**”，然后单击“**用户策略**”。
    
5. 在“**新建存档策略**”中，执行下列操作：
    
   - 在“**名称**”中，指定用户策略的名称。 
    
   - 在“**说明**”中，提供有关该用户策略内容的信息（例如，法律部门的用户策略）。
    
   - 若要控制用户策略的内部通信存档，请选中或清除“**存档内部通信**”复选框。
    
   - 若要控制用户策略的外部通信存档，请选中或清除“**存档外部通信**”复选框。
    
6. 单击“**提交**”。
    
用户策略仅适用于为其分配策略的用户。
### <a name="apply-a-skype-for-business-server-archiving-policy-to-a-user"></a>将 Skype for Business 服务器存档策略应用于用户

1. 使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 打开一个浏览器窗口, 然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。 
    
3. 在左侧导航栏中，单击“**用户**”，然后搜索要配置的用户帐户。
    
4. 在列出搜索结果的表中，单击相应的用户帐户，再单击“**编辑**”，然后单击“**显示详细信息**”。
    
5. 在 "编辑**策略**" 下的 "**编辑 Skype for business 服务器" 用户**中, 选择要应用的存档用户策略。
    
    > [!NOTE]
    > " ** \<自动\> **设置" 应用默认服务器安装设置。 服务器将自动应用这些设置。
  
6. 单击“**提交**”。
    

