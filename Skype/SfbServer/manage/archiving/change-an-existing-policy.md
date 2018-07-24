---
title: 更改现有业务服务器存档策略中 Skype
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4cf600be-ba3d-4bce-aa22-e158b9ccf8a9
description: 摘要： 了解如何更改用户存档策略的 Skype 业务服务器。
ms.openlocfilehash: 6c92d4f7e4c2a464d248f6b981165de000615432
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20974649"
---
# <a name="change-an-existing-archiving-policy-in-skype-for-business-server"></a>更改现有业务服务器存档策略中 Skype
 
**摘要：** 了解如何更改用户存档策略的 Skype 业务服务器。
  
您首先部署业务服务器 Skype，您设置确定如何实施存档的部署中用户的初始存档策略。 本主题介绍了如何管理和修订策略。 
  
## <a name="change-archiving-policies-by-using-the-control-panel"></a>使用控制面板更改存档策略

1. 使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。 
    
2. 打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。 
    
3. 在左侧导航栏中，单击“**监控和存档**”，然后单击“**存档策略**”。
    
4. 在策略列表中，执行下列操作之一： 
    
   - 若要更改整个部署的策略，请单击策略列表中的“**全局**”，再单击“**编辑**”，然后单击“**显示详细信息**”。
    
   - 若要更改单个站点的策略，请单击策略列表中的站点名称，再单击“**编辑**”，然后单击“**显示详细信息**”。
    
   - 若要更改单个用户或用户组的策略，请单击策略列表中的用户或用户组的名称，再单击“**编辑**”，然后单击“**显示详细信息**”。
    
5. 在“**编辑存档策略**”页中，执行下列操作：
    
   - 若要为策略启用或禁用内部存档，请选中或清除“**存档内部通信**”复选框。
    
   - 若要为策略启用或禁用外部存档，请选中或清除“**存档外部通信**”复选框。
    
6. 单击“**提交**”。
    
    > [!IMPORTANT]
    > 用户策略的设置仅适用于要应用该策略的特定用户和用户组。 有关详细信息，请参阅[应用到 Skype 业务服务器中的用户存档策略](apply-a-policy-to-users.md)。 
  
## <a name="change-archiving-policies-by-using-windows-powershell"></a>使用 Windows PowerShell 更改存档策略

您也可以使用 Windows PowerShell **Set-CsArchivingPolicy** cmdlet 更改存档策略。
  
### <a name="enable-archiving-policies"></a>启用存档策略

要启用内部通信会话的存档，请将 ArchiveInternal 参数的值设置为 True ($True)： 
  
```
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True
```

要启用外部通信会话的存档，请将 ArchiveExternal 数的值设置为 True ($True)： 
  
```
Set-CsArchivingPolicy -Identity "global" -ArchiveExternal $True
```

若要启用这两个内部和外部通信会话的存档，设置为 True 的 ArchiveInternal 和 ArchiveExternal 参数的值： 
  
```
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True
```

### <a name="disable-archiving-policies"></a>禁用存档策略

要禁用全部存档，请将 ArchiveInternal 和 ArchiveExternal 参数的值设置为 False ($False)： 
  
```
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $False -ArchiveExternal $False
```