---
title: 管理存档中 Skype 业务服务器
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 63fd56cf-6d40-4db5-96fc-32d813930bcf
description: 摘要： 了解如何管理存档的 Skype 业务服务器。
ms.openlocfilehash: 3044ad4bd8c5b551d5cc43c2d3f6ae9b111c7ca6
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "21008073"
---
# <a name="manage-archiving-in-skype-for-business-server"></a>管理存档中 Skype 业务服务器

**摘要：** 了解如何管理存档的 Skype 业务服务器。
  
在为组织部署存档时，可以在部署期间指定初始配置。 但是，有时您希望针对日常管理或为了满足组织的新需求而更改实施存档支持的方式。 例如，您可能需要为组织中的特定站点、特定池或特定用户单独设置存档支持。 业务服务器位于 Skype 上的用户，您需要执行此操作通过创建和自定义存档配置选项和用户策略。 
  
在阅读本主题之前，请确保您熟悉[Plan for Business Server 的 Skype 的存档](../../plan-your-deployment/archiving/archiving.md)和[部署存档 Skype 业务服务器](../../deploy/deploy-archiving/deploy-archiving.md)中的信息。
  
> [!NOTE]
> 如果对部署启用 Microsoft Exchange 集成，Exchange 策略将控制是否对驻留在 Exchange 上并将邮箱置于就地保留状态的用户启用存档。 有关详细信息，请参阅[规划存档中的业务服务器 Skype](../../plan-your-deployment/archiving/archiving.md)和[配置与业务服务器 Skype 的 Exchange 存储的集成](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md)。 
  
## <a name="archiving-configuration-options"></a>存档配置选项

存档配置选项指定是否：
  
- 启用或禁用存档
    
- 存档 IM 会话
    
- 存档 Web 会议会话
    
- 在存档不可用时阻止活动
    
- 使用  Exchange 集成
    
- 设置数据的清除和导出
    
可在全局、站点或池级别设置这些选项。 有关详细信息，请参阅[管理 Skype 业务服务器中的存档选项](options.md)。
  
## <a name="archiving-policies"></a>存档策略

存档策略确定是否存档以下：
  
- 内部通信
    
- 外部通信
    
可在全局、站点或用户级别设置这些策略。 有关详细信息，请参阅[管理 Skype 业务服务器中的存档策略](policies.md)。
  
## <a name="manage-archiving-by-using-the-control-panel-or-by-using-windows-powershell"></a>使用控制面板或 Windows PowerShell 管理存档

您可以使用控制面板或 Windows PowerShell 管理存档。 下表汇总了可帮助您管理存档的 cmdlet。 有关语法，包括所有可用的参数的详细信息，请参阅[Business Server Management Shell 的 Skype](../management-shell.md)。 


|**Cmdlet**|**说明**|
|:-----|:-----|
|Export-csarchivingdata  <br/> |导出已存储在业务 Server 存档数据库 Skype 的记录。  <br/> |
|Get-csarchivingconfiguration  <br/> |返回有关组织的存档配置设置的信息。  <br/> |
|Get-csarchivingpolicy  <br/> |返回有关组织的内部和外部通信存档策略的信息。  <br/> |
|Grant-csarchivingpolicy  <br/> |将即时消息 (IM) 会话存档策略分配给用户或用户集。 通过这些策略，您可以存档在内部用户之间发生的所有 IM 会话，以及/或者存档在内部用户与外部伙伴之间发生的所有 IM 会话。  <br/> |
|Invoke-csarchivingdatabasepurge  <br/> |手动清除存档数据库中的记录。  <br/> |
|New-csarchivingconfiguration  <br/> |创建一组新的即时消息 (IM) 设置，这些设置可用于启用或禁用 IM 会话的自动保存功能，也可用于阻止无法存档的任何即时消息。  <br/> |
|New-csarchivingpolicy  <br/> |创建新的即时消息 (IM) 会话存档策略。 通过这些策略，您可以存档在内部用户之间发生的所有 IM 会话，以及/或者存档在内部用户与外部伙伴之间发生的所有 IM 会话。  <br/> |
|Remove-csarchivingconfiguration  <br/> |删除指定的存档设置集合，存档设置可用于启用或禁用即时消息 (IM) 会话自动保存功能，以及选择性地阻止任何无法存档的即时消息。  <br/> |
|Remove-csarchivingpolicy  <br/> |删除存档策略，用于确定是否 Skype 业务服务器自动保存所有内部用户和/或内部用户和联盟的伙伴之间的所有 IM 会话之间进行的 IM 会话的指定即时消息 (IM)。  <br/> |
|Set-csarchivingconfiguration  <br/> |修改即时消息 (IM) 存档配置选项的现有集合。  <br/> |
|Set-csarchivingpolicy  <br/> |修改现有的即时消息 (IM) 存档策略。 通过存档策略，您可以存档在内部用户之间发生的所有 IM 会话和会议；您还可以存档在内部用户与联盟伙伴之间发生的会话。  <br/> |
|设置 CsArchivingServer  <br/> |使您可以为一个或多个存档服务器指定新数据库位置。  <br/> |
   

