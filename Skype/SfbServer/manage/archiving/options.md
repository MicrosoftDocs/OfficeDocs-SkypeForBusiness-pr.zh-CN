---
title: 管理 Business Server Skype 中的存档选项
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50399f26-58a3-4ce2-8229-32a8cafc7733
description: 摘要： 了解如何配置的 Skype 业务服务器的存档选项。
ms.openlocfilehash: 235a0170a4301e48caeae17b7315a174ca2c8aee
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20993565"
---
# <a name="manage-archiving-options-in-skype-for-business-server"></a>管理 Business Server Skype 中的存档选项

**摘要：** 了解如何配置的 Skype 业务服务器的存档选项。
  
您最初在部署时配置存档，但您可以在部署后更改、添加和删除配置。 存档选项决定了是否： 
  
- 启用或禁用存档
    
- 存档 IM 会话
    
- 存档 Web 会议会话
    
- 在存档不可用时阻止活动
    
- 使用  Exchange 集成
    
- 设置数据的清除和导出
    
您可以在以下级别指定配置选项：
  
- 为业务 Server 部署 Skype 时默认创建的全局级配置
    
- 指定如何为特定站点实施存档的可选站点级别配置
    
- 指定如何实现存档的特定池的可选池级配置
    
可以删除站点配置或池配置，但无法删除全局配置。 如果删除全局配置，该配置将自动重置为默认值。 有关详细信息如何实现存档配置和层次结构的存档配置，请参阅[Plan for Business Server 的 Skype 的存档](../../plan-your-deployment/archiving/archiving.md)。
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a>使用控制面板配置存档选项

可以使用控制面板配置存档选项，如下所示：
  
1. 使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。 
    
2. 打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。 
    
3. 在左侧导航栏中，单击“**存档配置**”
    
## <a name="configure-archiving-options-by-using-windows-powershell"></a>使用 Windows PowerShell 配置存档选项

也可以使用下表中列出的 Windows PowerShell cmdlet 配置存档选项。 有关语法，包括所有可用的参数的详细信息，请参阅[Business Server Management Shell 的 Skype](../management-shell.md)。
  

|**Cmdlet**|**说明**|
|:-----|:-----|
|Get-csarchivingconfiguration  <br/> |返回有关组织的存档配置设置的信息。  <br/> |
|New-csarchivingconfiguration  <br/> |创建一组新的即时消息 (IM) 设置，这些设置可用于启用或禁用 IM 会话的自动保存功能，也可用于阻止无法存档的任何即时消息。  <br/> |
|Remove-csarchivingconfiguration  <br/> |删除指定的存档设置集合，存档设置可用于启用或禁用即时消息 (IM) 会话自动保存功能，以及选择性地阻止任何无法存档的即时消息。  <br/> |
|Set-csarchivingconfiguration  <br/> |修改即时消息 (IM) 存档配置选项的现有集合。  <br/> |