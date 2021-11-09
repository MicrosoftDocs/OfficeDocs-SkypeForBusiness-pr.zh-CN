---
title: 管理存档Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 63fd56cf-6d40-4db5-96fc-32d813930bcf
description: 摘要：了解如何管理存档Skype for Business Server。
ms.openlocfilehash: bdb373bf723e586cbc7222cd2559b87f4c72381e
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60856789"
---
# <a name="manage-archiving-in-skype-for-business-server"></a>管理存档Skype for Business Server

**摘要：** 了解如何管理存档Skype for Business Server。
  
为组织部署存档时，在部署过程中指定初始配置。 但是，有时可能需要更改实现存档支持以用于日常管理或满足组织的新要求。 例如，您可能需要为组织内部的特定站点、特定池或特定用户设置不同的存档支持。 对于位于Skype for Business Server的用户，通过创建和自定义存档配置选项和用户策略来完成此操作。 
  
在阅读本主题之前，请确保您熟悉在 Skype for Business Server 中规划存档和[](../../plan-your-deployment/archiving/archiving.md)部署存档[中Skype for Business Server。](../../deploy/deploy-archiving/deploy-archiving.md)
  
> [!NOTE]
> 如果为部署Exchange Microsoft Exchange集成，则 Exchange 策略将控制是否对位于 Exchange 上且其邮箱置于"保留"状态In-Place存档。 有关详细信息，请参阅 Plan [for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md)和 Configure integration with Exchange storage for [Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md)。 
  
## <a name="archiving-configuration-options"></a>存档配置选项

存档配置选项指定是否：
  
- 启用或禁用存档
    
- 存档 IM 会话
    
- 存档 Web 会议会话
    
- 存档不可用时阻止活动
    
- 使用Exchange集成
    
- 设置数据的清除和导出
    
可以在全局、站点或池级别设置这些选项。 有关详细信息，请参阅管理[存档Skype for Business Server。](options.md)
  
## <a name="archiving-policies"></a>存档策略

存档策略确定是否存档以下内容：
  
- 内部通信
    
- 外部通信
    
可以在全局、站点或用户级别设置这些策略。 有关详细信息，请参阅管理[存档策略Skype for Business Server。](policies.md)
  
## <a name="manage-archiving-by-using-the-control-panel-or-by-using-windows-powershell"></a>使用控制面板或管理存档Windows PowerShell

可以使用控制面板或自动管理存档Windows PowerShell。 下表总结了可帮助您管理存档的 cmdlet。 有关语法的详细信息，包括所有可用参数，请参阅Skype for Business Server[命令行管理程序](../management-shell.md)。 


|**Cmdlet**|**说明**|
|:-----|:-----|
|Export-CsArchivingData  <br/> |导出已存储在存档Skype for Business Server中的记录。  <br/> |
|Get-CsArchivingConfiguration  <br/> |返回有关您组织的存档配置设置的信息。  <br/> |
|Get-CsArchivingPolicy  <br/> |返回有关组织的内部和外部通信存档策略的信息。  <br/> |
|Grant-CsArchivingPolicy  <br/> |将即时消息 (IM) 会话存档策略分配给用户或用户集。 通过这些策略，您可以存档在内部用户之间发生的所有 IM 会话，以及/或者存档在内部用户与外部伙伴之间发生的所有 IM 会话。  <br/> |
|Invoke-CsArchivingDatabasePurge  <br/> |手动清除存档数据库中的记录。  <br/> |
|New-CsArchivingConfiguration  <br/> |创建一组新的即时消息 (IM) 设置，这些设置可用于启用或禁用 IM 会话的自动保存，并阻止无法存档的任何即时消息。  <br/> |
|New-CsArchivingPolicy  <br/> |创建新的即时消息 (IM) 会话存档策略。 通过这些策略，您可以存档在内部用户之间发生的所有 IM 会话，以及/或者存档在内部用户与外部伙伴之间发生的所有 IM 会话。  <br/> |
|Remove-CsArchivingConfiguration  <br/> |删除指定的存档设置集合，这些设置用于启用或禁用即时消息 (IM) 会话的自动保存，以及（可选）阻止任何无法存档的即时消息。  <br/> |
|Remove-CsArchivingPolicy  <br/> |删除指定的即时消息 (IM) 存档策略，该策略确定 Skype for Business Server 是否将自动保存内部用户之间发生的所有 IM 会话，以及/或内部用户与联盟伙伴之间的所有 IM 会话。  <br/> |
|Set-CsArchivingConfiguration  <br/> |修改现有的即时消息传递集合 (IM) 存档配置选项。  <br/> |
|Set-CsArchivingPolicy  <br/> |修改现有的即时消息 (IM) 存档策略。 通过存档策略，您可以存档在内部用户之间发生的所有 IM 会话和会议；您还可以存档在内部用户与联盟伙伴之间发生的会话。  <br/> |
|Set-CsArchivingServer  <br/> |用于指定一个或多个存档服务器的新数据库位置。  <br/> |
   

