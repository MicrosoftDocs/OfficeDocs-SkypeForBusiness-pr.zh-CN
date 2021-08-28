---
title: 管理存档选项Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 50399f26-58a3-4ce2-8229-32a8cafc7733
description: 摘要：了解如何配置存档Skype for Business Server。
ms.openlocfilehash: c38142f9a3c4e0db6c856bb1c75846399e9d62dd
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58616608"
---
# <a name="manage-archiving-options-in-skype-for-business-server"></a>管理存档选项Skype for Business Server

**摘要：** 了解如何配置存档的存档Skype for Business Server。
  
您最初在部署时配置存档，但您可以在部署后更改、添加和删除配置。 存档选项确定是否： 
  
- 启用或禁用存档
    
- 存档 IM 会话
    
- 存档 Web 会议会话
    
- 存档不可用时阻止活动
    
- 使用Exchange集成
    
- 设置数据的清除和导出
    
可以在以下级别指定配置选项：
  
- 在部署数据库时默认创建的全局Skype for Business Server
    
- 指定如何为特定站点实施存档的可选站点级别配置
    
- 指定如何为特定池实施存档的可选池级别配置
    
可以删除站点配置或池配置，但无法删除全局配置。 如果删除全局配置，该配置将自动重置为默认值。 有关如何实施存档配置以及存档配置的层次结构的详细信息，请参阅规划存档[Skype for Business Server。](../../plan-your-deployment/archiving/archiving.md)
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a>使用控制面板配置存档选项

可以使用控制面板配置存档选项，如下所示：
  
1. 使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。 
    
2. 打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。 
    
3. 在左侧导航栏中，单击"存档 **配置"。**
    
## <a name="configure-archiving-options-by-using-windows-powershell"></a>使用配置存档选项Windows PowerShell

您还可以使用下表中列出的 Windows PowerShell cmdlet 配置存档选项。 有关语法的详细信息，包括所有可用参数，请参阅Skype for Business Server[命令行管理程序](../management-shell.md)。
  

|**Cmdlet**|**说明**|
|:-----|:-----|
|Get-CsArchivingConfiguration  <br/> |返回有关您组织的存档配置设置的信息。  <br/> |
|New-CsArchivingConfiguration  <br/> |创建一组新的即时消息 (IM) 设置，这些设置可用于启用或禁用 IM 会话的自动保存，并阻止任何无法存档的即时消息。  <br/> |
|Remove-CsArchivingConfiguration  <br/> |删除指定的存档设置集合，这些设置用于启用或禁用即时消息 (IM) 会话的自动保存，以及（可选）阻止任何无法存档的即时消息。  <br/> |
|Set-CsArchivingConfiguration  <br/> |修改现有的即时消息和 IM (存档) 集合。  <br/> |
