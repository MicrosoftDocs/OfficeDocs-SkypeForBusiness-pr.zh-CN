---
title: 为 Skype for Business Server 2015 配置存档策略
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8e48087-d4f0-4fe1-9e7e-f2b3e07f815f
description: 摘要： 请阅读本主题，以了解如何配置为 Skype 业务服务器 2015年用户的初始归档策略。
ms.openlocfilehash: 9829d0c5ad5ea9e62c2335c3387fcd22623c6751
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="configure-archiving-policies-for-skype-for-business-server-2015"></a>为 Skype for Business Server 2015 配置存档策略
 
**摘要：**阅读本主题，以了解如何为业务服务器 2015年用户的 Skype 配置初始归档策略。
  
在 Skype 业务服务器，可以使用策略来启用和禁用存档内部通信和外部通信的业务服务器驻留在 Skype 的用户。 这包括以下内容：
  
- 为业务服务器部署 Skype 时默认创建一个全局策略
    
- 指定如何为特定站点实施存档的可选站点级别策略
    
- 指定如何存档的特定用户实现的可选用户级策略
    
您最初在部署存档时设置存档策略，但您可以在部署后更改、添加和删除策略。 在 Skype 业务服务器控件面板，可以使用**存档和监视**组的**存档策略**页管理策略在全局、 站点和用户级别。
  
> [!NOTE]
> 为了控制存档的实施，您必须指定选项，如是否存档 IM 或会议、关键模式的使用，以及清除选项。 默认情况下，在全局存档配置或任何站点或池存档配置中不会启用任何选项。 您应先指定所有适当的选项，然后再针对内部或外部通信启用存档。 有关详细信息，请参阅[配置存档业务服务器 2015年的 Skype 的选项](configure-archiving-options.md)。 
  
> [!NOTE]
> 如果您的部署 Exchange 的就地保存策略控制启用 Microsoft Exchange 集成是否驻留在 Exchange 的用户启用存档和保留在原位上放有自己的邮箱。 
  
有关如何存档策略的详细信息的工作，包括全局站点的层次结构，用户策略，请参阅[规划业务服务器 2015年的 Skype 在存档](../../plan-your-deployment/archiving/archiving.md)。 详细信息有关如何管理策略后部署，请参阅[管理中业务服务器 2015年的 Skype 的存档策略](../../manage/archiving/policies.md)。
  
## <a name="global-policy"></a>全局策略

在部署您前端服务器时，Skype 业务服务器创建存档的全局策略。 默认情况下，将在全局策略中禁用存档。 全球政策控制已启用存档为内部和外部通讯的整个部署，除非您设置站点或用户策略，覆盖全球的政策，还是您的部分或全部使用 Microsoft Exchange 集成您的用户。 如果您使用 Microsoft Exchange 集成，全球政策不适用于驻留在 Exchange 的任何用户，并具有邮箱放在原位保存。
  
### <a name="configure-the-global-policy-for-archiving-for-skype-for-business-server-archiving-databases"></a>配置存档的 Skype 业务 Server 存档数据库的全局策略

1. 使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 打开浏览器窗口，然后输入管理员 URL 打开 Skype 业务服务器控件面板。 
    
3. 在左侧导航栏中，单击“**监控和存档**”，然后单击“**存档策略**”。
    
4. 在“**存档策略**”页上，单击“**全局**”，再单击“**编辑**”，然后单击“**显示详细信息**”。
    
5. 在“**编辑存档策略 - 全局**”中，执行下列操作：
    
   - 在“**名称**”中，如果不想使用全局策略的默认名称 Global，可以为其指定新名称。 
    
   - 在**说明**提供了有关的策略是什么 （例如，对于*divisionName*的全球政策。
    
   - 要控制未通过特定站点策略或用户策略控制的所有站点和用户的内部通信存档，请选中或清除“**存档内部通信**”复选框。
    
   - 要控制未通过特定站点策略或用户策略控制的所有站点和用户的外部通信存档，请选中或清除“**存档外部通信**”复选框。
    
