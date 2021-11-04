---
title: 启用或禁用存档Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: d5aed328-e89d-4a7b-b603-15ae5c33c5dd
description: 摘要：了解如何在存档中启用或禁用Skype for Business Server。
ms.openlocfilehash: ad59cd2f8bf22ae0f4ac8b8ba08c84b40fbeffb4
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60747328"
---
# <a name="enable-or-disable-archiving-in-skype-for-business-server"></a>启用或禁用存档Skype for Business Server

**摘要：** 了解如何在存档中启用或禁用Skype for Business Server。
  
## <a name="enable-or-disable-archiving-by-using-the-control-panel"></a>使用控制面板启用或禁用存档

1. 使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。 
    
2. 打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。 
    
3. 在左侧导航栏中，单击 **“监控和存档”**，然后单击 **“存档配置”**。
    
4. 从存档配置列表中选择相应的全局、站点或池策略，单击“编辑”，再单击“显示详细信息”，然后执行下列操作：
    
   - 若要只为即时消息 (IM) 会话启用存档，请单击“存档 IM 会话”。
    
   - 若要同时为 IM 会话和会议启用存档，请单击“存档 IM 和会议会话”。
    
   - 若要为配置禁用存档，请单击"**禁用存档"。**
    
5. 单击“提交”。
    
## <a name="enable-or-disable-archiving-by-using-windows-powershell"></a>使用管理程序启用或禁用Windows PowerShell

您还可以使用 **Set-CsArchivingConfiguration** cmdlet 启用或禁用存档。 例如，以下命令修改所有存档配置设置，以便仅存档 IM 会话。 该命令调用不带任何参数的 **Get-CsArchivingConfiguration** cmdlet，以返回组织中当前使用的所有存档配置设置。 然后，将此集合通过管道管道到 **Where-Object** cmdlet，该 cmdlet 将仅选择 EnableArchiving 属性等于 (-eq) "ImAndWebConf"的设置。 然后，将筛选出的集合通过管道通过管道到 **Set-CsArchivingConfiguration** cmdlet，该 cmdlet 将接受集合中的每个项目，然后将 EnableArchiving 的值更改为"ImOnly"：
  
```PowerShell
Get-CsArchivingConfiguration | Where-Object {$_.EnableArchiving -eq "ImAndWebConf"} | Set-CsArchivingConfiguration -EnableArchiving "ImOnly"
```
