---
title: 在 Skype for Business Server 中管理存档
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 63fd56cf-6d40-4db5-96fc-32d813930bcf
description: 摘要：了解如何管理 Skype for Business Server 的存档。
ms.openlocfilehash: 3c84fe35e59d14f957391ecb9bdc503e1bff6b87
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817732"
---
# <a name="manage-archiving-in-skype-for-business-server"></a>在 Skype for Business Server 中管理存档

**摘要：** 了解如何管理 Skype for Business Server 的存档。
  
为组织部署存档时，在部署过程中指定初始配置。 但是，有时可能需要更改对日常管理实施存档支持或满足组织的新要求。 例如，您可能需要为组织中特定站点、特定池或特定用户设置不同的存档支持。 对于位于 Skype for Business Server 上的用户，通过创建和自定义存档配置选项和用户策略来完成此操作。 
  
在阅读本主题之前，请确保你熟悉规划 [Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) 中的存档和为 Skype for Business [Server](../../deploy/deploy-archiving/deploy-archiving.md)部署存档的信息。
  
> [!NOTE]
> 如果为部署启用 Microsoft Exchange 集成，Exchange 策略将控制是否对位于 Exchange 上且其邮箱置于"保留"状态的用户In-Place存档。 有关详细信息，请参阅[Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and Configure integration with Exchange storage for Skype for Business [Server.](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md) 
  
## <a name="archiving-configuration-options"></a>存档配置选项

存档配置选项指定是否：
  
- 启用或禁用存档
    
- 存档 IM 会话
    
- 存档 Web 会议会话
    
- 存档不可用时阻止活动
    
- 使用 Exchange 集成
    
- 设置清除和导出数据
    
可以在全局、站点或池级别设置这些选项。 有关详细信息，请参阅管理 [Skype for Business Server 中的存档选项](options.md)。
  
## <a name="archiving-policies"></a>存档策略

存档策略确定是否存档以下内容：
  
- 内部通信
    
- 外部通信
    
可以在全局、站点或用户级别设置这些策略。 有关详细信息，请参阅管理 [Skype for Business Server 中的存档策略](policies.md)。
  
## <a name="manage-archiving-by-using-the-control-panel-or-by-using-windows-powershell"></a>使用控制面板或管理存档Windows PowerShell

您可以使用控制面板或管理存档Windows PowerShell。 下表总结了可帮助您管理存档的 cmdlet。 有关语法的详细信息，包括所有可用参数，请参阅 Skype [for Business Server 命令行管理程序](../management-shell.md)。 


|**Cmdlet**|**说明**|
|:-----|:-----|
|Export-CsArchivingData  <br/> |导出存储在 Skype for Business Server 存档数据库中的记录。  <br/> |
|Get-CsArchivingConfiguration  <br/> |返回有关组织中存档配置设置的信息。  <br/> |
|Get-CsArchivingPolicy  <br/> |返回有关组织的内部和外部通信存档策略的信息。  <br/> |
|Grant-CsArchivingPolicy  <br/> |将即时消息 (IM) 会话存档策略分配给用户或一组用户。 通过这些策略，您可以存档在内部用户之间发生的所有 IM 会话，以及/或者存档在内部用户与外部伙伴之间发生的所有 IM 会话。  <br/> |
|Invoke-CsArchivingDatabasePurge  <br/> |手动清除存档数据库中的记录。  <br/> |
|New-CsArchivingConfiguration  <br/> |创建一组新的即时消息 (IM) 设置，这些设置可用于启用或禁用 IM 会话的自动保存，并阻止无法存档的任何即时消息。  <br/> |
|New-CsArchivingPolicy  <br/> |创建新的即时消息 (IM) 会话存档策略。 通过这些策略，您可以存档在内部用户之间发生的所有 IM 会话，以及/或者存档在内部用户与外部伙伴之间发生的所有 IM 会话。  <br/> |
|Remove-CsArchivingConfiguration  <br/> |删除指定的存档设置集合，这些设置用于启用或禁用即时消息 (IM) 会话的自动保存，并选择性地阻止任何无法存档的即时消息。  <br/> |
|Remove-CsArchivingPolicy  <br/> |删除指定的即时消息 (IM) 存档策略，该策略确定 Skype for Business Server 是否将自动保存内部用户之间发生的所有 IM 会话，以及/或内部用户和联盟伙伴之间的所有 IM 会话。  <br/> |
|Set-CsArchivingConfiguration  <br/> |修改现有的即时消息传递集合 (IM) 存档配置选项。  <br/> |
|Set-CsArchivingPolicy  <br/> |修改现有的即时消息 (IM) 存档策略。 通过存档策略，您可以存档在内部用户之间发生的所有 IM 会话和会议；您还可以存档在内部用户与联盟伙伴之间发生的会话。  <br/> |
|Set-CsArchivingServer  <br/> |使您可以指定一个或多个存档服务器的新数据库位置。  <br/> |
   

