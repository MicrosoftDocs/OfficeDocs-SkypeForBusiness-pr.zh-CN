---
title: 在 Skype for Business Server 2015 中管理存档策略
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 75ce32ba-eb82-4339-9c02-5df5f2c2ebd2
description: 摘要： 了解如何管理用户 Skype 业务服务器 2015年的存档策略。
ms.openlocfilehash: 584849862e106098bc4bbad92ed4e0b87be410e9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="manage-archiving-policies-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中管理存档策略

**摘要：**了解如何管理用户 Skype 业务服务器 2015年的存档策略。
  
您初次设置归档策略，当您部署存档，但您可以更改、 添加和删除部署后配置。 存档策略确定是否存档： 
  
- 内部通信
    
- 外部通信
    
存档策略可以在全局组、 站点或用户级别。
  
> [!NOTE]
> 如果您启用 Microsoft Exchange 集成部署，交换策略控制是否驻留在 Exchange 的用户启用存档和保留在原位上放有自己的邮箱。 有关详细信息，请参阅[规划业务服务器 2015年的 Skype 在归档](../../plan-your-deployment/archiving/archiving.md)和[具有的业务服务器 2015 Skype 的 Exchange 存储配置集成](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md)。 
  
## <a name="manage-archiving-policies-by-using-the-control-panel"></a>使用控制面板管理存档策略

可以使用控制面板管理存档策略，如下所示：
  
1. 使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。 
    
2. 打开浏览器窗口，然后输入管理员 URL 打开 Skype 业务服务器控件面板。 
    
3. 在左侧导航栏中，单击“**存档策略**”
    
## <a name="manage-archiving-policies-by-using-windows-powershell"></a>使用 Windows PowerShell 管理存档策略

也可以使用下表中列出的 Windows PowerShell cmdlet 配置存档策略。 有关语法，包括所有的可用参数的详细信息请参阅[业务服务器 2015年管理外壳的 Skype](../management-shell.md)。
  

|**Cmdlet**|**说明**|
|:-----|:-----|
|获得 CsArchivingPolicy  <br/> |返回有关您组织的即时消息 (IM) 会话存档策略的信息。  <br/> |
|授予 CsArchivingPolicy  <br/> |将即时消息 (IM) 会话存档策略分配给用户或用户集。 通过这些策略，您可以存档在内部用户之间发生的所有 IM 会话，以及/或者存档在内部用户与外部伙伴之间发生的所有 IM 会话。  <br/> |
|新 CsArchivingPolicy  <br/> |创建新的即时消息 (IM) 会话存档策略。 通过这些策略，您可以存档在内部用户之间发生的所有 IM 会话，以及/或者存档在内部用户与外部伙伴之间发生的所有 IM 会话。  <br/> |
|删除 CsArchivingPolicy  <br/> |删除存档策略，用于确定是否 Skype 业务服务器自动将所有内部用户，和/或内部用户和联盟的用户之间的所有 IM 会话之间进行的 IM 会话指定即时消息 (IM)。  <br/> |
|一组 CsArchivingPolicy  <br/> |修改现有的即时消息 (IM) 存档策略。 通过存档策略，您可以存档在内部用户之间发生的所有 IM 会话和会议；您还可以存档在内部用户与联盟伙伴之间发生的会话。  <br/> |
   

