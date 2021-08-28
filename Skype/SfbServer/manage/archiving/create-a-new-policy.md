---
title: 在存档中创建新的存档Skype for Business Server
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
ms.assetid: 50c39731-ba2f-49c2-a571-6dc373f6aaeb
description: 摘要：了解如何为用户创建新的存档Skype for Business Server。
ms.openlocfilehash: 3f32509c6b49a0b0bbbacddac409c817e1e7e2cc
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58632966"
---
# <a name="create-a-new-archiving-policy-in-skype-for-business-server"></a>在存档中创建新的存档Skype for Business Server

**摘要：** 了解如何为用户创建新的存档Skype for Business Server。
  
可以使用控制面板或 cmdlet 创建新的存档Windows PowerShell策略。
  
## <a name="create-a-new-archiving-policy-by-using-the-control-panel"></a>使用控制面板创建新的存档策略

若要使用控制面板创建新的存档策略，请执行以下操作：
  
1. 使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。 
    
2. 打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。 
    
3. 在左侧导航栏中，单击 **“监控和存档”**，然后单击 **“存档策略”**。
    
4. 单击“新建”，然后执行以下操作之一： 
    
   - 要创建站点级别的存档策略，请单击"站点策略"，然后在"选择站点"中单击要应用该策略的站点。
    
   - 若要创建用户级别的存档策略，请单击“用户策略”。
    
5. 在“新建存档策略”中，执行下列操作：
    
   - 在“名称”中，指定新策略的名称（例如，externalContoso）。
    
   - 在“说明”中，提供有关该策略内容的详细信息（例如，Contoso 的外部用户存档策略）。
    
   - 要控制内部用户通信的存档，请选中或清除“存档内部通信”复选框。
    
   - 要控制外部用户通信的存档，请选中或清除“存档外部通信”复选框。
    
6. 单击“提交”。
    
    > [!IMPORTANT]
    > 用户策略的设置仅适用于要应用该策略的特定用户和用户组。 有关详细信息，请参阅[向用户应用存档策略Skype for Business Server。](apply-a-policy-to-users.md) 
  
## <a name="create-a-new-archiving-policy-by-using-windows-powershell"></a>使用存档策略创建新的存档Windows PowerShell

您还可以使用 **New-CsArchivingPolicy** cmdlet Windows PowerShell存档策略。 有关详细信息，请参阅 [New-CsArchivingPolicy](/powershell/module/skype/new-csarchivingpolicy?view=skype-ps) cmdlet 的帮助主题。
  
### <a name="to-create-a-new-archiving-policy-at-the-site-level"></a>在站点级别创建新的存档策略

此命令可为 Redmond 站点创建新的存档策略：
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond"
```

### <a name="to-create-a-new-archiving-policy-at-the-per-user-level"></a>在每个用户级别创建新的存档策略

若要在每个用户级别创建新的存档策略，只需在创建策略时指定唯一标识：
  
```PowerShell
New-CsArchivingPolicy -Identity "RedmondArchivingPolicy"
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-internal-communication-sessions"></a>创建启用内部通信会话存档的新存档策略

由于前面的命令中未指定参数（必需的 Identity 参数之外），因此新策略将对其所有属性使用默认值。 若要创建使用其他属性值的策略，只需包括适当的参数和参数值。 例如，以下命令可创建允许对内部即时消息会话进行存档的存档策略： 
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-both-internal-and-external-communication-sessions"></a>创建启用内部和外部通信会话存档的新存档策略

可以通过包含多个参数来修改多个属性值。 例如，此命令将新策略配置为同时存档内部和外部即时消息会话：
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True -ArchiveExternal $True
```