6. 单击“**提交**”。
    
## <a name="site-policies"></a>站点策略

您可通过为特定站点中的每个站点创建存档策略来启用或禁用这些站点的存档。 站点策略将覆盖全局策略，但用户策略将覆盖站点策略。 存档策略仅应用如果不使用 Microsoft Exchange 集成或如果您使用 Microsoft Exchange 的集成，但保留在原位上放有一些没有驻留在 Exchange 和拥有自己的邮箱的用户。
  
### <a name="create-an-archiving-policy-for-a-site"></a>创建站点的存档策略

1. 使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 打开浏览器窗口，然后输入管理员 URL 打开 Skype 业务服务器控件面板。
    
3. 在左侧导航栏中，单击“**监控和存档**”，然后单击“**存档策略**”。
    
    有关如何存档策略的详细信息的工作，包括全局站点的层次结构，用户策略，请参阅[规划业务服务器 2015年的 Skype 在存档](../../plan-your-deployment/archiving/archiving.md)。
    
4. 单击“**新建**”，然后单击“**站点策略**”。
    
5. 在“**选择站点**”中，单击要应用此策略的站点。
    
6. 在“**新建存档策略**”中，执行下列操作：
    
   - 在“**名称**”中，指定站点策略的名称。 
    
   - 在“**说明**”中，提供有关该站点策略内容的信息（例如，Redmond 的站点策略）。
    
   - 若要控制指定站点的内部通信存档，请选中或清除“**存档内部通信**”复选框。
    
   - 若要控制指定站点的外部通信存档，请选中或清除“**存档外部通信**”复选框。
    
7. 单击“**提交**”。
    
## <a name="user-policies"></a>用户策略

通过为用户创建和配置存档策略、然后将该策略应用于特定用户或用户组，可为特定用户启用或禁用存档。 用户策略会覆盖任何全局策略或站点策略。 存档策略仅应用如果不使用 Microsoft Exchange 集成或如果您使用 Microsoft Exchange 的集成，但保留在原位上放有一些没有驻留在 Exchange 和拥有自己的邮箱的用户。
  
### <a name="configure-an-archiving-policy-for-users-homed-on-skype-for-business-server"></a>用户为业务服务器驻留在 Skype 上配置的存档策略

1. 使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 打开浏览器窗口，然后输入管理员 URL 打开 Skype 业务服务器控件面板。 
    
3. 在左侧导航栏中，单击“**监控和存档**”，然后单击“**存档策略**”。
    
4. 单击“**新建**”，然后单击“**用户策略**”。
    
5. 在“**新建存档策略**”中，执行下列操作：
    
   - 在“**名称**”中，指定用户策略的名称。 
    
   - 在“**说明**”中，提供有关该用户策略内容的信息（例如，法律部门的用户策略）。
    
   - 若要控制用户策略的内部通信存档，请选中或清除“**存档内部通信**”复选框。
    
   - 若要控制用户策略的外部通信存档，请选中或清除“**存档外部通信**”复选框。
    
6. 单击“**提交**”。
    
用户策略仅适用于为其分配策略的用户。
### <a name="apply-a-skype-for-business-server-archiving-policy-to-a-user"></a>适用于业务服务器存档策略向用户的 Skype

1. 使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 打开浏览器窗口，然后输入管理员 URL 打开 Skype 业务服务器控件面板。 
    
3. 在左侧导航栏中，单击“**用户**”，然后搜索要配置的用户帐户。
    
4. 在列出搜索结果的表中，单击相应的用户帐户，再单击“**编辑**”，然后单击“**显示详细信息**”。
    
5. 在**存档策略**下**编辑业务服务器用户的 Skype** ，选择您要应用的存档用户策略。
    
    > [!NOTE]
    > **\<自动\>**设置应用默认服务器安装设置。 服务器将自动应用这些设置。
  
6. 单击“**提交**”。
    

