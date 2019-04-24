---
title: 为业务 Server Skype 的配置存档策略
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8e48087-d4f0-4fe1-9e7e-f2b3e07f815f
description: 摘要： 阅读本主题可了解如何配置初始存档策略的 Skype 业务 Server 用户。
ms.openlocfilehash: 88840d10cbd7a71b32b5079a8600018b97e8b0c3
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32233242"
---
# <a name="configure-archiving-policies-for-skype-for-business-server"></a>为业务 Server Skype 的配置存档策略
 
**摘要：** 阅读本主题可了解如何配置初始存档策略的 Skype 业务 Server 用户。
  
Skype 业务服务器，在使用策略启用和禁用存档内部通信和外部通信的业务服务器驻留在 Skype 的用户。 这包括以下内容：
  
- 为业务 Server 部署 Skype 时默认创建的全局策略
    
- 指定如何为特定站点实施存档的可选站点级别策略
    
- 指定如何实现存档的特定用户的可选用户级别策略
    
您最初在部署存档时设置存档策略，但您可以在部署后更改、添加和删除策略。 在业务 Server Control Panel 的 Skype，您可以使用**存档策略**页上的**存档和监控**组管理策略在全局、 站点和用户级别。
  
> [!NOTE]
> 为了控制存档的实施，您必须指定选项，如是否存档 IM 或会议、关键模式的使用，以及清除选项。 默认情况下，在全局存档配置或任何站点或池存档配置中不会启用任何选项。 您应先指定所有适当的选项，然后再针对内部或外部通信启用存档。 有关详细信息，请参阅[配置存档的业务服务器 Skype 选项](configure-archiving-options.md)。 
  
> [!NOTE]
> 如果您部署，Exchange 就地保留策略控件上启用 Microsoft Exchange 集成，是否驻留在 Exchange 上的用户启用存档，并且具有其邮箱置于就地保留。 
  
有关如何存档策略的详细信息工作，包括的层次结构全局、 站点和用户策略，请参阅[Plan for Business Server 的 Skype 的存档](../../plan-your-deployment/archiving/archiving.md)。 有关如何管理的详细信息策略后部署，请参阅[管理 Skype 业务服务器中的存档策略](../../manage/archiving/policies.md)。
  
## <a name="global-policy"></a>全局策略

当您部署前端服务器时，业务服务器 Skype 创建存档的全局策略。 默认情况下，将在全局策略中禁用存档。 全局策略控制设置站点或用户策略，覆盖全局策略，除非您的整个部署的内部和外部通信存档启用还是为部分或全部使用 Microsoft Exchange 集成您的用户。 如果您使用 Microsoft Exchange 集成，全局策略不适用于任何用户驻留在 Exchange 和具有邮箱置于就地保留。
  
### <a name="configure-the-global-policy-for-archiving-for-skype-for-business-server-archiving-databases"></a>配置存档的 Skype Business Server 存档数据库的全局策略

1. 使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。 
    
3. 在左侧导航栏中，单击“监控和存档”****，然后单击“存档策略”****。
    
4. 在“**存档策略**”页上，单击“**全局**”，再单击“**编辑**”，然后单击“**显示详细信息**”。
    
5. 在“**编辑存档策略 - 全局**”中，执行下列操作：
    
   - 在“**名称**”中，如果不想使用全局策略的默认名称 Global，可以为其指定新名称。 
    
   - 在**说明**框中，提供有关哪些策略信息 （例如， *divisionname*的全局策略。
    
   - 要控制未通过特定站点策略或用户策略控制的所有站点和用户的内部通信存档，请选中或清除“**存档内部通信**”复选框。
    
   - 要控制未通过特定站点策略或用户策略控制的所有站点和用户的外部通信存档，请选中或清除“**存档外部通信**”复选框。
    
6. 单击“**提交**”。
    
## <a name="site-policies"></a>站点策略

您可通过为特定站点中的每个站点创建存档策略来启用或禁用这些站点的存档。 站点策略将覆盖全局策略，但用户策略将覆盖站点策略。 存档策略仅适用如果不使用 Microsoft Exchange 集成或者，如果您使用 Microsoft Exchange 集成，但有一些用户未驻留在 Exchange 上并让其邮箱置于就地保留。
  
### <a name="create-an-archiving-policy-for-a-site"></a>创建站点的存档策略

1. 使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。
    
3. 在左侧导航栏中，单击“监控和存档”****，然后单击“存档策略”****。
    
    有关如何存档策略的详细信息工作，包括的层次结构全局、 站点和用户策略，请参阅[Plan for Business Server 的 Skype 的存档](../../plan-your-deployment/archiving/archiving.md)。
    
4. 单击“**新建**”，然后单击“**站点策略**”。
    
5. 在“**选择站点**”中，单击要应用此策略的站点。
    
6. 在“**新建存档策略**”中，执行下列操作：
    
   - 在“**名称**”中，指定站点策略的名称。 
    
   - 在“**说明**”中，提供有关该站点策略内容的信息（例如，Redmond 的站点策略）。
    
   - 若要控制指定站点的内部通信存档，请选中或清除“**存档内部通信**”复选框。
    
   - 若要控制指定站点的外部通信存档，请选中或清除“**存档外部通信**”复选框。
    
7. 单击“**提交**”。
    
## <a name="user-policies"></a>用户策略

通过为用户创建和配置存档策略、然后将该策略应用于特定用户或用户组，可为特定用户启用或禁用存档。 用户策略会覆盖任何全局策略或站点策略。 存档策略仅适用如果不使用 Microsoft Exchange 集成或者，如果您使用 Microsoft Exchange 集成，但有一些用户未驻留在 Exchange 上并让其邮箱置于就地保留。
  
### <a name="configure-an-archiving-policy-for-users-homed-on-skype-for-business-server"></a>业务服务器上 Skype 位于用户配置存档策略

1. 使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。 
    
3. 在左侧导航栏中，单击“监控和存档”****，然后单击“存档策略”****。
    
4. 单击“**新建**”，然后单击“**用户策略**”。
    
5. 在“**新建存档策略**”中，执行下列操作：
    
   - 在“**名称**”中，指定用户策略的名称。 
    
   - 在“**说明**”中，提供有关该用户策略内容的信息（例如，法律部门的用户策略）。
    
   - 若要控制用户策略的内部通信存档，请选中或清除“**存档内部通信**”复选框。
    
   - 若要控制用户策略的外部通信存档，请选中或清除“**存档外部通信**”复选框。
    
6. 单击“**提交**”。
    
用户策略仅适用于为其分配策略的用户。
### <a name="apply-a-skype-for-business-server-archiving-policy-to-a-user"></a>Skype 之前应用的存档用户策略的业务服务器

1. 使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。 
    
3. 在左侧导航栏中，单击“**用户**”，然后搜索要配置的用户帐户。
    
4. 在列出搜索结果的表中，单击相应的用户帐户，再单击“**编辑**”，然后单击“**显示详细信息**”。
    
5. 在**存档策略**下的**企业服务器用户编辑 Skype**中，选择要应用的存档用户策略。
    
    > [!NOTE]
    > **\<自动\>** 设置应用默认服务器安装设置。 服务器将自动应用这些设置。
  
6. 单击“**提交**”。
    

