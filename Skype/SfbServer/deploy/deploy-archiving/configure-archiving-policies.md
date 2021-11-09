---
title: 配置存档策略Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: e8e48087-d4f0-4fe1-9e7e-f2b3e07f815f
description: 摘要：阅读本主题，了解如何为用户配置Skype for Business Server策略。
ms.openlocfilehash: 96d53ae71a8faa72c5dcdc3816c09c1b6d492e67
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60853786"
---
# <a name="configure-archiving-policies-for-skype-for-business-server"></a>配置存档策略Skype for Business Server
 
**摘要：** 阅读本主题，了解如何为用户配置Skype for Business Server策略。
  
在Skype for Business Server中，可以使用策略为内部通信和外部通信启用和禁用对位于 Skype for Business Server 上的用户的存档。 其中包括：
  
- 部署策略时默认创建的全局Skype for Business Server
    
- 指定如何为特定站点实施存档的可选站点级别策略
    
- 指定如何为特定用户实施存档的可选用户级别策略
    
您最初在部署存档时设置存档策略，但您可以在部署后更改、添加和删除策略。 在Skype for Business Server控制面板中，可以使用"存档和监控"组的"存档策略"页来管理全局、站点和用户级别的策略。
  
> [!NOTE]
> 若要控制存档的实现，必须指定选项，例如是否存档 IM 或会议、关键模式的使用和清除选项。 默认情况下，在全局存档配置或任何站点或池存档配置中未启用任何选项。 在启用内部或外部通信的存档之前，应指定所有适当的选项。 有关详细信息，请参阅[Configure archiving options for Skype for Business Server](configure-archiving-options.md)。 
  
> [!NOTE]
> 如果为部署启用 Microsoft Exchange 集成，Exchange In-Place 保留策略将控制是否对位于 Exchange 上且其邮箱已置于 In-Place 保留状态的用户启用存档。 
  
有关存档策略如何工作的详细信息（包括全局、站点和用户策略的层次结构）的信息，请参阅 Plan [for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md)。 有关部署后如何管理策略的详细信息，请参阅在部署[后管理Skype for Business Server。](../../manage/archiving/policies.md)
  
## <a name="global-policy"></a>全局策略

部署前端服务器时，Skype for Business Server创建全局存档策略。 默认情况下，全局策略中禁用存档。 全局策略控制是否针对整个部署的内部和外部通信启用存档，除非您设置了站点或用户策略（这将覆盖全局策略）或者对部分或所有用户使用 Microsoft Exchange 集成。 如果使用 Microsoft Exchange集成，则全局策略不适用于位于 Exchange 上且将邮箱置于保留In-Place用户。
  
### <a name="configure-the-global-policy-for-archiving-for-skype-for-business-server-archiving-databases"></a>配置存档数据库的全局Skype for Business Server策略

1. 使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。 
    
3. 在左侧导航栏中，单击 **“监控和存档”**，然后单击 **“存档策略”**。
    
4. 在“存档策略”页上，单击“全局”，再单击“编辑”，然后单击“显示详细信息”。
    
5. 在“编辑存档策略 - 全局”中，执行下列操作：
    
   - 在“名称”中，如果不想使用全局策略的默认名称 Global，可以为其指定新名称。 
    
   - 在 **"说明**"中，提供有关策略 (例如  *，divisionName*  的全局策略。
    
   - 要控制未通过特定站点策略或用户策略控制的所有站点和用户的内部通信存档，请选中或清除“存档内部通信”复选框。
    
   - 要控制未通过特定站点策略或用户策略控制的所有站点和用户的外部通信存档，请选中或清除“存档外部通信”复选框。
    
6. 单击“提交”。
    
## <a name="site-policies"></a>网站策略

可以通过为特定站点的每个站点创建存档策略来启用或禁用存档。 站点策略会覆盖全局策略，但用户策略会覆盖站点策略。 存档策略仅在您不使用 Microsoft Exchange 集成或如果您使用 Microsoft Exchange 集成，但有些用户未位于 Exchange 且其邮箱被置于 In-Place 保留状态时适用。
  
### <a name="create-an-archiving-policy-for-a-site"></a>为站点创建存档策略

1. 使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。
    
3. 在左侧导航栏中，单击 **“监控和存档”**，然后单击 **“存档策略”**。
    
    有关存档策略如何工作的详细信息（包括全局、站点和用户策略的层次结构）的信息，请参阅 Plan [for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md)。
    
4. 单击“新建”，然后单击“站点策略”。
    
5. 在 **"选择站点**"中，单击要应用策略的站点。
    
6. 在 **“新建存档策略”** 中，执行下列操作：
    
   - 在 **"名称**"中，指定站点策略的名称。 
    
   - 在 **"说明**"中，提供有关站点策略 (例如，Redmond) 。
    
   - 若要控制指定站点的内部通信存档，请选中或清除"存档 **内部通信"** 复选框。
    
   - 若要控制指定站点的外部通信存档，请选中或清除"存档 **外部通信"** 复选框。
    
7. 单击“提交”。
    
## <a name="user-policies"></a>用户策略

通过为用户创建和配置存档策略，然后将该策略应用于特定用户或用户组，您可以为特定用户启用或禁用存档。 用户策略会覆盖任何全局策略或站点策略。 存档策略仅在您不使用 Microsoft Exchange 集成或如果您使用 Microsoft Exchange 集成，但有些用户未位于 Exchange 且其邮箱被置于 In-Place 保留状态时适用。
  
### <a name="configure-an-archiving-policy-for-users-homed-on-skype-for-business-server"></a>为本地用户配置存档Skype for Business Server

1. 使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。 
    
3. 在左侧导航栏中，单击 **“监控和存档”**，然后单击 **“存档策略”**。
    
4. 单击 **“新建”**，然后单击 **“用户策略”**。
    
5. 在“新建存档策略”中，执行下列操作：
    
   - 在“名称”中，指定用户策略的名称。 
    
   - 在“说明”中，提供有关该用户策略内容的信息（例如，法律部门的用户策略）。
    
   - 若要控制用户策略的内部通信存档，请选中或清除“存档内部通信”复选框。
    
   - 若要控制用户策略的外部通信存档，请选中或清除“存档外部通信”复选框。
    
6. 单击“提交”。
    
用户策略仅适用于为其分配策略的用户。
### <a name="apply-a-skype-for-business-server-archiving-policy-to-a-user"></a>将Skype for Business Server存档策略应用于用户

1. 使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。 
    
3. 在左侧导航栏中，单击“用户”，然后搜索要配置的用户帐户。
    
4. 在列出搜索结果的表中，单击相应的用户帐户，再单击“编辑”，然后单击“显示详细信息”。
    
5. 在 **"Skype for Business Server** 策略"下的"编辑用户"中，选择要应用存档用户策略。
    
    > [!NOTE]
    > 这些设置 **\<Automatic\>** 将应用默认服务器安装设置。 服务器将自动应用这些设置。
  
6. 单击“提交”。
    

