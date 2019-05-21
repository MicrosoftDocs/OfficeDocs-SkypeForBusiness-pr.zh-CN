---
title: 在 Skype for Business 服务器中创建新的存档策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50c39731-ba2f-49c2-a571-6dc373f6aaeb
description: '摘要: 了解如何为 Skype for Business 服务器创建新的存档策略。'
ms.openlocfilehash: d6bf33254feece1fe9f1a4fe848b2601e758faf3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299970"
---
# <a name="create-a-new-archiving-policy-in-skype-for-business-server"></a>在 Skype for Business 服务器中创建新的存档策略

**摘要:** 了解如何为 Skype for Business 服务器创建新的存档策略。
  
您可以使用控制面板或 Windows PowerShell cmdlet 创建新的存档策略。
  
## <a name="create-a-new-archiving-policy-by-using-the-control-panel"></a>使用控制面板创建新的存档策略

要使用控制面板创建新的存档策略：
  
1. 使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。 
    
2. 打开一个浏览器窗口, 然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。 
    
3. 在左侧导航栏中，单击“监控和存档”****，然后单击“存档策略”****。
    
4. 单击“**新建**”，然后执行以下操作之一： 
    
   - 若要创建站点级别的存档策略，请单击“**站点策略**”，然后在“**选择站点**”中，单击要应用该策略的站点。
    
   - 若要创建用户级别的存档策略，请单击“**用户策略**”。
    
5. 在“**新建存档策略**”中，执行下列操作：
    
   - 在“**名称**”中，指定新策略的名称（例如，externalContoso）。
    
   - 在“**说明**”中，提供有关该策略内容的详细信息（例如，Contoso 的外部用户存档策略）。
    
   - 要控制内部用户通信的存档，请选中或清除“**存档内部通信**”复选框。
    
   - 要控制外部用户通信的存档，请选中或清除“**存档外部通信**”复选框。
    
6. 单击“**提交**”。
    
    > [!IMPORTANT]
    > 用户策略的设置仅适用于要应用该策略的特定用户和用户组。 有关详细信息, 请参阅[将存档策略应用于 Skype for Business 服务器中的用户](apply-a-policy-to-users.md)。 
  
## <a name="create-a-new-archiving-policy-by-using-windows-powershell"></a>使用 Windows PowerShell 创建新的存档策略

也可以使用 Windows PowerShell **New-CsArchivingPolicy** cmdlet 创建新的存档策略。 有关详细信息, 请参阅[CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csarchivingpolicy?view=skype-ps) cmdlet 的帮助主题。
  
### <a name="to-create-a-new-archiving-policy-at-the-site-level"></a>要在站点级别创建新的存档策略

此命令可为 Redmond 站点创建新的存档策略：
  
```
New-CsArchivingPolicy -Identity "site:Redmond"
```

### <a name="to-create-a-new-archiving-policy-at-the-per-user-level"></a>要在每用户级别创建新的存档策略

若要在每用户级别创建新的存档策略，只需在创建策略时指定唯一标识即可：
  
```
New-CsArchivingPolicy -Identity "RedmondArchivingPolicy"
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-internal-communication-sessions"></a>要创建允许对内部通信会话进行存档的新存档策略

由于前面的命令中未指定参数（必需的 Identity 参数之外），因此新策略将对其所有属性使用默认值。 若要创建使用其他属性值的策略，只需包括适当的参数和参数值。 例如, 以下命令将创建允许存档内部即时消息会话的存档策略: 
  
```
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-both-internal-and-external-communication-sessions"></a>要创建允许对内部和外部通信会话进行存档的新存档策略

可通过包含多个参数来修改多个属性值。例如，此命令将配置新策略以便对内部和外部即时消息会话进行存档：
  
```
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True -ArchiveExternal $True
```
