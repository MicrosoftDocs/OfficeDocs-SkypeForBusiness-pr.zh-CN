---
title: 在 Skype for Business 服务器中启用或禁用存档
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d5aed328-e89d-4a7b-b603-15ae5c33c5dd
description: 摘要：了解如何在 Skype for Business 服务器中启用或禁用存档。
ms.openlocfilehash: 603ffece7d3b0dabe27ee95d27eaee1e84f48fb9
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991577"
---
# <a name="enable-or-disable-archiving-in-skype-for-business-server"></a>在 Skype for Business 服务器中启用或禁用存档

**摘要：** 了解如何在 Skype for Business 服务器中启用或禁用存档。
  
## <a name="enable-or-disable-archiving-by-using-the-control-panel"></a>使用控制面板启用或禁用存档

1. 使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。 
    
2. 打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。 
    
3. 在左侧导航栏中，单击“监控和存档”****，然后单击“存档配置”****。
    
4. 从存档配置列表中选择相应的全局、站点或池策略，单击“**编辑**”，再单击“**显示详细信息**”，然后执行下列操作：
    
   - 若要只为即时消息 (IM) 会话启用存档，请单击“**存档 IM 会话**”。
    
   - 若要同时为 IM 会话和会议启用存档，请单击“**存档 IM 和会议会话**”。
    
   - 若要为此配置禁用存档，请单击“**禁用存档**”。
    
5. 单击“**提交**”。
    
## <a name="enable-or-disable-archiving-by-using-windows-powershell"></a>使用 Windows PowerShell 启用或禁用存档

您也可以使用 **Set-CsArchivingConfiguration** cmdlet 启用或禁用存档。 例如，以下命令可修改所有存档配置设置，从而仅存档 IM 会话。 该命令可调用不带任何参数的 **Get-CsArchivingConfiguration** cmdlet 以返回当前在组织内使用的所有存档配置设置。 然后将此集合通过管道传递到 **Where-Object** cmdlet，后者将仅挑选出 EnableArchiving 属性等于 (-eq) "ImAndWebConf" 的设置。 然后，将筛选出的集合通过管道传递到 **Set-CsArchivingConfiguration** cmdlet，后者将选取集合中的每一项，并将 EnableArchiving 的值更改为 "ImOnly"。
  
```PowerShell
Get-CsArchivingConfiguration | Where-Object {$_.EnableArchiving -eq "ImAndWebConf"} | Set-CsArchivingConfiguration -EnableArchiving "ImOnly"
```
