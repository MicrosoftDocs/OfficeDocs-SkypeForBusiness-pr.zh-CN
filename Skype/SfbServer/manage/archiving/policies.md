---
title: 管理 Skype for Business 服务器中的存档策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 75ce32ba-eb82-4339-9c02-5df5f2c2ebd2
description: 摘要：了解如何管理适用于 Skype for business 服务器存档的用户策略。
ms.openlocfilehash: f2dca47dd7fd3095b2865ff72516b6be84144352
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818884"
---
# <a name="manage-archiving-policies-in-skype-for-business-server"></a>管理 Skype for Business 服务器中的存档策略

**摘要：** 了解如何管理用于 Skype for Business 服务器存档的用户策略。
  
你在部署存档时最初设置存档策略，但你可以在部署后更改、添加和删除配置。 存档策略确定是否存档： 
  
- 内部通信
    
- 外部通信
    
可以在全局、网站或用户级别设置存档策略。
  
> [!NOTE]
> 如果为你的部署启用了 Microsoft Exchange 集成，Exchange 策略将控制是否为托管在 Exchange 上的用户启用存档，并将其邮箱置于原地保留。 有关详细信息，请参阅[在 skype for Business 服务器中规划存档](../../plan-your-deployment/archiving/archiving.md)和[配置与 Skype for Business 服务器的 Exchange 存储的集成](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md)。 
  
## <a name="manage-archiving-policies-by-using-the-control-panel"></a>使用控制面板管理存档策略

可以使用控制面板管理存档策略，如下所示：
  
1. 使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。 
    
2. 打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。 
    
3. 在左侧导航栏中，单击“**存档策略**”
    
## <a name="manage-archiving-policies-by-using-windows-powershell"></a>使用 Windows PowerShell 管理存档策略

也可以使用下表中列出的 Windows PowerShell cmdlet 配置存档策略。 有关语法的详细信息（包括所有可用参数），请参阅[Skype for Business Server 命令行管理](../management-shell.md)程序。
  

|**Cmdlet**|**说明**|
|:-----|:-----|
|Get-CsArchivingPolicy  <br/> |返回有关您组织的即时消息 (IM) 会话存档策略的信息。  <br/> |
|Grant-CsArchivingPolicy  <br/> |将即时消息 (IM) 会话存档策略分配给用户或用户集。 通过这些策略，您可以存档在内部用户之间发生的所有 IM 会话，以及/或者存档在内部用户与外部伙伴之间发生的所有 IM 会话。  <br/> |
|New-CsArchivingPolicy  <br/> |创建新的即时消息 (IM) 会话存档策略。 通过这些策略，您可以存档在内部用户之间发生的所有 IM 会话，以及/或者存档在内部用户与外部伙伴之间发生的所有 IM 会话。  <br/> |
|Remove-CsArchivingPolicy  <br/> |删除指定的即时消息（IM）存档策略，该策略确定 Skype for Business 服务器是否会自动保存内部用户和/或内部用户与联盟合作伙伴之间所有 IM 会话之间发生的所有 IM 会话。  <br/> |
|Set-CsArchivingPolicy  <br/> |修改现有的即时消息 (IM) 存档策略。 通过存档策略，您可以存档在内部用户之间发生的所有 IM 会话和会议；您还可以存档在内部用户与联盟伙伴之间发生的会话。  <br/> |
   

