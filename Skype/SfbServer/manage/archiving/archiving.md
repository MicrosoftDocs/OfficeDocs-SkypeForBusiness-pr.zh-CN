---
title: 管理 Skype for Business Server 2015 中的存档
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 63fd56cf-6d40-4db5-96fc-32d813930bcf
description: 摘要： 了解如何管理业务服务器 2015 Skype 的存档。
ms.openlocfilehash: fb8359d47b1933e2575685bc532d69e6b9bb6c45
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="manage-archiving-in-skype-for-business-server-2015"></a>管理 Skype for Business Server 2015 中的存档

**摘要：**了解如何管理业务服务器 2015 Skype 的存档。
  
在为组织部署存档时，可以在部署期间指定初始配置。 但是，有时您希望针对日常管理或为了满足组织的新需求而更改实施存档支持的方式。 例如，您可能需要为组织中的特定站点、特定池或特定用户单独设置存档支持。 对于用户驻留在 Skype 上的业务服务器，您可以执行此操作通过创建和自定义存档配置选项和用户策略。 
  
在阅读本主题之前，请确保您熟悉[存档业务服务器 2015年的 Skype 的规划](../../plan-your-deployment/archiving/archiving.md)和[部署业务服务器 2015年的 Skype 的存档](../../deploy/deploy-archiving/deploy-archiving.md)中的信息。
  
> [!NOTE]
> 如果对部署启用 Microsoft Exchange 集成，Exchange 策略将控制是否对驻留在 Exchange 上并将邮箱置于就地保留状态的用户启用存档。 有关详细信息，请参阅[规划业务服务器 2015年的 Skype 在归档](../../plan-your-deployment/archiving/archiving.md)和[具有的业务服务器 2015 Skype 的 Exchange 存储配置集成](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md)。 
  
## <a name="archiving-configuration-options"></a>存档配置选项

存档配置选项指定是否：
  
- 启用或禁用存档
    
- 存档 IM 会话
    
- 存档 Web 会议会话
    
- 在存档不可用时阻止活动
    
- 使用  Exchange 集成
    
- 设置数据的清除和导出
    
可在全局、站点或池级别设置这些选项。 有关详细信息，请参阅[管理中业务服务器 2015年的 Skype 的存档选项](options.md)。
  
## <a name="archiving-policies"></a>存档策略

存档策略确定是否存档以下：
  
- 内部通信
    
- 外部通信
    
可在全局、站点或用户级别设置这些策略。 有关详细信息，请参阅[管理中业务服务器 2015年的 Skype 的存档策略](policies.md)。
  
## <a name="manage-archiving-by-using-the-control-panel-or-by-using-windows-powershell"></a>使用控制面板或 Windows PowerShell 管理存档

您可以使用控制面板或 Windows PowerShell 管理存档。 下表汇总了可帮助您管理存档的 cmdlet。 有关语法，包括所有的可用参数的详细信息请参阅[业务服务器 2015年管理外壳的 Skype](../management-shell.md)。 


|**Cmdlet**|**说明**|
|:-----|:-----|
|导出 CsArchivingData  <br/> |导出在 Skype 业务服务器存档数据库中已存储的记录。  <br/> |
|获得 CsArchivingConfiguration  <br/> |返回有关组织的存档配置设置的信息。  <br/> |
|获得 CsArchivingPolicy  <br/> |返回有关组织的内部和外部通信存档策略的信息。  <br/> |
|授予 CsArchivingPolicy  <br/> |将即时消息 (IM) 会话存档策略分配给用户或用户集。 通过这些策略，您可以存档在内部用户之间发生的所有 IM 会话，以及/或者存档在内部用户与外部伙伴之间发生的所有 IM 会话。  <br/> |
|调用 CsArchivingDatabasePurge  <br/> |手动清除存档数据库中的记录。  <br/> |
|新 CsArchivingConfiguration  <br/> |创建一组新的即时消息 (IM) 设置，这些设置可用于启用或禁用 IM 会话的自动保存功能，也可用于阻止无法存档的任何即时消息。  <br/> |
|新 CsArchivingPolicy  <br/> |创建新的即时消息 (IM) 会话存档策略。 通过这些策略，您可以存档在内部用户之间发生的所有 IM 会话，以及/或者存档在内部用户与外部伙伴之间发生的所有 IM 会话。  <br/> |
|删除 CsArchivingConfiguration  <br/> |删除指定的存档设置集合，存档设置可用于启用或禁用即时消息 (IM) 会话自动保存功能，以及选择性地阻止任何无法存档的即时消息。  <br/> |
|删除 CsArchivingPolicy  <br/> |删除存档策略，用于确定是否 Skype 业务服务器自动将所有内部用户，和/或内部用户和联盟的用户之间的所有 IM 会话之间进行的 IM 会话指定即时消息 (IM)。  <br/> |
|一组 CsArchivingConfiguration  <br/> |修改即时消息 (IM) 存档配置选项的现有集合。  <br/> |
|一组 CsArchivingPolicy  <br/> |修改现有的即时消息 (IM) 存档策略。 通过存档策略，您可以存档在内部用户之间发生的所有 IM 会话和会议；您还可以存档在内部用户与联盟伙伴之间发生的会话。  <br/> |
|一组 CsArchivingServer  <br/> |使您可以为一个或多个存档服务器指定新数据库位置。  <br/> |
   

