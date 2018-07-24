---
title: 启用或禁用存档中 Skype 业务服务器
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d5aed328-e89d-4a7b-b603-15ae5c33c5dd
description: 摘要： 了解如何启用或禁用存档中 Skype 业务服务器。
ms.openlocfilehash: a0d32a3bacb604c326db13034bf5315c7f3d4d99
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20965889"
---
# <a name="enable-or-disable-archiving-in-skype-for-business-server"></a>启用或禁用存档中 Skype 业务服务器

**摘要：** 了解如何启用或禁用存档中 Skype 业务服务器。
  
## <a name="enable-or-disable-archiving-by-using-the-control-panel"></a>使用控制面板启用或禁用存档

1. 使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。 
    
2. 打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。 
    
3. 在左侧导航栏中，单击“**监控和存档**”，然后单击“**存档配置**”。
    
4. 从存档配置列表中选择相应的全局、站点或池策略，单击“**编辑**”，再单击“**显示详细信息**”，然后执行下列操作：
    
   - 若要只为即时消息 (IM) 会话启用存档，请单击“**存档 IM 会话**”。
    
   - 若要同时为 IM 会话和会议启用存档，请单击“**存档 IM 和会议会话**”。
    
   - 若要为此配置禁用存档，请单击“**禁用存档**”。
    
5. 单击“**提交**”。
    
## <a name="enable-or-disable-archiving-by-using-windows-powershell"></a>使用 Windows PowerShell 启用或禁用存档

您也可以使用 **Set-CsArchivingConfiguration** cmdlet 启用或禁用存档。 例如，以下命令可修改所有存档配置设置，从而仅存档 IM 会话。 命令调用不带任何参数的**Get-csarchivingconfiguration** cmdlet，以便返回组织中使用当前的所有存档配置设置。 此集合通过管道传递到**Where-object** cmdlet，选择其中 EnableArchiving 属性等于的那些设置 (-eq)"ImAndWebConf"。 筛选出的集合是然后通过管道传递到**Set-csarchivingconfiguration** cmdlet，它采用集合中的每个项目并 EnableArchiving 的值更改为"ImOnly":
  
```
Get-CsArchivingConfiguration | Where-Object {$_.EnableArchiving -eq "ImAndWebConf"} | Set-CsArchivingConfiguration -EnableArchiving "ImOnly"
```