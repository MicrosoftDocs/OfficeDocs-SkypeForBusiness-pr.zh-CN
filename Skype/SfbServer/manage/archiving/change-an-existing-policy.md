---
title: 更改现有存档策略Skype for Business Server
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
ms.assetid: 4cf600be-ba3d-4bce-aa22-e158b9ccf8a9
description: 摘要：了解如何更改用户存档Skype for Business Server。
ms.openlocfilehash: 0e59bd87691fd59859445ce6b6863eeecee714d0
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58630646"
---
# <a name="change-an-existing-archiving-policy-in-skype-for-business-server"></a>更改现有存档策略Skype for Business Server
 
**摘要：** 了解如何更改用户存档策略Skype for Business Server。
  
首次部署Skype for Business Server时，将设置初始存档策略，以确定如何为部署中的用户实施存档。 本主题介绍如何管理和修订策略。 
  
## <a name="change-archiving-policies-by-using-the-control-panel"></a>使用控制面板更改存档策略

1. 使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。 
    
2. 打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。 
    
3. 在左侧导航栏中，单击 **“监控和存档”**，然后单击 **“存档策略”**。
    
4. 在策略列表中，执行下列操作之一： 
    
   - 若要更改整个部署的策略，请单击策略列表中的“全局”，再单击“编辑”，然后单击“显示详细信息”。
    
   - 若要更改单个站点的策略，请单击策略列表中的站点名称，再单击“编辑”，然后单击“显示详细信息”。
    
   - 若要更改单个用户或用户组的策略，请单击策略列表中的用户或用户组的名称，再单击“编辑”，然后单击“显示详细信息”。
    
5. 在“编辑存档策略”页中，执行下列操作：
    
   - 若要为策略启用或禁用内部存档，请选中或清除“存档内部通信”复选框。
    
   - 若要为策略启用或禁用外部存档，请选中或清除“存档外部通信”复选框。
    
6. 单击“提交”。
    
    > [!IMPORTANT]
    > 用户策略的设置仅适用于要应用该策略的特定用户和用户组。 有关详细信息，请参阅[向用户应用存档Skype for Business Server。](apply-a-policy-to-users.md) 
  
## <a name="change-archiving-policies-by-using-windows-powershell"></a>使用策略更改存档Windows PowerShell

您还可以使用 **Set-CsArchivingPolicy** cmdlet Windows PowerShell存档策略。
  
### <a name="enable-archiving-policies"></a>启用存档策略

若要启用内部通信会话的存档，将 ArchiveInternal 参数的值设置为 True ($True) ： 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True
```

若要启用外部通信会话的存档，将 ArchiveExternal 参数的值设置为 True ($True) ： 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveExternal $True
```

若要同时启用内部和外部通信会话的存档，请同时将 ArchiveInternal 和 ArchiveExternal 参数的值设置为 True： 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True
```

### <a name="disable-archiving-policies"></a>禁用存档策略

若要完全禁用存档，请同时将 ArchiveInternal 和 ArchiveExternal 参数的值设置为 False ($False) ： 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $False -ArchiveExternal $False
```
