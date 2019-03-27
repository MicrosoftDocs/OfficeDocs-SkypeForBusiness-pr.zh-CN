---
title: Skype 中的存档策略管理业务服务器 （英文）
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 75ce32ba-eb82-4339-9c02-5df5f2c2ebd2
description: 摘要： 了解如何管理业务服务器 Skype 的存档用户策略。
ms.openlocfilehash: 289902ded6f1530c74f9c945517a3c853c99d364
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30873238"
---
# <a name="manage-archiving-policies-in-skype-for-business-server"></a>Skype 中的存档策略管理业务服务器 （英文）

**摘要：** 了解如何管理业务服务器 Skype 的存档用户策略。
  
您最初设置了当您部署存档，但您可以更改、 添加和删除部署后的配置存档策略。 存档策略确定是否存档： 
  
- 内部通信
    
- 外部通信
    
存档策略可以是在全局设置、 站点或用户级别。
  
> [!NOTE]
> 如果您为您的部署，Exchange 策略控件上启用 Microsoft Exchange 集成，是否驻留在 Exchange 上的用户启用存档，并且具有其邮箱置于就地保留。 有关详细信息，请参阅[规划存档中的业务服务器 Skype](../../plan-your-deployment/archiving/archiving.md)和[配置与业务服务器 Skype 的 Exchange 存储的集成](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md)。 
  
## <a name="manage-archiving-policies-by-using-the-control-panel"></a>使用控制面板管理存档策略

可以使用控制面板管理存档策略，如下所示：
  
1. 使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。 
    
2. 打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。 
    
3. 在左侧导航栏中，单击“**存档策略**”
    
## <a name="manage-archiving-policies-by-using-windows-powershell"></a>使用 Windows PowerShell 管理存档策略

也可以使用下表中列出的 Windows PowerShell cmdlet 配置存档策略。 有关语法，包括所有可用的参数的详细信息，请参阅[Business Server Management Shell 的 Skype](../management-shell.md)。
  

|**Cmdlet**|**说明**|
|:-----|:-----|
|Get-CsArchivingPolicy  <br/> |返回有关您组织的即时消息 (IM) 会话存档策略的信息。  <br/> |
|Grant-CsArchivingPolicy  <br/> |将即时消息 (IM) 会话存档策略分配给用户或用户集。 通过这些策略，您可以存档在内部用户之间发生的所有 IM 会话，以及/或者存档在内部用户与外部伙伴之间发生的所有 IM 会话。  <br/> |
|New-CsArchivingPolicy  <br/> |创建新的即时消息 (IM) 会话存档策略。 通过这些策略，您可以存档在内部用户之间发生的所有 IM 会话，以及/或者存档在内部用户与外部伙伴之间发生的所有 IM 会话。  <br/> |
|Remove-CsArchivingPolicy  <br/> |删除存档策略，用于确定是否 Skype 业务服务器自动保存所有内部用户和/或内部用户和联盟的伙伴之间的所有 IM 会话之间进行的 IM 会话的指定即时消息 (IM)。  <br/> |
|Set-CsArchivingPolicy  <br/> |修改现有的即时消息 (IM) 存档策略。 通过存档策略，您可以存档在内部用户之间发生的所有 IM 会话和会议；您还可以存档在内部用户与联盟伙伴之间发生的会话。  <br/> |
   

