---
title: 在 Skype for Business Server 2015 中更改现有存档策略
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4cf600be-ba3d-4bce-aa22-e158b9ccf8a9
description: 摘要： 了解如何更改用户的业务服务器 2015 Skype 的存档策略。
ms.openlocfilehash: f03ddc0799868e825c46fad2f93ba93d3b8a071a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="change-an-existing-archiving-policy-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中更改现有存档策略
 
**摘要：**了解如何更改用户的业务服务器 2015 Skype 的存档策略。
  
当您第一次部署业务服务器 2015 Skype 时，您设置初始归档策略，用以确定如何归档为您部署中的用户实现。 本主题介绍了如何管理和修订策略。 
  
## <a name="change-archiving-policies-by-using-the-control-panel"></a>使用控制面板更改存档策略

1. 使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。 
    
2. 打开浏览器窗口，然后输入管理员 URL 打开 Skype 业务服务器控件面板。 
    
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
    > 用户策略的设置仅适用于要应用该策略的特定用户和用户组。 有关详细信息，请参阅[应用中业务服务器 2015年的 Skype 用户的存档策略](apply-a-policy-to-users.md)。 
  
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

要启用这两个内部和外部通信会话存档，请使用 ArchiveInternal 和 ArchiveExternal 参数的值设置为 True: 
  
```
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True

```

### <a name="disable-archiving-policies"></a>禁用存档策略

要禁用全部存档，请将 ArchiveInternal 和 ArchiveExternal 参数的值设置为 False ($False)： 
  
```
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $False -ArchiveExternal $False

```