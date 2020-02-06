---
title: 管理 Skype for Business 服务器中的存档
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 63fd56cf-6d40-4db5-96fc-32d813930bcf
description: 摘要：了解如何管理 Skype for business 服务器的存档。
ms.openlocfilehash: 46b0937a00f289ad5383d3bb1a4acf890bf48390
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818994"
---
# <a name="manage-archiving-in-skype-for-business-server"></a>管理 Skype for Business 服务器中的存档

**摘要：** 了解如何管理 Skype for business 服务器的存档。
  
在为组织部署存档时，可以在部署期间指定初始配置。 但是，有时您希望针对日常管理或为了满足组织的新需求而更改实施存档支持的方式。 例如，您可能需要为组织中的特定站点、特定池或特定用户单独设置存档支持。 对于驻留在 Skype for business 服务器上的用户，可通过创建和自定义存档配置选项和用户策略来执行此操作。 
  
在阅读本主题之前，请确保熟悉 " [skype for Business 服务器](../../plan-your-deployment/archiving/archiving.md)" 中的存档信息和[为 Skype For business 服务器部署存档](../../deploy/deploy-archiving/deploy-archiving.md)。
  
> [!NOTE]
> 如果对部署启用 Microsoft Exchange 集成，Exchange 策略将控制是否对驻留在 Exchange 上并将邮箱置于就地保留状态的用户启用存档。 有关详细信息，请参阅[在 skype for Business 服务器中规划存档](../../plan-your-deployment/archiving/archiving.md)和[配置与 Skype for Business 服务器的 Exchange 存储的集成](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md)。 
  
## <a name="archiving-configuration-options"></a>存档配置选项

存档配置选项指定是否：
  
- 启用或禁用存档
    
- 存档 IM 会话
    
- 存档 Web 会议会话
    
- 在存档不可用时阻止活动
    
- 使用  Exchange 集成
    
- 设置数据的清除和导出
    
可在全局、站点或池级别设置这些选项。 有关详细信息，请参阅[管理 Skype For Business 服务器中的存档选项](options.md)。
  
## <a name="archiving-policies"></a>存档策略

存档策略确定是否存档以下内容：
  
- 内部通信
    
- 外部通信
    
可在全局、站点或用户级别设置这些策略。 有关详细信息，请参阅[管理 Skype For Business 服务器中的存档策略](policies.md)。
  
## <a name="manage-archiving-by-using-the-control-panel-or-by-using-windows-powershell"></a>使用控制面板或 Windows PowerShell 管理存档

您可以使用控制面板或 Windows PowerShell 管理存档。 下表汇总了可帮助您管理存档的 cmdlet。 有关语法的详细信息（包括所有可用参数），请参阅[Skype for Business Server 命令行管理](../management-shell.md)程序。 


|**Cmdlet**|**说明**|
|:-----|:-----|
|Export-CsArchivingData  <br/> |导出存储在 Skype for Business 服务器存档数据库中的记录。  <br/> |
|Get-CsArchivingConfiguration  <br/> |返回有关组织的存档配置设置的信息。  <br/> |
|Get-CsArchivingPolicy  <br/> |返回有关组织的内部和外部通信存档策略的信息。  <br/> |
|Grant-CsArchivingPolicy  <br/> |将即时消息 (IM) 会话存档策略分配给用户或用户集。 通过这些策略，您可以存档在内部用户之间发生的所有 IM 会话，以及/或者存档在内部用户与外部伙伴之间发生的所有 IM 会话。  <br/> |
|Invoke-CsArchivingDatabasePurge  <br/> |手动清除存档数据库中的记录。  <br/> |
|New-CsArchivingConfiguration  <br/> |创建一组新的即时消息 (IM) 设置，这些设置可用于启用或禁用 IM 会话的自动保存功能，也可用于阻止无法存档的任何即时消息。  <br/> |
|New-CsArchivingPolicy  <br/> |创建新的即时消息 (IM) 会话存档策略。 通过这些策略，您可以存档在内部用户之间发生的所有 IM 会话，以及/或者存档在内部用户与外部伙伴之间发生的所有 IM 会话。  <br/> |
|Remove-CsArchivingConfiguration  <br/> |删除指定的存档设置集合，存档设置可用于启用或禁用即时消息 (IM) 会话自动保存功能，以及选择性地阻止任何无法存档的即时消息。  <br/> |
|Remove-CsArchivingPolicy  <br/> |删除指定的即时消息（IM）存档策略，该策略确定 Skype for Business 服务器是否会自动保存内部用户和/或内部用户与联盟合作伙伴之间所有 IM 会话之间发生的所有 IM 会话。  <br/> |
|Set-CsArchivingConfiguration  <br/> |修改即时消息 (IM) 存档配置选项的现有集合。  <br/> |
|Set-CsArchivingPolicy  <br/> |修改现有的即时消息 (IM) 存档策略。 通过存档策略，您可以存档在内部用户之间发生的所有 IM 会话和会议；您还可以存档在内部用户与联盟伙伴之间发生的会话。  <br/> |
|Set-CsArchivingServer  <br/> |使您可以为一个或多个存档服务器指定新数据库位置。  <br/> |
   

