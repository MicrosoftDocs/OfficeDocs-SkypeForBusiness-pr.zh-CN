---
title: 管理 Skype for Business 服务器中的存档选项
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50399f26-58a3-4ce2-8229-32a8cafc7733
description: '摘要: 了解如何配置 Skype for Business 服务器的存档选项。'
ms.openlocfilehash: c7353c305125e8e35523c573150471821f53301e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34278417"
---
# <a name="manage-archiving-options-in-skype-for-business-server"></a>管理 Skype for Business 服务器中的存档选项

**摘要:** 了解如何配置 Skype for Business 服务器的存档选项。
  
您最初在部署时配置存档，但您可以在部署后更改、添加和删除配置。 存档选项决定了是否： 
  
- 启用或禁用存档
    
- 存档 IM 会话
    
- 存档 Web 会议会话
    
- 在存档不可用时阻止活动
    
- 使用  Exchange 集成
    
- 设置数据的清除和导出
    
您可以在以下级别指定配置选项：
  
- 部署 Skype for Business 服务器时默认创建的全局级别配置
    
- 指定如何为特定站点实施存档的可选站点级别配置
    
- 指定如何为特定池实施存档的可选池级别配置
    
可以删除站点配置或池配置，但无法删除全局配置。 如果删除全局配置，该配置将自动重置为默认值。 有关如何实施存档配置和存档配置的层次结构的详细信息, 请参阅[在 Skype For Business 服务器中计划存档](../../plan-your-deployment/archiving/archiving.md)。
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a>使用控制面板配置存档选项

可以使用控制面板配置存档选项，如下所示：
  
1. 使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。 
    
2. 打开一个浏览器窗口, 然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。 
    
3. 在左侧导航栏中，单击“**存档配置**”
    
## <a name="configure-archiving-options-by-using-windows-powershell"></a>使用 Windows PowerShell 配置存档选项

也可以使用下表中列出的 Windows PowerShell cmdlet 配置存档选项。 有关语法的详细信息 (包括所有可用参数), 请参阅[Skype for Business Server 命令行管理](../management-shell.md)程序。
  

|**Cmdlet**|**说明**|
|:-----|:-----|
|Get-CsArchivingConfiguration  <br/> |返回有关组织的存档配置设置的信息。  <br/> |
|New-CsArchivingConfiguration  <br/> |创建一组新的即时消息 (IM) 设置，这些设置可用于启用或禁用 IM 会话的自动保存功能，也可用于阻止无法存档的任何即时消息。  <br/> |
|Remove-CsArchivingConfiguration  <br/> |删除指定的存档设置集合，存档设置可用于启用或禁用即时消息 (IM) 会话自动保存功能，以及选择性地阻止任何无法存档的即时消息。  <br/> |
|Set-CsArchivingConfiguration  <br/> |修改即时消息 (IM) 存档配置选项的现有集合。  <br/> |
