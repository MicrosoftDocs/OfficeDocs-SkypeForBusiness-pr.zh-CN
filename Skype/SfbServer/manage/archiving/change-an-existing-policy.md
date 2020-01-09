---
title: 在 Skype for Business 服务器中更改现有存档策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4cf600be-ba3d-4bce-aa22-e158b9ccf8a9
description: 摘要：了解如何更改 Skype for business Server 的用户存档策略。
ms.openlocfilehash: 00f22b9afa5332bd7075b03823d321d35a0e4b8b
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992769"
---
# <a name="change-an-existing-archiving-policy-in-skype-for-business-server"></a>在 Skype for Business 服务器中更改现有存档策略
 
**摘要：** 了解如何更改 Skype for business Server 的用户存档策略。
  
当您首次部署 Skype for Business 服务器时，设置用于确定如何为部署中的用户实现存档的初始存档策略。 本主题介绍了如何管理和修订策略。 
  
## <a name="change-archiving-policies-by-using-the-control-panel"></a>使用控制面板更改存档策略

1. 使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。 
    
2. 打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。 
    
3. 在左侧导航栏中，单击“监控和存档”****，然后单击“存档策略”****。
    
4. 在策略列表中，执行下列操作之一： 
    
   - 若要更改整个部署的策略，请单击策略列表中的“**全局**”，再单击“**编辑**”，然后单击“**显示详细信息**”。
    
   - 若要更改单个站点的策略，请单击策略列表中的站点名称，再单击“**编辑**”，然后单击“**显示详细信息**”。
    
   - 若要更改单个用户或用户组的策略，请单击策略列表中的用户或用户组的名称，再单击“**编辑**”，然后单击“**显示详细信息**”。
    
5. 在“**编辑存档策略**”页中，执行下列操作：
    
   - 若要为策略启用或禁用内部存档，请选中或清除“**存档内部通信**”复选框。
    
   - 若要为策略启用或禁用外部存档，请选中或清除“**存档外部通信**”复选框。
    
6. 单击“**提交**”。
    
    > [!IMPORTANT]
    > 用户策略的设置仅适用于要应用该策略的特定用户和用户组。 有关详细信息，请参阅[将存档策略应用于 Skype for Business 服务器中的用户](apply-a-policy-to-users.md)。 
  
## <a name="change-archiving-policies-by-using-windows-powershell"></a>使用 Windows PowerShell 更改存档策略

您也可以使用 Windows PowerShell **Set-CsArchivingPolicy** cmdlet 更改存档策略。
  
### <a name="enable-archiving-policies"></a>启用存档策略

要启用内部通信会话的存档，请将 ArchiveInternal 参数的值设置为 True ($True)： 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True
```

要启用外部通信会话的存档，请将 ArchiveExternal 数的值设置为 True ($True)： 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveExternal $True
```

若要启用内部和外部通信会话的存档，请将 ArchiveInternal 和 ArchiveExternal 参数的值设置为 True： 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True
```

### <a name="disable-archiving-policies"></a>禁用存档策略

要禁用全部存档，请将 ArchiveInternal 和 ArchiveExternal 参数的值设置为 False ($False)： 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $False -ArchiveExternal $False
```
