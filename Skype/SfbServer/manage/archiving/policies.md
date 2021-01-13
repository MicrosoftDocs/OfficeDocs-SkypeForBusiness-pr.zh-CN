---
title: 在 Skype for Business Server 中管理存档策略
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 75ce32ba-eb82-4339-9c02-5df5f2c2ebd2
description: 摘要：了解如何管理 Skype for Business Server 的用户存档策略。
ms.openlocfilehash: 949ac807faea4f563ee078512a3c0a335a517d2c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828542"
---
# <a name="manage-archiving-policies-in-skype-for-business-server"></a>在 Skype for Business Server 中管理存档策略

**摘要：** 了解如何管理 Skype for Business Server 的用户存档策略。
  
您最初在部署存档时设置存档策略，但您可以在部署后更改、添加和删除配置。 存档策略确定是否存档： 
  
- 内部通信
    
- 外部通信
    
可以在全局、站点或用户级别设置存档策略。
  
> [!NOTE]
> 如果为部署启用了 Microsoft Exchange 集成，Exchange 策略将控制是否对位于 Exchange 上且其邮箱置于"保留"状态In-Place存档。 有关详细信息，请参阅[Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and Configure integration with Exchange storage for Skype for Business [Server.](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md) 
  
## <a name="manage-archiving-policies-by-using-the-control-panel"></a>使用控制面板管理存档策略

您可以使用控制面板管理存档策略，如下所示：
  
1. 使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。 
    
2. 打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。 
    
3. 在左侧导航栏中，单击 **"存档策略"**
    
## <a name="manage-archiving-policies-by-using-windows-powershell"></a>使用策略管理存档Windows PowerShell

您还可以使用下表中列出的 Windows PowerShell cmdlet 配置存档策略。 有关语法的详细信息，包括所有可用参数，请参阅 Skype [for Business Server 命令行管理程序](../management-shell.md)。
  

|**Cmdlet**|**说明**|
|:-----|:-----|
|Get-CsArchivingPolicy  <br/> |返回有关组织的即时消息和 IM (会话) 策略的信息。  <br/> |
|Grant-CsArchivingPolicy  <br/> |将即时消息 (IM) 会话存档策略分配给用户或一组用户。 通过这些策略，您可以存档在内部用户之间发生的所有 IM 会话，以及/或者存档在内部用户与外部伙伴之间发生的所有 IM 会话。  <br/> |
|New-CsArchivingPolicy  <br/> |创建新的即时消息 (IM) 会话存档策略。 通过这些策略，您可以存档在内部用户之间发生的所有 IM 会话，以及/或者存档在内部用户与外部伙伴之间发生的所有 IM 会话。  <br/> |
|Remove-CsArchivingPolicy  <br/> |删除指定的即时消息 (IM) 存档策略，该策略确定 Skype for Business Server 是否将自动保存内部用户之间发生的所有 IM 会话，以及/或内部用户和联盟伙伴之间的所有 IM 会话。  <br/> |
|Set-CsArchivingPolicy  <br/> |修改现有的即时消息 (IM) 存档策略。 通过存档策略，您可以存档在内部用户之间发生的所有 IM 会话和会议；您还可以存档在内部用户与联盟伙伴之间发生的会话。  <br/> |
   

