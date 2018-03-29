---
title: 在 Skype for Business Server 2015 中启用或禁用存档
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d5aed328-e89d-4a7b-b603-15ae5c33c5dd
description: 摘要： 了解如何启用或禁用存档在 Skype 业务服务器 2015年。
ms.openlocfilehash: ef4e24025d0f1c27b0249b4ea237a579882e74c2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="enable-or-disable-archiving-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中启用或禁用存档

**摘要：**了解如何启用或禁用存档在 Skype 业务服务器 2015年。
  
## <a name="enable-or-disable-archiving-by-using-the-control-panel"></a>使用控制面板启用或禁用存档

1. 使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。 
    
2. 打开浏览器窗口，然后输入管理员 URL 打开 Skype 业务服务器控件面板。 
    
3. 在左侧导航栏中，单击“**监控和存档**”，然后单击“**存档配置**”。
    
4. 从存档配置列表中选择相应的全局、站点或池策略，单击“**编辑**”，再单击“**显示详细信息**”，然后执行下列操作：
    
   - 若要只为即时消息 (IM) 会话启用存档，请单击“**存档 IM 会话**”。
    
   - 若要同时为 IM 会话和会议启用存档，请单击“**存档 IM 和会议会话**”。
    
   - 若要为此配置禁用存档，请单击“**禁用存档**”。
    
5. 单击“**提交**”。
    
## <a name="enable-or-disable-archiving-by-using-windows-powershell"></a>使用 Windows PowerShell 启用或禁用存档

您也可以使用 **Set-CsArchivingConfiguration** cmdlet 启用或禁用存档。 例如，以下命令可修改所有存档配置设置，从而仅存档 IM 会话。 命令调用不带任何参数的**获取 CsArchivingConfiguration** cmdlet 以存档的所有配置设置都返回当前组织中的使用。 此集合然后输送到**对象的位置的**cmdlet，选择其中的 EnableArchiving 属性等于那些设置 (-eq)"ImAndWebConf"。 然后，经过筛选的集合被输送到**集 CsArchivingConfiguration** cmdlet，也不能将集合中的每一项的 EnableArchiving 的值更改为"ImOnly":
  
```
Get-CsArchivingConfiguration | Where-Object {$_.EnableArchiving -eq "ImAndWebConf"} | Set-CsArchivingConfiguration -EnableArchiving "ImOnly"
```